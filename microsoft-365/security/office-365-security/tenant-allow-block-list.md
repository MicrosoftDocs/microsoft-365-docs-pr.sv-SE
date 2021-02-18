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
ms.openlocfilehash: 250b6223ffe663e0cd950069a3c3c7827b4aa57b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290171"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="cb39d-103">Hantera Klientorganisationens Tillåt/blockera listan</span><span class="sxs-lookup"><span data-stu-id="cb39d-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cb39d-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="cb39d-104">**Applies to**</span></span>
- [<span data-ttu-id="cb39d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="cb39d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="cb39d-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="cb39d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="cb39d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cb39d-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="cb39d-108">Funktionerna som beskrivs i den här artikeln är förhandsversioner, kan komma att ändras och är inte tillgängliga i alla organisationer.</span><span class="sxs-lookup"><span data-stu-id="cb39d-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="cb39d-109">Du kan för **stunden inte** konfigurera tillåtna objekt i klientorganisationens lista över tillåtna/blockerade objekt.</span><span class="sxs-lookup"><span data-stu-id="cb39d-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="cb39d-110">I Microsoft 365-organisationer som har postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kanske du inte håller med om EOP-filtreringens bedömning.</span><span class="sxs-lookup"><span data-stu-id="cb39d-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="cb39d-111">Ett bra meddelande kan till exempel markeras som dåligt (falskt positivt) eller så kan ett felaktigt meddelande tillåtas (falskt negativa).</span><span class="sxs-lookup"><span data-stu-id="cb39d-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="cb39d-112">Klientorganisationens lista över tillåtna/blockerade listor i Säkerhets- & efterlevnadscenter ger dig ett sätt att manuellt åsidosätta filtreringsvillkoren i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cb39d-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="cb39d-113">Klientorganisationens lista över tillåtna/blockerade används under e-postflödet och när användaren klickar.</span><span class="sxs-lookup"><span data-stu-id="cb39d-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="cb39d-114">Du kan ange URL:er eller filer som alltid ska blockeras.</span><span class="sxs-lookup"><span data-stu-id="cb39d-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="cb39d-115">I den här artikeln beskrivs hur du konfigurerar poster i listan över tillåtna och blockerade klientorganisationer i Säkerhets- & och efterlevnadscenter eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="cb39d-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cb39d-116">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="cb39d-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cb39d-117">Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="cb39d-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="cb39d-118">Använd det här om du **vill gå direkt till sidan Tillåt/blockera** klientorganisation. <https://protection.office.com/tenantAllowBlockList></span><span class="sxs-lookup"><span data-stu-id="cb39d-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="cb39d-119">Du anger filer med hjälp av SHA256-hashvärdet för filen.</span><span class="sxs-lookup"><span data-stu-id="cb39d-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="cb39d-120">Om du vill hitta SHA256-hashvärdet för en fil i Windows kör du följande kommando i en kommandotolk:</span><span class="sxs-lookup"><span data-stu-id="cb39d-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="cb39d-121">Ett exempelvärde är `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="cb39d-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="cb39d-122">Värden för perceptuell hash (pHash) stöds inte.</span><span class="sxs-lookup"><span data-stu-id="cb39d-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="cb39d-123">Tillgängliga URL-värden beskrivs i [URL-syntaxen för avsnittet Tillåt/blockera klientorganisation senare](#url-syntax-for-the-tenant-allowblock-list) i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="cb39d-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="cb39d-124">Klientorganisationens lista över tillåtna/blockerade kan högst 500 poster för URL:er och 500 poster för filshashar.</span><span class="sxs-lookup"><span data-stu-id="cb39d-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="cb39d-125">En post ska vara aktiv inom 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="cb39d-125">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="cb39d-126">Som standard förfaller poster i klientorganisationens lista över tillåtna/blockerade poster efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="cb39d-126">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="cb39d-127">Du kan ange ett datum eller ange att de aldrig ska upphöra att gälla.</span><span class="sxs-lookup"><span data-stu-id="cb39d-127">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="cb39d-128">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="cb39d-128">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="cb39d-129">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="cb39d-129">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="cb39d-130">Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="cb39d-130">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="cb39d-131">Om du vill lägga till och ta bort värden från klientorganisationens lista över tillåtna/blockerade måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="cb39d-131">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="cb39d-132">För skrivskyddad åtkomst till klientorganisationens lista över tillåtna/blockerade måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="cb39d-132">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="cb39d-133">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="cb39d-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="cb39d-134">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="cb39d-134">**Notes**:</span></span>

  - <span data-ttu-id="cb39d-135">Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cb39d-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="cb39d-136">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="cb39d-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="cb39d-137">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="cb39d-137">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="cb39d-138">Använd Säkerhets- & center för att skapa URL-poster i klientorganisationens lista över tillåtna/blockerade adresser</span><span class="sxs-lookup"><span data-stu-id="cb39d-138">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="cb39d-139">Mer information om syntaxen för URL-poster finns i URL-syntaxen för avsnittet [Tillåt/blockera klientorganisation](#url-syntax-for-the-tenant-allowblock-list) senare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="cb39d-139">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="cb39d-140">Gå till innehavarlistan & för  hanteringsklientorganisationens tillåtna/blockerade hot i säkerhets- och \>  \> **efterlevnadscentret.**</span><span class="sxs-lookup"><span data-stu-id="cb39d-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="cb39d-141">Kontrollera att **fliken URL:er är** markerad på sidan **Tillåt/blockera** klientorganisation och klicka sedan på **Blockera**</span><span class="sxs-lookup"><span data-stu-id="cb39d-141">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="cb39d-142">I den **utfällna** menyn Blockera URL:er som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="cb39d-142">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="cb39d-143">**Lägg till URL-adresser** som ska blockeras: Ange en URL per rad, upp till maximalt 20.</span><span class="sxs-lookup"><span data-stu-id="cb39d-143">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="cb39d-144">**Upphör aldrig** att gälla: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="cb39d-144">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="cb39d-145">Kontrollera att inställningen är inaktiverad (inaktiverad) och ange ![ ](../../media/scc-toggle-off.png) **utgångsdatumet** för posterna med hjälp av rutan Förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="cb39d-145">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="cb39d-146">eller</span><span class="sxs-lookup"><span data-stu-id="cb39d-146">or</span></span>

     - <span data-ttu-id="cb39d-147">Flytta reglaget till höger för att konfigurera posterna så att de aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="cb39d-147">Move the toggle to the right to configure the entries to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png)<span data-ttu-id="cb39d-149">.</span><span class="sxs-lookup"><span data-stu-id="cb39d-149">.</span></span>

   - <span data-ttu-id="cb39d-150">**Valfritt:** Ange beskrivande text för posterna.</span><span class="sxs-lookup"><span data-stu-id="cb39d-150">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="cb39d-151">Klicka på Lägg till när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="cb39d-151">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="cb39d-152">Använd Säkerhets- & Center för efterlevnad för att skapa filposter i klientorganisationens lista över tillåtna/blockerade filer</span><span class="sxs-lookup"><span data-stu-id="cb39d-152">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="cb39d-153">Gå till innehavarlistan & över  tillåtna och blockerade hothanteringsprinciper i Säkerhets- \>  \> **och efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="cb39d-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="cb39d-154">Välj fliken **Filer på sidan Tillåt/blockera** för **klientorganisation** och klicka sedan på **Blockera.**</span><span class="sxs-lookup"><span data-stu-id="cb39d-154">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="cb39d-155">I den **utfällna menyn** Lägg till filer för att blockera som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="cb39d-155">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="cb39d-156">**Lägga till filshashar:** Ange ett SHA256-hashvärde per rad, upp till maximalt 20.</span><span class="sxs-lookup"><span data-stu-id="cb39d-156">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="cb39d-157">**Upphör aldrig** att gälla: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="cb39d-157">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="cb39d-158">Kontrollera att inställningen är inaktiverad (inaktiverad) och ange ![ ](../../media/scc-toggle-off.png) **utgångsdatumet** för posterna med hjälp av rutan Förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="cb39d-158">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="cb39d-159">eller</span><span class="sxs-lookup"><span data-stu-id="cb39d-159">or</span></span>

     - <span data-ttu-id="cb39d-160">Flytta reglaget till höger för att konfigurera posterna så att de aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="cb39d-160">Move the toggle to the right to configure the entries to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png)<span data-ttu-id="cb39d-162">.</span><span class="sxs-lookup"><span data-stu-id="cb39d-162">.</span></span>

   - <span data-ttu-id="cb39d-163">**Valfritt:** Ange beskrivande text för posterna.</span><span class="sxs-lookup"><span data-stu-id="cb39d-163">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="cb39d-164">Klicka på Lägg till när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="cb39d-164">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="cb39d-165">Använd Säkerhets- & efterlevnadscenter för att visa poster i klientorganisationens lista över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="cb39d-165">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="cb39d-166">Gå till innehavarlistan & för  hanteringsklientorganisationens tillåtna/blockerade hot i säkerhets- och \>  \> **efterlevnadscentret.**</span><span class="sxs-lookup"><span data-stu-id="cb39d-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="cb39d-167">Välj **fliken URL:er** eller **fliken** Filer.</span><span class="sxs-lookup"><span data-stu-id="cb39d-167">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="cb39d-168">Klicka på följande kolumnrubriker för att sortera i stigande eller fallande ordning:</span><span class="sxs-lookup"><span data-stu-id="cb39d-168">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="cb39d-169">**Värde:** URL:en eller filens hashtagg.</span><span class="sxs-lookup"><span data-stu-id="cb39d-169">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="cb39d-170">**Datum för senaste uppdatering**</span><span class="sxs-lookup"><span data-stu-id="cb39d-170">**Last updated date**</span></span>
- <span data-ttu-id="cb39d-171">**Förfallodatum**</span><span class="sxs-lookup"><span data-stu-id="cb39d-171">**Expiration date**</span></span>
- <span data-ttu-id="cb39d-172">**Obs!**</span><span class="sxs-lookup"><span data-stu-id="cb39d-172">**Note**</span></span>

<span data-ttu-id="cb39d-173">Klicka **på Sök,** ange hela eller en del av ett värde och tryck sedan på RETUR för att hitta ett visst värde.</span><span class="sxs-lookup"><span data-stu-id="cb39d-173">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="cb39d-174">När du är klar klickar du på **ikonen Rensa** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) sökning.</span><span class="sxs-lookup"><span data-stu-id="cb39d-174">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="cb39d-175">Klicka **på Filter.**</span><span class="sxs-lookup"><span data-stu-id="cb39d-175">Click **Filter**.</span></span> <span data-ttu-id="cb39d-176">I den **utfällna** menyn Filter som visas konfigurerar du någon av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="cb39d-176">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="cb39d-177">**Upphör aldrig** att gälla: Välj ![ av: Aktivera ](../../media/scc-toggle-off.png) eller ![ ](../../media/scc-toggle-on.png) inaktivera.</span><span class="sxs-lookup"><span data-stu-id="cb39d-177">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="cb39d-178">**Senast uppdaterad:** Välj ett startdatum **(Från),** ett slutdatum **(Till)** eller både och.</span><span class="sxs-lookup"><span data-stu-id="cb39d-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="cb39d-179">**Förfallodatum:** Välj ett startdatum **(Från),** ett slutdatum **(Till)** eller båda.</span><span class="sxs-lookup"><span data-stu-id="cb39d-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="cb39d-180">Klicka på Använd när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="cb39d-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="cb39d-181">Om du vill ta bort befintliga  **filter klickar** du på Filter och sedan på Rensa filter i den **utfällklara filterfällan som visas.**</span><span class="sxs-lookup"><span data-stu-id="cb39d-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="cb39d-182">Använd Säkerhets- & Center för efterlevnad för att ändra blockeringsposter i klientorganisationens lista över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="cb39d-182">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="cb39d-183">Du kan inte ändra befintliga blockerade URL-adresser eller filvärden i en post.</span><span class="sxs-lookup"><span data-stu-id="cb39d-183">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="cb39d-184">Om du vill ändra dessa värden måste du ta bort och återskapa posten.</span><span class="sxs-lookup"><span data-stu-id="cb39d-184">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="cb39d-185">Gå till innehavarlistan & för  hanteringsklientorganisationens tillåtna/blockerade hot i säkerhets- och \>  \> **efterlevnadscentret.**</span><span class="sxs-lookup"><span data-stu-id="cb39d-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="cb39d-186">Välj **fliken URL:er** eller **fliken** Filer.</span><span class="sxs-lookup"><span data-stu-id="cb39d-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="cb39d-187">Markera den blockpost som du vill ändra och klicka sedan **på** ikonen ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) Redigera.</span><span class="sxs-lookup"><span data-stu-id="cb39d-187">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="cb39d-188">Konfigurera följande inställningar i den utfäll plats som visas:</span><span class="sxs-lookup"><span data-stu-id="cb39d-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="cb39d-189">**Upphör aldrig** att gälla: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="cb39d-189">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="cb39d-190">Kontrollera att inställningen är inaktiverad (inaktiverad) och ange förfallodatumet med hjälp av rutan ![ ](../../media/scc-toggle-off.png) Förfallodatum. </span><span class="sxs-lookup"><span data-stu-id="cb39d-190">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="cb39d-191">eller</span><span class="sxs-lookup"><span data-stu-id="cb39d-191">or</span></span>

     - <span data-ttu-id="cb39d-192">Flytta reglaget till höger för att konfigurera posten så att den aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="cb39d-192">Move the toggle to the right to configure the entry to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png)<span data-ttu-id="cb39d-194">.</span><span class="sxs-lookup"><span data-stu-id="cb39d-194">.</span></span>

   - <span data-ttu-id="cb39d-195">**Valfritt** meddelande: Ange beskrivande text för posten.</span><span class="sxs-lookup"><span data-stu-id="cb39d-195">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="cb39d-196">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="cb39d-196">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="cb39d-197">Använda Säkerhets- & för att ta bort blockeringsposter från klientorganisationens lista över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="cb39d-197">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="cb39d-198">Gå till innehavarlistan & för  hanteringsklientorganisationens tillåtna/blockerade hot i säkerhets- och \>  \> **efterlevnadscentret.**</span><span class="sxs-lookup"><span data-stu-id="cb39d-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="cb39d-199">Välj **fliken URL:er** eller **fliken** Filer.</span><span class="sxs-lookup"><span data-stu-id="cb39d-199">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="cb39d-200">Markera den blockpost du vill ta bort och klicka sedan på ikonen **Ta** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) bort.</span><span class="sxs-lookup"><span data-stu-id="cb39d-200">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="cb39d-201">Klicka på Ta bort i **varningsdialogrutan som visas.**</span><span class="sxs-lookup"><span data-stu-id="cb39d-201">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="cb39d-202">Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera klientorganisationens lista över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="cb39d-202">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="cb39d-203">Använda PowerShell för att lägga till blockeringsposter i klientorganisationens lista över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="cb39d-203">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="cb39d-204">Använd följande syntax för att lägga till blockeringsposter i klientorganisationens lista över tillåtna/blockerade:</span><span class="sxs-lookup"><span data-stu-id="cb39d-204">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="cb39d-205">Det här exemplet lägger till en blockerings-URL-post för contoso.com och alla underdomäner (till exempel contoso.com, www.contoso.com och xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="cb39d-205">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="cb39d-206">Eftersom vi inte använder parametrarna Förfallodatum eller NoExpiration går posten ut efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="cb39d-206">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="cb39d-207">I det här exemplet läggs en blockeringsfilpost till för de angivna filerna som aldrig förfaller.</span><span class="sxs-lookup"><span data-stu-id="cb39d-207">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="cb39d-208">Detaljerad information om syntax och parametrar finns i [New-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="cb39d-208">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="cb39d-209">Använda PowerShell för att visa poster i klientorganisationens lista över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="cb39d-209">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="cb39d-210">För att visa poster i klientorganisationens lista över tillåtna/blockerade, använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="cb39d-210">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="cb39d-211">I det här exemplet returneras alla blockerade URL:er.</span><span class="sxs-lookup"><span data-stu-id="cb39d-211">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="cb39d-212">Det här exemplet returnerar information för det angivna hashvärdet för filen.</span><span class="sxs-lookup"><span data-stu-id="cb39d-212">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="cb39d-213">Detaljerad information om syntax och parametrar finns i [Get-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="cb39d-213">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="cb39d-214">Använda PowerShell för att ändra blockeringsposter i klientorganisationens lista över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="cb39d-214">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="cb39d-215">Du kan inte ändra befintliga URL- eller filvärden inom en blockeringspost.</span><span class="sxs-lookup"><span data-stu-id="cb39d-215">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="cb39d-216">Om du vill ändra dessa värden måste du ta bort och återskapa posten.</span><span class="sxs-lookup"><span data-stu-id="cb39d-216">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="cb39d-217">Använd följande syntax för att ändra blockeringsposter i klientorganisationens lista över tillåtna/blockerade:</span><span class="sxs-lookup"><span data-stu-id="cb39d-217">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="cb39d-218">I det här exemplet ändras förfallodatumet för den angivna blockeringsposten.</span><span class="sxs-lookup"><span data-stu-id="cb39d-218">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="cb39d-219">Detaljerad information om syntax och parametrar finns i [Set-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="cb39d-219">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="cb39d-220">Använda PowerShell för att ta bort blockeringsposter från klientorganisationens lista över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="cb39d-220">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="cb39d-221">Använd följande syntax för att ta bort blockeringsposter från klientorganisationens lista över tillåtna/blockerade:</span><span class="sxs-lookup"><span data-stu-id="cb39d-221">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="cb39d-222">I det här exemplet tas den angivna blockerings-URL-posten bort från klientorganisationens lista över tillåtna/blockerade adresser.</span><span class="sxs-lookup"><span data-stu-id="cb39d-222">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="cb39d-223">Detaljerad information om syntax och parametrar finns i [Remove-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="cb39d-223">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="cb39d-224">URL-syntax för klientorganisationens lista över tillåtna/blockerade</span><span class="sxs-lookup"><span data-stu-id="cb39d-224">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="cb39d-225">IP4v- och IPv6-adresser är tillåtna, men TCP-/UDP-portar är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="cb39d-225">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="cb39d-226">Filnamnstillägg är inte tillåtna (till exempel test.pdf).</span><span class="sxs-lookup"><span data-stu-id="cb39d-226">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="cb39d-227">Unicode stöds inte, men punycode stöds.</span><span class="sxs-lookup"><span data-stu-id="cb39d-227">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="cb39d-228">Hostnames tillåts om alla följande uttryck är sanna:</span><span class="sxs-lookup"><span data-stu-id="cb39d-228">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="cb39d-229">Värdnamnet innehåller en punkt.</span><span class="sxs-lookup"><span data-stu-id="cb39d-229">The hostname contains a period.</span></span>
  - <span data-ttu-id="cb39d-230">Det finns minst ett tecken till vänster om perioden.</span><span class="sxs-lookup"><span data-stu-id="cb39d-230">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="cb39d-231">Det finns minst två tecken till höger om perioden.</span><span class="sxs-lookup"><span data-stu-id="cb39d-231">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="cb39d-232">Till exempel är `t.co` tillåtet eller `.com` är inte `contoso.` tillåtet.</span><span class="sxs-lookup"><span data-stu-id="cb39d-232">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="cb39d-233">Undervägar är inte underförstådda.</span><span class="sxs-lookup"><span data-stu-id="cb39d-233">Subpaths are not implied.</span></span>

  <span data-ttu-id="cb39d-234">Exempel: `contoso.com` Inkluderar inte `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="cb39d-234">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="cb39d-235">Jokertecken (\*) tillåts i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="cb39d-235">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="cb39d-236">Ett vänster jokertecken måste följas av en punkt för att ange en underdomän.</span><span class="sxs-lookup"><span data-stu-id="cb39d-236">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="cb39d-237">Till exempel `*.contoso.com` tillåts, `*contoso.com` är inte tillåtet.</span><span class="sxs-lookup"><span data-stu-id="cb39d-237">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="cb39d-238">Ett höger jokertecken måste följa ett snedstreck (/) för att ange en sökväg.</span><span class="sxs-lookup"><span data-stu-id="cb39d-238">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="cb39d-239">Till exempel är `contoso.com/*` tillåtet eller `contoso.com*` är inte `contoso.com/ab*` tillåtet.</span><span class="sxs-lookup"><span data-stu-id="cb39d-239">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="cb39d-240">Alla undervägar är inte underförstådda med ett rätt jokertecken.</span><span class="sxs-lookup"><span data-stu-id="cb39d-240">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="cb39d-241">Exempel: `contoso.com/*` Inkluderar inte `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="cb39d-241">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="cb39d-242">`*.com*` är ogiltig (inte en lösbar domän och rätt jokertecken följer inte ett snedstreck).</span><span class="sxs-lookup"><span data-stu-id="cb39d-242">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="cb39d-243">Jokertecken är inte tillåtna i IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="cb39d-243">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="cb39d-244">Tecknet tilde (~) är tillgängligt i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="cb39d-244">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="cb39d-245">Ett vänster tilde-namn antyder en domän och alla underdomäner.</span><span class="sxs-lookup"><span data-stu-id="cb39d-245">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="cb39d-246">Till exempel `~contoso.com` tar vi med och `contoso.com` `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="cb39d-246">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="cb39d-247">URL-poster som innehåller protokoll (till exempel, eller ) kommer att `http://` `https://` `ftp://` misslyckas, eftersom URL-poster gäller för alla protokoll.</span><span class="sxs-lookup"><span data-stu-id="cb39d-247">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="cb39d-248">Ett användarnamn eller lösenord stöds inte eller krävs inte.</span><span class="sxs-lookup"><span data-stu-id="cb39d-248">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="cb39d-249">Citattecken (' eller ") är ogiltiga tecken.</span><span class="sxs-lookup"><span data-stu-id="cb39d-249">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="cb39d-250">En URL bör innehålla alla omdirigeringar om det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="cb39d-250">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="cb39d-251">URL-inmatningsscenarier</span><span class="sxs-lookup"><span data-stu-id="cb39d-251">URL entry scenarios</span></span>

<span data-ttu-id="cb39d-252">Giltiga URL-poster och deras resultat beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="cb39d-252">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="cb39d-253">Scenario: Inga jokertecken</span><span class="sxs-lookup"><span data-stu-id="cb39d-253">Scenario: No wildcards</span></span>

<span data-ttu-id="cb39d-254">**Post:**`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="cb39d-254">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="cb39d-255">**Tillåt matchning:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-255">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="cb39d-256">**Tillåt ej matchad:**</span><span class="sxs-lookup"><span data-stu-id="cb39d-256">**Allow not matched**:</span></span>

  - <span data-ttu-id="cb39d-257">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-257">abc-contoso.com</span></span>
  - <span data-ttu-id="cb39d-258">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="cb39d-258">contoso.com/a</span></span>
  - <span data-ttu-id="cb39d-259">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-259">payroll.contoso.com</span></span>
  - <span data-ttu-id="cb39d-260">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-260">test.com/contoso.com</span></span>
  - <span data-ttu-id="cb39d-261">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-261">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="cb39d-262">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-262">www.contoso.com</span></span>
  - <span data-ttu-id="cb39d-263">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-263">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="cb39d-264">**Blockmatchning:**</span><span class="sxs-lookup"><span data-stu-id="cb39d-264">**Block match**:</span></span>

  - <span data-ttu-id="cb39d-265">contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-265">contoso.com</span></span>
  - <span data-ttu-id="cb39d-266">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="cb39d-266">contoso.com/a</span></span>
  - <span data-ttu-id="cb39d-267">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-267">payroll.contoso.com</span></span>
  - <span data-ttu-id="cb39d-268">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-268">test.com/contoso.com</span></span>
  - <span data-ttu-id="cb39d-269">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-269">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="cb39d-270">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-270">www.contoso.com</span></span>
  - <span data-ttu-id="cb39d-271">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-271">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="cb39d-272">**Blocket matchas inte:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-272">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="cb39d-273">Scenario: Vänster jokertecken (underdomän)</span><span class="sxs-lookup"><span data-stu-id="cb39d-273">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="cb39d-274">**Post:**`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="cb39d-274">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="cb39d-275">**Tillåt matchning** och **blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="cb39d-275">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="cb39d-276">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-276">www.contoso.com</span></span>
  - <span data-ttu-id="cb39d-277">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-277">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="cb39d-278">**Tillåt ej matchad** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="cb39d-278">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="cb39d-279">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-279">123contoso.com</span></span>
  - <span data-ttu-id="cb39d-280">contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-280">contoso.com</span></span>
  - <span data-ttu-id="cb39d-281">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-281">test.com/contoso.com</span></span>
  - <span data-ttu-id="cb39d-282">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="cb39d-282">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="cb39d-283">Scenario: Höger jokertecken högst upp i sökvägen</span><span class="sxs-lookup"><span data-stu-id="cb39d-283">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="cb39d-284">**Post:**`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="cb39d-284">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="cb39d-285">**Tillåt matchning** och **blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="cb39d-285">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="cb39d-286">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="cb39d-286">contoso.com/a/b</span></span>
  - <span data-ttu-id="cb39d-287">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="cb39d-287">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="cb39d-288">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-288">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="cb39d-289">**Tillåt ej matchad** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="cb39d-289">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="cb39d-290">contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-290">contoso.com</span></span>
  - <span data-ttu-id="cb39d-291">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="cb39d-291">contoso.com/a</span></span>
  - <span data-ttu-id="cb39d-292">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-292">www.contoso.com</span></span>
  - <span data-ttu-id="cb39d-293">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-293">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="cb39d-294">Scenario: Vänster tilde</span><span class="sxs-lookup"><span data-stu-id="cb39d-294">Scenario: Left tilde</span></span>

<span data-ttu-id="cb39d-295">**Post:**`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="cb39d-295">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="cb39d-296">**Tillåt matchning** och **blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="cb39d-296">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="cb39d-297">contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-297">contoso.com</span></span>
  - <span data-ttu-id="cb39d-298">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-298">www.contoso.com</span></span>
  - <span data-ttu-id="cb39d-299">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-299">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="cb39d-300">**Tillåt ej matchad** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="cb39d-300">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="cb39d-301">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-301">123contoso.com</span></span>
  - <span data-ttu-id="cb39d-302">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="cb39d-302">contoso.com/abc</span></span>
  - <span data-ttu-id="cb39d-303">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="cb39d-303">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="cb39d-304">Scenario: Höger suffix för jokertecken</span><span class="sxs-lookup"><span data-stu-id="cb39d-304">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="cb39d-305">**Post:**`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="cb39d-305">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="cb39d-306">**Tillåt matchning** och **blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="cb39d-306">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="cb39d-307">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-307">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="cb39d-308">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="cb39d-308">contoso.com/a</span></span>
  - <span data-ttu-id="cb39d-309">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="cb39d-309">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="cb39d-310">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="cb39d-310">contoso.com/ab</span></span>
  - <span data-ttu-id="cb39d-311">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="cb39d-311">contoso.com/b</span></span>
  - <span data-ttu-id="cb39d-312">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="cb39d-312">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="cb39d-313">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="cb39d-313">contoso.com/ba</span></span>

- <span data-ttu-id="cb39d-314">**Tillåt ej matchad** och **Blockera matchas inte:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-314">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="cb39d-315">Scenario: Underdomän för vänster jokertecken och höger suffix för jokertecken</span><span class="sxs-lookup"><span data-stu-id="cb39d-315">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="cb39d-316">**Post:**`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="cb39d-316">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="cb39d-317">**Tillåt matchning** och **blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="cb39d-317">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="cb39d-318">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="cb39d-318">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="cb39d-319">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="cb39d-319">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="cb39d-320">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="cb39d-320">www.contoso.com/a</span></span>
  - <span data-ttu-id="cb39d-321">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="cb39d-321">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="cb39d-322">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="cb39d-322">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="cb39d-323">**Tillåt ej matchad** och **Blockera matchas inte:** contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="cb39d-323">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="cb39d-324">Scenario: Vänster och höger tilde</span><span class="sxs-lookup"><span data-stu-id="cb39d-324">Scenario: Left and right tilde</span></span>

<span data-ttu-id="cb39d-325">**Post:**`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="cb39d-325">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="cb39d-326">**Tillåt matchning** och **blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="cb39d-326">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="cb39d-327">contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-327">contoso.com</span></span>
  - <span data-ttu-id="cb39d-328">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="cb39d-328">contoso.com/a</span></span>
  - <span data-ttu-id="cb39d-329">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-329">www.contoso.com</span></span>
  - <span data-ttu-id="cb39d-330">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="cb39d-330">www.contoso.com/b</span></span>
  - <span data-ttu-id="cb39d-331">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-331">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="cb39d-332">**Tillåt ej matchad** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="cb39d-332">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="cb39d-333">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-333">123contoso.com</span></span>
  - <span data-ttu-id="cb39d-334">contoso.org</span><span class="sxs-lookup"><span data-stu-id="cb39d-334">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="cb39d-335">Scenario: IP-adress</span><span class="sxs-lookup"><span data-stu-id="cb39d-335">Scenario: IP address</span></span>

<span data-ttu-id="cb39d-336">**Post:**`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="cb39d-336">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="cb39d-337">**Tillåt matchning** och **blockeringsmatchning:** 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="cb39d-337">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="cb39d-338">**Tillåt ej matchad** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="cb39d-338">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="cb39d-339">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="cb39d-339">1.2.3.4/a</span></span>
  - <span data-ttu-id="cb39d-340">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="cb39d-340">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="cb39d-341">IP-adress med rätt jokertecken</span><span class="sxs-lookup"><span data-stu-id="cb39d-341">IP address with right wildcard</span></span>

<span data-ttu-id="cb39d-342">**Post:**`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="cb39d-342">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="cb39d-343">**Tillåt matchning** och **blockeringsmatchning:**</span><span class="sxs-lookup"><span data-stu-id="cb39d-343">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="cb39d-344">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="cb39d-344">1.2.3.4/b</span></span>
  - <span data-ttu-id="cb39d-345">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="cb39d-345">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="cb39d-346">Exempel på ogiltiga poster</span><span class="sxs-lookup"><span data-stu-id="cb39d-346">Examples of invalid entries</span></span>

<span data-ttu-id="cb39d-347">Följande poster är ogiltiga:</span><span class="sxs-lookup"><span data-stu-id="cb39d-347">The following entries are invalid:</span></span>

- <span data-ttu-id="cb39d-348">**Värden som saknas eller är ogiltiga:**</span><span class="sxs-lookup"><span data-stu-id="cb39d-348">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="cb39d-349">contoso</span><span class="sxs-lookup"><span data-stu-id="cb39d-349">contoso</span></span>
  - <span data-ttu-id="cb39d-350">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="cb39d-350">\*.contoso.\*</span></span>
  - <span data-ttu-id="cb39d-351">\*.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-351">\*.com</span></span>
  - <span data-ttu-id="cb39d-352">\*PDF</span><span class="sxs-lookup"><span data-stu-id="cb39d-352">\*.pdf</span></span>

- <span data-ttu-id="cb39d-353">**Jokertecken i text eller utan avståndstecken:**</span><span class="sxs-lookup"><span data-stu-id="cb39d-353">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="cb39d-354">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-354">\*contoso.com</span></span>
  - <span data-ttu-id="cb39d-355">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="cb39d-355">contoso.com\*</span></span>
  - <span data-ttu-id="cb39d-356">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="cb39d-356">\*1.2.3.4</span></span>
  - <span data-ttu-id="cb39d-357">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="cb39d-357">1.2.3.4\*</span></span>
  - <span data-ttu-id="cb39d-358">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="cb39d-358">contoso.com/a\*</span></span>
  - <span data-ttu-id="cb39d-359">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="cb39d-359">contoso.com/ab\*</span></span>

- <span data-ttu-id="cb39d-360">**IP-adresser med portar:**</span><span class="sxs-lookup"><span data-stu-id="cb39d-360">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="cb39d-361">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="cb39d-361">contoso.com:443</span></span>
  - <span data-ttu-id="cb39d-362">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="cb39d-362">abc.contoso.com:25</span></span>

- <span data-ttu-id="cb39d-363">**Icke-beskrivande jokertecken:**</span><span class="sxs-lookup"><span data-stu-id="cb39d-363">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="cb39d-364">\*.\*</span><span class="sxs-lookup"><span data-stu-id="cb39d-364">\*.\*</span></span>

- <span data-ttu-id="cb39d-365">**Mellan jokertecken:**</span><span class="sxs-lookup"><span data-stu-id="cb39d-365">**Middle wildcards**:</span></span>

  - <span data-ttu-id="cb39d-366">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-366">conto\*so.com</span></span>
  - <span data-ttu-id="cb39d-367">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="cb39d-367">conto~so.com</span></span>

- <span data-ttu-id="cb39d-368">**Dubbla jokertecken**</span><span class="sxs-lookup"><span data-stu-id="cb39d-368">**Double wildcards**</span></span>

  - <span data-ttu-id="cb39d-369">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="cb39d-369">contoso.com/\*\*</span></span>
  - <span data-ttu-id="cb39d-370">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="cb39d-370">contoso.com/\*/\*</span></span>
