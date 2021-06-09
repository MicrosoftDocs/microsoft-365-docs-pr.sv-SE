---
title: Felsöka problem med livesvar i Microsoft Defender för Endpoint
description: Felsöka problem som kan uppstå när du använder livesvar i Microsoft Defender för Slutpunkt
keywords: felsöka livesvar, live, svar, låst, fil
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
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 99a52188dd5f6eca2f8368aa3c114d0bfb950b10
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844160"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a><span data-ttu-id="7fb35-104">Felsöka problem med livesvar i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="7fb35-104">Troubleshoot Microsoft Defender for Endpoint live response issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7fb35-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7fb35-105">**Applies to:**</span></span>
- [<span data-ttu-id="7fb35-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="7fb35-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7fb35-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7fb35-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7fb35-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="7fb35-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7fb35-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="7fb35-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="7fb35-110">På den här sidan finns detaljerade anvisningar för felsökning av problem med livesvar.</span><span class="sxs-lookup"><span data-stu-id="7fb35-110">This page provides detailed steps to troubleshoot live response issues.</span></span>

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a><span data-ttu-id="7fb35-111">Det går inte att komma åt filen under svarssessioner i livesändning</span><span class="sxs-lookup"><span data-stu-id="7fb35-111">File cannot be accessed during live response sessions</span></span>
<span data-ttu-id="7fb35-112">Om du stöter på ett felmeddelande när du försöker vidta en åtgärd under en svarssession och du får ett felmeddelande som säger att filen inte kan kommas åt måste du följa stegen nedan för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="7fb35-112">If while trying to take an action during a live response session, you encounter an error message stating that the file can't be accessed, you'll need to use the steps below to address the issue.</span></span>

1. <span data-ttu-id="7fb35-113">Kopiera följande skriptkodavsnitt och spara det som en PS1-fil:</span><span class="sxs-lookup"><span data-stu-id="7fb35-113">Copy the following script code snippet and save it as a PS1 file:</span></span>

    ```
    $copied_file_path=$args[0] 
    $action=Copy-Item $copied_file_path -Destination $env:TEMP -PassThru -ErrorAction silentlyContinue
        
    if ($action){
         Write-Host "You copied the file specified in $copied_file_path to $env:TEMP Succesfully"
    }
    
    else{
        Write-Output "Error occoured while trying to copy a file, details:"
        Write-Output  $error[0].exception.message
 
    }
    ```


2. <span data-ttu-id="7fb35-114">Lägg till skriptet i livesvarsbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="7fb35-114">Add the script to the live response library.</span></span>
3. <span data-ttu-id="7fb35-115">Kör skriptet med en parameter: filsökvägen för den fil som ska kopieras.</span><span class="sxs-lookup"><span data-stu-id="7fb35-115">Run the script with one parameter: the file path of the file to be copied.</span></span>
4. <span data-ttu-id="7fb35-116">Navigera till TEMP-mappen.</span><span class="sxs-lookup"><span data-stu-id="7fb35-116">Navigate to your TEMP folder.</span></span>
5. <span data-ttu-id="7fb35-117">Kör den åtgärd du vill vidta för den kopierade filen.</span><span class="sxs-lookup"><span data-stu-id="7fb35-117">Run the action you wanted to take on the copied file.</span></span>

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a><span data-ttu-id="7fb35-118">Långsamma svarssessioner eller fördröjningar vid initiala anslutningar</span><span class="sxs-lookup"><span data-stu-id="7fb35-118">Slow live response sessions or delays during initial connections</span></span>
<span data-ttu-id="7fb35-119">Live Response utnyttjar Defender för slutpunkts sensorregistrering med WNS-tjänsten i Windows.</span><span class="sxs-lookup"><span data-stu-id="7fb35-119">Live response leverages Defender for Endpoint sensor registration with WNS service in Windows.</span></span> <span data-ttu-id="7fb35-120">Om du har anslutningsproblem med live-svar bekräftar du följande information:</span><span class="sxs-lookup"><span data-stu-id="7fb35-120">If you are having connectivity issues with live response, confirm the following details:</span></span>
1. <span data-ttu-id="7fb35-121">`notify.windows.com` inte är blockerad i din miljö.</span><span class="sxs-lookup"><span data-stu-id="7fb35-121">`notify.windows.com` is not blocked in your environment.</span></span> <span data-ttu-id="7fb35-122">Mer information finns i Konfigurera [enhetsproxy och Internetanslutningsinställningar.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="7fb35-122">For more information, see, [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>
2. <span data-ttu-id="7fb35-123">WpnService (Windows Push Notifications System Service) inaktiveras inte.</span><span class="sxs-lookup"><span data-stu-id="7fb35-123">WpnService (Windows Push Notifications System Service) is not disabled.</span></span>

<span data-ttu-id="7fb35-124">Läs artiklarna nedan för fullständig förståelse av WpnService-tjänstens beteende och krav:</span><span class="sxs-lookup"><span data-stu-id="7fb35-124">Refer to the articles below to fully understand the WpnService service behavior and requirements:</span></span>
- [<span data-ttu-id="7fb35-125">Windows Översikt över Push Notification Services (WNS)</span><span class="sxs-lookup"><span data-stu-id="7fb35-125">Windows Push Notification Services (WNS) overview</span></span>](/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [<span data-ttu-id="7fb35-126">Företagsbrandväggs- och proxykonfigurationer för stöd för WNS-trafik</span><span class="sxs-lookup"><span data-stu-id="7fb35-126">Enterprise Firewall and Proxy Configurations to Support WNS Traffic</span></span>](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [<span data-ttu-id="7fb35-127">Offentliga IP-intervall för Microsoft Push Notifications Service (MPNS)</span><span class="sxs-lookup"><span data-stu-id="7fb35-127">Microsoft Push Notifications Service (MPNS) Public IP ranges</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=44535)

