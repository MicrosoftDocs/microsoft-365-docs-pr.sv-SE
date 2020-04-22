---
title: Konfigurera en lista med anpassade blockerade webbadresser med ATP Safe Links
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
description: Lär dig hur du konfigurerar en lista med blockerade url:er för din organisation med hjälp av avancerat skydd mot office 365. De blockerade webbadresserna gäller för e-postmeddelanden och Office-dokument enligt dina ATP-principer för säkra länkar.
ms.openlocfilehash: ff8709a8bf0f8afc27ace2b3977be975f42c33a5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638410"
---
# <a name="set-up-a-custom-blocked-urls-list-using-atp-safe-links"></a><span data-ttu-id="1507c-104">Konfigurera en lista med anpassade blockerade webbadresser med ATP Safe Links</span><span class="sxs-lookup"><span data-stu-id="1507c-104">Set up a custom blocked URLs list using ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1507c-105">Den här artikeln är avsedd för företagskunder som har [Office 365 Avancerat skydd](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="1507c-105">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="1507c-106">Om du är hemanvändare och letar efter information om säkra länkar i Outlook läser du [Avancerad Outlook.com säkerhet](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="1507c-106">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="1507c-107">Med [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kan din organisation ha en anpassad lista över webbadresser som är blockerade.</span><span class="sxs-lookup"><span data-stu-id="1507c-107">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked.</span></span> <span data-ttu-id="1507c-108">När en webbadress blockeras tas personer som klickar på länkar till den blockerade webbadressen till en [varningssida](atp-safe-links-warning-pages.md) som liknar följande bild:</span><span class="sxs-lookup"><span data-stu-id="1507c-108">When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![Den här webbplatsen är blockerad](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="1507c-110">Listan blockerade webbadresser definieras av organisationens Microsoft 365 för företag-säkerhetsteam, och den listan gäller alla i organisationen som omfattas av Office 365 ATP Safe Links-principer.</span><span class="sxs-lookup"><span data-stu-id="1507c-110">The blocked URLs list is defined by your organization's Microsoft 365 for business security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="1507c-111">Läs den här artikeln om du vill lära dig hur du konfigurerar organisationens anpassade lista med blockerade webbadresser för [BETRODDA ATP-länkar i Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="1507c-111">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="1507c-112">Visa eller redigera en anpassad lista med blockerade webbadresser</span><span class="sxs-lookup"><span data-stu-id="1507c-112">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="1507c-113">[ATP Safe Links i Office 365](atp-safe-links.md) använder flera listor, inklusive organisationens anpassade lista med blockerade webbadresser.</span><span class="sxs-lookup"><span data-stu-id="1507c-113">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list.</span></span> <span data-ttu-id="1507c-114">Om du har de behörigheter som krävs kan du ställa in organisationens anpassade lista.</span><span class="sxs-lookup"><span data-stu-id="1507c-114">If you have the necessary permissions, you can set up your organization's custom list.</span></span> <span data-ttu-id="1507c-115">Du gör detta genom att redigera organisationens standardprincip för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="1507c-115">You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="1507c-116">Om du vill redigera (eller definiera) ATP-principer måste du tilldelas en av de roller som beskrivs i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="1507c-116">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span> 

|<span data-ttu-id="1507c-117">Roll</span><span class="sxs-lookup"><span data-stu-id="1507c-117">Role</span></span>  |<span data-ttu-id="1507c-118">Var/hur tilldelas</span><span class="sxs-lookup"><span data-stu-id="1507c-118">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="1507c-119">global administratör</span><span class="sxs-lookup"><span data-stu-id="1507c-119">global administrator</span></span> |<span data-ttu-id="1507c-120">Den person som registrerar sig för att köpa Microsoft 365 är en global administratör som standard.</span><span class="sxs-lookup"><span data-stu-id="1507c-120">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="1507c-121">(Läs [mer om Microsoft 365-administratörsroller.)](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="1507c-121">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="1507c-122">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="1507c-122">Security Administrator</span></span> |<span data-ttu-id="1507c-123">Administrationscenter för[https://aad.portal.azure.com](https://aad.portal.azure.com)Azure Active Directory ( )</span><span class="sxs-lookup"><span data-stu-id="1507c-123">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="1507c-124">Hantering av Exchange Online-organisation</span><span class="sxs-lookup"><span data-stu-id="1507c-124">Exchange Online Organization Management</span></span> |<span data-ttu-id="1507c-125">Administrationscenter[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)för Exchange ( )</span><span class="sxs-lookup"><span data-stu-id="1507c-125">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="1507c-126">eller</span><span class="sxs-lookup"><span data-stu-id="1507c-126">or</span></span> <br>  <span data-ttu-id="1507c-127">PowerShell-cmdletar (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="1507c-127">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span></span> |

> [!TIP]
> <span data-ttu-id="1507c-128">Mer information om roller och behörigheter finns [i Behörigheter i Säkerhetsefterlevnadscenter &amp; ](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="1507c-128">To learn more about roles and permissions, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="1507c-129">Så här visar eller redigerar du en anpassad lista med blockerade webbadresser</span><span class="sxs-lookup"><span data-stu-id="1507c-129">To view or edit a custom blocked URLs list</span></span>
  
1. <span data-ttu-id="1507c-130">Gå [https://protection.office.com](https://protection.office.com) till och logga in med ditt arbets- eller skolkonto.</span><span class="sxs-lookup"><span data-stu-id="1507c-130">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="1507c-131">Välj **Policy** \> Säkra länkar under **Hothantering**i den vänstra **navigeringen.**</span><span class="sxs-lookup"><span data-stu-id="1507c-131">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="1507c-132">I de **principer som gäller för hela organisationsavsnittet** väljer du **Standard**och väljer sedan **Redigera** (knappen Redigera liknar en penna).</span><span class="sxs-lookup"><span data-stu-id="1507c-132">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="1507c-133">![Klicka på Redigera om du vill redigera standardprincipen för skydd av säkra länkar](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="1507c-133">![Click Edit to edit your default policy for Safe Links protection](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="1507c-134">På så sätt kan du visa listan över blockerade webbadresser.</span><span class="sxs-lookup"><span data-stu-id="1507c-134">This enables you to view your list of blocked URLs.</span></span> <span data-ttu-id="1507c-135">Först kanske du inte har några webbadresser listade här.</span><span class="sxs-lookup"><span data-stu-id="1507c-135">At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="1507c-136">![Lista med blockerade webbadresser i standardprincipen för säkra länkar](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="1507c-136">![Blocked URLs list in the default Safe Links policy](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>
  
4. <span data-ttu-id="1507c-137">Markera rutan **Ange en giltig URL,** skriv en URL**+** och välj sedan plustecknet ( ).</span><span class="sxs-lookup"><span data-stu-id="1507c-137">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span> 

5. <span data-ttu-id="1507c-138">När du har lagt till webbadresser väljer du **Spara**i det nedre högra hörnet av skärmen .</span><span class="sxs-lookup"><span data-stu-id="1507c-138">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="1507c-139">Några saker att tänka på</span><span class="sxs-lookup"><span data-stu-id="1507c-139">A few things to keep in mind</span></span>

<span data-ttu-id="1507c-140">När du lägger till webbadresser i listan bör du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="1507c-140">While you add URLs to your list, keep the following points in mind:</span></span> 

- <span data-ttu-id="1507c-141">Ta inte med ett **/** snedstreck ( ) i slutet av webbadressen.</span><span class="sxs-lookup"><span data-stu-id="1507c-141">Do not include a forward slash ( **/**) at the end of the URL.</span></span> <span data-ttu-id="1507c-142">I stället för att `https://www.contoso.com/`till `https://www.contoso.com`exempel skriva in anger du .</span><span class="sxs-lookup"><span data-stu-id="1507c-142">For example, instead of entering `https://www.contoso.com/`, enter `https://www.contoso.com`.</span></span>
    
- <span data-ttu-id="1507c-143">Du kan ange en URL `contoso.com` endast `tailspintoys.com`för domän (gilla eller ).</span><span class="sxs-lookup"><span data-stu-id="1507c-143">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`).</span></span> <span data-ttu-id="1507c-144">Detta blockerar klick på alla webbadresser som innehåller domänen.</span><span class="sxs-lookup"><span data-stu-id="1507c-144">This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="1507c-145">Du kan ange en underdomän (som) `toys.contoso.com*`utan att `contoso.com`blockera en fullständig domän (till exempel ).</span><span class="sxs-lookup"><span data-stu-id="1507c-145">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`).</span></span> <span data-ttu-id="1507c-146">Detta blockerar klick på en URL som innehåller underdomänen, men det blockerar inte klick till en URL som innehåller hela domänen.</span><span class="sxs-lookup"><span data-stu-id="1507c-146">This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>  
    
- <span data-ttu-id="1507c-147">Du kan inkludera upp till tre jokerteckenasterisker (\*) per webbadress.</span><span class="sxs-lookup"><span data-stu-id="1507c-147">You can include up to three wildcard asterisks (\*) per URL.</span></span> <span data-ttu-id="1507c-148">I följande tabell visas några exempel på vad du kan ange och vilken effekt dessa poster har.</span><span class="sxs-lookup"><span data-stu-id="1507c-148">The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="1507c-149">**Exempel på post**</span><span class="sxs-lookup"><span data-stu-id="1507c-149">**Example Entry**</span></span>|<span data-ttu-id="1507c-150">**Vad den gör**</span><span class="sxs-lookup"><span data-stu-id="1507c-150">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1507c-151">`contoso.com`Eller`*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="1507c-151">`contoso.com` or `*contoso.com*`</span></span>  <br/> |<span data-ttu-id="1507c-152">Blockerar domänen, underdomänerna och sökvägarna, till exempel `https://www.contoso.com`, `https://sub.contoso.com`och`https://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="1507c-152">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc`</span></span>  <br/> |
|`https://contoso.com/a`  <br/> |<span data-ttu-id="1507c-153">Blockerar en `https://contoso.com/a` plats men inte ytterligare undervägar som`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="1507c-153">Blocks a site `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`</span></span>  <br/> |
|`https://contoso.com/a*`  <br/> |<span data-ttu-id="1507c-154">Blockerar en `https://contoso.com/a` webbplats och ytterligare undervägar som`https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="1507c-154">Blocks a site `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`</span></span>  <br/> |
|`https://toys.contoso.com*`  <br/> |<span data-ttu-id="1507c-155">Blockerar en underdomän ("leksaker" i det här fallet) men tillåter `https://contoso.com` `https://home.contoso.com`klick till andra domänadresser (gilla eller ).</span><span class="sxs-lookup"><span data-stu-id="1507c-155">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="1507c-156">Så här definierar du undantag för vissa användare i en organisation</span><span class="sxs-lookup"><span data-stu-id="1507c-156">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="1507c-157">Om du vill att vissa grupper ska kunna visa webbadresser som kan vara blockerade för andra kan du ange en ATP Safe Links-princip som gäller för specifika mottagare.</span><span class="sxs-lookup"><span data-stu-id="1507c-157">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients.</span></span> <span data-ttu-id="1507c-158">Se [Konfigurera en anpassad url-lista för "skriv inte om" med hjälp av ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span><span class="sxs-lookup"><span data-stu-id="1507c-158">See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  

