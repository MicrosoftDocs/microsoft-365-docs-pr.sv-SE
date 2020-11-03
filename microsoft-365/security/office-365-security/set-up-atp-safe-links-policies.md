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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa mer om hur du visar, skapar, ändrar och tar bort principer för säkra länkar och globala inställningar för säkra länkar i Microsoft Defender för Office 365.
ms.openlocfilehash: ed95c72c98e0c9d59b9860e89843c5f9b4970c8e
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846442"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b665e-103">Konfigurera principer för säkra länkar i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="b665e-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="b665e-104">Den här artikeln är avsedd för företags kunder som har [Microsoft Defender för Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="b665e-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="b665e-105">Om du är hem användare letar efter information om Safelinks i Outlook kan du läsa mer i [avancerad Outlook.com-säkerhet](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="b665e-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="b665e-106">Säkra länkar är en funktion i [Microsoft Defender för Office 365](office-365-atp.md) som tillhandahåller URL-genomsökning av inkommande e-postmeddelanden i e-postflöde och när du klickar på verifiering av URL-adresser och länkar i e-postmeddelanden och på andra platser.</span><span class="sxs-lookup"><span data-stu-id="b665e-106">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="b665e-107">Mer information finns i [säkra länkar i Microsoft Defender för Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="b665e-107">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="b665e-108">Det finns inga inbyggda eller standard principer för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="b665e-108">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="b665e-109">För att få säker sökning efter URL-adresser måste du skapa en eller flera principer för säkra länkar enligt beskrivningen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="b665e-109">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

<span data-ttu-id="b665e-110">Du kan konfigurera principer för säkra länkar i säkerhets &s kontroll Center eller i PowerShell (Exchange Online PowerShell för kvalificerade Microsoft 365-organisationer med post lådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor, men med prenumerationer för tilläggsprogram för Microsoft Defender för Office 365).</span><span class="sxs-lookup"><span data-stu-id="b665e-110">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="b665e-111">De grundläggande delarna i en policy för säkra länkar är:</span><span class="sxs-lookup"><span data-stu-id="b665e-111">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="b665e-112">**Principen för säkra länkar** : Aktivera skyddad länk skydd, aktivera URL-genomsökning i real tid, ange om du vill vänta på att genomsökning i real tid ska slutföras innan du levererar meddelandet, aktiverar skanning för interna meddelanden, anger om du vill spåra användare klickar på URL-adresser och ange om du vill tillåta användare att klicka på återträff till den ursprungliga URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="b665e-112">**The safe links policy** : Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="b665e-113">**Regeln för säkra länkar** : anger de prioritets-och mottagar filter (som principen gäller för).</span><span class="sxs-lookup"><span data-stu-id="b665e-113">**The safe links rule** : Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="b665e-114">Skillnaden mellan dessa två element är inte uppenbar när du hanterar Safe Links-principer i säkerhets & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="b665e-114">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="b665e-115">När du skapar en policy för säkra länkar skapar du verkligen en regel för ett säkert länkar och den associerade principen för säkra länkar samtidigt med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="b665e-115">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="b665e-116">När du ändrar en princip för ett säkert länkar kan inställningar som är relaterade till namn, prioritet, aktiverade eller inaktiverade och mottagar filter ändra regeln för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="b665e-116">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="b665e-117">Alla andra inställningar ändrar policyn för associerade säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="b665e-117">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="b665e-118">När du tar bort en princip för ett säkert länkar tas reglerna för säkra länkar och den associerade principen för säkra länkar bort.</span><span class="sxs-lookup"><span data-stu-id="b665e-118">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="b665e-119">I Exchange Online PowerShell eller fristående EOP PowerShell hanterar du policyn och regeln separat.</span><span class="sxs-lookup"><span data-stu-id="b665e-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="b665e-120">Mer information finns i [använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för Safe Links](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="b665e-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="b665e-121">Du konfigurerar globala inställningar för skydd mot säkra länkar **utanför** principer för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="b665e-121">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="b665e-122">Anvisningar finns i [Konfigurera globala inställningar för säkra länkar i Microsoft Defender för Office 365](configure-global-settings-for-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="b665e-122">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b665e-123">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="b665e-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b665e-124">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b665e-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b665e-125">Om du vill gå direkt till sidan **Safe Links** använder du <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="b665e-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="b665e-126">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b665e-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="b665e-127">Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="b665e-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b665e-128">För att visa, skapa, ändra och ta bort principer för säkra länkar måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="b665e-128">To view, create, modify, and delete Safe Links policies, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="b665e-129">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b665e-129">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="b665e-130">**Organisations hantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="b665e-130">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="b665e-131">För de rekommenderade inställningarna för principer för säkra länkar, se [princip inställningar för säkra länkar](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="b665e-131">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="b665e-132">Tillåt upp till 30 minuter för att en ny eller uppdaterad princip ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="b665e-132">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="b665e-133">[Nya funktioner läggs hela tiden till i Microsoft Defender för Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="b665e-133">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="b665e-134">När nya funktioner läggs till kan du behöva justera dina befintliga principer för säker länkar.</span><span class="sxs-lookup"><span data-stu-id="b665e-134">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="b665e-135">Skapa principer för säkra länkar med hjälp av säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="b665e-135">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="b665e-136">Om du skapar en anpassad princip för säkra länkar i säkerhets & Compliance Center skapas regeln för säkra länkar och den associerade principen för Safe Links samtidigt med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="b665e-136">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="b665e-137">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** - \> **säkra länkar**.</span><span class="sxs-lookup"><span data-stu-id="b665e-137">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="b665e-138">Klicka på **skapa** på sidan **Safe Links** .</span><span class="sxs-lookup"><span data-stu-id="b665e-138">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="b665e-139">Guiden **ny princip för säkra länkar** öppnas.</span><span class="sxs-lookup"><span data-stu-id="b665e-139">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="b665e-140">På sidan **namnge din policy** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="b665e-140">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="b665e-141">**Namn** : Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="b665e-141">**Name** : Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="b665e-142">**Beskrivning** : Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="b665e-142">**Description** : Enter an optional description for the policy.</span></span>

   <span data-ttu-id="b665e-143">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="b665e-143">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="b665e-144">På sidan **Inställningar** som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="b665e-144">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="b665e-145">**Välj åtgärd för okända URL-adresser i meddelanden** : Välj **på** för att aktivera skydda Länkar för länkar i e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="b665e-145">**Select the action for unknown potentially malicious URLs in messages** : Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="b665e-146">**Välj åtgärd för okända eller potentiellt skadliga URL-adresser i Microsoft Teams** : Välj **på** för att aktivera skydd mot säkra Länkar för länkar i team.</span><span class="sxs-lookup"><span data-stu-id="b665e-146">**Select the action for unknown or potentially malicious URLs within Microsoft Teams** : Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="b665e-147">**Använda URL-genomsökning i real tid för misstänkta länkar och länkar som pekar på filer** : Välj den här inställningen för att aktivera genomsökning i real tid med länkar i e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="b665e-147">**Apply real-time URL scanning for suspicious links and links that point to files** : Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="b665e-148">**Vänta på att URL-genomsökningen ska slutföras innan du levererar meddelandet** : Välj den här inställningen för att vänta på att URL-genomsökning i real tid ska slutföras innan meddelandet levereras.</span><span class="sxs-lookup"><span data-stu-id="b665e-148">**Wait for URL scanning to complete before delivering the message** : Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="b665e-149">**Använd Safe Links för e-postmeddelanden som skickas inom organisationen** : Välj den här inställningen om du vill tillämpa principen för säkra länkar i meddelanden mellan interna avsändare och interna mottagare.</span><span class="sxs-lookup"><span data-stu-id="b665e-149">**Apply Safe Links to email messages sent within the organization** : Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="b665e-150">**Spåra inte användare** Klicka på: låt den här inställningen vara avmarkerad för att aktivera spårnings användaren på URL: er i e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="b665e-150">**Do not track user clicks** : Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="b665e-151">**Tillåt inte att användare klickar genom till ursprunglig URL** : Välj den här inställningen för att hindra användare från att klicka dig fram till den ursprungliga URL-adressen i [varnings sidor](atp-safe-links.md#warning-pages-from-safe-links).</span><span class="sxs-lookup"><span data-stu-id="b665e-151">**Do not allow users to click through to original URL** : Select this setting to block users from clicking through to the original URL in [warning pages](atp-safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="b665e-152">**Skriv inte om följande webb adresser** : tillåter åtkomst till angivna URL-adresser som annars skulle blockeras av säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="b665e-152">**Do not rewrite the following URLs** : Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="b665e-153">Skriv URL: en eller det värde du vill använda i rutan och klicka sedan på</span><span class="sxs-lookup"><span data-stu-id="b665e-153">In the box, type the URL or value that you want, and then click</span></span> ![Ikonen Lägg till knapp](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="b665e-155">.</span><span class="sxs-lookup"><span data-stu-id="b665e-155">.</span></span>

     <span data-ttu-id="b665e-156">Om du vill ta bort en befintlig post markerar du den och klickar sedan på</span><span class="sxs-lookup"><span data-stu-id="b665e-156">To remove an existing entry, select it and then click</span></span> ![Ikonen Ta bort](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="b665e-158">.</span><span class="sxs-lookup"><span data-stu-id="b665e-158">.</span></span>

     <span data-ttu-id="b665e-159">Syntaxen för inmatning finns i [syntaxen för listan "Skriv inte om följande URL: er"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="b665e-159">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="b665e-160">Detaljerad information om dessa inställningar finns i [Inställningar för säkra Länkar för e-postmeddelanden](atp-safe-links.md#safe-links-settings-for-email-messages) och [Inställningar för säkra Länkar för Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="b665e-160">For detailed information about these settings, see [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="b665e-161">Fler rekommenderade värden för standard-och strikta princip inställningar finns i [princip inställningar för säkra länkar](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="b665e-161">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="b665e-162">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="b665e-162">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b665e-163">**På sidan som** visas anger du vilka interna mottagare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="b665e-163">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="b665e-164">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="b665e-164">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="b665e-165">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_ ).</span><span class="sxs-lookup"><span data-stu-id="b665e-165">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_ ).</span></span> <span data-ttu-id="b665e-166">Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_ ).</span><span class="sxs-lookup"><span data-stu-id="b665e-166">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_ ).</span></span>

   <span data-ttu-id="b665e-167">Klicka på **Lägg till ett villkor**.</span><span class="sxs-lookup"><span data-stu-id="b665e-167">Click **Add a condition**.</span></span> <span data-ttu-id="b665e-168">I den nedrullningsbara List rutan som visas väljer du ett villkor under **används om** :</span><span class="sxs-lookup"><span data-stu-id="b665e-168">In the dropdown that appears, select a condition under **Applied if** :</span></span>

   - <span data-ttu-id="b665e-169">**Mottagaren är** : anger en eller flera post lådor, e-postkonton eller e-postkontakter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="b665e-169">**The recipient is** : Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="b665e-170">**Mottagaren är medlem i** : anger en eller flera grupper i din organisation.</span><span class="sxs-lookup"><span data-stu-id="b665e-170">**The recipient is a member of** : Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="b665e-171">**Mottagande domän är** : Anger mottagare i en eller flera av de godkända domänerna som har konfigurerats i din organisation.</span><span class="sxs-lookup"><span data-stu-id="b665e-171">**The recipient domain is** : Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="b665e-172">När du har valt villkoret visas en motsvarande listruta med en **av dessa** rutor.</span><span class="sxs-lookup"><span data-stu-id="b665e-172">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="b665e-173">Klicka i rutan och bläddra igenom listan med värden att välja.</span><span class="sxs-lookup"><span data-stu-id="b665e-173">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="b665e-174">Klicka i rutan och börja skriva för att filtrera listan och välja ett värde.</span><span class="sxs-lookup"><span data-stu-id="b665e-174">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="b665e-175">Om du vill lägga till fler värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="b665e-175">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="b665e-176">Om du vill ta bort enskilda poster klickar du på **ta bort** - ![ ikonen ](../../media/scc-remove-icon.png) för värdet.</span><span class="sxs-lookup"><span data-stu-id="b665e-176">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="b665e-177">Om du vill ta bort hela villkoret klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="b665e-177">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="b665e-178">Om du vill lägga till ytterligare villkor klickar du på **Lägg till ett villkor** och väljer ett återstående värde under **används om**.</span><span class="sxs-lookup"><span data-stu-id="b665e-178">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="b665e-179">Om du vill lägga till undantag klickar du på **Lägg till ett villkor** och väljer ett undantag under **utom om**.</span><span class="sxs-lookup"><span data-stu-id="b665e-179">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="b665e-180">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="b665e-180">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="b665e-181">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="b665e-181">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="b665e-182">Granska inställningarna på sidan **Granska inställningar** som visas.</span><span class="sxs-lookup"><span data-stu-id="b665e-182">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="b665e-183">Du kan klicka på **Redigera** på varje inställning för att ändra den.</span><span class="sxs-lookup"><span data-stu-id="b665e-183">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="b665e-184">När du är klar klickar du på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="b665e-184">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="b665e-185">Använda tjänsten säkerhets & efterlevnad för att visa principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="b665e-185">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="b665e-186">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** - \> **säkra länkar**.</span><span class="sxs-lookup"><span data-stu-id="b665e-186">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="b665e-187">På sidan **Safe Links** väljer du en princip i listan och klickar på den (markerar inte kryss rutan).</span><span class="sxs-lookup"><span data-stu-id="b665e-187">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="b665e-188">Princip detaljerna visas i ett flyg utåt</span><span class="sxs-lookup"><span data-stu-id="b665e-188">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="b665e-189">Använda inställningarna för säkerhets & efterlevnad för att ändra principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="b665e-189">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="b665e-190">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** - \> **säkra länkar**.</span><span class="sxs-lookup"><span data-stu-id="b665e-190">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="b665e-191">På sidan **Safe Links** väljer du en princip i listan och klickar på den (markerar inte kryss rutan).</span><span class="sxs-lookup"><span data-stu-id="b665e-191">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="b665e-192">I princip informationen som visas klickar du på **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="b665e-192">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="b665e-193">Tillgängliga inställningar i rutan Lägg på och som visas är identiska med de som beskrivs i avsnittet [använda säkerhets & efterlevnad för att skapa principer för säkra länkar](#use-the-security--compliance-center-to-create-safe-links-policies) .</span><span class="sxs-lookup"><span data-stu-id="b665e-193">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="b665e-194">Om du vill aktivera eller inaktivera en princip eller ange prioritetsordning för principer kan du läsa följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="b665e-194">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="b665e-195">Principer för att aktivera och inaktivera säkra länkar</span><span class="sxs-lookup"><span data-stu-id="b665e-195">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="b665e-196">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** - \> **säkra länkar**.</span><span class="sxs-lookup"><span data-stu-id="b665e-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="b665e-197">Observera värdet i kolumnen **status** :</span><span class="sxs-lookup"><span data-stu-id="b665e-197">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="b665e-198">Flytta växlingsknappen åt vänster om du vill inaktivera principen:</span><span class="sxs-lookup"><span data-stu-id="b665e-198">Move the toggle to the left to disable the policy:</span></span> ![Inaktivera princip](../../media/scc-toggle-off.png)<span data-ttu-id="b665e-200">.</span><span class="sxs-lookup"><span data-stu-id="b665e-200">.</span></span>

   - <span data-ttu-id="b665e-201">Flytta växlingsknappen åt höger om du vill aktivera principen:</span><span class="sxs-lookup"><span data-stu-id="b665e-201">Move the toggle to the right to enable the policy:</span></span> ![Aktivera princip](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="b665e-203">.</span><span class="sxs-lookup"><span data-stu-id="b665e-203">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="b665e-204">Ange prioritet för principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="b665e-204">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="b665e-205">Som standard ges principer för säkra länkar en prioritet som baseras på den ordning de skapades i (nyare policys är lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="b665e-205">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="b665e-206">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="b665e-206">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="b665e-207">Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="b665e-207">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="b665e-208">För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="b665e-208">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="b665e-209">Principer för säkra länkar visas i den ordning de behandlas (den första principen har **prioritet** svärdet 0).</span><span class="sxs-lookup"><span data-stu-id="b665e-209">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="b665e-210">**Obs!** i säkerhets & Compliance Center kan du bara ändra prioriteten för principen för säkra länkar när du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="b665e-210">**Note** : In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="b665e-211">I PowerShell kan du åsidosätta standard prioriteten när du skapar regeln för säkra länkar (som kan påverka prioriteringen för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="b665e-211">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="b665e-212">Du ändrar prioriteten för en princip genom att flytta principen uppåt eller nedåt i listan (du kan inte ändra **prioritetsnumret** direkt i Säkerhets- och efterlevnadscenter).</span><span class="sxs-lookup"><span data-stu-id="b665e-212">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="b665e-213">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** - \> **säkra länkar**.</span><span class="sxs-lookup"><span data-stu-id="b665e-213">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="b665e-214">På sidan **Safe Links** väljer du en princip i listan och klickar på den (markerar inte kryss rutan).</span><span class="sxs-lookup"><span data-stu-id="b665e-214">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="b665e-215">I princip detaljerna som visas klickar du på knappen tillgänglig prioritet:</span><span class="sxs-lookup"><span data-stu-id="b665e-215">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="b665e-216">Principen för säkra länkar med **prioritet** svärdet **0** har bara knappen **minska prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="b665e-216">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="b665e-217">Principen för säkra länkar med det lägsta **prioritet** svärdet (till exempel **3** ) har bara knappen **öka prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="b665e-217">The Safe Links policy with the lowest **Priority** value (for example, **3** ) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="b665e-218">Om du har tre eller fler Safe Link-principer har de principer som gäller för de högsta och lägsta värdena både knappen **öka prioritet** och knappen för att **minska prioriteten** tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="b665e-218">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="b665e-219">Klicka på **öka prioritet** eller **minska prioritet** för att ändra **prioritet** svärdet.</span><span class="sxs-lookup"><span data-stu-id="b665e-219">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="b665e-220">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="b665e-220">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="b665e-221">Använda inställningarna för säkerhets & efterlevnad för att ta bort principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="b665e-221">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="b665e-222">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** - \> **säkra länkar**.</span><span class="sxs-lookup"><span data-stu-id="b665e-222">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="b665e-223">På sidan **Safe Links** väljer du en princip i listan och klickar på den (markerar inte kryss rutan).</span><span class="sxs-lookup"><span data-stu-id="b665e-223">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="b665e-224">I princip detaljerna som visas klickar du på **ta bort princip** och sedan på **Ja** i varnings dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="b665e-224">In the policy details fly out that appears, click **Delete policy** , and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="b665e-225">Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="b665e-225">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="b665e-226">Som du redan har beskrivit innehåller en policy för Safe Links en princip för säkra länkar och en regel för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="b665e-226">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="b665e-227">I PowerShell är skillnaden mellan principer för säkra länkar och regler för säkra länkar uppenbar.</span><span class="sxs-lookup"><span data-stu-id="b665e-227">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="b665e-228">Du hanterar principer för säkra länkar genom att använda cmdletarna **\* -SafeLinksPolicy** och du hanterar reglerna för säkra länkar genom att använda cmdlet **\* -SafeLinksRule** .</span><span class="sxs-lookup"><span data-stu-id="b665e-228">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="b665e-229">I PowerShell skapar du principen för säkra länkar först och skapar sedan regeln för säkra länkar som identifierar den princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="b665e-229">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="b665e-230">I PowerShell ändrar du inställningarna för principen för säkra länkar och regeln för säkra länkar var för sig.</span><span class="sxs-lookup"><span data-stu-id="b665e-230">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="b665e-231">När du tar bort en princip för säkra länkar från PowerShell tas inte den motsvarande regeln för Safe-länkar bort automatiskt och vice versa.</span><span class="sxs-lookup"><span data-stu-id="b665e-231">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="b665e-232">Använda PowerShell för att skapa principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="b665e-232">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="b665e-233">Att skapa en princip för säkra länkar i PowerShell är en process i två steg:</span><span class="sxs-lookup"><span data-stu-id="b665e-233">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="b665e-234">Skapa principen för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="b665e-234">Create the safe links policy.</span></span>
2. <span data-ttu-id="b665e-235">Skapa regeln för säkra länkar som anger principen för säkra länkar som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="b665e-235">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

 <span data-ttu-id="b665e-236">**Anmärkningar** :</span><span class="sxs-lookup"><span data-stu-id="b665e-236">**Notes** :</span></span>

- <span data-ttu-id="b665e-237">Du kan skapa en ny regel för ett säkert länkar och koppla en befintlig princip för osäkra länkar till den.</span><span class="sxs-lookup"><span data-stu-id="b665e-237">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="b665e-238">En regel för säkert länkar kan inte kopplas till fler än en princip för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="b665e-238">A safe links rule can't be associated with more than one safe links policy.</span></span>

- <span data-ttu-id="b665e-239">Du kan konfigurera följande inställningar på nya principer för säkra länkar i PowerShell som inte är tillgängliga i säkerhets & Compliance Center förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="b665e-239">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="b665e-240">Skapa den nya principen som inaktive rad ( _aktive rad_ `$false` på **New-SafeLinksRule-** cmdleten).</span><span class="sxs-lookup"><span data-stu-id="b665e-240">Create the new policy as disabled ( _Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
  - <span data-ttu-id="b665e-241">Ange prioriteten för principen när den skapas ( _prioritet_ _\<Number\>_ ) på den **nya SafeLinksRule-** cmdleten.</span><span class="sxs-lookup"><span data-stu-id="b665e-241">Set the priority of the policy during creation ( _Priority_ _\<Number\>_ ) on the **New-SafeLinksRule** cmdlet).</span></span>

- <span data-ttu-id="b665e-242">En ny princip för säkra länkar som du skapar i PowerShell visas inte i fönstret säkerhets & efterlevnad förrän du tilldelar principen en regel för ett säkert länkar.</span><span class="sxs-lookup"><span data-stu-id="b665e-242">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="b665e-243">Steg 1: använda PowerShell för att skapa en policy för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="b665e-243">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="b665e-244">Använd den här syntaxen om du vill skapa en princip för säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="b665e-244">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

<span data-ttu-id="b665e-245">**Anmärkningar** :</span><span class="sxs-lookup"><span data-stu-id="b665e-245">**Notes** :</span></span>

- <span data-ttu-id="b665e-246">Mer information om syntaxen för _DoNotRewriteUrls_ finns i [syntaxen för listan "Skriv inte om följande URL-adresser"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="b665e-246">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

- <span data-ttu-id="b665e-247">Ytterligare syntax som du kan använda för _DoNotRewriteUrls_ -parametern när du ändrar befintliga principer för säkra länkar med hjälp av cmdleten **set-SafeLinksPolicy** finns i avsnittet [använda PowerShell för att ändra principer för Safe Links](#use-powershell-to-modify-safe-links-policies) senare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="b665e-247">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="b665e-248">I det här exemplet skapas en princip för säkra länkar med namnet contoso alla med följande värden:</span><span class="sxs-lookup"><span data-stu-id="b665e-248">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="b665e-249">Aktivera URL-genomsökning och omskrivning i e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="b665e-249">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="b665e-250">Aktivera URL-genomsökning i Teams (tryck bara på för hands version).</span><span class="sxs-lookup"><span data-stu-id="b665e-250">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="b665e-251">Aktivera genomsökning i real tid med URL-adresser, inklusive klickade på länkar som pekar på filer.</span><span class="sxs-lookup"><span data-stu-id="b665e-251">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="b665e-252">Vänta på att URL-genomsökningen ska slutföras innan du levererar meddelandet.</span><span class="sxs-lookup"><span data-stu-id="b665e-252">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="b665e-253">Aktivera URL-genomsökning och omskrivning för interna meddelanden.</span><span class="sxs-lookup"><span data-stu-id="b665e-253">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="b665e-254">Spåra användar klickningar relaterade till skydd mot säkra länkar (vi använder inte parametern _DoNotTrackUserClicks_ och standardvärdet är $false, vilket innebär att användare klickar på spåras).</span><span class="sxs-lookup"><span data-stu-id="b665e-254">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="b665e-255">Tillåt inte användare att klicka dig fram till original-URL: en.</span><span class="sxs-lookup"><span data-stu-id="b665e-255">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="b665e-256">Detaljerad information om syntax och parametrar finns i [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="b665e-256">For detailed syntax and parameter information, see [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="b665e-257">Steg 2: använda PowerShell för att skapa en regel för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="b665e-257">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="b665e-258">Använd den här syntaxen om du vill skapa en regel för säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="b665e-258">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="b665e-259">I det här exemplet skapas en regel för säkra länkar som heter Contoso alla med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="b665e-259">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="b665e-260">Regeln kopplas till principen för säkra länkar med namnet contoso all.</span><span class="sxs-lookup"><span data-stu-id="b665e-260">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="b665e-261">Regeln gäller för alla mottagare i contoso.com-domänen.</span><span class="sxs-lookup"><span data-stu-id="b665e-261">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="b665e-262">Eftersom vi inte använder _prioritets_ parametern används standard prioriteten.</span><span class="sxs-lookup"><span data-stu-id="b665e-262">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="b665e-263">Regeln är aktive rad (vi använder inte den _aktiverade_ parametern och standardvärdet är `$true` ).</span><span class="sxs-lookup"><span data-stu-id="b665e-263">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="b665e-264">Detaljerad information om syntax och parametrar finns i [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="b665e-264">For detailed syntax and parameter information, see [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="b665e-265">Använda PowerShell för att visa principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="b665e-265">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="b665e-266">Använd följande syntax för att visa befintliga principer för säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="b665e-266">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="b665e-267">I det här exemplet returneras en sammanfattande lista över alla principer för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="b665e-267">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="b665e-268">I det här exemplet returneras detaljerad information för principen för säkra länkar som heter Contoso-chefer.</span><span class="sxs-lookup"><span data-stu-id="b665e-268">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="b665e-269">Detaljerad information om syntax och parametrar finns i [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="b665e-269">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="b665e-270">Använda PowerShell för att visa regler för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="b665e-270">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="b665e-271">Använd följande syntax för att visa befintliga regler för säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="b665e-271">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="b665e-272">I det här exemplet returneras en sammanfattande lista över alla regler för säker länk.</span><span class="sxs-lookup"><span data-stu-id="b665e-272">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="b665e-273">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="b665e-273">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="b665e-274">I det här exemplet returneras detaljerad information för regeln för säkra länkar som heter Contoso-chefer.</span><span class="sxs-lookup"><span data-stu-id="b665e-274">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="b665e-275">Detaljerad information om syntax och parametrar finns i [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="b665e-275">For detailed syntax and parameter information, see [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="b665e-276">Använda PowerShell för att ändra principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="b665e-276">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="b665e-277">Det går inte att byta namn på en policy för säkra länkar i PowerShell (cmdleten **set-SafeLinksPolicy** , saknar _namn_ parameter).</span><span class="sxs-lookup"><span data-stu-id="b665e-277">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="b665e-278">När du byter namn på en policy för säkra länkar i säkerhets &s kontroll namn ändras inte _regeln_ för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="b665e-278">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="b665e-279">Det enda alternativet för att ändra principer för säkra länkar i PowerShell är den tillgängliga syntaxen för parametern _DoNotRewriteUrls_ (alternativet ["Skriv inte om följande URL-adresser"](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span><span class="sxs-lookup"><span data-stu-id="b665e-279">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="b665e-280">Om du vill lägga till värden som ersätter befintliga poster kan du använda följande syntax: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="b665e-280">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="b665e-281">Använd följande syntax för att lägga till eller ta bort värden utan att påverka andra befintliga poster: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="b665e-281">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="b665e-282">I annat fall är samma inställningar tillgängliga när du skapar en princip för säkra länkar enligt beskrivningen i [steg 1: använda PowerShell för att skapa en princip för säkra länkar](#step-1-use-powershell-to-create-a-safe-links-policy) i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="b665e-282">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="b665e-283">Använd den här syntaxen om du vill ändra en princip för ett säkert länkar:</span><span class="sxs-lookup"><span data-stu-id="b665e-283">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="b665e-284">Detaljerad information om syntax och parametrar finns i [set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="b665e-284">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="b665e-285">Använda PowerShell för att ändra regler för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="b665e-285">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="b665e-286">Den enda inställning som inte är tillgänglig när du ändrar en regel för ett säkert länkar i PowerShell är den _aktiverade_ parametern som gör att du kan skapa en regel för inaktivitet.</span><span class="sxs-lookup"><span data-stu-id="b665e-286">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="b665e-287">Information om hur du aktiverar eller inaktiverar befintliga Safe Links-regler finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="b665e-287">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="b665e-288">I annat fall är samma inställningar tillgängliga när du skapar en regel enligt beskrivningen i [steg 2: använda PowerShell för att skapa en regel för ett säkert länkar](#step-2-use-powershell-to-create-a-safe-links-rule) i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="b665e-288">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="b665e-289">Om du vill ändra en regel för ett säkert länkar använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="b665e-289">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="b665e-290">Detaljerad information om syntax och parametrar finns i [set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="b665e-290">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="b665e-291">Använda PowerShell för att aktivera eller inaktivera regler för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="b665e-291">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="b665e-292">När du aktiverar eller inaktiverar en regel för ett säkert länkar i PowerShell aktive ras eller inaktive ras hela principen för säkra länkar (reglerna för säkra länkar och tilldelnings principen för tilldelade säkra länkar).</span><span class="sxs-lookup"><span data-stu-id="b665e-292">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="b665e-293">Använd den här syntaxen om du vill aktivera eller inaktivera en regel för ett säkert länkar i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b665e-293">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="b665e-294">Det här exemplet inaktiverar regeln för säkra länkar som heter marknadsförings avdelningen.</span><span class="sxs-lookup"><span data-stu-id="b665e-294">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="b665e-295">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="b665e-295">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="b665e-296">Detaljerad information om syntax och parametrar finns i [Aktivera-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) och [disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="b665e-296">For detailed syntax and parameter information, see [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="b665e-297">Använda PowerShell för att ange prioritet för regler för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="b665e-297">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="b665e-298">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="b665e-298">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="b665e-299">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="b665e-299">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="b665e-300">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="b665e-300">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="b665e-301">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="b665e-301">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="b665e-302">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="b665e-302">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="b665e-303">Använd följande syntax för att ange prioriteten för en regel för säkra länkar i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b665e-303">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="b665e-304">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="b665e-304">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="b665e-305">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="b665e-305">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="b665e-306">**Obs!** om du vill ange prioriteten för en ny regel när du skapar den kan du använda _prioritets_ parametern i **New-SafeLinksRule** cmdlet i stället.</span><span class="sxs-lookup"><span data-stu-id="b665e-306">**Note** : To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="b665e-307">Detaljerad information om syntax och parametrar finns i [set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="b665e-307">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="b665e-308">Använda PowerShell för att ta bort principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="b665e-308">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="b665e-309">När du använder PowerShell för att ta bort en princip för säkra länkar tas inte den motsvarande regeln för Safe Links bort.</span><span class="sxs-lookup"><span data-stu-id="b665e-309">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="b665e-310">Använd den här syntaxen om du vill ta bort en princip för säkra länkar i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b665e-310">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="b665e-311">Det här exemplet tar bort policyn för säkra länkar som heter marknadsförings avdelningen.</span><span class="sxs-lookup"><span data-stu-id="b665e-311">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="b665e-312">Detaljerad information om syntax och parametrar finns i [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="b665e-312">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="b665e-313">Använda PowerShell för att ta bort regler för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="b665e-313">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="b665e-314">När du använder PowerShell för att ta bort en regel för ett säkert länkar tas inte motsvarande principer för säkra länkar bort.</span><span class="sxs-lookup"><span data-stu-id="b665e-314">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="b665e-315">Använd den här syntaxen om du vill ta bort en regel för säkra länkar i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b665e-315">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="b665e-316">Det här exemplet tar bort regeln för säkra länkar som heter marknadsförings avdelningen.</span><span class="sxs-lookup"><span data-stu-id="b665e-316">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="b665e-317">Detaljerad information om syntax och parametrar finns i [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="b665e-317">For detailed syntax and parameter information, see [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="b665e-318">Om du vill kontrol lera att de säkra länkarna är att söka igenom meddelanden markerar du de tillgängliga Microsoft Defender för Office 365-rapporterna.</span><span class="sxs-lookup"><span data-stu-id="b665e-318">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="b665e-319">Mer information finns i [Visa rapporter för Defender för Office 365](view-reports-for-atp.md) och [använda utforskaren i säkerhets & Compliance Center](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="b665e-319">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="b665e-320">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="b665e-320">How do you know these procedures worked?</span></span>

<span data-ttu-id="b665e-321">Gör något av följande för att kontrol lera att du har skapat, ändrat eller tagit bort principer för säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="b665e-321">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="b665e-322">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** - \> **säkra länkar**.</span><span class="sxs-lookup"><span data-stu-id="b665e-322">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="b665e-323">Verifiera listan med principer, deras **status** värden och deras **prioriterade** värden.</span><span class="sxs-lookup"><span data-stu-id="b665e-323">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="b665e-324">Om du vill visa mer information väljer du den i listan och visar detaljerna i Lägg utåt.</span><span class="sxs-lookup"><span data-stu-id="b665e-324">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="b665e-325">I Exchange Online PowerShell eller Exchange Online Protection PowerShell ersätter du \<Name\> med namnet på principen eller regeln, kör följande kommando och kontrollerar inställningarna:</span><span class="sxs-lookup"><span data-stu-id="b665e-325">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
