---
title: Översikt över modern hybridautentisering och förutsättningar för användning med Skype för företag- och Exchange-servrar lokalt
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
description: I den här artikeln får du lära dig mer om modern hybridautentisering och förutsättningar för användning med lokala Skype för företag- och Exchange-servrar.
ms.openlocfilehash: b9b48f591f74bd508b20a851ec48a0d7132d6a84
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097110"
---
# <a name="hybrid-modern-authentication-overview-and-prerequisites-for-using-it-with-on-premises-skype-for-business-and-exchange-servers"></a>Översikt över modern hybridautentisering och förutsättningar för att använda den med Skype för företag- och Exchange-servrar lokalt

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

_Modern autentisering_ är en metod för identitetshantering med säkrare användarautentisering och auktorisering. Den är tillgänglig för Office 365-hybriddistributioner av Skype för företag – server lokalt och Exchange-server lokalt, samt för skype för företag-hybrider med delad domän. Den här artikeln länkar till relaterade dokument om krav, konfiguration/inaktivering av modern autentisering och till en del av den relaterade klienten (t.ex. Information om Outlook- och Skype-klienter.

- [Vad är modern autentisering?](hybrid-modern-auth-overview.md#BKMK_WhatisModAuth)
- [Vad ändras när jag använder modern autentisering?](hybrid-modern-auth-overview.md#BKMK_WhatChanges)
- [Kontrollera modern autentiseringsstatus för din lokala miljö](hybrid-modern-auth-overview.md#BKMK_CheckStatus)
- [Uppfyller du kraven för modern autentisering?](#do-you-meet-modern-authentication-prerequisites)
- [Vad mer behöver jag veta innan jag börjar?](hybrid-modern-auth-overview.md#BKMK_Whatelse)

## <a name="what-is-modern-authentication"></a>Vad är modern autentisering?
<a name="BKMK_WhatisModAuth"> </a>

Modern autentisering är en övergripande term för en kombination av autentiserings- och auktoriseringsmetoder mellan en klient (till exempel din bärbara dator eller telefon) och en server, samt vissa säkerhetsåtgärder som kräver åtkomstprinciper som du kanske redan är bekant med. Det innehåller:

- **Autentiseringsmetoder:** Multifaktorautentisering (MFA) autentisering med smartkort certifikatbaserad autentisering för klient
- **Auktoriseringsmetoder:** Microsofts implementering av Open Authorization (OAuth)
- **Villkorsstyrda** åtkomstprinciper: Villkorsstyrd åtkomst för mobilprogramshantering (MAM) och villkorsstyrd åtkomst i Azure Active Directory (Azure AD)

Hantering av användaridentiteter med modern autentisering ger administratörer många olika verktyg för att skydda resurser och erbjuder säkrare metoder för identitetshantering för både lokal (Exchange och Skype för företag), Exchange-hybrid och hybrid-/delningsdomänscenarier för Skype för företag.

Eftersom Skype för företag samarbetar nära med Exchange påverkas inloggningsbeteendet som Skype för företag-klientanvändarna ser av den moderna autentiseringsstatusen för Exchange. Det här gäller även om du  har en hybridarkitektur med delad domän i Skype för företag där du har både Skype för företag – Online och Skype för företag lokalt, med användare lokalt på båda platserna.

Mer information om modern autentisering i Office 365 finns i supporten för [Office 365-klientappen – multifaktorautentisering.](microsoft-365-client-support-multi-factor-authentication.md)

> [!IMPORTANT]
> Från och med augusti 2017 kommer alla nya Office 365-innehavare som inkluderar Skype för företag – Online och Exchange Online att ha modern autentisering aktiverad som standard. Befintliga klientorganisationar har ingen ändring av standardtillståndet för ma, men alla nya klientorganisations har automatiskt stöd för den utökade uppsättning identitetsfunktioner som du ser ovan. Om du vill kontrollera din MA-status, [se kontrollera status för modern autentisering för din lokala](hybrid-modern-auth-overview.md#BKMK_CheckStatus) miljö.

## <a name="what-changes-when-i-use-modern-authentication"></a>Vad ändras när jag använder modern autentisering?
<a name="BKMK_WhatChanges"> </a>

När du använder modern autentisering med Skype för företag eller  Exchange-server lokalt autentiserar du  fortfarande användare lokalt, men hur det går till med auktorisering av deras åtkomst till resurser (t.ex. filer eller e-postmeddelanden) ändras. Det är därför, även om modern autentisering handlar om klient- och serverkommunikation, hur stegen som vidtas vid konfigurering av MA-resultatet i säkerhetstoken (en tjänst för säkerhetstoken som används av Azure AD) anges som autentiseringsserver för Skype för företag och Exchange-server lokalt.

Genom att ändra till de lokala serversystemen kan dina lokala servrar dra nytta av OAuth (token-utfärdning) för att auktorisera klienter och även låta dina lokala använda säkerhetsmetoder som är gemensamma för molnet (t.ex. multifaktorautentisering). Dessutom gäller de säkerhets-TOKENS-problem som gör att användare kan begära åtkomst till resurser utan att ange sitt lösenord som en del av begäran. Oavsett var användarna finns (online eller lokalt) och oavsett vilken plats som är värd för den nödvändiga resursen blir ResursSTS kärnan i auktorisering av användare och klienter när modern autentisering har konfigurerats.

Om en Skype för företag-klient till exempel behöver åtkomst till Exchange server för att få kalenderinformation åt en användare använder den ADAL (Active Directory Authentication Library) för att göra det. ADAL är ett kodbibliotek som utformats för att göra skyddade resurser i katalogen tillgängliga för klientprogram med OAuth-säkerhetstoken. ADAL arbetar med OAuth för att verifiera anspråk och utbyta token (i stället för lösenord), för att ge en användare åtkomst till en resurs. Tidigare kan instansen i en transaktion som den här – servern som vet hur användaren begär och utfärda nödvändiga token – ha varit en lokal säkerhetstokentjänst eller till och med Active Directory Federation Services. Modern autentisering centraliserar emellertid den behörigheten med hjälp av Azure AD.

Det här innebär också att även om Exchange-servern och Skype för företag-miljöerna kan vara helt lokala finns den auktoriseringsservern online och din lokala miljö måste kunna skapa och underhålla en anslutning till din Office 365-prenumeration i molnet (och den Azure AD-instans som din prenumeration använder som katalog).

Vad ändras inte? Oavsett om du är i en hybrid med delad domän eller använder Skype för företag och Exchange server lokalt måste alla användare först *autentisera lokalt.* I en hybridimplementering av modern autentisering _pekar Lyncdiscovery_ och _Automatisk_ upptäckt båda på din lokala server.

> [!IMPORTANT]
> Om du behöver veta vilka Skype för företag-topologier som stöds med MA finns det ett [dokument här.](https://technet.microsoft.com/library/mt803262.aspx)

## <a name="check-the-modern-authentication-status-of-your-on-premises-environment"></a>Kontrollera modern autentiseringsstatus för din lokala miljö
<a name="BKMK_CheckStatus"> </a>

Eftersom modern autentisering ändrar auktoriseringsservern som används när tjänster använder OAuth/S2S behöver du veta om modern autentisering är aktiverad eller inaktiverad för dina lokala Skype för företag- och Exchange-miljöer. Du kan kontrollera statusen på dina Exchange-servrar genom att köra följande PowerShell-kommando:

```powershell
Get-OrganizationConfig | ft OAuth*
```

Om värdet för egenskapen _OAuth2ClientProfileEnabled_ är **Falskt** inaktiveras modern autentisering.

Mer information om Get-OrganizationConfig cmdlet finns [i Get-OrganizationConfig.](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig)

Du kan kontrollera dina Skype för företag-servrar genom att köra följande PowerShell-kommando:

```powershell
Get-CSOAuthConfiguration
```

Om kommandot returnerar en tom _OAuthServers-egenskap,_ eller om värdet för egenskapen _ClientADALAuthOverride_ inte är **Tillåtet,** inaktiveras modern autentisering.

Mer information om Get-CsOAuthConfiguration cmdleten finns i [Get-CsOAuthConfiguration.](https://docs.microsoft.com/powershell/module/skype/get-csoauthconfiguration)

## <a name="do-you-meet-modern-authentication-prerequisites"></a>Uppfyller du kraven för modern autentisering?

Kontrollera och kontrollera dessa objekt i listan innan du fortsätter:

- **Skype för företag-specifikt**
  - Alla servrar måste ha kumulativ uppdatering maj 2017 (CU5) för Skype för företag – Server 2015 eller senare
    - **Undantag** – ABA (ABA) kan vara baserat på den aktuella versionen (baserat på Lync 2013)
  - Din SIP-domän läggs till som en federerad domän i Office 365
  - Alla SAB-klientslut måste ha anslutningar utgående till Internet, till URL-adresser för Office 365-autentisering (TCP 443) och välkända rotcertifikat-CRL (TCP 80) som visas i raderna 56 och 125 i avsnittet "Microsoft 365 Common and Office" i [OFFICE 365-URL:er](urls-and-ip-address-ranges.md)och IP-adressintervall.

- **Skype för företag lokalt i en Office 365-hybridmiljö**
  - En skype för företag – Server 2019-distribution med alla servrar som kör Skype för företag – Server 2019.
  - En skype för företag – Server 2015-distribution med alla servrar som kör Skype för företag – Server 2015.
  - En distribution med högst två olika serverversioner som anges nedan:
    - Skype för företag 2015
    - Skype för företag 2019
  - Alla Skype för företag-servrar måste ha de senaste kumulativa uppdateringarna installerade, se [Skype för företag – Server-uppdateringar för](https://docs.microsoft.com/skypeforbusiness/sfb-server-updates) att hitta och hantera alla tillgängliga uppdateringar.
  - Det finns ingen Lync Server 2010 eller 2013 i hybridmiljön.

>[!NOTE]
>Om Skype för företag-frontend-servrarna använder en proxyserver för Internetåtkomst måste proxyserverns IP- och portnummer anges i konfigurationsavsnittet i web.config-filen för varje frontend.

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
> Se till att prenumerera på RSS-flödet för URL-adresser och IP-adressintervall för [Office 365](urls-and-ip-address-ranges.md) så att du alltid har de senaste listorna med obligatoriska URL:er.

- **Exchange Server specifik**
  - Du använder antingen Exchange Server 2013 CU19 och uppåt, Exchange server 2016 CU8 och uppåt, eller Exchange Server 2019 CU1 och uppåt.
  - Det finns ingen Exchange server 2010 i miljön.
  - SSL-avläsning är inte konfigurerat. SSL-uppsägning och omkryptering stöds.
  - Om miljön använder en proxyserverinfrastruktur som tillåter att servrar ansluter till Internet måste du kontrollera att alla Exchange-servrar har den proxyserver som definierats i egenskapen [InternetWebProxy.](https://technet.microsoft.com/library/bb123716%28v=exchg.160%29.aspx)

- **Exchange Server lokalt i en Office 365-hybridmiljö**

  - Om du använder Exchange Server 2013 måste minst en server ha serverrollerna Postlåda och Klientåtkomst installerad. Även om det är möjligt att installera rollerna Postlåda och Klientåtkomst på olika servrar rekommenderar vi starkt att du installerar båda rollerna på samma server för att ge ytterligare tillförlitlighet och bättre prestanda.
  - Om du använder Exchange Server 2016 eller senare måste minst en server ha serverrollen Postlåda installerad.
  - Det finns ingen Exchange-server 2007 eller 2010 i hybridmiljön.
  - Alla Exchange-servrar måste ha de senaste kumulativa uppdateringarna installerade. Se Uppgradera Exchange till de senaste [kumulativa uppdateringarna för](https://docs.microsoft.com/exchange/plan-and-deploy/install-cumulative-updates) att hitta och hantera alla tillgängliga uppdateringar.

- **Krav för Exchange-klient och -protokoll**

    Tillgängligheten för modern autentisering bestäms av kombinationen av klienten, protokollet och konfigurationen. Om modern autentisering inte stöds av klienten, protokollet och/eller konfigurationen fortsätter klienten att utnyttja äldre autentisering.
  
    Följande klienter och protokoll stöder modern autentisering med lokal Exchange när modern autentisering är aktiverad i miljön:

  |**Klienter**|**Primary Protocol**|**Kommentarer**|
  |:-----|:-----|:-----|
  |Outlook 2013 och senare  <br/> |MAPI över HTTP  <br/> |MAPI över HTTP måste vara aktiverat i Exchange för att kunna utnyttja modern autentisering med dessa klienter (vanligtvis aktiverat eller Sant för nya installationer av Exchange 2013 Service Pack 1 och högre). mer information finns i [Hur modern autentisering fungerar för Office 2013- och Office 2016-klientprogram.](modern-auth-for-office-2013-and-2016.md)  <br/> Se till att du kör den lägsta version som krävs av Outlook. se [de senaste uppdateringarna för versioner av Outlook som använder Windows Installer (MSI).](https://docs.microsoft.com/officeupdates/outlook-updates-msi)  <br/> |
  |Outlook 2016 för Mac och senare  <br/> |Exchange-webbtjänster  <br/> |  <br/> |
  |Outlook för iOS och Android  <br/> | Microsofts synkroniseringsteknik <br/> |Mer information [finns i Använda modern hybridautentisering med Outlook för iOS](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) och Android.  <br/> |
  |Exchange ActiveSync-klienter (t.ex. e-post i iOS11)  <br/> |Exchange ActiveSync  <br/> |För Exchange ActiveSync-klienter som stöder modern autentisering måste du återskapa profilen för att kunna växla från grundläggande autentisering till modern autentisering.  <br/> |

    Klienter och/eller protokoll som inte visas (t.ex. POP3) stöder inte modern autentisering med lokal Exchange och fortsätter att använda äldre autentiseringsmetoder även efter att modern autentisering har aktiverats i miljön.

- **Allmänna krav**
  - Resursskogsscenarier kräver tvåvägsförtroende med konto skog för att säkerställa att korrekt SID-uppslag utförs under hybrid modern autentiseringsbegäranden. 
  - Om du använder AD FS bör du ha Windows 2012 R2 AD FS 3.0 och högre för federation.
  - Dina identitetskonfigurationer är alla typer som stöds av Azure AD Connect, till exempel synkronisering av lösenordshashar, direktautentisering och lokal STS som stöds av Office 365.
  - Du har Azure AD Connect konfigurerat och fungerande för användarreplikering och synkronisering.
  - Du har kontrollerat att hybrid är konfigurerad med klassisk hybridtopologiläge i Exchange mellan din lokala miljö och Office 365-miljön. Officiellt supportmeddelande för Exchange-hybrid säger att du måste ha antingen aktuell CU eller aktuell CU - 1.
    > [!NOTE]
    > Modern hybridautentisering stöds inte med [hybridagenten.](https://docs.microsoft.com/exchange/hybrid-deployment/hybrid-agent)

  - Se till att både en testanvändare på plats och en hybridtestanvändare som finns i Office 365 kan logga in på Skype för företag-skrivbordsklienten (om du vill använda modern autentisering med Skype) och Microsoft Outlook (om du vill använda modern autentisering med Exchange).

## <a name="what-else-do-i-need-to-know-before-i-begin"></a>Vad mer behöver jag veta innan jag börjar?
<a name="BKMK_Whatelse"> </a>

- Alla scenarier för lokala servrar innebär att konfigurera modern autentisering lokalt (faktum är att för Skype för företag finns det en lista med topologier som stöds) så att den server som ansvarar för autentisering och auktorisering finns i Microsoft Cloud (Azure AD:s säkerhetstokentjänst, som kallas 'desTS') och uppdaterar Azure AD om URL:er eller namnområden som används av din lokala installation av antingen Skype för företag eller Exchange. Därför har lokala servrar ett Microsoft Cloud-beroende. Att vidta den här åtgärden kan vara att konfigurera "hybridauth".
- Den här artikeln länkar till andra som hjälper dig att välja modern autentiserings topologi som stöds (endast nödvändig för Skype för företag) och instruktioner för artiklar som beskriver konfigurationsstegen, eller anvisningar för att inaktivera modern autentisering, för lokal Exchange och skype för företag lokalt. Gör den här sidan till favorit i webbläsaren om du behöver en bas för att använda modern autentisering i servermiljön.

## <a name="related-topics"></a>Relaterade ämnen
<a name="BKMK_URLListforMA"> </a>

- [Så här konfigurerar Exchange Server lokal användning av modern autentisering](configure-exchange-server-for-hybrid-modern-authentication.md)
- [Topologier i Skype för företag som stöds med modern autentisering](https://technet.microsoft.com/library/mt803262.aspx)
- [Konfigurera lokal Skype för företag för användning av modern autentisering](configure-skype-for-business-for-hybrid-modern-authentication.md)
- [Ta bort eller inaktivera modern hybridautentisering från Skype för företag och Exchange](remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha.md)
