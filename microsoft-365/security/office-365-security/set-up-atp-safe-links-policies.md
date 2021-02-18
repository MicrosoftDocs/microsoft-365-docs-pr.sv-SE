---
title: Konfigurera principer för säkra länkar i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Administratörer kan ta reda på hur de visar, skapar, ändrar och tar bort principer för säkra länkar och globala inställningar för säkra länkar i Microsoft Defender för Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 29d777a7f351b9ab33232cb0136703ce3fa29842
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290159"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fd3e0-103">Konfigurera principer för säkra länkar i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="fd3e0-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fd3e0-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-104">**Applies to**</span></span>
- [<span data-ttu-id="fd3e0-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="fd3e0-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="fd3e0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd3e0-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> <span data-ttu-id="fd3e0-107">Den här artikeln är avsedd för företagskunder som har [Microsoft Defender för Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-107">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="fd3e0-108">Om du är hemanvändare och vill ha information om säkra länkar i Outlook kan du [läsa Mer Outlook.com säkerhet.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="fd3e0-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="fd3e0-109">Säkra länkar är en funktion i Microsoft Defender för [Office 365](office-365-atp.md) som ger URL-genomsökning av inkommande e-postmeddelanden i e-postflödet och tidpunkten för klickverifiering av URL:er och länkar i e-postmeddelanden och på andra platser.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-109">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="fd3e0-110">Mer information finns i [Säkra länkar i Microsoft Defender för Office 365.](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="fd3e0-110">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="fd3e0-111">Det finns ingen inbyggd eller standardprincip för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="fd3e0-112">För att få säker länksökning av URL:er måste du skapa en eller flera principer för Säkra länkar enligt beskrivningen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="fd3e0-113">Du konfigurerar de globala inställningarna för skydd mot **säkra länkar utanför** principerna för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="fd3e0-114">Instruktioner finns i Konfigurera [globala inställningar för Säkra länkar i Microsoft Defender för Office 365.](configure-global-settings-for-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="fd3e0-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="fd3e0-115">Du kan konfigurera principer för säkra länkar i Säkerhets- & och efterlevnadscenter eller i PowerShell (Exchange Online PowerShell för kvalificerade Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor, men med Microsoft Defender för Office 365-tilläggsprenumerationer).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-115">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="fd3e0-116">Grunderna i en princip för säkra länkar är:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-116">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="fd3e0-117">Principen **för** säkra länkar: Aktivera skydd mot säkra länkar, aktivera URL-genomsökning i realtid, ange om du vill vänta med att skanning i realtid slutförs innan meddelandet levereras, aktivera genomsökning för interna meddelanden, ange om användaren ska klicka på URL-adresser och ange om användarna ska kunna klicka på webbadressen.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-117">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="fd3e0-118">**Regeln för säkra länkar:** Anger prioritet och mottagarfilter (vem principen gäller för).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-118">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="fd3e0-119">Skillnaden mellan dessa två element är inte uppenbara när du hanterar säkerhetschefer i Säkerhets- och & Efterlevnadscenter:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-119">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="fd3e0-120">När du skapar en princip för säkra länkar skapar du i själva verket en regel för säkra länkar och den associerade principen för säkra länkar samtidigt som du använder samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-120">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="fd3e0-121">När du ändrar en princip för säkra länkar ändras regeln för säkra länkar om namn, prioritet, aktiverad eller inaktiverad, och mottagarens filter ändrar regeln för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-121">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="fd3e0-122">Alla andra inställningar ändrar den associerade principen för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-122">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="fd3e0-123">När du tar bort en princip för säkra länkar tas regeln för säkra länkar och den tillhörande principen för säkra länkar bort.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-123">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="fd3e0-124">I Exchange Online PowerShell eller fristående EOP PowerShell hanterar du policyn och regeln separat.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-124">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="fd3e0-125">Mer information finns i avsnittet Använda Exchange Online PowerShell eller [fristående EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) för att konfigurera principer för säkra länkar längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-125">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fd3e0-126">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="fd3e0-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fd3e0-127">Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-127">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="fd3e0-128">Om du vill gå direkt **till sidan Säkra** länkar använder du <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="fd3e0-128">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="fd3e0-129">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="fd3e0-130">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="fd3e0-131">Du måste ha tilldelats behörigheter innan du kan utföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="fd3e0-132">Om du vill skapa, ändra och ta bort principer  för säkra  länkar måste du vara medlem i rollgrupperna Organisationshantering  eller Säkerhetsadministratör i Säkerhets- & Efterlevnadscenter och medlem i rollgruppen Organisationshantering i Exchange Online. </span><span class="sxs-lookup"><span data-stu-id="fd3e0-132">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="fd3e0-133">För skrivskyddade åtkomst till principer för säkra länkar måste du vara medlem i rollgrupperna **Global Reader** **eller** Säkerhetsläsare.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-133">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="fd3e0-134">Mer information finns i [Behörigheter i Säkerhets- & Efterlevnadscenter](permissions-in-the-security-and-compliance-center.md) och [Behörigheter i Exchange Online.](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="fd3e0-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="fd3e0-135">Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="fd3e0-136">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="fd3e0-137">.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-137">.</span></span> <span data-ttu-id="fd3e0-138">- **Rollgruppen Skrivskyddade organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddsåtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-138">- The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="fd3e0-139">Vi rekommenderar inställningar för principer för säkra länkar i [principinställningarna för Säkra länkar.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="fd3e0-139">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="fd3e0-140">Det kan ta upp till 30 minuter innan en ny eller uppdaterad princip tillämpas.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="fd3e0-141">[Nya funktioner läggs kontinuerligt till i Microsoft Defender för Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="fd3e0-141">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="fd3e0-142">När nya funktioner läggs till kan du behöva justera dina befintliga principer för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-142">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="fd3e0-143">Använda Säkerhets- & för att skapa principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="fd3e0-143">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="fd3e0-144">Om du skapar en egen princip för säkra länkar i Säkerhets- & efterlevnadscenter skapas regeln för säkra länkar och den tillhörande principen för säkra länkar samtidigt som samma namn används för båda.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-144">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="fd3e0-145">I Säkerhets- & Efterlevnadscenter går du till ATP **–** säkra \> **länkar för** \> **hothanteringspolicy.**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="fd3e0-146">Klicka på **Skapa på** sidan Säkra **länkar.**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-146">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="fd3e0-147">Guiden **Ny princip för säkra** länkar öppnas.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-147">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="fd3e0-148">Konfigurera **följande inställningar på** sidan Namnge principen:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-148">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="fd3e0-149">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-149">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="fd3e0-150">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-150">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="fd3e0-151">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="fd3e0-152">På sidan **Inställningar** som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-152">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="fd3e0-153">**Välj åtgärden för okända potentiellt skadliga URL:er i** meddelanden: Välj **På** för att aktivera skydd mot säkra länkar för länkar i e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-153">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="fd3e0-154">**Välj åtgärden för okända eller potentiellt skadliga URL-adresser i Microsoft Teams:** Välj **På** för att aktivera skydd mot säkra länkar för länkar i Teams.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-154">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="fd3e0-155">**Använd URL-skanning i realtid** för misstänkta länkar och länkar som pekar på filer: Välj den här inställningen om du vill aktivera sökning i realtid av länkar i e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-155">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="fd3e0-156">**Vänta tills URL-skanningen har slutförts innan** du levererar meddelandet: Välj den här inställningen om du vill vänta tills sökningen i realtid har slutförts innan meddelandet levereras.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-156">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="fd3e0-157">**Tillämpa säkra länkar på e-postmeddelanden** som skickas inom organisationen: Välj den här inställningen om du vill tillämpa principen För säkra länkar på meddelanden mellan interna avsändare och interna mottagare.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-157">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="fd3e0-158">**Spåra inte användarklick: Låt** den här inställningen vara avmarkerad om du vill aktivera uppföljningsanvändaren klick på URL-adresser i e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-158">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="fd3e0-159">**Tillåt inte att användare klickar sig fram till** den ursprungliga URL:en: Välj den här inställningen om du vill blockera användare från att klicka till den ursprungliga URL:en på [varningssidor.](atp-safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="fd3e0-159">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](atp-safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="fd3e0-160">**Skapa inte om följande URL:er:** Ger åtkomst till de angivna URL:er som annars skulle blockeras av säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-160">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="fd3e0-161">I rutan skriver du URL-adressen eller värdet som du vill använda och klickar sedan på</span><span class="sxs-lookup"><span data-stu-id="fd3e0-161">In the box, type the URL or value that you want, and then click</span></span> ![Knappikonen Lägg till](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="fd3e0-163">.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-163">.</span></span>

     <span data-ttu-id="fd3e0-164">Om du vill ta bort en befintlig post markerar du den och klickar sedan på</span><span class="sxs-lookup"><span data-stu-id="fd3e0-164">To remove an existing entry, select it and then click</span></span> ![Knappikonen Ta bort](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="fd3e0-166">.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-166">.</span></span>

     <span data-ttu-id="fd3e0-167">Information om postsyntaxen [finns i Postsyntax för listan "Ange inte följande URL:er".](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="fd3e0-167">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="fd3e0-168">Detaljerad information om dessa inställningar finns i inställningarna [för Säkra länkar för e-postmeddelanden](atp-safe-links.md#safe-links-settings-for-email-messages) och inställningar för Säkra länkar för Microsoft [Teams.](atp-safe-links.md#safe-links-settings-for-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="fd3e0-168">For detailed information about these settings, see [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="fd3e0-169">Fler rekommenderade värden för principinställningarna Standard och Strikt finns i [principinställningarna för Säkra länkar.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="fd3e0-169">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="fd3e0-170">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="fd3e0-171">På sidan **Används på** som visas identifierar du de interna mottagare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-171">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="fd3e0-172">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-172">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="fd3e0-173">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-173">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="fd3e0-174">Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-174">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="fd3e0-175">Klicka **på Lägg till ett villkor.**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-175">Click **Add a condition**.</span></span> <span data-ttu-id="fd3e0-176">I listrutan som visas väljer du ett villkor under **Används om:**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-176">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="fd3e0-177">**Mottagaren är: Anger** en eller flera postlådor, e-postanvändare eller e-postkontakter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-177">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="fd3e0-178">**Mottagaren är medlem i:** Anger en eller flera grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-178">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="fd3e0-179">**Mottagande domän är**: Anger mottagare i en eller flera av de godkända domänerna som har konfigurerats i din organisation.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-179">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="fd3e0-180">När du har valt villkoret visas en motsvarande listruta med **rutan Valfri av dessa.**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-180">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="fd3e0-181">Klicka i rutan och bläddra igenom listan med värden för att välja.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-181">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="fd3e0-182">Klicka i rutan och börja skriva för att filtrera listan och välja ett värde.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-182">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="fd3e0-183">Om du vill lägga till ytterligare värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-183">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="fd3e0-184">Om du vill ta bort enskilda poster klickar **du på ta** ![ ](../../media/scc-remove-icon.png) bort-ikonen för värdet.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-184">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="fd3e0-185">Om du vill ta bort hela villkoret klickar **du på ikonen** Ta bort i ![ ](../../media/scc-remove-icon.png) villkoret.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-185">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="fd3e0-186">Om du vill lägga till ytterligare ett villkor klickar **du på Lägg till ett** villkor och väljer ett återstående värde under Används **om.**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-186">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="fd3e0-187">Om du vill lägga till undantag **klickar du på Lägg till ett** villkor och väljer ett undantag under Utom **om.**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-187">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="fd3e0-188">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-188">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="fd3e0-189">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-189">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="fd3e0-190">Granska **inställningarna på sidan** Granska dina inställningar som visas.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-190">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="fd3e0-191">Du kan klicka **på Redigera** för varje inställning för att ändra den.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-191">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="fd3e0-192">Klicka på Slutför när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-192">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="fd3e0-193">Använda säkerhets- & efterlevnadscenter för att visa principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="fd3e0-193">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="fd3e0-194">I Säkerhets- & Efterlevnadscenter går du till ATP **–** säkra \> **länkar för** \> **hothanteringspolicy.**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-194">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="fd3e0-195">På sidan **Säkra** länkar väljer du en princip i listan och klickar på den (markera inte kryssrutan).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-195">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="fd3e0-196">Principinformationen visas i en flyg utfällning</span><span class="sxs-lookup"><span data-stu-id="fd3e0-196">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="fd3e0-197">Använda Säkerhets- & säkerhets- och efterlevnadscenter för att ändra principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="fd3e0-197">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="fd3e0-198">I Säkerhets- & Efterlevnadscenter går du till ATP **–** säkra \> **länkar för** \> **hothanteringspolicy.**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="fd3e0-199">På sidan **Säkra** länkar väljer du en princip i listan och klickar på den (markera inte kryssrutan).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-199">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="fd3e0-200">I den policyinformation som visas klickar du på **Redigera princip.**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-200">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="fd3e0-201">De tillgängliga inställningarna i flyg utfällpunkten som visas är identiska med de som beskrivs i Använda säkerhets- och & säkerhets- och [efterlevnadscentret](#use-the-security--compliance-center-to-create-safe-links-policies) för att skapa avsnittet för principer för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-201">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="fd3e0-202">Läs följande avsnitt om du vill aktivera eller inaktivera en princip eller ange prioritetsordning för principen.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-202">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="fd3e0-203">Aktivera eller inaktivera principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="fd3e0-203">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="fd3e0-204">I Säkerhets- & Efterlevnadscenter går du till ATP **–** säkra \> **länkar för** \> **hothanteringspolicy.**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-204">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="fd3e0-205">Observera värdet i **kolumnen** Status:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-205">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="fd3e0-206">Flytta växlingsknappen åt vänster om du vill inaktivera principen:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-206">Move the toggle to the left to disable the policy:</span></span> ![Inaktivera principen](../../media/scc-toggle-off.png)<span data-ttu-id="fd3e0-208">.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-208">.</span></span>

   - <span data-ttu-id="fd3e0-209">Flytta växlingsknappen åt höger om du vill aktivera principen:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-209">Move the toggle to the right to enable the policy:</span></span> ![Aktivera princip](../../media/scc-toggle-on.png)<span data-ttu-id="fd3e0-211">.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-211">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="fd3e0-212">Ange prioritet för principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="fd3e0-212">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="fd3e0-213">Som standard prioriteras principer för säkra länkar som baseras på den ordning som de skapades i (nyare principer har lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-213">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="fd3e0-214">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-214">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="fd3e0-215">Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-215">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="fd3e0-216">För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-216">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="fd3e0-217">Principer för säkra länkar visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-217">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

> [!NOTE]
> <span data-ttu-id="fd3e0-218">I Säkerhets- & Efterlevnadscenter kan du bara ändra prioriteten för principen för säkra länkar efter att du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-218">In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="fd3e0-219">I PowerShell kan du åsidosätta standardprioritet när du skapar regeln om säkra länkar (vilket kan påverka prioriteten för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-219">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="fd3e0-220">Du ändrar prioriteten för en princip genom att flytta principen uppåt eller nedåt i listan (du kan inte ändra **prioritetsnumret** direkt i Säkerhets- och efterlevnadscenter).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-220">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="fd3e0-221">I Säkerhets- & Efterlevnadscenter går du till ATP **–** säkra \> **länkar för** \> **hothanteringspolicy.**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="fd3e0-222">På sidan **Säkra** länkar väljer du en princip i listan och klickar på den (markera inte kryssrutan).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-222">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="fd3e0-223">I policyinformationen som visas klickar du på den tillgängliga prioritetsknappen:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-223">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="fd3e0-224">Principen Säkra länkar med **prioritetsvärdet** **0** har endast knappen **Minska** prioritet tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-224">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="fd3e0-225">Principen Säkra länkar med det lägsta **prioritetsvärdet** (till exempel **3)** har endast knappen Öka **prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-225">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="fd3e0-226">Om du har tre eller fler principer för säkra länkar,  har principer mellan de högsta och lägsta prioritetsvärdena både knapparna Öka prioritet och **Minska** prioritet tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-226">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="fd3e0-227">Klicka **på Öka prioritet** eller Minska **prioritet** om du vill ändra **prioritetsvärdet.**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-227">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="fd3e0-228">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-228">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="fd3e0-229">Använda Säkerhets- & för att ta bort principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="fd3e0-229">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="fd3e0-230">I Säkerhets- & Efterlevnadscenter går du till ATP **–** säkra \> **länkar för** \> **hothanteringspolicy.**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-230">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="fd3e0-231">På sidan **Säkra** länkar väljer du en princip i listan och klickar på den (markera inte kryssrutan).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-231">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="fd3e0-232">I den policyinformation som visas klickar du på **Ta bort princip** och sedan på **Ja** i varningsdialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-232">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="fd3e0-233">Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="fd3e0-233">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="fd3e0-234">Som tidigare beskrivits består en princip för säkra länkar av en princip för säkra länkar och en regel för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-234">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="fd3e0-235">I PowerShell visas skillnaden mellan principer för säkra länkar och regler för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-235">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="fd3e0-236">Du hanterar principer för säkra länkar med cmdlets **\* -SafeLinksPolicy** och hanterar regler för säkra länkar med cmdlet:arna **\* -SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-236">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="fd3e0-237">I PowerShell skapar du först principen för säkra länkar och sedan skapar du den regel för säkra länkar som identifierar principen som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-237">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="fd3e0-238">I PowerShell ändrar du inställningarna i principen för säkra länkar och regeln om säkra länkar separat.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-238">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="fd3e0-239">När du tar bort en princip för säkra länkar från PowerShell tas inte motsvarande regel för säkra länkar bort automatiskt och vice versa.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-239">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="fd3e0-240">Använda PowerShell för att skapa principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="fd3e0-240">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="fd3e0-241">Att skapa en princip för säkra länkar i PowerShell är en process i två steg:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-241">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="fd3e0-242">Skapa principen för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-242">Create the safe links policy.</span></span>
2. <span data-ttu-id="fd3e0-243">Skapa den regel för säkra länkar som anger principen för säkra länkar som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-243">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="fd3e0-244">Du kan skapa en ny regel för säkra länkar och tilldela en befintlig, oassocierad princip för säkra länkar till den.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-244">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="fd3e0-245">En regel för säkra länkar kan inte associeras med mer än en princip för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-245">A safe links rule can't be associated with more than one safe links policy.</span></span>
> 
> - <span data-ttu-id="fd3e0-246">Du kan konfigurera följande inställningar för nya principer för säkra länkar i PowerShell som inte är tillgängliga i Säkerhets- och &-efterlevnadscentret förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-246">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
> 
>   - <span data-ttu-id="fd3e0-247">Skapa den nya principen som inaktiverad _(aktiverad_ `$false` för **cmdleten New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-247">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="fd3e0-248">Ange prioriteten för principen när den skapas _(Priority)_ _\<Number\>_ på **cmdleten New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-248">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
> 
> - <span data-ttu-id="fd3e0-249">En ny princip för säkra länkar som du skapar i Power & Shell visas inte i Säkerhets- och efterlevnadscenter förrän du tilldelar principen till en regel för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-249">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="fd3e0-250">Steg 1: Använda PowerShell för att skapa en princip för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="fd3e0-250">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="fd3e0-251">Använd följande syntax för att skapa en princip för säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-251">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - <span data-ttu-id="fd3e0-252">Mer information om postsyntaxen för parametern _DoNotRewriteUrls_ finns i Postsyntaxen för [listan "Ange](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)inte följande URL:er".</span><span class="sxs-lookup"><span data-stu-id="fd3e0-252">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
> 
> - <span data-ttu-id="fd3e0-253">Mer information om ytterligare syntax som du kan använda för parametern _DoNotRewriteUrls_ när du ändrar befintliga principer för säkra länkar med hjälp av cmdleten **Set-SafeLinksPolicy** finns i avsnittet Använda [PowerShell](#use-powershell-to-modify-safe-links-policies) för att ändra principer för säkra länkar senare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-253">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="fd3e0-254">I det här exemplet skapas en princip för säkra länkar med namnet Contoso All med följande värden:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-254">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="fd3e0-255">Aktivera URL-genomsökning och omskrivning i e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-255">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="fd3e0-256">Aktivera URL-genomsökning i Teams (endast TAP Preview).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-256">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="fd3e0-257">Aktivera genomsökning i realtid av klickade URL:er, inklusive klickade länkar som pekar på filer.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-257">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="fd3e0-258">Vänta tills URL-skanningen är klar innan du levererar meddelandet.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-258">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="fd3e0-259">Aktivera URL-genomsökning och omskrivning av interna meddelanden.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-259">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="fd3e0-260">Spåra användarklick relaterade till skydd mot säkra länkar (vi använder inte parametern _DoNotTrackUserClicks_ och standardvärdet är $false, vilket innebär att användarklick spåras).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-260">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="fd3e0-261">Tillåt inte att användare klickar sig fram till den ursprungliga URL:en.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-261">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="fd3e0-262">Detaljerad information om syntax och parametrar finns i [New-SafeLinksPolicy.](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="fd3e0-262">For detailed syntax and parameter information, see [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="fd3e0-263">Steg 2: Använda PowerShell för att skapa en regel för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="fd3e0-263">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="fd3e0-264">Använd följande syntax för att skapa en regel för säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-264">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="fd3e0-265">I det här exemplet skapas en regel för säkra länkar med namnet Contoso Alla med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-265">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="fd3e0-266">Regeln är kopplad till principen för säkra länkar med namnet Contoso All.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-266">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="fd3e0-267">Regeln gäller för alla mottagare i contoso.com domän.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-267">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="fd3e0-268">Eftersom vi inte använder _parametern Priority_ används standardprioritet.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-268">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="fd3e0-269">Regeln är aktiverad (vi använder inte parametern _Enabled_ och standardvärdet är `$true` ).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-269">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="fd3e0-270">Detaljerad information om syntax och parametrar finns i [New-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="fd3e0-270">For detailed syntax and parameter information, see [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="fd3e0-271">Använda PowerShell för att visa principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="fd3e0-271">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="fd3e0-272">Om du vill visa befintliga principer för säkra länkar använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-272">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="fd3e0-273">Det här exemplet returnerar en sammanfattning av alla principer för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-273">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="fd3e0-274">I det här exemplet returneras detaljerad information för principen för säkra länkar med namnet Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-274">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="fd3e0-275">Detaljerad information om syntax och parametrar finns i [Get-SafeLinksPolicy.](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="fd3e0-275">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="fd3e0-276">Använda PowerShell för att visa regler för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="fd3e0-276">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="fd3e0-277">Om du vill visa befintliga regler för säkra länkar använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-277">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="fd3e0-278">Det här exemplet returnerar en sammanfattning av alla regler för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-278">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="fd3e0-279">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-279">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="fd3e0-280">I det här exemplet returneras detaljerad information för regeln om säkra länkar som heter Contoso-chefer.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-280">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="fd3e0-281">Detaljerad information om syntax och parametrar finns [i Get-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="fd3e0-281">For detailed syntax and parameter information, see [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="fd3e0-282">Använda PowerShell för att ändra principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="fd3e0-282">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="fd3e0-283">Du kan inte byta namn på en princip för säkra länkar i PowerShell **(set-SafeLinksPolicy-cmdleten** har ingen _namnparameter)._</span><span class="sxs-lookup"><span data-stu-id="fd3e0-283">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="fd3e0-284">När du byter namn på en princip för säkra länkar & Säkerhets- och efterlevnadscenter byter du bara namn på regeln för säkra _länkar._</span><span class="sxs-lookup"><span data-stu-id="fd3e0-284">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="fd3e0-285">Den enda ytterligare överväganden för att ändra principer för säkra länkar i PowerShell är den tillgängliga syntaxen för parametern _DoNotRewriteUrls_ (listan ["Skriva](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)inte om följande URL:er"):</span><span class="sxs-lookup"><span data-stu-id="fd3e0-285">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="fd3e0-286">Använd följande syntax om du vill lägga till värden som ersätter befintliga `"Entry1","Entry2,..."EntryN"` poster:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-286">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="fd3e0-287">Om du vill lägga till eller ta bort värden utan att påverka andra befintliga poster använder du följande syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="fd3e0-287">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="fd3e0-288">Annars är samma inställningar tillgängliga när du skapar en princip för säkra länkar enligt beskrivningen i steg [1:](#step-1-use-powershell-to-create-a-safe-links-policy) Använda PowerShell för att skapa ett avsnitt för principen för säkra länkar tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-288">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="fd3e0-289">Använd följande syntax för att ändra en princip för säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-289">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="fd3e0-290">Detaljerad information om syntax och parametrar finns [i Set-SafeLinksPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="fd3e0-290">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="fd3e0-291">Använda PowerShell för att ändra regler för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="fd3e0-291">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="fd3e0-292">Den enda inställning som inte är tillgänglig när du ändrar en regel för säkra länkar i PowerShell är den aktiverade _parametern_ som gör att du kan skapa en inaktiverad regel.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-292">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="fd3e0-293">Nästa avsnitt innehåller information om hur du aktiverar eller inaktiverar befintliga regler för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-293">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="fd3e0-294">Annars är samma inställningar tillgängliga när du skapar en regel enligt beskrivningen i steg [2:](#step-2-use-powershell-to-create-a-safe-links-rule) Använd PowerShell för att skapa ett avsnitt med en regel för säkra länkar tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-294">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="fd3e0-295">Använd följande syntax för att ändra en regel för säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-295">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="fd3e0-296">Detaljerad information om syntax och parametrar finns [i Set-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="fd3e0-296">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="fd3e0-297">Använda PowerShell för att aktivera eller inaktivera regler för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="fd3e0-297">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="fd3e0-298">Aktivering eller inaktivering av en regel för säkra länkar i PowerShell aktiverar eller inaktiverar hela principen för säkra länkar (regeln om säkra länkar och den tilldelade principen för säkra länkar).</span><span class="sxs-lookup"><span data-stu-id="fd3e0-298">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="fd3e0-299">Använd följande syntax för att aktivera eller inaktivera en regel för säkra länkar i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-299">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="fd3e0-300">I det här exemplet inaktiveras regeln om säkra länkar med namnet Marknadsföringsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-300">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="fd3e0-301">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-301">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="fd3e0-302">Detaljerad information om syntax och parametrar finns i [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) och [Disable-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="fd3e0-302">For detailed syntax and parameter information, see [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="fd3e0-303">Använda PowerShell för att ange prioritet för regler för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="fd3e0-303">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="fd3e0-304">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-304">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="fd3e0-305">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-305">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="fd3e0-306">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-306">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="fd3e0-307">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-307">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="fd3e0-308">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-308">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="fd3e0-309">Använd följande syntax för att ange prioritet för en regel för säkra länkar i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-309">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="fd3e0-310">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-310">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="fd3e0-311">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="fd3e0-311">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="fd3e0-312">Om du vill ange prioriteten för en  ny regel när du skapar den använder du prioritetsparametern i cmdleten **New-SafeLinksRule** i stället.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-312">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="fd3e0-313">Detaljerad information om syntax och parametrar finns [i Set-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="fd3e0-313">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="fd3e0-314">Använda PowerShell för att ta bort principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="fd3e0-314">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="fd3e0-315">När du använder PowerShell för att ta bort en princip för säkra länkar tas motsvarande regel för säkra länkar inte bort.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-315">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="fd3e0-316">Använd följande syntax om du vill ta bort en princip för säkra länkar i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-316">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="fd3e0-317">Det här exemplet tar bort principen för säkra länkar med namnet Marknadsföringsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-317">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="fd3e0-318">Detaljerad information om syntax och parametrar finns i [Remove-SafeLinksPolicy.](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="fd3e0-318">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="fd3e0-319">Använda PowerShell för att ta bort regler för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="fd3e0-319">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="fd3e0-320">När du använder PowerShell för att ta bort en regel för säkra länkar tas motsvarande princip för säkra länkar inte bort.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-320">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="fd3e0-321">Om du vill ta bort en regel för säkra länkar i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-321">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="fd3e0-322">I det här exemplet tas regeln om säkra länkar bort med namnet Marknadsföringsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-322">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="fd3e0-323">Detaljerad information om syntax och parametrar finns i [Remove-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="fd3e0-323">For detailed syntax and parameter information, see [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="fd3e0-324">Kontrollera vilka Microsoft Defender-rapporter som är tillgängliga för Office 365-rapporter om du vill kontrollera att Säkra länkar söker igenom meddelanden.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-324">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="fd3e0-325">Mer information finns i [Visa rapporter för Defender för Office 365](view-reports-for-atp.md) och Använda Utforskaren i [Säkerhets- & Efterlevnadscenter.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="fd3e0-325">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="fd3e0-326">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="fd3e0-326">How do you know these procedures worked?</span></span>

<span data-ttu-id="fd3e0-327">Kontrollera att du har skapat, ändrat eller tagit bort principer för säkra länkar genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-327">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="fd3e0-328">I Säkerhets- & Efterlevnadscenter går du till ATP **–** säkra \> **länkar för** \> **hothanteringspolicy.**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-328">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="fd3e0-329">Kontrollera listan över principer, deras **statusvärden** och deras **prioritetsvärden.**</span><span class="sxs-lookup"><span data-stu-id="fd3e0-329">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="fd3e0-330">Om du vill visa mer information väljer du principen i listan och visar informationen i flyg ut.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-330">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="fd3e0-331">I Exchange Online PowerShell eller Exchange Online Protection PowerShell ersätter du med namnet på principen eller regeln, kör följande kommando \<Name\> och kontrollerar inställningarna:</span><span class="sxs-lookup"><span data-stu-id="fd3e0-331">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
