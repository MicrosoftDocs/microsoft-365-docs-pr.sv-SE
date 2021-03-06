---
title: Hantera dina tillåtna och block i klientorganisationens lista över tillåtna/blockerade
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
description: Administratörer kan ta reda på hur de konfigurerar tillåts och spärras i listan över tillåtna eller blockerade klienter i säkerhetsportalen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 20e460f4e93f7b87faaead8b87ba561224e38938
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515214"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="f79cd-103">Hantera Klientorganisationens Tillåt/blockera listan</span><span class="sxs-lookup"><span data-stu-id="f79cd-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f79cd-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="f79cd-104">**Applies to**</span></span>
- [<span data-ttu-id="f79cd-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f79cd-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f79cd-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="f79cd-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="f79cd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f79cd-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="f79cd-108">Funktionerna som beskrivs i den här artikeln är förhandsversioner, kan komma att ändras och är inte tillgängliga i alla organisationer.</span><span class="sxs-lookup"><span data-stu-id="f79cd-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="f79cd-109">Du kan för **stunden inte** konfigurera tillåtna objekt i klientorganisationens lista över tillåtna/blockerade objekt.</span><span class="sxs-lookup"><span data-stu-id="f79cd-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="f79cd-110">I Microsoft 365-organisationer som har postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kanske du inte håller med om EOP-filtreringens bedömning.</span><span class="sxs-lookup"><span data-stu-id="f79cd-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="f79cd-111">Ett bra meddelande kan till exempel markeras som dåligt (falskt positivt) eller så kan ett felaktigt meddelande tillåtas (falskt negativa).</span><span class="sxs-lookup"><span data-stu-id="f79cd-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="f79cd-112">Klientorganisationens lista över tillåtna/blockerade i Säkerhets- & efterlevnadscenter ger dig ett sätt att manuellt åsidosätta filtreringsvillkoren i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f79cd-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="f79cd-113">Klientorganisationens lista över tillåtna/blockerade används under e-postflödet och när användaren klickar.</span><span class="sxs-lookup"><span data-stu-id="f79cd-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="f79cd-114">Du kan ange URL:er eller filer som alltid ska blockeras.</span><span class="sxs-lookup"><span data-stu-id="f79cd-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="f79cd-115">I den här artikeln beskrivs hur du konfigurerar poster i listan över tillåtna och blockerade klientorganisationer i Säkerhets- & och efterlevnadscenter eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="f79cd-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f79cd-116">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="f79cd-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f79cd-117">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f79cd-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f79cd-118">Om du vill gå direkt **till sidan Tillåt/blockera klientorganisation** använder du <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="f79cd-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="f79cd-119">Du anger filer med hjälp av SHA256-hashvärdet för filen.</span><span class="sxs-lookup"><span data-stu-id="f79cd-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="f79cd-120">Om du vill hitta SHA256-hashvärdet för en fil i Windows kör du följande kommando i en kommandotolk:</span><span class="sxs-lookup"><span data-stu-id="f79cd-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="f79cd-121">Ett exempelvärde är `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="f79cd-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="f79cd-122">Värden för perceptuell hash (pHash) stöds inte.</span><span class="sxs-lookup"><span data-stu-id="f79cd-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="f79cd-123">Tillgängliga URL-värden beskrivs i [URL-syntaxen för avsnittet Tillåt/blockera klientorganisation senare](#url-syntax-for-the-tenant-allowblock-list) i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="f79cd-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="f79cd-124">Klientorganisationens lista över tillåtna/blockerade kan högst 500 poster för URL:er och 500 poster för filshashar.</span><span class="sxs-lookup"><span data-stu-id="f79cd-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="f79cd-125">Det maximala antalet tecken för varje post är:</span><span class="sxs-lookup"><span data-stu-id="f79cd-125">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="f79cd-126">Filshashar = 64</span><span class="sxs-lookup"><span data-stu-id="f79cd-126">File hashes = 64</span></span>
  - <span data-ttu-id="f79cd-127">URL = 250</span><span class="sxs-lookup"><span data-stu-id="f79cd-127">URL = 250</span></span>

- <span data-ttu-id="f79cd-128">En post ska vara aktiv inom 30 minuter.</span><span class="sxs-lookup"><span data-stu-id="f79cd-128">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="f79cd-129">Som standard förfaller poster i klientorganisationens lista över tillåtna/blockerade poster efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="f79cd-129">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="f79cd-130">Du kan ange ett datum eller ange att de aldrig ska upphöra att gälla.</span><span class="sxs-lookup"><span data-stu-id="f79cd-130">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="f79cd-131">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f79cd-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f79cd-132">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="f79cd-132">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f79cd-133">Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="f79cd-133">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f79cd-134">Om du vill lägga till och ta bort värden från klientorganisationens lista över tillåtna/blockerade måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="f79cd-134">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="f79cd-135">För skrivskyddad åtkomst till klientorganisationens lista över tillåtna/blockerade måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="f79cd-135">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="f79cd-136">Mer information finns under [Behörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="f79cd-136">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="f79cd-137">Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f79cd-137">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f79cd-138">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f79cd-138">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > - <span data-ttu-id="f79cd-139">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="f79cd-139">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f79cd-140">Använd Säkerhets- & center för att skapa URL-poster i klientorganisationens lista över tillåtna/blockerade adresser</span><span class="sxs-lookup"><span data-stu-id="f79cd-140">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f79cd-141">Mer information om syntaxen för URL-poster finns i URL-syntaxen för avsnittet [Tillåt/blockera klientorganisation](#url-syntax-for-the-tenant-allowblock-list) senare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="f79cd-141">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="f79cd-142">Gå till innehavarlistan & över  tillåtna och blockerade hothanteringsprinciper i Säkerhets- \>  \> **och efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="f79cd-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f79cd-143">Kontrollera att **fliken URL:er är** markerad på sidan **Tillåt/blockera** klientorganisation och klicka sedan på **Blockera**</span><span class="sxs-lookup"><span data-stu-id="f79cd-143">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="f79cd-144">I den **utfällna** menyn Blockera URL:er som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f79cd-144">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f79cd-145">**Lägg till URL-adresser som** ska blockeras: Ange en URL per rad, upp till maximalt 20.</span><span class="sxs-lookup"><span data-stu-id="f79cd-145">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="f79cd-146">**Upphör aldrig** att gälla: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="f79cd-146">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f79cd-147">Kontrollera att inställningen är inaktiverad (inaktiverad) och ange ![ ](../../media/scc-toggle-off.png) **utgångsdatumet** för posterna med hjälp av rutan Förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="f79cd-147">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="f79cd-148">eller</span><span class="sxs-lookup"><span data-stu-id="f79cd-148">or</span></span>

     - <span data-ttu-id="f79cd-149">Flytta reglaget till höger för att konfigurera posterna så att de aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="f79cd-149">Move the toggle to the right to configure the entries to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png)<span data-ttu-id="f79cd-151">.</span><span class="sxs-lookup"><span data-stu-id="f79cd-151">.</span></span>

   - <span data-ttu-id="f79cd-152">**Valfritt:** Ange beskrivande text för posterna.</span><span class="sxs-lookup"><span data-stu-id="f79cd-152">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="f79cd-153">Klicka på Lägg till när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="f79cd-153">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f79cd-154">Använd Säkerhets- & Center för efterlevnad för att skapa filposter i klientorganisationens lista över tillåtna/blockerade filer</span><span class="sxs-lookup"><span data-stu-id="f79cd-154">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f79cd-155">Gå till innehavarlistan & över  tillåtna och blockerade hothanteringsprinciper i Säkerhets- \>  \> **och efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="f79cd-155">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f79cd-156">Välj fliken **Filer på sidan Tillåt/blockera** **för** klientorganisation och klicka sedan på **Blockera.**</span><span class="sxs-lookup"><span data-stu-id="f79cd-156">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="f79cd-157">I den **utfällna menyn** Lägg till filer för att blockera som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f79cd-157">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f79cd-158">**Lägga till filshashar:** Ange ett SHA256-hashvärde per rad, upp till maximalt 20.</span><span class="sxs-lookup"><span data-stu-id="f79cd-158">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="f79cd-159">**Upphör aldrig** att gälla: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="f79cd-159">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f79cd-160">Kontrollera att inställningen är inaktiverad (inaktiverad) och ange ![ ](../../media/scc-toggle-off.png) **utgångsdatumet** för posterna med hjälp av rutan Förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="f79cd-160">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="f79cd-161">eller</span><span class="sxs-lookup"><span data-stu-id="f79cd-161">or</span></span>

     - <span data-ttu-id="f79cd-162">Flytta reglaget till höger för att konfigurera posterna så att de aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="f79cd-162">Move the toggle to the right to configure the entries to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png)<span data-ttu-id="f79cd-164">.</span><span class="sxs-lookup"><span data-stu-id="f79cd-164">.</span></span>

   - <span data-ttu-id="f79cd-165">**Valfritt:** Ange beskrivande text för posterna.</span><span class="sxs-lookup"><span data-stu-id="f79cd-165">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="f79cd-166">Klicka på Lägg till när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="f79cd-166">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f79cd-167">Använd Säkerhets- & efterlevnadscenter för att visa poster i klientorganisationens lista över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="f79cd-167">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f79cd-168">Gå till innehavarlistan & över  tillåtna och blockerade hothanteringsprinciper i Säkerhets- \>  \> **och efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="f79cd-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f79cd-169">Välj **fliken URL:er** eller **fliken** Filer.</span><span class="sxs-lookup"><span data-stu-id="f79cd-169">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="f79cd-170">Klicka på följande kolumnrubriker för att sortera i stigande eller fallande ordning:</span><span class="sxs-lookup"><span data-stu-id="f79cd-170">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="f79cd-171">**Värde:** URL:en eller filens hashtagg.</span><span class="sxs-lookup"><span data-stu-id="f79cd-171">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="f79cd-172">**Datum för senaste uppdatering**</span><span class="sxs-lookup"><span data-stu-id="f79cd-172">**Last updated date**</span></span>
- <span data-ttu-id="f79cd-173">**Förfallodatum**</span><span class="sxs-lookup"><span data-stu-id="f79cd-173">**Expiration date**</span></span>
- <span data-ttu-id="f79cd-174">**Obs!**</span><span class="sxs-lookup"><span data-stu-id="f79cd-174">**Note**</span></span>

<span data-ttu-id="f79cd-175">Klicka **på Sök,** ange hela eller en del av ett värde och tryck sedan på RETUR för att hitta ett visst värde.</span><span class="sxs-lookup"><span data-stu-id="f79cd-175">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="f79cd-176">När du är klar klickar du på **ikonen Rensa** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) sökning.</span><span class="sxs-lookup"><span data-stu-id="f79cd-176">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="f79cd-177">Klicka **på Filtrera.**</span><span class="sxs-lookup"><span data-stu-id="f79cd-177">Click **Filter**.</span></span> <span data-ttu-id="f79cd-178">I den **utfällna** menyn Filter som visas konfigurerar du någon av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f79cd-178">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="f79cd-179">**Upphör aldrig** att gälla: Välj ![ av: Aktivera ](../../media/scc-toggle-off.png) eller ![ ](../../media/scc-toggle-on.png) inaktivera.</span><span class="sxs-lookup"><span data-stu-id="f79cd-179">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="f79cd-180">**Senast uppdaterad:** Välj ett startdatum **(Från),** ett slutdatum **(Till)** eller både och.</span><span class="sxs-lookup"><span data-stu-id="f79cd-180">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="f79cd-181">**Förfallodatum:** Välj ett startdatum **(Från),** ett slutdatum **(Till)** eller båda.</span><span class="sxs-lookup"><span data-stu-id="f79cd-181">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="f79cd-182">Klicka på Använd när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="f79cd-182">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="f79cd-183">Om du vill ta bort befintliga  **filter klickar** du på Filter och sedan på Rensa filter i den **utfällklara filterfällan som visas.**</span><span class="sxs-lookup"><span data-stu-id="f79cd-183">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f79cd-184">Använd Säkerhets- & Center för efterlevnad för att ändra blockeringsposter i klientorganisationens lista över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="f79cd-184">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f79cd-185">Du kan inte ändra befintliga blockerade URL-adresser eller filvärden i en post.</span><span class="sxs-lookup"><span data-stu-id="f79cd-185">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="f79cd-186">Om du vill ändra dessa värden måste du ta bort och återskapa posten.</span><span class="sxs-lookup"><span data-stu-id="f79cd-186">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="f79cd-187">Gå till innehavarlistan & över  tillåtna och blockerade hothanteringsprinciper i Säkerhets- \>  \> **och efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="f79cd-187">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f79cd-188">Välj **fliken URL:er** eller **fliken** Filer.</span><span class="sxs-lookup"><span data-stu-id="f79cd-188">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="f79cd-189">Markera den blockpost som du vill ändra och klicka sedan **på** ikonen ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) Redigera.</span><span class="sxs-lookup"><span data-stu-id="f79cd-189">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="f79cd-190">Konfigurera följande inställningar i den utfällo som visas:</span><span class="sxs-lookup"><span data-stu-id="f79cd-190">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f79cd-191">**Upphör aldrig** att gälla: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="f79cd-191">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f79cd-192">Kontrollera att inställningen är inaktiverad (inaktiverad) och ange förfallodatumet med hjälp av rutan ![ ](../../media/scc-toggle-off.png) Förfallodatum. </span><span class="sxs-lookup"><span data-stu-id="f79cd-192">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

       <span data-ttu-id="f79cd-193">eller</span><span class="sxs-lookup"><span data-stu-id="f79cd-193">or</span></span>

     - <span data-ttu-id="f79cd-194">Flytta reglaget till höger för att konfigurera posten så att den aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="f79cd-194">Move the toggle to the right to configure the entry to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png)<span data-ttu-id="f79cd-196">.</span><span class="sxs-lookup"><span data-stu-id="f79cd-196">.</span></span>

   - <span data-ttu-id="f79cd-197">**Valfritt** meddelande: Ange beskrivande text för posten.</span><span class="sxs-lookup"><span data-stu-id="f79cd-197">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="f79cd-198">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="f79cd-198">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f79cd-199">Använda Säkerhets- & för att ta bort blockeringsposter från klientorganisationens lista över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="f79cd-199">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f79cd-200">Gå till innehavarlistan & över  tillåtna och blockerade hothanteringsprinciper i Säkerhets- \>  \> **och efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="f79cd-200">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f79cd-201">Välj **fliken URL:er** eller **fliken** Filer.</span><span class="sxs-lookup"><span data-stu-id="f79cd-201">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="f79cd-202">Markera den blockpost du vill ta bort och klicka sedan på ikonen **Ta** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) bort.</span><span class="sxs-lookup"><span data-stu-id="f79cd-202">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="f79cd-203">Klicka på Ta bort i **varningsdialogrutan som visas.**</span><span class="sxs-lookup"><span data-stu-id="f79cd-203">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="f79cd-204">Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera klientorganisationens lista över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="f79cd-204">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="f79cd-205">Använda PowerShell för att lägga till blockeringsposter i klientorganisationens lista över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="f79cd-205">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="f79cd-206">Använd följande syntax för att lägga till blockeringsposter i klientorganisationens lista över tillåtna/blockerade:</span><span class="sxs-lookup"><span data-stu-id="f79cd-206">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="f79cd-207">Det här exemplet lägger till en blockerings-URL-post för contoso.com och alla underdomäner (till exempel contoso.com, www.contoso.com och xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f79cd-207">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="f79cd-208">Eftersom vi inte använder parametrarna Förfallodatum eller NoExpiration går posten ut efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="f79cd-208">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="f79cd-209">I det här exemplet läggs en blockeringsfilpost till för de angivna filerna som aldrig förfaller.</span><span class="sxs-lookup"><span data-stu-id="f79cd-209">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="f79cd-210">Detaljerad information om syntax och parametrar finns i [New-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="f79cd-210">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f79cd-211">Använda PowerShell för att visa poster i klientorganisationens lista över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="f79cd-211">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f79cd-212">För att visa poster i klientorganisationens lista över tillåtna/blockerade, använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="f79cd-212">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="f79cd-213">I det här exemplet returneras alla blockerade URL:er.</span><span class="sxs-lookup"><span data-stu-id="f79cd-213">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="f79cd-214">Det här exemplet returnerar information för det angivna hashvärdet för filen.</span><span class="sxs-lookup"><span data-stu-id="f79cd-214">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="f79cd-215">Detaljerad information om syntax och parametrar finns i [Get-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="f79cd-215">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f79cd-216">Använda PowerShell för att ändra blockeringsposter i klientorganisationens lista över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="f79cd-216">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f79cd-217">Du kan inte ändra befintliga URL- eller filvärden inom en blockeringspost.</span><span class="sxs-lookup"><span data-stu-id="f79cd-217">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="f79cd-218">Om du vill ändra dessa värden måste du ta bort och återskapa posten.</span><span class="sxs-lookup"><span data-stu-id="f79cd-218">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="f79cd-219">Använd följande syntax för att ändra blockeringsposter i klientorganisationens lista över tillåtna/blockerade:</span><span class="sxs-lookup"><span data-stu-id="f79cd-219">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="f79cd-220">I det här exemplet ändras förfallodatumet för den angivna blockeringsposten.</span><span class="sxs-lookup"><span data-stu-id="f79cd-220">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="f79cd-221">Detaljerad information om syntax och parametrar finns i [Set-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="f79cd-221">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f79cd-222">Använda PowerShell för att ta bort blockeringsposter från klientorganisationens lista över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="f79cd-222">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="f79cd-223">Använd följande syntax för att ta bort blockeringsposter från klientorganisationens lista över tillåtna/blockerade:</span><span class="sxs-lookup"><span data-stu-id="f79cd-223">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="f79cd-224">I det här exemplet tas den angivna blockerings-URL-posten bort från klientorganisationens lista över tillåtna/blockerade adresser.</span><span class="sxs-lookup"><span data-stu-id="f79cd-224">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="f79cd-225">Detaljerad information om syntax och parametrar finns i [Remove-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="f79cd-225">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="f79cd-226">URL-syntax för klientorganisationens lista över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="f79cd-226">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="f79cd-227">IP4v- och IPv6-adresser är tillåtna, men TCP-/UDP-portar är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="f79cd-227">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="f79cd-228">Filnamnstillägg är inte tillåtna (till exempel test.pdf).</span><span class="sxs-lookup"><span data-stu-id="f79cd-228">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="f79cd-229">Unicode stöds inte, men punycode stöds.</span><span class="sxs-lookup"><span data-stu-id="f79cd-229">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="f79cd-230">Hostnames tillåts om alla följande uttryck är sanna:</span><span class="sxs-lookup"><span data-stu-id="f79cd-230">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="f79cd-231">Värdnamnet innehåller en punkt.</span><span class="sxs-lookup"><span data-stu-id="f79cd-231">The hostname contains a period.</span></span>
  - <span data-ttu-id="f79cd-232">Det finns minst ett tecken till vänster om perioden.</span><span class="sxs-lookup"><span data-stu-id="f79cd-232">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="f79cd-233">Det finns minst två tecken till höger om perioden.</span><span class="sxs-lookup"><span data-stu-id="f79cd-233">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="f79cd-234">Till exempel är `t.co` tillåtet eller `.com` är inte `contoso.` tillåtet.</span><span class="sxs-lookup"><span data-stu-id="f79cd-234">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="f79cd-235">Undervägar är inte underförstådda.</span><span class="sxs-lookup"><span data-stu-id="f79cd-235">Subpaths are not implied.</span></span>

  <span data-ttu-id="f79cd-236">Exempel: `contoso.com` Inkluderar inte `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="f79cd-236">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="f79cd-237">Jokertecken (\*) tillåts i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="f79cd-237">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="f79cd-238">Ett vänster jokertecken måste följas av en punkt för att ange en underdomän.</span><span class="sxs-lookup"><span data-stu-id="f79cd-238">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="f79cd-239">Till exempel `*.contoso.com` tillåts, `*contoso.com` är inte tillåtet.</span><span class="sxs-lookup"><span data-stu-id="f79cd-239">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="f79cd-240">Ett höger jokertecken måste följa ett snedstreck (/) för att ange en sökväg.</span><span class="sxs-lookup"><span data-stu-id="f79cd-240">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="f79cd-241">Till exempel är `contoso.com/*` tillåtet eller `contoso.com*` är inte `contoso.com/ab*` tillåtet.</span><span class="sxs-lookup"><span data-stu-id="f79cd-241">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="f79cd-242">Alla undervägar är inte underförstådda med ett rätt jokertecken.</span><span class="sxs-lookup"><span data-stu-id="f79cd-242">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="f79cd-243">Exempel: `contoso.com/*` Inkluderar inte `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="f79cd-243">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="f79cd-244">`*.com*` är ogiltig (inte en lösbar domän och rätt jokertecken följer inte ett snedstreck).</span><span class="sxs-lookup"><span data-stu-id="f79cd-244">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="f79cd-245">Jokertecken är inte tillåtna i IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="f79cd-245">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="f79cd-246">Tecknet tilde (~) är tillgängligt i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="f79cd-246">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="f79cd-247">Ett vänster tilde-namn antyder en domän och alla underdomäner.</span><span class="sxs-lookup"><span data-stu-id="f79cd-247">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="f79cd-248">Exempel: `~contoso.com` `contoso.com` innehåller och `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="f79cd-248">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="f79cd-249">URL-poster som innehåller protokoll (till exempel, eller ) kommer att `http://` `https://` `ftp://` misslyckas, eftersom URL-poster gäller för alla protokoll.</span><span class="sxs-lookup"><span data-stu-id="f79cd-249">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="f79cd-250">Ett användarnamn eller lösenord stöds inte eller krävs inte.</span><span class="sxs-lookup"><span data-stu-id="f79cd-250">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="f79cd-251">Citattecken (' eller ") är ogiltiga tecken.</span><span class="sxs-lookup"><span data-stu-id="f79cd-251">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="f79cd-252">En URL bör innehålla alla omdirigeringar om det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="f79cd-252">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="f79cd-253">URL-inmatningsscenarier</span><span class="sxs-lookup"><span data-stu-id="f79cd-253">URL entry scenarios</span></span>

<span data-ttu-id="f79cd-254">Giltiga URL-poster och deras resultat beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="f79cd-254">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="f79cd-255">Scenario: Inga jokertecken</span><span class="sxs-lookup"><span data-stu-id="f79cd-255">Scenario: No wildcards</span></span>

<span data-ttu-id="f79cd-256">**Post:**`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f79cd-256">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="f79cd-257">**Tillåt matchning:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-257">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="f79cd-258">**Tillåt ej matchad:**</span><span class="sxs-lookup"><span data-stu-id="f79cd-258">**Allow not matched**:</span></span>

  - <span data-ttu-id="f79cd-259">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-259">abc-contoso.com</span></span>
  - <span data-ttu-id="f79cd-260">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f79cd-260">contoso.com/a</span></span>
  - <span data-ttu-id="f79cd-261">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-261">payroll.contoso.com</span></span>
  - <span data-ttu-id="f79cd-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="f79cd-263">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-263">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="f79cd-264">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-264">www.contoso.com</span></span>
  - <span data-ttu-id="f79cd-265">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-265">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="f79cd-266">**Blockmatchning:**</span><span class="sxs-lookup"><span data-stu-id="f79cd-266">**Block match**:</span></span>

  - <span data-ttu-id="f79cd-267">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-267">contoso.com</span></span>
  - <span data-ttu-id="f79cd-268">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f79cd-268">contoso.com/a</span></span>
  - <span data-ttu-id="f79cd-269">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-269">payroll.contoso.com</span></span>
  - <span data-ttu-id="f79cd-270">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-270">test.com/contoso.com</span></span>
  - <span data-ttu-id="f79cd-271">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-271">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="f79cd-272">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-272">www.contoso.com</span></span>
  - <span data-ttu-id="f79cd-273">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-273">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="f79cd-274">**Blocket matchas inte:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-274">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="f79cd-275">Scenario: Vänster jokertecken (underdomän)</span><span class="sxs-lookup"><span data-stu-id="f79cd-275">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="f79cd-276">**Post:**`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f79cd-276">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="f79cd-277">**Tillåt matchning** och **blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="f79cd-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f79cd-278">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-278">www.contoso.com</span></span>
  - <span data-ttu-id="f79cd-279">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-279">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f79cd-280">**Tillåt ej matchad** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="f79cd-280">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f79cd-281">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-281">123contoso.com</span></span>
  - <span data-ttu-id="f79cd-282">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-282">contoso.com</span></span>
  - <span data-ttu-id="f79cd-283">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-283">test.com/contoso.com</span></span>
  - <span data-ttu-id="f79cd-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f79cd-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="f79cd-285">Scenario: Höger jokertecken högst upp i sökvägen</span><span class="sxs-lookup"><span data-stu-id="f79cd-285">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="f79cd-286">**Post:**`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="f79cd-286">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="f79cd-287">**Tillåt matchning** och **blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="f79cd-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f79cd-288">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="f79cd-288">contoso.com/a/b</span></span>
  - <span data-ttu-id="f79cd-289">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f79cd-289">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f79cd-290">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-290">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="f79cd-291">**Tillåt ej matchad** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="f79cd-291">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f79cd-292">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-292">contoso.com</span></span>
  - <span data-ttu-id="f79cd-293">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f79cd-293">contoso.com/a</span></span>
  - <span data-ttu-id="f79cd-294">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-294">www.contoso.com</span></span>
  - <span data-ttu-id="f79cd-295">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-295">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="f79cd-296">Scenario: Vänster tilde</span><span class="sxs-lookup"><span data-stu-id="f79cd-296">Scenario: Left tilde</span></span>

<span data-ttu-id="f79cd-297">**Post:**`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f79cd-297">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="f79cd-298">**Tillåt matchning** och **blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="f79cd-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f79cd-299">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-299">contoso.com</span></span>
  - <span data-ttu-id="f79cd-300">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-300">www.contoso.com</span></span>
  - <span data-ttu-id="f79cd-301">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-301">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f79cd-302">**Tillåt ej matchad** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="f79cd-302">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f79cd-303">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-303">123contoso.com</span></span>
  - <span data-ttu-id="f79cd-304">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f79cd-304">contoso.com/abc</span></span>
  - <span data-ttu-id="f79cd-305">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f79cd-305">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="f79cd-306">Scenario: Höger suffix för jokertecken</span><span class="sxs-lookup"><span data-stu-id="f79cd-306">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="f79cd-307">**Post:**`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="f79cd-307">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="f79cd-308">**Tillåt matchning** och **blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="f79cd-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f79cd-309">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-309">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="f79cd-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f79cd-310">contoso.com/a</span></span>
  - <span data-ttu-id="f79cd-311">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f79cd-311">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f79cd-312">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="f79cd-312">contoso.com/ab</span></span>
  - <span data-ttu-id="f79cd-313">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f79cd-313">contoso.com/b</span></span>
  - <span data-ttu-id="f79cd-314">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="f79cd-314">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="f79cd-315">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="f79cd-315">contoso.com/ba</span></span>

- <span data-ttu-id="f79cd-316">**Tillåt ej matchad** och **Blockera matchas inte:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-316">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="f79cd-317">Scenario: Underdomän för vänster jokertecken och höger suffix för jokertecken</span><span class="sxs-lookup"><span data-stu-id="f79cd-317">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="f79cd-318">**Post:**`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="f79cd-318">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="f79cd-319">**Tillåt matchning** och **blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="f79cd-319">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f79cd-320">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="f79cd-320">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="f79cd-321">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f79cd-321">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f79cd-322">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f79cd-322">www.contoso.com/a</span></span>
  - <span data-ttu-id="f79cd-323">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="f79cd-323">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="f79cd-324">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="f79cd-324">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="f79cd-325">**Tillåt ej matchad** och **Blockera matchas inte:** contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f79cd-325">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="f79cd-326">Scenario: Vänster och höger tilde</span><span class="sxs-lookup"><span data-stu-id="f79cd-326">Scenario: Left and right tilde</span></span>

<span data-ttu-id="f79cd-327">**Post:**`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="f79cd-327">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="f79cd-328">**Tillåt matchning** och **blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="f79cd-328">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f79cd-329">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-329">contoso.com</span></span>
  - <span data-ttu-id="f79cd-330">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f79cd-330">contoso.com/a</span></span>
  - <span data-ttu-id="f79cd-331">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-331">www.contoso.com</span></span>
  - <span data-ttu-id="f79cd-332">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f79cd-332">www.contoso.com/b</span></span>
  - <span data-ttu-id="f79cd-333">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-333">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f79cd-334">**Tillåt ej matchad** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="f79cd-334">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f79cd-335">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-335">123contoso.com</span></span>
  - <span data-ttu-id="f79cd-336">contoso.org</span><span class="sxs-lookup"><span data-stu-id="f79cd-336">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="f79cd-337">Scenario: IP-adress</span><span class="sxs-lookup"><span data-stu-id="f79cd-337">Scenario: IP address</span></span>

<span data-ttu-id="f79cd-338">**Post:**`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="f79cd-338">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="f79cd-339">**Tillåt matchning** och **blockeringsmatchning:** 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="f79cd-339">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="f79cd-340">**Tillåt ej matchad** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="f79cd-340">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f79cd-341">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="f79cd-341">1.2.3.4/a</span></span>
  - <span data-ttu-id="f79cd-342">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="f79cd-342">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="f79cd-343">IP-adress med rätt jokertecken</span><span class="sxs-lookup"><span data-stu-id="f79cd-343">IP address with right wildcard</span></span>

<span data-ttu-id="f79cd-344">**Post:**`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="f79cd-344">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="f79cd-345">**Tillåt matchning** och **blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="f79cd-345">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f79cd-346">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="f79cd-346">1.2.3.4/b</span></span>
  - <span data-ttu-id="f79cd-347">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="f79cd-347">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="f79cd-348">Exempel på ogiltiga poster</span><span class="sxs-lookup"><span data-stu-id="f79cd-348">Examples of invalid entries</span></span>

<span data-ttu-id="f79cd-349">Följande poster är ogiltiga:</span><span class="sxs-lookup"><span data-stu-id="f79cd-349">The following entries are invalid:</span></span>

- <span data-ttu-id="f79cd-350">**Värden som saknas eller är ogiltiga:**</span><span class="sxs-lookup"><span data-stu-id="f79cd-350">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="f79cd-351">contoso</span><span class="sxs-lookup"><span data-stu-id="f79cd-351">contoso</span></span>
  - <span data-ttu-id="f79cd-352">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="f79cd-352">\*.contoso.\*</span></span>
  - <span data-ttu-id="f79cd-353">\*.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-353">\*.com</span></span>
  - <span data-ttu-id="f79cd-354">\*PDF</span><span class="sxs-lookup"><span data-stu-id="f79cd-354">\*.pdf</span></span>

- <span data-ttu-id="f79cd-355">**Jokertecken i text eller utan avståndstecken:**</span><span class="sxs-lookup"><span data-stu-id="f79cd-355">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="f79cd-356">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-356">\*contoso.com</span></span>
  - <span data-ttu-id="f79cd-357">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="f79cd-357">contoso.com\*</span></span>
  - <span data-ttu-id="f79cd-358">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="f79cd-358">\*1.2.3.4</span></span>
  - <span data-ttu-id="f79cd-359">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="f79cd-359">1.2.3.4\*</span></span>
  - <span data-ttu-id="f79cd-360">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="f79cd-360">contoso.com/a\*</span></span>
  - <span data-ttu-id="f79cd-361">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="f79cd-361">contoso.com/ab\*</span></span>

- <span data-ttu-id="f79cd-362">**IP-adresser med portar:**</span><span class="sxs-lookup"><span data-stu-id="f79cd-362">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="f79cd-363">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="f79cd-363">contoso.com:443</span></span>
  - <span data-ttu-id="f79cd-364">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="f79cd-364">abc.contoso.com:25</span></span>

- <span data-ttu-id="f79cd-365">**Icke-beskrivande jokertecken:**</span><span class="sxs-lookup"><span data-stu-id="f79cd-365">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="f79cd-366">\*.\*</span><span class="sxs-lookup"><span data-stu-id="f79cd-366">\*.\*</span></span>

- <span data-ttu-id="f79cd-367">**Mellan jokertecken:**</span><span class="sxs-lookup"><span data-stu-id="f79cd-367">**Middle wildcards**:</span></span>

  - <span data-ttu-id="f79cd-368">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-368">conto\*so.com</span></span>
  - <span data-ttu-id="f79cd-369">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="f79cd-369">conto~so.com</span></span>

- <span data-ttu-id="f79cd-370">**Dubbla jokertecken**</span><span class="sxs-lookup"><span data-stu-id="f79cd-370">**Double wildcards**</span></span>

  - <span data-ttu-id="f79cd-371">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="f79cd-371">contoso.com/\*\*</span></span>
  - <span data-ttu-id="f79cd-372">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="f79cd-372">contoso.com/\*/\*</span></span>
