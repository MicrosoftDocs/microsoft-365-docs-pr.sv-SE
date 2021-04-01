---
title: Åtgärder i migreringsfaser och påverkan på migreringen från Microsoft Cloud Deutschland (avancerat)
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
description: 'Sammanfattning: Mer information om kundupplevelsen när du flyttar från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365-tjänster i den nya tyska datacenterregion.'
ms.openlocfilehash: 8e28b9d6c8cc23e128234973039a4873b327e9fd
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476378"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>Åtgärder i migreringsfaser och påverkan på migreringen från Microsoft Cloud Deutschland (avancerat)

Klientmigrering från Microsoft Cloud Deutschland till Tyskland-regionen för Microsofts Office 365-tjänster utförs som en uppsättning faser och deras konfigurerade åtgärder för varje arbetsbelastning. I den här bilden visas de tio faserna av migreringen till de nya tyska datacenteren.

![De tio migreringsfaserna till de nya Tyskland-datacenter](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Följande avsnitt ger ytterligare information om kundupplevelser när du flyttar från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365-tjänster i den nya tyska datacenterområdet.

## <a name="office-365-portal-services-between-phase-2-and-phase-3"></a>Office 365-portaltjänster mellan fas 2 och fas 3

Mellan fas 2 och fas 3 är partnerportalen kanske inte tillgänglig. Under tiden kanske partnern inte kan komma åt klientorganisationens information på partnerportalen. Eftersom varje migrering är olika kan varaktigheten för tillgänglighet vara i timmar.

### <a name="ediscovery-phase-4-to-the-end-of-phase-9"></a>eDiscovery fas 4 till slutet av fas 9

**Gäller för:** Alla kunder som använder eDiscovery

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Från början av fas 4 tills fas 9 är slutförd kommer eDiscovery-sökningar att misslyckas eller returnera 0 resultat för SharePoint Online-, OneDrive för företag- och Exchange Online-platser som har migrerats. | Under migreringen kan kunder fortsätta att skapa ärenden, innehåll, sökningar och exporter i Säkerhets- [&,](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)inklusive [Innehållssökning.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content) Men sökningar mot SharePoint Online-, OneDrive för företag- och Exchange Online-platser som har migrerats returnerar antingen 0 resultat eller resulterar i ett fel. Mer information om åtgärder finns i _kolumnen_ Påverkan. | Om en sökning returnerar noll resultat eller ett fel under migreringen kan du vidta följande åtgärd för SharePoint Online: <ul><li>Ladda ned webbplatser direkt från SharePoint Online- eller OneDrive för företag-webbplatsen genom att följa anvisningarna i Ladda ned filer och [mappar från OneDrive eller SharePoint.](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) Den här metoden kräver administratörsbehörigheter för SharePoint Online eller skrivskyddsbehörigheter på webbplatsen.</li><li>Om gränserna överskrids, vilket förklaras i Ladda ned filer och mappar från OneDrive eller [SharePoint,](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)kan kunder använda synkroniseringsklienten för OneDrive för företag genom att följa vägledning i Synkronisera [SharePoint-](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)och Teams-filer med din dator.</li><li>Mer information finns i  [EDiscovery på plats i Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
||||

## <a name="exchange-online-set-userphoto-during-phase-5"></a>Exchange OnlineSet-UserPhoto under fas 5

**Gäller för:** Alla kunder som lagrar användarfoton i Exchange Online och använder **Set-UserPhoto:**

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Den nya regionen "Tyskland" läggs till i en befintlig Exchange Online-organisationskonfiguration och postlådor flyttas till Office 365-tjänster. | Exchange Online-konfigurationen lägger till den nya lokala tyska regionen i övergången. Den här Office 365-tjänstområdet har angetts som standard, vilket gör att den interna belastningsutjämningstjänsten kan distribuera om postlådor till rätt standardområde i Office 365-tjänsterna. I den här övergången finns användarna på vardera sidan (Tyskland eller Office 365-tjänster) i samma organisation och kan använda antingen URL-slutpunkten. | Om en användarpostlåda har migrerats men en administratörspostlåda inte har migrerats, eller tvärtom, kan administratörer inte köra **Set-UserPhoto**, en PowerShell-cmdlet. I det här fallet måste en administratör överföra ytterligare en sträng under anslutningen `ConnectionUri` som konfigureras med följande syntax: <br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br> var finns platshållaren för e-post-ID för användaren vars foto `<user_email>` behöver ändras genom att använda **Set-UserPhoto**. |
||||

## <a name="post-migration"></a>Efter migrering

### <a name="azure-ad-phase-9"></a>Azure AD, fas 9

**Gäller för:** Alla kunder synkroniserar identiteter med Azure AD Connect

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Uppdatera Azure AD Connect. | Efter att användningen av Azure AD har slutförts använder organisationen alla Office 365-tjänster och är inte längre ansluten till Microsoft Cloud Deutschland. I det här läget måste kunden säkerställa att deltasynkroniseringsprocessen har slutförs och sedan ändra strängvärdet från `AzureInstance` 3 (Microsoft Cloud Deutschland) till 0 i `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` registersökvägen. | Ändra `AzureInstance` registernyckelns värde. Om du inte gör det kommer objekten inte att synkroniseras efter att Microsoft Cloud Deutschland-slutpunkterna inte längre är tillgängliga. |
|||||

**Gäller för:** Alla kunder som använder federerad autentisering med ADFS

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Ta bort förtroenden från en part i Microsoft Cloud Deutschland AD FS. | Efter att användningen av Azure AD har slutförts använder organisationen alla Office 365-tjänster och är inte längre ansluten till Microsoft Cloud Deutschland. I det här läget behöver kunden ta bort det beroende tredjepartsförtroendet till Microsoft Cloud Deutschland-slutpunkterna. Detta kan endast göras om ingen av kundens program pekar på Microsoft Cloud Deutschland-slutpunkter när Azure AD används som en identitetsprovider (IdP). | Organisationer med federerad autentisering | Ingen. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
**Gäller för:** Slutanvändare vars Azure AD-gruppgodkännandebegäranden inte godkänts under de senaste 30 dagarna före migreringen 

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Förfrågningar om att gå med i en Azure AD-grupp de senaste 30 dagarna innan migreringen måste begäras igen om den ursprungliga begäran inte godkänts. | Slutanvändarkunder måste använda åtkomstpanelen för att skicka en begäran om att ansluta till en Azure AD-grupp igen om dessa begäranden inte godkänts under de senaste 30 dagarna före migreringen. |  Som slutanvändare: <ol><li>Gå till [åtkomstpanelen](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Hitta en Azure AD-grupp för vilken godkännande av medlemskap väntar under 30 dagar före migreringen.</li><li>Begär att få gå med i Azure AD-gruppen igen.</li></ol> Förfrågningar om att gå med i en grupp som är aktiv mindre än 30 dagar innan migreringen kan inte godkännas, såvida de inte begärs igen efter migreringen. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
**Gäller för:**  Alla kunder som hanterar sina egna DNS-zoner

| Steg | Beskrivning | Påverkan |
|:------|:-------|:-------|
| Uppdatera lokala DNS-tjänster för Office 365-tjänstslutpunkter. | Kund hanterade DNS-poster som pekar på Microsoft Cloud Deutschland måste uppdateras så att de pekar på slutpunkterna för globala Office 365-tjänster. | Om du inte gör det kan det leda till att tjänsten eller programvaruklienten inte fungerar. |
||||

**Gäller för:** Kunder som använder tjänster från tredje part för Office 365-tjänsteslutpunkter

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Uppdatera partner och tredjepartstjänster för Office 365-tjänsteslutpunkter. | <ul><li>Tredjepartstjänster och partner som pekar på Office 365 Germany måste uppdateras så att de pekar på Office 365-tjänstslutpunkterna. Exempel: Registrera igen, i linje med dina leverantörer och partner, galleriets appversion av program, om tillgängligt. </li><li>Peka alla anpassade program som utnyttjar Graph API från `graph.microsoft.de` till `graph.microsoft.com` . Andra API:er med ändrade slutpunkter måste också uppdateras, om de används. </li><li>Ändra alla företagsprogram som inte är från första part så att de omdirigeras till de globala slutpunkterna. </li></ul>| Obligatorisk åtgärd. Om du inte gör det kan det leda till att tjänsten eller programvaruklienten inte fungerar. |
||||

### <a name="sharepoint-online-post-migration"></a>SharePoint Online efter migrering

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Publicera om SharePoint 2013-arbetsflöden. | Under före migreringen minskade vi antalet SharePoint 2013-arbetsflöden. Nu när migreringen är klar kan kunden publicera arbetsflödena på nytt. | Det här är en åtgärd som krävs. Om du inte gör det kan det leda till förvirring och samtal till supporten. |
| Dela objekt via Outlook | Det går inte längre att dela objekt i SharePoint Online och OneDrive för företag via Outlook efter klientorganisationens övertid. |<ul><li>I SharePoint Online och OneDrive för företag kan du dela objekt via Outlook. När du trycker på Outlook-knappen skapas en delningsbar länk som skickades till ett nytt meddelande i Outlook Web App.</li><li>Efter att klientorganisationen har tagit över kommer den här delningsmetoden inte att fungera. Vi känner igen det här är ett känt problem. Men eftersom den här Outlook-funktionen är i vägen för utfasningen är det inte planerat att åtgärda problemet förrän utfasningen har distribuerats. </li></ul>|
||||

### <a name="exchange-online-post-migration"></a>Exchange Online efter migrering

Om du använder en Hybrid Exchange-konfiguration:

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Kör hybridkonfigurationsguiden (HCW) igen mot Office 365-tjänster. | Den befintliga HCW-konfigurationen är avsedd att stödja Microsoft Cloud Deutschland. När migreringen av Exchange-tjänster är slutförd avkodar vi den lokala konfigurationen från Microsoft Cloud Deutschland. |<ul><li>Obligatorisk åtgärd. Om du inte gör det kan det leda till att tjänsten eller programvaruklienten inte fungerar. Innan Exchange-postlådemigrering börjar (med 5 eller fler dagars förvarning) bör du meddela klienterna att de bör stoppa och ta bort alla flyttningar av onboarding eller offboarding för postlådorna.  Om de inte gör det visas fel i sina flyttningsförfrågningar. </li><li>När Exchange-postlådemigrering har slutförts meddelar du klienter att de kan återuppta flyttningar av onboarding och offboarding. <br> **Test-MigrationServerAvailabiilty**, en PowerShell-cmdlet, under migreringen av Exchange från Microsoft Cloud Deutschland till Office 365-tjänster kanske inte fungerar. Men det fungerar korrekt när migreringen är klar. </li><li>Om klienter får problem med autentiseringsuppgifter eller auktorisering efter att postlådorna migrerats, kan användare ange sina lokala administratörsautentiseringsuppgifter på nytt i migreringsslutpunkten genom att köra , eller genom att ange samma med hjälp av Exchange Control `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` Panel (ECP). </li></ul>|

### <a name="ediscovery-post-migration"></a>eDiscovery efter migrering

**Gäller för:** Alla kunder som använder eDiscovery

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
|  Alla SharePoint Online-, OneDrive för företag- och Exchange Online-platser har migrerats tillsammans med Säkerhets- och efterlevnadscenter (SCC). | All eDiscovery-aktivitet bör köras från den globala klientorganisationen. Sökningarna lyckas nu till 100 %.  Eventuella fel bör följa vanliga supportkanaler. | Ingen |
||||

**Gäller för:**  Alla kunder som har tillämpat en bevarandeprincip under före migreringen

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Ta bort bevarandeprinciper för hela organisationen som skapades före migreringen | Kunder kan ta bort de organisationsomfattande bevarandeprinciper som skapades under kundernas arbete före migreringen. | Ingen |
||||

## <a name="next-step"></a>Nästa steg

[Förstå åtgärder och påverkan på migreringsfaser](ms-cloud-germany-transition-phases.md)

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