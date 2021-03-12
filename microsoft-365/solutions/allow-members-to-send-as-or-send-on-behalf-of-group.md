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
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Lär dig hur du tillåter att gruppmedlemmar skickar e-post som en Microsoft 365-grupp eller skickar e-post åt en Microsoft 365-grupp.
ms.openlocfilehash: 44a0a7a690c8faa9fe00732e8154f36aa5a6fe6f
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727085"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="aa309-103">Tillåta medlemmar att skicka som eller skicka för en grupp</span><span class="sxs-lookup"><span data-stu-id="aa309-103">Allow members to send as or send on behalf of a group</span></span>

<span data-ttu-id="aa309-104">En medlem i en Microsoft 365-grupp  som har beviljats behörigheten Skicka som eller Skicka för kan skicka e-post som gruppen eller åt hela gruppen. </span><span class="sxs-lookup"><span data-stu-id="aa309-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="aa309-105">(Gäster i gruppen kan inte beviljas de här behörigheterna.)</span><span class="sxs-lookup"><span data-stu-id="aa309-105">(Guests in the group cannot be granted these permissions.)</span></span>

<span data-ttu-id="aa309-106">I den här artikeln förklaras hur en global administratör eller Exchange-administratör kan ställa in de här behörigheterna.</span><span class="sxs-lookup"><span data-stu-id="aa309-106">This article explains how a global or Exchange administrator can set these permissions.</span></span>
  
<span data-ttu-id="aa309-107">Om Till exempel Bow Bowen  ingår i Microsoft 365-gruppen Utbildning och har behörigheten Skicka som för gruppen,  och hon skickar ett e-postmeddelande som gruppen, ser det ut som att gruppen Utbildning har skickat e-postmeddelandet. </span><span class="sxs-lookup"><span data-stu-id="aa309-107">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="aa309-108">Med **behörigheten Skicka för** kan användare skicka e-post åt en Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="aa309-108">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="aa309-109">Om till exempel Alex Wilber ingår i **Microsoft** 365-gruppen Marknadsföring och har behörigheten Skicka för och skickar ett e-postmeddelande som gruppen, ser e-postmeddelandet ut som om det skickades av **Alex Wilber** på uppdrag av Marknadsföring. </span><span class="sxs-lookup"><span data-stu-id="aa309-109">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa309-110">Du kan konfigurera **Skicka som** eller Skicka **för en** viss användare, men inte båda.</span><span class="sxs-lookup"><span data-stu-id="aa309-110">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="aa309-111">Om du konfigurerar båda inställningarna används Skicka **som som som standard.**</span><span class="sxs-lookup"><span data-stu-id="aa309-111">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="aa309-112">Mer information om hur du använder Outlook och Outlook på webben för att skicka e-post från en grupp finns i Skicka e-post från eller åt en [Microsoft 365-grupp.](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)</span><span class="sxs-lookup"><span data-stu-id="aa309-112">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="aa309-113">Tillåt medlemmar att skicka e-post som en grupp</span><span class="sxs-lookup"><span data-stu-id="aa309-113">Allow members to send email as a group</span></span>

<span data-ttu-id="aa309-114">I det här avsnittet förklaras hur du tillåter att användare skickar e-post som en grupp i [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=2059104) för Exchange (EAC) i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="aa309-114">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="aa309-115">Gå till Mottagare grupper i **administrationscentret för** <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange.</a> \> </span><span class="sxs-lookup"><span data-stu-id="aa309-115">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="aa309-116">Välj **Redigera** ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) grupp-ikonen för den grupp som du vill tillåta användare att skicka som.  </span><span class="sxs-lookup"><span data-stu-id="aa309-116">Select **Edit**  ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="aa309-117">Välj **gruppdelegering**.</span><span class="sxs-lookup"><span data-stu-id="aa309-117">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="aa309-118">I avsnittet **Skicka som** väljer du tecknet för att lägga till de användare som du vill skicka **+** som grupp.</span><span class="sxs-lookup"><span data-stu-id="aa309-118">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Skärmbild av dialogrutan Skicka som](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="aa309-120">Sök efter eller välj en användare i listan.</span><span class="sxs-lookup"><span data-stu-id="aa309-120">Type to search or pick a user from the list.</span></span> <span data-ttu-id="aa309-121">Välj **OK** och **Spara**.</span><span class="sxs-lookup"><span data-stu-id="aa309-121">Select **OK** and **Save**.</span></span>
    
    ![Skriv om du vill söka efter eller välja en användare i listan](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="aa309-123">Tillåta medlemmar att skicka e-post för en grupp</span><span class="sxs-lookup"><span data-stu-id="aa309-123">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="aa309-124">I det här avsnittet förklaras hur du tillåter att användare skickar e-post för en grupp i administrationscentret för Exchange (EAC) i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="aa309-124">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="aa309-125">Gå till Mottagare grupper i **administrationscentret för** <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange.</a> \> </span><span class="sxs-lookup"><span data-stu-id="aa309-125">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="aa309-126">Välj **Redigera** ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) grupp-ikonen för den grupp som du vill tillåta användare att skicka som.</span><span class="sxs-lookup"><span data-stu-id="aa309-126">Select **Edit** ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="aa309-127">Välj **gruppdelegering**.</span><span class="sxs-lookup"><span data-stu-id="aa309-127">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="aa309-128">I avsnittet Skicka för väljer du tecknet **+** för att lägga till de användare som du vill skicka som grupp.</span><span class="sxs-lookup"><span data-stu-id="aa309-128">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Skärmbild av dialogrutan Skicka för](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="aa309-130">Sök efter eller välj en användare i listan.</span><span class="sxs-lookup"><span data-stu-id="aa309-130">Type to search or pick a user from the list.</span></span> <span data-ttu-id="aa309-131">Välj **OK** och **Spara**.</span><span class="sxs-lookup"><span data-stu-id="aa309-131">Select **OK** and **Save**.</span></span>
    
    ![Skriv om du vill söka efter eller välja en användare i listan](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="aa309-133">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="aa309-133">Related articles</span></span>

[<span data-ttu-id="aa309-134">Planering av samarbetsstyrning steg för steg</span><span class="sxs-lookup"><span data-stu-id="aa309-134">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="aa309-135">Skapa din plan för samarbetesstyrning</span><span class="sxs-lookup"><span data-stu-id="aa309-135">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="aa309-136">Läs mer om Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="aa309-136">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="aa309-137">Add-RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="aa309-137">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="aa309-138">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="aa309-138">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
