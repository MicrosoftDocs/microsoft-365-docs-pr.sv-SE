---
title: Ytterligare slut punkter som inte ingår i Office 365 IP Address and URL Web Service
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/29/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: ''
description: 'Sammanfattning: den nya webb tjänsten för slut punkter innehåller inte ett litet antal slut punkter för specifika scenarier.'
hideEdit: true
ms.openlocfilehash: 30d0c7af8420f85abf820839a26c989704860c0a
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235588"
---
# <a name="additional-endpoints-not-included-in-the-office-365-ip-address-and-url-web-service"></a>Ytterligare slut punkter som inte ingår i Office 365 IP Address and URL Web Service

Vissa nätverks slut punkter publicerades tidigare och har inte inkluderats i [Office 365 IP Address and URL Web Service](microsoft-365-ip-web-service.md). Webb tjänstens omfattning är nätverks slut punkter som krävs för anslutning från en användare av Office 365 i ett företags perimeternätverk. Detta inkluderar för närvarande inte:

1. Nätverks anslutning som kan krävas från ett Microsoft-datacenter till ett kund nätverk (inkommande Hybrid Server nätverks trafik).
2. Nätverks anslutningar från servrar i ett kund nät i företags gränserna (Utgående server nätverks trafik).
3. Vanliga scenarier för nätverks anslutnings krav från en användare.
4. Krav för DNS-namnupplösning (visas inte nedan).
5. Tillförlitliga webbplatser för Internet Explorer eller Microsoft Edge.

Förutom DNS är det alla valfria för de flesta kunder om du inte behöver det särskilda scenario som beskrivs.

| Radtyp | Syfte | Destination | Type (Typ) |
|:-----|:-----|:-----|:-----|
| 9.1  | [Importera tjänst](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) för PST och filintag | Mer information finns i [import tjänsten](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) . | Ovanligt utgående scenario |
| två  | [Microsoft-assistenten för support och återställning för Office 365](https://diagnostics.office.com/#/)  | https<span>://</span>Autodiscover.Outlook.com <BR> <span>https://</span>officecdn.Microsoft.com <BR> <span>https://</span>API.Diagnostics.Office.com <BR> <span>https://</span>apibasic.Diagnostics.Office.com <BR> <span>https://</span>Autodiscover-s.Outlook.com <BR> <span>https://</span>cloudcheckenabler.azurewebsites.net <BR> <span>https://</span>DCS-staging.Azure-API.net <BR> <span>https://</span>login.live.com <BR> <span>https://</span>login.microsoftonline.com <BR> <span>https://</span>login.Windows.net <BR> <span>https://</span>o365diagtelemetry.trafficmanager.net <BR> <span>https://</span>ODC.officeapps.live.com <BR> <span>https://</span>offcatedge.azureedge.net <BR> <span>https://</span>officeapps.live.com <BR> <span>https://</span>Outlook.Office365.com <BR> <span>https://</span>outlookdiagnostics.azureedge.net | Utgående server trafik |
| amp;3D  | Azure AD Connect (med alternativ för SSO) – WinRM & Remote PowerShell | Customer STS-miljö (AD FS-server och AD FS-proxy) \| TCP-portarna 80 & 443 | Inkommande server trafik |
| 9.4  | STS som AD FS-proxyservrar (endast för externa kunder) | Kund-STS (som AD FS-proxy) \| portar TCP 443 eller TCP 49443 med ClientTLS | Inkommande server trafik |
| T5  | [Integrering med Exchange Online Unified Messaging/SBC](https://technet.microsoft.com/library/jj673565.aspx) | Dubbelriktad mellan den lokala sessionsgränsen och *. um.outlook.com | Endast utgående Server trafik |
| 18.6  | Migrering av post låda. När migrering av post låda startas från en lokal [Exchange-hybrid](https://docs.microsoft.com/exchange/exchange-deployment-assistant) till Office 365 ansluter Office 365 till din publicerade Exchange Web Services-/Mailbox (EWS) Server. Om du behöver NAT-IP-adresser som används av Exchange Online-servrar för att begränsa inkommande anslutningar från specifika käll-IP-intervall, visas de i [Office 365 URL & IP-intervall](urls-and-ip-address-ranges.md) under tjänst området "Exchange Online". Det är viktigt att se till att åtkomsten till publicerade EWS-slutpunkter som OWA inte påverkas genom att kontrol lera att MRS-proxyn matchar en separat FQDN och en offentlig IP-adress innan du begränsar TCP 443-anslutningar från specifika käll-IP-intervall. | Kundlokal EWS/MRS-proxy<br> TCP-port 443 | Inkommande server trafik |
| borttagning  | [Exchange hybrid](https://docs.microsoft.com/exchange/exchange-deployment-assistant) funktioner för samtidig användning, till exempel ledig/upptagen-delning. | Lokal Exchange-Server | Inkommande server trafik |
| 8.2  | [Exchange hybrid](https://docs.microsoft.com/exchange/exchange-deployment-assistant) proxyautentisering | Kund lokal STS | Inkommande server trafik |
| 9  | Används för att konfigurera [Exchange-hybrid](https://docs.microsoft.com/exchange/exchange-deployment-assistant)med [konfigurations guiden för Exchange-hybrid](https://docs.microsoft.com/exchange/hybrid-configuration-wizard) <br> Obs! dessa slut punkter krävs bara för att konfigurera Exchange-hybrid  | domains.live.com på TCP-portarna 80 & 443, krävs endast för konfigurations guiden för Exchange 2010 SP3<BR> <BR> GCC High, DoD IP-adresser: 40.118.209.192/32; 168.62.190.41/32 <BR> <BR> Världs omfattande & GCC: *. store.core.windows.net; asl.configure.office.com; mshrcstorageprod.blob.core.windows.net; tds.configure.office.com; mshybridservice.trafficmanager.net <BR>  | Endast utgående Server trafik |
| 10.3  | Tjänsten för automatisk identifiering används i [Exchange-hybrid](https://docs.microsoft.com/exchange/exchange-deployment-assistant) scenarier med [hybrid modern med Outlook för iOS och Android](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) <BR> <BR> ```*.acompli.net``` <BR> <BR> ```*.outlookmobile.com``` <BR> <BR> ```*.outlookmobile.us``` <BR> <BR> ```52.125.128.0/20``` <BR> ```52.127.96.0/23``` <BR> | Lokal Exchange Server i TCP 443 | Inkommande server trafik |
| Nr  | Exchange hybrid Azure AD-verifikation | *. msappproxy.net | Endast trafik med TCP utgående Server |
| 12,5  | Skype för företag i Office 2016 inkluderar videobaserad skärm delning som använder UDP-portar. Föregående Skype för företag-klienter i Office 2013 och tidigare använde RDP via TCP-port 443. | TCP-port 443 öppen till 52.112.0.0/14 | Äldre klient versioner av Skype för företag i Office 2013 och tidigare |
| 11  | Lokal server anslutning i Skype för företag till Skype för företag – Online | 13.107.64.0/18, 52.112.0.0/14  <BR> UDP-portar 50000 – 59 999 <BR>  TCP-portarna 50000 – 59 999; 5061 | Utgående anslutning till lokal server för Skype för företag |
| 14  | Cloud PSTN med lokal hybrid anslutning kräver nätverks anslutning öppen för de lokala värdarna. Mer information om hybrid konfigurationer för Skype för företag – Online  | Se [Planera hybrid anslutningar mellan Skype för företag – Server och Office 365](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-hybrid-connectivity) | Lokal hybrid inkommande Skype för företag |
| 0,15  | **Domän namn för inloggningsautentisering och identitet** <br> FQDN ```secure.aadcdn.microsoftonline-p.com``` måste finnas i klientens Internet Explorer (IE) eller Edge Trusted Sites Zone för att fungera. |  | Tillförlitliga platser |
| 16.1  |  **Microsoft Teams FQDN** <br> Om du använder Internet Explorer eller Microsoft Edge måste du aktivera första och tredje partens cookies och lägga till FQDN-namn för Teams på dina betrodda platser. Det här är utöver programomfattande program vara, CDN och telemetri som visas i rad 14. Mer information finns i [kända problem för Microsoft Teams](https://docs.microsoft.com/microsoftteams/known-issues) . |  | Tillförlitliga platser |
| 17.3  |  **SharePoint Online-och OneDrive för företag-FQDN** <br> Alla ". sharepoint.com"-FQDN-namn med " \<tenant> ' i FQDN måste finnas i din klients IE eller Edge Trusted sites för att fungera. Utöver programomfattande-FQDN-, CDN-och telemetri i rad 14 måste du också lägga till dessa slut punkter. |  | Tillförlitliga platser |
| 18.3  | **Yammer**  <br> Yammer är bara tillgänglig i webbläsaren och kräver att den autentiserade användaren passerar via en proxyserver. Alla FQDN-namn för Yammer måste finnas i klientens IE eller Edge Trusted sites för att fungera. |  | Tillförlitliga platser |
| 19.1  | Använd [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/) för att synkronisera lokala användar konton med Azure AD. | Se [hybrid identitet, portar och protokoll](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-ports), [Felsöka Azure AD-anslutning](https://docs.microsoft.com/azure/active-directory/hybrid/tshoot-connect-connectivity)och [installation av Health Agent för Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-health-agent-install#outbound-connectivity-to-the-azure-service-endpoints). | Endast utgående Server trafik |
| 20.1  | [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/) med 21 ViaNet i Kina för att synkronisera lokala användar konton med Azure AD. | \*. digicert.com:80 <BR> \*. entrust.net:80 <BR> \*. chinacloudapi.cn:443 <BR> secure.aadcdn.partner.microsoftonline-p.cn:443 <BR>*. partner.microsoftonline.cn:443 <BR> <BR>Se även [Felsöka problem med Azure AD-anslutningsproblem](https://docs.azure.cn/zh-cn/active-directory/hybrid/tshoot-connect-connectivity). | Endast utgående Server trafik |
| 21.3  | Microsoft Stream (kräver Azure AD User token). <BR> Office 365 världen över (inklusive GCC) | \*. cloudapp.net <BR> \*. api.microsoftstream.com <BR> \*. notification.api.microsoftstream.com <BR> amp.azure.net <BR> api.microsoftstream.com <BR> az416426.vo.msecnd.net <BR> s0.assets-yammer.com <BR> vortex.data.microsoft.com <BR> web.microsoftstream.com <BR> TCP-port 443  | Inkommande server trafik |
| 22  | Använd MFA Server för multifaktorautentisering med multifaktorautentisering, både nya installationer av servern och inställningar i Active Directory Domain Services (AD DS). | Se [komma igång med Azure Multi-Factor Server](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-deploy#plan-your-deployment).  | Endast utgående Server trafik |
| 23  | Microsoft Graph-ändrings aviseringar | Utvecklarna kan utnyttja [ändrings aviseringar](https://docs.microsoft.com/graph/webhooks?context=graph%2Fapi%2F1.0&view=graph-rest-1.0) för att prenumerera på händelser i Microsoft Graph. | *. cloudapp.net<BR> 104.43.130.21, 137.116.169.230, 13.79.38.63, 104.214.39.228, offentlig moln: 168.63.250.205, 52.161.9.202, 40.68.103.62, 13.89.60.223, 23.100.95.104, 40.113.95.219, 104.214.32.10, 168.63.237.145, 52.161.110.176, 52.174.177.183, 13.85.192.59, 13.85.192.123, 13.86.37.15, 13.89.108.233, 13.89.104.147, 20.44.210.83, 20.44.210.146, 40.76.162.99, 40.76.162.42, 40.74.203.28, 40.74.203.27, 51.104.159.213, 51.104.159.181, 51.124.75.43, 51.124.73.177, 51.138.90.7, 51.138.90.52, 52.139.153.222, 52.139.170.157, 52.139.170.47, 52.142.114.29, 52.142.115.31, 52.147.213.251, 52.147.213.181, 52.148.24.136, 52.148.27.39, 52.148.115.48, 52.148.114.238, 52.154.246.238, 52.159.23.209, 52.159.17.84, 52.184.94.140 <BR> Microsoft Cloud för amerikanska myndigheter: 52.244.231.173, 52.238.76.151, 52.244.250.211, 52.238.78.108, 52.243.147.249, 52.243.148.19, 52.243.157.104, 52.243.157.105, 52.244.33.45, 52.244.35.174, 52.244.111.156, 52.244.111.170 <BR> Microsoft Cloud Tyskland: 51.4.231.136, 51.5.243.223, 51.4.226.154, 51.5.244.215, 51.4.150.206, 51.4.150.235, 51.5.147.130, 51.5.148.103 <BR> Microsoft Cloud Kina drivs av 21Vianet: 139.219.15.33, 42.159.154.223, 42.159.88.79, 42.159.155.77, 40.72.155.199, 40.72.155.216, 40.125.138.23, 40.125.136.69, 42.159.72.35, 42.159.72.47, 42.159.180.55, 42.159.180.56<BR> TCP-port 443 <BR> Obs! utvecklare kan ange olika portar när de skapar abonnemangen.  | Inkommande server trafik |
|||||

## <a name="related-topics"></a>Relaterade ämnen

[Hantera Office 365-slutpunkter](managing-office-365-endpoints.md)
  
[Felsöka Office 365-anslutningar](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d.aspx)
  
[Klientanslutning](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[Nätverk för innehållsleverans](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Microsoft Azure Datacenter IP-intervall](https://www.microsoft.com/download/details.aspx?id=41653)
  
[Microsoft Public IP-utrymme](https://www.microsoft.com/download/details.aspx?id=53602)
