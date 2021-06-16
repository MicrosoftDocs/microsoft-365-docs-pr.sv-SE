---
title: Konfigurera principer Valv Länkar i Microsoft Defender för Office 365
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
description: Administratörer kan läsa mer om hur de visar, skapar, ändrar och tar bort Valv-principer och globala Valv-länkar i Microsoft Defender för Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 40ae52cfce53c3fa14253a94e72f1a2bccda9a86
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929833"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="953fb-103">Konfigurera principer Valv Länkar i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="953fb-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="953fb-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="953fb-104">**Applies to**</span></span>
- [<span data-ttu-id="953fb-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="953fb-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="953fb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="953fb-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="953fb-107">Den här artikeln är avsedd för företagskunder som har [Microsoft Defender för Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="953fb-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="953fb-108">Om du är hemanvändare och vill ha information om säkra länkar i Outlook kan du läsa [Mer Outlook.com-säkerhet.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="953fb-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="953fb-109">Valv Länkar är en funktion i [Microsoft Defender](defender-for-office-365.md) för Office 365 som ger URL-skanning av inkommande e-postmeddelanden i e-postflödet och tidpunkten för klickverifiering av URL:er och länkar i e-postmeddelanden och på andra platser.</span><span class="sxs-lookup"><span data-stu-id="953fb-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="953fb-110">Mer information finns i artikeln [Valv i Microsoft Defender för Office 365](safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="953fb-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="953fb-111">Det finns ingen inbyggd eller standardprincip för Valv länkar.</span><span class="sxs-lookup"><span data-stu-id="953fb-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="953fb-112">Om du Valv länkar för genomsökning av URL:er måste du skapa en eller flera Valv länkar enligt beskrivningen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="953fb-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="953fb-113">Du konfigurerar de globala inställningarna Valv skydd **vid länkar utanför** Valv Principer för länkar.</span><span class="sxs-lookup"><span data-stu-id="953fb-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="953fb-114">Anvisningar finns i [Konfigurera globala inställningar för Valv i Microsoft Defender för Office 365.](configure-global-settings-for-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="953fb-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="953fb-115">Du kan konfigurera principer för Valv-länkar i Microsoft 365 Defender-portalen eller i PowerShell (Exchange Online PowerShell för kvalificerade Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor, men med Microsoft Defender för Office 365-tilläggsprenumerationer).</span><span class="sxs-lookup"><span data-stu-id="953fb-115">You can configure Safe Links policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="953fb-116">De grundläggande elementen i en Valv-länkprincip är:</span><span class="sxs-lookup"><span data-stu-id="953fb-116">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="953fb-117">Principen för säkra **länkar:** Aktivera skydd mot Valv-länkar, aktivera URL-genomsökning i realtid, ange om du vill vänta på att skanning i realtid ska slutföras innan meddelandet levereras, aktivera genomsökning av interna meddelanden, ange om användaren ska klicka på URL-adresser och ange om de vill tillåta att användare klickar på samma webbadress.</span><span class="sxs-lookup"><span data-stu-id="953fb-117">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="953fb-118">**Regeln säkra länkar:** Anger prioritet och mottagarfilter (vem principen gäller för).</span><span class="sxs-lookup"><span data-stu-id="953fb-118">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="953fb-119">Administratörer bör överväga olika konfigurationsinställningar för Säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="953fb-119">Admins should consider the different configuration settings for SafeLinks.</span></span> <span data-ttu-id="953fb-120">Ett av de tillgängliga alternativen är att inkludera användaridentifierande information i Säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="953fb-120">One of the available options is to include user identifiable information in SafeLinks.</span></span> <span data-ttu-id="953fb-121">Med den här funktionen kan *säkerhets ops-team* undersöka potentiella användarintrång, vidta korrigerande åtgärder och begränsa dyrbara överträdelser.</span><span class="sxs-lookup"><span data-stu-id="953fb-121">This feature enables *Security Ops teams* to investigate potential user compromise, take corrective action, and limit costly breaches.</span></span>

<span data-ttu-id="953fb-122">Skillnaden mellan dessa två element är inte uppenbara när du hanterar Valv Länkar i Microsoft 365 Defender-portalen:</span><span class="sxs-lookup"><span data-stu-id="953fb-122">The difference between these two elements isn't obvious when you manage Safe Links polices in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="953fb-123">När du skapar Valv princip för länkar skapar du egentligen en regel för säkra länkar och den tillhörande principen för säkra länkar samtidigt med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="953fb-123">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="953fb-124">När du ändrar en Valv-länkprincip ändras regeln för säkra länkar om namn, prioritet, aktiverad eller inaktiverad, och mottagarfilter.</span><span class="sxs-lookup"><span data-stu-id="953fb-124">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="953fb-125">Alla andra inställningar ändrar den associerade principen för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="953fb-125">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="953fb-126">När du tar Valv princip för säkra länkar och den tillhörande principen för säkra länkar tas den bort.</span><span class="sxs-lookup"><span data-stu-id="953fb-126">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="953fb-127">I Exchange Online PowerShell eller fristående EOP PowerShell hanterar du policyn och regeln separat.</span><span class="sxs-lookup"><span data-stu-id="953fb-127">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="953fb-128">Mer information finns i avsnittet Använda Exchange Online PowerShell eller [fristående EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) för att konfigurera Valv-länkar längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="953fb-128">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="953fb-129">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="953fb-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="953fb-130">Du kan öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="953fb-130">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="953fb-131">Om du vill gå **direkt Valv sidan** Länkar använder du <https://security.microsoft.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="953fb-131">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="953fb-132">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="953fb-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="953fb-133">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="953fb-133">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="953fb-134">Du måste ha tilldelats behörigheter innan du kan utföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="953fb-134">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="953fb-135">Om du vill skapa, ändra och ta bort Valv-länkar måste du  vara medlem i rollgrupperna Organisationshantering  eller Säkerhetsadministratör  i Microsoft 365 Defender-portalen och medlem i rollgruppen Organisationshantering i Exchange Online. </span><span class="sxs-lookup"><span data-stu-id="953fb-135">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="953fb-136">För skrivskyddade åtkomst Valv länkar måste du vara medlem i rollgrupperna **Global Reader** **eller Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="953fb-136">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="953fb-137">Mer information finns i [Behörigheter i Microsoft 365 Defender-portalen](permissions-in-the-security-and-compliance-center.md) och [Behörigheter i Exchange Online.](/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="953fb-137">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="953fb-138">Om du lägger till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna  de behörigheter som krävs i Microsoft 365 Defender-portalen och behörigheter för andra funktioner Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="953fb-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="953fb-139">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="953fb-139">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="953fb-140">.</span><span class="sxs-lookup"><span data-stu-id="953fb-140">.</span></span> <span data-ttu-id="953fb-141">- **Rollgruppen Skrivskyddade** organisationshantering i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) även skrivskyddade funktioner för funktionen.</span><span class="sxs-lookup"><span data-stu-id="953fb-141">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="953fb-142">Vi rekommenderar inställningar för att Valv principer för länkar i Valv [principinställningar för länkar.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="953fb-142">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="953fb-143">Det kan ta upp till 30 minuter innan en ny eller uppdaterad princip tillämpas.</span><span class="sxs-lookup"><span data-stu-id="953fb-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="953fb-144">[Nya funktioner läggs kontinuerligt till i Microsoft Defender för Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="953fb-144">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="953fb-145">När nya funktioner läggs till kan du behöva justera dina befintliga principer Valv Länkar.</span><span class="sxs-lookup"><span data-stu-id="953fb-145">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a><span data-ttu-id="953fb-146">Använda Defender Microsoft 365 portalen för att skapa Valv länkar</span><span class="sxs-lookup"><span data-stu-id="953fb-146">Use the Microsoft 365 Defender portal to create Safe Links policies</span></span>

<span data-ttu-id="953fb-147">När du skapar Valv egen princip för Microsoft 365 Defender-portalen skapas regeln för säkra länkar och den tillhörande principen för säkra länkar samtidigt med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="953fb-147">Creating a custom Safe Links policy in the Microsoft 365 Defender portal creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="953fb-148">I Microsoft 365 Defender-portalen går du till **Principer & principer för** hot \> **Valv** \> **.**</span><span class="sxs-lookup"><span data-stu-id="953fb-148">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="953fb-149">På sidan **Valv klickar** du på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="953fb-149">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="953fb-150">Principguiden **Valv Länkar** öppnas.</span><span class="sxs-lookup"><span data-stu-id="953fb-150">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="953fb-151">Konfigurera **följande inställningar på** sidan Namnge principen:</span><span class="sxs-lookup"><span data-stu-id="953fb-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="953fb-152">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="953fb-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="953fb-153">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="953fb-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="953fb-154">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="953fb-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="953fb-155">På **Inställningar** som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="953fb-155">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="953fb-156">**Välj åtgärden för okända potentiellt skadliga URL-adresser i meddelanden:** Välj **På** för att Valv skydd mot länkar i e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="953fb-156">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="953fb-157">**Välj åtgärden för okända eller potentiellt skadliga URL-adresser** i Microsoft Teams : Välj På för att aktivera Valv skydd för länkar i Teams. </span><span class="sxs-lookup"><span data-stu-id="953fb-157">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="953fb-158">**Använd URL-skanning i realtid** för misstänkta länkar och länkar som pekar på filer: Välj den här inställningen om du vill aktivera genomsökning i realtid av länkar i e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="953fb-158">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="953fb-159">**Vänta tills URL-skanningen** är klar innan du levererar meddelandet : Välj den här inställningen om du vill vänta på att URL-skanningen i realtid ska slutföras innan meddelandet levereras.</span><span class="sxs-lookup"><span data-stu-id="953fb-159">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="953fb-160">Använd Valv länkar till e-postmeddelanden som skickas inom organisationen: Välj den här inställningen om du vill använda principen **Valv-länkar** för meddelanden mellan interna avsändare och interna mottagare.</span><span class="sxs-lookup"><span data-stu-id="953fb-160">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="953fb-161">**Spåra inte användarklick: Låt den** här inställningen vara avmarkerad om du vill aktivera uppföljningsanvändaren klick på URL:er i e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="953fb-161">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="953fb-162">**Tillåt inte att användare klickar sig fram till** den ursprungliga URL:en: Välj den här inställningen om du vill blockera användare från att klicka till den ursprungliga URL:en på [varningssidor.](safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="953fb-162">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="953fb-163">**Skriva inte om följande URL:er:** Ger åtkomst till angivna URL:er som annars skulle blockeras av Valv Länkar.</span><span class="sxs-lookup"><span data-stu-id="953fb-163">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="953fb-164">I rutan skriver du webbadressen eller värdet som du vill använda och klickar sedan på</span><span class="sxs-lookup"><span data-stu-id="953fb-164">In the box, type the URL or value that you want, and then click</span></span> ![Knappikonen Lägg till](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="953fb-166">.</span><span class="sxs-lookup"><span data-stu-id="953fb-166">.</span></span>

     <span data-ttu-id="953fb-167">Om du vill ta bort en befintlig post markerar du den och klickar på</span><span class="sxs-lookup"><span data-stu-id="953fb-167">To remove an existing entry, select it and then click</span></span> ![Knappikonen Ta bort](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="953fb-169">.</span><span class="sxs-lookup"><span data-stu-id="953fb-169">.</span></span>

     <span data-ttu-id="953fb-170">Information om [postsyntax finns i Postsyntax för listan "Ange inte om följande URL:er".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="953fb-170">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="953fb-171">Detaljerad information om dessa inställningar finns i inställningar [Valv för](safe-links.md#safe-links-settings-for-email-messages) e-postmeddelanden och inställningar Valv länkar [för Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="953fb-171">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="953fb-172">Fler rekommenderade värden för principinställningarna Standard och Strikt finns i Valv [principinställningar för Länkar.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="953fb-172">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="953fb-173">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="953fb-173">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="953fb-174">På sidan **Används på** som visas identifierar du de interna mottagare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="953fb-174">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="953fb-175">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="953fb-175">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="953fb-176">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="953fb-176">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="953fb-177">Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="953fb-177">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="953fb-178">Klicka **på Lägg till ett villkor.**</span><span class="sxs-lookup"><span data-stu-id="953fb-178">Click **Add a condition**.</span></span> <span data-ttu-id="953fb-179">I listrutan som visas väljer du ett villkor under **Används om:**</span><span class="sxs-lookup"><span data-stu-id="953fb-179">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="953fb-180">**Mottagaren är: Anger** en eller flera postlådor, e-postanvändare eller e-postkontakter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="953fb-180">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="953fb-181">**Mottagaren är medlem i**: Anger en eller flera grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="953fb-181">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="953fb-182">**Mottagande domän är**: Anger mottagare i en eller flera av de godkända domänerna som har konfigurerats i din organisation.</span><span class="sxs-lookup"><span data-stu-id="953fb-182">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="953fb-183">När du har valt villkoret visas motsvarande listruta med rutan **Valfri av dessa.**</span><span class="sxs-lookup"><span data-stu-id="953fb-183">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="953fb-184">Klicka i rutan och bläddra igenom listan med värden du vill välja.</span><span class="sxs-lookup"><span data-stu-id="953fb-184">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="953fb-185">Klicka i rutan och börja skriva för att filtrera listan och välja ett värde.</span><span class="sxs-lookup"><span data-stu-id="953fb-185">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="953fb-186">Om du vill lägga till ytterligare värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="953fb-186">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="953fb-187">Om du vill ta bort enskilda poster klickar **du på Ta** bort ikon för ![ ](../../media/scc-remove-icon.png) värdet.</span><span class="sxs-lookup"><span data-stu-id="953fb-187">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="953fb-188">Om du vill ta bort hela villkoret klickar du **på Ta** bort ikon ![ för ](../../media/scc-remove-icon.png) villkoret.</span><span class="sxs-lookup"><span data-stu-id="953fb-188">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="953fb-189">Om du vill lägga till ytterligare ett villkor klickar **du på Lägg till ett** villkor och väljer ett återstående värde under Används **om**.</span><span class="sxs-lookup"><span data-stu-id="953fb-189">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="953fb-190">Om du vill lägga till undantag klickar **du på Lägg till ett** villkor och väljer ett undantag under Utom **om**.</span><span class="sxs-lookup"><span data-stu-id="953fb-190">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="953fb-191">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="953fb-191">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="953fb-192">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="953fb-192">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="953fb-193">Granska **inställningarna på sidan** Granska dina inställningar som visas.</span><span class="sxs-lookup"><span data-stu-id="953fb-193">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="953fb-194">Du kan klicka **på Redigera** för varje inställning för att ändra den.</span><span class="sxs-lookup"><span data-stu-id="953fb-194">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="953fb-195">Klicka på Slutför när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="953fb-195">When you're finished, click **Finish**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a><span data-ttu-id="953fb-196">Använda Defender Microsoft 365 portalen för att visa Valv principer för länkar</span><span class="sxs-lookup"><span data-stu-id="953fb-196">Use the Microsoft 365 Defender portal to view Safe Links policies</span></span>

1. <span data-ttu-id="953fb-197">I Microsoft 365 Defender-portalen går du till **Principer & principer för** hot \> **Valv** \> **.**</span><span class="sxs-lookup"><span data-stu-id="953fb-197">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="953fb-198">På **Valv länkar** väljer du en princip i listan och klickar på den (markera inte kryssrutan).</span><span class="sxs-lookup"><span data-stu-id="953fb-198">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="953fb-199">Principinformationen visas i en flyg ut</span><span class="sxs-lookup"><span data-stu-id="953fb-199">The policy details appear in a fly out</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a><span data-ttu-id="953fb-200">Använda Defender Microsoft 365 portalen för att ändra Valv länkar</span><span class="sxs-lookup"><span data-stu-id="953fb-200">Use the Microsoft 365 Defender portal to modify Safe Links policies</span></span>

1. <span data-ttu-id="953fb-201">I Microsoft 365 Defender-portalen går du till \***Principer & principer för** hot \> **Valv** \> **.**</span><span class="sxs-lookup"><span data-stu-id="953fb-201">In the Microsoft 365 Defender portal, go to \***Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="953fb-202">På **Valv länkar** väljer du en princip i listan och klickar på den (markera inte kryssrutan).</span><span class="sxs-lookup"><span data-stu-id="953fb-202">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="953fb-203">I den utfällna menyn med principinformation klickar du på **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="953fb-203">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="953fb-204">De tillgängliga inställningarna som visas är identiska med de som beskrivs i avsnittet [använda Defender Microsoft 365 för att skapa Valv-länkar.](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies)</span><span class="sxs-lookup"><span data-stu-id="953fb-204">The available settings in the fly out that appears are identical to those described in the [Use the Microsoft 365 Defender portal to create Safe Links policies](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="953fb-205">Läs följande avsnitt om du vill aktivera eller inaktivera en princip eller ange prioritetsordning för principen.</span><span class="sxs-lookup"><span data-stu-id="953fb-205">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="953fb-206">Aktivera eller inaktivera Valv länkar</span><span class="sxs-lookup"><span data-stu-id="953fb-206">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="953fb-207">I Microsoft 365 Defender-portalen går du till **Principer & principer för** hot \> **Valv** \> **.**</span><span class="sxs-lookup"><span data-stu-id="953fb-207">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="953fb-208">Observera värdet i **kolumnen** Status:</span><span class="sxs-lookup"><span data-stu-id="953fb-208">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="953fb-209">Flytta växlingsknappen åt vänster om du vill inaktivera principen:</span><span class="sxs-lookup"><span data-stu-id="953fb-209">Move the toggle to the left to disable the policy:</span></span> ![Inaktivera principen](../../media/scc-toggle-off.png)<span data-ttu-id="953fb-211">.</span><span class="sxs-lookup"><span data-stu-id="953fb-211">.</span></span>

   - <span data-ttu-id="953fb-212">Flytta växlingsknappen åt höger om du vill aktivera principen:</span><span class="sxs-lookup"><span data-stu-id="953fb-212">Move the toggle to the right to enable the policy:</span></span> ![Aktivera princip](../../media/scc-toggle-on.png)<span data-ttu-id="953fb-214">.</span><span class="sxs-lookup"><span data-stu-id="953fb-214">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="953fb-215">Ange prioriteten för Valv-länkar</span><span class="sxs-lookup"><span data-stu-id="953fb-215">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="953fb-216">Som standard prioriteras Valv-länkar-principer som baseras på den ordning de skapades i (nyare principer har lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="953fb-216">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="953fb-217">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="953fb-217">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="953fb-218">Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="953fb-218">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="953fb-219">För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="953fb-219">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="953fb-220">Valv Länkprinciper visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0).</span><span class="sxs-lookup"><span data-stu-id="953fb-220">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

> [!NOTE]
> <span data-ttu-id="953fb-221">I Microsoft 365 Defender-portalen kan du bara ändra prioritet för Valv Länkar när du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="953fb-221">In the Microsoft 365 Defender portal, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="953fb-222">I PowerShell kan du åsidosätta standardprioritet när du skapar regeln om säkra länkar (vilket kan påverka prioriteringen för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="953fb-222">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="953fb-223">Om du vill ändra prioriteten för en princip flyttar du principen uppåt  eller nedåt i listan (du kan inte direkt ändra prioritetsnumret i Microsoft 365 Defender-portalen).</span><span class="sxs-lookup"><span data-stu-id="953fb-223">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span>

1. <span data-ttu-id="953fb-224">I Microsoft 365 Defender-portalen går du till **Principer & principer för** hot \> **Valv** \> **.**</span><span class="sxs-lookup"><span data-stu-id="953fb-224">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="953fb-225">På **Valv länkar** väljer du en princip i listan och klickar på den (markera inte kryssrutan).</span><span class="sxs-lookup"><span data-stu-id="953fb-225">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="953fb-226">I den policyinformation som visas klickar du på knappen med tillgänglig prioritet:</span><span class="sxs-lookup"><span data-stu-id="953fb-226">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="953fb-227">Principen Valv med **prioritetsvärdet** **0** har endast knappen **Minska** prioritet tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="953fb-227">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="953fb-228">Principen Valv med det lägsta värdet **för** Prioritet (till exempel **3**) har endast knappen **Öka** prioritet tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="953fb-228">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="953fb-229">Om du har tre eller fler Valv-länkar finns det både knapparna  Öka prioritet och Minska prioritet mellan de högsta och lägsta  prioritetsvärdena.</span><span class="sxs-lookup"><span data-stu-id="953fb-229">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="953fb-230">Klicka **på Öka prioritet** eller Minska **prioritet** om du vill ändra värdet **för** Prioritet.</span><span class="sxs-lookup"><span data-stu-id="953fb-230">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="953fb-231">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="953fb-231">When you're finished, click **Close**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a><span data-ttu-id="953fb-232">Använda Defender-Microsoft 365 för att ta bort principer Valv Länkar</span><span class="sxs-lookup"><span data-stu-id="953fb-232">Use the Microsoft 365 Defender portal to remove Safe Links policies</span></span>

1. <span data-ttu-id="953fb-233">I Microsoft 365 Defender-portalen går du till **Principer & principer för** hot \> **Valv** \> **.**</span><span class="sxs-lookup"><span data-stu-id="953fb-233">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="953fb-234">På **Valv länkar** väljer du en princip i listan och klickar på den (markera inte kryssrutan).</span><span class="sxs-lookup"><span data-stu-id="953fb-234">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="953fb-235">I policyinformationen som visas klickar du på Ta **bort princip** och sedan på **Ja i** varningsdialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="953fb-235">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="953fb-236">Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera Valv-länkar</span><span class="sxs-lookup"><span data-stu-id="953fb-236">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="953fb-237">Som tidigare beskrivits består en Valv-länkprincip av en princip för säkra länkar och en regel för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="953fb-237">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="953fb-238">I PowerShell visas skillnaden mellan principer för säkra länkar och regler för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="953fb-238">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="953fb-239">Du hanterar principer för säkra länkar med hjälp av cmdletarna **\* -SafeLinksPolicy** och hanterar regler för säkra länkar med hjälp av cmdletarna **\* -SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="953fb-239">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="953fb-240">I PowerShell skapar du först principen för säkra länkar och sedan skapar du den regel för säkra länkar som identifierar principen som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="953fb-240">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="953fb-241">I PowerShell ändrar du inställningarna i principen för säkra länkar och regeln om säkra länkar separat.</span><span class="sxs-lookup"><span data-stu-id="953fb-241">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="953fb-242">När du tar bort en princip för säkra länkar från PowerShell tas inte motsvarande regel för säkra länkar bort automatiskt och vice versa.</span><span class="sxs-lookup"><span data-stu-id="953fb-242">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="953fb-243">Använda PowerShell för att skapa Valv-länkar</span><span class="sxs-lookup"><span data-stu-id="953fb-243">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="953fb-244">Att skapa Valv princip för Länkar i PowerShell är en process i två steg:</span><span class="sxs-lookup"><span data-stu-id="953fb-244">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="953fb-245">Skapa principen för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="953fb-245">Create the safe links policy.</span></span>
2. <span data-ttu-id="953fb-246">Skapa den regel för säkra länkar som anger principen för säkra länkar som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="953fb-246">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="953fb-247">Du kan skapa en ny regel för säkra länkar och tilldela en befintlig princip för säkra länkar som inte har associerats till den.</span><span class="sxs-lookup"><span data-stu-id="953fb-247">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="953fb-248">En regel för säkra länkar kan inte associeras med mer än en princip för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="953fb-248">A safe links rule can't be associated with more than one safe links policy.</span></span>
> 
> - <span data-ttu-id="953fb-249">Du kan konfigurera följande inställningar för nya principer för säkra länkar i PowerShell som inte är tillgängliga i Microsoft 365 Defender-portalen förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="953fb-249">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
> 
>   - <span data-ttu-id="953fb-250">Skapa den nya principen som _inaktiverad (aktiverad_ `$false` på **cmdleten New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="953fb-250">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="953fb-251">Ange prioritet för principen vid skapandet _(Priority_ _\<Number\>_ ) på **New-SafeLinksRule-cmdleten).**</span><span class="sxs-lookup"><span data-stu-id="953fb-251">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
> 
> - <span data-ttu-id="953fb-252">En ny princip för säkra länkar som du skapar i PowerShell visas inte i Microsoft 365 Defender-portalen förrän du tilldelar principen till en regel för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="953fb-252">A new safe links policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="953fb-253">Steg 1: Använda PowerShell för att skapa en princip för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="953fb-253">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="953fb-254">Använd följande syntax för att skapa en princip för säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="953fb-254">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - <span data-ttu-id="953fb-255">Mer information om postsyntaxen för parametern _DoNotRewriteUrls_ finns i Postsyntax för listan "Ange inte om följande URL:er". [](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="953fb-255">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
> 
> - <span data-ttu-id="953fb-256">Ytterligare syntax som du kan använda för parametern _DoNotRewriteUrls_ när du ändrar befintliga principer för säkra länkar med hjälp av cmdleten **Set-SafeLinksPolicy** finns i avsnittet Använda [PowerShell](#use-powershell-to-modify-safe-links-policies) för att ändra principer för säkra länkar längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="953fb-256">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="953fb-257">I det här exemplet skapas en princip för säkra länkar med namnet Contoso Alla med följande värden:</span><span class="sxs-lookup"><span data-stu-id="953fb-257">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="953fb-258">Aktivera URL-skanning och skriva om den i e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="953fb-258">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="953fb-259">Aktivera URL-skanning i Teams (endast TAP Preview).</span><span class="sxs-lookup"><span data-stu-id="953fb-259">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="953fb-260">Aktivera genomsökning i realtid av klickade URL:er, inklusive klickade länkar som pekar på filer.</span><span class="sxs-lookup"><span data-stu-id="953fb-260">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="953fb-261">Vänta tills URL-skanningen är klar innan du levererar meddelandet.</span><span class="sxs-lookup"><span data-stu-id="953fb-261">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="953fb-262">Aktivera URL-genomsökning och skriva om interna meddelanden.</span><span class="sxs-lookup"><span data-stu-id="953fb-262">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="953fb-263">Spåra användarklick relaterade till Valv-länkskydd (vi använder inte parametern _DoNotTrackUserClicks_ och standardvärdet är $false vilket innebär att användarklickningar spåras).</span><span class="sxs-lookup"><span data-stu-id="953fb-263">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="953fb-264">Tillåt inte att användare klickar sig fram till den ursprungliga URL:en.</span><span class="sxs-lookup"><span data-stu-id="953fb-264">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="953fb-265">Detaljerad information om syntax och parametrar finns [i New-SafeLinksPolicy.](/powershell/module/exchange/new-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="953fb-265">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="953fb-266">Steg 2: Använda PowerShell för att skapa en regel för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="953fb-266">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="953fb-267">Använd följande syntax för att skapa en regel för säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="953fb-267">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="953fb-268">I det här exemplet skapas en regel för säkra länkar med namnet Contoso Alla med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="953fb-268">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="953fb-269">Regeln är kopplad till principen För säkra länkar med namnet Contoso Alla.</span><span class="sxs-lookup"><span data-stu-id="953fb-269">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="953fb-270">Regeln gäller för alla mottagare i contoso.com domän.</span><span class="sxs-lookup"><span data-stu-id="953fb-270">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="953fb-271">Eftersom vi inte använder _parametern Priority_ används standardprioritet.</span><span class="sxs-lookup"><span data-stu-id="953fb-271">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="953fb-272">Regeln är aktiverad (vi använder inte parametern _Enabled_ och standardvärdet är `$true` ).</span><span class="sxs-lookup"><span data-stu-id="953fb-272">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="953fb-273">Detaljerad information om syntax och parametrar finns [i New-SafeLinksRule.](/powershell/module/exchange/new-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="953fb-273">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="953fb-274">Använda PowerShell för att visa principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="953fb-274">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="953fb-275">Använd följande syntax för att visa befintliga principer för säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="953fb-275">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="953fb-276">Det här exemplet returnerar en sammanfattningslista över alla principer för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="953fb-276">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="953fb-277">Det här exemplet returnerar detaljerad information om principen för säkra länkar som heter Contoso-chefer.</span><span class="sxs-lookup"><span data-stu-id="953fb-277">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="953fb-278">Detaljerad information om syntax och parametrar finns i [Get-SafeLinksPolicy.](/powershell/module/exchange/get-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="953fb-278">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="953fb-279">Använda PowerShell för att visa regler för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="953fb-279">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="953fb-280">Om du vill visa befintliga regler för säkra länkar använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="953fb-280">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="953fb-281">Det här exemplet returnerar en sammanfattningslista över alla regler för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="953fb-281">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="953fb-282">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="953fb-282">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="953fb-283">Det här exemplet returnerar detaljerad information om regeln Contoso Executives som heter Säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="953fb-283">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="953fb-284">Detaljerad information om syntax och parametrar finns i [Get-SafeLinksRule.](/powershell/module/exchange/get-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="953fb-284">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="953fb-285">Använda PowerShell för att ändra principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="953fb-285">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="953fb-286">Du kan inte byta namn på en princip för säkra länkar i PowerShell **(Set-SafeLinksPolicy-cmdleten** har ingen _namnparameter)._</span><span class="sxs-lookup"><span data-stu-id="953fb-286">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="953fb-287">När du byter namn Valv princip för Microsoft 365 Defender-portalen byter du bara namn på regeln för säkra _länkar._</span><span class="sxs-lookup"><span data-stu-id="953fb-287">When you rename a Safe Links policy in the Microsoft 365 Defender portal, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="953fb-288">Den enda ytterligare faktorn för att ändra principer för säkra länkar i PowerShell är den tillgängliga syntaxen för parametern _DoNotRewriteUrls_ (listan ["Ange](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)inte om följande URL:er"):</span><span class="sxs-lookup"><span data-stu-id="953fb-288">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="953fb-289">Om du vill lägga till värden som ska ersätta befintliga poster använder du följande syntax: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="953fb-289">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="953fb-290">Om du vill lägga till eller ta bort värden utan att påverka andra befintliga poster använder du följande syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="953fb-290">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="953fb-291">Annars är samma inställningar tillgängliga när du skapar en princip för säkra länkar enligt beskrivningen i steg [1:](#step-1-use-powershell-to-create-a-safe-links-policy) Använda PowerShell för att skapa en princip för säkra länkar längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="953fb-291">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="953fb-292">Använd följande syntax för att ändra en princip för säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="953fb-292">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="953fb-293">Detaljerad information om syntax och parametrar finns i [Set-SafeLinksPolicy.](/powershell/module/exchange/set-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="953fb-293">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="953fb-294">Använda PowerShell för att ändra regler för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="953fb-294">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="953fb-295">Den enda inställning som inte är tillgänglig när du ändrar en regel för säkra länkar i PowerShell är parametern _Enabled_ som gör att du kan skapa en inaktiverad regel.</span><span class="sxs-lookup"><span data-stu-id="953fb-295">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="953fb-296">Nästa avsnitt innehåller information om hur du aktiverar eller inaktiverar befintliga regler för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="953fb-296">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="953fb-297">Annars är samma inställningar tillgängliga när du skapar en regel som beskrivs i steg [2:](#step-2-use-powershell-to-create-a-safe-links-rule) Använd PowerShell för att skapa en regel för säkra länkar längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="953fb-297">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="953fb-298">Använd följande syntax för att ändra en regel för säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="953fb-298">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="953fb-299">Detaljerad information om syntax och parametrar finns [i Set-SafeLinksRule.](/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="953fb-299">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="953fb-300">Använda PowerShell för att aktivera eller inaktivera regler för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="953fb-300">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="953fb-301">Om du aktiverar eller inaktiverar en regel för säkra länkar i PowerShell aktiveras eller inaktiveras hela Valv Links-principen (regeln för säkra länkar och den tilldelade principen för säkra länkar).</span><span class="sxs-lookup"><span data-stu-id="953fb-301">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="953fb-302">Om du vill aktivera eller inaktivera en regel för säkra länkar i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="953fb-302">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="953fb-303">I det här exemplet inaktiveras regeln För säkra länkar med namnet Marknadsföringsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="953fb-303">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="953fb-304">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="953fb-304">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="953fb-305">Detaljerad information om syntax och parametrar finns i [Enable-SafeLinksRule och](/powershell/module/exchange/enable-safelinksrule) [Disable-SafeLinksRule.](/powershell/module/exchange/disable-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="953fb-305">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="953fb-306">Använda PowerShell för att ange prioritet för regler för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="953fb-306">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="953fb-307">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="953fb-307">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="953fb-308">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="953fb-308">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="953fb-309">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="953fb-309">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="953fb-310">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="953fb-310">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="953fb-311">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="953fb-311">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="953fb-312">Ange prioritet för en regel för säkra länkar i PowerShell med följande syntax:</span><span class="sxs-lookup"><span data-stu-id="953fb-312">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="953fb-313">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="953fb-313">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="953fb-314">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="953fb-314">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="953fb-315">Om du vill ange prioriteten för en ny regel när du skapar den använder du parametern _Priority_ i cmdleten **New-SafeLinksRule** i stället.</span><span class="sxs-lookup"><span data-stu-id="953fb-315">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="953fb-316">Detaljerad information om syntax och parametrar finns [i Set-SafeLinksRule.](/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="953fb-316">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="953fb-317">Använda PowerShell för att ta bort principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="953fb-317">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="953fb-318">När du använder PowerShell för att ta bort en princip för säkra länkar tas motsvarande regel för säkra länkar inte bort.</span><span class="sxs-lookup"><span data-stu-id="953fb-318">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="953fb-319">Använd följande syntax för att ta bort en princip för säkra länkar i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="953fb-319">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="953fb-320">Det här exemplet tar bort principen för säkra länkar med namnet Marknadsföringsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="953fb-320">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="953fb-321">Detaljerad information om syntax och parametrar finns i [Remove-SafeLinksPolicy.](/powershell/module/exchange/remove-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="953fb-321">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="953fb-322">Använda PowerShell för att ta bort regler för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="953fb-322">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="953fb-323">När du använder PowerShell för att ta bort en regel för säkra länkar tas motsvarande princip för säkra länkar inte bort.</span><span class="sxs-lookup"><span data-stu-id="953fb-323">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="953fb-324">Använd följande syntax för att ta bort en regel för säkra länkar i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="953fb-324">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="953fb-325">Det här exemplet tar bort regeln om säkra länkar med namnet Marknadsföringsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="953fb-325">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="953fb-326">Detaljerad information om syntax och parametrar finns i [Remove-SafeLinksRule.](/powershell/module/exchange/remove-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="953fb-326">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="953fb-327">Kontrollera att Valv söker igenom meddelanden genom att titta i tillgängliga Microsoft Defender Office 365.</span><span class="sxs-lookup"><span data-stu-id="953fb-327">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="953fb-328">Mer information finns i [Visa rapporter för Defender för Office 365](view-reports-for-mdo.md) och Använda [Utforskaren i Microsoft 365 Defender-portalen.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="953fb-328">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="953fb-329">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="953fb-329">How do you know these procedures worked?</span></span>

<span data-ttu-id="953fb-330">Kontrollera att du har skapat, ändrat eller tagit bort principer Valv länkar genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="953fb-330">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="953fb-331">I Defender Microsoft 365 portalen går du till **Principer för & principer** för hot \> **Valv** \> **.**</span><span class="sxs-lookup"><span data-stu-id="953fb-331">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Safe Links**.</span></span> <span data-ttu-id="953fb-332">Kontrollera listan med principer, deras **statusvärden** och deras **prioritetsvärden.**</span><span class="sxs-lookup"><span data-stu-id="953fb-332">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="953fb-333">Om du vill visa mer information väljer du principen i listan och visar informationen i den utfäll plats du vill ha.</span><span class="sxs-lookup"><span data-stu-id="953fb-333">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="953fb-334">I Exchange Online PowerShell eller Exchange Online Protection PowerShell ersätter du med namnet på principen eller regeln, kör följande kommando och \<Name\> kontrollerar inställningarna:</span><span class="sxs-lookup"><span data-stu-id="953fb-334">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```