---
title: Felsöka problem med Tjänsten Microsoft Threat Protection
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
ms.openlocfilehash: bbc7d5d434765b94b0b2707605be2edfbbc8e423
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "42808631"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="4a518-104">Felsöka problem med Tjänsten Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4a518-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

<span data-ttu-id="4a518-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="4a518-105">**Applies to:**</span></span>
- <span data-ttu-id="4a518-106">Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="4a518-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="4a518-107">I det här avsnittet beskrivs problem som kan uppstå när du använder Microsoft Threat Protection-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="4a518-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="i-dont-see-microsoft-threat-protection-content"></a><span data-ttu-id="4a518-108">Jag ser inte Microsoft Threat Protection-innehåll</span><span class="sxs-lookup"><span data-stu-id="4a518-108">I don't see Microsoft Threat Protection content</span></span>
<span data-ttu-id="4a518-109">Om du inte ser funktioner i navigeringsfönstret, till exempel Incidenter, Åtgärdscenter eller Jakt i portalen, måste du kontrollera att din klient har rätt licenser.</span><span class="sxs-lookup"><span data-stu-id="4a518-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="4a518-110">Mer information finns i [Förutsättningar](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="4a518-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="4a518-111">Azure ATP-aviseringar visas inte i Microsoft Threat Protection-incidenterna</span><span class="sxs-lookup"><span data-stu-id="4a518-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="4a518-112">Om du har Azure ATP distribuerat i din miljö men inte ser Azure ATP-aviseringar som en del av Microsoft Threat Protection-incidenter måste du se till att Microsoft Cloud App Security och Azure ATP-integrering är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="4a518-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="4a518-113">Mer information finns i [Azure ATP-integrering](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span><span class="sxs-lookup"><span data-stu-id="4a518-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="4a518-114">Är Microsoft Threat Protection tillgängligt för GCC (US Government Community Cloud) eller GCC High?</span><span class="sxs-lookup"><span data-stu-id="4a518-114">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="4a518-115">För närvarande är den inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="4a518-115">At the moment, it is not available.</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="4a518-116">Var finns inställningssidan för att slå på tjänsten?</span><span class="sxs-lookup"><span data-stu-id="4a518-116">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="4a518-117">Om du vill aktivera Microsoft Threat Protection kommer du åt **Inställningar** från navigeringsfönstret i Microsoft 365-säkerhetscentret.</span><span class="sxs-lookup"><span data-stu-id="4a518-117">To turn on Microsoft Threat Protection, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="4a518-118">Det här [navigeringsobjektet](mtp-enable.md#check-license-eligibility-and-required-permissions)visas bara om du har behörighet och licenser .</span><span class="sxs-lookup"><span data-stu-id="4a518-118">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="can-i-use-an-add-on-instead-of-the-required-e5-licenses"></a><span data-ttu-id="4a518-119">Kan jag använda ett tillägg i stället för de E5-licenser som krävs?</span><span class="sxs-lookup"><span data-stu-id="4a518-119">Can I use an add-on instead of the required E5 licenses?</span></span>
<span data-ttu-id="4a518-120">Det finns för närvarande inga tillägg för Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="4a518-120">There are currently no add-ons for Microsoft Threat Protection.</span></span> [<span data-ttu-id="4a518-121">Se licenskrav</span><span class="sxs-lookup"><span data-stu-id="4a518-121">See licensing requirements</span></span>](prerequisites.md) 

