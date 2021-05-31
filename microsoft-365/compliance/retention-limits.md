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
ms.openlocfilehash: 1ee2d07a42aaf4dff45ae22e9dfc005b3c4593d9
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698970"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a><span data-ttu-id="cb64f-103">Begränsningar när det gäller principer för kvarhållning och kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="cb64f-103">Limits for retention policies and retention label policies</span></span>

><span data-ttu-id="cb64f-104">*[Licensieringsvägledning för Microsoft 365 för säkerhet och efterlevnad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="cb64f-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="cb64f-105">När du använder [ principer för kvarhållning och kvarhållningsetiketter ](retention.md#retention-policies-and-retention-labels) för att automatiskt kvarhålla eller ta bort data åt organisationen så finns det några maxantal som du bör känna till.</span><span class="sxs-lookup"><span data-stu-id="cb64f-105">When you use [retention policies and retention label policies](retention.md#retention-policies-and-retention-labels) to automatically retain or delete data for your organization, there are some maximum numbers to be aware of.</span></span>

## <a name="maximum-number-of-policies-per-tenant"></a><span data-ttu-id="cb64f-106">Högsta antal principer per klientorganisation</span><span class="sxs-lookup"><span data-stu-id="cb64f-106">Maximum number of policies per tenant</span></span>

<span data-ttu-id="cb64f-107">En enskild klientorganisation kan ha högst 10 000 principer (alla konfigurationer).</span><span class="sxs-lookup"><span data-stu-id="cb64f-107">A single tenant can have a maximum of 10,000 policies (any configuration).</span></span> <span data-ttu-id="cb64f-108">Maxantalet inkluderar olika kvarhållningsprinciper och andra efterlevnadsprinciper, till exempel DLP-principer, informationsbarriärer, eDiscovery-undantag och känslighetsetiketter.</span><span class="sxs-lookup"><span data-stu-id="cb64f-108">This maximum number includes the different policies for retention, and other policies for compliance such as policies for DLP, information barriers, eDiscovery holds, and sensitivity labels.</span></span>

<span data-ttu-id="cb64f-109">Inom denna gräns på 10.000 principer finns det också några begränsningar för det högsta antalet kvarhållningsprinciper per arbetsbelastning:</span><span class="sxs-lookup"><span data-stu-id="cb64f-109">Within this 10,000 policies limit, there are also some limits on the maximum number of policies for retention per workload:</span></span>

- <span data-ttu-id="cb64f-110">Exchange Online (alla konfigurationer): 1 800</span><span class="sxs-lookup"><span data-stu-id="cb64f-110">Exchange Online (any configuration): 1,800</span></span>
- <span data-ttu-id="cb64f-111">SharePoint eller OneDrive: (alla webbplatser inkluderas automatiskt): 13</span><span class="sxs-lookup"><span data-stu-id="cb64f-111">SharePoint or OneDrive: (all sites automatically included): 13</span></span>
- <span data-ttu-id="cb64f-112">SharePoint eller OneDrive (specifika platser inkluderas eller exkluderas): 2 600</span><span class="sxs-lookup"><span data-stu-id="cb64f-112">SharePoint or OneDrive (specific locations included or excluded): 2,600</span></span>

<span data-ttu-id="cb64f-113">Även om kvarhållningprinciper för Teams och Yammer använder e-postlådor för att lagra data för kvarhållningssyften, exkluderar de högsta antalet principer för Exchange Online lagringsprinciper för Teams och Yammer.</span><span class="sxs-lookup"><span data-stu-id="cb64f-113">Although retention policies for Microsoft Teams and Yammer use mailboxes to store data for retention purposes, the maximum number of policies for Exchange Online exclude retention policies for Teams and Yammer.</span></span>

## <a name="maximum-number-of-items-per-policy"></a><span data-ttu-id="cb64f-114">Högsta antal objekt per princip</span><span class="sxs-lookup"><span data-stu-id="cb64f-114">Maximum number of items per policy</span></span>

<span data-ttu-id="cb64f-115">Om du använder den valfria konfigurationen för att begränsa dina kvarhållningsinställningar till specifika användare, specifika Microsoft 365-grupper eller specifika webbplatser, finns det några begränsningar per princip som du bör känna till:</span><span class="sxs-lookup"><span data-stu-id="cb64f-115">If you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of:</span></span> 

<span data-ttu-id="cb64f-116">Högsta antal objekt per kvarhållningsprincip:</span><span class="sxs-lookup"><span data-stu-id="cb64f-116">Maximum numbers of items per policy for retention:</span></span>

  - <span data-ttu-id="cb64f-117">1 000 postlådor (användarpostlådor eller gruppostlådor)</span><span class="sxs-lookup"><span data-stu-id="cb64f-117">1,000 mailboxes (user mailboxes or group mailboxes)</span></span>
  - <span data-ttu-id="cb64f-118">1 000 Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="cb64f-118">1,000 Microsoft 365 groups</span></span>
  - <span data-ttu-id="cb64f-119">1 000 användare i Teams privata chattar</span><span class="sxs-lookup"><span data-stu-id="cb64f-119">1,000 users for Teams private chats</span></span>
  - <span data-ttu-id="cb64f-120">100 webbplatser (OneDrive eller SharePoint).</span><span class="sxs-lookup"><span data-stu-id="cb64f-120">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="cb64f-121">Eftersom dessa begränsningar gäller per princip kan du skapa ytterligare principer som har samma kvarhållningsinställningar om du behöver använda specifika inkluderingar eller exkluderingar som leder till att du överskrider dessa antal.</span><span class="sxs-lookup"><span data-stu-id="cb64f-121">Because these limitations are per policy, if you need to use specific inclusions or exclusions that result in going over these numbers, you can create additional policies that have the same retention settings.</span></span> <span data-ttu-id="cb64f-122">I nästa avsnitt finns några [exempel på scenarion och lösningar](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) som använder flera kvarhållningsprinciper av den här anledningen.</span><span class="sxs-lookup"><span data-stu-id="cb64f-122">See the next section for some [example scenarios and solutions](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) that use multiple retention policies for this reason.</span></span>

<span data-ttu-id="cb64f-123">Men flera principer medför högre administrationskostnader, så bekräfta alltid om du verkligen behöver inkluderingar och exkluderingar.</span><span class="sxs-lookup"><span data-stu-id="cb64f-123">However, multiple policies result in higher administrative overheads, so always confirm whether you really need inclusions and exclusions.</span></span> <span data-ttu-id="cb64f-124">Kom ihåg att standardkonfigurationen som gäller för hela platsen inte har några begränsningar och att det här konfigurationsvalet kan vara en bättre lösning än att skapa och underhålla flera principer.</span><span class="sxs-lookup"><span data-stu-id="cb64f-124">Remember that the default configuration that applies to the entire location doesn't have any limitations, and this configuration choice might be a better solution than creating and maintaining multiple policies.</span></span>

> [!TIP]
> <span data-ttu-id="cb64f-125">Om du behöver skapa och underhålla flera principer för det här scenariot kan du överväga att använda [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) för att få en effektivare konfiguration.</span><span class="sxs-lookup"><span data-stu-id="cb64f-125">If do you need to create and maintain multiple policies for this scenario, consider using [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) for more efficient configuration.</span></span>

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a><span data-ttu-id="cb64f-126">Exempel på att använda flera principer för att undvika att överskrida maxantalen</span><span class="sxs-lookup"><span data-stu-id="cb64f-126">Examples of using multiple policies to avoid exceeding maximum numbers</span></span>

<span data-ttu-id="cb64f-127">Följande exempel innehåller några designlösningar för när du inte bara kan ange en kvarhållningsprincips plats och måste ta hänsyn till maxantalet objekt som angavs i det föregående avsnittet.</span><span class="sxs-lookup"><span data-stu-id="cb64f-127">The following examples provide some design solutions for when you can't specify just the location for a retention policy, and must take into account the maximum number of items documented in the previous section.</span></span>

<span data-ttu-id="cb64f-128">Exempel för Exchange:</span><span class="sxs-lookup"><span data-stu-id="cb64f-128">Exchange example:</span></span>

- <span data-ttu-id="cb64f-129">**Krav**: I en organisation med över 40 000 användarpostlådor måste de flesta användare kvarhålla sin e-post i 7 år, men en delmängd av de identifierade användarna (425) måste kvarhålla sin e-post i endast 5 år.</span><span class="sxs-lookup"><span data-stu-id="cb64f-129">**Requirement**: In an organization that has over 40,000 user mailboxes, most users must have their email retained for 7 years but a subset of identified users (425) must have their email retained for only 5 years.</span></span>

- <span data-ttu-id="cb64f-130">**Lösning**: Skapa en kvarhållningsprincip för e-post i Exchange med en kvarhållningsperiod på sju år och exkludera delmängden bland användarna.</span><span class="sxs-lookup"><span data-stu-id="cb64f-130">**Solution**: Create one retention policy for Exchange email with a retention period of 7 years and exclude the subset of users.</span></span> <span data-ttu-id="cb64f-131">Skapa sedan en andra kvarhållningsprincip för e-post i Exchange med en kvarhållningsperiod på fem år och inkludera delmängden bland användarna.</span><span class="sxs-lookup"><span data-stu-id="cb64f-131">Then create a second retention policy for Exchange email with a retention period of 5 years and include the subset of users.</span></span> 
    
    <span data-ttu-id="cb64f-132">I båda fallen är antalet som inkluderas och exkluderas under det maximala antalet angivna postlådor för en enskild princip och vissa användare måste uttryckligen undantas från den första principen eftersom den har en [längre kvarhållningsperiod](retention.md#the-principles-of-retention-or-what-takes-precedence) än den andra principen.</span><span class="sxs-lookup"><span data-stu-id="cb64f-132">In both cases, the number included and excluded is below the maximum number of specified mailboxes for a single policy, and the subset of users must be explicitly excluded from the first policy because it has a [longer retention period](retention.md#the-principles-of-retention-or-what-takes-precedence) than the second policy.</span></span> <span data-ttu-id="cb64f-133">Om det krävs en längre kvarhållningsprincip för delmängden användare behöver du inte utesluta dem från den första principen.</span><span class="sxs-lookup"><span data-stu-id="cb64f-133">If the subset of users required a longer retention policy, you wouldn't need to exclude them from the first policy.</span></span>
     
    <span data-ttu-id="cb64f-134">Om någon ny blir medlem i organisationen inkluderas postlådan automatiskt i den första principen på sju år och antalet som stöds påverkas inte alls med den här lösningen.</span><span class="sxs-lookup"><span data-stu-id="cb64f-134">With this solution, if anybody new joins the organization, their mailbox is automatically included in the first policy for 7 years and there is no impact to the maximum numbers supported.</span></span> <span data-ttu-id="cb64f-135">Nya användare som kräver kvarhållningsperioden på fem år ökar dock siffrorna för att inkludera och exkludera, och den här gränsen nås vid 1 000.</span><span class="sxs-lookup"><span data-stu-id="cb64f-135">However, new users that require the 5-year retention period add to the include and exclude numbers, and this limit would be reached at 1,000.</span></span>

<span data-ttu-id="cb64f-136">Exempel från SharePoint:</span><span class="sxs-lookup"><span data-stu-id="cb64f-136">SharePoint example:</span></span>

- <span data-ttu-id="cb64f-137">**Krav**: en organisation har flera tusen SharePoint-webbplatser men bara 2 000 webbplatser kräver en kvarhållningsperiod på 10 år och 8 000 webbplatser kräver en kvarhållningsperiod på 4 år.</span><span class="sxs-lookup"><span data-stu-id="cb64f-137">**Requirement**: An organization has several thousand SharePoint sites but only 2,000 sites require a retention period of 10 years, and 8,000 sites require a retention period of 4 years.</span></span>

- <span data-ttu-id="cb64f-138">**Lösning**: Skapa 20 kvarhållningsprinciper för SharePoint med en kvarhållningsperiod på 10 år som omfattar 100 specifika webbplatser och skapa 80 kvarhållningsprinciper för SharePoint med en kvarhållningsperiod på 4 år som omfattar 100 specifika webbplatser.</span><span class="sxs-lookup"><span data-stu-id="cb64f-138">**Solution**: Create 20 retention policies for SharePoint with a retention period of 10 years that includes 100 specific sites, and create 80 retention policies for SharePoint with a retention period of 4 years that includes 100 specific sites.</span></span>
    
    <span data-ttu-id="cb64f-139">Eftersom du inte behöver kvarhålla alla SharePoint-webbplatser måste du skapa kvarhållningsprinciper som specificerar de specifika webbplatserna.</span><span class="sxs-lookup"><span data-stu-id="cb64f-139">Because you don't need to retain all SharePoint sites, you must create retention policies that specify the specific sites.</span></span> <span data-ttu-id="cb64f-140">Eftersom en kvarhållningsprincip inte stöder fler än 100 angivna webbplatser måste du skapa flera principer för de två kvarhållningsperioderna.</span><span class="sxs-lookup"><span data-stu-id="cb64f-140">Because a retention policy doesn't support more than 100 specified sites, you must create multiple policies for the two retention periods.</span></span> <span data-ttu-id="cb64f-141">De här kvarhållningsprinciperna har ett maxantal webbplatser som ingår. Nästa nya webbplats som måste kvarhållas kräver en ny kvarhållningsprincip, oavsett hur lång kvarhållningsperioden är.</span><span class="sxs-lookup"><span data-stu-id="cb64f-141">These retention policies  have the maximum number of included sites, so the next new site that needs retaining would require a new retention policy, irrespective of the retention period.</span></span>