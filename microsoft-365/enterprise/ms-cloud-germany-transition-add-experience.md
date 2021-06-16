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
ms.openlocfilehash: 3659ce8ffa3424c3521c8f8954be88c7d53d0a51
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930421"
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
| Ta bort förtroenden från en part i Microsoft Cloud Deutschland AD FS. | Efter att användningen av Azure AD har slutförts använder organisationen alla tjänster Office 365 och är inte längre ansluten till Microsoft Cloud Deutschland. I det här läget behöver kunden ta bort det beroende tredjepartsförtroendet till Microsoft Cloud Deutschland-slutpunkterna. Detta kan endast göras om ingen av kundens program pekar på Microsoft Cloud Deutschland-slutpunkter när Azure AD används som en identitetsprovider (IdP). | Organisationer med federerad autentisering | 
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

## <a name="custom-dns-updates"></a>Anpassade DNS-uppdateringar
**Gäller för:**  Alla kunder som hanterar sina egna DNS-zoner

| Steg | Beskrivning | Påverkan |
|:------|:-------|:-------|
| Uppdatera lokala DNS-tjänster för Office 365-tjänstens slutpunkter. | Kund hanterade DNS-poster som pekar på Microsoft Cloud Deutschland måste uppdateras så att de pekar Office 365 slutpunkter för globala tjänster. Se Domäner [i administrationscentret Microsoft 365 och](https://admin.microsoft.com/Adminportal/Home#/Domains) tillämpa ändringarna i DNS-konfigurationen. | Om du inte gör det kan det leda till att tjänsten eller programvaruklienten inte fungerar. |
||||

## <a name="third-party-services"></a>Tredjepartstjänster
**Gäller för:** Kunder som använder tredjepartstjänster för Office 365 slutpunkter för tjänster

| Steg | Beskrivning | Påverkan |
|:-------|:-------|:-------|
| Uppdatera partner och tredjepartstjänster för att Office 365 slutpunkter för tjänster. | <ul><li>Tredjepartstjänster och partner som pekar på Office 365 Germany måste uppdateras så att de pekar Office 365-tjänstslutpunkterna. Exempel: Registrera igen, i linje med dina leverantörer och partner, galleriets appversion av program, om tillgängligt. </li><li>Peka alla anpassade program som utnyttjar Graph API från `graph.microsoft.de` till `graph.microsoft.com` . Andra API:er med ändrade slutpunkter måste också uppdateras, om de används. </li><li>Ändra alla företagsprogram som inte är från första part så att de omdirigeras till de globala slutpunkterna. </li></ul>| Obligatorisk åtgärd. Om du inte gör det kan det leda till att tjänsten eller programvaruklienten inte fungerar. |
||||