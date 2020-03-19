---
title: Se till att skräppost dirigeras till varje användares skräppostmapp
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 7/16/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur du dirigerar skräppost till mappar för skräppost från användare i Exchange Online Protection.
ms.openlocfilehash: 6d1fd625669e8b638a408b2db1993f45fa653ffb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42810739"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="dfafa-103">Se till att skräppost dirigeras till varje användares skräppostmapp</span><span class="sxs-lookup"><span data-stu-id="dfafa-103">Ensure that spam is routed to each user's Junk Email folder</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dfafa-104">Det här avsnittet gäller endast För Exchange Online Protection (EOP) kunder som är värdar för postlådor lokalt i en hybriddistribution.</span><span class="sxs-lookup"><span data-stu-id="dfafa-104">This topic only applies to Exchange Online Protection (EOP) customers who host mailboxes on-premises in a hybrid deployment.</span></span> <span data-ttu-id="dfafa-105">Exchange Online-kunder vars postlådor är fullt värd i Office 365 behöver inte köra dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="dfafa-105">Exchange Online customers whose mailboxes are fully-hosted in Office 365 do not need to run these commands.</span></span>

<span data-ttu-id="dfafa-106">Standardåtgärden mot skräppost för EOP-kunder är att flytta skräppost till mottagarnas skräppostmapp.</span><span class="sxs-lookup"><span data-stu-id="dfafa-106">The default anti-spam action for EOP customers is to move spam messages to the recipients' Junk Email folder.</span></span> <span data-ttu-id="dfafa-107">För att den här åtgärden ska fungera med lokala postlådor måste du konfigurera Exchange-regler för e-postflöde (kallas även transportregler) på dina lokala Edge- eller Hub-servrar för att identifiera skräpposthuvuden som lagts till av EOP.</span><span class="sxs-lookup"><span data-stu-id="dfafa-107">In order for this action to work with on-premises mailboxes, you must configure Exchange mail flow rules (also known as transport rules) on your on-premises Edge or Hub servers to detect spam headers added by EOP.</span></span> <span data-ttu-id="dfafa-108">Dessa regler för e-postflöde anger den scl-nivå (Spam Confidence Level) som används av egenskapen SclJunkThreshold för cmdlet Set-OrganizationConfig för att flytta skräppost till mappen Skräppost i varje postlåda.</span><span class="sxs-lookup"><span data-stu-id="dfafa-108">These mail flow rules set the spam confidence level (SCL) used by the SclJunkThreshold property of the Set-OrganizationConfig cmdlet to move spam into the Junk Email folder of each mailbox.</span></span>

### <a name="to-add-mail-flow-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a><span data-ttu-id="dfafa-109">Så här lägger du till regler för e-postflöde för att säkerställa att skräppost flyttas till mappen Skräppost med hjälp av Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dfafa-109">To add mail flow rules to ensure spam is moved to the Junk Email folder by using Windows PowerShell</span></span>

1. <span data-ttu-id="dfafa-110">Öppna Exchange Management Shell för din lokala Exchange-server.</span><span class="sxs-lookup"><span data-stu-id="dfafa-110">Access the Exchange Management Shell for your on-premises Exchange server.</span></span> <span data-ttu-id="dfafa-111">Mer information om hur du öppnar Exchange Management Shell i din lokala Exchange-organisation finns **i Öppna Shell**.</span><span class="sxs-lookup"><span data-stu-id="dfafa-111">To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**.</span></span>

2. <span data-ttu-id="dfafa-112">Kör följande kommando för att dirigera innehållsfiltrerade skräppostmeddelanden till mappen Skräppost:</span><span class="sxs-lookup"><span data-stu-id="dfafa-112">Run the following command to route content-filtered spam messages to the Junk Email folder:</span></span>

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
   ```

   <span data-ttu-id="dfafa-113">Där _NameForRule_ är namnet på den nya regeln, till exempel JunkContentFilteredMail.</span><span class="sxs-lookup"><span data-stu-id="dfafa-113">Where _NameForRule_ is the name for the new rule, for example, JunkContentFilteredMail.</span></span>

3. <span data-ttu-id="dfafa-114">Kör följande kommando för att dirigera meddelanden som markerats som skräppost innan innehållsfiltret når mappen Skräppost:</span><span class="sxs-lookup"><span data-stu-id="dfafa-114">Run the following command to route messages marked as spam prior to reaching the content filter to the Junk Email folder:</span></span>

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
   ```

   <span data-ttu-id="dfafa-115">Där _NameForRule_ är namnet på den nya regeln, till exempel JunkMailBeforeReachingContentFilter.</span><span class="sxs-lookup"><span data-stu-id="dfafa-115">Where _NameForRule_ is the name for the new rule, for example, JunkMailBeforeReachingContentFilter.</span></span>

4. <span data-ttu-id="dfafa-116">Kör följande kommando för att säkerställa att meddelanden från avsändare i en blockeringslista i skräppostfilterprincipen, till exempel **blockeringslistan av avsändare,** dirigeras till mappen Skräppost:</span><span class="sxs-lookup"><span data-stu-id="dfafa-116">Run the following command to ensure that messages from senders in a block list in the spam filter policy, such as the **Sender block** list, are routed to the Junk Email folder:</span></span>

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
   ```

   <span data-ttu-id="dfafa-117">Där _NameForRule_ är namnet på den nya regeln, till exempel JunkMailInSenderBlockList.</span><span class="sxs-lookup"><span data-stu-id="dfafa-117">Where _NameForRule_ is the name for the new rule, for example, JunkMailInSenderBlockList.</span></span>

<span data-ttu-id="dfafa-118">Om du inte vill använda åtgärden **Flytta meddelande till skräppostmapp** kan du välja en annan åtgärd i innehållsfilterprinciperna i administrationscentret för Exchange.</span><span class="sxs-lookup"><span data-stu-id="dfafa-118">If you do not want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="dfafa-119">Mer information finns i [Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="dfafa-119">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="dfafa-120">Mer information om dessa fält i meddelandehuvudet finns i [Rubriker för skräppostmeddelanden](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="dfafa-120">For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

> [!TIP]
> <span data-ttu-id="dfafa-121">Om du inte vill använda åtgärden **Flytta meddelande till skräppostmapp** kan du välja en annan åtgärd i innehållsfilterprinciperna i administrationscentret för Exchange.</span><span class="sxs-lookup"><span data-stu-id="dfafa-121">If you don't want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="dfafa-122">Mer information finns i [Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="dfafa-122">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="dfafa-123">Mer information om dessa fält i meddelandehuvudet finns i [Rubriker för skräppostmeddelanden](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="dfafa-123">For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dfafa-124">Se även</span><span class="sxs-lookup"><span data-stu-id="dfafa-124">See also</span></span>

[<span data-ttu-id="dfafa-125">Ny-TransportRule</span><span class="sxs-lookup"><span data-stu-id="dfafa-125">New-TransportRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)
