---
title: Konfigurera enhetsproxy och internetanslutningsinställningar
description: Konfigurera Microsoft Defender ATP-proxy- och Internetinställningar för att aktivera kommunikation med molntjänsten.
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
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ce8599556b1d0c8efbd020d525b30ed2cedaa9cb
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165471"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Konfigurera enhetsproxy och internetanslutningsinställningar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

Defender för slutpunkts sensor kräver Microsoft Windows HTTP (WinHTTP) för att rapportera sensordata och kommunicera med Defender för slutpunktstjänsten.

Den inbäddade Defender för slutpunkts sensor körs i systemkontext med localSystem-kontot. Sensorn använder Microsoft Windows HTTP Services (WinHTTP) för att aktivera kommunikation med Defender för molntjänsten Endpoint.

>[!TIP]
>För organisationer som använder proxyservrar som en gateway till Internet kan du använda nätverksskydd och undersöka bakom en proxy. Mer information finns i Undersöka [anslutningshändelser som inträffar bakom proxy proxy.](investigate-behind-proxy.md)

WinHTTP-konfigurationsinställningen är oberoende av proxyinställningarna för Internetsurfning på Windows Internet (WinINet) och kan bara identifiera en proxyserver med hjälp av följande identifieringsmetoder:

- Metoder för automatisk identifiering:
  - Transparent proxy
  - Web Proxy Auto-discovery Protocol (WPAD)

    > [!NOTE]
    > Om du använder Transparent proxy eller WPAD i nätverkstopologin behöver du inga särskilda konfigurationsinställningar. Mer information om undantag för Slutpunkts-URL för Defender i proxyn finns i Aktivera åtkomst till Defender för [slutpunktstjänst-URL:er i proxyservern.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)

- Manuell statisk proxykonfiguration:
  - Registerbaserad konfiguration
  - WinHTTP som konfigurerats med netsh-kommandot – endast lämpligt för stationära datorer i en stabil topologi (till exempel: ett skrivbord i ett företagsnätverk bakom samma proxy)

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>Konfigurera proxyservern manuellt med hjälp av en registerbaserad statisk proxyserver

Konfigurera en registerbaserad statisk proxy så att endast Defender för slutpunkts sensor kan rapportera diagnostikdata och kommunicera med Defender för Slutpunktstjänster om en dator inte har tillåtelse att ansluta till Internet.

Den statiska proxyn kan konfigureras via grupprincip (GP). Grupprincipen hittar du under:

- Administrativa mallar > Windows-komponenter > datainsamlings- och förhandsversioner > Konfigurera autentiserad proxyanvändning för den anslutna användarupplevelsen och telemetritjänsten
  - Ställ in den **på Aktiverad** och välj **Inaktivera autentiserad proxyanvändning:** ![ Bild på grupprincipinställning1](images/atp-gpo-proxy1.png)
- **Administrativa mallar > Windows-komponenter > datainsamlings- och förhandsversioner > Konfigurera anslutna användarupplevelser och telemetri:**
  - Konfigurera proxyn:<br>
    ![Bild av grupprincipinställning2](images/atp-gpo-proxy2.png)

    Principen anger två registervärden `TelemetryProxyServer` som REG_SZ och REG_DWORD `DisableEnterpriseAuthProxy` registernyckeln `HKLM\Software\Policies\Microsoft\Windows\DataCollection` .

    Registervärdet `TelemetryProxyServer` har följande strängformat:

    ```text
    <server name or ip>:<port>
    ```

    Till exempel: 10.0.0.6:8080

    Registervärdet `DisableEnterpriseAuthProxy` ska vara 1.

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a>Konfigurera proxyservern manuellt med netsh-kommandot

Använd netsh för att konfigurera en systemomfattande statisk proxy.

> [!NOTE]
> - Detta påverkar alla program, inklusive Windows-tjänster som använder WinHTTP med standardproxy.</br>
> - Bärbara datorer som ändrar topologi (till exempel från kontor till hem) fungerar inte på netsh. Använd den registerbaserade statiska proxykonfigurationen.

1. Öppna en upphöjd kommandorad:

    a. Gå till **Start** och skriv **cmd**.

    b. Högerklicka på **Kommandotolk** och välj **Kör som administratör.**

2. Ange följande kommando och tryck på **Retur:**

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   Till exempel: netsh winhttp set proxy 10.0.0.6:8080

Om du vill återställa winhttp proxy, ange följande kommando och tryck på **Retur**

```PowerShell
netsh winhttp reset proxy
```

Mer [information finns i Netsh-kommandosyntax,](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts) sammanhang och formatering.

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a>Aktivera åtkomst till URL-adresser för Microsoft Defender för slutpunktstjänsten på proxyservern

Om en proxy eller brandvägg blockerar all trafik som standard och bara tillåter specifika domäner genom, lägger du till de domäner som visas i det nedladdningsbara bladet i listan med tillåtna domäner.

I följande nedladdningsbara kalkylblad finns de tjänster och deras tillhörande URL:er som nätverket måste kunna ansluta till. Du bör kontrollera att det inte finns några brandväggs- eller nätverksfiltreringsregler som nekar åtkomst till dessa URL:er, eller att du kan behöva skapa en *tillåta-regel* specifikt för dem.


|**Kalkylblad med domänlista**|**Beskrivning**|
|:-----|:-----|
|![Miniatyrbild för Microsoft Defender för slutpunkts-URL:er-kalkylblad](images/mdatp-urls.png)<br/>  | Kalkylblad med specifika DNS-poster för tjänstplatser, geografiska platser och operativsystem. <br><br>[Ladda ned kalkylbladet här.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


Om https-skanning (SSL-skanning) är aktiverat för en proxy eller brandvägg ska du utesluta domäner som listas i tabellen ovan från HTTPS-skanning.

> [!NOTE]
> settings-win.data.microsoft.com bara om du har Windows 10-enheter med version 1803 eller tidigare.<br>


> [!NOTE]
> URL-adresser som innehåller v20 i dem behövs bara om du har Windows 10-enheter med version 1803 eller senare. Du behöver till ```us-v20.events.data.microsoft.com``` exempel en Windows 10-enhet med version 1803 eller senare och förs in i området för datalagring i USA.


> [!NOTE]
> Om du använder Microsoft Defender Antivirus i din miljö kan du gå [till Konfigurera nätverksanslutningar till molntjänsten Microsoft Defender Antivirus.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)

Om en proxy eller brandvägg blockerar anonym trafik, som Defender för Slutpunkts sensor ansluter från systemkontext, kontrollerar du att anonym trafik tillåts i tidigare angivna URL:er.

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a>Microsoft Monitoring Agent (MMA) – proxy- och brandväggskrav för äldre versioner av Windows-klienten eller Windows Server

I informationen nedan visas den konfigurationsinformation för proxy och brandvägg som krävs för att kommunicera med loganalysagenten (kallas ofta Microsoft monitoring agent) för tidigare versioner av Windows, till exempel Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2 och Windows Server 2016.

|Agentresurs|Portar |Riktning |Förbikoppling av HTTPS-kontroll|
|------|---------|--------|--------|   
|*.ods.opinsights.azure.com |Port 443 |Utgående|Ja |  
|*.oms.opinsights.azure.com |Port 443 |Utgående|Ja |  
|*.blob.core.windows.net |Port 443 |Utgående|Ja |
|*.azure-automation.net |Port 443 |Utgående|Ja |  


> [!NOTE]
> Som en molnbaserad lösning kan IP-intervallet ändras. Vi rekommenderar att du går över till DNS-lösningsinställningen.

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a>Bekräfta URL-krav för Tjänst-URL för Microsoft Monitoring Agent (MMA) 

Läs följande vägledning för att ta bort jokertecknet (*) för din specifika miljö när du använder Microsoft Monitoring Agent (MMA) för tidigare versioner av Windows.

1.  Introducera ett tidigare operativsystem med Microsoft Monitoring Agent (MMA) i Defender för slutpunkt (mer information finns i Hantera tidigare versioner av Windows på [Defender](https://go.microsoft.com/fwlink/p/?linkid=2010326) för slutpunkt och Onboard [Windows-servrar.](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)

2.  Kontrollera att datorn rapporterar till Microsoft Defender Säkerhetscenter-portalen.

3.  Kör verktyget TestCloudConnection.exe C:\Program\Microsoft Monitoring Agent\Agent" för att verifiera anslutningen och visa de URL-adresser som krävs för den specifika arbetsytan.

4.  Titta i listan med URL-adresser för Microsoft Defender för slutpunkten för en fullständig lista över krav för din region (mer information finns i [Tjänstwebbadresser för kalkylblad](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).

![Bild på administratör i Windows PowerShell](images/admin-powershell.png)

Jokert många (*) som används i *.ods.opinsights.azure.com-, *.oms.opinsights.azure.com- och *.agentsvc.azure-automation.net-URL-slutpunkter kan ersättas med ditt specifika arbetsyte-ID. Arbetsyte-ID:t är specifikt för din miljö och arbetsyta och finns i avsnittet Registrering för klientorganisationen i Microsoft Defender Säkerhetscenter-portalen.

Slutpunkten *.blob.core.windows.net-URL kan ersättas med WEBBADRESSerna som visas i avsnittet "Brandväggsregel: *.blob.core.windows.net" i testresultaten. 

> [!NOTE]
> När det gäller registrering via Azure Säkerhetscenter (ASC) kan flera arbetsytor användas. Du måste utföra TestCloudConnection.exe ovan på en inbyggd dator från varje arbetsyta (för att avgöra om det finns några ändringar i URL blob.core.windows.net adresserna mellan arbetsytorna).

## <a name="verify-client-connectivity-to-microsoft-defender-atp-service-urls"></a>Kontrollera klientanslutningen till URL-adresser för Microsoft Defender ATP-tjänsten

Verifiera att proxykonfigurationen har slutförts, att WinHTTP kan identifiera och kommunicera via proxyservern i din miljö och att proxyservern tillåter trafik till URL:er för Defender för slutpunktstjänsten.

1. Ladda ned [verktyget MDATP-klientanalys till](https://aka.ms/mdatpanalyzer) den dator där Defender för slutpunkts sensor körs på.

2. Extrahera innehållet i MDATPClientAnalyzer.zip på enheten.

3. Öppna en upphöjd kommandorad:

    a. Gå till **Start** och skriv **cmd**.

    b.  Högerklicka på **Kommandotolk** och välj **Kör som administratör.**

4. Ange följande kommando och tryck på **Retur:**

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    Ersätt *HardDrivePath* med sökvägen dit verktyget MDATPClientAnalyzer laddades ned till, till exempel

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. Extrahera den *MDATPClientAnalyzerResult.zip* som skapats av verktyget i mappen som används i *HardDrivePath.*

6. Öppna *MDATPClientAnalyzerResult.txt* och kontrollera att du har utfört proxykonfigurationsstegen för att aktivera serveridentifiering och åtkomst till tjänstens URL:er. <br><br>
   Verktyget kontrollerar anslutningen för Defender för slutpunktstjänst-URL:er som Defender för Slutpunktsklient är konfigurerad att interagera med. Sedan skrivs resultaten ut iMDATPClientAnalyzerResult.txt *för* varje URL-adress som potentiellt kan användas för att kommunicera med Defender för slutpunktstjänster. Till exempel:

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

Om minst ett av anslutningsalternativen returnerar en (200) status kan Defender för Endpoint-klienten kommunicera med den testat URL-adressen korrekt med den här anslutningsmetoden. <br><br>

Men om anslutningskontrollens resultat indikerar ett fel visas ett HTTP-fel (se HTTP-statuskoder). Du kan sedan använda URL:erna i tabellen som visas i Aktivera åtkomst till Defender för [slutpunktstjänst-URL:er i proxyservern.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server) Vilka URL-adresser du använder beror på vilken region du valde under registreringsprocessen.

> [!NOTE]
> Verktyget Anslutningsanalys är inte kompatibelt med ASR-regeln Blockera processskapanden som kommer från [PSExec- och WMI-kommandon.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules) Du måste tillfälligt inaktivera den här regeln för att köra anslutningsverktyget.


> [!NOTE]
> När telemetriproxyServer har angetts i registret eller via grupprincip hamnar Defender för Slutpunkt direkt om den inte har åtkomst till den definierade proxyn.

## <a name="related-topics"></a>Relaterade ämnen

- [Introducera Windows 10-enheter](configure-endpoints.md)
- [Felsöka problem med Introduktion till Slutpunkt för Microsoft Defender](troubleshoot-onboarding.md)
