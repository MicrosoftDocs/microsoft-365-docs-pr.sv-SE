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
description: Du kan få felmeddelanden när du konfigurerade delade postlådor. Prova de här lösningarna om du upplever problem med delade postlådor.
ms.openlocfilehash: 89cdfbe29ab035b1eb6c3a0183629eef59d67477
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706136"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="62761-104">Lösa problem med delade postlådor</span><span class="sxs-lookup"><span data-stu-id="62761-104">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="62761-105">Om du ser felmeddelanden när du skapar eller använder en delad postlåda kan du prova de här möjliga lösningarna.</span><span class="sxs-lookup"><span data-stu-id="62761-105">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="62761-106">Fel när delade postlådor skapas</span><span class="sxs-lookup"><span data-stu-id="62761-106">Error when creating shared mailboxes</span></span>
<span data-ttu-id="62761-107"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="62761-107"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="62761-108">Om du ser felmeddelandet används proxyadressen "smtp:<namn på delad postlåda " redan av proxyadresserna eller **\> LegacyExchangeDN för " \<name> ". Välj en annan proxyadress**, det innebär att du försöker ge den delade postlådan ett namn som redan används.</span><span class="sxs-lookup"><span data-stu-id="62761-108">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="62761-109">Anta att du vill ha delade postlådor med namnen info@domän1 och info@domän2.</span><span class="sxs-lookup"><span data-stu-id="62761-109">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="62761-110">Du kan göra det på två sätt:</span><span class="sxs-lookup"><span data-stu-id="62761-110">There are two ways to do this:</span></span>

  - <span data-ttu-id="62761-111">Använd Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="62761-111">Use Windows PowerShell.</span></span> <span data-ttu-id="62761-112">Anvisningar finns i det här blogginlägget: [Skapa delade postlådor med samma alias på olika domäner](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="62761-112">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="62761-113">Ge den andra delade postlådan ett annat namn på en gång för att komma runt felet.</span><span class="sxs-lookup"><span data-stu-id="62761-113">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="62761-114">I administrationscentret byter du sedan namn på den delade postlådan till det du vill.</span><span class="sxs-lookup"><span data-stu-id="62761-114">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="62761-115">Felmeddelande om att du inte har skicka behörigheter när du använder en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="62761-115">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="62761-116">Om du har skapat en delad postlåda och sedan försöker skicka ett meddelande från den, kan du få följande:</span><span class="sxs-lookup"><span data-stu-id="62761-116">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="62761-117">**Det här meddelandet kunde inte skickas. Du har inte behörighet att skicka meddelandet åt den angivna användaren.**</span><span class="sxs-lookup"><span data-stu-id="62761-117">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="62761-118">Det här meddelandet visas Microsoft 365 har problem med replikeringssvarstid.</span><span class="sxs-lookup"><span data-stu-id="62761-118">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="62761-119">Den bör försvinna om någon timme, när informationen om din nya delade postlåda (eller användare som lagts till) replikeras i alla våra datacenter.</span><span class="sxs-lookup"><span data-stu-id="62761-119">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="62761-120">Vänta en timme och försök sedan igen för att skicka ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="62761-120">Wait an hour and then try again to send a message.</span></span>

## <a name="related-content"></a><span data-ttu-id="62761-121">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="62761-121">Related content</span></span>

<span data-ttu-id="62761-122">[Om delade postlådor](about-shared-mailboxes.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="62761-122">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="62761-123">[Skapa en delad postlåda](create-a-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="62761-123">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="62761-124">[Konfigurera en delad postlåda](configure-a-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="62761-124">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="62761-125">[Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="62761-125">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="62761-126">[Ta bort en licens från en delad postlåda](remove-license-from-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="62761-126">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>


    

