---
title: Microsoft Defender för Endpoint för Mac
ms.reviewer: ''
description: Lär dig hur du installerar, konfigurerar, uppdaterar och använder Microsoft Defender för Slutpunkt för Mac.
keywords: microsoft, defender, atp, mac, installation, distribuera, avinstallation, intune, jamf, macos, big sur, catalina, mojave, mde för mac
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
ms.openlocfilehash: 22d35a42eb7fb7eadbba686c292729772951c05c
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500682"
---
# <a name="microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="354cd-104">Microsoft Defender för Endpoint för Mac</span><span class="sxs-lookup"><span data-stu-id="354cd-104">Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="354cd-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="354cd-105">**Applies to:**</span></span>
- [<span data-ttu-id="354cd-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="354cd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="354cd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="354cd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="354cd-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="354cd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="354cd-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="354cd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="354cd-110">I det här avsnittet beskrivs hur du installerar, konfigurerar, uppdaterar och använder Defender för Slutpunkt för Mac.</span><span class="sxs-lookup"><span data-stu-id="354cd-110">This topic describes how to install, configure, update, and use Defender for Endpoint for Mac.</span></span>

> [!CAUTION]
> <span data-ttu-id="354cd-111">Att köra andra slutpunktsskyddsprodukter från tredje part tillsammans med Microsoft Defender för Endpoint för Mac kan sannolikt leda till prestandaproblem och oförutsägbara sidoeffekter.</span><span class="sxs-lookup"><span data-stu-id="354cd-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint for Mac is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="354cd-112">Om skydd mot slutpunkter som inte är Microsoft är ett absolut krav i din miljö kan du ändå tryggt dra nytta av Defender för Endpoint för Mac EDR-funktioner när du har konfigurerat antivirusfunktionerna så att de körs i [passivt läge.](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="354cd-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint for Mac EDR functionality after configuring the antivirus functionality to run in [Passive mode](mac-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="whats-new-in-the-latest-release"></a><span data-ttu-id="354cd-113">Nyheter i den senaste versionen</span><span class="sxs-lookup"><span data-stu-id="354cd-113">What’s new in the latest release</span></span>

[<span data-ttu-id="354cd-114">Senaste nytt i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="354cd-114">What's new in Microsoft Defender for Endpoint</span></span>](whats-new-in-microsoft-defender-atp.md)

[<span data-ttu-id="354cd-115">Vad är nytt i Microsoft Defender för Slutpunkt för Mac</span><span class="sxs-lookup"><span data-stu-id="354cd-115">What's new in Microsoft Defender for Endpoint for Mac</span></span>](mac-whatsnew.md)

> [!TIP]
> <span data-ttu-id="354cd-116">Om du har några synpunkter som du vill dela kan du skicka in den genom att öppna Microsoft Defender för Endpoint för Mac på din enhet och gå till **Hjälp med** att  >  **skicka feedback.**</span><span class="sxs-lookup"><span data-stu-id="354cd-116">If you have any feedback that you would like to share, submit it by opening Microsoft Defender for Endpoint for Mac on your device and navigating to **Help** > **Send feedback**.</span></span>

<span data-ttu-id="354cd-117">För att få de senaste funktionerna, inklusive förhandsgranskningsfunktioner (till exempel identifiering av slutpunkt och svar för dina Mac-enheter), konfigurerar du din macOS-enhet som kör Microsoft Defender för Slutpunkt att vara en "Insider"-enhet.</span><span class="sxs-lookup"><span data-stu-id="354cd-117">To get the latest features, including preview capabilities (such as endpoint detection and response for your Mac devices), configure your macOS device running Microsoft Defender for Endpoint to be an "Insider" device.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="354cd-118">Så här installerar du Microsoft Defender för Slutpunkt för Mac</span><span class="sxs-lookup"><span data-stu-id="354cd-118">How to install Microsoft Defender for Endpoint for Mac</span></span>

### <a name="prerequisites"></a><span data-ttu-id="354cd-119">Krav</span><span class="sxs-lookup"><span data-stu-id="354cd-119">Prerequisites</span></span>

- <span data-ttu-id="354cd-120">En Defender för Endpoint-prenumeration och åtkomst till Microsoft Defender Säkerhetscenter-portalen</span><span class="sxs-lookup"><span data-stu-id="354cd-120">A Defender for Endpoint subscription and access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="354cd-121">Nybörjarupplevelse med macOS- och BASH-skript</span><span class="sxs-lookup"><span data-stu-id="354cd-121">Beginner-level experience in macOS and BASH scripting</span></span>
- <span data-ttu-id="354cd-122">Administratörsbehörigheter på enheten (vid manuell distribution)</span><span class="sxs-lookup"><span data-stu-id="354cd-122">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="354cd-123">Installationsanvisningar</span><span class="sxs-lookup"><span data-stu-id="354cd-123">Installation instructions</span></span>

<span data-ttu-id="354cd-124">Det finns flera metoder och distributionsverktyg som du kan använda för att installera och konfigurera Defender för Endpoint för Mac.</span><span class="sxs-lookup"><span data-stu-id="354cd-124">There are several methods and deployment tools that you can use to install and configure Defender for Endpoint for Mac.</span></span>

- <span data-ttu-id="354cd-125">Hanteringsverktyg från tredje part:</span><span class="sxs-lookup"><span data-stu-id="354cd-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="354cd-126">Microsoft Intune-baserad distribution</span><span class="sxs-lookup"><span data-stu-id="354cd-126">Microsoft Intune-based deployment</span></span>](mac-install-with-intune.md)
    - [<span data-ttu-id="354cd-127">JAMF-baserad distribution</span><span class="sxs-lookup"><span data-stu-id="354cd-127">JAMF-based deployment</span></span>](mac-install-with-jamf.md)
    - [<span data-ttu-id="354cd-128">Andra MDM-produkter</span><span class="sxs-lookup"><span data-stu-id="354cd-128">Other MDM products</span></span>](mac-install-with-other-mdm.md)

- <span data-ttu-id="354cd-129">Kommandoradsverktyget:</span><span class="sxs-lookup"><span data-stu-id="354cd-129">Command-line tool:</span></span>
    - [<span data-ttu-id="354cd-130">Manuell distribution</span><span class="sxs-lookup"><span data-stu-id="354cd-130">Manual deployment</span></span>](mac-install-manually.md)

### <a name="system-requirements"></a><span data-ttu-id="354cd-131">Systemkrav</span><span class="sxs-lookup"><span data-stu-id="354cd-131">System requirements</span></span>

<span data-ttu-id="354cd-132">De tre senaste större versionerna av macOS stöds.</span><span class="sxs-lookup"><span data-stu-id="354cd-132">The three most recent major releases of macOS are supported.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="354cd-133">På macOS 11 (Big Sur) kräver Microsoft Defender för Endpoint ytterligare konfigurationsprofiler.</span><span class="sxs-lookup"><span data-stu-id="354cd-133">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="354cd-134">Om du redan är kund och uppgraderar från tidigare versioner av macOS distribuerar du de ytterligare konfigurationsprofiler som finns listade i Nya konfigurationsprofiler för [macOS Catalina](mac-sysext-policies.md)och nyare versioner av macOS.</span><span class="sxs-lookup"><span data-stu-id="354cd-134">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [New configuration profiles for macOS Catalina and newer versions of macOS](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="354cd-135">Stöd för macOS 10.13 (High Sierra) har upphört från och med den 15 februari 2021.</span><span class="sxs-lookup"><span data-stu-id="354cd-135">Support for macOS 10.13 (High Sierra) has been discontinued as of February 15th, 2021.</span></span>

- <span data-ttu-id="354cd-136">11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave)</span><span class="sxs-lookup"><span data-stu-id="354cd-136">11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave)</span></span>
- <span data-ttu-id="354cd-137">Diskutrymme: 1 GB</span><span class="sxs-lookup"><span data-stu-id="354cd-137">Disk space: 1GB</span></span>

<span data-ttu-id="354cd-138">Betaversioner av macOS stöds inte.</span><span class="sxs-lookup"><span data-stu-id="354cd-138">Beta versions of macOS are not supported.</span></span>

<span data-ttu-id="354cd-139">När du har aktiverat tjänsten kan du behöva konfigurera nätverket eller brandväggen för att tillåta utgående anslutningar mellan den och dina slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="354cd-139">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="354cd-140">Licenskrav</span><span class="sxs-lookup"><span data-stu-id="354cd-140">Licensing requirements</span></span>

<span data-ttu-id="354cd-141">Microsoft Defender för Slutpunkt för Mac kräver något av följande Microsoft volymlicensieringserbjudanden:</span><span class="sxs-lookup"><span data-stu-id="354cd-141">Microsoft Defender for Endpoint for Mac requires one of the following Microsoft Volume Licensing offers:</span></span>

- <span data-ttu-id="354cd-142">Microsoft 365 E5 (M365 E5)</span><span class="sxs-lookup"><span data-stu-id="354cd-142">Microsoft 365 E5 (M365 E5)</span></span>
- <span data-ttu-id="354cd-143">Microsoft 365 E5 – säkerhet</span><span class="sxs-lookup"><span data-stu-id="354cd-143">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="354cd-144">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="354cd-144">Microsoft 365 A5 (M365 A5)</span></span>

> [!NOTE]
> <span data-ttu-id="354cd-145">Kvalificerade licensierade användare kan använda Microsoft Defender för Endpoint på upp till fem samtidiga enheter.</span><span class="sxs-lookup"><span data-stu-id="354cd-145">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="354cd-146">Microsoft Defender för Endpoint kan också köpas från en leverantör av molnlösningar (CSP).</span><span class="sxs-lookup"><span data-stu-id="354cd-146">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span> <span data-ttu-id="354cd-147">När microsoft volymlicensieringserbjudandena listas för dem när de köps via en microsoft-moln moln</span><span class="sxs-lookup"><span data-stu-id="354cd-147">When purchased via a CSP, it does not require Microsoft Volume Licensing offers listed.</span></span>

### <a name="network-connections"></a><span data-ttu-id="354cd-148">Nätverksanslutningar</span><span class="sxs-lookup"><span data-stu-id="354cd-148">Network connections</span></span>

<span data-ttu-id="354cd-149">I följande nedladdningsbara kalkylblad finns de tjänster och deras tillhörande URL:er som nätverket måste kunna ansluta till.</span><span class="sxs-lookup"><span data-stu-id="354cd-149">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="354cd-150">Du bör kontrollera att det inte finns några brandväggs- eller nätverksfiltreringsregler som nekar åtkomst till dessa URL:er, eller att du kan behöva skapa en *tillåta-regel* specifikt för dem.</span><span class="sxs-lookup"><span data-stu-id="354cd-150">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>



|<span data-ttu-id="354cd-151">**Kalkylblad med domänlista**</span><span class="sxs-lookup"><span data-stu-id="354cd-151">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="354cd-152">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="354cd-152">**Description**</span></span>|
|:-----|:-----|
|![Miniatyrbild för Microsoft Defender för slutpunkts-URL:er-kalkylblad](images/mdatp-urls.png)<br/>  | <span data-ttu-id="354cd-154">Kalkylblad med specifika DNS-poster för tjänstplatser, geografiska platser och operativsystem.</span><span class="sxs-lookup"><span data-stu-id="354cd-154">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br><span data-ttu-id="354cd-155">Ladda ned kalkylbladet här: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).</span><span class="sxs-lookup"><span data-stu-id="354cd-155">Download the spreadsheet here: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).</span></span>

<span data-ttu-id="354cd-156">Microsoft Defender för Endpoint kan identifiera en proxyserver med hjälp av följande identifieringsmetoder:</span><span class="sxs-lookup"><span data-stu-id="354cd-156">Microsoft Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="354cd-157">Autoconfig-proxy (PAC)</span><span class="sxs-lookup"><span data-stu-id="354cd-157">Proxy autoconfig (PAC)</span></span>
- <span data-ttu-id="354cd-158">Web Proxy Autodiscovery Protocol (WPAD)</span><span class="sxs-lookup"><span data-stu-id="354cd-158">Web Proxy Autodiscovery Protocol (WPAD)</span></span>
- <span data-ttu-id="354cd-159">Manuell statisk proxykonfiguration</span><span class="sxs-lookup"><span data-stu-id="354cd-159">Manual static proxy configuration</span></span>

<span data-ttu-id="354cd-160">Om en proxy eller brandvägg blockerar anonym trafik kontrollerar du att anonym trafik tillåts i tidigare angivna URL:er.</span><span class="sxs-lookup"><span data-stu-id="354cd-160">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="354cd-161">Autentiserad proxy.</span><span class="sxs-lookup"><span data-stu-id="354cd-161">Authenticated proxies are not supported.</span></span> <span data-ttu-id="354cd-162">Se till att endast PAC, WPAD eller en statisk proxy används.</span><span class="sxs-lookup"><span data-stu-id="354cd-162">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span>
>
> <span data-ttu-id="354cd-163">SSL-proxy proxy och skärningspunkt stöds inte heller av säkerhetsskäl.</span><span class="sxs-lookup"><span data-stu-id="354cd-163">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="354cd-164">Konfigurera ett undantag för SSL-kontroll och proxyservern för att direkt överföra data från Microsoft Defender för Endpoint för Mac till relevanta URL:er utan avlyssning.</span><span class="sxs-lookup"><span data-stu-id="354cd-164">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint for Mac to the relevant URLs without interception.</span></span> <span data-ttu-id="354cd-165">Om du lägger till ditt certifikat för avlyssning i det globala lagret tillåts inte avlyssning.</span><span class="sxs-lookup"><span data-stu-id="354cd-165">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="354cd-166">Testa att en anslutning inte är blockerad genom att öppna [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) och [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) i en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="354cd-166">To test that a connection is not blocked, open [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) and [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) in a browser.</span></span>

<span data-ttu-id="354cd-167">Om du föredrar kommandoraden kan du också kontrollera anslutningen genom att köra följande kommando i Terminal:</span><span class="sxs-lookup"><span data-stu-id="354cd-167">If you prefer the command line, you can also check the connection by running the following command in Terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="354cd-168">Utdata från det här kommandot bör se ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="354cd-168">The output from this command should be similar to the following:</span></span>

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> <span data-ttu-id="354cd-169">Vi rekommenderar att du fortsätter att [ha System Integrity Protection](https://support.apple.com/en-us/HT204899) (SIP) aktiverat på klientenheter.</span><span class="sxs-lookup"><span data-stu-id="354cd-169">We recommend that you keep [System Integrity Protection](https://support.apple.com/en-us/HT204899) (SIP) enabled on client devices.</span></span> <span data-ttu-id="354cd-170">SIP är en inbyggd säkerhetsfunktion i macOS som förhindrar att operativsystemet ändrar operativsystemet på låg nivå och är aktiverat som standard.</span><span class="sxs-lookup"><span data-stu-id="354cd-170">SIP is a built-in macOS security feature that prevents low-level tampering with the OS, and is enabled by default.</span></span>

<span data-ttu-id="354cd-171">När Microsoft Defender för slutpunkt har installerats kan anslutningen verifieras genom att köra följande kommando i terminalen:</span><span class="sxs-lookup"><span data-stu-id="354cd-171">Once Microsoft Defender for Endpoint is installed, connectivity can be validated by running the following command in Terminal:</span></span>
```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="354cd-172">Uppdatera Microsoft Defender för Slutpunkt för Mac</span><span class="sxs-lookup"><span data-stu-id="354cd-172">How to update Microsoft Defender for Endpoint for Mac</span></span>

<span data-ttu-id="354cd-173">Microsoft publicerar regelbundet programuppdateringar för att förbättra prestanda, säkerhet och för att leverera nya funktioner.</span><span class="sxs-lookup"><span data-stu-id="354cd-173">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="354cd-174">För att uppdatera Microsoft Defender för Slutpunkt för Mac används ett program med namnet Microsoft AutoUpdate (MAU).</span><span class="sxs-lookup"><span data-stu-id="354cd-174">To update Microsoft Defender for Endpoint for Mac, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="354cd-175">Mer information finns i [Distribuera uppdateringar för Microsoft Defender för Endpoint för Mac.](mac-updates.md)</span><span class="sxs-lookup"><span data-stu-id="354cd-175">To learn more, see [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="354cd-176">Konfigurera Microsoft Defender för Slutpunkt för Mac</span><span class="sxs-lookup"><span data-stu-id="354cd-176">How to configure Microsoft Defender for Endpoint for Mac</span></span>

<span data-ttu-id="354cd-177">Information om hur du konfigurerar produkten i företagsmiljöer finns i Ange [inställningar för Microsoft Defender för slutpunkt för Mac.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="354cd-177">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>

## <a name="macos-kernel-and-system-extensions"></a><span data-ttu-id="354cd-178">macOS kernel- och systemtillägg</span><span class="sxs-lookup"><span data-stu-id="354cd-178">macOS kernel and system extensions</span></span>

<span data-ttu-id="354cd-179">I linje med macOS-utveckling förbereder vi en Microsoft Defender för slutpunkt för Mac-uppdatering som utnyttjar systemtillägg istället för kernel-tillägg.</span><span class="sxs-lookup"><span data-stu-id="354cd-179">In alignment with macOS evolution, we are preparing a Microsoft Defender for Endpoint for Mac update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="354cd-180">Mer information finns i [Vad är nytt i Microsoft Defender för Endpoint för Mac.](mac-whatsnew.md)</span><span class="sxs-lookup"><span data-stu-id="354cd-180">For relevant details, see [What's new in Microsoft Defender for Endpoint for Mac](mac-whatsnew.md).</span></span>

## <a name="resources"></a><span data-ttu-id="354cd-181">Resurser</span><span class="sxs-lookup"><span data-stu-id="354cd-181">Resources</span></span>

- <span data-ttu-id="354cd-182">Mer information om loggning, avinstallation eller andra ämnen finns i Resurser [för Microsoft Defender för Slutpunkt för Mac.](mac-resources.md)</span><span class="sxs-lookup"><span data-stu-id="354cd-182">For more information about logging, uninstalling, or other topics, see [Resources for Microsoft Defender for Endpoint for Mac](mac-resources.md).</span></span>

- <span data-ttu-id="354cd-183">[Sekretess för Microsoft Defender för Endpoint för Mac](mac-privacy.md).</span><span class="sxs-lookup"><span data-stu-id="354cd-183">[Privacy for Microsoft Defender for Endpoint for Mac](mac-privacy.md).</span></span>
