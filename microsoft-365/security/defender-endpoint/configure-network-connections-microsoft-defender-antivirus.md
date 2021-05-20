---
title: Konfigurera och verifiera nätverksanslutningar för Microsoft Defender Antivirus
description: Konfigurera och testa anslutningen till Microsoft Defender Antivirus molnskyddstjänst.
keywords: antivirus, Microsoft Defender Antivirus, antimalware, säkerhet, försvarare, moln, aggressivitet, skyddsnivå
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ef5a9ffdf45a2f8e7f262ae7f969cd19e848b7a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572531"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a><span data-ttu-id="2ba14-104">Konfigurera och verifiera nätverksanslutningar för Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="2ba14-104">Configure and validate Microsoft Defender Antivirus network connections</span></span>

<span data-ttu-id="2ba14-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2ba14-105">**Applies to:**</span></span>

- [<span data-ttu-id="2ba14-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="2ba14-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="2ba14-107">För att Microsoft Defender Antivirus att det molnbaserade skyddet fungerar korrekt måste du konfigurera nätverket så att anslutningar mellan slutpunkterna och vissa Microsoft-servrar tillåts.</span><span class="sxs-lookup"><span data-stu-id="2ba14-107">To ensure Microsoft Defender Antivirus cloud-delivered protection works properly, you need to configure your network to allow connections between your endpoints and certain Microsoft servers.</span></span> <span data-ttu-id="2ba14-108">I den här artikeln visas de anslutningar som måste tillåtas, till exempel genom att använda brandväggsregler, och instruktioner för hur du validerar anslutningen.</span><span class="sxs-lookup"><span data-stu-id="2ba14-108">This article lists the connections that must be allowed, such as by using firewall rules, and provides instructions for validating your connection.</span></span> <span data-ttu-id="2ba14-109">Genom att konfigurera ditt skydd på rätt sätt kan du se till att du får det bästa värdet från dina molnbaserade skyddstjänster.</span><span class="sxs-lookup"><span data-stu-id="2ba14-109">Configuring your protection properly helps ensure that you receive the best value from your cloud-delivered protection services.</span></span>

<span data-ttu-id="2ba14-110">Se blogginlägget Viktiga [ändringar i Slutpunkten för Microsoft Active Protection Services för](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) viss information om nätverksanslutning.</span><span class="sxs-lookup"><span data-stu-id="2ba14-110">See the blog post [Important changes to Microsoft Active Protection Services endpoint](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) for some details about network connectivity.</span></span>

> [!TIP]
> <span data-ttu-id="2ba14-111">Du kan också besöka Microsoft Defender for Endpoint-demowebbplatsen [demo.wd.microsoft.com för](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) att bekräfta att följande funktioner fungerar:</span><span class="sxs-lookup"><span data-stu-id="2ba14-111">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
>
> - <span data-ttu-id="2ba14-112">Molnbaserat skydd</span><span class="sxs-lookup"><span data-stu-id="2ba14-112">Cloud-delivered protection</span></span>
> - <span data-ttu-id="2ba14-113">Snabb inlärning (inklusive block vid första anblicken)</span><span class="sxs-lookup"><span data-stu-id="2ba14-113">Fast learning (including block at first sight)</span></span>
> - <span data-ttu-id="2ba14-114">Potentiellt oönskad programblockering</span><span class="sxs-lookup"><span data-stu-id="2ba14-114">Potentially unwanted application blocking</span></span>

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a><span data-ttu-id="2ba14-115">Tillåt anslutningar till Microsoft Defender Antivirus molntjänst</span><span class="sxs-lookup"><span data-stu-id="2ba14-115">Allow connections to the Microsoft Defender Antivirus cloud service</span></span>

<span data-ttu-id="2ba14-116">Den Microsoft Defender Antivirus molntjänsten ger snabbt och starkt skydd för dina slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="2ba14-116">The Microsoft Defender Antivirus cloud service provides fast, strong protection for your endpoints.</span></span> <span data-ttu-id="2ba14-117">Att aktivera den molnbaserade skyddstjänsten är valfritt, men det rekommenderas starkt eftersom det ger viktigt skydd mot skadlig kod på dina slutpunkter och i hela nätverket.</span><span class="sxs-lookup"><span data-stu-id="2ba14-117">Enabling the cloud-delivered protection service is optional, however it's highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

> [!NOTE]
> <span data-ttu-id="2ba14-118">Den Microsoft Defender Antivirus molntjänsten är en mekanism för att leverera uppdaterat skydd till ditt nätverk och punkter.</span><span class="sxs-lookup"><span data-stu-id="2ba14-118">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="2ba14-119">Även om det kallas en molntjänst är det inte bara skydd för filer som lagras i molnet, utan använder distribuerade resurser och maskininlärning för att leverera skydd till dina punkter i en hastighet som är mycket snabbare än traditionella Security Intelligence-uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="2ba14-119">Although it's called a cloud service, it's not simply protection for files stored in the cloud, rather it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="2ba14-120">Se [Aktivera molnskydd för](enable-cloud-protection-microsoft-defender-antivirus.md) information om hur du aktiverar tjänsten med Intune, Microsoft Endpoint Configuration Manager, Grupprincip, PowerShell-cmdletar eller på enskilda klienter i Windows-säkerhet appen.</span><span class="sxs-lookup"><span data-stu-id="2ba14-120">See [Enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) for details on enabling the service with Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, or on individual clients in the Windows Security app.</span></span> 

<span data-ttu-id="2ba14-121">När du har aktiverat tjänsten kan du behöva konfigurera nätverket eller brandväggen för att tillåta anslutningar mellan den och slutpunkterna.</span><span class="sxs-lookup"><span data-stu-id="2ba14-121">After you've enabled the service, you may need to configure your network or firewall to allow connections between it and your endpoints.</span></span>

<span data-ttu-id="2ba14-122">Eftersom ditt skydd är en molntjänst måste datorer ha tillgång till Internet och nå Microsoft Defender för Office 365 maskininlärningstjänster.</span><span class="sxs-lookup"><span data-stu-id="2ba14-122">Because your protection is a cloud service, computers must have access to the internet and reach the Microsoft Defender for Office 365 machine learning services.</span></span> <span data-ttu-id="2ba14-123">Uteslut inte WEBBADRESSen `*.blob.core.windows.net` från någon form av nätverksinspektion.</span><span class="sxs-lookup"><span data-stu-id="2ba14-123">Don't exclude the URL `*.blob.core.windows.net` from any kind of network inspection.</span></span> 

<span data-ttu-id="2ba14-124">Tabellen nedan visar tjänsterna och tillhörande webbadresser.</span><span class="sxs-lookup"><span data-stu-id="2ba14-124">The table below lists the services and their associated URLs.</span></span> <span data-ttu-id="2ba14-125">Kontrollera att det inte finns några brandväggs- eller nätverksfiltreringsregler som nekar åtkomst till dessa webbadresser, eller att du kan behöva skapa en tillåt-regel specifikt för dem (exklusive WEBBADRESSen `*.blob.core.windows.net` ).</span><span class="sxs-lookup"><span data-stu-id="2ba14-125">Make sure that there are no firewall or network filtering rules denying access to these URLs, or you may need to create an allow rule specifically for them (excluding the URL `*.blob.core.windows.net`).</span></span> <span data-ttu-id="2ba14-126">Nedan nämns webbadresser använder port 443 för kommunikation.</span><span class="sxs-lookup"><span data-stu-id="2ba14-126">Below mention URLs are using port 443 for communication.</span></span>


| <span data-ttu-id="2ba14-127">**Tjänst**</span><span class="sxs-lookup"><span data-stu-id="2ba14-127">**Service**</span></span>| <span data-ttu-id="2ba14-128">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="2ba14-128">**Description**</span></span> |<span data-ttu-id="2ba14-129">**URL**</span><span class="sxs-lookup"><span data-stu-id="2ba14-129">**URL**</span></span> |
| :--: | :-- | :-- |
| <span data-ttu-id="2ba14-130">Microsoft Defender Antivirus molnbaserad skyddstjänst, även kallad Microsoft Active Protection Service (MAPS)</span><span class="sxs-lookup"><span data-stu-id="2ba14-130">Microsoft Defender Antivirus cloud-delivered protection service, also referred to as Microsoft Active Protection Service (MAPS)</span></span>|<span data-ttu-id="2ba14-131">Används av Microsoft Defender Antivirus för att ge molnskydd</span><span class="sxs-lookup"><span data-stu-id="2ba14-131">Used by Microsoft Defender Antivirus to provide cloud-delivered protection</span></span>|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| <span data-ttu-id="2ba14-132">Mu (Microsoft Update Service)</span><span class="sxs-lookup"><span data-stu-id="2ba14-132">Microsoft Update Service (MU)</span></span> <br/> <span data-ttu-id="2ba14-133">Windows Wu (Update Service)</span><span class="sxs-lookup"><span data-stu-id="2ba14-133">Windows Update Service (WU)</span></span>|  <span data-ttu-id="2ba14-134">Säkerhetsintelligens och produktuppdateringar</span><span class="sxs-lookup"><span data-stu-id="2ba14-134">Security intelligence and product updates</span></span>   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> <span data-ttu-id="2ba14-135">Mer information finns [i Anslutningsslutpunkter för Windows Uppdatering](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span><span class="sxs-lookup"><span data-stu-id="2ba14-135">For details see [Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span></span>|
|<span data-ttu-id="2ba14-136">Security Intelligence uppdaterar alternativ nedladdningsplats (ADL)</span><span class="sxs-lookup"><span data-stu-id="2ba14-136">Security intelligence updates Alternate Download Location (ADL)</span></span>|   <span data-ttu-id="2ba14-137">Alternativ plats för Microsoft Defender Antivirus Security Intelligence-uppdateringar om den installerade säkerhetsintelligensen är in dated (7 eller fler dagar efter)</span><span class="sxs-lookup"><span data-stu-id="2ba14-137">Alternate location for Microsoft Defender Antivirus Security intelligence updates if the installed Security intelligence is out of date (7 or more days behind)</span></span>|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br>  `go.microsoft.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| <span data-ttu-id="2ba14-138">Lagring av skadlig kod</span><span class="sxs-lookup"><span data-stu-id="2ba14-138">Malware submission storage</span></span>|<span data-ttu-id="2ba14-139">Upload plats för filer som skickas till Microsoft via formuläret Inlämning eller automatisk exempelinlämning</span><span class="sxs-lookup"><span data-stu-id="2ba14-139">Upload location for files submitted to Microsoft via the Submission form or automatic sample submission</span></span>    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| <span data-ttu-id="2ba14-140">Lista över återkallade certifikat (CRL)</span><span class="sxs-lookup"><span data-stu-id="2ba14-140">Certificate Revocation List (CRL)</span></span>|<span data-ttu-id="2ba14-141">Används av Windows när du skapar SSL-anslutningen till MAPS för uppdatering av listan över återkallade certifikat</span><span class="sxs-lookup"><span data-stu-id="2ba14-141">Used by Windows when creating the SSL connection to MAPS for updating the CRL</span></span>   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| <span data-ttu-id="2ba14-142">Symbol butik</span><span class="sxs-lookup"><span data-stu-id="2ba14-142">Symbol Store</span></span>|<span data-ttu-id="2ba14-143">Används av Microsoft Defender Antivirus för att återställa vissa kritiska filer under reparationsflöden</span><span class="sxs-lookup"><span data-stu-id="2ba14-143">Used by Microsoft Defender Antivirus to restore certain critical files during remediation flows</span></span>  | `https://msdl.microsoft.com/download/symbols` |
| <span data-ttu-id="2ba14-144">Universell telemetriklient</span><span class="sxs-lookup"><span data-stu-id="2ba14-144">Universal Telemetry Client</span></span>| <span data-ttu-id="2ba14-145">Används av Windows för att skicka klientdiagnostikdata; Microsoft Defender Antivirus använder telemetri för produktkvalitetsövervakning</span><span class="sxs-lookup"><span data-stu-id="2ba14-145">Used by Windows to send client diagnostic data; Microsoft Defender Antivirus uses telemetry for product quality monitoring purposes</span></span>   | <span data-ttu-id="2ba14-146">Uppdateringen använder SSL (TCP Port 443) för att hämta manifest och ladda upp diagnostikdata till Microsoft som använder följande DNS-slutpunkter:   `vortex-win.data.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="2ba14-146">The update uses SSL (TCP Port 443) to download manifests and upload diagnostic data to Microsoft that uses the following DNS endpoints:   `vortex-win.data.microsoft.com`</span></span> <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a><span data-ttu-id="2ba14-147">Validera anslutningar mellan nätverket och molnet</span><span class="sxs-lookup"><span data-stu-id="2ba14-147">Validate connections between your network and the cloud</span></span>

<span data-ttu-id="2ba14-148">När du har tillåtit webbadresserna ovan kan du testa om du är ansluten till molntjänsten Microsoft Defender Antivirus och rapporterar och tar emot information korrekt för att säkerställa att du är helt skyddad.</span><span class="sxs-lookup"><span data-stu-id="2ba14-148">After allowing the URLs listed above, you can test if you're connected to the Microsoft Defender Antivirus cloud service and are correctly reporting and receiving information to ensure you're fully protected.</span></span>

<span data-ttu-id="2ba14-149">**Använd cmdline-verktyget för att validera molnskydd:**</span><span class="sxs-lookup"><span data-stu-id="2ba14-149">**Use the cmdline tool to validate cloud-delivered protection:**</span></span>

<span data-ttu-id="2ba14-150">Använd följande argument med kommandoradsverktyget Microsoft Defender Antivirus `mpcmdrun.exe` ( ) för att verifiera att nätverket kan kommunicera med Microsoft Defender Antivirus molntjänst:</span><span class="sxs-lookup"><span data-stu-id="2ba14-150">Use the following argument with the Microsoft Defender Antivirus command-line utility (`mpcmdrun.exe`) to verify that your network can communicate with the Microsoft Defender Antivirus cloud service:</span></span>

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> <span data-ttu-id="2ba14-151">Du måste öppna en version på administratörsnivå av kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="2ba14-151">You need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="2ba14-152">Högerklicka på objektet på Start-menyn, klicka på **Kör som administratör och** klicka på **Ja** vid behörighetsprompten.</span><span class="sxs-lookup"><span data-stu-id="2ba14-152">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span> <span data-ttu-id="2ba14-153">Det här kommandot fungerar bara Windows 10, version 1703 eller senare.</span><span class="sxs-lookup"><span data-stu-id="2ba14-153">This command will only work on Windows 10, version 1703 or higher.</span></span>

<span data-ttu-id="2ba14-154">Mer information finns i [Hantera Microsoft Defender Antivirus med mpcmdrun.exe kommandoradsverktyget](command-line-arguments-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="2ba14-154">For more information, see [Manage Microsoft Defender Antivirus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="2ba14-155">**Försök att ladda ner en falsk skadlig fil från Microsoft:**</span><span class="sxs-lookup"><span data-stu-id="2ba14-155">**Attempt to download a fake malware file from Microsoft:**</span></span>

<span data-ttu-id="2ba14-156">Du kan hämta en exempelfil Microsoft Defender Antivirus kommer att upptäcka och blockera om du är korrekt ansluten till molnet.</span><span class="sxs-lookup"><span data-stu-id="2ba14-156">You can download a sample file that Microsoft Defender Antivirus will detect and block if you're properly connected to the cloud.</span></span>

<span data-ttu-id="2ba14-157">Ladda ner filen genom att besöka [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .</span><span class="sxs-lookup"><span data-stu-id="2ba14-157">Download the file by visiting [https://aka.ms/ioavtest](https://aka.ms/ioavtest).</span></span>

> [!NOTE]
> <span data-ttu-id="2ba14-158">Den här filen är inte en faktisk bit av skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="2ba14-158">This file is not an actual piece of malware.</span></span> <span data-ttu-id="2ba14-159">Det är en falsk fil som är utformad för att testa om du är korrekt ansluten till molnet.</span><span class="sxs-lookup"><span data-stu-id="2ba14-159">It's a fake file that is designed to test if you're properly connected to the cloud.</span></span>

<span data-ttu-id="2ba14-160">Om du är korrekt ansluten visas en varning Microsoft Defender Antivirus meddelande.</span><span class="sxs-lookup"><span data-stu-id="2ba14-160">If you're properly connected, you'll see a warning Microsoft Defender Antivirus notification.</span></span>

<span data-ttu-id="2ba14-161">Om du använder Microsoft Edge visas också ett meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ba14-161">If you're using Microsoft Edge, you'll also see a notification message:</span></span>

![Microsoft Edge informera användaren om att skadlig programvara hittades](images/defender/wdav-bafs-edge.png)

<span data-ttu-id="2ba14-163">Ett liknande meddelande visas om du använder Internet Explorer:</span><span class="sxs-lookup"><span data-stu-id="2ba14-163">A similar message occurs if you're using Internet Explorer:</span></span>

![Microsoft Defender Antivirus meddelande som informerar användaren om att skadlig kod hittades](images/defender/wdav-bafs-ie.png)

<span data-ttu-id="2ba14-165">Du ser också en identifiering under **Karantänhot i** avsnittet Skanna **historik** i Windows-säkerhet appen:</span><span class="sxs-lookup"><span data-stu-id="2ba14-165">You'll also see a detection under **Quarantined threats** in the **Scan history** section in the Windows Security app:</span></span>

1. <span data-ttu-id="2ba14-166">Öppna appen Windows-säkerhet genom att klicka på sköldikonen i Aktivitetsfältet eller söka på Start-menyn för **Säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="2ba14-166">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="2ba14-167">Välj **Virus & hotskydd** och välj sedan **Skyddshistorik**.</span><span class="sxs-lookup"><span data-stu-id="2ba14-167">Select **Virus & threat protection**, and then select **Protection history**.</span></span>

3. <span data-ttu-id="2ba14-168">Under avsnittet **Karantänhot väljer du** Se fullständig **historik för att** se den upptäckta falska skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="2ba14-168">Under the **Quarantined threats** section, select **See full history** to see the detected fake malware.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2ba14-169">Versioner av Windows 10 före version 1703 har ett annat användargränssnitt.</span><span class="sxs-lookup"><span data-stu-id="2ba14-169">Versions of Windows 10 before version 1703 have a different user interface.</span></span> <span data-ttu-id="2ba14-170">Se [Microsoft Defender Antivirus i Windows-säkerhet appen](microsoft-defender-security-center-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="2ba14-170">See [Microsoft Defender Antivirus in the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

   <span data-ttu-id="2ba14-171">Händelseloggen Windows visas också [Windows Defender 1116 för klienthändelse.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="2ba14-171">The Windows event log will also show [Windows Defender client event ID 1116](troubleshoot-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="2ba14-172">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="2ba14-172">Related articles</span></span>

- [<span data-ttu-id="2ba14-173">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="2ba14-173">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="2ba14-174">Aktivera molnbaserat skydd</span><span class="sxs-lookup"><span data-stu-id="2ba14-174">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="2ba14-175">Argument för kommandorad</span><span class="sxs-lookup"><span data-stu-id="2ba14-175">Command line arguments</span></span>](command-line-arguments-microsoft-defender-antivirus.md)

- [<span data-ttu-id="2ba14-176">Viktiga ändringar i slutpunkten för Microsoft Active Protection Services</span><span class="sxs-lookup"><span data-stu-id="2ba14-176">Important changes to Microsoft Active Protection Services endpoint</span></span>](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)
