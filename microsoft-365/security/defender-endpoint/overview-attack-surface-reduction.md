---
title: Översikt för minskning av attackytan
ms.reviewer: ''
description: Läs mer om funktionerna för att minska attackytan i Microsoft Defender för Endpoint.
keywords: asr, minskning av attackytan, microsoft defender atp, microsoft defender för slutpunkt, microsoft defender, antivirus, av, windows defender
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
ms.openlocfilehash: 60efae91e4b65c5977bd2aebf111d9174d7c1042
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893559"
---
# <a name="overview-of-attack-surface-reduction"></a><span data-ttu-id="2b0ae-104">Översikt för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="2b0ae-104">Overview of attack surface reduction</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2b0ae-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2b0ae-105">**Applies to:**</span></span>
- [<span data-ttu-id="2b0ae-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="2b0ae-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2b0ae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2b0ae-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2b0ae-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="2b0ae-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2b0ae-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="2b0ae-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="2b0ae-110">Minska attackytorna genom att minimera platserna där organisationen är sårbar för cyberhot och attacker.</span><span class="sxs-lookup"><span data-stu-id="2b0ae-110">Help reduce your attack surfaces, by minimizing the places where your organization is vulnerable to cyberthreats and attacks.</span></span> <span data-ttu-id="2b0ae-111">Använd följande resurser för att konfigurera skydd för enheter och program i organisationen.</span><span class="sxs-lookup"><span data-stu-id="2b0ae-111">Use the following resources to configure protection for the devices and applications in your organization.</span></span>


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4woug]


<span data-ttu-id="2b0ae-112">Artikel</span><span class="sxs-lookup"><span data-stu-id="2b0ae-112">Article</span></span> | <span data-ttu-id="2b0ae-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2b0ae-113">Description</span></span>
-|-
[<span data-ttu-id="2b0ae-114">Minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="2b0ae-114">Attack surface reduction</span></span>](./attack-surface-reduction.md) | <span data-ttu-id="2b0ae-115">Minska säkerhetsproblem (attackytor) i dina program med intelligenta regler som hjälper dig att stoppa skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="2b0ae-115">Reduce vulnerabilities (attack surfaces) in your applications with intelligent rules that help stop malware.</span></span> <span data-ttu-id="2b0ae-116">(Kräver Microsoft Defender Antivirus).</span><span class="sxs-lookup"><span data-stu-id="2b0ae-116">(Requires Microsoft Defender Antivirus).</span></span>
[<span data-ttu-id="2b0ae-117">Maskinvarubaserad isolering</span><span class="sxs-lookup"><span data-stu-id="2b0ae-117">Hardware-based isolation</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview) | <span data-ttu-id="2b0ae-118">Skydda och upprätthålla integriteten för ett system när det startar och medan det körs.</span><span class="sxs-lookup"><span data-stu-id="2b0ae-118">Protect and maintain the integrity of a system as it starts and while it's running.</span></span> <span data-ttu-id="2b0ae-119">Verifiera systemintegritet genom lokal och fjärransluten tillförlitlighet.</span><span class="sxs-lookup"><span data-stu-id="2b0ae-119">Validate system integrity through local and remote attestation.</span></span> <span data-ttu-id="2b0ae-120">Och använd behållarisolering för Microsoft Edge för att skydda dig mot skadliga webbplatser.</span><span class="sxs-lookup"><span data-stu-id="2b0ae-120">And, use container isolation for Microsoft Edge to help guard against malicious websites.</span></span>
[<span data-ttu-id="2b0ae-121">Applikationskontroll</span><span class="sxs-lookup"><span data-stu-id="2b0ae-121">Application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) | <span data-ttu-id="2b0ae-122">Använd programkontrollen så att programmen måste vara betrodda för att kunna köras.</span><span class="sxs-lookup"><span data-stu-id="2b0ae-122">Use application control so that your applications must earn trust in order to run.</span></span>
[<span data-ttu-id="2b0ae-123">Exploateringsskydd</span><span class="sxs-lookup"><span data-stu-id="2b0ae-123">Exploit protection</span></span>](./exploit-protection.md) | <span data-ttu-id="2b0ae-124">Skydda operativsystem och appar som din organisation använder från att utnyttjas.</span><span class="sxs-lookup"><span data-stu-id="2b0ae-124">Help protect operating systems and apps your organization uses from being exploited.</span></span> <span data-ttu-id="2b0ae-125">Sårbarhetsskydd fungerar också med antiviruslösningar från tredje part.</span><span class="sxs-lookup"><span data-stu-id="2b0ae-125">Exploit protection also works with third-party antivirus solutions.</span></span>
[<span data-ttu-id="2b0ae-126">Nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="2b0ae-126">Network protection</span></span>](./network-protection.md) | <span data-ttu-id="2b0ae-127">Utöka skyddet till nätverkstrafiken och anslutningarna på din organisations enheter.</span><span class="sxs-lookup"><span data-stu-id="2b0ae-127">Extend protection to your network traffic and connectivity on your organization's devices.</span></span> <span data-ttu-id="2b0ae-128">(Kräver Microsoft Defender Antivirus)</span><span class="sxs-lookup"><span data-stu-id="2b0ae-128">(Requires Microsoft Defender Antivirus)</span></span>
[<span data-ttu-id="2b0ae-129">Webbskydd</span><span class="sxs-lookup"><span data-stu-id="2b0ae-129">Web protection</span></span>](./web-protection-overview.md) | <span data-ttu-id="2b0ae-130">Skydda dina enheter mot webbhot och hjälp dig att reglera oönskat innehåll.</span><span class="sxs-lookup"><span data-stu-id="2b0ae-130">Secure your devices against web threats and help you regulate unwanted content.</span></span>
[<span data-ttu-id="2b0ae-131">Kontrollerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="2b0ae-131">Controlled folder access</span></span>](./controlled-folders.md) | <span data-ttu-id="2b0ae-132">Förhindra skadliga eller misstänkta program (inklusive filkrypterande skadlig kod för utpressningstrojaner) från att göra ändringar i filer i nyckelsystemmapparna (kräver Microsoft Defender Antivirus)</span><span class="sxs-lookup"><span data-stu-id="2b0ae-132">Help prevent malicious or suspicious apps (including file-encrypting ransomware malware) from making changes to files in your key system folders (Requires Microsoft Defender Antivirus)</span></span>
[<span data-ttu-id="2b0ae-133">Nätverksbrandvägg</span><span class="sxs-lookup"><span data-stu-id="2b0ae-133">Network firewall</span></span>](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) | <span data-ttu-id="2b0ae-134">Förhindra obehörig trafik från att gå till eller från organisationens enheter med tvåvägsfiltrering av nätverkstrafik.</span><span class="sxs-lookup"><span data-stu-id="2b0ae-134">Prevent unauthorized traffic from flowing to or from your organization's devices with two-way network traffic filtering.</span></span>
[<span data-ttu-id="2b0ae-135">Vanliga frågor och svar för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="2b0ae-135">Attack surface reduction FAQ</span></span>](./attack-surface-reduction-faq.md) | <span data-ttu-id="2b0ae-136">Vanliga frågor och svar om regler för att minska attackytan, licensiering med mera.</span><span class="sxs-lookup"><span data-stu-id="2b0ae-136">Frequently asked questions about Attack surface reduction rules, licensing, and more.</span></span>
