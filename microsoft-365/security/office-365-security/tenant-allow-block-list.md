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
ms.openlocfilehash: 742a44c7ed63c8a3037e2ada295c94f89afa9c93
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726811"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a><span data-ttu-id="c7fd0-103">Hantera webbadresser och filer i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="c7fd0-103">Manage URLs and files in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="c7fd0-104">Funktionerna som beskrivs i det här avsnittet är i förhandsversion, kan komma att ändras och är inte tillgängliga i alla organisationer.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="c7fd0-105">I Microsoft 365-organisationer med postlådor i Exchange Online- eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kanske du inte håller med om EOP-filtreringsdomen.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="c7fd0-106">Ett bra meddelande kan till exempel markeras som dåligt (falskt positivt) eller så kan ett felaktigt meddelande tillåtas (ett falskt negativt).</span><span class="sxs-lookup"><span data-stu-id="c7fd0-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="c7fd0-107">Listan Tillåt/blockera innehavare i Security & Compliance Center ger dig ett sätt att manuellt åsidosätta Microsoft 365-filtreringsutlåtandena.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="c7fd0-108">Listan Tillåt/blockera klienter används under e-postflödet och vid tidpunkten för användarens klick.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="c7fd0-109">Du kan ange webbadresser och filer som ska tillåtas eller blockeras i listan Tillåt/blockera klient.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-109">You can specify URLs and files to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="c7fd0-110">I det här avsnittet beskrivs hur du konfigurerar poster i listan Tillåt/blockera klient i Security & Compliance Center eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="c7fd0-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c7fd0-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="c7fd0-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c7fd0-112">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c7fd0-113">Om du vill gå direkt till sidan **Tillåt/blockera lista för klienter** använder du <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="c7fd0-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="c7fd0-114">Du anger filer med hjälp av sha256-hash-värdet för filen.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-114">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="c7fd0-115">Om du vill hitta SHA256-hash-värdet för en fil i Windows kör du följande kommando i en kommandotolk:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-115">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="c7fd0-116">Ett exempelvärde är `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="c7fd0-116">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="c7fd0-117">Perceptuella hash-värden (pHash) är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-117">Perceptual hash (pHash) values are not allowed.</span></span>

- <span data-ttu-id="c7fd0-118">De tillgängliga URL-värdena beskrivs i [URL-syntaxen för avsnittet Tillåt/blockera klient](#url-syntax-for-the-tenant-allowblock-list) senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-118">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="c7fd0-119">Med listan Tillåt/blockera klient kan högst 500 poster för webbadresser och 500 poster för filh hashar.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-119">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="c7fd0-120">En post ska vara aktiv inom 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-120">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="c7fd0-121">Blockposter har företräde framför tillåta transaktioner.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-121">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="c7fd0-122">Som standard upphör posterna i listan Tillåt/blockera klient att gälla efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-122">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="c7fd0-123">Du kan ange ett datum eller ange att de aldrig ska upphöra att gälla.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-123">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="c7fd0-124">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c7fd0-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c7fd0-125">Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="c7fd0-125">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c7fd0-126">Du måste tilldelas behörigheter innan du kan göra procedurerna i det här avsnittet:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-126">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="c7fd0-127">Om du vill lägga till och ta bort värden från listan Tillåt/blockera klient måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-127">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="c7fd0-128">**Organisationshantering** eller **säkerhetsadministratör** i [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c7fd0-128">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="c7fd0-129">**Organisationshantering** eller **hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="c7fd0-129">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="c7fd0-130">För skrivskyddad åtkomst till listan Tillåt/blockera klient måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-130">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="c7fd0-131">**Säkerhetsläsaren** i [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c7fd0-131">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="c7fd0-132">**Endast visningsorganisation i** [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="c7fd0-132">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c7fd0-133">Använda security & Compliance Center för att skapa URL-poster i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="c7fd0-133">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c7fd0-134">Mer information om syntaxen för URL-poster finns i [URL-syntaxen för avsnittet Tillåt/blockera klient](#url-syntax-for-the-tenant-allowblock-list) senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-134">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="c7fd0-135">Gå till Tillåt/blockera listor för **&-efterlevnad** i säkerhets- & \> **Policy** \> **efterlevnadscenter**.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c7fd0-136">Kontrollera att fliken **Webbadresser** är markerad på sidan **Tillåt/blockera lista** för klienter och klicka sedan på **Lägg till**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-136">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="c7fd0-137">Konfigurera följande inställningar i utfällbara **url:er** som visas:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-137">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c7fd0-138">**Lägg till webbadresser med jokertecken:** Ange en URL per rad, upp till högst 20.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-138">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="c7fd0-139">**Blockera/tillåt**: Välj om du vill **tillåta** eller **blockera** de angivna webbadresserna.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-139">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="c7fd0-140">**Upphör aldrig att gälla**: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-140">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="c7fd0-141">Kontrollera att inställningen är inaktiverad ( ![ Stäng av ) och använd rutan Upphör att gälla för att ange ](../../media/scc-toggle-off.png) **utgångsdatum** för transaktionerna.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-141">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="c7fd0-142">eller</span><span class="sxs-lookup"><span data-stu-id="c7fd0-142">or</span></span>

     - <span data-ttu-id="c7fd0-143">Flytta växlingsknappen åt höger för att konfigurera posterna så att de aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-143">Move the toggle to the right to configure the entries to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="c7fd0-145">.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-145">.</span></span>

   - <span data-ttu-id="c7fd0-146">**Valfri anmärkning:** Ange beskrivande text för posterna.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-146">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="c7fd0-147">När du är klar klickar du på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-147">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c7fd0-148">Använda Security & Compliance Center för att skapa filposter i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="c7fd0-148">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c7fd0-149">Gå till Tillåt/blockera listor för **&-efterlevnad** i säkerhets- & \> **Policy** \> **efterlevnadscenter**.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-149">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c7fd0-150">På sidan **Tillåt/blockera lista för klienter** väljer du fliken **Filer** och klickar sedan på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-150">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="c7fd0-151">Konfigurera följande inställningar i utfällbara **filer** som visas:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-151">In the **Add new files** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c7fd0-152">**Lägg till fil hashar:** Ange ett SHA256 hash-värde per rad, upp till maximalt 20.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-152">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="c7fd0-153">**Blockera/Tillåt**: Välj om du vill **tillåta** eller **blockera** de angivna filerna.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-153">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified files.</span></span>

   - <span data-ttu-id="c7fd0-154">**Upphör aldrig att gälla**: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-154">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="c7fd0-155">Kontrollera att inställningen är inaktiverad ( ![ Stäng av ) och använd rutan Upphör att gälla för att ange ](../../media/scc-toggle-off.png) **utgångsdatum** för transaktionerna.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-155">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="c7fd0-156">eller</span><span class="sxs-lookup"><span data-stu-id="c7fd0-156">or</span></span>

     - <span data-ttu-id="c7fd0-157">Flytta växlingsknappen åt höger för att konfigurera posterna så att de aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-157">Move the toggle to the right to configure the entries to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="c7fd0-159">.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-159">.</span></span>

   - <span data-ttu-id="c7fd0-160">**Valfri anmärkning:** Ange beskrivande text för posterna.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-160">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="c7fd0-161">När du är klar klickar du på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-161">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c7fd0-162">Använda Security & Compliance Center för att visa URL- och filposter i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="c7fd0-162">Use the Security & Compliance Center to view URL and file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c7fd0-163">Gå till Tillåt/blockera listor för **&-efterlevnad** i säkerhets- & \> **Policy** \> **efterlevnadscenter**.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-163">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c7fd0-164">Välj fliken **Webbadresser** eller fliken **Filer.**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-164">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="c7fd0-165">Klicka på följande kolumnrubriker för att sortera i stigande eller fallande ordning:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-165">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="c7fd0-166">**Värde**: URL:en eller filhh.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-166">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="c7fd0-167">**Åtgärd**: **Blockera** eller **tillåt**.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-167">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="c7fd0-168">**Senast uppdaterat datum**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-168">**Last updated date**</span></span>
- <span data-ttu-id="c7fd0-169">**Utgångsdatum**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-169">**Expiration date**</span></span>
- <span data-ttu-id="c7fd0-170">**Observera**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-170">**Note**</span></span>

<span data-ttu-id="c7fd0-171">Klicka på **Gruppera** om du vill gruppera transaktionerna efter **Åtgärd** (**Block** eller **Tillåt**) eller **Ingen**.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-171">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="c7fd0-172">Klicka på **Sök,** ange hela eller delar av en URL eller ett filvärde och tryck sedan på RETUR för att hitta ett visst värde.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-172">Click **Search**, enter all or part of a URL or file value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="c7fd0-173">När du är klar klickar du på **Rensa** ![ sökikonen Rensa sökning ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="c7fd0-173">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="c7fd0-174">Klicka på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-174">Click **Filter**.</span></span> <span data-ttu-id="c7fd0-175">Konfigurera någon av följande inställningar i **utfällbara filter** som visas:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-175">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="c7fd0-176">**Åtgärd**: Välj **Tillåt,** **Blockera** eller båda.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-176">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="c7fd0-177">**Upphör aldrig att gälla:** Välj av ![ (Växla ](../../media/scc-toggle-off.png) av) eller på ( ![ Växla på ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="c7fd0-177">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="c7fd0-178">**Senast uppdaterad**: Välj ett startdatum (**Från**), ett slutdatum (**Till**) eller båda.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="c7fd0-179">**Utgångsdatum**: Välj ett startdatum (**Från**), ett slutdatum (**Till**) eller båda.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="c7fd0-180">När du är klar klickar du på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="c7fd0-181">Om du vill ta bort befintliga filter klickar du på **Filtrera**och klickar på **Rensa filter**i det utfällbara **filter som** visas.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c7fd0-182">Använda Security & Compliance Center för att ändra URL- och filposter i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="c7fd0-182">Use the Security & Compliance Center to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c7fd0-183">Du kan inte ändra själva URL:en: eller filvärdet.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-183">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="c7fd0-184">I stället måste du ta bort posten och återskapa den.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-184">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="c7fd0-185">Gå till Tillåt/blockera listor för **&-efterlevnad** i säkerhets- & \> **Policy** \> **efterlevnadscenter**.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c7fd0-186">Välj fliken **Webbadresser** eller fliken **Filer.**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="c7fd0-187">Markera den post som du vill ändra och klicka sedan på **Ikonen Redigera** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) redigera.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-187">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="c7fd0-188">Konfigurera följande inställningar i utfällbara utfällbara inställningar:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c7fd0-189">**Blockera/tillåt**: Välj **Tillåt** eller **Blockera**.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-189">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="c7fd0-190">**Upphör aldrig att gälla**: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-190">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="c7fd0-191">Kontrollera att inställningen är inaktiverad ( ![ Stäng av ) och använd rutan Upphör att gälla ](../../media/scc-toggle-off.png) **för** att ange förfallodatumet för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-191">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="c7fd0-192">eller</span><span class="sxs-lookup"><span data-stu-id="c7fd0-192">or</span></span>

     - <span data-ttu-id="c7fd0-193">Flytta växlingsknappen åt höger för att konfigurera posten så att den aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-193">Move the toggle to the right to configure the entry to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="c7fd0-195">.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-195">.</span></span>

   - <span data-ttu-id="c7fd0-196">**Valfri anmärkning:** Ange beskrivande text för posten.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-196">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="c7fd0-197">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-197">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="c7fd0-198">Använd säkerhets- & Compliance Center för att ta bort URL- och filposter från listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="c7fd0-198">Use the Security & Compliance Center to remove URL and file entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c7fd0-199">Gå till Tillåt/blockera listor för **&-efterlevnad** i säkerhets- & \> **Policy** \> **efterlevnadscenter**.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c7fd0-200">Välj fliken **Webbadresser** eller fliken **Filer.**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-200">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="c7fd0-201">Markera den post som du vill ta bort och klicka sedan på **Ikonen Ta bort borttagning** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="c7fd0-201">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="c7fd0-202">Klicka på **Ta bort**i varningsdialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-202">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="c7fd0-203">Använd Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="c7fd0-203">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c7fd0-204">Använda PowerShell för att lägga till URL- och filposter i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="c7fd0-204">Use PowerShell to add URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c7fd0-205">Om du vill lägga till URL- och filposter i listan Tillåt/blockera klienter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-205">To add URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="c7fd0-206">I det här exemplet läggs en URL-blockpost för contoso.com och alla underdomäner (till exempel contoso.com, www.contoso.com och xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c7fd0-206">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="c7fd0-207">Eftersom vi inte använde parametrarna ExpirationDate eller NoExpiration upphör posten att gälla efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-207">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="c7fd0-208">I det här exemplet läggs en fil tillåta post för de angivna filer som aldrig upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-208">This example adds a file allow entry for the specified files that never expires.</span></span>

<span data-ttu-id="c7fd0-209">Detaljerad syntax- och parameterinformation finns i [Ny-KlientEns 111111.For](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)detailed syntax and parameter information, see New-TenantAllowBlockListItems .</span><span class="sxs-lookup"><span data-stu-id="c7fd0-209">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c7fd0-210">Använda PowerShell för att visa URL- och filposter i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="c7fd0-210">Use PowerShell to view URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c7fd0-211">Om du vill visa URL- och filposter i listan Tillåt/blockera klienter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-211">To view URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="c7fd0-212">I det här exemplet returneras alla blockerade webbadresser.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-212">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="c7fd0-213">I det här exemplet returneras information om det angivna filhh-värdet.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-213">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="c7fd0-214">Detaljerad syntax- och parameterinformation finns i [Hämta-klientEnAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c7fd0-214">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c7fd0-215">Använda PowerShell för att ändra URL- och filposter i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="c7fd0-215">Use PowerShell to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c7fd0-216">Du kan inte ändra själva URL:en: eller filvärdet.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-216">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="c7fd0-217">I stället måste du ta bort posten och återskapa den.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-217">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="c7fd0-218">Om du vill ändra URL- och filposter i listan Tillåt/blockera klienter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-218">To modify URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="c7fd0-219">I det här exemplet ändras förfallodatumet för den angivna posten.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-219">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="c7fd0-220">Detaljerad syntax- och parameterinformation finns i [Ange-klientEnAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c7fd0-220">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="c7fd0-221">Använda PowerShell för att ta bort URL- och filposter från listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="c7fd0-221">Use PowerShell to remove URL and file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="c7fd0-222">Om du vill ta bort URL- och filposter från listan Tillåt/blockera klienter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-222">To remove URL and file entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="c7fd0-223">I det här exemplet tas den angivna URL-posten bort från listan Tillåt/blockera klient.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-223">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="c7fd0-224">Detaljerad syntax- och parameterinformation finns i [Ta bort-klientEnAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c7fd0-224">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="c7fd0-225">URL-syntax för listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="c7fd0-225">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="c7fd0-226">IP4v- och IPv6-adresser är tillåtna, men TCP/UDP-portar är det inte.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-226">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="c7fd0-227">Filnamnstillägg är inte tillåtna (till exempel test.pdf).</span><span class="sxs-lookup"><span data-stu-id="c7fd0-227">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="c7fd0-228">Unicode stöds inte, men Punycode är.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-228">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="c7fd0-229">Värdnamn är tillåtna om alla följande satser är sanna:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-229">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="c7fd0-230">Värdnamnet innehåller en punkt.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-230">The hostname contains a period.</span></span>
  - <span data-ttu-id="c7fd0-231">Det finns minst ett tecken till vänster om perioden.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-231">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="c7fd0-232">Det finns minst två tecken till höger om perioden.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-232">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="c7fd0-233">Till exempel `t.co` är tillåtet, `.com` eller är inte `contoso.` tillåtna.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-233">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="c7fd0-234">Undervägar är inte underförstådda.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-234">Subpaths are not implied.</span></span>

  <span data-ttu-id="c7fd0-235">Innehåller till exempel `contoso.com` inte `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="c7fd0-235">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="c7fd0-236">Jokertecken (\*) tillåts i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-236">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="c7fd0-237">Ett vänster jokertecken måste följas av en punkt för att ange en underdomän.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-237">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="c7fd0-238">Till exempel `*.contoso.com` är tillåtet, `*contoso.com` är inte tillåtet.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-238">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="c7fd0-239">Ett höger jokertecken måste följa ett snedstreck (/) för att ange en bana.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-239">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="c7fd0-240">Till exempel `contoso.com/*` är tillåtet, `contoso.com*` eller är inte `contoso.com/ab*` tillåtna.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-240">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="c7fd0-241">Alla underbanor är inte underförstådda av ett höger jokertecken.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-241">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="c7fd0-242">Innehåller till exempel `contoso.com/*` inte `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="c7fd0-242">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="c7fd0-243">`*.com*`är ogiltigt (inte en lösningsbar domän och det högra jokertecknet följer inte ett snedstreck).</span><span class="sxs-lookup"><span data-stu-id="c7fd0-243">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="c7fd0-244">Jokertecken är inte tillåtna i IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-244">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="c7fd0-245">Tilde -tecknet (~) är tillgängligt i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-245">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="c7fd0-246">En vänster tilde innebär en domän och alla underdomäner.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-246">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="c7fd0-247">Till exempel `~contoso.com` innehåller `contoso.com` och `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="c7fd0-247">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="c7fd0-248">URL-poster som innehåller protokoll (till exempel `http://` `https://` , eller ) `ftp://` misslyckas, eftersom URL-poster gäller för alla protokoll.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-248">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="c7fd0-249">Ett användarnamn eller lösenord stöds inte eller krävs inte.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-249">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="c7fd0-250">Citattecken (' eller ") är ogiltiga tecken.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-250">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="c7fd0-251">En webbadress bör innehålla alla omdirigeringar där det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-251">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="c7fd0-252">Scenarier för URL-post</span><span class="sxs-lookup"><span data-stu-id="c7fd0-252">URL entry scenarios</span></span>

<span data-ttu-id="c7fd0-253">Giltiga URL-poster och deras resultat beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="c7fd0-253">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="c7fd0-254">Scenario: Inga jokertecken</span><span class="sxs-lookup"><span data-stu-id="c7fd0-254">Scenario: No wildcards</span></span>

<span data-ttu-id="c7fd0-255">**Inträde**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="c7fd0-255">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="c7fd0-256">**Tillåt matchning**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-256">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="c7fd0-257">**Tillåt inte matchad:**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-257">**Allow not matched**:</span></span>

  - <span data-ttu-id="c7fd0-258">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-258">abc-contoso.com</span></span>
  - <span data-ttu-id="c7fd0-259">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c7fd0-259">contoso.com/a</span></span>
  - <span data-ttu-id="c7fd0-260">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-260">payroll.contoso.com</span></span>
  - <span data-ttu-id="c7fd0-261">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-261">test.com/contoso.com</span></span>
  - <span data-ttu-id="c7fd0-262">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-262">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="c7fd0-263">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-263">www.contoso.com</span></span>
  - <span data-ttu-id="c7fd0-264">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-264">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="c7fd0-265">**Blockera matchning:**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-265">**Block match**:</span></span>

  - <span data-ttu-id="c7fd0-266">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-266">contoso.com</span></span>
  - <span data-ttu-id="c7fd0-267">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c7fd0-267">contoso.com/a</span></span>
  - <span data-ttu-id="c7fd0-268">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-268">payroll.contoso.com</span></span>
  - <span data-ttu-id="c7fd0-269">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-269">test.com/contoso.com</span></span>
  - <span data-ttu-id="c7fd0-270">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-270">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="c7fd0-271">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-271">www.contoso.com</span></span>
  - <span data-ttu-id="c7fd0-272">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-272">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="c7fd0-273">**Blocket matchas inte:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-273">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="c7fd0-274">Scenario: Vänster jokertecken (underdomän)</span><span class="sxs-lookup"><span data-stu-id="c7fd0-274">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="c7fd0-275">**Inträde**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="c7fd0-275">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="c7fd0-276">**Tillåt matchning** och **blockmatchning:**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-276">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c7fd0-277">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-277">www.contoso.com</span></span>
  - <span data-ttu-id="c7fd0-278">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-278">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="c7fd0-279">**Tillåt inte matchade** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-279">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c7fd0-280">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-280">123contoso.com</span></span>
  - <span data-ttu-id="c7fd0-281">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-281">contoso.com</span></span>
  - <span data-ttu-id="c7fd0-282">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-282">test.com/contoso.com</span></span>
  - <span data-ttu-id="c7fd0-283">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="c7fd0-283">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="c7fd0-284">Scenario: Höger jokertecken högst upp i banan</span><span class="sxs-lookup"><span data-stu-id="c7fd0-284">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="c7fd0-285">**Inträde**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="c7fd0-285">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="c7fd0-286">**Tillåt matchning** och **blockmatchning:**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-286">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c7fd0-287">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="c7fd0-287">contoso.com/a/b</span></span>
  - <span data-ttu-id="c7fd0-288">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="c7fd0-288">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="c7fd0-289">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-289">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="c7fd0-290">**Tillåt inte matchade** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-290">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c7fd0-291">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-291">contoso.com</span></span>
  - <span data-ttu-id="c7fd0-292">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c7fd0-292">contoso.com/a</span></span>
  - <span data-ttu-id="c7fd0-293">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-293">www.contoso.com</span></span>
  - <span data-ttu-id="c7fd0-294">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-294">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="c7fd0-295">Scenario: Vänster tilde</span><span class="sxs-lookup"><span data-stu-id="c7fd0-295">Scenario: Left tilde</span></span>

<span data-ttu-id="c7fd0-296">**Inträde**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="c7fd0-296">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="c7fd0-297">**Tillåt matchning** och **blockmatchning:**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-297">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c7fd0-298">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-298">contoso.com</span></span>
  - <span data-ttu-id="c7fd0-299">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-299">www.contoso.com</span></span>
  - <span data-ttu-id="c7fd0-300">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-300">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="c7fd0-301">**Tillåt inte matchade** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-301">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c7fd0-302">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-302">123contoso.com</span></span>
  - <span data-ttu-id="c7fd0-303">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="c7fd0-303">contoso.com/abc</span></span>
  - <span data-ttu-id="c7fd0-304">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="c7fd0-304">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="c7fd0-305">Scenario: Höger jokertecken suffix</span><span class="sxs-lookup"><span data-stu-id="c7fd0-305">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="c7fd0-306">**Inträde**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="c7fd0-306">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="c7fd0-307">**Tillåt matchning** och **blockmatchning:**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c7fd0-308">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-308">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="c7fd0-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c7fd0-309">contoso.com/a</span></span>
  - <span data-ttu-id="c7fd0-310">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="c7fd0-310">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="c7fd0-311">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="c7fd0-311">contoso.com/ab</span></span>
  - <span data-ttu-id="c7fd0-312">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="c7fd0-312">contoso.com/b</span></span>
  - <span data-ttu-id="c7fd0-313">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="c7fd0-313">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="c7fd0-314">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="c7fd0-314">contoso.com/ba</span></span>

- <span data-ttu-id="c7fd0-315">**Tillåt inte matchade** och **Blockera inte matchas:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-315">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="c7fd0-316">Scenario: Vänster jokertecken underdomän och höger jokertecken suffix</span><span class="sxs-lookup"><span data-stu-id="c7fd0-316">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="c7fd0-317">**Inträde**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="c7fd0-317">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="c7fd0-318">**Tillåt matchning** och **blockmatchning:**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-318">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c7fd0-319">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="c7fd0-319">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="c7fd0-320">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="c7fd0-320">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="c7fd0-321">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c7fd0-321">www.contoso.com/a</span></span>
  - <span data-ttu-id="c7fd0-322">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="c7fd0-322">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="c7fd0-323">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="c7fd0-323">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="c7fd0-324">**Tillåt inte matchade** och **Blockera inte matchas:** contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="c7fd0-324">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="c7fd0-325">Scenario: Vänster och höger tilde</span><span class="sxs-lookup"><span data-stu-id="c7fd0-325">Scenario: Left and right tilde</span></span>

<span data-ttu-id="c7fd0-326">**Inträde**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="c7fd0-326">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="c7fd0-327">**Tillåt matchning** och **blockmatchning:**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-327">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c7fd0-328">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-328">contoso.com</span></span>
  - <span data-ttu-id="c7fd0-329">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c7fd0-329">contoso.com/a</span></span>
  - <span data-ttu-id="c7fd0-330">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-330">www.contoso.com</span></span>
  - <span data-ttu-id="c7fd0-331">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="c7fd0-331">www.contoso.com/b</span></span>
  - <span data-ttu-id="c7fd0-332">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-332">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="c7fd0-333">**Tillåt inte matchade** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-333">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c7fd0-334">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-334">123contoso.com</span></span>
  - <span data-ttu-id="c7fd0-335">contoso.org</span><span class="sxs-lookup"><span data-stu-id="c7fd0-335">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="c7fd0-336">Scenario: IP-adress</span><span class="sxs-lookup"><span data-stu-id="c7fd0-336">Scenario: IP address</span></span>

<span data-ttu-id="c7fd0-337">**Inträde**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="c7fd0-337">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="c7fd0-338">**Tillåt matchning** och **blockmatchning:** 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="c7fd0-338">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="c7fd0-339">**Tillåt inte matchade** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-339">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c7fd0-340">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="c7fd0-340">1.2.3.4/a</span></span>
  - <span data-ttu-id="c7fd0-341">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="c7fd0-341">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="c7fd0-342">IP-adress med höger jokertecken</span><span class="sxs-lookup"><span data-stu-id="c7fd0-342">IP address with right wildcard</span></span>

<span data-ttu-id="c7fd0-343">**Inträde**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="c7fd0-343">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="c7fd0-344">**Tillåt matchning** och **blockmatchning:**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-344">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c7fd0-345">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="c7fd0-345">1.2.3.4/b</span></span>
  - <span data-ttu-id="c7fd0-346">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="c7fd0-346">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="c7fd0-347">Exempel på ogiltiga poster</span><span class="sxs-lookup"><span data-stu-id="c7fd0-347">Examples of invalid entries</span></span>

<span data-ttu-id="c7fd0-348">Följande poster är ogiltiga:</span><span class="sxs-lookup"><span data-stu-id="c7fd0-348">The following entries are invalid:</span></span>

- <span data-ttu-id="c7fd0-349">**Domänvärden som saknas eller är ogiltiga:**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-349">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="c7fd0-350">Contoso</span><span class="sxs-lookup"><span data-stu-id="c7fd0-350">contoso</span></span>
  - <span data-ttu-id="c7fd0-351">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="c7fd0-351">\*.contoso.\*</span></span>
  - <span data-ttu-id="c7fd0-352">\*.com (på marknaden)</span><span class="sxs-lookup"><span data-stu-id="c7fd0-352">\*.com</span></span>
  - <span data-ttu-id="c7fd0-353">\*Pdf</span><span class="sxs-lookup"><span data-stu-id="c7fd0-353">\*.pdf</span></span>

- <span data-ttu-id="c7fd0-354">**Jokertecken på text eller utan mellanrumstecken:**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-354">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="c7fd0-355">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-355">\*contoso.com</span></span>
  - <span data-ttu-id="c7fd0-356">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="c7fd0-356">contoso.com\*</span></span>
  - <span data-ttu-id="c7fd0-357">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="c7fd0-357">\*1.2.3.4</span></span>
  - <span data-ttu-id="c7fd0-358">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="c7fd0-358">1.2.3.4\*</span></span>
  - <span data-ttu-id="c7fd0-359">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="c7fd0-359">contoso.com/a\*</span></span>
  - <span data-ttu-id="c7fd0-360">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="c7fd0-360">contoso.com/ab\*</span></span>

- <span data-ttu-id="c7fd0-361">**IP-adresser med portar:**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-361">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="c7fd0-362">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="c7fd0-362">contoso.com:443</span></span>
  - <span data-ttu-id="c7fd0-363">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="c7fd0-363">abc.contoso.com:25</span></span>

- <span data-ttu-id="c7fd0-364">**Icke-beskrivande jokertecken:**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-364">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="c7fd0-365">\*.\*</span><span class="sxs-lookup"><span data-stu-id="c7fd0-365">\*.\*</span></span>

- <span data-ttu-id="c7fd0-366">**Jokertecken i mitten:**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-366">**Middle wildcards**:</span></span>

  - <span data-ttu-id="c7fd0-367">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-367">conto\*so.com</span></span>
  - <span data-ttu-id="c7fd0-368">conto ~so.com</span><span class="sxs-lookup"><span data-stu-id="c7fd0-368">conto~so.com</span></span>

- <span data-ttu-id="c7fd0-369">**Dubbla jokertecken**</span><span class="sxs-lookup"><span data-stu-id="c7fd0-369">**Double wildcards**</span></span>

  - <span data-ttu-id="c7fd0-370">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="c7fd0-370">contoso.com/\*\*</span></span>
  - <span data-ttu-id="c7fd0-371">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="c7fd0-371">contoso.com/\*/\*</span></span>
