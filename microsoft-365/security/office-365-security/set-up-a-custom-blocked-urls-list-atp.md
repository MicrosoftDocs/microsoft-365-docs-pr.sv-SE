---
title: Konfigurera en egen lista med blockerade URL-adresser med säkerhet för ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du konfigurerar en lista över blockerade URL-adresser för organisationen med hjälp av Office 365 Avancerat skydd.
ms.openlocfilehash: e153d5631c12d52564643477216b777cdbc49433
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201009"
---
# <a name="set-up-a-custom-blocked-urls-list-using-atp-safe-links"></a><span data-ttu-id="f5c1f-103">Konfigurera en egen lista med blockerade URL-adresser med säkerhet för ATP</span><span class="sxs-lookup"><span data-stu-id="f5c1f-103">Set up a custom blocked URLs list using ATP Safe Links</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> <span data-ttu-id="f5c1f-104">Den här artikeln är avsedd för företagskunder som har [Office 365 Avancerat skydd](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="f5c1f-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="f5c1f-105">Om du är hem användare letar efter information om säkra länkar i Outlook kan du läsa mer i [avancerad Outlook.com säkerhet](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="f5c1f-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="f5c1f-106">Med [Office 365 Avancerat skydd](office-365-atp.md) (ATP) kan din organisation ha en anpassad lista med webb adresser (URL: er) som blockeras.</span><span class="sxs-lookup"><span data-stu-id="f5c1f-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked.</span></span> <span data-ttu-id="f5c1f-107">När en URL blockeras, tas de som klickar på länkar till den blockerade URL-adressen till en [varnings sida](atp-safe-links-warning-pages.md) som ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="f5c1f-107">When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span>

![Den här webbplatsen är blockerad](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

<span data-ttu-id="f5c1f-109">Listan blockerade URL-adresser definieras av organisationens säkerhets team för Microsoft 365 för företag och den listan gäller för alla i organisationen som omfattas av principer för säkra Länkar för Office 365.</span><span class="sxs-lookup"><span data-stu-id="f5c1f-109">The blocked URLs list is defined by your organization's Microsoft 365 for business security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span>

<span data-ttu-id="f5c1f-110">Läs den här artikeln för att få reda på hur du konfigurerar din organisations anpassade blockerade URL-adresser för [säkraste ATP-länkar i Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="f5c1f-110">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>

## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="f5c1f-111">Visa eller redigera en anpassad lista med blockerade URL: er</span><span class="sxs-lookup"><span data-stu-id="f5c1f-111">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="f5c1f-112">Med [ATP-säkra länkar i Office 365](atp-safe-links.md) används flera listor, till exempel organisationens anpassade blockerade URL-adresser.</span><span class="sxs-lookup"><span data-stu-id="f5c1f-112">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list.</span></span> <span data-ttu-id="f5c1f-113">Om du har nödvändig behörighet kan du ställa in organisationens anpassade lista.</span><span class="sxs-lookup"><span data-stu-id="f5c1f-113">If you have the necessary permissions, you can set up your organization's custom list.</span></span> <span data-ttu-id="f5c1f-114">Det gör du genom att redigera organisationens standard princip för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="f5c1f-114">You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="f5c1f-115">Om du vill redigera (eller definiera) ATP-principer måste du ha en av de roller som beskrivs i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="f5c1f-115">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

****

|<span data-ttu-id="f5c1f-116">Roll</span><span class="sxs-lookup"><span data-stu-id="f5c1f-116">Role</span></span>|<span data-ttu-id="f5c1f-117">Där/hur kopplat</span><span class="sxs-lookup"><span data-stu-id="f5c1f-117">Where/how assigned</span></span>|
|---|---|
|<span data-ttu-id="f5c1f-118">global administratör</span><span class="sxs-lookup"><span data-stu-id="f5c1f-118">global administrator</span></span>|<span data-ttu-id="f5c1f-119">Den person som registrerar sig för att köpa Microsoft 365 är en global administratör som standard.</span><span class="sxs-lookup"><span data-stu-id="f5c1f-119">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="f5c1f-120">(Mer information finns i [om administratörs roller i Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .)</span><span class="sxs-lookup"><span data-stu-id="f5c1f-120">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="f5c1f-121">Säkerhets administratör</span><span class="sxs-lookup"><span data-stu-id="f5c1f-121">Security Administrator</span></span>|<span data-ttu-id="f5c1f-122">Azure Active Directory-administratörs Center ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="f5c1f-122">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="f5c1f-123">Organisations hantering i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f5c1f-123">Exchange Online Organization Management</span></span>|<span data-ttu-id="f5c1f-124">Administrations Center för Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) )</span><span class="sxs-lookup"><span data-stu-id="f5c1f-124">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="f5c1f-125">eller</span><span class="sxs-lookup"><span data-stu-id="f5c1f-125">or</span></span> <br>  <span data-ttu-id="f5c1f-126">PowerShell-cmdletar (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="f5c1f-126">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span></span>|
|

> [!TIP]
> <span data-ttu-id="f5c1f-127">Mer information om roller och behörigheter finns i [behörigheter i säkerhets & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f5c1f-127">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="f5c1f-128">Visa eller redigera en anpassad lista över blockerade URL-adresser</span><span class="sxs-lookup"><span data-stu-id="f5c1f-128">To view or edit a custom blocked URLs list</span></span>

1. <span data-ttu-id="f5c1f-129">Gå till [https://protection.office.com](https://protection.office.com) och logga in med ditt arbets-eller skol konto.</span><span class="sxs-lookup"><span data-stu-id="f5c1f-129">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="f5c1f-130">I det vänstra navigerings fältet, under **Threat Management**, väljer du **policy** \> **Safe Links**.</span><span class="sxs-lookup"><span data-stu-id="f5c1f-130">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>

3. <span data-ttu-id="f5c1f-131">I de **principer som gäller för hela avsnittet organisation** väljer du **standard**och sedan **Redigera** (knappen Redigera påminner om en penna).</span><span class="sxs-lookup"><span data-stu-id="f5c1f-131">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="f5c1f-132">![Klicka på Redigera om du vill redigera standard principen för skydd av säkra länkar](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="f5c1f-132">![Click Edit to edit your default policy for Safe Links protection](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="f5c1f-133">Det gör att du kan visa din lista med blockerade URL-adresser.</span><span class="sxs-lookup"><span data-stu-id="f5c1f-133">This enables you to view your list of blocked URLs.</span></span> <span data-ttu-id="f5c1f-134">För det första kanske du inte har några URL-adresser här.</span><span class="sxs-lookup"><span data-stu-id="f5c1f-134">At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="f5c1f-135">![Lista över blockerade URL-adresser i standard principen för säkra länkar](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="f5c1f-135">![Blocked URLs list in the default Safe Links policy](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>

4. <span data-ttu-id="f5c1f-136">Markera rutan **Ange en giltig URL** , Skriv en URL och välj sedan plus tecknet ( **+** ).</span><span class="sxs-lookup"><span data-stu-id="f5c1f-136">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span>

5. <span data-ttu-id="f5c1f-137">När du är klar med att lägga till URL-adresser väljer du **Spara**längst ned till höger på skärmen.</span><span class="sxs-lookup"><span data-stu-id="f5c1f-137">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>

## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="f5c1f-138">Ett par saker du bör tänka på</span><span class="sxs-lookup"><span data-stu-id="f5c1f-138">A few things to keep in mind</span></span>

<span data-ttu-id="f5c1f-139">Tänk på följande när du lägger till URL-adresser i listan:</span><span class="sxs-lookup"><span data-stu-id="f5c1f-139">While you add URLs to your list, keep the following points in mind:</span></span>

- <span data-ttu-id="f5c1f-140">Ta inte med snedstreck ( **/** ) i slutet av webb adressen.</span><span class="sxs-lookup"><span data-stu-id="f5c1f-140">Do not include a forward slash ( **/**) at the end of the URL.</span></span> <span data-ttu-id="f5c1f-141">I stället för att ange `https://www.contoso.com/` skriver du in `https://www.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="f5c1f-141">For example, instead of entering `https://www.contoso.com/`, enter `https://www.contoso.com`.</span></span>

- <span data-ttu-id="f5c1f-142">Du kan ange en domän-URL (till exempel `contoso.com` eller `tailspintoys.com` ).</span><span class="sxs-lookup"><span data-stu-id="f5c1f-142">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`).</span></span> <span data-ttu-id="f5c1f-143">Då blockeras klickningar på alla URL-adresser som innehåller domänen.</span><span class="sxs-lookup"><span data-stu-id="f5c1f-143">This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="f5c1f-144">Du kan ange en under domän (gilla `toys.contoso.com*` ) utan att blockera en fullständig domän (som `contoso.com` ).</span><span class="sxs-lookup"><span data-stu-id="f5c1f-144">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`).</span></span> <span data-ttu-id="f5c1f-145">Då raderas en URL som innehåller under domänen, men blockerar inte klickningar till en URL som innehåller den fullständiga domänen.</span><span class="sxs-lookup"><span data-stu-id="f5c1f-145">This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>

- <span data-ttu-id="f5c1f-146">Du kan ta med upp till tre asterisker ( \* ) per URL.</span><span class="sxs-lookup"><span data-stu-id="f5c1f-146">You can include up to three wildcard asterisks (\*) per URL.</span></span> <span data-ttu-id="f5c1f-147">I tabellen nedan visas några exempel på vad du kan ange och vilken effekt de har.</span><span class="sxs-lookup"><span data-stu-id="f5c1f-147">The following table lists some examples of what you can enter and what effect those entries have.</span></span>

****

|<span data-ttu-id="f5c1f-148">Exempel post</span><span class="sxs-lookup"><span data-stu-id="f5c1f-148">Example Entry</span></span>|<span data-ttu-id="f5c1f-149">Vad det gör</span><span class="sxs-lookup"><span data-stu-id="f5c1f-149">What It Does</span></span>|
|---|---|
|<span data-ttu-id="f5c1f-150">`contoso.com` respektive `*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="f5c1f-150">`contoso.com` or `*contoso.com*`</span></span>|<span data-ttu-id="f5c1f-151">Blockerar domänen, under domäner och sökvägar, till exempel `https://www.contoso.com` , `https://sub.contoso.com` och `https://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="f5c1f-151">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="f5c1f-152">Blockerar en webbplats `https://contoso.com/a` men inte fler under Sök vägar `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="f5c1f-152">Blocks a site `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a*`|<span data-ttu-id="f5c1f-153">Blockerar en webbplats `https://contoso.com/a` och ytterligare under Sök vägar som `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="f5c1f-153">Blocks a site `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`</span></span>|
|`https://toys.contoso.com*`|<span data-ttu-id="f5c1f-154">Blockerar en under domän ("leksaker" i det här fallet) men tillåter klickningar till andra domän adresser (till exempel `https://contoso.com` eller `https://home.contoso.com` ).</span><span class="sxs-lookup"><span data-stu-id="f5c1f-154">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>|
|

> [!NOTE]
> <span data-ttu-id="f5c1f-155">Som standard kan du bara lägga till 500-URL: er i listan blockerade URL-adresser i Office 365-standard för Safe Links.</span><span class="sxs-lookup"><span data-stu-id="f5c1f-155">By default, you can only add 500 URLs to the blocked URL list in the Office 365 ATP Safe Links default policy.</span></span> <span data-ttu-id="f5c1f-156">En enskild URL får inte överstiga 128 tecken.</span><span class="sxs-lookup"><span data-stu-id="f5c1f-156">An individual URL can't exceed 128 characters.</span></span> <span data-ttu-id="f5c1f-157">Hela den blockerade URL-listan får inte innehålla fler än 10 000 tecken.</span><span class="sxs-lookup"><span data-stu-id="f5c1f-157">The entire Blocked URL list can't exceed 10,000 characters.</span></span>

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="f5c1f-158">Så här definierar du undantag för vissa användare i en organisation</span><span class="sxs-lookup"><span data-stu-id="f5c1f-158">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="f5c1f-159">Om du vill att vissa grupper ska kunna visa URL-adresser som kan ha blockerats av andra kan du ange en policy för Safet ATP-länkar som gäller för specifika mottagare.</span><span class="sxs-lookup"><span data-stu-id="f5c1f-159">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients.</span></span> <span data-ttu-id="f5c1f-160">Se [Konfigurera en anpassad "URL-lista", Skriv inte över "med hjälp av säkerhet för ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span><span class="sxs-lookup"><span data-stu-id="f5c1f-160">See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
