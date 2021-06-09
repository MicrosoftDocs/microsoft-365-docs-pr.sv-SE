---
title: DNS-poster för Office 365 DoD
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Sammanfattning: DNS-poster för Office 365 DoD'
hideEdit: true
ms.openlocfilehash: 656fb5aff3365dfb5f975f7d3ad1c222b36e1e56
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694533"
---
# <a name="dns-records-for-office-365-dod"></a><span data-ttu-id="17777-103">DNS-poster för Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="17777-103">DNS records for Office 365 DoD</span></span>

<span data-ttu-id="17777-104">*Den här artikeln gäller för Office 365 dod och Microsoft 365 dod*</span><span class="sxs-lookup"><span data-stu-id="17777-104">*This article applies to Office 365 DoD and Microsoft 365 DoD*</span></span>

<span data-ttu-id="17777-105">Som en del av onboarding till Office 365 DoD måste du lägga till dina SMTP- och SIP-domäner till Online Services-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="17777-105">As part of onboarding to Office 365 DoD, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="17777-106">Du gör detta med hjälp av New-MsolDomain-cmdleten i Azure AD PowerShell eller använda [Azure Government-portalen](https://portal.azure.us) för att starta processen med att lägga till domänen och bevisa ägarskap.</span><span class="sxs-lookup"><span data-stu-id="17777-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="17777-107">När du har lagt till domänerna i klientorganisationen och validerat dem kan du använda följande anvisningar för att lägga till lämpliga DNS-poster för tjänsterna nedan.</span><span class="sxs-lookup"><span data-stu-id="17777-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="17777-108">Du kan behöva ändra tabellen nedan för att passa organisationens behov med avseende på den inkommande MX-posten eller -posterna och eventuella Exchange Autodiscover-poster du har.</span><span class="sxs-lookup"><span data-stu-id="17777-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="17777-109">Vi rekommenderar att du koordinerar de här DNS-posterna med meddelandeteamet för att undvika avbrott eller felaktig e-postleverans.</span><span class="sxs-lookup"><span data-stu-id="17777-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="17777-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="17777-110">Exchange Online</span></span>

| <span data-ttu-id="17777-111">Typ</span><span class="sxs-lookup"><span data-stu-id="17777-111">Type</span></span> | <span data-ttu-id="17777-112">Prioritet</span><span class="sxs-lookup"><span data-stu-id="17777-112">Priority</span></span> | <span data-ttu-id="17777-113">Värdnamn</span><span class="sxs-lookup"><span data-stu-id="17777-113">Host name</span></span> | <span data-ttu-id="17777-114">Pekar på adress eller värde</span><span class="sxs-lookup"><span data-stu-id="17777-114">Points to address or value</span></span> | <span data-ttu-id="17777-115">TTL</span><span class="sxs-lookup"><span data-stu-id="17777-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="17777-116">MX</span><span class="sxs-lookup"><span data-stu-id="17777-116">MX</span></span> | <span data-ttu-id="17777-117">0</span><span class="sxs-lookup"><span data-stu-id="17777-117">0</span></span> | @ | <span data-ttu-id="17777-118">*klientorganisations*-mail.protection.office365.us (se nedan för ytterligare information)</span><span class="sxs-lookup"><span data-stu-id="17777-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="17777-119">1 timme</span><span class="sxs-lookup"><span data-stu-id="17777-119">1 Hour</span></span> |
| <span data-ttu-id="17777-120">TXT</span><span class="sxs-lookup"><span data-stu-id="17777-120">TXT</span></span> | - | @ | <span data-ttu-id="17777-121">v=spf1 include:spf.protection.office365.us -all</span><span class="sxs-lookup"><span data-stu-id="17777-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="17777-122">1 timme</span><span class="sxs-lookup"><span data-stu-id="17777-122">1 Hour</span></span> |
| <span data-ttu-id="17777-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="17777-123">CNAME</span></span> | - | <span data-ttu-id="17777-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="17777-124">autodiscover</span></span> | <span data-ttu-id="17777-125">autodiscover-dod.office365.us</span><span class="sxs-lookup"><span data-stu-id="17777-125">autodiscover-dod.office365.us</span></span> | <span data-ttu-id="17777-126">1 timme</span><span class="sxs-lookup"><span data-stu-id="17777-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="17777-127">Exchange Post för automatisk upptäckt</span><span class="sxs-lookup"><span data-stu-id="17777-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="17777-128">Om du har Exchange Server lokalt rekommenderar vi att du lämnar den befintliga posten på plats medan du migrerar till Exchange Online och uppdaterar posten när du har slutfört migreringen.</span><span class="sxs-lookup"><span data-stu-id="17777-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span>

### <a name="exchange-online-mx-record"></a><span data-ttu-id="17777-129">Exchange Online MX Record</span><span class="sxs-lookup"><span data-stu-id="17777-129">Exchange Online MX Record</span></span>

<span data-ttu-id="17777-130">MX-postvärdet för dina godkända domäner följer ett standardformat som anges *ovan:* klientorganisationens .mail.protection.office365.us, och ersätter klientorganisationen med den första delen av standardklientnamnet. </span><span class="sxs-lookup"><span data-stu-id="17777-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="17777-131">Om ditt klientnamn till exempel är contoso.onmicrosoft.us, använder du **contoso.mail.protection.office365.us** som värde för MX-posten.</span><span class="sxs-lookup"><span data-stu-id="17777-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="17777-132">Skype för företag – Online</span><span class="sxs-lookup"><span data-stu-id="17777-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="17777-133">CNAME-poster</span><span class="sxs-lookup"><span data-stu-id="17777-133">CNAME records</span></span>

| <span data-ttu-id="17777-134">Typ</span><span class="sxs-lookup"><span data-stu-id="17777-134">Type</span></span> | <span data-ttu-id="17777-135">Värdnamn</span><span class="sxs-lookup"><span data-stu-id="17777-135">Host name</span></span> | <span data-ttu-id="17777-136">Pekar på adress eller värde</span><span class="sxs-lookup"><span data-stu-id="17777-136">Points to address or value</span></span> | <span data-ttu-id="17777-137">TTL</span><span class="sxs-lookup"><span data-stu-id="17777-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="17777-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="17777-138">CNAME</span></span> | <span data-ttu-id="17777-139">sip</span><span class="sxs-lookup"><span data-stu-id="17777-139">sip</span></span> | <span data-ttu-id="17777-140">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="17777-140">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="17777-141">1 timme</span><span class="sxs-lookup"><span data-stu-id="17777-141">1 Hour</span></span> |
| <span data-ttu-id="17777-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="17777-142">CNAME</span></span> | <span data-ttu-id="17777-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="17777-143">lyncdiscover</span></span> | <span data-ttu-id="17777-144">webdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="17777-144">webdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="17777-145">1 timme</span><span class="sxs-lookup"><span data-stu-id="17777-145">1 Hour</span></span> | 

### <a name="srv-records"></a><span data-ttu-id="17777-146">SRV-poster</span><span class="sxs-lookup"><span data-stu-id="17777-146">SRV records</span></span>

| <span data-ttu-id="17777-147">Typ</span><span class="sxs-lookup"><span data-stu-id="17777-147">Type</span></span> | <span data-ttu-id="17777-148">Tjänst</span><span class="sxs-lookup"><span data-stu-id="17777-148">Service</span></span> | <span data-ttu-id="17777-149">Protokoll</span><span class="sxs-lookup"><span data-stu-id="17777-149">Protocol</span></span> | <span data-ttu-id="17777-150">Port</span><span class="sxs-lookup"><span data-stu-id="17777-150">Port</span></span> | <span data-ttu-id="17777-151">Vikt</span><span class="sxs-lookup"><span data-stu-id="17777-151">Weight</span></span> | <span data-ttu-id="17777-152">Prioritet</span><span class="sxs-lookup"><span data-stu-id="17777-152">Priority</span></span> | <span data-ttu-id="17777-153">Namn</span><span class="sxs-lookup"><span data-stu-id="17777-153">Name</span></span> | <span data-ttu-id="17777-154">Mål</span><span class="sxs-lookup"><span data-stu-id="17777-154">Target</span></span> | <span data-ttu-id="17777-155">TTL</span><span class="sxs-lookup"><span data-stu-id="17777-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="17777-156">SRV</span><span class="sxs-lookup"><span data-stu-id="17777-156">SRV</span></span> | <span data-ttu-id="17777-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="17777-157">\_sip</span></span> | <span data-ttu-id="17777-158">\_tls</span><span class="sxs-lookup"><span data-stu-id="17777-158">\_tls</span></span> | <span data-ttu-id="17777-159">443</span><span class="sxs-lookup"><span data-stu-id="17777-159">443</span></span> | <span data-ttu-id="17777-160">1</span><span class="sxs-lookup"><span data-stu-id="17777-160">1</span></span> | <span data-ttu-id="17777-161">100</span><span class="sxs-lookup"><span data-stu-id="17777-161">100</span></span> | @ | <span data-ttu-id="17777-162">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="17777-162">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="17777-163">1 timme</span><span class="sxs-lookup"><span data-stu-id="17777-163">1 Hour</span></span> |
| <span data-ttu-id="17777-164">SRV</span><span class="sxs-lookup"><span data-stu-id="17777-164">SRV</span></span> | <span data-ttu-id="17777-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="17777-165">\_sipfederationtls</span></span> | <span data-ttu-id="17777-166">\_tcp</span><span class="sxs-lookup"><span data-stu-id="17777-166">\_tcp</span></span> | <span data-ttu-id="17777-167">5061</span><span class="sxs-lookup"><span data-stu-id="17777-167">5061</span></span> | <span data-ttu-id="17777-168">1</span><span class="sxs-lookup"><span data-stu-id="17777-168">1</span></span> | <span data-ttu-id="17777-169">100</span><span class="sxs-lookup"><span data-stu-id="17777-169">100</span></span> | @ | <span data-ttu-id="17777-170">sipfed.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="17777-170">sipfed.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="17777-171">1 timme</span><span class="sxs-lookup"><span data-stu-id="17777-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="17777-172">Ytterligare DNS-poster</span><span class="sxs-lookup"><span data-stu-id="17777-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="17777-173">Om du har en befintlig *msoid* CNAME-post i din DNS-zon måste **du ta** bort posten från DNS för stunden.</span><span class="sxs-lookup"><span data-stu-id="17777-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="17777-174">Msoid-posten är inte kompatibel med Microsoft 365 Enterprise *(tidigare Office 365 ProPlus)* och kommer att förhindra att aktiveringen lyckas.</span><span class="sxs-lookup"><span data-stu-id="17777-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
