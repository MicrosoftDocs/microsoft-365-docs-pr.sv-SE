---
title: Konfigurera Övrig e-post för organisationen
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Lär dig att aktivera eller inaktivera övrig e-post för alla eller specifika användare i organisationen med Hjälp av Exchange PowerShell. '
ms.openlocfilehash: 6ba1e3f2b6a8a516a2b55267ab22fb43613350e0
ms.sourcegitcommit: 83f980927728bc080f97a3e6dc70dc305f3df841
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44053842"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="26048-103">Konfigurera Övrig e-post för organisationen</span><span class="sxs-lookup"><span data-stu-id="26048-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="26048-104">[Prioriterad inkorg](../setup/configure-focused-inbox.md) kommer att ersätta Övrig e-post.</span><span class="sxs-lookup"><span data-stu-id="26048-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="26048-105">Läs mer: [Uppdatera om fokuserad inkorg och våra planer för Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="26048-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="26048-106">Som administratör kan du behöva hantera övrig övrig övrig e-post i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26048-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="26048-107">Om du vill aktivera/inaktivera funktionen Övrig e-post för användare i organisationen måste du använda Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26048-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="26048-108">(Enskilda användare kan aktivera/inaktivera med hjälp av de här anvisningarna: [Aktivera/inaktivera Övrig e-post i Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx).)</span><span class="sxs-lookup"><span data-stu-id="26048-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx).)</span></span> 
  
<span data-ttu-id="26048-109">Läs artikeln [Använd PowerShell med Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) och [Ansluta till Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) för information om hur du använder Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26048-109">Check out [Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) and [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="26048-110">Du måste ha ett konto som har minst rollen Exchange Service-administratör och möjligheten att ansluta till Exchange Online med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26048-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="26048-111">Aktivera Övrig e-post med Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="26048-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="26048-p104">Du kan manuellt aktivera Övrig e-post för en postlåda genom att köra cmdleten [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446). Du kan också visa inställningar för Övrig e-post för postlådor i din organisation genom att köra cmdleten [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759).</span><span class="sxs-lookup"><span data-stu-id="26048-p104">You can enable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet. You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="26048-114">Aktivera Övrig e-post för en enskild användare med namnet Diana Bergqvist</span><span class="sxs-lookup"><span data-stu-id="26048-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="26048-115">Inaktivera Övrig e-post med Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="26048-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="26048-p105">Du kan manuellt inaktivera Övrig e-post för en postlåda genom att köra cmdleten [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446). Du kan också visa inställningarna för **Övrig e-post** för postlådor i din organisation genom att köra cmdleten [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759).</span><span class="sxs-lookup"><span data-stu-id="26048-p105">You can disable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet. You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="26048-118">Inaktivera Övrig e-post för en enskild användare med namnet Diana Bergqvist:</span><span class="sxs-lookup"><span data-stu-id="26048-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="26048-119">Om du använder PowerShell för att skapa flera användare samtidigt måste du köra [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) mot varje användares postlåda för att hantera Övrig e-post.</span><span class="sxs-lookup"><span data-stu-id="26048-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="26048-120">När visas alternativet för att aktivera/inaktivera Övrig e-post för användare i Outlook på webben?</span><span class="sxs-lookup"><span data-stu-id="26048-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="26048-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="26048-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="26048-122">Som administratör kan du återaktivera övrig e-post med Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26048-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="26048-123">När du gjort detta inaktiveras Prioriterad inkorg och Övrig e-post aktiveras igen.</span><span class="sxs-lookup"><span data-stu-id="26048-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="26048-124">**Om du använder Outlook på webben med en Microsoft 365 Business Premium-prenumeration:**</span><span class="sxs-lookup"><span data-stu-id="26048-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="26048-125">Om användaren har aktiverat Övrig e-post:</span><span class="sxs-lookup"><span data-stu-id="26048-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="26048-126">Inställningar för Övrig e-post visas</span><span class="sxs-lookup"><span data-stu-id="26048-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="26048-127">Om användaren har aktiverat Prioriterad inkorg:</span><span class="sxs-lookup"><span data-stu-id="26048-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="26048-128">Inställningarna för Övrig e-post visas inte</span><span class="sxs-lookup"><span data-stu-id="26048-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="26048-129">Om varken Övrig e-post eller Prioriterad inkorg har aktiverats:</span><span class="sxs-lookup"><span data-stu-id="26048-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="26048-130">Både Övrig e-post och Prioriterad inkorg visas som alternativ i användarens e-postinställningar</span><span class="sxs-lookup"><span data-stu-id="26048-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="26048-131">**Om du använder Outlook.com:**</span><span class="sxs-lookup"><span data-stu-id="26048-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="26048-132">Om användaren har aktiverat Övrig e-post:</span><span class="sxs-lookup"><span data-stu-id="26048-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="26048-133">Inställningar för Övrig e-post visas</span><span class="sxs-lookup"><span data-stu-id="26048-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="26048-134">Om användaren har aktiverat Prioriterad inkorg:</span><span class="sxs-lookup"><span data-stu-id="26048-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="26048-135">Inställningarna för Övrig e-post visas inte</span><span class="sxs-lookup"><span data-stu-id="26048-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="26048-136">Om varken Övrig e-post eller Prioriterad inkorg har aktiverats:</span><span class="sxs-lookup"><span data-stu-id="26048-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="26048-137">Både Övrig e-post och Prioriterad inkorg visas som alternativ i användarens e-postinställningar</span><span class="sxs-lookup"><span data-stu-id="26048-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="26048-138">Om användaren har aktiverat Prioriterad inkorg tidigare:</span><span class="sxs-lookup"><span data-stu-id="26048-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="26048-139">Inställningarna för Övrig e-post visas aldrig</span><span class="sxs-lookup"><span data-stu-id="26048-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="26048-140">I annat fall</span><span class="sxs-lookup"><span data-stu-id="26048-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="26048-141">Övrig e-post visas</span><span class="sxs-lookup"><span data-stu-id="26048-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="26048-142">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="26048-142">Related articles</span></span>
<span data-ttu-id="26048-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="26048-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="26048-144">Använd Övrig e-post för att sortera meddelanden med låg prioritet i Outlook</span><span class="sxs-lookup"><span data-stu-id="26048-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.office.com/article/use-clutter-to-sort-low-priority-messages-in-outlook-7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[<span data-ttu-id="26048-145">Använd Övrig e-post för att sortera meddelanden med låg prioritet i OWA</span><span class="sxs-lookup"><span data-stu-id="26048-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.office.com/article/fe4d64ca-bf73-48f1-91b4-9a659e008bce.aspx)
    
[<span data-ttu-id="26048-146">Stänga av Övrig e-post i Outlook</span><span class="sxs-lookup"><span data-stu-id="26048-146">Turn off Clutter in Outlook</span></span>](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)
    

