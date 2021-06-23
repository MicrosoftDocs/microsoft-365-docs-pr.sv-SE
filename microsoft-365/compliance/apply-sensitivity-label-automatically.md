---
title: Använda en känslighetsetikett för innehåll automatiskt i Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: När du skapar en känslighetsetikett kan du automatiskt tilldela filer och e-postmeddelanden en etikett, eller så kan du uppmana användarna att välja den etikett som du rekommenderar.
ms.openlocfilehash: 77834c71c7df9f5a460533f1a06878e0e3e38145
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53061893"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a>Använda en känslighetsetikett för innehåll automatiskt

>*[Licensieringsvägledning för Microsoft 365 för säkerhet och efterlevnad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Information om omfattningen om hur du automatiskt använder en känslighetsetikett i Azure Purview (förhandsversion) finns i [Märka innehållet i Azure Purview automatiskt](/azure/purview/create-sensitivity-label).

När du skapar en känslighetsetikett kan du tilldela etiketten automatiskt till fler och e-post, när det matchar de villkor du anger.

Det är viktigt att använda känsliga etiketter för innehåll automatiskt eftersom:

- Du behöver inte träna dina användare när de använder var och en av dina klassificeringar.

- Du behöver inte förlita dig på att användare ska klassificera allt innehåll på rätt sätt.

- Användarna behöver inte längre veta om dina principer – de kan istället fokusera på sitt arbete.

När innehållet har etiketterats manuellt kommer den etiketten aldrig att ersättas med automatisk etikett. Automatisk etikettering kan ersätta en [etikett med lägre prioritet](sensitivity-labels.md#label-priority-order-matters) som tillämpats automatiskt.

Det finns två olika metoder för att automatiskt använda en känslighetsetikett för innehåll i Microsoft 365:

- **Etikett på klientsidan när användare redigerar dokument eller skriver (eller svarar på eller vidarebefordrar) e-postmeddelanden**: Använd en etikett som är konfigurerad för automatisk etikettering för filer och e-postmeddelanden (inkluderar Word, Excel, PowerPoint och Outlook). 
    
    Den här metoden kan användas för att rekommendera en etikett till användare, liksom att automatiskt använda en etikett. I båda fallen bestämmer användaren om du vill acceptera eller avvisa etiketten för att säkerställa rätt etikettering av innehållet. På den här sidan i klienten finns det minimalt med dokument. det innebär att du inte kan använda etiketter. Det är dock inga klient program som har stöd för automatisk etikettering. Den här funktionen stöds av den enhetliga klient versionen av Azure information Protection och [vissa versioner av Office](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps). 
    
    Instruktioner för konfiguration finns i [hur du konfigurerar automatisk etikettering för Office-program](#how-to-configure-auto-labeling-for-office-apps) på den här sidan.

- **Etikettering på tjänstsidan när innehåll redan har sparats (i SharePoint eller OneDrive) eller mejlats (bearbetats av Exchange Online)**: Använd en princip för automatisk etikettering. 
    
    Du kanske också har hört att metoden kallas för automatisk etikettering av data i vila (dokument i SharePoint och OneDrive) och data som överförs (e-post som skickas eller tas emot av Exchange). För Exchange innehåller det inte e-postmeddelanden i vila (postlådor).
    
    Eftersom den här etiketteringen tillämpas av tjänster i stället för program behöver du inte oroa dig för vilket appanvändare har eller vilken version. Därför är den här funktionen omedelbart tillgänglig i hela organisationen och lämpar sig för etikettering vid skalan. Automatiskt märkta principer har inte stöd för Rekommenderad etikett eftersom användaren inte interagerar med namngivnings processen. I stället körs principerna i simuleringsläge för att säkerställa rätt etikettering av innehållet innan etiketten tillämpas.
    
    Instruktioner för konfiguration finns i [hur du konfigurerar principer för automatisk etikettering för SharePoint, OneDrive och Exchange](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) på den här sidan.
    
    Specifikt för autoetikettering för SharePoint och OneDrive:
    - Office-filer för Word, PowerPoint och Excel stöds. Öppna XML-format stöds (t.ex. .docx och .xlsx) men inte Microsoft Office 97-2003-format (t.ex. .doc och .xls).
        - Filerna kan märkas automatiskt före eller efter att principerna för automatisk etikettering har skapats. Filer kan inte etiketteras automatiskt om de är en del av en öppen session (filen är öppen).
        - För närvarande stöds inte bilagor till listobjekt och de kommer inte att märkas automatiskt.
    - Högst 25 000 automatiskt etiketterade filer i klientorganisationen per dag.
    - Högst tio principer för automatisk etikettering per klientorganisation, varav varje riktar sig till upp till tio webbplatser (SharePoint eller OneDrive).
    - Befintliga värden för ändrad, ändrad av och datum ändras inte på grund av principer för automatisk etikettering – det gäller både simuleringsläge och när etiketter används.
    - När etiketten tillämpar kryptering är det [utfärdaren av rättighetshantering och ägaren av rättighetshantering](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner) det konto som senast ändrade filen.

    Specifikt för automatisk etikettering för Exchange:
    - Till skillnad från manuell etikettering eller automatisk etikettering med Office-program skannas även PDF-bilagor och Office-bilagor (Word-, Excel- och PowerPoint-filer) efter de villkor som du anger i principen för automatisk etikett. När det finns en matchning etiketteras e-postmeddelandet, men inte den bifogade filen.
        - Om etiketten tillämpar kryptering för PDF-filer krypteras filerna när klientorganisationen har [aktiverats för bifogade PDF-filer](ome-faq.yml#are-pdf-file-attachments-supported-).
        - För dessa Office-filer stöds Open XML-format (till exempel .docx och .xlsx) men inte Microsoft Office 97-2003-format (t.ex. .doc och .xls). Om etiketten tillämpar kryptering krypteras filerna.
    - Om du har regler för e-postflödet i Exchange eller DLP-principer (dataförlustskydd) som tillämpar IRM-kryptering: En etikett tillämpas när innehåll identifieras av dessa regler eller principer samt en princip för automatisk etikettering. Om den etiketten tillämpar kryptering ignoreras IRM-inställningarna från Exchange-e-postflödesregler eller DLP-principer. Om etiketten inte tillämpar kryptering tillämpas IRM-inställningarna från e-postflödesregler eller DLP-principer utöver etiketten.
    - E-post som har IRM-kryptering utan etikett ersätts med en etikett med alla krypteringsinställningar när det finns en matchning genom att använda automatisk etikettering.
    - Inkommande e-post etiketteras när det finns ett samband med de villkor som gäller för automatisk etikettering:
        - Om etiketten har konfigurerats för [kryptering](encryption-sensitivity-labels.md), tillämpas inte den krypteringen.
        - Om etiketten är konfigurerad för att tillämpa [dynamiska markeringar](sensitivity-labels-office-apps.md#dynamic-markings-with-variables) bör du vara medveten om att det kan resultera i namnen på personer utanför organisationen.
    - När etiketten tillämpar kryptering är [utfärdaren av rättighetshantering och ägaren av rättighetshantering](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner) den person som skickar e-postmeddelandet. För närvarande går det inte att ställa in ägare för rättighetshantering för alla inkommande e-postmeddelanden som krypteras automatiskt.
    

## <a name="compare-auto-labeling-for-office-apps-with-auto-labeling-policies"></a>Jämföra automatisk etikettering för Office-appar med principer för automatisk etikettering

I följande tabell kan du identifiera skillnader i beteende för två kompletterande automatiska etiketteringsmetoder:

|Funktion eller beteende|Etikettinställning: Automatisk etikettering av filer och e-postmeddelanden  |Princip: Automatisk etikettering|
|:-----|:-----|:-----|
|Appberoende|[Ja](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps) |Nej \* |
|Begränsa efter plats|Nej |Ja |
|Villkor: träningsbara klassificerare|Ja |Nej |
|Villkor: Delningsalternativ och ytterligare alternativ för e-post|Nej |Ja |
|Rekommendationer, principbeskrivningar och användaråsidosättningar|Ja |Nej |
|Simuleringsläge|Nej |Ja |
|Exchange-bilagor som kontrollerats för villkor|Nej | Ja|
|Använda synliga markeringar |Ja |Ja (endast e-post) |
|Åsidosätta IRM-kryptering som används utan etikett|Ja, om användaren har den lägsta användningsrättigheten för export |Ja (endast e-post) |
|Märka inkommande e-post|Nej |Ja|

\* Automatisk etikettering är för närvarande inte tillgängligt i alla regioner. Om din klientorganisation inte har stöd för den här funktionen visas inte fliken Automatisk etikettering i administrationscentret för etiketter.

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a>Hur flera villkor utvärderas när de gäller för mer än en etikett

Etiketterna är ordnade för utvärdering enligt den position du anger i principen: Etiketten som placeras först har den lägsta positionen (minst känslig) och etiketten som är placerad sist har den högsta positionen (mest känslig). Mer information om prioritet finns i [Etikettprioritet (ordningen har betydelse)](sensitivity-labels.md#label-priority-order-matters).

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a>Konfigurera inte en överordnad etikett så att den tillämpas automatiskt eller rekommenderas

Tänk på att det inte går att använda en överordnad etikett (en etikett med underetiketter) på innehållet. Kontrollera att du inte konfigurerar en överordnad etikett som ska tillämpas automatiskt eller rekommenderas i Office-program, och välj inte en överordnad etikett för en princip för automatisk etikettering. Om du gör det används inte den överordnade etiketten på innehållet.

Om du vill använda automatisk etikettering med underetiketter måste du publicera både den överordnade etiketten och underetiketten.

Mer information om överordnade etiketter och underetiketter finns i [Underetiketter (gruppering av etiketter)](sensitivity-labels.md#sublabels-grouping-labels).

## <a name="how-to-configure-auto-labeling-for-office-apps"></a>Så här konfigurerar du automatisk etikettering för Office-appar

Automatisk etikettering i Office-appar för Windows stöds av Azure Information Protection-klienten för enhetliga etiketter. För inbyggd etikettering i Office-appar finns den här funktionen i [olika faser av tillgänglighet för olika appar](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

Inställningarna för automatisk etikettering för Office-appar är tillgängliga när du [skapar eller redigerar en känslighetsetikett](create-sensitivity-labels.md). Kontrollera att **Filer och e-postmeddelanden** är valt för etikettens omfattning: 

![Omfångsalternativ för känslighetsetiketter i filer och e-postmeddelanden](../media/filesandemails-scope-options-sensitivity-label.png)

När du förflyttar dig genom guiden ser du sidan **Automatisk etikettering för filer och e-postmeddelanden** där du kan välja från en lista med typer av känslig information eller träningsbara klassificerare:

![Etikettvillkor för automatisk etikettering i Office-appar](../media/sensitivity-labels-conditions.png)

När den här känslighetsetiketten tillämpats automatiskt ser användaren ett meddelande i Office-appen. Till exempel:

![Meddelande om att en etikett används automatiskt i ett dokument](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a>Konfigurera typer av känslig information för en etikett

När du väljer alternativet **Typer av känslig information** visas samma lista över typer av känslig information som när du skapar en DLP-princip (dataförlustskydd). Du kan t.ex. automatiskt tillämpa en strikt konfidentiell etikett på allt innehåll som innehåller kundernas personliga uppgifter, som kreditkortsnummer, personnummer eller passnummer:

![Typer av känslig information för automatisk etikettering i Office-appar](../media/sensitivity-labels-sensitive-info-types.png)

På samma sätt som när du konfigurerar DLP-principer kan du sedan förfina villkoret genom att ändra antalet instanser och matcha noggrannheten. Till exempel:

![Alternativ för att matcha noggrannhet och antal instanser](../media/sit-confidence-level.png)

Mer information om de här konfigurationsalternativen från DLP-dokumentationen finns här: [Justera regler för att göra dem enklare eller svårare att matcha](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).

Precis som med DLP-principkonfigurationen kan du också välja om ett villkor ska identifiera alla typer av känslig information eller bara en av dem. Om du vill göra villkoren mer flexibla eller komplexa kan du lägga till [grupper och använda logiska operatorer mellan grupperna](data-loss-prevention-policies.md#grouping-and-logical-operators).

### <a name="configuring-trainable-classifiers-for-a-label"></a>Konfigurera träningsbara klassificerare för en etikett

Det här alternativet är en förhandsversion. Om du använder det här alternativet ska du kontrollera att du har publicerat minst en annan känslighetsetikett som har konfigurerats för automatisk etikettering och alternativet [Typer av känslig information](#configuring-sensitive-info-types-for-a-label).

När du väljer **träningsbara klassificerare** väljer du en eller flera av de inbyggda klassificerarna från Microsoft. Om du har skapat egna anpassade träningsbara klassificerare går de också att välja:

![Alternativ för träningsbara klassificerare och känslighetsetiketter](../media/sensitivity-labels-classifers.png)

> [!CAUTION]
> Vi håller på att dra tillbaka den inbyggda klassificeraren för **stötande språk** eftersom den har gett ett stort antal falska positiva identifieringar. Använd inte den här inbyggda klassificeraren, och om du använder den just nu bör du flytta bort affärsprocesserna från den. Vi rekommenderar att du använder de inbyggda klassificerarna för **riktade trakasserier**, **svordomar** och **hot** istället.

Mer information om dessa klassificerare finns i [Mer information om utbildningsbara klassificerare](classifier-learn-about.md).

Under förhandsversionsperioden för det här alternativet har följande appar stöd för träningsbara klassificerare för känslighetsetiketter:

- Microsoft 365-appar för företag ([tidigare Office 365 ProPlus](/deployoffice/name-change)) för Windows lanseras nu för [Aktuell kanal](/deployoffice/overview-update-channels#current-channel-overview) i version 2006 och senare:
    - Word
    - Excel
    - PowerPoint

- Office på webben-appar, när du har [aktiverade känslighetsetiketter för Office-filer i SharePoint och OneDrive](sensitivity-labels-sharepoint-onedrive-files.md):
    - Word
    - Excel
    - PowerPoint
    - Outlook

### <a name="recommend-that-the-user-applies-a-sensitivity-label"></a>Rekommendera att användaren tillämpar en känslighetsetikett

Om du föredrar det kan du rekommendera att användarna använder etiketten. Med det här alternativet kan användarna godkänna klassificeringen och eventuellt associerat skydd, eller avvisa rekommendationen om etiketten inte är lämplig för innehållet.

![Alternativ för att rekommendera en känslighetsetikett för användarna](../media/Sensitivity-labels-Recommended-label-option.png)

Här är ett exempel på en uppmaning från Azure Information Protection-klienten för enhetliga etiketter när du konfigurerar ett villkor för att använda en etikett som en rekommenderad åtgärd, med ett anpassat principtips. Du kan välja den text som ska visas i principtipset.

![Fråga om du vill använda en rekommenderad etikett](../media/Sensitivity-label-Prompt-for-required-label.png)

### <a name="when-automatic-or-recommended-labels-are-applied"></a>När automatiska och rekommenderade etiketter används

Implementeringen av automatisk och rekommenderad etikettering i Office-program beror på om du använder etiketter som är inbyggda i Office eller om Azure Information Protection har enhetlig etikettklient. Men i båda fallen:

- Du kan inte använda automatisk etikettering för dokument och e-postmeddelanden som tidigare etiketterats manuellt eller tidigare etiketterats med en högre känslighet. Kom ihåg att du bara kan använda en enstaka känslighetsetikett i ett dokument eller ett e-postmeddelande (förutom en enstaka kvarhållningsetikett).

- Du kan inte använda rekommenderad etikettering för dokument eller e-postmeddelanden som tidigare var märkta med en högre känslighet. När innehållet redan är märkt med en högre känslighet visas inte frågan med rekommendationen eller principtipset.

Specifikt för inbyggd etikettering:

- Alla Office-program har inte stöd för automatisk (och rekommenderad) etikettering. Mer information finns i [Stöd för funktioner för känslighetsetiketter i program](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

- För rekommenderade etiketter i skrivbordsversionerna av Word flaggas det känsliga innehåll som utlöste rekommendationen så att användare kan granska och ta bort det känsliga innehållet i stället för att använda den rekommenderade känslighetsetiketten.

- Mer information om hur de här etiketterna används i Office-appar, exempel på skärmbilder och hur känslig information identifieras finns i [Tillämpa känslighetsetiketter automatiskt eller rekommendera känslighetsetiketter för filer och e-postmeddelanden i Office](https://support.office.com/sv-SE/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1).

Specifikt för Azure Information Protection-klienten för enhetliga etiketter:

-  Automatisk och rekommenderad etikett gäller för Word, Excel och PowerPoint när du sparar ett dokument och i Outlook när du skickar ett e-postmeddelande.

- Om Outlook ska ha stöd för rekommenderad etikettering måste du först konfigurera [avancerade principinställningar](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook).

- Känslig information kan identifieras i brödtexten i dokument och e-postmeddelanden, sidhuvuden och sidfötter, men inte i ämnesraden eller i e-postbilagor.

## <a name="how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange"></a>Så här konfigurerar du principer för automatisk etikettering för SharePoint, OneDrive och Exchange

Kontrollera att du är medveten om kraven innan du konfigurerar principer för automatisk etikettering. 

### <a name="prerequisites-for-auto-labeling-policies"></a>Krav för principer för automatisk etikettering

- Simuleringsläge:
    - Granskning för Microsoft 365 måste aktiveras. Om du behöver aktivera granskning eller inte vet om granskning redan är på går du till [Aktivera eller inaktivera granskningsloggsökning](turn-audit-log-search-on-or-off.md).
    - Om du vill visa fil- eller e-postinnehåll i källvyn måste du ha rollen **innehållshanterare för innehållsutforskaren**. Globala administratörer har inte den här rollen som standard. Om du inte har den här behörigheten visas inte förhandsgranskningsfönstret när du väljer ett objekt på fliken **Matchade objekt**.

- Så här etiketterar du filer automatiskt i SharePoint och OneDrive:
    - Du har [aktiverade känslighetsetiketter för Office-filer i SharePoint och OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).
    - När principen för automatisk etikettering körs får filen inte vara öppen av en annan process eller användare. En fil som är utcheckad för redigering tillhör den här kategorin.

- Om du planerar att använda [anpassade typer av känslig information](sensitive-information-type-learn-about.md) i stället för de inbyggda känslighetstyperna: 
    - Anpassade informationstyper för känslighet utvärderas för innehåll som läggs till i SharePoint eller OneDrive efter att de anpassade informationstyperna för känslighet sparats. 
    - Om du vill testa nya anpassade typer av känslig information skapar du dem innan du skapar din automatiska etikettprincip och skapar sedan nya dokument med exempeldata för testning.

- En eller flera känslighetsetiketter [skapas och publiceras](create-sensitivity-labels.md) (till minst en användare) som du kan välja för principer för automatisk etikettering. För dessa etiketter:
    - Det spelar ingen roll om inställningen för automatisk etikettering i Office-appar är aktiverad eller inaktiverad, eftersom den inställningen ger tillägg till principer för automatisk etikettering, som det förklaras i introduktionen.
    - Observera att de etiketter som du vill använda för automatisk etikettering är konfigurerade att använda visuella markeringar (sidhuvuden, sidfötter och vattenstämplar) som inte tillämpas på dokument.
    - Om etiketterna använder [kryptering](encryption-sensitivity-labels.md):
        - När principen för automatisk etikettering innehåller platser för SharePoint eller OneDrive måste etiketten vara konfigurerad för inställningen **Tilldela behörigheter nu**.
        - När principen för automatisk etikettering endast är för Exchange kan etiketten konfigureras för antingen **Tilldela behörigheter nu** eller **Låt användare tilldela behörigheter** (för alternativen Vidarebefordra inte eller Endast kryptering).

### <a name="learn-about-simulation-mode"></a>Mer information om simuleringsläget

Simuleringsläge är unikt för automatisk etikettering av principer och ingår i dess arbetsflöde. Du kan inte automatiskt märka dokument och e-postmeddelanden förrän principen har kört minst en simulering.

Arbetsflöde för en princip för automatisk etikettering:

1. Skapa och konfigurera en princip för automatisk etikettering.

2. Kör principen i simuleringsläge, vilket kan ta 48 timmar att slutföra.

3. Granska resultaten och förfina principen om det behövs. Kör om simuleringsläget och vänta tills det är klart igen.

4. Upprepa steg 3 efter behov.

5. Distribuera i produktion.

Den simulerade distributionen körs som parametern WhatIf för PowerShell. Du ser de resultat som rapporterats som om principen för automatisk etikettering hade använt din valda etikett med hjälp av de regler som du definierat. Du kan sedan förfina reglerna och köra simuleringen igen om det behövs. Men eftersom automatisk etikettering för Exchange gäller för e-postmeddelanden som skickas och tas emot, i stället för e-postmeddelanden som lagras i postlådor, förväntar du dig inte att resultatet för e-post i en simulering ska vara konsekvent, såvida du inte kan skicka och ta emot exakt samma e-postmeddelanden.

Med simuleringsläget kan du gradvis utöka omfattningen för principen för automatisk etikettering före distributionen. Du kan till exempel börja med en enda plats, till exempel en SharePoint-webbplats, med ett enda dokumentbibliotek. Sedan kan du, med iterativa ändringar, öka omfattningen till flera webbplatser och sedan till en annan plats, till exempel OneDrive.

Slutligen kan du använda simuleringsläge för att få en ungefärlig bild av hur lång tid som behövs för att köra principen för automatisk etikettering, så att du kan planera och schemalägga när den ska köras utan simuleringsläge.

### <a name="creating-an-auto-labeling-policy"></a>Skapa en princip för automatisk etikettering

1. I [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com/) går du till känslighetsetiketter:
    
    - **Lösningar** > **Informationsskydd**
    
    Om du inte ser det här alternativet direkt väljer du först **Visa alla**.

2. Välj fliken **Automatisk etikettering**:
    
    ![Fliken Automatisk etikettering](../media/auto-labeling-tab.png)
    
    > [!NOTE]
    > Om fliken **Automatisk etikettering** inte visas är den här funktionen inte tillgänglig i din region.

3. Välj **+Skapa princip för automatisk etikettering**. Guiden för ny princip startas:
    
    ![Ny principguide för automatisk etikettering ](../media/auto-labeling-wizard.png)

4. På sidan **Välj information som du vill att etiketten ska tillämpas på**: Välj en av mallarna, till exempel **Ekonomi** eller **Sekretess**. Du kan förfina sökningen med hjälp av listrutan **Visa alternativ för**. Eller välj **Anpassad princip** om mallarna inte uppfyller dina krav. Välj **Nästa**.

5. På sidan **Namnge principen för automatiska etiketter**: Ange ett unikt namn och alternativt en beskrivning för att identifiera automatiskt tillämpade etiketter, platser och villkor som identifierar innehållet på etiketten.

6. På sidan **Välj platser där du vill tillämpa etiketten**: Välj och ange platser för Exchange, SharePoint-webbplatser och OneDrive. Välj sedan **Nästa**.
    
    ![Choose locations page auto-labelingwizard ](../media/locations-auto-labeling-wizard.png)
    
    Du måste ange enskilda SharePoint-webbplatser och OneDrive-konton. För OneDrive har URL-adressen för en användares OneDrive-konto följande format: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`
    
    Exempelvis för en användare i Contoso-klientorganisationen som har användarnamnet ”rsimone”: `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`
    
    Information om hur du verifierar klientorganisationens syntax och identifierar URL-adresser för användare finns i [Get a list of all user OneDrive URLs in your organization](/onedrive/list-onedrive-urls) (Få en lista över alla OneDrive-URL:er för användare i organisationen).

7. På sidan **Konfigurera gemensamma eller avancerade regler**: Behåll standardinställningen **Gemensamma regler** för att definiera regler som identifierar innehåll som ska märkas på alla valda platser. Om du behöver olika regler per plats väljer du **Avancerade regler**. Välj sedan **Nästa**.
    
    Reglerna använder villkor som innehåller typer av känslig information och delningsalternativ:
    - För känslig information kan du välja både inbyggda och anpassade typer av känslig information.
    - För de delade alternativen kan du välja **bara med personer inom organisationen** eller **med personer utanför organisationen**.
    
    Om den enda platsen **är Exchange**, eller om du väljer **Avancerade regler**, finns det ytterligare villkor som du kan välja:
    - Avsändarens IP-adress är
    - Mottagardomän är
    - Mottagaren är
    - Den bifogade filens filtillägg är
    - Bifogad fil är lösenordsskyddad
    - Det gick inte att skanna innehållet i en e-postbilaga
    - Genomsökningen slutfördes inte för innehåll i e-postbilaga

8. Beroende på dina tidigare val har du nu möjlighet att skapa nya regler med hjälp av villkor och undantag.
    
    Konfigurationsalternativen för typer av känslig information är desamma som de du väljer för automatisk etikettering för Office-appar. Om du behöver mer information går du till [Konfigurera typer av känslig information för en etikett](#configuring-sensitive-info-types-for-a-label).
    
    När du har definierat alla regler du behöver och bekräftat att deras status är på väljer du **Nästa** för att gå vidare och välja en etikett som ska tillämpas automatiskt.

11. På sidan **Välj en etikett som ska tillämpas automatiskt**: Välj **+ Välj en etikett**, välj en etikett i fönstret **Välj en känslighetsetikett** och välj sedan **Nästa**.

12. På sidan **Bestäm om du vill testa principen nu eller senare**: Välj **Kör principen i simuleringsläge** om du är redo att köra principen för automatisk etikettering i simuleringsläge nu. Annars väljer du **Låt principen förbli inaktiverad**. Välj **Nästa**: 
    
    ![Testa principen för att skapa automatisk etikettering](../media/simulation-mode-auto-labeling-wizard.png)

13. På sidan **Sammanfattning**: Kontrollera konfigurationen av principen för automatisk etikettering, gör de ändringar som behövs och slutför guiden.

På sidan **Informationsskydd** > **Automatisk etikettering** ser du din princip för automatisk etikettering i avsnittet **Simulering** eller **Av**, beroende på om du valde att köra den i simuleringsläge eller inte. Välj principen om du vill visa information om konfiguration och status (till exempel **Principsimulering körs fortfarande**). För principer i simuleringsläge väljer du fliken **Matchade objekt** för att se vilka e-postmeddelanden eller dokument som matchade reglerna du angav.

Du kan ändra din princip direkt i det här gränssnittet:

- För en princip i avsnittet **Av** väljer du knappen **Redigera princip**.

- För princip i avsnittet **Simulering** väljer du alternativet **Redigera princip** högst upp på sidan på någon av flikarna:
    
    ![Alternativ för att redigera en princip för automatisk etikettering](../media/auto-labeling-edit.png)
    
    När du är redo att köra principen utan simulering väljer du alternativet **Aktivera principen**.

Dina automatiska principer körs kontinuerligt tills de tas bort. Nya och ändrade dokument inkluderas exempelvis i de aktuella principinställningarna.

Du kan också se resultatet av principen för automatisk etikettering genom att använda [Innehållsutforskaren](data-classification-content-explorer.md) när du har rätt [behörigheter](data-classification-content-explorer.md#permissions):
- Med **Listvy för innehållsutforskare** kan du se en fils etikett men inte filens innehåll.
- Med **Innehållshanterare för innehållsutforskaren** kan du se innehållet i filen.

> [!TIP]
> Du kan också använda Innehållsutforskaren för att identifiera platser som innehåller dokument med känslig information, men som inte är etiketterade. Med den här informationen kan du lägga till dessa platser i principen för automatisk etikettering och inkludera de identifierade typerna av känslig information som regler.

### <a name="use-powershell-for-auto-labeling-policies"></a>Använda PowerShell för principer för automatisk etikettering

Du kan använda [Säkerhets- och efterlevnadscenter PowerShell](/powershell/exchange/scc-powershell) för att skapa och konfigurera principer för automatisk etikettering. Det innebär att du kan skapa och underhålla principer för automatisk etikettering med skript, vilket också erbjuder en effektivare metod för att ange flera URL-adresser för OneDrive och SharePoint-webbplatser.

Innan du kör kommandona i PowerShell måste du först [ansluta till Säkerhets- och efterlevnadscentret via PowerShell](/powershell/exchange/connect-to-scc-powershell).

Skapa en ny princip för automatisk etikettering: 

```powershell
New-AutoSensitivityLabelPolicy -Name <AutoLabelingPolicyName> -SharePointLocation "<SharePointSiteLocation>" -ApplySensitivityLabel <Label> -Mode TestWithoutNotifications
```
Med det här kommandot skapas en princip med automatisk etikettering för en SharePoint-webbplats som du anger. För en OneDrive-plats använder du istället parametern *OneDriveLocation*. 

Så här lägger du till fler webbplatser i en befintlig princip för automatisk etikettering:

```powershell
$spoLocations = @("<SharePointSiteLocation1>","<SharePointSiteLocation2>")
Set-AutoSensitivityLabelPolicy -Identity <AutoLabelingPolicyName> -AddSharePointLocation $spoLocations -ApplySensitivityLabel <Label> -Mode TestWithoutNotifications
```

Det här kommandot anger de ytterligare SharePoint-URL:erna i en variabel som sedan läggs till i en befintlig princip för automatisk etikettering. Om du vill lägga till OneDrive-platser i stället använder du parametern *AddOneDriveLocation* med en annan variabel, till exempel *$OneDriveLocations*.

Skapa en ny regel för princip för automatisk etikettering:

```powershell
New-AutoSensitivityLabelRule -Policy <AutoLabelingPolicyName> -Name <AutoLabelingRuleName> -ContentContainsSensitiveInformation @{"name"= "a44669fe-0d48-453d-a9b1-2cc83f2cba77"; "mincount" = "2"} -Workload SharePoint
```

För en befintlig princip för automatisk etikettering.skapar det här kommandot en ny principregel för att identifiera känslig informationstyp för **amerikanskt socialförsäkringsnummer (SSN)**, som har enhets-ID:t a44669fe-0d48-453d-a9b1-2cc83f2cba77. Om du vill hitta entitets-ID för andra typer av känslig information finns mer information i [Entitetsdefinitioner av känsliga informationstyper](sensitive-information-type-entity-definitions.md).

Mer information om PowerShell-cmdletar som stöder automatiska etiketter, deras tillgängliga parametrar och några exempel finns i följande cmdlet-hjälp:

- [Get-AutoSensitivityLabelPolicy](/powershell/module/exchange/get-autosensitivitylabelpolicy)
- [New-AutoSensitivityLabelPolicy](/powershell/module/exchange/new-autosensitivitylabelpolicy)
- [New-AutoSensitivityLabelRule](/powershell/module/exchange/new-autosensitivitylabelrule)
- [Remove-AutoSensitivityLabelPolicy](/powershell/module/exchange/remove-autosensitivitylabelpolicy)
- [Remove-AutoSensitivityLabelRule](/powershell/module/exchange/remove-autosensitivitylabelrule)
- [Set-AutoSensitivityLabelPolicy](/powershell/module/exchange/set-autosensitivitylabelpolicy)
- [Set-AutoSensitivityLabelRule](/powershell/module/exchange/set-autosensitivitylabelrule)

## <a name="tips-to-increase-labeling-reach"></a>Tips för att öka etiketteringsräckvidd

Även om automatisk etikettering är ett av de mest effektiva sätten att klassificera, märka och skydda Office-filer som din organisation äger, kontrollera om du kan komplettera det med någon av de ytterligare metoderna för att öka din etiketteringsräckvidd:

- När du använder [Azure Information Protection enhetliga etiketteringsklienten](/azure/information-protection/rms-client/aip-clientv2):
    
    - För filer i lokala datalager som nätverksresurser och SharePoint Server-bibliotek: Använd [-skannern](/azure/information-protection/deploy-aip-scanner) för att identifiera känslig information i dessa filer och märka dem på rätt sätt. Om du planerar att migrera eller ladda upp dessa filer till SharePoint i Microsoft 365 använder du skannern för att märka filerna innan du flyttar dem till molnet.
    
    - Om du har använt en annan etikettlösning innan du använder känslighetsetiketter: Använd PowerShell och [en avancerad inställning för att återanvända etiketter](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#migrate-labels-from-secure-islands-and-other-labeling-solutions) från dessa lösningar.

- Uppmuntra [manuell etikettering](https://support.microsoft.com/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9) när du har gett användarna utbildning om vilka känslighetsetiketter som ska tillämpas. När du är säker på att användarna förstår vilken etikett som ska tillämpas bör du överväga att konfigurera en standardetikett och obligatorisk etikettering som [principinställningar](sensitivity-labels.md#what-label-policies-can-do). 

Överväg också [att markera nya filer som känsliga som standard](/sharepoint/sensitive-by-default) i SharePoint för att hindra gäster från att komma åt nyligen tillagda filer tills minst en DLP-princip söker igenom innehållet i filen.
