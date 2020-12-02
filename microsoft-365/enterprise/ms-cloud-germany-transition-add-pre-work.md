---
title: Ytterligare information för arbets uppgifter för migrering från Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
description: 'Sammanfattning: ytterligare information före arbete som flyttas från Microsoft Cloud Tyskland (Microsoft Cloud Deutschland) till Office 365-tjänster i det nya tyska data centret.'
ms.openlocfilehash: 41953aa9d91faa91bd983fbbc8d93baf08c172ed
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551717"
---
# <a name="additional-pre-work-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Ytterligare information för arbets uppgifter för migrering från Microsoft Cloud Deutschland

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Kontrol lera nätverks anslutningen till [Office 365-adresser och IP-adresserna](https://aka.ms/o365urls). | Alla klienter och tjänster som tillhandahålls av kunden och som används för att komma åt Office 365-tjänsten måste kunna komma åt slut punkter för Office 365-tjänster. | Alla över gångs kunder och kunder med nätverks åtkomst begränsat till Microsoft Cloud Deutschland. | Nödvändig åtgärd. Inåtgärd kan leda till att tjänsten eller klient program varan inte fungerar. |
| Granska och förbereda för systemrelaterade DNS-ändringar. | Kunden förbereder DNS-poster för Exchange Online och Exchange Online Protection (MX-post osv.). | Exchange Online-kunder | Det här är en Rekommenderad åtgärd. Ingen åtgärd innebär att migrerade kunders e-post kan dirigera via Microsoft Cloud Deutschland tills Microsoft Cloud Deutschland-tjänsterna är inaktiverade. |
| Granska och förbereda för systemrelaterade DNS-ändringar. | Ändringar av kundägda DNS-zoner för Skype för företag – online. | Skype för företag – Online-kunder | -Vi rekommenderar att du uppdaterar TTL-värdet (Time-to-Live) för alla kunder som ägs av domänen till fem minuter för att påskynda uppdateringen av DNS-poster. Den Microsoft-hanterade snabbmigrering som är kopplad till den här DNS-ändringen kan komma att visas när du är i ändrings fönstret. <br><br> -Det är möjligt att störa en tjänst. Användare kommer inte att kunna logga in på Skype för företag och omdirigeras till de migrerade team funktionerna i Office 365-tjänsterna. |
| Förbereda slutanvändares-och administrations utbildning och-beredskap för över gången till Microsoft Teams. | Lyckas med över gången från Skype till grupper genom att planera användarnas kommunikation och beredskap. | Skype för företag – Online-kunder | -Klienter måste vara medvetna om de nya tjänsterna och hur de ska användas när deras tjänster övergår till Office 365-tjänsterna. <br><br> -När DNS-ändringar görs för både Customer alternativa Domains och initial Domain kan användarna logga in i Skype för företag och se att de nu migreras till Teams. Det här kan även hämta Skriv bords klienten för grupper i bakgrunden. |
| Förbereda slutanvändares-och administrations utbildning för användare att ta bort och lägga till deras konto i Microsoft Outlook för iOS och Android. | Microsoft Outlook för iOS-och Android-konton som har kon figurer ATS med post lådor i Microsoft Cloud Deutschland kan behöva tas bort och läggas till i Outlook för att korrekt kunna synkronisera de nya Office 365-tjänsterna. | Kunder i Microsoft Outlook för iOS och Android | Outlook-postlådor som har kon figurer ATS tidigare för Microsoft Cloud Deutschland kanske inte hämtar den nya Office 365-tjänstens konfiguration, leder till fel och försämrad prestanda för andra användar upplevelser. IT-administratörer uppmuntras att tillhandahålla dokumentation som proaktiva anger att användare ska kunna ta bort och lägga till sina konton i Microsoft Outlook för iOS och Android om problem med att logga in eller synkronisera e-post sker efter migreringen. |
| Förbereda för att meddela användare om att starta om och logga in i och ut ur sina klienter efter migreringen. | Klient licenser för Office övergår över från Microsoft Cloud Deutschland till Office 365-tjänster i migreringen. Klienterna hämtar en ny giltig licens efter utloggning från och in på Office-klienter. | Microsoft 365-appar |  Användarnas Office-produkter måste uppdatera licenser från Office 365-tjänster. Om licenser inte uppdateras kan Office-produkter få licens validerings fel. |
| Avbryt eventuella prov abonnemang. | Utvärderings prenumerationer migreras inte och blockerar överföring av betalda abonnemang. | Alla kunder | Utvärderings tjänsterna har upphört att gälla och är inte tillgängliga för användare efter annullering. |
| Distribuera Teams-klienten för användare som använder Skype för företag i Tyskland. | Migreringen flyttar användare till Teams för samarbete, samtal och chatt. Du kan antingen distribuera Teams-klienten eller kontrol lera att det finns en webbläsare som stöds. | Skype för företag-kunder | Inåtgärd innebär att Teams samarbets tjänster inte är tillgängliga. |
| Analysera skillnader i licens funktionerna mellan Microsoft Cloud Deutschland och Office 365-tjänsterna. | Office 365-tjänster inkluderar ytterligare funktioner och tjänster som inte är tillgängliga i det aktuella Microsoft Cloud-Deutschland. Under prenumerations överföring blir nya funktioner tillgängliga för användarna. | Alla kunder | -Analysera de olika funktioner som tillhandahålls av licenserna för Microsoft Cloud Deutschland och Office 365-tjänsterna. Börja med [beskrivningen av Office 365 Platform service](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description). <br><br> -Ta reda på om nya funktioner i Office 365-tjänsterna först inaktive ras för att begränsa följderna för användare eller för användar ändrings hantering och ändra användar licens tilldelningar efter behov. <br><br> -Förbered användare och supportavdelning för nya tjänster och funktioner som tillhandahålls av Office 365-tjänster. |
| Skapa organisations [principer](https://docs.microsoft.com/microsoft-365/compliance/retention) för hela organisationen för att skydda från oavsiktlig borttagning av innehåll under migreringen.  | – För att säkerställa att innehållet inte oavsiktligt tas bort av slutanvändare under migreringen kan kunderna välja att aktivera en bevarande princip för hela organisationen. <br><br> -Även om kvarhållning inte är obligatoriskt, eftersom undantagen när som helst under migreringen bör fungera som förväntat, är en säkerhets mekanism för säkerhets kopiering. Samtidigt kan ingen bevarande princip användas av alla kunder, särskilt dem som bekymrar sig över. | Office-kunder | Tillämpa bevarande policy enligt beskrivningen i [Läs mer om bevarande principer och bevarande etiketter](https://docs.microsoft.com/microsoft-365/compliance/retention-policies). |
| [Säkerhets kopiering av AD FS-servergrupper (Active Directory Federation Services)](ms-cloud-germany-transition-add-adfs.md#backup) för katastrof återställning. | Kunderna behöver säkerhetskopiera AD FS-servergruppen på lämpligt sätt för att säkerställa att förlitande part-förtroenden till globala & Tyskland slut punkter kan återställas utan att den som utfärdar utgivaren är i domänen. Microsoft rekommenderar att du använder AD FS Rapid Restore för en säkerhets kopia av Server gruppen och respektive återställning, om det behövs. | Organisationer för extern autentiseringsprocess | Nödvändig åtgärd. Inåtgärd innebär att tjänst påverkan under migreringen sker om kundens AD FS-grupp inte fungerar. |


## <a name="exchange-online"></a>Exchange Online

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Meddela externa partners för den kommande över gången till Office 365-tjänster. | Med konfigurationer för tillgänglighets adress utrymme kan du dela med dig av ledig/upptagen-information med Office 365. | Exchange Online-kunder som har aktiverat delning av kalender-och tillgänglighets adress utrymme. | Nödvändig åtgärd.  Underlåtenhet att göra detta kan leda till tjänst-eller klient fel vid en senare fas av kundmigrering. |
|||||

Om du har hybrid Exchange:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Avinstallera tidigare versioner av hybrid konfigurations guiden (HCW) och installera och kör den senaste versionen, 17.0.5378.0, från [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) . | Den senaste versionen av HCW inkluderar nödvändiga uppdateringar för att stödja kunder som går över från Microsoft Cloud Deutschland till Office 365-tjänster. <br><br> Uppdateringar inkluderar ändringar av lokala certifikat inställningar för skicka och ta emot koppling. | Exchange Online-kunder som använder hybrid distribution | Nödvändig åtgärd. Om du inte gör det kanske tjänst-eller klient fel uppstår. |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

Om du har SharePoint 2013:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Begränsa SharePoint 2013-arbetsflöden, Använd under migreringen av SharePoint Online. | Minska arbets flöden i SharePoint 2013 och färdigställa arbets flöden före över gångarna. | SharePoint Online-kunder | Inåtgärd kan leda till användar förvirring och helpdesk-samtal. |
|||||

<!--
[Reference:  If Pre-Work][ SharePoint 2013 ]
--> 

## <a name="mobile"></a>Mobil

Om du använder en lösning från en tredjepartsleverantör (Mobile Device Management):

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Avgöra om en omkonfiguration krävs efter migreringen. | MDM-lösningar kan nå `outlook.de` slut punkter. I den här över gången till Office 365-tjänster ska klient profilerna uppdateras till URL-adressen för Office 365-tjänster `outlook.office365.com` . | Exchange Online-och MDM-kunder | Klienter kan fortsätta fungera när `outlook.de` slut punkten är tillgänglig, men de fungerar inte om Microsoft Cloud Deutschland slut punkter inte längre är tillgängliga. |
|||||

<!--
[Reference:  If Pre-Work][ Mobile]
-->             

## <a name="line-of-business-apps"></a>Branschspecifika program

Om du använder en tjänst från tredje part eller ett LOB-program som är integrerade med Office 365: 

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Avgöra om en omkonfiguration krävs efter migreringen. | Tjänster och program från tredje part som integreras med Office 365 kan kodas för att förvänta sig Microsoft Cloud Deutschland IP-adresser och URL: er. | Alla kunder | Nödvändig åtgärd. Inåtgärd kan leda till att tjänsten eller klient program varan inte fungerar. |
|||||

<!--
[Reference:  If Pre-Work][ LOB]
--> 

## <a name="azure"></a>Azure 

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Fastställ vilka Azure-tjänster som används och förbereda framtida migrering från Tyskland till Office 365-tjänstens klient organisation genom att arbeta med dina partners. Följ stegen som beskrivs i [Azure migration Playbook](https://docs.microsoft.com/azure/germany/germany-migration-main). | Migrering av Azure-resurser är ett kund ansvar och kräver manuell ansträngning enligt anvisningarna. Det är viktigt att förstå vilka tjänster som används i organisationen för att kunna migrera Azure-tjänsterna. <br><br> Office 365 Germany-kunder som har Azure-abonnemang under samma identitetsmappen (organisation) måste följa Microsoft-den beskrivna ordningen när de kan påbörja migrering av prenumerationer och tjänster. | Azure-kunder | -Kunder kan ha flera Azure-abonnemang, alla abonnemang som innehåller infrastruktur, tjänster och plattforms komponenter. <br><br> -Administratörer bör identifiera prenumerationer och intressenter för att säkerställa att det går att migrera och validera meddelanden i den här migreringen. <br><br> Om det inte går att slutföra migreringen av dessa abonnemang och Azure-komponenterna inom den angivna tids linjen påverkar det slut för ande av Office-och Azure AD-överföring till Office 365-tjänster och kan leda till data förlust.  <br><br> -En avisering om meddelande Center signalerar den punkt där kund Lede migration kan påbörjas. |
|||||

<!--
[Reference:  If Azure Pre-Work][ Azure]
-->  

## <a name="dynamics-365"></a>Dynamics 365

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| För Dynamics 365 sandbox-prenumerationer ska du ladda ned produktions miljön för Dynamics SQL-instansen från din Dynamics 365-prenumeration i Microsoft Cloud Deutschland. Den senaste arbets säkerhets kopieringen bör återställas till sand lådan före sand låde migrering. | Migrering av Dynamics 365 kräver att kunderna ser till att den begränsade miljön uppdateras med den senaste produktions databasen. | Microsoft Dynamics-kunder | FastTrack-teamet hjälper kunder att genomföra torra sekvenser för att verifiera versions uppgraderingen från 8 till 9. x till 9.1. x. |
|||||

<!--
[Reference: Prework][Dynamics]
-->             

## <a name="power-bi"></a>Power BI

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Borttagning av objekt från Power BI-prenumerationer som inte migreras från Power BI-Deutschland till Office 365-tjänster. | Om du migrerar Power BI-tjänsterna måste kund åtgärden ta bort vissa artefakter, till exempel data mängder och instrument paneler. | Power BI-kunder | Administratörer kan behöva ta bort följande objekt från deras prenumeration: <br> -Real-Time data uppsättningar (till exempel direkt uppspelning eller push-datauppsättningar) <br> -Konfiguration och data källa i Power BI-lokal data Gateway |
|||||

<!--
[Reference: Prework][Power BI]
--> 

## <a name="dns"></a>SERVERTJÄNSTEN

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Granska och förbereda för DNS-ändring om den aktuella DNS-posten har en MSOID. | Ändringar av kundägda DNS-zoner | Office klient tjänst kunder | Uppdatera TTL-värdet (Time to Live) för kundägda DNS-poster till fem minuter om det finns en MSOID CName. |
|||||

<!--
[Reference: Prework][DNS]
-->             

## <a name="federated-identity"></a>Federerad identitet

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Generera förtroende för förlitande part för globala Azure AD-slutpunkter. | Kunderna måste manuellt skapa ett förlitande part-förtroende för [globala](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) slut punkter. Det gör du genom att lägga till en ny RPT via GUI genom att använda URL-adressen för den globala federationsmetadata (i AD [FS-hjälpen](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) ) för att generera anspråks reglerna och importera dem till en RPT. | Organisationer för extern autentiseringsprocess | Nödvändig åtgärd. Inåtgärd innebär att tjänsten påverkas under migreringen. |
|||||

<!--
[Reference: Prework][Federation]
-->  

## <a name="more-information"></a>Mer information

Komma igång:

- [Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i de nya tyska Data Center-regionerna](ms-cloud-germany-transition.md)
- [Hjälp för Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Så här väljer du för migrering](ms-cloud-germany-migration-opt-in.md)
- [Kund upplevelse under migreringen](ms-cloud-germany-transition-experience.md)

Flytta genom över gången:

- [Åtgärder och konsekvenser för migreringen](ms-cloud-germany-transition-phases.md)
- [Övrig för hands arbete](ms-cloud-germany-transition-add-pre-work.md)
- Ytterligare information om [tjänster](ms-cloud-germany-transition-add-general.md), [enheter](ms-cloud-germany-transition-add-devices.md), [erfarenheter](ms-cloud-germany-transition-add-experience.md)och [AD FS](ms-cloud-germany-transition-add-adfs.md).

Molnappar:

- [Information om programmet för Dynamics 365 migration](https://aka.ms/d365ceoptin)
- [Information om datamigreringshanteraren för Power BI](https://aka.ms/pbioptin)
- [Komma igång med din uppgradering av Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
