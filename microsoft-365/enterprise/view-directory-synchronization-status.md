---
title: Visa katalogsynkroniseringsstatus i Microsoft 365
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
description: I den här artikeln lär du dig hur du kontrollerar status för katalogsynkroniseringen i Office 365.
ms.openlocfilehash: cbaae8bbd31f6124c2b0f4984b9a625ffbde538f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924666"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="1bbc4-103">Visa katalogsynkroniseringsstatus i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1bbc4-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="1bbc4-104">Om du har integrerat din lokala Active Directory Domain Services (AD DS) med Azure Active Directory (Azure AD) genom att synkronisera din lokala miljö med Microsoft 365 kan du även kontrollera status för synkroniseringen.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-104">If you have integrated your on-premises Active Directory Domain Services (AD DS) with Azure Active Directory (Azure AD) by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="1bbc4-105">Visa katalogsynkroniseringsstatus</span><span class="sxs-lookup"><span data-stu-id="1bbc4-105">View directory synchronization status</span></span>

- <span data-ttu-id="1bbc4-106">Logga in på [administrationscentret för Microsoft 365](https://admin.microsoft.com) och välj **DirSync-status** på startsidan.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="1bbc4-107">Alternativt kan du gå till Användare **aktiva användare** och på \> sidan Aktiva **användare** väljer du Mer **katalogsynkronisering.** \> </span><span class="sxs-lookup"><span data-stu-id="1bbc4-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="1bbc4-108">I fönstret **Katalogsynkronisering** väljer du **Gå till DirSync-hantering**.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="1bbc4-109">Information på sidan Hantera katalogsynkronisering</span><span class="sxs-lookup"><span data-stu-id="1bbc4-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="1bbc4-110">I följande tabell visas de funktioner du kan få information om på sidan.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="1bbc4-111">Om det är problem med katalogsynkroniseringen visas även felen på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="1bbc4-112">Mer information om olika fel som kan uppstå finns i [Identifiera katalogsynkroniseringsfel i Microsoft 365.](identify-directory-synchronization-errors.md)</span><span class="sxs-lookup"><span data-stu-id="1bbc4-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="1bbc4-113">Objekt</span><span class="sxs-lookup"><span data-stu-id="1bbc4-113">Item</span></span>|<span data-ttu-id="1bbc4-114">Vad det används till</span><span class="sxs-lookup"><span data-stu-id="1bbc4-114">What it's for</span></span>|
|:-----|:-----|
|<span data-ttu-id="1bbc4-115">**Verifierade domäner**</span><span class="sxs-lookup"><span data-stu-id="1bbc4-115">**Domains verified**</span></span> | <span data-ttu-id="1bbc4-116">Antal domäner i din Microsoft 365-klientorganisation som du har verifierat att du äger.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="1bbc4-117">**Domäner som inte har verifierats**</span><span class="sxs-lookup"><span data-stu-id="1bbc4-117">**Domains not verified**</span></span> | <span data-ttu-id="1bbc4-118">Domäner som du har lagt till, men inte verifierat.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="1bbc4-119">**Katalogsynkronisering aktiverad**</span><span class="sxs-lookup"><span data-stu-id="1bbc4-119">**Directory sync enabled**</span></span> |<span data-ttu-id="1bbc4-120">Sant eller falskt.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-120">True or False.</span></span> <span data-ttu-id="1bbc4-121">Anger om du har aktiverat katalogsynkronisering.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="1bbc4-122">**Senaste katalogsynkronisering**</span><span class="sxs-lookup"><span data-stu-id="1bbc4-122">**Latest directory sync**</span></span> | <span data-ttu-id="1bbc4-123">Senaste gången katalogsynkronisering kördes.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-123">Last time directory sync ran.</span></span> <span data-ttu-id="1bbc4-124">Visar en varning och en länk till ett felsökningsverktyg, om den senaste synkroniseringen gjordes för mer än tre dagar sedan.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="1bbc4-125">**Lösenordssynkronisering aktiverad**</span><span class="sxs-lookup"><span data-stu-id="1bbc4-125">**Password sync enabled**</span></span> | <span data-ttu-id="1bbc4-126">Sant eller falskt.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-126">True or False.</span></span> <span data-ttu-id="1bbc4-127">Anger om du har synkronisering av lösenordshashar mellan vår lokala och din Microsoft 365-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="1bbc4-128">**Senaste lösenordssynkronisering**</span><span class="sxs-lookup"><span data-stu-id="1bbc4-128">**Last Password Sync**</span></span> | <span data-ttu-id="1bbc4-129">Senaste gången hash-synkronisering av lösenord kördes.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-129">Last time password hash sync ran.</span></span> <span data-ttu-id="1bbc4-130">Visar en varning och en länk till ett felsökningsverktyg, om den senaste synkroniseringen gjordes för mer än tre dagar sedan.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="1bbc4-131">**Version av katalogsynkroniseringsklient**</span><span class="sxs-lookup"><span data-stu-id="1bbc4-131">**Directory sync client version**</span></span> | <span data-ttu-id="1bbc4-132">Innehåller en nedladdningslänk om en ny version av Azure AD Connect har släppts.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="1bbc4-133">**Katalogsynkroniseringstjänstkonto**</span><span class="sxs-lookup"><span data-stu-id="1bbc4-133">**Directory sync service account**</span></span> | <span data-ttu-id="1bbc4-134">Visar namnet på ditt Microsoft 365-katalogsynkroniseringstjänstkonto.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |
|||

## <a name="monitor-synchronization-health"></a><span data-ttu-id="1bbc4-135">Övervaka synkroniseringshälsa</span><span class="sxs-lookup"><span data-stu-id="1bbc4-135">Monitor synchronization health</span></span>

<span data-ttu-id="1bbc4-136">I det här avsnittet installerar du en Azure AD Connect Health-agent på var och en av dina lokala AD DS-domänkontrollanter för att övervaka din identitetsinfrastruktur och de synkroniseringstjänster som tillhandahålls av Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-136">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="1bbc4-137">Övervakningsinformationen visas i en Azure AD Connect Health-portal, där du kan se varningar, prestandaövervakning, användningsanalys och annan information.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-137">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

<span data-ttu-id="1bbc4-138">Det viktiga beslutet för hur du ska använda Azure AD Connect Health, baseras på hur du använder Azure AD Connect:</span><span class="sxs-lookup"><span data-stu-id="1bbc4-138">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="1bbc4-139">Om du använder **hanterad autentisering** börjar du med [Använda Azure AD Connect Health med synkronisering](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) för att förstå och konfigurera Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-139">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="1bbc4-140">Om du bara synkroniserar namnen på de konton och grupper som använder **federerad autentisering** med Active Directory Federation Services (AD FS), börjar du med [Använda Azure AD Connect Health med AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) för att förstå och konfigurera Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-140">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="1bbc4-141">När det är klart har du:</span><span class="sxs-lookup"><span data-stu-id="1bbc4-141">When complete, you’ll have:</span></span>

- <span data-ttu-id="1bbc4-142">Azure AD Connect Health-agenten installerad på dina lokala identitetsproviderservrar.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-142">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="1bbc4-143">Azure AD Connect Health-portalen visar aktuell status för lokal infrastruktur och synkronisering med Azure AD-klientorganisationen för din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="1bbc4-143">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>