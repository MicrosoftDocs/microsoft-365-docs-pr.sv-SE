---
title: Ytterligare slutpunkter som inte ingår i IP-adressen och URL-webbtjänsten för Office 365
ms.author: kvice
author: kelleyvice-msft
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
description: 'Sammanfattning: Den nya slutpunktswebbtjänsten innehåller inte ett litet antal slutpunkter för specifika scenarier.'
hideEdit: true
ms.openlocfilehash: 7922730957be93b2cdfbd06a48d39fc54ac4af89
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711982"
---
# <a name="additional-endpoints-not-included-in-the-office-365-ip-address-and-url-web-service"></a>Ytterligare slutpunkter som inte ingår i IP-adressen och URL-webbtjänsten för Office 365

Vissa nätverksslutpunkter publicerades tidigare och har inte inkluderats i IP-adressen och [URL-webbtjänsten för Office 365.](microsoft-365-ip-web-service.md) Webbtjänstomfattningen är nätverksslutpunkter som krävs för anslutning från en användare av Office 365 över ett företags perimeternätverk. Detta omfattar för närvarande inte:

1. Nätverksanslutning som kan krävas från ett Microsoft-datacenter till ett kundnätverk (inkommande nätverkstrafik på hybridservern).
2. Nätverksanslutning från servrar i ett kundnätverk över företags perimeter (utgående servernätverkstrafik).
3. Ovanliga scenarier för nätverksanslutningskrav från en användare.
4. Krav på anslutning till DNS-upplösning (anges inte nedan).
5. Betrodda platser i Internet Explorer eller Microsoft Edge.

Förutom DNS är alla dessa valfria för de flesta kunder om du inte behöver det specifika scenario som beskrivs.

| Rad | Syfte | Destination | Type (Typ) |
|:-----|:-----|:-----|:-----|
| 1  | [Importtjänst](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) för PST- och filtillägg | Se [importtjänsten för](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) ytterligare krav. | Ovanligt utgående scenario |
| 2  | [Microsoft Support- och återställningsassistenten för Office 365](https://diagnostics.office.com/#/)  | https<span>://</span>autodiscover.outlook.com <BR> <span>https://</span>officecdn.microsoft.com <BR> <span>https://</span>api.diagnostics.office.com <BR> <span>https://</span>apibasic.diagnostics.office.com <BR> <span>https://</span>autodiscover-s.outlook.com <BR> <span>https://</span>cloudcheckenabler.azurewebsites.net <BR> <span>https://</span>dcs-staging.azure-api.net <BR> <span>https://</span>login.live.com <BR> <span>https://</span>login.microsoftonline.com <BR> <span>https://</span>login.windows.net <BR> <span>https://</span>o365diagtelemetry.trafficmanager.net <BR> <span>https://</span>odc.officeapps.live.com <BR> <span>https://</span>offcatedge.azureedge.net <BR> <span>https://</span>officeapps.live.com <BR> <span>https://</span>outlook.office365.com <BR> <span>https://</span>outlookdiagnostics.azureedge.net | Utgående servertrafik |
| 3  | Azure AD Connect (med SSO-alternativ) – WinRM & fjärr-PowerShell | TCP-portar 80 & 443 för kunders STS-miljö (AD FS-server \| och AD FS-proxy) | Inkommande servertrafik |
| 4  | STS som AD FS-proxyservrar (endast för externa kunder) | Klient-STS-portar (till exempel AD FS-proxy) \| portar TCP 443 eller TCP 49443 med ClientTLS | Inkommande servertrafik |
| 5  | [Exchange Online Unified Messaging/SBC-integrering](https://technet.microsoft.com/library/jj673565.aspx) | Dubbelriktad mellan lokal sessionsgränskontroll och *.um.outlook.com | Endast trafik för utgående server |
| 6  | Migrering av postlåda. När postlådemigrering initieras från lokal [Exchange-hybrid](https://docs.microsoft.com/exchange/exchange-deployment-assistant) till Office 365 ansluter Office 365 till din publicerade Exchange Web Services-server (EWS)/Mailbox Replication Services (MRS). Om du behöver NAT IP-adresserna som används av Exchange Online-servrarna för att begränsa inkommande anslutningar från specifika käll-IP-intervall visas de i IP-intervallen för [Office 365 URL &](urls-and-ip-address-ranges.md) under tjänstområdet "Exchange Online". Se till att åtkomst till publicerade EWS-slutpunkter som OWA inte påverkas genom att säkerställa att MRS-proxyn matchas till en separat FQDN och offentlig IP-adress innan du begränsar TCP 443-anslutningar från specifika käll-IP-intervall. | Kundens lokala EWS/MRS-proxy<br> TCP-port 443 | Inkommande servertrafik |
| 7  | [Exchange-hybrid](https://docs.microsoft.com/exchange/exchange-deployment-assistant) med samexistensfunktioner som delning av ledig/upptagen tid. | Lokal Exchange-server för kunder | Inkommande servertrafik |
| 8  | [Proxyautentisering för Exchange-hybrid](https://docs.microsoft.com/exchange/exchange-deployment-assistant) | Kundens lokala STS | Inkommande servertrafik |
| 9  | Används för att konfigurera [Exchange-hybrid](https://docs.microsoft.com/exchange/exchange-deployment-assistant)med hjälp av [konfigurationsguiden för Exchange-hybrid](https://docs.microsoft.com/exchange/hybrid-configuration-wizard) <br> Obs! Dessa slutpunkter krävs endast för att konfigurera Exchange-hybrid  | domains.live.com på TCP-portarna 80 & 443, krävs endast för konfigurationsguiden för Exchange 2010 SP3-hybrid<BR> <BR> GCC High, DoD IP addresses: 40.118.209.192/32; 168.62.190.41/32 <BR> <BR> Global & GCC: *.store.core.windows.net; asl.configure.office.com; tds.configure.office.com; mshybridservice.trafficmanager.net ; <BR> aka.ms/hybridwizard; <BR> shcwreleaseprod.blob.core.windows.net/shcw/ \* ;<BR>  | Endast trafik för utgående server |
| 10  | Tjänsten Identifiera automatiskt används [](https://docs.microsoft.com/exchange/exchange-deployment-assistant) i Exchange-hybridscenarier med [modern hybridautentisering med Outlook för iOS och Android](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) <BR> <BR> ```*.acompli.net``` <BR> <BR> ```*.outlookmobile.com``` <BR> <BR> ```*.outlookmobile.us``` <BR> <BR> ```52.125.128.0/20``` <BR> ```52.127.96.0/23``` <BR> | Kundens lokala Exchange-server på TCP 443 | Inkommande servertrafik |
| 11  | Azure AD-autentisering för Exchange-hybrid | *.msappproxy.net | TCP-utgående server – endast trafik |
| 12  | Skype för företag i Office 2016 innehåller videobaserad skärmdelning som använder UDP-portar. Tidigare Skype för företag-klienter i Office 2013 och tidigare använda RDP över TCP-port 443. | TCP-port 443 öppen till 52.112.0.0/14 | Äldre Skype för företag-klientversioner i Office 2013 och tidigare |
| 13  | Skype för företag-hybridanslutning på lokal server till Skype för företag – Online | 13.107.64.0/18, 52.112.0.0/14  <BR> UDP-portar 50 000–59 999 <BR>  TCP-portarna 50 000–59 999; 5061 | Utgående Skype för företag-server |
| 14  | Pstn i molnet med lokal hybridanslutning kräver att nätverksanslutningen är öppen till de lokala värdarna. Mer information om hybridkonfigurationer för Skype för företag – Online  | Se [planhybridanslutning mellan Skype för företag – Server och Office 365](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-hybrid-connectivity) | Inkommande Skype för företag-hybrid |
| 15  | **Autentisering och identitet, FQDN** <br> FQDN måste finnas i klientens zon för tillförlitliga platser i Internet Explorer (IE) eller Edge för ```secure.aadcdn.microsoftonline-p.com``` att fungera. |  | Betrodda platser |
| 16  |  **Microsoft Teams, FQDN** <br> Om du använder Internet Explorer eller Microsoft Edge måste du aktivera cookies från första och tredje part och lägga till de FQDN för Teams i betrodda platser. Detta är ett tillägg till de FQDN, CDN:er och telemetri som visas på rad 14. Mer information [finns i Kända problem i Microsoft Teams.](https://docs.microsoft.com/microsoftteams/known-issues) |  | Betrodda platser |
| 17  |  **SharePoint Online och OneDrive för företag, FQDN** <br> Alla FQDN sharepoint.com.sharepoint.com ' i det FQDN som finns i klientens betrodda platser i IE eller Edge för \<tenant> att fungera. Förutom de programsvitens FQDN, CDN:er och telemetri som visas på rad 14 måste du också lägga till dessa slutpunkter. |  | Betrodda platser |
| 18  | **Yammer**  <br> Yammer är bara tillgängligt i webbläsaren och kräver att den autentiserade användaren går via proxy. Alla Yammer FQDN måste finnas i klientens betrodda platser för IE eller Edge för att fungera. |  | Betrodda platser |
| 19  | Använd [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/) för att synkronisera lokala användarkonton till Azure AD. | Se [portar och protokoll som krävs för hybrididentitet,](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-ports)Felsöka Azure [AD-anslutning](https://docs.microsoft.com/azure/active-directory/hybrid/tshoot-connect-connectivity)och [installation av Azure AD Connect Health Agent.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-health-agent-install#outbound-connectivity-to-the-azure-service-endpoints) | Endast trafik för utgående server |
| 20  | [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/) med 21 ViaNet i Kina för att synkronisera lokala användarkonton till Azure AD. | \*.digicert.com:80 <BR> \*.entrust.net:80 <BR> \*.chinacloudapi.cn:443 <BR> secure.aadcdn.partner.microsoftonline-p.cn:443 <BR>*.partner.microsoftonline.cn:443 <BR> <BR>Se även [Felsöka anslutningsproblem med Azure AD-anslutning.](https://docs.azure.cn/zh-cn/active-directory/hybrid/tshoot-connect-connectivity) | Endast trafik för utgående server |
| 21  | Microsoft Stream (kräver Azure AD-användartoken). <BR> Office 365 worldwide (inklusive GCC) | \*.cloudapp.net <BR> \*.api.microsoftstream.com <BR> \*.notification.api.microsoftstream.com <BR> amp.azure.net <BR> api.microsoftstream.com <BR> az416426.vo.msecnd.net <BR> s0.assets-yammer.com <BR> vortex.data.microsoft.com <BR> web.microsoftstream.com <BR> TCP-port 443  | Inkommande servertrafik |
| 22  | Använd MFA-server för multifaktorautentiseringsförfrågningar, både för nya installationer av servern och för att konfigurera den Active Directory DS (AD DS). | Se [Komma igång med Azure AD Multi-Factor Authentication Server.](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-deploy#plan-your-deployment)  | Endast trafik för utgående server |
| 23  | Meddelanden om ändringar i Microsoft Graph | Utvecklare kan använda [aviseringar om ändringar](https://docs.microsoft.com/graph/webhooks?context=graph%2Fapi%2F1.0&view=graph-rest-1.0) för att prenumerera på händelser i Microsoft Graph. | *.cloudapp.net<BR> 104.43.130.21, 137.116.169.230, 13.79.38.63, 104.214.39.228, Public Cloud: 168.63.250.205, 52.161.9.202, 40.68.103.62, 13.89.60.223, 23.100.95.104, 40.113.95.219, 104.214.32.10, 168.63.237.145, 52.161.110.176, 52.174.177.183, 13.85.192.59, 13.85.192.123, 13.86.37.15, 13.89.108.233, 13.89.104.147, 20.44.210.83, 20.44.210.146, 40.76.162.99, 40.76.162.42, 40.74.203.28, 40.74.203.27, 51.104.159.213, 51.104.159.181, 51.124.75.43, 51.124.73.177, 51.138.90.7, 51.138.90.52, 52.139.153.222, 52.139.170.157, 52.139.170.47, 52.142.114.29, 52.142.115.31, 52.147.213.251, 52.147.213.181, 52.148.24.136, 52.148.27.39, 52.148.115.48, 52.148.114.238, 52.154.246.238, 52.159.23.209, 52.159.17.84, 52.184.94.140 <BR> Microsoft Cloud för amerikanska myndigheter: 52.244.231.173, 52.238.76.151, 52.244.250.211, 52.238.78.108, 52.243.147.249, 52.243.148.19, 52.243.157.104, 52.243.157.105, 52.244.33.45, 52.244.35.174, 52.244.111.156, 52.244.111.170 <BR> Microsoft Cloud Germany: 51.4.231.136, 51.5.243.223, 51.4.226.154, 51.5.244.215, 51.4.150.206, 51.4.150.235, 51.5.147.130, 51.5.148.103 <BR> Microsoft Cloud China som drivs av 21Vianet: 139.219.15.33 42.159.154.223, 42.159.88.79, 42.159.155.77, 40.72.155.199, 40.72.155.216, 40.125.138.23, 40.125.136.69, 42.159.72.35, 42.159.72.47, 42.159.180.55, 42.159.180.56<BR> TCP-port 443 <BR> Obs! Utvecklare kan ange olika portar när prenumerationer skapas.  | Inkommande servertrafik |
|||||

## <a name="related-topics"></a>Relaterade ämnen

[Hantera Office 365-slutpunkter](managing-office-365-endpoints.md)
  
[Övervaka Microsoft 365 anslutning](https://docs.microsoft.com/microsoft-365/enterprise/monitor-connectivity?view=o365-worldwide)
  
[Klientanslutning](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[Nätverk för innehållsleverans](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Azure IP-intervall och tjänsttaggar – offentligt moln](https://www.microsoft.com/download/details.aspx?id=56519)

[Azure IP-intervall och tjänsttaggar – AMERIKANSKA Government Cloud](https://www.microsoft.com/download/details.aspx?id=57063)

[Azure IP-intervall och tjänsttaggar – Germany Cloud](https://www.microsoft.com/download/details.aspx?id=57064)

[Azure IP-intervall och tjänsttaggar – China Cloud](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Microsoft Public IP-utrymme](https://www.microsoft.com/download/details.aspx?id=53602)
