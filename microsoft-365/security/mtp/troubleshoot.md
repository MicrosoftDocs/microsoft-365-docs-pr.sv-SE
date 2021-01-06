---
title: Felsöka problem med Microsoft 365 Defender-tjänsten
description: Hitta lösningar och Undvik kända problem med Microsoft 365 Defender
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
ms.openlocfilehash: b7b6ea55d084c114b79dfee0e061b09c8ede8632
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760464"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="92db3-104">Felsöka problem med Microsoft 365 Defender-tjänsten</span><span class="sxs-lookup"><span data-stu-id="92db3-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="92db3-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="92db3-105">**Applies to:**</span></span>
- <span data-ttu-id="92db3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="92db3-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="92db3-107">I det här avsnittet åtgärdas problem som kan uppstå när du använder Microsoft 365 Defender-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="92db3-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="92db3-108">Jag ser inte Microsoft 365 Defender-innehåll</span><span class="sxs-lookup"><span data-stu-id="92db3-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="92db3-109">Om du inte ser funktionerna i navigerings fönstret, till exempel händelser, åtgärds Center eller jakt på din portal, måste du verifiera att klient organisationen har rätt licenser.</span><span class="sxs-lookup"><span data-stu-id="92db3-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="92db3-110">För mer information, se [förutsättningar](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="92db3-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="92db3-111">Microsoft Defender för identitets varningar visas inte i Microsoft 365 Defender-incidenterna</span><span class="sxs-lookup"><span data-stu-id="92db3-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="92db3-112">Om du har Microsoft Defender för en identitet distribuerad i din miljö men inte ser Defender för identitets aviseringar som en del av Microsoft 365 Defender-incidenter måste du kontrol lera att Microsoft Cloud App Security och Defender för identitets integrering är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="92db3-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="92db3-113">Mer information finns i [Microsoft Defender för identitets integrering](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span><span class="sxs-lookup"><span data-stu-id="92db3-113">For more information, see [Microsoft Defender for Identity integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="92db3-114">Var är inställnings sidan för att aktivera tjänsten?</span><span class="sxs-lookup"><span data-stu-id="92db3-114">Where is the settings page for turning the service on?</span></span>

<span data-ttu-id="92db3-115">Om du vill aktivera Microsoft 365 Defender öppnar du **Inställningar** från navigerings fönstret i Microsoft 365 säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="92db3-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="92db3-116">Det här navigerings objektet visas bara om du har [behörighet och licenser för nödvändig](mtp-enable.md#check-license-eligibility-and-required-permissions)installation.</span><span class="sxs-lookup"><span data-stu-id="92db3-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
