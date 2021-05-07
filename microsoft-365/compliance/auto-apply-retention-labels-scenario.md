---
title: Hantera livscykeln för dokument som lagras i SharePoint med hjälp av kvarhållningsetiketter
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Information om hur du kan använda kvarhållningsetiketter för att hantera livscykeln för dokument i SharePoint med hjälp av metadata för att klassificera innehåll, automatiskt tillämpa etiketterna och använda händelsebaserad kvarhållning för att starta kvarhållningsperioden.
ms.openlocfilehash: 6c58658378fd0def9a56783e7b8b35db3323b135
ms.sourcegitcommit: 8998f70d3f7bd673f93f8d1cf12ce981b1b771c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "52162330"
---
# <a name="use-retention-labels-to-manage-the-lifecycle-of-documents-stored-in-sharepoint"></a>Hantera livscykeln för dokument som lagras i SharePoint med hjälp av kvarhållningsetiketter

>*[Licensieringsvägledning för Microsoft 365 för säkerhet och efterlevnad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

I den här artikeln beskrivs hur du kan hantera livscykeln för dokument som lagras i SharePoint genom att använda automatiskt tillämpade kvarhållningsetiketter och händelsebaserad kvarhållning.

Funktionen för automatisk tillämpning använder SharePoint-metadata för dokumentklassificering. Exemplet i den här artikeln gäller produktrelaterade dokument, men samma koncept kan användas för andra scenarier. Inom olje- och gasindustrin kan det till exempel används till att hantera livscykeln för dokument om fysiska tillgångar som oljeplattformar, borrhålsloggar eller produktionslicenser. I finansiella tjänster kan det användas till att hantera dokument för bankkonton, huslån eller försäkringsavtal. Och inom den offentliga sektorn kan du hantera dokument som bygglov eller skatteblanketter.

I den här artikeln ska vi titta närmare på informationsarkitekturen och definitionen av kvarhållningsetiketterna. Sedan klassificerar vi dokument genom att automatiskt tillämpa etiketterna. Slutligen genererar vi de händelser som startar kvarhållningsperioden.

## <a name="information-architecture"></a>Informationsarkitektur

I vårt scenario använder ett tillverkningsföretag SharePoint för att lagra alla dokument om de produkter som företaget utvecklar. Dessa dokument omfattar produktspecifikationer, avtal med leverantörer och användarhandböcker. När dessa dokument lagras i SharePoint via principer för innehållshantering för företag definieras dokumentmetadata som används för att klassificera dem. Varje dokument har följande metadataegenskaper:

- **Doc Type** (till exempel produktspecifikation, avtal eller användarhandbok)

- **Produktnamn**

- **Status** (utkast eller slutgiltig)

Dessa metadata utgör en basinnehållstyp som kallas *produktionsdokument* för alla dokument.

![Tabell över metadata för produktdokumentation](../media/SPRetention1.png)

> [!NOTE]
> Senare i det här scenariot använder kvarhållningsprinciperna egenskaperna **Doc Type** och **Status** för att klassificera och automatiskt tillämpa kvarhållningsetiketter.

Vi kan ha flera innehållstyper som representerar olika typer av dokument, men nu ska vi fokusera på produktdokumentationen.

I det här scenariot använder vi tjänsten Hanterade metadata och termlagringsplatsen för att skapa en termuppsättning för *Doc Type* och en annan för *Produktnamn*. För varje termuppsättning skapar vi en term för varje värde. Det skulle se ut ungefär så här i termlagringsplatsen för SharePoint-organisationen:

![Exempel på termuppsättning för produktdokumentation i termlagringsplatsen](../media/SPRetention2.png)

Du kan skapa och publicera en *innehållstyp* med hjälp av [innehållstypsnavet](https://support.office.com/article/manage-content-type-publishing-06f39ac0-5576-4b68-abbc-82b68334889b). Du kan också skapa och publicera en innehållstyp med hjälp av verktyg för webbplatsetablering som [PnP Provisioning Framework](/sharepoint/dev/solution-guidance/pnp-provisioning-framework) eller [site design JSON schema](/sharepoint/dev/declarative-customization/site-design-json-schema#define-a-new-content-type).

Varje produkt har en dedikerad SharePoint-webbplats som innehåller ett dokumentbibliotek med rätt innehållstyper aktiverade. Alla dokument lagras i det här dokumentbiblioteket.

[ ![Dokumentbibliotek för produktdokumentation](../media/SPRetention3.png) ](../media/SPRetention3.png#lightbox)

> [!NOTE]
> I stället för att ha en SharePoint-webbplats per produkt skulle tillverkningsföretaget i det här scenariot kunna använda ett Microsoft Team per produkt så att alla i teamet kan samarbeta, till exempel via fortlöpande chatt, och använda fliken **Filer** i Teams för dokumenthantering. I den här artikeln fokuserar vi bara på dokument, så vi använder bara en webbplats.

Här är en vy över dokumentbiblioteket för produkten Spinning Widget:

[ ![Dokumentbibliotek för Spinning Widget](../media/SPRetention4.png) ](../media/SPRetention4.png#lightbox)

Nu när vi har den grundläggande informationsarkitekturen för dokumenthantering på plats kan vi ta en titt på kvarhållnings- och borttagningsstrategin för dokument som använder metadata och hur vi klassificerar dessa dokument.

## <a name="retention-and-disposition"></a>Kvarhållning och borttagning

Tillverkningsföretagets efterlevnads- och datastyrningsprinciper bestämmer hur data bevaras och kasseras. Produktrelaterade dokument måste bevaras så länge produkten tillverkas och sedan ytterligare en viss tid. Denna tidsperiod är olika för produktspecifikationer, avtal och användarhandböcker. Följande tabell anger kraven för kvarhållning och borttagning:

|   Dokumenttyp            |   Kvarhållning                            |   Borttagning                                |
| -------------------------- | -------------------------------------- | -------------------------------------------- |
| Produktspecifikationer      | Fem år efter avslutad produktion  | Ta bort                                       |
| Produktavtal          | Tio år efter avslutad produktion | Granska                                       |
| Användarhandböcker                | Fem år efter avslutad produktion  | Ta bort                                       |
| Alla andra typer av dokument | Behåll inte aktivt  | Ta bort när dokumentet är äldre än 3 år <br /><br /> Ett dokument anses vara äldre än 3 år om det inte har ändrats under de senaste 3 åren. |
|||

Vi använder Microsoft 365 Efterlevnadscenter för att skapa följande [kvarhållningsetiketter](retention.md#retention-labels):

  - Produktspecifikation

  - Produktavtal

  - Användarhandbok

I den här artikeln visar vi bara hur du skapar och automatiskt tillämpar kvarhållningsetiketten för produktspecifikation. Om du vill implementera hela scenariot kan du också skapa och automatiskt tillämpa kvarhållningsetiketter för de andra två dokumenttyperna.

### <a name="settings-for-the-product-specification-retention-label"></a>Inställningar för kvarhållningsetikett för produktspecifikation

Här är [filplanen](file-plan-manager.md) för kvarhållningsetiketten för produktspecifikation:

- **Namn:** Produktspecifikation

- **Beskrivning för användare:** bevara i 5 år efter avslutad produktion.

- **Beskrivning för administratörer:** bevara i fem år efter avslutad produktion, ta bort automatiskt, händelsebaserad kvarhållning, händelsetypen är *produktupphörande*.

- **Bevarandeåtgärd:** Bevara och ta bort.

- **Kvarhållningsperiod:** 5 år (1 825 dagar).

- **Postetikett**: Konfigurera kvarhållningsetiketten så att objekt markeras som en [arkivhandling](records-management.md#records), vilket innebär att de märkta dokumenten inte kan ändras eller tas bort av användare.

- **Filplansbeskrivningar:** För enkelhetens skull används inga valfria filbeskrivningar i det här scenariot.

Följande skärmbild visar inställningarna när du skapar en kvarhållningsetikett för produktspecifikation i Microsoft 365 Efterlevnadscenter. Du kan skapa händelsetypen *Produktupphörande* när du skapar kvarhållningsetiketten. Se proceduren i följande avsnitt.

![Kvarhållningsinställningar för produktspecifikationsetiketten](../media/SPRetention5.png)

> [!NOTE]
> Om du vill undvika en väntetid på 5 år för borttagning av dokumentet anger du kvarhållningsperioden till ***1 dag*** om du återskapar det här scenariot i en testmiljö.

### <a name="create-an-event-type-when-you-create-a-retention-label"></a>Skapa en händelsetyp när du skapar en kvarhållningsetikett

1. Efter **Start the retention period based on** (Starta kvarhållningsperioden baserat på) på sidan **Define retention settings** (Definiera kvarhållningsinställningar) i guiden Skapa kvarhållningsetikett väljer du **Create new event type** (Skapa ny händelsetyp):
    
    ![Skapa en ny händelsetyp för dialogrutan för produktspecifikationsetikett](../media/SPRetention6.png)

3. På sidan **Name your event type** (Namnge din händelsetyp) anger du **Product Cessation** (Produktupphörande) och en valfri beskrivning. Välj sedan **Nästa**, **Skicka** och **Klart**.

4. Tillbaka på sidan **Define retention settings** (Definiera kvarhållningsinställningar) väljer du händelsetypen **Produktupphörande** (som du skapade) i **Start the retention period based on** (Starta kvarhållningsperioden baserat på).
    
    Så här ser inställningar ut för kvarhållningsetiketten för produktspecifikation: 
    
   ![Inställningar för den nya produktspecifikationsetiketten](../media/SPRetention7.png)

6. Välj **Skapa etikett**. På nästa sida ser du alternativen för att publicera etiketten, tillämpa den automatiskt eller bara spara etiketten: Välj **Just save the label for now** (Spara bara etiketten för tillfället) och välj sedan **Klar**. 
    
    > [!TIP]
    > Mer detaljerade anvisningar finns i [Skapa en etikett vars kvarhållningstid baseras på en händelse](event-driven-retention.md#step-1-create-a-label-whose-retention-period-is-based-on-an-event).

Nu ska vi titta närmare på hur vi tillämpar kvarhållningsetiketten automatiskt på innehåll i produktspecifikationer.

## <a name="auto-apply-retention-labels-to-documents"></a>Tillämpa kvarhållningsetiketter automatiskt för dokument

Vi kommer att använda KQL (Keyword Query Language) för att [automatiskt tillämpa](apply-retention-labels-automatically.md) de kvarhållningsetiketter som vi har skapat. KQL är det språk som används för att skapa sökfrågor. I KQL kan söka du med nyckelord eller hanterade egenskaper. Mer information finns i [syntaxreferensen för KQL (Keyword Query Language)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).

Vi vill säga till Microsoft 365 att vi vill "tillämpa kvarhållningsetiketten **Produktspecifikation** för alla dokument som har **statusen** **Slutgiltig** och **dokumenttypen** **Produktspecifikation**." **Status** och **Doc Type** är som du kanske minns de webbplatskolumner som vi definierade för innehållstypen Produktdokumentation i avsnittet [Informationsarkitektur](#information-architecture). För att göra det måste vi konfigurera sökschemat.

När SharePoint indexerar innehåll genereras automatiskt crawlade egenskaper för varje webbplatskolumn. I det här scenariot är vi intresserade av egenskaperna **Doc Type** och **Status**. För att skapa de crawlade egenskaperna behöver vi dokument i biblioteket som har rätt innehållstyp och som har ifyllda webbplatskolumner för sökning.

I administrationscentret för SharePoint öppnar du Sökkonfiguration och väljer **Hantera schemasökning** för att visa och konfigurera de crawlade egenskaperna.

![Crawlade egenskaper i sökschemat](../media/SPRetention8.png)

Om vi skriver ***status** _ i rutan _ *Crawlade egenskaper** och väljer den gröna pilen bör resultatet bli så här:

![Den crawlade egenskapen ows_Status](../media/SPRetention9.png)

Egenskapen **ows\_\_Status** (observera det dubbla understrecket) är den som vi är intresserade av. Den mappar till egenskapen **Status** för innehållstypen Produktionsdokument.

Om vi nu skriver ***ows\_doc*** och väljer den gröna pilen, bör vi se något som ser ut så här:

![Den crawlade egenskapen ows_Doc_Type](../media/SPRetention10.png)

Egenskapen **ows\_Doc\_x0020\_Type** är den andra egenskapen som vi är intresserade av. Den mappar till egenskapen **Status** för innehållstypen Produktionsdokument.

> [!TIP]
> Om du vill ta reda på namnet på en crawlad egenskap i det här scenariot går du till dokumentbiblioteket som innehåller produktionsdokumenten. Gå sedan till biblioteksinställningarna. För **Kolumner** väljer du namnet på kolumnen (till exempel **Status** eller **Doc Type**) för att öppna webbplatskolumnsidan. Parametern *Field* i URL-adressen för sidan innehåller namnet på fältet. Det här fältnamnet, med prefixet ”ows_”, är namnet på den crawlade egenskapen. URL-adressen `https://tenantname.sharepoint.com/sites/SpinningWidget/_layouts/15/FldEdit.aspx?List=%7BC38C2F45-3BD6-4C3B-AA3B-EF5DF6B3D172%7D&Field=_Status` motsvarar till exempel den crawlade egenskapen *ows\_\_Status*.

Om de crawlade egenskaper du letar efter inte visas i avsnittet Hantera schemasökning i administrationscentret för SharePoint:

- Det kan hända att dokumenten inte har indexerats. Du kan tvinga fram en omindexering av biblioteket genom att gå till **Inställningar för dokumentbibliotek** > **Avancerade inställningar**.

- Om dokumentbiblioteket finns på en modern webbplats kontrollerar du att SharePoint-administratören även är webbplatssamlingsadministratör.

Mer information om crawlade och hanterade egenskaper finns i [Automatiskt skapade hanterade egenskaper i SharePoint Server](/sharepoint/technical-reference/automatically-created-managed-properties-in-sharepoint).

### <a name="map-crawled-properties-to-pre-defined-managed-properties"></a>Mappa crawlade egenskaper till fördefinierade hanterade egenskaper

KQL kan inte använda crawlade egenskaper i sökfrågor. Du måste använda en hanterad egenskap. I ett normalt sökscenario skapar vi en hanterad egenskap och mappar den till den crawlade egenskapen som vi behöver. Men för automatisk tillämpning av kvarhållningsetiketter kan du bara ange fördefinierade hanterade egenskaper i KQL, inte anpassade hanterade egenskaper. Det finns en uppsättning fördefinierade hanterade egenskaper i systemet för sträng *RefinableString00* till *RefinableString199* som du kan använda. En fullständig lista finns i [Oanvända hanterade egenskaper (standard)](/sharepoint/manage-search-schema#default-unused-managed-properties). De här standardegenskaperna används vanligtvis för att definiera sökförfining.

För att KQL-frågan ska kunna tillämpa rätt kvarhållningsetikett automatiskt för produktdokumentinnehåll mappar vi de crawlade egenskaperna **ows\_Doc\_x0020\_Type* och *ows\_\_Status** till två begränsningsbara hanterade egenskaper. I testmiljön för det här scenariot används inte **RefinableString00** och **RefinableString01**. Vi fastställde detta genom att titta på **Hanterade egenskaper** i **Hantera schemasökning** i administrationscentret för SharePoint.

[ ![Hanterade egenskaper i sökschemat](../media/SPRetention12.png) ](../media/SPRetention12.png#lightbox)

Observera att kolumnen **Mappade crawlade egenskaper** på föregående skärmbild är tom.

Så här mappar du den crawlade egenskapen **ows\_Doc\_x0020\_Type**:

1. I filterrutan **Hanterad egenskap** skriver du **_RefinableString00_** och väljer den gröna pilen.

2. Välj länken **RefinableString00** i resultatlistan och rulla sedan ned till avsnittet **Mappningar till crawlade egenskaper**.  

3. Välj **Lägg till en mappning** och skriv sedan **_ows\_Doc\_x0020\_Type_*_ i rutan _* Sök efter crawlade egenskapsnamn** i fönstret **Välj crawlad egenskap**. Välj **Sök**.  

4. I resultatlistan väljer du **ows\_Doc\_x0020\_Type** och sedan **OK**.

   I avsnittet **Mappade crawlade egenskaper** bör du se något som liknar den här skärmbilden:

   [ ![Välj Lägg till en mappning i avsnittet Mappade crawlade egenskaper](../media/SPRetention13.png) ](../media/SPRetention13.png#lightbox)


5. Rulla längst ned på sidan och välj **OK** om du vill spara mappningen.

Upprepa de här stegen för att mappa **RefinableString01** och **ows\_\_Status**.

Nu ska du ha två hanterade egenskaper mappade till två crawlade egenskaper:

[ ![Hanterade egenskaper mappade till crawlade egenskaper](../media/SPRetention14.png) ](../media/SPRetention14.png#lightbox)

Vi kontrollerar att konfigurationen är korrekt genom att köra en företagssökning. Gå till *https://\<your_tenant>.sharepoint.com/search* i en webbläsare. I sökrutan skriver du ***RefinableString00:"Produktspecifikation"** _ och trycker på Retur. Den här sökningen ska returnera alla dokument som har **_dokumenttypen_** _ *Produktspecifikation**.

Skriv **RefinableString00:"Produktspecifikation" AND RefinableString01:Slutgiltig** i sökrutan och tryck på Retur. Då returneras alla dokument som har **_dokumenttypen_*_ **Produktspecifikation** och _* statusen** **_Slutgiltig_**.

### <a name="create-auto-apply-label-policies"></a>Skapa principer för automatisk tillämpning av etiketter

Nu när vi har kontrollerat att KQL-frågan fungerar ska vi skapa en princip för automatisk etikettillämpning som använder en KQL -fråga för att automatiskt tillämpa kvarhållningsetiketten Produktspecifikation för lämpliga dokument.

1. I [efterlevnadscentret](https://compliance.microsoft.com/homepage) går du till **Hantering av arkivhandlingar** > **Etikettprinciper** > **Använd en etikett automatiskt**.

   [ ![Välj ”Använd en etikett automatiskt” på sidan Etiketter](../media/SPRetention16.png) ](../media/SPRetention16.png#lightbox)

2. På sidan för att **namnge principen för automatisk etikettering** i guiden för att skapa princip för automatisk etikettering anger du ett namn, till exempel **Automatisk tillämpning av etiketten Produktspecifikation**, och anger en beskrivning (valfritt). Välj sedan **Nästa**.

3. Välj **Tillämpa etiketten på innehåll som innehåller specifika ord eller fraser, eller egenskaper** på sidan **Välj den typ av innehåll du vill använda etiketten med** och välj sedan **Nästa**.
    
   [ ![Välj Tillämpa etiketten på innehåll som innehåller specifika ord eller fraser, eller egenskaper](../media/SPRetention17.png) ](../media/SPRetention17.png#lightbox)
    
   Med det här alternativet kan vi ange samma KQL-sökfråga som vi testade i föregående avsnitt. Frågan returnerar alla produktspecifikationsdokument som har statusen *Slutgiltig*. När vi använder samma fråga i principen för automatisk etikettillämpning tillämpas kvarhållningsetiketten Produktspecifikation automatiskt för alla dokument som matchar den.

4. På sidan **Använd etiketten på innehåll som matchar den här frågan** skriver du **RefinableString00:"Produktspecifikation" AND RefinableString01:Slutgiltig** och väljer sedan **Nästa**.

   ![Ange frågan i rutan Frågeredigerare för nyckelord](../media/SPRetention19.png)

5. På sidan **Välj platser där principen ska tillämpas** väljer du de innehållsplatser där principen ska tillämpas. I det här scenariot tillämpar vi principen endast på SharePoint-webbplatser eftersom alla produktionsdokument lagras i SharePoint-dokumentbibliotek. Växla status för **Exchange-e-post**, **OneDrive-konton** och **Microsoft 365-grupper** till **Av**. Kontrollera att statusen för SharePoint-webbplatser är inställd på **På** innan du väljer **Nästa**: 
    
    ![Välj de specifika webbplatser där etiketter ska tillämpas automatiskt](../media/SPRetentionSPlocations.png)
    
   > [!TIP]
   > I stället för att använda principen på alla SharePoint-webbplatser kan du välja **Välj webbplats** och lägga till URL-adresser för specifika SharePoint-webbplatser.

6. På sidan **Välj etikett att tillämpa automatiskt** väljer du **Lägg till etikett**.

7. Välj **Produktspecifikation** i listan med kvarhållningsetiketter. Välj sedan **Lägg till** och **Nästa**.

8. Granska dina inställningar:

    ![Inställningar för automatisk tillämpning av etiketten](../media/SPRetention18.png)

9. Välj **Skicka** för att skapa principen för automatisk etikettillämpning.
    
   >[!NOTE]
   >Det tar upp till sju dagar att automatiskt tillämpa etiketten Produktspecifikation på alla dokument som matchar KQL-sökfrågan.

### <a name="verify-that-the-retention-label-was-automatically-applied"></a>Kontrollera att kvarhållningsetiketten tillämpats automatiskt

Efter sju dagar använder du [aktivitetsutforskaren](data-classification-activity-explorer.md) i efterlevnadscentret för att kontrollera att principen för automatisk etikettillämpning som vi skapade tillämpar kvarhållningsetiketterna automatiskt på produktdokumenten.

Titta också på egenskaperna för dokumenten i dokumentbiblioteket. På informationspanelen kan du se om kvarhållningsetiketten används i ett valt dokument.

[ ![Kontrollera att etiketten tillämpas genom att titta på dokumentegenskaperna i dokumentbiblioteket](../media/SPRetention21.png) ](../media/SPRetention21.png#lightbox)

Eftersom kvarhållningsetiketterna tillämpas automatiskt på dokument skyddas dessa dokument från att tas bort eftersom kvarhållningsetiketten har konfigurerats för att deklarera dokumenten som *arkivhandlingar*. Ett exempel på det här skyddet är att vi får följande felmeddelande när vi försöker ta bort något av dessa dokument:

[ ![Ett felmeddelande visas som anger att dokument inte kan tas bort eftersom etiketten deklarerar att dokumenten är arkivhandlingar.](../media/SPRetention22.png) ](../media/SPRetention22.png#lightbox)

## <a name="generate-the-event-that-triggers-the-retention-period"></a>Generera den händelse som utlöser kvarhållningsperioden

Nu när kvarhållningsetiketterna används kan vi fokusera på händelsen som indikerar upphörande av produktion för en viss produkt. Den här händelsen utlöser starten på den kvarhållningsperiod som har definierats i kvarhållningsetiketterna. För produktspecifikationsdokument börjar till exempel den femåriga kvarhållningsperioden när händelsen ”upphörande av produktion” utlöses.

Du kan skapa händelsen manuellt i Microsoft 365 Efterlevnadscenter genom att gå till **Hantering av arkivhandlingar** > **Händelser**. Sedan väljer du händelsetyp, anger rätt tillgångs-ID:n och anger ett datum för händelsen. Mer information finns i [Starta kvarhållning när en händelse inträffar](event-driven-retention.md).

Men i det här scenariot genererar vi automatiskt händelsen från ett externt produktionssystem. Systemet är en enkel SharePoint-lista som anger om en produkt är i produktion eller inte. Ett [Power Automate](/flow/getting-started)-flöde som är kopplat till listan utlöser händelsen. I ett verkligt scenario kan du använda olika system för att generera händelsen, till exempel ett HR- eller CRM-system. Power Automate innehåller många färdiga interaktioner och byggblock för Microsoft 365-arbetsbelastningar, till exempel Microsoft Exchange, SharePoint, Teams och Dynamics 365, samt appar från tredje part som Twitter, Box, Salesforce och Workdays. Den här funktionen gör det enkelt att integrera Power Automate med olika system. Mer information finns i [Automatisera händelsebaserad kvarhållning](./event-driven-retention.md#automate-events-by-using-a-rest-api).

Följande skärmbild visar SharePoint-listan som används för att utlösa händelsen:

[ ![Listan som utlöser kvarhållningshändelsen](../media/SPRetention23.png) ](../media/SPRetention23.png#lightbox)

Det finns två produkter som för närvarande är i produktion, vilket anges av ***Ja** _ i kolumnen _ *I produktion**. När värdet i den här kolumnen är inställt på **_Nej_** för en produkt genereras händelsen automatiskt av det flöde som är kopplat till listan. Händelsen utlöser starten på kvarhållningsperioden för den kvarhållningsetikett som tillämpades automatiskt för motsvarande produktdokument.

I det här scenariot använder vi följande flöde för att utlösa händelsen:

[ ![Konfigurera flödet som ska utlösa händelsen](../media/SPRetention24.png) ](../media/SPRetention24.png#lightbox)

Om du vill skapa det här flödet utgår du från en SharePoint-anslutningsapp och väljer utlösaren **När ett objekt skapas eller ändras**. Ange webbplatsadressen och listnamnet. Lägg sedan till ett villkor baserat på när kolumnvärdet för listan **I produktion** är inställt på **_Nej_* _ (eller lika med _false* på villkorskortet). Lägg sedan till en åtgärd baserat på den inbyggda HTTP-mallen. Använd värdena i följande avsnitt för att konfigurera HTTP-åtgärden. Du kan kopiera värdena för egenskaperna **URI** och **Body** från följande avsnitt och klistra in dem i mallen.

- **Method**: POST
- **URI**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`
- **Headers**: Key = Content-Type, Value = application/atom+xml
- **Body**:
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'>
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices' xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata' xmlns='https://www.w3.org/2005/Atom'>
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent'>
    <updated>9/9/2017 10:50:00 PM</updated>
    <content type='application/xml'>
    <m:properties>
    <d:Name>Cessation Production @{triggerBody()?['Product_x0020_Name']?['Value']}</d:Name>
    <d:EventType>Product Cessation&lt;</d:EventType>
    <d:SharePointAssetIdQuery>ProductName:&quot;@{triggerBody()?['Product_x0020_Name']?['Value']}<d:SharePointAssetIdQuery>
    <d:EventDateTime>@{formatDateTime(utcNow(),'yyyy-MM-dd')}</d:EventDateTime>
    </m:properties>
    </content&gt>
    </entry>
    ```

I den här listan beskrivs parametrarna i egenskapen **Body** för den åtgärd som måste konfigureras för det här scenariot:

- **Name**: Den här parametern anger namnet på händelsen som kommer att skapas i Microsoft 365 Efterlevnadscenter. I det här scenariot är namnet “Cessation Production *xxx*", där *xxx* är värdet för den hanterade egenskapen **ProductName** som vi skapade tidigare.
- **EventType**: Värdet för den här parametern motsvarar den händelsetyp som den skapade händelsen gäller för. Den här händelsetypen definierades när du skapade kvarhållningsetiketten. I det här scenariot är händelsetypen ”Produktupphörande”.
- **SharePointAssetIdQuery**: Den här parametern definierar tillgångs-ID:t för händelsen. För händelsebaserad kvarhållning behövs ett unikt ID för dokumentet. Vi kan använda tillgångs-ID:n för att identifiera dokument som en viss händelse gäller för eller, som i det här scenariot, metadatakolumnen **Produktnamn**. För att göra det måste vi skapa en ny hanterad egenskap, **ProductName**, som kan användas i KQL-frågan. (Du kan också använda **RefinableString00** i stället för att skapa en ny hanterad egenskap). Vi måste också mappa den nya hanterade egenskapen till den crawlade egenskapen **ows_Product_x0020_Name**. Här är en skärmbild av den här hanterade egenskapen.

    [ ![Hanterad egenskap för kvarhållning](../media/SPRetention25.png) ](../media/SPRetention25.png#lightbox)

- **EventDateTime**: Den här parametern definierar datumet då händelsen inträffar. Använd formatet för aktuellt datum:<br/><br/>*formatDateTime(utcNow(),'yyyy-MM-dd'*)

### <a name="putting-it-all-together"></a>Sammanställa allt

Nu har kvarhållningsetiketten skapats och tillämpas automatiskt, och flödet har konfigurerats och skapats. När värdet i kolumnen **I produktion** för produkten Spinning Widget i produktlistan ändras från **_Ja_*_ till _*_Nej_*_ utlöser flödet skapandet av händelsen. Om du vill se händelsen i efterlevnadscentret går du till _* Hantering av arkivhandlingar** > **Händelser**.

[ ![Händelsen som utlöstes av flödet visas på sidan Händelser i efterlevnadscentret.](../media/SPRetention28.png) ](../media/SPRetention28.png#lightbox)

Välj händelsen om du vill visa informationen på den utfällbara sidan. Observera att även om händelsen skapas så visar händelsestatusen att inga SharePoint-webbplatser eller -dokument har bearbetats.

![Händelseinformation](../media/SPRetention29.png)

Men efter en fördröjning visas händelsestatusen att en SharePoint-webbplats och ett SharePoint-dokument har bearbetats.  

![Händelseinformation som visar att dokument har bearbetats.](../media/SPRetention31.png)
 
Du kan se att kvarhållningsperioden för etiketten som används för produktdokumentet Spinning Widget har startats baserat på händelsedatumet för händelsen *Cessation Production Spinning Widget*. Om du implementerade scenariot i din testmiljö genom att konfigurera en kvarhållningsperiod på en dag kan du gå till dokumentbiblioteket för dina produktdokument ett par dagar efter händelsen skapades och kontrollera att dokumentet har tagits bort (efter att borttagningsjobbet i SharePoint har körts).

### <a name="more-about-asset-ids"></a>Mer om tillgångs-ID:n

Som det står i artikeln [Starta kvarhållning när en händelse inträffar](event-driven-retention.md) är det viktigt att förstå relationen mellan händelsetyper, kvarhållningsetiketter och tillgångs-ID:n. Tillgångs-ID är bara en dokumentegenskap i SharePoint och OneDrive. Med tillgångs-ID:t kan du identifiera de dokument vars kvarhållningsperiod ska utlösas av händelsen. Som standard finns en **tillgångs-ID**-egenskap i SharePoint som du kan använda för händelsebaserad kvarhållning:

![Tillgångs-ID-egenskapen visas på en sida med information om dokumentegenskaper.](../media/SPRetention26.png)

Som följande skärmbild visar heter den hanterade tillgångs-ID-egenskapen **ComplianceAssetId**.

[ ![Den hanterade egenskapen ComplianceAssetId](../media/SPRetention27.png) ](../media/SPRetention27.png#lightbox)

Du måste inte använda **tillgångs-ID**-standardegenskapen som vi gör i det här scenariot. Du kan använda vilken annan egenskap du vill. Men det är viktigt att förstå att om du inte anger ett tillgångs-ID eller nyckelord för en händelse utlöser händelsen kvarhållningsperioden för allt innehåll som har en etikett av den händelsetypen.

### <a name="using-advanced-search-in-sharepoint"></a>Använda avancerad sökning i SharePoint

På den föregående skärmbilden kan du se att det finns en annan hanterad egenskap kopplad till kvarhållningsetiketter som heter **ComplianceTag** och som är mappad till en crawlad egenskap. Den hanterade egenskapen **ComplianceAssetId** är också mappad till en crawlad egenskap. Det innebär att du kan använda de här hanterade egenskaperna i avancerad sökning för att hämta alla dokument som har taggats med en kvarhållningsetikett.