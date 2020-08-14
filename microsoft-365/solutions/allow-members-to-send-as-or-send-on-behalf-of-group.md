---
title: Tillåta medlemmar att skicka som eller skicka för en grupp
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Lär dig hur du tillåter att medlemmar skickar e-post som en Microsoft 365-grupp eller skickar e-post åt en Microsoft 365-grupp.
ms.openlocfilehash: b660131798e60182435a69f479411cdec948bc99
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662851"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="34dd1-103">Tillåta medlemmar att skicka som eller skicka för en grupp</span><span class="sxs-lookup"><span data-stu-id="34dd1-103">Allow members to send as or send on behalf of a group</span></span>

<span data-ttu-id="34dd1-104">En medlem i en Microsoft 365-grupp som har behörighet att **Skicka som** eller **Skicka för ombud** kan skicka e-post som grupp eller åt gruppen.</span><span class="sxs-lookup"><span data-stu-id="34dd1-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="34dd1-105">I den här artikeln förklaras hur en administratör kan ange behörigheter.</span><span class="sxs-lookup"><span data-stu-id="34dd1-105">This article explains how an admin can set these permissions.</span></span>
  
<span data-ttu-id="34dd1-106">Om till exempel Megan Bowen är en del av Microsoft 365-gruppen **utbildning** och har **Send as** -behörighet för gruppen, om hon skickar ett e-postmeddelande som grupp, ser det ut som **utbildnings** gruppen skickade e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="34dd1-106">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="34dd1-107">Med behörigheten **Skicka åt** kan en användare skicka e-post åt en Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="34dd1-107">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="34dd1-108">Till exempel, om Alex Wilber är en del av Microsoft 365-gruppen för **marknadsföring** och har behörigheten **Skicka för** användare och skickar ett e-postmeddelande som grupp, ser e-postmeddelandet ut som om det har skickats av **Alex Wilber för marknadsförings räkning**.</span><span class="sxs-lookup"><span data-stu-id="34dd1-108">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34dd1-109">Du kan konfigurera **Skicka som** eller **Skicka** för en given användare, men inte båda.</span><span class="sxs-lookup"><span data-stu-id="34dd1-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="34dd1-110">Om du konfigurerar båda är det standard att **Skicka som**.</span><span class="sxs-lookup"><span data-stu-id="34dd1-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="34dd1-111">Mer information om hur du använder Outlook och Outlook på webben för att skicka e-post från en grupp finns i [skicka e-post från eller på uppdrag av en Microsoft 365-grupp](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) .</span><span class="sxs-lookup"><span data-stu-id="34dd1-111">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="34dd1-112">Tillåt att medlemmar skickar e-post som en grupp</span><span class="sxs-lookup"><span data-stu-id="34dd1-112">Allow members to send email as a group</span></span>

<span data-ttu-id="34dd1-113">I det här avsnittet förklaras hur du tillåter att användare skickar e-post som en grupp i [administrations centret för Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) (UK) i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="34dd1-113">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="34dd1-114">I <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>går du till gruppen **mottagare** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="34dd1-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="34dd1-115">Välj **Redigera** ![ ikonen Redigera grupp ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) i gruppen som du vill tillåta användare att skicka som.  </span><span class="sxs-lookup"><span data-stu-id="34dd1-115">Select **Edit**  ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="34dd1-116">Välj **gruppdelegering**.</span><span class="sxs-lookup"><span data-stu-id="34dd1-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="34dd1-117">I avsnittet **Skicka som** väljer du **+** tecknet för att lägga till de användare som du vill skicka som grupp.</span><span class="sxs-lookup"><span data-stu-id="34dd1-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Välj plus tecknet för att lägga till de användare som du vill skicka som Microsoft 365-gruppen](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="34dd1-119">Sök efter eller välj en användare i listan.</span><span class="sxs-lookup"><span data-stu-id="34dd1-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="34dd1-120">Välj **OK** och **Spara**.</span><span class="sxs-lookup"><span data-stu-id="34dd1-120">Select **OK** and **Save**.</span></span>
    
    ![Skriv för att söka eller välja en användare i listan](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="34dd1-122">Tillåt att medlemmar skickar e-post åt en grupp</span><span class="sxs-lookup"><span data-stu-id="34dd1-122">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="34dd1-123">I det här avsnittet förklaras hur du tillåter att användare skickar e-post för en grupp i administrations centret för Exchange (UK) i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="34dd1-123">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="34dd1-124">I <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>går du till gruppen **mottagare** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="34dd1-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="34dd1-125">Välj **Redigera** ![ ikonen Redigera grupp ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) i gruppen som du vill tillåta användare att skicka som.</span><span class="sxs-lookup"><span data-stu-id="34dd1-125">Select **Edit** ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="34dd1-126">Välj **gruppdelegering**.</span><span class="sxs-lookup"><span data-stu-id="34dd1-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="34dd1-127">I avsnittet Skicka för väljer du **+** tecknet för att lägga till de användare som du vill skicka som grupp.</span><span class="sxs-lookup"><span data-stu-id="34dd1-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Välj plus tecknet för att lägga till de användare som du vill skicka som Microsoft 365-gruppen](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="34dd1-129">Sök efter eller välj en användare i listan.</span><span class="sxs-lookup"><span data-stu-id="34dd1-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="34dd1-130">Välj **OK** och **Spara**.</span><span class="sxs-lookup"><span data-stu-id="34dd1-130">Select **OK** and **Save**.</span></span>
    
    ![Skriv för att söka eller välja en användare i listan](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="34dd1-132">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="34dd1-132">Related articles</span></span>

[<span data-ttu-id="34dd1-133">Lär dig mer om Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="34dd1-133">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="34dd1-134">Add-RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="34dd1-134">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="34dd1-135">Set-Unifiedgrouphttps</span><span class="sxs-lookup"><span data-stu-id="34dd1-135">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
