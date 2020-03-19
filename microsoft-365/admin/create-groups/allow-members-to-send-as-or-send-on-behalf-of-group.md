---
title: Tillåt medlemmar att skicka som eller skicka på uppdrag av en grupp
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
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
description: Läs om hur du tillåter medlemmar att skicka e-post som en Office 365-grupp eller skicka e-post för en Office 365-grupp.
ms.openlocfilehash: 0179dbd2e3093ce80929f6c5f9e689aece845a40
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42808315"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="37c18-103">Tillåt medlemmar att skicka som eller skicka på uppdrag av en grupp</span><span class="sxs-lookup"><span data-stu-id="37c18-103">Allow members to send as or send on behalf of a Group</span></span>

<span data-ttu-id="37c18-104">En medlem i en Office 365-grupp som har beviljats behörigheten **Skicka som** eller **Skicka för** kan nu skicka e-post som gruppen eller åt hela gruppen.</span><span class="sxs-lookup"><span data-stu-id="37c18-104">A member of an Office 365 Group who has been granted **Send as** or **Send on behalf** permissions can now send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="37c18-105">I det här avsnittet beskrivs hur en administratör kan ange dessa behörigheter.</span><span class="sxs-lookup"><span data-stu-id="37c18-105">This topic explains how an admin can set these permissions.</span></span>
  
<span data-ttu-id="37c18-106">Om Megan Bowen till exempel ingår i **utbildningsoffice** 365-gruppen och har **Skicka som** behörigheter för gruppen, om hon skickar ett e-postmeddelande som grupp, kommer det att se ut som **att utbildningsgruppen** har skickat e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="37c18-106">For example, if Megan Bowen is part of the **Training** Office 365 Group, and has **Send as** permissions on the group, if she sends an email as the Group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="37c18-107">Med behörigheten **Skicka för** kan användare skicka e-post för Office 365-gruppens räkning.</span><span class="sxs-lookup"><span data-stu-id="37c18-107">The **Send on Behalf** permission lets a user send email on behalf of an Office 365 Group.</span></span> <span data-ttu-id="37c18-108">Om Alex Wilber till exempel är en del av **Marketing** Office 365 Group och har **behörigheten Skicka för räkning** och skickar ett e-postmeddelande som grupp, ser e-postmeddelandet ut som om det skickades av Alex **Wilber på uppdrag av Marknadsföring**.</span><span class="sxs-lookup"><span data-stu-id="37c18-108">For example, if Alex Wilber is a part of the **Marketing** Office 365 Group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37c18-109">Du kan konfigurera **Skicka som** eller **Skicka för** en viss användare, men inte båda.</span><span class="sxs-lookup"><span data-stu-id="37c18-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="37c18-110">Om du konfigurerar båda, kommer det som standard att **skicka som**.</span><span class="sxs-lookup"><span data-stu-id="37c18-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="37c18-111">Läs stegen i [Skicka e-post från eller på uppdrag av en Office 365-grupp](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) om du vill lära dig hur du använder Outlook och Outlook på webben för att skicka e-post från en grupp.</span><span class="sxs-lookup"><span data-stu-id="37c18-111">Check the out the steps in [Send email from or on behalf of an Office 365 group](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) to learn how to use Outlook and Outlook on the Web to send email from a Group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="37c18-112">Tillåt medlemmar att skicka e-post som grupp</span><span class="sxs-lookup"><span data-stu-id="37c18-112">Allow members to send email as a Group</span></span>

<span data-ttu-id="37c18-113">I det här avsnittet beskrivs hur du tillåter användare att skicka e-post som grupp i [Administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=2059104) för Exchange (EAC) i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="37c18-113">This section explains how to allow users to send email as a Group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="37c18-114">Gå till **mottagargrupper**i \> **administrationscentret** <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">för Exchange.</a></span><span class="sxs-lookup"><span data-stu-id="37c18-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="37c18-115">Välj **Redigera**![gruppikon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) i Grupp som du vill tillåta användare att skicka som.  </span><span class="sxs-lookup"><span data-stu-id="37c18-115">Select **Edit**  ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="37c18-116">Välj **gruppdelegering**.</span><span class="sxs-lookup"><span data-stu-id="37c18-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="37c18-117">Markera **Send As** tecknet **+** i avsnittet Skicka som om du vill lägga till de användare som du vill skicka som gruppen.</span><span class="sxs-lookup"><span data-stu-id="37c18-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Välj plustecknet om du vill lägga till de användare som du vill skicka som Office 365-grupp](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="37c18-119">Sök efter eller välj en användare i listan.</span><span class="sxs-lookup"><span data-stu-id="37c18-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="37c18-120">Välj **OK** och **Spara**.</span><span class="sxs-lookup"><span data-stu-id="37c18-120">Select **OK** and **Save**.</span></span>
    
    ![Skriv för att söka eller välja en användare från listan](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="37c18-122">Tillåt medlemmar att skicka e-post för en grupps räkning</span><span class="sxs-lookup"><span data-stu-id="37c18-122">Allow members to send email on behalf of a Group</span></span>

<span data-ttu-id="37c18-123">I det här avsnittet beskrivs hur du tillåter användare att skicka e-post för en grupp i Administrationscentret för Exchange (EAC) i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="37c18-123">This section explains how to allow users to send email on behalf of a Group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="37c18-124">Gå till **mottagargrupper**i \> **administrationscentret** <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">för Exchange.</a></span><span class="sxs-lookup"><span data-stu-id="37c18-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="37c18-125">Välj **Redigera** ![redigera gruppikon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) i den grupp som du vill tillåta användare att skicka som.</span><span class="sxs-lookup"><span data-stu-id="37c18-125">Select **Edit** ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="37c18-126">Välj **gruppdelegering**.</span><span class="sxs-lookup"><span data-stu-id="37c18-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="37c18-127">Markera tecknet **+** i avsnittet Skicka för räkning för att lägga till de användare som du vill skicka som gruppen.</span><span class="sxs-lookup"><span data-stu-id="37c18-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Välj plustecknet om du vill lägga till de användare som du vill skicka som Office 365-grupp](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="37c18-129">Sök efter eller välj en användare i listan.</span><span class="sxs-lookup"><span data-stu-id="37c18-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="37c18-130">Välj **OK** och **Spara**.</span><span class="sxs-lookup"><span data-stu-id="37c18-130">Select **OK** and **Save**.</span></span>
    
    ![Skriv för att söka eller välja en användare från listan](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="37c18-132">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="37c18-132">Related articles</span></span>

[<span data-ttu-id="37c18-133">Läs mer om Office 365-grupper</span><span class="sxs-lookup"><span data-stu-id="37c18-133">Learn more about Office 365 Groups</span></span>](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)

[<span data-ttu-id="37c18-134">Behörighet för lägg till mottagare</span><span class="sxs-lookup"><span data-stu-id="37c18-134">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="37c18-135">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="37c18-135">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
