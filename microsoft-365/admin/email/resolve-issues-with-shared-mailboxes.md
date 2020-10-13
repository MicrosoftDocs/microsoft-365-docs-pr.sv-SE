---
title: Lösa problem med delade postlådor
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Prova de här lösningarna om du får problem med delade post lådor.
ms.openlocfilehash: c889d3aa2fab8c2dce4cc2a8a00ef49a905363a1
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445513"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="6be08-103">Lösa problem med delade postlådor</span><span class="sxs-lookup"><span data-stu-id="6be08-103">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="6be08-104">Om du ser fel meddelanden när du skapar eller använder en delad post låda kan du försöka med följande.</span><span class="sxs-lookup"><span data-stu-id="6be08-104">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="6be08-105">Fel när delade post lådor skapades</span><span class="sxs-lookup"><span data-stu-id="6be08-105">Error when creating shared mailboxes</span></span>
<span data-ttu-id="6be08-106"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="6be08-106"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="6be08-107">Om du får fel meddelandet " **" SMTP: <delade post lådans namn \> "används redan av proxyadresser eller LegacyExchangeDN av" \<name> ". Välj en annan proxyadress**, det innebär att du försöker ge den delade post lådan ett namn som redan används.</span><span class="sxs-lookup"><span data-stu-id="6be08-107">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="6be08-108">Anta att du vill ha delade postlådor med namnen info@domän1 och info@domän2.</span><span class="sxs-lookup"><span data-stu-id="6be08-108">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="6be08-109">Du kan göra det på två sätt:</span><span class="sxs-lookup"><span data-stu-id="6be08-109">There are two ways to do this:</span></span>

  - <span data-ttu-id="6be08-110">Använd Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6be08-110">Use Windows PowerShell.</span></span> <span data-ttu-id="6be08-111">Anvisningar finns i det här blogg inlägget: [skapa delade post lådor med samma alias på olika domäner](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="6be08-111">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="6be08-112">Ge den andra delade post lådan något annat från början för att få veta mer om felet.</span><span class="sxs-lookup"><span data-stu-id="6be08-112">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="6be08-113">I Admin Center byter du namn på den delade post lådan till det du vill ha.</span><span class="sxs-lookup"><span data-stu-id="6be08-113">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="6be08-114">Fel om att inte ha behörighet att skicka när du använder en delad post låda</span><span class="sxs-lookup"><span data-stu-id="6be08-114">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="6be08-115">Om du har skapat en delad post låda och sedan försöker skicka ett meddelande från den kan du få följande:</span><span class="sxs-lookup"><span data-stu-id="6be08-115">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="6be08-116">**Det gick inte att skicka meddelandet. Du har inte behörighet att skicka meddelandet å angiven användares vägnar.**</span><span class="sxs-lookup"><span data-stu-id="6be08-116">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="6be08-117">Det här meddelandet visas när Microsoft 365 drabbas av ett problem med replikeringsfördröjning.</span><span class="sxs-lookup"><span data-stu-id="6be08-117">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="6be08-118">Det ska gå längre tid än en timme, eller så när informationen om den nya delade post lådan (eller tillagd användare) replikeras i alla data Center.</span><span class="sxs-lookup"><span data-stu-id="6be08-118">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="6be08-119">Vänta en timme och försök sedan igen för att skicka ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="6be08-119">Wait an hour and then try again to send a message.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6be08-120">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="6be08-120">Related articles</span></span>

[<span data-ttu-id="6be08-121">Om delade postlådor</span><span class="sxs-lookup"><span data-stu-id="6be08-121">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="6be08-122">Skapa en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="6be08-122">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="6be08-123">Konfigurera en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="6be08-123">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="6be08-124">Konvertera en användarpostlåda till en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="6be08-124">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="6be08-125">Ta bort en licens från en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="6be08-125">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)


    

