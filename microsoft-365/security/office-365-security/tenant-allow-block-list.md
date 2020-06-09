---
title: Hantera tillåtna och blockerade webbadresser och filer i listan Tillåt/blockera klient
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Administratörer kan lära sig hur du konfigurerar URL- och filposter i listan Tillåt/blockera klient i säkerhets- & Compliance Center.
ms.openlocfilehash: 0143ee2601a4cb9593c79f8c6c62d1f06914088f
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44613426"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a><span data-ttu-id="04a75-103">Hantera webbadresser och filer i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="04a75-103">Manage URLs and files in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="04a75-104">Funktionerna som beskrivs i det här avsnittet är i förhandsversion, kan komma att ändras och är inte tillgängliga i alla organisationer.</span><span class="sxs-lookup"><span data-stu-id="04a75-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="04a75-105">I Microsoft 365-organisationer med postlådor i Exchange Online- eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kanske du inte håller med om EOP-filtreringsdomen.</span><span class="sxs-lookup"><span data-stu-id="04a75-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="04a75-106">Ett bra meddelande kan till exempel markeras som dåligt (falskt positivt) eller så kan ett felaktigt meddelande tillåtas (ett falskt negativt).</span><span class="sxs-lookup"><span data-stu-id="04a75-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="04a75-107">Listan Tillåt/blockera klient i Security & Compliance Center ger dig ett sätt att manuellt åsidosätta Microsoft 365-filtreringsutlåtandena.</span><span class="sxs-lookup"><span data-stu-id="04a75-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="04a75-108">Listan Tillåt/blockera klient används under e-postflödet och vid tidpunkten för användarens klick.</span><span class="sxs-lookup"><span data-stu-id="04a75-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="04a75-109">Du kan ange webbadresser och filer som ska tillåtas eller blockeras i listan Tillåt/blockera klient.</span><span class="sxs-lookup"><span data-stu-id="04a75-109">You can specify URLs and files to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="04a75-110">I det här avsnittet beskrivs hur du konfigurerar poster i listan Tillåt/blockera innehavare i Security & Compliance Center eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="04a75-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="04a75-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="04a75-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="04a75-112">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="04a75-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="04a75-113">Om du vill gå direkt till sidan **Tillåt/blockera lista för klienter** använder du <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="04a75-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="04a75-114">Du anger filer med hjälp av sha256-hash-värdet för filen.</span><span class="sxs-lookup"><span data-stu-id="04a75-114">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="04a75-115">Om du vill hitta SHA256-hash-värdet för en fil i Windows kör du följande kommando i en kommandotolk:</span><span class="sxs-lookup"><span data-stu-id="04a75-115">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="04a75-116">Ett exempelvärde är `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="04a75-116">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="04a75-117">Perceptuella hash-värden (pHash) är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="04a75-117">Perceptual hash (pHash) values are not allowed.</span></span>

- <span data-ttu-id="04a75-118">De tillgängliga URL-värdena beskrivs i [URL-syntaxen för avsnittet Tillåt/blockera klient](#url-syntax-for-the-tenant-allowblock-list) senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="04a75-118">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="04a75-119">Med listan Tillåt/blockera klient kan högst 500 poster för webbadresser och 500 poster för filh hashar.</span><span class="sxs-lookup"><span data-stu-id="04a75-119">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="04a75-120">En post ska vara aktiv inom 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="04a75-120">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="04a75-121">Blockposter har företräde framför tillåta transaktioner.</span><span class="sxs-lookup"><span data-stu-id="04a75-121">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="04a75-122">Som standard upphör posterna i listan Tillåt/blockera klient att gälla efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="04a75-122">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="04a75-123">Du kan ange ett datum eller ange att de aldrig ska upphöra att gälla.</span><span class="sxs-lookup"><span data-stu-id="04a75-123">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="04a75-124">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="04a75-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="04a75-125">Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="04a75-125">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="04a75-126">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="04a75-126">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="04a75-127">Om du vill lägga till och ta bort värden från listan Tillåt/blockera klient måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="04a75-127">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="04a75-128">För skrivskyddad åtkomst till listan Tillåt/blockera klient måste du vara medlem i rollgruppen **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="04a75-128">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="04a75-129">Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="04a75-129">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="04a75-130">Använd säkerhets- & compliance center för att skapa URL-poster i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="04a75-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="04a75-131">Mer information om syntaxen för URL-poster finns i [URL-syntaxen för avsnittet Tillåt/blockera klient](#url-syntax-for-the-tenant-allowblock-list) senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="04a75-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="04a75-132">Gå till **Hothanteringsprincipen** \> **Policy** \> **Tillåt/Blockera listor**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="04a75-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="04a75-133">Kontrollera att fliken **Webbadresser** är markerad på sidan **Tillåt/blockera lista** för klienter och klicka sedan på **Lägg till**</span><span class="sxs-lookup"><span data-stu-id="04a75-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="04a75-134">Konfigurera följande inställningar i utfällbara **url:er** som visas:</span><span class="sxs-lookup"><span data-stu-id="04a75-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="04a75-135">**Lägg till webbadresser med jokertecken:** Ange en URL per rad, upp till maximalt 20.</span><span class="sxs-lookup"><span data-stu-id="04a75-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="04a75-136">**Blockera/tillåt**: Välj om du vill **tillåta** eller **blockera** de angivna webbadresserna.</span><span class="sxs-lookup"><span data-stu-id="04a75-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="04a75-137">**Upphör aldrig att gälla**: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="04a75-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="04a75-138">Kontrollera att inställningen är inaktiverad ( ![ Stäng av ) och använd rutan Upphör att gälla för att ange ](../../media/scc-toggle-off.png) **utgångsdatum** för transaktionerna.</span><span class="sxs-lookup"><span data-stu-id="04a75-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="04a75-139">eller</span><span class="sxs-lookup"><span data-stu-id="04a75-139">or</span></span>

     - <span data-ttu-id="04a75-140">Flytta växlingsknappen åt höger för att konfigurera posterna så att de aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="04a75-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="04a75-142">.</span><span class="sxs-lookup"><span data-stu-id="04a75-142">.</span></span>

   - <span data-ttu-id="04a75-143">**Valfri anmärkning:** Ange beskrivande text för posterna.</span><span class="sxs-lookup"><span data-stu-id="04a75-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="04a75-144">När du är klar klickar du på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="04a75-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="04a75-145">Använda Security & Compliance Center för att skapa filposter i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="04a75-145">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="04a75-146">Gå till **Hothanteringsprincipen** \> **Policy** \> **Tillåt/Blockera listor**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="04a75-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="04a75-147">På sidan **Tillåt/blockera lista för klienter** väljer du fliken **Filer** och klickar sedan på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="04a75-147">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="04a75-148">Konfigurera följande inställningar i utfällbara **filer** som visas:</span><span class="sxs-lookup"><span data-stu-id="04a75-148">In the **Add new files** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="04a75-149">**Lägg till fil hashar:** Ange ett SHA256 hash-värde per rad, upp till maximalt 20.</span><span class="sxs-lookup"><span data-stu-id="04a75-149">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="04a75-150">**Blockera/tillåt**: Välj om du vill **tillåta** eller **blockera** de angivna filerna.</span><span class="sxs-lookup"><span data-stu-id="04a75-150">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified files.</span></span>

   - <span data-ttu-id="04a75-151">**Upphör aldrig att gälla**: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="04a75-151">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="04a75-152">Kontrollera att inställningen är inaktiverad ( ![ Stäng av ) och använd rutan Upphör att gälla för att ange ](../../media/scc-toggle-off.png) **utgångsdatum** för transaktionerna.</span><span class="sxs-lookup"><span data-stu-id="04a75-152">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="04a75-153">eller</span><span class="sxs-lookup"><span data-stu-id="04a75-153">or</span></span>

     - <span data-ttu-id="04a75-154">Flytta växlingsknappen åt höger för att konfigurera posterna så att de aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="04a75-154">Move the toggle to the right to configure the entries to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="04a75-156">.</span><span class="sxs-lookup"><span data-stu-id="04a75-156">.</span></span>

   - <span data-ttu-id="04a75-157">**Valfri anmärkning:** Ange beskrivande text för posterna.</span><span class="sxs-lookup"><span data-stu-id="04a75-157">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="04a75-158">När du är klar klickar du på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="04a75-158">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="04a75-159">Använda Säkerhets- & Compliance Center för att visa URL- och filposter i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="04a75-159">Use the Security & Compliance Center to view URL and file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="04a75-160">Gå till **Hothanteringsprincipen** \> **Policy** \> **Tillåt/Blockera listor**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="04a75-160">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="04a75-161">Välj fliken **Webbadresser** eller fliken **Filer.**</span><span class="sxs-lookup"><span data-stu-id="04a75-161">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="04a75-162">Klicka på följande kolumnrubriker för att sortera i stigande eller fallande ordning:</span><span class="sxs-lookup"><span data-stu-id="04a75-162">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="04a75-163">**Värde**: URL:en eller filh hash.</span><span class="sxs-lookup"><span data-stu-id="04a75-163">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="04a75-164">**Åtgärd**: **Blockera** eller **tillåt**.</span><span class="sxs-lookup"><span data-stu-id="04a75-164">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="04a75-165">**Senast uppdaterat datum**</span><span class="sxs-lookup"><span data-stu-id="04a75-165">**Last updated date**</span></span>
- <span data-ttu-id="04a75-166">**Utgångsdatum**</span><span class="sxs-lookup"><span data-stu-id="04a75-166">**Expiration date**</span></span>
- <span data-ttu-id="04a75-167">**Observera**</span><span class="sxs-lookup"><span data-stu-id="04a75-167">**Note**</span></span>

<span data-ttu-id="04a75-168">Klicka på **Gruppera** om du vill gruppera transaktionerna efter **Åtgärd** (**Block** eller **Tillåt**) eller **Ingen**.</span><span class="sxs-lookup"><span data-stu-id="04a75-168">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="04a75-169">Klicka på **Sök,** ange hela eller delar av en URL eller ett filvärde och tryck sedan på RETUR för att hitta ett visst värde.</span><span class="sxs-lookup"><span data-stu-id="04a75-169">Click **Search**, enter all or part of a URL or file value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="04a75-170">När du är klar klickar du på **Rensa** ![ sökikonen Rensa sökning ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="04a75-170">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="04a75-171">Klicka på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="04a75-171">Click **Filter**.</span></span> <span data-ttu-id="04a75-172">Konfigurera någon av följande inställningar i **utfällbara filter** som visas:</span><span class="sxs-lookup"><span data-stu-id="04a75-172">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="04a75-173">**Åtgärd**: Välj **Tillåt,** **Blockera** eller båda.</span><span class="sxs-lookup"><span data-stu-id="04a75-173">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="04a75-174">**Upphör aldrig att gälla:** Välj av ![ (Växla ](../../media/scc-toggle-off.png) av) eller på ( ![ Växla på ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="04a75-174">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="04a75-175">**Senast uppdaterad**: Välj ett startdatum (**Från**), ett slutdatum (**Till**) eller båda.</span><span class="sxs-lookup"><span data-stu-id="04a75-175">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="04a75-176">**Utgångsdatum**: Välj ett startdatum (**Från**), ett slutdatum (**Till**) eller båda.</span><span class="sxs-lookup"><span data-stu-id="04a75-176">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="04a75-177">När du är klar klickar du på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="04a75-177">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="04a75-178">Om du vill ta bort befintliga filter klickar du på **Filtrera**och klickar på **Rensa filter**i det utfällbara **filter som** visas.</span><span class="sxs-lookup"><span data-stu-id="04a75-178">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="04a75-179">Använda Security & Compliance Center för att ändra URL- och filposter i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="04a75-179">Use the Security & Compliance Center to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="04a75-180">Du kan inte ändra själva URL:en: eller filvärdet.</span><span class="sxs-lookup"><span data-stu-id="04a75-180">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="04a75-181">I stället måste du ta bort posten och återskapa den.</span><span class="sxs-lookup"><span data-stu-id="04a75-181">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="04a75-182">Gå till **Hothanteringsprincipen** \> **Policy** \> **Tillåt/Blockera listor**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="04a75-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="04a75-183">Välj fliken **Webbadresser** eller fliken **Filer.**</span><span class="sxs-lookup"><span data-stu-id="04a75-183">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="04a75-184">Markera den post som du vill ändra och klicka sedan på **Ikonen Redigera** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) redigera.</span><span class="sxs-lookup"><span data-stu-id="04a75-184">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="04a75-185">Konfigurera följande inställningar i utfällbara utfällbara inställningar:</span><span class="sxs-lookup"><span data-stu-id="04a75-185">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="04a75-186">**Blockera/tillåt**: Välj **Tillåt** eller **Blockera**.</span><span class="sxs-lookup"><span data-stu-id="04a75-186">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="04a75-187">**Upphör aldrig att gälla**: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="04a75-187">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="04a75-188">Kontrollera att inställningen är inaktiverad ( ![ Stäng av ) och använd rutan Upphör att gälla för att ange ](../../media/scc-toggle-off.png) **utgångsdatum** för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="04a75-188">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="04a75-189">eller</span><span class="sxs-lookup"><span data-stu-id="04a75-189">or</span></span>

     - <span data-ttu-id="04a75-190">Flytta växlingsknappen åt höger för att konfigurera posten så att den aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="04a75-190">Move the toggle to the right to configure the entry to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="04a75-192">.</span><span class="sxs-lookup"><span data-stu-id="04a75-192">.</span></span>

   - <span data-ttu-id="04a75-193">**Valfri anmärkning:** Ange beskrivande text för posten.</span><span class="sxs-lookup"><span data-stu-id="04a75-193">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="04a75-194">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="04a75-194">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="04a75-195">Använd Security & Compliance Center för att ta bort URL- och filposter från listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="04a75-195">Use the Security & Compliance Center to remove URL and file entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="04a75-196">Gå till **Hothanteringsprincipen** \> **Policy** \> **Tillåt/Blockera listor**i Security & Compliance Center .</span><span class="sxs-lookup"><span data-stu-id="04a75-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="04a75-197">Välj fliken **Webbadresser** eller fliken **Filer.**</span><span class="sxs-lookup"><span data-stu-id="04a75-197">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="04a75-198">Markera den post som du vill ta bort och klicka sedan på **Ikonen Ta bort borttagning** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="04a75-198">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="04a75-199">Klicka på **Ta bort**i varningsdialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="04a75-199">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="04a75-200">Använd Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="04a75-200">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="04a75-201">Använda PowerShell för att lägga till URL- och filposter i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="04a75-201">Use PowerShell to add URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="04a75-202">Om du vill lägga till URL- och filposter i listan Tillåt/blockera klienter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="04a75-202">To add URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="04a75-203">I det här exemplet läggs en URL-blockpost till för contoso.com och alla underdomäner (till exempel contoso.com, www.contoso.com och xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="04a75-203">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="04a75-204">Eftersom vi inte använde parametrarna ExpirationDate eller NoExpiration upphör posten att gälla efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="04a75-204">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="04a75-205">I det här exemplet läggs en fil tillåta post för de angivna filerna som aldrig upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="04a75-205">This example adds a file allow entry for the specified files that never expires.</span></span>

<span data-ttu-id="04a75-206">Detaljerad syntax- och parameterinformation finns i [Ny-KlientEns 111111.For](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)detailed syntax and parameter information, see New-TenantAllowBlockListItems .</span><span class="sxs-lookup"><span data-stu-id="04a75-206">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="04a75-207">Använda PowerShell för att visa URL- och filposter i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="04a75-207">Use PowerShell to view URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="04a75-208">Om du vill visa URL- och filposter i listan Tillåt/blockera klienter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="04a75-208">To view URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="04a75-209">I det här exemplet returneras alla blockerade webbadresser.</span><span class="sxs-lookup"><span data-stu-id="04a75-209">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="04a75-210">I det här exemplet returneras information om det angivna filhh-värdet.</span><span class="sxs-lookup"><span data-stu-id="04a75-210">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="04a75-211">Detaljerad syntax- och parameterinformation finns i [Hämta-klientEnAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="04a75-211">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="04a75-212">Använda PowerShell för att ändra URL- och filposter i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="04a75-212">Use PowerShell to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="04a75-213">Du kan inte ändra själva URL:en: eller filvärdet.</span><span class="sxs-lookup"><span data-stu-id="04a75-213">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="04a75-214">I stället måste du ta bort posten och återskapa den.</span><span class="sxs-lookup"><span data-stu-id="04a75-214">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="04a75-215">Om du vill ändra URL- och filposter i listan Tillåt/blockera klienter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="04a75-215">To modify URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="04a75-216">I det här exemplet ändras förfallodatumet för den angivna posten.</span><span class="sxs-lookup"><span data-stu-id="04a75-216">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="04a75-217">Detaljerad syntax- och parameterinformation finns i [Ange-klientEnAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="04a75-217">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="04a75-218">Använda PowerShell för att ta bort URL- och filposter från listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="04a75-218">Use PowerShell to remove URL and file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="04a75-219">Om du vill ta bort URL- och filposter från listan Tillåt/blockera klienter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="04a75-219">To remove URL and file entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="04a75-220">I det här exemplet tas den angivna URL-posten bort från listan Tillåt/blockera klient.</span><span class="sxs-lookup"><span data-stu-id="04a75-220">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="04a75-221">Detaljerad syntax- och parameterinformation finns i [Ta bort-klientEnAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="04a75-221">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="04a75-222">URL-syntax för listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="04a75-222">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="04a75-223">IP4v- och IPv6-adresser är tillåtna, men TCP/UDP-portar är det inte.</span><span class="sxs-lookup"><span data-stu-id="04a75-223">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="04a75-224">Filnamnstillägg är inte tillåtna (till exempel test.pdf).</span><span class="sxs-lookup"><span data-stu-id="04a75-224">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="04a75-225">Unicode stöds inte, men Punycode är.</span><span class="sxs-lookup"><span data-stu-id="04a75-225">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="04a75-226">Värdnamn är tillåtna om alla följande satser är sanna:</span><span class="sxs-lookup"><span data-stu-id="04a75-226">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="04a75-227">Värdnamnet innehåller en punkt.</span><span class="sxs-lookup"><span data-stu-id="04a75-227">The hostname contains a period.</span></span>
  - <span data-ttu-id="04a75-228">Det finns minst ett tecken till vänster om perioden.</span><span class="sxs-lookup"><span data-stu-id="04a75-228">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="04a75-229">Det finns minst två tecken till höger om perioden.</span><span class="sxs-lookup"><span data-stu-id="04a75-229">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="04a75-230">Till exempel `t.co` är tillåtet, `.com` eller är inte `contoso.` tillåtna.</span><span class="sxs-lookup"><span data-stu-id="04a75-230">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="04a75-231">Undervägar är inte underförstådda.</span><span class="sxs-lookup"><span data-stu-id="04a75-231">Subpaths are not implied.</span></span>

  <span data-ttu-id="04a75-232">Innehåller till exempel `contoso.com` inte `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="04a75-232">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="04a75-233">Jokertecken (\*) tillåts i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="04a75-233">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="04a75-234">Ett vänster jokertecken måste följas av en punkt för att ange en underdomän.</span><span class="sxs-lookup"><span data-stu-id="04a75-234">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="04a75-235">Till exempel `*.contoso.com` är tillåtet, `*contoso.com` är inte tillåtet.</span><span class="sxs-lookup"><span data-stu-id="04a75-235">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="04a75-236">Ett höger jokertecken måste följa ett snedstreck (/) för att ange en sökväg.</span><span class="sxs-lookup"><span data-stu-id="04a75-236">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="04a75-237">Till exempel `contoso.com/*` är tillåtet, `contoso.com*` eller är inte `contoso.com/ab*` tillåtna.</span><span class="sxs-lookup"><span data-stu-id="04a75-237">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="04a75-238">Alla underbanor är inte underförstådda av ett höger jokertecken.</span><span class="sxs-lookup"><span data-stu-id="04a75-238">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="04a75-239">Innehåller till exempel `contoso.com/*` inte `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="04a75-239">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="04a75-240">`*.com*`är ogiltigt (inte en upplösningsbar domän och det högra jokertecknet följer inte ett snedstreck).</span><span class="sxs-lookup"><span data-stu-id="04a75-240">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="04a75-241">Jokertecken är inte tillåtna i IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="04a75-241">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="04a75-242">Tilde -tecknet (~) är tillgängligt i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="04a75-242">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="04a75-243">En vänster tilde innebär en domän och alla underdomäner.</span><span class="sxs-lookup"><span data-stu-id="04a75-243">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="04a75-244">Till exempel `~contoso.com` innehåller `contoso.com` och `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="04a75-244">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="04a75-245">URL-poster som innehåller protokoll (till exempel `http://` `https://` , eller ) `ftp://` misslyckas, eftersom URL-poster gäller för alla protokoll.</span><span class="sxs-lookup"><span data-stu-id="04a75-245">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="04a75-246">Ett användarnamn eller lösenord stöds inte eller krävs inte.</span><span class="sxs-lookup"><span data-stu-id="04a75-246">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="04a75-247">Citattecken (' eller ") är ogiltiga tecken.</span><span class="sxs-lookup"><span data-stu-id="04a75-247">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="04a75-248">En webbadress bör innehålla alla omdirigeringar där det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="04a75-248">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="04a75-249">Scenarier för URL-post</span><span class="sxs-lookup"><span data-stu-id="04a75-249">URL entry scenarios</span></span>

<span data-ttu-id="04a75-250">Giltiga URL-poster och deras resultat beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="04a75-250">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="04a75-251">Scenario: Inga jokertecken</span><span class="sxs-lookup"><span data-stu-id="04a75-251">Scenario: No wildcards</span></span>

<span data-ttu-id="04a75-252">**Inträde**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="04a75-252">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="04a75-253">**Tillåt matchning**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-253">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="04a75-254">**Tillåt inte matchad:**</span><span class="sxs-lookup"><span data-stu-id="04a75-254">**Allow not matched**:</span></span>

  - <span data-ttu-id="04a75-255">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-255">abc-contoso.com</span></span>
  - <span data-ttu-id="04a75-256">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="04a75-256">contoso.com/a</span></span>
  - <span data-ttu-id="04a75-257">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-257">payroll.contoso.com</span></span>
  - <span data-ttu-id="04a75-258">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-258">test.com/contoso.com</span></span>
  - <span data-ttu-id="04a75-259">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-259">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="04a75-260">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-260">www.contoso.com</span></span>
  - <span data-ttu-id="04a75-261">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-261">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="04a75-262">**Blockera matchning:**</span><span class="sxs-lookup"><span data-stu-id="04a75-262">**Block match**:</span></span>

  - <span data-ttu-id="04a75-263">contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-263">contoso.com</span></span>
  - <span data-ttu-id="04a75-264">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="04a75-264">contoso.com/a</span></span>
  - <span data-ttu-id="04a75-265">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-265">payroll.contoso.com</span></span>
  - <span data-ttu-id="04a75-266">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-266">test.com/contoso.com</span></span>
  - <span data-ttu-id="04a75-267">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-267">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="04a75-268">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-268">www.contoso.com</span></span>
  - <span data-ttu-id="04a75-269">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-269">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="04a75-270">**Blocket matchas inte:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-270">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="04a75-271">Scenario: Vänster jokertecken (underdomän)</span><span class="sxs-lookup"><span data-stu-id="04a75-271">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="04a75-272">**Inträde**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="04a75-272">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="04a75-273">**Tillåt matchning** och **blockera matchning:**</span><span class="sxs-lookup"><span data-stu-id="04a75-273">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="04a75-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-274">www.contoso.com</span></span>
  - <span data-ttu-id="04a75-275">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-275">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="04a75-276">**Tillåt inte matchade** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="04a75-276">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="04a75-277">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-277">123contoso.com</span></span>
  - <span data-ttu-id="04a75-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-278">contoso.com</span></span>
  - <span data-ttu-id="04a75-279">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-279">test.com/contoso.com</span></span>
  - <span data-ttu-id="04a75-280">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="04a75-280">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="04a75-281">Scenario: Höger jokertecken högst upp i banan</span><span class="sxs-lookup"><span data-stu-id="04a75-281">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="04a75-282">**Inträde**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="04a75-282">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="04a75-283">**Tillåt matchning** och **blockera matchning:**</span><span class="sxs-lookup"><span data-stu-id="04a75-283">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="04a75-284">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="04a75-284">contoso.com/a/b</span></span>
  - <span data-ttu-id="04a75-285">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="04a75-285">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="04a75-286">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="04a75-286">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="04a75-287">**Tillåt inte matchade** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="04a75-287">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="04a75-288">contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-288">contoso.com</span></span>
  - <span data-ttu-id="04a75-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="04a75-289">contoso.com/a</span></span>
  - <span data-ttu-id="04a75-290">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-290">www.contoso.com</span></span>
  - <span data-ttu-id="04a75-291">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-291">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="04a75-292">Scenario: Vänster tilde</span><span class="sxs-lookup"><span data-stu-id="04a75-292">Scenario: Left tilde</span></span>

<span data-ttu-id="04a75-293">**Inträde**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="04a75-293">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="04a75-294">**Tillåt matchning** och **blockera matchning:**</span><span class="sxs-lookup"><span data-stu-id="04a75-294">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="04a75-295">contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-295">contoso.com</span></span>
  - <span data-ttu-id="04a75-296">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-296">www.contoso.com</span></span>
  - <span data-ttu-id="04a75-297">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-297">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="04a75-298">**Tillåt inte matchade** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="04a75-298">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="04a75-299">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-299">123contoso.com</span></span>
  - <span data-ttu-id="04a75-300">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="04a75-300">contoso.com/abc</span></span>
  - <span data-ttu-id="04a75-301">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="04a75-301">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="04a75-302">Scenario: Höger jokertecken suffix</span><span class="sxs-lookup"><span data-stu-id="04a75-302">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="04a75-303">**Inträde**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="04a75-303">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="04a75-304">**Tillåt matchning** och **blockera matchning:**</span><span class="sxs-lookup"><span data-stu-id="04a75-304">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="04a75-305">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="04a75-305">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="04a75-306">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="04a75-306">contoso.com/a</span></span>
  - <span data-ttu-id="04a75-307">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="04a75-307">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="04a75-308">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="04a75-308">contoso.com/ab</span></span>
  - <span data-ttu-id="04a75-309">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="04a75-309">contoso.com/b</span></span>
  - <span data-ttu-id="04a75-310">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="04a75-310">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="04a75-311">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="04a75-311">contoso.com/ba</span></span>

- <span data-ttu-id="04a75-312">**Tillåt inte matchade** och **Blockera inte matchas:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-312">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="04a75-313">Scenario: Vänster jokerteckenunderdomän och höger jokertecken suffix</span><span class="sxs-lookup"><span data-stu-id="04a75-313">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="04a75-314">**Inträde**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="04a75-314">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="04a75-315">**Tillåt matchning** och **blockera matchning:**</span><span class="sxs-lookup"><span data-stu-id="04a75-315">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="04a75-316">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="04a75-316">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="04a75-317">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="04a75-317">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="04a75-318">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="04a75-318">www.contoso.com/a</span></span>
  - <span data-ttu-id="04a75-319">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="04a75-319">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="04a75-320">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="04a75-320">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="04a75-321">**Tillåt inte matchade** och **Blockera inte matchas:** contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="04a75-321">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="04a75-322">Scenario: Vänster och höger tilde</span><span class="sxs-lookup"><span data-stu-id="04a75-322">Scenario: Left and right tilde</span></span>

<span data-ttu-id="04a75-323">**Inträde**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="04a75-323">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="04a75-324">**Tillåt matchning** och **blockera matchning:**</span><span class="sxs-lookup"><span data-stu-id="04a75-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="04a75-325">contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-325">contoso.com</span></span>
  - <span data-ttu-id="04a75-326">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="04a75-326">contoso.com/a</span></span>
  - <span data-ttu-id="04a75-327">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-327">www.contoso.com</span></span>
  - <span data-ttu-id="04a75-328">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="04a75-328">www.contoso.com/b</span></span>
  - <span data-ttu-id="04a75-329">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-329">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="04a75-330">**Tillåt inte matchade** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="04a75-330">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="04a75-331">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-331">123contoso.com</span></span>
  - <span data-ttu-id="04a75-332">contoso.org</span><span class="sxs-lookup"><span data-stu-id="04a75-332">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="04a75-333">Scenario: IP-adress</span><span class="sxs-lookup"><span data-stu-id="04a75-333">Scenario: IP address</span></span>

<span data-ttu-id="04a75-334">**Inträde**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="04a75-334">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="04a75-335">**Tillåt matchning** och **blockmatchning:** 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="04a75-335">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="04a75-336">**Tillåt inte matchade** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="04a75-336">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="04a75-337">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="04a75-337">1.2.3.4/a</span></span>
  - <span data-ttu-id="04a75-338">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="04a75-338">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="04a75-339">IP-adress med höger jokertecken</span><span class="sxs-lookup"><span data-stu-id="04a75-339">IP address with right wildcard</span></span>

<span data-ttu-id="04a75-340">**Inträde**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="04a75-340">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="04a75-341">**Tillåt matchning** och **blockera matchning:**</span><span class="sxs-lookup"><span data-stu-id="04a75-341">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="04a75-342">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="04a75-342">1.2.3.4/b</span></span>
  - <span data-ttu-id="04a75-343">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="04a75-343">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="04a75-344">Exempel på ogiltiga poster</span><span class="sxs-lookup"><span data-stu-id="04a75-344">Examples of invalid entries</span></span>

<span data-ttu-id="04a75-345">Följande poster är ogiltiga:</span><span class="sxs-lookup"><span data-stu-id="04a75-345">The following entries are invalid:</span></span>

- <span data-ttu-id="04a75-346">**Domänvärden saknas eller är ogiltiga:**</span><span class="sxs-lookup"><span data-stu-id="04a75-346">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="04a75-347">Contoso</span><span class="sxs-lookup"><span data-stu-id="04a75-347">contoso</span></span>
  - <span data-ttu-id="04a75-348">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="04a75-348">\*.contoso.\*</span></span>
  - <span data-ttu-id="04a75-349">\*.com (på marknaden)</span><span class="sxs-lookup"><span data-stu-id="04a75-349">\*.com</span></span>
  - <span data-ttu-id="04a75-350">\*Pdf</span><span class="sxs-lookup"><span data-stu-id="04a75-350">\*.pdf</span></span>

- <span data-ttu-id="04a75-351">**Jokertecken på text eller utan mellanrum:**</span><span class="sxs-lookup"><span data-stu-id="04a75-351">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="04a75-352">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="04a75-352">\*contoso.com</span></span>
  - <span data-ttu-id="04a75-353">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="04a75-353">contoso.com\*</span></span>
  - <span data-ttu-id="04a75-354">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="04a75-354">\*1.2.3.4</span></span>
  - <span data-ttu-id="04a75-355">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="04a75-355">1.2.3.4\*</span></span>
  - <span data-ttu-id="04a75-356">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="04a75-356">contoso.com/a\*</span></span>
  - <span data-ttu-id="04a75-357">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="04a75-357">contoso.com/ab\*</span></span>

- <span data-ttu-id="04a75-358">**IP-adresser med portar:**</span><span class="sxs-lookup"><span data-stu-id="04a75-358">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="04a75-359">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="04a75-359">contoso.com:443</span></span>
  - <span data-ttu-id="04a75-360">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="04a75-360">abc.contoso.com:25</span></span>

- <span data-ttu-id="04a75-361">**Icke-beskrivande jokertecken:**</span><span class="sxs-lookup"><span data-stu-id="04a75-361">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="04a75-362">\*.\*</span><span class="sxs-lookup"><span data-stu-id="04a75-362">\*.\*</span></span>

- <span data-ttu-id="04a75-363">**Jokertecken i mitten:**</span><span class="sxs-lookup"><span data-stu-id="04a75-363">**Middle wildcards**:</span></span>

  - <span data-ttu-id="04a75-364">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="04a75-364">conto\*so.com</span></span>
  - <span data-ttu-id="04a75-365">conto ~so.com</span><span class="sxs-lookup"><span data-stu-id="04a75-365">conto~so.com</span></span>

- <span data-ttu-id="04a75-366">**Dubbla jokertecken**</span><span class="sxs-lookup"><span data-stu-id="04a75-366">**Double wildcards**</span></span>

  - <span data-ttu-id="04a75-367">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="04a75-367">contoso.com/\*\*</span></span>
  - <span data-ttu-id="04a75-368">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="04a75-368">contoso.com/\*/\*</span></span>
