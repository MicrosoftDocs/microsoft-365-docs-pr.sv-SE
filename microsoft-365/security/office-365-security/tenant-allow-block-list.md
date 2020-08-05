---
title: Hantera tillåtna och blockerade webbadresser i listan Tillåt/blockera klient
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
description: Administratörer kan lära sig hur du konfigurerar URL-poster i listan Tillåt/blockera klient i säkerhets- & Compliance Center.
ms.openlocfilehash: 5ff34cca922f18a015bd9da847facc8177cf8790
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552556"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="fa2bb-103">Hantera url:er i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="fa2bb-103">Manage URLs in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="fa2bb-104">Funktionerna som beskrivs i det här avsnittet är i förhandsversion, kan komma att ändras och är inte tillgängliga i alla organisationer.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="fa2bb-105">I Microsoft 365-organisationer med postlådor i Exchange Online- eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kanske du inte håller med om EOP-filtreringsdomen.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="fa2bb-106">Ett bra meddelande kan till exempel markeras som dåligt (falskt positivt) eller så kan ett felaktigt meddelande tillåtas (ett falskt negativt).</span><span class="sxs-lookup"><span data-stu-id="fa2bb-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="fa2bb-107">Listan Tillåt/blockera innehavare i Security & Compliance Center ger dig ett sätt att manuellt åsidosätta Microsoft 365-filtreringsutlåtandena.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="fa2bb-108">Listan Tillåt/blockera klienter används under e-postflödet och vid tidpunkten för användarens klick.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="fa2bb-109">Du kan ange webbadresser som ska tillåtas eller blockeras i listan Tillåt/blockera klient.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="fa2bb-110">I det här avsnittet beskrivs hur du konfigurerar poster i listan Tillåt/blockera klient i Security & Compliance Center eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="fa2bb-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fa2bb-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="fa2bb-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fa2bb-112">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="fa2bb-113">Om du vill gå direkt till sidan **Tillåt/blockera lista för klienter** använder du <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="fa2bb-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="fa2bb-114">De tillgängliga URL-värdena beskrivs i [URL-syntaxen för avsnittet Tillåt/blockera klient](#url-syntax-for-the-tenant-allowblock-list) senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="fa2bb-115">Med listan Tillåt/blockera klient kan högst 500 poster för webbadresser.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLss.</span></span>

- <span data-ttu-id="fa2bb-116">En post ska vara aktiv inom 15 minuter.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="fa2bb-117">Blockposter har företräde framför tillåta transaktioner.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="fa2bb-118">Som standard upphör posterna i listan Tillåt/blockera klient att gälla efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="fa2bb-119">Du kan ange ett datum eller ange att de aldrig ska upphöra att gälla.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="fa2bb-120">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="fa2bb-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="fa2bb-121">Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="fa2bb-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="fa2bb-122">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:</span><span class="sxs-lookup"><span data-stu-id="fa2bb-122">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="fa2bb-123">Om du vill lägga till och ta bort värden från listan Tillåt/blockera klient måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="fa2bb-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="fa2bb-124">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="fa2bb-124">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="fa2bb-125">**Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="fa2bb-125">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="fa2bb-126">För skrivskyddad åtkomst till listan Tillåt/blockera klient måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="fa2bb-126">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="fa2bb-127">**Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="fa2bb-127">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="fa2bb-128">**Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="fa2bb-128">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="fa2bb-129">Använda security & Compliance Center för att skapa URL-poster i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="fa2bb-129">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="fa2bb-130">Mer information om syntaxen för URL-poster finns i [URL-syntaxen för avsnittet Tillåt/blockera klient](#url-syntax-for-the-tenant-allowblock-list) senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-130">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="fa2bb-131">Gå till Tillåt/blockera listor för **&-efterlevnad** i säkerhets- & \> **Policy** \> **efterlevnadscenter**.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="fa2bb-132">Kontrollera att fliken **Webbadresser** är markerad på sidan **Tillåt/blockera lista** för klienter och klicka sedan på **Lägg till**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-132">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="fa2bb-133">Konfigurera följande inställningar i utfällbara **url:er** som visas:</span><span class="sxs-lookup"><span data-stu-id="fa2bb-133">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="fa2bb-134">**Lägg till webbadresser med jokertecken:** Ange en URL per rad, upp till högst 20.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-134">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="fa2bb-135">**Blockera/tillåt**: Välj om du vill **tillåta** eller **blockera** de angivna webbadresserna.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-135">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="fa2bb-136">**Upphör aldrig att gälla**: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="fa2bb-136">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="fa2bb-137">Kontrollera att inställningen är inaktiverad ( ![ Stäng av ) och använd rutan Upphör att gälla för att ange ](../../media/scc-toggle-off.png) **utgångsdatum** för transaktionerna.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-137">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="fa2bb-138">eller</span><span class="sxs-lookup"><span data-stu-id="fa2bb-138">or</span></span>

     - <span data-ttu-id="fa2bb-139">Flytta växlingsknappen åt höger för att konfigurera posterna så att de aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="fa2bb-139">Move the toggle to the right to configure the entries to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="fa2bb-141">.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-141">.</span></span>

   - <span data-ttu-id="fa2bb-142">**Valfri anmärkning:** Ange beskrivande text för posterna.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-142">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="fa2bb-143">När du är klar klickar du på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-143">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="fa2bb-144">Använda säkerhets- & compliance center för att visa poster i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="fa2bb-144">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="fa2bb-145">Gå till Tillåt/blockera listor för **&-efterlevnad** i säkerhets- & \> **Policy** \> **efterlevnadscenter**.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="fa2bb-146">Välj fliken **Webbadresser.**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-146">Select the **URLs** tab.</span></span>

<span data-ttu-id="fa2bb-147">Klicka på följande kolumnrubriker för att sortera i stigande eller fallande ordning:</span><span class="sxs-lookup"><span data-stu-id="fa2bb-147">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="fa2bb-148">**Värde**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-148">**Value**</span></span>
- <span data-ttu-id="fa2bb-149">**Åtgärd**: **Blockera** eller **tillåt**.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-149">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="fa2bb-150">**Senast uppdaterat datum**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-150">**Last updated date**</span></span>
- <span data-ttu-id="fa2bb-151">**Utgångsdatum**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-151">**Expiration date**</span></span>
- <span data-ttu-id="fa2bb-152">**Observera**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-152">**Note**</span></span>

<span data-ttu-id="fa2bb-153">Klicka på **Gruppera** om du vill gruppera transaktionerna efter **Åtgärd** (**Block** eller **Tillåt**) eller **Ingen**.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-153">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="fa2bb-154">Klicka på **Sök,** ange hela eller delar av ett värde och tryck sedan på RETUR för att hitta ett visst värde.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-154">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="fa2bb-155">När du är klar klickar du på **Rensa** ![ sökikonen Rensa sökning ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="fa2bb-155">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="fa2bb-156">Klicka på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-156">Click **Filter**.</span></span> <span data-ttu-id="fa2bb-157">Konfigurera någon av följande inställningar i **utfällbara filter** som visas:</span><span class="sxs-lookup"><span data-stu-id="fa2bb-157">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="fa2bb-158">**Åtgärd**: Välj **Tillåt,** **Blockera** eller båda.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-158">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="fa2bb-159">**Upphör aldrig att gälla:** Välj av ![ (Växla ](../../media/scc-toggle-off.png) av) eller på ( ![ Växla på ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="fa2bb-159">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="fa2bb-160">**Senast uppdaterad**: Välj ett startdatum (**Från**), ett slutdatum (**Till**) eller båda.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-160">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="fa2bb-161">**Utgångsdatum**: Välj ett startdatum (**Från**), ett slutdatum (**Till**) eller båda.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-161">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="fa2bb-162">När du är klar klickar du på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-162">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="fa2bb-163">Om du vill ta bort befintliga filter klickar du på **Filtrera**och klickar på **Rensa filter**i det utfällbara **filter som** visas.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-163">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="fa2bb-164">Använda säkerhets- & compliance center för att ändra poster i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="fa2bb-164">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="fa2bb-165">Du kan inte ändra själva URL-värdet.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-165">You can't modify the URL value itself.</span></span> <span data-ttu-id="fa2bb-166">I stället måste du ta bort posten och återskapa den.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-166">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="fa2bb-167">Gå till Tillåt/blockera listor för **&-efterlevnad** i säkerhets- & \> **Policy** \> **efterlevnadscenter**.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="fa2bb-168">Välj fliken **Webbadresser.**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-168">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="fa2bb-169">Markera den post som du vill ändra och klicka sedan på **Ikonen Redigera** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) redigera.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-169">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="fa2bb-170">Konfigurera följande inställningar i utfällbara utfällbara inställningar:</span><span class="sxs-lookup"><span data-stu-id="fa2bb-170">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="fa2bb-171">**Blockera/tillåt**: Välj **Tillåt** eller **Blockera**.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-171">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="fa2bb-172">**Upphör aldrig att gälla**: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="fa2bb-172">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="fa2bb-173">Kontrollera att inställningen är inaktiverad ( ![ Stäng av ) och använd rutan Upphör att gälla ](../../media/scc-toggle-off.png) **för** att ange förfallodatumet för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-173">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="fa2bb-174">eller</span><span class="sxs-lookup"><span data-stu-id="fa2bb-174">or</span></span>

     - <span data-ttu-id="fa2bb-175">Flytta växlingsknappen åt höger för att konfigurera posten så att den aldrig upphör att gälla:</span><span class="sxs-lookup"><span data-stu-id="fa2bb-175">Move the toggle to the right to configure the entry to never expire:</span></span> ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="fa2bb-177">.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-177">.</span></span>

   - <span data-ttu-id="fa2bb-178">**Valfri anmärkning:** Ange beskrivande text för posten.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-178">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="fa2bb-179">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-179">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="fa2bb-180">Använd Security & Compliance Center för att ta bort poster från listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="fa2bb-180">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="fa2bb-181">Gå till Tillåt/blockera listor för **&-efterlevnad** i säkerhets- & \> **Policy** \> **efterlevnadscenter**.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-181">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="fa2bb-182">Välj fliken **Webbadresser.**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-182">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="fa2bb-183">Markera den post som du vill ta bort och klicka sedan på **Ikonen Ta bort borttagning** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="fa2bb-183">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="fa2bb-184">Klicka på **Ta bort**i varningsdialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-184">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="fa2bb-185">Använd Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="fa2bb-185">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="fa2bb-186">Använda PowerShell för att lägga till poster i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="fa2bb-186">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="fa2bb-187">Om du vill lägga till poster i listan Tillåt/blockera klienter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="fa2bb-187">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="fa2bb-188">I det här exemplet läggs en URL-blockpost för contoso.com och alla underdomäner (till exempel contoso.com, www.contoso.com och xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="fa2bb-188">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="fa2bb-189">Eftersom vi inte använde parametrarna ExpirationDate eller NoExpiration upphör posten att gälla efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-189">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="fa2bb-190">Detaljerad syntax- och parameterinformation finns i [Ny-KlientEns 111111.For](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)detailed syntax and parameter information, see New-TenantAllowBlockListItems .</span><span class="sxs-lookup"><span data-stu-id="fa2bb-190">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="fa2bb-191">Använda PowerShell för att visa poster i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="fa2bb-191">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="fa2bb-192">Om du vill visa poster i listan Tillåt/blockera klienter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="fa2bb-192">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="fa2bb-193">I det här exemplet returneras alla blockerade webbadresser.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-193">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="fa2bb-194">Detaljerad syntax- och parameterinformation finns i [Hämta-klientEnAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="fa2bb-194">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="fa2bb-195">Använda PowerShell för att ändra poster i listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="fa2bb-195">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="fa2bb-196">Du kan inte ändra själva URL-värdet.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-196">You can't modify the URL value itself.</span></span> <span data-ttu-id="fa2bb-197">I stället måste du ta bort posten och återskapa den.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-197">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="fa2bb-198">Om du vill ändra poster i listan Tillåt/blockera klienter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="fa2bb-198">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="fa2bb-199">I det här exemplet ändras förfallodatumet för den angivna posten.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-199">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="fa2bb-200">Detaljerad syntax- och parameterinformation finns i [Ange-klientEnAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="fa2bb-200">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="fa2bb-201">Använda PowerShell för att ta bort poster från listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="fa2bb-201">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="fa2bb-202">Om du vill ta bort poster från listan Tillåt/blockera klienter använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="fa2bb-202">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="fa2bb-203">I det här exemplet tas den angivna URL-posten bort från listan Tillåt/blockera klient.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-203">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="fa2bb-204">Detaljerad syntax- och parameterinformation finns i [Ta bort-klientEnAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="fa2bb-204">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="fa2bb-205">URL-syntax för listan Tillåt/blockera klient</span><span class="sxs-lookup"><span data-stu-id="fa2bb-205">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="fa2bb-206">IP4v- och IPv6-adresser är tillåtna, men TCP/UDP-portar är det inte.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-206">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="fa2bb-207">Filnamnstillägg är inte tillåtna (till exempel test.pdf).</span><span class="sxs-lookup"><span data-stu-id="fa2bb-207">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="fa2bb-208">Unicode stöds inte, men Punycode är.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-208">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="fa2bb-209">Värdnamn är tillåtna om alla följande satser är sanna:</span><span class="sxs-lookup"><span data-stu-id="fa2bb-209">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="fa2bb-210">Värdnamnet innehåller en punkt.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-210">The hostname contains a period.</span></span>
  - <span data-ttu-id="fa2bb-211">Det finns minst ett tecken till vänster om perioden.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-211">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="fa2bb-212">Det finns minst två tecken till höger om perioden.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-212">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="fa2bb-213">Till exempel `t.co` är tillåtet, `.com` eller är inte `contoso.` tillåtna.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-213">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="fa2bb-214">Undervägar är inte underförstådda.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-214">Subpaths are not implied.</span></span>

  <span data-ttu-id="fa2bb-215">Innehåller till exempel `contoso.com` inte `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="fa2bb-215">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="fa2bb-216">Jokertecken (\*) tillåts i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="fa2bb-216">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="fa2bb-217">Ett vänster jokertecken måste följas av en punkt för att ange en underdomän.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-217">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="fa2bb-218">Till exempel `*.contoso.com` är tillåtet, `*contoso.com` är inte tillåtet.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-218">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="fa2bb-219">Ett höger jokertecken måste följa ett snedstreck (/) för att ange en bana.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-219">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="fa2bb-220">Till exempel `contoso.com/*` är tillåtet, `contoso.com*` eller är inte `contoso.com/ab*` tillåtna.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-220">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="fa2bb-221">Alla underbanor är inte underförstådda av ett höger jokertecken.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-221">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="fa2bb-222">Innehåller till exempel `contoso.com/*` inte `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="fa2bb-222">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="fa2bb-223">`*.com*`är ogiltigt (inte en lösningsbar domän och det högra jokertecknet följer inte ett snedstreck).</span><span class="sxs-lookup"><span data-stu-id="fa2bb-223">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="fa2bb-224">Jokertecken är inte tillåtna i IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-224">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="fa2bb-225">Tilde -tecknet (~) är tillgängligt i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="fa2bb-225">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="fa2bb-226">En vänster tilde innebär en domän och alla underdomäner.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-226">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="fa2bb-227">Till exempel `~contoso.com` innehåller `contoso.com` och `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="fa2bb-227">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="fa2bb-228">URL-poster som innehåller protokoll (till exempel `http://` `https://` , eller ) `ftp://` misslyckas, eftersom URL-poster gäller för alla protokoll.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-228">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="fa2bb-229">Ett användarnamn eller lösenord stöds inte eller krävs inte.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-229">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="fa2bb-230">Citattecken (' eller ") är ogiltiga tecken.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-230">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="fa2bb-231">En webbadress bör innehålla alla omdirigeringar där det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-231">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="fa2bb-232">Scenarier för URL-post</span><span class="sxs-lookup"><span data-stu-id="fa2bb-232">URL entry scenarios</span></span>

<span data-ttu-id="fa2bb-233">Giltiga URL-poster och deras resultat beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="fa2bb-233">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="fa2bb-234">Scenario: Inga jokertecken</span><span class="sxs-lookup"><span data-stu-id="fa2bb-234">Scenario: No wildcards</span></span>

<span data-ttu-id="fa2bb-235">**Inträde**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="fa2bb-235">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="fa2bb-236">**Tillåt matchning**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-236">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="fa2bb-237">**Tillåt inte matchad:**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-237">**Allow not matched**:</span></span>

  - <span data-ttu-id="fa2bb-238">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-238">abc-contoso.com</span></span>
  - <span data-ttu-id="fa2bb-239">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="fa2bb-239">contoso.com/a</span></span>
  - <span data-ttu-id="fa2bb-240">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-240">payroll.contoso.com</span></span>
  - <span data-ttu-id="fa2bb-241">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-241">test.com/contoso.com</span></span>
  - <span data-ttu-id="fa2bb-242">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-242">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="fa2bb-243">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-243">www.contoso.com</span></span>
  - <span data-ttu-id="fa2bb-244">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-244">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="fa2bb-245">**Blockera matchning:**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-245">**Block match**:</span></span>

  - <span data-ttu-id="fa2bb-246">contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-246">contoso.com</span></span>
  - <span data-ttu-id="fa2bb-247">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="fa2bb-247">contoso.com/a</span></span>
  - <span data-ttu-id="fa2bb-248">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-248">payroll.contoso.com</span></span>
  - <span data-ttu-id="fa2bb-249">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-249">test.com/contoso.com</span></span>
  - <span data-ttu-id="fa2bb-250">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-250">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="fa2bb-251">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-251">www.contoso.com</span></span>
  - <span data-ttu-id="fa2bb-252">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-252">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="fa2bb-253">**Blocket matchas inte:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-253">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="fa2bb-254">Scenario: Vänster jokertecken (underdomän)</span><span class="sxs-lookup"><span data-stu-id="fa2bb-254">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="fa2bb-255">**Inträde**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="fa2bb-255">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="fa2bb-256">**Tillåt matchning** och **blockmatchning:**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-256">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="fa2bb-257">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-257">www.contoso.com</span></span>
  - <span data-ttu-id="fa2bb-258">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-258">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="fa2bb-259">**Tillåt inte matchade** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-259">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="fa2bb-260">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-260">123contoso.com</span></span>
  - <span data-ttu-id="fa2bb-261">contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-261">contoso.com</span></span>
  - <span data-ttu-id="fa2bb-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="fa2bb-263">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="fa2bb-263">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="fa2bb-264">Scenario: Höger jokertecken högst upp i banan</span><span class="sxs-lookup"><span data-stu-id="fa2bb-264">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="fa2bb-265">**Inträde**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="fa2bb-265">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="fa2bb-266">**Tillåt matchning** och **blockmatchning:**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-266">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="fa2bb-267">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="fa2bb-267">contoso.com/a/b</span></span>
  - <span data-ttu-id="fa2bb-268">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="fa2bb-268">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="fa2bb-269">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-269">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="fa2bb-270">**Tillåt inte matchade** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-270">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="fa2bb-271">contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-271">contoso.com</span></span>
  - <span data-ttu-id="fa2bb-272">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="fa2bb-272">contoso.com/a</span></span>
  - <span data-ttu-id="fa2bb-273">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-273">www.contoso.com</span></span>
  - <span data-ttu-id="fa2bb-274">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-274">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="fa2bb-275">Scenario: Vänster tilde</span><span class="sxs-lookup"><span data-stu-id="fa2bb-275">Scenario: Left tilde</span></span>

<span data-ttu-id="fa2bb-276">**Inträde**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="fa2bb-276">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="fa2bb-277">**Tillåt matchning** och **blockmatchning:**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="fa2bb-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-278">contoso.com</span></span>
  - <span data-ttu-id="fa2bb-279">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-279">www.contoso.com</span></span>
  - <span data-ttu-id="fa2bb-280">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-280">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="fa2bb-281">**Tillåt inte matchade** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-281">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="fa2bb-282">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-282">123contoso.com</span></span>
  - <span data-ttu-id="fa2bb-283">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="fa2bb-283">contoso.com/abc</span></span>
  - <span data-ttu-id="fa2bb-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="fa2bb-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="fa2bb-285">Scenario: Höger jokertecken suffix</span><span class="sxs-lookup"><span data-stu-id="fa2bb-285">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="fa2bb-286">**Inträde**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="fa2bb-286">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="fa2bb-287">**Tillåt matchning** och **blockmatchning:**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="fa2bb-288">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-288">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="fa2bb-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="fa2bb-289">contoso.com/a</span></span>
  - <span data-ttu-id="fa2bb-290">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="fa2bb-290">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="fa2bb-291">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="fa2bb-291">contoso.com/ab</span></span>
  - <span data-ttu-id="fa2bb-292">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="fa2bb-292">contoso.com/b</span></span>
  - <span data-ttu-id="fa2bb-293">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="fa2bb-293">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="fa2bb-294">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="fa2bb-294">contoso.com/ba</span></span>

- <span data-ttu-id="fa2bb-295">**Tillåt inte matchade** och **Blockera inte matchas:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-295">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="fa2bb-296">Scenario: Vänster jokertecken underdomän och höger jokertecken suffix</span><span class="sxs-lookup"><span data-stu-id="fa2bb-296">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="fa2bb-297">**Inträde**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="fa2bb-297">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="fa2bb-298">**Tillåt matchning** och **blockmatchning:**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="fa2bb-299">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="fa2bb-299">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="fa2bb-300">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="fa2bb-300">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="fa2bb-301">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="fa2bb-301">www.contoso.com/a</span></span>
  - <span data-ttu-id="fa2bb-302">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="fa2bb-302">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="fa2bb-303">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="fa2bb-303">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="fa2bb-304">**Tillåt inte matchade** och **Blockera inte matchas:** contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="fa2bb-304">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="fa2bb-305">Scenario: Vänster och höger tilde</span><span class="sxs-lookup"><span data-stu-id="fa2bb-305">Scenario: Left and right tilde</span></span>

<span data-ttu-id="fa2bb-306">**Inträde**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="fa2bb-306">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="fa2bb-307">**Tillåt matchning** och **blockmatchning:**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="fa2bb-308">contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-308">contoso.com</span></span>
  - <span data-ttu-id="fa2bb-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="fa2bb-309">contoso.com/a</span></span>
  - <span data-ttu-id="fa2bb-310">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-310">www.contoso.com</span></span>
  - <span data-ttu-id="fa2bb-311">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="fa2bb-311">www.contoso.com/b</span></span>
  - <span data-ttu-id="fa2bb-312">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-312">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="fa2bb-313">**Tillåt inte matchade** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-313">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="fa2bb-314">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-314">123contoso.com</span></span>
  - <span data-ttu-id="fa2bb-315">contoso.org</span><span class="sxs-lookup"><span data-stu-id="fa2bb-315">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="fa2bb-316">Scenario: IP-adress</span><span class="sxs-lookup"><span data-stu-id="fa2bb-316">Scenario: IP address</span></span>

<span data-ttu-id="fa2bb-317">**Inträde**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="fa2bb-317">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="fa2bb-318">**Tillåt matchning** och **blockmatchning:** 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="fa2bb-318">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="fa2bb-319">**Tillåt inte matchade** och **Blockera matchas inte:**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-319">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="fa2bb-320">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="fa2bb-320">1.2.3.4/a</span></span>
  - <span data-ttu-id="fa2bb-321">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="fa2bb-321">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="fa2bb-322">IP-adress med höger jokertecken</span><span class="sxs-lookup"><span data-stu-id="fa2bb-322">IP address with right wildcard</span></span>

<span data-ttu-id="fa2bb-323">**Inträde**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="fa2bb-323">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="fa2bb-324">**Tillåt matchning** och **blockmatchning:**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="fa2bb-325">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="fa2bb-325">1.2.3.4/b</span></span>
  - <span data-ttu-id="fa2bb-326">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="fa2bb-326">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="fa2bb-327">Exempel på ogiltiga poster</span><span class="sxs-lookup"><span data-stu-id="fa2bb-327">Examples of invalid entries</span></span>

<span data-ttu-id="fa2bb-328">Följande poster är ogiltiga:</span><span class="sxs-lookup"><span data-stu-id="fa2bb-328">The following entries are invalid:</span></span>

- <span data-ttu-id="fa2bb-329">**Domänvärden som saknas eller är ogiltiga:**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-329">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="fa2bb-330">Contoso</span><span class="sxs-lookup"><span data-stu-id="fa2bb-330">contoso</span></span>
  - <span data-ttu-id="fa2bb-331">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="fa2bb-331">\*.contoso.\*</span></span>
  - <span data-ttu-id="fa2bb-332">\*.com (på marknaden)</span><span class="sxs-lookup"><span data-stu-id="fa2bb-332">\*.com</span></span>
  - <span data-ttu-id="fa2bb-333">\*Pdf</span><span class="sxs-lookup"><span data-stu-id="fa2bb-333">\*.pdf</span></span>

- <span data-ttu-id="fa2bb-334">**Jokertecken på text eller utan mellanrumstecken:**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-334">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="fa2bb-335">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-335">\*contoso.com</span></span>
  - <span data-ttu-id="fa2bb-336">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="fa2bb-336">contoso.com\*</span></span>
  - <span data-ttu-id="fa2bb-337">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="fa2bb-337">\*1.2.3.4</span></span>
  - <span data-ttu-id="fa2bb-338">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="fa2bb-338">1.2.3.4\*</span></span>
  - <span data-ttu-id="fa2bb-339">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="fa2bb-339">contoso.com/a\*</span></span>
  - <span data-ttu-id="fa2bb-340">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="fa2bb-340">contoso.com/ab\*</span></span>

- <span data-ttu-id="fa2bb-341">**IP-adresser med portar:**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-341">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="fa2bb-342">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="fa2bb-342">contoso.com:443</span></span>
  - <span data-ttu-id="fa2bb-343">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="fa2bb-343">abc.contoso.com:25</span></span>

- <span data-ttu-id="fa2bb-344">**Icke-beskrivande jokertecken:**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-344">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="fa2bb-345">\*.\*</span><span class="sxs-lookup"><span data-stu-id="fa2bb-345">\*.\*</span></span>

- <span data-ttu-id="fa2bb-346">**Jokertecken i mitten:**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-346">**Middle wildcards**:</span></span>

  - <span data-ttu-id="fa2bb-347">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-347">conto\*so.com</span></span>
  - <span data-ttu-id="fa2bb-348">conto ~so.com</span><span class="sxs-lookup"><span data-stu-id="fa2bb-348">conto~so.com</span></span>

- <span data-ttu-id="fa2bb-349">**Dubbla jokertecken**</span><span class="sxs-lookup"><span data-stu-id="fa2bb-349">**Double wildcards**</span></span>

  - <span data-ttu-id="fa2bb-350">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="fa2bb-350">contoso.com/\*\*</span></span>
  - <span data-ttu-id="fa2bb-351">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="fa2bb-351">contoso.com/\*/\*</span></span>
