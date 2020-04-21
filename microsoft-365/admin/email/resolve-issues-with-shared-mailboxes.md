---
title: Lösa problem med delade postlådor
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
description: Prova de här lösningarna om du får problem med delade postlådor.
ms.openlocfilehash: 52aac8ab6936dfeba2ae4b5b7a80c45029ec6105
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628753"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="cd797-103">Lösa problem med delade postlådor</span><span class="sxs-lookup"><span data-stu-id="cd797-103">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="cd797-104">Om felmeddelanden visas när du skapar eller använder en delad postlåda kan du prova de här möjliga lösningarna.</span><span class="sxs-lookup"><span data-stu-id="cd797-104">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="cd797-105">Fel vid skapande av delade postlådor</span><span class="sxs-lookup"><span data-stu-id="cd797-105">Error when creating shared mailboxes</span></span>
<span data-ttu-id="cd797-106"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="cd797-106"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="cd797-107">Om felmeddelandet visas **används proxyadressen "smtp:<delat\>postlådenamn " redan av proxyadresserna eller\<LegacyExchangeDN för " namn>". Välj en annan proxyadress**betyder det att du försöker ge den delade postlådan ett namn som redan används.</span><span class="sxs-lookup"><span data-stu-id="cd797-107">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="cd797-108">Anta att du vill ha delade postlådor med namnen info@domän1 och info@domän2.</span><span class="sxs-lookup"><span data-stu-id="cd797-108">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="cd797-109">Du kan göra det på två sätt:</span><span class="sxs-lookup"><span data-stu-id="cd797-109">There are two ways to do this:</span></span>

  - <span data-ttu-id="cd797-110">Använd Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd797-110">Use Windows PowerShell.</span></span> <span data-ttu-id="cd797-111">Se det här blogginlägget för instruktioner: [Skapa delade postlådor med samma alias på olika domäner](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="cd797-111">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="cd797-112">Ge den andra delade postlådan namnet något annat än början för att komma runt felet.</span><span class="sxs-lookup"><span data-stu-id="cd797-112">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="cd797-113">Byt sedan namn på den delade postlådan till det du vill att den ska vara i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="cd797-113">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="cd797-114">Fel om att inte ha skicka behörigheter när du använder en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="cd797-114">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="cd797-115">Om du har skapat en delad postlåda och sedan försöker skicka ett meddelande från den kan du få följande:</span><span class="sxs-lookup"><span data-stu-id="cd797-115">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="cd797-116">**Det gick inte att skicka det här meddelandet. Du har inte behörighet att skicka meddelandet för den angivna användarens räkning.**</span><span class="sxs-lookup"><span data-stu-id="cd797-116">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="cd797-117">Det här meddelandet visas när Microsoft 365 har ett replikeringsfördröjningsproblem.</span><span class="sxs-lookup"><span data-stu-id="cd797-117">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="cd797-118">Det bör försvinna inom en timme eller så, när informationen om din nya delade postlåda (eller tillagd användare) replikeras över alla våra datacenter.</span><span class="sxs-lookup"><span data-stu-id="cd797-118">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="cd797-119">Vänta en timme och försök sedan igen för att skicka ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="cd797-119">Wait an hour and then try again to send a message.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cd797-120">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="cd797-120">Related articles</span></span>

[<span data-ttu-id="cd797-121">Om delade postlådor</span><span class="sxs-lookup"><span data-stu-id="cd797-121">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="cd797-122">Skapa en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="cd797-122">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="cd797-123">Konfigurera en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="cd797-123">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="cd797-124">Konvertera en användarpostlåda till en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="cd797-124">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="cd797-125">Ta bort en licens från en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="cd797-125">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)


    

