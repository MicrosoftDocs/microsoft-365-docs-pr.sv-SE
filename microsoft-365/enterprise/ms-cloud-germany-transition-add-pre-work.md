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
ms.openlocfilehash: 5110c6bd86d5df35a7ceccb4abfedf059cb826d0
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826182"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>Före migreringen från Microsoft Cloud Deutschland

Använd de här länkarna för att komma till de anvisningar som gäller i förväg för din organisation:

- Gör följande för alla kunder som använder Office 365 i Microsoft Cloud Deutschland. [](#applies-to-everyone)
- Om du använder Exchange Online eller Exchange-hybrid gör du [det här steget.](#exchange-online)
- Om du använder SharePoint Online gör du [det här steget.](#sharepoint-online)
- Om du använder en MDM-lösning (Mobile Device Management) från tredje part gör du [det här steget.](#mobile)
- Om du använder en tredjepartstjänst eller verksamhetsbaserade appar som är integrerade med Office 365 ska du göra [det här steget.](#line-of-business-apps)
- Om du även använder Azure-tjänster utöver de som ingår i din Office 365-prenumeration gör du [det här steget.](#microsoft-azure)
- Om du även använder Dynamics 365 gör du [det här steget.](#dynamics365)
- Om du även använder Power BI gör du [det här steget.](#power-bi)
- För DNS-ändringar gör du [det här steget.](#dns)
- Om du använder federerad identitet gör du [följande.](#federated-identity)

## <a name="applies-to-everyone"></a>Gäller för alla

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Förbered dig för att meddela användarna om omstart och inloggning på och ut från sina klienter efter migreringen. | Office-klientlicensiering kommer att övergå från Microsoft Cloud Deutschland till Office 365-tjänster under migreringen. Klienter hämtar en ny giltig licens när de har loggat ut från och in på Office-klienter. | Användarnas Office-produkter behöver uppdatera licenser från Office 365-tjänster. Om licenserna inte uppdateras kan verifieringsfel uppstå i Office-produkter. |
| Säkerställa nätverksanslutningen till [URL:er och IP-adresser för Office 365-tjänster.](https://aka.ms/o365urls) | Alla klienter och tjänster hos kunden som används för att få åtkomst till Office 365-tjänsten måste kunna komma åt slutpunkterna för globala Office 365-tjänster. <br>Om du eller dina samarbetspartner har brandväggsregler som skulle förhindra åtkomst till URL:er och IP-adresser som listas i URL:er och IP-adresser för [Office 365-tjänster](https://aka.ms/o365urls) måste du ändra brandväggsregler för att tillåta åtkomst till de globala tjänstslutpunkterna för Office 365| Fel i tjänsten eller klientprogramvaran kan inträffa om detta inte görs före fas 4  |
| Avbryt utvärderingsprenumerationer. | Utvärderingsprenumerationer migreras inte och kommer att blockera överföring av betalda prenumerationer. | Utvärderingstjänster har upphört att gälla och är inte fungerande om användare kommer åt dem efter att de har avbrytas. |
| Analysera skillnaderna i licensfunktioner mellan Microsoft Cloud Deutschland och Office 365-tjänster. | Office 365-tjänster innehåller ytterligare funktioner och tjänster som inte är tillgängliga i den aktuella Microsoft Cloud Deutschland. Under prenumerationsöverföringen blir nya funktioner tillgängliga för användarna. | <ul><li> Analysera de olika funktionerna som tillhandahålls av licenserna för Microsoft Cloud Deutschland och Office 365-tjänster. Börja med [Tjänstbeskrivning för Office 365-plattformen.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) </li><li> Avgöra om några nya funktioner i Office 365-tjänsterna ska inaktiveras först för att begränsa effekter för användare eller ändringshantering samt ändra användarlicenstilldelningar efter behov. </li><li>Förbereda användare och supportpersonal för nya tjänster och funktioner som tillhandahålls av Office 365-tjänster. |
| Skapa bevarandeprinciper för [hela organisationen för](https://docs.microsoft.com/microsoft-365/compliance/retention) att skydda från oavsiktlig borttagning av innehåll under migreringen.  |<ul><li>Kunder kan välja att aktivera en bevarandeprincip för hela organisationen för att säkerställa att innehåll inte oavsiktligt tas bort av slutanvändare under migreringen. </li><li>Bevarande är inte obligatoriskt, eftersom bevarande som sätts in när som helst under migreringen fungerar som förväntat, men att ha en bevarandeprincip är en säkerhetsmekanism för säkerhet. En bevarandeprincip kanske inte används av alla kunder, särskilt de som är oroliga för bevarandet.</li></ul>| Använd bevarandeprincip enligt beskrivningen i [Läs mer om bevarandeprinciper och bevarandeetiketter.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) Fel i tjänsten eller klientprogramvaran kan inträffa om detta inte görs före fas 4 av 9. </li></ul>|
| Rätt licens overage | I vissa fall kan kunder använda fler tjänster än vad som köps. Det här villkoret kallas för ett licensfel. Microsoft kan inte migrera kunder som har ett licensavbrott från Microsoft Cloud Deutschland till de tyska datacenterområdena. För att säkerställa kontinuerlig åtkomst till tjänsten och data kräver varje tilldelad användare en licens. | Alla kunder | Kunder måste utvärdera och lösa villkoret för licensavbrott genom köp av ytterligare licenser eller genom att ta bort licenser från användare. |
|||||

## <a name="active-directory-federation-services-ad-fs"></a>AD FS (Active Directory Federation Services)

**Gäller för:** Kunder som använder AD FS lokalt för att autentisera användare som ansluter till Microsoft Office 365

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| [Säkerhetskopiering av AD FS-servergruppen (Active Directory Federation Services) för](ms-cloud-germany-transition-add-adfs.md#backup) katastrofåterställningsscenarier. | Kunder måste backa AD FS-servergruppen på rätt sätt för att säkerställa att beroende part-förtroenden för globala slutpunkter för & Germany kan återställas utan att utfärdare URI för domänerna vidrörs. Microsoft rekommenderar att du använder AD FS Rapid Restore för en säkerhetskopia av servergruppen och respektive återställning, om det behövs. | Åtgärd som krävs. Inaction will result in service impact during the migration if the AD FS farm of the customer fails. Mer information finns i [ADFS-migreringsstegen](https://docs.microsoft.com/microsoft-365/enterprise/ms-cloud-germany-transition-add-adfs) |
||||

## <a name="exchange-online"></a>Exchange Online

**Gäller för:** Exchange Online-kunder som har aktiverat delning av kalender och tillgänglighet för adressutrymme.

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Meddela externa partner om den kommande övergången till Office 365-tjänster. | I konfigurationer av tillgänglighetsadressutrymmet går det att dela ledig/upptagen-information med Office 365. | Om du inte gör det kan det leda till service- eller klientfel i en senare fas av kundmigrering. |
|||||

### <a name="exchange-online-hybrid-configuration"></a>Exchange Online-hybridkonfiguration

**Gäller för:** Exchange Online-kunder med en aktiv Exchange-hybridkonfiguration

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Uppdatera till den senaste versionen av hybridkonfigurationsguiden (HCW) när som helst innan klientorganisationen anger migreringssteg 5. Du kan starta aktiviteten direkt när du har fått meddelandet om att migreringen av Office 365-klientorganisationen har startat.<br><br> Microsoft Cloud Deutschland-hybrid Exchange Online-kunder måste avinstallera tidigare versioner av HCW och sedan installera och köra den senaste versionen (17.0.5378.0 eller senare) från [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) . |<ul><li>Den senaste versionen av HCW innehåller nödvändiga uppdateringar för att stödja kunder som håller på att övergå från Microsoft Cloud Deutschland till Office 365-tjänster.</li><li> Uppdateringar omfattar ändringar av lokala certifikatinställningar för Skicka anslutaren och Receive-anslutningen.</li><li> Exchange-administratörer måste installera OM HCW när som helst innan fas 5 av 9 (Exchange-migrering) startar.<br>När du kör HCW före fas 5 väljer du "Office 365 Germany" på den andra sidan i HCW under _Office 365 Exchange Online_ i listrutan under Min Office _365-organisation_ är värd</li><li>**Obs!** När du har slutfört migreringen för Office 365-klientorganisationen tar du bort och installerar HCW igen, den här gången med hjälp av inställningarna för Office 365 i hela världen på den andra sidan av HCW-enheten för att slutföra hybridkonfigurationen med den globala Exchange Online-tjänsten.</li></ul>|Det går inte att köra HCW före fas 5 (Exchange-migrering) kan resultera i tjänst- eller klientfel. |
||||

## <a name="sharepoint-online"></a>SharePoint Online

**Gäller för:** Kunder som använder SharePoint 2013 lokalt


| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Begränsa SharePoint 2013-arbetsflöden som används under SharePoint Online-migreringen. | Minska SharePoint 2013-arbetsflöden och slutför direktarbetsflöden före övergångar. | Inaction may result in user confusion and help desk calls. |
||||

## <a name="skype-for-business-online"></a>Skype för företag online

**Gäller för:** Skype för företag – Online-kunder

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Distribuera Teams-skrivbordsklient för användare med åtkomst till Skype för företag i Tyskland. | Migreringen flyttar Skype för företag-användare till Microsoft Teams för samarbete, samtal och chatt. Distribuera skrivbordsklienten för Microsoft Teams eller kontrollera att en webbläsare som stöds är tillgänglig. | Om du inte gör det innebär det att Microsoft Teams-samarbetstjänster inte är tillgängliga. |
| Granska och förbereda dig för migreringsrelaterade DNS-ändringar. | Ändringar av kundens DNS-zon för Skype för företag – Online. |<ul><li>Vi rekommenderar att du uppdaterar TTL (Time-to-Live) för alla kundägda domän-DNS-poster till 5 minuter för att underlätta uppdatering av DNS-poster. Men det Microsoft-hanterade cutover som är kopplat till denna DNS-ändring kan inträffa när som helst inom det angivna 24-timmarsändringsfönstret. </li><li>Avbrott i tjänsten kan komma att vara möjlig i framtiden. Användarna kan inte logga in i Skype för företag och dirigeras om till den migrerade Teams-upplevelsen i Office 365-tjänsterna. </li></ul>|
| Förbered utbildning och förberedelser för övergången till Microsoft Teams för slutanvändare och administration. | Se till att du har lyckats med övergången från Skype till Teams genom att planera användarkommunikation och beredskap. | <ul><li>Klienter måste vara medvetna om de nya tjänsterna och hur de ska använda när deras tjänster har övergåt till Office 365-tjänsterna. </li><li>När DNS-ändringar har gjorts för både kunddomänerna och den första domänen kan användarna logga in i Skype för företag och se till att de nu migreras till Teams. Det skulle även ladda ned skrivbordsklienten för Teams i bakgrunden. </li></ul>|
||||

## <a name="mobile"></a>Mobil

Om du använder en MDM-lösning (Mobile Device Management) från tredje part:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Förbered utbildning för slutanvändare och administration om att användare tar bort och lägger till sitt konto i Microsoft Outlook för iOS och Android. | Microsoft Outlook för iOS- och Android-konton som konfigurerats med postlådor i Microsoft Cloud Deutschland kan behöva tas bort och läggas till i Outlook igen för att den nya konfigurationen av Office 365-tjänsterna ska kunna synkroniseras. | Microsoft Outlook för iOS- och Android-kunder | Outlook-postlådor som tidigare konfigurerats för Microsoft Cloud Deutschland kanske inte hämtar den nya Office 365-tjänstkonfigurationen, vilket leder till fel och försämrad prestanda i andra användarupplevelser. IT-administratörer uppmanas att ta fram dokumentation som proaktivt instruerar användarna att ta bort och lägga till sina konton i Microsoft Outlook för iOS och Android om problem med inloggning eller synkronisering av e-post uppstår efter migreringen. |
| Avgöra om någon konfiguration krävs efter migreringen. | MdM-lösningar (Mobile Device Management) kan ha som `outlook.de` målslutpunkter. I den här övergången till Office 365-tjänster bör klientprofiler uppdateras till URL:en för Office 365-tjänster, `outlook.office365.com` . | Exchange Online- och MDM-kunder | Klienter kan fortsätta att fungera medan slutpunkten är tillgänglig, men de kommer att misslyckas `outlook.de` om Microsoft Cloud Deutschland-slutpunkter inte längre är tillgängliga. |
|||||

## <a name="line-of-business-apps"></a>Verksamhetsbaserade appar

Om du använder en tredjepartstjänst eller verksamhetsbaserade appar som är integrerade med Office 365: 

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Avgöra om någon konfiguration krävs efter migreringen. | Tredjepartstjänster och program som integrerar med Office 365 kan kodas så att de förväntar sig Microsoft Cloud Deutschland IP-adresser och URL-adresser. | Obligatorisk åtgärd. Inaction kan resultera i fel i tjänsten eller klientprogramvaran. |
||||

## <a name="dynamics-365"></a>Dynamics 365

**Gäller för:** Kunder som använder Microsoft Dynamics

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| För prenumerationer i begränsat läge för Dynamics 365 laddar du ned produktionsmiljön för Dynamics SQL-instansen från din Dynamics 365-prenumeration i Microsoft Cloud Deutschland. Den senaste säkerhetskopieringen för produktion bör återställas till begränsat läge före migrering i begränsat läge. | Migrering av Dynamics 365 kräver att kunder ser till att miljön i begränsat läge uppdateras med den senaste produktionsdatabasen. | FastTrack-teamet hjälper kunder att utföra torr körningar för att verifiera versionsuppgraderingen från 8.x till 9.1.x. |
||||

## <a name="power-bi"></a>Power BI

**Gäller för:** Power BI-kunder 

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Borttagning av objekt från Power BI-prenumerationer som inte migreras från Power BI Microsoft Cloud Deutschland till Office 365-tjänster. | Migrering av Power BI-tjänster kräver åtgärder från kunder för att ta bort vissa artefakter, till exempel datamängder och instrumentpaneler. | <ul><li>Administratörer kan behöva ta bort följande objekt från prenumerationen: </li><li>Real-Time datauppsättningar (till exempel strömmande datamängder eller push-datauppsättningar) </li><li>Konfiguration och datakälla för lokal Power BI-datagateway </li></ul>|
||||

## <a name="dns"></a>DNS

**Gäller för:** Kunder som använder Office-skrivbordsklienten (Microsoft 365-appar, Office 365 ProPlus, Office 2019, 2016, ...)<br>
Ta bort MSOID, CName från kundägd DNS om det finns när som helst innan Azure Active Directory (Azure AD) klipps över. Du kan ange en TTL på 5 minuter så att ändringen snabbt kan genomföras.

## <a name="federated-identity"></a>Federerad identitet

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Lägg till en identifierare för enkel inloggning (SSO) i ett befintligt beroende tredjepartsförtroende och inaktivera automatiska uppdateringar av AD FS-metadata. | Ett ID måste läggas till i DET AD FS-förtroende som parten litar på innan migreringen påbörjas. Inaktivera automatisk uppdatering av metadatauppdateringar för att undvika att tredjepartsidentifierare tas bort av misstag. <br><br> Kör det här kommandot som en enda kommandorad på AD FS-servern: <br>`Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de', 'https://login.microsoftonline.de/extSTS.srf', 'https://login.microsoftonline.de') -AutoUpdate $False`
| Organisationer med federerad autentisering | Åtgärd som krävs. Inaction before Phase 4 of 9 (SharePoint) will result in service impact during the migration.  |
| Generera förlitande part-förtroende för globala Azure AD-slutpunkter. | Kunder måste manuellt skapa ett förtroende för förlitande part (RPT) till [globala](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) slutpunkter. Det gör du genom att lägga till en ny rapport för indatatjänst (RPT) via GUI genom att dra nytta av URL:en för globala federationsmetadata och sedan använda [Azure AD RPT-anspråksregler](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) (i AD FS-hjälpen) för att generera anspråksreglerna och importera dem till rapportgruppen. | Organisationer med federerad autentisering | Åtgärd som krävs. Inaction kommer att resultera i tjänst påverkan under migreringen. |
|||||

## <a name="microsoft-azure"></a>Microsoft Azure

Om du använder samma Azure Active Directory-identitetspartition för Office 365 och Microsoft Azure i Microsoft Cloud Deutschland-instansen ska du se till att du förbereder dig för en kunddriven migrering av Microsoft Azure-tjänster.
Migreringen av Microsoft Azure-tjänster får inte startas innan din Office 365-klientorganisation har nått migrering fas 3 och måste slutföras innan migreringsfasen 8 har slutförts.

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Avgör vilka Azure-tjänster som används och förbereda en framtida migrering från Tyskland till Office 365-tjänstklientorganisationen genom att arbeta med dina partner. Följ stegen som beskrivs i [Azure-migreringsspelboken](https://docs.microsoft.com/azure/germany/germany-migration-main). |<ul><li>Migrering av Azure-resurser är ett kundansvar och kräver manuella åtgärder enligt angivna steg. Det är viktigt att förstå vilka tjänster som används i organisationen för att migreringen av Azure-tjänster ska lyckas. </li><li> Office 365 Germany-kunder som har Azure-prenumerationer med samma identitetspartition (organisation) måste följa den Microsoft-bestämt ordningen när de kan påbörja prenumerations- och tjänstmigrering.</li></ul>|<ul><li>Kunder kan ha flera Azure-prenumerationer, varje prenumeration som innehåller infrastruktur, tjänster och plattformskomponenter. </li><li> Administratörer bör identifiera prenumerationer och intressenter för att säkerställa att snabb migrering och validering är möjlig som en del av den här migreringshändelsen. </li><li>Om inte de här prenumerationerna och Azure-komponenterna slutförs inom den angivna tidslinjen påverkas slutförandet av Office- och Azure AD-övergången till Office 365-tjänsterna, och data kan gå förlorade. </li><li> Ett meddelande i Meddelandecenter signalerar punkten då en kundledd migrering kan starta. </li></ul>|
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

- [Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i nya tyska datacenterområden](ms-cloud-germany-transition.md)
- [Migreringshjälp för Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Så här väljer du in för migrering](ms-cloud-germany-migration-opt-in.md)
- [Kundupplevelse under migreringen](ms-cloud-germany-transition-experience.md)

Flytta genom övergången:

- [Åtgärder och påverkan i migreringsfaser](ms-cloud-germany-transition-phases.md)
- [Ytterligare arbete](ms-cloud-germany-transition-add-pre-work.md)
- Ytterligare information för [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [enheter,](ms-cloud-germany-transition-add-devices.md) [upplevelser](ms-cloud-germany-transition-add-experience.md)och [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Molnappar:

- [Information om Dynamics 365-migreringsprogram](https://aka.ms/d365ceoptin)
- [Information om Migreringsprogram för Power BI](https://aka.ms/pbioptin)
- [Komma igång med uppgraderingen till Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
