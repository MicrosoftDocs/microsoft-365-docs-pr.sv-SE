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
ms.openlocfilehash: f44dc509e28c19c320418c28dda6146331669cde
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314482"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="b7bea-103">Konfigurera Schemaläggaren för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b7bea-103">Setting up Scheduler for Microsoft 365</span></span>


<span data-ttu-id="b7bea-104">Om du vill konfigurera Schemaläggaren för Microsoft 365 är följande förutsättningar:</span><span class="sxs-lookup"><span data-stu-id="b7bea-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

| <span data-ttu-id="b7bea-105">Vad behöver jag?</span><span class="sxs-lookup"><span data-stu-id="b7bea-105">What do I need?</span></span> | <span data-ttu-id="b7bea-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b7bea-106">Description</span></span> |
|-------------------|-------------|
|<span data-ttu-id="b7bea-107">Cortana postlåda</span><span class="sxs-lookup"><span data-stu-id="b7bea-107">Cortana mailbox</span></span> |<span data-ttu-id="b7bea-108">Innehavaradministratörer måste ange att en postlåda ska fungera som "Cortana"-postlåda (d.v.s. cortana@yourdomain.com).</span><span class="sxs-lookup"><span data-stu-id="b7bea-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="b7bea-109">Exchange Online postlåda</span><span class="sxs-lookup"><span data-stu-id="b7bea-109">Exchange Online mailbox</span></span> |<span data-ttu-id="b7bea-110">Användarna måste ha en e Exchange Online post och kalender</span><span class="sxs-lookup"><span data-stu-id="b7bea-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="b7bea-111">Scheduler-licens</span><span class="sxs-lookup"><span data-stu-id="b7bea-111">Scheduler license</span></span> |<span data-ttu-id="b7bea-112">Information om licensiering och priser finns i [Schemaläggare för Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing).</span><span class="sxs-lookup"><span data-stu-id="b7bea-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="b7bea-113">Skapa en postlåda för Cortana</span><span class="sxs-lookup"><span data-stu-id="b7bea-113">Create a mailbox for Cortana</span></span>

<span data-ttu-id="b7bea-114">En Exchange postlåda i klientorganisationen fungerar som den Cortana postlådan för din klientorganisation att skicka och ta emot e-postmeddelanden till och Cortana.</span><span class="sxs-lookup"><span data-stu-id="b7bea-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="b7bea-115">Alla e-postmeddelanden som Cortana till andra sparas i klientorganisationens Cortana baserat på bevarandeprincipen.</span><span class="sxs-lookup"><span data-stu-id="b7bea-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="b7bea-116">Använd Administrationscenter för Microsoft 365 för att skapa en användarpostlåda.</span><span class="sxs-lookup"><span data-stu-id="b7bea-116">Use the Microsoft 365 admin center to create a user mailbox.</span></span> <span data-ttu-id="b7bea-117">En 30-dagarsbevarandeprincip rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="b7bea-117">A 30-day retention policy is recommended.</span></span> 
- <span data-ttu-id="b7bea-118">Använd namnet Cortana i postlådans primära SMTP-adress.</span><span class="sxs-lookup"><span data-stu-id="b7bea-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="b7bea-119">Namn som "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" eller "Cortana. Scheduler@yourdomain.com' rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="b7bea-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a><span data-ttu-id="b7bea-120">Ange postlådan som Schemaläggarassistenten</span><span class="sxs-lookup"><span data-stu-id="b7bea-120">Designate the mailbox as the Scheduler Assistant</span></span>

<span data-ttu-id="b7bea-121">När en unik postlåda Cortana schemaläggaren har skapats måste du utse postlådan till Microsoft 365 postlådan.</span><span class="sxs-lookup"><span data-stu-id="b7bea-121">After a unique mailbox for Cortana Scheduler has been created, you must designate the mailbox to Microsoft 365 formally.</span></span> <span data-ttu-id="b7bea-122">När du har angett Cortana Scheduler-postlådan blir den tillgänglig för att schemalägga möten för dina användare.</span><span class="sxs-lookup"><span data-stu-id="b7bea-122">After you designate the Cortana Scheduler mailbox, it will be available to schedule meetings on behalf of your users.</span></span>

<span data-ttu-id="b7bea-123">För att utse Cortana Scheduler-postlådan måste en behörig administratör köra ett PowerShell-kommando med en rad.</span><span class="sxs-lookup"><span data-stu-id="b7bea-123">To designate the Cortana Scheduler mailbox, an authorized admin must run a one-line PowerShell command.</span></span> 

1. <span data-ttu-id="b7bea-124">Anslut att Microsoft 365 köra utrymme för din organisation med fjärr-PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7bea-124">Connect to Microsoft 365 remote PowerShell run space for your organization.</span></span>

2. <span data-ttu-id="b7bea-125">Kör följande PowerShell-skript för att ange postlådan för Scheduler:</span><span class="sxs-lookup"><span data-stu-id="b7bea-125">Run the following PowerShell script to designate the mailbox for Scheduler:</span></span>

    ```powershell
    Set-mailbox cortana@contoso.com -SchedulerAssistant:$true
    ```
    
    <span data-ttu-id="b7bea-126">När du har kört kommandot "uppsättning" på Cortana Scheduler-postlådan ställs en ny "PersistedCapability" in för postlådan som anger att den här postlådan är "SchedulerAssistant".</span><span class="sxs-lookup"><span data-stu-id="b7bea-126">After running this "set" command on the Cortana Scheduler mailbox, a new "PersistedCapability" is set on the mailbox to note that this mailbox is the "SchedulerAssistant".</span></span>

> [!NOTE]
> <span data-ttu-id="b7bea-127">Följ de här anvisningarna för att ansluta din organisation till PowerShell om du inte har gjort det tidigare: Anslut [att Microsoft 365 med PowerShell](../enterprise/connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="b7bea-127">Follow these steps to connect your organization to PowerShell if you’ve not done so previously: [Connect to Microsoft 365 with PowerShell](../enterprise/connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="b7bea-128">Om du vill ta reda på vilken postlåda i organisationen som är inställd Cortana – Schemaläggaren kör du funktionen Hämta:</span><span class="sxs-lookup"><span data-stu-id="b7bea-128">To discover which mailbox in your organization is currently set as the Cortana Scheduler assistant, run the get function:</span></span>

```powershell
Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> <span data-ttu-id="b7bea-129">Det kan ta upp till två timmar för Scheduler-postlådan att slutföra den fullständiga etableringen för att ange funktionen SchedulerAssistant.</span><span class="sxs-lookup"><span data-stu-id="b7bea-129">It might take up to two hours for the Scheduler mailbox to complete full provisioning to set the SchedulerAssistant capability.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="b7bea-130">Exchange Online postlåda</span><span class="sxs-lookup"><span data-stu-id="b7bea-130">Exchange Online mailbox</span></span>

<span data-ttu-id="b7bea-131">Schemaläggaren är ett tillägg till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b7bea-131">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="b7bea-132">Mötesorganisatörer måste ha Exchange Online postlåda och kalender för att Schemaläggaren ska fungera.</span><span class="sxs-lookup"><span data-stu-id="b7bea-132">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="b7bea-133">Krav för Exchange</span><span class="sxs-lookup"><span data-stu-id="b7bea-133">Exchange requirements</span></span>

<span data-ttu-id="b7bea-134">Förutom Schemaläggaren för licensiering måste du ha någon av följande licenser:</span><span class="sxs-lookup"><span data-stu-id="b7bea-134">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="b7bea-135">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="b7bea-135">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="b7bea-136">Business Basic, Business, Business Standard, Business Premium</span><span class="sxs-lookup"><span data-stu-id="b7bea-136">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="b7bea-137">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="b7bea-137">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="b7bea-138">Business Essentials, Business Premium</span><span class="sxs-lookup"><span data-stu-id="b7bea-138">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="b7bea-139">Exchange Online Abonnemang 1- eller abonnemang 2-licens.</span><span class="sxs-lookup"><span data-stu-id="b7bea-139">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="b7bea-140">**Scheduler for Microsoft 365** is currently available for worldwide multi-tenants, only in English.</span><span class="sxs-lookup"><span data-stu-id="b7bea-140">**Scheduler for Microsoft 365** is currently available for worldwide multi-tenants, in English only.</span></span></br>
>
> <span data-ttu-id="b7bea-141">Det är inte tillgängligt för användare av Office 365 som drivs av 21Vianet i Kina eller användare av Microsoft 365 med det tyska molnet som använder dataförvaltarens tyska Telekom.</span><span class="sxs-lookup"><span data-stu-id="b7bea-141">It is not available for users of Office 365 operated by 21Vianet in China or users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="b7bea-142">Det stöds för användare i Tyskland vars dataplats inte finns i det tyska datacentret.</span><span class="sxs-lookup"><span data-stu-id="b7bea-142">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
> <span data-ttu-id="b7bea-143">Den här funktionen stöds inte heller för användare av Government Cloud, GCC, Consumer, GCC High eller DoD.</span><span class="sxs-lookup"><span data-stu-id="b7bea-143">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>
