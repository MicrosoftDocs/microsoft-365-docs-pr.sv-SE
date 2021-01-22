---
title: Felsöka tjänstproblem i Microsoft 365 Defender
description: Hitta lösningar och lösningar på kända problem med Microsoft 365 Defender
keywords: felsöka Microsoft Threat Protection, felsöka, Azure ATP, problem, tillägg, inställningssida
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 414743fa5ba25b9d2714c1dd08dd38e34ec94372
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925724"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="70b68-104">Felsöka tjänstproblem i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="70b68-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="70b68-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="70b68-105">**Applies to:**</span></span>
- <span data-ttu-id="70b68-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="70b68-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="70b68-107">Det här avsnittet tar upp problem som kan uppstå när du använder Tjänsten Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="70b68-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="70b68-108">Jag ser inte Microsoft 365 Defender-innehåll</span><span class="sxs-lookup"><span data-stu-id="70b68-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="70b68-109">Om du inte ser funktioner i navigeringsfönstret, som Incidenter, Åtgärdscenter eller Sök i portalen, måste du kontrollera att klientorganisationen har rätt licenser.</span><span class="sxs-lookup"><span data-stu-id="70b68-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="70b68-110">Mer information finns i [Förutsättningarna.](prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="70b68-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="70b68-111">Microsoft Defender för identitetsaviseringar visas inte i Microsoft 365 Defender-incidenterna</span><span class="sxs-lookup"><span data-stu-id="70b68-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="70b68-112">Om du har Distribuerat Microsoft Defender för identitet i din miljö men inte ser Defender för identitetsaviseringar som en del av Microsoft 365 Defender-incidenter måste du se till att Microsoft Cloud App Security och Defender för identitetsintegrering är aktiverade.</span><span class="sxs-lookup"><span data-stu-id="70b68-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="70b68-113">Mer information finns i [Microsoft Defender för identitetsintegrering.](https://docs.microsoft.com/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="70b68-113">For more information, see [Microsoft Defender for Identity integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="70b68-114">Var finns inställningssidan för att aktivera tjänsten?</span><span class="sxs-lookup"><span data-stu-id="70b68-114">Where is the settings page for turning the service on?</span></span>

<span data-ttu-id="70b68-115">Om du vill aktivera Microsoft 365 Defender öppnar du Inställningar från navigeringsfönstret i Säkerhetscenter för Microsoft 365. </span><span class="sxs-lookup"><span data-stu-id="70b68-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="70b68-116">Det här navigeringsobjektet visas bara om du har nödvändiga [behörigheter och licenser.](mtp-enable.md#check-license-eligibility-and-required-permissions)</span><span class="sxs-lookup"><span data-stu-id="70b68-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
