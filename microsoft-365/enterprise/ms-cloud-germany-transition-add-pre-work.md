---
title: Före migreringen från Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/18/2020
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
ms.openlocfilehash: 8160756bdbf973741f5e75f45dc2a2044f63e39b
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242848"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>Före migreringen från Microsoft Cloud Deutschland


Använd de här länkarna för att komma till de anvisningar som är relevanta för din organisation:

- Gör följande för alla [prenumerationer.](#applies-to-everyone)
- Om du använder Exchange Online- eller Exchange-hybrid gör du det [här steget.](#exchange-online)
- Om du använder SharePoint Online gör du så [här.](#sharepoint-online)
- Om du använder en MDM-lösning (Mobile Device Management) från tredje part gör du [det här steget.](#mobile)
- Om du använder en tredjepartstjänst eller verksamhetsbaserade appar som är integrerade med Office 365 gör du det [här steget.](#line-of-business-apps)
- Om du även använder Azure-tjänster utöver dem som ingår i din Office 365-prenumeration gör du [det här steget.](#azure)
- Om du också använder Dynamics 365 gör du [det här steget.](#dynamics365)
- Om du också använder Power BI gör du det [här steget.](#power-bi)
- Gör det här steget för [DNS-ändringar.](#dns)
- Om du använder federerad identitet gör du [så här.](#federated-identity)

## <a name="applies-to-everyone"></a>Gäller för alla

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Säkerställa nätverksanslutningen till [URL-adresser och IP-adresser för Office 365-tjänster.](https://aka.ms/o365urls) | Alla klienter och tjänster hos kunden som används för att få åtkomst till Office 365-tjänsten måste kunna komma åt Office 365-tjänstslutpunkterna. | Alla övergångskunder och kunder med nätverksåtkomst begränsad till Microsoft Cloud Deutschland. | Åtgärd krävs. Fel i tjänsten eller klientprogramvaran kan inträffa om detta inte har utförts före fas 4 av 9. |
| Granska och förbereda migreringsrelaterade DNS-ändringar. | Ändringar av DNS-zonändringar som ägs av kunder för Skype för företag – Online. | Skype för företag – Online-kunder | – Vi rekommenderar att du uppdaterar Time-to-Live (TTL) för alla kundägda domän-DNS-poster till 5 minuter för att underlätta uppdatering av DNS-poster. Men den Microsoft-hanterade övergången som är kopplad till denna DNS-ändring kan inträffa när som helst inom det angivna 24-timmarsbytesfönstret. <br><br> - Avbrott i tjänsten är möjligt i framtiden. Användarna kan inte logga in på Skype för företag och dirigeras om till den migrerade Teams-upplevelsen i Office 365-tjänsterna. |
| Förbered utbildning för slutanvändare och administration och förberedelser inför övergången till Microsoft Teams. | Lyckas med övergången från Skype till Teams genom att planera användarkommunikation och beredskap. | Skype för företag – Online-kunder | - Klienter måste vara medvetna om de nya tjänsterna och hur de ska använda när deras tjänster har övergår till Office 365-tjänsterna. <br><br> – När DNS-ändringarna har gjorts för både kunddomänerna och den initiala domänen loggar användarna in i Skype för företag och ser till att de nu migreras till Teams. Det skulle också ladda ned skrivbordsklienten för Teams i bakgrunden. |
| Förbered utbildning för slutanvändare och administration om att användare tar bort och lägger till sitt konto i Microsoft Outlook för iOS och Android. | Microsoft Outlook för iOS- och Android-konton som konfigurerats med postlådor i Microsoft Cloud Deutschland kan behöva tas bort och läggas till i Outlook igen för att kunna synkronisera den nya konfigurationen av Office 365-tjänster på rätt sätt. | Microsoft Outlook för iOS- och Android-kunder | Outlook-postlådor som tidigare konfigurerats för Microsoft Cloud Deutschland kanske inte hämtar den nya Office 365-tjänstkonfigurationen, vilket leder till fel och försämrad prestanda i andra användarupplevelser. IT-administratörer uppmanas att tillhandahålla dokumentation som proaktivt instruerar användarna att ta bort och lägga till sina konton i Microsoft Outlook för iOS och Android om problem med att logga in eller synkronisera e-post uppstår efter migreringen. |
| Förbered dem för att meddela användarna om omstart och inloggning till och från sina klienter efter migreringen. | Office-klientlicensiering kommer att övergå från Microsoft Cloud Deutschland till Office 365-tjänster under migreringen. Klienter hämtar en ny giltig licens när de har loggat ut från och in i Office-klienter. | Microsoft 365 Apps-kunder |  Användarnas Office-produkter behöver uppdatera licenser från Office 365-tjänster. Om licenser inte uppdateras kan verifieringsfel uppstå i Office-produkter. |
| Avsluta utvärderingsprenumerationer. | Utvärderingsprenumerationer migreras inte och blockerar överföring av betalda prenumerationer. | Alla kunder | Utvärderingstjänster upphör att gälla och fungerar inte om de används av användarna efter att de har avbrytas. |
| Distribuera Teams-skrivbordsklient för användare med åtkomst till Skype för företag i Tyskland. | Migrering flyttar användare till Teams för samarbete, samtal och chatt. Distribuera Teams-skrivbordsklienten eller se till att en webbläsare som stöds är tillgänglig. | Skype för företag-kunder | Inaction kommer att resultera i att Teams samarbetstjänster inte är tillgängliga. |
| Analysera skillnader i licensfunktioner mellan Microsoft Cloud Deutschland och Office 365-tjänster. | Office 365-tjänster innehåller ytterligare funktioner och tjänster som inte är tillgängliga i den aktuella Microsoft Cloud Deutschland. Under prenumerationsöverföring blir nya funktioner tillgängliga för användarna. | Alla kunder | - Analysera de olika funktionerna som tillhandahålls av licenserna för Microsoft Cloud Deutschland och Office 365-tjänster. Börja med [tjänstbeskrivning för Office 365-plattformen.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) <br><br> – Avgör om några nya funktioner i Office 365-tjänster först ska inaktiveras för att begränsa effekterna för användare eller för hantering av användarändring och ändra användarlicenstilldelningar efter behov. <br><br> - Förbereda användare och supportpersonal för nya tjänster och funktioner som tillhandahålls av Office 365-tjänster. |
| Skapa bevarandeprinciper [för hela organisationen för](https://docs.microsoft.com/microsoft-365/compliance/retention) att skydda mot oavsiktlig borttagning av innehåll under migreringen.  | – För att säkerställa att innehåll inte oavsiktligt tas bort av slutanvändare under migreringen kan kunder välja att aktivera en bevarandeprincip för hela organisationen. <br><br> – Även om bevarande inte krävs, eftersom kvarhållning som gjorts när som helst under migreringen bör fungera som förväntat, är en bevarandeprincip en säkerhetsmekanism för säkerhet. På samma gång kanske inte en bevarandeprincip används av alla kunder, särskilt de som är oroliga för att bevara bevarandet. | Office-kunder | Använd en bevarandeprincip enligt beskrivningen i [Läs mer om bevarandeprinciper och bevarandeetiketter.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) Fel i tjänsten eller klientprogramvaran kan inträffa om detta inte har utförts före fas 4 av 9.  |
| [Säkerhetskopiering av AD FS-servergruppen (Active Directory Federation Services)](ms-cloud-germany-transition-add-adfs.md#backup) för katastrofåterställningsscenarier. | Kunder måste backa AD FS-servergruppen på rätt sätt för att säkerställa att förtroenden för globala slutpunkter för & Germany kan återställas utan att utfärdare-URI för domänerna vidrörs. Microsoft rekommenderar att du använder AD FS Rapid Restore för en säkerhetskopia av servergruppen och motsvarande återställning, om det behövs. | Organisationer med federerad autentisering | Åtgärd som krävs. Inaction resulterar i tjänst påverkan under migreringen om AD FS-servergruppen för kunden misslyckas. Mer information finns i [ADFS-migreringssteg] (https://docs.microsoft.com/microsoft-365/enterprise/ms-cloud-germany-transition-add-adfs) |


## <a name="exchange-online"></a>Exchange Online

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Meddela externa partner om den kommande övergången till Office 365-tjänster. | Med konfigurationer av tillgänglighetsadressutrymme kan du dela ledig/upptagen-information med Office 365. | Exchange Online-kunder som har aktiverat delning av kalender och tillgängligt adressutrymme. | Åtgärd krävs.  Om du inte gör det kan det leda till service- eller klientfel i en senare fas av kundmigrering. |
|||||

<!--
Reworked as text:

**Step:** Notify external partners of the upcoming transition to Office 365 services.

**Description:** Availability address space configurations allow sharing of free/busy information with Office 365. | Exchange Online customers who have enabled sharing calendar and availability address space.

**Applies to:** Exchange Online customers who have enabled sharing calendar and availability address space.

**Impact:** Required action.  Failure to do so may result in service or client failure at a later phase of customer migration.

- **Step:** Notify external partners of the upcoming transition to Office 365 services.

- **Description:** Availability address space configurations allow sharing of free/busy information with Office 365. | Exchange Online customers who have enabled sharing calendar and availability address space.

- **Applies to:** Exchange Online customers who have enabled sharing calendar and availability address space.

- **Impact:** Required action.  Failure to do so may result in service or client failure at a later phase of customer migration.

--> 


### <a name="for-hybrid-exchange"></a>För Exchange-hybrid

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Avinstallera tidigare versioner av hybridkonfigurationsguiden (HCW) och installera sedan och kör den senaste versionen, 17.0.5378.0, [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) från. | Den senaste versionen av HCW innehåller uppdateringar som stöd för kunder som övergår från Microsoft Cloud Deutschland till Office 365 Services. <br><br> Uppdateringar omfattar ändringar av lokala certifikatinställningar för Skicka anslutare och Ta emot-anslutning. | Exchange Online-kunder som kör hybriddistribution | Åtgärd krävs. Om du inte gör det före fas 5 av 9 (Exchange) kan det leda till service- eller klientfel. |
|||||

<!--
Reworked as text:

**Step:** Uninstall previous versions of Hybrid Configuration wizard (HCW), and then install and execute the latest version, 17.0.5378.0, from [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard).

**Description:** The latest version of the HCW includes necessary updates to support customers who are transitioning from Microsoft Cloud Deutschland to Office 365 Services. <br><br> Updates include changes to on-premises certificate settings for Send connector and Receive connector.

**Applies to:** Exchange Online customers running Hybrid deployment

**Impact:** Required action. Failure to do so may result in service or client failure.
-->


## <a name="sharepoint-online"></a>SharePoint Online

Om du har SharePoint 2013:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Begränsa SharePoint 2013-arbetsflöden, som används under SharePoint Online-migreringen. | Minska SharePoint 2013-arbetsflöden och slutför direktarbetsflöden före övergångar. | SharePoint Online-kunder | Inaction kan resultera i förvirring och supportsamtal. |
|||||

## <a name="mobile"></a>Mobil

Om du använder en MDM-lösning (Mobile Device Management) från tredje part:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Avgöra om någon konfiguration krävs efter migreringen. | MDM-lösningar kan ha som `outlook.de` målslutpunkter. I den här övergången till Office 365-tjänster bör klientprofilerna uppdateras till URL:en för Office 365-tjänster. `outlook.office365.com` | Exchange Online- och MDM-kunder | Klienter kan fortsätta att fungera medan slutpunkten är tillgänglig, men de kommer att misslyckas om `outlook.de` Microsoft Cloud Deutschland-slutpunkter inte längre är tillgängliga. |
|||||

## <a name="line-of-business-apps"></a>Verksamhetsbaserade appar

Om du använder en tredjepartstjänst eller verksamhetsbaserade appar som är integrerade med Office 365: 

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Avgöra om någon konfiguration krävs efter migreringen. | Tredjepartstjänster och program som integrerar med Office 365 kan kodas för att räkna med microsoft Cloud Deutschland IP-adresser och URL-adresser. | Alla kunder | Åtgärd krävs. Inaction kan resultera i fel i tjänsten eller klientprogramvaran. |
|||||

## <a name="azure"></a>Azure 

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Ta reda på vilka Azure-tjänster som används och förbered för framtida migrering från Tyskland till Klientorganisationen för Office 365-tjänster genom att arbeta med dina partner. Följ anvisningarna i [Azure-migreringsspelboken.](https://docs.microsoft.com/azure/germany/germany-migration-main) | Migrering av Azure-resurser är ett kundansvar och kräver manuell insats genom att följa de angivna stegen. Att förstå vilka tjänster som används i organisationen är avgörande för en lyckad migrering av Azure-tjänster. <br><br> Office 365 Germany-kunder som har Azure-prenumerationer under samma identitetspartition (organisation) måste följa den Microsoft-angivna ordningen när de kan påbörja prenumerations- och tjänstemigrering. | Azure-kunder | - Kunder kan ha flera Azure-prenumerationer, varje prenumeration som innehåller infrastruktur, tjänster och plattformskomponenter. <br><br> – Administratörer bör identifiera prenumerationer och intressenter för att säkerställa att snabb migrering och validering är möjlig som en del av den här migreringshändelsen. <br><br> Om det inte går att slutföra migreringen av dessa prenumerationer och Azure-komponenter inom den angivna tidslinjen påverkar slutförandet av Övergången för Office och Azure AD till Office 365-tjänsterna och kan resultera i dataförlust.  <br><br> – Ett meddelande i Meddelandecenter signalerar vid vilken punkt en kundledd migrering kan starta. |
|||||

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

## <a name="dynamics-365"></a>Dynamics 365

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| För prenumerationer på Dynamics 365 i begränsat läge måste du ladda ned produktionsmiljön för Dynamics SQL-instansen från din Dynamics 365-prenumeration i Microsoft Cloud Deutschland. Den senaste säkerhetskopieringen för produktionen bör återställas till sandbox-miljön före migrering i begränsat läge. | Migrering av Dynamics 365 kräver att kunderna ser till att miljön i begränsat läge uppdateras med den senaste produktionsdatabasen. | Microsoft Dynamics-kunder | FastTrack-teamet hjälper kunderna att utföra torr körningar för att verifiera versionsuppgraderingen från 8.x till 9.1.x. |
|||||

## <a name="power-bi"></a>Power BI

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Borttagning av objekt från Power BI-prenumerationer som inte migreras från Power BI Microsoft Cloud Deutschland till Office 365-tjänster. | Migrering av Power BI-tjänster kräver åtgärder från kunder för att ta bort vissa artefakter, till exempel datauppsättningar och instrumentpaneler. | Power BI-kunder | Administratörer kan behöva ta bort följande objekt från prenumerationen: <br> - Real-Time datauppsättningar (till exempel strömmande datamängder eller push-datauppsättningar) <br> - Konfiguration och datakälla för Lokal Power BI-datagateway |
|||||

## <a name="dns"></a>DNS

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Ta bort MSOID, CName från kundägd DNS om det finns när som helst innan Azure AD klipps över. Du kan ange en TTL på 5 minuter så att ändringen snabbt kan genomföras. | Ändringar av DNS-zonändringar som ägs av kunder | Office-klienttjänster till kunder | 
|||||

## <a name="federated-identity"></a>Federerad identitet

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Lägg till en identifierare för enkel inloggning (SSO) i ett befintligt beroende partförtroende och inaktivera automatiska uppdateringar av AD FS-metadata. | Ett ID måste läggas till i DET AD FS-förtroende som är beroende av parten innan migreringen startar. Inaktivera automatisk uppdatering för metadatauppdateringar för att undvika oavsiktlig borttagning av den förlitar sig på partidentifierare. <br><br> Kör det här kommandot på AD FS-servern: <br> `Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de','https://login.microsoftonline.de/extSTS.srf','https://login.microsoftonline.de') -AutoUpdate $False` | Organisationer med federerad autentisering | Åtgärd som krävs. Inaction before Phase 4 of 9 (SharePoint) will result in service impact during the migration.  |
| Generera förlitande partförtroende för globala Azure AD-slutpunkter. | Kunder måste manuellt skapa ett förlitande partförtroende (RPT) till [globala](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) slutpunkter. Det gör du genom att lägga till en ny export- och exporttjänsttjänst (RPT) via GUI med hjälp av URL:en för globala federationsmetadata och sedan använda [Azure AD RPT Claim Rules](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) (i AD FS-hjälpen) för att generera anspråksreglerna och importera dem till rapporttjänsten. | Organisationer med federerad autentisering | Åtgärd som krävs. Inaction kommer att resultera i tjänst påverkan under migreringen. |
|||||

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
