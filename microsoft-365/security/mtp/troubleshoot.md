---
title: Felsöka serviceproblem för Microsoft Threat Protection
description: Hitta lösningar och lösa information om kända problem med Microsoft Threat Protection
keywords: felsöka Microsoft Threat Protection, felsöka, Azure ATP, problem, tillägg, inställningssida
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
ms.openlocfilehash: e19e5758f4d42799c96ecec51fd6295e3da19f9b
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844924"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="a77f8-104">Felsöka serviceproblem för Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a77f8-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

<span data-ttu-id="a77f8-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="a77f8-105">**Applies to:**</span></span>
- <span data-ttu-id="a77f8-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="a77f8-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="a77f8-107">I det här avsnittet beskrivs problem som kan uppstå när du använder Microsoft Threat Protection-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="a77f8-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="i-dont-see-microsoft-threat-protection-content"></a><span data-ttu-id="a77f8-108">Jag ser inte Microsoft Threat Protection-innehåll</span><span class="sxs-lookup"><span data-stu-id="a77f8-108">I don't see Microsoft Threat Protection content</span></span>
<span data-ttu-id="a77f8-109">Om du inte ser funktioner i navigeringsfönstret, till exempel Incidenter, Åtgärdscenter eller Jakt i portalen, måste du kontrollera att din klient har rätt licenser.</span><span class="sxs-lookup"><span data-stu-id="a77f8-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="a77f8-110">Mer information finns i [Förutsättningar](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="a77f8-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="a77f8-111">Azure ATP-aviseringar visas inte i Microsoft Threat Protection-incidenterna</span><span class="sxs-lookup"><span data-stu-id="a77f8-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="a77f8-112">Om du har Azure ATP distribuerat i din miljö men inte ser Azure ATP-aviseringar som en del av Microsoft Threat Protection-incidenter måste du se till att Microsoft Cloud App Security och Azure ATP-integrering är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="a77f8-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="a77f8-113">Mer information finns i [Azure ATP-integrering](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span><span class="sxs-lookup"><span data-stu-id="a77f8-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="a77f8-114">Var finns inställningssidan för att slå på tjänsten?</span><span class="sxs-lookup"><span data-stu-id="a77f8-114">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="a77f8-115">Om du vill aktivera Microsoft Threat Protection öppnar du **Inställningar** från navigeringsfönstret i Microsoft 365-säkerhetscentret.</span><span class="sxs-lookup"><span data-stu-id="a77f8-115">To turn on Microsoft Threat Protection, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="a77f8-116">Det här [navigeringsobjektet](mtp-enable.md#check-license-eligibility-and-required-permissions)visas bara om du har behörighet och licenser .</span><span class="sxs-lookup"><span data-stu-id="a77f8-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
 

