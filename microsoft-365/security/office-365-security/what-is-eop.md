---
title: Vad är EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: dansimp
ms.date: 02/25/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 393b0050-7c7e-49e6-a03d-b1e09fe4de9e
description: Detta inledande dokument hjälper dig att förstå Exchange Online Protection (EOP) och några viktiga terminologi. Detta gäller för kunder som skyddar Exchange Online-molnbaserade postlådor och EOP-fristående kunder som skyddar lokala postlådor som Exchange Server 2016.
ms.openlocfilehash: dc08507a80db8e15d2e08ff5b954dec1905cfada
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630923"
---
# <a name="what-is-exchange-online-protection-eop"></a><span data-ttu-id="8b036-104">Vad är Exchange Online Protection (EOP)</span><span class="sxs-lookup"><span data-stu-id="8b036-104">What is Exchange Online Protection (EOP)</span></span>

<span data-ttu-id="8b036-105">Exchange Online Protection (EOP) är en molnbaserad e-postfiltreringstjänst som hjälper till att skydda din organisation mot skräppost och skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="8b036-105">Exchange Online Protection (EOP) is a cloud-based email filtering service that helps protect your organization against spam and malware.</span></span> <span data-ttu-id="8b036-106">Om du har postlådor i Microsoft 365 skyddas de automatiskt av EOP eftersom det är en del av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="8b036-106">If you have mailboxes in Microsoft 365, they are automatically protected by EOP since it is part of the service.</span></span> <span data-ttu-id="8b036-107">Detta inkluderar organisationer som har postlådor i både Microsoft 365 och lokalt, vilket brukar kallas ett hybridscenario.</span><span class="sxs-lookup"><span data-stu-id="8b036-107">This includes organizations that have mailboxes in both Microsoft 365 and on-premise, which is commonly known as a hybrid scenario.</span></span> <span data-ttu-id="8b036-108">EOP fristående är också tillgängligt för kunder som inte har postlådor i molnet men vill skydda sina lokala postlådor.</span><span class="sxs-lookup"><span data-stu-id="8b036-108">EOP standalone is also available for customers who do not have mailboxes in the cloud but want to protect their on-premises mailboxes.</span></span>

<span data-ttu-id="8b036-109">EOP försöker filtrera bort skräp, hålla inkorgen borta från innehåll som användarna inte vill se.</span><span class="sxs-lookup"><span data-stu-id="8b036-109">EOP attempts to filter out junk, keeping your Inbox clear of content that users don't want to see.</span></span> <span data-ttu-id="8b036-110">Normalt levereras skräppost till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="8b036-110">Normally, junk mail is delivered to the Junk Email folder.</span></span> <span data-ttu-id="8b036-111">Vissa användare gillar att kontrollera att filtrering gör vad de vill så skräppost mappen är ett enkelt sätt för användare att kontrollera på egen hand.</span><span class="sxs-lookup"><span data-stu-id="8b036-111">Some users like to check to make sure the filtering is doing what they want so the Junk Email folder is an easy way for users to check on their own.</span></span>  

> [!TIP]
> <span data-ttu-id="8b036-112">Det är en bra sak när skräp eller på annat sätt dålig e-post går in i skräppostmappen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="8b036-112">It is a good thing when junk or otherwise bad email goes into the Junk Email folder automatically.</span></span> <span data-ttu-id="8b036-113">Tjänsten kommer att göra vad som är nödvändigt baserat på vad standard- eller anpassade administratörsinställningarna anger.</span><span class="sxs-lookup"><span data-stu-id="8b036-113">The service will do what is necessary based on what the default or the custom admin settings state.</span></span> <span data-ttu-id="8b036-114">Med andra ord bör användarna inte oroa sig för att se en hel del skräppost i skräppostmappen.</span><span class="sxs-lookup"><span data-stu-id="8b036-114">In other words, users should not worry about seeing a lot of spam mail in the Junk Email folder.</span></span> <span data-ttu-id="8b036-115">Om administratörer föredrar att flytta allt skräp utom synhåll, bör karantänen konfigureras.</span><span class="sxs-lookup"><span data-stu-id="8b036-115">If admins prefer to move all junk out of sight, then the Quarantine should be configured.</span></span> <span data-ttu-id="8b036-116">Mer information finns i artikeln [Karantänmeddelanden.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="8b036-116">For more details, see the [Quarantine email messages](quarantine-email-messages.md) article.</span></span>

## <a name="important-terms"></a><span data-ttu-id="8b036-117">Viktiga termer</span><span class="sxs-lookup"><span data-stu-id="8b036-117">Important terms</span></span>

<span data-ttu-id="8b036-118">**Inkommande**: Meddelanden som kommer till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8b036-118">**Inbound**: Messages that are coming into Microsoft 365.</span></span>

<span data-ttu-id="8b036-119">**Utgående**: Meddelanden som kommer från Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8b036-119">**Outbound**: Messages that are going out of Microsoft 365.</span></span>

<span data-ttu-id="8b036-120">**Internt**: Meddelanden som kommer från någon inom organisationen till någon inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="8b036-120">**Internal**: Messages that are from someone inside the organization to someone inside the organization.</span></span> <span data-ttu-id="8b036-121">Detta inkluderar kunder som är i hybridscenarier och en postlåda kan vara lokalt och den andra postlådan finns i molnet.</span><span class="sxs-lookup"><span data-stu-id="8b036-121">This includes customers who are in hybrid scenarios and one mailbox could be on-premises and the other mailbox is in the cloud.</span></span>

<span data-ttu-id="8b036-122">**False Negative (FN)**: Spam och annat skräp som felaktigt skickas in i inkorgen.</span><span class="sxs-lookup"><span data-stu-id="8b036-122">**False Negative (FN)**: Spam and other junk that incorrectly gets sent into the inbox.</span></span>

<span data-ttu-id="8b036-123">**Falskt positivt (FP)**: Legitima meddelanden som felaktigt får markeras som skräppost och sätts in i mappen Skräppost eller Karantän.</span><span class="sxs-lookup"><span data-stu-id="8b036-123">**False Positive (FP)**: Legitimate messages that incorrectly get marked as spam and put into the Junk Email folder or Quarantine.</span></span>

<span data-ttu-id="8b036-124">**Spam, även känd som oönskad e-post:** Detta kommer i form av kommersiell reklam, kedjebrev, politiska utskick, etc. Detta är e-post som användare inte registrerar sig för och från spammare som försöker värva produkter eller försöker begå bedrägeri.</span><span class="sxs-lookup"><span data-stu-id="8b036-124">**Spam, also known as unsolicited e-mail**: This comes in the form of commercial advertising, chain letters, political mailings, etc. This is email that users do not sign up for and from spammers who are trying to solicit products or attempting to commit fraud.</span></span>

<span data-ttu-id="8b036-125">**Phish**: Phishing är en speciell typ av spam som är avsedd att lura dig att ge upp personlig information i syfte att begå identitetsstöld eller bedrägeri.</span><span class="sxs-lookup"><span data-stu-id="8b036-125">**Phish**: Phishing is a special type of spam that is intended to trick you into giving up personal information for the purpose of committing identity theft or fraud.</span></span> <span data-ttu-id="8b036-126">Den här typen av meddelande innehåller vanligtvis en skadlig länk eller bifogad fil, men inte alltid.</span><span class="sxs-lookup"><span data-stu-id="8b036-126">This type of message usually contains a malicious link or attachment, but not always.</span></span>

<span data-ttu-id="8b036-127">**Spoof:** Spoofing är när spammare smida FRÅN-huvudet så att meddelanden verkar ha sitt ursprung från någon eller någon annan än den faktiska källan.</span><span class="sxs-lookup"><span data-stu-id="8b036-127">**Spoof**: Spoofing is when spammers forge the FROM header so that messages appear to have originated from someone or somewhere other than the actual source.</span></span> <span data-ttu-id="8b036-128">Detta kan vara spam men oftast används för att phish användare.</span><span class="sxs-lookup"><span data-stu-id="8b036-128">This can be spam but most commonly used to phish users.</span></span>

<span data-ttu-id="8b036-129">**Personifiering:** Denna typ av spam är också ett sätt att förfalska avsändaradressen, men det görs genom att ändra en del av namnet eller domänen så att den ser ut som den verkliga källan.</span><span class="sxs-lookup"><span data-stu-id="8b036-129">**Impersonation**: This type of spam is also a way to forge the sender address, but it is done by modifying part of the name or domain so that it looks like the real source.</span></span> <span data-ttu-id="8b036-130">Till exempel Bi11@micr0s0ft.com, där "l" i Bill var faktiskt nummer elva och "o" i Microsoft ersattes med numret noll.</span><span class="sxs-lookup"><span data-stu-id="8b036-130">For example, Bi11@micr0s0ft.com, where the "l" in Bill was actually the number eleven and the "o" in Microsoft was replaced with the number zero.</span></span>

<span data-ttu-id="8b036-131">**Bulk**: Bulk post är oftast efterfrågas av användare, men ibland indirekt när företag säljer information till andra företag.</span><span class="sxs-lookup"><span data-stu-id="8b036-131">**Bulk**: Bulk mail is usually solicited by users, although sometimes indirectly when companies sell information to other companies.</span></span> <span data-ttu-id="8b036-132">Det är vanligt att användare avsiktligt registrera dig för massutskick (dvs. newletters) men glömma senare och tycker att det är spam.</span><span class="sxs-lookup"><span data-stu-id="8b036-132">It is common that users intentionally sign up for bulk mail (i.e. newletters) but forget later on and think it is spam.</span></span> <span data-ttu-id="8b036-133">Massutskick blir skräppost när massutskick skickar mer än användare registrerar sig och klagomålsnivåerna blir för höga.</span><span class="sxs-lookup"><span data-stu-id="8b036-133">Bulk mail becomes spam when bulk mailers send more than users sign up and complaint levels get too high.</span></span>
