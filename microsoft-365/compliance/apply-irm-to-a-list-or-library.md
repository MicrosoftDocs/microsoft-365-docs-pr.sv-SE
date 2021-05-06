---
title: Tillämpa IRM (Information Rights Management) på en lista eller ett bibliotek
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1
ms.collection:
- M365-security-compliance
- SPO_Content
description: Du kan använda IRM (Information Rights Management) för att styra och skydda filer som hämtas från listor eller bibliotek.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0648d511ee882765f1905e83ebdea673f306c186
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2021
ms.locfileid: "52161800"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a>Tillämpa IRM (Information Rights Management) på en lista eller ett bibliotek

Du kan använda IRM (Information Rights Management) för att styra och skydda filer som hämtas från listor eller bibliotek. Den här funktionen stöds endast i det globala Microsoft-molnet. IRM stöds inte för SharePoint och bibliotek i nationella molndistributioner.
  
## <a name="administrator-preparations-before-applying-irm"></a>Administratörsförberedelser innan de använder IRM

- Azure Rights Management Service (Azure RMS) från Azure Information Protection och den lokala motsvarigheten till Active Directory Rights Management Services (AD RMS) har stöd för Information Rights Management för webbplatser. Inga separata eller ytterligare installationer krävs.

- Innan du tillämpar IRM på en lista eller ett bibliotek måste du aktivera IRM för webbplatsen. Du måste ha administratörsbehörighet för att aktivera IRM.

- Om du vill tillämpa IRM på en lista eller ett bibliotek måste du ha administratörsbehörighet för listan eller biblioteket.

- Om du använder Internet SharePoint kan timeout vara lång för användarna när de laddar ned större IRM-skyddade filer. Du kan undvika timeouts genom att använda Office-program för att tillämpa IRM-skydd och lagra större filer i ett SharePoint-bibliotek som inte använder IRM.

> [!NOTE]
> Om du använder SharePoint Server 2013 måste en serveradministratör installera dns-installationer på alla frontend-webbservrar för varje filtyp som personerna i organisationen vill skydda med hjälp av IRM.
  
## <a name="apply-irm-to-a-list-or-library"></a>Använda IRM för en lista eller ett bibliotek
<a name="__toc256598179"> </a>

![Information Rights Management Inställningar](../media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. Gå till listan eller biblioteket som du vill konfigurera IRM för.

2. Välj fliken Bibliotek i **menyfliksområdet och** välj sedan Bibliotek **Inställningar**. (Om du arbetar i en lista väljer du **fliken Lista** och sedan **Listlista** Inställningar ).
    
    ![SharePoint Knappar Inställningar Bibliotek i menyfliksområdet](../media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. Under **Behörigheter och hantering** väljer du **IR (Information Rights Management).** Om länken Information Rights Management inte visas kanske IRM inte är aktiverat för webbplatsen. Kontakta serveradministratören för att se om du kan aktivera IRM för webbplatsen. Länken **Information Rights Management** visas inte för bildbibliotek.

4. På sidan **Information Rights Management Inställningar** markerar  du kryssrutan Begränsa behörighet till dokument i det här biblioteket vid hämtning om du vill tillämpa begränsad behörighet för dokument som användare hämtar från listan eller biblioteket.

5. Ange ett **beskrivande namn på principen** i rutan Skapa en rubrik för behörighetsprincipen. Använd ett namn som hjälper dig att identifiera den här principen från andra principer. Du kan till exempel använda **Konfidentiellt om** du vill tillämpa begränsade behörigheter på en lista eller ett bibliotek som innehåller konfidentiella företagsdokument.

6. I rutan **Lägg till** en beskrivning av behörighetsprincipen anger du en beskrivning som visas för personer som använder listan eller biblioteket som förklarar hur de ska hantera dokumenten i listan eller biblioteket. Du kan till exempel skriva **Diskutera** innehållet i det här dokumentet endast med andra anställda om du vill begränsa åtkomsten till informationen i dessa dokument till interna medarbetare. 

7. Om du vill tillämpa ytterligare begränsningar för dokumenten i listan eller biblioteket väljer **du Visa** alternativ och gör något av följande:

|**Gör så här:**|**Gör så här:**|
|:-----|:-----|
|Tillåt att andra skriver ut dokument från listan eller biblioteket|Markera **kryssrutan Tillåt användare att skriva** ut.|
|Tillåta användare med minst behörigheten Visa objekt att köra inbäddad kod eller makron i ett dokument.|Markera kryssrutan **Tillåt läsare att köra skript och skärmläsare för att fungera i nedladdade** dokument. Om du väljer det här alternativet kan användare köra kod för att extrahera innehållet i ett dokument.           |
|Välj det här alternativet om du vill begränsa åtkomsten till innehåll till en angiven tidsperiod. Om du väljer det här alternativet utfärdar licenser för att få tillgång till innehållet upphör att gälla efter det angivna antalet dagar och personer kommer att behöva återgå till servern för att bekräfta sina autentiseringsuppgifter och ladda ned en ny kopia.|Markera kryssrutan Efter nedladdning förfaller dokumentåtkomsträttigheter efter dessa antal dagar **(1–365)** och ange sedan det antal dagar som du vill att dokumentet ska visas.|
| Hindra andra från att ladda upp dokument som inte stöder IRM till den här listan eller det här biblioteket. Om du väljer det här alternativet kan andra inte ladda upp någon av följande filtyper: Filtyper som inte har motsvarande IRM-skydd installerade på alla frontend-webbservrar. Filtyper som SharePoint Server 2010 kan inte dekryptera. Filtyper som är IRM-skyddade i ett annat program.|Markera kryssrutan **Tillåt inte användare att ladda upp dokument som inte stöder IRM.**|
|Ta bort begränsade behörigheter från listan eller biblioteket på ett visst datum.|Markera **kryssrutan Sluta begränsa åtkomsten till** biblioteket hos och välj sedan det datum du vill ha.|
|Kontrollera hur mycket autentiseringsuppgifter som cachelagras för det program som har licens för att öppna dokumentet.|Markera kryssrutan Användare måste verifiera sina autentiseringsuppgifter med det här intervallet **(dagar)** och ange sedan intervallet för cachelagring av autentiseringsuppgifter om ett antal dagar.|
|Tillåt gruppskydd så att användare kan dela med medlemmar i samma grupp.|Välj **Tillåt gruppskydd** och ange gruppens namn för delning.|

8. När du har valt de alternativ du vill ha väljer du **OK.**
  
## <a name="what-is-information-rights-management"></a>Vad är Information Rights Management?
<a name="__toc256598175"> </a>

Med IRM (Information Rights Management) kan du begränsa åtgärderna som användare kan utföra på filer som har laddats ned från listor eller bibliotek. IRM krypterar de nedladdade filerna och begränsar antalet användare och program som tillåts dekryptera dessa filer. IRM kan också begränsa behörigheterna för användare som tillåts att läsa filer, så att de inte kan utföra åtgärder som att skriva ut kopior av filerna eller kopiera text från dem.
  
Du kan använda IRM för listor eller bibliotek för att begränsa spridning av känsligt innehåll. Om du till exempel skapar ett dokumentbibliotek för att dela information om kommande produkter med valda marknadsrepresentanter kan du använda IRM för att förhindra att de här personerna delar det här innehållet med andra anställda i företaget.
  
På en webbplats tillämpar du IRM på en hel lista eller ett helt bibliotek, i stället för på enskilda filer. Det gör det enklare att säkerställa en konsekvent skyddsnivå för en hel uppsättning dokument eller filer. IRM kan därmed hjälpa organisationen att tillämpa företagsprinciper som styr användning och spridning av konfidentiell information eller företagsinformation.
  
> [!NOTE]
> Informationen på den här sidan om Information Rights Management ersätter alla villkor som refererar till "Information Rights Management" i alla licensavtal för Microsoft SharePoint Server 2013 och SharePoint Server 2016. 
  
### <a name="how-irm-can-help-protect-content"></a>Hur IRM kan skydda innehåll
<a name="__toc256598176"> </a>

IRM skyddar begränsat innehåll på följande sätt:
  
- Förhindrar att en behörig användare kopierar, ändrar, skriver ut, faxar eller kopierar och klistrar in innehåll för obehörig användning
    
- Förhindrar att en behörig användare kopierar innehållet med hjälp av funktionen Print Screen i Microsoft Windows
    
- Förhindrar att obehöriga tittare visar innehållet om det skickas i ett e-postmeddelande efter att det laddats ned från servern
    
- Begränsar åtkomsten till innehållet till en angiven tidsperiod, därefter måste användarna bekräfta sina autentiseringsuppgifter och ladda ned innehållet på nytt
    
- Gör det lättare att tillämpa företagsprinciper som reglerar användning och spridning av innehåll inom organisationen
    
### <a name="how-irm-cannot-help-protect-content"></a>Hur IRM inte kan skydda innehåll
<a name="__toc256598177"> </a>

IRM kan inte skydda begränsat innehåll från följande:
  
- Radera, fånga in eller överföra innehåll från skadliga program som trojaner, tangentbordsloggningsprogram och vissa typer av spionprogram
    
- Förlust eller skada på grund av datorvirus
    
- Kopiera eller skriva in innehåll manuellt från skärmen på en skärm
    
- Digital eller filmbildbild av innehåll som visas på en skärm
    
- Kopiera via användning av skärmdumpsprogram från tredje part
    
- Kopiera metadata för innehåll (kolumnvärden) med hjälp av skärmdumpsprogram från tredje part eller kopiera och klistra in
  
## <a name="how-irm-works-for-lists-and-libraries"></a>Så här fungerar IRM för listor och bibliotek
<a name="__toc256598178"> </a>

IRM-skydd tillämpas på filer på list- eller biblioteksnivå. När IRM har aktiverats för ett bibliotek tillämpas rättighetshantering på alla filerna i biblioteket. När IRM har aktiverats för en lista gäller rättighetshantering endast filer som är kopplade till listobjekt, inte de faktiska listobjekten.
  
När personer laddar ned filer i en lista eller ett bibliotek med IRM krypteras filerna så att endast behöriga personer kan visa dem. Alla rättighet hanterade filer innehåller också en utfärdningslicens som begränsningar för de personer som kan visa filen. Vanliga begränsningar är att skrivskydda en fil, inaktivera textkopiering, hindra andra från att spara lokala kopior och hindra personer från att skriva ut filen. I klientprogram som kan läsa filtyper med IRM-stöd används utfärdningslicensen för att tillämpa begränsningarna i den rättighetsbaserade filen. På så sätt bibehålls skyddet för de rättighetsskyddade filer även efter att de hämtats från servern.
  
De typer av begränsningar som tillämpas på en fil när den laddas ned från en lista eller ett bibliotek baseras på de enskilda användarnas behörigheter på webbplatsen som innehåller filen. I följande tabell beskrivs hur behörigheterna på webbplatserna motsvarar IRM-behörigheter.
  
|**Behörigheter**|**IRM-behörigheter**|
|:-----|:-----|
|Hantera behörigheter, hantera webbplats|**Fullständig behörighet** (enligt klientprogrammet): Med den här behörigheten kan användare normalt läsa, redigera, kopiera, spara och ändra behörigheter för rättighetsskyddat innehåll.|
|Redigera objekt, Hantera listor, Lägga till och anpassa sidor|**Redigera,** **Kopiera** och **Spara:** En användare kan  bara skriva ut en fil om kryssrutan Tillåt användare att skriva ut dokument är markerad på sidan Inställningar för listan eller biblioteket.|
|Visa objekt|**Läsa**: En användare kan läsa dokumentet, men kan inte kopiera eller ändra dess innehåll. En användare kan bara  skriva ut om kryssrutan Tillåt användare att skriva ut dokument är markerad på sidan Inställningar för listan eller biblioteket.|
|Annat|Inga andra behörigheter motsvarar direkt IRM-behörigheter.|
   
När du aktiverar IRM för en lista eller ett bibliotek i SharePoint Server 2013 kan du bara skydda filtyper i den listan eller det bibliotek som ett dokument är installerat för på alla frontend-webbservrar. En behörighet är ett program som styr kryptering och dekryptering av rättighetsskyddade filer i ett visst filformat. SharePoint omfattar del av följande filtyper:
  
- Microsoft Office InfoPath-formulär
    
- 97–2003-filformaten för följande Microsoft Office program: Word, Excel och PowerPoint
    
- Listan Office Open XML-format för följande Microsoft Office program: Word, Excel och PowerPoint
    
- XPS-format (XML Paper Specification)
    
Om din organisation planerar att använda IRM för att skydda andra filtyper utöver de som anges ovan måste serveradministratören installera system för ytterligare filformat.
  

