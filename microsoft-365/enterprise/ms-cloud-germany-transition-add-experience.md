---
title: Åtgärder och effekter för migreringsfaserna för migreringen från Microsoft Cloud Deutschland (avancerat)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
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
description: 'Sammanfattning: Ytterligare kundupplevelseinformation vid flytt från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365-tjänster i den nya tyska datacenterområdet.'
ms.openlocfilehash: 8dcb8b8ab2ec5c3dea105380858d26cfd5537d9c
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712288"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>Åtgärder och effekter för migreringsfaserna för migreringen från Microsoft Cloud Deutschland (avancerat) 

Klientmigrering från Microsoft Cloud Deutschland till Regionen Tyskland för Microsofts Office 365-tjänster utförs som en uppsättning faser och deras konfigurerade åtgärder för varje arbetsbelastning. I den här bilden visas de nio faserna av migreringen till de nya tyska datacenteren.

![De nio faserna av migreringen till de nya Tyskland-datacenter](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Följande avsnitt innehåller ytterligare information om kundupplevelser när du flyttar från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365-tjänster i den nya tyska datacenterområdet.

## <a name="office-365-portal-services"></a>Office 365-portaltjänster

Mellan fas 2 av 9 och fas 3 av 9 är partnerportalen eventuellt inte tillgänglig. Under tiden kanske partnern inte kan komma åt klientinformationen på partnerportalen. Eftersom varje migrering är olika kan varaktigheten för tillgänglighet vara i timmar.

### <a name="prework-for-azure-ad-phase-2"></a>Förarbete för Azure AD (fas 2)

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Azure AD-klientorganisationen i Microsoft Cloud Deutschland kopierad till Office 365-tjänster. | Azure AD kopierar klientorganisationen till Office 365-tjänster. Klientorganisations- och användaridentifierare bevaras. Azure AD-tjänstsamtal dirigeras om från Microsoft Cloud Deutschland till Office 365-tjänster och är transparenta mot tjänster. | Alla Office-kunder | - Dataskyddsförordningen (GDPR) Data Subject Requests (DSR) utförs från Azure Admin-portalen för framtida förfrågningar. Alla äldre eller icke-kunddiagnostikdata som finns i Microsoft Cloud Deutschland tas bort vid eller före 30 dagars förfluten tid. <br><br> - Kunder som använder federerad autentisering med Ad FS (Active Directory Federation Services) ska inte göra ändringar i utfärdare-URI:er som används för alla autentiseringar med lokal Active Directory under migreringen. Om URI:er för utfärdare ändras leder det till autentiseringsfel för användare i domänen. Uri:er för utfärdare kan ändras direkt i  AD FS eller när en domän konverteras från _hanterad till federerad_ och tvärtom. Vi rekommenderar att kunder inte lägger till, tar bort eller konverterar en federerad domän i Azure AD-klientorganisationen som har migrerats. URI:er för utfärdare kan ändras när migreringen är fullständig. <br><br> - Multifaktorautentisering (MFA) begär att Microsoft Authenticator ska visas som användarobjekt-ID (en GUID) medan klientorganisationen kopieras till Office 365-tjänster. MFA-begäranden fungerar som förväntat trots det här visningsbeteendet.  Microsoft Authenticator-konton som har aktiverats med hjälp av Office 365-tjänstslutpunkter visar huvudnamnet (UPN).  Konton som läggs till med hjälp av Microsoft Cloud Deutschland-slutpunkter visar användarens ObjectID men fungerar med både Microsoft Cloud Deutschland- och Office 365-slutpunkter.  |
| Migrering av Azure-resurser. | Kunder som använder Office 365- och Azure-resurser (till exempel nätverk, beräkning och lagring) migrerar resurser till Office 365-tjänstinstansen. Den här migreringen är ett ansvar för kunderna. Inlägg i Meddelandecenter signalerar start. Migreringen måste slutföras innan Azure AD-organisationen slutförs i Office 365-tjänstmiljön. | Azure-kunder | För Azure-migreringar, se Azure-migreringsspelboken, [Översikt över migreringsvägledning för Azure Germany.](https://docs.microsoft.com/azure/germany/germany-migration-main) |
|||||

### <a name="exchange-online-before-phase-5"></a>Exchange Online före fas 5

**Gäller för:** Alla kunder som använder en Exchange-hybridkonfiguration med Exchange-servrar lokalt

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Upprätta AuthServer lokalt som pekar på den globala STS-tjänsten. | Detta garanterar att förfrågningar från användare som migrerar till Microsoft Cloud Deutschland för Exchange-tillgänglighetsförfrågningar som är mål för hybriden i den lokala miljön autentiseras för åtkomst till den lokala tjänsten. På samma sätt säkerställer detta autentisering av förfrågningar från lokala slutpunkter till Office 365-tjänster. | När Azure AD-migreringen är klar måste administratören för den lokala Exchange-topologin (hybrid) lägga till en ny autentiseringstjänst-slutpunkt för Office 365-tjänsterna. Med det här kommandot från Exchange PowerShell ersätter du med din `<TenantID>` organisations klientorganisations-ID (finns i Azure-portalen i **Azure Active Directory).**<br><br>`New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> Om du inte kan slutföra den här uppgiften kan det leda till att hybridförfrågningar om ledig/upptagen-aktivitet inte kan tillhandahålla information för postlådeanvändare som har migrerats från Microsoft Cloud Deutschland till Office 365-tjänster.  |
|Stoppa eller ta bort alla onboarding- eller offboarding-postlådor, nämligen att inte flytta postlådor mellan Exchange lokalt och Exchange Online  | Det säkerställer att postlådeflyttningsförfrågningarna inte misslyckas och får ett fel. | Om du inte gör det kan det leda till att tjänsten eller programvaruklienterna misslyckas. |
||||

<!--
    Question from ckinder
    Not clear if this has to be done before, during or after phase 5
-->

**Gäller för:** Alla kunder lagrar användarfoton i Exchange Online och använder **Set-UserPhoto:**

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Den nya regionen "Tyskland" läggs till i en befintlig konfiguration av Exchange Online-organisationen och postlådor flyttas till Office 365-tjänster. | Exchange Online-konfigurationen lägger till den nya lokala tyska regionen i övergången. Det här Office 365-tjänsteområdet är inställt som standard, vilket gör att den interna belastningsutjämningstjänsten kan distribuera postlådor till rätt standardområde i Office 365-tjänster. I den här övergången finns användarna på vardera sidan (Tyskland eller Office 365-tjänster) i samma organisation och kan använda någon av URL-slutpunkterna. | Om en användarpostlåda har migrerats men en administratörspostlåda inte har migrerats, eller tvärtom, kan administratörer inte köra **Set-UserPhoto**, en PowerShell-cmdlet. I det här fallet måste en administratör överföra ytterligare en sträng under `ConnectionUri` anslutningens konfigurerade genom att använda följande syntax: <br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br> var `<user_email>` finns platshållaren för e-post-ID för användaren vars foto behöver ändras med **Set-UserPhoto.** |
||||

## <a name="during-migration"></a>Under migreringen

### <a name="sharepoint-online-phase-4"></a>SharePoint Online fas 4

**Gäller för:** Alla kunder som använder eDiscovery

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| SharePoint och OneDrive har nu övergångar. | SharePoint och OneDrive migreras från Microsoft Cloud Deutschland till globala Office 365-tjänster under fas 4. Befintliga URL-adresser för Microsoft Cloud Deutschland bevaras ( `contoso.sharepoint.de` ). Token som utfärdats av Microsoft Cloud Deutschland eller Office 365-tjänster är giltiga under övergången. | Inflight SharePoint 2013-arbetsflöden bryts under migreringen och måste publiceras på nytt efter migreringen. |
||||

### <a name="ediscovery-phase-4-to-the-end-of-phase-9"></a>eDiscovery fas 4 till slutet av fas 9

**Gäller för:** Alla kunder som använder eDiscovery

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Från början av fas 4 tills fas 9 är slutförd kommer eDiscovery-sökningar att misslyckas eller returnera 0 resultat för SharePoint Online-, OneDrive för företag- och Exchange Online-platser som har migrerats. | Under migreringen kan kunder fortsätta att skapa ärenden, innehåll, sökningar och exporter i Säkerhets- [och &,](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)inklusive [Innehållssökning.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)  Men sökningar mot SharePoint Online-, OneDrive för företag- och Exchange Online-platser som har migrerats returnerar antingen 0 resultat eller resulterar i ett fel. För åtgärd, se kolumnen _Effekt._ | Om en sökning returnerar noll resultat eller ett fel under migreringen kan du vidta följande åtgärd för SharePoint Online: <ul><li>Ladda ned webbplatser direkt från en SharePoint Online- eller OneDrive för företag-webbplats genom att följa anvisningarna i Ladda ned filer och [mappar från OneDrive eller SharePoint.](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) Den här metoden kräver SharePoint Online-administratörsbehörigheter eller skrivskyddade behörigheter på webbplatsen.</li><li>Om gränserna överskrids, vilket förklaras i Ladda ned filer och mappar från OneDrive eller [SharePoint,](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)kan kunder använda synkroniseringsklienten för OneDrive för företag genom att följa ederna i Synkronisera [SharePoint-](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)och Teams-filer med datorn.</li><li>Mer information finns i  [In-Place eDiscovery i Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
||||

## <a name="post-migration"></a>Efter migreringen

### <a name="azure-ad-phase-9"></a>Azure AD fas 9

**Gäller för:** Alla kunder synkroniserar identiteter med Azure AD Connect

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Uppdatera Azure AD Connect. | När användningen av Azure AD har slutförts använder organisationen Office 365-tjänster fullt ut och är inte längre ansluten till Microsoft Cloud Deutschland. I det här läget måste kunden säkerställa att deltasynkroniseringsprocessen har slutförs och sedan ändra strängvärdet från `AzureInstance` 3 (Microsoft Cloud Deutschland) till 0 i `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` registersökvägen. | Ändra `AzureInstance` registernyckelns värde. Om du inte gör det kommer objekten inte att synkroniseras efter att Microsoft Cloud Deutschland-slutpunkterna inte längre är tillgängliga. |
|||||

**Gäller för:** Alla kunder som använder federerad autentisering med ADFS

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Ta bort förtroenden från betrodda parter från Microsoft Cloud Deutschland AD FS. | När användningen av Azure AD har slutförts använder organisationen Office 365-tjänster fullt ut och är inte längre ansluten till Microsoft Cloud Deutschland. I det här läget måste kunden ta bort det förtroende som den förlitar sig på i Microsoft Cloud Deutschland-slutpunkterna. Det här kan endast göras om inga program för kundpunkter pekar på Microsoft Cloud Deutschland-slutpunkter när Azure AD används som identitetsprovider (IdP). | Organisationer med federerad autentisering | Inget. |
|||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
För Azure AD:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Förfrågningar om att ansluta till en Azure AD-grupp under de senaste 30 dagarna innan migreringen måste begäras igen om den ursprungliga begäran inte godkänts. | Slutanvändare måste använda åtkomstpanelen för att skicka en begäran om att ansluta till en Azure AD-grupp igen om dessa begäranden inte godkänts under de senaste 30 dagarna före migreringen. | Slutanvändare vars azure AD-gruppgodkännandebegäranden inte godkänts under de senaste 30 dagarna före migreringen |  Som slutanvändare: <ol><li>Gå till [panelen Åtkomst.](https://account.activedirectory.windowsazure.com/r#/joinGroups)</li><li>Hitta en Azure AD-grupp för vilken godkännande av medlemskap väntar på 30 dagar före migreringen.</li><li>Begär att ansluta till Azure AD-gruppen igen.</li></ol> Förfrågningar om att gå med i en grupp som är aktiv mindre än 30 dagar före migreringen kan inte godkännas, såvida de inte begärs på nytt efter migreringen. |
|||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
**Gäller för:**  Alla kunder som hanterar sina egna DNS-zoner

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Uppdatera lokala DNS-tjänster för Slutpunkter för Office 365-tjänster. | Customer-managed DNS entries that point to Microsoft Cloud Deutschland need to be updated to point to the Office 365 Global services endpoints. | Om du inte gör det kan det leda till att tjänsten eller programvaruklienterna misslyckas. |
||||

För tredjepartstjänster för Slutpunkter för Office 365-tjänster:

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Uppdatera partner och tredjepartstjänster för Slutpunkter för Office 365-tjänster. | <ul><li>Tredjepartstjänster och partner som pekar på Office 365 Germany måste uppdateras så att de pekar på Slutpunkter för Office 365-tjänster. Exempel: Registrera dig igen, i linje med dina leverantörer och partner, galleriets appversion av program, om tillgängligt. </li><li>Visa alla anpassade program som utnyttjar Graph API från `graph.microsoft.de` `graph.microsoft.com` till. Andra API:er med ändrade slutpunkter måste också uppdateras, om de används. </li><li>Ändra alla företagsprogram som inte kommer från första part så att de omdirigeras till de globala slutpunkterna. </li></ul>| Åtgärd krävs. Om du inte gör det kan det leda till att tjänsten eller programvaruklienterna misslyckas. |
||||

### <a name="sharepoint-online-post-migration"></a>SharePoint Online efter migreringen

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Publicera om SharePoint 2013-arbetsflöden. | I arbetet före migreringen minskade vi antalet SharePoint 2013-arbetsflöden. När migreringen är klar kan kunden publicera arbetsflödena på nytt. | Det här är en åtgärd som krävs. Om du inte gör det kan det leda till förvirring och supportsamtal. |
| Dela objekt via Outlook | Det går inte längre att dela objekt i SharePoint Online och OneDrive för företag via Outlook efter att klientorganisationen har klippt på sig. |<ul><li>I SharePoint Online och OneDrive för företag kan du dela objekt via Outlook. När du tryckt på Outlook-knappen skapas en delningsbar länk och skickas till ett nytt meddelande i Outlook Web App.</li><li>Efter att klientorganisationen har klippt ut kommer den här delningsmetoden inte att fungera. Vi känner igen att det här är ett känt problem. Men eftersom den här Outlook-funktionen är i vägen för utfasningen är det inte planerat att åtgärda problemet förrän utfasningen har distribuerats. </li></ul>|
||||

### <a name="exchange-online-post-migration"></a>Exchange Online efter migrering

Om du använder en Hybrid Exchange-konfiguration:

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Kör hybridkonfigurationsguiden (HCW) igen mot Office 365-tjänster. | Den befintliga HCW-konfigurationen är avsedd att stödja Microsoft Cloud Deutschland. När migreringen av Exchange-tjänster är klar kan vi avkoda den lokala konfigurationen från Microsoft Cloud Deutschland. |<ul><li>Åtgärd krävs. Om du inte gör det kan det leda till att tjänsten eller programvaruklienterna misslyckas. Innan Exchange-postlådemigrering börjar (med 5 eller fler dagars förvarning) bör du meddela klienterna att de ska stoppa och ta bort flyttningar av onboarding eller offboarding för postlådorna.  Om de inte har det visas fel i flyttningsförfrågningarna. </li><li>När Exchange-postlådemigrering har slutförts meddelar du klienterna att de kan återuppta onboarding- och offboarding-flyttningar. <br> **Test-MigrationServerAvailabiilty**, en PowerShell-cmdlet, under migreringen av Exchange från Microsoft Cloud Deutschland till Office 365-tjänster kanske inte fungerar. Men det fungerar korrekt när migreringen är klar. </li><li>Om klienter får problem med autentiseringsuppgifter eller auktorisering efter att postlådor har migrerats kan användare ange sina lokala administratörsautentiseringsuppgifter på nytt i migreringsslutpunkten genom att köra eller genom att ange samma sak med hjälp av `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` Exchange-kontrollpanelen (ECP). </li></ul>|

### <a name="ediscovery-post-migration"></a>eDiscovery efter migrering

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
|  Alla SharePoint Online-, OneDrive för företag- och Exchange Online-platser har migrerats tillsammans med Säkerhets- och efterlevnadscenter (SCC). | All eDiscovery-aktivitet bör köras från den globala klientorganisationen. Sökningarna lyckas nu till 100 %.  Eventuella misslyckanden eller fel bör följa de normala supportkanalerna. | Alla kunder som använder eDiscovery | Inget. |
| Ta bort bevarandeprinciper för hela organisationen som skapades under före migreringen | Kunder kan ta bort de organisationsomfattande bevarandeprinciper som skapades under kundernas arbete före migreringen. | Alla kunder som tillämpade en bevarandeprincip som en del av före migreringen. | Inget. |
|||||

## <a name="next-step"></a>Nästa steg

[Förstå åtgärder och effekter i migreringsfaser](ms-cloud-germany-transition-phases.md)

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
