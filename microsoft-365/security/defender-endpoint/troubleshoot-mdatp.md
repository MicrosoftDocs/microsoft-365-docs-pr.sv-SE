---
title: Felsöka tjänsteproblem med Microsoft Defender för Endpoint
description: Hitta lösningar och lösningar på kända problem, till exempel serverfel när du försöker komma åt tjänsten.
keywords: felsöka Microsoft Defender för slutpunkt, serverfel, åtkomst nekad, ogiltiga autentiseringsuppgifter, inga data, instrumentpanelsportal, tillåt, loggboken
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
ms.openlocfilehash: 8aaea65c617300a16f99a9a3e3a62d94b7983198
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538357"
---
# <a name="troubleshoot-service-issues"></a><span data-ttu-id="b0682-104">Felsöka tjänstproblem</span><span class="sxs-lookup"><span data-stu-id="b0682-104">Troubleshoot service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b0682-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b0682-105">**Applies to:**</span></span>
- [<span data-ttu-id="b0682-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="b0682-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b0682-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0682-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b0682-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="b0682-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b0682-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="b0682-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="b0682-110">I det här avsnittet behandlas problem som kan uppstå när du använder Tjänsten Microsoft Defender för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="b0682-110">This section addresses issues that might arise as you use the Microsoft Defender for Endpoint service.</span></span>

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a><span data-ttu-id="b0682-111">Serverfel – Åtkomst nekas på grund av ogiltiga autentiseringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="b0682-111">Server error - Access is denied due to invalid credentials</span></span>
<span data-ttu-id="b0682-112">Om det uppstår ett serverfel när du försöker komma åt tjänsten måste du ändra inställningarna för webbläsarens cookie.</span><span class="sxs-lookup"><span data-stu-id="b0682-112">If you encounter a server error when trying to access the service, you’ll need to change your browser cookie settings.</span></span>
<span data-ttu-id="b0682-113">Konfigurera webbläsaren så att den tillåter cookies.</span><span class="sxs-lookup"><span data-stu-id="b0682-113">Configure your browser to allow cookies.</span></span>

## <a name="elements-or-data-missing-on-the-portal"></a><span data-ttu-id="b0682-114">Element eller data saknas på portalen</span><span class="sxs-lookup"><span data-stu-id="b0682-114">Elements or data missing on the portal</span></span>
<span data-ttu-id="b0682-115">Om vissa element eller data saknas på Microsoft Defender Säkerhetscenter det möjligt att proxyinställningarna blockerar den.</span><span class="sxs-lookup"><span data-stu-id="b0682-115">If some elements or data is missing on Microsoft Defender Security Center it’s possible that proxy settings are blocking it.</span></span>

<span data-ttu-id="b0682-116">Se till att `*.securitycenter.windows.com` finns med i listan över tillåtna proxyservrar.</span><span class="sxs-lookup"><span data-stu-id="b0682-116">Make sure that `*.securitycenter.windows.com` is included the proxy allowlist.</span></span>


> [!NOTE]
> <span data-ttu-id="b0682-117">Du måste använda HTTPS-protokollet när du lägger till följande slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="b0682-117">You must use the HTTPS protocol when adding the following endpoints.</span></span>

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a><span data-ttu-id="b0682-118">Microsoft Defender för slutpunktstjänsten visar händelse- eller felloggar i loggboken</span><span class="sxs-lookup"><span data-stu-id="b0682-118">Microsoft Defender for Endpoint service shows event or error logs in the Event Viewer</span></span>

<span data-ttu-id="b0682-119">Se [Granska händelser och fel med hjälp av Loggboken](event-error-codes.md) för en lista över händelse-IDt som rapporterats av Microsoft Defender för slutpunktstjänsten.</span><span class="sxs-lookup"><span data-stu-id="b0682-119">See [Review events and errors using Event Viewer](event-error-codes.md) for a list of event IDs that are reported by the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="b0682-120">Artikeln innehåller även felsökningssteg för händelsefel.</span><span class="sxs-lookup"><span data-stu-id="b0682-120">The article also contains troubleshooting steps for event errors.</span></span>

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a><span data-ttu-id="b0682-121">Microsoft Defender för slutpunktstjänsten startar inte efter en omstart och visar felet 577</span><span class="sxs-lookup"><span data-stu-id="b0682-121">Microsoft Defender for Endpoint service fails to start after a reboot and shows error 577</span></span>

<span data-ttu-id="b0682-122">Om onboarding-enheter slutförs men Microsoft Defender för Endpoint inte startar efter en omstart och felmeddelande 577 visas kontrollerar du att Windows Defender inaktiveras av en princip.</span><span class="sxs-lookup"><span data-stu-id="b0682-122">If onboarding devices successfully completes but Microsoft Defender for Endpoint does not start after a reboot and shows error 577, check that Windows Defender is not disabled by a policy.</span></span>

<span data-ttu-id="b0682-123">Mer information finns i Se [till att Microsoft Defender Antivirus inaktiveras av principen.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</span><span class="sxs-lookup"><span data-stu-id="b0682-123">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>

## <a name="known-issues-with-regional-formats"></a><span data-ttu-id="b0682-124">Kända problem med nationella format</span><span class="sxs-lookup"><span data-stu-id="b0682-124">Known issues with regional formats</span></span>

<span data-ttu-id="b0682-125">**Datum- och tidsformat**</span><span class="sxs-lookup"><span data-stu-id="b0682-125">**Date and time formats**</span></span><br>
<span data-ttu-id="b0682-126">Det finns några kända problem med tids- och datumformat.</span><span class="sxs-lookup"><span data-stu-id="b0682-126">There are some known issues with the time and date formats.</span></span> 

<span data-ttu-id="b0682-127">Följande datumformat stöds:</span><span class="sxs-lookup"><span data-stu-id="b0682-127">The following date formats are supported:</span></span>
- <span data-ttu-id="b0682-128">MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="b0682-128">MM/dd/yyyy</span></span>
- <span data-ttu-id="b0682-129">dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="b0682-129">dd/MM/yyyy</span></span>

<span data-ttu-id="b0682-130">Följande datum- och tidsformat stöds för närvarande inte:</span><span class="sxs-lookup"><span data-stu-id="b0682-130">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="b0682-131">Datumformat yyyy/MM/dd</span><span class="sxs-lookup"><span data-stu-id="b0682-131">Date format yyyy/MM/dd</span></span>
- <span data-ttu-id="b0682-132">Datumformat dd/MM/yy</span><span class="sxs-lookup"><span data-stu-id="b0682-132">Date format dd/MM/yy</span></span>
- <span data-ttu-id="b0682-133">Datumformat med yy.</span><span class="sxs-lookup"><span data-stu-id="b0682-133">Date format with yy.</span></span> <span data-ttu-id="b0682-134">Kommer bara att visa yyyy.</span><span class="sxs-lookup"><span data-stu-id="b0682-134">Will only show yyyy.</span></span>
- <span data-ttu-id="b0682-135">Tidsformatet HH:mm:ss stöds inte (formatet 12 timmar/EM stöds inte).</span><span class="sxs-lookup"><span data-stu-id="b0682-135">Time format HH:mm:ss is not supported (the 12 hour AM/PM format is not supported).</span></span> <span data-ttu-id="b0682-136">Endast 24-timmarsformatet stöds.</span><span class="sxs-lookup"><span data-stu-id="b0682-136">Only the 24-hour format is supported.</span></span>

<span data-ttu-id="b0682-137">**Användning av kommatecken för att ange tusental**</span><span class="sxs-lookup"><span data-stu-id="b0682-137">**Use of comma to indicate thousand**</span></span><br>
<span data-ttu-id="b0682-138">Stöd för användning av kommatecken som avgränsare i tal stöds inte.</span><span class="sxs-lookup"><span data-stu-id="b0682-138">Support of use of comma as a separator in numbers are not supported.</span></span> <span data-ttu-id="b0682-139">Regioner där ett tal avgränsas med ett kommatecken som anger tusen, ser bara användningen av en punkt som avgränsare.</span><span class="sxs-lookup"><span data-stu-id="b0682-139">Regions where a number is separated with a comma to indicate a thousand, will only see the use of a dot as a separator.</span></span> <span data-ttu-id="b0682-140">Till exempel visas 15,5K som 15,5K.</span><span class="sxs-lookup"><span data-stu-id="b0682-140">For example, 15,5K is displayed as 15.5K.</span></span>

><span data-ttu-id="b0682-141">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="b0682-141">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b0682-142">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="b0682-142">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a><span data-ttu-id="b0682-143">Microsoft Defender för slutpunktsklientorganisationen skapades automatiskt i Europa</span><span class="sxs-lookup"><span data-stu-id="b0682-143">Microsoft Defender for Endpoint tenant was automatically created in Europe</span></span>
<span data-ttu-id="b0682-144">När du använder Azure Defender för att övervaka servrar skapas automatiskt en Microsoft Defender för slutpunktsklientorganisation.</span><span class="sxs-lookup"><span data-stu-id="b0682-144">When you use Azure Defender to monitor servers, a Microsoft Defender for Endpoint tenant is automatically created.</span></span> <span data-ttu-id="b0682-145">Microsoft Defender för slutpunktsdata lagras i Europa som standard.</span><span class="sxs-lookup"><span data-stu-id="b0682-145">The Microsoft Defender for Endpoint data is stored in Europe by default.</span></span>





## <a name="related-topics"></a><span data-ttu-id="b0682-146">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="b0682-146">Related topics</span></span>
- [<span data-ttu-id="b0682-147">Felsöka problem med Introduktion till Slutpunkt för Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b0682-147">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
- [<span data-ttu-id="b0682-148">Granska händelser och fel med hjälp av Loggboken</span><span class="sxs-lookup"><span data-stu-id="b0682-148">Review events and errors using Event Viewer</span></span>](event-error-codes.md)
