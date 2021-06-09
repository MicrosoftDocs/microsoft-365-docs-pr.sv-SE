---
title: Ytterligare slutpunkter ingår inte i IP-adressen och URL-webbtjänsten för Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/19/2021
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
ms.openlocfilehash: 6c545b6060b44ebe234baaebd3ae1eb2fdb0fb89
ms.sourcegitcommit: 76f3c75413cc960289489d0ca29efadb8a9a5b31
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "51887215"
---
# <a name="additional-endpoints-not-included-in-the-office-365-ip-address-and-url-web-service"></a>Ytterligare slutpunkter ingår inte i IP-adressen och URL-webbtjänsten för Office 365

Vissa nätverksslutpunkter har publicerats tidigare och har inte inkluderats i [IP-Office 365 och URL-webbtjänsten](microsoft-365-ip-web-service.md)i microsoft Office 365. Webbtjänstomfattningen är nätverksslutpunkter som krävs för anslutning från en användare av Office 365 över ett företags perimeternätverk. Detta omfattar för närvarande inte:

1. Nätverksanslutning som kan krävas från ett Microsoft-datacenter till ett kundnätverk (inkommande hybridservernätverkstrafik).
2. Nätverksanslutning från servrar i ett kundnätverk över företags perimeter (utgående servernätverkstrafik).
3. Ovanliga scenarier för nätverksanslutningskrav från en användare.
4. Krav på anslutning av DNS-upplösning (anges inte nedan).
5. Internet Explorer eller Microsoft Edge betrodda platser.

Förutom DNS är alla dessa valfria för de flesta kunder såvida du inte behöver det specifika scenario som beskrivs.

| Rad | Syfte | Destination | Typ |
|:-----|:-----|:-----|:-----|
| 1  | [Importtjänst](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) för PST- och filtillägg | Se [importtjänsten för](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) ytterligare krav. | Ovanligt utgående scenario |
| 2  | [Microsoft Support- och återställningsassistenten för Office 365](https://diagnostics.office.com/#/)  | https<span>://</span>autodiscover.outlook.com <BR> <span>https://</span>officecdn.microsoft.com <BR> <span>https://</span>api.diagnostics.office.com <BR> <span>https://</span>apibasic.diagnostics.office.com <BR> <span>https://</span>autodiscover-s.outlook.com <BR> <span>https://</span>cloudcheckenabler.azurewebsites.net <BR> <span>https://</span>login.live.com <BR> <span>https://</span>login.microsoftonline.com <BR> <span>https://</span>login.windows.net <BR> <span>https://</span>o365diagtelemetry.trafficmanager.net <BR> <span>https://</span>odc.officeapps.live.com <BR> <span>https://</span>offcatedge.azureedge.net <BR> <span>https://</span>officeapps.live.com <BR> <span>https://</span>outlook.office365.com <BR> <span>https://</span>outlookdiagnostics.azureedge.net | Utgående servertrafik |
| 3  | Azure AD Anslut (med SSO-alternativ) – WinRM & fjärr-PowerShell | KUNDENS STS-miljö (AD FS-server och AD FS-proxy) \| TCP-portar 80 & 443 | Inkommande servertrafik |
| 4  | STS som AD FS-proxyservrar (endast för externa kunder) | Kundens STS-portar (till exempel AD FS-proxy) \| TCP 443 eller TCP 49443 med/ClientTLS | Inkommande servertrafik |
| 5  | [Exchange Online Unified Messaging/SBC-integrering](/exchange/voice-mail-unified-messaging/telephone-system-integration-with-um/configuration-notes-for-session-border-controllers) | Dubbelriktad mellan lokal sessionsgränskontroll och *.um.outlook.com | Utgående servertrafik |
| 6  | Migrering av postlåda. När postlådemigrering initieras från lokal [Exchange-hybrid](/exchange/exchange-deployment-assistant) till Office 365 kommer Office 365 att ansluta till din publicerade Exchange Web Services-server (EWS)/Mailbox Replication Services (MRS). Om du behöver NAT IP-adresser som används av Exchange Online-servrar för att begränsa inkommande anslutningar från specifika käll-IP-intervall visas de i [Office 365 URL & IP-intervall](urls-and-ip-address-ranges.md) under "Exchange Online"-tjänstområdet. Se till att åtkomst till publicerade EWS-slutpunkter som OWA inte påverkas genom att säkerställa att MRS-proxyn löser till en separat FQDN och offentlig IP-adress innan du begränsar TCP 443-anslutningar från specifika käll-IP-intervall. | Kundens lokala EWS/MRS-proxy<br> TCP-port 443 | Inkommande servertrafik |
| 7  | [Exchange](/exchange/exchange-deployment-assistant) hybrid-samexistensfunktioner som delning av ledig/upptagen. | Kundens lokala Exchange server | Inkommande servertrafik |
| 8  | [Exchange hybridproxyautentisering](/exchange/exchange-deployment-assistant) | Kundens lokala STS | Inkommande servertrafik |
| 9  | Används för att [Exchange hybrid](/exchange/exchange-deployment-assistant), med hjälp [Exchange hybridkonfigurationsguiden](/exchange/hybrid-configuration-wizard) <br> Obs! Dessa slutpunkter krävs endast för att konfigurera Exchange-hybrid  | domains.live.com på TCP-portarna 80 & 443 krävs endast för Exchange 2010 SP3-hybridkonfigurationsguiden<BR> <BR> GCC High, DoD IP addresses: 40.118.209.192/32; 168.62.190.41/32 <BR> <BR> Globala kommersiella & GCC: *.store.core.windows.net; asl.configure.office.com; tds.configure.office.com; mshybridservice.trafficmanager.net ; <BR> aka.ms/hybridwizard; <BR> shcwreleaseprod.blob.core.windows.net/shcw/ \* ;<BR>  | Utgående servertrafik |
| 10  | Tjänsten Identifiera automatiskt används i Exchange [med modern](/exchange/exchange-deployment-assistant) [hybridautentisering med Outlook för iOS och Android](/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) <BR> <BR> ```*.acompli.net``` <BR> <BR> ```*.outlookmobile.com``` <BR> <BR> ```*.outlookmobile.us``` <BR> <BR> ```52.125.128.0/20``` <BR> ```52.127.96.0/23``` <BR> | Kundens lokala Exchange på TCP 443 | Inkommande servertrafik |
| 11  | Exchange Azure AD-hybridautentisering | *.msappproxy.net | TCP-utgående servertrafik |
| 12  | Skype för företag i Office 2016 finns videobaserad skärmdelning som använder UDP-portar. Tidigare Skype för företag klienter i Office 2013 och tidigare använda RDP över TCP-port 443. | TCP-port 443 öppen för 52.112.0.0/14 | Skype för företag äldre klientversioner i Office 2013 och tidigare |
| 13  | Skype för företag en lokal hybridserveranslutning till Skype för företag Online | 13.107.64.0/18, 52.112.0.0/14  <BR> UDP-portar 50 000–59 999 <BR>  TCP-portarna 50 000–59 999; 5061 | Skype för företag utgående server på en lokal server |
| 14  | Pstn i molnet med lokal hybridanslutning kräver att nätverksanslutningen är öppen till de lokala värdarna. Mer information om Skype för företag Online-hybridkonfigurationer  | Se [Planera hybridanslutningar mellan Skype för företag – Server och Office 365](/skypeforbusiness/hybrid/plan-hybrid-connectivity) | Skype för företag inkommande hybrid i lokal miljö |
| 15  | **Autentisering och identitet, FQDN** <br> FQDN måste finnas i zonen för tillförlitliga platser i ```secure.aadcdn.microsoftonline-p.com``` Internet Explorer (IE) eller Edge för att fungera. |  | Betrodda platser |
| 16  |  **Microsoft Teams FQDN** <br> Om du använder Internet Explorer eller Microsoft Edge måste du aktivera cookies från första och tredje part och lägga till de FQDN för Teams i Betrodda platser. Detta utöver de programsvitens FQDN, CDN:er och telemetri som visas på rad 14. Mer [information finns i Microsoft Teams](/microsoftteams/known-issues) problem med data. |  | Betrodda platser |
| 17  |  **SharePoint Online och OneDrive för företag FQDN** <br> Alla FQDN sharepoint.com .sharepoint.com ' med ' i FQDN måste finnas i klientens betrodda platser för IE eller Edge för \<tenant> att fungera. Förutom de programsvitens FQDN, CDN:er och telemetri som visas på rad 14 måste du även lägga till dessa slutpunkter. |  | Betrodda platser |
| 18  | **Yammer**  <br> Yammer är bara tillgängligt i webbläsaren och kräver att den autentiserade användaren går via proxy. Alla Yammer FQDN måste finnas i zonen för tillförlitliga platser i IE eller Edge för att fungera. |  | Betrodda platser |
| 19  | Använd [Azure AD Anslut](/azure/active-directory/hybrid/) för att synkronisera lokala användarkonton till Azure AD. | Se [Portar och protokoll som krävs för hybrididentitet,](/azure/active-directory/hybrid/reference-connect-ports)Felsöka Azure [AD-anslutningar](/azure/active-directory/hybrid/tshoot-connect-connectivity)och [Azure AD Anslut Health Agent Installation](/azure/active-directory/hybrid/how-to-connect-health-agent-install#outbound-connectivity-to-the-azure-service-endpoints). | Utgående servertrafik |
| 20  | [Azure AD Anslut](/azure/active-directory/hybrid/) med 21 ViaNet i Kina för att synkronisera lokala användarkonton till Azure AD. | \*.digicert.com:80 <BR> \*.entrust.net:80 <BR> \*.chinacloudapi.cn:443 <BR> secure.aadcdn.partner.microsoftonline-p.cn:443 <BR>*.partner.microsoftonline.cn:443 <BR> <BR>Se även [Felsöka anslutningsproblem med Azure AD-anslutning.](https://docs.azure.cn/zh-cn/active-directory/hybrid/tshoot-connect-connectivity) | Utgående servertrafik |
| 21  | Microsoft Stream (azure AD-användartoken krävs). <BR> Office 365 Globalt (inklusive GCC) | \*.cloudapp.net <BR> \*.api.microsoftstream.com <BR> \*.notification.api.microsoftstream.com <BR> amp.azure.net <BR> api.microsoftstream.com <BR> az416426.vo.msecnd.net <BR> s0.assets-yammer.com <BR> vortex.data.microsoft.com <BR> web.microsoftstream.com <BR> TCP-port 443  | Inkommande servertrafik |
| 22  | Använd MFA-server för multifaktorautentiseringsförfrågningar, både för nya installationer av servern och för att konfigurera den med AD DS (Active Directory Domain Services). | Se [Komma igång med Azure AD Multi-Factor Authentication Server.](/azure/active-directory/authentication/howto-mfaserver-deploy#plan-your-deployment)  | Utgående servertrafik |
| 23  | Microsoft Graph Ändra aviseringar | Utvecklare kan använda [aviseringar om ändringar](/graph/webhooks?context=graph%2fapi%2f1.0&view=graph-rest-1.0) för att prenumerera på händelser i Microsoft Graph. | *.cloudapp.net<BR> 104.43.130.21, 137.116.169.230, 13.79.38.63, 104.214.39.228, Public Cloud: 168.63.250.205, 52.161.9.202, 40.68.103.62, 13.89.60.223, 23.100.95.104, 40.113.95.219, 104.214.32.10, 168.63.237.145, 52.161.110.176, 52.174.177.183, 13.85.192.59, 13.85.192.123, 13.86.37.15, 13.89.108.233, 13.89.104.147, 20.44.210.83, 20.44.210.146, 40.76.162.99, 40.76.162.42, 40.74.203.28, 40.74.203.27, 51.104.159.213, 51.104.159.181, 51.124.75.43, 51.124.73.177, 51.138.90.7, 51.138.90.52, 52.139.153.222, 52.139.170.157, 52.139.170.47, 52.142.114.29, 52.142.115.31, 52.147.213.251, 52.147.213.181, 52.148.24.136, 52.148.27.39, 52.148.115.48, 52.148.114.238, 52.154.246.238, 52.159.23.209, 52.159.17.84, 52.184.94.140 <BR> Microsoft Cloud for US Government: 52.244.231.173 52.238.76.151, 52.244.250.211, 52.238.78.108, 52.243.147.249, 52.243.148.19, 52.243.157.104, 52.243.157.105, 52.244.33.45, 52.244.35.174, 52.244.111.156, 52.244.111.170 <BR> Microsoft Cloud Germany: 51.4.231.136, 51.5.243.223, 51.4.226.154, 51.5.244.215, 51.4.150.206, 51.4.150.235, 51.5.147.130, 51.5.148.103 <BR> Microsoft Cloud China som drivs av 21Vianet: 139.219.15.33 42.159.154.223, 42.159.88.79, 42.159.155.77, 40.72.155.199, 40.72.155.216, 40.125.138.23, 40.125.136.69, 42.159.72.35, 42.159.72.47, 42.159.180.55, 42.159.180.56<BR> TCP-port 443 <BR> Obs! Utvecklare kan ange olika portar när prenumerationer skapas.  | Inkommande servertrafik |
|||||

## <a name="related-topics"></a>Relaterade ämnen

[Hantera Office 365-slutpunkter](managing-office-365-endpoints.md)
  
[Övervaka Microsoft 365 anslutning](./monitor-connectivity.md)
  
[Klientanslutning](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[Nätverk för innehållsleverans](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Azure IP-intervall och tjänsttaggar – Offentligt moln](https://www.microsoft.com/download/details.aspx?id=56519)

[Azure IP-intervall och tjänsttaggar – Us Government Cloud](https://www.microsoft.com/download/details.aspx?id=57063)

[Azure IP-intervall och tjänsttaggar – Germany Cloud](https://www.microsoft.com/download/details.aspx?id=57064)

[Azure IP-intervall och tjänsttaggar – China Cloud](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Microsoft Public IP-utrymme](https://www.microsoft.com/download/details.aspx?id=53602)