---
title: Felsöka Microsoft 365 Defender problem med tjänsten
description: Hitta lösningar och lösningar på kända Microsoft 365 Defender problem
keywords: felsöka Microsoft 365 Defender, felsöka, microsoft Defender för identitet, problem, tillägg, inställningssida
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 7891d61de7581a896a6599004eae91a4e47e1581
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029951"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="226ed-104">Felsöka Microsoft 365 Defender problem med tjänsten</span><span class="sxs-lookup"><span data-stu-id="226ed-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="226ed-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="226ed-105">**Applies to:**</span></span>
- <span data-ttu-id="226ed-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="226ed-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="226ed-107">I det här avsnittet behandlas problem som kan uppstå när du Microsoft 365 Defender tjänsten.</span><span class="sxs-lookup"><span data-stu-id="226ed-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="226ed-108">Jag ser inte Microsoft 365 Defender innehåll</span><span class="sxs-lookup"><span data-stu-id="226ed-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="226ed-109">Om du inte ser funktioner i navigeringsfönstret, till exempel Incidenter, Åtgärdscenter eller Om det finns sökfunktioner i portalen, måste du kontrollera att klientorganisationen har rätt licenser.</span><span class="sxs-lookup"><span data-stu-id="226ed-109">If you don't see capabilities on the navigation pane such as the Incidents, Action center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="226ed-110">Mer information finns i [Krav](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="226ed-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="226ed-111">Microsoft Defender för identitetsaviseringar visas inte i de Microsoft 365 Defender incidenter</span><span class="sxs-lookup"><span data-stu-id="226ed-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="226ed-112">Om du har Microsoft Defender för identitet distribuerat i din miljö men inte ser Defender för identitetsaviseringar som en del av Microsoft 365 Defender-incidenter måste du se till att Microsoft Cloud App Security och Defender för identitetsintegrering är aktiverade.</span><span class="sxs-lookup"><span data-stu-id="226ed-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="226ed-113">Mer information finns i [Microsoft Defender för identitetsintegrering.](/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="226ed-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a><span data-ttu-id="226ed-114">Var finns inställningssidan för att aktivera tjänsten?</span><span class="sxs-lookup"><span data-stu-id="226ed-114">Where is the settings page for turning on the service?</span></span>

<span data-ttu-id="226ed-115">Du aktiverar Microsoft 365 Defender genom att **Inställningar** från navigeringsfönstret i Microsoft 365 Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="226ed-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="226ed-116">Det här navigeringsobjektet visas bara om du har nödvändiga [behörigheter och licenser.](m365d-enable.md#check-license-eligibility-and-required-permissions)</span><span class="sxs-lookup"><span data-stu-id="226ed-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](m365d-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a><span data-ttu-id="226ed-117">Hur skapar jag ett undantag för min fil/URL?</span><span class="sxs-lookup"><span data-stu-id="226ed-117">How do I create an exception for my file/URL?</span></span>

<span data-ttu-id="226ed-118">En falsk positiv inställning är en fil eller URL som identifieras som skadlig men inte är ett hot.</span><span class="sxs-lookup"><span data-stu-id="226ed-118">A false positive is a file or URL that is detected as malicious but is not a threat.</span></span> <span data-ttu-id="226ed-119">Du kan skapa indikatorer och definiera undantag för att häva blockeringen och tillåta vissa filer/URL-adresser.</span><span class="sxs-lookup"><span data-stu-id="226ed-119">You can create indicators and define exclusions to unblock and allow certain files/URLs.</span></span> <span data-ttu-id="226ed-120">Se [Adress: falska positiva/negativa i Defender för Slutpunkt](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).</span><span class="sxs-lookup"><span data-stu-id="226ed-120">See [Address false positives/negatives in Defender for Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).</span></span>
