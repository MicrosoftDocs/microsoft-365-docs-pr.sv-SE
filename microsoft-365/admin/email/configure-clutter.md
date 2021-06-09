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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Lär dig att aktivera eller inaktivera funktionen Övrig e-post för alla eller vissa användare i organisationen, med hjälp Exchange PowerShell. '
ms.openlocfilehash: 059fb8e626a0b05e0224fc89931453aaae43be0b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706123"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="4c672-103">Konfigurera Övrig e-post för organisationen</span><span class="sxs-lookup"><span data-stu-id="4c672-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="4c672-104">[Prioriterad inkorg](../setup/configure-focused-inbox.md) kommer att ersätta Övrig e-post.</span><span class="sxs-lookup"><span data-stu-id="4c672-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="4c672-105">Läs mer: [Uppdaterad information om Prioriterad inkorg och våra planer för Övrig e-post](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="4c672-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="4c672-106">Som administratör kan du behöva hantera funktionen Övrig e-post i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c672-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="4c672-107">Om du vill aktivera/inaktivera funktionen Övrig e-post för användare i organisationen måste du använda Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c672-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="4c672-108">(Enskilda användare kan aktivera/inaktivera med hjälp av de här anvisningarna: [Aktivera/inaktivera Övrig e-Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span><span class="sxs-lookup"><span data-stu-id="4c672-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span></span>
  
<span data-ttu-id="4c672-109">Läs artikeln [Använd PowerShell med Exchange Online](/powershell/exchange/exchange-online-powershell) och [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) för information om hur du använder Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c672-109">Check out [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="4c672-110">Du måste ha ett konto som har minst rollen Exchange tjänstadministratör och möjlighet att ansluta till Exchange Online med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c672-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="4c672-111">Aktivera Övrig e-post med Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c672-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="4c672-p104">Du kan manuellt aktivera Övrig e-post för en postlåda genom att köra cmdleten [Set-Clutter](/powershell/module/exchange/set-clutter). Du kan också visa inställningar för Övrig e-post för postlådor i din organisation genom att köra cmdleten [Get-Clutter](/powershell/module/exchange/get-clutter).</span><span class="sxs-lookup"><span data-stu-id="4c672-p104">You can enable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet. You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="4c672-114">Aktivera Övrig e-post för en enskild användare med namnet Diana Bergqvist</span><span class="sxs-lookup"><span data-stu-id="4c672-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="4c672-115">Inaktivera Övrig e-post med Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c672-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="4c672-p105">Du kan manuellt inaktivera Övrig e-post för en postlåda genom att köra cmdleten [Set-Clutter](/powershell/module/exchange/set-clutter). Du kan också visa inställningarna för **Övrig e-post** för postlådor i din organisation genom att köra cmdleten [Get-Clutter](/powershell/module/exchange/get-clutter).</span><span class="sxs-lookup"><span data-stu-id="4c672-p105">You can disable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet. You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="4c672-118">Inaktivera Övrig e-post för en enskild användare med namnet Diana Bergqvist:</span><span class="sxs-lookup"><span data-stu-id="4c672-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="4c672-119">Om du använder PowerShell för att skapa flera användare samtidigt måste du köra [Set-Clutter](/powershell/module/exchange/set-clutter) mot varje användares postlåda för att hantera Övrig e-post.</span><span class="sxs-lookup"><span data-stu-id="4c672-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](/powershell/module/exchange/set-clutter) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="4c672-120">När visas alternativet för att aktivera/inaktivera Övrig e-post för användare i Outlook på webben?</span><span class="sxs-lookup"><span data-stu-id="4c672-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="4c672-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="4c672-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="4c672-122">Som administratör kan du återaktivera Övrig e-post med Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c672-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="4c672-123">När du gjort detta inaktiveras Prioriterad inkorg och Övrig e-post aktiveras igen.</span><span class="sxs-lookup"><span data-stu-id="4c672-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="4c672-124">**Om du använder en Outlook på webben med en Microsoft 365 Business Premium prenumeration:**</span><span class="sxs-lookup"><span data-stu-id="4c672-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="4c672-125">Om användaren har aktiverat Övrig e-post:</span><span class="sxs-lookup"><span data-stu-id="4c672-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="4c672-126">Inställningar för Övrig e-post visas</span><span class="sxs-lookup"><span data-stu-id="4c672-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="4c672-127">Om användaren har aktiverat Prioriterad inkorg:</span><span class="sxs-lookup"><span data-stu-id="4c672-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="4c672-128">Inställningarna för Övrig e-post visas inte</span><span class="sxs-lookup"><span data-stu-id="4c672-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="4c672-129">Om varken Övrig e-post eller Prioriterad inkorg har aktiverats:</span><span class="sxs-lookup"><span data-stu-id="4c672-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="4c672-130">Både Övrig e-post och Prioriterad inkorg visas som alternativ i användarens e-postinställningar</span><span class="sxs-lookup"><span data-stu-id="4c672-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="4c672-131">**Om du använder Outlook.com:**</span><span class="sxs-lookup"><span data-stu-id="4c672-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="4c672-132">Om användaren har aktiverat Övrig e-post:</span><span class="sxs-lookup"><span data-stu-id="4c672-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="4c672-133">Inställningar för Övrig e-post visas</span><span class="sxs-lookup"><span data-stu-id="4c672-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="4c672-134">Om användaren har aktiverat Prioriterad inkorg:</span><span class="sxs-lookup"><span data-stu-id="4c672-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="4c672-135">Inställningarna för Övrig e-post visas inte</span><span class="sxs-lookup"><span data-stu-id="4c672-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="4c672-136">Om varken Övrig e-post eller Prioriterad inkorg har aktiverats:</span><span class="sxs-lookup"><span data-stu-id="4c672-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="4c672-137">Både Övrig e-post och Prioriterad inkorg visas som alternativ i användarens e-postinställningar</span><span class="sxs-lookup"><span data-stu-id="4c672-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="4c672-138">Om användaren har aktiverat Prioriterad inkorg tidigare:</span><span class="sxs-lookup"><span data-stu-id="4c672-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="4c672-139">Inställningarna för Övrig e-post visas aldrig</span><span class="sxs-lookup"><span data-stu-id="4c672-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="4c672-140">I annat fall</span><span class="sxs-lookup"><span data-stu-id="4c672-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="4c672-141">Övrig e-post visas</span><span class="sxs-lookup"><span data-stu-id="4c672-141">Clutter settings will appear</span></span>
    
## <a name="related-content"></a><span data-ttu-id="4c672-142">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="4c672-142">Related content</span></span>

<span data-ttu-id="4c672-143">[Använd Övrig e-post för att sortera meddelanden med låg prioritet Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0) (artikel)</span><span class="sxs-lookup"><span data-stu-id="4c672-143">[Use Clutter to sort low priority messages in Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0) (article)</span></span>\
<span data-ttu-id="4c672-144">[Använd Övrig e-post för att sortera meddelanden med låg prioritet i OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) (artikel)</span><span class="sxs-lookup"><span data-stu-id="4c672-144">[Use Clutter to sort low priority messages in OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) (article)</span></span>\
<span data-ttu-id="4c672-145">[Inaktivera Övrig e-post i Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) (artikel)</span><span class="sxs-lookup"><span data-stu-id="4c672-145">[Turn off Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) (article)</span></span>
