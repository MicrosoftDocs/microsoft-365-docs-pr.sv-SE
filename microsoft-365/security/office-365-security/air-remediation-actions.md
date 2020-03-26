---
title: Åtgärder för reparation i office 365-automatiska undersökningar och svar
keywords: AIR, autoIR, ATP, automatiserad, utredning, svar, sanering, hot, avancerad, hot, skydd
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Lär dig mer om reparationsåtgärder i automatiska undersöknings- och svarsfunktioner i Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 1dff52fe1bdab364e03bc42afc84c9b54696ccf5
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955539"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="e3868-104">Åtgärder för reparation efter en automatiserad undersökning i Office 365</span><span class="sxs-lookup"><span data-stu-id="e3868-104">Remediation actions following an automated investigation in Office 365</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="e3868-105">Åtgärder för reparation</span><span class="sxs-lookup"><span data-stu-id="e3868-105">Remediation actions</span></span>

<span data-ttu-id="e3868-106">[Automatiska undersöknings- och svarsfunktioner](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) i [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 innehåller vissa åtgärder för reparation.</span><span class="sxs-lookup"><span data-stu-id="e3868-106">[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 include certain remediation actions.</span></span> <span data-ttu-id="e3868-107">När en automatisk undersökning körs eller har slutförts ser du vanligtvis en eller flera reparationsåtgärder som kräver godkännande av säkerhetsoperationsteamet för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="e3868-107">Whenever an automated investigation is running or has completed, you'll typically see one or more remediation actions that require approval by your security operations team to proceed.</span></span> 

<span data-ttu-id="e3868-108">I följande tabell sammanfattas de reparationsåtgärder som för närvarande är tillgängliga i Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="e3868-108">The following table summarizes the remediation actions that are currently available in Office 365 ATP.</span></span> 

|<span data-ttu-id="e3868-109">Åtgärder</span><span class="sxs-lookup"><span data-stu-id="e3868-109">Action</span></span> | <span data-ttu-id="e3868-110">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e3868-110">Description</span></span> |
|-----|-----|
|<span data-ttu-id="e3868-111">Blockera URL (tid för klick)</span><span class="sxs-lookup"><span data-stu-id="e3868-111">Block URL (time-of-click)</span></span> |<span data-ttu-id="e3868-112">Skyddar mot e-postmeddelanden och dokument som innehåller skadliga webbadresser.</span><span class="sxs-lookup"><span data-stu-id="e3868-112">Protects against email messages and documents that contain malicious URLs.</span></span> <span data-ttu-id="e3868-113">Detta gör det möjligt att blockera skadliga länkar och relaterade webbsidor via [Säkra länkar](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) när användaren klickar på en länk i en befintlig Office-fil eller i ett äldre e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="e3868-113">This enables the blocking of malicious links and any related webpages via [Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) when the user clicks a link in an existing Office file or in an older email message.</span></span> |
|<span data-ttu-id="e3868-114">E-post med mjuk borttagning</span><span class="sxs-lookup"><span data-stu-id="e3868-114">Soft delete email</span></span>  |<span data-ttu-id="e3868-115">Ta bort vissa e-postmeddelanden från en användares postlåda.</span><span class="sxs-lookup"><span data-stu-id="e3868-115">Soft delete specific email messages from a user's mailbox.</span></span> <br/><span data-ttu-id="e3868-116">Ett mjukt borttaget meddelande flyttas till en användares mapp för återställningsbara objekt och behålls tills kvarhållningsperioden för borttaget objekt löper ut.</span><span class="sxs-lookup"><span data-stu-id="e3868-116">A soft-deleted message is moved to a user's Recoverable Items folder and is retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="e3868-117">E-kluster för mjuk borttagning</span><span class="sxs-lookup"><span data-stu-id="e3868-117">Soft delete email clusters</span></span>  |<span data-ttu-id="e3868-118">Ta bort skadliga e-postmeddelanden som matchar en fråga från alla användares postlådor.</span><span class="sxs-lookup"><span data-stu-id="e3868-118">Soft delete malicious email messages matching a query from all users' mailboxes.</span></span> <br/><span data-ttu-id="e3868-119">Meddelanden som tagits bort med mjuka objekt flyttas till användarnas mapp för återställningsbara objekt och behålls tills kvarhållningsperioden för borttaget objekt löper ut.</span><span class="sxs-lookup"><span data-stu-id="e3868-119">Soft-deleted messages are moved to users' Recoverable Items folder and are retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="e3868-120">Inaktivera vidarebefordran av extern e-post</span><span class="sxs-lookup"><span data-stu-id="e3868-120">Turn off external mail forwarding</span></span> |<span data-ttu-id="e3868-121">Tar bort en vidarebefordringsregel från en viss slutanvändarpostlåda.</span><span class="sxs-lookup"><span data-stu-id="e3868-121">Removes a forwarding rule from a specific end user's mailbox.</span></span>|

> [!NOTE]
> <span data-ttu-id="e3868-122">I Office 365 ATP vidtas inga åtgärder för reparation automatiskt.</span><span class="sxs-lookup"><span data-stu-id="e3868-122">In Office 365 ATP, no remediation actions are taken automatically.</span></span> <span data-ttu-id="e3868-123">Reparationsåtgärder vidtas endast efter godkännande av organisationens säkerhetsteam.</span><span class="sxs-lookup"><span data-stu-id="e3868-123">Remediation actions are taken only upon approval by your organization's security team.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="e3868-124">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="e3868-124">Next steps</span></span>

- [<span data-ttu-id="e3868-125">Visa väntande eller slutförda reparationsåtgärder efter en automatisk undersökning i Office 365</span><span class="sxs-lookup"><span data-stu-id="e3868-125">View pending or completed remediation actions following an automated investigation in Office 365</span></span>](air-review-approve-pending-completed-actions.md)

- [<span data-ttu-id="e3868-126">Information och resultat av en automatiserad undersökning i Office 365</span><span class="sxs-lookup"><span data-stu-id="e3868-126">Details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)

## <a name="related-articles"></a><span data-ttu-id="e3868-127">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="e3868-127">Related articles</span></span>

- [<span data-ttu-id="e3868-128">Automatiserad undersökning i Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e3868-128">Automated investigation in Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="e3868-129">Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="e3868-129">Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)