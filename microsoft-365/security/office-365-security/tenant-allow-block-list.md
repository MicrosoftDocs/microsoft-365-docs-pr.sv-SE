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
ms.openlocfilehash: 2f97308bfc3600e4e85f5ac92d951b12d9a50f24
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928538"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="9e9ad-103">Hantera Klientorganisationens Tillåt/blockera listan</span><span class="sxs-lookup"><span data-stu-id="9e9ad-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9e9ad-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-104">**Applies to**</span></span>
- [<span data-ttu-id="9e9ad-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9e9ad-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9e9ad-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="9e9ad-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="9e9ad-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e9ad-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="9e9ad-108">Funktionerna som beskrivs i den här artikeln är förhandsversioner, kan komma att ändras och är inte tillgängliga i alla organisationer.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="9e9ad-109">Du kan för **stunden inte** konfigurera tillåtna objekt i listan över tillåtna/blockerade klienter.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="9e9ad-110">I Microsoft 365-organisationer som har postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kanske du inte instämmer i EOP-filtreringsrektion.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="9e9ad-111">Till exempel kan ett bra meddelande markeras som dåligt (falskt positivt) eller så kan ett felaktigt meddelande tillåtas (falskt negativt).</span><span class="sxs-lookup"><span data-stu-id="9e9ad-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="9e9ad-112">Med klientorganisationens lista över tillåtna/blockerade & säkerhets- och efterlevnadscenter får du ett sätt att manuellt åsidosätta Microsoft 365-filtreringens bedömningar.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="9e9ad-113">Klientorganisationens lista över tillåtna/blockerade används under e-postflödet och när användaren klickar.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="9e9ad-114">Du kan ange att URL:er eller filer alltid ska blockeras.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="9e9ad-115">I den här artikeln beskrivs hur du konfigurerar poster i listan Över tillåtna/blockerade klientorganisationer i Säkerhets- och efterlevnadscenter för & eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="9e9ad-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9e9ad-116">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="9e9ad-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9e9ad-117">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9e9ad-118">Använd för att gå direkt **till sidan För att tillåta/blockera** klientorganisation. <https://protection.office.com/tenantAllowBlockList></span><span class="sxs-lookup"><span data-stu-id="9e9ad-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="9e9ad-119">Du anger filer genom att använda hashvärdet SHA256 för filen.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="9e9ad-120">Om du vill hitta HASH-värdet för SHA256 för en fil i Windows kör du följande kommando i kommandotolken:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="9e9ad-121">Ett exempelvärde är `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="9e9ad-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="9e9ad-122">Perceptuella hash-värden (pHash) stöds inte.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="9e9ad-123">Tillgängliga URL-värden beskrivs i [URL-syntaxen för avsnittet Tillåt/blockera klientorganisation](#url-syntax-for-the-tenant-allowblock-list) senare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="9e9ad-124">Klientorganisationens lista över tillåtna/blockerade tillåter maximalt 500 poster för URL:er och 500 poster för filshashar.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="9e9ad-125">Det maximala antalet tecken för varje post är:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-125">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="9e9ad-126">Filshashar = 64</span><span class="sxs-lookup"><span data-stu-id="9e9ad-126">File hashes = 64</span></span>
  - <span data-ttu-id="9e9ad-127">URL = 250</span><span class="sxs-lookup"><span data-stu-id="9e9ad-127">URL = 250</span></span>

- <span data-ttu-id="9e9ad-128">En post ska vara aktiv inom 30 minuter.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-128">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="9e9ad-129">Som standard förfaller poster i klientorganisationens lista över tillåtna/blockerade användare efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-129">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="9e9ad-130">Du kan ange ett datum eller ange att de aldrig ska upphöra.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-130">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="9e9ad-131">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9e9ad-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9e9ad-132">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="9e9ad-132">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9e9ad-133">Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-133">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="9e9ad-134">Om du vill lägga till och ta bort värden från klientorganisationens lista över tillåtna/blockerade användare måste du vara medlem i rollgrupperna Organisationshantering eller **Säkerhetsadministratör.** </span><span class="sxs-lookup"><span data-stu-id="9e9ad-134">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="9e9ad-135">För skrivskyddad åtkomst till listan över tillåtna/blockerade klientorganisationer måste du vara medlem i rollgrupperna **Global Reader** **eller Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-135">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="9e9ad-136">Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="9e9ad-136">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="9e9ad-137">Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-137">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="9e9ad-138">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9e9ad-138">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > - <span data-ttu-id="9e9ad-139">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-139">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9e9ad-140">Använd Säkerhets- & kompatibilitetscenter för att skapa URL-poster i listan över tillåtna/blockerade klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="9e9ad-140">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9e9ad-141">Mer information om syntaxen för URL-poster finns i URL-syntaxen för avsnittet [Tillåt/blockera klientorganisation](#url-syntax-for-the-tenant-allowblock-list) längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-141">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="9e9ad-142">I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9e9ad-143">På sidan **Lista över tillåtna/blockerade** klientorganisation kontrollerar du att **fliken URL:er** är markerad och klickar sedan på **Blockera**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-143">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="9e9ad-144">I den **utfällna** menyn Blockera URL:er som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-144">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="9e9ad-145">**Lägg till URL:er som ska** blockeras: Ange en URL per rad, upp till högst 20.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-145">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="9e9ad-146">**Upphör aldrig** att gälla: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-146">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="9e9ad-147">Kontrollera att inställningen är inaktiverad (inaktiverad) och ange utgångsdatumet för posterna ![ ](../../media/scc-toggle-off.png) i rutan Förfaller. </span><span class="sxs-lookup"><span data-stu-id="9e9ad-147">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="9e9ad-148">eller</span><span class="sxs-lookup"><span data-stu-id="9e9ad-148">or</span></span>

     - <span data-ttu-id="9e9ad-149">Flytta reglaget till höger för att konfigurera posterna så att de aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-149">Move the toggle to the right to configure the entries to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png)<span data-ttu-id="9e9ad-151">.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-151">.</span></span>

   - <span data-ttu-id="9e9ad-152">**Valfritt:** Ange beskrivande text för posterna.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-152">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="9e9ad-153">När du är klar klickar du på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-153">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9e9ad-154">Använd Säkerhets- & säkerhets- och efterlevnadscenter för att skapa filposter i klientorganisationens lista över tillåtna/blockerade filer</span><span class="sxs-lookup"><span data-stu-id="9e9ad-154">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="9e9ad-155">I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-155">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9e9ad-156">Välj fliken **Filer på sidan Lista över tillåtna/blockerade** **klientorganisation** och klicka sedan på **Blockera**.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-156">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="9e9ad-157">I den **utfällna menyn** Lägg till filer för att blockera som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-157">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="9e9ad-158">**Lägga till filhashar:** Ange ett SHA256-hashvärde per rad, upp till högst 20.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-158">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="9e9ad-159">**Upphör aldrig** att gälla: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-159">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="9e9ad-160">Kontrollera att inställningen är inaktiverad (inaktiverad) och ange utgångsdatumet för posterna ![ ](../../media/scc-toggle-off.png) i rutan Förfaller. </span><span class="sxs-lookup"><span data-stu-id="9e9ad-160">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="9e9ad-161">eller</span><span class="sxs-lookup"><span data-stu-id="9e9ad-161">or</span></span>

     - <span data-ttu-id="9e9ad-162">Flytta reglaget till höger för att konfigurera posterna så att de aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-162">Move the toggle to the right to configure the entries to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png)<span data-ttu-id="9e9ad-164">.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-164">.</span></span>

   - <span data-ttu-id="9e9ad-165">**Valfritt:** Ange beskrivande text för posterna.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-165">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="9e9ad-166">När du är klar klickar du på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-166">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9e9ad-167">Använd Säkerhets- & kompatibilitetscenter för att visa poster i listan över tillåtna/blockerade klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="9e9ad-167">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="9e9ad-168">I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9e9ad-169">Välj **fliken URL:er** eller **fliken** Filer.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-169">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="9e9ad-170">Klicka på följande kolumnrubriker om du vill sortera stigande eller fallande:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-170">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="9e9ad-171">**Värde:** URL:en eller filens hashtagg.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-171">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="9e9ad-172">**Datum för senaste uppdatering**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-172">**Last updated date**</span></span>
- <span data-ttu-id="9e9ad-173">**Förfallodatum**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-173">**Expiration date**</span></span>
- <span data-ttu-id="9e9ad-174">**Obs!**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-174">**Note**</span></span>

<span data-ttu-id="9e9ad-175">Klicka **på** Sök , ange hela eller en del av ett värde och tryck sedan på RETUR för att hitta ett visst värde.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-175">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="9e9ad-176">När du är klar klickar du på **Rensa sökning Ikonen** Rensa ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) sökning.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-176">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="9e9ad-177">Klicka **på Filtrera**.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-177">Click **Filter**.</span></span> <span data-ttu-id="9e9ad-178">I  den utfällna menyn Filter som visas konfigurerar du någon av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-178">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="9e9ad-179">**Upphör aldrig:** Välj av: ![ Aktivera eller ](../../media/scc-toggle-off.png) inaktivera: Aktivera ![ ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="9e9ad-179">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="9e9ad-180">**Uppdaterades** senast: Välj ett startdatum **(Från),** ett slutdatum **(Till)** eller båda.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-180">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="9e9ad-181">**Förfallodatum:** Välj ett startdatum **(Från),** ett slutdatum **(Till)** eller båda.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-181">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="9e9ad-182">När du är klar klickar du på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-182">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="9e9ad-183">Om du vill ta bort befintliga  **filter klickar** du på Filter och sedan på Rensa filter i den **utfällklara filterfällan som visas.**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-183">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9e9ad-184">Använd Säkerhets- & säkerhets- och efterlevnadscenter för att ändra blockeringsposter i listan över tillåtna/blockerade klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="9e9ad-184">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9e9ad-185">Du kan inte ändra befintliga blockerade URL-adresser eller filvärden i en post.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-185">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="9e9ad-186">Om du vill ändra dessa värden måste du ta bort och återskapa posten.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-186">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="9e9ad-187">I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-187">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9e9ad-188">Välj **fliken URL:er** eller **fliken** Filer.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-188">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="9e9ad-189">Markera den blockpost som du vill  ändra och klicka sedan på redigera ![ redigeringsikonen ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="9e9ad-189">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="9e9ad-190">Konfigurera följande inställningar i den utfäll du vill använda:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-190">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="9e9ad-191">**Upphör aldrig** att gälla: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-191">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="9e9ad-192">Kontrollera att inställningen är inaktiverad (inaktiverad) och ange utgångsdatumet för inmatningen i ![ ](../../media/scc-toggle-off.png) rutan Förfaller. </span><span class="sxs-lookup"><span data-stu-id="9e9ad-192">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

       <span data-ttu-id="9e9ad-193">eller</span><span class="sxs-lookup"><span data-stu-id="9e9ad-193">or</span></span>

     - <span data-ttu-id="9e9ad-194">Flytta reglaget till höger för att konfigurera posten så att den aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-194">Move the toggle to the right to configure the entry to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png)<span data-ttu-id="9e9ad-196">.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-196">.</span></span>

   - <span data-ttu-id="9e9ad-197">**Valfritt:** Ange en beskrivande text för posten.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-197">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="9e9ad-198">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-198">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="9e9ad-199">Använd Säkerhets- & för att ta bort blockeringsposter från listan över tillåtna/blockerade klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="9e9ad-199">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="9e9ad-200">I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-200">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9e9ad-201">Välj **fliken URL:er** eller **fliken** Filer.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-201">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="9e9ad-202">Markera den blockeringspost du vill ta bort och klicka sedan på ikonen **Ta** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) bort.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-202">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="9e9ad-203">Klicka på Ta bort i varningsdialogrutan som **visas.**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-203">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="9e9ad-204">Använd Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera listan över tillåtna/blockerade klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="9e9ad-204">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="9e9ad-205">Använda PowerShell för att lägga till blockeringsposter i innehavarlistan över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="9e9ad-205">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="9e9ad-206">Använd följande syntax för att lägga till blockeringsposter i klientorganisationens lista över tillåtna/blockerade klienter:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-206">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="9e9ad-207">I det här exemplet läggs en blockerings-URL-post till för contoso.com och alla underdomäner (till exempel contoso.com, www.contoso.com och xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9e9ad-207">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="9e9ad-208">Eftersom vi inte använder parametrarna Förfallodatum eller NoExpiration upphör posten att gälla efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-208">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="9e9ad-209">I det här exemplet läggs en post för blockering av filer till för de angivna filerna som aldrig förfaller.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-209">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="9e9ad-210">Detaljerad information om syntax och parametrar finns i [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="9e9ad-210">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9e9ad-211">Använda PowerShell för att visa poster i listan över tillåtna/blockerade klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="9e9ad-211">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9e9ad-212">Om du vill visa poster i listan över tillåtna/blockerade klientorganisationen använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-212">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="9e9ad-213">I det här exemplet returneras alla blockerade URL-adresser.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-213">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="9e9ad-214">Det här exemplet returnerar information om det angivna hash-värdet för filen.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-214">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="9e9ad-215">Detaljerad information om syntax och parametrar finns i [Get-TenantAllowBlockListItems.](/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="9e9ad-215">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9e9ad-216">Använda PowerShell för att ändra blockeringsposter i innehavarlistan över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="9e9ad-216">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9e9ad-217">Du kan inte ändra befintliga URL- eller filvärden inom en blockeringspost.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-217">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="9e9ad-218">Om du vill ändra dessa värden måste du ta bort och återskapa posten.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-218">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="9e9ad-219">Om du vill ändra blockeringsposter i listan över tillåtna/blockerade klientorganisationen använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-219">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="9e9ad-220">I det här exemplet ändras förfallodatumet för den angivna blockposten.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-220">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="9e9ad-221">Detaljerad information om syntax och parametrar finns i [Set-TenantAllowBlockListItems.](/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="9e9ad-221">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="9e9ad-222">Använda PowerShell för att ta bort blockeringsposter från innehavarlistan över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="9e9ad-222">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="9e9ad-223">Använd följande syntax för att ta bort blockeringsposter från klientorganisationens lista över tillåtna/blockerade användare:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-223">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="9e9ad-224">Det här exemplet tar bort den angivna blockerings-URL-posten från klientorganisationens lista över tillåtna/blockerade adresser.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-224">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="9e9ad-225">Detaljerad information om syntax och parametrar finns i [Remove-TenantAllowBlockListItems.](/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="9e9ad-225">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="9e9ad-226">URL-syntax för klientorganisationens lista över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="9e9ad-226">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="9e9ad-227">IP4v- och IPv6-adresser är tillåtna, men INTE TCP-/UDP-portar.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-227">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="9e9ad-228">Filnamnstillägg är inte tillåtna (till exempel test.pdf).</span><span class="sxs-lookup"><span data-stu-id="9e9ad-228">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="9e9ad-229">Unicode stöds inte, men punycode stöds.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-229">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="9e9ad-230">Hostnames tillåts om alla följande uttryck är sanna:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-230">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="9e9ad-231">Värdnamnet innehåller en punkt.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-231">The hostname contains a period.</span></span>
  - <span data-ttu-id="9e9ad-232">Det finns minst ett tecken till vänster om perioden.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-232">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="9e9ad-233">Det finns minst två tecken till höger om perioden.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-233">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="9e9ad-234">Till exempel är `t.co` tillåtet eller `.com` inte `contoso.` tillåtet.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-234">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="9e9ad-235">Undervägar är inte underförstådda.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-235">Subpaths are not implied.</span></span>

  <span data-ttu-id="9e9ad-236">Exempelvis `contoso.com` ingår inte `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="9e9ad-236">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="9e9ad-237">Jokertecken (\*) tillåts i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-237">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="9e9ad-238">Ett vänster jokertecken måste följas av en punkt för att ange en underdomän.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-238">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="9e9ad-239">Är till exempel `*.contoso.com` tillåtet, `*contoso.com` är inte tillåtet.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-239">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="9e9ad-240">Ett höger jokertecken måste följa ett snedstreck (/) om du vill ange en sökväg.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-240">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="9e9ad-241">Till exempel är `contoso.com/*` tillåtet eller `contoso.com*` inte `contoso.com/ab*` tillåtet.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-241">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="9e9ad-242">Alla undervägar kan inte underförstådas med ett rätt jokertecken.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-242">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="9e9ad-243">Exempelvis `contoso.com/*` ingår inte `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="9e9ad-243">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="9e9ad-244">`*.com*` är ogiltig (inte en lösbar domän och att rätt jokertecken inte följer ett snedstreck).</span><span class="sxs-lookup"><span data-stu-id="9e9ad-244">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="9e9ad-245">Jokertecken tillåts inte i IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-245">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="9e9ad-246">Tecknet tilde (~) är tillgängligt i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-246">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="9e9ad-247">Ett vänster tilde-namn antyder en domän och alla underdomäner.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-247">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="9e9ad-248">Exempel: `~contoso.com` inkluderar `contoso.com` och `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="9e9ad-248">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="9e9ad-249">URL-poster som innehåller protokoll (till exempel , eller ) kommer att `http://` `https://` `ftp://` misslyckas, eftersom URL-poster tillämpas på alla protokoll.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-249">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="9e9ad-250">Ett användarnamn eller lösenord stöds inte eller krävs inte.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-250">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="9e9ad-251">Citattecken (' eller ") är ogiltiga tecken.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-251">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="9e9ad-252">En URL bör innehålla alla omdirigeringar där det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-252">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="9e9ad-253">URL-inmatningsscenarier</span><span class="sxs-lookup"><span data-stu-id="9e9ad-253">URL entry scenarios</span></span>

<span data-ttu-id="9e9ad-254">Giltiga URL-poster och deras resultat beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="9e9ad-254">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="9e9ad-255">Scenario: Inga jokertecken</span><span class="sxs-lookup"><span data-stu-id="9e9ad-255">Scenario: No wildcards</span></span>

<span data-ttu-id="9e9ad-256">**Post:**`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="9e9ad-256">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="9e9ad-257">**Tillåt matchning:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-257">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="9e9ad-258">**Tillåt ej matchad:**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-258">**Allow not matched**:</span></span>

  - <span data-ttu-id="9e9ad-259">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-259">abc-contoso.com</span></span>
  - <span data-ttu-id="9e9ad-260">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9e9ad-260">contoso.com/a</span></span>
  - <span data-ttu-id="9e9ad-261">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-261">payroll.contoso.com</span></span>
  - <span data-ttu-id="9e9ad-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="9e9ad-263">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-263">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="9e9ad-264">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-264">www.contoso.com</span></span>
  - <span data-ttu-id="9e9ad-265">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-265">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="9e9ad-266">**Blockmatchning:**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-266">**Block match**:</span></span>

  - <span data-ttu-id="9e9ad-267">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-267">contoso.com</span></span>
  - <span data-ttu-id="9e9ad-268">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9e9ad-268">contoso.com/a</span></span>
  - <span data-ttu-id="9e9ad-269">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-269">payroll.contoso.com</span></span>
  - <span data-ttu-id="9e9ad-270">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-270">test.com/contoso.com</span></span>
  - <span data-ttu-id="9e9ad-271">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-271">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="9e9ad-272">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-272">www.contoso.com</span></span>
  - <span data-ttu-id="9e9ad-273">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-273">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="9e9ad-274">**Blockera matchas inte:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-274">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="9e9ad-275">Scenario: Vänster jokertecken (underdomän)</span><span class="sxs-lookup"><span data-stu-id="9e9ad-275">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="9e9ad-276">**Post:**`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="9e9ad-276">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="9e9ad-277">**Tillåt matchning** och **Blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9e9ad-278">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-278">www.contoso.com</span></span>
  - <span data-ttu-id="9e9ad-279">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-279">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="9e9ad-280">**Tillåt ej matchad** och **Blockera ej matchad:**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-280">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9e9ad-281">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-281">123contoso.com</span></span>
  - <span data-ttu-id="9e9ad-282">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-282">contoso.com</span></span>
  - <span data-ttu-id="9e9ad-283">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-283">test.com/contoso.com</span></span>
  - <span data-ttu-id="9e9ad-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="9e9ad-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="9e9ad-285">Scenario: Höger jokertecken högst upp i sökvägen</span><span class="sxs-lookup"><span data-stu-id="9e9ad-285">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="9e9ad-286">**Post:**`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="9e9ad-286">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="9e9ad-287">**Tillåt matchning** och **Blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9e9ad-288">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="9e9ad-288">contoso.com/a/b</span></span>
  - <span data-ttu-id="9e9ad-289">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="9e9ad-289">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="9e9ad-290">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-290">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="9e9ad-291">**Tillåt ej matchad** och **Blockera ej matchad:**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-291">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9e9ad-292">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-292">contoso.com</span></span>
  - <span data-ttu-id="9e9ad-293">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9e9ad-293">contoso.com/a</span></span>
  - <span data-ttu-id="9e9ad-294">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-294">www.contoso.com</span></span>
  - <span data-ttu-id="9e9ad-295">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-295">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="9e9ad-296">Scenario: Vänster tilde</span><span class="sxs-lookup"><span data-stu-id="9e9ad-296">Scenario: Left tilde</span></span>

<span data-ttu-id="9e9ad-297">**Post:**`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="9e9ad-297">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="9e9ad-298">**Tillåt matchning** och **Blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9e9ad-299">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-299">contoso.com</span></span>
  - <span data-ttu-id="9e9ad-300">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-300">www.contoso.com</span></span>
  - <span data-ttu-id="9e9ad-301">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-301">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="9e9ad-302">**Tillåt ej matchad** och **Blockera ej matchad:**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-302">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9e9ad-303">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-303">123contoso.com</span></span>
  - <span data-ttu-id="9e9ad-304">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="9e9ad-304">contoso.com/abc</span></span>
  - <span data-ttu-id="9e9ad-305">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="9e9ad-305">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="9e9ad-306">Scenario: Höger suffix för jokertecken</span><span class="sxs-lookup"><span data-stu-id="9e9ad-306">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="9e9ad-307">**Post:**`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="9e9ad-307">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="9e9ad-308">**Tillåt matchning** och **Blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9e9ad-309">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-309">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="9e9ad-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9e9ad-310">contoso.com/a</span></span>
  - <span data-ttu-id="9e9ad-311">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="9e9ad-311">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="9e9ad-312">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="9e9ad-312">contoso.com/ab</span></span>
  - <span data-ttu-id="9e9ad-313">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="9e9ad-313">contoso.com/b</span></span>
  - <span data-ttu-id="9e9ad-314">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="9e9ad-314">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="9e9ad-315">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="9e9ad-315">contoso.com/ba</span></span>

- <span data-ttu-id="9e9ad-316">**Tillåt ej matchad** och **Blockera ej matchad**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-316">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="9e9ad-317">Scenario: Vänster underdomän med jokertecken och höger suffix för jokertecken</span><span class="sxs-lookup"><span data-stu-id="9e9ad-317">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="9e9ad-318">**Post:**`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="9e9ad-318">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="9e9ad-319">**Tillåt matchning** och **Blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-319">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9e9ad-320">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="9e9ad-320">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="9e9ad-321">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="9e9ad-321">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="9e9ad-322">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9e9ad-322">www.contoso.com/a</span></span>
  - <span data-ttu-id="9e9ad-323">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="9e9ad-323">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="9e9ad-324">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="9e9ad-324">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="9e9ad-325">**Tillåt ej matchad** och **Blockera ej matchad**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="9e9ad-325">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="9e9ad-326">Scenario: Vänster och höger tilde</span><span class="sxs-lookup"><span data-stu-id="9e9ad-326">Scenario: Left and right tilde</span></span>

<span data-ttu-id="9e9ad-327">**Post:**`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="9e9ad-327">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="9e9ad-328">**Tillåt matchning** och **Blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-328">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9e9ad-329">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-329">contoso.com</span></span>
  - <span data-ttu-id="9e9ad-330">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9e9ad-330">contoso.com/a</span></span>
  - <span data-ttu-id="9e9ad-331">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-331">www.contoso.com</span></span>
  - <span data-ttu-id="9e9ad-332">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="9e9ad-332">www.contoso.com/b</span></span>
  - <span data-ttu-id="9e9ad-333">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-333">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="9e9ad-334">**Tillåt ej matchad** och **Blockera ej matchad:**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-334">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9e9ad-335">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-335">123contoso.com</span></span>
  - <span data-ttu-id="9e9ad-336">contoso.org</span><span class="sxs-lookup"><span data-stu-id="9e9ad-336">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="9e9ad-337">Scenario: IP-adress</span><span class="sxs-lookup"><span data-stu-id="9e9ad-337">Scenario: IP address</span></span>

<span data-ttu-id="9e9ad-338">**Post:**`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="9e9ad-338">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="9e9ad-339">**Tillåt matchning** och **Blockeringsmatchning**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="9e9ad-339">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="9e9ad-340">**Tillåt ej matchad** och **Blockera ej matchad:**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-340">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9e9ad-341">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="9e9ad-341">1.2.3.4/a</span></span>
  - <span data-ttu-id="9e9ad-342">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="9e9ad-342">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="9e9ad-343">IP-adress med rätt jokertecken</span><span class="sxs-lookup"><span data-stu-id="9e9ad-343">IP address with right wildcard</span></span>

<span data-ttu-id="9e9ad-344">**Post:**`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="9e9ad-344">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="9e9ad-345">**Tillåt matchning** och **Blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-345">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9e9ad-346">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="9e9ad-346">1.2.3.4/b</span></span>
  - <span data-ttu-id="9e9ad-347">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="9e9ad-347">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="9e9ad-348">Exempel på ogiltiga poster</span><span class="sxs-lookup"><span data-stu-id="9e9ad-348">Examples of invalid entries</span></span>

<span data-ttu-id="9e9ad-349">Följande poster är ogiltiga:</span><span class="sxs-lookup"><span data-stu-id="9e9ad-349">The following entries are invalid:</span></span>

- <span data-ttu-id="9e9ad-350">**Värden som saknas eller är ogiltiga:**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-350">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="9e9ad-351">contoso</span><span class="sxs-lookup"><span data-stu-id="9e9ad-351">contoso</span></span>
  - <span data-ttu-id="9e9ad-352">\*CONTOSO.\*</span><span class="sxs-lookup"><span data-stu-id="9e9ad-352">\*.contoso.\*</span></span>
  - <span data-ttu-id="9e9ad-353">\*.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-353">\*.com</span></span>
  - <span data-ttu-id="9e9ad-354">\*PDF</span><span class="sxs-lookup"><span data-stu-id="9e9ad-354">\*.pdf</span></span>

- <span data-ttu-id="9e9ad-355">**Jokertecken på text eller utan avståndstecken:**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-355">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="9e9ad-356">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-356">\*contoso.com</span></span>
  - <span data-ttu-id="9e9ad-357">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="9e9ad-357">contoso.com\*</span></span>
  - <span data-ttu-id="9e9ad-358">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="9e9ad-358">\*1.2.3.4</span></span>
  - <span data-ttu-id="9e9ad-359">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="9e9ad-359">1.2.3.4\*</span></span>
  - <span data-ttu-id="9e9ad-360">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="9e9ad-360">contoso.com/a\*</span></span>
  - <span data-ttu-id="9e9ad-361">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="9e9ad-361">contoso.com/ab\*</span></span>

- <span data-ttu-id="9e9ad-362">**IP-adresser med portar:**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-362">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="9e9ad-363">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="9e9ad-363">contoso.com:443</span></span>
  - <span data-ttu-id="9e9ad-364">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="9e9ad-364">abc.contoso.com:25</span></span>

- <span data-ttu-id="9e9ad-365">**Icke-beskrivande jokertecken:**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-365">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="9e9ad-366">\*.\*</span><span class="sxs-lookup"><span data-stu-id="9e9ad-366">\*.\*</span></span>

- <span data-ttu-id="9e9ad-367">**Jokertecken i mitten:**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-367">**Middle wildcards**:</span></span>

  - <span data-ttu-id="9e9ad-368">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-368">conto\*so.com</span></span>
  - <span data-ttu-id="9e9ad-369">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="9e9ad-369">conto~so.com</span></span>

- <span data-ttu-id="9e9ad-370">**Dubbla jokertecken**</span><span class="sxs-lookup"><span data-stu-id="9e9ad-370">**Double wildcards**</span></span>

  - <span data-ttu-id="9e9ad-371">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="9e9ad-371">contoso.com/\*\*</span></span>
  - <span data-ttu-id="9e9ad-372">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="9e9ad-372">contoso.com/\*/\*</span></span>