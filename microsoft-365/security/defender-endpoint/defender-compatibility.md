---
title: Kompatibilitet med Microsoft Defender Antivirus med Defender för Slutpunkt
description: Läs mer om hur Windows Defender fungerar med Microsoft Defender för Endpoint och hur det fungerar när en tredjepartsklient mot skadlig programvara används.
keywords: windows defender-kompatibilitet, defender, microsoft defender atp, defender för slutpunkt, antivirus, mde
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 63dca2694dae5dee924c9a0a02a660003907c42b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165967"
---
# <a name="microsoft-defender-antivirus-compatibility-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="dc109-104">Kompatibilitet med Microsoft Defender Antivirus med Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="dc109-104">Microsoft Defender Antivirus compatibility with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dc109-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="dc109-105">**Applies to:**</span></span>
- [<span data-ttu-id="dc109-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="dc109-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="dc109-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dc109-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="dc109-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="dc109-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="dc109-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="dc109-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

<span data-ttu-id="dc109-110">Agenten Microsoft Defender för slutpunkt är beroende av Microsoft Defender Antivirus för vissa funktioner, till exempel genomsökning av filer.</span><span class="sxs-lookup"><span data-stu-id="dc109-110">The Microsoft Defender for Endpoint agent depends on Microsoft Defender Antivirus for some capabilities such as file scanning.</span></span>

>[!IMPORTANT]
><span data-ttu-id="dc109-111">Defender för Endpoint följer inte inställningarna för undantag från Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="dc109-111">Defender for Endpoint does not adhere to the Microsoft Defender Antivirus Exclusions settings.</span></span> 

<span data-ttu-id="dc109-112">Du måste konfigurera säkerhetsintelligensuppdateringar på Defender för slutpunktsenheter oavsett om Microsoft Defender Antivirus är aktivt mot skadlig programvara eller inte.</span><span class="sxs-lookup"><span data-stu-id="dc109-112">You must configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="dc109-113">Mer information finns i Hantera [uppdateringar för Microsoft Defender Antivirus och tillämpa baslinjer.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="dc109-113">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="dc109-114">Om en onboarded-enhet skyddas av en tredjepartsklient för program mot skadlig programvara kommer Microsoft Defender Antivirus för den slutpunkten att gå in i passivt läge.</span><span class="sxs-lookup"><span data-stu-id="dc109-114">If an onboarded device is protected by a third-party antimalware client, Microsoft Defender Antivirus on that endpoint will enter into passive mode.</span></span>

<span data-ttu-id="dc109-115">Microsoft Defender Antivirus fortsätter att ta emot uppdateringar och *mspeng.exe-processen* visas som en tjänst som körs, men genomsökningar utförs inte och ersätter inte den datorprogram mot skadlig programvara från tredje part som körs.</span><span class="sxs-lookup"><span data-stu-id="dc109-115">Microsoft Defender Antivirus will continue to receive updates, and the *mspeng.exe* process will be listed as a running a service, but it will not perform scans and will not replace the running third-party antimalware client.</span></span>

<span data-ttu-id="dc109-116">Microsoft Defender Antivirus-gränssnittet inaktiveras och användare på enheten kan inte använda Microsoft Defender Antivirus för att utföra genomsökningar på begäran eller konfigurera de flesta alternativ.</span><span class="sxs-lookup"><span data-stu-id="dc109-116">The Microsoft Defender Antivirus interface will be disabled, and users on the device will not be able to use Microsoft Defender Antivirus to perform on-demand scans or configure most options.</span></span>

<span data-ttu-id="dc109-117">Mer information finns i avsnittet [Microsoft Defender Antivirus och Defender om slutpunktskompatibilitet.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="dc109-117">For more information, see the [Microsoft Defender Antivirus and Defender for Endpoint compatibility topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
