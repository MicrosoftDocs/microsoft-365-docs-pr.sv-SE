---
title: Hantera licenser för enheter
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: Lär dig hur du tilldelar licenser till grupper som du kan använda med enheter.
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: 29bd56ccff01d8c21cc67d1188fa21e338fb4b7e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638189"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="c2d33-103">Hantera licenser för enheter</span><span class="sxs-lookup"><span data-stu-id="c2d33-103">Manage licenses for devices</span></span>

<span data-ttu-id="c2d33-104">Om du har Microsoft 365-appar för Enterprise (enhet) eller Microsoft 365-appar för utbildning (enhet) kan du tilldela licenser till enheter med Azure AD Groups.</span><span class="sxs-lookup"><span data-stu-id="c2d33-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="c2d33-105">När en enhet har en licens kan alla som använder enheten använda Microsoft 365-appar för företag (tidigare kallat Office 365 ProPlus).</span><span class="sxs-lookup"><span data-stu-id="c2d33-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="c2d33-106">Låt oss säga att du har 20 bärbara datorer och surfplattor som används av personer i din organisation.</span><span class="sxs-lookup"><span data-stu-id="c2d33-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="c2d33-107">När du tilldelar en licens till varje enhet använder varje person som loggar in på en av enheterna Microsoft 365-appar för företag utan att den egna licensen behövs.</span><span class="sxs-lookup"><span data-stu-id="c2d33-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2d33-108">Enhets licenser för Microsoft 365-appar för företag är bara tillgänglig som en tilläggs licens för vissa kommersiella kunder och vissa utbildnings kunder.</span><span class="sxs-lookup"><span data-stu-id="c2d33-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="c2d33-109">För kommersiella kunder är licensen *Microsoft 365-appar för Enterprise (enhet)* och är endast tillgänglig genom ett avtal för Enterprise-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="c2d33-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="c2d33-110">För utbildnings kunder är licensen *Microsoft 365-program för utbildning (enhet)* och är endast tillgänglig via registrering för utbildnings lösningar (EES).</span><span class="sxs-lookup"><span data-stu-id="c2d33-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="c2d33-111">Mer information finns i blogg inlägget på [utbildning](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span><span class="sxs-lookup"><span data-stu-id="c2d33-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="c2d33-112">För att få en kommersiell tillgänglighet kontaktar du din Microsoft-representant.</span><span class="sxs-lookup"><span data-stu-id="c2d33-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="c2d33-113">Börja genom att skapa en grupp i administrations centret för Azure Active Directory och sedan tilldela enheter till gruppen.</span><span class="sxs-lookup"><span data-stu-id="c2d33-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="c2d33-114">Om du vill veta mer om enhets licensiering, inklusive enhets krav, vilka typer av grupper du kan använda och hur du konfigurerar Microsoft 365-appar för företag att använda enhets licensiering, läser du [enhets licensiering för microsoft 365-program för företag](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span><span class="sxs-lookup"><span data-stu-id="c2d33-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2d33-115">Du måste vara global administratör för att utföra åtgärderna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="c2d33-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="c2d33-116">Tilldela licenser till enheter</span><span class="sxs-lookup"><span data-stu-id="c2d33-116">Assign licenses to devices</span></span>

<span data-ttu-id="c2d33-117">När du tilldelar licenser till en grupp tilldelar du licenser till alla enheter i gruppen.</span><span class="sxs-lookup"><span data-stu-id="c2d33-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="c2d33-118">Du kan bara tilldela en prenumeration till en enda grupp.</span><span class="sxs-lookup"><span data-stu-id="c2d33-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="c2d33-119">Gå till sidan för **fakturerings**licenser i administrations centret för Microsoft 365  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> .</span><span class="sxs-lookup"><span data-stu-id="c2d33-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="c2d33-120">På sidan **licenser** väljer du **Microsoft 365-appar för utbildning (enhet)** eller **Microsoft 365-appar för företag (enhet)**.</span><span class="sxs-lookup"><span data-stu-id="c2d33-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="c2d33-121">På nästa sida väljer du ett abonnemang och sedan **tilldela licenser**.</span><span class="sxs-lookup"><span data-stu-id="c2d33-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="c2d33-122">I fönstret **tilldela licenser i en grupp** börjar du skriva ett grupp namn och väljer det från resultaten för att lägga till det i listan.</span><span class="sxs-lookup"><span data-stu-id="c2d33-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="c2d33-123">Välj **tilldela**och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="c2d33-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="c2d33-124">Ta bort licenser från enheter</span><span class="sxs-lookup"><span data-stu-id="c2d33-124">Unassign licenses from devices</span></span>

<span data-ttu-id="c2d33-125">När du tilldelar licenser från en grupp tar du bort licenser från alla enheter i gruppen.</span><span class="sxs-lookup"><span data-stu-id="c2d33-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="c2d33-126">Alla program och tillhör ande data är då skrivskyddade.</span><span class="sxs-lookup"><span data-stu-id="c2d33-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="c2d33-127">Gå till sidan för **fakturerings**licenser i administrations centret  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> .</span><span class="sxs-lookup"><span data-stu-id="c2d33-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="c2d33-128">På sidan **licenser** väljer du **Microsoft 365-appar för utbildning (enhet)** eller **Microsoft 365-appar för företag (enhet)**.</span><span class="sxs-lookup"><span data-stu-id="c2d33-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="c2d33-129">På nästa sida väljer du ett abonnemang, väljer **fler åtgärder**och väljer sedan **ta bort tilldelning av licenser**.</span><span class="sxs-lookup"><span data-stu-id="c2d33-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="c2d33-130">Välj **ta bort tilldelning**i dialog rutan **ta bort licenser** .</span><span class="sxs-lookup"><span data-stu-id="c2d33-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>