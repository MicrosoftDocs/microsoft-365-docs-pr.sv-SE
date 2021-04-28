---
title: Aktiviteter före migreringen från Microsoft Cloud Deutschland
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
ms.openlocfilehash: 9c3aff56f5d85cd1b98747ef5b747720af74fe02
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073943"
---
# <a name="pre-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Aktiviteter före migreringen från Microsoft Cloud Deutschland

Använd de här länkarna för att komma till de anvisningar före migreringen som är relevanta för din organisation.

Om du använder

- **Office 365 i Microsoft Cloud Deutschland** gör [du följande.](#general-tenant-migration-considerations)
- **Anpassade domäner** gör du [det här steget.](#dns-entries-for-custom-domains)
- **Office-appar**– tänk på [det här steget.](#office-apps)
- **SharePoint Online**– gör [det här steget.](#sharepoint-online)
- **Exchange Online eller** **Exchange-hybrid** gör du [det här steget.](#exchange-online)
- **Skype för företag – Online**– gör detta [steg.](#skype-for-business-online)
- **Dynamics 365**– gör [det här steget.](#dynamics365)
- **Power BI**, gör [det här steget.](#power-bi)

- **Active Directory Federation Services** för Azure AD Connect gör [du följande.](#active-directory-federation-services-ad-fs)
- **Tredjepartstjänster eller** **LOB-appar (verksamhetsbaserade appar)** som är integrerade med Office 365 gör du [på det här steget.](#line-of-business-apps)
- Det här steget är en MDM-lösning (Mobile Device Management) [från tredje part.](#mobile-device-management)
- **Azure-tjänster** med din Office 365-prenumeration gör du [det här steget.](#microsoft-azure)

## <a name="general-tenant-migration-considerations"></a>Allmänna överväganden vid klientmigrering

**Gäller för:** Alla kunder som använder Office 365 i Microsoft Deutschland Cloud-instansen

Office 365-klientorganisationen och användaridentifierare bevaras under migreringen. Azure AD-tjänstsamtal omdirigeras från Microsoft Cloud Deutschland till globala Office 365-tjänster och är transparenta mot Office 365-tjänster.

- Allmän dataskyddsförordning (GDPR) Data Subject Requests (DSRs) körs från Azure Admin-portalen för framtida förfrågningar. Alla äldre eller icke-kunddiagnostikdata som finns i Microsoft Cloud Deutschland tas bort vid eller före 30 dagar.
- Multifaktorautentisering (MFA) begär att Microsoft Authenticator ska visas som användarobjekt-ID (en GUID) medan klientorganisationen kopieras till Office 365-tjänster. MFA-begäranden fungerar som förväntat trots detta visningsbeteende.  Microsoft Authenticator-konton som aktiverades med office 365-tjänsters slutpunkter visar användarens huvudnamn (UPN).  Konton som läggs till med hjälp av Microsoft Cloud Deutschland-slutpunkter visar användarens ObjectID men fungerar med både Microsoft Cloud Deutschland- och Office 365-slutpunkter.

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Förbered dig för att meddela användarna om omstart och inloggning på och ut från sina klienter efter migreringen. | Office-klientlicensiering kommer att övergå från Microsoft Cloud Deutschland till Office 365-tjänster under migreringen. Klienter hämtar en ny giltig licens när de har loggat ut från och in på Office-klienter. | Användarnas Office-produkter behöver uppdatera licenser från Office 365-tjänster. Om licenserna inte uppdateras kan verifieringsfel uppstå i Office-produkter. |
| Säkerställa nätverksanslutningen till [URL:er och IP-adresser för Office 365-tjänster.](https://aka.ms/o365urls) | Alla klienter och tjänster hos kunden som används för att få åtkomst till Office 365-tjänsten måste kunna komma åt slutpunkterna för globala Office 365-tjänster. <br>Om du eller dina samarbetspartner har brandväggsregler som skulle förhindra åtkomst till URL:er och IP-adresser som listas i URL:er och IP-adresser för [Office 365-tjänster](https://aka.ms/o365urls) måste brandväggsregler ändra brandväggsregler för att ge åtkomst till de globala tjänstslutpunkterna för Office 365| Fel i tjänsten eller klientprogramvaran kan inträffa om detta inte görs före fas 4  |
| Avbryt utvärderingsprenumerationer. | Utvärderingsprenumerationer migreras inte och kommer att blockera överföring av betalda prenumerationer. | Utvärderingstjänster har upphört att gälla och är inte fungerande om användare kommer åt dem efter att de har avbrytas. |
| Analysera skillnaderna i licensfunktioner mellan Microsoft Cloud Deutschland och globala Office 365-tjänster. | Office 365-tjänster innehåller ytterligare funktioner och tjänster som inte är tillgängliga i den aktuella Microsoft Cloud Deutschland. Under prenumerationsöverföringen blir nya funktioner tillgängliga för användarna. | <ul><li> Analysera de olika funktionerna som tillhandahålls av licenserna för Microsoft Cloud Deutschland och Globala Office 365-tjänster. Börja med [Tjänstbeskrivning för Office 365-plattformen.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) </li><li> Avgöra om några nya funktioner i Office 365-tjänsterna ska inaktiveras först för att begränsa effekter för användare eller ändringshantering samt ändra användarlicenstilldelningar efter behov. </li><li>Förbereda användare och supportpersonal för nya tjänster och funktioner som tillhandahålls av Office 365-tjänster. |
| Skapa bevarandeprinciper för [hela organisationen för](https://docs.microsoft.com/microsoft-365/compliance/retention) att skydda från oavsiktlig borttagning av innehåll under migreringen.  |<ul><li>Kunder kan välja att aktivera en bevarandeprincip för hela organisationen för att säkerställa att innehåll inte oavsiktligt tas bort av slutanvändare under migreringen. </li><li>Bevarande är inte obligatoriskt, eftersom bevarande som sätts in när som helst under migreringen fungerar som förväntat, men att ha en bevarandeprincip är en säkerhetsmekanism för säkerhet. En bevarandeprincip kanske inte används av alla kunder, särskilt de som är oroliga för bevarandet.</li></ul>| Använd bevarandeprincip enligt beskrivningen i [Läs mer om bevarandeprinciper och bevarandeetiketter.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) Fel i tjänsten eller klientprogramvaran kan inträffa om detta inte görs före fas 4 av 9. </li></ul>|
|||||

## <a name="dns-entries-for-custom-domains"></a>DNS-poster för egna domäner

<!-- before phase 9 -->

**Gäller för:** Kunder som har angett en anpassad _msoid_ CNAME i sin egen DNS-domän eller med en domän för Exchange Online

Om den konfigureras påverkar _msoid_ CNAME bara kunder som använder Office-skrivbordsklienten (Microsoft 365-appar, Office 365 ProPlus, Office 2019, 2016, ...).

Om du har angett dns-CNAME med namnet _msoid_ i ett eller flera DNS-namnområden som du äger, måste du ta bort CNAME-namnet till slutet av fas 8 senast. Du kan ta bort _CNAME-msoid_ när som helst före slutet av fas 8.

Kontrollera om du har angett ett CNAME i DNS-namnområdet genom att följa stegen nedan och ersätta _contoso.com_ med ditt eget domännamn:

```console
nslookup -querytype=CNAME msoid.contoso.com
```

Om kommandoraden returnerar en DNS-post tar du bort _msoid_ CNAME från domänen.

> [!NOTE]
> Om du använder en egen domän för Exchange Online måste du ha åtkomst till din DNS-värd. Se till att du kan komma åt och redigera DNS-inställningarna, så kommer du att ändra DNS-poster under migreringen.

## <a name="office-apps"></a>Office-program

**Gäller för:** Kunder som använder Office-appar, särskilt på Windows-klienter <br>
**När den används:** Varje gång före fas 9 startar

För klientorganisationen av Office 365 under övergången till regionen "Tyskland" måste alla användare stänga, logga ut från Office 365 och tillbaka in för alla Office-skrivbordsprogram (Word, Excel, PowerPoint, Outlook osv.) och OneDrive för företag-klienten när klientorganisationens migrering har nått fas 9. Genom att logga ut och in kan Office-tjänsterna hämta nya autentiseringstoken från den globala Azure AD-tjänsten.

Detta krävs för alla klienter. För att migreringen ska gå smidigt rekommenderas det starkt att informera och instruera alla berörda användare i förväg och i ett tidigt skede om den här aktiviteten.

Kunder med hanterade Windows-klienter kan förbereda Windows-datorer med [Office CLIENT Cutover Tool (TIDE)](https://github.com/microsoft/OCCT). THE TIDE är utformad för att köras med jämna mellanrum på Windows-klienter tills klientorganisationen nått fas 9 av migreringen. När fas 9 har uppnåtts utför TIDE SÅ att alla nödvändiga ändringar utförs på datorn automatiskt utan interaktion med användaren.

TIDSFÖRD kan distribueras på Windows-klienter när som helst före fas 9. Om TIDE:t ska stödja migreringsupplevelsen rekommenderar vi att du startar distributionen så snart som möjligt för att hjälpa till med maximalt antal klienter.

## <a name="active-directory-federation-services-ad-fs"></a>AD FS (Active Directory Federation Services)

<!-- before phase 4 -->

**Gäller för:** Kunder som använder AD FS lokalt för att autentisera användare som ansluter till Microsoft Office 365<br>
**När den används:** Varje gång före fas 4 startar

Läsa och använda [ADFS-migreringsstegen](ms-cloud-germany-transition-add-adfs.md)

## <a name="sharepoint-online"></a>SharePoint Online

<!-- before phase 4 -->

**Gäller för:** Kunder som använder SharePoint 2013 lokalt<br>
**När den används:** Varje gång före fas 4 startar

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Begränsa SharePoint 2013-arbetsflöden som används under SharePoint Online-migreringen. | Minska SharePoint 2013-arbetsflöden och slutför direktarbetsflöden före övergångar. | Inaction may result in user confusion and help desk calls. |
||||

## <a name="exchange-online"></a>Exchange Online

<!-- before phase 5 -->

**Gäller för:** Exchange Online-kunder<br>
**När den används:** Någon tid före slutet av fas 9

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Meddela externa partner om den kommande övergången till Office 365-tjänster. |  Kunderna måste meddela sina partner som de har aktiverat för delning av kalender och tillgänglighet för adressutrymme (tillåt delning av ledig/upptagen-information med Office 365). Tillgänglighetskonfigurationen måste gå över till att använda [globala Office 365-slutpunkter](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide) när Exchange Online-migreringen har slutförts. | Om du inte gör det kan det leda till service- eller klientfel i en senare fas av kundmigrering. |
| Meddela användarna om obligatoriska IMAP4-/POP3-/SMTP-klientändringar. | Användare som har enhetsanslutningar till Microsoft Cloud Deutschland-slutpunkter för klientprotokoll IMAP4, POP3 och SMTP måste manuellt uppdatera sina klientenheter för att växla till [Exchange Online-servernamnen.](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/pop3-and-imap4#settings-users-use-to-set-up-pop3-or-imap4-access-to-their-exchange-online-mailboxes) | Informera i förväg om det här beroendet till användare av dessa protokoll och se till att de antingen byter till Outlook Mobile eller Outlook på webben under den här migreringen. Om det inte går att uppdatera klientens slutpunkter misslyckas klientanslutningen mot Microsoft Cloud Deutschland när användarpostlådor migreras. |
||||

### <a name="exchange-online-hybrid-customers"></a>Exchange Online-hybridkunder

**Gäller för:** Alla kunder som använder en aktiv Exchange-hybridkonfiguration med Exchange-servrar lokalt<br>
**När den** används: Vilken tid som helst före fas 5 startar

Enterprise customers with a hybrid deployment of Exchange Online and an on-premises Exchange Server run the Hybrid Configuration Wizard (HCW) and AAD Connect to maintain and establish the hybrid setup. Exchange  **Online-hybridadministratörer måste köra hybridkonfigurationsguiden (HCW) flera gånger som** en del av övergången. Vid övergången från Microsoft Cloud Deutschland till Office 365 Germany-regionen måste administratören köra den senaste versionen av HCW på nytt i Läget "Office 365 Germany" innan Exchange-migreringen (fas 5) startar. Kör sedan HCW igen i läget "Office 365 Worldwide" när fas 5 är slutförd för att slutföra den lokala distributionen med regionsinställningarna för Office 365 Germany. HCW-körningen får inte utföras under fas 5, det är viktigt att inte köra HCW förrän fas 5 har avslutats.
Katalogattribut synkroniseras mellan Office 365 och Azure AD med den lokala distributionen via AAD Connect. 

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Kör om HCW med hjälp av inställningarna för Office 365 Germany <br><br> <i>Du kan starta aktiviteten direkt efter att du fått meddelandet i meddelandecentret om att migreringen av Office 365-klientorganisationen har startat (fas 1).</i>| Avinstallera och köra HCW (17.0.5378.0 eller senare) från innan fas 5 så att din lokala konfiguration är redo att skicka och ta emot e-post med både Microsoft Cloud Deutschland-användare och användare som migreras till regionen [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) Office 365 Germany. <p><li> I HCW för listrutan under **Min Office 365-organisation** finns på väljer du **Office 365 Germany.** | Om du inte kan slutföra den här uppgiften innan fas 5 [Exchange-migrering] börjar kan det resultera i NDR-meddelanden för e-post som dirigeras mellan den lokala Exchange-distributionen och Office 365.  
| Bevara inställningarna för delad postlåda | Vissa hybridkunder har konverterat molnbaserade användarpostlådor till delade postlådor med Exchange Online-kommandon. Den här molnpostlådekonfigurationen är skriven till postlådan och den lokala Exchange Online-katalogen, men den synkroniseras inte tillbaka till kundens Active Directory via AAD Connect. Resultatet är en avvikelse mellan Active Directory-representationen av postlådans RemoteRecipientType- och RemoteDisplayType-värden och den i Exchange Online som definierar postlådan som delad. <br><br> Kunden ansvarar för att säkerställa att alla delade postlådor är korrekt etablerade med hjälp `New-RemoteMailbox -Shared` av , `Enable-RemoteMailbox -Shared` eller `Set-RemoteMailbox -Shared` .  I den här referensen finns [information om hur du konverterar en användares postlåda i en hybridmiljö.](/microsoft-365/admin/email/convert-user-mailbox-to-shared-mailbox?view=o365-worldwide)| Om du inte kan slutföra den här uppgiften före fas 5 [Exchange Online-migrering] kan det resultera i NDR-resultat för delade postlådor som konverteras tillbaka till olicensierade postlådor och att delad åtkomst för berörda postlådor går förlorad. [Delade postlådor konverteras](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes) oväntat till användarpostlådor när katalogsynkroniseringen körs i en Exchange-hybriddistribution ger en översikt över effekterna av att inte åtgärda detta innan Exchange Online-migreringen har slutförts.  
||||

## <a name="skype-for-business-online"></a>Skype för företag online

<!-- before phase 7 -->

**Gäller för:** Skype för företag – Online-kunder<br>
**När den används:** Varje gång före fas 7 startar

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Distribuera Teams-skrivbordsklient för användare med åtkomst till Skype för företag i Tyskland. | Migreringen flyttar Skype för företag-användare till Microsoft Teams för samarbete, samtal och chatt. Distribuera skrivbordsklienten för Microsoft Teams eller kontrollera att en webbläsare som stöds är tillgänglig. | Om du inte gör det innebär det att Microsoft Teams-samarbetstjänster inte är tillgängliga. |
| Granska och förbereda dig för migreringsrelaterade DNS-ändringar. | Ändringar av kundens DNS-zon för Skype för företag – Online. |<ul><li>Vi rekommenderar att du uppdaterar TTL (Time-to-Live) för alla kundägda domän-DNS-poster till 5 minuter för att underlätta uppdatering av DNS-poster. Men det Microsoft-hanterade cutover som är kopplat till denna DNS-ändring kan inträffa när som helst inom det angivna 24-timmarsändringsfönstret. </li><li>Avbrott i tjänsten kan komma att vara möjlig i framtiden. Användarna kan inte logga in i Skype för företag och dirigeras om till den migrerade Teams-upplevelsen i Office 365-tjänsterna. </li></ul>|
| Förbered utbildning och förberedelser för övergången till Microsoft Teams för slutanvändare och administration. | Se till att du har lyckats med övergången från Skype till Teams genom att planera användarkommunikation och beredskap. | <ul><li>Klienter måste vara medvetna om de nya tjänsterna och hur de ska använda när deras tjänster har övergåt till Office 365-tjänsterna. </li><li>När DNS-ändringar har gjorts för både kunddomänerna och den första domänen kan användarna logga in i Skype för företag och se till att de nu migreras till Teams. Det skulle även ladda ned skrivbordsklienten för Teams i bakgrunden. </li></ul>|
||||

## <a name="mobile-device-management"></a>Hantering av mobila enheter

<!-- before phase 5 -->
**Gäller för:** Kunder som använder en MDM-lösning (Mobile Device Management) från tredje part<br>
**När den används:** Varje gång före fas 5 startar

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Förbered utbildning för slutanvändare och administration om att användare tar bort och lägger till sitt konto i Microsoft Outlook för iOS och Android. | Microsoft Outlook för iOS- och Android-konton som konfigurerats med postlådor i Microsoft Cloud Deutschland kan behöva tas bort och läggas till i Outlook igen för att den nya konfigurationen av Office 365-tjänsterna ska kunna synkroniseras. | Microsoft Outlook för iOS- och Android-kunder | Outlook-postlådor som tidigare konfigurerats för Microsoft Cloud Deutschland kanske inte hämtar den nya Office 365-tjänstkonfigurationen, vilket leder till fel och försämrad prestanda i andra användarupplevelser. IT-administratörer uppmanas att ta fram dokumentation som proaktivt instruerar användarna att ta bort och lägga till sina konton i Microsoft Outlook för iOS och Android om problem med inloggning eller synkronisering av e-post uppstår efter migreringen. |
| Avgöra om någon konfiguration krävs efter migreringen. | MdM-lösningar (Mobile Device Management) kan ha som `outlook.de` målslutpunkter. I den här övergången till Office 365-tjänster bör klientprofiler uppdateras till URL:en för Office 365-tjänster, `outlook.office365.com` . | Exchange Online- och MDM-kunder | Klienter kan fortsätta att fungera medan slutpunkten är tillgänglig, men de kommer att misslyckas `outlook.de` om Microsoft Cloud Deutschland-slutpunkter inte längre är tillgängliga. |
|||||

## <a name="line-of-business-apps"></a>Verksamhetsbaserade appar

**Gäller för:** Kunder som använder verksamhetsbaserade appar (LOB) med slutpunkter från Microsoft Cloud Deutschland<br>
**Används:** Efter slutförande av fas 2 och före slutet av fas 9

Om du använder en tredjepartstjänst eller verksamhetsbaserade appar (LOB) som är integrerade med Office 365 måste du lösa eventuella beroenden av slutpunkter som tillhandahålls av Microsoft Cloud Deutschland-instansen. Om dina affärsprogram till exempel ansluter till `https://graph.microsoft.de/` måste du ändra slutpunkten till `https://graph.microsoft.com/` . Slutpunkterna för den globala Microsoft Office 365-tjänsten blir tillgängliga för din klientorganisation efter fas 2.

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Avgöra om någon konfiguration krävs efter migreringen. | Tredjepartstjänster och program som integrerar med Office 365 kan kodas så att de förväntar sig Microsoft Cloud Deutschland IP-adresser och URL-adresser. | Obligatorisk åtgärd. Inaction kan resultera i fel i tjänsten eller klientprogramvaran. |
||||

## <a name="dynamics-365"></a>Dynamics 365

**Gäller för:** Kunder som använder Microsoft Dynamics 365

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| För prenumerationer i begränsat läge för Dynamics 365 laddar du ned produktionsmiljön för Dynamics SQL-instansen från din Dynamics 365-prenumeration i Microsoft Cloud Deutschland. Den senaste säkerhetskopieringen för produktion bör återställas till begränsat läge före migrering i begränsat läge. | Migrering av Dynamics 365 kräver att kunder ser till att miljön i begränsat läge uppdateras med den senaste produktionsdatabasen. | FastTrack-teamet hjälper kunder att utföra torr körningar för att verifiera versionsuppgraderingen från 8.x till 9.1.x. |
||||

## <a name="power-bi"></a>Power BI

**Gäller för:** Kunder som använder Power BI

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Borttagning av objekt från Power BI-prenumerationer som inte migreras från Power BI Microsoft Cloud Deutschland till Office 365-tjänster. | Migrering av Power BI-tjänster kräver åtgärder från kunder för att ta bort vissa artefakter, till exempel datamängder och instrumentpaneler. | <ul><li>Administratörer kan behöva ta bort följande objekt från prenumerationen: </li><li>Real-Time datauppsättningar (till exempel strömmande datamängder eller push-datauppsättningar) </li><li>Konfiguration och datakälla för lokal Power BI-datagateway </li></ul>|
||||

## <a name="microsoft-azure"></a>Microsoft Azure

Om du använder samma Azure Active Directory-identitetspartition för Office 365 och Microsoft Azure i Microsoft Cloud Deutschland-instansen ska du se till att du förbereder dig för en kunddriven migrering av Microsoft Azure-tjänster.

> [!NOTE]
> Migreringen av Microsoft Azure-tjänster får inte startas innan din Office 365-klientorganisation har nått migrering fas 3 och måste slutföras innan migreringsfasen 8 har slutförts.

Kunder som använder Office 365- och Azure-resurser (till exempel nätverk, beräkning och lagring) migrerar resurser till Office 365-tjänstinstansen. Den här migreringen är kundens ansvar. Inlägg i Meddelandecenter signalerar start. Migreringen måste slutföras innan Azure AD-organisationen slutförs i Office 365-tjänstmiljön. För Azure-migreringar, se Azure-migreringsspelboken, [Översikt över migreringsvägledning för Azure Germany.](https://docs.microsoft.com/azure/germany/germany-migration-main)

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Avgör vilka Azure-tjänster som används och förbereda en framtida migrering från Tyskland till Office 365-tjänstklientorganisationen genom att arbeta med dina partner. Följ stegen som beskrivs i [Azure-migreringsspelboken](/azure/germany/germany-migration-main). |<ul><li>Migrering av Azure-resurser är ett kundansvar och kräver manuella åtgärder enligt angivna steg. Det är viktigt att förstå vilka tjänster som används i organisationen för att migreringen av Azure-tjänster ska lyckas. </li><li> Office 365 Germany-kunder som har Azure-prenumerationer med samma identitetspartition (organisation) måste följa den Microsoft-bestämt ordningen när de kan påbörja prenumerations- och tjänstmigrering.</li></ul>|<ul><li>Kunder kan ha flera Azure-prenumerationer, varje prenumeration som innehåller infrastruktur, tjänster och plattformskomponenter. </li><li> Administratörer bör identifiera prenumerationer och intressenter för att säkerställa att snabb migrering och validering är möjlig som en del av den här migreringshändelsen. </li><li>Om inte de här prenumerationerna och Azure-komponenterna slutförs inom den angivna tidslinjen påverkas slutförandet av Office- och Azure AD-övergången till Office 365-tjänsterna, och data kan gå förlorade. </li><li> Ett meddelande i Meddelandecenter signalerar punkten då en kundledd migrering kan starta. </li></ul>|
||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](/azure/germany/germany-migration-main).

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

- [Information om Dynamics 365-migreringsprogram](/dynamics365/get-started/migrate-data-german-region)
- [Information om Migreringsprogram för Power BI](/power-bi/admin/service-admin-migrate-data-germany)
- [Komma igång med uppgraderingen till Microsoft Teams](/microsoftteams/upgrade-start-here)
