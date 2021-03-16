---
title: Åtgärder i migreringsfaser och påverkan på migreringen från Microsoft Cloud Deutschland (allmänt)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/05/2021
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: Sammanfattning Förstå åtgärderna i migreringsfaserna och hur de påverkar flytten från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365-tjänster i den nya tyska datacenterområdet.
ms.openlocfilehash: e630e88fa25bc97bcac27a032499bc31718be396
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826216"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Åtgärder i migreringsfaser och påverkan på migreringen från Microsoft Cloud Deutschland (allmänt)

Klientmigrering från Microsoft Cloud Deutschland (MCD) till regionen "Tyskland" av Microsofts globala Office 365-tjänster körs som en uppsättning faser och deras konfigurerade åtgärder för varje arbetsbelastning. I den här bilden visas de nio faserna av migrering till de nya tyska datacenteren.

![De nio faserna av migreringen till de nya Tyskland-datacenter](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Migreringsprocessen slutförs under många veckor beroende på organisationens totala storlek och komplexitet. Under tiden migreringen pågår kan användare och administratörer fortsätta använda tjänsterna med märkbara ändringar i den här dokumentationen. Grafiken och tabellen definierar faser och steg under migreringen.

|Steg|Varaktighet|Ansvarig part|Beskrivning|
|:--------|:--------|:--------|:--------|
|Opt-In|Tider|Kund|Välj din organisation för migreringen.|
|Före arbete|dagar|Kund|Slutför arbetet som krävs för att förbereda användare, arbetsstationer och nätverk för migrering.|
|Azure Active Directory (Azure AD)|1–2 dagar|Microsoft|Migrera Azure AD-organisationen till hela världen.|
|Azure|Veckor|Kund|Skapa nya globala Azure-prenumerationer och övergång Azure-tjänster.|
|Övergången & prenumerationslicens|1–2 dagar|Microsoft|Köp globala prenumerationer, avbryt Microsoft Cloud Deutschland-prenumerationer och gå över användarlicenser.|
|SharePoint och OneDrive|15+ dagar|Microsoft|Migrera innehåll i SharePoint och OneDrive för företag, men sharepoint.de URL:er.|
|Exchange Online|15+ dagar|Microsoft|Migrera Exchange Online-innehåll och gå över till globala URL:er.|
|Säkerhets- & efterlevnad|1–2 dagar|Microsoft|Säkerhet och & och innehåll för övergång.|
|Skype för företag|1–2 dagar|Microsoft|Gå över från Skype för företag till Microsoft Teams.|
|Power BI & Dynamics 365|15+ dagar|Microsoft|Migrera innehåll i Power BI och Dynamics 365.|
|Slutför Azure AD|1–2 dagar|Microsoft|Slutför klientuppeställningen till hela världen.|
|Clean-Up|1–2 dagar|Kund|Rensa upp äldre anslutningar till Microsoft Cloud Deutschland, till exempel AD FS (Active Directory Federation Services) Relying Party Trust, Azure AD Connect och Office-klienten startar om.|

Faserna och deras åtgärder säkerställer att kritiska data och upplevelser migreras till globala Office 365-tjänster. När klientorganisationen har lagts till i migreringskön slutförs varje arbetsbelastning som en uppsättning steg som körs på backend-tjänsten. Vissa arbetsbelastningar kan kräva åtgärder av administratören (eller användaren), eller så kan migreringen påverka användningen för faserna som körs och diskuteras i Hur [organiseras migreringen?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

Följande avsnitt innehåller åtgärder och effekter för arbetsbelastningen medan de går igenom olika faser av migreringen. Granska tabellerna och bestäm vilka åtgärder eller effekter som gäller för din organisation. Se till att du är redo att utföra stegen i respektive fas efter behov. Om du inte kan slutföra de nödvändiga stegen kan det leda till avbrott i tjänsten och kan fördröja migreringen till Office 365-tjänsterna.

## <a name="opt-in"></a>Opt-In

**Gäller för:** Alla kunder med en Office 365-klientorganisation som finns på Microsoft Cloud Deutschland (MCD)

| Steg | Beskrivning | Påverkan |
|:-------|:-----|:-------|
| Vi kan inte migrera Office 365-klientorganisationen på MCD utan medgivande. | Microsoft får rätten att migrera på ett av två sätt, vilket gör att Microsoft kan överföra data och tjänster till den globala Office 365-tjänstinstansen. <ol><li>Office 365-innehavaradministratören väljer den Microsoft-drivna migreringen. </li><li> Kunder förnyar alla prenumerationer i SIN MCD Office 365-klientorganisation efter den 1 maj 2020. Vi meddelar dessa kunder om migreringen varje månad, väntar i 30 dagar för att ge kunderna möjlighet att avbryta och sedan direkt anmäla sig.</li></ol> | <ul><li>Klientorganisationen markeras som bekräftad för migrering och admincentret visar en bekräftelse. </li><li>Bekräftelsen publiceras i Meddelandecenter för Office 365-klientorganisationen. Tjänstkonfigurationen fortsätter från Microsoft Cloud Deutschland-slutpunkter. </li><li>Innehavaradministratören måste övervaka Office 365 Meddelandecenter för uppdateringar om status för migreringsfasen. </li></ul>|

## <a name="subscription-phase-3"></a>Prenumeration (fas 3)

**Gäller för:** Alla kunder med en Office 365-klientorganisation som finns på Microsoft Cloud Deutschland (MCD)

| Steg | Beskrivning | Påverkan |
|:-------|:-----|:-------|
| Prenumerationer överförs och licenser tilldelas om. | När klientorganisationen har övergåt till Office 365-tjänster köps motsvarande Office 365-tjänstprenumerationer för de överförda Microsoft Cloud Deutschland-prenumerationerna. Användare med tilldelade Microsoft Cloud Deutschland-licenser tilldelas Office 365-tjänstlicenser. Äldre Microsoft Cloud Deutschland-prenumerationer tas bort från Office 365-tjänstklientorganisationen när den är klar. | <ul><li>Om din organisation befinner sig i en "licensöversituation" (använder fler platser än vad som är licensierade) kan migreringen blockeras tills det här åtgärdas. I [Förarbete finns information om](ms-cloud-germany-transition-add-pre-work.md?view=o365-worldwide#applies-to-everyone) hur du kan säkerställa att antalet tilldelade platser stämmer överens med de platser som används.</li><li> Ändringar av befintliga prenumerationer kommer att blockeras (t.ex. inga ändringar av nya prenumerationer eller antal platser) under den här fasen. </li><li> Ändringar av licenstilldelning blockeras. </li><li> Microsoft Cloud Deutschland-prenumerationen migreras till motsvarande Office 365-tjänstprenumeration. Office 365-tjänsterbjudandet för prenumerationen definieras av Microsoft (kallas även _erbjudandemappning)._ </li><li> Antalet funktioner (tjänstplaner) som erbjuds av Office 365-tjänster kan vara större än det ursprungliga Microsoft Cloud Deutschland-erbjudandet. Användarlicenser i Office 365-tjänster tilldelas likvärdigt med liknande Microsoft Cloud Deutschland-funktioner (tjänstplaner). Användarlicenserna för alla användare tilldelas automatiskt de nya funktionerna. Administratören måste vidta en uttrycklig åtgärd för att inaktivera licenserna om det behövs. </li><li> När prenumerationsmigrering har slutförts visas både Office 365-tjänster och Germany-prenumerationer i administrationsportalen för Office 365, med statusen För Tyskland-prenumerationer som _återkallad._ </li><li> Användare kommer att omtilldelas licenser som är kopplade till de nya Office 365-tjänstprenumerationer. Alla kundprocesser som är beroende av Germany-prenumerationer eller SKU GUID kommer att brytas och måste revideras med Office 365-tjänsterbjudandet. </li><li> Nya prenumerationer i Office 365-tjänsterna köps med den nya perioden (per månad/kvartal/år) och kunden får en prorrerad återbetalning för det oanvända saldot i Microsoft Cloud Deutschland-prenumerationen. </li><li> Partner Microsoft Cloud Deutschland-klientorganisationen kommer inte att migreras. Kunder som använder CSP migreras till Office 365-tjänster under den nya Office 365-tjänstklientorganisationen hos samma partner. Efter kundmigrering kan partnern bara hantera den här kunden från Office 365-tjänstklientorganisationen. </li><li> Fler funktioner är tillgängliga (till exempel Microsoft Planner och Microsoft Flow), om de inte inaktiveras av administratören för klientorganisationen. Mer information om hur du inaktiverar tjänstplaner som är tilldelade till användarnas licenser finns i Inaktivera åtkomst till [Microsoft 365-tjänster medan du tilldelar användarlicenser.](disable-access-to-services-while-assigning-user-licenses.md) |
||||

## <a name="sharepoint-online-phase-4"></a>SharePoint Online (fas 4)

**Gäller för:** Alla kunder som använder SharePoint Online

| Steg | Beskrivning | Påverkan |
|:-------|:-----|:-------|
| SharePoint och OneDrive har övergångar | SharePoint Online och OneDrive för företag migreras från Microsoft Cloud Deutschland till globala Office 365-tjänster i den här fasen.<br><ul><li>Befintliga Microsoft Cloud Deutschland-WEBBADRESSer bevaras (till exempel `contoso.sharepoint.de` ).</li><li>Befintliga webbplatser bevaras.</li><li>Klientbaserade autentiseringstoken som utfärdats av STS (Security Token Service) i Microsoft Cloud Deutschland eller Office 365 Global Services-instansen är giltiga under övergången.</li></ul>|<ul><li>Innehållet kommer att vara skrivskyddat under två korta perioder under migreringen. Under tiden kan du förvänta dig en banderoll i SharePoint som säger att du inte kan redigera innehåll.</li><li>Sökindexet bevaras inte, och det kan ta upp till tio dagar att återskapa det.</li><li>SharePoint Online- och OneDrive för företag-innehåll kommer att vara skrivskyddat under två korta perioder under migreringen. Under den här tiden visas en banderoll som säger att du inte kan redigera innehåll.</li><li>När SharePoint Online-migreringen slutförts kanske sökresultaten för SharePoint Online- och OneDrive för företag-innehåll inte är tillgängliga medan indexet återskapas. Under den här perioden kan det hända att sökfrågor inte returnerar fullständiga resultat. Funktioner som är beroende av sökindex, till exempel SharePoint Online Nyheter, kan påverkas när indexeringen slutförs.</li></ul>|
||||

Ytterligare överväganden:

- Om din organisation fortfarande använder SharePoint 2010-arbetsflöden kommer de inte längre att fungera efter den 31 december 2021. SharePoint 2013-arbetsflöden kommer att fortsätta stödjas, även om det är inaktiverat som standard för nya klientorganisationar som startar den 1 november 2020. När migreringen till SharePoint Online-tjänsten är klar rekommenderar vi att du flyttar till Power Automate eller andra lösningar som stöds.

- Microsoft Cloud Deutschland-kunder vars SharePoint Online-instans ännu inte migrerats måste vara kvar på SharePoint Online PowerShell-modulen/Microsoft.SharePointOnline.CSOM version 16.0.20616.12000 eller senare. I annat fall går det inte att använda anslutningar till SharePoint Online via PowerShell eller objektmodellen på klientsidan.

- Microsoft Cloud Deutschland-kunder vars SharePoint Online-instans har migrerats måste uppdatera SharePoint Online PowerShell-modulen/Microsoft.SharePointOnline.CSOM till version 16.0.20717.12000 eller senare. I annat fall går det inte att använda anslutningar till SharePoint Online via PowerShell eller objektmodellen på klientsidan.

## <a name="exchange-online-phase-5"></a>Exchange Online (fas 5)

**Gäller för:** Alla kunder som använder Exchange Online

Om du använder Exchange Online-hybrid: Exchange Online-hybridadministratörer måste köra hybridkonfigurationsguiden  **(HCW)** flera gånger under den här övergången. Se de [förarbetade avancerade migreringsstegen för Exchange](ms-cloud-germany-transition-add-experience.md#exchange-online-before-phase-5)

Enligt beskrivningen i migreringsförarbetet [,](ms-cloud-germany-transition-add-pre-work.md#exchange-online)innan migrering steg **5 börjar,** måste Exchange Online-hybridkunder köra den senaste versionen av HCW (Exchange Hybrid Configuration Wizard) i läget "Office 365 Germany" för att förbereda den lokala konfigurationen för migreringen till globala Office 365-tjänster.

När migreringsfasen **5** är slutförd (när meddelandet om meddelandecenter publiceras) måste du köra HCW igen med hjälp av de globala inställningarna för Office 365 så att dina lokala system pekar på de globala Office 365-tjänsterna. Ytterligare DNS-uppdateringar kan krävas om du använder egna domäner.

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Exchange Online-postlådor flyttas från Microsoft Cloud Deutschland till globala Office 365-tjänster.| Exchange Online-konfigurationen lägger till den nya lokala tyska regionen i övergången. Region för globala Office 365-tjänster har angetts som standard, vilket gör att den interna belastningsutjämningstjänsten kan distribuera om postlådor till rätt standardområde i Office 365-tjänsterna. I den här övergången finns användarna på vardera sidan (MCD eller globala tjänster) i samma organisation och kan använda antingen URL-slutpunkten. |<ul><li>Gå över användare och tjänster från äldre MCD-URL:er (outlook.office.de) till nya URL-adresser för Office 365-tjänster ( `https://outlook.office365.com` ).</li><li>Användarna kan fortsätta att få åtkomst till tjänsten via äldre MCD-URL:er under migreringen, men de måste sluta använda de äldre webbadresserna när migreringen slutförts.</li><li>Användarna bör gå över till att använda den globala Office-portalen för Office Online-funktionerna (Kalender, E-post, Kontakter). Navigering till tjänster som ännu inte har migrerats till Office 365-tjänster fungerar inte förrän de migreras. </li><li>Outlook Web App tillhandahåller inte de gemensamma mapparna under migreringen. </li></ul>|
| Uppdatera anpassade DNS-inställningar för Automatisk upptäckt| Customer-managed DNS settings for AutoDiscover that currently point to Microsoft Cloud Deutschland need to be updated to refer to the Office 365 Global endpoint on completion of the Exchange Online phase (phase 5). <br> Befintliga DNS-poster där CNAME pekar autodiscover-outlook.office.de måste uppdateras så att de pekar på autodiscover.outlook.com. |  Begäran om tillgänglighet och samtal om tjänstidentifiering via AutoDiscover pekar direkt på Office 365-tjänsterna. Kunder som inte utför de här DNS-uppdateringarna kan få problem med tjänsten för automatisk upptäckt när migreringen har slutförs. |
||||

Ytterligare överväganden:
<!--
    The statement below is not clear. What does myaccount.microsoft.com mean?
-->

- `myaccount.microsoft.com` kommer bara att fungera efter klientorganisationens cutover i fas 9. Länkar ger felmeddelanden om att något gick fel tills dess.

- Användare av Outlook Web App som har åtkomst till en delad postlåda i en annan miljö (till exempel en användare i MCD-miljön får åtkomst till en delad postlåda i den globala miljön) uppmanas att autentisera en andra gång. Användaren måste först autentisera och komma åt sin postlåda i `outlook.office.de` och sedan öppna den delade postlådan som finns i `outlook.office365.com` . De måste autentiseras en andra gång när de får åtkomst till de delade resurser som finns i den andra tjänsten.

- För befintliga Microsoft Cloud Deutschland-kunder eller användare som är under övergång kan det hända att en delad postlåda läggs till i Outlook med Arkiv **> Info >** Lägg till konto . Visa kalenderbehörigheter kan misslyckas (Outlook-klienten försöker använda Rest `https://outlook.office.de/api/v2.0/Me/Calendars` API).) Kunder som vill lägga till ett konto för att visa kalenderbehörigheter kan lägga till registernyckeln enligt beskrivningen i Ändringar i användarupplevelsen för delning av en kalender i [Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) för att säkerställa att den här åtgärden lyckas. Den här registernyckeln kan distribueras i hela organisationen med hjälp av Grupprincip.

- Under migreringsfasen kan användning av **PowerShell-cmdlets Ny migreringEndpoint,** **Set-MigrationEndpoint** och **Test-MigrationsServerAvailability** resultera i fel (fel på proxy). Det här inträffar när skiljebrevlådan har migrerats till hela världen men administratörspostlådan inte har det eller vice versa. Du kan lösa problemet genom att använda skiljepostlådan som tips om routning i **ConnectionUri** när du skapar PowerShell-klientsessionen. Ett exempel:

```powershell
New-PSSession 
    -ConfigurationName Microsoft.Exchange 
    -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de"
    -Credential $UserCredential
    -Authentication Basic
    -AllowRedirection
```

Om du vill veta mer om skillnaderna för organisationer i migrering och när Exchange Online-resurser har migrerats kan du läsa informationen i Kundupplevelse under migreringen till [Office 365-tjänster](ms-cloud-germany-transition-experience.md)i de nya tyska datacenterområdena.

## <a name="exchange-online-protection--security-and-compliance-phase-6"></a>Exchange Online Protection/Säkerhet och efterlevnad (fas 6)

**Gäller för:** Alla kunder som använder Exchange Online<br>

EOP-funktioner (Back-end Exchange Online Protection) kopieras till den nya regionen "Tyskland".

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Migrering av Exchange Online-routning och historiska meddelandedetaljer. | Exchange Online aktiverar routning från externa värdar till Office 365. De externa MX-posterna går över till EOP-tjänsten. Klientkonfiguration och historisk information migreras. |<ul><li>Microsoft-hanterade DNS-poster uppdateras från Office 365 Germany EOP till Office 365-tjänster.</li><li>Kunder bör vänta i 30 dagar efter att EOP har skrivit dubbelt så för EOP-migrering. Annars kan data gå förlorade.</li></ul>|
||||

## <a name="skype-for-business-online-phase-7"></a>Skype för företag – Online (fas 7)

**Gäller för:** Alla kunder som använder SharePoint Online

<!--
    Question from ckinder
    the PowerShell command seems to be incomplete
-->
| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Migrering av Skype för företag till Teams. | Befintliga Skype för företag-kunder migreras till globala Office 365-tjänster i Europa och flyttas sedan över till Microsoft Teams i regionen "Tyskland" för Office 365-tjänster. |<ul><li>Användarna kan inte logga in på Skype för företag på migreringsdatumet. Tio dagar före migreringen publicerar vi ett inlägg i administrationscentret för att meddela dig om när migreringen kommer att ske, och igen när vi påbörjar migreringen.</li><li> Principkonfigurationen migreras. </li><li>Användarna migreras till Teams och har inte längre Skype för företag efter migreringen. </li><li>Användarna måste ha Teams-skrivbordsklienten installerad. Installationen sker under tio dagar via policyn för Skype för företag-infrastrukturen, men om det misslyckas måste användarna fortfarande hämta klienten eller ansluta med en webbläsare som stöds. </li><li>Kontakter och möten migreras till Teams.</li><li>Användarna kan inte logga in i Skype för företag mellan tidstjänstens övergångar till Office 365-tjänster och inte förrän DNS-posterna för kunder har slutförts. </li><li>Kontakter och befintliga möten fortsätter att fungera som Skype för företag-möten. </li><li>PowerShell kommer att använda för att administrera inställningar och principer för din klientorganisation och dina användare. När du ansluter till en PowerShell-session lägger du till följande: <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"`</li></ul>|
||||

## <a name="dynamics-365-phase-8"></a>Dynamics 365 (fas 8)

**Gäller för:** Alla kunder som använder Microsoft Dynamics 365

Kunder med Dynamics 365 kräver ytterligare engagemang för att migrera organisationens Dynamics-organisationer oberoende av varandra.

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Microsoft Dynamics-resurser | Kunder med Microsoft Dynamics kommer att anlitas av Microsoft Engineering eller Microsoft FastTrack för att övergå Microsoft Dynamics 365 till den globala Office 365-tjänstinstansen.* |<ul><li>Efter migreringen validerar administratören organisationen. <</li><li>Administratören ändrar arbetsflöden efter behov. </li><li>Administratören tar bort AdminOnly-läget efter behov.</li><li>Administratören ändrar organisationstypen från begränsat _läge_ efter behov</li><li>Meddela slutanvändarna om den nya URL-adressen för åtkomst till instansen (org).</li><li>Uppdatera alla inkommande anslutningar till den nya slutpunkts-URL:en. </li><li>Dynamics-tjänsten kommer inte att vara tillgänglig för användarna under övergången. </li><li>Användarna måste validera organisationens hälsa och funktioner efter migreringen av varje organisation.</li></ul>|
|||||

\* (i) Kunder med Microsoft Dynamics 365 måste vidta åtgärder i det här migreringsscenariot som definierats av den angivna migreringsprocessen. (ii) Om kunden inte kan vidta någon åtgärd kommer Microsoft inte att kunna slutföra migreringen. (iii) När Microsoft inte kan slutföra migreringen på grund av kundens inaktivitet upphör kundens prenumeration den 29 oktober 2021.

## <a name="power-bi-phase-8-of-9"></a>Power BI (Fas 8 av 9)

**Gäller för:** Alla kunder som använder Microsoft Power BI (PBI)

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Migrering av Power BI-resurser | Kunder med Microsoft Power BI (PBI) kommer att vara engagerade av Microsoft Engineering eller Microsoft FastTrack efter att manuellt ha utlöst ett befintligt PBI-migreringsverktyg för att gå över Power BI till den globala tjänstinstansen för Office 365.\*\* |<ul><li>Följande Power _BI-objekt_ kommer inte att gå över och de måste skapas på ny sätt: <</li><li>Realtidsdatamängder (till exempel strömmande datamängder eller push-datauppsättningar). </li><li>Konfiguration och datakälla för lokal datagateway i Power BI. </li><li>Rapporter som bygger på realtidsdatamängderna blir inte tillgängliga efter migreringen och de måste återskapas. </li><li>Under övergången kommer inte användarna att kunna använda Power BI-tjänsterna. Tillgängligheten för tjänsten bör inte vara mer än 24 timmar.</li><li>Användare måste konfigurera om datakällor och deras lokala datagateway med Power BI-tjänsten efter migreringen.  Fram till dess kan användarna inte använda dessa datakällor för att utföra schemalagda uppdateringar och/eller direkta frågor mot dessa datakällor. </li><li>Kapaciteter och premiumarbetsytor kan inte migreras. Kunder måste ta bort alla kapaciteter före migreringen och skapa dem igen efter migreringen. Flytta arbetsytor tillbaka till kapaciteterna efter behov.</li></ul>  |
||||

\*\* (i) Kunder med Microsoft Power BI måste vidta åtgärder i det här migreringsscenariot som definierats av den migreringsprocess som tillhandahålls. (ii) Om kunden inte kan vidta någon åtgärd kommer Microsoft inte att kunna slutföra migreringen. (iii) När Microsoft inte kan slutföra migreringen på grund av kundens inaktivitet upphör kundens prenumeration den 29 oktober 2021.

## <a name="office-apps"></a>Office-program

**Gäller för:** Alla kunder som använder Office-skrivbordsprogram (Word, Excel, PowerPoint, Outlook, ...)

För klientorganisationen av Office 365 under övergången till regionen "Tyskland" måste alla användare stänga, logga ut från Office 365 och tillbaka in för alla Office-skrivbordsprogram (Word, Excel, PowerPoint, Outlook osv.) och OneDrive för företag-klienten när klientorganisationens migrering har nått fas 9. Genom att logga ut och in kan Office-tjänsterna hämta nya autentiseringstoken från den globala Azure AD-tjänsten.

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Klienter, Office Online under office-klientens övergången, slutför Azure AD klientorganisationens omfattning så att den pekar på Office 365-tjänsterna. | Med den här konfigurationsändringen kan Office-klienter uppdatera och peka på Slutpunkter för Office 365-tjänster. | <ul><li>Meddela användarna att stänga _alla_ Office-program och logga in igen (eller tvinga klienter att starta om och användarna att logga in) för att aktivera Office-klienter för att hämta ändringen. </li><li>Meddela användare och supportpersonal  att användarna kan se en Office-banderoll som uppmanar dem att återaktivera Office-program inom 72 timmar efter övergången. </li><li>Alla Office-program på persondatorer måste vara stängda och användarna måste logga ut och sedan logga in igen. I det gula aktiveringsfältet loggar du in för att återaktivera mot Office 365-tjänster.</li><li>Delade datorer kräver åtgärder som liknar personliga maskiner och kräver ingen särskild procedur. </li><li>På mobila enheter måste användarna logga ut från appar, stänga dem och sedan logga in igen. </li></ul>|
||||

## <a name="office-services"></a>Office-tjänster

Den senast använda (MRU) tjänsten i Office är en cutover från MCD till globala Office 365-tjänster, inte en migrering. Endast MU-länkar från den globala Office 365-tjänstsidan visas efter migrering från Office.com portalen. MRU-länkar från MCD visas inte som MU-länkar i globala Office 365-tjänster. I globala Office 365-tjänster är MNAU-länkar bara tillgängliga när klientorganisationens migrering har nått fas 9.

## <a name="next-step"></a>Nästa steg

[Utföra ytterligare uppgifter i förväg](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>Mer information

Komma igång:

- [Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i nya tyska datacenterområden](ms-cloud-germany-transition.md)
- [Migreringshjälp för Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Så här väljer du in för migrering](ms-cloud-germany-migration-opt-in.md)
- [Kundupplevelse under migreringen](ms-cloud-germany-transition-experience.md)

Flytta genom övergången:

- [Ytterligare arbete](ms-cloud-germany-transition-add-pre-work.md)
- Ytterligare information för [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [enheter,](ms-cloud-germany-transition-add-devices.md) [upplevelser](ms-cloud-germany-transition-add-experience.md)och [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Molnappar:

- [Information om Dynamics 365-migreringsprogram](https://aka.ms/d365ceoptin)
- [Information om Migreringsprogram för Power BI](https://aka.ms/pbioptin)
- [Komma igång med uppgraderingen till Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
