---
title: Hybrid modern verifierings översikt och förutsättningar för användning med lokala Skype för företag-och Exchange-servrar
ms.author: kvice
ms.reviewer: smithre4
author: kelleyvice-msft
manager: laurawi
ms.date: 04/15/2020
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
description: I den här artikeln får du lära dig om hybrid modern verifiering och förutsättningar för användning med lokala Skype för företag-och Exchange-servrar.
ms.openlocfilehash: 1e0330bd62d9098f11a12b44b46e9ace30b59420
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546450"
---
# <a name="hybrid-modern-authentication-overview-and-prerequisites-for-using-it-with-on-premises-skype-for-business-and-exchange-servers"></a>Hybrid modern verifierings översikt och förutsättningar för att använda den med lokala Skype för företag-och Exchange-servrar

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

_Modern autentisering_ är en metod för identitets hantering som erbjuder säkrare användarautentisering och verifiering. Den är tillgänglig för Office 365 Hybrid distributioner av Skype för företag-Server lokalt och Exchange Server lokalt, samt för delade domäner med Skype för företag-hybrider. Den här artikeln länkar till relaterade dokument om förutsättningar, konfiguration/inaktive ring av modern verifiering och till en del av den relaterade klienten (ex. Outlook-och Skype-klienter) information.

- [Vad är modern lösenordsautentisering?](hybrid-modern-auth-overview.md#BKMK_WhatisModAuth)
- [Vad ändras när jag använder modern lösenordsautentisering?](hybrid-modern-auth-overview.md#BKMK_WhatChanges)
- [Kontrol lera modern status för den lokala miljön](hybrid-modern-auth-overview.md#BKMK_CheckStatus)
- [Möter du moderna verifierings krav?](#do-you-meet-modern-authentication-prerequisites)
- [Behöver jag veta något mer innan jag börjar?](hybrid-modern-auth-overview.md#BKMK_Whatelse)

## <a name="what-is-modern-authentication"></a>Vad är modern lösenordsautentisering?
<a name="BKMK_WhatisModAuth"> </a>

Modern autentisering är en parasoll för en kombination av autentiserings-och auktoriseringsregler mellan en klient (till exempel din bärbara dator eller din telefon) och en server samt vissa säkerhets åtgärder som kräver åtkomst principer som du kanske redan är bekant med. Det innehåller:

- **Autentiseringsmetoder**: MULTIFAKTORAUTENTISERING (MFA); Smart Card-identifiering; klient certifikat-baserad verifikation
- **Auktoriseringsregler**: Microsofts implementering av Open Authorization (OAuth)
- **Villkor för villkorsstyrd åtkomst**: villkorlig åtkomst för Mam (Mobile Application Management) och Azure Active Directory (Azure AD)

Om du hanterar användar identiteter med modern verifikation får administratörer många olika verktyg som du kan använda när de kommer att skydda resurser och erbjuder säkrare metoder för identitets hantering till både lokala (Exchange-och Skype för företag), Exchange-hybrider och Skype för företag hybrid/delade domän scenarier.

Tänk på att eftersom Skype för företag fungerar tätt med Exchange kommer användar beteendet för Skype för företag-klienter att påverkas av modern status för Exchange. Detta gäller även om du har en hybrid arkitektur för Skype för företag, som du använder för både Skype för företag _–_ online och Skype för företag, med användare som har Home på båda platserna.

Mer information om modern auktorisering i Office 365 finns i [Support för office 365-appen-modern-verifikation](microsoft-365-client-support-modern-authentication.md).

> [!IMPORTANT]
> Från och med augusti 2017 har alla nya Office 365-klient organisationer som har Skype för företag – Online och Exchange Online aktiverat modern autentisering som standard. Befintliga klient organisationer har ingen ändring i standard läget MA, men alla nya klient organisationer stöder automatiskt den utökade uppsättning med identitets funktioner som visas ovan. Om du vill kontrol lera MA-status läser du den [moderna autentiseringsinställningarna för den lokala miljö](hybrid-modern-auth-overview.md#BKMK_CheckStatus) avdelningen.

## <a name="what-changes-when-i-use-modern-authentication"></a>Vad ändras när jag använder modern lösenordsautentisering?
<a name="BKMK_WhatChanges"> </a>

När du använder modern autentisering med lokala Skype för företag eller Exchange Server *verifierar* du fortfarande lokala användare, men artikeln om att *auktorisera* åtkomsten till resurser (som filer eller e-post) ändras. Det här är orsaken, men modern autentisering gäller för klient-och server kommunikation, de åtgärder som vidtas vid konfigurering av MA-resultat i evoSTS (en säkerhetstokentjänst som används av Azure AD) anges som auth Server för Skype för företag och Exchange Server lokalt.

Ändringen av evoSTS gör att dina lokala servrar kan utnyttja OAuth (token-utgivning) för att auktorisera klienterna och även tillåta dina lokala säkerhets metoder i molnet (som multifaktorautentisering). Dessutom utfärdar evoSTS de token som gör att användare kan begära åtkomst till resurser utan att ange deras lösen ord som en del av begäran. Det spelar ingen roll var användarna är anslutna (online eller lokalt), och oavsett vilken plats som är värd för den resurs som krävs, kommer EvoSTS att bli den grundläggande delen av att auktorisera användare och klienter när modern autentisering har kon figurer ATS.

Om till exempel en Skype för företag-klient behöver komma åt Exchange Server för att få kalender information för en användares räkning använder den Active Directory-autentiseringsschemat (ADAL) för att göra det. ADAL är ett kod bibliotek som är utformat för att göra skyddade resurser i katalogen tillgängliga för klient program som använder OAuth-säkerhetstoken. ADAL fungerar med OAuth för att verifiera anspråk och till Exchange-token (istället för lösen ord) för att ge en användare åtkomst till en resurs. Förr i tiden har myndigheten i en transaktion som den här en--server som känner till hur man verifierar användar anspråk och utfärdar de nödvändiga tokens--tjänsten (Security Token Service) eller ens Active Directory Federation Services. Men den här funktionen centraliserar modern användning av Azure AD.

Det innebär också att även om Exchange-servern och Skype för företag-miljön kanske är lokalt, är den auktoriserade servern online och den lokala miljön måste kunna skapa och underhålla en anslutning till din Office 365-prenumeration i molnet (och den Azure AD-instans som din prenumeration använder som katalog).

Vad är inte ändrat? Oavsett om du befinner dig i en delad domän hybrid eller använder Skype för företag och Exchange Server lokalt måste alla användare först verifiera *lokala*. I en hybrid implementering av modern inloggningsautentisering kan _Lyncdiscovery_ och _Autodiscover_ båda peka på den lokala servern.

> [!IMPORTANT]
> Om du behöver veta de specifika topologierna för Skype för företag med MA är det [dokumenterat här](https://technet.microsoft.com/library/mt803262.aspx).

## <a name="check-the-modern-authentication-status-of-your-on-premises-environment"></a>Kontrol lera modern status för den lokala miljön
<a name="BKMK_CheckStatus"> </a>

Eftersom modern autentisering ändrar den auktoriseringsprincip som används när tjänster utnyttjar OAuth/S2S, måste du veta om modern autentisering är aktive rad eller inaktiv för dina lokala Skype för företag-och Exchange-miljöer. Du kan kontrol lera statusen på dina Exchange-servrar genom att köra följande PowerShell-kommando:

```powershell
Get-OrganizationConfig | ft OAuth*
```

Om värdet för egenskapen _OAuth2ClientProfileEnabled_ är **false**är modern verifikation inaktive rad.

Mer information om cmdleten Get-OrganizationConfig finns i [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).

Du kan kontrol lera dina Skype för företag-servrar genom att köra följande PowerShell-kommando:

```powershell
Get-CSOAuthConfiguration
```

Om kommandot returnerar en tom _OAuthServers_ -egenskap, eller om värdet för egenskapen _ClientADALAuthOverride_ inte **tillåts**, är modern verifikation inaktive rad.

Mer information om cmdleten Get-CsOAuthConfiguration finns i [Get-CsOAuthConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csoauthconfiguration).

## <a name="do-you-meet-modern-authentication-prerequisites"></a>Möter du moderna verifierings krav?

Kontrol lera och kontrol lera dessa objekt i listan innan du fortsätter:

- **Skype för företag – specifikt**
  - Alla servrar måste ha 2017 Cumulative Update (CU5) för Skype för företag – Server 2015 eller senare
    - **Exception** -SBA (efterlevande) kan finnas i den aktuella versionen (baserat på Lync 2013)
  - Din SIP-domän läggs till som en federerad domän i Office 365
  - Alla SFB frontend-enheter måste ha anslutningar som är utgående till Internet, till Office 365-URL: er (TCP 443) och välkända certifikat rot listor (TCP 80) som visas i raderna 56 och 125 i avsnittet "Microsoft 365 common och Office" i [Office URL-adresser och IP-adressintervall](urls-and-ip-address-ranges.md).

- **Skype för företag – lokalt i en hybrid Office 365-miljö**
  - En distribution av Skype för företag – Server 2019 med alla servrar som kör Skype för företag – Server 2019.
  - En distribution av Skype för företag – Server 2015 med alla servrar som kör Skype för företag – Server 2015.
  - En distribution med maximalt två olika Server versioner enligt nedan:
    - Skype för företag – Server 2015
    - Skype för företag – Server 2019
  - Alla Skype för företag-servrar måste ha de senaste kumulativa uppdateringarna installerade, se [uppdateringar för Skype för företag – Server](https://docs.microsoft.com/skypeforbusiness/sfb-server-updates) för att hitta och hantera alla tillgängliga uppdateringar.
  - Det finns inga Lync Server 2010 eller 2013 i hybrid miljön.

>[!NOTE]
>Om dina Skype för företag-frontend-servrar använder en proxyserver för Internet åtkomst måste den IP-adress och det port nummer som används anges i konfigurations delen av web.config filen för varje klient.

- C:\Program Files\Skype for Business Server 2015 \ webb Components\Web ticket\int\web.config
- C:\Program Files\Skype for Business Server 2015 \ webb Components\Web ticket\ext\web.config

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
> Se till att du abonnerar på RSS-feeden för [Office 365 URL-adresser och IP-adressintervall](urls-and-ip-address-ranges.md) för att hålla sig uppdaterade med de senaste tablåerna av obligatoriska webb adresser.

- **Exchange Server specifikt**
  - Du använder antingen Exchange Server 2013 CU19 och up, Exchange Server 2016 CU8 och up eller Exchange Server 2019 CU1 och upp.
  - Det finns ingen Exchange Server 2010 i miljön.
  - SSL-avläsning är inte konfigurerat. SSL-terminering och omkryptering stöds.
  - I händelse av att din miljö använder en proxyserver för att tillåta servrar att ansluta till Internet bör du kontrol lera att alla Exchange-servrar har den proxyserver som är angiven i egenskapen [InternetWebProxy](https://technet.microsoft.com/library/bb123716%28v=exchg.160%29.aspx) .

- **Exchange Server lokalt i en hybrid Office 365-miljö**

  - Om du använder Exchange Server 2013, måste minst en server ha installerat server för post lådor och klient åtkomst. Det går att installera rollerna post låda och klient åtkomst på separata servrar, men vi rekommenderar starkt att du installerar båda rollerna på samma server för att ge ytterligare pålitlighet och bättre prestanda.
  - Om du använder Exchange Server 2016 eller senare version måste Server rollen för post lådan vara installerad på minst en server.
  - Det finns ingen Exchange Server 2007 eller 2010 i hybrid miljön.
  - Alla Exchange-servrar måste ha de senaste kumulativa uppdateringarna installerade, se [Uppgradera Exchange till de senaste kumulativa uppdateringarna](https://docs.microsoft.com/exchange/plan-and-deploy/install-cumulative-updates?view=exchserver-2019) för att hitta och hantera alla tillgängliga uppdateringar.

- **Krav för Exchange-klient och-protokoll**

  - Följande klienter har stöd för modern inloggningsautentisering:

  |**Förvirra**|**Primärt protokoll**|**Kommentarer**|
  |:-----|:-----|:-----|
  |Outlook 2013 och Outlook 2016  <br/> |MAPI via HTTP  <br/> |MAPI via HTTP måste aktive ras i Exchange för att det ska vara en modern dator med dessa klienter (vanligt vis aktiverat eller sant för nya installationer av Exchange 2013 Service Pack 1 och senare); Mer information finns i [så här fungerar modern inloggningsautentisering för office 2013-och Office 2016-klient program](modern-auth-for-office-2013-and-2016.md).  <br/> Kontrol lera att du använder den minsta nödvändiga versionen av Outlook; Se de [senaste uppdateringarna för versioner av Outlook som använder Windows installations program (MSI)](https://docs.microsoft.com/officeupdates/outlook-updates-msi).  <br/> |
  |Outlook 2016 för Mac  <br/> |Exchange-webbtjänster  <br/> |  <br/> |
  |Outlook för iOS och Android  <br/> |  <br/> |Mer information finns i [använda hybrid modern med Outlook för iOS och Android](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) .  <br/> |
  |Exchange ActiveSync-klienter (till exempel iOS11 e-post)  <br/> |Exchange ActiveSync  <br/> |För Exchange ActiveSync-klienter som har stöd för modern inloggning måste du återskapa profilen för att kunna växla från grundläggande verifikation till modern.  <br/> |

- **Allmänna förutsättningar**
  - Om du använder AD FS bör du ha Windows 2012 R2 AD FS 3,0 och högre för federation.
  - Dina identitets konfigurationer är en av de typer som stöds av Azure AD Connect, till exempel lösen ord för hash-synkronisering, vidarekoppling och lokal STS som stöds av Office 365.
  - Du har konfigurerat Azure AD Connect och fungerar för användarautentisering och synkronisering.
  - Du har kontrollerat att Hybrid är konfigurerat med hjälp av läget för Exchange klassisk hybrid topologi mellan din lokala och Office 365-miljö. Officiell support policy för Exchange-hybrid säger att du måste ha antingen aktuellt CU eller aktuellt CU-1.
    > [!NOTE]
    > Hybrid modern inloggningsautentisering stöds inte med [hybrid agenten](https://docs.microsoft.com/exchange/hybrid-deployment/hybrid-agent).

  - Se till att både en lokal test användare och en hybrid test användare i Office 365 kan logga in på Skype för företag-datorn (om du vill använda modern auktorisering med Skype) och Microsoft Outlook (om du vill använda modern-auktorisering med Exchange).

## <a name="what-else-do-i-need-to-know-before-i-begin"></a>Behöver jag veta något mer innan jag börjar?
<a name="BKMK_Whatelse"> </a>

- Alla scenarier för lokala servrar är bland annat att konfigurera modern lokal inloggning (i själva verket för Skype för företag finns det en lista över topologier som stöds, så att den server som ansvarar för autentisering och godkännande finns i Microsofts moln (Azure AD-säkerhetstokentjänsten, som heter ' evoSTS ') och uppdaterar Azure AD angående de URL-adresser eller namn områden som används av din lokala installation av antingen Skype för företag eller Exchange. Därför tar lokala servrar ett Microsoft-moln beroende. Att vidta den här åtgärden kan överväga att konfigurera "hybrid auth".
- Den här artikeln länkar ut till andra som hjälper dig att välja moderna autentiseringsmetoder (endast för Skype för företag) och instruktioner om hur du gör för att göra det, eller hur du inaktiverar modern behörighet, för Exchange lokalt och Skype för företag. Favorit den här sidan i din webbläsare om du vill ha en start bas för modern lösenordsautentisering i din server miljö.

## <a name="related-topics"></a>Relaterade ämnen
<a name="BKMK_URLListforMA"> </a>

- [Konfigurera Exchange Server lokalt för användning av modern](configure-exchange-server-for-hybrid-modern-authentication.md)
- [Topologier för Skype för företag med modern lösenordsautentisering](https://technet.microsoft.com/library/mt803262.aspx)
- [Konfigurera Skype för företag-lokal att använda modern](configure-skype-for-business-for-hybrid-modern-authentication.md)
- [Ta bort eller inaktivera Hybrid från Skype för företag och Exchange](remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha.md)
