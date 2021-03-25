---
title: Blockering av feedbackslinga
description: Blockering av feedbackslingor, även kallat snabbt skydd, är en del av funktioner för blockering och inneslutning i Microsoft Defender för Endpoint
keywords: beteendeblockering, snabbt skydd, feedbackblockering, Microsoft Defender för Slutpunkt
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection: ''
ms.technology: mde
ms.openlocfilehash: b1ec879a2f05a0354b1a49cf94fccacb4a382193
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076610"
---
# <a name="feedback-loop-blocking"></a><span data-ttu-id="57a47-104">Blockering av feedbackslinga</span><span class="sxs-lookup"><span data-stu-id="57a47-104">Feedback-loop blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="57a47-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="57a47-105">**Applies to:**</span></span>
- [<span data-ttu-id="57a47-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="57a47-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a><span data-ttu-id="57a47-107">Översikt</span><span class="sxs-lookup"><span data-stu-id="57a47-107">Overview</span></span>

<span data-ttu-id="57a47-108">Blockering av feedbackslingor, även kallat snabbt [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) skydd, är en komponent i funktioner för beteendeblockering och inneslutning i [Microsoft Defender för Slutpunkt.](https://docs.microsoft.com/windows/security/threat-protection/)</span><span class="sxs-lookup"><span data-stu-id="57a47-108">Feedback-loop blocking, also referred to as rapid protection, is a component of [behavioral blocking and containment capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/).</span></span> <span data-ttu-id="57a47-109">Med blockering av feedbackslinga skyddas enheter i organisationen bättre mot attacker.</span><span class="sxs-lookup"><span data-stu-id="57a47-109">With feedback-loop blocking, devices across your organization are better protected from attacks.</span></span> 

## <a name="how-feedback-loop-blocking-works"></a><span data-ttu-id="57a47-110">Så här fungerar blockering av feedbackslingar</span><span class="sxs-lookup"><span data-stu-id="57a47-110">How feedback-loop blocking works</span></span>

<span data-ttu-id="57a47-111">När ett misstänkt beteende eller en fil identifieras, till exempel av [Microsoft Defender Antivirus,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)skickas information om artefakten till flera klassificerare.</span><span class="sxs-lookup"><span data-stu-id="57a47-111">When a suspicious behavior or file is detected, such as by [Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), information about that artifact is sent to multiple classifiers.</span></span> <span data-ttu-id="57a47-112">Den snabba skyddslingsmotorn inspekterar och korrelerar informationen med andra signaler för att komma till ett beslut om huruvida en fil ska blockeras.</span><span class="sxs-lookup"><span data-stu-id="57a47-112">The rapid protection loop engine inspects and correlates the information with other signals to arrive at a decision as to whether to block a file.</span></span> <span data-ttu-id="57a47-113">Det går snabbt att kontrollera och klassificera artefakter.</span><span class="sxs-lookup"><span data-stu-id="57a47-113">Checking and classifying artifacts happens quickly.</span></span> <span data-ttu-id="57a47-114">Det leder till snabb blockering av bekräftad skadlig programvara och skyddar hela ekosystemet.</span><span class="sxs-lookup"><span data-stu-id="57a47-114">It results in rapid blocking of confirmed malware, and drives protection across the entire ecosystem.</span></span> 

<span data-ttu-id="57a47-115">Med snabbt skydd på plats kan en attack stoppas på en enhet, andra enheter i organisationen och enheter i andra organisationer eftersom en attack försöker bredda fothoppet.</span><span class="sxs-lookup"><span data-stu-id="57a47-115">With rapid protection in place, an attack can be stopped on a device, other devices in the organization, and devices in other organizations, as an attack attempts to broaden its foothold.</span></span>


## <a name="configuring-feedback-loop-blocking"></a><span data-ttu-id="57a47-116">Konfigurera blockering av feedbackslinga</span><span class="sxs-lookup"><span data-stu-id="57a47-116">Configuring feedback-loop blocking</span></span>

<span data-ttu-id="57a47-117">Om din organisation använder Defender för Endpoint är blockering av feedbackslinga aktiverad som standard.</span><span class="sxs-lookup"><span data-stu-id="57a47-117">If your organization is using Defender for Endpoint, feedback-loop blocking is enabled by default.</span></span> <span data-ttu-id="57a47-118">Ett snabbt skydd sker emellertid genom en kombination av Defender för Endpoint-funktioner, funktioner för maskininlärningsskydd och signaldelning mellan Microsofts säkerhetstjänster.</span><span class="sxs-lookup"><span data-stu-id="57a47-118">However, rapid protection occurs through a combination of Defender for Endpoint capabilities, machine learning protection features, and signal-sharing across Microsoft security services.</span></span> <span data-ttu-id="57a47-119">Kontrollera att följande funktioner i Defender för Slutpunkt är aktiverade och konfigurerade:</span><span class="sxs-lookup"><span data-stu-id="57a47-119">Make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="57a47-120">Microsoft Defender för slutpunktsbaslinjer</span><span class="sxs-lookup"><span data-stu-id="57a47-120">Microsoft Defender for Endpoint baselines</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="57a47-121">Enheter som finns i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="57a47-121">Devices onboarded to Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="57a47-122">EDR i blockläge</span><span class="sxs-lookup"><span data-stu-id="57a47-122">EDR in block mode</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="57a47-123">Minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="57a47-123">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="57a47-124">[Nästa generations skydd](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span><span class="sxs-lookup"><span data-stu-id="57a47-124">[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="57a47-125">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="57a47-125">Related articles</span></span>

- [<span data-ttu-id="57a47-126">Blockering och inneslutning av beteende</span><span class="sxs-lookup"><span data-stu-id="57a47-126">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="57a47-127">(Blogg) Beteendeblockering och inneslutning: Omvandla fiberoptisk till skydd</span><span class="sxs-lookup"><span data-stu-id="57a47-127">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="57a47-128">Användbara Microsoft Defender för Slutpunkt-resurser</span><span class="sxs-lookup"><span data-stu-id="57a47-128">Helpful Microsoft Defender for Endpoint resources</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
