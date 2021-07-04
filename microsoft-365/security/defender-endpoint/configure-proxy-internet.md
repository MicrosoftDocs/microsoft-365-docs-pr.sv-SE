---
title: Konfigurera enhetsproxy och internetanslutningsinställningar
description: Konfigurera Microsoft Defender för slutpunktsproxy och Internetinställningar för att aktivera kommunikation med molntjänsten.
keywords: konfigurera, proxy, internet, internetanslutning, inställningar, proxyinställningar, netsh, winhttp, proxyserver
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: af50e3c2a6db1a09d546bfa06b26c80dcf4481e5
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290093"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Konfigurera enhetsproxy och internetanslutningsinställningar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

Defender för slutpunkts sensor kräver Microsoft Windows HTTP (WinHTTP) för att rapportera sensordata och kommunicera med Defender för slutpunktstjänsten.

Den inbäddade Defender för slutpunkts sensor körs i systemkontext med localSystem-kontot. Sensorn använder Microsoft Windows HTTP-tjänster (WinHTTP) för att aktivera kommunikation med Defender för slutpunktsmolntjänsten.

> [!TIP]
> Organisationer som använder proxyservrar för vidarebefordran som en gateway till Internet, kan använda nätverksskydd till undersökningar bakom en proxy. Mer information finns i [Undersöka anslutningshändelser som inträffar bakom proxyservrar för vidarebefordran](investigate-behind-proxy.md).

WinHTTP-konfigurationsinställningen är oberoende av proxyinställningarna för Internetsurfning på Windows Internet (WinINet) på Internet och kan bara identifiera en proxyserver med hjälp av följande identifieringsmetoder:

- Metoder för automatisk identifiering:

  - Transparent proxy

  - WPAD (Web Proxy Auto-discovery Protocol)

    > [!NOTE]
    > Om du använder Transparent proxy eller WPAD i nätverkstopologin behöver du inga särskilda konfigurationsinställningar. Mer information om undantag för Slutpunkts-URL för Defender i proxyn finns i Aktivera åtkomst till Defender för [slutpunktstjänst-URL:er i proxyservern.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)

- Manuell konfiguration av statisk proxy:

  - Registerbaserad konfiguration

  - WinHTTP som är konfigurerat med ett netsh-kommando – Endast lämpligt för stationära datorer i en stabil topologi (t.ex. en stationär dator i ett företagsnätverk bakom samma proxy)

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>Konfigurera proxyservern manuellt med hjälp av en registerbaserad statisk proxy

Konfigurera en registerbaserad statisk proxy så att endast Defender för slutpunkts sensor kan rapportera diagnostikdata och kommunicera med Defender för Slutpunktstjänster om en dator inte har tillåtelse att ansluta till Internet.

> [!NOTE]
> När du använder det här alternativet på Windows 10 eller Windows Server 2019 rekommenderas du att ha följande (eller senare) samlad uppdatering och kumulativ uppdatering:
>
> - Windows 10 version 1809 eller Windows Server 2019 –https://support.microsoft.com/kb/5001384
> - Windows 10, version 1909 -https://support.microsoft.com/kb/4601380
> - Windows 10, version 2004 –https://support.microsoft.com/kb/4601382
> - Windows 10, version 20H2 -https://support.microsoft.com/kb/4601382
>
> Dessa uppdateringar förbättrar anslutningen och tillförlitligheten för CnC-kanalen (kommando- och kontrollkanal).

Den statiska proxyn kan konfigureras via en grupprincip. Grupprincipen finns under:

- **Administrativa mallar > Windows komponenter > datainsamlings- och förhandsversioner > Konfigurera autentiserad proxyanvändning för den anslutna användarupplevelsen och telemetritjänsten**

  Ställ in den **på Aktiverad** och välj **Inaktivera autentiserad proxyanvändning.**

  ![Bild av grupprincipinställning1](images/atp-gpo-proxy1.png)

- **Administrativa mallar > Windows komponenter > datainsamlings- och förhandsversioner > Konfigurera anslutna användarupplevelser och telemetri:**

  Konfigurera proxyn

  ![Bild av grupprincipinställning2](images/atp-gpo-proxy2.png)

  Principen anger två registervärden, `TelemetryProxyServer` som REG_SZ och som `DisableEnterpriseAuthProxy` REG_DWORD, under registernyckeln `HKLM\Software\Policies\Microsoft\Windows\DataCollection` .

  Registervärdet `TelemetryProxyServer` har följande strängformat:

  ```text
  <server name or ip>:<port>
  ```

  Till exempel: 10.0.0.6:8080

  Registervärdet `DisableEnterpriseAuthProxy` anges till 1.

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a>Konfigurera proxyservern manuellt med netsh-kommandot

Använd netsh för att konfigurera en systemomfattande statisk proxy.

> [!NOTE]
>
> - Detta påverkar alla program, inklusive Windows-tjänster som använder WinHTTP med standardproxyn.</br>
> - Bärbara datorer som ändrar topologi (till exempel från kontor till hem) fungerar inte på netsh. Använd den registerbaserade statiska proxykonfigurationen.

1. Öppna en upphöjd kommandorad:

   1. Gå till **Start** och skriv **cmd**.

   1. Högerklicka på **Kommandotolken** och välj **Kör som administratör**.

2. Skriv följande kommando och tryck på **Retur**:

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   Till exempel: `netsh winhttp set proxy 10.0.0.6:8080`

Återställ winhttp-proxyn genom att ange följande kommando och trycka på **Retur**:

```PowerShell
netsh winhttp reset proxy
```

Se [Netsh-kommandosyntax, kontexter och formatering](/windows-server/networking/technologies/netsh/netsh-contexts) för mer information.

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a>Aktivera åtkomst till URL-adresser för Microsoft Defender för slutpunktstjänsten på proxyservern

Om en proxy eller brandvägg blockerar all trafik som standard och endast tillåter vissa domäner, lägger du till domänerna som visas på det nedladdningsbara bladet i listan med tillåtna domäner.

I följande nedladdningsbara kalkylblad finns de tjänster och deras tillhörande URL:er som nätverket måste kunna ansluta till. Du bör kontrollera att det inte finns några brandväggs- eller nätverksfiltreringsregler som nekar åtkomst till dessa URL:er, eller att du kan behöva skapa en *tillåta-regel* specifikt för dem.

| Kalkylblad med domänlista | Beskrivning |
|:-----|:-----|
|![Miniatyrbild för Microsoft Defender för slutpunkts-URL:er-kalkylblad](images/mdatp-urls.png)<br/>  | Kalkylblad med specifika DNS-poster för tjänstplatser, geografiska platser och operativsystem. <br><br>[Ladda ned kalkylbladet här.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

Om en proxy eller brandvägg har HTTPS-skanning (SSL-inspektion) aktiverad, utesluter du domänerna som visas i tabellen ovan från HTTPS-skanningen.

> [!NOTE]
> settings-win.data.microsoft.com bara om du har en Windows 10 som kör version 1803 eller tidigare.<br>
>
> URL-adresser som innehåller v20 i dem behövs bara om du har Windows 10 enheter med version 1803 eller senare. For example, `us-v20.events.data.microsoft.com` is needed for a Windows 10 device running version 1803 or later and onboarded to US Data Storage region.
>
> Om du använder Microsoft Defender Antivirus i din miljö kan du [gå till Konfigurera nätverksanslutningar till Microsoft Defender Antivirus molntjänsten.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)

Om en proxy eller brandvägg blockerar anonym trafik, som Defender för Slutpunkts sensor ansluter från systemkontext, kontrollerar du att anonym trafik tillåts i tidigare angivna URL:er.

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a>Microsoft Monitoring Agent (MMA) – proxy- och brandväggskrav för äldre versioner Windows klient eller Windows Server

Informationen nedan innehåller den konfigurationsinformation för proxy och brandvägg som krävs för att kommunicera med loganalysagenten (kallas ofta Microsoft monitoring agent) för tidigare versioner av Windows, till exempel Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2 och Windows Server 2016.

|Agentreurs|Portar |Riktning |Kringgå HTTPS-inspektion|
|------|---------|--------|--------|
|*.ods.opinsights.azure.com |Port 443 |Utgående|Ja |  
|*.oms.opinsights.azure.com |Port 443 |Utgående|Ja |  
|*.blob.core.windows.net |Port 443 |Utgående|Ja |
|*.azure-automation.net |Port 443 |Utgående|Ja |  

> [!NOTE]
> Som en molnbaserad lösning kan IP-intervallet ändras. Vi rekommenderar att du går över till DNS-lösningsinställningen.

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a>Bekräfta URL-krav för Tjänst-URL för Microsoft Monitoring Agent (MMA) 

Läs följande vägledning för att ta bort jokertecknet (*) för din specifika miljö när du använder Microsoft Monitoring Agent (MMA) för tidigare versioner av Windows.

1. Introducera ett tidigare operativsystem med Microsoft Monitoring Agent (MMA) i Defender för Slutpunkt (mer information finns i Hantera tidigare versioner av [Windows på Defender](https://go.microsoft.com/fwlink/p/?linkid=2010326) för slutpunkt och onboard [Windows-servrar](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).

2. Kontrollera att datorn rapporterar till Microsoft Defender Säkerhetscenter portalen.

3. Kör verktyget TestCloudConnection.exe C:\Program\Microsoft Monitoring Agent\Agent" för att verifiera anslutningen och visa de URL-adresser som krävs för den specifika arbetsytan.

4. Titta i listan med URL-adresser för Microsoft Defender för slutpunkten för en fullständig lista över krav för din region (mer information finns i [Tjänstwebbadresser för kalkylblad](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).

    ![Bild av administratör i Windows PowerShell](images/admin-powershell.png)

De jokertecken ( ) som används i URL-slutpunkterna för .ods.opinsights.azure.com, .oms.opinsights.azure.com och .agentsvc.azure-automation.net kan ersättas med ditt \* \* specifika \* \* Arbetsyte-ID. Arbetsyte-ID:t är specifikt för din miljö och arbetsyta och finns i avsnittet Registrering för klientorganisationen i Microsoft Defender Säkerhetscenter portal.

URL-slutpunkten .blob.core.windows.net kan ersättas med URL:erna som visas i \* avsnittet "Brandväggsregel: \* .blob.core.windows.net" i testresultaten.

> [!NOTE]
> När det gäller registrering via Azure Defender kan flera arbetsytor användas. Du måste utföra TestCloudConnection.exe ovan på en inbyggd dator från varje arbetsyta (för att avgöra om det finns några ändringar i URL blob.core.windows.net adresserna mellan arbetsytorna).

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a>Verifiera klientanslutningen till URL-adresser för Microsoft Defender för slutpunktstjänsten

Verifiera att proxykonfigurationen har slutförts, att WinHTTP kan identifiera och kommunicera via proxyservern i din miljö och att proxyservern tillåter trafik till URL:erna för Defender för Endpoint-tjänsten.

1. Ladda ned [verktyget MDATP-klientanalys till](https://aka.ms/mdatpanalyzer) den dator där Defender för slutpunkts sensor körs på.

2. Extrahera innehållet i MDATPClientAnalyzer.zip på enheten.

3. Öppna en upphöjd kommandorad:

   1. Gå till **Start** och skriv **cmd**.

   1. Högerklicka på **Kommandotolken** och välj **Kör som administratör**.

4. Skriv följande kommando och tryck på **Retur**:

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    Ersätt *HardDrivePath* med sökvägen dit verktyget MDATPClientAnalyzer laddades ned till, till exempel:

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. Extrahera den *MDATPClientAnalyzerResult.zip* som skapats av verktyget i mappen som används i *HardDrivePath.*

6. Öppna *MDATPClientAnalyzerResult.txt* och kontrollera att du har utfört proxykonfigurationsstegen som aktiverar serveridentifiering och åtkomst till tjänstens URL:er.

   Verktyget kontrollerar anslutningen av URL:erna för Defender för Endpoint-tjänsten som Defender för Endpoint-klienten har konfigurerats att interagera med. Resultatet skrivs sedan i filen *MDATPClientAnalyzerResult.txt* för varje URL som kan användas till att kommunicera med Defender för Endpoint-tjänsterna. Till exempel:

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

Om minst ett av anslutningsalternativen returnerar en status (200) kan Defender för Endpoint-klienten kommunicera med den testade URL:en med anslutningsmetoden.

Men om anslutningskontrollens resultat anger att ett fel uppstod, visas ett HTTP-fel (se HTTP-statuskoder). Du kan sedan använda URL:erna i tabellen som visas i Aktivera åtkomst till Defender för [slutpunktstjänst-URL:er i proxyservern.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server) Vilka URL-adresser du använder beror på vilken region du valde under registreringsprocessen.

> [!NOTE]
> Verktyget Connectivity Analyzer är inte kompatibelt med ASR-regeln [Blockera processer som skapas från PSExec- och WMI-kommandon](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules). Du måste inaktivera regeln tillfälligt om du vill köra anslutningsverktyget.
>
> När telemetriproxyServer har angetts i registret eller via grupprincip hamnar Defender för Slutpunkt direkt om den inte har åtkomst till den definierade proxyn.

## <a name="related-topics"></a>Relaterade ämnen

- [Registrera Windows 10-enheter](configure-endpoints.md)
- [Felsöka problem med Introduktion till Slutpunkt för Microsoft Defender](troubleshoot-onboarding.md)
