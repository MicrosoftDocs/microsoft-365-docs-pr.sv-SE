---
title: Tillåt medlemmar att skicka som eller skicka för en grupp
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Lär dig hur du tillåter medlemmar att skicka e-post som en Office 365-grupp eller skicka e-post för en Office 365-grupp.
ms.openlocfilehash: b85b0318587058f1c3eb4d681086ccfcad7f1d8d
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212111"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="6b81b-103">Tillåt medlemmar att skicka som eller skicka för en grupp</span><span class="sxs-lookup"><span data-stu-id="6b81b-103">Allow members to send as or send on behalf of a Group</span></span>

<span data-ttu-id="6b81b-104">En medlem i en Office 365-grupp som har beviljats **send as** eller **Skicka för räkning** kan skicka e-post som grupp eller för gruppens räkning.</span><span class="sxs-lookup"><span data-stu-id="6b81b-104">A member of an Office 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="6b81b-105">I det här avsnittet beskrivs hur en administratör kan ange dessa behörigheter.</span><span class="sxs-lookup"><span data-stu-id="6b81b-105">This topic explains how an admin can set these permissions.</span></span>
  
<span data-ttu-id="6b81b-106">Om Megan Bowen till exempel ingår i gruppen **Utbildningskontor** 365 och har **Skicka som** behörigheter för gruppen, om hon skickar ett e-postmeddelande som grupp, ser det ut som att gruppen **Utbildning** har skickat e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="6b81b-106">For example, if Megan Bowen is part of the **Training** Office 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="6b81b-107">Med behörigheten **Skicka för räkning** kan en användare skicka e-post för en Office 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="6b81b-107">The **Send on Behalf** permission lets a user send email on behalf of an Office 365 group.</span></span> <span data-ttu-id="6b81b-108">Om Alex Wilber till exempel ingår i gruppen **Marknadsföringskontor** 365 och har behörigheter **för skicka för räkning** och skickar ett e-postmeddelande som grupp, ser e-postmeddelandet ut som om det skickades av Alex **Wilber för marknadsföring**.</span><span class="sxs-lookup"><span data-stu-id="6b81b-108">For example, if Alex Wilber is a part of the **Marketing** Office 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6b81b-109">Du kan konfigurera **Skicka som** eller **Skicka för** en viss användare, men inte båda.</span><span class="sxs-lookup"><span data-stu-id="6b81b-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="6b81b-110">Om du konfigurerar båda, kommer det att standard **skicka som**.</span><span class="sxs-lookup"><span data-stu-id="6b81b-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="6b81b-111">Se [Skicka e-post från eller på uppdrag av en Office 365-grupp](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) om du vill lära dig hur du använder Outlook och Outlook på webben för att skicka e-post från en grupp.</span><span class="sxs-lookup"><span data-stu-id="6b81b-111">See [Send email from or on behalf of an Office 365 group](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="6b81b-112">Tillåt medlemmar att skicka e-post som en grupp</span><span class="sxs-lookup"><span data-stu-id="6b81b-112">Allow members to send email as a group</span></span>

<span data-ttu-id="6b81b-113">I det här avsnittet beskrivs hur du tillåter användare att skicka e-post som en grupp i [Administrationscenter](https://go.microsoft.com/fwlink/p/?linkid=2059104) för Exchange (EAC) i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6b81b-113">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="6b81b-114">Gå till Mottagare **grupper**i \> **administrationscentret för** <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="6b81b-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="6b81b-115">Välj **Ikonen**![Redigera](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) redigera grupp i gruppen som du vill tillåta användare att skicka som.  </span><span class="sxs-lookup"><span data-stu-id="6b81b-115">Select **Edit**  ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="6b81b-116">Välj **gruppdelegering**.</span><span class="sxs-lookup"><span data-stu-id="6b81b-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="6b81b-117">I avsnittet **Skicka som** **+** markerar du tecknet för att lägga till de användare som du vill skicka som grupp.</span><span class="sxs-lookup"><span data-stu-id="6b81b-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Välj plustecknet för att lägga till de användare som du vill skicka som Office 365-grupp](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="6b81b-119">Sök efter eller välj en användare i listan.</span><span class="sxs-lookup"><span data-stu-id="6b81b-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="6b81b-120">Välj **OK** och **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6b81b-120">Select **OK** and **Save**.</span></span>
    
    ![Skriv om du vill söka eller välja en användare i listan](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="6b81b-122">Tillåt medlemmar att skicka e-post för en grupp</span><span class="sxs-lookup"><span data-stu-id="6b81b-122">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="6b81b-123">I det här avsnittet beskrivs hur du tillåter användare att skicka e-post för en grupp i Administrationscenter för Exchange (EAC) i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6b81b-123">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="6b81b-124">Gå till Mottagare **grupper**i \> **administrationscentret för** <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="6b81b-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="6b81b-125">Välj **Edit** ![Ikonen Redigera](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) redigera grupp på den grupp som du vill tillåta användare att skicka som.</span><span class="sxs-lookup"><span data-stu-id="6b81b-125">Select **Edit** ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="6b81b-126">Välj **gruppdelegering**.</span><span class="sxs-lookup"><span data-stu-id="6b81b-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="6b81b-127">I avsnittet Skicka för räkning **+** väljer du tecknet för att lägga till de användare som du vill skicka som grupp.</span><span class="sxs-lookup"><span data-stu-id="6b81b-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Välj plustecknet för att lägga till de användare som du vill skicka som Office 365-grupp](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="6b81b-129">Sök efter eller välj en användare i listan.</span><span class="sxs-lookup"><span data-stu-id="6b81b-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="6b81b-130">Välj **OK** och **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6b81b-130">Select **OK** and **Save**.</span></span>
    
    ![Skriv om du vill söka eller välja en användare i listan](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="6b81b-132">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="6b81b-132">Related articles</span></span>

[<span data-ttu-id="6b81b-133">Läs mer om Office 365-grupper</span><span class="sxs-lookup"><span data-stu-id="6b81b-133">Learn more about Office 365 Groups</span></span>](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)

[<span data-ttu-id="6b81b-134">TilläggstilläggPrebehörigheter</span><span class="sxs-lookup"><span data-stu-id="6b81b-134">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="6b81b-135">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="6b81b-135">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
