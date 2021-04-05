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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b529b1c7fa5c4f9f81cb6bfbb5f1a6bd7823a9ad
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587605"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="2895c-104">Konfigurera enhetsproxy och internetanslutningsinställningar</span><span class="sxs-lookup"><span data-stu-id="2895c-104">Configure device proxy and Internet connectivity settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2895c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2895c-105">**Applies to:**</span></span>
- [<span data-ttu-id="2895c-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="2895c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2895c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2895c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2895c-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="2895c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2895c-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="2895c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="2895c-110">Defender för slutpunkts sensor kräver Microsoft Windows HTTP (WinHTTP) för att rapportera sensordata och kommunicera med Defender för slutpunktstjänsten.</span><span class="sxs-lookup"><span data-stu-id="2895c-110">The Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Defender for Endpoint service.</span></span>

<span data-ttu-id="2895c-111">Den inbäddade Defender för slutpunkts sensor körs i systemkontext med localSystem-kontot.</span><span class="sxs-lookup"><span data-stu-id="2895c-111">The embedded Defender for Endpoint sensor runs in system context using the LocalSystem account.</span></span> <span data-ttu-id="2895c-112">Sensorn använder Microsoft Windows HTTP Services (WinHTTP) för att aktivera kommunikation med Defender för molntjänsten Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2895c-112">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Defender for Endpoint cloud service.</span></span>

>[!TIP]
><span data-ttu-id="2895c-113">För organisationer som använder proxyservrar som en gateway till Internet kan du använda nätverksskydd och undersöka bakom en proxy.</span><span class="sxs-lookup"><span data-stu-id="2895c-113">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="2895c-114">Mer information finns i Undersöka [anslutningshändelser som inträffar bakom proxy proxy.](investigate-behind-proxy.md)</span><span class="sxs-lookup"><span data-stu-id="2895c-114">For more information, see [Investigate connection events that occur behind forward proxies](investigate-behind-proxy.md).</span></span>

<span data-ttu-id="2895c-115">WinHTTP-konfigurationsinställningen är oberoende av proxyinställningarna för Internetsurfning på Windows Internet (WinINet) och kan bara identifiera en proxyserver med hjälp av följande identifieringsmetoder:</span><span class="sxs-lookup"><span data-stu-id="2895c-115">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

- <span data-ttu-id="2895c-116">Metoder för automatisk identifiering:</span><span class="sxs-lookup"><span data-stu-id="2895c-116">Auto-discovery methods:</span></span>
  - <span data-ttu-id="2895c-117">Transparent proxy</span><span class="sxs-lookup"><span data-stu-id="2895c-117">Transparent proxy</span></span>
  - <span data-ttu-id="2895c-118">Web Proxy Auto-discovery Protocol (WPAD)</span><span class="sxs-lookup"><span data-stu-id="2895c-118">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

    > [!NOTE]
    > <span data-ttu-id="2895c-119">Om du använder Transparent proxy eller WPAD i nätverkstopologin behöver du inga särskilda konfigurationsinställningar.</span><span class="sxs-lookup"><span data-stu-id="2895c-119">If you're using Transparent proxy or WPAD in your network topology, you don't need special configuration settings.</span></span> <span data-ttu-id="2895c-120">Mer information om undantag för Slutpunkts-URL för Defender i proxyn finns i Aktivera åtkomst till Defender för [slutpunktstjänst-URL:er i proxyservern.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="2895c-120">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="2895c-121">Manuell statisk proxykonfiguration:</span><span class="sxs-lookup"><span data-stu-id="2895c-121">Manual static proxy configuration:</span></span>
  - <span data-ttu-id="2895c-122">Registerbaserad konfiguration</span><span class="sxs-lookup"><span data-stu-id="2895c-122">Registry based configuration</span></span>
  - <span data-ttu-id="2895c-123">WinHTTP som konfigurerats med netsh-kommandot – endast lämpligt för stationära datorer i en stabil topologi (till exempel: ett skrivbord i ett företagsnätverk bakom samma proxy)</span><span class="sxs-lookup"><span data-stu-id="2895c-123">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="2895c-124">Konfigurera proxyservern manuellt med hjälp av en registerbaserad statisk proxyserver</span><span class="sxs-lookup"><span data-stu-id="2895c-124">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="2895c-125">Konfigurera en registerbaserad statisk proxy så att endast Defender för slutpunkts sensor kan rapportera diagnostikdata och kommunicera med Defender för Slutpunktstjänster om en dator inte har tillåtelse att ansluta till Internet.</span><span class="sxs-lookup"><span data-stu-id="2895c-125">Configure a registry-based static proxy to allow only Defender for Endpoint sensor to report diagnostic data and communicate with Defender for Endpoint services if a computer is not be permitted to connect to the Internet.</span></span>

<span data-ttu-id="2895c-126">Den statiska proxyn kan konfigureras via grupprincip (GP).</span><span class="sxs-lookup"><span data-stu-id="2895c-126">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="2895c-127">Grupprincipen hittar du under:</span><span class="sxs-lookup"><span data-stu-id="2895c-127">The group policy can be found under:</span></span>

- <span data-ttu-id="2895c-128">Administrativa mallar > Windows-komponenter > datainsamlings- och förhandsversioner > Konfigurera autentiserad proxyanvändning för den anslutna användarupplevelsen och telemetritjänsten</span><span class="sxs-lookup"><span data-stu-id="2895c-128">Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service</span></span>
  - <span data-ttu-id="2895c-129">Ställ in den **på Aktiverad** och välj **Inaktivera autentiserad proxyanvändning:** ![ Bild på grupprincipinställning1](images/atp-gpo-proxy1.png)</span><span class="sxs-lookup"><span data-stu-id="2895c-129">Set it to **Enabled** and select **Disable Authenticated Proxy usage**: ![Image of Group Policy setting1](images/atp-gpo-proxy1.png)</span></span>
- <span data-ttu-id="2895c-130">**Administrativa mallar > Windows-komponenter > datainsamlings- och förhandsversioner > Konfigurera anslutna användarupplevelser och telemetri:**</span><span class="sxs-lookup"><span data-stu-id="2895c-130">**Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>
  - <span data-ttu-id="2895c-131">Konfigurera proxyn:</span><span class="sxs-lookup"><span data-stu-id="2895c-131">Configure the proxy:</span></span><br>
    <span data-ttu-id="2895c-132">![Bild av grupprincipinställning2](images/atp-gpo-proxy2.png)</span><span class="sxs-lookup"><span data-stu-id="2895c-132">![Image of Group Policy setting2](images/atp-gpo-proxy2.png)</span></span>

    <span data-ttu-id="2895c-133">Principen anger två registervärden `TelemetryProxyServer` som REG_SZ och REG_DWORD `DisableEnterpriseAuthProxy` registernyckeln `HKLM\Software\Policies\Microsoft\Windows\DataCollection` .</span><span class="sxs-lookup"><span data-stu-id="2895c-133">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

    <span data-ttu-id="2895c-134">Registervärdet `TelemetryProxyServer` har följande strängformat:</span><span class="sxs-lookup"><span data-stu-id="2895c-134">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

    ```text
    <server name or ip>:<port>
    ```

    <span data-ttu-id="2895c-135">Till exempel: 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="2895c-135">For example: 10.0.0.6:8080</span></span>

    <span data-ttu-id="2895c-136">Registervärdet `DisableEnterpriseAuthProxy` ska vara 1.</span><span class="sxs-lookup"><span data-stu-id="2895c-136">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="2895c-137">Konfigurera proxyservern manuellt med netsh-kommandot</span><span class="sxs-lookup"><span data-stu-id="2895c-137">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="2895c-138">Använd netsh för att konfigurera en systemomfattande statisk proxy.</span><span class="sxs-lookup"><span data-stu-id="2895c-138">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> - <span data-ttu-id="2895c-139">Detta påverkar alla program, inklusive Windows-tjänster som använder WinHTTP med standardproxy.</span><span class="sxs-lookup"><span data-stu-id="2895c-139">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="2895c-140">Bärbara datorer som ändrar topologi (till exempel från kontor till hem) fungerar inte på netsh.</span><span class="sxs-lookup"><span data-stu-id="2895c-140">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="2895c-141">Använd den registerbaserade statiska proxykonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="2895c-141">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="2895c-142">Öppna en upphöjd kommandorad:</span><span class="sxs-lookup"><span data-stu-id="2895c-142">Open an elevated command-line:</span></span>

    <span data-ttu-id="2895c-143">a.</span><span class="sxs-lookup"><span data-stu-id="2895c-143">a.</span></span> <span data-ttu-id="2895c-144">Gå till **Start** och skriv **cmd**.</span><span class="sxs-lookup"><span data-stu-id="2895c-144">Go to **Start** and type **cmd**.</span></span>

    <span data-ttu-id="2895c-145">b.</span><span class="sxs-lookup"><span data-stu-id="2895c-145">b.</span></span> <span data-ttu-id="2895c-146">Högerklicka på **Kommandotolk** och välj **Kör som administratör.**</span><span class="sxs-lookup"><span data-stu-id="2895c-146">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="2895c-147">Ange följande kommando och tryck på **Retur:**</span><span class="sxs-lookup"><span data-stu-id="2895c-147">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="2895c-148">Till exempel: netsh winhttp set proxy 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="2895c-148">For example: netsh winhttp set proxy 10.0.0.6:8080</span></span>

<span data-ttu-id="2895c-149">Om du vill återställa winhttp proxy, ange följande kommando och tryck på **Retur**</span><span class="sxs-lookup"><span data-stu-id="2895c-149">To reset the winhttp proxy, enter the following command and press **Enter**</span></span>

```PowerShell
netsh winhttp reset proxy
```

<span data-ttu-id="2895c-150">Mer [information finns i Netsh-kommandosyntax,](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts) sammanhang och formatering.</span><span class="sxs-lookup"><span data-stu-id="2895c-150">See [Netsh Command Syntax, Contexts, and Formatting](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a><span data-ttu-id="2895c-151">Aktivera åtkomst till URL-adresser för Microsoft Defender för slutpunktstjänsten på proxyservern</span><span class="sxs-lookup"><span data-stu-id="2895c-151">Enable access to Microsoft Defender for Endpoint service URLs in the proxy server</span></span>

<span data-ttu-id="2895c-152">Om en proxy eller brandvägg blockerar all trafik som standard och bara tillåter specifika domäner genom, lägger du till de domäner som visas i det nedladdningsbara bladet i listan med tillåtna domäner.</span><span class="sxs-lookup"><span data-stu-id="2895c-152">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="2895c-153">I följande nedladdningsbara kalkylblad finns de tjänster och deras tillhörande URL:er som nätverket måste kunna ansluta till.</span><span class="sxs-lookup"><span data-stu-id="2895c-153">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="2895c-154">Du bör kontrollera att det inte finns några brandväggs- eller nätverksfiltreringsregler som nekar åtkomst till dessa URL:er, eller att du kan behöva skapa en *tillåta-regel* specifikt för dem.</span><span class="sxs-lookup"><span data-stu-id="2895c-154">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>


|<span data-ttu-id="2895c-155">**Kalkylblad med domänlista**</span><span class="sxs-lookup"><span data-stu-id="2895c-155">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="2895c-156">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="2895c-156">**Description**</span></span>|
|:-----|:-----|
|![Miniatyrbild för Microsoft Defender för slutpunkts-URL:er-kalkylblad](images/mdatp-urls.png)<br/>  | <span data-ttu-id="2895c-158">Kalkylblad med specifika DNS-poster för tjänstplatser, geografiska platser och operativsystem.</span><span class="sxs-lookup"><span data-stu-id="2895c-158">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="2895c-159">Ladda ned kalkylbladet här.</span><span class="sxs-lookup"><span data-stu-id="2895c-159">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


<span data-ttu-id="2895c-160">Om https-skanning (SSL-skanning) är aktiverat för en proxy eller brandvägg ska du utesluta domäner som listas i tabellen ovan från HTTPS-skanning.</span><span class="sxs-lookup"><span data-stu-id="2895c-160">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>

> [!NOTE]
> <span data-ttu-id="2895c-161">settings-win.data.microsoft.com bara om du har Windows 10-enheter med version 1803 eller tidigare.</span><span class="sxs-lookup"><span data-stu-id="2895c-161">settings-win.data.microsoft.com is only needed if you have Windows 10 devices running version 1803 or earlier.</span></span><br>


> [!NOTE]
> <span data-ttu-id="2895c-162">URL-adresser som innehåller v20 i dem behövs bara om du har Windows 10-enheter med version 1803 eller senare.</span><span class="sxs-lookup"><span data-stu-id="2895c-162">URLs that include v20 in them are only needed if you have Windows 10 devices running version 1803 or later.</span></span> <span data-ttu-id="2895c-163">Du behöver till ```us-v20.events.data.microsoft.com``` exempel en Windows 10-enhet med version 1803 eller senare och förs in i området för datalagring i USA.</span><span class="sxs-lookup"><span data-stu-id="2895c-163">For example, ```us-v20.events.data.microsoft.com``` is needed for a Windows 10 device running version 1803 or later and onboarded to US Data Storage region.</span></span>


> [!NOTE]
> <span data-ttu-id="2895c-164">Om du använder Microsoft Defender Antivirus i din miljö kan du gå [till Konfigurera nätverksanslutningar till molntjänsten Microsoft Defender Antivirus.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="2895c-164">If you are using Microsoft Defender Antivirus in your environment, see [Configure network connections to the Microsoft Defender Antivirus cloud service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="2895c-165">Om en proxy eller brandvägg blockerar anonym trafik, som Defender för Slutpunkts sensor ansluter från systemkontext, kontrollerar du att anonym trafik tillåts i tidigare angivna URL:er.</span><span class="sxs-lookup"><span data-stu-id="2895c-165">If a proxy or firewall is blocking anonymous traffic, as Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a><span data-ttu-id="2895c-166">Microsoft Monitoring Agent (MMA) – proxy- och brandväggskrav för äldre versioner av Windows-klienten eller Windows Server</span><span class="sxs-lookup"><span data-stu-id="2895c-166">Microsoft Monitoring Agent (MMA) - proxy and firewall requirements for older versions of Windows client or Windows Server</span></span>

<span data-ttu-id="2895c-167">I informationen nedan visas den konfigurationsinformation för proxy och brandvägg som krävs för att kommunicera med loganalysagenten (kallas ofta Microsoft monitoring agent) för tidigare versioner av Windows, till exempel Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2 och Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="2895c-167">The information below list the proxy and firewall configuration information required to communicate with Log Analytics agent (often referred to as Microsoft Monitoring Agent) for the previous versions of Windows such as Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2, and Windows Server 2016.</span></span>

|<span data-ttu-id="2895c-168">Agentresurs</span><span class="sxs-lookup"><span data-stu-id="2895c-168">Agent Resource</span></span>|<span data-ttu-id="2895c-169">Portar</span><span class="sxs-lookup"><span data-stu-id="2895c-169">Ports</span></span> |<span data-ttu-id="2895c-170">Riktning</span><span class="sxs-lookup"><span data-stu-id="2895c-170">Direction</span></span> |<span data-ttu-id="2895c-171">Förbikoppling av HTTPS-kontroll</span><span class="sxs-lookup"><span data-stu-id="2895c-171">Bypass HTTPS inspection</span></span>|
|------|---------|--------|--------|   
|<span data-ttu-id="2895c-172">\*.ods.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="2895c-172">\*.ods.opinsights.azure.com</span></span> |<span data-ttu-id="2895c-173">Port 443</span><span class="sxs-lookup"><span data-stu-id="2895c-173">Port 443</span></span> |<span data-ttu-id="2895c-174">Utgående</span><span class="sxs-lookup"><span data-stu-id="2895c-174">Outbound</span></span>|<span data-ttu-id="2895c-175">Ja</span><span class="sxs-lookup"><span data-stu-id="2895c-175">Yes</span></span> |  
|<span data-ttu-id="2895c-176">\*.oms.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="2895c-176">\*.oms.opinsights.azure.com</span></span> |<span data-ttu-id="2895c-177">Port 443</span><span class="sxs-lookup"><span data-stu-id="2895c-177">Port 443</span></span> |<span data-ttu-id="2895c-178">Utgående</span><span class="sxs-lookup"><span data-stu-id="2895c-178">Outbound</span></span>|<span data-ttu-id="2895c-179">Ja</span><span class="sxs-lookup"><span data-stu-id="2895c-179">Yes</span></span> |  
|<span data-ttu-id="2895c-180">\*.blob.core.windows.net</span><span class="sxs-lookup"><span data-stu-id="2895c-180">\*.blob.core.windows.net</span></span> |<span data-ttu-id="2895c-181">Port 443</span><span class="sxs-lookup"><span data-stu-id="2895c-181">Port 443</span></span> |<span data-ttu-id="2895c-182">Utgående</span><span class="sxs-lookup"><span data-stu-id="2895c-182">Outbound</span></span>|<span data-ttu-id="2895c-183">Ja</span><span class="sxs-lookup"><span data-stu-id="2895c-183">Yes</span></span> |
|<span data-ttu-id="2895c-184">\*.azure-automation.net</span><span class="sxs-lookup"><span data-stu-id="2895c-184">\*.azure-automation.net</span></span> |<span data-ttu-id="2895c-185">Port 443</span><span class="sxs-lookup"><span data-stu-id="2895c-185">Port 443</span></span> |<span data-ttu-id="2895c-186">Utgående</span><span class="sxs-lookup"><span data-stu-id="2895c-186">Outbound</span></span>|<span data-ttu-id="2895c-187">Ja</span><span class="sxs-lookup"><span data-stu-id="2895c-187">Yes</span></span> |  


> [!NOTE]
> <span data-ttu-id="2895c-188">Som en molnbaserad lösning kan IP-intervallet ändras.</span><span class="sxs-lookup"><span data-stu-id="2895c-188">As a cloud-based solution, the IP range can change.</span></span> <span data-ttu-id="2895c-189">Vi rekommenderar att du går över till DNS-lösningsinställningen.</span><span class="sxs-lookup"><span data-stu-id="2895c-189">It's recommended you move to DNS resolving setting.</span></span>

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a><span data-ttu-id="2895c-190">Bekräfta URL-krav för Tjänst-URL för Microsoft Monitoring Agent (MMA)</span><span class="sxs-lookup"><span data-stu-id="2895c-190">Confirm Microsoft Monitoring Agent (MMA) Service URL Requirements</span></span> 

<span data-ttu-id="2895c-191">Läs följande vägledning för att ta bort jokertecknet (\*) för din specifika miljö när du använder Microsoft Monitoring Agent (MMA) för tidigare versioner av Windows.</span><span class="sxs-lookup"><span data-stu-id="2895c-191">Please see the following guidance to eliminate the wildcard (\*) requirement for your specific environment when using the Microsoft Monitoring Agent (MMA) for previous versions of Windows.</span></span>

1.  <span data-ttu-id="2895c-192">Introducera ett tidigare operativsystem med Microsoft Monitoring Agent (MMA) i Defender för slutpunkt (mer information finns i Hantera tidigare versioner av Windows på [Defender](https://go.microsoft.com/fwlink/p/?linkid=2010326) för slutpunkt och Onboard [Windows-servrar.](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)</span><span class="sxs-lookup"><span data-stu-id="2895c-192">Onboard a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, see [Onboard previous versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and [Onboard Windows servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span>

2.  <span data-ttu-id="2895c-193">Kontrollera att datorn rapporterar till Microsoft Defender Säkerhetscenter-portalen.</span><span class="sxs-lookup"><span data-stu-id="2895c-193">Ensure the machine is successfully reporting into the Microsoft Defender Security Center portal.</span></span>

3.  <span data-ttu-id="2895c-194">Kör verktyget TestCloudConnection.exe C:\Program\Microsoft Monitoring Agent\Agent" för att verifiera anslutningen och visa de URL-adresser som krävs för den specifika arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="2895c-194">Run the TestCloudConnection.exe tool from “C:\Program Files\Microsoft Monitoring Agent\Agent” to validate the connectivity and to see the required URLs for your specific workspace.</span></span>

4.  <span data-ttu-id="2895c-195">Titta i listan med URL-adresser för Microsoft Defender för slutpunkten för en fullständig lista över krav för din region (mer information finns i [Tjänstwebbadresser för kalkylblad](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span><span class="sxs-lookup"><span data-stu-id="2895c-195">Check the Microsoft Defender for Endpoint URLs list for the complete list of requirements for your region (please refer to the Service URLs [Spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span></span>

![Bild på administratör i Windows PowerShell](images/admin-powershell.png)

<span data-ttu-id="2895c-197">Jokert många (\*) som används i \*.ods.opinsights.azure.com-, \*.oms.opinsights.azure.com- och \*.agentsvc.azure-automation.net-URL-slutpunkter kan ersättas med ditt specifika arbetsyte-ID.</span><span class="sxs-lookup"><span data-stu-id="2895c-197">The wildcards (\*) used in \*.ods.opinsights.azure.com, \*.oms.opinsights.azure.com, and \*.agentsvc.azure-automation.net URL endpoints can be replaced with your specific Workspace ID.</span></span> <span data-ttu-id="2895c-198">Arbetsyte-ID:t är specifikt för din miljö och arbetsyta och finns i avsnittet Registrering för klientorganisationen i Microsoft Defender Säkerhetscenter-portalen.</span><span class="sxs-lookup"><span data-stu-id="2895c-198">The Workspace ID is specific to your environment and workspace and can be found in the Onboarding section of your tenant within the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="2895c-199">Slutpunkten \*.blob.core.windows.net-URL kan ersättas med WEBBADRESSerna som visas i avsnittet "Brandväggsregel: \*.blob.core.windows.net" i testresultaten.</span><span class="sxs-lookup"><span data-stu-id="2895c-199">The \*.blob.core.windows.net URL endpoint can be replaced with the URLs shown in the “Firewall Rule: \*.blob.core.windows.net” section of the test results.</span></span> 

> [!NOTE]
> <span data-ttu-id="2895c-200">När det gäller registrering via Azure Säkerhetscenter (ASC) kan flera arbetsytor användas.</span><span class="sxs-lookup"><span data-stu-id="2895c-200">In the case of onboarding via Azure Security Center (ASC), multiple workspaces maybe used.</span></span> <span data-ttu-id="2895c-201">Du måste utföra TestCloudConnection.exe ovan på en inbyggd dator från varje arbetsyta (för att avgöra om det finns några ändringar i URL blob.core.windows.net adresserna mellan arbetsytorna).</span><span class="sxs-lookup"><span data-stu-id="2895c-201">You will need to perform the TestCloudConnection.exe procedure above on an onboarded machine from each workspace (to determine if there are any changes to the \*.blob.core.windows.net URLs between the workspaces).</span></span>

## <a name="verify-client-connectivity-to-microsoft-defender-atp-service-urls"></a><span data-ttu-id="2895c-202">Kontrollera klientanslutningen till URL-adresser för Microsoft Defender ATP-tjänsten</span><span class="sxs-lookup"><span data-stu-id="2895c-202">Verify client connectivity to Microsoft Defender ATP service URLs</span></span>

<span data-ttu-id="2895c-203">Verifiera att proxykonfigurationen har slutförts, att WinHTTP kan identifiera och kommunicera via proxyservern i din miljö och att proxyservern tillåter trafik till URL:er för Defender för slutpunktstjänsten.</span><span class="sxs-lookup"><span data-stu-id="2895c-203">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="2895c-204">Ladda ned [verktyget MDATP-klientanalys till](https://aka.ms/mdatpanalyzer) den dator där Defender för slutpunkts sensor körs på.</span><span class="sxs-lookup"><span data-stu-id="2895c-204">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Defender for Endpoint sensor is running on.</span></span>

2. <span data-ttu-id="2895c-205">Extrahera innehållet i MDATPClientAnalyzer.zip på enheten.</span><span class="sxs-lookup"><span data-stu-id="2895c-205">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>

3. <span data-ttu-id="2895c-206">Öppna en upphöjd kommandorad:</span><span class="sxs-lookup"><span data-stu-id="2895c-206">Open an elevated command-line:</span></span>

    <span data-ttu-id="2895c-207">a.</span><span class="sxs-lookup"><span data-stu-id="2895c-207">a.</span></span> <span data-ttu-id="2895c-208">Gå till **Start** och skriv **cmd**.</span><span class="sxs-lookup"><span data-stu-id="2895c-208">Go to **Start** and type **cmd**.</span></span>

    <span data-ttu-id="2895c-209">b.</span><span class="sxs-lookup"><span data-stu-id="2895c-209">b.</span></span>  <span data-ttu-id="2895c-210">Högerklicka på **Kommandotolk** och välj **Kör som administratör.**</span><span class="sxs-lookup"><span data-stu-id="2895c-210">Right-click **Command prompt** and select **Run as administrator**.</span></span>

4. <span data-ttu-id="2895c-211">Ange följande kommando och tryck på **Retur:**</span><span class="sxs-lookup"><span data-stu-id="2895c-211">Enter the following command and press **Enter**:</span></span>

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    <span data-ttu-id="2895c-212">Ersätt *HardDrivePath* med sökvägen dit verktyget MDATPClientAnalyzer laddades ned till, till exempel</span><span class="sxs-lookup"><span data-stu-id="2895c-212">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example</span></span>

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. <span data-ttu-id="2895c-213">Extrahera den *MDATPClientAnalyzerResult.zip* som skapats av verktyget i mappen som används i *HardDrivePath.*</span><span class="sxs-lookup"><span data-stu-id="2895c-213">Extract the *MDATPClientAnalyzerResult.zip* file created by tool in the folder used in the *HardDrivePath*.</span></span>

6. <span data-ttu-id="2895c-214">Öppna *MDATPClientAnalyzerResult.txt* och kontrollera att du har utfört proxykonfigurationsstegen för att aktivera serveridentifiering och åtkomst till tjänstens URL:er.</span><span class="sxs-lookup"><span data-stu-id="2895c-214">Open *MDATPClientAnalyzerResult.txt* and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span> <br><br>
   <span data-ttu-id="2895c-215">Verktyget kontrollerar anslutningen för Defender för slutpunktstjänst-URL:er som Defender för Slutpunktsklient är konfigurerad att interagera med.</span><span class="sxs-lookup"><span data-stu-id="2895c-215">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="2895c-216">Sedan skrivs resultaten ut iMDATPClientAnalyzerResult.txt *för* varje URL-adress som potentiellt kan användas för att kommunicera med Defender för slutpunktstjänster.</span><span class="sxs-lookup"><span data-stu-id="2895c-216">It then prints the results into the *MDATPClientAnalyzerResult.txt* file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="2895c-217">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2895c-217">For example:</span></span>

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

<span data-ttu-id="2895c-218">Om minst ett av anslutningsalternativen returnerar en (200) status kan Defender för Endpoint-klienten kommunicera med den testat URL-adressen korrekt med den här anslutningsmetoden.</span><span class="sxs-lookup"><span data-stu-id="2895c-218">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span> <br><br>

<span data-ttu-id="2895c-219">Men om anslutningskontrollens resultat indikerar ett fel visas ett HTTP-fel (se HTTP-statuskoder).</span><span class="sxs-lookup"><span data-stu-id="2895c-219">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="2895c-220">Du kan sedan använda URL:erna i tabellen som visas i Aktivera åtkomst till Defender för [slutpunktstjänst-URL:er i proxyservern.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="2895c-220">You can then use the URLs in the table shown in [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="2895c-221">Vilka URL-adresser du använder beror på vilken region du valde under registreringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="2895c-221">The URLs you'll use will depend on the region selected during the onboarding procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="2895c-222">Verktyget Anslutningsanalys är inte kompatibelt med ASR-regeln Blockera processskapanden som kommer från [PSExec- och WMI-kommandon.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="2895c-222">The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="2895c-223">Du måste tillfälligt inaktivera den här regeln för att köra anslutningsverktyget.</span><span class="sxs-lookup"><span data-stu-id="2895c-223">You will need to temporarily disable this rule to run the connectivity tool.</span></span>


> [!NOTE]
> <span data-ttu-id="2895c-224">När telemetriproxyServer har angetts i registret eller via grupprincip hamnar Defender för Slutpunkt direkt om den inte har åtkomst till den definierade proxyn.</span><span class="sxs-lookup"><span data-stu-id="2895c-224">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can't access the defined proxy.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2895c-225">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="2895c-225">Related topics</span></span>

- [<span data-ttu-id="2895c-226">Registrera Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="2895c-226">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="2895c-227">Felsöka problem med Introduktion till Slutpunkt för Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2895c-227">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
