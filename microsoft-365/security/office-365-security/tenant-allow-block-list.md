---
title: Hantera tillåt och block i listan över tillåtna/blockerade klientorganisation
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratörer kan ta reda på hur de konfigurerar tillåts och block i listan över tillåtna/blockerade klienter i säkerhetsportalen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 270e38d65857de2f4d06460fb3bb77f72a165ecf
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538969"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-103">Hantera Klientorganisationens Tillåt/blockera listan</span><span class="sxs-lookup"><span data-stu-id="2d7ef-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2d7ef-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-104">**Applies to**</span></span>
- [<span data-ttu-id="2d7ef-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2d7ef-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2d7ef-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="2d7ef-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2d7ef-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2d7ef-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="2d7ef-108">Funktionerna som beskrivs i den här artikeln är förhandsversioner, kan komma att ändras och är inte tillgängliga i alla organisationer.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="2d7ef-109">Om din organisation inte har de förfalskningsfunktioner som beskrivs i den här artikeln kan du läsa mer om den äldre hanteringsupplevelsen för förfalskningsfunktioner i Hantera förfalskningsavsändare med hjälp av [förfalskningsprincip](walkthrough-spoof-intelligence-insight.md)och förfalskningsinformation i EOP.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="2d7ef-110">Du kan för **stunden inte** konfigurera tillåtna URL-adresser eller filobjekt i listan över tillåtna/blockerade klienter.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="2d7ef-111">I Microsoft 365 organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor, kanske du inte instämmer i EOP-filtrerings förlopp.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="2d7ef-112">Till exempel kan ett bra meddelande markeras som dåligt (falskt positivt) eller så kan ett felaktigt meddelande tillåtas (falskt negativt).</span><span class="sxs-lookup"><span data-stu-id="2d7ef-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="2d7ef-113">Med klientorganisationens lista över tillåtna/blockerade & säkerhets- och efterlevnadscenter får du ett sätt att manuellt åsidosätta Microsoft 365 filtrera överensstämmelser.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-113">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="2d7ef-114">Klientorganisationens lista över tillåtna/blockerade används under e-postflödet och när användaren klickar.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="2d7ef-115">Du kan ange följande typer av åsidosättningar:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="2d7ef-116">URL:er som ska blockeras.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-116">URLs to block.</span></span>
- <span data-ttu-id="2d7ef-117">Filer som ska blockeras.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-117">Files to block.</span></span>
- <span data-ttu-id="2d7ef-118">Massutskick av avsändardomäner som ska tillåtas.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-118">Bulk mail sender domains to allow.</span></span> <span data-ttu-id="2d7ef-119">Mer information om massutskick, BCL (Bulk Confidence Level) och massfiltrering efter principer för skräppost finns i Nivå för massklagomål [(BCL) i EOP.](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="2d7ef-119">For more information about bulk mail, the bulk confidence level (BCL), and bulk mail filtering by anti-spam policies, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>
- <span data-ttu-id="2d7ef-120">Förfalskningsavsändare som ska tillåta eller blockera.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-120">Spoofed senders to allow or block.</span></span> <span data-ttu-id="2d7ef-121">Om du åsidosätter blockeringen av tillåtande eller blockering av förfalskningsinformation [blir](learn-about-spoof-intelligence.md)den falska avsändaren en  manuell tillåta- eller blockeringspost som bara visas på fliken Förfalskning i innehavarlistan över tillåtna/blockerade avsändare.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-121">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="2d7ef-122">Här kan du även manuellt skapa tillåta eller blockera poster för förfalskningsavsändare innan de identifieras av förfalskningsinformation.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-122">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="2d7ef-123">Den här artikeln beskriver hur du konfigurerar poster i listan Över tillåtna/blockerade klientorganisationer i Säkerhets- och efterlevnadscenter för & eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="2d7ef-123">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2d7ef-124">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="2d7ef-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2d7ef-125">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-125">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="2d7ef-126">Använd för att gå direkt **till sidan För att tillåta/blockera** klientorganisation. <https://protection.office.com/tenantAllowBlockList></span><span class="sxs-lookup"><span data-stu-id="2d7ef-126">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="2d7ef-127">Du anger filer genom att använda hashvärdet SHA256 för filen.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-127">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="2d7ef-128">Om du vill hitta hashvärdet SHA256 för en fil i Windows kör du följande kommando i kommandotolken:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-128">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="2d7ef-129">Ett exempelvärde är `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="2d7ef-129">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="2d7ef-130">Perceptuella hash-värden (pHash) stöds inte.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-130">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="2d7ef-131">Tillgängliga URL-värden beskrivs i [URL-syntaxen för avsnittet Tillåt/blockera klientorganisation](#url-syntax-for-the-tenant-allowblock-list) senare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-131">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="2d7ef-132">Klientorganisationens lista över tillåtna/blockerade tillåter maximalt 500 poster för URL:er och 500 poster för filshashar.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-132">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="2d7ef-133">Det maximala antalet tecken för varje post är:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-133">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="2d7ef-134">Filshashar = 64</span><span class="sxs-lookup"><span data-stu-id="2d7ef-134">File hashes = 64</span></span>
  - <span data-ttu-id="2d7ef-135">URL = 250</span><span class="sxs-lookup"><span data-stu-id="2d7ef-135">URL = 250</span></span>

- <span data-ttu-id="2d7ef-136">En post ska vara aktiv inom 30 minuter.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-136">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="2d7ef-137">Som standard förfaller poster i klientorganisationens lista över tillåtna/blockerade användare efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-137">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="2d7ef-138">Du kan ange ett datum eller ange att de aldrig ska upphöra.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-138">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="2d7ef-139">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2d7ef-139">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="2d7ef-140">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="2d7ef-140">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2d7ef-141">Du måste ha tilldelats behörigheter i Exchange Online innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-141">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="2d7ef-142">**URL:er, filer och tillåt massavsändare:**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-142">**URLs, files, and allow bulk senders**:</span></span>
    - <span data-ttu-id="2d7ef-143">Om du vill lägga till och ta bort värden från klientorganisationens lista över tillåtna/blockerade användare måste du vara medlem i rollgrupperna Organisationshantering eller **Säkerhetsadministratör.** </span><span class="sxs-lookup"><span data-stu-id="2d7ef-143">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="2d7ef-144">För skrivskyddad åtkomst till listan över tillåtna/blockerade klientorganisationer måste du vara medlem i rollgrupperna **Global Reader** **eller Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-144">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="2d7ef-145">**Förfalskning**: En av följande kombinationer:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-145">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="2d7ef-146">**Organisationshantering**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-146">**Organization Management**</span></span>
    - <span data-ttu-id="2d7ef-147">**Säkerhetsadministratör** <u>och</u> **endast visa-konfiguration** **eller organisationshantering – endast visa.**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-147">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="2d7ef-148">Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="2d7ef-148">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="2d7ef-149">Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-149">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="2d7ef-150">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="2d7ef-150">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="2d7ef-151">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-151">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-152">Använd Säkerhets- & efterlevnadscenter för att skapa blockera URL-poster i klientorganisationens lista över tillåtna/blockerade adresser</span><span class="sxs-lookup"><span data-stu-id="2d7ef-152">Use the Security & Compliance Center to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="2d7ef-153">I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="2d7ef-154">På sidan **Lista över tillåtna/blockerade** klientorganisation kontrollerar du att **fliken URL:er** är markerad och klickar sedan på **Blockera**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-154">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="2d7ef-155">I den **utfällna** menyn Blockera URL:er som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-155">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="2d7ef-156">**Lägg till URL:er som ska** blockeras: Ange en URL per rad, upp till högst 20.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-156">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="2d7ef-157">Mer information om syntaxen för URL-poster finns i URL-syntaxen för avsnittet [Tillåt/blockera klientorganisation](#url-syntax-for-the-tenant-allowblock-list) längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-157">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="2d7ef-158">**Upphör aldrig** att gälla: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-158">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="2d7ef-159">Kontrollera att inställningen är inaktiverad (inaktiverad) och ange utgångsdatumet för posterna ![ ](../../media/scc-toggle-off.png) i rutan Förfaller. </span><span class="sxs-lookup"><span data-stu-id="2d7ef-159">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="2d7ef-160">eller</span><span class="sxs-lookup"><span data-stu-id="2d7ef-160">or</span></span>

     - <span data-ttu-id="2d7ef-161">Flytta reglaget till höger för att konfigurera posterna så att de aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-161">Move the toggle to the right to configure the entries to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png)<span data-ttu-id="2d7ef-163">.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-163">.</span></span>

   - <span data-ttu-id="2d7ef-164">**Valfritt:** Ange beskrivande text för posterna.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-164">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="2d7ef-165">När du är klar klickar du på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-165">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-166">Använd Säkerhets- & säkerhets- och efterlevnadscenter för att skapa blockeringsfilposter i klientorganisationens lista över tillåtna/blockerade filer</span><span class="sxs-lookup"><span data-stu-id="2d7ef-166">Use the Security & Compliance Center to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="2d7ef-167">I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="2d7ef-168">På sidan **Lista över tillåtna/blockerade** klientorganisation väljer du **fliken** Filer och klickar sedan på **Blockera**.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-168">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="2d7ef-169">I den **utfällna menyn** Lägg till filer för att blockera som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-169">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="2d7ef-170">**Lägga till filhashar:** Ange ett SHA256-hashvärde per rad, upp till högst 20.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-170">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="2d7ef-171">**Upphör aldrig** att gälla: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-171">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="2d7ef-172">Kontrollera att inställningen är inaktiverad (inaktiverad) och ange utgångsdatumet för posterna ![ ](../../media/scc-toggle-off.png) i rutan Förfaller. </span><span class="sxs-lookup"><span data-stu-id="2d7ef-172">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="2d7ef-173">eller</span><span class="sxs-lookup"><span data-stu-id="2d7ef-173">or</span></span>

     - <span data-ttu-id="2d7ef-174">Flytta reglaget till höger för att konfigurera posterna så att de aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-174">Move the toggle to the right to configure the entries to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png)<span data-ttu-id="2d7ef-176">.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-176">.</span></span>

   - <span data-ttu-id="2d7ef-177">**Valfritt:** Ange beskrivande text för posterna.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-177">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="2d7ef-178">När du är klar klickar du på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-178">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-179">Använd Säkerhets- & säkerhets- och efterlevnadscenter för att skapa domänposter för massutskick av avsändare i listan Över tillåtna/blockerade klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="2d7ef-179">Use the Security & Compliance Center to create allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="2d7ef-180">I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-180">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="2d7ef-181">På sidan **Lista över tillåtna/blockerade klienter** väljer du avsändardomänerna för **BCL-förbikopplingsfliken** och klickar sedan på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-181">On the **Tenant Allow/Block List** page, select the **Sender domains for BCL bypass** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="2d7ef-182">Konfigurera följande **inställningar i den utfällklara menyn** Lägg till avsändardomän för BCL som visas:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-182">In the **Add sender domain for BCL bypass** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="2d7ef-183">**Lägga till avsändardomäner för** BCL-förbikoppling: Ange en källdomän för bra massutskick per rad, upp till högst 20.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-183">**Add sender domains for BCL bypass**: Enter one source domain of good bulk mail per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="2d7ef-184">**Upphör aldrig** att gälla: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-184">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="2d7ef-185">Kontrollera att inställningen är inaktiverad (inaktiverad) och ange utgångsdatumet för posterna ![ ](../../media/scc-toggle-off.png) i rutan Förfaller. </span><span class="sxs-lookup"><span data-stu-id="2d7ef-185">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="2d7ef-186">eller</span><span class="sxs-lookup"><span data-stu-id="2d7ef-186">or</span></span>

     - <span data-ttu-id="2d7ef-187">Flytta reglaget till höger för att konfigurera posterna så att de aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-187">Move the toggle to the right to configure the entries to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png)<span data-ttu-id="2d7ef-189">.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-189">.</span></span>

4. <span data-ttu-id="2d7ef-190">När du är klar klickar du på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-190">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-191">Använd Säkerhets- & säkerhets- och efterlevnadscenter för att skapa tillåta eller blockera förfalskning av avsändare i listan Tillåt/blockera klientorganisation</span><span class="sxs-lookup"><span data-stu-id="2d7ef-191">Use the Security & Compliance Center to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2d7ef-192">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-192">**Notes**:</span></span>

- <span data-ttu-id="2d7ef-193">Endast kombinationen _av_ den förfalskningsanvändaren och avsändarinfrastrukturen som definierats i domänparet är specifikt tillåten eller blockerad från förfalskning. </span><span class="sxs-lookup"><span data-stu-id="2d7ef-193">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="2d7ef-194">När du konfigurerar en tillåta- eller blockeringspost för ett domänpar visas inte längre meddelanden från det domänparet i förfalskningsinformation.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-194">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="2d7ef-195">Poster för falska avsändare upphör aldrig att gälla.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-195">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="2d7ef-196">I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="2d7ef-197">Välj **fliken Förfalskning på sidan Lista** över tillåtna/blockerade **klientorganisation** och klicka sedan på Lägg **till.**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-197">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="2d7ef-198">I den **utfällna menyn** Lägg till ny domänpar som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-198">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="2d7ef-199">**Lägga till nya domänpar med jokertecken:** Ange ett domänpar per rad, upp till maximalt 20.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-199">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="2d7ef-200">Mer information om syntaxen för falska avsändarposter finns i syntaxen för domänpar för posterna för falska avsändare i avsnittet [Tillåt/blockera](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) lista för klientorganisation längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-200">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="2d7ef-201">**Förfalskningstyp:** Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-201">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="2d7ef-202">**Internt**: Förfalskningsavsändare finns i en domän som tillhör din organisation (en [godkänd domän).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="2d7ef-202">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="2d7ef-203">**Extern:** Den falska avsändaren finns i en extern domän.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-203">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="2d7ef-204">**Åtgärd:** Välj **Tillåt** eller **Blockera**.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-204">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="2d7ef-205">När du är klar klickar du på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-205">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-206">Använd Säkerhets- & kompatibilitetscenter för att visa poster i listan över tillåtna/blockerade klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="2d7ef-206">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="2d7ef-207">I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-207">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="2d7ef-208">Välj den flik du vill använda.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-208">Select the tab you want.</span></span> <span data-ttu-id="2d7ef-209">Vilka kolumner som är tillgängliga beror på vilken flik du valde:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-209">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="2d7ef-210">**URL:er:**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-210">**URLs**:</span></span>
     - <span data-ttu-id="2d7ef-211">**Värde:** URL:en.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-211">**Value**: The URL.</span></span>
     - <span data-ttu-id="2d7ef-212">**Åtgärd:** **Värdeblocket**.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-212">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="2d7ef-213">**Datum för senaste uppdatering**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-213">**Last updated date**</span></span>
     - <span data-ttu-id="2d7ef-214">**Förfallodatum**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-214">**Expiration date**</span></span>
     - <span data-ttu-id="2d7ef-215">**Obs!**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-215">**Note**</span></span>

   - <span data-ttu-id="2d7ef-216">**Filer**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-216">**Files**</span></span>
     - <span data-ttu-id="2d7ef-217">**Värde:** Filens hash-kod.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-217">**Value**: The file hash.</span></span>
     - <span data-ttu-id="2d7ef-218">**Åtgärd:** **Värdeblocket**.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-218">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="2d7ef-219">**Datum för senaste uppdatering**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-219">**Last updated date**</span></span>
     - <span data-ttu-id="2d7ef-220">**Förfallodatum**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-220">**Expiration date**</span></span>
     - <span data-ttu-id="2d7ef-221">**Obs!**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-221">**Note**</span></span>

   - <span data-ttu-id="2d7ef-222">**Sender domains for BCL bypass**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-222">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="2d7ef-223">**Värde:** Avsändardomänen för massutskick.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-223">**Value**: The bulk mail sender's domain.</span></span>
     - <span data-ttu-id="2d7ef-224">**Datum för senaste uppdatering**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-224">**Last updated date**</span></span>
     - <span data-ttu-id="2d7ef-225">**Förfallodatum**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-225">**Expiration date**</span></span>

   - <span data-ttu-id="2d7ef-226">**Förfalskning**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-226">**Spoofing**</span></span>
     - <span data-ttu-id="2d7ef-227">**Spoofed användare**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-227">**Spoofed user**</span></span>
     - <span data-ttu-id="2d7ef-228">**Skicka infrastruktur**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-228">**Sending infrastructure**</span></span>
     - <span data-ttu-id="2d7ef-229">**Förfalskningstyp:** värdet **Internt eller** **Externt**.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-229">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="2d7ef-230">**Åtgärd:** **Värdeblockering** eller **Tillåt**.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-230">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="2d7ef-231">Du kan klicka på en kolumnrubrik om du vill sortera i stigande eller fallande ordning.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-231">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="2d7ef-232">Du kan gruppera **resultatet genom** att klicka på Gruppera.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-232">You can click **Group** to group the results.</span></span> <span data-ttu-id="2d7ef-233">Vilka värden som är tillgängliga beror på vilken flik du valde:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-233">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="2d7ef-234">**URL:er:** Du kan gruppera resultatet efter **åtgärd.**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-234">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="2d7ef-235">**Filer:** Du kan gruppera resultatet efter **åtgärd.**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-235">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="2d7ef-236">**Avsändardomäner för BCL-förbikoppling:** **Gruppen** är inte tillgänglig på den här fliken.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-236">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="2d7ef-237">**Förfalskning:** Du kan gruppera resultaten efter **Åtgärds-** **eller förfalskningstyp.**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-237">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="2d7ef-238">Klicka **på** Sök , ange hela eller en del av ett värde och tryck sedan på RETUR för att hitta ett visst värde.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-238">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="2d7ef-239">När du är klar klickar du på **Rensa sökning Ikonen** Rensa ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) sökning.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-239">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="2d7ef-240">Filtrera **resultatet genom** att klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-240">Click **Filter** to filter the results.</span></span> <span data-ttu-id="2d7ef-241">Vilka värden som är tillgängliga **i den utfällade** filterflik som visas beror på vilken flik du valde:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-241">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="2d7ef-242">**URL:er**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-242">**URLs**</span></span>
     - <span data-ttu-id="2d7ef-243">**Åtgärd**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-243">**Action**</span></span>
     - <span data-ttu-id="2d7ef-244">**Upphör aldrig att gälla**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-244">**Never expire**</span></span>
     - <span data-ttu-id="2d7ef-245">**Datum för senaste uppdatering**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-245">**Last updated date**</span></span>
     - <span data-ttu-id="2d7ef-246">**Förfallodatum**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-246">**Expiration date**</span></span>

   - <span data-ttu-id="2d7ef-247">**Filer**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-247">**Files**</span></span>
     - <span data-ttu-id="2d7ef-248">**Åtgärd**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-248">**Action**</span></span>
     - <span data-ttu-id="2d7ef-249">**Upphör aldrig att gälla**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-249">**Never expire**</span></span>
     - <span data-ttu-id="2d7ef-250">**Datum för senaste uppdatering**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-250">**Last updated date**</span></span>
     - <span data-ttu-id="2d7ef-251">**Förfallodatum**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-251">**Expiration date**</span></span>

   - <span data-ttu-id="2d7ef-252">**Sender domains for BCL bypass**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-252">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="2d7ef-253">**Upphör aldrig att gälla**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-253">**Never expire**</span></span>
     - <span data-ttu-id="2d7ef-254">**Datum för senaste uppdatering**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-254">**Last updated date**</span></span>
     - <span data-ttu-id="2d7ef-255">**Förfallodatum**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-255">**Expiration date**</span></span>

   - <span data-ttu-id="2d7ef-256">**Förfalskning**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-256">**Spoofing**</span></span>
     - <span data-ttu-id="2d7ef-257">**Åtgärd**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-257">**Action**</span></span>
     - <span data-ttu-id="2d7ef-258">**Förfalskningstyp**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-258">**Spoof type**</span></span>

   <span data-ttu-id="2d7ef-259">När du är klar klickar du på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-259">When you're finished, click **Apply**.</span></span> <span data-ttu-id="2d7ef-260">Om du vill ta bort befintliga  **filter klickar** du på Filter och sedan på Rensa filter i den **utfällklara filterfällan som visas.**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-260">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-261">Använd Säkerhets- & säkerhets- och efterlevnadscenter för att ändra poster i listan över tillåtna/blockerade klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="2d7ef-261">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="2d7ef-262">I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-262">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="2d7ef-263">Välj den flik som innehåller den typ av post som du vill ändra:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-263">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="2d7ef-264">**URL:er**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-264">**URLs**</span></span>
   - <span data-ttu-id="2d7ef-265">**Filer**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-265">**Files**</span></span>
   - <span data-ttu-id="2d7ef-266">**Sender domains for BCL bypass**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-266">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="2d7ef-267">**Förfalskning**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-267">**Spoofing**</span></span>

3. <span data-ttu-id="2d7ef-268">Markera den post som du vill  ändra och klicka sedan på redigera ![ redigeringsikonen ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="2d7ef-268">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="2d7ef-269">Vilka värden som du kan ändra i den utfäll plats som visas beror på vilken flik du valde i föregående steg:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-269">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="2d7ef-270">**URL:er**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-270">**URLs**</span></span>
     - <span data-ttu-id="2d7ef-271">**Upphör aldrig att** gälla och/eller förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-271">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="2d7ef-272">**Valfri anteckning**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-272">**Optional note**</span></span>

   - <span data-ttu-id="2d7ef-273">**Filer**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-273">**Files**</span></span>
     - <span data-ttu-id="2d7ef-274">**Upphör aldrig att** gälla och/eller förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-274">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="2d7ef-275">**Valfri anteckning**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-275">**Optional note**</span></span>

   - <span data-ttu-id="2d7ef-276">**Sender domains for BCL bypass**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-276">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="2d7ef-277">**Upphör aldrig att** gälla och/eller förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-277">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="2d7ef-278">**Förfalskning**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-278">**Spoofing**</span></span>
     - <span data-ttu-id="2d7ef-279">**Åtgärd:** Du kan ändra värdet till **Tillåt** eller **Blockera.**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-279">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="2d7ef-280">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-280">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-281">Använda Säkerhets- & säkerhets- och efterlevnadscenter för att ta bort poster från listan över tillåtna/blockerade klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="2d7ef-281">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="2d7ef-282">I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-282">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="2d7ef-283">Välj den flik som innehåller den typ av post som du vill ta bort:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-283">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="2d7ef-284">**URL:er**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-284">**URLs**</span></span>
   - <span data-ttu-id="2d7ef-285">**Filer**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-285">**Files**</span></span>
   - <span data-ttu-id="2d7ef-286">**Sender domains for BCL bypass**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-286">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="2d7ef-287">**Förfalskning**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-287">**Spoofing**</span></span>

3. <span data-ttu-id="2d7ef-288">Markera den post som du vill ta bort och klicka sedan på ikonen **Ta** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) bort.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-288">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="2d7ef-289">Klicka på Ta bort i varningsdialogrutan som **visas.**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-289">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-290">Använd Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera innehavarlistan över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="2d7ef-290">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-291">Använda PowerShell för att lägga till blockeringsfiler eller URL-poster i klientorganisationens lista över tillåtna/blockerade adresser</span><span class="sxs-lookup"><span data-stu-id="2d7ef-291">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="2d7ef-292">Använd följande syntax för att lägga till blockeringsfiler eller URL-poster i klientorganisationens lista över tillåtna/blockerade adresser:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-292">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="2d7ef-293">I det här exemplet läggs en post för blockering av filer till för de angivna filerna som aldrig förfaller.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-293">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="2d7ef-294">I det här exemplet läggs en blockerings-URL-post till för contoso.com och alla underdomäner (till exempel contoso.com, www.contoso.com och xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2d7ef-294">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="2d7ef-295">Eftersom vi inte använder parametrarna Förfallodatum eller NoExpiration upphör posten att gälla efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-295">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="2d7ef-296">Detaljerad information om syntax och parametrar finns i [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="2d7ef-296">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-bulk-mail-sender-domain-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-297">Använda PowerShell för att lägga till domänposter för massutskick av avsändare i listan Över tillåtna/blockerade klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="2d7ef-297">Use PowerShell to add allow bulk mail sender domain entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="2d7ef-298">Om du vill lägga till domänposterna tillåt massutskick av avsändare i listan Tillåt/blockera klientorganisation använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-298">To add allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType BulkSender -Block:$false -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="2d7ef-299">I det här exemplet läggs en post för tillåtna massavsändare till för den angivna domänen som aldrig förfaller.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-299">This example adds an allowed bulk sender entry for the specified domain that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType BulkSender -Block:$false -Entries contosodailydeals.com
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="2d7ef-300">Detaljerad information om syntax och parametrar finns i [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="2d7ef-300">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-301">Använd PowerShell för att lägga till posterna tillåta eller blockera förfalskning av avsändare i klientorganisationens lista över tillåtna/blockerade avsändare</span><span class="sxs-lookup"><span data-stu-id="2d7ef-301">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="2d7ef-302">Om du vill lägga till förfalskningsposter från klientorganisationens lista över tillåtna/blockerade avsändare använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-302">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="2d7ef-303">Detaljerad information om syntax och parametrar finns i [New-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/new-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="2d7ef-303">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-304">Använda PowerShell för att visa blockera fil- eller URL-poster i klientorganisationens lista över tillåtna/blockerade adresser</span><span class="sxs-lookup"><span data-stu-id="2d7ef-304">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2d7ef-305">Om du vill visa blockeringsfil- eller URL-poster i klientorganisationens lista över tillåtna/blockerade adresser använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-305">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="2d7ef-306">Det här exemplet returnerar information om det angivna hash-värdet för filen.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-306">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="2d7ef-307">I det här exemplet returneras alla blockerade URL-adresser.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-307">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="2d7ef-308">Detaljerad information om syntax och parametrar finns i [Get-TenantAllowBlockListItems.](/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="2d7ef-308">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-309">Använda PowerShell för att visa tillåta domänposter för massutskick av avsändare i listan Över tillåtna/blockerade klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="2d7ef-309">Use PowerShell to view allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2d7ef-310">Om du vill visa tillåt domänposter för massutskick av avsändare i listan Tillåt/blockera klientorganisation använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-310">To view allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender [-Entry <BulkSenderDomainValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="2d7ef-311">Det här exemplet returnerar alla tillåtna domäner för massutskick.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-311">This example returns all allowed bulk mail sender domains.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender
```

<span data-ttu-id="2d7ef-312">Det här exemplet returnerar information om den angivna domänen för massavsändare.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-312">This example returns information for the specified bulk sender domain.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "contosodailydeals.com"
```

<span data-ttu-id="2d7ef-313">Detaljerad information om syntax och parametrar finns i [Get-TenantAllowBlockListItems.](/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="2d7ef-313">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-314">Använda PowerShell för att visa tillåta eller blockera förfalskning av avsändare i klientorganisationens lista över tillåtna/blockerade avsändare</span><span class="sxs-lookup"><span data-stu-id="2d7ef-314">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2d7ef-315">Använd följande syntax för att visa falska avsändarposter i listan Tillåt/blockera klientorganisation:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-315">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="2d7ef-316">Det här exemplet returnerar alla falska avsändarposter i listan över tillåtna/blockerade klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-316">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="2d7ef-317">Det här exemplet returnerar alla interna poster med tillåta förfalskning.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-317">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="2d7ef-318">Det här exemplet returnerar alla externa poster för spärrade avsändare.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-318">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="2d7ef-319">Detaljerad information om syntax och parametrar finns i [Get-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/get-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="2d7ef-319">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-320">Använda PowerShell för att ändra blockeringsfiler och URL-poster i klientorganisationens lista över tillåtna/blockerade adresser</span><span class="sxs-lookup"><span data-stu-id="2d7ef-320">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2d7ef-321">Använd följande syntax för att ändra blockeringsfiler och URL-poster i klientorganisationens lista över tillåtna/blockerade adresser:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-321">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="2d7ef-322">I det här exemplet ändras förfallodatumet för den angivna blockerings-URL-posten.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-322">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="2d7ef-323">Detaljerad information om syntax och parametrar finns i [Set-TenantAllowBlockListItems.](/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="2d7ef-323">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-324">Använda PowerShell för att ändra tillåta domänposter för massutskick av avsändare i listan Tillåt/Blockera klientorganisation</span><span class="sxs-lookup"><span data-stu-id="2d7ef-324">Use PowerShell to modify allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2d7ef-325">Om du vill ändra tillåta domänposter för massutskick av avsändare i listan Tillåt/blockera klientorganisation använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-325">To modify allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="2d7ef-326">I det här exemplet ändras förfallotiden för angiven domänpost för massutskick av avsändare så att den aldrig upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-326">This example changes the expiration of the specified allow bulk mail sender domain entry to never expire.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType BulkSender -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -NoExpiration
```

<span data-ttu-id="2d7ef-327">Detaljerad information om syntax och parametrar finns i [Get-TenantAllowBlockListItems.](/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="2d7ef-327">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-328">Använda PowerShell för att ändra posterna för tillåta eller blockera förfalskning av avsändare i listan över tillåtna/blockerade klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="2d7ef-328">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2d7ef-329">Om du vill ändra tillåta eller blockera förfalskning av avsändare i listan över tillåtna eller blockerade avsändare använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-329">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="2d7ef-330">I det här exemplet ändras en förfalskningspost från tillåts till blockering.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-330">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="2d7ef-331">Detaljerad information om syntax och parametrar finns i [Set-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/set-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="2d7ef-331">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-bulk-mail-sender-domain-file-and-domain-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-332">Använda PowerShell för att ta bort domän-, fil- och domänposter för massutskick från klientorganisationens lista över tillåtna/blockerade avsändare</span><span class="sxs-lookup"><span data-stu-id="2d7ef-332">Use PowerShell to remove bulk mail sender domain, file, and domain entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="2d7ef-333">Om du vill ta bort tillåta domänposter för massutskick, blockera filposter och blockera URL-poster från klientorganisationens lista över tillåtna/blockerade avsändare använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-333">To remove allow bulk mail sender domain entries, block file entries, and block URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <BulkSender | FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="2d7ef-334">Det här exemplet tar bort den angivna blockerings-URL-posten från klientorganisationens lista över tillåtna/blockerade adresser.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-334">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="2d7ef-335">Detaljerad information om syntax och parametrar finns i [Remove-TenantAllowBlockListItems.](/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="2d7ef-335">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-336">Använda PowerShell för att ta bort tillåta eller blockera förfalskning av avsändare från klientorganisationens lista över tillåtna/blockerade avsändare</span><span class="sxs-lookup"><span data-stu-id="2d7ef-336">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="2d7ef-337">Om du vill ta bort tillåta eller blockera förfalskning av avsändare från klientorganisationens lista över tillåtna/blockerade avsändare använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-337">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="2d7ef-338">Detaljerad information om syntax och parametrar finns i [Remove-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="2d7ef-338">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-339">URL-syntax för klientorganisationens lista över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="2d7ef-339">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="2d7ef-340">IP4v- och IPv6-adresser är tillåtna, men INTE TCP-/UDP-portar.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-340">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="2d7ef-341">Filnamnstillägg är inte tillåtna (till exempel test.pdf).</span><span class="sxs-lookup"><span data-stu-id="2d7ef-341">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="2d7ef-342">Unicode stöds inte, men punycode stöds.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-342">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="2d7ef-343">Hostnames tillåts om alla följande uttryck är sanna:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-343">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="2d7ef-344">Värdnamnet innehåller en punkt.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-344">The hostname contains a period.</span></span>
  - <span data-ttu-id="2d7ef-345">Det finns minst ett tecken till vänster om perioden.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-345">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="2d7ef-346">Det finns minst två tecken till höger om perioden.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-346">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="2d7ef-347">Till exempel är `t.co` tillåtet eller `.com` inte `contoso.` tillåtet.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-347">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="2d7ef-348">Undervägar är inte underförstådda.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-348">Subpaths are not implied.</span></span>

  <span data-ttu-id="2d7ef-349">Exempelvis `contoso.com` ingår inte `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="2d7ef-349">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="2d7ef-350">Jokertecken (\*) tillåts i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-350">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="2d7ef-351">Ett vänster jokertecken måste följas av en punkt för att ange en underdomän.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-351">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="2d7ef-352">Är till exempel `*.contoso.com` tillåtet, `*contoso.com` är inte tillåtet.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-352">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="2d7ef-353">Ett höger jokertecken måste följa ett snedstreck (/) om du vill ange en sökväg.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-353">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="2d7ef-354">Till exempel är `contoso.com/*` tillåtet eller `contoso.com*` inte `contoso.com/ab*` tillåtet.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-354">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="2d7ef-355">Alla undervägar kan inte underförstådas med ett rätt jokertecken.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-355">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="2d7ef-356">Exempelvis `contoso.com/*` ingår inte `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="2d7ef-356">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="2d7ef-357">`*.com*` är ogiltig (inte en lösbar domän och att rätt jokertecken inte följer ett snedstreck).</span><span class="sxs-lookup"><span data-stu-id="2d7ef-357">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="2d7ef-358">Jokertecken tillåts inte i IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-358">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="2d7ef-359">Tecknet tilde (~) är tillgängligt i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-359">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="2d7ef-360">Ett vänster tilde-namn antyder en domän och alla underdomäner.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-360">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="2d7ef-361">Exempel: `~contoso.com` inkluderar `contoso.com` och `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="2d7ef-361">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="2d7ef-362">URL-poster som innehåller protokoll (till exempel , eller ) kommer att `http://` `https://` `ftp://` misslyckas, eftersom URL-poster tillämpas på alla protokoll.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-362">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="2d7ef-363">Ett användarnamn eller lösenord stöds inte eller krävs inte.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-363">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="2d7ef-364">Citattecken (' eller ") är ogiltiga tecken.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-364">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="2d7ef-365">En URL bör innehålla alla omdirigeringar där det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-365">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="2d7ef-366">URL-inmatningsscenarier</span><span class="sxs-lookup"><span data-stu-id="2d7ef-366">URL entry scenarios</span></span>

<span data-ttu-id="2d7ef-367">Giltiga URL-poster och deras resultat beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-367">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="2d7ef-368">Scenario: Inga jokertecken</span><span class="sxs-lookup"><span data-stu-id="2d7ef-368">Scenario: No wildcards</span></span>

<span data-ttu-id="2d7ef-369">**Post:**`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="2d7ef-369">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="2d7ef-370">**Tillåt matchning:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-370">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="2d7ef-371">**Tillåt ej matchad:**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-371">**Allow not matched**:</span></span>

  - <span data-ttu-id="2d7ef-372">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-372">abc-contoso.com</span></span>
  - <span data-ttu-id="2d7ef-373">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2d7ef-373">contoso.com/a</span></span>
  - <span data-ttu-id="2d7ef-374">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-374">payroll.contoso.com</span></span>
  - <span data-ttu-id="2d7ef-375">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-375">test.com/contoso.com</span></span>
  - <span data-ttu-id="2d7ef-376">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-376">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="2d7ef-377">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-377">www.contoso.com</span></span>
  - <span data-ttu-id="2d7ef-378">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-378">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="2d7ef-379">**Blockmatchning:**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-379">**Block match**:</span></span>

  - <span data-ttu-id="2d7ef-380">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-380">contoso.com</span></span>
  - <span data-ttu-id="2d7ef-381">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2d7ef-381">contoso.com/a</span></span>
  - <span data-ttu-id="2d7ef-382">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-382">payroll.contoso.com</span></span>
  - <span data-ttu-id="2d7ef-383">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-383">test.com/contoso.com</span></span>
  - <span data-ttu-id="2d7ef-384">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-384">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="2d7ef-385">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-385">www.contoso.com</span></span>
  - <span data-ttu-id="2d7ef-386">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-386">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="2d7ef-387">**Blockera matchas inte:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-387">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="2d7ef-388">Scenario: Vänster jokertecken (underdomän)</span><span class="sxs-lookup"><span data-stu-id="2d7ef-388">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="2d7ef-389">**Post:**`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="2d7ef-389">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="2d7ef-390">**Tillåt matchning** och **Blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2d7ef-391">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-391">www.contoso.com</span></span>
  - <span data-ttu-id="2d7ef-392">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-392">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="2d7ef-393">**Tillåt ej matchad** och **Blockera ej matchad:**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-393">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="2d7ef-394">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-394">123contoso.com</span></span>
  - <span data-ttu-id="2d7ef-395">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-395">contoso.com</span></span>
  - <span data-ttu-id="2d7ef-396">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-396">test.com/contoso.com</span></span>
  - <span data-ttu-id="2d7ef-397">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="2d7ef-397">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="2d7ef-398">Scenario: Höger jokertecken högst upp i sökvägen</span><span class="sxs-lookup"><span data-stu-id="2d7ef-398">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="2d7ef-399">**Post:**`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="2d7ef-399">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="2d7ef-400">**Tillåt matchning** och **Blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-400">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2d7ef-401">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="2d7ef-401">contoso.com/a/b</span></span>
  - <span data-ttu-id="2d7ef-402">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="2d7ef-402">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="2d7ef-403">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-403">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="2d7ef-404">**Tillåt ej matchad** och **Blockera ej matchad:**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-404">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="2d7ef-405">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-405">contoso.com</span></span>
  - <span data-ttu-id="2d7ef-406">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2d7ef-406">contoso.com/a</span></span>
  - <span data-ttu-id="2d7ef-407">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-407">www.contoso.com</span></span>
  - <span data-ttu-id="2d7ef-408">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-408">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="2d7ef-409">Scenario: Vänster tilde</span><span class="sxs-lookup"><span data-stu-id="2d7ef-409">Scenario: Left tilde</span></span>

<span data-ttu-id="2d7ef-410">**Post:**`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="2d7ef-410">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="2d7ef-411">**Tillåt matchning** och **Blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-411">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2d7ef-412">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-412">contoso.com</span></span>
  - <span data-ttu-id="2d7ef-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-413">www.contoso.com</span></span>
  - <span data-ttu-id="2d7ef-414">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-414">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="2d7ef-415">**Tillåt ej matchad** och **Blockera ej matchad:**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-415">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="2d7ef-416">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-416">123contoso.com</span></span>
  - <span data-ttu-id="2d7ef-417">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="2d7ef-417">contoso.com/abc</span></span>
  - <span data-ttu-id="2d7ef-418">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="2d7ef-418">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="2d7ef-419">Scenario: Höger suffix för jokertecken</span><span class="sxs-lookup"><span data-stu-id="2d7ef-419">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="2d7ef-420">**Post:**`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="2d7ef-420">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="2d7ef-421">**Tillåt matchning** och **Blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-421">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2d7ef-422">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-422">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="2d7ef-423">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2d7ef-423">contoso.com/a</span></span>
  - <span data-ttu-id="2d7ef-424">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="2d7ef-424">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="2d7ef-425">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="2d7ef-425">contoso.com/ab</span></span>
  - <span data-ttu-id="2d7ef-426">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="2d7ef-426">contoso.com/b</span></span>
  - <span data-ttu-id="2d7ef-427">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="2d7ef-427">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="2d7ef-428">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="2d7ef-428">contoso.com/ba</span></span>

- <span data-ttu-id="2d7ef-429">**Tillåt ej matchad** och **Blockera ej matchad**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-429">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="2d7ef-430">Scenario: Vänster underdomän med jokertecken och höger suffix för jokertecken</span><span class="sxs-lookup"><span data-stu-id="2d7ef-430">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="2d7ef-431">**Post:**`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="2d7ef-431">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="2d7ef-432">**Tillåt matchning** och **Blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-432">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2d7ef-433">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="2d7ef-433">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="2d7ef-434">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="2d7ef-434">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="2d7ef-435">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2d7ef-435">www.contoso.com/a</span></span>
  - <span data-ttu-id="2d7ef-436">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="2d7ef-436">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="2d7ef-437">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="2d7ef-437">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="2d7ef-438">**Tillåt ej matchad** och **Blockera ej matchad**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="2d7ef-438">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="2d7ef-439">Scenario: Vänster och höger tilde</span><span class="sxs-lookup"><span data-stu-id="2d7ef-439">Scenario: Left and right tilde</span></span>

<span data-ttu-id="2d7ef-440">**Post:**`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="2d7ef-440">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="2d7ef-441">**Tillåt matchning** och **Blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-441">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2d7ef-442">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-442">contoso.com</span></span>
  - <span data-ttu-id="2d7ef-443">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2d7ef-443">contoso.com/a</span></span>
  - <span data-ttu-id="2d7ef-444">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-444">www.contoso.com</span></span>
  - <span data-ttu-id="2d7ef-445">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="2d7ef-445">www.contoso.com/b</span></span>
  - <span data-ttu-id="2d7ef-446">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-446">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="2d7ef-447">**Tillåt ej matchad** och **Blockera ej matchad:**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-447">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="2d7ef-448">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-448">123contoso.com</span></span>
  - <span data-ttu-id="2d7ef-449">contoso.org</span><span class="sxs-lookup"><span data-stu-id="2d7ef-449">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="2d7ef-450">Scenario: IP-adress</span><span class="sxs-lookup"><span data-stu-id="2d7ef-450">Scenario: IP address</span></span>

<span data-ttu-id="2d7ef-451">**Post:**`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="2d7ef-451">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="2d7ef-452">**Tillåt matchning** och **Blockeringsmatchning**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="2d7ef-452">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="2d7ef-453">**Tillåt ej matchad** och **Blockera ej matchad:**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-453">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="2d7ef-454">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="2d7ef-454">1.2.3.4/a</span></span>
  - <span data-ttu-id="2d7ef-455">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="2d7ef-455">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="2d7ef-456">IP-adress med rätt jokertecken</span><span class="sxs-lookup"><span data-stu-id="2d7ef-456">IP address with right wildcard</span></span>

<span data-ttu-id="2d7ef-457">**Post:**`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="2d7ef-457">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="2d7ef-458">**Tillåt matchning** och **Blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-458">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2d7ef-459">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="2d7ef-459">1.2.3.4/b</span></span>
  - <span data-ttu-id="2d7ef-460">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="2d7ef-460">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="2d7ef-461">Exempel på ogiltiga poster</span><span class="sxs-lookup"><span data-stu-id="2d7ef-461">Examples of invalid entries</span></span>

<span data-ttu-id="2d7ef-462">Följande poster är ogiltiga:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-462">The following entries are invalid:</span></span>

- <span data-ttu-id="2d7ef-463">**Värden som saknas eller är ogiltiga:**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-463">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="2d7ef-464">contoso</span><span class="sxs-lookup"><span data-stu-id="2d7ef-464">contoso</span></span>
  - <span data-ttu-id="2d7ef-465">\*CONTOSO.\*</span><span class="sxs-lookup"><span data-stu-id="2d7ef-465">\*.contoso.\*</span></span>
  - <span data-ttu-id="2d7ef-466">\*.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-466">\*.com</span></span>
  - <span data-ttu-id="2d7ef-467">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="2d7ef-467">\*.pdf</span></span>

- <span data-ttu-id="2d7ef-468">**Jokertecken på text eller utan avståndstecken:**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-468">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="2d7ef-469">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-469">\*contoso.com</span></span>
  - <span data-ttu-id="2d7ef-470">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="2d7ef-470">contoso.com\*</span></span>
  - <span data-ttu-id="2d7ef-471">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="2d7ef-471">\*1.2.3.4</span></span>
  - <span data-ttu-id="2d7ef-472">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="2d7ef-472">1.2.3.4\*</span></span>
  - <span data-ttu-id="2d7ef-473">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="2d7ef-473">contoso.com/a\*</span></span>
  - <span data-ttu-id="2d7ef-474">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="2d7ef-474">contoso.com/ab\*</span></span>

- <span data-ttu-id="2d7ef-475">**IP-adresser med portar:**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-475">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="2d7ef-476">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="2d7ef-476">contoso.com:443</span></span>
  - <span data-ttu-id="2d7ef-477">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="2d7ef-477">abc.contoso.com:25</span></span>

- <span data-ttu-id="2d7ef-478">**Icke-beskrivande jokertecken:**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-478">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="2d7ef-479">\*.\*</span><span class="sxs-lookup"><span data-stu-id="2d7ef-479">\*.\*</span></span>

- <span data-ttu-id="2d7ef-480">**Jokertecken i mitten:**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-480">**Middle wildcards**:</span></span>

  - <span data-ttu-id="2d7ef-481">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-481">conto\*so.com</span></span>
  - <span data-ttu-id="2d7ef-482">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-482">conto~so.com</span></span>

- <span data-ttu-id="2d7ef-483">**Dubbla jokertecken**</span><span class="sxs-lookup"><span data-stu-id="2d7ef-483">**Double wildcards**</span></span>

  - <span data-ttu-id="2d7ef-484">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="2d7ef-484">contoso.com/\*\*</span></span>
  - <span data-ttu-id="2d7ef-485">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="2d7ef-485">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2d7ef-486">Domänparsyntax för falska avsändarposter i listan Över tillåtna/blockerade klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="2d7ef-486">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2d7ef-487">Ett domänpar för en förfalskningsavsändare i innehavarlistan över tillåtna/blockerade avsändare har följande syntax: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="2d7ef-487">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="2d7ef-488">**Förfalskningsanvändare:** Det här värdet innefattar e-postadressen till den kapade  användaren som visas i rutan Från i e-postklienter.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-488">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="2d7ef-489">Den här adressen kallas även `5322.From` för adressen.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-489">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="2d7ef-490">Giltiga värden är:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-490">Valid values include:</span></span>
  - <span data-ttu-id="2d7ef-491">En enskild e-postadress (till exempel chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2d7ef-491">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="2d7ef-492">En e-postdomän (till exempel contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2d7ef-492">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="2d7ef-493">Jokertecknet (till exempel \* ).</span><span class="sxs-lookup"><span data-stu-id="2d7ef-493">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="2d7ef-494">**Skicka infrastruktur:** Det här värdet anger källan till meddelanden från den kapade användaren.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-494">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="2d7ef-495">Giltiga värden är:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-495">Valid values include:</span></span>
  - <span data-ttu-id="2d7ef-496">Domänen som finns i en omvänd DNS-sökning (PTR-post) för käll-e-postserverns IP-adress (till exempel fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="2d7ef-496">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="2d7ef-497">Om käll-IP-adressen inte har någon PTR-post identifieras den avsändande infrastrukturen som \<source IP\> /24 (till exempel 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="2d7ef-497">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="2d7ef-498">Här är några exempel på giltiga domänpar för att identifiera förfalskningsavsändare:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-498">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="2d7ef-499">Genom att lägga till ett domänpar tillåts *eller* blockeras bara kombinationen av den förfalskningsanvändaren *och* avsändarinfrastrukturen.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-499">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="2d7ef-500">E-post från förfalskningsanvändare från någon källa tillåts inte heller e-post från den avsändande infrastrukturkällan för någon förfalskningsanvändare.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-500">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span>

<span data-ttu-id="2d7ef-501">Du kan till exempel lägga till en tillåt-post för följande domänpar:</span><span class="sxs-lookup"><span data-stu-id="2d7ef-501">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="2d7ef-502">**Domän:** gmail.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-502">**Domain**: gmail.com</span></span>
- <span data-ttu-id="2d7ef-503">**Infrastruktur:** tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="2d7ef-503">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="2d7ef-504">Endast meddelanden från den *domänen och* sändning av infrastrukturpar tillåts förfalskning.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-504">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="2d7ef-505">Andra avsändare som försöker kapa gmail.com-post är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-505">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="2d7ef-506">Meddelanden från avsändare i andra domäner med ursprung i tms.mx.com kontrolleras med förfalskningsinformation.</span><span class="sxs-lookup"><span data-stu-id="2d7ef-506">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
