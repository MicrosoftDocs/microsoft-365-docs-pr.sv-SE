---
title: Före migreringen från Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/09/2021
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
description: 'Sammanfattning: Arbeta i förväg när du flyttar från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365-tjänster i den nya tyska datacenterområdet.'
ms.openlocfilehash: 94b3758bbf24133c0d01a0db9e17f9451cf2d8d2
ms.sourcegitcommit: 9adb89206daa075af34a73bcb7e8fb86d7c2919a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50603870"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>Före migreringen från Microsoft Cloud Deutschland

Använd de här länkarna för att komma till de anvisningar som är relevanta för din organisation:

- Gör följande för alla kunder som använder Office 365 i Microsoft Cloud Deutschland. [](#applies-to-everyone)
- Om du använder Exchange Online- eller Exchange-hybrid gör du det [här steget.](#exchange-online)
- Om du använder SharePoint Online gör du så [här.](#sharepoint-online)
- Om du använder en MDM-lösning (Mobile Device Management) från tredje part gör du [det här steget.](#mobile)
- Om du använder en tredjepartstjänst eller verksamhetsbaserade appar som är integrerade med Office 365 gör du det [här steget.](#line-of-business-apps)
- Om du även använder Azure-tjänster utöver dem som ingår i din Office 365-prenumeration gör du [det här steget.](#microsoft-azure)
- Om du också använder Dynamics 365 gör du [det här steget.](#dynamics365)
- Om du också använder Power BI gör du det [här steget.](#power-bi)
- Gör det här steget för [DNS-ändringar.](#dns)
- Om du använder federerad identitet gör du [så här.](#federated-identity)

## <a name="applies-to-everyone"></a>Gäller för alla

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Förbered dem för att meddela användarna om omstart och inloggning till och från sina klienter efter migreringen. | Office-klientlicensiering kommer att övergå från Microsoft Cloud Deutschland till Office 365-tjänster under migreringen. Klienter hämtar en ny giltig licens när de har loggat ut från och in i Office-klienter. | Användarnas Office-produkter behöver uppdatera licenser från Office 365-tjänster. Om licenser inte uppdateras kan verifieringsfel uppstå i Office-produkter. |
| Säkerställa nätverksanslutningen till [URL-adresser och IP-adresser för Office 365-tjänster.](https://aka.ms/o365urls) | Alla klienter och tjänster hos kunden som används för att få åtkomst till Office 365-tjänsten måste kunna komma åt slutpunkter för globala Office 365-tjänster. <br>Om du eller dina samarbetspartner har brandväggsregler som förhindrar åtkomst till URL:er och IP-adresser som listas i URL:er och IP-adresser för [Office 365-tjänster](https://aka.ms/o365urls) måste du ändra brandväggsregler för att tillåta åtkomst till den globala Office 365-tjänst enpoints| Fel i tjänsten eller klientprogramvaran kan inträffa om detta inte görs före fas 4  |
| Avsluta utvärderingsprenumerationer. | Utvärderingsprenumerationer migreras inte och blockerar överföring av betalda prenumerationer. | Utvärderingstjänster upphör att gälla och fungerar inte om de används av användarna efter att de har avbrytas. |
| Analysera skillnader i licensfunktioner mellan Microsoft Cloud Deutschland och Office 365-tjänster. | Office 365-tjänster innehåller ytterligare funktioner och tjänster som inte är tillgängliga i nuvarande Microsoft Cloud Deutschland. Under prenumerationsöverföring blir nya funktioner tillgängliga för användarna. | <ul><li> Analysera de olika funktionerna som tillhandahålls av licenserna för Microsoft Cloud Deutschland och Office 365-tjänster. Börja med [tjänstbeskrivning för Office 365-plattformen.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) </li><li> Avgör om några nya funktioner i Office 365-tjänster först ska inaktiveras för att begränsa effekterna för användare eller ändringshantering och ändra användarlicenstilldelningar efter behov. </li><li>Förbereda användare och supportpersonal för nya tjänster och funktioner som tillhandahålls av Office 365-tjänster. |
| Skapa bevarandeprinciper [för hela organisationen för](https://docs.microsoft.com/microsoft-365/compliance/retention) att skydda mot oavsiktlig borttagning av innehåll under migreringen.  |<ul><li>För att säkerställa att innehåll inte oavsiktligt tas bort av slutanvändare under migreringen kan kunder välja att aktivera en bevarandeprincip för hela organisationen. </li><li>Bevarande är inte obligatoriskt, eftersom kvarhållning som gjorts när som helst under migreringen bör fungera som förväntat, men att ha en bevarandeprincip är en säkerhetsmekanism för säkerhet. Samtidigt kan det hända att en bevarandeprincip inte används av alla kunder, särskilt de som är oroliga för att bevara bevarandet.</li></ul>| Använd en bevarandeprincip enligt beskrivningen i [Läs mer om bevarandeprinciper och bevarandeetiketter.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) Fel i tjänsten eller klientprogramvaran kan uppstå om detta inte görs före fas 4 av 9. </li></ul>|
|||||

## <a name="active-directory-federation-services-ad-fs"></a>AD FS (Active Directory Federation Services)

**Gäller för:** Kunder som använder AD FS lokalt för att autentisera användare som ansluter till Microsoft Office 365

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| [Säkerhetskopiering av AD FS-servergruppen (Active Directory Federation Services)](ms-cloud-germany-transition-add-adfs.md#backup) för katastrofåterställningsscenarier. | Kunder måste backa AD FS-servergruppen på rätt sätt för att säkerställa att förtroenden för globala slutpunkter för & Germany kan återställas utan att utfärdare-URI för domänerna vidrörs. Microsoft rekommenderar att du använder AD FS Rapid Restore för en säkerhetskopia av servergruppen och motsvarande återställning, om det behövs. | Åtgärd som krävs. Inaction resulterar i tjänst påverkan under migreringen om AD FS-servergruppen för kunden misslyckas. Mer information finns i [ADFS-migreringsstegen](https://docs.microsoft.com/microsoft-365/enterprise/ms-cloud-germany-transition-add-adfs) |
||||

## <a name="exchange-online"></a>Exchange Online

**Gäller för:** Exchange Online-kunder som har aktiverat delning av kalender och tillgängligt adressutrymme.

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Meddela externa partner om den kommande övergången till Office 365-tjänster. | Med konfigurationer av tillgänglighetsadressutrymme kan du dela ledig/upptagen-information med Office 365. | Om du inte gör det kan det leda till service- eller klientfel i en senare fas av kundmigrering. |
|||||

### <a name="exchange-online-hybrid-configuration"></a>Hybridkonfiguration för Exchange Online

**Gäller för:** Exchange Online-kunder med en aktiv Exchange-hybridkonfiguration

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Uppdatera till den senaste versionen av hybridkonfigurationsguiden (HCW) när som helst innan klientorganisationen anger migreringssteg 5. Du kan starta den här aktiviteten direkt när du har fått meddelandecentret, men det kan vara viktigt att office 365-klientorganisationens migrering har påbörjats.<br><br> Microsoft Cloud Deutschland-hybridkunder i Exchange Online måste avinstallera tidigare versioner av HCW och sedan installera och köra den senaste versionen (17.0.5378.0 eller senare) [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) från. |<ul><li>Den senaste versionen av HCW innehåller uppdateringar som stöd för kunder som övergår från Microsoft Cloud Deutschland till Office 365 Services.</li><li> Uppdateringar omfattar ändringar av lokala certifikatinställningar för skicka anslutare och mottagningskoppling.</li><li> Exchange-administratörer måste installera OM HCW när som helst innan fas 5 av 9 (Exchange-migrering) påbörjas.<br>När DU kör HCW före fas 5 väljer du Office 365 Germany på den andra sidan i HCW-filen under _Office 365 Exchange Online_ i listrutan under Min Office  _365-organisation._</li><li>**Obs!** När office 365-klientmigreringen är slutförd tar du bort och installerar OM HCW igen, den här gången med hjälp av inställningarna för "Office 365 Worldwide" på den andra parsningen av HCW för att slutföra hybridkonfigurationen med den globala Exchange Online-tjänsten.</li></ul>|Om det inte går att köra HCW före fas 5 (Exchange-migrering) kan det leda till tjänst- eller klientfel. |
||||

## <a name="sharepoint-online"></a>SharePoint Online

**Gäller för:** Kunder som använder SharePoint 2013 lokalt


| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Begränsa SharePoint 2013-arbetsflöden, som används under SharePoint Online-migreringen. | Minska SharePoint 2013-arbetsflöden och slutför direktarbetsflöden före övergångar. | Inaction kan resultera i förvirring och supportsamtal. |
||||

## <a name="skype-for-business-online"></a>Skype för företag online

**Gäller för:** Skype för företag – Online-kunder

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Distribuera Teams-skrivbordsklienten för användare med åtkomst till Skype för företag i Tyskland. | Migreringen flyttar Skype för företag-användare till Microsoft Teams för samarbete, samtal och chatt. Distribuera antingen Microsoft Teams-skrivbordsklienten eller se till att en webbläsare som stöds är tillgänglig. | Inaction kommer att resultera i att Microsoft Teams samarbetstjänster inte är tillgängliga. |
| Granska och förbereda migreringsrelaterade DNS-ändringar. | Ändringar av DNS-zonändringar som ägs av kunder för Skype för företag – Online. |<ul><li>Vi rekommenderar att du uppdaterar Time-to-Live (TTL) för alla kundägda domän-DNS-poster till 5 minuter för att underlätta uppdatering av DNS-poster. Men den Microsoft-hanterade övergången som är kopplad till denna DNS-ändring kan inträffa när som helst inom det angivna 24-timmarsbytesfönstret. </li><li>Avbrott i tjänsten är möjligt i framtiden. Användarna kan inte logga in på Skype för företag och omdirigeras till den migrerade Teams-upplevelsen i Office 365-tjänsterna. </li></ul>|
| Förbered utbildning för slutanvändare och administration och förberedelser inför övergången till Microsoft Teams. | Lyckas med övergången från Skype till Teams genom att planera användarkommunikation och beredskap. | <ul><li>Klienter måste vara medvetna om de nya tjänsterna och hur de ska använda när deras tjänster väl har övergåt till Office 365-tjänsterna. </li><li>När DNS-ändringarna har gjorts för både kunddomänerna och den första domänen loggar användarna in i Skype för företag och ser till att de nu migreras till Teams. Det skulle också ladda ned skrivbordsklienten för Teams i bakgrunden. </li></ul>|
||||

## <a name="mobile"></a>Mobil

Om du använder en MDM-lösning (Mobile Device Management) från tredje part:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Förbered utbildning för slutanvändare och administration om att användare tar bort och lägger till sitt konto i Microsoft Outlook för iOS och Android. | Microsoft Outlook för iOS- och Android-konton som konfigurerats med postlådor i Microsoft Cloud Deutschland kan behöva tas bort och läggas till i Outlook igen för att kunna synkronisera den nya konfigurationen av Office 365-tjänster på rätt sätt. | Microsoft Outlook för iOS- och Android-kunder | Outlook-postlådor som tidigare konfigurerats för Microsoft Cloud Deutschland kanske inte hämtar den nya Office 365-tjänstkonfigurationen, vilket leder till fel och försämrad prestanda i andra användarupplevelser. IT-administratörer uppmanas att tillhandahålla dokumentation som proaktivt instruerar användarna att ta bort och lägga till sina konton i Microsoft Outlook för iOS och Android om problem med att logga in eller synkronisera e-post uppstår efter migreringen. |
| Avgöra om någon konfiguration krävs efter migreringen. | MDM-lösningar (Mobile Device Management) kan ha som `outlook.de` målslutpunkter. I den här övergången till Office 365-tjänster bör klientprofilerna uppdateras till URL:en för Office 365-tjänster. `outlook.office365.com` | Exchange Online- och MDM-kunder | Klienter kan fortsätta att fungera medan slutpunkten är tillgänglig, men de kommer att misslyckas om `outlook.de` Microsoft Cloud Deutschland-slutpunkter inte längre är tillgängliga. |
|||||

## <a name="line-of-business-apps"></a>Verksamhetsbaserade appar

Om du använder en tredjepartstjänst eller verksamhetsbaserade appar som är integrerade med Office 365: 

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Avgöra om någon konfiguration krävs efter migreringen. | Tredjepartstjänster och program som integrerar med Office 365 kan kodas för att räkna med microsoft Cloud Deutschland IP-adresser och URL-adresser. | Åtgärd krävs. Inaction kan resultera i fel i tjänsten eller klientprogramvaran. |
||||

## <a name="dynamics-365"></a>Dynamics 365

**Gäller för:** Kunder som använder Microsoft Dynamics

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| För prenumerationer på Dynamics 365 i begränsat läge måste du ladda ned produktionsmiljön för Dynamics SQL-instansen från din Dynamics 365-prenumeration i Microsoft Cloud Deutschland. Den senaste säkerhetskopieringen för produktionen bör återställas till sandbox-miljön före migrering i begränsat läge. | Migrering av Dynamics 365 kräver att kunderna ser till att miljön i begränsat läge uppdateras med den senaste produktionsdatabasen. | FastTrack-teamet hjälper kunderna att utföra torr körningar för att verifiera versionsuppgraderingen från 8.x till 9.1.x. |
||||

## <a name="power-bi"></a>Power BI

**Gäller för:** Power BI-kunder 

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Borttagning av objekt från Power BI-prenumerationer som inte migreras från Power BI Microsoft Cloud Deutschland till Office 365-tjänster. | Migrering av Power BI-tjänster kräver åtgärder från kunder för att ta bort vissa artefakter, till exempel datauppsättningar och instrumentpaneler. | <ul><li>Administratörer kan behöva ta bort följande objekt från prenumerationen: </li><li>Real-Time datauppsättningar (till exempel strömmande datamängder eller push-datauppsättningar) </li><li>Konfiguration och datakälla för lokal Power BI-datagateway </li></ul>|
||||

## <a name="dns"></a>DNS

**Gäller för:** Kunder som använder Office-skrivbordsklienten (Microsoft 365-appar, Office 365 ProPlus, Office 2019, 2016, ...)<br>
Ta bort MSOID, CName från kundägd DNS om det finns när som helst innan Azure Active Directory (Azure AD) klipps över. Du kan ange en TTL på 5 minuter så att ändringen snabbt kan genomföras.

## <a name="federated-identity"></a>Federerad identitet

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Lägg till en identifierare för enkel inloggning (SSO) i ett befintligt beroende partförtroende och inaktivera automatiska uppdateringar av AD FS-metadata. | Ett ID måste läggas till i DET AD FS-förtroende som parten litar på innan migreringen startar. Inaktivera automatisk uppdatering för metadatauppdateringar för att undvika oavsiktlig borttagning av den förlitar sig på partidentifierare. <br><br> Kör det här kommandot som en enda kommandorad på AD FS-servern: <br>`Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de', 'https://login.microsoftonline.de/extSTS.srf', 'https://login.microsoftonline.de') -AutoUpdate $False`
| Organisationer med federerad autentisering | Åtgärd som krävs. Inaction before Phase 4 of 9 (SharePoint) will result in service impact during the migration.  |
| Generera förlitande partförtroende för globala Azure AD-slutpunkter. | Kunder måste manuellt skapa ett förlitande partförtroende (RPT) till [globala](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) slutpunkter. Det gör du genom att lägga till en ny export- och exporttjänsttjänst (RPT) via GUI med hjälp av URL:en för globala federationsmetadata och sedan använda [Azure AD RPT Claim Rules](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) (i AD FS-hjälpen) för att generera anspråksreglerna och importera dem till rapporttjänsten. | Organisationer med federerad autentisering | Åtgärd som krävs. Inaction kommer att resultera i tjänst påverkan under migreringen. |
|||||

## <a name="microsoft-azure"></a>Microsoft Azure

Om du använder samma Azure Active Directory-identitetspartition för Office 365 och Microsoft Azure i Microsoft Cloud Deutschland-instansen ska du se till att du förbereder en kunddriven migrering av Microsoft Azure-tjänster.
Migreringen av Dina Microsoft Azure-tjänster får inte startas innan Office 365-klienten har nått migreringsfas 3 och måste slutföras innan migreringsfas 8 har slutförts.
| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Ta reda på vilka Azure-tjänster som används och förbered för framtida migrering från Tyskland till Klientorganisationen för Office 365-tjänster genom att arbeta med dina partner. Följ anvisningarna i [Azure-migreringsspelboken.](https://docs.microsoft.com/azure/germany/germany-migration-main) |<ul><li>Migrering av Azure-resurser är ett kundansvar och kräver manuell insats genom att följa de angivna stegen. Att förstå vilka tjänster som används i organisationen är avgörande för en lyckad migrering av Azure-tjänster. </li><li> Office 365 Germany-kunder som har Azure-prenumerationer under samma identitetspartition (organisation) måste följa den Microsoft-angivna ordningen när de kan påbörja prenumerations- och tjänstemigrering.</li></ul>|<ul><li>Kunder kan ha flera Azure-prenumerationer, varje prenumeration som innehåller infrastruktur, tjänster och plattformskomponenter. </li><li> Administratörer bör identifiera prenumerationer och intressenter för att säkerställa att snabb migrering och validering är möjlig som en del av den här migreringshändelsen. </li><li>Om det inte går att slutföra migreringen av dessa prenumerationer och Azure-komponenter inom den angivna tidslinjen påverkar slutförandet av Övergången för Office och Azure AD till Office 365-tjänsterna och kan resultera i dataförlust. </li><li> Ett meddelande i Meddelandecenter signalerar vid vilken tidpunkt en kundledd migrering kan starta. </li></ul>|
||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](https://docs.microsoft.com/azure/germany/germany-migration-main).

**Description:** Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services. 

Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.

**Applies to:** Azure Customers

**Impact:** 

- Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components. 
- Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event.

  Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss.
- A Message center notification will signal the point at which customer-led migration can begin.
-->

## <a name="more-information"></a>Mer information

Komma igång:

- [Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i de nya tyska datacenterområdena](ms-cloud-germany-transition.md)
- [Migreringshjälp för Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Så här väljer du in för migrering](ms-cloud-germany-migration-opt-in.md)
- [Kundupplevelse under migreringen](ms-cloud-germany-transition-experience.md)

Flytta genom övergången:

- [Åtgärder och påverkan i migreringsfaser](ms-cloud-germany-transition-phases.md)
- [Ytterligare förarbete](ms-cloud-germany-transition-add-pre-work.md)
- Ytterligare information för [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [enheter,](ms-cloud-germany-transition-add-devices.md) [upplevelser](ms-cloud-germany-transition-add-experience.md)och AD [FS.](ms-cloud-germany-transition-add-adfs.md)

Molnappar:

- [Information om Dynamics 365-migreringsprogram](https://aka.ms/d365ceoptin)
- [Information om migreringsprogrammet för Power BI](https://aka.ms/pbioptin)
- [Komma igång med uppgraderingen till Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
