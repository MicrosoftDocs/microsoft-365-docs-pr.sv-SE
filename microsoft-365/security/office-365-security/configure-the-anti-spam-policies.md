---
title: Konfigurera policyerna mot skräppost
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 6/9/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 31279431-828d-48bd-b979-20b6de15fa4a
ms.collection:
- M365-security-compliance
description: Skräppostfiltrering aktiveras automatiskt i hela företaget via standardpolicyerna mot skräppost (anslutningsfilter, skräppostfilter och utgående skräppost). Som administratör kan du visa och redigera, men inte ta bort, standardpolicyerna mot skräppost så att de är anpassade för att bäst uppfylla organisationens behov. För större granularitet kan du också skapa anpassade principer och tillämpa dem på angivna användare, grupper eller domäner i organisationen. Som standard har anpassade principer företräde framför standardprincipen, men du kan ändra prioriteten för dina principer.
ms.openlocfilehash: 2ee5833bf476123a84411a7ad645b9f8c5d0b2b8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42805658"
---
# <a name="configure-the-anti-spam-policies"></a><span data-ttu-id="f27c0-106">Konfigurera policyerna mot skräppost</span><span class="sxs-lookup"><span data-stu-id="f27c0-106">Configure the anti-spam policies</span></span>

<span data-ttu-id="f27c0-107">Skräppostfiltrering aktiveras automatiskt i hela företaget via standardpolicyerna mot skräppost (anslutningsfilter, skräppostfilter och utgående skräppost).</span><span class="sxs-lookup"><span data-stu-id="f27c0-107">Spam filtering is automatically enabled company-wide through the default anti-spam policies (connection filter, spam filter, and outbound spam).</span></span> <span data-ttu-id="f27c0-108">Som administratör kan du visa och redigera, men inte ta bort, standardpolicyerna mot skräppost så att de är anpassade för att bäst uppfylla organisationens behov.</span><span class="sxs-lookup"><span data-stu-id="f27c0-108">As an administrator, you can view and edit, but not delete, the default anti-spam policies so that they are tailored to best meet the needs of your organization.</span></span> <span data-ttu-id="f27c0-109">För större granularitet kan du också skapa anpassade principer och tillämpa dem på angivna användare, grupper eller domäner i organisationen.</span><span class="sxs-lookup"><span data-stu-id="f27c0-109">For greater granularity, you can also create custom policies and apply them to specified users, groups, or domains in your organization.</span></span> <span data-ttu-id="f27c0-110">Som standard har anpassade principer företräde framför standardprincipen, men du kan ändra prioriteten för dina principer.</span><span class="sxs-lookup"><span data-stu-id="f27c0-110">By default, custom policies take precedence over the default policy, but you can change the priority of your policies.</span></span> 
  
<span data-ttu-id="f27c0-111">Mer information om hur du konfigurerar dina policyer mot skräppost finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="f27c0-111">For more about configuring your anti-spam policies, see the following topics:</span></span>
  
[<span data-ttu-id="f27c0-112">Konfigurera princip för anslutningsfilter</span><span class="sxs-lookup"><span data-stu-id="f27c0-112">Configure the connection filter policy</span></span>](configure-the-connection-filter-policy.md)
  
[<span data-ttu-id="f27c0-113">Konfigurera principer för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="f27c0-113">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> <span data-ttu-id="f27c0-114">För fristående EOP-kunder: Som standard skickar EOP-innehållsfiltren skräppostupptäcktmeddelanden till varje mottagares skräppostmapp.</span><span class="sxs-lookup"><span data-stu-id="f27c0-114">For EOP standalone customers: By default, the EOP content filters send spam-detected messages to each recipients' Junk Email folder.</span></span> <span data-ttu-id="f27c0-115">För att säkerställa att åtgärden **Flytta meddelande till skräppost** fungerar med lokala postlådor måste du dock konfigurera två Exchange-regler för e-postflöde (kallas även transportregler) på dina lokala servrar för att identifiera skräpposthuvuden som lagts till av EOP.</span><span class="sxs-lookup"><span data-stu-id="f27c0-115">However, in order to ensure that the **Move message to Junk Email folder** action will work with on-premises mailboxes, you must configure two Exchange mail flow rules (also known as transport rules) on your on-premises servers to detect spam headers added by EOP.</span></span> <span data-ttu-id="f27c0-116">Mer information finns [i Se till att skräppost dirigeras till varje användares skräppostmapp](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span><span class="sxs-lookup"><span data-stu-id="f27c0-116">For details, see [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> 
  
[<span data-ttu-id="f27c0-117">Konfigurera principen för skräppost för utgående</span><span class="sxs-lookup"><span data-stu-id="f27c0-117">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  

