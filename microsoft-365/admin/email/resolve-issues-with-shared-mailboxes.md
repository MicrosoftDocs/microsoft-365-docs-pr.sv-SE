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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Prova de här lösningarna om du upplever problem med delade postlådor.
ms.openlocfilehash: ba62db76edff6e4ab3d738ed0af8db2a40c18394
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926492"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="c7414-103">Lösa problem med delade postlådor</span><span class="sxs-lookup"><span data-stu-id="c7414-103">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="c7414-104">Om du får felmeddelanden när du skapar eller använder en delad postlåda kan du prova de här lösningarna.</span><span class="sxs-lookup"><span data-stu-id="c7414-104">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="c7414-105">Fel när delade postlådor skapas</span><span class="sxs-lookup"><span data-stu-id="c7414-105">Error when creating shared mailboxes</span></span>
<span data-ttu-id="c7414-106"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="c7414-106"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="c7414-107">Om du ser felmeddelandet används proxyadressen "smtp:<namn på delad postlåda " redan av proxyadresserna eller **\> LegacyExchangeDN för " \<name> ". Välj en annan proxyadress,** vilket innebär att du försöker ge den delade postlådan ett namn som redan används.</span><span class="sxs-lookup"><span data-stu-id="c7414-107">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="c7414-108">Anta att du vill ha delade postlådor med namnen info@domän1 och info@domän2.</span><span class="sxs-lookup"><span data-stu-id="c7414-108">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="c7414-109">Du kan göra det på två sätt:</span><span class="sxs-lookup"><span data-stu-id="c7414-109">There are two ways to do this:</span></span>

  - <span data-ttu-id="c7414-110">Använd Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7414-110">Use Windows PowerShell.</span></span> <span data-ttu-id="c7414-111">Anvisningar finns i det här blogginlägget: [Skapa delade postlådor med samma alias på olika domäner](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="c7414-111">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="c7414-112">Ge den andra delade postlådan ett annat namn från början för att komma runt felet.</span><span class="sxs-lookup"><span data-stu-id="c7414-112">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="c7414-113">Byt sedan namn på den delade postlådan till det du vill i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="c7414-113">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="c7414-114">Fel om att du inte har skickat behörigheter när du använder en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="c7414-114">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="c7414-115">Om du har skapat en delad postlåda och sedan försöker skicka ett meddelande från den kan följande hända:</span><span class="sxs-lookup"><span data-stu-id="c7414-115">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="c7414-116">**Det här meddelandet kunde inte skickas. Du har inte behörighet att skicka meddelandet åt den angivna användaren.**</span><span class="sxs-lookup"><span data-stu-id="c7414-116">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="c7414-117">Det här meddelandet visas när Microsoft 365 har problem med replikeringssvarstid.</span><span class="sxs-lookup"><span data-stu-id="c7414-117">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="c7414-118">Den bör försvinna om någon timme, när informationen om den nya delade postlådan (eller den nya användaren) replikeras över alla våra datacenter.</span><span class="sxs-lookup"><span data-stu-id="c7414-118">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="c7414-119">Vänta en timme och försök sedan igen för att skicka ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="c7414-119">Wait an hour and then try again to send a message.</span></span>

## <a name="related-articles"></a><span data-ttu-id="c7414-120">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="c7414-120">Related articles</span></span>

[<span data-ttu-id="c7414-121">Om delade postlådor</span><span class="sxs-lookup"><span data-stu-id="c7414-121">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="c7414-122">Skapa en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="c7414-122">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="c7414-123">Konfigurera en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="c7414-123">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="c7414-124">Konvertera en användarpostlåda till en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="c7414-124">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="c7414-125">Ta bort en licens från en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="c7414-125">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)


    

