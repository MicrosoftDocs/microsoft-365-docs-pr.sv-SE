---
title: Konfigurera minskning av attackytan
description: Använd Microsoft Intune, Microsoft Endpoint Configuration Manager, PowerShell-cmdlets och Grupprincip för att konfigurera minskning av attackytan.
keywords: asr, attack surface reduction, windows defender, microsoft defender, antivirus, av
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6129fb889e2bd42f177c4e3be30f676854119f91
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166175"
---
# <a name="configure-attack-surface-reduction"></a><span data-ttu-id="1c645-104">Konfigurera minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="1c645-104">Configure attack surface reduction</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1c645-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1c645-105">**Applies to:**</span></span>
- [<span data-ttu-id="1c645-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1c645-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1c645-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c645-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1c645-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="1c645-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1c645-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="1c645-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="1c645-110">Du kan konfigurera minskning av attackytan med många verktyg, till exempel:</span><span class="sxs-lookup"><span data-stu-id="1c645-110">You can configure attack surface reduction with many tools, including:</span></span>

* <span data-ttu-id="1c645-111">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1c645-111">Microsoft Intune</span></span>
* <span data-ttu-id="1c645-112">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1c645-112">Microsoft Endpoint Configuration Manager</span></span>
* <span data-ttu-id="1c645-113">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="1c645-113">Group Policy</span></span>
* <span data-ttu-id="1c645-114">PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="1c645-114">PowerShell cmdlets</span></span>

<span data-ttu-id="1c645-115">Artikel</span><span class="sxs-lookup"><span data-stu-id="1c645-115">Article</span></span> | <span data-ttu-id="1c645-116">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1c645-116">Description</span></span>
-|-
[<span data-ttu-id="1c645-117">Aktivera maskinvarubaserad avgränsning för Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1c645-117">Enable hardware-based isolation for Microsoft Edge</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard) | <span data-ttu-id="1c645-118">Förbereda och installera Application Guard, inklusive maskin- och programvarukrav</span><span class="sxs-lookup"><span data-stu-id="1c645-118">How to prepare for and install Application Guard, including hardware and software requirements</span></span>
[<span data-ttu-id="1c645-119">Aktivera programkontroll</span><span class="sxs-lookup"><span data-stu-id="1c645-119">Enable application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)|<span data-ttu-id="1c645-120">Styra program som körs av användare och skydda kernellägesprocesser</span><span class="sxs-lookup"><span data-stu-id="1c645-120">How to control applications run by users and protect kernel mode processes</span></span>
[<span data-ttu-id="1c645-121">Sårbarhetsskydd</span><span class="sxs-lookup"><span data-stu-id="1c645-121">Exploit protection</span></span>](./enable-exploit-protection.md)|<span data-ttu-id="1c645-122">Hur du automatiskt tillämpar sårbarhetstekniker på både operativsystemprocesser och på enskilda appar</span><span class="sxs-lookup"><span data-stu-id="1c645-122">How to automatically apply exploit mitigation techniques on both operating system processes and on individual apps</span></span>
[<span data-ttu-id="1c645-123">Nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="1c645-123">Network protection</span></span>](./enable-network-protection.md)|<span data-ttu-id="1c645-124">Hur du hindrar användare från att använda appar för att komma åt skadliga domäner</span><span class="sxs-lookup"><span data-stu-id="1c645-124">How to prevent users from using any apps to access dangerous domains</span></span>
[<span data-ttu-id="1c645-125">Reglerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="1c645-125">Controlled folder access</span></span>](./enable-controlled-folders.md)|<span data-ttu-id="1c645-126">Så här skyddar du värdefulla data från skadliga program</span><span class="sxs-lookup"><span data-stu-id="1c645-126">How to protect valuable data from malicious apps</span></span>
[<span data-ttu-id="1c645-127">Minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="1c645-127">Attack surface reduction</span></span>](./enable-attack-surface-reduction.md)|<span data-ttu-id="1c645-128">Hur du förhindrar åtgärder och appar som vanligtvis används av sårbarhets-och skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="1c645-128">How to prevent actions and apps that are typically used by exploit-seeking malware</span></span>
[<span data-ttu-id="1c645-129">Nätverksbrandvägg</span><span class="sxs-lookup"><span data-stu-id="1c645-129">Network firewall</span></span>](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)|<span data-ttu-id="1c645-130">Skydda enheter och data i ett nätverk</span><span class="sxs-lookup"><span data-stu-id="1c645-130">How to protect devices and data across a network</span></span>

