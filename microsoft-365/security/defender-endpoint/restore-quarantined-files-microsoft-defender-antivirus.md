---
title: Återställa filer i karantän i Microsoft Defender AV
description: Du kan återställa filer och mappar som har satts i karantän av Microsoft Defender AV.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/20/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: e0253c4ac7d92c91e3fda45681568d721645f2b0
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275390"
---
# <a name="restore-quarantined-files-in-microsoft-defender-av"></a><span data-ttu-id="cdb69-103">Återställa filer i karantän i Microsoft Defender AV</span><span class="sxs-lookup"><span data-stu-id="cdb69-103">Restore quarantined files in Microsoft Defender AV</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cdb69-104">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="cdb69-104">**Applies to:**</span></span>

- [<span data-ttu-id="cdb69-105">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="cdb69-105">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="cdb69-106">Om Microsoft Defender Antivirus har konfigurerats för att identifiera och åtgärda hot på din enhet Microsoft Defender Antivirus du misstänkta filer i karantän.</span><span class="sxs-lookup"><span data-stu-id="cdb69-106">If Microsoft Defender Antivirus is configured to detect and remediate threats on your device, Microsoft Defender Antivirus quarantines suspicious files.</span></span> <span data-ttu-id="cdb69-107">Om du har en fil i karantän som inte är ett hot kan du återställa den.</span><span class="sxs-lookup"><span data-stu-id="cdb69-107">If you are certain a quarantined file is not a threat, you can restore it.</span></span>

1. <span data-ttu-id="cdb69-108">Öppna **Windows-säkerhet**.</span><span class="sxs-lookup"><span data-stu-id="cdb69-108">Open **Windows Security**.</span></span>
2. <span data-ttu-id="cdb69-109">Välj **Virus & skydd mot hot och** klicka sedan på **Säkerhetshistorik**.</span><span class="sxs-lookup"><span data-stu-id="cdb69-109">Select **Virus & threat protection** and then click **Protection history**.</span></span>
3. <span data-ttu-id="cdb69-110">I listan över de senaste objekten filtrerar du på **Objekt i karantän.**</span><span class="sxs-lookup"><span data-stu-id="cdb69-110">In the list of all recent items, filter on **Quarantined Items**.</span></span>
4. <span data-ttu-id="cdb69-111">Markera ett objekt som du vill behålla och vidta en åtgärd, till exempel återställa.</span><span class="sxs-lookup"><span data-stu-id="cdb69-111">Select an item you want to keep, and take an action, such as restore.</span></span>

> [!TIP]
> <span data-ttu-id="cdb69-112">Återställning av en fil från karantän kan också göras med kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="cdb69-112">Restoring a file from quarantine can also be done using Command Prompt.</span></span> <span data-ttu-id="cdb69-113">Se [Återställa en fil från karantän](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine).</span><span class="sxs-lookup"><span data-stu-id="cdb69-113">See [Restore a file from quarantine](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine).</span></span> 

## <a name="related-articles"></a><span data-ttu-id="cdb69-114">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="cdb69-114">Related articles</span></span>

- [<span data-ttu-id="cdb69-115">Konfigurera åtgärd för genomsökningar</span><span class="sxs-lookup"><span data-stu-id="cdb69-115">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md)
- [<span data-ttu-id="cdb69-116">Granska genomsökningsresultat</span><span class="sxs-lookup"><span data-stu-id="cdb69-116">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md)
- [<span data-ttu-id="cdb69-117">Konfigurera och validera undantag baserat på filnamn, filnamnstillägg och mappplats</span><span class="sxs-lookup"><span data-stu-id="cdb69-117">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="cdb69-118">Konfigurera och validera undantag för filer som öppnas i processer</span><span class="sxs-lookup"><span data-stu-id="cdb69-118">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="cdb69-119">Konfigurera Microsoft Defender Antivirus undantag på Windows Server</span><span class="sxs-lookup"><span data-stu-id="cdb69-119">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)