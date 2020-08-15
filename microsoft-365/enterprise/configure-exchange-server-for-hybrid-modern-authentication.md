---
title: Så här konfigurerar du Exchange Server lokalt för användning av hybrid modern
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Lär dig hur du konfigurerar en Exchange-Server lokalt för användning av hybrid modern autentisering (HMA) och ger dig säkrare autentisering och verifiering.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 291c7c220fb4ee56db2a42409d5b81724de5da32
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694283"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>Så här konfigurerar du Exchange Server lokalt för användning av hybrid modern

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Hybrid modern autentisering (HMA) är en metod för identitets hantering som erbjuder säkrare användar verifiering och-auktorisering och är tillgängligt för Exchange Server-lokala hybrid installationer.
  
## <a name="fyi"></a>Observera

Innan vi börjar ringer jag:
  
- Hybrid modern, \> HMA

- Exchange \> lokalt valutakurs

- Exchange Online- \> EXO

*Om en bild i den här artikeln har ett objekt som är nedtonat eller nedtonat, innebär det att elementet som visas i grått inte ingår i HMA-specifik konfiguration* .
  
## <a name="enabling-hybrid-modern-authentication"></a>Aktivera hybrid modern

Att aktivera HMA på medelvärden:
  
1. Det är bara att möta PreReqs innan du börjar.

1. Eftersom många **förutsättningar** är vanliga för både Skype för företag och Exchange, är [hybrid modern verifiering och förutsättningar för att använda den med lokala Skype för företag-och Exchange-servrar](hybrid-modern-auth-overview.md). Gör det innan du följer anvisningarna i den här artikeln.

1. Lägga till lokala webb tjänst-URL: er som **tjänst huvud namn (SPN)** i Azure AD.

1. Kontrol lera att alla virtuella kataloger är aktiverade för HMA

1. Söker efter serverobjektet för EvoSTS

1. Aktivera HMA i VALUTAKURS.

 **Obs!** Stöder din version av Office MA? Se [hur modern inloggningsautentisering fungerar för office 2013-och Office 2016-klient program](modern-auth-for-office-2013-and-2016.md).
  
## <a name="make-sure-you-meet-all-the-prerequisites"></a>Kontrol lera att du uppfyller alla krav

Eftersom många förutsättningar är vanliga för både Skype för företag och Exchange bör du läsa [hybridens översikt över modern och förutsättningar för att använda den med lokala Skype för företag-och Exchange-servrar](hybrid-modern-auth-overview.md). Gör det  *innan*  du följer anvisningarna i den här artikeln.
  
## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>Lägga till lokala webb tjänst-URL: er som SPN i Azure AD

Kör kommandona som tilldelar dina lokala webb tjänst-URL: er som Azure AD-SPN. SPN används av klient datorer och enheter vid autentisering och auktorisering. Alla URL-adresser som kan användas för att ansluta från lokala platser till Azure Active Directory (Azure AD) måste vara registrerade i Azure AD (Detta inkluderar både interna och externa namn områden).
  
Först samlar du in alla URL-adresser som du måste lägga till i AAD. Kör dessa kommandon lokalt:
  
```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```
    
Se till att URL-klienterna kan ansluta till är listade som HTTPS-tjänstens huvud namn i AAD.
  
1. Först ansluter du till AAD med [dessa instruktioner](connect-to-microsoft-365-powershell.md).

 **Obs!** Du måste använda alternativet _Connect-MSOLService_ på den här sidan om du vill kunna använda kommandot nedan.

2. För Exchange-relaterade URL-adresser skriver du följande kommando:

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
```

Ta del av (och skärmdump för senare jämförelse) utdata för det här kommandot, vilket bör omfatta en https://  *Autodiscover.yourdomain.com*  och https://  *mail.yourdomain.com* -URL, men i de flesta fall är SPN-namn som börjar med 00000002-0000-0ff1-CE00-000000000000/. Om det finns https://URL-adresser från dina lokala platser måste vi lägga till dessa specifika poster i den här listan.
  
3. Om du inte ser dina interna och externa MAPI/HTTP-, EWS-, ActiveSync-, OAB-och Autodiscover-poster i den här listan måste du lägga till dem med hjälp av kommandot nedan (exempel-URL: erna är " `mail.corp.contoso.com` " och " `owa.contoso.com` ", men du **ersätter exempel URL-adresserna med din egen** ): <br/>
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
$x.ServicePrincipalnames.Add("https://owa.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```

4. Verifiera att de nya posterna har lagts till genom att köra kommandot Get-MsolServicePrincipal från steg 2 igen och titta igenom resultatet. Jämför listan/skärm bilden från den nya listan med SPN-namn (du kan också skriva in den nya listan för posterna). Om du lyckades ser du de två nya URL-adresserna i listan. I vårt exempel kommer listan med SPN att inkludera specifika URL: er  `https://mail.corp.contoso.com`  och  `https://owa.contoso.com` . 
  
## <a name="verify-virtual-directories-are-properly-configured"></a>Verifiera att virtuella kataloger är korrekt konfigurerade

Verifiera att OAuth är korrekt aktive rad i Exchange på alla virtuella kataloger som Outlook kan använda genom att köra följande kommandon:

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth* 
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

Kontrol lera att **OAuth** är aktiverat på var och en av de här VDirs kommer det att se ut ungefär så här (och de viktigaste att titta på är ' OAuth '):

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```
  
Om OAuth saknas från någon server och någon av de fyra virtuella katalogerna måste du lägga till den med relevanta kommandon innan du fortsätter ([set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-mapivirtualdirectory?view=exchange-ps), [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-webservicesvirtualdirectory?view=exchange-ps), [set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/email-addresses-and-address-books/set-oabvirtualdirectory?view=exchange-ps)och [set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-autodiscovervirtualdirectory?view=exchange-ps)).
  
## <a name="confirm-the-evosts-auth-server-object-is-present"></a>Bekräfta att EvoSTS-auth-objektet finns

Återvänd till det lokala Exchange Management Shell för det här senaste kommandot. Nu kan du kontrol lera att din lokala tjänst har en post för evoSTS-autentiseringsprovidern:
  
```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

Utdata ska visa en AuthServer av namnet EvoSts och läget ' Enabled ' ska vara sant. Om du inte ser det här ska du ladda ned och köra den senaste versionen av hybrid konfigurations guiden.
  
 **Viktigt** Om du kör Exchange 2010 i din miljö skapas inte EvoSTS. 
  
## <a name="enable-hma"></a>Aktivera HMA

Kör följande kommando i Exchange Management Shell, lokalt:

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true  
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a>Kontroll

När du har aktiverat HMA använder klientens nästa inloggning det nya trafikflödet. Observera att när du aktiverar HMA utlöses ingen omauktorisering för någon klient. Klienterna autentiseras på nytt baserat på hur många autentiseringstoken och/eller vilka certifikat de har.
  
Du bör även hålla ned CTRL-tangenten samtidigt som du högerklickar på ikonen för Outlook-klienten (även i Windows Notifications) och klickar på "anslutnings status". Leta efter klientens SMTP-adress mot "authn" \* -typen, som representerar Bearer-token som används i OAuth.
  
 **Obs!** Behöver du konfigurera Skype för företag med HMA? Du behöver två artiklar: en som visar en lista med [topologier som stöds](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)och en som visar [hur](configure-skype-for-business-for-hybrid-modern-authentication.md)du konfigurerar.
 
## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>Använda hybrid modern inloggningsautentisering med Outlook för iOS och Android

Om du är lokal kund med Exchange Server på TCP 443 ska du Lägg följande IP-adressintervall:  <BR> ```52.125.128.0/20``` <BR> ```52.127.96.0/23``` <BR>

## <a name="related-topics"></a>Relaterade ämnen

[Moderna konfigurations krav för inloggningsautentisering för över gång från Office 365 dedikerade/ITAR till vNext](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
