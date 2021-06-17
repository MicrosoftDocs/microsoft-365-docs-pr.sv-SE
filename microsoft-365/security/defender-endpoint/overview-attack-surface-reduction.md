---
title: Översikt för minskning av attackytan
ms.reviewer: ''
description: Läs mer om funktionerna för att minska attackytan i Microsoft Defender för Endpoint.
keywords: asr, minskning av attackytan, Microsoft Defender för Slutpunkt, microsoft defender, antivirus, av, windows defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: asr
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 6b3c88f23d3ceffbca588c80b05266d12147ca39
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985030"
---
# <a name="overview-of-attack-surface-reduction-capabilities"></a><span data-ttu-id="3c63c-104">Översikt över funktioner för att minska attackytan</span><span class="sxs-lookup"><span data-stu-id="3c63c-104">Overview of attack surface reduction capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3c63c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3c63c-105">**Applies to:**</span></span>

- [<span data-ttu-id="3c63c-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="3c63c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3c63c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c63c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="3c63c-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="3c63c-108">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="3c63c-109">[Registrera dig för en kostnadsfri utvärderingsversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="3c63c-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink).</span></span>

<span data-ttu-id="3c63c-110">Attackytor är alla platser där organisationen är sårbar för cyberhot och attacker.</span><span class="sxs-lookup"><span data-stu-id="3c63c-110">Attack surfaces are all the places where your organization is vulnerable to cyberthreats and attacks.</span></span> <span data-ttu-id="3c63c-111">Defender för Slutpunkt innehåller flera funktioner som hjälper dig att minska attackytorna.</span><span class="sxs-lookup"><span data-stu-id="3c63c-111">Defender for Endpoint includes several capabilities to help reduce your attack surfaces.</span></span> <span data-ttu-id="3c63c-112">I följande video får du lära dig mer om hur du minskar attackytan.</span><span class="sxs-lookup"><span data-stu-id="3c63c-112">Watch the following video to learn more about attack surface reduction.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4woug]

## <a name="resources-to-learn-more-about-attack-surface-reduction"></a><span data-ttu-id="3c63c-113">Resurser för att lära dig mer om att minska attackytan</span><span class="sxs-lookup"><span data-stu-id="3c63c-113">Resources to learn more about attack surface reduction</span></span>

<span data-ttu-id="3c63c-114">Som nämns i videon innehåller Defender för Slutpunkt flera minskningsfunktioner för attackytor.</span><span class="sxs-lookup"><span data-stu-id="3c63c-114">As mentioned in the video, Defender for Endpoint includes several attack surface reduction capabilities.</span></span> <span data-ttu-id="3c63c-115">Använd följande resurser för mer information:</span><span class="sxs-lookup"><span data-stu-id="3c63c-115">Use the following resources to learn more:</span></span>

| <span data-ttu-id="3c63c-116">Artikel</span><span class="sxs-lookup"><span data-stu-id="3c63c-116">Article</span></span> | <span data-ttu-id="3c63c-117">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3c63c-117">Description</span></span> |
|:---|:---|
| [<span data-ttu-id="3c63c-118">Maskinvarubaserad isolering</span><span class="sxs-lookup"><span data-stu-id="3c63c-118">Hardware-based isolation</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview) | <span data-ttu-id="3c63c-119">Skydda och upprätthålla integriteten för ett system när det startar och medan det körs.</span><span class="sxs-lookup"><span data-stu-id="3c63c-119">Protect and maintain the integrity of a system as it starts and while it's running.</span></span> <span data-ttu-id="3c63c-120">Verifiera systemintegritet genom lokal och fjärransluten tillförlitlighet.</span><span class="sxs-lookup"><span data-stu-id="3c63c-120">Validate system integrity through local and remote attestation.</span></span> <span data-ttu-id="3c63c-121">Använd behållarisolering för Microsoft Edge för att skydda dig mot skadliga webbplatser.</span><span class="sxs-lookup"><span data-stu-id="3c63c-121">Use container isolation for Microsoft Edge to help guard against malicious websites.</span></span> |
| [<span data-ttu-id="3c63c-122">Applikationskontroll</span><span class="sxs-lookup"><span data-stu-id="3c63c-122">Application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) | <span data-ttu-id="3c63c-123">Använd programkontrollen så att programmen måste vara betrodda för att kunna köras.</span><span class="sxs-lookup"><span data-stu-id="3c63c-123">Use application control so that your applications must earn trust in order to run.</span></span> |
| [<span data-ttu-id="3c63c-124">Kontrollerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="3c63c-124">Controlled folder access</span></span>](controlled-folders.md) | <span data-ttu-id="3c63c-125">Förhindra skadliga eller misstänkta program (inklusive filkrypterande skadlig kod för utpressningstrojaner) från att göra ändringar i filer i viktiga systemmappar (kräver Microsoft Defender Antivirus)</span><span class="sxs-lookup"><span data-stu-id="3c63c-125">Help prevent malicious or suspicious apps (including file-encrypting ransomware malware) from making changes to files in your key system folders (Requires Microsoft Defender Antivirus)</span></span> |
| [<span data-ttu-id="3c63c-126">Nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="3c63c-126">Network protection</span></span>](network-protection.md) | <span data-ttu-id="3c63c-127">Utöka skyddet till nätverkstrafiken och anslutningarna på din organisations enheter.</span><span class="sxs-lookup"><span data-stu-id="3c63c-127">Extend protection to your network traffic and connectivity on your organization's devices.</span></span> <span data-ttu-id="3c63c-128">(Kräver Microsoft Defender Antivirus)</span><span class="sxs-lookup"><span data-stu-id="3c63c-128">(Requires Microsoft Defender Antivirus)</span></span> |
| [<span data-ttu-id="3c63c-129">Exploateringsskydd</span><span class="sxs-lookup"><span data-stu-id="3c63c-129">Exploit protection</span></span>](exploit-protection.md) | <span data-ttu-id="3c63c-130">Hjälper till att skydda operativsystem och appar som din organisation använder från att utnyttjas.</span><span class="sxs-lookup"><span data-stu-id="3c63c-130">Help protect the operating systems and apps your organization uses from being exploited.</span></span> <span data-ttu-id="3c63c-131">Sårbarhetsskydd fungerar också med antiviruslösningar från tredje part.</span><span class="sxs-lookup"><span data-stu-id="3c63c-131">Exploit protection also works with third-party antivirus solutions.</span></span> |
| [<span data-ttu-id="3c63c-132">Regler för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="3c63c-132">Attack surface reduction rules</span></span>](attack-surface-reduction.md) | <span data-ttu-id="3c63c-133">Minska säkerhetsproblem (attackytor) i dina program med intelligenta regler som hjälper dig att stoppa skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="3c63c-133">Reduce vulnerabilities (attack surfaces) in your applications with intelligent rules that help stop malware.</span></span> <span data-ttu-id="3c63c-134">(Kräver Microsoft Defender Antivirus).</span><span class="sxs-lookup"><span data-stu-id="3c63c-134">(Requires Microsoft Defender Antivirus).</span></span> |
| [<span data-ttu-id="3c63c-135">Enhetskontroll</span><span class="sxs-lookup"><span data-stu-id="3c63c-135">Device control</span></span>](device-control-report.md) | <span data-ttu-id="3c63c-136">Skyddar mot dataförlust genom att övervaka och kontrollera media som används på enheter, till exempel flyttbara lagringsenheter och USB-enheter, i organisationen.</span><span class="sxs-lookup"><span data-stu-id="3c63c-136">Protects against data loss by monitoring and controlling media used on devices, such as removable storage and USB drives, in your organization.</span></span> |
