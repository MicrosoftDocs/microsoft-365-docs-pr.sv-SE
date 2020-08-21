---
title: Hantera tillåtna och blockerade webb adresser i listan Tillåt/blockera i klient organisationen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa mer om hur du konfigurerar URL-poster i listan Tillåt/blockera i klient organisationen för säkerhets &.
ms.openlocfilehash: 888a96f23daf2cf47847466ad4080f310be7f9b4
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845948"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="8d833-103">Hantera URL: er i listan Tillåt / blockera hyresgäster</span><span class="sxs-lookup"><span data-stu-id="8d833-103">Manage URLs in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="8d833-104">De funktioner som beskrivs i det här avsnittet är i förhands gransknings syfte och kan ändras och är inte tillgängliga i alla organisationer.</span><span class="sxs-lookup"><span data-stu-id="8d833-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="8d833-105">I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor kanske du inte kan komma att behöva filtrera EOP Verdict.</span><span class="sxs-lookup"><span data-stu-id="8d833-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="8d833-106">Ett bra meddelande kan till exempel vara markerat som dåligt (ett falskt positivt) eller så tillåts ett ogiltigt meddelande genom (ett falskt negativt).</span><span class="sxs-lookup"><span data-stu-id="8d833-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="8d833-107">Med listan Tillåt/begränsa klient organisation i säkerhets & Compliance Center kan du manuellt åsidosätta Microsoft 365 filter-verdicts.</span><span class="sxs-lookup"><span data-stu-id="8d833-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="8d833-108">Listan över tillåtna/blockerade innehavare används under e-postflöde och när användaren klickar på den.</span><span class="sxs-lookup"><span data-stu-id="8d833-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="8d833-109">Du kan ange URL-adresser att tillåta eller blockera i listan Tillåt/blockera för klient organisation.</span><span class="sxs-lookup"><span data-stu-id="8d833-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="8d833-110">I det här avsnittet beskrivs hur du konfigurerar poster i listan Tillåt/blockera i säkerhets & för kontroll av klient organisation eller i PowerShell-organisationen (Exchange Online PowerShell för Microsoft 365-organisationer med post lådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="8d833-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8d833-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="8d833-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8d833-112">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="8d833-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8d833-113">För att gå direkt till sidan **Tillåt/blockera lista för klient organisation** , Använd <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="8d833-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="8d833-114">Tillgängliga URL-värden beskrivs i [URL-syntaxen för avsnittet Tillåt/blockera lista för klient organisation](#url-syntax-for-the-tenant-allowblock-list) längre ned i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="8d833-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="8d833-115">Listan Tillåt/blockera för klient organisationer tillåter högst 500 poster för URL: er.</span><span class="sxs-lookup"><span data-stu-id="8d833-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="8d833-116">En post ska vara aktiv inom 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="8d833-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="8d833-117">Block poster har högre prioritet än Tillåt-poster.</span><span class="sxs-lookup"><span data-stu-id="8d833-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="8d833-118">Poster i listan Tillåt/blockera för klient organisationer upphör som standard efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="8d833-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="8d833-119">Du kan ange ett datum eller ange att de aldrig ska upphöra att gälla.</span><span class="sxs-lookup"><span data-stu-id="8d833-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="8d833-120">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="8d833-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="8d833-121">Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="8d833-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="8d833-122">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:</span><span class="sxs-lookup"><span data-stu-id="8d833-122">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="8d833-123">Om du vill lägga till och ta bort värden från listan Tillåt/blockera för klient organisationer måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="8d833-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="8d833-124">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="8d833-124">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="8d833-125">**Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="8d833-125">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="8d833-126">Om du vill ha skrivskyddad åtkomst till listan Tillåt/blockera för klient organisationer måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="8d833-126">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="8d833-127">**Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="8d833-127">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="8d833-128">**Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="8d833-128">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8d833-129">Använd säkerhets & efterlevnad för att skapa URL-poster i listan Tillåt/blockera för klient organisation</span><span class="sxs-lookup"><span data-stu-id="8d833-129">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8d833-130">Mer information om syntaxen för URL-poster finns i [URL-syntaxen för listan Tillåt/blockera lista för klient organisation](#url-syntax-for-the-tenant-allowblock-list) längre ned i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="8d833-130">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="8d833-131">Gå till fliken **Threat Management** \> **policy** för \> **Tillåt/blockera listor**i säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="8d833-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8d833-132">På sidan **Tillåt/blockera lista för klient organisation** kontrollerar du att fliken **URL: er** är markerad och klickar sedan på **Lägg till** .</span><span class="sxs-lookup"><span data-stu-id="8d833-132">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="8d833-133">I **Lägg till** utfällbara URL-adresser som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="8d833-133">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8d833-134">**Lägga till URL-adresser med jokertecken**: Ange en URL per rad, upp till maximalt 20.</span><span class="sxs-lookup"><span data-stu-id="8d833-134">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="8d833-135">**Blockera/Tillåt**: Välj om du vill **tillåta** eller **blockera** angivna URL-adresser.</span><span class="sxs-lookup"><span data-stu-id="8d833-135">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="8d833-136">**Aldrig giltig**: gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="8d833-136">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="8d833-137">Kontrol lera att inställningen är avstängt ![ ](../../media/scc-toggle-off.png) och ange förfallo datumet för posterna genom att använda rutan **upphör att gälla** .</span><span class="sxs-lookup"><span data-stu-id="8d833-137">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="8d833-138">eller</span><span class="sxs-lookup"><span data-stu-id="8d833-138">or</span></span>

     - <span data-ttu-id="8d833-139">Flytta växlings knappen till höger för att konfigurera att posterna aldrig ska förfalla:</span><span class="sxs-lookup"><span data-stu-id="8d833-139">Move the toggle to the right to configure the entries to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="8d833-141">.</span><span class="sxs-lookup"><span data-stu-id="8d833-141">.</span></span>

   - <span data-ttu-id="8d833-142">**Valfri anmärkning**: Ange en beskrivande text för posterna.</span><span class="sxs-lookup"><span data-stu-id="8d833-142">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="8d833-143">När du är klar klickar du på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="8d833-143">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8d833-144">Använd säkerhets & Compliance Center för att visa poster i listan Tillåt/blockera för klient organisation</span><span class="sxs-lookup"><span data-stu-id="8d833-144">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="8d833-145">Gå till fliken **Threat Management** \> **policy** för \> **Tillåt/blockera listor**i säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="8d833-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8d833-146">Välj fliken **URL: er** .</span><span class="sxs-lookup"><span data-stu-id="8d833-146">Select the **URLs** tab.</span></span>

<span data-ttu-id="8d833-147">Klicka på följande kolumn rubriker för att sortera i stigande eller fallande ordning:</span><span class="sxs-lookup"><span data-stu-id="8d833-147">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="8d833-148">**Värde**</span><span class="sxs-lookup"><span data-stu-id="8d833-148">**Value**</span></span>
- <span data-ttu-id="8d833-149">**Åtgärd**: **blockera** eller **Tillåt**.</span><span class="sxs-lookup"><span data-stu-id="8d833-149">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="8d833-150">**Senast uppdaterad**</span><span class="sxs-lookup"><span data-stu-id="8d833-150">**Last updated date**</span></span>
- <span data-ttu-id="8d833-151">**Utgångs datum**</span><span class="sxs-lookup"><span data-stu-id="8d833-151">**Expiration date**</span></span>
- <span data-ttu-id="8d833-152">**Fotnot**</span><span class="sxs-lookup"><span data-stu-id="8d833-152">**Note**</span></span>

<span data-ttu-id="8d833-153">Klicka på **gruppera** för att gruppera posterna **efter åtgärd** (**blockera** eller **Tillåt**) eller **ingen**.</span><span class="sxs-lookup"><span data-stu-id="8d833-153">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="8d833-154">Klicka på **Sök**, ange hela eller delar av ett värde och tryck sedan på RETUR för att hitta ett visst värde.</span><span class="sxs-lookup"><span data-stu-id="8d833-154">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="8d833-155">När du är klar klickar du på **Rensa sökning** ![ rensa Sök ikonen ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="8d833-155">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="8d833-156">Klicka på **filter**.</span><span class="sxs-lookup"><span data-stu-id="8d833-156">Click **Filter**.</span></span> <span data-ttu-id="8d833-157">I det **filter** som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="8d833-157">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="8d833-158">**Åtgärd**: Välj **Tillåt**, **blockera** eller båda.</span><span class="sxs-lookup"><span data-stu-id="8d833-158">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="8d833-159">**Aldrig förfaller**: Välj av ( ![ Växla av ](../../media/scc-toggle-off.png) ) eller på ( ![ växling på ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="8d833-159">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="8d833-160">**Uppdaterades senast**: Välj ett start datum (**från**), ett slutdatum (**till**) eller båda.</span><span class="sxs-lookup"><span data-stu-id="8d833-160">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="8d833-161">**Utgångs datum**: Välj ett start datum (**från**), ett slutdatum (**till**) eller båda.</span><span class="sxs-lookup"><span data-stu-id="8d833-161">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="8d833-162">När du är klar klickar du på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="8d833-162">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="8d833-163">Om du vill ta bort befintliga filter klickar du på **filter**och sedan på **Rensa filter**i det **filter** som visas.</span><span class="sxs-lookup"><span data-stu-id="8d833-163">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8d833-164">Använd säkerhets & Compliance Center för att ändra poster i listan Tillåt/blockera för klient organisation</span><span class="sxs-lookup"><span data-stu-id="8d833-164">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8d833-165">Du kan inte ändra själva URL-värdet.</span><span class="sxs-lookup"><span data-stu-id="8d833-165">You can't modify the URL value itself.</span></span> <span data-ttu-id="8d833-166">I stället måste du ta bort posten och skapa den igen.</span><span class="sxs-lookup"><span data-stu-id="8d833-166">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="8d833-167">Gå till fliken **Threat Management** \> **policy** för \> **Tillåt/blockera listor**i säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="8d833-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8d833-168">Välj fliken **URL: er** .</span><span class="sxs-lookup"><span data-stu-id="8d833-168">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="8d833-169">Markera den post som du vill ändra och klicka sedan på **Redigera** ![ redigerings ikon ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="8d833-169">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="8d833-170">I den utfällbara filen som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="8d833-170">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8d833-171">**Blockera/Tillåt**: Välj **Tillåt** eller **blockera**.</span><span class="sxs-lookup"><span data-stu-id="8d833-171">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="8d833-172">**Aldrig giltig**: gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="8d833-172">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="8d833-173">Kontrol lera att inställningen är avstängt ![ ](../../media/scc-toggle-off.png) och ange förfallo datumet för posten i rutan **upphör att gälla** .</span><span class="sxs-lookup"><span data-stu-id="8d833-173">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="8d833-174">eller</span><span class="sxs-lookup"><span data-stu-id="8d833-174">or</span></span>

     - <span data-ttu-id="8d833-175">Flytta växlings knappen till höger för att konfigurera posten så att den aldrig förfaller:</span><span class="sxs-lookup"><span data-stu-id="8d833-175">Move the toggle to the right to configure the entry to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="8d833-177">.</span><span class="sxs-lookup"><span data-stu-id="8d833-177">.</span></span>

   - <span data-ttu-id="8d833-178">**Valfri anmärkning**: Ange en beskrivande text för posten.</span><span class="sxs-lookup"><span data-stu-id="8d833-178">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="8d833-179">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="8d833-179">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="8d833-180">Använd säkerhets & Compliance Center för att ta bort poster från listan Tillåt/blockera för klient organisation</span><span class="sxs-lookup"><span data-stu-id="8d833-180">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="8d833-181">Gå till fliken **Threat Management** \> **policy** för \> **Tillåt/blockera listor**i säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="8d833-181">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8d833-182">Välj fliken **URL: er** .</span><span class="sxs-lookup"><span data-stu-id="8d833-182">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="8d833-183">Markera den post som du vill ta bort och klicka sedan på **ta bort** ![ ikon för borttagning ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="8d833-183">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="8d833-184">I varnings dialog rutan som visas klickar du på **ta bort**.</span><span class="sxs-lookup"><span data-stu-id="8d833-184">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="8d833-185">Använd Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera listan Tillåt/blockera klient organisation</span><span class="sxs-lookup"><span data-stu-id="8d833-185">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8d833-186">Använd PowerShell för att lägga till poster i listan Tillåt/blockera för klient organisation</span><span class="sxs-lookup"><span data-stu-id="8d833-186">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8d833-187">Använd följande syntax för att lägga till poster i listan Tillåt/blockera i klient organisationen:</span><span class="sxs-lookup"><span data-stu-id="8d833-187">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="8d833-188">Det här exemplet lägger till en URL-adressblock för contoso.com och alla under domäner (till exempel contoso.com, www.contoso.com och xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8d833-188">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="8d833-189">Eftersom vi inte använde parametrarna förfallo eller noexpires upphör posten efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="8d833-189">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="8d833-190">Detaljerad information om syntax och parametrar finns i [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="8d833-190">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8d833-191">Använda PowerShell för att visa poster i listan Tillåt/blockera i klient organisationen</span><span class="sxs-lookup"><span data-stu-id="8d833-191">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8d833-192">Om du vill visa poster i listan Tillåt/begränsa klient organisation använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="8d833-192">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="8d833-193">I det här exemplet returneras alla blockerade URL: er.</span><span class="sxs-lookup"><span data-stu-id="8d833-193">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="8d833-194">Detaljerad information om syntax och parametrar finns i [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="8d833-194">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8d833-195">Använda PowerShell för att ändra poster i listan Tillåt/blockera för klient organisation</span><span class="sxs-lookup"><span data-stu-id="8d833-195">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8d833-196">Du kan inte ändra själva URL-värdet.</span><span class="sxs-lookup"><span data-stu-id="8d833-196">You can't modify the URL value itself.</span></span> <span data-ttu-id="8d833-197">I stället måste du ta bort posten och skapa den igen.</span><span class="sxs-lookup"><span data-stu-id="8d833-197">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="8d833-198">Om du vill ändra poster i listan Tillåt/blockera för klient organisation använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="8d833-198">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="8d833-199">I det här exemplet ändras utgångs datumet för den angivna posten.</span><span class="sxs-lookup"><span data-stu-id="8d833-199">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="8d833-200">Detaljerad information om syntax och parametrar finns i [set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="8d833-200">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="8d833-201">Använd PowerShell för att ta bort poster från listan Tillåt/blockera för klient organisation</span><span class="sxs-lookup"><span data-stu-id="8d833-201">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="8d833-202">Om du vill ta bort poster från listan Tillåt/blockera klient organisation använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="8d833-202">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="8d833-203">I det här exemplet tas den angivna URL-posten bort från listan Tillåt/blockera för klient organisation.</span><span class="sxs-lookup"><span data-stu-id="8d833-203">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="8d833-204">Detaljerad information om syntax och parametrar finns i [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="8d833-204">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="8d833-205">URL-syntax för listan Tillåt/blockera för klient organisation</span><span class="sxs-lookup"><span data-stu-id="8d833-205">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="8d833-206">IP4v-och IPv6-adresser är tillåtna, men TCP/UDP-portarna är inte det.</span><span class="sxs-lookup"><span data-stu-id="8d833-206">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="8d833-207">Fil namns tillägg tillåts inte (till exempel test.pdf).</span><span class="sxs-lookup"><span data-stu-id="8d833-207">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="8d833-208">Unicode stöds inte, men punycode är.</span><span class="sxs-lookup"><span data-stu-id="8d833-208">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="8d833-209">Värddator namn är tillåtna om följande påståenden stämmer:</span><span class="sxs-lookup"><span data-stu-id="8d833-209">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="8d833-210">Värd namnet innehåller en punkt.</span><span class="sxs-lookup"><span data-stu-id="8d833-210">The hostname contains a period.</span></span>
  - <span data-ttu-id="8d833-211">Det finns minst ett tecken till vänster om perioden.</span><span class="sxs-lookup"><span data-stu-id="8d833-211">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="8d833-212">Det finns minst två tecken till höger om perioden.</span><span class="sxs-lookup"><span data-stu-id="8d833-212">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="8d833-213">Till exempel `t.co` tillåts `.com` eller `contoso.` är inte tillåtet.</span><span class="sxs-lookup"><span data-stu-id="8d833-213">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="8d833-214">Under Sök vägar är inte underförstådda.</span><span class="sxs-lookup"><span data-stu-id="8d833-214">Subpaths are not implied.</span></span>

  <span data-ttu-id="8d833-215">Innehåller till exempel `contoso.com` inte `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="8d833-215">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="8d833-216">Jokertecken (\*) tillåts i följande fall:</span><span class="sxs-lookup"><span data-stu-id="8d833-216">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="8d833-217">Ett vänster jokertecken måste följas av en punkt för att ange en under domän.</span><span class="sxs-lookup"><span data-stu-id="8d833-217">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="8d833-218">Till exempel `*.contoso.com` tillåts; `*contoso.com` är inte tillåtet.</span><span class="sxs-lookup"><span data-stu-id="8d833-218">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="8d833-219">Ett höger jokertecken måste följa ett snedstreck (/) för att ange en sökväg.</span><span class="sxs-lookup"><span data-stu-id="8d833-219">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="8d833-220">Till exempel `contoso.com/*` tillåts `contoso.com*` eller `contoso.com/ab*` är inte tillåtet.</span><span class="sxs-lookup"><span data-stu-id="8d833-220">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="8d833-221">Alla under Sök vägar underförstås inte med ett höger jokertecken.</span><span class="sxs-lookup"><span data-stu-id="8d833-221">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="8d833-222">Innehåller till exempel `contoso.com/*` inte `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="8d833-222">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="8d833-223">`*.com*` är ogiltig (inte en matchad domän och höger jokertecken följer inte ett snedstreck).</span><span class="sxs-lookup"><span data-stu-id="8d833-223">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="8d833-224">Jokertecken tillåts inte i IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="8d833-224">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="8d833-225">Tilde-tecknet (~) är tillgängligt i följande fall:</span><span class="sxs-lookup"><span data-stu-id="8d833-225">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="8d833-226">Ett Vänsterställt tildetecken innebär en domän och alla under domäner.</span><span class="sxs-lookup"><span data-stu-id="8d833-226">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="8d833-227">Till exempel `~contoso.com` inkluderar `contoso.com` och `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="8d833-227">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="8d833-228">URL-poster som innehåller protokoll (till exempel `http://` , `https://` eller `ftp://` ) fungerar inte eftersom URL-poster gäller för alla protokoll.</span><span class="sxs-lookup"><span data-stu-id="8d833-228">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="8d833-229">Det finns inget användar namn eller lösen ord.</span><span class="sxs-lookup"><span data-stu-id="8d833-229">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="8d833-230">Citat tecken ("or") är ogiltiga tecken.</span><span class="sxs-lookup"><span data-stu-id="8d833-230">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="8d833-231">En URL ska inkludera alla omdirigeringar om möjligt.</span><span class="sxs-lookup"><span data-stu-id="8d833-231">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="8d833-232">Scenarier för URL-post</span><span class="sxs-lookup"><span data-stu-id="8d833-232">URL entry scenarios</span></span>

<span data-ttu-id="8d833-233">Giltiga URL-värden och deras resultat beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="8d833-233">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="8d833-234">Scenario: inga jokertecken</span><span class="sxs-lookup"><span data-stu-id="8d833-234">Scenario: No wildcards</span></span>

<span data-ttu-id="8d833-235">**Post**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="8d833-235">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="8d833-236">**Tillåt matchning**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-236">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="8d833-237">**Tillåt ej matchad**:</span><span class="sxs-lookup"><span data-stu-id="8d833-237">**Allow not matched**:</span></span>

  - <span data-ttu-id="8d833-238">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-238">abc-contoso.com</span></span>
  - <span data-ttu-id="8d833-239">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8d833-239">contoso.com/a</span></span>
  - <span data-ttu-id="8d833-240">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-240">payroll.contoso.com</span></span>
  - <span data-ttu-id="8d833-241">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-241">test.com/contoso.com</span></span>
  - <span data-ttu-id="8d833-242">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-242">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="8d833-243">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-243">www.contoso.com</span></span>
  - <span data-ttu-id="8d833-244">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="8d833-244">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="8d833-245">**Blockera träff**:</span><span class="sxs-lookup"><span data-stu-id="8d833-245">**Block match**:</span></span>

  - <span data-ttu-id="8d833-246">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-246">contoso.com</span></span>
  - <span data-ttu-id="8d833-247">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8d833-247">contoso.com/a</span></span>
  - <span data-ttu-id="8d833-248">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-248">payroll.contoso.com</span></span>
  - <span data-ttu-id="8d833-249">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-249">test.com/contoso.com</span></span>
  - <span data-ttu-id="8d833-250">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-250">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="8d833-251">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-251">www.contoso.com</span></span>
  - <span data-ttu-id="8d833-252">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="8d833-252">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="8d833-253">**Blockering ej matchad**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-253">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="8d833-254">Scenario: vänster jokertecken (under domän)</span><span class="sxs-lookup"><span data-stu-id="8d833-254">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="8d833-255">**Post**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="8d833-255">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="8d833-256">**Tillåt matcha** och **blockera matchning**:</span><span class="sxs-lookup"><span data-stu-id="8d833-256">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8d833-257">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-257">www.contoso.com</span></span>
  - <span data-ttu-id="8d833-258">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-258">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="8d833-259">**Tillåt ej matchat** och **Blockera ej matchade**:</span><span class="sxs-lookup"><span data-stu-id="8d833-259">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8d833-260">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-260">123contoso.com</span></span>
  - <span data-ttu-id="8d833-261">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-261">contoso.com</span></span>
  - <span data-ttu-id="8d833-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="8d833-263">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="8d833-263">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="8d833-264">Scenario: höger mönster överst i sökvägen</span><span class="sxs-lookup"><span data-stu-id="8d833-264">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="8d833-265">**Post**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="8d833-265">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="8d833-266">**Tillåt matcha** och **blockera matchning**:</span><span class="sxs-lookup"><span data-stu-id="8d833-266">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8d833-267">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="8d833-267">contoso.com/a/b</span></span>
  - <span data-ttu-id="8d833-268">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="8d833-268">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="8d833-269">contoso. com/a/? q = joe@t. com</span><span class="sxs-lookup"><span data-stu-id="8d833-269">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="8d833-270">**Tillåt ej matchat** och **Blockera ej matchade**:</span><span class="sxs-lookup"><span data-stu-id="8d833-270">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8d833-271">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-271">contoso.com</span></span>
  - <span data-ttu-id="8d833-272">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8d833-272">contoso.com/a</span></span>
  - <span data-ttu-id="8d833-273">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-273">www.contoso.com</span></span>
  - <span data-ttu-id="8d833-274">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="8d833-274">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="8d833-275">Scenario: vänster Tilde</span><span class="sxs-lookup"><span data-stu-id="8d833-275">Scenario: Left tilde</span></span>

<span data-ttu-id="8d833-276">**Post**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="8d833-276">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="8d833-277">**Tillåt matcha** och **blockera matchning**:</span><span class="sxs-lookup"><span data-stu-id="8d833-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8d833-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-278">contoso.com</span></span>
  - <span data-ttu-id="8d833-279">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-279">www.contoso.com</span></span>
  - <span data-ttu-id="8d833-280">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-280">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="8d833-281">**Tillåt ej matchat** och **Blockera ej matchade**:</span><span class="sxs-lookup"><span data-stu-id="8d833-281">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8d833-282">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-282">123contoso.com</span></span>
  - <span data-ttu-id="8d833-283">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="8d833-283">contoso.com/abc</span></span>
  - <span data-ttu-id="8d833-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="8d833-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="8d833-285">Scenario: höger jokertecken</span><span class="sxs-lookup"><span data-stu-id="8d833-285">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="8d833-286">**Post**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="8d833-286">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="8d833-287">**Tillåt matcha** och **blockera matchning**:</span><span class="sxs-lookup"><span data-stu-id="8d833-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8d833-288">contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="8d833-288">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="8d833-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8d833-289">contoso.com/a</span></span>
  - <span data-ttu-id="8d833-290">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="8d833-290">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="8d833-291">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="8d833-291">contoso.com/ab</span></span>
  - <span data-ttu-id="8d833-292">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="8d833-292">contoso.com/b</span></span>
  - <span data-ttu-id="8d833-293">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="8d833-293">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="8d833-294">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="8d833-294">contoso.com/ba</span></span>

- <span data-ttu-id="8d833-295">**Tillåt ej matchat** och **blockera icke matchade**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-295">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="8d833-296">Scenario: vänster-domän och höger jokertecken</span><span class="sxs-lookup"><span data-stu-id="8d833-296">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="8d833-297">**Post**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="8d833-297">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="8d833-298">**Tillåt matcha** och **blockera matchning**:</span><span class="sxs-lookup"><span data-stu-id="8d833-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8d833-299">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="8d833-299">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="8d833-300">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="8d833-300">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="8d833-301">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8d833-301">www.contoso.com/a</span></span>
  - <span data-ttu-id="8d833-302">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="8d833-302">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="8d833-303">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="8d833-303">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="8d833-304">**Tillåt ej matchat** och **blockera icke matchade**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="8d833-304">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="8d833-305">Scenario: vänster och höger Tilde</span><span class="sxs-lookup"><span data-stu-id="8d833-305">Scenario: Left and right tilde</span></span>

<span data-ttu-id="8d833-306">**Post**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="8d833-306">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="8d833-307">**Tillåt matcha** och **blockera matchning**:</span><span class="sxs-lookup"><span data-stu-id="8d833-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8d833-308">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-308">contoso.com</span></span>
  - <span data-ttu-id="8d833-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8d833-309">contoso.com/a</span></span>
  - <span data-ttu-id="8d833-310">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-310">www.contoso.com</span></span>
  - <span data-ttu-id="8d833-311">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="8d833-311">www.contoso.com/b</span></span>
  - <span data-ttu-id="8d833-312">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-312">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="8d833-313">**Tillåt ej matchat** och **Blockera ej matchade**:</span><span class="sxs-lookup"><span data-stu-id="8d833-313">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8d833-314">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-314">123contoso.com</span></span>
  - <span data-ttu-id="8d833-315">contoso.org</span><span class="sxs-lookup"><span data-stu-id="8d833-315">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="8d833-316">Scenario: IP-adress</span><span class="sxs-lookup"><span data-stu-id="8d833-316">Scenario: IP address</span></span>

<span data-ttu-id="8d833-317">**Post**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="8d833-317">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="8d833-318">**Tillåt matchning** och **blockering**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="8d833-318">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="8d833-319">**Tillåt ej matchat** och **Blockera ej matchade**:</span><span class="sxs-lookup"><span data-stu-id="8d833-319">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8d833-320">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="8d833-320">1.2.3.4/a</span></span>
  - <span data-ttu-id="8d833-321">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="8d833-321">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="8d833-322">IP-adress med höger jokertecken</span><span class="sxs-lookup"><span data-stu-id="8d833-322">IP address with right wildcard</span></span>

<span data-ttu-id="8d833-323">**Post**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="8d833-323">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="8d833-324">**Tillåt matcha** och **blockera matchning**:</span><span class="sxs-lookup"><span data-stu-id="8d833-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8d833-325">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="8d833-325">1.2.3.4/b</span></span>
  - <span data-ttu-id="8d833-326">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="8d833-326">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="8d833-327">Exempel på ogiltiga poster</span><span class="sxs-lookup"><span data-stu-id="8d833-327">Examples of invalid entries</span></span>

<span data-ttu-id="8d833-328">Följande poster är ogiltiga:</span><span class="sxs-lookup"><span data-stu-id="8d833-328">The following entries are invalid:</span></span>

- <span data-ttu-id="8d833-329">**Domän värden saknas eller är ogiltiga**:</span><span class="sxs-lookup"><span data-stu-id="8d833-329">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="8d833-330">contoso</span><span class="sxs-lookup"><span data-stu-id="8d833-330">contoso</span></span>
  - <span data-ttu-id="8d833-331">\*contoso.\*</span><span class="sxs-lookup"><span data-stu-id="8d833-331">\*.contoso.\*</span></span>
  - <span data-ttu-id="8d833-332">\*. com</span><span class="sxs-lookup"><span data-stu-id="8d833-332">\*.com</span></span>
  - <span data-ttu-id="8d833-333">\*. pdf</span><span class="sxs-lookup"><span data-stu-id="8d833-333">\*.pdf</span></span>

- <span data-ttu-id="8d833-334">**Jokertecken på text eller utan blank steg**:</span><span class="sxs-lookup"><span data-stu-id="8d833-334">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="8d833-335">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="8d833-335">\*contoso.com</span></span>
  - <span data-ttu-id="8d833-336">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="8d833-336">contoso.com\*</span></span>
  - <span data-ttu-id="8d833-337">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="8d833-337">\*1.2.3.4</span></span>
  - <span data-ttu-id="8d833-338">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="8d833-338">1.2.3.4\*</span></span>
  - <span data-ttu-id="8d833-339">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="8d833-339">contoso.com/a\*</span></span>
  - <span data-ttu-id="8d833-340">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="8d833-340">contoso.com/ab\*</span></span>

- <span data-ttu-id="8d833-341">**IP-adresser med portar**:</span><span class="sxs-lookup"><span data-stu-id="8d833-341">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="8d833-342">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="8d833-342">contoso.com:443</span></span>
  - <span data-ttu-id="8d833-343">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="8d833-343">abc.contoso.com:25</span></span>

- <span data-ttu-id="8d833-344">**Icke beskrivande jokertecken**:</span><span class="sxs-lookup"><span data-stu-id="8d833-344">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="8d833-345">\*.\*</span><span class="sxs-lookup"><span data-stu-id="8d833-345">\*.\*</span></span>

- <span data-ttu-id="8d833-346">**Jokertecken**:</span><span class="sxs-lookup"><span data-stu-id="8d833-346">**Middle wildcards**:</span></span>

  - <span data-ttu-id="8d833-347">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="8d833-347">conto\*so.com</span></span>
  - <span data-ttu-id="8d833-348">conto ~ så. com</span><span class="sxs-lookup"><span data-stu-id="8d833-348">conto~so.com</span></span>

- <span data-ttu-id="8d833-349">**Dubbel jokertecken**</span><span class="sxs-lookup"><span data-stu-id="8d833-349">**Double wildcards**</span></span>

  - <span data-ttu-id="8d833-350">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="8d833-350">contoso.com/\*\*</span></span>
  - <span data-ttu-id="8d833-351">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="8d833-351">contoso.com/\*/\*</span></span>
