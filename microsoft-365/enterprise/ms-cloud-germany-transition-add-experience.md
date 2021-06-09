---
title: Aktiviteter efter migreringen från Microsoft Cloud Deutschland
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
description: 'Sammanfattning: Efter migreringens aktiviteter efter flytten från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365 i den nya tyska datacenterområdet.'
ms.openlocfilehash: ee8dedf7ffaf6bfc4246b1a8cc2522c15d763cd1
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899370"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Aktiviteter efter migreringen från Microsoft Cloud Deutschland

I följande avsnitt finns aktiviteter efter migrering för flera tjänster efter flytt från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365 tjänster i den nya tyska datacenterområdet.

## <a name="azure-ad"></a>Azure AD
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a>Federerad Azure AD-autentisering med AD FS
**Gäller för:** Alla kunder som använder federerad autentisering med AD FS

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Ta bort förtroenden från en part i Microsoft Cloud Deutschland AD FS. | Efter att användningen av Azure AD har slutförts använder organisationen alla tjänster Office 365 och är inte längre ansluten till Microsoft Cloud Deutschland. I det här läget behöver kunden ta bort det beroende tredjepartsförtroendet till Microsoft Cloud Deutschland-slutpunkterna. Detta kan endast göras om ingen av kundens program pekar på Microsoft Cloud Deutschland-slutpunkter när Azure AD används som en identitetsprovider (IdP). | Organisationer med federerad autentisering | Ingen. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a>Gruppgodkännanden
**Gäller för:** Slutanvändare vars Azure AD-gruppgodkännandebegäranden inte godkänts under de senaste 30 dagarna före migreringen 

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Förfrågningar om att gå med i en Azure AD-grupp de senaste 30 dagarna innan migreringen måste begäras igen om den ursprungliga begäran inte godkänts. | Slutanvändarkunder måste använda åtkomstpanelen för att skicka en begäran om att ansluta till en Azure AD-grupp igen om dessa begäranden inte godkänts under de senaste 30 dagarna före migreringen. |  Som slutanvändare: <ol><li>Gå till [åtkomstpanelen](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Hitta en Azure AD-grupp för vilken godkännande av medlemskap väntar under 30 dagar före migreringen.</li><li>Begär att få gå med i Azure AD-gruppen igen.</li></ol> Förfrågningar om att gå med i en grupp som är aktiv mindre än 30 dagar innan migreringen kan inte godkännas, såvida de inte begärs igen efter migreringen. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
## <a name="custom-dns-updates"></a>Anpassade DNS-uppdateringar
**Gäller för:**  Alla kunder som hanterar sina egna DNS-zoner

| Steg | Beskrivning | Påverkan |
|:------|:-------|:-------|
| Uppdatera lokala DNS-tjänster för Office 365-tjänstens slutpunkter. | Kund hanterade DNS-poster som pekar på Microsoft Cloud Deutschland måste uppdateras så att de pekar Office 365 slutpunkter för globala tjänster. | Om du inte gör det kan det leda till att tjänsten eller programvaruklienten inte fungerar. |
||||

## <a name="third-party-services"></a>Tredjepartstjänster
**Gäller för:** Kunder som använder tredjepartstjänster för Office 365 slutpunkter för tjänster

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Uppdatera partner och tredjepartstjänster för att Office 365 slutpunkter för tjänster. | <ul><li>Tredjepartstjänster och partner som pekar på Office 365 Germany måste uppdateras så att de pekar Office 365-tjänstslutpunkterna. Exempel: Registrera igen, i linje med dina leverantörer och partner, galleriets appversion av program, om tillgängligt. </li><li>Peka alla anpassade program som utnyttjar Graph API från `graph.microsoft.de` till `graph.microsoft.com` . Andra API:er med ändrade slutpunkter måste också uppdateras, om de används. </li><li>Ändra alla företagsprogram som inte är från första part så att de omdirigeras till de globala slutpunkterna. </li></ul>| Obligatorisk åtgärd. Om du inte gör det kan det leda till att tjänsten eller programvaruklienten inte fungerar. |
||||

## <a name="sharepoint-online"></a>SharePoint Online
**Gäller för:** Kunder som SharePoint 2013-arbetsflöden

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Publicera om SharePoint 2013-arbetsflöden. | Under arbetet före migreringen minskade vi antalet arbetsflöden i SharePoint 2013. Nu när migreringen är klar kan kunden publicera arbetsflödena på nytt. | Det här är en åtgärd som krävs. Om du inte gör det kan det leda till förvirring och samtal till supporten. |
| Dela objekt via Outlook | Delning av objekt SharePoint Online och OneDrive för företag via Outlook inte längre fungerar efter klientorganisationens övertid. |<ul><li>I SharePoint Online och OneDrive för företag kan du dela objekt via Outlook. När du trycker Outlook här knappen skapas en delningsbar länk som sedan skickas till ett nytt meddelande i Outlook Web App.</li><li>Efter att klientorganisationen har tagit över kommer den här delningsmetoden inte att fungera. Vi känner igen det här är ett känt problem. Men eftersom den Outlook är i vägen för utfasningen är det inte planerat att åtgärda problemet förrän utfasningen distribueras. </li></ul>|
||||

## <a name="exchange-online"></a>Exchange Online
**Gäller för:** Kunder som använder en hybridkonfiguration Exchange hybridlösningar

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Kör om hybridkonfigurationsguiden (HCW) mot Office 365 tjänster. | Den befintliga HCW-konfigurationen är avsedd att stödja Microsoft Cloud Deutschland. När migreringen Exchange tjänster slutförs avkodas vi den lokala konfigurationen från Microsoft Cloud Deutschland. |<ul><li>Obligatorisk åtgärd. Om du inte gör det kan det leda till att tjänsten eller programvaruklienten inte fungerar. Innan Exchange postlådemigrering börjar (med 5 eller fler dagars förvarning) bör du meddela klienterna att de ska stoppa och ta bort alla flyttningar av onboarding eller offboarding för postlådorna.  Om de inte gör det visas fel i sina flyttningsförfrågningar. </li><li>När Exchange postlådemigrering har slutförts meddelar du klienter att de kan återuppta flyttningar av onboarding och offboarding. <br> **Test-MigrationServerAvailabiilty**, en PowerShell-cmdlet, under migreringen av Exchange från Microsoft Cloud Deutschland till Office 365-tjänster kanske inte fungerar. Men det fungerar korrekt när migreringen är klar. </li><li>Om klienter får problem med autentiseringsuppgifter eller auktorisering efter att postlådorna migrerats kan användare ange sina lokala administratörsautentiseringsuppgifter på nytt i migreringsslutpunkten genom att köra , eller genom att ange samma med hjälp av `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` Exchange Control Panel (ECP). </li></ul>|
