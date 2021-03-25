---
title: Använda nätverksskydd för att förhindra anslutningar till dåliga webbplatser
description: Skydda nätverket genom att hindra användare från att komma åt kända skadliga och misstänkta nätverksadresser
keywords: Nätverksskydd, sårbarheter, skadlig webbplats, ip, domän, domäner
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.date: 03/08/2021
ms.topic: how-to
ms.openlocfilehash: be98bf810d00b6e39ba9d2674604a9fd2128a8cc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198665"
---
# <a name="protect-your-network"></a><span data-ttu-id="6157b-104">Skydda ditt nätverk</span><span class="sxs-lookup"><span data-stu-id="6157b-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6157b-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6157b-105">**Applies to:**</span></span>
- [<span data-ttu-id="6157b-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="6157b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6157b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6157b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6157b-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="6157b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6157b-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="6157b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="6157b-110">Nätverksskydd hjälper till att minska enheternas attackytor från Internetbaserade händelser.</span><span class="sxs-lookup"><span data-stu-id="6157b-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="6157b-111">Det förhindrar anställda att använda något program för att komma åt skadliga domäner som kan vara värdar för nätfiske, sårbarheter och annat skadligt innehåll på Internet.</span><span class="sxs-lookup"><span data-stu-id="6157b-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="6157b-112">Nätverksskyddet utökar Omfattningen av [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) för att blockera all utgående HTTP-trafik som försöker ansluta till ryktes beryka källor (baserat på domän eller värdnamn).</span><span class="sxs-lookup"><span data-stu-id="6157b-112">Network protection expands the scope of [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="6157b-113">Nätverksskydd stöds i Windows från och med Windows 10, version 1709.</span><span class="sxs-lookup"><span data-stu-id="6157b-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> 

<span data-ttu-id="6157b-114">Mer information om hur du aktiverar nätverksskydd finns [i Aktivera nätverksskydd.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="6157b-114">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="6157b-115">Använd grupprinciper, PowerShell och MDM-CSP:er för att aktivera och hantera nätverksskydd i nätverket.</span><span class="sxs-lookup"><span data-stu-id="6157b-115">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="6157b-116">Se webbplatsen för Microsoft Defender ATP-testfält [på demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) om du vill se hur nätverksskyddet fungerar.</span><span class="sxs-lookup"><span data-stu-id="6157b-116">See the Microsoft Defender ATP testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="6157b-117">Nätverksskyddet fungerar bäst med [Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)för Endpoint , som ger dig detaljerad rapportering om sårbarhetsskyddshändelser och -block som en del av scenarier [för aviseringsundersökning.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="6157b-117">Network protection works best with [Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="6157b-118">När nätverksskydd blockerar en anslutning visas ett meddelande från Åtgärdscenter.</span><span class="sxs-lookup"><span data-stu-id="6157b-118">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="6157b-119">Ditt säkerhetsteam kan [anpassa meddelandet](customize-attack-surface-reduction.md#customize-the-notification) med organisationens information och kontaktinformation.</span><span class="sxs-lookup"><span data-stu-id="6157b-119">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="6157b-120">Dessutom kan regler för att minska attackytan aktiveras och anpassas så att de passar vissa tekniker att övervaka.</span><span class="sxs-lookup"><span data-stu-id="6157b-120">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="6157b-121">Du kan också använda [granskningsläge](audit-windows-defender.md) för att utvärdera hur nätverksskydd skulle påverka organisationen om det var aktiverat.</span><span class="sxs-lookup"><span data-stu-id="6157b-121">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="6157b-122">Krav</span><span class="sxs-lookup"><span data-stu-id="6157b-122">Requirements</span></span>

<span data-ttu-id="6157b-123">Nätverksskydd kräver Windows 10 Pro eller Enterprise och realtidsskydd i Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="6157b-123">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="6157b-124">Windows-version</span><span class="sxs-lookup"><span data-stu-id="6157b-124">Windows version</span></span> | <span data-ttu-id="6157b-125">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="6157b-125">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="6157b-126">Windows 10 version 1709 eller senare</span><span class="sxs-lookup"><span data-stu-id="6157b-126">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="6157b-127">Windows Server 1803 eller senare</span><span class="sxs-lookup"><span data-stu-id="6157b-127">Windows Server 1803 or later</span></span> | <span data-ttu-id="6157b-128">[Realtidsskydd och moln levererat skydd](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) [i](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) Microsoft Defender Antivirus måste vara aktiverat</span><span class="sxs-lookup"><span data-stu-id="6157b-128">[Microsoft Defender Antivirus real-time protection](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="6157b-129">När du har aktiverat tjänsterna kan du behöva konfigurera nätverket eller brandväggen så att anslutningarna mellan tjänsterna och dina enheter tillåts (kallas även slutpunkter).</span><span class="sxs-lookup"><span data-stu-id="6157b-129">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- <span data-ttu-id="6157b-130">.smartscreen.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6157b-130">.smartscreen.microsoft.com</span></span>
- <span data-ttu-id="6157b-131">.smartscreen-prod.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6157b-131">.smartscreen-prod.microsoft.com</span></span>

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="6157b-132">Granska nätverksskyddshändelser i Microsoft Defender för Endpoint Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="6157b-132">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="6157b-133">Microsoft Defender för Endpoint tillhandahåller detaljerad rapportering om händelser och block som en del av dess scenarier [för aviseringsundersökning.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="6157b-133">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="6157b-134">Du kan fråga Microsoft Defender efter Slutpunktsdata med hjälp av [Avancerad sökning](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="6157b-134">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="6157b-135">Om du använder granskningsläge [kan du](audit-windows-defender.md)använda avancerad sökning för att se hur inställningarna för nätverksskydd skulle påverka din miljö om de var aktiverade.</span><span class="sxs-lookup"><span data-stu-id="6157b-135">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="6157b-136">Här är en exempelfråga</span><span class="sxs-lookup"><span data-stu-id="6157b-136">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="6157b-137">Granska nätverksskyddshändelser i Windows Loggboken</span><span class="sxs-lookup"><span data-stu-id="6157b-137">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="6157b-138">Du kan granska Windows händelselogg för att se händelser som skapas när nätverksskydd blockerar (eller granskar) åtkomst till en skadlig IP eller domän:</span><span class="sxs-lookup"><span data-stu-id="6157b-138">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="6157b-139">[Kopiera XML-filen direkt.](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="6157b-139">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="6157b-140">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="6157b-140">Select **OK**.</span></span>

<span data-ttu-id="6157b-141">Den här proceduren skapar en anpassad vy som filtrerar för att bara visa följande händelser relaterade till nätverksskydd:</span><span class="sxs-lookup"><span data-stu-id="6157b-141">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="6157b-142">Händelse-ID</span><span class="sxs-lookup"><span data-stu-id="6157b-142">Event ID</span></span> | <span data-ttu-id="6157b-143">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6157b-143">Description</span></span> |
|:---|:---|
| <span data-ttu-id="6157b-144">5007</span><span class="sxs-lookup"><span data-stu-id="6157b-144">5007</span></span> | <span data-ttu-id="6157b-145">Händelse när inställningar ändras</span><span class="sxs-lookup"><span data-stu-id="6157b-145">Event when settings are changed</span></span> |
| <span data-ttu-id="6157b-146">1125</span><span class="sxs-lookup"><span data-stu-id="6157b-146">1125</span></span> | <span data-ttu-id="6157b-147">Händelse när nätverksskydd aktiveras i granskningsläge</span><span class="sxs-lookup"><span data-stu-id="6157b-147">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="6157b-148">1126</span><span class="sxs-lookup"><span data-stu-id="6157b-148">1126</span></span> | <span data-ttu-id="6157b-149">Händelse när nätverksskyddet utbrandar i blockläge</span><span class="sxs-lookup"><span data-stu-id="6157b-149">Event when network protection fires in block mode</span></span> |

## <a name="related-articles"></a><span data-ttu-id="6157b-150">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="6157b-150">Related articles</span></span>

- <span data-ttu-id="6157b-151">[Utvärdera |](evaluate-network-protection.md) Utför ett snabbt scenario som visar hur funktionen fungerar och vilka händelser som normalt skulle skapas.</span><span class="sxs-lookup"><span data-stu-id="6157b-151">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="6157b-152">[Aktivera nätverksskydd](enable-network-protection.md) | Använd grupprinciper, PowerShell och MDM-CSP:er för att aktivera och hantera nätverksskydd i nätverket.</span><span class="sxs-lookup"><span data-stu-id="6157b-152">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
