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
ms.openlocfilehash: 636114180a1814f5ef842b2a704f2df98488f46e
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694491"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="585ce-103">Hantera Klientorganisationens Tillåt/blockera listan</span><span class="sxs-lookup"><span data-stu-id="585ce-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="585ce-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="585ce-104">**Applies to**</span></span>
- [<span data-ttu-id="585ce-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="585ce-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="585ce-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="585ce-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="585ce-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="585ce-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="585ce-108">Funktionerna som beskrivs i den här artikeln är förhandsversioner, kan komma att ändras och är inte tillgängliga i alla organisationer.</span><span class="sxs-lookup"><span data-stu-id="585ce-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="585ce-109">Om din organisation inte har de förfalskningsfunktioner som beskrivs i den här artikeln kan du läsa mer om den äldre hanteringsupplevelsen för förfalskningsfunktioner i Hantera förfalskningsavsändare med hjälp av [förfalskningsprincip](walkthrough-spoof-intelligence-insight.md)och förfalskningsinformation i EOP.</span><span class="sxs-lookup"><span data-stu-id="585ce-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="585ce-110">Du kan för **stunden inte** konfigurera tillåtna URL-adresser eller filobjekt i listan över tillåtna/blockerade klienter.</span><span class="sxs-lookup"><span data-stu-id="585ce-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="585ce-111">I Microsoft 365 organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor, kanske du inte instämmer i EOP-filtrerings förlopp.</span><span class="sxs-lookup"><span data-stu-id="585ce-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="585ce-112">Till exempel kan ett bra meddelande markeras som dåligt (falskt positivt) eller så kan ett felaktigt meddelande tillåtas (falskt negativt).</span><span class="sxs-lookup"><span data-stu-id="585ce-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="585ce-113">Med klientorganisationens lista över tillåtna/blockerade & säkerhets- och efterlevnadscenter får du ett sätt att manuellt åsidosätta Microsoft 365 filtrera överensstämmelser.</span><span class="sxs-lookup"><span data-stu-id="585ce-113">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="585ce-114">Klientorganisationens lista över tillåtna/blockerade används under e-postflödet och när användaren klickar.</span><span class="sxs-lookup"><span data-stu-id="585ce-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="585ce-115">Du kan ange följande typer av åsidosättningar:</span><span class="sxs-lookup"><span data-stu-id="585ce-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="585ce-116">URL:er som ska blockeras.</span><span class="sxs-lookup"><span data-stu-id="585ce-116">URLs to block.</span></span>
- <span data-ttu-id="585ce-117">Filer som ska blockeras.</span><span class="sxs-lookup"><span data-stu-id="585ce-117">Files to block.</span></span>
- <span data-ttu-id="585ce-118">Förfalskningsavsändare som ska tillåta eller blockera.</span><span class="sxs-lookup"><span data-stu-id="585ce-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="585ce-119">Om du åsidosätter blockeringen av tillåtande eller blockering av förfalskningsinformation [blir](learn-about-spoof-intelligence.md)den falska avsändaren en  manuell tillåta- eller blockeringspost som bara visas på fliken Förfalskning i innehavarlistan över tillåtna/blockerade avsändare.</span><span class="sxs-lookup"><span data-stu-id="585ce-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="585ce-120">Här kan du även manuellt skapa tillåta eller blockera poster för förfalskningsavsändare innan de identifieras av förfalskningsinformation.</span><span class="sxs-lookup"><span data-stu-id="585ce-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="585ce-121">Den här artikeln beskriver hur du konfigurerar poster i listan Över tillåtna/blockerade klientorganisationer i Säkerhets- och efterlevnadscenter för & eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="585ce-121">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="585ce-122">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="585ce-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="585ce-123">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="585ce-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="585ce-124">Använd för att gå direkt **till sidan För att tillåta/blockera** klientorganisation. <https://protection.office.com/tenantAllowBlockList></span><span class="sxs-lookup"><span data-stu-id="585ce-124">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="585ce-125">Du anger filer genom att använda hashvärdet SHA256 för filen.</span><span class="sxs-lookup"><span data-stu-id="585ce-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="585ce-126">Om du vill hitta hashvärdet SHA256 för en fil i Windows kör du följande kommando i kommandotolken:</span><span class="sxs-lookup"><span data-stu-id="585ce-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="585ce-127">Ett exempelvärde är `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="585ce-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="585ce-128">Perceptuella hash-värden (pHash) stöds inte.</span><span class="sxs-lookup"><span data-stu-id="585ce-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="585ce-129">Tillgängliga URL-värden beskrivs i [URL-syntaxen för avsnittet Tillåt/blockera klientorganisation](#url-syntax-for-the-tenant-allowblock-list) senare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="585ce-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="585ce-130">Klientorganisationens lista över tillåtna/blockerade tillåter maximalt 500 poster för URL:er och 500 poster för filshashar.</span><span class="sxs-lookup"><span data-stu-id="585ce-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="585ce-131">Det maximala antalet tecken för varje post är:</span><span class="sxs-lookup"><span data-stu-id="585ce-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="585ce-132">Filshashar = 64</span><span class="sxs-lookup"><span data-stu-id="585ce-132">File hashes = 64</span></span>
  - <span data-ttu-id="585ce-133">URL = 250</span><span class="sxs-lookup"><span data-stu-id="585ce-133">URL = 250</span></span>

- <span data-ttu-id="585ce-134">En post ska vara aktiv inom 30 minuter.</span><span class="sxs-lookup"><span data-stu-id="585ce-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="585ce-135">Som standard förfaller poster i klientorganisationens lista över tillåtna/blockerade användare efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="585ce-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="585ce-136">Du kan ange ett datum eller ange att de aldrig ska upphöra.</span><span class="sxs-lookup"><span data-stu-id="585ce-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="585ce-137">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="585ce-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="585ce-138">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="585ce-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="585ce-139">Du måste ha tilldelats behörigheter i Exchange Online innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="585ce-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="585ce-140">**URL:er och filer:**</span><span class="sxs-lookup"><span data-stu-id="585ce-140">**URLs and files**:</span></span>
    - <span data-ttu-id="585ce-141">Om du vill lägga till och ta bort värden från klientorganisationens lista över tillåtna/blockerade användare måste du vara medlem i rollgrupperna Organisationshantering eller **Säkerhetsadministratör.** </span><span class="sxs-lookup"><span data-stu-id="585ce-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="585ce-142">För skrivskyddad åtkomst till listan över tillåtna/blockerade klientorganisationer måste du vara medlem i rollgrupperna **Global Reader** **eller Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="585ce-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="585ce-143">**Förfalskning**: En av följande kombinationer:</span><span class="sxs-lookup"><span data-stu-id="585ce-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="585ce-144">**Organisationshantering**</span><span class="sxs-lookup"><span data-stu-id="585ce-144">**Organization Management**</span></span>
    - <span data-ttu-id="585ce-145">**Säkerhetsadministratör** <u>och</u> **endast visa-konfiguration** **eller organisationshantering – endast visa.**</span><span class="sxs-lookup"><span data-stu-id="585ce-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="585ce-146">Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="585ce-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="585ce-147">Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="585ce-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="585ce-148">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="585ce-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="585ce-149">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="585ce-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="585ce-150">Använd Säkerhets- & efterlevnadscenter för att skapa blockera URL-poster i klientorganisationens lista över tillåtna/blockerade adresser</span><span class="sxs-lookup"><span data-stu-id="585ce-150">Use the Security & Compliance Center to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="585ce-151">I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**</span><span class="sxs-lookup"><span data-stu-id="585ce-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="585ce-152">På sidan **Lista över tillåtna/blockerade** klientorganisation kontrollerar du att **fliken URL:er** är markerad och klickar sedan på **Blockera**</span><span class="sxs-lookup"><span data-stu-id="585ce-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="585ce-153">I den **utfällna** menyn Blockera URL:er som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="585ce-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="585ce-154">**Lägg till URL:er som ska** blockeras: Ange en URL per rad, upp till högst 20.</span><span class="sxs-lookup"><span data-stu-id="585ce-154">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="585ce-155">Mer information om syntaxen för URL-poster finns i URL-syntaxen för avsnittet [Tillåt/blockera klientorganisation](#url-syntax-for-the-tenant-allowblock-list) längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="585ce-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="585ce-156">**Upphör aldrig** att gälla: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="585ce-156">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="585ce-157">Kontrollera att inställningen är inaktiverad (inaktiverad) och ange utgångsdatumet för posterna ![ ](../../media/scc-toggle-off.png) i rutan Förfaller. </span><span class="sxs-lookup"><span data-stu-id="585ce-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="585ce-158">eller</span><span class="sxs-lookup"><span data-stu-id="585ce-158">or</span></span>

     - <span data-ttu-id="585ce-159">Flytta reglaget till höger för att konfigurera posterna så att de aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="585ce-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png)<span data-ttu-id="585ce-161">.</span><span class="sxs-lookup"><span data-stu-id="585ce-161">.</span></span>

   - <span data-ttu-id="585ce-162">**Valfritt:** Ange beskrivande text för posterna.</span><span class="sxs-lookup"><span data-stu-id="585ce-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="585ce-163">När du är klar klickar du på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="585ce-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="585ce-164">Använd Säkerhets- & säkerhets- och efterlevnadscenter för att skapa blockeringsfilposter i klientorganisationens lista över tillåtna/blockerade filer</span><span class="sxs-lookup"><span data-stu-id="585ce-164">Use the Security & Compliance Center to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="585ce-165">I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**</span><span class="sxs-lookup"><span data-stu-id="585ce-165">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="585ce-166">På sidan **Lista över tillåtna/blockerade** klientorganisation väljer du **fliken** Filer och klickar sedan på **Blockera**.</span><span class="sxs-lookup"><span data-stu-id="585ce-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="585ce-167">I den **utfällna menyn** Lägg till filer för att blockera som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="585ce-167">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="585ce-168">**Lägga till filhashar:** Ange ett SHA256-hashvärde per rad, upp till högst 20.</span><span class="sxs-lookup"><span data-stu-id="585ce-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="585ce-169">**Upphör aldrig** att gälla: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="585ce-169">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="585ce-170">Kontrollera att inställningen är inaktiverad (inaktiverad) och ange utgångsdatumet för posterna ![ ](../../media/scc-toggle-off.png) i rutan Förfaller. </span><span class="sxs-lookup"><span data-stu-id="585ce-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="585ce-171">eller</span><span class="sxs-lookup"><span data-stu-id="585ce-171">or</span></span>

     - <span data-ttu-id="585ce-172">Flytta reglaget till höger för att konfigurera posterna så att de aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="585ce-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png)<span data-ttu-id="585ce-174">.</span><span class="sxs-lookup"><span data-stu-id="585ce-174">.</span></span>

   - <span data-ttu-id="585ce-175">**Valfritt:** Ange beskrivande text för posterna.</span><span class="sxs-lookup"><span data-stu-id="585ce-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="585ce-176">När du är klar klickar du på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="585ce-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="585ce-177">Använd Säkerhets- & säkerhets- och efterlevnadscenter för att skapa tillåta eller blockera förfalskning av avsändare i listan Tillåt/blockera klientorganisation</span><span class="sxs-lookup"><span data-stu-id="585ce-177">Use the Security & Compliance Center to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="585ce-178">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="585ce-178">**Notes**:</span></span>

- <span data-ttu-id="585ce-179">Endast kombinationen _av_ den förfalskningsanvändaren och avsändarinfrastrukturen som definierats i domänparet är specifikt tillåten eller blockerad från förfalskning. </span><span class="sxs-lookup"><span data-stu-id="585ce-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="585ce-180">När du konfigurerar en tillåta- eller blockeringspost för ett domänpar visas inte längre meddelanden från det domänparet i förfalskningsinformation.</span><span class="sxs-lookup"><span data-stu-id="585ce-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="585ce-181">Poster för falska avsändare upphör aldrig att gälla.</span><span class="sxs-lookup"><span data-stu-id="585ce-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="585ce-182">I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**</span><span class="sxs-lookup"><span data-stu-id="585ce-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="585ce-183">Välj **fliken Förfalskning på sidan Lista** över tillåtna/blockerade **klientorganisation** och klicka sedan på Lägg **till.**</span><span class="sxs-lookup"><span data-stu-id="585ce-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="585ce-184">I den **utfällna menyn** Lägg till ny domänpar som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="585ce-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="585ce-185">**Lägga till nya domänpar med jokertecken:** Ange ett domänpar per rad, upp till maximalt 20.</span><span class="sxs-lookup"><span data-stu-id="585ce-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="585ce-186">Mer information om syntaxen för falska avsändarposter finns i syntaxen för domänpar för posterna för falska avsändare i avsnittet [Tillåt/blockera](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) lista för klientorganisation längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="585ce-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="585ce-187">**Förfalskningstyp:** Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="585ce-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="585ce-188">**Internt**: Förfalskningsavsändare finns i en domän som tillhör din organisation (en [godkänd domän).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="585ce-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="585ce-189">**Extern:** Den falska avsändaren finns i en extern domän.</span><span class="sxs-lookup"><span data-stu-id="585ce-189">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="585ce-190">**Åtgärd:** Välj **Tillåt** eller **Blockera**.</span><span class="sxs-lookup"><span data-stu-id="585ce-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="585ce-191">När du är klar klickar du på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="585ce-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="585ce-192">Använd Säkerhets- & kompatibilitetscenter för att visa poster i listan över tillåtna/blockerade klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="585ce-192">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="585ce-193">I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**</span><span class="sxs-lookup"><span data-stu-id="585ce-193">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="585ce-194">Välj den flik du vill använda.</span><span class="sxs-lookup"><span data-stu-id="585ce-194">Select the tab you want.</span></span> <span data-ttu-id="585ce-195">Vilka kolumner som är tillgängliga beror på vilken flik du valde:</span><span class="sxs-lookup"><span data-stu-id="585ce-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="585ce-196">**URL:er:**</span><span class="sxs-lookup"><span data-stu-id="585ce-196">**URLs**:</span></span>
     - <span data-ttu-id="585ce-197">**Värde:** URL:en.</span><span class="sxs-lookup"><span data-stu-id="585ce-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="585ce-198">**Åtgärd:** **Värdeblocket**.</span><span class="sxs-lookup"><span data-stu-id="585ce-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="585ce-199">**Datum för senaste uppdatering**</span><span class="sxs-lookup"><span data-stu-id="585ce-199">**Last updated date**</span></span>
     - <span data-ttu-id="585ce-200">**Förfallodatum**</span><span class="sxs-lookup"><span data-stu-id="585ce-200">**Expiration date**</span></span>
     - <span data-ttu-id="585ce-201">**Obs!**</span><span class="sxs-lookup"><span data-stu-id="585ce-201">**Note**</span></span>

   - <span data-ttu-id="585ce-202">**Filer**</span><span class="sxs-lookup"><span data-stu-id="585ce-202">**Files**</span></span>
     - <span data-ttu-id="585ce-203">**Värde:** Filens hash-kod.</span><span class="sxs-lookup"><span data-stu-id="585ce-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="585ce-204">**Åtgärd:** **Värdeblocket**.</span><span class="sxs-lookup"><span data-stu-id="585ce-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="585ce-205">**Datum för senaste uppdatering**</span><span class="sxs-lookup"><span data-stu-id="585ce-205">**Last updated date**</span></span>
     - <span data-ttu-id="585ce-206">**Förfallodatum**</span><span class="sxs-lookup"><span data-stu-id="585ce-206">**Expiration date**</span></span>
     - <span data-ttu-id="585ce-207">**Obs!**</span><span class="sxs-lookup"><span data-stu-id="585ce-207">**Note**</span></span>

   - <span data-ttu-id="585ce-208">**Förfalskning**</span><span class="sxs-lookup"><span data-stu-id="585ce-208">**Spoofing**</span></span>
     - <span data-ttu-id="585ce-209">**Spoofed användare**</span><span class="sxs-lookup"><span data-stu-id="585ce-209">**Spoofed user**</span></span>
     - <span data-ttu-id="585ce-210">**Skicka infrastruktur**</span><span class="sxs-lookup"><span data-stu-id="585ce-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="585ce-211">**Förfalskningstyp:** värdet **Internt eller** **Externt**.</span><span class="sxs-lookup"><span data-stu-id="585ce-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="585ce-212">**Åtgärd:** **Värdeblockering** eller **Tillåt**.</span><span class="sxs-lookup"><span data-stu-id="585ce-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="585ce-213">Du kan klicka på en kolumnrubrik om du vill sortera i stigande eller fallande ordning.</span><span class="sxs-lookup"><span data-stu-id="585ce-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="585ce-214">Du kan gruppera **resultatet genom** att klicka på Gruppera.</span><span class="sxs-lookup"><span data-stu-id="585ce-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="585ce-215">Vilka värden som är tillgängliga beror på vilken flik du valde:</span><span class="sxs-lookup"><span data-stu-id="585ce-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="585ce-216">**URL:er:** Du kan gruppera resultatet efter **åtgärd.**</span><span class="sxs-lookup"><span data-stu-id="585ce-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="585ce-217">**Filer:** Du kan gruppera resultatet efter **åtgärd.**</span><span class="sxs-lookup"><span data-stu-id="585ce-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="585ce-218">**Avsändardomäner för BCL-förbikoppling:** **Gruppen** är inte tillgänglig på den här fliken.</span><span class="sxs-lookup"><span data-stu-id="585ce-218">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="585ce-219">**Förfalskning:** Du kan gruppera resultaten efter **Åtgärds-** **eller förfalskningstyp.**</span><span class="sxs-lookup"><span data-stu-id="585ce-219">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="585ce-220">Klicka **på** Sök , ange hela eller en del av ett värde och tryck sedan på RETUR för att hitta ett visst värde.</span><span class="sxs-lookup"><span data-stu-id="585ce-220">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="585ce-221">När du är klar klickar du på **Rensa sökning Ikonen** Rensa ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) sökning.</span><span class="sxs-lookup"><span data-stu-id="585ce-221">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="585ce-222">Filtrera **resultatet genom** att klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="585ce-222">Click **Filter** to filter the results.</span></span> <span data-ttu-id="585ce-223">Vilka värden som är tillgängliga **i den utfällade** filterflik som visas beror på vilken flik du valde:</span><span class="sxs-lookup"><span data-stu-id="585ce-223">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="585ce-224">**URL:er**</span><span class="sxs-lookup"><span data-stu-id="585ce-224">**URLs**</span></span>
     - <span data-ttu-id="585ce-225">**Åtgärd**</span><span class="sxs-lookup"><span data-stu-id="585ce-225">**Action**</span></span>
     - <span data-ttu-id="585ce-226">**Upphör aldrig att gälla**</span><span class="sxs-lookup"><span data-stu-id="585ce-226">**Never expire**</span></span>
     - <span data-ttu-id="585ce-227">**Datum för senaste uppdatering**</span><span class="sxs-lookup"><span data-stu-id="585ce-227">**Last updated date**</span></span>
     - <span data-ttu-id="585ce-228">**Förfallodatum**</span><span class="sxs-lookup"><span data-stu-id="585ce-228">**Expiration date**</span></span>

   - <span data-ttu-id="585ce-229">**Filer**</span><span class="sxs-lookup"><span data-stu-id="585ce-229">**Files**</span></span>
     - <span data-ttu-id="585ce-230">**Åtgärd**</span><span class="sxs-lookup"><span data-stu-id="585ce-230">**Action**</span></span>
     - <span data-ttu-id="585ce-231">**Upphör aldrig att gälla**</span><span class="sxs-lookup"><span data-stu-id="585ce-231">**Never expire**</span></span>
     - <span data-ttu-id="585ce-232">**Datum för senaste uppdatering**</span><span class="sxs-lookup"><span data-stu-id="585ce-232">**Last updated date**</span></span>
     - <span data-ttu-id="585ce-233">**Förfallodatum**</span><span class="sxs-lookup"><span data-stu-id="585ce-233">**Expiration date**</span></span>

   - <span data-ttu-id="585ce-234">**Sender domains for BCL bypass**</span><span class="sxs-lookup"><span data-stu-id="585ce-234">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="585ce-235">**Upphör aldrig att gälla**</span><span class="sxs-lookup"><span data-stu-id="585ce-235">**Never expire**</span></span>
     - <span data-ttu-id="585ce-236">**Datum för senaste uppdatering**</span><span class="sxs-lookup"><span data-stu-id="585ce-236">**Last updated date**</span></span>
     - <span data-ttu-id="585ce-237">**Förfallodatum**</span><span class="sxs-lookup"><span data-stu-id="585ce-237">**Expiration date**</span></span>

   - <span data-ttu-id="585ce-238">**Förfalskning**</span><span class="sxs-lookup"><span data-stu-id="585ce-238">**Spoofing**</span></span>
     - <span data-ttu-id="585ce-239">**Åtgärd**</span><span class="sxs-lookup"><span data-stu-id="585ce-239">**Action**</span></span>
     - <span data-ttu-id="585ce-240">**Förfalskningstyp**</span><span class="sxs-lookup"><span data-stu-id="585ce-240">**Spoof type**</span></span>

   <span data-ttu-id="585ce-241">När du är klar klickar du på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="585ce-241">When you're finished, click **Apply**.</span></span> <span data-ttu-id="585ce-242">Om du vill ta bort befintliga  **filter klickar** du på Filter och sedan på Rensa filter i den **utfällklara filterfällan som visas.**</span><span class="sxs-lookup"><span data-stu-id="585ce-242">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="585ce-243">Använd Säkerhets- & säkerhets- och efterlevnadscenter för att ändra poster i listan över tillåtna/blockerade klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="585ce-243">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="585ce-244">I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**</span><span class="sxs-lookup"><span data-stu-id="585ce-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="585ce-245">Välj den flik som innehåller den typ av post som du vill ändra:</span><span class="sxs-lookup"><span data-stu-id="585ce-245">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="585ce-246">**URL:er**</span><span class="sxs-lookup"><span data-stu-id="585ce-246">**URLs**</span></span>
   - <span data-ttu-id="585ce-247">**Filer**</span><span class="sxs-lookup"><span data-stu-id="585ce-247">**Files**</span></span>
   - <span data-ttu-id="585ce-248">**Sender domains for BCL bypass**</span><span class="sxs-lookup"><span data-stu-id="585ce-248">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="585ce-249">**Förfalskning**</span><span class="sxs-lookup"><span data-stu-id="585ce-249">**Spoofing**</span></span>

3. <span data-ttu-id="585ce-250">Markera den post som du vill  ändra och klicka sedan på redigera ![ redigeringsikonen ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="585ce-250">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="585ce-251">Vilka värden som du kan ändra i den utfäll plats som visas beror på vilken flik du valde i föregående steg:</span><span class="sxs-lookup"><span data-stu-id="585ce-251">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="585ce-252">**URL:er**</span><span class="sxs-lookup"><span data-stu-id="585ce-252">**URLs**</span></span>
     - <span data-ttu-id="585ce-253">**Upphör aldrig att** gälla och/eller förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="585ce-253">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="585ce-254">**Valfri anteckning**</span><span class="sxs-lookup"><span data-stu-id="585ce-254">**Optional note**</span></span>

   - <span data-ttu-id="585ce-255">**Filer**</span><span class="sxs-lookup"><span data-stu-id="585ce-255">**Files**</span></span>
     - <span data-ttu-id="585ce-256">**Upphör aldrig att** gälla och/eller förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="585ce-256">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="585ce-257">**Valfri anteckning**</span><span class="sxs-lookup"><span data-stu-id="585ce-257">**Optional note**</span></span>

   - <span data-ttu-id="585ce-258">**Sender domains for BCL bypass**</span><span class="sxs-lookup"><span data-stu-id="585ce-258">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="585ce-259">**Upphör aldrig att** gälla och/eller förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="585ce-259">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="585ce-260">**Förfalskning**</span><span class="sxs-lookup"><span data-stu-id="585ce-260">**Spoofing**</span></span>
     - <span data-ttu-id="585ce-261">**Åtgärd:** Du kan ändra värdet till **Tillåt** eller **Blockera.**</span><span class="sxs-lookup"><span data-stu-id="585ce-261">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="585ce-262">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="585ce-262">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="585ce-263">Använda Säkerhets- & säkerhets- och efterlevnadscenter för att ta bort poster från listan över tillåtna/blockerade klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="585ce-263">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="585ce-264">I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**</span><span class="sxs-lookup"><span data-stu-id="585ce-264">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="585ce-265">Välj den flik som innehåller den typ av post som du vill ta bort:</span><span class="sxs-lookup"><span data-stu-id="585ce-265">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="585ce-266">**URL:er**</span><span class="sxs-lookup"><span data-stu-id="585ce-266">**URLs**</span></span>
   - <span data-ttu-id="585ce-267">**Filer**</span><span class="sxs-lookup"><span data-stu-id="585ce-267">**Files**</span></span>
   - <span data-ttu-id="585ce-268">**Sender domains for BCL bypass**</span><span class="sxs-lookup"><span data-stu-id="585ce-268">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="585ce-269">**Förfalskning**</span><span class="sxs-lookup"><span data-stu-id="585ce-269">**Spoofing**</span></span>

3. <span data-ttu-id="585ce-270">Markera den post som du vill ta bort och klicka sedan på ikonen **Ta** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) bort.</span><span class="sxs-lookup"><span data-stu-id="585ce-270">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="585ce-271">Klicka på Ta bort i varningsdialogrutan som **visas.**</span><span class="sxs-lookup"><span data-stu-id="585ce-271">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="585ce-272">Använd Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera innehavarlistan över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="585ce-272">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="585ce-273">Använda PowerShell för att lägga till blockeringsfiler eller URL-poster i klientorganisationens lista över tillåtna/blockerade adresser</span><span class="sxs-lookup"><span data-stu-id="585ce-273">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="585ce-274">Använd följande syntax för att lägga till blockeringsfiler eller URL-poster i klientorganisationens lista över tillåtna/blockerade adresser:</span><span class="sxs-lookup"><span data-stu-id="585ce-274">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="585ce-275">I det här exemplet läggs en post för blockering av filer till för de angivna filerna som aldrig förfaller.</span><span class="sxs-lookup"><span data-stu-id="585ce-275">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="585ce-276">I det här exemplet läggs en blockerings-URL-post till för contoso.com och alla underdomäner (till exempel contoso.com, www.contoso.com och xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="585ce-276">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="585ce-277">Eftersom vi inte använder parametrarna Förfallodatum eller NoExpiration upphör posten att gälla efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="585ce-277">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="585ce-278">Detaljerad information om syntax och parametrar finns i [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="585ce-278">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="585ce-279">Använd PowerShell för att lägga till posterna tillåta eller blockera förfalskning av avsändare i klientorganisationens lista över tillåtna/blockerade avsändare</span><span class="sxs-lookup"><span data-stu-id="585ce-279">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="585ce-280">Om du vill lägga till förfalskningsposter från klientorganisationens lista över tillåtna/blockerade avsändare använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="585ce-280">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="585ce-281">Detaljerad information om syntax och parametrar finns i [New-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/new-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="585ce-281">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="585ce-282">Använda PowerShell för att visa blockera fil- eller URL-poster i klientorganisationens lista över tillåtna/blockerade adresser</span><span class="sxs-lookup"><span data-stu-id="585ce-282">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="585ce-283">Om du vill visa blockeringsfil- eller URL-poster i klientorganisationens lista över tillåtna/blockerade adresser använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="585ce-283">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="585ce-284">Det här exemplet returnerar information om det angivna hash-värdet för filen.</span><span class="sxs-lookup"><span data-stu-id="585ce-284">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="585ce-285">I det här exemplet returneras alla blockerade URL-adresser.</span><span class="sxs-lookup"><span data-stu-id="585ce-285">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="585ce-286">Detaljerad information om syntax och parametrar finns i [Get-TenantAllowBlockListItems.](/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="585ce-286">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="585ce-287">Använda PowerShell för att visa tillåta eller blockera förfalskning av avsändare i klientorganisationens lista över tillåtna/blockerade avsändare</span><span class="sxs-lookup"><span data-stu-id="585ce-287">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="585ce-288">Använd följande syntax för att visa falska avsändarposter i listan Tillåt/blockera klientorganisation:</span><span class="sxs-lookup"><span data-stu-id="585ce-288">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="585ce-289">Det här exemplet returnerar alla falska avsändarposter i listan över tillåtna/blockerade klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="585ce-289">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="585ce-290">Det här exemplet returnerar alla interna poster med tillåta förfalskning.</span><span class="sxs-lookup"><span data-stu-id="585ce-290">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="585ce-291">Det här exemplet returnerar alla externa poster för spärrade avsändare.</span><span class="sxs-lookup"><span data-stu-id="585ce-291">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="585ce-292">Detaljerad information om syntax och parametrar finns i [Get-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/get-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="585ce-292">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="585ce-293">Använda PowerShell för att ändra blockeringsfiler och URL-poster i klientorganisationens lista över tillåtna/blockerade adresser</span><span class="sxs-lookup"><span data-stu-id="585ce-293">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="585ce-294">Använd följande syntax för att ändra blockeringsfiler och URL-poster i klientorganisationens lista över tillåtna/blockerade adresser:</span><span class="sxs-lookup"><span data-stu-id="585ce-294">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="585ce-295">I det här exemplet ändras förfallodatumet för den angivna blockerings-URL-posten.</span><span class="sxs-lookup"><span data-stu-id="585ce-295">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="585ce-296">Detaljerad information om syntax och parametrar finns i [Set-TenantAllowBlockListItems.](/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="585ce-296">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="585ce-297">Använda PowerShell för att ändra posterna för tillåta eller blockera förfalskning av avsändare i listan över tillåtna/blockerade klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="585ce-297">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="585ce-298">Om du vill ändra tillåta eller blockera förfalskning av avsändare i listan över tillåtna eller blockerade avsändare använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="585ce-298">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="585ce-299">I det här exemplet ändras en förfalskningspost från tillåts till blockering.</span><span class="sxs-lookup"><span data-stu-id="585ce-299">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="585ce-300">Detaljerad information om syntax och parametrar finns i [Set-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/set-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="585ce-300">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="585ce-301">Använda PowerShell för att ta bort URL-adresser eller filposter från klientorganisationens lista över tillåtna/blockerade adresser</span><span class="sxs-lookup"><span data-stu-id="585ce-301">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="585ce-302">Använd följande syntax för att ta bort fil- och URL-poster från klientorganisationens lista över tillåtna/blockerade adresser:</span><span class="sxs-lookup"><span data-stu-id="585ce-302">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="585ce-303">Det här exemplet tar bort den angivna blockerings-URL-posten från klientorganisationens lista över tillåtna/blockerade adresser.</span><span class="sxs-lookup"><span data-stu-id="585ce-303">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="585ce-304">Detaljerad information om syntax och parametrar finns i [Remove-TenantAllowBlockListItems.](/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="585ce-304">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="585ce-305">Använda PowerShell för att ta bort tillåta eller blockera förfalskning av avsändare från klientorganisationens lista över tillåtna/blockerade avsändare</span><span class="sxs-lookup"><span data-stu-id="585ce-305">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="585ce-306">Om du vill ta bort tillåta eller blockera förfalskning av avsändare från klientorganisationens lista över tillåtna/blockerade avsändare använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="585ce-306">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="585ce-307">Detaljerad information om syntax och parametrar finns i [Remove-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="585ce-307">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="585ce-308">URL-syntax för klientorganisationens lista över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="585ce-308">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="585ce-309">IP4v- och IPv6-adresser är tillåtna, men INTE TCP-/UDP-portar.</span><span class="sxs-lookup"><span data-stu-id="585ce-309">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="585ce-310">Filnamnstillägg är inte tillåtna (till exempel test.pdf).</span><span class="sxs-lookup"><span data-stu-id="585ce-310">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="585ce-311">Unicode stöds inte, men punycode stöds.</span><span class="sxs-lookup"><span data-stu-id="585ce-311">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="585ce-312">Hostnames tillåts om alla följande uttryck är sanna:</span><span class="sxs-lookup"><span data-stu-id="585ce-312">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="585ce-313">Värdnamnet innehåller en punkt.</span><span class="sxs-lookup"><span data-stu-id="585ce-313">The hostname contains a period.</span></span>
  - <span data-ttu-id="585ce-314">Det finns minst ett tecken till vänster om perioden.</span><span class="sxs-lookup"><span data-stu-id="585ce-314">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="585ce-315">Det finns minst två tecken till höger om perioden.</span><span class="sxs-lookup"><span data-stu-id="585ce-315">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="585ce-316">Till exempel är `t.co` tillåtet eller `.com` inte `contoso.` tillåtet.</span><span class="sxs-lookup"><span data-stu-id="585ce-316">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="585ce-317">Undervägar är inte underförstådda.</span><span class="sxs-lookup"><span data-stu-id="585ce-317">Subpaths are not implied.</span></span>

  <span data-ttu-id="585ce-318">Exempelvis `contoso.com` ingår inte `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="585ce-318">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="585ce-319">Jokertecken (\*) tillåts i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="585ce-319">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="585ce-320">Ett vänster jokertecken måste följas av en punkt för att ange en underdomän.</span><span class="sxs-lookup"><span data-stu-id="585ce-320">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="585ce-321">Är till exempel `*.contoso.com` tillåtet, `*contoso.com` är inte tillåtet.</span><span class="sxs-lookup"><span data-stu-id="585ce-321">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="585ce-322">Ett höger jokertecken måste följa ett snedstreck (/) om du vill ange en sökväg.</span><span class="sxs-lookup"><span data-stu-id="585ce-322">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="585ce-323">Till exempel är `contoso.com/*` tillåtet eller `contoso.com*` inte `contoso.com/ab*` tillåtet.</span><span class="sxs-lookup"><span data-stu-id="585ce-323">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="585ce-324">Alla undervägar kan inte underförstådas med ett rätt jokertecken.</span><span class="sxs-lookup"><span data-stu-id="585ce-324">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="585ce-325">Exempelvis `contoso.com/*` ingår inte `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="585ce-325">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="585ce-326">`*.com*` är ogiltig (inte en lösbar domän och att rätt jokertecken inte följer ett snedstreck).</span><span class="sxs-lookup"><span data-stu-id="585ce-326">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="585ce-327">Jokertecken tillåts inte i IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="585ce-327">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="585ce-328">Tecknet tilde (~) är tillgängligt i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="585ce-328">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="585ce-329">Ett vänster tilde-namn antyder en domän och alla underdomäner.</span><span class="sxs-lookup"><span data-stu-id="585ce-329">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="585ce-330">Exempel: `~contoso.com` inkluderar `contoso.com` och `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="585ce-330">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="585ce-331">URL-poster som innehåller protokoll (till exempel , eller ) kommer att `http://` `https://` `ftp://` misslyckas, eftersom URL-poster tillämpas på alla protokoll.</span><span class="sxs-lookup"><span data-stu-id="585ce-331">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="585ce-332">Ett användarnamn eller lösenord stöds inte eller krävs inte.</span><span class="sxs-lookup"><span data-stu-id="585ce-332">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="585ce-333">Citattecken (' eller ") är ogiltiga tecken.</span><span class="sxs-lookup"><span data-stu-id="585ce-333">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="585ce-334">En URL bör innehålla alla omdirigeringar där det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="585ce-334">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="585ce-335">URL-inmatningsscenarier</span><span class="sxs-lookup"><span data-stu-id="585ce-335">URL entry scenarios</span></span>

<span data-ttu-id="585ce-336">Giltiga URL-poster och deras resultat beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="585ce-336">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="585ce-337">Scenario: Inga jokertecken</span><span class="sxs-lookup"><span data-stu-id="585ce-337">Scenario: No wildcards</span></span>

<span data-ttu-id="585ce-338">**Post:**`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="585ce-338">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="585ce-339">**Tillåt matchning:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-339">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="585ce-340">**Tillåt ej matchad:**</span><span class="sxs-lookup"><span data-stu-id="585ce-340">**Allow not matched**:</span></span>

  - <span data-ttu-id="585ce-341">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-341">abc-contoso.com</span></span>
  - <span data-ttu-id="585ce-342">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="585ce-342">contoso.com/a</span></span>
  - <span data-ttu-id="585ce-343">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-343">payroll.contoso.com</span></span>
  - <span data-ttu-id="585ce-344">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-344">test.com/contoso.com</span></span>
  - <span data-ttu-id="585ce-345">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-345">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="585ce-346">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-346">www.contoso.com</span></span>
  - <span data-ttu-id="585ce-347">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-347">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="585ce-348">**Blockmatchning:**</span><span class="sxs-lookup"><span data-stu-id="585ce-348">**Block match**:</span></span>

  - <span data-ttu-id="585ce-349">contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-349">contoso.com</span></span>
  - <span data-ttu-id="585ce-350">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="585ce-350">contoso.com/a</span></span>
  - <span data-ttu-id="585ce-351">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-351">payroll.contoso.com</span></span>
  - <span data-ttu-id="585ce-352">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-352">test.com/contoso.com</span></span>
  - <span data-ttu-id="585ce-353">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-353">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="585ce-354">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-354">www.contoso.com</span></span>
  - <span data-ttu-id="585ce-355">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-355">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="585ce-356">**Blockera matchas inte:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-356">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="585ce-357">Scenario: Vänster jokertecken (underdomän)</span><span class="sxs-lookup"><span data-stu-id="585ce-357">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="585ce-358">**Post:**`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="585ce-358">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="585ce-359">**Tillåt matchning** och **Blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="585ce-359">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="585ce-360">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-360">www.contoso.com</span></span>
  - <span data-ttu-id="585ce-361">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-361">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="585ce-362">**Tillåt ej matchad** och **Blockera ej matchad:**</span><span class="sxs-lookup"><span data-stu-id="585ce-362">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="585ce-363">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-363">123contoso.com</span></span>
  - <span data-ttu-id="585ce-364">contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-364">contoso.com</span></span>
  - <span data-ttu-id="585ce-365">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-365">test.com/contoso.com</span></span>
  - <span data-ttu-id="585ce-366">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="585ce-366">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="585ce-367">Scenario: Höger jokertecken högst upp i sökvägen</span><span class="sxs-lookup"><span data-stu-id="585ce-367">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="585ce-368">**Post:**`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="585ce-368">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="585ce-369">**Tillåt matchning** och **Blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="585ce-369">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="585ce-370">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="585ce-370">contoso.com/a/b</span></span>
  - <span data-ttu-id="585ce-371">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="585ce-371">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="585ce-372">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="585ce-372">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="585ce-373">**Tillåt ej matchad** och **Blockera ej matchad:**</span><span class="sxs-lookup"><span data-stu-id="585ce-373">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="585ce-374">contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-374">contoso.com</span></span>
  - <span data-ttu-id="585ce-375">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="585ce-375">contoso.com/a</span></span>
  - <span data-ttu-id="585ce-376">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-376">www.contoso.com</span></span>
  - <span data-ttu-id="585ce-377">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-377">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="585ce-378">Scenario: Vänster tilde</span><span class="sxs-lookup"><span data-stu-id="585ce-378">Scenario: Left tilde</span></span>

<span data-ttu-id="585ce-379">**Post:**`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="585ce-379">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="585ce-380">**Tillåt matchning** och **Blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="585ce-380">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="585ce-381">contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-381">contoso.com</span></span>
  - <span data-ttu-id="585ce-382">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-382">www.contoso.com</span></span>
  - <span data-ttu-id="585ce-383">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-383">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="585ce-384">**Tillåt ej matchad** och **Blockera ej matchad:**</span><span class="sxs-lookup"><span data-stu-id="585ce-384">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="585ce-385">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-385">123contoso.com</span></span>
  - <span data-ttu-id="585ce-386">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="585ce-386">contoso.com/abc</span></span>
  - <span data-ttu-id="585ce-387">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="585ce-387">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="585ce-388">Scenario: Höger suffix för jokertecken</span><span class="sxs-lookup"><span data-stu-id="585ce-388">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="585ce-389">**Post:**`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="585ce-389">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="585ce-390">**Tillåt matchning** och **Blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="585ce-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="585ce-391">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="585ce-391">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="585ce-392">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="585ce-392">contoso.com/a</span></span>
  - <span data-ttu-id="585ce-393">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="585ce-393">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="585ce-394">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="585ce-394">contoso.com/ab</span></span>
  - <span data-ttu-id="585ce-395">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="585ce-395">contoso.com/b</span></span>
  - <span data-ttu-id="585ce-396">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="585ce-396">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="585ce-397">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="585ce-397">contoso.com/ba</span></span>

- <span data-ttu-id="585ce-398">**Tillåt ej matchad** och **Blockera ej matchad**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-398">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="585ce-399">Scenario: Vänster underdomän med jokertecken och höger suffix för jokertecken</span><span class="sxs-lookup"><span data-stu-id="585ce-399">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="585ce-400">**Post:**`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="585ce-400">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="585ce-401">**Tillåt matchning** och **Blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="585ce-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="585ce-402">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="585ce-402">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="585ce-403">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="585ce-403">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="585ce-404">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="585ce-404">www.contoso.com/a</span></span>
  - <span data-ttu-id="585ce-405">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="585ce-405">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="585ce-406">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="585ce-406">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="585ce-407">**Tillåt ej matchad** och **Blockera ej matchad**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="585ce-407">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="585ce-408">Scenario: Vänster och höger tilde</span><span class="sxs-lookup"><span data-stu-id="585ce-408">Scenario: Left and right tilde</span></span>

<span data-ttu-id="585ce-409">**Post:**`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="585ce-409">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="585ce-410">**Tillåt matchning** och **Blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="585ce-410">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="585ce-411">contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-411">contoso.com</span></span>
  - <span data-ttu-id="585ce-412">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="585ce-412">contoso.com/a</span></span>
  - <span data-ttu-id="585ce-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-413">www.contoso.com</span></span>
  - <span data-ttu-id="585ce-414">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="585ce-414">www.contoso.com/b</span></span>
  - <span data-ttu-id="585ce-415">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-415">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="585ce-416">**Tillåt ej matchad** och **Blockera ej matchad:**</span><span class="sxs-lookup"><span data-stu-id="585ce-416">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="585ce-417">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-417">123contoso.com</span></span>
  - <span data-ttu-id="585ce-418">contoso.org</span><span class="sxs-lookup"><span data-stu-id="585ce-418">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="585ce-419">Scenario: IP-adress</span><span class="sxs-lookup"><span data-stu-id="585ce-419">Scenario: IP address</span></span>

<span data-ttu-id="585ce-420">**Post:**`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="585ce-420">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="585ce-421">**Tillåt matchning** och **Blockeringsmatchning**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="585ce-421">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="585ce-422">**Tillåt ej matchad** och **Blockera ej matchad:**</span><span class="sxs-lookup"><span data-stu-id="585ce-422">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="585ce-423">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="585ce-423">1.2.3.4/a</span></span>
  - <span data-ttu-id="585ce-424">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="585ce-424">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="585ce-425">IP-adress med rätt jokertecken</span><span class="sxs-lookup"><span data-stu-id="585ce-425">IP address with right wildcard</span></span>

<span data-ttu-id="585ce-426">**Post:**`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="585ce-426">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="585ce-427">**Tillåt matchning** och **Blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="585ce-427">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="585ce-428">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="585ce-428">1.2.3.4/b</span></span>
  - <span data-ttu-id="585ce-429">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="585ce-429">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="585ce-430">Exempel på ogiltiga poster</span><span class="sxs-lookup"><span data-stu-id="585ce-430">Examples of invalid entries</span></span>

<span data-ttu-id="585ce-431">Följande poster är ogiltiga:</span><span class="sxs-lookup"><span data-stu-id="585ce-431">The following entries are invalid:</span></span>

- <span data-ttu-id="585ce-432">**Värden som saknas eller är ogiltiga:**</span><span class="sxs-lookup"><span data-stu-id="585ce-432">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="585ce-433">contoso</span><span class="sxs-lookup"><span data-stu-id="585ce-433">contoso</span></span>
  - <span data-ttu-id="585ce-434">\*CONTOSO.\*</span><span class="sxs-lookup"><span data-stu-id="585ce-434">\*.contoso.\*</span></span>
  - <span data-ttu-id="585ce-435">\*.com</span><span class="sxs-lookup"><span data-stu-id="585ce-435">\*.com</span></span>
  - <span data-ttu-id="585ce-436">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="585ce-436">\*.pdf</span></span>

- <span data-ttu-id="585ce-437">**Jokertecken på text eller utan avståndstecken:**</span><span class="sxs-lookup"><span data-stu-id="585ce-437">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="585ce-438">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="585ce-438">\*contoso.com</span></span>
  - <span data-ttu-id="585ce-439">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="585ce-439">contoso.com\*</span></span>
  - <span data-ttu-id="585ce-440">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="585ce-440">\*1.2.3.4</span></span>
  - <span data-ttu-id="585ce-441">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="585ce-441">1.2.3.4\*</span></span>
  - <span data-ttu-id="585ce-442">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="585ce-442">contoso.com/a\*</span></span>
  - <span data-ttu-id="585ce-443">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="585ce-443">contoso.com/ab\*</span></span>

- <span data-ttu-id="585ce-444">**IP-adresser med portar:**</span><span class="sxs-lookup"><span data-stu-id="585ce-444">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="585ce-445">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="585ce-445">contoso.com:443</span></span>
  - <span data-ttu-id="585ce-446">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="585ce-446">abc.contoso.com:25</span></span>

- <span data-ttu-id="585ce-447">**Icke-beskrivande jokertecken:**</span><span class="sxs-lookup"><span data-stu-id="585ce-447">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="585ce-448">\*.\*</span><span class="sxs-lookup"><span data-stu-id="585ce-448">\*.\*</span></span>

- <span data-ttu-id="585ce-449">**Jokertecken i mitten:**</span><span class="sxs-lookup"><span data-stu-id="585ce-449">**Middle wildcards**:</span></span>

  - <span data-ttu-id="585ce-450">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="585ce-450">conto\*so.com</span></span>
  - <span data-ttu-id="585ce-451">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="585ce-451">conto~so.com</span></span>

- <span data-ttu-id="585ce-452">**Dubbla jokertecken**</span><span class="sxs-lookup"><span data-stu-id="585ce-452">**Double wildcards**</span></span>

  - <span data-ttu-id="585ce-453">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="585ce-453">contoso.com/\*\*</span></span>
  - <span data-ttu-id="585ce-454">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="585ce-454">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="585ce-455">Domänparsyntax för falska avsändarposter i listan Över tillåtna/blockerade klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="585ce-455">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="585ce-456">Ett domänpar för en förfalskningsavsändare i innehavarlistan över tillåtna/blockerade avsändare har följande syntax: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="585ce-456">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="585ce-457">**Förfalskningsanvändare:** Det här värdet innefattar e-postadressen till den kapade  användaren som visas i rutan Från i e-postklienter.</span><span class="sxs-lookup"><span data-stu-id="585ce-457">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="585ce-458">Den här adressen kallas även `5322.From` för adressen.</span><span class="sxs-lookup"><span data-stu-id="585ce-458">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="585ce-459">Giltiga värden är:</span><span class="sxs-lookup"><span data-stu-id="585ce-459">Valid values include:</span></span>
  - <span data-ttu-id="585ce-460">En enskild e-postadress (till exempel chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="585ce-460">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="585ce-461">En e-postdomän (till exempel contoso.com).</span><span class="sxs-lookup"><span data-stu-id="585ce-461">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="585ce-462">Jokertecknet (till exempel \* ).</span><span class="sxs-lookup"><span data-stu-id="585ce-462">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="585ce-463">**Skicka infrastruktur:** Det här värdet anger källan till meddelanden från den kapade användaren.</span><span class="sxs-lookup"><span data-stu-id="585ce-463">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="585ce-464">Giltiga värden är:</span><span class="sxs-lookup"><span data-stu-id="585ce-464">Valid values include:</span></span>
  - <span data-ttu-id="585ce-465">Domänen som finns i en omvänd DNS-sökning (PTR-post) för käll-e-postserverns IP-adress (till exempel fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="585ce-465">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="585ce-466">Om käll-IP-adressen inte har någon PTR-post identifieras den avsändande infrastrukturen som \<source IP\> /24 (till exempel 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="585ce-466">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="585ce-467">Här är några exempel på giltiga domänpar för att identifiera förfalskningsavsändare:</span><span class="sxs-lookup"><span data-stu-id="585ce-467">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="585ce-468">Genom att lägga till ett domänpar tillåts *eller* blockeras bara kombinationen av den förfalskningsanvändaren *och* avsändarinfrastrukturen.</span><span class="sxs-lookup"><span data-stu-id="585ce-468">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="585ce-469">E-post från förfalskningsanvändare från någon källa tillåts inte heller e-post från den avsändande infrastrukturkällan för någon förfalskningsanvändare.</span><span class="sxs-lookup"><span data-stu-id="585ce-469">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span>

<span data-ttu-id="585ce-470">Du kan till exempel lägga till en tillåt-post för följande domänpar:</span><span class="sxs-lookup"><span data-stu-id="585ce-470">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="585ce-471">**Domän:** gmail.com</span><span class="sxs-lookup"><span data-stu-id="585ce-471">**Domain**: gmail.com</span></span>
- <span data-ttu-id="585ce-472">**Infrastruktur:** tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="585ce-472">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="585ce-473">Endast meddelanden från den *domänen och* sändning av infrastrukturpar tillåts förfalskning.</span><span class="sxs-lookup"><span data-stu-id="585ce-473">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="585ce-474">Andra avsändare som försöker kapa gmail.com-post är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="585ce-474">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="585ce-475">Meddelanden från avsändare i andra domäner med ursprung i tms.mx.com kontrolleras med förfalskningsinformation.</span><span class="sxs-lookup"><span data-stu-id="585ce-475">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
