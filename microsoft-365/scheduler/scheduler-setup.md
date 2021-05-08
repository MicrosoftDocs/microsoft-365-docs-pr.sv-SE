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
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286252"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="3f257-103">Konfigurera Scheduler för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3f257-103">Setting up Scheduler for Microsoft 365</span></span>

<span data-ttu-id="3f257-104">Om du vill konfigurera Schemaläggaren för Microsoft 365 är följande förutsättningar:</span><span class="sxs-lookup"><span data-stu-id="3f257-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

|<span data-ttu-id="3f257-105">**Vad behöver jag?**</span><span class="sxs-lookup"><span data-stu-id="3f257-105">**What do I need?**</span></span> |<span data-ttu-id="3f257-106">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="3f257-106">**Description**</span></span> |
|-------------------|-------------|
|<span data-ttu-id="3f257-107">Cortana-postlåda</span><span class="sxs-lookup"><span data-stu-id="3f257-107">Cortana mailbox</span></span> |<span data-ttu-id="3f257-108">Innehavaradministratörer måste ange att en postlåda ska fungera som "Cortana"-postlåda (d.v.s. cortana@yourdomain.com).</span><span class="sxs-lookup"><span data-stu-id="3f257-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="3f257-109">Exchange Online postlåda</span><span class="sxs-lookup"><span data-stu-id="3f257-109">Exchange Online mailbox</span></span> |<span data-ttu-id="3f257-110">Användarna måste ha en e Exchange Online post och kalender</span><span class="sxs-lookup"><span data-stu-id="3f257-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="3f257-111">Scheduler-licens</span><span class="sxs-lookup"><span data-stu-id="3f257-111">Scheduler license</span></span> |<span data-ttu-id="3f257-112">Information om licensiering och priser finns i [Schemaläggare för Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span><span class="sxs-lookup"><span data-stu-id="3f257-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="3f257-113">Skapa en postlåda för Cortana</span><span class="sxs-lookup"><span data-stu-id="3f257-113">Create a mailbox for Cortana</span></span>
<span data-ttu-id="3f257-114">En Exchange postlåda i klientorganisationen fungerar som Cortana-postlådan för din klientorganisation att skicka och ta emot e-postmeddelanden till och från Cortana.</span><span class="sxs-lookup"><span data-stu-id="3f257-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="3f257-115">Alla e-postmeddelanden som skickas till Cortana behålls i klientorganisationens Cortana-postlåda baserat på bevarandeprincipen.</span><span class="sxs-lookup"><span data-stu-id="3f257-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="3f257-116">Använd administrationscentret Microsoft 365 skapa en ny postlåda.</span><span class="sxs-lookup"><span data-stu-id="3f257-116">Use the Microsoft 365 admin center to create a new mailbox.</span></span> <span data-ttu-id="3f257-117">En 30-dagarsbevarandeprincip rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="3f257-117">A 30-day retention policy is recommended.</span></span> <span data-ttu-id="3f257-118">Använd namnet Cortana i postlådans primära SMTP-adress.</span><span class="sxs-lookup"><span data-stu-id="3f257-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="3f257-119">Namn som "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" eller "Cortana.Scheduler@yourdomain.com" rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="3f257-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>
- <span data-ttu-id="3f257-120">Kontakta Microsoft (scheduler_m365@microsoft.com) för att aktivera Cortana-postlådan.</span><span class="sxs-lookup"><span data-stu-id="3f257-120">Contact Microsoft (scheduler_m365@microsoft.com) to enable your Cortana mailbox.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="3f257-121">Du måste kontakta Microsoft om du vill konfigurera Cortana-postlådan så att den använder scheduler-tjänsten genom att skicka e-scheduler_m365@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="3f257-121">You must contact Microsoft to configure your Cortana mailbox to use the Scheduler service by emailing scheduler_m365@microsoft.com.</span></span> <span data-ttu-id="3f257-122">Det kan ta upp till två veckor att aktivera Cortana-postlådan.</span><span class="sxs-lookup"><span data-stu-id="3f257-122">Enabling your Cortana mailbox may take up to two weeks.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="3f257-123">Exchange Online postlåda</span><span class="sxs-lookup"><span data-stu-id="3f257-123">Exchange Online mailbox</span></span>
<span data-ttu-id="3f257-124">Schemaläggaren är ett tillägg till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f257-124">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="3f257-125">Mötesorganisatörer måste ha Exchange Online postlåda och kalender för att Schemaläggaren ska fungera.</span><span class="sxs-lookup"><span data-stu-id="3f257-125">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="3f257-126">Krav för Exchange</span><span class="sxs-lookup"><span data-stu-id="3f257-126">Exchange requirements</span></span>

<span data-ttu-id="3f257-127">Förutom Schemaläggaren för licensiering måste du ha någon av följande licenser:</span><span class="sxs-lookup"><span data-stu-id="3f257-127">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="3f257-128">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="3f257-128">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="3f257-129">Business Basic, Business, Business Standard, Business Premium</span><span class="sxs-lookup"><span data-stu-id="3f257-129">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="3f257-130">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="3f257-130">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="3f257-131">Business Essentials, Business Premium</span><span class="sxs-lookup"><span data-stu-id="3f257-131">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="3f257-132">Exchange Online Abonnemang 1- eller abonnemang 2-licens.</span><span class="sxs-lookup"><span data-stu-id="3f257-132">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="3f257-133">**Scheduler för Microsoft 365** är inte tillgängligt för användare av Office 365 som drivs av 21Vianet i Kina.</span><span class="sxs-lookup"><span data-stu-id="3f257-133">**Scheduler for Microsoft 365** isn't available for users of Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="3f257-134">Det är inte heller tillgängligt för användare av Microsoft 365 med det tyska molnet som använder dataförvaltaren tyska Telekom.</span><span class="sxs-lookup"><span data-stu-id="3f257-134">It's also not available for users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="3f257-135">Det stöds för användare i Tyskland vars dataplats inte finns i det tyska datacentret.</span><span class="sxs-lookup"><span data-stu-id="3f257-135">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
><span data-ttu-id="3f257-136">Den här funktionen stöds inte heller för användare av Government Cloud, GCC, Consumer, GCC High eller DoD.</span><span class="sxs-lookup"><span data-stu-id="3f257-136">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>
