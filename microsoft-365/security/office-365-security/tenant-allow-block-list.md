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
ms.openlocfilehash: 4bf5e2e29a9f48c434be527a2447ca4bf98c4208
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49660004"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="2f9a8-103">Hantera URL:er i Klientorganisation Tillåt / blockera listan</span><span class="sxs-lookup"><span data-stu-id="2f9a8-103">Manage URLs in the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="2f9a8-104">De funktioner som beskrivs i den här artikeln är i förhands granskning och kan ändras och är inte tillgängliga i alla organisationer.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-104">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="2f9a8-105">I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor kanske du inte kan komma att behöva filtrera EOP Verdict.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="2f9a8-106">Ett bra meddelande kan till exempel vara markerat som dåligt (ett falskt positivt) eller så tillåts ett ogiltigt meddelande genom (ett falskt negativt).</span><span class="sxs-lookup"><span data-stu-id="2f9a8-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="2f9a8-107">Med listan Tillåt/begränsa klient organisation i säkerhets & Compliance Center kan du manuellt åsidosätta Microsoft 365 filter-verdicts.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="2f9a8-108">Listan över tillåtna/blockerade innehavare används under e-postflöde och när användaren klickar på den.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="2f9a8-109">Du kan ange URL-adresser att tillåta eller blockera i listan Tillåt/blockera för klient organisation.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="2f9a8-110">I det här avsnittet beskrivs hur du konfigurerar poster i listan Tillåt/blockera i säkerhets & för kontroll av klient organisation eller i PowerShell-organisationen (Exchange Online PowerShell för Microsoft 365-organisationer med post lådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="2f9a8-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2f9a8-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="2f9a8-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2f9a8-112">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="2f9a8-113">För att gå direkt till sidan **Tillåt/blockera lista för klient organisation** , Använd <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="2f9a8-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="2f9a8-114">Tillgängliga URL-värden beskrivs i [URL-syntaxen för avsnittet Tillåt/blockera lista för klient organisation](#url-syntax-for-the-tenant-allowblock-list) längre ned i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="2f9a8-115">Listan Tillåt/blockera för klient organisationer tillåter högst 500 poster för URL: er.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="2f9a8-116">En post ska vara aktiv inom 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="2f9a8-117">Block poster har högre prioritet än Tillåt-poster.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="2f9a8-118">Poster i listan Tillåt/blockera för klient organisationer upphör som standard efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="2f9a8-119">Du kan ange ett datum eller ange att de aldrig ska upphöra att gälla.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="2f9a8-120">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2f9a8-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="2f9a8-121">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="2f9a8-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2f9a8-122">Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="2f9a8-123">För att lägga till och ta bort värden från listan över tillåtna/blockerade innehavare måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** .</span><span class="sxs-lookup"><span data-stu-id="2f9a8-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="2f9a8-124">Om du vill ha skrivskyddad åtkomst till listan Tillåt/blockera för klient organisationen måste du vara medlem i rollen **global läsare** eller **säkerhets läsare** .</span><span class="sxs-lookup"><span data-stu-id="2f9a8-124">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="2f9a8-125">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="2f9a8-125">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="2f9a8-126">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-126">**Notes**:</span></span>

  - <span data-ttu-id="2f9a8-127">Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-127">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="2f9a8-128">Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="2f9a8-128">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="2f9a8-129">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-129">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2f9a8-130">Använd säkerhets & efterlevnad för att skapa URL-poster i listan Tillåt/blockera för klient organisation</span><span class="sxs-lookup"><span data-stu-id="2f9a8-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2f9a8-131">Mer information om syntaxen för URL-poster finns i [URL-syntaxen för listan Tillåt/blockera lista för klient organisation](#url-syntax-for-the-tenant-allowblock-list) längre ned i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="2f9a8-132">Gå till fliken **Threat Management** \> **policy** för \> **Tillåt/blockera listor** i säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="2f9a8-133">På sidan **Tillåt/blockera lista för klient organisation** kontrollerar du att fliken **URL: er** är markerad och klickar sedan på **Lägg till** .</span><span class="sxs-lookup"><span data-stu-id="2f9a8-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="2f9a8-134">I **Lägg till** utfällbara URL-adresser som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="2f9a8-135">**Lägga till URL-adresser med jokertecken**: Ange en URL per rad, upp till maximalt 20.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="2f9a8-136">**Blockera/Tillåt**: Välj om du vill **tillåta** eller **blockera** angivna URL-adresser.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="2f9a8-137">**Aldrig giltig**: gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="2f9a8-138">Kontrol lera att inställningen är avstängt ![ ](../../media/scc-toggle-off.png) och ange förfallo datumet för posterna genom att använda rutan **upphör att gälla** .</span><span class="sxs-lookup"><span data-stu-id="2f9a8-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="2f9a8-139">eller</span><span class="sxs-lookup"><span data-stu-id="2f9a8-139">or</span></span>

     - <span data-ttu-id="2f9a8-140">Flytta växlings knappen till höger för att konfigurera att posterna aldrig ska förfalla:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="2f9a8-142">.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-142">.</span></span>

   - <span data-ttu-id="2f9a8-143">**Valfri anmärkning**: Ange en beskrivande text för posterna.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="2f9a8-144">När du är klar klickar du på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2f9a8-145">Använd säkerhets & Compliance Center för att visa poster i listan Tillåt/blockera för klient organisation</span><span class="sxs-lookup"><span data-stu-id="2f9a8-145">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="2f9a8-146">Gå till fliken **Threat Management** \> **policy** för \> **Tillåt/blockera listor** i säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="2f9a8-147">Välj fliken **URL: er** .</span><span class="sxs-lookup"><span data-stu-id="2f9a8-147">Select the **URLs** tab.</span></span>

<span data-ttu-id="2f9a8-148">Klicka på följande kolumn rubriker för att sortera i stigande eller fallande ordning:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-148">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="2f9a8-149">**Värde**</span><span class="sxs-lookup"><span data-stu-id="2f9a8-149">**Value**</span></span>
- <span data-ttu-id="2f9a8-150">**Åtgärd**: **blockera** eller **Tillåt**.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-150">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="2f9a8-151">**Senast uppdaterad**</span><span class="sxs-lookup"><span data-stu-id="2f9a8-151">**Last updated date**</span></span>
- <span data-ttu-id="2f9a8-152">**Utgångs datum**</span><span class="sxs-lookup"><span data-stu-id="2f9a8-152">**Expiration date**</span></span>
- <span data-ttu-id="2f9a8-153">**Fotnot**</span><span class="sxs-lookup"><span data-stu-id="2f9a8-153">**Note**</span></span>

<span data-ttu-id="2f9a8-154">Klicka på **gruppera** för att gruppera posterna **efter åtgärd** (**blockera** eller **Tillåt**) eller **ingen**.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-154">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="2f9a8-155">Klicka på **Sök**, ange hela eller delar av ett värde och tryck sedan på RETUR för att hitta ett visst värde.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-155">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="2f9a8-156">När du är klar klickar du på **Rensa sökning** ![ rensa Sök ikonen ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="2f9a8-156">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="2f9a8-157">Klicka på **filter**.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-157">Click **Filter**.</span></span> <span data-ttu-id="2f9a8-158">I det **filter** som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-158">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="2f9a8-159">**Åtgärd**: Välj **Tillåt**, **blockera** eller båda.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-159">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="2f9a8-160">**Aldrig förfaller**: Välj av ( ![ Växla av ](../../media/scc-toggle-off.png) ) eller på ( ![ växling på ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="2f9a8-160">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="2f9a8-161">**Uppdaterades senast**: Välj ett start datum (**från**), ett slutdatum (**till**) eller båda.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-161">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="2f9a8-162">**Utgångs datum**: Välj ett start datum (**från**), ett slutdatum (**till**) eller båda.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-162">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="2f9a8-163">När du är klar klickar du på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-163">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="2f9a8-164">Om du vill ta bort befintliga filter klickar du på **filter** och sedan på **Rensa filter** i det **filter** som visas.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-164">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2f9a8-165">Använd säkerhets & Compliance Center för att ändra poster i listan Tillåt/blockera för klient organisation</span><span class="sxs-lookup"><span data-stu-id="2f9a8-165">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2f9a8-166">Du kan inte ändra själva URL-värdet.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-166">You can't modify the URL value itself.</span></span> <span data-ttu-id="2f9a8-167">I stället måste du ta bort posten och skapa den igen.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-167">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="2f9a8-168">Gå till fliken **Threat Management** \> **policy** för \> **Tillåt/blockera listor** i säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="2f9a8-169">Välj fliken **URL: er** .</span><span class="sxs-lookup"><span data-stu-id="2f9a8-169">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="2f9a8-170">Markera den post som du vill ändra och klicka sedan på **Redigera** ![ redigerings ikon ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="2f9a8-170">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="2f9a8-171">I den utfällbara filen som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-171">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="2f9a8-172">**Blockera/Tillåt**: Välj **Tillåt** eller **blockera**.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-172">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="2f9a8-173">**Aldrig giltig**: gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-173">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="2f9a8-174">Kontrol lera att inställningen är avstängt ![ ](../../media/scc-toggle-off.png) och ange förfallo datumet för posten i rutan **upphör att gälla** .</span><span class="sxs-lookup"><span data-stu-id="2f9a8-174">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="2f9a8-175">eller</span><span class="sxs-lookup"><span data-stu-id="2f9a8-175">or</span></span>

     - <span data-ttu-id="2f9a8-176">Flytta växlings knappen till höger för att konfigurera posten så att den aldrig förfaller:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-176">Move the toggle to the right to configure the entry to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="2f9a8-178">.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-178">.</span></span>

   - <span data-ttu-id="2f9a8-179">**Valfri anmärkning**: Ange en beskrivande text för posten.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-179">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="2f9a8-180">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-180">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="2f9a8-181">Använd säkerhets & Compliance Center för att ta bort poster från listan Tillåt/blockera för klient organisation</span><span class="sxs-lookup"><span data-stu-id="2f9a8-181">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="2f9a8-182">Gå till fliken **Threat Management** \> **policy** för \> **Tillåt/blockera listor** i säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="2f9a8-183">Välj fliken **URL: er** .</span><span class="sxs-lookup"><span data-stu-id="2f9a8-183">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="2f9a8-184">Markera den post som du vill ta bort och klicka sedan på **ta bort** ![ ikon för borttagning ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="2f9a8-184">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="2f9a8-185">I varnings dialog rutan som visas klickar du på **ta bort**.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-185">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="2f9a8-186">Använd Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera listan Tillåt/blockera klient organisation</span><span class="sxs-lookup"><span data-stu-id="2f9a8-186">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2f9a8-187">Använd PowerShell för att lägga till poster i listan Tillåt/blockera för klient organisation</span><span class="sxs-lookup"><span data-stu-id="2f9a8-187">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2f9a8-188">Använd följande syntax för att lägga till poster i listan Tillåt/blockera i klient organisationen:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-188">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="2f9a8-189">Det här exemplet lägger till en URL-adressblock för contoso.com och alla under domäner (till exempel contoso.com, www.contoso.com och xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2f9a8-189">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="2f9a8-190">Eftersom vi inte använde parametrarna förfallo eller noexpires upphör posten efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-190">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="2f9a8-191">Detaljerad information om syntax och parametrar finns i [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="2f9a8-191">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2f9a8-192">Använda PowerShell för att visa poster i listan Tillåt/blockera i klient organisationen</span><span class="sxs-lookup"><span data-stu-id="2f9a8-192">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2f9a8-193">Om du vill visa poster i listan Tillåt/begränsa klient organisation använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-193">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="2f9a8-194">I det här exemplet returneras alla blockerade URL: er.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-194">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="2f9a8-195">Detaljerad information om syntax och parametrar finns i [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="2f9a8-195">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2f9a8-196">Använda PowerShell för att ändra poster i listan Tillåt/blockera för klient organisation</span><span class="sxs-lookup"><span data-stu-id="2f9a8-196">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2f9a8-197">Du kan inte ändra själva URL-värdet.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-197">You can't modify the URL value itself.</span></span> <span data-ttu-id="2f9a8-198">I stället måste du ta bort posten och skapa den igen.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-198">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="2f9a8-199">Om du vill ändra poster i listan Tillåt/blockera för klient organisation använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-199">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="2f9a8-200">I det här exemplet ändras utgångs datumet för den angivna posten.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-200">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="2f9a8-201">Detaljerad information om syntax och parametrar finns i [set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="2f9a8-201">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="2f9a8-202">Använd PowerShell för att ta bort poster från listan Tillåt/blockera för klient organisation</span><span class="sxs-lookup"><span data-stu-id="2f9a8-202">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="2f9a8-203">Om du vill ta bort poster från listan Tillåt/blockera klient organisation använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-203">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="2f9a8-204">I det här exemplet tas den angivna URL-posten bort från listan Tillåt/blockera för klient organisation.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-204">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="2f9a8-205">Detaljerad information om syntax och parametrar finns i [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="2f9a8-205">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="2f9a8-206">URL-syntax för listan Tillåt/blockera för klient organisation</span><span class="sxs-lookup"><span data-stu-id="2f9a8-206">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="2f9a8-207">IP4v-och IPv6-adresser är tillåtna, men TCP/UDP-portarna är inte det.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-207">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="2f9a8-208">Fil namns tillägg tillåts inte (till exempel test.pdf).</span><span class="sxs-lookup"><span data-stu-id="2f9a8-208">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="2f9a8-209">Unicode stöds inte, men punycode är.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-209">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="2f9a8-210">Värddator namn är tillåtna om följande påståenden stämmer:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-210">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="2f9a8-211">Värd namnet innehåller en punkt.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-211">The hostname contains a period.</span></span>
  - <span data-ttu-id="2f9a8-212">Det finns minst ett tecken till vänster om perioden.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-212">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="2f9a8-213">Det finns minst två tecken till höger om perioden.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-213">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="2f9a8-214">Till exempel `t.co` tillåts `.com` eller `contoso.` är inte tillåtet.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-214">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="2f9a8-215">Under Sök vägar är inte underförstådda.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-215">Subpaths are not implied.</span></span>

  <span data-ttu-id="2f9a8-216">Innehåller till exempel `contoso.com` inte `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="2f9a8-216">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="2f9a8-217">Jokertecken (\*) tillåts i följande fall:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-217">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="2f9a8-218">Ett vänster jokertecken måste följas av en punkt för att ange en under domän.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-218">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="2f9a8-219">Till exempel `*.contoso.com` tillåts; `*contoso.com` är inte tillåtet.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-219">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="2f9a8-220">Ett höger jokertecken måste följa ett snedstreck (/) för att ange en sökväg.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-220">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="2f9a8-221">Till exempel `contoso.com/*` tillåts `contoso.com*` eller `contoso.com/ab*` är inte tillåtet.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-221">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="2f9a8-222">Alla under Sök vägar underförstås inte med ett höger jokertecken.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-222">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="2f9a8-223">Innehåller till exempel `contoso.com/*` inte `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="2f9a8-223">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="2f9a8-224">`*.com*` är ogiltig (inte en matchad domän och höger jokertecken följer inte ett snedstreck).</span><span class="sxs-lookup"><span data-stu-id="2f9a8-224">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="2f9a8-225">Jokertecken tillåts inte i IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-225">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="2f9a8-226">Tilde-tecknet (~) är tillgängligt i följande fall:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-226">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="2f9a8-227">Ett Vänsterställt tildetecken innebär en domän och alla under domäner.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-227">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="2f9a8-228">Till exempel `~contoso.com` inkluderar `contoso.com` och `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="2f9a8-228">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="2f9a8-229">URL-poster som innehåller protokoll (till exempel `http://` , `https://` eller `ftp://` ) fungerar inte eftersom URL-poster gäller för alla protokoll.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-229">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="2f9a8-230">Det finns inget användar namn eller lösen ord.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-230">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="2f9a8-231">Citat tecken ("or") är ogiltiga tecken.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-231">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="2f9a8-232">En URL ska inkludera alla omdirigeringar om möjligt.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-232">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="2f9a8-233">Scenarier för URL-post</span><span class="sxs-lookup"><span data-stu-id="2f9a8-233">URL entry scenarios</span></span>

<span data-ttu-id="2f9a8-234">Giltiga URL-värden och deras resultat beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="2f9a8-234">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="2f9a8-235">Scenario: inga jokertecken</span><span class="sxs-lookup"><span data-stu-id="2f9a8-235">Scenario: No wildcards</span></span>

<span data-ttu-id="2f9a8-236">**Post**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="2f9a8-236">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="2f9a8-237">**Tillåt matchning**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-237">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="2f9a8-238">**Tillåt ej matchad**:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-238">**Allow not matched**:</span></span>

  - <span data-ttu-id="2f9a8-239">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-239">abc-contoso.com</span></span>
  - <span data-ttu-id="2f9a8-240">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2f9a8-240">contoso.com/a</span></span>
  - <span data-ttu-id="2f9a8-241">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-241">payroll.contoso.com</span></span>
  - <span data-ttu-id="2f9a8-242">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-242">test.com/contoso.com</span></span>
  - <span data-ttu-id="2f9a8-243">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-243">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="2f9a8-244">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-244">www.contoso.com</span></span>
  - <span data-ttu-id="2f9a8-245">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-245">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="2f9a8-246">**Blockera träff**:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-246">**Block match**:</span></span>

  - <span data-ttu-id="2f9a8-247">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-247">contoso.com</span></span>
  - <span data-ttu-id="2f9a8-248">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2f9a8-248">contoso.com/a</span></span>
  - <span data-ttu-id="2f9a8-249">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-249">payroll.contoso.com</span></span>
  - <span data-ttu-id="2f9a8-250">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-250">test.com/contoso.com</span></span>
  - <span data-ttu-id="2f9a8-251">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-251">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="2f9a8-252">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-252">www.contoso.com</span></span>
  - <span data-ttu-id="2f9a8-253">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-253">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="2f9a8-254">**Blockering ej matchad**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-254">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="2f9a8-255">Scenario: vänster jokertecken (under domän)</span><span class="sxs-lookup"><span data-stu-id="2f9a8-255">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="2f9a8-256">**Post**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="2f9a8-256">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="2f9a8-257">**Tillåt matcha** och **blockera matchning**:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-257">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2f9a8-258">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-258">www.contoso.com</span></span>
  - <span data-ttu-id="2f9a8-259">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-259">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="2f9a8-260">**Tillåt ej matchat** och **Blockera ej matchade**:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-260">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="2f9a8-261">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-261">123contoso.com</span></span>
  - <span data-ttu-id="2f9a8-262">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-262">contoso.com</span></span>
  - <span data-ttu-id="2f9a8-263">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-263">test.com/contoso.com</span></span>
  - <span data-ttu-id="2f9a8-264">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="2f9a8-264">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="2f9a8-265">Scenario: höger mönster överst i sökvägen</span><span class="sxs-lookup"><span data-stu-id="2f9a8-265">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="2f9a8-266">**Post**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="2f9a8-266">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="2f9a8-267">**Tillåt matcha** och **blockera matchning**:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-267">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2f9a8-268">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="2f9a8-268">contoso.com/a/b</span></span>
  - <span data-ttu-id="2f9a8-269">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="2f9a8-269">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="2f9a8-270">contoso. com/a/? q = joe@t. com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-270">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="2f9a8-271">**Tillåt ej matchat** och **Blockera ej matchade**:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-271">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="2f9a8-272">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-272">contoso.com</span></span>
  - <span data-ttu-id="2f9a8-273">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2f9a8-273">contoso.com/a</span></span>
  - <span data-ttu-id="2f9a8-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-274">www.contoso.com</span></span>
  - <span data-ttu-id="2f9a8-275">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-275">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="2f9a8-276">Scenario: vänster Tilde</span><span class="sxs-lookup"><span data-stu-id="2f9a8-276">Scenario: Left tilde</span></span>

<span data-ttu-id="2f9a8-277">**Post**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="2f9a8-277">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="2f9a8-278">**Tillåt matcha** och **blockera matchning**:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-278">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2f9a8-279">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-279">contoso.com</span></span>
  - <span data-ttu-id="2f9a8-280">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-280">www.contoso.com</span></span>
  - <span data-ttu-id="2f9a8-281">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-281">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="2f9a8-282">**Tillåt ej matchat** och **Blockera ej matchade**:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-282">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="2f9a8-283">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-283">123contoso.com</span></span>
  - <span data-ttu-id="2f9a8-284">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="2f9a8-284">contoso.com/abc</span></span>
  - <span data-ttu-id="2f9a8-285">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="2f9a8-285">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="2f9a8-286">Scenario: höger jokertecken</span><span class="sxs-lookup"><span data-stu-id="2f9a8-286">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="2f9a8-287">**Post**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="2f9a8-287">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="2f9a8-288">**Tillåt matcha** och **blockera matchning**:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-288">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2f9a8-289">contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-289">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="2f9a8-290">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2f9a8-290">contoso.com/a</span></span>
  - <span data-ttu-id="2f9a8-291">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="2f9a8-291">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="2f9a8-292">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="2f9a8-292">contoso.com/ab</span></span>
  - <span data-ttu-id="2f9a8-293">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="2f9a8-293">contoso.com/b</span></span>
  - <span data-ttu-id="2f9a8-294">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="2f9a8-294">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="2f9a8-295">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="2f9a8-295">contoso.com/ba</span></span>

- <span data-ttu-id="2f9a8-296">**Tillåt ej matchat** och **blockera icke matchade**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-296">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="2f9a8-297">Scenario: vänster-domän och höger jokertecken</span><span class="sxs-lookup"><span data-stu-id="2f9a8-297">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="2f9a8-298">**Post**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="2f9a8-298">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="2f9a8-299">**Tillåt matcha** och **blockera matchning**:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-299">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2f9a8-300">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="2f9a8-300">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="2f9a8-301">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="2f9a8-301">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="2f9a8-302">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2f9a8-302">www.contoso.com/a</span></span>
  - <span data-ttu-id="2f9a8-303">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="2f9a8-303">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="2f9a8-304">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="2f9a8-304">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="2f9a8-305">**Tillåt ej matchat** och **blockera icke matchade**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="2f9a8-305">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="2f9a8-306">Scenario: vänster och höger Tilde</span><span class="sxs-lookup"><span data-stu-id="2f9a8-306">Scenario: Left and right tilde</span></span>

<span data-ttu-id="2f9a8-307">**Post**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="2f9a8-307">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="2f9a8-308">**Tillåt matcha** och **blockera matchning**:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2f9a8-309">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-309">contoso.com</span></span>
  - <span data-ttu-id="2f9a8-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2f9a8-310">contoso.com/a</span></span>
  - <span data-ttu-id="2f9a8-311">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-311">www.contoso.com</span></span>
  - <span data-ttu-id="2f9a8-312">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="2f9a8-312">www.contoso.com/b</span></span>
  - <span data-ttu-id="2f9a8-313">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-313">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="2f9a8-314">**Tillåt ej matchat** och **Blockera ej matchade**:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-314">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="2f9a8-315">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-315">123contoso.com</span></span>
  - <span data-ttu-id="2f9a8-316">contoso.org</span><span class="sxs-lookup"><span data-stu-id="2f9a8-316">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="2f9a8-317">Scenario: IP-adress</span><span class="sxs-lookup"><span data-stu-id="2f9a8-317">Scenario: IP address</span></span>

<span data-ttu-id="2f9a8-318">**Post**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="2f9a8-318">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="2f9a8-319">**Tillåt matchning** och **blockering**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="2f9a8-319">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="2f9a8-320">**Tillåt ej matchat** och **Blockera ej matchade**:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-320">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="2f9a8-321">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="2f9a8-321">1.2.3.4/a</span></span>
  - <span data-ttu-id="2f9a8-322">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="2f9a8-322">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="2f9a8-323">IP-adress med höger jokertecken</span><span class="sxs-lookup"><span data-stu-id="2f9a8-323">IP address with right wildcard</span></span>

<span data-ttu-id="2f9a8-324">**Post**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="2f9a8-324">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="2f9a8-325">**Tillåt matcha** och **blockera matchning**:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-325">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2f9a8-326">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="2f9a8-326">1.2.3.4/b</span></span>
  - <span data-ttu-id="2f9a8-327">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="2f9a8-327">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="2f9a8-328">Exempel på ogiltiga poster</span><span class="sxs-lookup"><span data-stu-id="2f9a8-328">Examples of invalid entries</span></span>

<span data-ttu-id="2f9a8-329">Följande poster är ogiltiga:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-329">The following entries are invalid:</span></span>

- <span data-ttu-id="2f9a8-330">**Domän värden saknas eller är ogiltiga**:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-330">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="2f9a8-331">contoso</span><span class="sxs-lookup"><span data-stu-id="2f9a8-331">contoso</span></span>
  - <span data-ttu-id="2f9a8-332">\*contoso.\*</span><span class="sxs-lookup"><span data-stu-id="2f9a8-332">\*.contoso.\*</span></span>
  - <span data-ttu-id="2f9a8-333">\*. com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-333">\*.com</span></span>
  - <span data-ttu-id="2f9a8-334">\*. pdf</span><span class="sxs-lookup"><span data-stu-id="2f9a8-334">\*.pdf</span></span>

- <span data-ttu-id="2f9a8-335">**Jokertecken på text eller utan blank steg**:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-335">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="2f9a8-336">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-336">\*contoso.com</span></span>
  - <span data-ttu-id="2f9a8-337">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="2f9a8-337">contoso.com\*</span></span>
  - <span data-ttu-id="2f9a8-338">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="2f9a8-338">\*1.2.3.4</span></span>
  - <span data-ttu-id="2f9a8-339">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="2f9a8-339">1.2.3.4\*</span></span>
  - <span data-ttu-id="2f9a8-340">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="2f9a8-340">contoso.com/a\*</span></span>
  - <span data-ttu-id="2f9a8-341">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="2f9a8-341">contoso.com/ab\*</span></span>

- <span data-ttu-id="2f9a8-342">**IP-adresser med portar**:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-342">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="2f9a8-343">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="2f9a8-343">contoso.com:443</span></span>
  - <span data-ttu-id="2f9a8-344">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="2f9a8-344">abc.contoso.com:25</span></span>

- <span data-ttu-id="2f9a8-345">**Icke beskrivande jokertecken**:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-345">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="2f9a8-346">\*.\*</span><span class="sxs-lookup"><span data-stu-id="2f9a8-346">\*.\*</span></span>

- <span data-ttu-id="2f9a8-347">**Jokertecken**:</span><span class="sxs-lookup"><span data-stu-id="2f9a8-347">**Middle wildcards**:</span></span>

  - <span data-ttu-id="2f9a8-348">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-348">conto\*so.com</span></span>
  - <span data-ttu-id="2f9a8-349">conto ~ så. com</span><span class="sxs-lookup"><span data-stu-id="2f9a8-349">conto~so.com</span></span>

- <span data-ttu-id="2f9a8-350">**Dubbel jokertecken**</span><span class="sxs-lookup"><span data-stu-id="2f9a8-350">**Double wildcards**</span></span>

  - <span data-ttu-id="2f9a8-351">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="2f9a8-351">contoso.com/\*\*</span></span>
  - <span data-ttu-id="2f9a8-352">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="2f9a8-352">contoso.com/\*/\*</span></span>
