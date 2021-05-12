---
title: Hantera licenser för enheter
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: shegu, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
description: Läs om hur du tilldelar licenser till grupper för användning med enheter.
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_licensing
search.appverid: MET150
ms.date: 03/17/2021
ms.openlocfilehash: 67bd0734953c64f51390aac949a7da477914c7b4
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331664"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="d90f9-103">Hantera licenser för enheter</span><span class="sxs-lookup"><span data-stu-id="d90f9-103">Manage licenses for devices</span></span>

<span data-ttu-id="d90f9-104">Om du har Microsoft 365-appar för företag (enhet) eller Microsoft 365-appar för utbildning (enhet) kan du tilldela licenser till enheter med hjälp av Azure AD-grupper.</span><span class="sxs-lookup"><span data-stu-id="d90f9-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="d90f9-105">När en enhet har en licens kan alla som använder enheten använda Microsoft 365-appar för företag (kallades tidigare Office 365 ProPlus).</span><span class="sxs-lookup"><span data-stu-id="d90f9-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="d90f9-106">Anta till exempel att du har 20 bärbara datorer och surfplattor som används av personer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="d90f9-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="d90f9-107">När du tilldelar en licens till varje enhet använder varje person som loggar in på någon av enheterna Microsoft 365-appar för företag utan att behöva ha en egen licens.</span><span class="sxs-lookup"><span data-stu-id="d90f9-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d90f9-108">Enhetsbaserad licensiering för Microsoft 365-appar för företag är endast tillgängligt som en tilläggslicens för vissa kommersiella kunder och vissa utbildningskunder.</span><span class="sxs-lookup"><span data-stu-id="d90f9-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="d90f9-109">För kommersiella kunder är licensen *Microsoft 365-appar* för företag (enhet) och är endast tillgänglig via Enterprise Agreement/Enterprise Agreement-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="d90f9-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="d90f9-110">För utbildningskunder är licensen *Microsoft 365 Apps for Education (enhet)* och är endast tillgänglig via Enrollment for Education Solutions (EES).</span><span class="sxs-lookup"><span data-stu-id="d90f9-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="d90f9-111">Mer information finns i blogginlägget om tillgänglighet [för utbildning.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education)</span><span class="sxs-lookup"><span data-stu-id="d90f9-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education).</span></span> <span data-ttu-id="d90f9-112">Kontakta din Microsoft-kontorepresentant om du behöver kommersiell tillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="d90f9-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="d90f9-113">Börja genom att skapa en grupp i administrationscentret för Azure Active Directory och sedan tilldela enheter till gruppen.</span><span class="sxs-lookup"><span data-stu-id="d90f9-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="d90f9-114">Mer information om enhetslicensiering, bland annat enhetskrav, vilka typer av grupper du kan använda och hur du konfigurerar Microsoft 365-appar för företag för användning av enhetslicensiering finns i Enhetsbaserade licenser för [Microsoft 365-appar](/deployoffice/device-based-licensing)för företag.</span><span class="sxs-lookup"><span data-stu-id="d90f9-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](/deployoffice/device-based-licensing).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d90f9-115">Du måste vara global administratör för att kunna utföra uppgifterna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="d90f9-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="d90f9-116">Tilldela licenser till enheter</span><span class="sxs-lookup"><span data-stu-id="d90f9-116">Assign licenses to devices</span></span>

<span data-ttu-id="d90f9-117">När du tilldelar licenser till en grupp tilldelar du licenser till alla enheter i gruppen.</span><span class="sxs-lookup"><span data-stu-id="d90f9-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="d90f9-118">Du kan bara tilldela en prenumeration till en enskild grupp.</span><span class="sxs-lookup"><span data-stu-id="d90f9-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="d90f9-119">I administrationscentret för Microsoft 365 går du till **sidan**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser.</a></span><span class="sxs-lookup"><span data-stu-id="d90f9-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="d90f9-120">På sidan **Licenser väljer** du **Microsoft 365-appar för utbildning (enhet)** eller Microsoft **365-appar för företag (enhet)**.</span><span class="sxs-lookup"><span data-stu-id="d90f9-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="d90f9-121">På nästa sida väljer du en prenumeration och sedan **Tilldela licenser.**</span><span class="sxs-lookup"><span data-stu-id="d90f9-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="d90f9-122">Börja skriva **ett gruppnamn i** fönstret Tilldela licenser till en grupp och välj sedan det från resultatet så att det kan läggas till i listan.</span><span class="sxs-lookup"><span data-stu-id="d90f9-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="d90f9-123">Välj **Tilldela** och välj sedan **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="d90f9-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="d90f9-124">Ta bort licenser från enheter</span><span class="sxs-lookup"><span data-stu-id="d90f9-124">Unassign licenses from devices</span></span>

<span data-ttu-id="d90f9-125">När du tar bort licenser från en grupp tar du bort licenserna från alla enheter i gruppen.</span><span class="sxs-lookup"><span data-stu-id="d90f9-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="d90f9-126">Alla appar och tillhörande data är skrivskyddade.</span><span class="sxs-lookup"><span data-stu-id="d90f9-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="d90f9-127">I administrationscentret går du till sidan  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Faktureringslicenser.</a></span><span class="sxs-lookup"><span data-stu-id="d90f9-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="d90f9-128">På sidan **Licenser väljer** du **Microsoft 365-appar för utbildning (enhet)** eller Microsoft **365-appar för företag (enhet)**.</span><span class="sxs-lookup"><span data-stu-id="d90f9-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="d90f9-129">På nästa sida väljer du en prenumeration, väljer **Fler åtgärder** och sedan Tilldela **licenser .**</span><span class="sxs-lookup"><span data-stu-id="d90f9-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="d90f9-130">I dialogrutan **Ta bort licenser** väljer du Ta bort **.**</span><span class="sxs-lookup"><span data-stu-id="d90f9-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>
