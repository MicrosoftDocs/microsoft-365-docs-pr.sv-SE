---
title: Hantera licenser för enheter
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: Läs om hur du tilldelar licenser till grupper som ska användas med enheter.
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: a29465e9425694f8913cc09d1b8a0c761c79803c
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826285"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="4c6d2-103">Hantera licenser för enheter</span><span class="sxs-lookup"><span data-stu-id="4c6d2-103">Manage licenses for devices</span></span>

<span data-ttu-id="4c6d2-104">Om du har Office 365 ProPlus (enhet) eller Office 365 ProPlus för utbildning (enhet) kan du tilldela licenser till enheter med hjälp av Azure AD-grupper.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-104">If you have Office 365 ProPlus (device) or Office 365 ProPlus for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="4c6d2-105">När en enhet har en licens kan alla som använder den enheten använda Office 365.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-105">When a device has a license, anyone who uses that device can use Office 365.</span></span> <span data-ttu-id="4c6d2-106">Anta till exempel att du har 20 bärbara datorer och surfplattor som används av personer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="4c6d2-107">När du tilldelar en licens till varje enhet använder varje person som loggar in på en av enheterna Office 365 utan att behöva sin egen licens.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-107">When you assign a license to each device, each person who logs in to one of the devices uses Office 365 without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c6d2-108">Enhetsbaserad licensiering för Office 365 ProPlus är endast tillgänglig som tilläggslicens för vissa kommersiella kunder och vissa utbildningskunder.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-108">Device-based licensing for Office 365 ProPlus is available only as an add-on license for some commerical customers and some education customers.</span></span> <span data-ttu-id="4c6d2-109">För kommersiella kunder är licensen *Office 365 ProPlus (enhet)* och är endast tillgänglig via Enterprise Agreement/Enterprise Agreement Subscription.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-109">For commercial customers, the license is *Office 365 ProPlus (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="4c6d2-110">För utbildningskunder är licensen *Office 365 ProPlus för utbildning (enhet)* och är endast tillgänglig via Inskrivning för utbildningslösningar (EES).</span><span class="sxs-lookup"><span data-stu-id="4c6d2-110">For education customers, the license is *Office 365 ProPlus for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="4c6d2-111">För mer information, läs blogginlägget om [utbildning tillgänglighet](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span><span class="sxs-lookup"><span data-stu-id="4c6d2-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="4c6d2-112">Kontakta din Microsoft-kontorepresentant om du vill ha kommersiell tillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="4c6d2-113">Till att börja med skapar du en grupp i Administrationscentret för Azure Active Directory och tilldelar sedan enheter till gruppen.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="4c6d2-114">Mer information om enhetslicensiering, inklusive enhetskrav, vilka typer av grupper du kan använda och hur du konfigurerar Office 365 ProPlus för att använda enhetslicensiering finns i [Enhetsbaserad licensiering för Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span><span class="sxs-lookup"><span data-stu-id="4c6d2-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Office 365 ProPlus to use device licensing, see [Device-based licensing for Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c6d2-115">Du måste vara global administratör för att kunna utföra uppgifterna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="4c6d2-116">Tilldela licenser till enheter</span><span class="sxs-lookup"><span data-stu-id="4c6d2-116">Assign licenses to devices</span></span>

<span data-ttu-id="4c6d2-117">När du tilldelar licenser till en grupp tilldelar du licenser till alla enheter i gruppen.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="4c6d2-118">Du kan bara tilldela en prenumeration till en enskild grupp.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="4c6d2-119">Gå till sidan<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser</a> i **administrationscentret** > för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="4c6d2-120">På sidan **Licenser** väljer du **Office 365 ProPlus för utbildning (enhet)** eller **Office ProPlus (enhet).**</span><span class="sxs-lookup"><span data-stu-id="4c6d2-120">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)** or **Office ProPlus (device)**.</span></span>
3. <span data-ttu-id="4c6d2-121">Välj en prenumeration på nästa sida och välj sedan **Tilldela licenser**.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="4c6d2-122">I fönstret **Tilldela licenser i en grupp** börjar du skriva ett gruppnamn och väljer det sedan från resultaten för att lägga till det i listan.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="4c6d2-123">Välj **Tilldela**och välj sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="4c6d2-124">Ta bort licenser från enheter</span><span class="sxs-lookup"><span data-stu-id="4c6d2-124">Unassign licenses from devices</span></span>

<span data-ttu-id="4c6d2-125">När du tar bort licenser från en grupp tar du bort licenserna från alla enheter i gruppen.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="4c6d2-126">Alla appar och tillhörande data är sedan skrivskyddade.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="4c6d2-127">Gå till sidan<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser</a> i **administrationscentret.** > </span><span class="sxs-lookup"><span data-stu-id="4c6d2-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="4c6d2-128">På sidan **Licenser** väljer du **Office 365 ProPlus för utbildning (enhet)** eller **Office ProPlus (enhet).**</span><span class="sxs-lookup"><span data-stu-id="4c6d2-128">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)** or **Office ProPlus (device)**.</span></span>
3. <span data-ttu-id="4c6d2-129">Välj en prenumeration på nästa sida, välj **Fler åtgärder**och välj sedan Ta **bort tilldelningslicenser**.</span><span class="sxs-lookup"><span data-stu-id="4c6d2-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="4c6d2-130">Välj **Ta bort tilldelning i**dialogrutan Ta bort **licenser** .</span><span class="sxs-lookup"><span data-stu-id="4c6d2-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>