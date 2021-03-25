---
title: Maskinvarubaserad avgränsning (Windows 10)
ms.reviewer: ''
description: Läs om hur maskinvarubaserad avgränsning i Windows 10 hjälper dig att bekämpa skadlig programvara.
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.author: macapara
ms.date: 09/07/2018
ms.technology: mde
ms.openlocfilehash: b31db39e03ed23698e71c4b38fb0937d2ba59727
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069079"
---
# <a name="hardware-based-isolation-in-windows-10"></a><span data-ttu-id="220b7-103">Maskinvarubaserad avgränsning i Windows 10</span><span class="sxs-lookup"><span data-stu-id="220b7-103">Hardware-based isolation in Windows 10</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="220b7-104">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="220b7-104">**Applies to:**</span></span>
- [<span data-ttu-id="220b7-105">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="220b7-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="220b7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="220b7-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="220b7-107">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="220b7-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="220b7-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="220b7-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="220b7-109">Maskinvarubaserad avgränsning skyddar systemintegriteten i Windows 10 och är integrerad med Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="220b7-109">Hardware-based isolation helps protect system integrity in Windows 10 and is integrated with Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="220b7-110">Funktion</span><span class="sxs-lookup"><span data-stu-id="220b7-110">Feature</span></span> | <span data-ttu-id="220b7-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="220b7-111">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="220b7-112">Windows Defender Application Guard</span><span class="sxs-lookup"><span data-stu-id="220b7-112">Windows Defender Application Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | <span data-ttu-id="220b7-113">Application Guard skyddar din enhet från avancerade attacker samtidigt som du håller dig produktiv.</span><span class="sxs-lookup"><span data-stu-id="220b7-113">Application Guard protects your device from advanced attacks while keeping you productive.</span></span> <span data-ttu-id="220b7-114">Med en unik maskinvarubaserad avgränsningsmetod är målet att isolera icke betrodda webbplatser och PDF-dokument i en lätt behållare som avgränsas från operativsystemet via den inbyggda Windows Hypervisor.</span><span class="sxs-lookup"><span data-stu-id="220b7-114">Using a unique hardware-based isolation approach, the goal is to isolate untrusted websites and PDF documents inside a lightweight container that is separated from the operating system via the native Windows Hypervisor.</span></span> <span data-ttu-id="220b7-115">Om ett icke betroddt webbplats- eller PDF-dokument visar sig vara skadligt finns det fortfarande kvar i Application Guard säkra behållare, så att den skyddade stationära datorn och attacken borta från dina företagsdata.</span><span class="sxs-lookup"><span data-stu-id="220b7-115">If an untrusted site or PDF document turns out to be malicious, it still remains contained within Application Guard’s secure container, keeping the desktop PC protected and the attacker away from your enterprise data.</span></span> |
| [<span data-ttu-id="220b7-116">Windows Defender System Guard</span><span class="sxs-lookup"><span data-stu-id="220b7-116">Windows Defender System Guard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows.md) | <span data-ttu-id="220b7-117">System Guard skyddar och behåller integriteten för systemet när det startar och efter att det körs samt validerar systemintegritet genom att använda att göra detta.</span><span class="sxs-lookup"><span data-stu-id="220b7-117">System Guard protects and maintains the integrity of the system as it starts and after it's running, and validates system integrity by using attestation.</span></span>  |
