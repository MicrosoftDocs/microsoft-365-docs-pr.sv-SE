---
title: Microsoft Defender för slutpunkt på Mac
ms.reviewer: ''
description: Lär dig hur du installerar, konfigurerar, uppdaterar och använder Microsoft Defender för Slutpunkt på Mac.
keywords: microsoft, defender, Microsoft Defender för slutpunkt, mac, installation, distribuera, avinstallation, intune, jamf, macos, big sur, catalina, mojave, mde för mac
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 365fed8b5f7c7fc617ea068e324da541f7f1b187
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52301782"
---
# <a name="microsoft-defender-for-endpoint-on-mac"></a>Microsoft Defender för slutpunkt på Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

I det här avsnittet beskrivs hur du installerar, konfigurerar, uppdaterar och använder Defender för slutpunkt på Mac.

> [!CAUTION]
> Att köra andra slutpunktsskyddsprodukter från tredje part tillsammans med Microsoft Defender för Endpoint på Mac kan sannolikt leda till prestandaproblem och oförutsägbara sidoeffekter. Om skydd mot slutpunkter som inte är Microsoft är ett absolut krav i din miljö kan du fortfarande tryggt dra nytta av Defender för Endpoint på Mac Identifiering och åtgärd på slutpunkt när du har konfigurerat antivirusfunktionen så att den körs i [passivt läge.](mac-preferences.md#enable--disable-passive-mode)

## <a name="whats-new-in-the-latest-release"></a>Nyheter i den senaste versionen

[Senaste nytt i Microsoft Defender för Endpoint](whats-new-in-microsoft-defender-atp.md)

[Vad är nytt i Microsoft Defender för slutpunkt på Mac](mac-whatsnew.md)

> [!TIP]
> Om du har någon feedback som du vill dela kan du skicka in den genom att öppna Microsoft Defender för Slutpunkt på Mac på din enhet och navigera till **Hjälp med** att  >  **skicka feedback.**

Om du vill ha de senaste funktionerna, till exempel förhandsgranskningsfunktioner (till exempel identifiering och åtgärd på slutpunkt för dina Mac-enheter), konfigurerar du din macOS-enhet som kör Microsoft Defender för Endpoint till en "Insider"-enhet.

## <a name="how-to-install-microsoft-defender-for-endpoint-on-mac"></a>Så här installerar du Microsoft Defender för slutpunkt på Mac

### <a name="prerequisites"></a>Förutsättningar

- En Defender för Endpoint-prenumeration och åtkomst till Microsoft Defender Säkerhetscenter portalen
- Nybörjarupplevelse med macOS- och BASH-skript
- Administratörsbehörigheter på enheten (vid manuell distribution)

### <a name="installation-instructions"></a>Installationsanvisningar

Det finns flera metoder och distributionsverktyg som du kan använda för att installera och konfigurera Defender för Slutpunkt på Mac.

- Hanteringsverktyg från tredje part:
    - [Microsoft Intune-baserad distribution](mac-install-with-intune.md)
    - [JAMF-baserad distribution](mac-install-with-jamf.md)
    - [Andra MDM-produkter](mac-install-with-other-mdm.md)

- Kommandoradsverktyget:
    - [Manuell distribution](mac-install-manually.md)

### <a name="system-requirements"></a>Systemkrav

De tre senaste större versionerna av macOS stöds.

> [!IMPORTANT]
> På macOS 11 (Big Sur) kräver Microsoft Defender för Endpoint ytterligare konfigurationsprofiler. Om du redan är kund och uppgraderar från tidigare versioner av macOS distribuerar du de ytterligare konfigurationsprofiler som finns listade i Nya konfigurationsprofiler för [macOS Catalina](mac-sysext-policies.md)och nyare versioner av macOS.

> [!IMPORTANT]
> Stöd för macOS 10.13 (High Sierra) har upphört från och med den 15 februari 2021.

- 11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave)
- Diskutrymme: 1 GB

Betaversioner av macOS stöds inte.

MacOS-enheter med M1-processorer stöds inte.

När du har aktiverat tjänsten kan du behöva konfigurera nätverket eller brandväggen för att tillåta utgående anslutningar mellan den och dina slutpunkter.

### <a name="licensing-requirements"></a>Licensieringskrav

Microsoft Defender för Slutpunkt på Mac kräver något av följande Microsoft volymlicensieringserbjudanden:

- Microsoft 365 E5 (M365 E5)
- Microsoft 365 E5 Security
- Microsoft 365 A5 (M365 A5)
- Windows 10 Enterprise E5
- Microsoft Defender för Endpoint

> [!NOTE]
> Kvalificerade licensierade användare kan använda Microsoft Defender för Endpoint på upp till fem samtidiga enheter.
> Microsoft Defender för Endpoint kan också köpas från en microsoft Molnlösningsleverantör (CSP). När microsoft volymlicensieringserbjudandena listas för dem när de köps via en microsoft-moln moln

### <a name="network-connections"></a>Nätverksanslutningar

I följande nedladdningsbara kalkylblad finns de tjänster och deras tillhörande URL:er som nätverket måste kunna ansluta till. Du bör kontrollera att det inte finns några brandväggs- eller nätverksfiltreringsregler som nekar åtkomst till dessa URL:er, eller att du kan behöva skapa en *tillåta-regel* specifikt för dem.



|**Kalkylblad med domänlista**|**Beskrivning**|
|:-----|:-----|
|![Miniatyrbild för Microsoft Defender för slutpunkts-URL:er-kalkylblad](images/mdatp-urls.png)<br/>  | Kalkylblad med specifika DNS-poster för tjänstplatser, geografiska platser och operativsystem. <br><br>Ladda ned kalkylbladet här: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).

Microsoft Defender för Endpoint kan identifiera en proxyserver med hjälp av följande identifieringsmetoder:
- Autoconfig-proxy (PAC)
- Web Proxy Autodiscovery Protocol (WPAD)
- Manuell statisk proxykonfiguration

Om en proxy eller brandvägg blockerar anonym trafik kontrollerar du att anonym trafik tillåts i tidigare angivna URL:er.

> [!WARNING]
> Autentiserad proxy. Se till att endast PAC, WPAD eller en statisk proxy används.
>
> SSL-proxy proxy och skärningspunkt stöds inte heller av säkerhetsskäl. Konfigurera ett undantag för SSL-kontroll och proxyservern för att direkt överföra data från Microsoft Defender för Slutpunkt i macOS till relevanta URL:er utan avlyssning. Om du lägger till ditt certifikat för avlyssning i det globala lagret tillåts inte avlyssning.

Testa att en anslutning inte är blockerad genom att öppna [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) och [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) i en webbläsare.

Om du föredrar kommandoraden kan du också kontrollera anslutningen genom att köra följande kommando i Terminal:

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

Utdata från det här kommandot bör se ut ungefär så här:

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> Vi rekommenderar att du fortsätter att [ha System Integrity Protection](https://support.apple.com/en-us/HT204899) (SIP) aktiverat på klientenheter. SIP är en inbyggd säkerhetsfunktion i macOS som förhindrar att operativsystemet ändrar operativsystemet på låg nivå och är aktiverat som standard.

När Microsoft Defender för slutpunkt har installerats kan anslutningen verifieras genom att köra följande kommando i terminalen:
```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-on-mac"></a>Uppdatera Microsoft Defender för slutpunkt på Mac

Microsoft publicerar regelbundet programuppdateringar för att förbättra prestanda, säkerhet och för att leverera nya funktioner. För att uppdatera Microsoft Defender för Slutpunkt på Mac används ett program med namnet Microsoft AutoUpdate (MAU). Mer information finns i [Distribuera uppdateringar för Microsoft Defender för Slutpunkt på Mac.](mac-updates.md)

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-mac"></a>Konfigurera Microsoft Defender för slutpunkt på Mac

Anvisningar om hur du konfigurerar produkten i företagsmiljöer finns i Ange inställningar för [Microsoft Defender för slutpunkt på Mac.](mac-preferences.md)

## <a name="macos-kernel-and-system-extensions"></a>macOS kernel- och systemtillägg

I linje med macOS-utveckling förbereder vi en Microsoft Defender för slutpunkt på Mac-uppdatering som utnyttjar systemtillägg istället för kernel-tillägg. Mer information finns i [Vad är nytt i Microsoft Defender för Slutpunkt på Mac.](mac-whatsnew.md)

## <a name="resources"></a>Resurser

- Mer information om loggning, avinstallation eller andra ämnen finns i Resurser [för Microsoft Defender för slutpunkt på Mac.](mac-resources.md)

- [Sekretess för Microsoft Defender för Slutpunkt på Mac](mac-privacy.md).
