---
title: Felsöka problem med Microsoft Threat Protection-tjänsten
description: Hitta lösningar och Undvik kända problem med Microsoft Threat Protection
keywords: felsöka Microsoft Threat Protection, felsöka, Azure ATP, problem, tillägg, sidan Inställningar
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bcf5b79fcd2fdf0a5af5648e6f6b7ea65d69594c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201297"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="944f6-104">Felsöka problem med Microsoft Threat Protection-tjänsten</span><span class="sxs-lookup"><span data-stu-id="944f6-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="944f6-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="944f6-105">**Applies to:**</span></span>
- <span data-ttu-id="944f6-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="944f6-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="944f6-107">I det här avsnittet åtgärdas problem som kan uppstå när du använder tjänsten Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="944f6-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="i-dont-see-microsoft-threat-protection-content"></a><span data-ttu-id="944f6-108">Jag ser inte innehåll från Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="944f6-108">I don't see Microsoft Threat Protection content</span></span>
<span data-ttu-id="944f6-109">Om du inte ser funktionerna i navigerings fönstret, till exempel händelser, åtgärds Center eller jakt på din portal, måste du verifiera att klient organisationen har rätt licenser.</span><span class="sxs-lookup"><span data-stu-id="944f6-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="944f6-110">För mer information, se [förutsättningar](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="944f6-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="944f6-111">Azure ATP-meddelanden visas inte i Microsofts skydds händelser för hotet</span><span class="sxs-lookup"><span data-stu-id="944f6-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="944f6-112">Om du har distribuerat Azure ATP i din miljö men inte ser Azure ATP-aviseringar som en del av Microsoft Threat Protection-incidenter måste du kontrol lera att Microsoft Cloud App Security och Azure ATP-integreringen är aktive rad.</span><span class="sxs-lookup"><span data-stu-id="944f6-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="944f6-113">Mer information finns i [integreringen av Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span><span class="sxs-lookup"><span data-stu-id="944f6-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="944f6-114">Var är inställnings sidan för att aktivera tjänsten?</span><span class="sxs-lookup"><span data-stu-id="944f6-114">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="944f6-115">Aktivera åtkomst **Inställningar** för Microsoft Threat från navigerings fönstret i Microsoft 365 säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="944f6-115">To turn on Microsoft Threat Protection, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="944f6-116">Det här navigerings objektet visas bara om du har [behörighet och licenser för nödvändig](mtp-enable.md#check-license-eligibility-and-required-permissions)installation.</span><span class="sxs-lookup"><span data-stu-id="944f6-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
 

