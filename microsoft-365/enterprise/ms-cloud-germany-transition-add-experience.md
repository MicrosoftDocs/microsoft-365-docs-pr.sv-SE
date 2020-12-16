---
title: Åtgärder och konsekvenser för migreringen från Microsoft Cloud Deutschland (avancerat)
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
description: 'Sammanfattning: ytterligare kund information när du flyttar från Microsoft Cloud Tyskland (Microsoft Cloud Deutschland) till Office 365-tjänster i det nya tyska data centret.'
ms.openlocfilehash: 3f22ca9c380b3271d0c186be1f50fae4a0ea5bb9
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688199"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>Åtgärder och konsekvenser för migreringen från Microsoft Cloud Deutschland (avancerat) 

Följande avsnitt innehåller ytterligare information om kund upplevelser när du flyttar från Microsoft Cloud Tyskland (Microsoft Cloud Deutschland) till Office 365-tjänster i det nya tyska data centret.

## <a name="services"></a>Tjänster

### <a name="azure-ad"></a>Azure AD

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Azure AD-klient organisation i Microsoft Cloud-Deutschland kopieras till Office 365-tjänster. | Azure AD kopierar klient organisationen till Office 365-tjänster. Klient-och användar identifierare bevaras. Azure AD service-samtal omdirigeras från Microsoft Cloud Deutschland till Office 365-tjänster och är transparenta för tjänster. | Alla Office-kunder | -Allmänna data GDPR (DSRs) körs från Azure admin-portalen för framtida förfrågningar. Alla gamla eller icke-kunddiagnostikdata som är bosatta i Microsoft Cloud Deutschland tas bort minst 30 dagar. <br><br> -Kunder som använder federerad inloggningsautentisering med AD FS (Active Directory Federation Services) ska inte göra ändringar i utgivarens URI: er som används för alla autentiseringsförsök med lokala Active Directory under migreringen. Ändring av utfärdares-URI: er leder till autentiserings fel för användare i domänen. Utfärdares-URI: er kan ändras direkt i AD FS eller när en domän konverteras från _hanterad_ till _federerad_ och vice versa. Vi rekommenderar att kunderna inte lägger till, tar bort eller konverterar en federerad domän i den Azure AD-klient som har migrerats. Utfärdares-URI: er kan ändras när migreringen är fullständigt fullständig. <br><br> -Multi-Factor autentisering-begäranden (MFA) som använder Microsoft Authenticator-visning som användare ObjectID (ett GUID) när klient organisationen kopieras till Office 365-tjänster. MFA-begäranden fungerar som förväntat trots detta visnings beteende.  Microsoft Authenticator-konton som har Aktiver ATS med hjälp av Office 365-slut punkter visar användarens huvud namn (UPN).  Konton som lagts till med slut punkter för Microsoft Cloud Deutschland visar användaren ObjectID men fungerar tillsammans med slut punkter för Microsoft Cloud Deutschland och Office 365-tjänster.  |
| Etablera AuthServer som pekar på global STS-tjänsten. | Detta säkerställer att förfrågningar från användare som migrerar till Microsoft Cloud Deutschland för Exchange Availability-begäranden som riktar sig till den hybrid lokala miljön verifieras för att få åtkomst till den lokala tjänsten. På samma sätt säkerställer detta att autentiseringsbegäranden från lokala platser till Office 365-slut punkter verifieras. | Exchange Online-kunder med hybrid distributioner (lokala) | När Azure AD migrationen är klar måste administratören för den lokala Exchange-topologin (hybrid) lägga till en ny slut punkt för autentiseringstjänst för Office 365-tjänsterna. Med det här kommandot från Exchange PowerShell ersätter `<TenantID>` du med organisationens klient organisations-ID (finns i Azure Portal i **Azure Active Directory**). <br><br> - `New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> Om du inte utför den här uppgiften kan det leda till att det inte går att genomföra en begäran om att tillhandahålla information för post lådor som har migrerats från Microsoft Cloud Deutschland till Office 365-tjänster.  |
| Migrering av Azure-resurser. | Kunder som använder Office 365 och Azure-resurser (till exempel nätverks-, beräknings-och lagrings enheter) utför migrering av resurser till Office 365-tjänstens instans. Denna migrering är ett ansvar för kunder. Inlägg i meddelande Center avaktiverar början. Migrering måste slutföras innan du slutför Azure AD-organisationen i Office 365-tjänst miljön. | Azure-kunder | För Azure-migreringar, se Azure migration Playbook, [Översikt över migreringstjänster för Azure Tyskland](https://docs.microsoft.com/azure/germany/germany-migration-main). |
|||||

### <a name="exchange-online"></a>Exchange Online

Om du använder **set-UserPhoto**:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Det nya Tyskland läggs till i en befintlig organisations inställning och post lådor flyttas till Office 365-tjänster. | Med Exchange Online-konfiguration läggs den nya lokala tyska regionen till i över gången. Den här Office 365-regionen är inställd som standard, vilket gör det möjligt för intern belastnings utjämning att distribuera post lådor till rätt standard region i Office 365-tjänster. I den här över gången finns användare på vardera sidan (Tyskland eller Office 365-tjänster) inom samma organisation och kan använda antingen URL-slutpunkt. |  Exchange Online | Om en användares post låda har migrerats men en administratörs post låda inte har migrerats, eller vice versa, kan administratörer inte köra **set-UserPhoto**, en PowerShell-cmdlet. I den här situationen måste en administratör skicka ytterligare en sträng `ConnectionUri` under anslutningen som konfigureras med hjälp av följande syntax: <br><br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br><br> var `<user_email>` finns plats hållaren för e-post-ID för den användare vars foto måste ändras med **set-UserPhoto**. |
|||||

Om du använder en hybrid lokal installation:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
|Stoppa eller ta bort eventuella registrerings-eller offboarding för post lådor.  | Det gör att det inte går att flytta med ett fel. | Exchange Online-kunder med hybrid distributioner (lokala) | Nödvändig åtgärd. Om du inte gör det kanske tjänsten eller program varu klienter Miss lyckas. |
|||||

### <a name="dynamics"></a>Dynamics

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Microsoft Dynamics-resurser | Kunder med Microsoft Dynamics kan driva teknik-eller FastTrack för att gå över till Office 365 Services-instansen. * | Microsoft Dynamics 365-kunder | -Efter migrering verifierar administratören organisationen. <br><br> -Administratören ändrar arbets flöden om det behövs. <br><br> -Administratören rensar AdminOnly-läge efter behov. <br><br> -Administratören ändrar organisations typen från _begränsat läge_, efter behov <br><br> -Meddela slutanvändarna om den nya URL-adressen för att komma åt instansen (org). <br><br> -Uppdatera alla inkommande anslutningar till den nya slut punkts-URL: en. <br><br> -Dynamics-tjänsten kommer inte att vara tillgänglig för användare under över gången. <br><br> -Användare måste verifiera organisationens hälsa och funktioner efter migreringen av varje organisation.  |
|||||

\* (i) kunder med Microsoft Dynamics 365 måste vidta åtgärder i det här Överflyttnings scenariot enligt vad som anges i migreringsprocessen. (II) ett fel av kunden att vidta åtgärder innebär att Microsoft inte kan slutföra migreringen. (III) när Microsoft inte kan slutföra migreringen på grund av kundens inaktivitet upphör kund-prenumerationen den 29 oktober 2021. 


### <a name="power-bi"></a>Power BI

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Migrering av Power BI-resurser | Kunder med Microsoft Power BI kommer att använda sig av teknik eller FastTrack efter att ha loggat in på ett befintligt PBI för att överföra Power BI till Office 365 Services-instansen.\*\* | Microsoft Power BI-kunder | -Följande Power BI-objekt kommer _inte_ att överföras och de måste återskapas: <br><br> -Data mängder i real tid (till exempel direkt uppspelning eller push-datauppsättningar). <br> -Konfiguration och data källa för Power BI-lokal data Gateway. <br> -Rapporter som bygger på data i real tid blir inte tillgängliga efter migrering och måste återskapas. <br><br> -Power BI-tjänsterna är inte tillgängliga för användare under över gången. Denna tjänst får inte vara längre än 24 timmar. <br><br> -Användare måste konfigurera om data källor och deras lokala data gateways med Power BI-tjänsten efter migreringen.  Till dess att de gör det kan användarna inte använda dessa data källor för att utföra schemalagd uppdatering och/eller direkta frågor mot dessa data källor. <br><br> -Arbets ytor kan inte migreras. Kunderna måste ta bort alla kapaciteter innan de migreras och återskapa dem efter migreringen. Flytta arbets ytorna tillbaka till önskad kapacitet.  |
|||||

\*\* (i) kunder med Microsoft Power BI måste vidta åtgärder i det här migreringsåtgärder som definieras av den angivna migreringsprocessen. (II) ett fel av kunden att vidta åtgärder innebär att Microsoft inte kan slutföra migreringen. (III) när Microsoft inte kan slutföra migreringen på grund av kundens inaktivitet upphör kund-prenumerationen den 29 oktober 2021. 


### <a name="office-apps"></a>Office-appar

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Klienter, Office Online under Office-snabbmigrering, Azure AD Slutför klient organisationens omfattning för att peka på Office 365-tjänsterna. | Denna konfigurations ändring gör att Office-klienter kan uppdatera och peka på Office 365-tjänstens slut punkter. | Alla Office-kunder | -Ta bort MSOID CName från kundägda DNS, om det finns. <br><br> -Meddela användare att _de stänger alla_ Office-program och logga sedan in igen (eller tvinga klienter att starta om och logga in) för att göra det möjligt för Office-klienter att fortsätta med ändringen. <br><br> -Meddela användare och supportavdelningen att användarna *kan* se en Office-banderoll som uppmanar dem att återaktivera Office-appar inom 72 timmar på snabbmigrering. <br><br> -Alla Office-program på personliga datorer måste vara stängda och användarna måste logga ut och sedan logga in igen. Logga in på återaktivera i det gula aktiverings fältet mot Office 365-tjänster. <br><br> -Delade datorer kräver åtgärder som liknar persondatorer och kräver ingen speciell procedur. <br><br> -På mobila enheter måste användarna logga ut från appar, stänga dem och sedan logga in igen. |
|||||

## <a name="during-migration"></a>Under migrering


### <a name="exchange-online"></a>Exchange Online

För eDiscovery:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Under migreringen Miss lyckas eDiscovery-sökningar eller returnerar 0 resultat för SharePoint Online-, OneDrive för företag-och Exchange Online-platser som har migrerats. | Under migreringen kan kunderna fortsätta att skapa ärenden, undantag, sökningar och exporter i [säkerhets & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations), inklusive [innehålls sökning](https://docs.microsoft.com/microsoft-365/compliance/search-for-content).  Sökningar mot SharePoint Online-, OneDrive för företag-och Exchange Online-platser som har migrerats returnerar då antingen 0 resultat eller orsakar ett fel. Information om hur du åtgärdar finns i kolumnen _effekt_ . | Alla kunder som använder eDiscovery |  Om en sökning returnerar 0 resultat eller ett fel under migreringen ska du vidta följande åtgärd för SharePoint Online: <br><br>  Ladda ned webbplatser direkt från SharePoint Online/OneDrive för företag-webbplatsen genom att följa anvisningarna i [Ladda ned filer och mappar från OneDrive eller SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05). Den här metoden kräver behörigheter för SharePoint Online-administratör eller skrivskyddade behörigheter på webbplatsen. <br><br> Om gränser överskrids, som förklaras i [Ladda ned filer och mappar från OneDrive eller SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05), kan kunder använda synkroniseringsklienten för OneDrive för företag genom att följa anvisningarna i [Synkronisera SharePoint-och team-filer med din dator](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88). <br><br> -Exchange Online <br><br> - [Lokal eDiscovery i Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
|||||


### <a name="sharepoint-online"></a>SharePoint Online

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| SharePoint och OneDrive är över gången. | SharePoint och OneDrive migreras från Microsoft Cloud Deutschland till Office 365-tjänster i den här fasen. Befintliga Microsoft Cloud Deutschland-URL: er bevaras ( `contoso.sharepoint.de` ). Token som utfärdas av Microsoft Cloud Deutschland eller Office 365-tjänsterna är giltiga under över gången. | SharePoint-kunder | Inflight SharePoint 2013-arbets flöden bryts under migreringen och måste publiceras igen efter migreringen. |
|||||

### <a name="skype-for-business-online"></a>Skype för företag online

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Migrering av Skype för företag till Teams. | Befintliga Skype för företag-kunder migreras till Office 365-tjänster i Europa och sedan övergår till Microsoft Teams i Tyskland för Office 365-tjänster. | Skype för företag-kunder |  PowerShell används för att administrera inställningar och principer för din klient organisation och användare. När du ansluter till en PowerShell-session lägger du till följande: <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"` |
|||||


## <a name="post-migration"></a>Efter migrering

### <a name="azure-ad"></a>Azure AD

För Hybrid:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Uppdatera Azure AD Connect. | När du har tagit bort allt till Azure AD är organisationen fullt med Office 365-tjänsterna och är inte längre ansluten till Microsoft Cloud Deutschland. För närvarande måste kunden kontrol lera att delta-synkroniseringen har slutförts, och därefter ändra strängvärdet för `AzureInstance` från 3 (Microsoft Cloud Deutschland) till 0 i register Sök vägen `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` . | Hybrid Azure AD – anslutna organisationer | Ändra värdet för `AzureInstance` , register nyckel. Det går inte att synkronisera objekt när det inte längre finns tillgängliga på Deutschland slut punkter för Microsoft Cloud. |
|||||

För federerad inloggningsautentisering:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Ta bort förlitande part-förtroenden från Microsoft Cloud Deutschland AD FS. | När du har tagit bort allt till Azure AD är organisationen fullt med Office 365-tjänsterna och är inte längre ansluten till Microsoft Cloud Deutschland. I det här läget måste kunden ta bort förlitande part-förtroendet till Microsoft Cloud Deutschland-slutpunkter. Det här kan bara göras när inga program av kunden pekar på Microsoft Cloud Deutschland-slutpunkter när Azure AD används som identitets leverantör (IdP). | Organisationer för extern autentiseringsprocess | Ingen. |
|||||

För Azure AD:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Begäran om att gå med i en Azure AD-grupp under de senaste 30 dagarna innan migrering måste begäras in igen om den ursprungliga begäran inte godkändes. | Slutanvändare kommer att behöva använda åtkomst panelen för att skicka en begäran om att ansluta till en Azure AD-grupp igen om dessa förfrågningar inte godkändes under de senaste 30 dagarna före migreringen. | Slutanvändare vars Azure AD-gruppbegäran om godkännande inte godkändes under de senaste 30 dagarna före migrering |  Som slutanvändare: <ol><li>Navigera till [åtkomst panelen](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Leta reda på en Azure AD-grupp där godkännande av medlemskap avvaktas inom 30 dagar före migreringen.</li><li>Begära att gå med i Azure AD-gruppen igen.</li></ol> Förfrågningar om att gå med i en grupp som är aktiva under 30 dagar innan migreringen kan inte godkännas, om de inte begärs efter migreringen. |
|||||

För DNS:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Uppdatera lokala DNS-tjänster för Office 365-slut punkter. | Kundhanterade DNS-poster som pekar på Office 365 Germany måste uppdateras så att de pekar på Office 365-tjänstens slut punkter. | Alla Office-kunder | Nödvändig åtgärd. Om du inte gör det kanske tjänsten eller program varu klienter Miss lyckas. |
|||||

För tjänster från tredje part för Office 365-tjänster:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Uppdaterings partners och tjänster från tredje part för Office 365-tjänster. | -Tredjepartsleverantörer som pekar på Office 365 Germany måste uppdateras för att peka på slut punkterna för Office 365-tjänsterna. Exempel: registrera dig på nytt, i justering med dina leverantörer och partners, program versionen för galleriet, om den finns tillgänglig. <br><br> -Peka på alla anpassade program som använder Graph API från `graph.microsoft.de` till `graph.microsoft.com` . Andra API: er med ändrade slut punkter måste också uppdateras, om de utnyttjas. <br><br> -Ändra alla företags program som inte är första part att omdirigera till slut punkter för hela världen.  | Alla Office-kunder | Nödvändig åtgärd. Om du inte gör det kanske tjänsten eller program varu klienter Miss lyckas. |
|||||

### <a name="exchange-online"></a>Exchange Online

Om du använder en hybrid Exchange-konfiguration:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Kör hybrid konfigurations guiden igen (HCW) mot Office 365-tjänster. | Den befintliga HCW-konfigurationen är avsedd att användas med Microsoft Cloud Deutschland. Om du har migrerat Exchange-tjänsterna är det mycket lokal konfiguration från Microsoft Cloud Deutschland. | Exchange Online-kunder som kör en hybrid distribution | Åtgärd krävs. Om du inte gör det kanske tjänsten eller program varu klienter Miss lyckas. Innan migrering från Exchange-postlådan börjar (med 5 eller fler dagar efter kallelse), bör du meddela klienterna att de ska stoppa och ta bort eventuella registrerings-eller offboarding för sina post lådor.  Om de inte gör det visas fel i deras flytt önskemål. <br><br> -När migreringen av Exchange-postlådan är klar ska du meddela klienterna att de kan återuppta registrerings-och offboarding. <br> Det kanske inte fungerar att köra **test-MigrationServerAvailabiilty**, en PowerShell-cmdlet under migrering av Exchange från Microsoft Cloud Deutschland till Office 365-tjänster. Men det fungerar när migreringen är klar. <br><br> Om klienterna stöter på problem med autentiseringsuppgifter eller auktorisering efter det att post lådorna migrerats, kan användare ange deras lokala administratörs uppgifter igen i migreringens slut punkt genom att köra `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` , eller genom att ange samma med hjälp av Exchange-Kontrollpanelen (ECP).  |

För eDiscovery:

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
|  Alla platser för SharePoint Online, OneDrive för företag och Exchange Online har migrerats tillsammans med säkerhets-och efterlevnadsprinciper (SCC). | Alla eDiscovery-aktiviteter bör köras från hela klient organisationen. Sökningar kommer nu att 100% lyckades.  Eventuella misslyckanden eller fel ska följa vanliga Support kanaler. | Alla kunder som använder eDiscovery | Ingen. |
| Ta bort organisations övergripande principer för bevarande som skapades under för migreringen | Kunderna kan ta bort organisationens övergripande bevarande principer som skapades under kundernas för migrering. | Alla kunder som tillämpar en bevarande princip som en del av stegen för migreringen. | Ingen. |
|||||

### <a name="sharepoint-online"></a>SharePoint Online

| Steg | Beskrivning | Gäller för | Påverkan |
|:-------|:-----|:-------|:-------|
| Publicera om SharePoint 2013-arbetsflöden. | För migreringen minskade vi antalet SharePoint 2013-arbetsflöden. Nu när migreringen är klar kan kunden publicera om arbets flödena. | Alla Office-kunder | Det här är en obligatorisk åtgärd. Om du inte gör det kan användarna bli förvirrande och helpdesk-samtal. |
| Dela objekt via Outlook | Att dela objekt via Outlook fungerar inte längre efter klient organisationens snabbmigrering. | SharePoint Online och OneDrive för företag | -I SharePoint Online och OneDrive för företag kan du dela objekt med Outlook. När du har tryckt på Outlook-knappen skapas en shareable länk till ett nytt meddelande i Outlook Web App. <br><br> -När klient organisationen snabbmigrering fungerar den här metoden för att dela. Det här är ett känt problem. Men eftersom den här Outlook-funktionen är i sökvägen för utfasningen är det inte planerat att åtgärda problemet förrän utfasningen är uppkopplad. |

## <a name="next-step"></a>Nästa steg

[Förstå åtgärder och konsekvenser för migreringsåtgärder](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Mer information

Komma igång:

- [Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i de nya tyska Data Center-regionerna](ms-cloud-germany-transition.md)
- [Hjälp för Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Så här väljer du för migrering](ms-cloud-germany-migration-opt-in.md)
- [Kund upplevelse under migreringen](ms-cloud-germany-transition-experience.md)

Flytta genom över gången:

- [Åtgärder och påverkan i migreringsfaser](ms-cloud-germany-transition-phases.md)
- [Övrig för hands arbete](ms-cloud-germany-transition-add-pre-work.md)
- Ytterligare information för [Azure AD](ms-cloud-germany-transition-azure-ad.md), [enheter](ms-cloud-germany-transition-add-devices.md), [upplevelser](ms-cloud-germany-transition-add-experience.md)och [AD FS](ms-cloud-germany-transition-add-adfs.md).

Molnappar:

- [Information om programmet för Dynamics 365 migration](https://aka.ms/d365ceoptin)
- [Information om datamigreringshanteraren för Power BI](https://aka.ms/pbioptin)
- [Komma igång med din uppgradering av Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
