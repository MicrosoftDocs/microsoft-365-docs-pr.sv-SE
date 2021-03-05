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
ms.openlocfilehash: 26db69583bac68723d5d57b07abb856c8190d9b1
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454473"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>Åtgärder och effekter för migreringsfaserna för migreringen från Microsoft Cloud Deutschland (avancerat) 

Klientmigrering från Microsoft Cloud Deutschland till Regionen Tyskland för Microsofts Office 365-tjänster utförs som en uppsättning faser och deras konfigurerade åtgärder för varje arbetsbelastning. I den här bilden visas de nio faserna av migreringen till de nya tyska datacenteren.

![De nio faserna av migreringen till de nya Tyskland-datacenter](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Följande avsnitt innehåller ytterligare information om kundupplevelser när du flyttar från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365-tjänster i den nya tyska datacenterområdet.

## <a name="services"></a>Tjänster

Mellan fas 2 av 9 och fas 3 av 9 är partnerportalen eventuellt inte tillgänglig. Under tiden kanske partnern inte kan komma åt klientinformationen på partnerportalen. Eftersom varje migrering är olika kan varaktigheten för tillgänglighet vara i timmar. 

### <a name="azure-ad-phase-2-of-9"></a>Azure AD (fas 2 av 9)

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Azure AD-klientorganisationen i Microsoft Cloud Deutschland kopierad till Office 365-tjänster. | Azure AD kopierar klientorganisationen till Office 365-tjänster. Klientorganisations- och användaridentifierare bevaras. Azure AD-tjänstsamtal omdirigeras från Microsoft Cloud Deutschland till Office 365-tjänster och är transparenta mot tjänster. | Alla Office-kunder | - Dataskyddsförordningen (GDPR) Data Subject Requests (DSR) utförs från Azure Admin-portalen för framtida förfrågningar. Alla äldre eller icke-kunddiagnostikdata som finns i Microsoft Cloud Deutschland tas bort vid eller före 30 dagars förfluten tid. <br><br> - Kunder som använder federerad autentisering med Ad FS (Active Directory Federation Services) ska inte göra ändringar i utfärdare-URI:er som används för alla autentiseringar med lokal Active Directory under migreringen. Om URI:er för utfärdare ändras leder det till autentiseringsfel för användare i domänen. Uri:er för utfärdare kan ändras direkt i  AD FS eller när en domän konverteras från _hanterad till federerad_ och tvärtom. Vi rekommenderar att kunder inte lägger till, tar bort eller konverterar en federerad domän i Azure AD-klientorganisationen som har migrerats. URI:er för utfärdare kan ändras när migreringen är fullständig. <br><br> - Multifaktorautentisering (MFA) begär att Microsoft Authenticator ska visas som användarobjekt-ID (en GUID) medan klientorganisationen kopieras till Office 365-tjänster. MFA-begäranden fungerar som förväntat trots det här visningsbeteendet.  Microsoft Authenticator-konton som har aktiverats med hjälp av Office 365-tjänstslutpunkter visar användarens huvudnamn (UPN).  Konton som läggs till med hjälp av Microsoft Cloud Deutschland-slutpunkter visar användarens ObjectID men fungerar med både Microsoft Cloud Deutschland- och Office 365-slutpunkter.  |
| Upprätta AuthServer lokalt som pekar på den globala STS-tjänsten. | Detta garanterar att förfrågningar från användare som migrerar till Microsoft Cloud Deutschland för Exchange-tillgänglighetsförfrågningar som är mål för hybriden i den lokala miljön autentiseras för åtkomst till den lokala tjänsten. På samma sätt säkerställer detta autentisering av förfrågningar från lokala slutpunkter till Office 365-tjänster. | Exchange Online-kunder med hybriddistributioner (lokalt) | När Azure AD-migreringen är klar måste administratören för den lokala Exchange-topologin (hybrid) lägga till en ny autentiseringstjänst-slutpunkt för Office 365-tjänsterna. Med det här kommandot från Exchange PowerShell ersätter du med din `<TenantID>` organisations klientorganisations-ID (finns i Azure-portalen i **Azure Active Directory).** <br><br> - `New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> Om du inte kan slutföra den här uppgiften kan det leda till att hybridförfrågningar om ledig/upptagen-aktivitet inte kan tillhandahålla information för postlådeanvändare som har migrerats från Microsoft Cloud Deutschland till Office 365-tjänster.  |
| Migrering av Azure-resurser. | Kunder som använder Office 365- och Azure-resurser (till exempel nätverk, beräkning och lagring) migrerar resurser till Office 365-tjänstinstansen. Den här migreringen är ett ansvar för kunderna. Inlägg i Meddelandecenter signalerar start. Migreringen måste slutföras innan Azure AD-organisationen slutförs i Office 365-tjänstmiljön. | Azure-kunder | För Azure-migreringar, se Azure-migreringsspelboken, [Översikt över migreringsvägledning för Azure Germany.](https://docs.microsoft.com/azure/germany/germany-migration-main) |
|||||

### <a name="exchange-online-phase-5-of-9"></a>Exchange Online (fas 5 av 9)

Om du använder **Set-UserPhoto:**

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Den nya Tyskland-regionen läggs till i en befintlig organisationskonfiguration och postlådor flyttas till Office 365-tjänster. | Exchange Online-konfigurationen lägger till den nya lokala tyska regionen i övergången. Det här Office 365-tjänsteområdet är inställt som standard, vilket gör att den interna belastningsutjämningstjänsten kan distribuera postlådor till rätt standardområde i Office 365-tjänster. I den här övergången finns användarna på vardera sidan (Tyskland eller Office 365-tjänster) i samma organisation och kan använda någon av URL-slutpunkterna. |  Exchange Online | Om en användarpostlåda har migrerats men en administratörspostlåda inte har migrerats, eller tvärtom, kan administratörer inte köra **Set-UserPhoto**, en PowerShell-cmdlet. I det här fallet måste en administratör överföra ytterligare en sträng under `ConnectionUri` anslutningens konfigurerade genom att använda följande syntax: <br><br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br><br> var `<user_email>` finns platshållaren för e-post-ID för användaren vars foto behöver ändras med **Set-UserPhoto.** |
|||||

Om du använder en hybriddistribution lokalt:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
|Stoppa eller ta bort alla onboarding- eller offboarding-flyttningar av postlådor.  | Detta garanterar att flyttningsförfrågningarna inte misslyckas med ett fel. | Exchange Online-kunder med hybriddistributioner (lokalt) | Åtgärd krävs. Om du inte gör det kan det leda till att tjänsten eller programvaruklienterna misslyckas. |
|||||

### <a name="dynamics-phase-8-of-9"></a>Dynamics (fas 8 av 9)

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Microsoft Dynamics-resurser | Kunder med Microsoft Dynamics kommer att vara engagerade av Teknik eller FastTrack för att övergå till Office 365-tjänstinstansen.* | Microsoft Dynamics 365-kunder | – Efter migreringen validerar administratören organisationen. <br><br> - Administratören ändrar arbetsflöden efter behov. <br><br> – administratören tar bort AdminOnly-läget efter behov. <br><br> - Administratören ändrar organisationstypen från begränsat _läge_ efter behov <br><br> - Meddela slutanvändarna om den nya URL:en för att få åtkomst till instansen (organisationen). <br><br> – Uppdatera alla inkommande anslutningar till den nya slutpunkts-URL:en. <br><br> - Dynamics-tjänsten kommer inte att vara tillgänglig för användare under övergången. <br><br> - Användarna måste validera organisationens hälsa och funktioner efter migreringen av varje organisation.  |
|||||

\* (i) Kunder med Microsoft Dynamics 365 måste vidta åtgärder i det här migreringsscenariot som definierats av den migreringsprocess som tillhandahålls. (ii) Om kunden inte kan vidta någon åtgärd kommer Microsoft inte att kunna slutföra migreringen. (iii) När Microsoft inte kan slutföra migreringen på grund av kundens inaction upphör kundens prenumeration den 29 oktober 2021. 


### <a name="power-bi-phase-8-of-9"></a>Power BI (Fas 8 av 9)

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Migrering av Power BI-resurser | Kunder med Microsoft Power BI kommer att vara engagerade av Teknik eller FastTrack efter att manuellt ha utlöst ett befintligt PBI-migreringsverktyg för att migrera Power BI till Office 365-tjänstinstansen.\*\* | Microsoft Power BI-kunder | - Följande Power _BI-objekt_ kommer inte att läggas över och de måste skapas på ny sätt: <br><br> – Realtidsdatamängder (till exempel strömma datamängder eller push-datauppsättningar). <br> - Konfiguration och datakälla för lokal Power BI-datagateway. <br> - Rapporter som bygger på realtidsdatamängderna blir inte tillgängliga efter migreringen och de måste återskapas. <br><br> - Power BI-tjänster kommer inte att vara tillgängliga för användarna under övergången. Tjänstens tillgänglighet är inte längre än 24 timmar. <br><br> – Användarna måste konfigurera om datakällor och deras lokala datagateway med Power BI-tjänsten efter migreringen.  Fram till dess kan användarna inte använda datakällorna till att utföra schemalagda uppdateringar och/eller direktfrågor mot dessa datakällor. <br><br> - Kapaciteter och premiumarbetsytor kan inte migreras. Kunder måste ta bort alla kapaciteter innan migreringen och skapa dem igen efter migreringen. Flytta arbetsytor tillbaka till kapaciteterna efter behov.  |
|||||

\*\* (i) Kunder med Microsoft Power BI måste vidta åtgärder i det här migreringsscenariot som definierats av den migreringsprocess som tillhandahålls. (ii) Om kunden inte kan vidta någon åtgärd kommer Microsoft inte att kunna slutföra migreringen. (iii) När Microsoft inte kan slutföra migreringen på grund av kundens inaction upphör kundens prenumeration den 29 oktober 2021. 



## <a name="during-migration"></a>Under migreringen

### <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (fas 4 av 9)

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| SharePoint och OneDrive har nu övergångar. | SharePoint och OneDrive migreras från Microsoft Cloud Deutschland till Office 365-tjänster i den här fasen. Befintliga URL-adresser för Microsoft Cloud Deutschland bevaras ( `contoso.sharepoint.de` ). Token som utfärdats av Microsoft Cloud Deutschland eller Office 365-tjänster är giltiga under övergången. | SharePoint-kunder | Inflight SharePoint 2013-arbetsflöden bryts under migreringen och måste publiceras på nytt efter migreringen. |
|||||


### <a name="exchange-online-phase-5-of-9"></a>Exchange Online (fas 5 av 9)

För eDiscovery:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Under migreringen kommer eDiscovery-sökningar att misslyckas eller returnera 0 resultat för SharePoint Online-, OneDrive för företag- och Exchange Online-platser som har migrerats. | Under migreringen kan kunder fortsätta att skapa ärenden, innehåll, sökningar och exporter i Säkerhets- [och &,](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)inklusive [Innehållssökning.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)  Men sökningar mot SharePoint Online-, OneDrive för företag- och Exchange Online-platser som har migrerats returnerar antingen 0 resultat eller resulterar i ett fel. För åtgärd, se kolumnen _Effekt._ | Alla kunder som använder eDiscovery |  Om en sökning returnerar 0 resultat eller ett fel under migreringen kan du vidta följande åtgärd för SharePoint Online: <br><br>  Ladda ned webbplatser direkt från en SharePoint Online- eller OneDrive för företag-webbplats genom att följa anvisningarna i Ladda ned filer och [mappar från OneDrive eller SharePoint.](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) Den här metoden kräver SharePoint Online-administratörsbehörigheter eller skrivskyddade behörigheter på webbplatsen. <br><br> Om gränserna överskrids, vilket förklaras i Ladda ned filer och mappar från OneDrive eller [SharePoint,](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)kan kunder använda synkroniseringsklienten för OneDrive för företag genom att följa ederna i Synkronisera [SharePoint-](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)och Teams-filer med datorn. <br><br> - Exchange Online <br><br> - [EDiscovery på plats i Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
|||||


### <a name="skype-for-business-online-phase-7-of-9"></a>Skype för företag – Online (fas 7 av 9)

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Migrering av Skype för företag till Teams. | Befintliga Skype för företag-kunder migreras till Office 365-tjänster i Europa och övergår sedan till Microsoft Teams i Tyskland-regionen för Office 365-tjänster. | Skype för företag-kunder |  PowerShell kommer att använda för att administrera inställningar och principer för klientorganisationen och användare. När du ansluter till en PowerShell-session lägger du till följande: <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"` |
|||||


## <a name="post-migration"></a>Efter migreringen

### <a name="azure-ad-phase-9-of-9"></a>Azure AD (fas 9 av 9)

För hybrid:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Uppdatera Azure AD Connect. | När användningen av Azure AD har slutförts använder organisationen Office 365-tjänster fullt ut och är inte längre ansluten till Microsoft Cloud Deutschland. I det här läget måste kunden säkerställa att deltasynkroniseringsprocessen har slutförs och sedan ändra strängvärdet från `AzureInstance` 3 (Microsoft Cloud Deutschland) till 0 i `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` registersökvägen. | Azure AD-anslutna hybridorganisationer | Ändra `AzureInstance` registernyckelns värde. Om du inte gör det kommer objekten inte att synkroniseras efter att Microsoft Cloud Deutschland-slutpunkterna inte längre är tillgängliga. |
|||||

För federerad autentisering:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Ta bort förtroenden från betrodda parter från Microsoft Cloud Deutschland AD FS. | När användningen av Azure AD har slutförts använder organisationen Office 365-tjänster fullt ut och är inte längre ansluten till Microsoft Cloud Deutschland. I det här läget måste kunden ta bort det förtroende som den förlitar sig på i Microsoft Cloud Deutschland-slutpunkterna. Det här kan endast göras om inga program för kundpunkter pekar på Microsoft Cloud Deutschland-slutpunkter när Azure AD används som identitetsprovider (IdP). | Organisationer med federerad autentisering | Inget. |
|||||

För Azure AD:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Förfrågningar om att ansluta till en Azure AD-grupp under de senaste 30 dagarna innan migreringen måste begäras igen om den ursprungliga begäran inte godkänts. | Slutanvändarkunder måste använda Åtkomstpanelen för att skicka en begäran om att ansluta till en Azure AD-grupp igen om dessa begäranden inte godkänts under de senaste 30 dagarna före migreringen. | Slutanvändare vars azure AD-gruppgodkännandebegäranden inte godkänts under de senaste 30 dagarna före migreringen |  Som slutanvändare: <ol><li>Gå till [panelen Åtkomst.](https://account.activedirectory.windowsazure.com/r#/joinGroups)</li><li>Hitta en Azure AD-grupp för vilken godkännande av medlemskap väntar på 30 dagar före migreringen.</li><li>Begär att ansluta till Azure AD-gruppen igen.</li></ol> Förfrågningar om att gå med i en grupp som är aktiv mindre än 30 dagar före migrering kan inte godkännas, såvida de inte begärs efter migreringen. |
|||||

För DNS:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Uppdatera lokala DNS-tjänster för Slutpunkter för Office 365-tjänster. | Kund hanterade DNS-poster som pekar på Office 365 Germany måste uppdateras så att de pekar på Slutpunkter för Office 365-tjänster. | Alla Office-kunder | Åtgärd krävs. Om du inte gör det kan det leda till att tjänsten eller programvaruklienterna misslyckas. |
|||||

För tredjepartstjänster för Slutpunkter för Office 365-tjänster:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Uppdatera partner och tredjepartstjänster för Office 365-tjänstslutpunkter. | - Tredjepartstjänster och partner som pekar på Office 365 Germany måste uppdateras så att de pekar på slutpunkterna för Office 365-tjänster. Exempel: Registrera dig igen, i linje med dina leverantörer och partner, galleriets appversion av program, om tillgängligt. <br><br> - Visa alla anpassade program som använder Graph API `graph.microsoft.de` `graph.microsoft.com` från. Andra API:er med ändrade slutpunkter måste också uppdateras, om de används. <br><br> – Ändra alla företagsprogram som inte kommer från första part så att de omdirigeras till de globala slutpunkterna.  | Alla Office-kunder | Åtgärd krävs. Om du inte gör det kan det leda till att tjänsten eller programvaruklienterna misslyckas. |
|||||

### <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (fas 4 av 9)

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Publicera om SharePoint 2013-arbetsflöden. | I arbetet före migreringen minskade vi antalet SharePoint 2013-arbetsflöden. När migreringen är klar kan kunden publicera arbetsflödena på nytt. | Alla Office-kunder | Det här är en åtgärd som krävs. Om du inte gör det kan det leda till förvirring och supportsamtal. |
| Dela objekt via Outlook | Det går inte längre att dela objekt via Outlook efter att klientorganisationen har klippt ut dem. | SharePoint Online och OneDrive för företag | – I SharePoint Online och OneDrive för företag kan du dela objekt via Outlook. När du tryckt på Outlook-knappen skapas en delningsbar länk och skickas till ett nytt meddelande i Outlook Web App. <br><br> – Den här delningsmetoden kommer inte att fungera efter att klientorganisationen har klippt ut den. Vi känner igen att det här är ett känt problem. Men eftersom den här Outlook-funktionen är i vägen för utfasningen är det inte planerat att åtgärda problemet förrän utfasningen har distribuerats. |


### <a name="exchange-online-phase-5-of-9"></a>Exchange Online (fas 5 av 9)

Om du använder en Hybrid Exchange-konfiguration:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Kör hybridkonfigurationsguiden (HCW) igen mot Office 365-tjänster. | Den befintliga HCW-konfigurationen är avsedd att stödja Microsoft Cloud Deutschland. När migreringen av Exchange-tjänster är klar kan vi avkoda den lokala konfigurationen från Microsoft Cloud Deutschland. | Exchange Online-kunder som kör en hybriddistribution | - Obligatorisk åtgärd. Om du inte gör det kan det leda till att tjänsten eller programvaruklienterna misslyckas. Innan exchange-postlådemigrering börjar (med 5 eller fler dagars förvarning) informerar du klienterna om att de bör stoppa och ta bort alla onboarding- eller offboarding-flyttningar av postlådor.  Om de inte gör det visas fel i sina flyttningsförfrågningar. <br><br> – När Exchange-postlådemigrering har slutförts meddelar du klienterna att de kan återuppta onboarding- och offboarding-flyttningar. <br> **Test-MigrationServerAvailabiilty**, en PowerShell-cmdlet, under migreringen av Exchange från Microsoft Cloud Deutschland till Office 365-tjänster kanske inte fungerar. Men det fungerar korrekt när migreringen är klar. <br><br> Om klienter får problem med autentiseringsuppgifter eller auktorisering efter att postlådor har migrerats kan användare ange sina lokala administratörsautentiseringsuppgifter på nytt i migreringsslutpunkten genom att köra eller genom att ange samma sak med hjälp av `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` Exchange-kontrollpanelen (ECP).  |

För eDiscovery:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
|  Alla SharePoint Online-, OneDrive för företag- och Exchange Online-platser har migrerats tillsammans med Säkerhets- och efterlevnadscenter (SCC). | All eDiscovery-aktivitet bör köras från den globala klientorganisationen. Sökningarna lyckas nu till 100 %.  Eventuella fel bör följa de vanliga supportkanalerna. | Alla kunder som använder eDiscovery | Inget. |
| Ta bort bevarandeprinciper för hela organisationen som skapades under före migreringen | Kunder kan ta bort de organisationsomfattande bevarandeprinciper som skapades under kundernas arbete före migreringen. | Alla kunder som tillämpade en bevarandeprincip under före migreringen. | Inget. |
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
