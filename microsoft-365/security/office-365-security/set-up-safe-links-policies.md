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
ms.openlocfilehash: fb157792f0f9e80e4a974b59aebaa2e1991c5d0b
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933125"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="6540f-103">Konfigurera principer Valv Länkar i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="6540f-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6540f-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="6540f-104">**Applies to**</span></span>
- [<span data-ttu-id="6540f-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="6540f-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6540f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6540f-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="6540f-107">Den här artikeln är avsedd för företagskunder som har [Microsoft Defender för Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="6540f-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="6540f-108">Om du är hemanvändare och vill ha information om säkra länkar i Outlook kan du läsa [Mer Outlook.com-säkerhet.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="6540f-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="6540f-109">Valv Länkar i [Microsoft Defender för Office 365](defender-for-office-365.md) tillhandahåller URL-genomsökning av inkommande e-postmeddelanden i e-postflödet och tidpunkten för klickverifiering av URL:er och länkar i e-postmeddelanden och på andra platser.</span><span class="sxs-lookup"><span data-stu-id="6540f-109">Safe Links in [Microsoft Defender for Office 365](defender-for-office-365.md) provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="6540f-110">Mer information finns i artikeln [Valv i Microsoft Defender för Office 365](safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="6540f-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="6540f-111">Det finns ingen inbyggd eller standardprincip för Valv länkar.</span><span class="sxs-lookup"><span data-stu-id="6540f-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="6540f-112">Om du Valv länkar för genomsökning av URL:er måste du skapa en eller flera Valv länkar enligt beskrivningen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="6540f-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
>
> <span data-ttu-id="6540f-113">Du konfigurerar de globala inställningarna Valv skydd **vid länkar utanför** Valv Principer för länkar.</span><span class="sxs-lookup"><span data-stu-id="6540f-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="6540f-114">Anvisningar finns i [Konfigurera globala inställningar för Valv i Microsoft Defender för Office 365.](configure-global-settings-for-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="6540f-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>
>
> <span data-ttu-id="6540f-115">Administratörer bör överväga de olika konfigurationsinställningarna för Valv Länkar.</span><span class="sxs-lookup"><span data-stu-id="6540f-115">Admins should consider the different configuration settings for Safe Links.</span></span> <span data-ttu-id="6540f-116">Ett av de tillgängliga alternativen är att inkludera användaridentifierande information i Valv Länkar.</span><span class="sxs-lookup"><span data-stu-id="6540f-116">One of the available options is to include user identifiable information in Safe Links.</span></span> <span data-ttu-id="6540f-117">Med den här funktionen kan *säkerhets ops-team* undersöka potentiella användarintrång, vidta korrigerande åtgärder och begränsa dyrbara överträdelser.</span><span class="sxs-lookup"><span data-stu-id="6540f-117">This feature enables *Security Ops teams* to investigate potential user compromise, take corrective action, and limit costly breaches.</span></span>

<span data-ttu-id="6540f-118">Du kan konfigurera principer för Valv-länkar i Microsoft 365 Defender-portalen eller i PowerShell (Exchange Online PowerShell för kvalificerade Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor, men med Microsoft Defender för Office 365-tilläggsprenumerationer).</span><span class="sxs-lookup"><span data-stu-id="6540f-118">You can configure Safe Links policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="6540f-119">De grundläggande elementen i en Valv-länkprincip är:</span><span class="sxs-lookup"><span data-stu-id="6540f-119">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="6540f-120">Principen för säkra **länkar:** Aktivera skydd mot Valv-länkar, aktivera URL-genomsökning i realtid, ange om du vill vänta på att skanning i realtid ska slutföras innan meddelandet levereras, aktivera genomsökning av interna meddelanden, ange om användaren ska klicka på URL-adresser och ange om de vill tillåta att användare klickar på samma webbadress.</span><span class="sxs-lookup"><span data-stu-id="6540f-120">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="6540f-121">**Regeln säkra länkar:** Anger prioritet och mottagarfilter (vem principen gäller för).</span><span class="sxs-lookup"><span data-stu-id="6540f-121">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="6540f-122">Skillnaden mellan dessa två element är inte uppenbara när du hanterar Valv Länkar i Microsoft 365 Defender-portalen:</span><span class="sxs-lookup"><span data-stu-id="6540f-122">The difference between these two elements isn't obvious when you manage Safe Links polices in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="6540f-123">När du skapar Valv princip för länkar skapar du egentligen en regel för säkra länkar och den tillhörande principen för säkra länkar samtidigt med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="6540f-123">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="6540f-124">När du ändrar en Valv-länkprincip ändras regeln för säkra länkar om namn, prioritet, aktiverad eller inaktiverad, och mottagarfilter.</span><span class="sxs-lookup"><span data-stu-id="6540f-124">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="6540f-125">Alla andra inställningar ändrar den associerade principen för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="6540f-125">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="6540f-126">När du tar Valv princip för säkra länkar och den tillhörande principen för säkra länkar tas den bort.</span><span class="sxs-lookup"><span data-stu-id="6540f-126">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="6540f-127">I Exchange Online PowerShell eller fristående EOP PowerShell hanterar du policyn och regeln separat.</span><span class="sxs-lookup"><span data-stu-id="6540f-127">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="6540f-128">Mer information finns i avsnittet Använda Exchange Online PowerShell eller [fristående EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) för att konfigurera Valv-länkar längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="6540f-128">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6540f-129">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="6540f-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6540f-130">Du kan öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="6540f-130">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="6540f-131">Om du vill gå **direkt Valv sidan** Länkar använder du <https://security.microsoft.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="6540f-131">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="6540f-132">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="6540f-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="6540f-133">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="6540f-133">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="6540f-134">Du måste ha tilldelats behörigheter innan du kan utföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="6540f-134">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="6540f-135">Om du vill skapa, ändra och ta bort Valv-länkar måste du  vara medlem i rollgrupperna Organisationshantering  eller Säkerhetsadministratör  i Microsoft 365 Defender-portalen och medlem i rollgruppen Organisationshantering i Exchange Online. </span><span class="sxs-lookup"><span data-stu-id="6540f-135">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="6540f-136">För skrivskyddade åtkomst Valv länkar måste du vara medlem i rollgrupperna **Global Reader** **eller Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="6540f-136">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="6540f-137">Mer information finns i [Behörigheter i Microsoft 365 Defender-portalen](permissions-in-the-security-and-compliance-center.md) och [Behörigheter i Exchange Online.](/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="6540f-137">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="6540f-138">Om du lägger till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna  de behörigheter som krävs i Microsoft 365 Defender-portalen och behörigheter för andra funktioner Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6540f-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="6540f-139">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="6540f-139">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="6540f-140">.</span><span class="sxs-lookup"><span data-stu-id="6540f-140">.</span></span> <span data-ttu-id="6540f-141">- **Rollgruppen Skrivskyddade** organisationshantering i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) även skrivskyddade funktioner för funktionen.</span><span class="sxs-lookup"><span data-stu-id="6540f-141">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="6540f-142">Vi rekommenderar inställningar för att Valv principer för länkar i Valv [principinställningar för länkar.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="6540f-142">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="6540f-143">Det kan ta upp till 30 minuter innan en ny eller uppdaterad princip tillämpas.</span><span class="sxs-lookup"><span data-stu-id="6540f-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="6540f-144">[Nya funktioner läggs kontinuerligt till i Microsoft Defender för Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="6540f-144">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="6540f-145">När nya funktioner läggs till kan du behöva justera dina befintliga principer Valv Länkar.</span><span class="sxs-lookup"><span data-stu-id="6540f-145">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a><span data-ttu-id="6540f-146">Använda Defender Microsoft 365 portalen för att skapa Valv länkar</span><span class="sxs-lookup"><span data-stu-id="6540f-146">Use the Microsoft 365 Defender portal to create Safe Links policies</span></span>

<span data-ttu-id="6540f-147">När du skapar Valv egen princip för Microsoft 365 Defender-portalen skapas regeln för säkra länkar och den tillhörande principen för säkra länkar samtidigt med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="6540f-147">Creating a custom Safe Links policy in the Microsoft 365 Defender portal creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="6540f-148">I Microsoft 365 Defender-portalen går du till **Principer & Principer** för \> **hotprinciper** Valv \>  \> **Länkar.**</span><span class="sxs-lookup"><span data-stu-id="6540f-148">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="6540f-149">På sidan **Valv klickar** du på Skapa ![ ikon ](../../media/m365-cc-sc-create-icon.png) **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="6540f-149">On the **Safe Links** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="6540f-150">Principguiden **Valv Länkar** öppnas.</span><span class="sxs-lookup"><span data-stu-id="6540f-150">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="6540f-151">Konfigurera **följande inställningar på** sidan Namnge principen:</span><span class="sxs-lookup"><span data-stu-id="6540f-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="6540f-152">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="6540f-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="6540f-153">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="6540f-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="6540f-154">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="6540f-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="6540f-155">På sidan **Användare och domäner** som visas identifierar du de interna mottagare som principen gäller för (mottagarvillkor):</span><span class="sxs-lookup"><span data-stu-id="6540f-155">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="6540f-156">**Användare**: De angivna postlådorna, e-postanvändarna eller e-postkontakterna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6540f-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="6540f-157">**Grupper**: De angivna distributionsgrupper, e-postaktiverade säkerhetsgrupper eller Microsoft 365-grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6540f-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="6540f-158">**Domäner**: Alla mottagare i den angivna [godkända domänen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6540f-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="6540f-159">Klicka i lämplig ruta, börja skriva in ett värde och välj det värde du vill använda i resultatet.</span><span class="sxs-lookup"><span data-stu-id="6540f-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="6540f-160">Upprepa det här steget så många gånger som det behövs.</span><span class="sxs-lookup"><span data-stu-id="6540f-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="6540f-161">Om du vill ta bort ett befintligt värde klickar du Ta bort</span><span class="sxs-lookup"><span data-stu-id="6540f-161">To remove an existing value, click remove</span></span> ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="6540f-163">bredvid värdet.</span><span class="sxs-lookup"><span data-stu-id="6540f-163">next to the value.</span></span>

   <span data-ttu-id="6540f-164">För användare eller grupper kan du använda de flesta identifierare (namn, visningsnamn, alias, e-postadress, kontonamn osv.), men motsvarande visningsnamn visas i resultatet.</span><span class="sxs-lookup"><span data-stu-id="6540f-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="6540f-165">Om du vill visa alla tillgängliga värden för användare anger du en asterisk (\*) för sig själv.</span><span class="sxs-lookup"><span data-stu-id="6540f-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="6540f-166">Använd ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_) för flera värden i samma villkor.</span><span class="sxs-lookup"><span data-stu-id="6540f-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="6540f-167">Använd OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_) för olika villkor.</span><span class="sxs-lookup"><span data-stu-id="6540f-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="6540f-168">**Exkludera dessa användare, grupper och domäner**: Om du vill lägga till undantag för interna mottagare som principen gäller för (Mottagarundantag), väljer du det här alternativet och konfigurerar undantagen.</span><span class="sxs-lookup"><span data-stu-id="6540f-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="6540f-169">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="6540f-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="6540f-170">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="6540f-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6540f-171">Konfigurera **följande inställningar** på sidan Skyddsinställningar som visas:</span><span class="sxs-lookup"><span data-stu-id="6540f-171">On the **Protection settings** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="6540f-172">**Välj åtgärden för okända potentiellt skadliga URL-adresser i meddelanden:** Välj **På** för att Valv skydd mot länkar i e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="6540f-172">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span> <span data-ttu-id="6540f-173">Om du aktiverar den här inställningen är följande inställningar tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="6540f-173">If you turn this setting on, the following settings are available:</span></span>
     - <span data-ttu-id="6540f-174">**Använd URL-skanning i realtid** för misstänkta länkar och länkar som pekar på filer: Välj det här alternativet om du vill aktivera genomsökning i realtid av länkar i e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="6540f-174">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this option to enable real-time scanning of links in email messages.</span></span> <span data-ttu-id="6540f-175">Om du aktiverar den här inställningen är följande inställning tillgänglig:</span><span class="sxs-lookup"><span data-stu-id="6540f-175">If you turn this setting on the following setting is available:</span></span>
       - <span data-ttu-id="6540f-176">**Vänta tills URL-skanningen** är klar innan du levererar meddelandet : Välj det här alternativet om du vill vänta på att URL-skanningen i realtid ska slutföras innan du levererar meddelandet.</span><span class="sxs-lookup"><span data-stu-id="6540f-176">**Wait for URL scanning to complete before delivering the message**: Select this option to wait for real-time URL scanning to complete before delivering the message.</span></span>
     - <span data-ttu-id="6540f-177">Använd Valv länkar till e-postmeddelanden som skickas inom organisationen: Välj det här alternativet om du vill använda principen **Valv-länkar** för meddelanden mellan interna avsändare och interna mottagare.</span><span class="sxs-lookup"><span data-stu-id="6540f-177">**Apply Safe Links to email messages sent within the organization**: Select this option to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>
   - <span data-ttu-id="6540f-178">**Välj åtgärden för okända eller potentiellt skadliga URL-adresser** i Microsoft Teams : Välj På för att aktivera Valv skydd för länkar i Teams. </span><span class="sxs-lookup"><span data-stu-id="6540f-178">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>
   - <span data-ttu-id="6540f-179">**Spåra inte användarklick: Låt den** här inställningen vara avmarkerad om du vill aktivera uppföljningsanvändaren klick på URL:er i e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="6540f-179">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>
   - <span data-ttu-id="6540f-180">**Tillåt inte att användare klickar sig fram till** den ursprungliga URL:en: Välj det här alternativet om du vill blockera användare från att klicka till den ursprungliga URL:en på [varningssidor.](safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="6540f-180">**Do not allow users to click through to original URL**: Select this option to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>
   - <span data-ttu-id="6540f-181">**Skriva inte om följande URL:er:** Ger åtkomst till angivna URL:er som annars skulle blockeras av Valv Länkar.</span><span class="sxs-lookup"><span data-stu-id="6540f-181">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="6540f-182">I rutan skriver du url-adressen eller värdet som du vill använda och klickar sedan på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="6540f-182">In the box, type the URL or value that you want, and then click **Add**.</span></span> <span data-ttu-id="6540f-183">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="6540f-183">Repeat this step as many times as necessary.</span></span>

     <span data-ttu-id="6540f-184">Om du vill ta bort en befintlig post klickar du på</span><span class="sxs-lookup"><span data-stu-id="6540f-184">To remove an existing entry, click</span></span> ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="6540f-186">bredvid posten.</span><span class="sxs-lookup"><span data-stu-id="6540f-186">next to the entry.</span></span>

     <span data-ttu-id="6540f-187">Information om [postsyntax finns i Postsyntax för listan "Ange inte om följande URL:er".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="6540f-187">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="6540f-188">Detaljerad information om dessa inställningar finns i inställningar [Valv för](safe-links.md#safe-links-settings-for-email-messages) e-postmeddelanden och inställningar Valv länkar [för Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="6540f-188">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="6540f-189">Fler rekommenderade värden för principinställningarna Standard och Strikt finns i Valv [principinställningar för Länkar.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="6540f-189">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="6540f-190">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="6540f-190">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6540f-191">På sidan **Meddelande** som visas väljer du något av följande värden för **Hur vill du meddela dina användare?**:</span><span class="sxs-lookup"><span data-stu-id="6540f-191">On the **Notification** page that appears, select one of the following values for **How would you like to notify your users?**:</span></span>
   - <span data-ttu-id="6540f-192">**Använda standardmeddelandetexten**</span><span class="sxs-lookup"><span data-stu-id="6540f-192">**Use the default notification text**</span></span>
   - <span data-ttu-id="6540f-193">**Använd anpassad meddelandetext:** Om du väljer det här värdet visas följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6540f-193">**Use custom notification text**: If you select this value, the following settings appear:</span></span>
     - <span data-ttu-id="6540f-194">**Använda Microsoft Translator för automatisk lokalisering**</span><span class="sxs-lookup"><span data-stu-id="6540f-194">**Use Microsoft Translator for automatic localization**</span></span>
     - <span data-ttu-id="6540f-195">**Anpassad meddelandetext:** Ange den anpassade aviseringstexten i den här rutan.</span><span class="sxs-lookup"><span data-stu-id="6540f-195">**Custom notification text**: Enter the custom notification text in this box.</span></span>

   <span data-ttu-id="6540f-196">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="6540f-196">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="6540f-197">Granska inställningarna på sidan **Granska** som visas.</span><span class="sxs-lookup"><span data-stu-id="6540f-197">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="6540f-198">Du kan välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet.</span><span class="sxs-lookup"><span data-stu-id="6540f-198">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="6540f-199">Eller så kan du klicka på **Föregående** eller välj den specifika sidan i guiden.</span><span class="sxs-lookup"><span data-stu-id="6540f-199">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="6540f-200">När du är klar klickar du på **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="6540f-200">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="6540f-201">På bekräftelsesidan som visas klickar du på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="6540f-201">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a><span data-ttu-id="6540f-202">Använda Defender Microsoft 365 portalen för att visa Valv principer för länkar</span><span class="sxs-lookup"><span data-stu-id="6540f-202">Use the Microsoft 365 Defender portal to view Safe Links policies</span></span>

1. <span data-ttu-id="6540f-203">I Microsoft 365 Defender-portalen går du till **Principer & Principer** för \> **hotprinciper** Valv \>  \> **Länkar.**</span><span class="sxs-lookup"><span data-stu-id="6540f-203">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="6540f-204">På **Valv Länkar** visas följande egenskaper i listan med länkar Valv principer:</span><span class="sxs-lookup"><span data-stu-id="6540f-204">On the **Safe Links** page, the following properties are displayed in the list of Safe Links policies:</span></span>
   - <span data-ttu-id="6540f-205">**Namn**</span><span class="sxs-lookup"><span data-stu-id="6540f-205">**Name**</span></span>
   - <span data-ttu-id="6540f-206">**Status**</span><span class="sxs-lookup"><span data-stu-id="6540f-206">**Status**</span></span>
   - <span data-ttu-id="6540f-207">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="6540f-207">**Priority**</span></span>

3. <span data-ttu-id="6540f-208">När du väljer en princip genom att klicka på namnet visas principinställningarna i en utfällbladstext.</span><span class="sxs-lookup"><span data-stu-id="6540f-208">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a><span data-ttu-id="6540f-209">Använda Defender Microsoft 365 portalen för att ändra Valv länkar</span><span class="sxs-lookup"><span data-stu-id="6540f-209">Use the Microsoft 365 Defender portal to modify Safe Links policies</span></span>

1. <span data-ttu-id="6540f-210">I Microsoft 365 Defender-portalen går du till **Principer & Principer** för \> **hotprinciper** Valv \>  \> **Länkar.**</span><span class="sxs-lookup"><span data-stu-id="6540f-210">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="6540f-211">På sidan **Valv väljer** du en princip i listan genom att klicka på namnet.</span><span class="sxs-lookup"><span data-stu-id="6540f-211">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="6540f-212">I den utfällda menyn för principinformationen kan du välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet.</span><span class="sxs-lookup"><span data-stu-id="6540f-212">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="6540f-213">Mer information om inställningarna finns i föregående använda [Defender-Microsoft 365 för](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) att skapa länkar Valv i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="6540f-213">For more information about the settings, see the previous [Use the Microsoft 365 Defender portal to create Safe Links policies](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) section in this article.</span></span>  

<span data-ttu-id="6540f-214">Läs följande avsnitt om du vill aktivera eller inaktivera en princip eller ange prioritetsordning för principen.</span><span class="sxs-lookup"><span data-stu-id="6540f-214">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="6540f-215">Aktivera eller inaktivera Valv länkar</span><span class="sxs-lookup"><span data-stu-id="6540f-215">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="6540f-216">I Defender Microsoft 365 portalen går du till avsnittet **Principer för &-&-e-post** och & Principer för hot \>  \>  \>  \> **Valv .**</span><span class="sxs-lookup"><span data-stu-id="6540f-216">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="6540f-217">På sidan **Valv väljer** du en princip i listan genom att klicka på namnet.</span><span class="sxs-lookup"><span data-stu-id="6540f-217">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="6540f-218">Högst upp i den utfällda menyn principinformation ser du något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="6540f-218">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="6540f-219">**Princip inaktiverad**: Om du vill aktivera principen klickar du på ![ikonen Aktivera](../../media/m365-cc-sc-turn-on-off-icon.png) **Aktivera** .</span><span class="sxs-lookup"><span data-stu-id="6540f-219">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="6540f-220">**Princip aktiverad**: Om du vill inaktivera principen klickar du på ![ikonen Inaktivera](../../media/m365-cc-sc-turn-on-off-icon.png) **Inaktivera**.</span><span class="sxs-lookup"><span data-stu-id="6540f-220">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="6540f-221">I bekräftelsedialogrutan som visas klickar du på **Aktivera** eller **Inaktivera**.</span><span class="sxs-lookup"><span data-stu-id="6540f-221">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="6540f-222">Klicka **Stäng** i den utfällda menyn principinformation.</span><span class="sxs-lookup"><span data-stu-id="6540f-222">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="6540f-223">Tillbaka på huvudsidan kommer värdet **Status** för principen att vara **På** eller **Av**.</span><span class="sxs-lookup"><span data-stu-id="6540f-223">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="6540f-224">Ange prioriteten för Valv-länkar</span><span class="sxs-lookup"><span data-stu-id="6540f-224">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="6540f-225">Som standard prioriteras Valv-länkar efter den ordning de skapades i (nyare principer har lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="6540f-225">By default, Safe Links are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="6540f-226">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="6540f-226">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="6540f-227">Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="6540f-227">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="6540f-228">Om du vill ändra prioriteten för en princip klickar du på **Öka prioritet** eller **Minska prioritet** i egenskaperna för principen (du kan inte direkt ändra numret för **Prioritet** i Microsoft 365 Defender-portalen).</span><span class="sxs-lookup"><span data-stu-id="6540f-228">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="6540f-229">Det är bara meningsfullt att ändra prioritet för en princip om du har flera principer.</span><span class="sxs-lookup"><span data-stu-id="6540f-229">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

<span data-ttu-id="6540f-230">**Obs!**</span><span class="sxs-lookup"><span data-stu-id="6540f-230">**Note**:</span></span>

- <span data-ttu-id="6540f-231">I Microsoft 365 Defender-portalen kan du bara ändra prioritet för Valv Länkar när du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="6540f-231">In the Microsoft 365 Defender portal, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="6540f-232">I PowerShell kan du åsidosätta standardprioritet när du skapar regeln om säkra länkar (vilket kan påverka prioriteringen för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="6540f-232">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="6540f-233">Valv Länkprinciper bearbetas i den ordning som de visas (den första principen har **prioritetsvärdet** 0).</span><span class="sxs-lookup"><span data-stu-id="6540f-233">Safe Links policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="6540f-234">För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="6540f-234">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

1. <span data-ttu-id="6540f-235">I Defender Microsoft 365 portalen går du till avsnittet **Principer för &-&-e-post** och & Principer för hot \>  \>  \>  \> **Valv .**</span><span class="sxs-lookup"><span data-stu-id="6540f-235">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="6540f-236">På sidan **Valv väljer** du en princip i listan genom att klicka på namnet.</span><span class="sxs-lookup"><span data-stu-id="6540f-236">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="6540f-237">Högst upp i den utfällda menyn principinformation som visas ser du **Öka prioritet** eller **Minska prioritet** baserat på det aktuella prioritetsvärdet och antalet anpassade principer:</span><span class="sxs-lookup"><span data-stu-id="6540f-237">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="6540f-238">Principen med **prioritetsvärdet** **0** har bara alternativet **Minska** prioritet tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="6540f-238">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="6540f-239">Principen med det lägsta **prioritetsvärdet** (till exempel **3)** har endast alternativet **Öka** prioritet tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="6540f-239">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="6540f-240">Om du har tre eller fler principer har principerna mellan de högsta och lägsta prioritetsvärdena både alternativen Öka **prioritet** **och Minska** prioritet tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="6540f-240">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="6540f-241">Klicka ![ikonen Öka prioritet](../../media/m365-cc-sc-increase-icon.png) **Öka prioritet** eller ![Ikonen Minska prioritet](../../media/m365-cc-sc-decrease-icon.png) **Minska prioritet** om du vill ändra värdet **Prioritet**.</span><span class="sxs-lookup"><span data-stu-id="6540f-241">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="6540f-242">Klicka **Stäng** i den utfällda menyn principinformation när du är klar.</span><span class="sxs-lookup"><span data-stu-id="6540f-242">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a><span data-ttu-id="6540f-243">Använda Defender-Microsoft 365 för att ta bort principer Valv Länkar</span><span class="sxs-lookup"><span data-stu-id="6540f-243">Use the Microsoft 365 Defender portal to remove Safe Links policies</span></span>

1. <span data-ttu-id="6540f-244">I Defender Microsoft 365 portalen går du till avsnittet **Principer för &-&-e-post** och & Principer för hot \>  \>  \>  \> **Valv .**</span><span class="sxs-lookup"><span data-stu-id="6540f-244">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="6540f-245">På sidan **Valv väljer** du en princip i listan genom att klicka på namnet.</span><span class="sxs-lookup"><span data-stu-id="6540f-245">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span> <span data-ttu-id="6540f-246">Längst upp i den utfällda menyn policyinformation som visas klickar du på ![ikonen Fler åtgärder](../../media/m365-cc-sc-more-actions-icon.png) **Fler åtgärder** \> ![ikonen Ta bort princip](../../media/m365-cc-sc-delete-icon.png) **Ta bort princip**.</span><span class="sxs-lookup"><span data-stu-id="6540f-246">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="6540f-247">I bekräftelsedialogrutan som visas klickar du på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="6540f-247">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="6540f-248">Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera Valv-länkar</span><span class="sxs-lookup"><span data-stu-id="6540f-248">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="6540f-249">Som tidigare beskrivits består en Valv-länkprincip av en princip för säkra länkar och en regel för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="6540f-249">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="6540f-250">I PowerShell visas skillnaden mellan principer för säkra länkar och regler för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="6540f-250">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="6540f-251">Du hanterar principer för säkra länkar med hjälp av cmdletarna **\* -SafeLinksPolicy** och hanterar regler för säkra länkar med hjälp av cmdletarna **\* -SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="6540f-251">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="6540f-252">I PowerShell skapar du först principen för säkra länkar och sedan skapar du den regel för säkra länkar som identifierar principen som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="6540f-252">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="6540f-253">I PowerShell ändrar du inställningarna i principen för säkra länkar och regeln om säkra länkar separat.</span><span class="sxs-lookup"><span data-stu-id="6540f-253">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="6540f-254">När du tar bort en princip för säkra länkar från PowerShell tas inte motsvarande regel för säkra länkar bort automatiskt och vice versa.</span><span class="sxs-lookup"><span data-stu-id="6540f-254">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="6540f-255">Använda PowerShell för att skapa Valv-länkar</span><span class="sxs-lookup"><span data-stu-id="6540f-255">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="6540f-256">Att skapa Valv princip för Länkar i PowerShell är en process i två steg:</span><span class="sxs-lookup"><span data-stu-id="6540f-256">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="6540f-257">Skapa principen för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="6540f-257">Create the safe links policy.</span></span>
2. <span data-ttu-id="6540f-258">Skapa den regel för säkra länkar som anger principen för säkra länkar som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="6540f-258">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="6540f-259">Du kan skapa en ny regel för säkra länkar och tilldela en befintlig princip för säkra länkar som inte har associerats till den.</span><span class="sxs-lookup"><span data-stu-id="6540f-259">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="6540f-260">En regel för säkra länkar kan inte associeras med mer än en princip för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="6540f-260">A safe links rule can't be associated with more than one safe links policy.</span></span>
>
> - <span data-ttu-id="6540f-261">Du kan konfigurera följande inställningar för nya principer för säkra länkar i PowerShell som inte är tillgängliga i Microsoft 365 Defender-portalen förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="6540f-261">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
>   - <span data-ttu-id="6540f-262">Skapa den nya principen som _inaktiverad (aktiverad_ `$false` på **cmdleten New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="6540f-262">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="6540f-263">Ange prioritet för principen vid skapandet _(Priority_ _\<Number\>_ ) på **New-SafeLinksRule-cmdleten).**</span><span class="sxs-lookup"><span data-stu-id="6540f-263">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
>
> - <span data-ttu-id="6540f-264">En ny princip för säkra länkar som du skapar i PowerShell visas inte i Microsoft 365 Defender-portalen förrän du tilldelar principen till en regel för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="6540f-264">A new safe links policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="6540f-265">Steg 1: Använda PowerShell för att skapa en princip för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="6540f-265">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="6540f-266">Använd följande syntax för att skapa en princip för säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="6540f-266">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
>
> - <span data-ttu-id="6540f-267">Mer information om postsyntaxen för parametern _DoNotRewriteUrls_ finns i Postsyntax för listan "Ange inte om följande URL:er". [](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="6540f-267">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
>
> - <span data-ttu-id="6540f-268">Ytterligare syntax som du kan använda för parametern _DoNotRewriteUrls_ när du ändrar befintliga principer för säkra länkar med hjälp av cmdleten **Set-SafeLinksPolicy** finns i avsnittet Använda [PowerShell](#use-powershell-to-modify-safe-links-policies) för att ändra principer för säkra länkar längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="6540f-268">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="6540f-269">I det här exemplet skapas en princip för säkra länkar med namnet Contoso Alla med följande värden:</span><span class="sxs-lookup"><span data-stu-id="6540f-269">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="6540f-270">Aktivera URL-skanning och skriva om den i e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="6540f-270">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="6540f-271">Aktivera URL-skanning i Teams (endast TAP Preview).</span><span class="sxs-lookup"><span data-stu-id="6540f-271">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="6540f-272">Aktivera genomsökning i realtid av klickade URL:er, inklusive klickade länkar som pekar på filer.</span><span class="sxs-lookup"><span data-stu-id="6540f-272">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="6540f-273">Vänta tills URL-skanningen är klar innan du levererar meddelandet.</span><span class="sxs-lookup"><span data-stu-id="6540f-273">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="6540f-274">Aktivera URL-genomsökning och skriva om interna meddelanden.</span><span class="sxs-lookup"><span data-stu-id="6540f-274">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="6540f-275">Spåra användarklick relaterade till Valv-länkskydd (vi använder inte parametern _DoNotTrackUserClicks_ och standardvärdet är $false vilket innebär att användarklickningar spåras).</span><span class="sxs-lookup"><span data-stu-id="6540f-275">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="6540f-276">Tillåt inte att användare klickar sig fram till den ursprungliga URL:en.</span><span class="sxs-lookup"><span data-stu-id="6540f-276">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="6540f-277">Detaljerad information om syntax och parametrar finns [i New-SafeLinksPolicy.](/powershell/module/exchange/new-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="6540f-277">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="6540f-278">Steg 2: Använda PowerShell för att skapa en regel för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="6540f-278">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="6540f-279">Använd följande syntax för att skapa en regel för säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="6540f-279">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="6540f-280">I det här exemplet skapas en regel för säkra länkar med namnet Contoso Alla med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="6540f-280">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="6540f-281">Regeln är kopplad till principen För säkra länkar med namnet Contoso Alla.</span><span class="sxs-lookup"><span data-stu-id="6540f-281">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="6540f-282">Regeln gäller för alla mottagare i contoso.com domän.</span><span class="sxs-lookup"><span data-stu-id="6540f-282">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="6540f-283">Eftersom vi inte använder _parametern Priority_ används standardprioritet.</span><span class="sxs-lookup"><span data-stu-id="6540f-283">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="6540f-284">Regeln är aktiverad (vi använder inte parametern _Enabled_ och standardvärdet är `$true` ).</span><span class="sxs-lookup"><span data-stu-id="6540f-284">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="6540f-285">Detaljerad information om syntax och parametrar finns [i New-SafeLinksRule.](/powershell/module/exchange/new-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="6540f-285">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="6540f-286">Använda PowerShell för att visa principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="6540f-286">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="6540f-287">Använd följande syntax för att visa befintliga principer för säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="6540f-287">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="6540f-288">Det här exemplet returnerar en sammanfattningslista över alla principer för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="6540f-288">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="6540f-289">Det här exemplet returnerar detaljerad information om principen för säkra länkar som heter Contoso-chefer.</span><span class="sxs-lookup"><span data-stu-id="6540f-289">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="6540f-290">Detaljerad information om syntax och parametrar finns i [Get-SafeLinksPolicy.](/powershell/module/exchange/get-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="6540f-290">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="6540f-291">Använda PowerShell för att visa regler för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="6540f-291">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="6540f-292">Om du vill visa befintliga regler för säkra länkar använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="6540f-292">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="6540f-293">Det här exemplet returnerar en sammanfattningslista över alla regler för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="6540f-293">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="6540f-294">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="6540f-294">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="6540f-295">Det här exemplet returnerar detaljerad information om regeln Contoso Executives som heter Säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="6540f-295">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="6540f-296">Detaljerad information om syntax och parametrar finns i [Get-SafeLinksRule.](/powershell/module/exchange/get-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="6540f-296">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="6540f-297">Använda PowerShell för att ändra principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="6540f-297">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="6540f-298">Du kan inte byta namn på en princip för säkra länkar i PowerShell **(Set-SafeLinksPolicy-cmdleten** har ingen _namnparameter)._</span><span class="sxs-lookup"><span data-stu-id="6540f-298">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="6540f-299">När du byter namn Valv princip för Microsoft 365 Defender-portalen byter du bara namn på regeln för säkra _länkar._</span><span class="sxs-lookup"><span data-stu-id="6540f-299">When you rename a Safe Links policy in the Microsoft 365 Defender portal, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="6540f-300">Den enda ytterligare faktorn för att ändra principer för säkra länkar i PowerShell är den tillgängliga syntaxen för parametern _DoNotRewriteUrls_ (listan ["Ange](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)inte om följande URL:er"):</span><span class="sxs-lookup"><span data-stu-id="6540f-300">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="6540f-301">Om du vill lägga till värden som ska ersätta befintliga poster använder du följande syntax: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="6540f-301">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="6540f-302">Om du vill lägga till eller ta bort värden utan att påverka andra befintliga poster använder du följande syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="6540f-302">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="6540f-303">Annars är samma inställningar tillgängliga när du skapar en princip för säkra länkar enligt beskrivningen i steg [1:](#step-1-use-powershell-to-create-a-safe-links-policy) Använda PowerShell för att skapa en princip för säkra länkar längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="6540f-303">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="6540f-304">Använd följande syntax för att ändra en princip för säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="6540f-304">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="6540f-305">Detaljerad information om syntax och parametrar finns i [Set-SafeLinksPolicy.](/powershell/module/exchange/set-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="6540f-305">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="6540f-306">Använda PowerShell för att ändra regler för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="6540f-306">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="6540f-307">Den enda inställning som inte är tillgänglig när du ändrar en regel för säkra länkar i PowerShell är parametern _Enabled_ som gör att du kan skapa en inaktiverad regel.</span><span class="sxs-lookup"><span data-stu-id="6540f-307">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="6540f-308">Nästa avsnitt innehåller information om hur du aktiverar eller inaktiverar befintliga regler för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="6540f-308">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="6540f-309">Annars är samma inställningar tillgängliga när du skapar en regel som beskrivs i steg [2:](#step-2-use-powershell-to-create-a-safe-links-rule) Använd PowerShell för att skapa en regel för säkra länkar längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="6540f-309">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="6540f-310">Använd följande syntax för att ändra en regel för säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="6540f-310">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="6540f-311">Detaljerad information om syntax och parametrar finns [i Set-SafeLinksRule.](/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="6540f-311">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="6540f-312">Använda PowerShell för att aktivera eller inaktivera regler för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="6540f-312">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="6540f-313">Om du aktiverar eller inaktiverar en regel för säkra länkar i PowerShell aktiveras eller inaktiveras hela Valv Links-principen (regeln för säkra länkar och den tilldelade principen för säkra länkar).</span><span class="sxs-lookup"><span data-stu-id="6540f-313">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="6540f-314">Om du vill aktivera eller inaktivera en regel för säkra länkar i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="6540f-314">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="6540f-315">I det här exemplet inaktiveras regeln För säkra länkar med namnet Marknadsföringsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="6540f-315">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="6540f-316">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="6540f-316">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="6540f-317">Detaljerad information om syntax och parametrar finns i [Enable-SafeLinksRule och](/powershell/module/exchange/enable-safelinksrule) [Disable-SafeLinksRule.](/powershell/module/exchange/disable-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="6540f-317">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="6540f-318">Använda PowerShell för att ange prioritet för regler för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="6540f-318">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="6540f-319">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="6540f-319">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="6540f-320">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="6540f-320">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="6540f-321">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="6540f-321">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="6540f-322">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="6540f-322">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="6540f-323">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="6540f-323">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="6540f-324">Ange prioritet för en regel för säkra länkar i PowerShell med följande syntax:</span><span class="sxs-lookup"><span data-stu-id="6540f-324">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="6540f-325">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="6540f-325">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="6540f-326">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="6540f-326">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="6540f-327">Om du vill ange prioriteten för en ny regel när du skapar den använder du parametern _Priority_ i cmdleten **New-SafeLinksRule** i stället.</span><span class="sxs-lookup"><span data-stu-id="6540f-327">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="6540f-328">Detaljerad information om syntax och parametrar finns [i Set-SafeLinksRule.](/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="6540f-328">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="6540f-329">Använda PowerShell för att ta bort principer för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="6540f-329">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="6540f-330">När du använder PowerShell för att ta bort en princip för säkra länkar tas motsvarande regel för säkra länkar inte bort.</span><span class="sxs-lookup"><span data-stu-id="6540f-330">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="6540f-331">Använd följande syntax för att ta bort en princip för säkra länkar i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6540f-331">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="6540f-332">Det här exemplet tar bort principen för säkra länkar med namnet Marknadsföringsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="6540f-332">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="6540f-333">Detaljerad information om syntax och parametrar finns i [Remove-SafeLinksPolicy.](/powershell/module/exchange/remove-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="6540f-333">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="6540f-334">Använda PowerShell för att ta bort regler för säkra länkar</span><span class="sxs-lookup"><span data-stu-id="6540f-334">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="6540f-335">När du använder PowerShell för att ta bort en regel för säkra länkar tas motsvarande princip för säkra länkar inte bort.</span><span class="sxs-lookup"><span data-stu-id="6540f-335">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="6540f-336">Använd följande syntax för att ta bort en regel för säkra länkar i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6540f-336">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="6540f-337">Det här exemplet tar bort regeln om säkra länkar med namnet Marknadsföringsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="6540f-337">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="6540f-338">Detaljerad information om syntax och parametrar finns i [Remove-SafeLinksRule.](/powershell/module/exchange/remove-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="6540f-338">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="6540f-339">Kontrollera att Valv söker igenom meddelanden genom att titta i tillgängliga Microsoft Defender Office 365.</span><span class="sxs-lookup"><span data-stu-id="6540f-339">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="6540f-340">Mer information finns i [Visa rapporter för Defender för Office 365](view-reports-for-mdo.md) och Använda [Utforskaren i Microsoft 365 Defender-portalen.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="6540f-340">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="6540f-341">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="6540f-341">How do you know these procedures worked?</span></span>

<span data-ttu-id="6540f-342">Kontrollera att du har skapat, ändrat eller tagit bort principer Valv länkar genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="6540f-342">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="6540f-343">I Defender Microsoft 365 portalen går du till **Principer för & principer** för hot \> **Valv** \> **.**</span><span class="sxs-lookup"><span data-stu-id="6540f-343">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Safe Links**.</span></span> <span data-ttu-id="6540f-344">Kontrollera listan med principer, deras **statusvärden** och deras **prioritetsvärden.**</span><span class="sxs-lookup"><span data-stu-id="6540f-344">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="6540f-345">Om du vill visa mer information väljer du principen i listan och visar informationen i den utfäll plats du vill ha.</span><span class="sxs-lookup"><span data-stu-id="6540f-345">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="6540f-346">I Exchange Online PowerShell eller Exchange Online Protection PowerShell ersätter du med namnet på principen eller regeln, kör följande kommando och \<Name\> kontrollerar inställningarna:</span><span class="sxs-lookup"><span data-stu-id="6540f-346">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
