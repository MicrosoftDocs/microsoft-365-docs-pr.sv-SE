---
title: Anslut din domän till Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig verifiera din domän och skapa DNS-poster på vilken DNS-värd som helst för Microsoft 365.
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: 206b435130e8e77ed1540432e3bbeff7f16463bf
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658221"
---
# <a name="connect-your-domain-to-microsoft-365"></a><span data-ttu-id="9762d-103">Anslut din domän till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9762d-103">Connect your domain to Microsoft 365</span></span>

> [!NOTE]
> <span data-ttu-id="9762d-104">Om du inte lägger till en domän kommer personer i organisationen att använda domänen onmicrosoft.com för sina e-postadresser tills du gör det.</span><span class="sxs-lookup"><span data-stu-id="9762d-104">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="9762d-105">Det är viktigt att lägga till domänen innan du lägger till användare, så att du inte behöver konfigurera dem två gånger.</span><span class="sxs-lookup"><span data-stu-id="9762d-105">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="9762d-106">[Läs frågor och svar om domäner](../setup/domains-faq.yml) om du inte hittar det du letar efter nedan.</span><span class="sxs-lookup"><span data-stu-id="9762d-106">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for below.</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="9762d-107">Lägga till en MX-post så att e-post för din domän kommer till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9762d-107">Add an MX record so email for your domain will come to Microsoft</span></span>

<span data-ttu-id="9762d-108">Du får information om MX-posten från administrationscentrets konfigurationsguide.</span><span class="sxs-lookup"><span data-stu-id="9762d-108">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="9762d-109">Lägg till en ny MX-post på värdens webbplats.</span><span class="sxs-lookup"><span data-stu-id="9762d-109">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="9762d-110">Kontrollera att fälten är inställda på följande värden:</span><span class="sxs-lookup"><span data-stu-id="9762d-110">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="9762d-111">Posttyp: `MX`</span><span class="sxs-lookup"><span data-stu-id="9762d-111">Record Type: `MX`</span></span>
- <span data-ttu-id="9762d-112">Prioritet: Ange det högsta värdet, vanligtvis `0`.</span><span class="sxs-lookup"><span data-stu-id="9762d-112">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="9762d-113">Värdnamn: `@`</span><span class="sxs-lookup"><span data-stu-id="9762d-113">Host Name: `@`</span></span>
- <span data-ttu-id="9762d-114">Pekar på adress: Kopiera värdet från administrationscentret och klistra in det här.</span><span class="sxs-lookup"><span data-stu-id="9762d-114">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="9762d-115">TTL: `3600‎` (eller din leverantörs standard)</span><span class="sxs-lookup"><span data-stu-id="9762d-115">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="9762d-116">Spara posten och ta bort eventuella andra MX-poster.</span><span class="sxs-lookup"><span data-stu-id="9762d-116">Save the record, and then remove any other MX records.</span></span>

## <a name="add-a-cname-record-to-connect-users-to-their-mailboxes"></a><span data-ttu-id="9762d-117">Lägg till en CNAME-post för att ansluta användare till deras brevlådor</span><span class="sxs-lookup"><span data-stu-id="9762d-117">Add a CNAME record to connect users to their mailboxes</span></span>
<span data-ttu-id="9762d-118">Du får information om CNAME-posterna från administrationscentrets konfigurationsguide.</span><span class="sxs-lookup"><span data-stu-id="9762d-118">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="9762d-119">Lägg till följande CNAME-post på din webbhotellleverantörs webbplats.</span><span class="sxs-lookup"><span data-stu-id="9762d-119">On your hosting provider's website, add the following CNAME record.</span></span> <span data-ttu-id="9762d-120">Kontrollera att fälten är inställda på följande värden för varje:</span><span class="sxs-lookup"><span data-stu-id="9762d-120">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="9762d-121">Posttyp: `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="9762d-121">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="9762d-122">Värd: Klistra in värdena som du kopierar från administrationscentret här.</span><span class="sxs-lookup"><span data-stu-id="9762d-122">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="9762d-123">Pekar på adress: Kopiera värdet från administrationscentret och klistra in det här.</span><span class="sxs-lookup"><span data-stu-id="9762d-123">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="9762d-124">TTL: `3600‎` (eller din leverantörs standard)</span><span class="sxs-lookup"><span data-stu-id="9762d-124">TTL: `3600‎` (or your provider default)</span></span>

## <a name="add-a-txt-record-to-help-prevent-spam"></a><span data-ttu-id="9762d-125">Lägga till en TXT-post för SPF för att förhindra skräppost</span><span class="sxs-lookup"><span data-stu-id="9762d-125">Add a TXT record to help prevent spam</span></span>
<span data-ttu-id="9762d-126">**Innan du börjar:** Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9762d-126">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="9762d-127">Lägg istället till de obligatoriska Microsoft 365-värdena i den aktuella posten på din värds webbplats så att du har en *enda* SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="9762d-127">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="9762d-128">Redigera den befintliga SPF-posten eller skapa en SPF-post på värdens webbplats.</span><span class="sxs-lookup"><span data-stu-id="9762d-128">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="9762d-129">Kontrollera att fälten är inställda på följande värden:</span><span class="sxs-lookup"><span data-stu-id="9762d-129">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="9762d-130">Posttyp: `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="9762d-130">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="9762d-131">Värd: `@`</span><span class="sxs-lookup"><span data-stu-id="9762d-131">Host: `@`</span></span>
- <span data-ttu-id="9762d-132">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="9762d-132">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="9762d-133">TTL: `3600‎` (eller din leverantörs standard)</span><span class="sxs-lookup"><span data-stu-id="9762d-133">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="9762d-134">Spara posten.</span><span class="sxs-lookup"><span data-stu-id="9762d-134">Save the record.</span></span>

<span data-ttu-id="9762d-135">Använd något av följande [SPF-verifieringsverktyg](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) för att verifiera SPF-posten</span><span class="sxs-lookup"><span data-stu-id="9762d-135">Validate your SPF record by using one of these [SPF validation tools](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="9762d-136">SPF har utformats för att hjälpa till att förhindra förfalskning men det finns förfalskningsmetoder som SPF inte skyddar mot.</span><span class="sxs-lookup"><span data-stu-id="9762d-136">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="9762d-137">För att skydda mot dessa ska du, efter att ha konfigurerat SPF, även konfigurera DKIM och DMARC för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9762d-137">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span>

<span data-ttu-id="9762d-138">Information om hur du kommer igång finns i [Använda DKIM för att validera utgående e-post som skickas från din domän i Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) och [Använda DMARC för att validera e-post i Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="9762d-138">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) and [Use DMARC to validate email in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="9762d-139">Slutligen, gå tillbaka till administratörscentrets domäninställningsguide för att slutföra installationen.</span><span class="sxs-lookup"><span data-stu-id="9762d-139">Finally, head back to the admin center domain setup wizard to complete your setup.</span></span>