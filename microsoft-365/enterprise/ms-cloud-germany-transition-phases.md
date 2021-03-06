---
title: Åtgärder och effekter för migreringsfaserna för migreringen från Microsoft Cloud Deutschland (allmänt)
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
description: 'Sammanfattning: Förstå åtgärderna i migreringsfaserna och hur de påverkar flytten från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365-tjänster i den nya tyska datacenterområdet.'
ms.openlocfilehash: 310b8abe0597a4d28a5c539e52bf9a0f5f5f83d9
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515186"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Åtgärder och effekter för migreringsfaserna för migreringen från Microsoft Cloud Deutschland (allmänt)

Klientmigrering från Microsoft Cloud Deutschland till Regionen Tyskland för Microsofts Office 365-tjänster utförs som en uppsättning faser och deras konfigurerade åtgärder för varje arbetsbelastning. I den här bilden visas de nio faserna av migreringen till de nya tyska datacenteren. 

![De nio faserna av migreringen till de nya Tyskland-datacenter](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Migreringsprocessen slutförs under flera veckor beroende på organisationens totala storlek och komplexitet. Medan migreringen pågår kan användare och administratörer fortsätta använda tjänsterna med märkbara ändringar i den här dokumentationen. Grafiken och tabellen definierar faser och steg under migreringen.

|Steg|Varaktighet|Ansvarig part|Beskrivning|
|:--------|:--------|:--------|:--------|
|Opt-In|Tider|Kund|Anmäl din organisation till migreringen.|
|Före arbete|dagar|Kund|Slutför arbetet som krävs för att förbereda användare, arbetsstationer och nätverk för migrering.|
|Azure Active Directory (Azure AD)|1–2 dagar|Microsoft|Migrera Azure AD-organisationen till hela världen.|
|Azure|Veckor|Kund|Skapa nya globala Azure-prenumerationer och övergång över Azure-tjänster.|
|Prenumeration & licensövergång|1–2 dagar|Microsoft|Köp globala prenumerationer, avbryt Microsoft Cloud Deutschland-prenumerationer och gå över användarlicenser.|
|SharePoint och OneDrive|15+ dagar|Microsoft|Migrera innehåll i SharePoint och OneDrive för företag, men sharepoint.de URL-adresser.|
|Exchange Online|15+ dagar|Microsoft|Migrera Exchange Online-innehåll och -övergång till globala URL:er.|
|Efterlevnad & säkerhet|1–2 dagar|Microsoft|Övergång från säkerhet & efterlevnadsprinciper och -innehåll.|
|Skype för företag|1–2 dagar|Microsoft|Gå över från Skype för företag till Microsoft Teams.|
|Power BI & Dynamics 365|15+ dagar|Microsoft|Migrera innehåll i Power BI och Dynamics 365.|
|Slutför Azure AD|1–2 dagar|Microsoft|Fullständig klientuppställning till hela världen.|
|Clean-Up|1–2 dagar|Kund|Rensa äldre anslutningar till Microsoft Cloud Deutschland, till exempel Active Directory Federation Services (AD FS) Relying Party Trust, Azure AD Connect och Office-klientstarter.|

Faserna och deras åtgärder säkerställer att kritiska data och funktioner migreras till Office 365-tjänsterna. När klientorganisationen har lagts till i migreringskön slutförs varje arbetsbelastning som en uppsättning steg som körs på backend-tjänsten. Vissa arbetsbelastningar kan kräva åtgärder av administratören (eller användaren), eller så kan migreringen påverka användningen av faserna som utförs och diskuteras i Hur organiseras [migreringen?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

Följande avsnitt innehåller åtgärder och effekter för arbetsbelastningar när de fortskrider genom olika faser av migreringen. Granska tabellerna och bestäm vilka åtgärder eller effekter som gäller för din organisation. Se till att du är redo att utföra stegen i respektive fas efter behov. Om du inte kan slutföra de steg som krävs kan det leda till avbrott i tjänsten och det kan fördröja slutförandet av migreringen till Office 365-tjänsterna.

## <a name="opt-in"></a>Opt-In
| Steg | Beskrivning | Påverkan |
|:-------|:-----|:-------|
| Vi kan inte migrera kunder utan medgivande. | Microsoft får rätten att migrera på ett av två sätt, vilket gör att Microsoft kan överföra data och tjänster till Office 365-tjänstinstansen. <br> Administratören väljer att delta i den Microsoft-drivna migreringen. <br> Kunder förnyar alla prenumerationer i Sin Microsoft Cloud Deutschland-klientorganisation efter den 1 maj 2020. Vi meddelar dessa kunder om migreringen varje månad, vänta i 30 dagar för att ge kunderna möjlighet att avbryta och sedan registrera sig direkt i ICM. | Alla Office-kunder | – Klientorganisationen har markerats som godkännande för migrering och admincentret visar en bekräftelse. <br><br> - Bekräftelse publiceras i Cloud Germany Message Center-klientorganisationen. Tjänstkonfigurationen fortsätter från Microsoft Cloud Deutschland-slutpunkter. <br><br> - Övervaka meddelandecentret för uppdateringar om status för migreringsfasen. |


## <a name="subscription-phase-3"></a>Prenumeration (fas 3)

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Prenumerationer överförs och licenser tilldelas om. | När klientorganisationen har övergåt till Office 365-tjänster köps motsvarande Office 365-tjänstprenumerationer till de överförda Microsoft Cloud Deutschland-prenumerationerna. Användare med tilldelade Microsoft Cloud Deutschland-licenser tilldelas Office 365-tjänstlicenser. Äldre Microsoft Cloud Deutschland-prenumerationer tas bort från Office 365-tjänstklientorganisationen när de slutförs. | Alla Office-kunder | – Ändringar av befintliga prenumerationer kommer att blockeras (till exempel inga ändringar av nya abonnemang eller ändringar av antal platser) under den här fasen. <br><br> - Ändringar av licenstilldelning blockeras. <br><br> - Microsoft Cloud Deutschland-prenumerationen migreras till motsvarande Office 365-tjänstprenumeration. Office 365-tjänsterbjudandet för prenumerationen definieras av Microsoft (kallas även _erbjudandemappning)._ <br><br> - Antalet funktioner (tjänstplaner) som erbjuds av Office 365-tjänster kan vara större än i det ursprungliga Microsoft Cloud Deutschland-erbjudandet. Användarlicenser i Office 365-tjänster tilldelas likvärdigt med liknande Microsoft Cloud Deutschland-funktioner (tjänstplaner). Användarlicenserna för alla användare tilldelas automatiskt de nya funktionerna. Administratören måste vidta en uttrycklig åtgärd för att inaktivera licenserna, om det behövs. <br><br> – När prenumerationsmigrering har slutförts visas både Office 365-tjänster och Germany-prenumerationer i administrationsportalen för Office 365, med statusen för Germany-prenumerationer som _återkallad._ <br><br> - Användare kommer att omtilldelas licenser som är kopplade till de nya prenumerationerna på Office 365-tjänster. Alla kundprocesser som är beroende av Germany-prenumerationer eller SKU GUID bryts och måste revideras med Office 365-tjänsterbjudandet. <br><br> - Nya prenumerationer på Office 365-tjänsterna köps med den nya perioden (varje månad/kvartal/år), och kunden får en prorerad återbetalning för det oanvända saldot i Microsoft Cloud Deutschland-prenumerationen. <br><br> – Partner Microsoft Cloud Deutschland-klientorganisationen migreras inte. CSP-kunder migreras till Office 365-tjänster enligt den nya Office 365-tjänstklientorganisationen för samma partner. Efter kundmigrering kan partnern endast hantera den här kunden från Office 365-tjänstklientorganisationen. <br><br> - Ytterligare funktioner är tillgängliga (till exempel Microsoft Planner och Microsoft Flow), om de inte inaktiveras av administratören för klientorganisationen. Mer information om hur du inaktiverar tjänstplaner som tilldelas till användarnas licenser finns i Inaktivera åtkomst till [Microsoft 365-tjänster när du tilldelar användarlicenser.](disable-access-to-services-while-assigning-user-licenses.md)  |
|||||


## <a name="sharepoint-online-phase-4"></a>SharePoint Online (fas 4)

**Gäller för:** SharePoint Online

| Steg | Beskrivning | Påverkan |
|:-------|:-----|:-------|
| SharePoint och OneDrive har övergångar | SharePoint Online och OneDrive för företag migreras från Microsoft Cloud Deutschland till globala Office 365-tjänster i den här fasen.<br><ul><li>Befintliga URL-adresser för Microsoft Cloud Deutschland bevaras (till `contoso.sharepoint.de` exempel).</li><li>Befintliga webbplatser bevaras.</li><li>Autentiseringstoken på klientsidan som utfärdats av STS (Security Token Service) i Microsoft Cloud Deutschland- eller Office 365 Global Services-instansen är giltiga under övergången.</li></ul>|<ul><li>Innehållet kommer att vara skrivskyddat under två korta perioder under migreringen. Under tiden kan du förvänta dig en banderoll som säger att du inte kan redigera innehåll i SharePoint.</li><li>Sökindexet bevaras inte och kan ta upp till tio dagar att återskapas.</li><li>SharePoint Online- och OneDrive för företag-innehåll kommer att vara skrivskyddat under två korta perioder under migreringen. Användarna kommer att se banderollen "du kan inte redigera innehåll" kort under denna tid.</li><li>När SharePoint Online-migreringen slutförts kanske sökresultaten för SharePoint Online- och OneDrive för företag-innehåll inte är tillgängliga medan indexet återskapas. Under den här perioden kan det hända att sökfrågor inte returnerar fullständiga resultat. Funktioner som är beroende av sökindex, till exempel SharePoint Online Nyheter, kan påverkas när omindexeringen slutförs.</li></ul>|
||||

Ytterligare överväganden:

- Om organisationen fortfarande använder SharePoint 2010-arbetsflöden kommer de inte längre att fungera efter den 31 december 2021. SharePoint 2013-arbetsflöden stöds fortfarande, även om de är inaktiverade som standard för nya klientorganisationen från och med den 1 november 2020. När migreringen till SharePoint Online-tjänsten är klar rekommenderar vi att du går över till Power Automate eller andra lösningar som stöds.

- Microsoft Cloud Deutschland-kunder vars SharePoint Online-instans ännu inte migrerats måste stanna kvar på SharePoint Online PowerShell-modulen/Microsoft.SharePointOnline.CSOM version 16.0.20616.12000 eller senare. Annars misslyckas anslutningar till SharePoint Online via PowerShell eller objektmodellen på klientsidan.

- Microsoft Cloud Deutschland-kunder vars SharePoint Online-instans har migrerats måste uppdatera SharePoint Online PowerShell-modulen/Microsoft.SharePointOnline.CSOM till version 16.0.20717.12000 eller senare. Annars misslyckas anslutningar till SharePoint Online via PowerShell eller objektmodellen på klientsidan.

## <a name="exchange-online-phase-5"></a>Exchange Online (fas 5)

**Gäller för:**  Exchange Online

Om du använder Exchange Online-hybrid: Exchange Online-hybridkunder måste köra hybridkonfigurationsguiden (HCW) flera gånger som en del av den här övergången.

Enligt beskrivningen [](ms-cloud-germany-transition-add-pre-work.md#exchange-online)i migreringens förarbete måste Exchange Online-hybridkunder köra den senaste versionen av HCW i Office 365 Germany-läget innan migreringsstegfas **5** börjar för att förbereda den lokala konfigurationen för migreringen till Office 365 global.

När migreringsfasen **5** är slutförd (när meddelandet har publicerats i Meddelandecenter) måste du köra HCW igen med hjälp av de globala inställningarna för Office 365 så att dina lokala system pekar på den globala Office 365-tjänsten. Ytterligare DNS-uppdateringar kan krävas om du använder anpassade domäner.


| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Exchange Online-postlådor flyttas från Microsoft Cloud Deutschland till globala Office 365-tjänster.| I exchange Online-konfigurationen läggs den nya lokala tyska regionen till i den nya övergångsorganisationen. Region för globala Office 365-tjänster anges som standard, vilket gör att den interna belastningsutjämningstjänsten kan distribuera postlådor till rätt standardområde i Office 365-tjänster. I den här övergången finns användarna på vardera sidan (Tyskland eller globala tjänster) i samma organisation och kan använda någon av URL-slutpunkterna. |<ul><li>Gå över användare och tjänster från dina tidigare URL-adresser för Tyskland (outlook.office.de) till nya URL-adresser för Office 365-tjänster `https://outlook.office365.com` ().</li><li>Användare kan fortsätta att få åtkomst till tjänsten via äldre Tyskland-URL:er under migreringen, men de måste sluta använda äldre URL:er när migreringen slutförts.</li><li>Användarna bör gå över till att använda den globala Office-portalen för Office Online-funktioner (kalender, e-post, kontakter). Navigering till tjänster som ännu inte migrerats till Office 365-tjänster fungerar inte förrän de migreras. </li><li>Outlook Web App tillhandahåller inte den gemensamma mappen under migreringen. </li></ul>|
| Uppdatera anpassade DNS-inställningar för Automatisk upptäckt| Customer-managed DNS settings for AutoDiscover that currently point to Microsoft Cloud Deutschland need to be updated to refer to the Office 365 Global endpoint on completion of the Exchange Online phase (phase 5). <br> Befintliga DNS-poster där CNAME pekar autodiscover-outlook.office.de måste uppdateras så att de pekar på autodiscover.outlook.com. |  Tillgänglighetsförfrågningar och samtal för identifiering av tjänster via AutoDiscover pekar direkt på Office 365-tjänsterna. Kunder som inte utför de här DNS-uppdateringarna kan få problem med tjänsten för automatisk upptäckt när migreringen har slutförs. |
||||

Ytterligare överväganden:

- `myaccount.microsoft.com` kommer bara att fungera efter office 365-övergången. Länkar ger felmeddelanden om att något gick fel tills dess.

- Användare av Outlook Web App som har åtkomst till en delad postlåda i den andra miljön (till exempel om en användare i Tyskland-miljön har åtkomst till en delad postlåda i den globala miljön) uppmanas att autentisera en andra gång. Användaren måste först autentisera och komma åt postlådan i `outlook.office.de` och sedan öppna den delade postlådan som finns `outlook.office365.com` i. De måste autentiseras en andra gång när de har åtkomst till de delade resurser som finns i den andra tjänsten.

- För befintliga Microsoft Cloud Deutschland-kunder eller sådana som är under övergång kan det hända att en delad postlåda läggs till i Outlook genom att använda **File > Info > Add Account**– kalenderbehörigheter kan misslyckas (Outlook-klienten försöker använda Rest `https://outlook.office.de/api/v2.0/Me/Calendars` API). Kunder som vill lägga till ett konto för att visa kalenderbehörigheter kan lägga till registernyckeln enligt beskrivningen i Användarupplevelse ändringar för delning av en kalender i [Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) för att säkerställa att den här åtgärden kommer att lyckas. Den här registernyckeln kan distribueras i hela organisationen med hjälp av grupprincip.

- Under migreringsfasen kan det uppstå fel (fel på proxy) om du använder **PowerShell-cmdlets New-migrationEndpoint,** **Set-MigrationEndpoint** och **Test-MigrationsServerAvailability.** Det här inträffar när skiljeförfarandespostlådan har migrerats till hela världen, men inte administratörspostlådan har det eller vice versa. Du kan lösa problemet genom att använda skiljebrevlådan som tips om routning i ConnectionUri när du skapar PowerShell-sessionen **för klientorganisationen.** Till exempel: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

Om du vill veta mer om skillnaderna för organisationer vid migrering och när Exchange Online-resurser har migrerats kan du läsa informationen i Kundupplevelse under migreringen till [Office 365-tjänster](ms-cloud-germany-transition-experience.md)i de nya tyska datacenterområdena.

## <a name="exchange-online-protection--security-and-compliance-phase-6"></a>Exchange Online Protection/Security and Compliance (fas 6)

Backend Exchange Online Protection (EOP) funktioner kopieras till den nya Tyskland-region. 

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Migrering av Exchange Online-routning och historiska meddelandedetaljer. | Exchange Online aktiverar routning från externa värdar till Office 365. De externa MX-posterna förs över till routen till EOP-tjänsten. Klientkonfiguration och historisk information migreras. | Exchange Online-kunder | – Microsoft-hanterade DNS-poster uppdateras från Office 365 Germany EOP till Office 365-tjänster. <br><br> - Kunder bör vänta i 30 dagar efter EOP med dubbla skrivning för EOP-migrering. Annars kan data gå förlorade. |
|||||

## <a name="skype-for-business-online-phase-7"></a>Skype för företag – Online (fas 7)

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Migrering av Skype för företag till Teams. | Befintliga Skype för företag-kunder migreras till Office 365-tjänster i Europa och flyttas sedan till Microsoft Teams i Tyskland-regionen för Office 365-tjänster. | Skype för företag-kunder | – Användarna kan inte logga in i Skype för företag på migreringsdatumet. Tio dagar före migreringen publicerar vi i administrationscentret för att berätta när migreringen kommer att ske, och igen när vi påbörjar migreringen. <br><br> - Principkonfigurationen migreras. <br><br> - Användarna migreras till Teams och kommer inte längre att ha Skype för företag efter migreringen. <br><br> - Användarna måste ha Teams-skrivbordsklienten installerad. Installationen sker under de 10 dagarna via principen för Infrastrukturen för Skype för företag, men om det misslyckas måste användarna fortfarande ladda ned klienten eller ansluta med en webbläsare som stöds. <br><br> - Kontakter och möten migreras till Teams. <br><br> - Användarna kan inte logga in i Skype för företag mellan tidstjänstens övergångar till Office 365-tjänster och inte förrän dns-posterna från kunder har slutförts. <br><br> - Kontakter och befintliga möten fortsätter att fungera som Skype för företag-möten. |
|||||

## <a name="dynamics-365-phase-8"></a>Dynamics 365 (fas 8)
Kunder med Dynamics 365 kräver ytterligare engagemang för att migrera organisationens Dynamics-organisationer oberoende av varandra.
 
| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Microsoft Dynamics-resurser | Kunder med Microsoft Dynamics kommer att vara engagerade av Teknik eller FastTrack för att övergå till Office 365-tjänstinstansen.* | Microsoft Dynamics 365-kunder | – Efter migreringen validerar administratören organisationen. <br><br> - Administratören ändrar arbetsflöden efter behov. <br><br> – administratören rensar AdminOnly-läge efter behov. <br><br> - Administratören ändrar organisationstypen från begränsat _läge_ efter behov <br><br> - Meddela slutanvändarna om den nya URL:en för att få åtkomst till instansen (organisationen). <br><br> – Uppdatera alla inkommande anslutningar till den nya slutpunkts-URL:en. <br><br> - Dynamics-tjänsten kommer inte att vara tillgänglig för användare under övergången. <br><br> - Användarna måste validera organisationens hälsa och funktioner efter migreringen av varje organisation.  |
|||||

\* (i) Kunder med Microsoft Dynamics 365 måste vidta åtgärder i det här migreringsscenariot som definierats av den migreringsprocess som tillhandahålls. (ii) Om kunden inte kan vidta någon åtgärd kommer Microsoft inte att kunna slutföra migreringen. (iii) När Microsoft inte kan slutföra migreringen på grund av kundens inaction upphör kundens prenumeration den 29 oktober 2021.


## <a name="power-bi-phase-8-of-9"></a>Power BI (Fas 8 av 9)

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Migrering av Power BI-resurser | Kunder med Microsoft Power BI kommer att vara engagerade av Teknik eller FastTrack efter att manuellt ha utlöst ett befintligt PBI-migreringsverktyg för att migrera Power BI till Office 365-tjänstinstansen.\*\* | Microsoft Power BI-kunder | - Följande Power _BI-objekt_ kommer inte att läggas över och de måste skapas på ny sätt: <br><br> – Realtidsdatamängder (till exempel strömma datamängder eller push-datauppsättningar). <br> - Konfiguration och datakälla för lokal Power BI-datagateway. <br> - Rapporter som bygger på realtidsdatamängderna blir inte tillgängliga efter migreringen och de måste återskapas. <br><br> - Power BI-tjänster kommer inte att vara tillgängliga för användarna under övergången. Tjänstens tillgänglighet är inte längre än 24 timmar. <br><br> – Användarna måste konfigurera om datakällor och deras lokala datagateway med Power BI-tjänsten efter migreringen.  Fram till dess kan användarna inte använda datakällorna till att utföra schemalagda uppdateringar och/eller direktfrågor mot dessa datakällor. <br><br> - Kapaciteter och premiumarbetsytor kan inte migreras. Kunder måste ta bort alla kapaciteter innan migreringen och skapa dem igen efter migreringen. Flytta arbetsytor tillbaka till kapaciteterna efter behov.  |
|||||

\*\* (i) Kunder med Microsoft Power BI måste vidta åtgärder i det här migreringsscenariot som definierats av den migreringsprocess som tillhandahålls. (ii) Om kunden inte kan vidta någon åtgärd kommer Microsoft inte att kunna slutföra migreringen. (iii) När Microsoft inte kan slutföra migreringen på grund av kundens inaction upphör kundens prenumeration den 29 oktober 2021. 


## <a name="office-apps"></a>Office-program

Office-kunder som övergår till Tyskland-regionen måste stänga och logga ut och tillbaka in för alla Office-program (Word, PowerPoint, Outlook osv.) och OneDrive för företag-klienten när migreringen är klar. Genom att logga ut och in kan Office-tjänsterna hämta nya autentiseringstoken från den globala Azure AD-tjänsten.
 
| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Klienter, Office Online under office-klientomfattningen slutför Azure AD klientomfattningen så att den pekar på Office 365-tjänsterna. | Med den här konfigurationsändringen kan Office-klienter uppdatera och peka på slutpunkterna för Office 365-tjänster. | Alla Office-kunder | – Meddela användarna att _stänga_ alla Office-program och logga in igen (eller tvinga klienterna att starta om och användarna att logga in) för att aktivera Office-klienter för att hämta ändringen. <br><br> – Meddela användare och supportpersonal att användarna kan se en Office-banderoll som uppmanar dem att återaktivera Office-appar inom 72 timmar från övergången.  <br><br> - Alla Office-program på persondatorer måste stängas och användarna måste logga ut och sedan logga in igen. Logga in i det gula aktiveringsfältet för att återaktivera mot Office 365-tjänster. <br><br> - Delade datorer kräver åtgärder som liknar personliga maskiner och kräver ingen särskild procedur. <br><br> – På mobila enheter måste användarna logga ut från appar, stänga dem och sedan logga in igen. |
|||||

## <a name="office-services"></a>Office-tjänster

Den senast använda tjänsten i Office är en övergång från Tyskland-tjänsten till Office 365-tjänster, inte en migrering. Endast MNA-länkar från Office 365-tjänstsidan kommer att visas efter migreringen Office.com portalen. MRU-länkar från Tyskland-tjänsten visas inte som mru-länkar i Office 365-tjänster. I Office 365 är MNA-länkar bara tillgängliga när klientorganisationen har migrerat.


## <a name="next-step"></a>Nästa steg

[Utföra ytterligare förarbete](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>Mer information

Komma igång:

- [Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i de nya tyska datacenterområdena](ms-cloud-germany-transition.md)
- [Migreringshjälp för Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Så här väljer du in för migrering](ms-cloud-germany-migration-opt-in.md)
- [Kundupplevelse under migreringen](ms-cloud-germany-transition-experience.md)

Flytta genom övergången:

- [Ytterligare förarbete](ms-cloud-germany-transition-add-pre-work.md)
- Ytterligare information för [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [enheter,](ms-cloud-germany-transition-add-devices.md) [upplevelser](ms-cloud-germany-transition-add-experience.md)och AD [FS.](ms-cloud-germany-transition-add-adfs.md)

Molnappar:

- [Information om Dynamics 365-migreringsprogram](https://aka.ms/d365ceoptin)
- [Information om migreringsprogrammet för Power BI](https://aka.ms/pbioptin)
- [Komma igång med uppgraderingen till Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
