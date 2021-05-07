---
title: Begränsningar när det gäller principer för kvarhållning och kvarhållningsetiketter
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: Förstå det högsta antalet principer och objekt per princip när det gäller principer för kvarhållning och kvarhållningsetiketter
ms.openlocfilehash: 007ca6eec50b243e1b820938ffa67553d7882c7b
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162930"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a><span data-ttu-id="73c36-103">Begränsningar när det gäller principer för kvarhållning och kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="73c36-103">Limits for retention policies and retention label policies</span></span>

><span data-ttu-id="73c36-104">*[Licensieringsvägledning för Microsoft 365 för säkerhet och efterlevnad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="73c36-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="73c36-105">När du använder [ principer för kvarhållning och kvarhållningsetiketter ](retention.md#retention-policies-and-retention-labels) för att automatiskt kvarhålla eller ta bort data åt organisationen så finns det några maxantal som du bör känna till.</span><span class="sxs-lookup"><span data-stu-id="73c36-105">When you use [retention policies and retention label policies](retention.md#retention-policies-and-retention-labels) to automatically retain or delete data for your organization, there are some maximum numbers to be aware of.</span></span>

## <a name="maximum-number-of-policies-per-tenant"></a><span data-ttu-id="73c36-106">Högsta antal principer per klientorganisation</span><span class="sxs-lookup"><span data-stu-id="73c36-106">Maximum number of policies per tenant</span></span>

<span data-ttu-id="73c36-107">En enskild klientorganisation kan ha högst 10 000 principer (alla konfigurationer).</span><span class="sxs-lookup"><span data-stu-id="73c36-107">A single tenant can have a maximum of 10,000 policies (any configuration).</span></span> <span data-ttu-id="73c36-108">Maxantalet inkluderar olika kvarhållningsprinciper och andra efterlevnadsprinciper, till exempel DLP-principer.</span><span class="sxs-lookup"><span data-stu-id="73c36-108">This maximum number includes the different policies for retention and other policies for compliance, such as DLP policies.</span></span>

<span data-ttu-id="73c36-109">Högsta antal kvarhållningsprinciper per arbetsbelastning:</span><span class="sxs-lookup"><span data-stu-id="73c36-109">Maximum number of policies for retention per workload:</span></span>

- <span data-ttu-id="73c36-110">Exchange Online (alla konfigurationer): 1 800</span><span class="sxs-lookup"><span data-stu-id="73c36-110">Exchange Online (any configuration): 1,800</span></span>
- <span data-ttu-id="73c36-111">SharePoint eller OneDrive: (alla webbplatser inkluderas automatiskt): 13</span><span class="sxs-lookup"><span data-stu-id="73c36-111">SharePoint or OneDrive: (all sites automatically included): 13</span></span>
- <span data-ttu-id="73c36-112">SharePoint eller OneDrive (specifika platser inkluderas eller exkluderas): 2 600</span><span class="sxs-lookup"><span data-stu-id="73c36-112">SharePoint or OneDrive (specific locations included or excluded): 2,600</span></span>

## <a name="maximum-number-of-items-per-policy"></a><span data-ttu-id="73c36-113">Högsta antal objekt per princip</span><span class="sxs-lookup"><span data-stu-id="73c36-113">Maximum number of items per policy</span></span>

<span data-ttu-id="73c36-114">Om du använder den valfria konfigurationen för att begränsa dina kvarhållningsinställningar till specifika användare, specifika Microsoft 365-grupper eller specifika webbplatser, finns det några begränsningar per princip som du bör känna till:</span><span class="sxs-lookup"><span data-stu-id="73c36-114">If you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of:</span></span> 

<span data-ttu-id="73c36-115">Högsta antal objekt per kvarhållningsprincip:</span><span class="sxs-lookup"><span data-stu-id="73c36-115">Maximum numbers of items per policy for retention:</span></span>

  - <span data-ttu-id="73c36-116">1 000 postlådor (användarpostlådor eller gruppostlådor)</span><span class="sxs-lookup"><span data-stu-id="73c36-116">1,000 mailboxes (user mailboxes or group mailboxes)</span></span>
  - <span data-ttu-id="73c36-117">1 000 Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="73c36-117">1,000 Microsoft 365 groups</span></span>
  - <span data-ttu-id="73c36-118">1 000 användare i Teams privata chattar</span><span class="sxs-lookup"><span data-stu-id="73c36-118">1,000 users for Teams private chats</span></span>
  - <span data-ttu-id="73c36-119">100 webbplatser (OneDrive eller SharePoint).</span><span class="sxs-lookup"><span data-stu-id="73c36-119">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="73c36-120">Eftersom dessa begränsningar gäller per princip kan du skapa ytterligare principer som har samma kvarhållningsinställningar om du behöver använda specifika inkluderingar eller exkluderingar som leder till att du överskrider dessa antal.</span><span class="sxs-lookup"><span data-stu-id="73c36-120">Because these limitations are per policy, if you need to use specific inclusions or exclusions that result in going over these numbers, you can create additional policies that have the same retention settings.</span></span> <span data-ttu-id="73c36-121">I nästa avsnitt finns några [exempel på scenarion och lösningar](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) som använder flera kvarhållningsprinciper av den här anledningen.</span><span class="sxs-lookup"><span data-stu-id="73c36-121">See the next section for some [example scenarios and solutions](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) that use multiple retention policies for this reason.</span></span>

<span data-ttu-id="73c36-122">Men flera principer medför högre administrationskostnader, så bekräfta alltid om du verkligen behöver inkluderingar och exkluderingar.</span><span class="sxs-lookup"><span data-stu-id="73c36-122">However, multiple policies result in higher administrative overheads, so always confirm whether you really need inclusions and exclusions.</span></span> <span data-ttu-id="73c36-123">Kom ihåg att standardkonfigurationen som gäller för hela platsen inte har några begränsningar och att det här konfigurationsvalet kan vara en bättre lösning än att skapa och underhålla flera principer.</span><span class="sxs-lookup"><span data-stu-id="73c36-123">Remember that the default configuration that applies to the entire location doesn't have any limitations, and this configuration choice might be a better solution than creating and maintaining multiple policies.</span></span>

> [!TIP]
> <span data-ttu-id="73c36-124">Om du behöver skapa och underhålla flera principer för det här scenariot kan du överväga att använda [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) för att få en effektivare konfiguration.</span><span class="sxs-lookup"><span data-stu-id="73c36-124">If do you need to create and maintain multiple policies for this scenario, consider using [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) for more efficient configuration.</span></span>

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a><span data-ttu-id="73c36-125">Exempel på att använda flera principer för att undvika att överskrida maxantalen</span><span class="sxs-lookup"><span data-stu-id="73c36-125">Examples of using multiple policies to avoid exceeding maximum numbers</span></span>

<span data-ttu-id="73c36-126">Följande exempel innehåller några designlösningar för när du inte bara kan ange en kvarhållningsprincips plats och måste ta hänsyn till maxantalet objekt som angavs i det föregående avsnittet.</span><span class="sxs-lookup"><span data-stu-id="73c36-126">The following examples provide some design solutions for when you can't specify just the location for a retention policy, and must take into account the maximum number of items documented in the previous section.</span></span>

<span data-ttu-id="73c36-127">Exempel för Exchange:</span><span class="sxs-lookup"><span data-stu-id="73c36-127">Exchange example:</span></span>

- <span data-ttu-id="73c36-128">**Krav**: I en organisation med över 40 000 användarpostlådor måste de flesta användare kvarhålla sin e-post i 7 år, men en delmängd av de identifierade användarna (425) måste kvarhålla sin e-post i endast 5 år.</span><span class="sxs-lookup"><span data-stu-id="73c36-128">**Requirement**: In an organization that has over 40,000 user mailboxes, most users must have their email retained for 7 years but a subset of identified users (425) must have their email retained for only 5 years.</span></span>

- <span data-ttu-id="73c36-129">**Lösning**: Skapa en kvarhållningsprincip för e-post i Exchange med en kvarhållningsperiod på sju år och exkludera delmängden bland användarna.</span><span class="sxs-lookup"><span data-stu-id="73c36-129">**Solution**: Create one retention policy for Exchange email with a retention period of 7 years and exclude the subset of users.</span></span> <span data-ttu-id="73c36-130">Skapa sedan en andra kvarhållningsprincip för e-post i Exchange med en kvarhållningsperiod på fem år och inkludera delmängden bland användarna.</span><span class="sxs-lookup"><span data-stu-id="73c36-130">Then create a second retention policy for Exchange email with a retention period of 5 years and include the subset of users.</span></span> 
    
    <span data-ttu-id="73c36-131">I båda fallen är antalet som inkluderas och exkluderas under det maximala antalet angivna postlådor för en enskild princip och vissa användare måste uttryckligen undantas från den första principen eftersom den har en [längre kvarhållningsperiod](retention.md#the-principles-of-retention-or-what-takes-precedence) än den andra principen.</span><span class="sxs-lookup"><span data-stu-id="73c36-131">In both cases, the number included and excluded is below the maximum number of specified mailboxes for a single policy, and the subset of users must be explicitly excluded from the first policy because it has a [longer retention period](retention.md#the-principles-of-retention-or-what-takes-precedence) than the second policy.</span></span> <span data-ttu-id="73c36-132">Om det krävs en längre kvarhållningsprincip för delmängden användare behöver du inte utesluta dem från den första principen.</span><span class="sxs-lookup"><span data-stu-id="73c36-132">If the subset of users required a longer retention policy, you wouldn't need to exclude them from the first policy.</span></span>
     
    <span data-ttu-id="73c36-133">Om någon ny blir medlem i organisationen inkluderas postlådan automatiskt i den första principen på sju år och antalet som stöds påverkas inte alls med den här lösningen.</span><span class="sxs-lookup"><span data-stu-id="73c36-133">With this solution, if anybody new joins the organization, their mailbox is automatically included in the first policy for 7 years and there is no impact to the maximum numbers supported.</span></span> <span data-ttu-id="73c36-134">Nya användare som kräver kvarhållningsperioden på fem år ökar dock siffrorna för att inkludera och exkludera, och den här gränsen nås vid 1 000.</span><span class="sxs-lookup"><span data-stu-id="73c36-134">However, new users that require the 5-year retention period add to the include and exclude numbers, and this limit would be reached at 1,000.</span></span>

<span data-ttu-id="73c36-135">Exempel från SharePoint:</span><span class="sxs-lookup"><span data-stu-id="73c36-135">SharePoint example:</span></span>

- <span data-ttu-id="73c36-136">**Krav**: en organisation har flera tusen SharePoint-webbplatser men bara 2 000 webbplatser kräver en kvarhållningsperiod på 10 år och 8 000 webbplatser kräver en kvarhållningsperiod på 4 år.</span><span class="sxs-lookup"><span data-stu-id="73c36-136">**Requirement**: An organization has several thousand SharePoint sites but only 2,000 sites require a retention period of 10 years, and 8,000 sites require a retention period of 4 years.</span></span>

- <span data-ttu-id="73c36-137">**Lösning**: Skapa 20 kvarhållningsprinciper för SharePoint med en kvarhållningsperiod på 10 år som omfattar 100 specifika webbplatser och skapa 80 kvarhållningsprinciper för SharePoint med en kvarhållningsperiod på 4 år som omfattar 100 specifika webbplatser.</span><span class="sxs-lookup"><span data-stu-id="73c36-137">**Solution**: Create 20 retention policies for SharePoint with a retention period of 10 years that includes 100 specific sites, and create 80 retention policies for SharePoint with a retention period of 4 years that includes 100 specific sites.</span></span>
    
    <span data-ttu-id="73c36-138">Eftersom du inte behöver kvarhålla alla SharePoint-webbplatser måste du skapa kvarhållningsprinciper som specificerar de specifika webbplatserna.</span><span class="sxs-lookup"><span data-stu-id="73c36-138">Because you don't need to retain all SharePoint sites, you must create retention policies that specify the specific sites.</span></span> <span data-ttu-id="73c36-139">Eftersom en kvarhållningsprincip inte stöder fler än 100 angivna webbplatser måste du skapa flera principer för de två kvarhållningsperioderna.</span><span class="sxs-lookup"><span data-stu-id="73c36-139">Because a retention policy doesn't support more than 100 specified sites, you must create multiple policies for the two retention periods.</span></span> <span data-ttu-id="73c36-140">De här kvarhållningsprinciperna har ett maxantal webbplatser som ingår. Nästa nya webbplats som måste kvarhållas kräver en ny kvarhållningsprincip, oavsett hur lång kvarhållningsperioden är.</span><span class="sxs-lookup"><span data-stu-id="73c36-140">These retention policies  have the maximum number of included sites, so the next new site that needs retaining would require a new retention policy, irrespective of the retention period.</span></span>