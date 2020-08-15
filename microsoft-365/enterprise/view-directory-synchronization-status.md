---
title: Visa synkroniseringsstatus för katalog i Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: I den här artikeln lär du dig hur du kan kontrol lera status för din katalog-synkronisering i Office 365.
ms.openlocfilehash: c77898b58b58c6ae91492debd7ad66f395d80d52
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694660"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="52a7b-103">Visa synkroniseringsstatus för katalog i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="52a7b-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="52a7b-104">Om du har integrerat din lokala Active Directory med Azure AD genom att synkronisera den lokala miljön med Microsoft 365 kan du också kontrol lera statusen för din synkronisering.</span><span class="sxs-lookup"><span data-stu-id="52a7b-104">If you have integrated your on-premises Active Directory with Azure AD by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="52a7b-105">Visa synkroniseringsstatus för katalog</span><span class="sxs-lookup"><span data-stu-id="52a7b-105">View directory synchronization status</span></span>

- <span data-ttu-id="52a7b-106">Logga in på [administrations centret för Microsoft 365](https://admin.microsoft.com) och välj **DirSync-status** på Start sidan.</span><span class="sxs-lookup"><span data-stu-id="52a7b-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="52a7b-107">Du kan också gå till **användare** \> **aktiva användare**och på sidan **aktiva användare** väljer du **mer** \> **katalog synkronisering**.</span><span class="sxs-lookup"><span data-stu-id="52a7b-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="52a7b-108">I fönstret **Directory-synkronisering** väljer du **gå till DirSync-hanteringen**.</span><span class="sxs-lookup"><span data-stu-id="52a7b-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="52a7b-109">Information om sidan Hantera katalog synkronisering</span><span class="sxs-lookup"><span data-stu-id="52a7b-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="52a7b-110">I följande tabell visas de funktioner du kan hämta information om på sidan.</span><span class="sxs-lookup"><span data-stu-id="52a7b-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="52a7b-111">Om det uppstår problem med din katalog-synkronisering visas felen på den här sidan också.</span><span class="sxs-lookup"><span data-stu-id="52a7b-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="52a7b-112">Mer information om olika fel som kan uppstå finns i avsnittet [identifiera synkroniseringsfel i Microsoft 365](identify-directory-synchronization-errors.md).</span><span class="sxs-lookup"><span data-stu-id="52a7b-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="52a7b-113">**Objekt**</span><span class="sxs-lookup"><span data-stu-id="52a7b-113">**Item**</span></span>|<span data-ttu-id="52a7b-114">**Vad det används till**</span><span class="sxs-lookup"><span data-stu-id="52a7b-114">**What it's for**</span></span>|
|:-----|:-----|
|<span data-ttu-id="52a7b-115">**Domäner verifierade**</span><span class="sxs-lookup"><span data-stu-id="52a7b-115">**Domains verified**</span></span> | <span data-ttu-id="52a7b-116">Antal domäner i din Microsoft 365-klient som du har verifierat.</span><span class="sxs-lookup"><span data-stu-id="52a7b-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="52a7b-117">**Domäner är inte verifierade**</span><span class="sxs-lookup"><span data-stu-id="52a7b-117">**Domains not verified**</span></span> | <span data-ttu-id="52a7b-118">Domäner som du har lagt till men inte verifierats.</span><span class="sxs-lookup"><span data-stu-id="52a7b-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="52a7b-119">**Katalog synkronisering aktive rad**</span><span class="sxs-lookup"><span data-stu-id="52a7b-119">**Directory sync enabled**</span></span> |<span data-ttu-id="52a7b-120">Sant eller falskt.</span><span class="sxs-lookup"><span data-stu-id="52a7b-120">True or False.</span></span> <span data-ttu-id="52a7b-121">Anger om du har aktiverat katalog synkronisering.</span><span class="sxs-lookup"><span data-stu-id="52a7b-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="52a7b-122">**Senaste katalog synkronisering**</span><span class="sxs-lookup"><span data-stu-id="52a7b-122">**Latest directory sync**</span></span> | <span data-ttu-id="52a7b-123">Förra gången katalog synkronisering kördes.</span><span class="sxs-lookup"><span data-stu-id="52a7b-123">Last time directory sync ran.</span></span> <span data-ttu-id="52a7b-124">Visar en varning och en länk till ett fel söknings verktyg om den senaste synkroniseringen var för mer än tre dagar sedan.</span><span class="sxs-lookup"><span data-stu-id="52a7b-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="52a7b-125">**Lösenordssynkronisering aktive rad**</span><span class="sxs-lookup"><span data-stu-id="52a7b-125">**Password sync enabled**</span></span> | <span data-ttu-id="52a7b-126">Sant eller falskt.</span><span class="sxs-lookup"><span data-stu-id="52a7b-126">True or False.</span></span> <span data-ttu-id="52a7b-127">Anger om du har ett lösen ord-hash-synkronisering mellan vår lokala och din Microsoft 365-klient.</span><span class="sxs-lookup"><span data-stu-id="52a7b-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="52a7b-128">**Senaste lösen ords synkronisering**</span><span class="sxs-lookup"><span data-stu-id="52a7b-128">**Last Password Sync**</span></span> | <span data-ttu-id="52a7b-129">Senaste gången lösen ordet för hash-synkronisering kördes.</span><span class="sxs-lookup"><span data-stu-id="52a7b-129">Last time password hash sync ran.</span></span> <span data-ttu-id="52a7b-130">Visar en varning och en länk till ett fel söknings verktyg om den senaste synkroniseringen var för mer än tre dagar sedan.</span><span class="sxs-lookup"><span data-stu-id="52a7b-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="52a7b-131">**Katalog-synkroniseringsklient**</span><span class="sxs-lookup"><span data-stu-id="52a7b-131">**Directory sync client version**</span></span> | <span data-ttu-id="52a7b-132">Innehåller en nedladdnings länk om en ny version av Azure AD Connect har frisläppts.</span><span class="sxs-lookup"><span data-stu-id="52a7b-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="52a7b-133">**Katalog-Sync-tjänstkonto**</span><span class="sxs-lookup"><span data-stu-id="52a7b-133">**Directory sync service account**</span></span> | <span data-ttu-id="52a7b-134">Visar namnet på ditt Microsoft 365 Directory Sync Service-konto.</span><span class="sxs-lookup"><span data-stu-id="52a7b-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |