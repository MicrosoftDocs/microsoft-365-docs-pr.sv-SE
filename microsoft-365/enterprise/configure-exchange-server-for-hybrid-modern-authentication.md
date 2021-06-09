---
title: Så här konfigurerar Exchange Server lokal användning av modern hybridautentisering
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
description: Lär dig hur du konfigurerar Exchange Server en lokal konfiguration för att använda modern hybridautentisering (HMA), som ger dig säkrare användarautentisering och auktorisering.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d30d1b2b14efd66d973e9bf6d45b970d7af681bc
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841636"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>Så här konfigurerar Exchange Server lokal användning av modern hybridautentisering

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

HMA (Hybrid Modern Authentication) är en metod för identitetshantering som ger säkrare användarautentisering och auktorisering, och är tillgänglig för Exchange-serverdistributioner med lokala hybriddistributioner.

## <a name="fyi"></a>OBS

Innan vi börjar ringer jag:

- HMA (Hybrid Modern \> Authentication)

- Exchange lokalt \> EXCH

- \>Exchange Online EXO

Om en bild i den här artikeln har ett objekt som är nedtonat eller nedtonat innebär det att elementet som visas med grått inte ingår i *HMA-specifik konfiguration.*

## <a name="enabling-hybrid-modern-authentication"></a>Aktivera modern hybridautentisering

Om du slår på HMA innebär det att:

1. Att vara säker på att du uppfyller kraven innan du börjar.

1. Eftersom många **förutsättningar** är vanliga för både Skype för företag och Exchange, översikt över hybrid modern autentisering och krav för att använda den med lokala Skype för företag och [Exchange servrar.](hybrid-modern-auth-overview.md) Gör detta innan du påbörjar något av stegen i den här artikeln.

1. Lägga till lokala webbtjänst-URL:er som **servicehuvudnamn (SPN)** i Azure AD. Om EXCH är i hybrid med flera innehavare måste dessa lokala webbtjänstwebbadresser läggas till som SPN i Azure AD för alla klientorganisationen som finns i hybrid med EXCH.

1. Kontrollera att alla virtuella kataloger är aktiverade för HMA

1. Söka efter objektet Enth Auth Server

1. Aktivera HMA i EXCH.

> [!NOTE]
> Stöder din version av Office MA? Se [Hur modern autentisering fungerar för Office 2013 och Office 2016-klientappar.](modern-auth-for-office-2013-and-2016.md)


## <a name="make-sure-you-meet-all-the-prerequisites"></a>Se till att du uppfyller alla krav

Eftersom det finns många krav som är gemensamma för både Skype för företag och Exchange bör du läsa Översikt över modern hybridautentisering och förutsättningar för att använda den med Skype för företag och [Exchange servrar.](hybrid-modern-auth-overview.md) Gör detta  *innan*  du påbörjar något av stegen i den här artikeln.

> [!NOTE]
> Outlook Web App och Exchange fungerar inte med modern hybridautentisering.

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>Lägga till lokala webbtjänst-URL:er som SPN i Azure AD

Kör kommandona som tilldelar lokala webbtjänstwebbadresser som Azure AD SPN. SPN används av klientdatorer och enheter under autentisering och auktorisering. Alla URL:er som kan användas för att ansluta från lokala resurser till Azure Active Directory (Azure AD) måste vara registrerade i Azure AD (detta omfattar både interna och externa namnområden).

Först måste du samla in alla URL-adresser som du behöver lägga till i AAD. Kör följande kommandon lokalt:

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
```

Kontrollera att URL-klienterna kanske ansluter till visas som HTTPS-tjänstens huvudnamn i AAD. Om EXCH är i hybrid med flera innehavare **,** ska dessa HTTPS-SPN läggas till i AAD för alla klientorganisationen i hybrid med EXCH.

1. Börja med att ansluta till AAD med [de här instruktionerna.](connect-to-microsoft-365-powershell.md)

    > [!NOTE]
    > Du måste använda alternativet _Anslut-MsolService_ från den här sidan för att kunna använda kommandot nedan.

2. För dina Exchange-relaterade URL:er skriver du följande kommando:

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   Notera (och skärmbilder för senare jämförelser) utdata för det här kommandot, som bör innehålla en URL för https://  *autodiscover.yourdomain.com*  och https://  *mail.yourdomain.com,* men består oftast av SPN som börjar med 00000002-0000-0ff1-ce00-000000000000/. Om det https:// url:er från din lokala plats som saknas måste vi lägga till de specifika posterna i den här listan.

3. Om du inte ser dina interna och externa MAPI/HTTP-, EWS-, ActiveSync-, OAB- och automatisk upptäckt-poster i den här listan måste du lägga till dem med hjälp av kommandot nedan (exempeladresserna är ' ' och ' men du kan ersätta exempeladresserna med dina `mail.corp.contoso.com` `owa.contoso.com` **egna**):

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. Kontrollera att de nya posterna har lagts till genom att köra kommandot Get-MsolServicePrincipal från steg 2 igen och titta igenom utdata. Jämför listan/skärmbilden före med den nya listan med SPN. Du kan också ta en skärmbild av den nya listan för dina poster. Om det lyckades visas de två nya webbadresserna i listan. Om vi går igenom exemplet innehåller listan med SPN nu specifika URL:er  `https://mail.corp.contoso.com`  och  `https://owa.contoso.com` .

## <a name="verify-virtual-directories-are-properly-configured"></a>Kontrollera att virtuella kataloger är korrekt konfigurerade

Kontrollera nu att OAuth är korrekt aktiverat Exchange i alla virtuella kataloger som Outlook kan använda genom att köra följande kommandon:

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

Kontrollera resultatet för att kontrollera att **OAuth** är aktiverat för var och en av dessa VDirs, det ser ut ungefär så här (och det viktiga att titta på är "OAuth"):

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

Om OAuth saknas på en server och någon av de fyra virtuella katalogerna måste du lägga till den med relevanta kommandon innan du fortsätter ([Set-MapiVirtualDirectory,](/powershell/module/exchange/set-mapivirtualdirectory) [Set-WebServicesVirtualDirectory,](/powershell/module/exchange/set-webservicesvirtualdirectory) [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)och [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>Bekräfta att The Ents Auth Server-objektet finns

Återgå till den lokala Exchange för det senaste kommandot. Nu kan du verifiera att din lokala tjänst har en post för autentiseringsprovidern för windows-säkerhet:

```powershell
Get-AuthServer | where {$_.Name -like "EvoSts"}
```

Dina utdata bör visa autentiseringsservern för Name EllerSts och statusen "Enabled" ska vara True. Om du inte ser det bör du ladda ned och köra den senaste versionen av hybridkonfigurationsguiden.

> [!NOTE]
> Om EXCH är i hybridläge med flera klientorganisationsklienter bör utdata visa en **autentiseringsserver** för namnkvitterna – {GUID} för varje klientorganisation i hybrid med EXCH och "Aktiverad"-läget ska vara Sant för alla dessa AuthServer-objekt.

 **Viktigt** Om du kör Exchange 2010 i din miljö skapas inte autentiseringsprovidern För företagsautentisering.

## <a name="enable-hma"></a>Aktivera HMA

Kör följande kommando i Exchange Management Shell lokalt:

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

Om EXCH-versionen är Exchange 2016 (CU18 eller senare) eller Exchange 2019 (CU7 eller senare) och hybrid konfigurerades med HCW som laddats ned efter september 2020 kör du följande kommando i Exchange Management Shell lokalt:

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -DomainName "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> Om EXCH är i hybrid **med** flera innehavare finns det flera AuthServer-objekt i EXCH med domäner som motsvarar varje klientorganisation.  Flaggan **IsDefaultAuthorizationEndpoint** ska vara inställd på true (med hjälp av cmdleten **IsDefaultAuthorizationEndpoint)** för något av dessa AuthServer-objekt. Den här flaggan kan inte ställas in på sant för alla Authserver-objekt och HMA aktiveras även om ett av authServer-objektets **IsDefaultAuthorizationEndpoint-flagga** är satt till true.

## <a name="verify"></a>Verifiera

När du har aktiverat HMA används det nya autentiseringsflödet för klientens nästa inloggning. Observera att endast aktivera HMA utlöser inte en nyauthentication för någon klient. Klienterna återauthenticate baserat på livslängden för autentiseringstoken och/eller certifikat de har.

Du bör också hålla ned CTRL-tangenten samtidigt som du högerklickar på ikonen för Outlook-klienten (även i meddelandefältet i Windows) och klickar på "Anslutningsstatus". Leta efter klientens SMTP-adress mot typen "Authn" av typen "Bearer", som representerar den bearer-token som används \* i OAuth.

> [!NOTE]
> Behöver du konfigurera Skype för företag med HMA? Du behöver två artiklar: en som innehåller [topologier](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)som stöds och en som visar [hur du gör konfigurationen.](configure-skype-for-business-for-hybrid-modern-authentication.md)


## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>Använda modern hybridautentisering med Outlook för iOS och Android

Om du är en lokal kund som använder Exchange på TCP 443 kringgår du trafikbearbetning för följande IP-adressintervall:

```text
52.125.128.0/20
52.127.96.0/23
```

Appen Outlook för iOS och Android är utformad som det bästa sättet att uppleva Microsoft 365 eller Office 365 på din mobila enhet med hjälp av Microsoft-tjänster för att hitta, planera och prioritera ditt dagliga liv och arbete. Mer information finns i Använda [modern hybridautentisering med Outlook för iOS och Android.](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)

## <a name="related-topics"></a>Relaterade ämnen

[Konfigurationskrav för modern autentisering för övergång Office 365 dedikerad/ITAR till vNext](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
