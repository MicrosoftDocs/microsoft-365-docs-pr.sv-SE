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
ms.openlocfilehash: 7577ed358a262d5b0ef2932bc73cf61941bec31b
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326955"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="3f58e-103">Visa synkroniseringsstatus för katalog i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3f58e-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="3f58e-104">Om du har integrerat din lokala Active Directory Domain Services (AD DS) med Azure Active Directory (Azure AD) genom att synkronisera den lokala miljön med Microsoft 365 kan du också kontrol lera statusen för din synkronisering.</span><span class="sxs-lookup"><span data-stu-id="3f58e-104">If you have integrated your on-premises Active Directory Domain Services (AD DS) with Azure Active Directory (Azure AD) by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="3f58e-105">Visa katalogsynkroniseringsstatus</span><span class="sxs-lookup"><span data-stu-id="3f58e-105">View directory synchronization status</span></span>

- <span data-ttu-id="3f58e-106">Logga in på [administrations centret för Microsoft 365](https://admin.microsoft.com) och välj **DirSync-status** på Start sidan.</span><span class="sxs-lookup"><span data-stu-id="3f58e-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="3f58e-107">Du kan också gå till **användare** \> **aktiva användare**och på sidan **aktiva användare** väljer du **mer** \> **katalog synkronisering**.</span><span class="sxs-lookup"><span data-stu-id="3f58e-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="3f58e-108">I fönstret **Directory-synkronisering** väljer du **gå till DirSync-hanteringen**.</span><span class="sxs-lookup"><span data-stu-id="3f58e-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="3f58e-109">Information om sidan Hantera katalog synkronisering</span><span class="sxs-lookup"><span data-stu-id="3f58e-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="3f58e-110">I följande tabell visas de funktioner du kan hämta information om på sidan.</span><span class="sxs-lookup"><span data-stu-id="3f58e-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="3f58e-111">Om det uppstår problem med din katalog-synkronisering visas felen på den här sidan också.</span><span class="sxs-lookup"><span data-stu-id="3f58e-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="3f58e-112">Mer information om olika fel som kan uppstå finns i avsnittet [identifiera synkroniseringsfel i Microsoft 365](identify-directory-synchronization-errors.md).</span><span class="sxs-lookup"><span data-stu-id="3f58e-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="3f58e-113">Objekt</span><span class="sxs-lookup"><span data-stu-id="3f58e-113">Item</span></span>|<span data-ttu-id="3f58e-114">Vad det används till</span><span class="sxs-lookup"><span data-stu-id="3f58e-114">What it's for</span></span>|
|:-----|:-----|
|<span data-ttu-id="3f58e-115">**Domäner verifierade**</span><span class="sxs-lookup"><span data-stu-id="3f58e-115">**Domains verified**</span></span> | <span data-ttu-id="3f58e-116">Antal domäner i din Microsoft 365-klient som du har verifierat.</span><span class="sxs-lookup"><span data-stu-id="3f58e-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="3f58e-117">**Domäner är inte verifierade**</span><span class="sxs-lookup"><span data-stu-id="3f58e-117">**Domains not verified**</span></span> | <span data-ttu-id="3f58e-118">Domäner som du har lagt till men inte verifierats.</span><span class="sxs-lookup"><span data-stu-id="3f58e-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="3f58e-119">**Katalog synkronisering aktive rad**</span><span class="sxs-lookup"><span data-stu-id="3f58e-119">**Directory sync enabled**</span></span> |<span data-ttu-id="3f58e-120">Sant eller falskt.</span><span class="sxs-lookup"><span data-stu-id="3f58e-120">True or False.</span></span> <span data-ttu-id="3f58e-121">Anger om du har aktiverat katalog synkronisering.</span><span class="sxs-lookup"><span data-stu-id="3f58e-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="3f58e-122">**Senaste katalog synkronisering**</span><span class="sxs-lookup"><span data-stu-id="3f58e-122">**Latest directory sync**</span></span> | <span data-ttu-id="3f58e-123">Förra gången katalog synkronisering kördes.</span><span class="sxs-lookup"><span data-stu-id="3f58e-123">Last time directory sync ran.</span></span> <span data-ttu-id="3f58e-124">Visar en varning och en länk till ett fel söknings verktyg om den senaste synkroniseringen var för mer än tre dagar sedan.</span><span class="sxs-lookup"><span data-stu-id="3f58e-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="3f58e-125">**Lösenordssynkronisering aktive rad**</span><span class="sxs-lookup"><span data-stu-id="3f58e-125">**Password sync enabled**</span></span> | <span data-ttu-id="3f58e-126">Sant eller falskt.</span><span class="sxs-lookup"><span data-stu-id="3f58e-126">True or False.</span></span> <span data-ttu-id="3f58e-127">Anger om du har ett lösen ord-hash-synkronisering mellan vår lokala och din Microsoft 365-klient.</span><span class="sxs-lookup"><span data-stu-id="3f58e-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="3f58e-128">**Senaste lösen ords synkronisering**</span><span class="sxs-lookup"><span data-stu-id="3f58e-128">**Last Password Sync**</span></span> | <span data-ttu-id="3f58e-129">Senaste gången lösen ordet för hash-synkronisering kördes.</span><span class="sxs-lookup"><span data-stu-id="3f58e-129">Last time password hash sync ran.</span></span> <span data-ttu-id="3f58e-130">Visar en varning och en länk till ett fel söknings verktyg om den senaste synkroniseringen var för mer än tre dagar sedan.</span><span class="sxs-lookup"><span data-stu-id="3f58e-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="3f58e-131">**Katalog-synkroniseringsklient**</span><span class="sxs-lookup"><span data-stu-id="3f58e-131">**Directory sync client version**</span></span> | <span data-ttu-id="3f58e-132">Innehåller en nedladdnings länk om en ny version av Azure AD Connect har frisläppts.</span><span class="sxs-lookup"><span data-stu-id="3f58e-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="3f58e-133">**Katalog-Sync-tjänstkonto**</span><span class="sxs-lookup"><span data-stu-id="3f58e-133">**Directory sync service account**</span></span> | <span data-ttu-id="3f58e-134">Visar namnet på ditt Microsoft 365 Directory Sync Service-konto.</span><span class="sxs-lookup"><span data-stu-id="3f58e-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |
|||

## <a name="monitor-synchronization-health"></a><span data-ttu-id="3f58e-135">Övervaka synkroniseringshälsa</span><span class="sxs-lookup"><span data-stu-id="3f58e-135">Monitor synchronization health</span></span>

<span data-ttu-id="3f58e-136">I det här avsnittet installerar du en Azure AD Connect Health-agent på var och en av dina lokala AD DS-domänkontrollanter för att övervaka din identitetsinfrastruktur och de synkroniseringstjänster som tillhandahålls av Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="3f58e-136">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="3f58e-137">Övervakningsinformationen visas i en Azure AD Connect Health-portal, där du kan se varningar, prestandaövervakning, användningsanalys och annan information.</span><span class="sxs-lookup"><span data-stu-id="3f58e-137">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

<span data-ttu-id="3f58e-138">Det viktiga beslutet för hur du ska använda Azure AD Connect Health, baseras på hur du använder Azure AD Connect:</span><span class="sxs-lookup"><span data-stu-id="3f58e-138">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="3f58e-139">Om du använder **hanterad autentisering** börjar du med [Använda Azure AD Connect Health med synkronisering](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) för att förstå och konfigurera Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="3f58e-139">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="3f58e-140">Om du bara synkroniserar namnen på de konton och grupper som använder **federerad autentisering** med Active Directory Federation Services (AD FS), börjar du med [Använda Azure AD Connect Health med AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) för att förstå och konfigurera Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="3f58e-140">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="3f58e-141">När du är klar har du:</span><span class="sxs-lookup"><span data-stu-id="3f58e-141">When complete, you’ll have:</span></span>

- <span data-ttu-id="3f58e-142">Azure AD Connect Health-agenten installerad på dina lokala identitetsproviderservrar.</span><span class="sxs-lookup"><span data-stu-id="3f58e-142">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="3f58e-143">Azure AD Connect Health-portalen visar aktuell status för lokal infrastruktur och synkronisering med Azure AD-klientorganisationen för din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="3f58e-143">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>

