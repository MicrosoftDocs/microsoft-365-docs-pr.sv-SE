---
title: Konfigurera Scheduler för Microsoft 365.
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Konfigurera Scheduler för Microsoft 365.
ms.openlocfilehash: 924b25e3d921f402c97632f7475ed5beea98d5c7
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362552"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="6f8c2-103">Konfigurera Schemaläggaren för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6f8c2-103">Setting up Scheduler for Microsoft 365</span></span>


<span data-ttu-id="6f8c2-104">Om du vill konfigurera Schemaläggaren för Microsoft 365 är följande förutsättningar:</span><span class="sxs-lookup"><span data-stu-id="6f8c2-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

| <span data-ttu-id="6f8c2-105">Vad behöver jag?</span><span class="sxs-lookup"><span data-stu-id="6f8c2-105">What do I need?</span></span> | <span data-ttu-id="6f8c2-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6f8c2-106">Description</span></span> |
|-------------------|-------------|
|<span data-ttu-id="6f8c2-107">Cortana postlåda</span><span class="sxs-lookup"><span data-stu-id="6f8c2-107">Cortana mailbox</span></span> |<span data-ttu-id="6f8c2-108">Innehavaradministratörer måste ange att en postlåda ska fungera som "Cortana"-postlåda (d.v.s. cortana@yourdomain.com).</span><span class="sxs-lookup"><span data-stu-id="6f8c2-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="6f8c2-109">Exchange Online postlåda</span><span class="sxs-lookup"><span data-stu-id="6f8c2-109">Exchange Online mailbox</span></span> |<span data-ttu-id="6f8c2-110">Användarna måste ha en e Exchange Online post och kalender</span><span class="sxs-lookup"><span data-stu-id="6f8c2-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="6f8c2-111">Scheduler-licens</span><span class="sxs-lookup"><span data-stu-id="6f8c2-111">Scheduler license</span></span> |<span data-ttu-id="6f8c2-112">Information om licensiering och priser finns i [Schemaläggare för Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing).</span><span class="sxs-lookup"><span data-stu-id="6f8c2-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="6f8c2-113">Skapa en postlåda för Cortana</span><span class="sxs-lookup"><span data-stu-id="6f8c2-113">Create a mailbox for Cortana</span></span>

<span data-ttu-id="6f8c2-114">En Exchange postlåda i klientorganisationen fungerar som den Cortana postlådan för din klientorganisation att skicka och ta emot e-postmeddelanden till och Cortana.</span><span class="sxs-lookup"><span data-stu-id="6f8c2-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="6f8c2-115">Alla e-postmeddelanden som Cortana till andra sparas i klientorganisationens Cortana baserat på bevarandeprincipen.</span><span class="sxs-lookup"><span data-stu-id="6f8c2-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="6f8c2-116">Använd Administrationscenter för Microsoft 365 för att skapa en användarpostlåda.</span><span class="sxs-lookup"><span data-stu-id="6f8c2-116">Use the Microsoft 365 admin center to create a user mailbox.</span></span> <span data-ttu-id="6f8c2-117">En 30-dagarsbevarandeprincip rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="6f8c2-117">A 30-day retention policy is recommended.</span></span> 
- <span data-ttu-id="6f8c2-118">Använd namnet Cortana i postlådans primära SMTP-adress.</span><span class="sxs-lookup"><span data-stu-id="6f8c2-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="6f8c2-119">Namn som "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" eller "Cortana. Scheduler@yourdomain.com' rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="6f8c2-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a><span data-ttu-id="6f8c2-120">Ange postlådan som Schemaläggarassistenten</span><span class="sxs-lookup"><span data-stu-id="6f8c2-120">Designate the mailbox as the Scheduler Assistant</span></span>

<span data-ttu-id="6f8c2-121">När en unik postlåda Cortana schemaläggaren har skapats måste du utse postlådan till Microsoft 365 postlådan.</span><span class="sxs-lookup"><span data-stu-id="6f8c2-121">After a unique mailbox for Cortana Scheduler has been created, you must designate the mailbox to Microsoft 365 formally.</span></span> <span data-ttu-id="6f8c2-122">När du har angett Cortana Scheduler-postlådan blir den tillgänglig för att schemalägga möten för dina användare.</span><span class="sxs-lookup"><span data-stu-id="6f8c2-122">After you designate the Cortana Scheduler mailbox, it will be available to schedule meetings on behalf of your users.</span></span>

<span data-ttu-id="6f8c2-123">För att utse Cortana Scheduler-postlådan måste en behörig administratör köra ett PowerShell-kommando med en rad.</span><span class="sxs-lookup"><span data-stu-id="6f8c2-123">To designate the Cortana Scheduler mailbox, an authorized admin must run a one-line PowerShell command.</span></span> 

1. <span data-ttu-id="6f8c2-124">Anslut att Microsoft 365 köra utrymme för din organisation med fjärr-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f8c2-124">Connect to Microsoft 365 remote PowerShell run space for your organization.</span></span>

2. <span data-ttu-id="6f8c2-125">Kör följande PowerShell-skript för att ange postlådan för Scheduler:</span><span class="sxs-lookup"><span data-stu-id="6f8c2-125">Run the following PowerShell script to designate the mailbox for Scheduler:</span></span>

    ```powershell
    Set-mailbox cortana@contoso.com -SchedulerAssistant:$true
    ```
    
    <span data-ttu-id="6f8c2-126">När du har kört kommandot "uppsättning" på Cortana Scheduler-postlådan ställs en ny "PersistedCapability" in för postlådan som anger att den här postlådan är "SchedulerAssistant".</span><span class="sxs-lookup"><span data-stu-id="6f8c2-126">After running this "set" command on the Cortana Scheduler mailbox, a new "PersistedCapability" is set on the mailbox to note that this mailbox is the "SchedulerAssistant".</span></span>

> [!NOTE]
> <span data-ttu-id="6f8c2-127">Följ de här anvisningarna för att ansluta din organisation till PowerShell om du inte har gjort det tidigare: Anslut [att Microsoft 365 med PowerShell](../enterprise/connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="6f8c2-127">Follow these steps to connect your organization to PowerShell if you’ve not done so previously: [Connect to Microsoft 365 with PowerShell](../enterprise/connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="6f8c2-128">Om du vill ta reda på vilken postlåda i organisationen som är inställd Cortana – Schemaläggaren kör du funktionen Hämta:</span><span class="sxs-lookup"><span data-stu-id="6f8c2-128">To discover which mailbox in your organization is currently set as the Cortana Scheduler assistant, run the get function:</span></span>

```powershell
Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> <span data-ttu-id="6f8c2-129">Det kan ta upp till två timmar för Scheduler-postlådan att slutföra den fullständiga etableringen för att ange funktionen SchedulerAssistant.</span><span class="sxs-lookup"><span data-stu-id="6f8c2-129">It might take up to two hours for the Scheduler mailbox to complete full provisioning to set the SchedulerAssistant capability.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="6f8c2-130">Exchange Online postlåda</span><span class="sxs-lookup"><span data-stu-id="6f8c2-130">Exchange Online mailbox</span></span>
<span data-ttu-id="6f8c2-131">En Schemaläggarlicens är ett tillägg till Microsoft 365 som gör att mötesorganisatören delegerar sina aktiviteter för mötesplanering till Schemaläggaren-assistenten.</span><span class="sxs-lookup"><span data-stu-id="6f8c2-131">A Scheduler license is an add-on to Microsoft 365, that enables the meeting organizer to delegate their meeting scheduling tasks to their Scheduler assistant.</span></span> <span data-ttu-id="6f8c2-132">För att Schemaläggaren ska fungera, vanligtvis via Microsoft 365 licens, kräver mötesorganisatörer följande komponenter:</span><span class="sxs-lookup"><span data-stu-id="6f8c2-132">For the Scheduler to work, typically through Microsoft 365 license, meeting organizers require the following components:</span></span>

- <span data-ttu-id="6f8c2-133">En postlåda som angetts som schemaläggarassistentpostlåda</span><span class="sxs-lookup"><span data-stu-id="6f8c2-133">A mailbox designated as Scheduler assistant mailbox</span></span>
- <span data-ttu-id="6f8c2-134">Scheduler-licens</span><span class="sxs-lookup"><span data-stu-id="6f8c2-134">Scheduler license</span></span>
- <span data-ttu-id="6f8c2-135">Exchange Online postlåda och kalender</span><span class="sxs-lookup"><span data-stu-id="6f8c2-135">Exchange Online mailbox and calendar</span></span>

<span data-ttu-id="6f8c2-136">Mötesdellådorna kräver inte schemaläggnings- eller Microsoft 365 licens.</span><span class="sxs-lookup"><span data-stu-id="6f8c2-136">The meeting attendees do not require Scheduler or Microsoft 365 license.</span></span>

## <a name="scheduler-end-user-license-requirements"></a><span data-ttu-id="6f8c2-137">Licenskrav för schemaläggaren</span><span class="sxs-lookup"><span data-stu-id="6f8c2-137">Scheduler end-user license requirements</span></span>

<span data-ttu-id="6f8c2-138">En Scheduler-licens kräver någon av följande licenser:</span><span class="sxs-lookup"><span data-stu-id="6f8c2-138">A Scheduler license requires one of the following licenses:</span></span>

- <span data-ttu-id="6f8c2-139">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="6f8c2-139">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="6f8c2-140">Business Basic, Business, Business Standard, Business Premium</span><span class="sxs-lookup"><span data-stu-id="6f8c2-140">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="6f8c2-141">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="6f8c2-141">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="6f8c2-142">Business Essentials, Business Premium</span><span class="sxs-lookup"><span data-stu-id="6f8c2-142">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="6f8c2-143">Exchange Online Abonnemang 1- eller abonnemang 2-licens.</span><span class="sxs-lookup"><span data-stu-id="6f8c2-143">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]

> <span data-ttu-id="6f8c2-144">Schemaläggaren för Microsoft 365 tillgänglig i globala miljöer med flera innehavare endast på engelska.</span><span class="sxs-lookup"><span data-stu-id="6f8c2-144">Scheduler for Microsoft 365 is available in worldwide multi-tenant environments in English only.</span></span> <span data-ttu-id="6f8c2-145">**Schemaläggaren för Microsoft 365** är inte tillgänglig för användare av:</span><span class="sxs-lookup"><span data-stu-id="6f8c2-145">**Scheduler for Microsoft 365** isn't available to users of:</span></span>

- <span data-ttu-id="6f8c2-146">Microsoft 365 som drivs av 21Vianet i Kina</span><span class="sxs-lookup"><span data-stu-id="6f8c2-146">Microsoft 365 operated by 21Vianet in China</span></span>
- <span data-ttu-id="6f8c2-147">Microsoft 365 med tyskt moln som använder dataförvaltaren tyska Telekom</span><span class="sxs-lookup"><span data-stu-id="6f8c2-147">Microsoft 365 with German cloud that uses the data trustee German Telekom</span></span>
- <span data-ttu-id="6f8c2-148">Government cloud including GCC, Consumer, GCC High, or DoD</span><span class="sxs-lookup"><span data-stu-id="6f8c2-148">Government cloud including GCC, Consumer, GCC High, or DoD</span></span>

<span data-ttu-id="6f8c2-149">Scheduler har stöd för användare i Tyskland vars dataplats inte finns i det tyska datacentret.</span><span class="sxs-lookup"><span data-stu-id="6f8c2-149">Scheduler does support users in Germany whose data location is not in the German datacenter.</span></span>
