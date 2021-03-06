---
title: Översikt över och förutsättningar för hybrid modern autentisering för användning med lokala Skype för företag och Exchange servrar
ms.author: kvice
ms.reviewer: smithre4
author: kelleyvice-msft
manager: laurawi
ms.date: 10/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.assetid: ef753b32-7251-4c9e-b442-1a5aec14e58d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: I den här artikeln lär du dig mer om modern hybridautentisering och förutsättningarna för användning med lokala Skype för företag och Exchange servrar.
ms.openlocfilehash: 33bcf9bde2cda0388160337d3ffe6b81ab94eb12
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907534"
---
# <a name="hybrid-modern-authentication-overview-and-prerequisites-for-using-it-with-on-premises-skype-for-business-and-exchange-servers"></a>Översikt över och förutsättningar för hybrid modern autentisering för att använda den med lokala Skype för företag och Exchange servrar

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

_Modern autentisering_ är en metod för identitetshantering som ger säkrare användarautentisering och auktorisering. Den är tillgänglig för Office 365-hybriddistributioner av Skype för företag lokala server och Exchange-server lokalt, samt för delning av Skype för företag-hybrider. Den här artikeln länkar till relaterade dokument om krav, konfiguration/inaktivering av modern autentisering och till en del relaterad klient (t.ex. Outlook klienter Skype klienter).

- [Vad är modern autentisering?](hybrid-modern-auth-overview.md#BKMK_WhatisModAuth)
- [Vad ändras när jag använder modern autentisering?](hybrid-modern-auth-overview.md#BKMK_WhatChanges)
- [Kontrollera status för modern autentisering för din lokala miljö](hybrid-modern-auth-overview.md#BKMK_CheckStatus)
- [Uppfyller du krav för modern autentisering?](#do-you-meet-modern-authentication-prerequisites)
- [Behöver jag veta något mer innan jag börjar?](hybrid-modern-auth-overview.md#BKMK_Whatelse)

## <a name="what-is-modern-authentication"></a>Vad är modern autentisering?
<a name="BKMK_WhatisModAuth"> </a>

Modern autentisering är en övergripande term för en kombination av autentiserings- och auktoriseringsmetoder mellan en klient (till exempel din bärbara dator eller telefon) och en server, samt vissa säkerhetsåtgärder som kräver åtkomstprinciper som du kanske redan är bekant med. Det innehåller:

- **Autentiseringsmetoder:** Multi-Factor Authentication (MFA) smartkortsautentisering certifikatbaserad autentisering för klient
- **Auktoriseringsmetoder:** Microsofts implementering av Open Authorization (OAuth)
- **Villkorsstyrda** åtkomstprinciper: Hantering av mobilprogram (MAM) och villkorsstyrd Azure Active Directory (Azure AD)

Hantering av användaridentiteter med modern autentisering ger administratörer många olika verktyg för att skydda resurser och erbjuder säkrare metoder för identitetshantering både lokalt (Exchange och Skype för företag), Exchange-hybrid och Skype för företag-hybrid-/delad domän.

Eftersom Skype för företag arbetar tillsammans med Exchange påverkas inloggningsbeteendet Skype för företag-klientanvändarna av den moderna autentiseringsstatusen för Exchange. Det här gäller även om du har en _Skype för företag-hybridarkitektur_ med delad domän där du har både Skype för företag Online och Skype för företag lokalt, med användare som finns på båda platserna.

Mer information om modern autentisering i Office 365 finns i Office 365 stöd för [klientappen – multifaktorautentisering.](microsoft-365-client-support-multi-factor-authentication.md)

> [!IMPORTANT]
> Från och med augusti 2017 kommer alla nya Office 365-klientorganisationen som inkluderar Skype för företag online och Exchange online att ha modern autentisering aktiverad som standard. Befintliga klientorganisationar har ingen ändring i standardtillståndet för ma, men alla nya klientorganisationen stöder automatiskt den utökade uppsättningen identitetsfunktioner som visas ovan. Information om hur du kontrollerar din ma-status finns i avsnittet Kontrollera status för modern autentisering [för din lokala](hybrid-modern-auth-overview.md#BKMK_CheckStatus) miljö.

## <a name="what-changes-when-i-use-modern-authentication"></a>Vad ändras när jag använder modern autentisering?
<a name="BKMK_WhatChanges"> </a>

När du använder modern autentisering med lokal Skype för företag eller Exchange-server  autentiserar du fortfarande användare lokalt,  men när det handlar om att auktorisera deras åtkomst till resurser (som filer eller e-postmeddelanden) ändras. Det är därför, även om modern autentisering handlar om klient- och serverkommunikation, stegen som vidtas när du konfigurerar MA-resultatet i säkerhetstokentjänsten (en säkerhetstokentjänst som används av Azure AD) anges som autentiseringsserver för Skype för företag och Exchange server lokalt.

Genom att ändra till systemskydd kan dina lokala servrar dra nytta av OAuth (tokenutfärdning) för att auktorisera dina klienter, och även låta dina lokala använda säkerhetsmetoder som är vanliga i molnet (t.ex. Multifaktorautentisering). Det innebär också att token som gör att användare kan begära åtkomst till resurser utan att ange sitt lösenord som en del av begäran. Oavsett var användarna finns (online eller lokalt) och oavsett på vilken plats som är värd för den nödvändiga resursen blir ResurssTS kärnan i auktorisering av användare och klienter när modern autentisering har konfigurerats.

Om en Skype för företag-klient till exempel behöver åtkomst till Exchange-server för att hämta kalenderinformation åt en användare, så används ADAL (Active Directory Authentication Library) för detta. ADAL är ett kodbibliotek som utformats för att göra skyddade resurser i katalogen tillgängliga för klientprogram med OAuth-säkerhetstoken. ADAL arbetar med OAuth för att verifiera anspråk och utbyta token (i stället för lösenord) för att ge en användare åtkomst till en resurs. Tidigare var behörigheten i en transaktion som den här – servern som vet hur användaren gör anspråk och utfärdar nödvändiga token – kan ha varit en lokal säkerhetstokentjänst eller till och med Active Directory Federation Services. Men modern autentisering centraliserar den behörigheten med hjälp av Azure AD.

Det innebär också att även om din Exchange-server och Skype för företag-miljö kan vara helt lokal, blir den auktoriseringsserver som är online och din lokala miljö måste kunna skapa och underhålla en anslutning till din Office 365-prenumeration i molnet (och Azure AD-instansen som prenumerationen använder som katalog).

Vad ändras inte? Oavsett om du är i en hybrid med delad domän eller Skype för företag och Exchange en server lokalt måste alla användare först *autentisera lokalt.* I en hybridimplementering av modern autentisering _pekar Både Lyncdiscovery_ och _Automatisk_ upptäckt på din lokala server.

> [!IMPORTANT]
> Om du behöver veta vilka topologier Skype för företag kan användas med ma, finns det [information här](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported).

## <a name="check-the-modern-authentication-status-of-your-on-premises-environment"></a>Kontrollera status för modern autentisering för din lokala miljö
<a name="BKMK_CheckStatus"> </a>

Eftersom modern autentisering ändrar auktoriseringsservern som används när tjänster utnyttjar OAuth/S2S behöver du veta om modern autentisering är aktiverad eller inaktiverad för dina lokala Skype för företag och Exchange miljöer. Du kan kontrollera statusen på dina Exchange genom att köra följande PowerShell-kommando:

```powershell
Get-OrganizationConfig | ft OAuth*
```

Om värdet för egenskapen _OAuth2ClientProfileEnabled_ är **Falskt** inaktiveras modern autentisering.

Mer information om Get-OrganizationConfig cmdlet finns i [Get-OrganizationConfig.](/powershell/module/exchange/get-organizationconfig)

Du kan kontrollera dina Skype för företag genom att köra följande PowerShell-kommando:

```powershell
Get-CSOAuthConfiguration
```

Om kommandot returnerar en tom _OAuthServers-egenskap,_ eller om värdet för egenskapen  _ClientADALAuthOverride_ inte är Tillåtet, är modern autentisering inaktiverad.

Mer information om Get-CsOAuthConfiguration cmdlet finns i [Get-CsOAuthConfiguration](/powershell/module/skype/get-csoauthconfiguration).

## <a name="do-you-meet-modern-authentication-prerequisites"></a>Uppfyller du krav för modern autentisering?

Kontrollera och kontrollera dessa objekt i listan innan du fortsätter:

- **Skype för företag specifik**
  - Alla servrar måste ha kumulativ uppdatering maj 2017 (CU5) för Skype för företag – Server 2015 eller senare
    - **Undantag** – SBA (AA) kan användas i den aktuella versionen (baserat på Lync 2013)
  - Sip-domänen läggs till som en federerad domän i Office 365
  - Alla SFB-klientslut måste ha anslutningar utgående till Internet, till URL:er för Office 365-autentisering (TCP 443) och välkända rotcertifikat-CRL (TCP 80) som visas i raderna 56 och 125 i avsnittet Microsoft 365 Common and Office' i [Office 365 URL:er](urls-and-ip-address-ranges.md)och IP-adressintervall.

- **Skype för företag lokalt i en hybridmiljö Office 365 miljö**
  - En Skype för företag – Server 2019-distribution med alla servrar som Skype för företag – Server 2019.
  - En Skype för företag – Server 2015-distribution med alla servrar som Skype för företag – Server 2015.
  - En distribution med högst två olika serverversioner enligt nedan:
    - Skype för företag 2015
    - Skype för företag 2019
  - Alla Skype för företag måste ha de senaste kumulativa uppdateringarna installerade. Mer information [Skype för företag – Server uppdateringar för](/skypeforbusiness/sfb-server-updates) att hitta och hantera alla tillgängliga uppdateringar.
  - Det finns ingen Lync Server 2010 eller 2013 i hybridmiljön.

>[!NOTE]
>Om dina Skype för företag-frontend-servrar använder en proxyserver för internetanslutning måste den proxyserver-IP och det portnummer som används anges i konfigurationsavsnittet i web.config-filen för varje frontend.

- C:\Program Files\Skype för företag – Server 2015\Web Components\Web ticket\int\web.config
- C:\Program Files\Skype för företag – Server 2015\Web Components\Web ticket\ext\web.config

```xml
<configuration>
  <system.net>
    <defaultProxy>
      <proxy
        proxyaddress="https://192.168.100.60:8080"
        bypassonlocal="true" />
    </defaultProxy>
  </system.net>
</configuration>
```

> [!IMPORTANT]
> Se till att prenumerera på RSS-feeden [för Office 365 URL:er](urls-and-ip-address-ranges.md) och IP-adressintervall för att hålla dig aktuell med de senaste listorna med obligatoriska URL:er.

- **Exchange Server specifik**
  - Du använder antingen Exchange server 2013 CU19 och uppåt, Exchange server 2016 CU8 och uppåt eller Exchange Server 2019 CU1 och uppåt.
  - Det finns Exchange server 2010 i miljön.
  - SSL Offloading är inte konfigurerat. Ssl-uppsägning och omkryptering stöds.
  - Om miljön använder en proxyserverinfrastruktur så att servrar kan ansluta till Internet bör du kontrollera att alla Exchange-servrar har proxyservern definierad i [egenskapen InternetWebProxy.](/powershell/module/exchange/set-exchangeserver)

- **Exchange Server lokalt i en hybridmiljö Office 365 miljö**

  - Om du använder Exchange Server 2013 måste minst en server ha serverrollerna Postlåda och Klientåtkomst installerad. Även om det är möjligt att installera rollerna Postlåda och Klientåtkomst på separata servrar rekommenderar vi starkt att du installerar båda rollerna på samma server för att ge ytterligare tillförlitlighet och högre prestanda.
  - Om du använder Exchange server 2016 eller senare måste minst en server ha serverrollen Mailbox installerad.
  - Det finns Exchange server 2007 eller 2010 i hybridmiljön.
  - Alla Exchange-servrar måste ha de senaste kumulativa uppdateringarna installerade. Mer information Exchange uppgradera till de senaste kumulativa uppdateringarna för att hitta och hantera alla tillgängliga uppdateringar. [](/exchange/plan-and-deploy/install-cumulative-updates)

- **Exchange för klient och protokoll**

    Tillgängligheten för modern autentisering avgörs av kombinationen av klienten, protokollet och konfigurationen. Om modern autentisering inte stöds av klienten, protokollet och/eller konfigurationen fortsätter klienten att utnyttja äldre autentisering.
  
    Följande klienter och protokoll stöder modern autentisering med lokal autentisering Exchange när modern autentisering är aktiverad i miljön:

  |**Klienter**|**Primary Protocol**|**Kommentarer**|
  |:-----|:-----|:-----|
  |Outlook 2013 och senare  <br/> |MAPI över HTTP  <br/> |MAPI över HTTP måste vara aktiverat inom Exchange för att du ska kunna utnyttja modern autentisering med dessa klienter (vanligtvis aktiverat eller Sant för nya installationer av Exchange 2013 Service Pack 1 och högre). Mer information finns i [Hur modern autentisering fungerar för Office 2013 och Office 2016-klientprogram.](modern-auth-for-office-2013-and-2016.md)  <br/> Se till att du kör den lägsta nödvändiga versionen av Outlook. se [Senaste uppdateringar för versioner av Outlook som använder Windows Installer (MSI).](/officeupdates/outlook-updates-msi)  <br/> |
  |Outlook 2016 för Mac och senare  <br/> |Exchange-webbtjänster  <br/> |  <br/> |
  |Outlook för iOS och Android  <br/> | Microsofts synkroniseringsteknik <br/> |Mer [information finns i Använda modern hybridautentisering med Outlook för iOS och Android.](/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)  <br/> |
  |Exchange ActiveSync klienter (t.ex. e-post i iOS11)  <br/> |Exchange ActiveSync  <br/> |För Exchange ActiveSync klienter som stöder modern autentisering måste du återskapa profilen för att kunna växla från grundläggande autentisering till modern autentisering.  <br/> |

    Klienter och/eller protokoll som inte listas (t.ex. POP3) stöder inte modern autentisering med lokal Exchange och fortsätter att utnyttja äldre autentiseringsmetoder även efter att modern autentisering har aktiverats i miljön.

- **Allmänna krav**
  - Resursskogsscenarier kräver tvåvägsförtroende med kontoskogen för att säkerställa att korrekt SID-sökning utförs under hybridsäkra autentiseringsbegäranden. 
  - Om du använder AD FS bör du ha AD FS 3.0 Windows 2012 R2 AD FS 3.0 och högre för federation.
  - Dina identitetskonfigurationer är alla typer som stöds av Azure AD Anslut, till exempel synkronisering av lösenordshashar, direktautentisering och lokal STS som stöds av Office 365.
  - Du har Azure AD Anslut konfigurerat och fungerande för användarreplikering och synkronisering.
  - Du har kontrollerat att hybrid är konfigurerad Exchange klassiskt hybridtopologiläge mellan den lokala Office 365 miljön. Officiellt supportmeddelande för Exchange-hybriden säger att du måste ha antingen aktuell CU eller aktuell CU - 1.
    > [!NOTE]
    > Modern hybridautentisering stöds inte med [hybridagenten.](/exchange/hybrid-deployment/hybrid-agent)

  - Kontrollera att både en testanvändare på datorn och en hybridtestanvändare som finns i Office 365 kan logga in på Skype för företag-skrivbordsklienten (om du vill använda modern autentisering med Skype) och Microsoft Outlook (om du vill använda modern autentisering med Exchange).

## <a name="what-else-do-i-need-to-know-before-i-begin"></a>Behöver jag veta något mer innan jag börjar?
<a name="BKMK_Whatelse"> </a>

- Alla scenarier för lokala servrar omfattar att konfigurera modern autentisering lokalt (för Skype för företag finns det i själva verket en lista över topologier som stöds) så att den server som ansvarar för autentisering och auktorisering finns i Microsoft Cloud (Azure AD:s säkerhetstokentjänst, som kallas "azureSTS") och uppdaterar Azure AD om de URL:er eller namnområden som används av den lokala installationen av antingen Skype för företag eller Exchange. Därför har lokala servrar ett Microsoft Cloud-beroende. Du kan överväga att konfigurera "hybridauth" för att vidta den här åtgärden.
- Den här artikeln länkar till andra som hjälper dig att välja topologier som stöds för modern autentisering (endast nödvändiga för Skype för företag) och instruktioner som beskriver konfigurationsstegen eller steg för att inaktivera modern autentisering, för Exchange lokalt och Skype för företag lokalt. Gör den här sidan till favorit i webbläsaren om du behöver en bas för användning av modern autentisering i servermiljön.

## <a name="related-topics"></a>Relaterade ämnen
<a name="BKMK_URLListforMA"> </a>

- [Så här konfigurerar Exchange Server lokal användning av modern autentisering](configure-exchange-server-for-hybrid-modern-authentication.md)
- [Skype för företag topologier som stöds med modern autentisering](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
- [Så här konfigurerar Skype för företag lokal användning av modern autentisering](configure-skype-for-business-for-hybrid-modern-authentication.md)
- [Ta bort eller inaktivera hybrid modern autentisering från Skype för företag och Exchange](remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha.md)