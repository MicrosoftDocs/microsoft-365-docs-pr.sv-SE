---
title: Konfigurera enhetsproxy- och Internetanslutningsinställningar för slutpunkts-DLP
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Mer information om att konfigurera enhetsproxy- och Internetanslutningsinställningar för slutpunkts-DLP.
ms.openlocfilehash: f2a62b5c7913b6f41c414310a97ab5f072f59642
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538621"
---
# <a name="configure-device-proxy-and-internet-connection-settings-for-endpoint-dlp"></a><span data-ttu-id="d71c0-103">Konfigurera enhetsproxy- och Internetanslutningsinställningar för slutpunkts-DLP</span><span class="sxs-lookup"><span data-stu-id="d71c0-103">Configure device proxy and internet connection settings for Endpoint DLP</span></span>

<span data-ttu-id="d71c0-104">Microsofts slutpunkts-DLP använder Microsoft Windows HTTP (WinHTTP) till att rapportera data och kommunicera med Microsofts slutpunktsmolntjänst.</span><span class="sxs-lookup"><span data-stu-id="d71c0-104">Microsoft Endpoint DLP uses Microsoft Windows HTTP (WinHTTP) to report data and communicate with the Microsoft endpoint cloud service.</span></span> <span data-ttu-id="d71c0-105">Den inbäddade slutpunkts-DLP:n körs i systemkontext med hjälp av LocalSystem-kontot.</span><span class="sxs-lookup"><span data-stu-id="d71c0-105">The embedded Endpoint DLP runs in system context using the LocalSystem account.</span></span>

> [!TIP]
> <span data-ttu-id="d71c0-106">Organisationer som använder proxyservrar för vidarebefordran som en gateway till Internet, kan använda nätverksskydd till undersökningar bakom en proxy.</span><span class="sxs-lookup"><span data-stu-id="d71c0-106">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="d71c0-107">Mer information finns i [Undersöka anslutningshändelser som inträffar bakom proxyservrar för vidarebefordran](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy).</span><span class="sxs-lookup"><span data-stu-id="d71c0-107">For more information, see [Investigate connection events that occur behind forward proxies](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy).</span></span>

<span data-ttu-id="d71c0-108">WinHTTP-konfigurationsinställningen är fristående från proxyinställningarna för WinINet-surfning (Windows Internet) och kan bara identifiera en proxyserver med följande metoder för automatisk identifiering:</span><span class="sxs-lookup"><span data-stu-id="d71c0-108">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following auto discovery methods:</span></span>

- <span data-ttu-id="d71c0-109">Transparent proxy</span><span class="sxs-lookup"><span data-stu-id="d71c0-109">Transparent proxy</span></span>
- <span data-ttu-id="d71c0-110">WPAD (Web Proxy Auto-discovery Protocol)</span><span class="sxs-lookup"><span data-stu-id="d71c0-110">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

> [!NOTE]
> <span data-ttu-id="d71c0-111">Om du använder transparent proxy eller WPAD i nätverkstopologin, behöver du inte några särskilda konfigurationsinställningar.</span><span class="sxs-lookup"><span data-stu-id="d71c0-111">If you’re using Transparent proxy or WPAD in your network topology, you don’t need special configuration settings.</span></span> <span data-ttu-id="d71c0-112">Mer information om URL-undantag för Defender för Endpoint i proxyn finns i [Aktivera åtkomst till URL:er för slutpunkts-DLP:ns molntjänster på proxyservern](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="d71c0-112">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="d71c0-113">Manuell konfiguration av statisk proxy:</span><span class="sxs-lookup"><span data-stu-id="d71c0-113">Manual static proxy configuration:</span></span>
    - <span data-ttu-id="d71c0-114">Registerbaserad konfiguration</span><span class="sxs-lookup"><span data-stu-id="d71c0-114">Registry-based configuration</span></span>
    - <span data-ttu-id="d71c0-115">WinHTTP som är konfigurerat med ett netsh-kommando – Endast lämpligt för stationära datorer i en stabil topologi (t.ex. en stationär dator i ett företagsnätverk bakom samma proxy)</span><span class="sxs-lookup"><span data-stu-id="d71c0-115">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="d71c0-116">Konfigurera proxyservern manuellt med hjälp av en registerbaserad statisk proxy</span><span class="sxs-lookup"><span data-stu-id="d71c0-116">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="d71c0-117">För slutpunktsenheter som inte har tillåtelse att ansluta till Internet måste du konfigurera en registerbaserad statisk proxy.</span><span class="sxs-lookup"><span data-stu-id="d71c0-117">For endpoint devices that aren't permitted to connect to the Internet, you need to configure a registry-based static proxy.</span></span> <span data-ttu-id="d71c0-118">Du måste konfigurera detta för att endast Microsofts slutpunkts-DLP ska kunna rapportera diagnostiska data och kommunicera med Microsoft-slutpunktens molntjänst.</span><span class="sxs-lookup"><span data-stu-id="d71c0-118">You need to configure this to allow only Microsoft Endpoint DLP to report diagnostic data and communicate with Microsoft endpoint cloud service.</span></span>

<span data-ttu-id="d71c0-119">Den statiska proxyn kan konfigureras via en grupprincip.</span><span class="sxs-lookup"><span data-stu-id="d71c0-119">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="d71c0-120">Grupprincipen finns under:</span><span class="sxs-lookup"><span data-stu-id="d71c0-120">The group policy can be found under:</span></span>

1. <span data-ttu-id="d71c0-121">Öppna **Administrativa mallar > Windows-komponenter > Datainsamling och förhandsversioner > Konfigurera användning av autentiserad proxy för tjänsten Enhetlig användarupplevelse och telemetri**</span><span class="sxs-lookup"><span data-stu-id="d71c0-121">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**</span></span>

2. <span data-ttu-id="d71c0-122">Ställ in den som **Aktiverad** och välj **Inaktivera användning av autentiserad proxy**:</span><span class="sxs-lookup"><span data-stu-id="d71c0-122">Set it to **Enabled** and select **Disable Authenticated Proxy usage**:</span></span> 

![Bild av grupprincipinställningar 1](../media/atp-gpo-proxy1.png)
 
3. <span data-ttu-id="d71c0-124">Öppna **Administrativa mallar > Windows-komponenter > Datainsamling och förhandsversioner > Konfigurera Enhetlig användarupplevelse och telemetri**:</span><span class="sxs-lookup"><span data-stu-id="d71c0-124">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>

 <span data-ttu-id="d71c0-125">Konfigurera proxyn</span><span class="sxs-lookup"><span data-stu-id="d71c0-125">Configure the proxy</span></span>

![Bild av grupprincipinställningar 2](../media/atp-gpo-proxy2.png)

<span data-ttu-id="d71c0-127">Principen anger två registervärden `TelemetryProxyServer` som REG_SZ och `DisableEnterpriseAuthProxy` som REG_DWORD under registernyckeln `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span><span class="sxs-lookup"><span data-stu-id="d71c0-127">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

<span data-ttu-id="d71c0-128">Registervärdet TelemetryProxyServer är i det här formatet \<server name or ip\>:\<port\>.</span><span class="sxs-lookup"><span data-stu-id="d71c0-128">The registry value TelemetryProxyServer is in this format \<server name or ip\>:\<port\>.</span></span> <span data-ttu-id="d71c0-129">Till exempel: **10.0.0.6:8080**</span><span class="sxs-lookup"><span data-stu-id="d71c0-129">For example: **10.0.0.6:8080**</span></span>

<span data-ttu-id="d71c0-130">Registervärdet `DisableEnterpriseAuthProxy` anges till 1.</span><span class="sxs-lookup"><span data-stu-id="d71c0-130">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="d71c0-131">Konfigurera proxyservern manuellt med hjälp av ”netsh”-kommandot</span><span class="sxs-lookup"><span data-stu-id="d71c0-131">Configure the proxy server manually using "netsh" command</span></span>

<span data-ttu-id="d71c0-132">Använd netsh för att konfigurera en systemomfattande statisk proxy.</span><span class="sxs-lookup"><span data-stu-id="d71c0-132">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> <span data-ttu-id="d71c0-133">Detta påverkar alla program, inklusive Windows-tjänster som använder WinHTTP med standardproxyn.</span><span class="sxs-lookup"><span data-stu-id="d71c0-133">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span> <span data-ttu-id="d71c0-134">– Bärbara datorer som byter topologi (t.ex. från kontoret till hemmet) fungerar inte med netsh.</span><span class="sxs-lookup"><span data-stu-id="d71c0-134">- Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="d71c0-135">Använd den registerbaserade statiska proxykonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="d71c0-135">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="d71c0-136">Öppna en upphöjd kommandorad:</span><span class="sxs-lookup"><span data-stu-id="d71c0-136">Open an elevated command line:</span></span>
    1. <span data-ttu-id="d71c0-137">Gå till **Start** och skriv **cmd**</span><span class="sxs-lookup"><span data-stu-id="d71c0-137">Go to **Start** and type **cmd**</span></span>
    1. <span data-ttu-id="d71c0-138">Högerklicka på **Kommandotolken** och välj **Kör som administratör**.</span><span class="sxs-lookup"><span data-stu-id="d71c0-138">Right-click **Command prompt** and select **Run as administrator**.</span></span>
2.  <span data-ttu-id="d71c0-139">Skriv följande kommando och tryck på **Retur**:</span><span class="sxs-lookup"><span data-stu-id="d71c0-139">Enter the following command and press **Enter**:</span></span>

    `netsh winhttp set proxy <proxy>:<port>`

    <span data-ttu-id="d71c0-140">Till exempel: **netsh winhttp set proxy 10.0.0.6:8080**</span><span class="sxs-lookup"><span data-stu-id="d71c0-140">For example: **netsh winhttp set proxy 10.0.0.6:8080**</span></span>

3. <span data-ttu-id="d71c0-141">Återställ winhttp-proxyn genom att ange följande kommando och trycka på **Retur**:</span><span class="sxs-lookup"><span data-stu-id="d71c0-141">To reset the winhttp proxy, enter the following command and press **Enter**:</span></span>

     `netsh winhttp reset proxy`

<span data-ttu-id="d71c0-142">Se [Netsh-kommandosyntax, kontexter och formatering](/windows-server/networking/technologies/netsh/netsh-contexts) för mer information.</span><span class="sxs-lookup"><span data-stu-id="d71c0-142">See [Netsh Command Syntax, Contexts, and Formatting](/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>


## <a name="enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server"></a><span data-ttu-id="d71c0-143">Aktivera åtkomst till URL:er för slutpunkts-DLP:ns molntjänst på proxyservern</span><span class="sxs-lookup"><span data-stu-id="d71c0-143">Enable access to Endpoint DLP cloud service URLs in the proxy server</span></span>

<span data-ttu-id="d71c0-144">Om en proxy eller brandvägg blockerar all trafik som standard och endast tillåter vissa domäner, lägger du till domänerna som visas på det nedladdningsbara bladet i listan med tillåtna domäner.</span><span class="sxs-lookup"><span data-stu-id="d71c0-144">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="d71c0-145">Det [nedladdningsbara kalkylbladet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) visar de tjänster och deras associerade URL:er som nätverket måste kunna ansluta till.</span><span class="sxs-lookup"><span data-stu-id="d71c0-145">This [downloadable spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="d71c0-146">Du bör se till att det inte finns några brandväggs- eller nätverksfiltreringsregler som nekar åtkomst till webbadresserna, eller så kan du behöva skapa en särskild regel som tillåter dem.</span><span class="sxs-lookup"><span data-stu-id="d71c0-146">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an allow rule specifically for them.</span></span>

<span data-ttu-id="d71c0-147">Om en proxy eller brandvägg har HTTPS-skanning (SSL-inspektion) aktiverad, utesluter du domänerna som visas i tabellen ovan från HTTPS-skanningen.</span><span class="sxs-lookup"><span data-stu-id="d71c0-147">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>
<span data-ttu-id="d71c0-148">Om en proxy eller brandvägg blockerar anonym trafik när slutpunkts-DLP:n ansluter från systemets kontext, kontrollerar du att anonym trafik har tillåtits i tidigare listade URL:er.</span><span class="sxs-lookup"><span data-stu-id="d71c0-148">If a proxy or firewall is blocking anonymous traffic, as Endpoint DLP is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

## <a name="verify-client-connectivity-to-microsoft-cloud-service-urls"></a><span data-ttu-id="d71c0-149">Verifiera klientanslutningen till URL:erna för Microsofts molntjänst</span><span class="sxs-lookup"><span data-stu-id="d71c0-149">Verify client connectivity to Microsoft cloud service URLs</span></span>

<span data-ttu-id="d71c0-150">Verifiera att proxykonfigurationen har slutförts, att WinHTTP kan identifiera och kommunicera via proxyservern i din miljö och att proxyservern tillåter trafik till URL:erna för Defender för Endpoint-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="d71c0-150">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="d71c0-151">Ladda ned [verktyget för MDATP-klientanalys](https://aka.ms/mdatpanalyzer) till den dator som slutpunkts-DLP:n körs på.</span><span class="sxs-lookup"><span data-stu-id="d71c0-151">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Endpoint DLP is running on.</span></span>
2. <span data-ttu-id="d71c0-152">Extrahera innehållet i MDATPClientAnalyzer.zip på enheten.</span><span class="sxs-lookup"><span data-stu-id="d71c0-152">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>
3. <span data-ttu-id="d71c0-153">Öppna en upphöjd kommandorad:</span><span class="sxs-lookup"><span data-stu-id="d71c0-153">Open an elevated command line:</span></span>
    1. <span data-ttu-id="d71c0-154">Gå till **Start** och skriv **cmd**.</span><span class="sxs-lookup"><span data-stu-id="d71c0-154">Go to **Start** and type **cmd**.</span></span>
    1. <span data-ttu-id="d71c0-155">Högerklicka på **Kommandotolken** och välj **Kör som administratör**.</span><span class="sxs-lookup"><span data-stu-id="d71c0-155">Right-click **Command prompt** and select **Run as administrator**.</span></span>
4.  <span data-ttu-id="d71c0-156">Skriv följande kommando och tryck på **Retur**:</span><span class="sxs-lookup"><span data-stu-id="d71c0-156">Enter the following command and press **Enter**:</span></span>
    
`HardDrivePath\MDATPClientAnalyzer.cmd`

<span data-ttu-id="d71c0-157">Ersätt *HardDrivePath* med sökvägen där verktyget MDATPClientAnalyzer laddades ned, till exempel</span><span class="sxs-lookup"><span data-stu-id="d71c0-157">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example</span></span>
    
<span data-ttu-id="d71c0-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**</span><span class="sxs-lookup"><span data-stu-id="d71c0-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**</span></span>


5.  <span data-ttu-id="d71c0-159">Extrahera filen **MDATPClientAnalyzerResult.zip** _ som skapades av verktyget i mappen som används i _HardDrivePath\*.</span><span class="sxs-lookup"><span data-stu-id="d71c0-159">Extract the **MDATPClientAnalyzerResult.zip** _ file created by tool in the folder used in the _HardDrivePath\*.</span></span>

6.  <span data-ttu-id="d71c0-160">Öppna **MDATPClientAnalyzerResult.txt** och kontrollera att du har utfört proxykonfigurationsstegen som aktiverar serveridentifiering och åtkomst till tjänstens URL:er.</span><span class="sxs-lookup"><span data-stu-id="d71c0-160">Open **MDATPClientAnalyzerResult.txt** and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span>  <span data-ttu-id="d71c0-161">Verktyget kontrollerar anslutningen av URL:erna för Defender för Endpoint-tjänsten som Defender för Endpoint-klienten har konfigurerats att interagera med.</span><span class="sxs-lookup"><span data-stu-id="d71c0-161">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="d71c0-162">Resultatet skrivs sedan i filen **MDATPClientAnalyzerResult.txt** för varje URL som kan användas till att kommunicera med Defender för Endpoint-tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="d71c0-162">It then prints the results into the **MDATPClientAnalyzerResult.txt** file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="d71c0-163">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="d71c0-163">For example:</span></span>

    <span data-ttu-id="d71c0-164">**Test-URL: https://xxx.microsoft.com/xxx </br> 1 – Standardproxy: Lyckades (200) </br> 2 – Automatisk identifiering av proxy (WPAD): Lyckades (200)</br> 3 – Inaktiverad proxy: Lyckades (200)</br> 4 – Namngiven proxy: Finns inte</br> 5 – Kommandoradsproxy: Finns inte**</span><span class="sxs-lookup"><span data-stu-id="d71c0-164">**Testing URL: https://xxx.microsoft.com/xxx </br> 1 - Default proxy: Succeeded (200) </br> 2 - Proxy auto discovery (WPAD): Succeeded (200)</br> 3 - Proxy disabled: Succeeded (200)</br> 4 - Named proxy: Doesn't exist</br> 5 - Command-line proxy: Doesn't exist**</span></span></br>


<span data-ttu-id="d71c0-165">Om minst ett av anslutningsalternativen returnerar en status (200) kan Defender för Endpoint-klienten kommunicera med den testade URL:en med anslutningsmetoden.</span><span class="sxs-lookup"><span data-stu-id="d71c0-165">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span> 

<span data-ttu-id="d71c0-166">Men om anslutningskontrollens resultat anger att ett fel uppstod, visas ett HTTP-fel (se HTTP-statuskoder).</span><span class="sxs-lookup"><span data-stu-id="d71c0-166">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="d71c0-167">Du kan därefter använda URL:erna i tabellen som visas i [Aktivera åtkomst till URL:er för slutpunkts-DLP:ns molntjänst på proxyservern](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="d71c0-167">You can then use the URLs in the table shown in [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="d71c0-168">Vilka URL:er som kommer att användas beror på den region som valdes under registreringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="d71c0-168">The URLs you’ll use will depend on the region selected during the onboarding procedure.</span></span>
[!NOTE]<span data-ttu-id="d71c0-169"> Verktyget Connectivity Analyzer är inte kompatibelt med ASR-regeln [Blockera processer som skapas från PSExec- och WMI-kommandon](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="d71c0-169"> The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="d71c0-170">Du måste inaktivera regeln tillfälligt om du vill köra anslutningsverktyget.</span><span class="sxs-lookup"><span data-stu-id="d71c0-170">You will need to temporarily disable this rule to run the connectivity tool.</span></span>

[!NOTE] <span data-ttu-id="d71c0-171">När TelemetryProxyServer har angetts i registret eller via en grupprincip kommer Defender för Endpoint att dirigeras om den inte har åtkomst till den definierade proxyn.</span><span class="sxs-lookup"><span data-stu-id="d71c0-171">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can’t access the defined proxy.</span></span>
<span data-ttu-id="d71c0-172">Närliggande information •   Registrera Windows 10-enheter •   Felsöka problem med Microsoft-registrering av slutpunkts-DLP</span><span class="sxs-lookup"><span data-stu-id="d71c0-172">Related topics •   Onboard Windows 10 devices •   Troubleshoot Microsoft Endpoint DLP onboarding issues</span></span>





## <a name="see-also"></a><span data-ttu-id="d71c0-173">Se även</span><span class="sxs-lookup"><span data-stu-id="d71c0-173">See also</span></span>

- [<span data-ttu-id="d71c0-174">Mer information om dataförlustskydd för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="d71c0-174">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="d71c0-175">Använda dataförlustskydd för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="d71c0-175">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="d71c0-176">Mer information om dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="d71c0-176">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="d71c0-177">Skapa, testa och justera en DLP-princip</span><span class="sxs-lookup"><span data-stu-id="d71c0-177">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="d71c0-178">Kom igång med Aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="d71c0-178">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="d71c0-179">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="d71c0-179">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="d71c0-180">Registreringsverktyg och metoder för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="d71c0-180">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="d71c0-181">Microsoft 365-prenumeration</span><span class="sxs-lookup"><span data-stu-id="d71c0-181">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="d71c0-182">Azure AD-anslutna enheter</span><span class="sxs-lookup"><span data-stu-id="d71c0-182">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="d71c0-183">Ladda ned nya Microsoft Edge som baseras på Chromium</span><span class="sxs-lookup"><span data-stu-id="d71c0-183">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)