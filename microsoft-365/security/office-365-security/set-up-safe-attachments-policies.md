---
title: Konfigurera principer Valv för bifogade filer i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Lär dig mer om hur du Valv principer för bifogade filer för att skydda organisationen från skadliga filer i e-post.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e7220140c25ecf457b42514356e41aabdf5481bb
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054326"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="7dbca-103">Konfigurera principer Valv för bifogade filer i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="7dbca-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7dbca-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="7dbca-104">**Applies to**</span></span>
- [<span data-ttu-id="7dbca-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="7dbca-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7dbca-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7dbca-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="7dbca-107">Den här artikeln är avsedd för företagskunder som har [Microsoft Defender för Office 365](whats-new-in-defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="7dbca-107">This article is intended for business customers who have [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md).</span></span> <span data-ttu-id="7dbca-108">Om du är hemanvändare och vill ha information om skanning av bifogade filer i Outlook, se [Avancerad Outlook.com-säkerhet.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="7dbca-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="7dbca-109">Valv Bifogade filer är en funktion i [Microsoft Defender](whats-new-in-defender-for-office-365.md) för Office 365 som använder en virtuell miljö för att kontrollera bifogade filer i inkommande e-postmeddelanden efter att de har genomsökts av skydd mot skadlig programvara i [Exchange Online Protection (EOP),](anti-malware-protection.md)men före leverans till mottagarna.</span><span class="sxs-lookup"><span data-stu-id="7dbca-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="7dbca-110">Mer information finns i Valv [i Microsoft Defender för Office 365](safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="7dbca-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](safe-attachments.md).</span></span>

<span data-ttu-id="7dbca-111">Det finns ingen inbyggd eller standardprincip för Valv för bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="7dbca-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="7dbca-112">Om du Valv att söka igenom bifogade filer i e-postmeddelanden, måste du skapa en eller Valv principer för bifogade filer enligt beskrivningen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="7dbca-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="7dbca-113">Du kan konfigurera principer för Valv-bilagor i Microsoft 365 Defender-portalen eller i PowerShell (Exchange Online PowerShell för kvalificerade Microsoft 365-organisationer med postlådor i Exchange Online– fristående EOP PowerShell för organisationer utan Exchange Online-postlådor, men med Defender för Office 365-tilläggsprenumerationer).</span><span class="sxs-lookup"><span data-stu-id="7dbca-113">You can configure Safe Attachments policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="7dbca-114">De grundläggande elementen i en princip Valv bifogade filer är:</span><span class="sxs-lookup"><span data-stu-id="7dbca-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="7dbca-115">**Principen för** säkra bifogade filer: Anger åtgärder för okänd identifiering av skadlig programvara, om du vill skicka meddelanden med bifogade filer från skadlig programvara till en viss e-postadress och om det inte går att skicka meddelanden om Valv genomsökning av bifogade filer inte kan slutföras.</span><span class="sxs-lookup"><span data-stu-id="7dbca-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="7dbca-116">**Regeln för säkra bifogade** filer: Anger prioritet och mottagarfilter (vem principen gäller för).</span><span class="sxs-lookup"><span data-stu-id="7dbca-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="7dbca-117">Skillnaden mellan dessa två element är inte uppenbara när du hanterar principer Valv bilagor i Microsoft 365 Defender portalen:</span><span class="sxs-lookup"><span data-stu-id="7dbca-117">The difference between these two elements isn't obvious when you manage Safe Attachments policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="7dbca-118">När du skapar Valv princip för bifogade filer skapar du egentligen en regel för säkra bifogade filer och den associerade principen för säkra bifogade filer samtidigt, med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="7dbca-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="7dbca-119">När du ändrar Valv en princip för bifogade filer ändras regeln för säker bifogad fil med inställningar för namn, prioritet, aktiverad eller inaktiverad, och mottagarfilter.</span><span class="sxs-lookup"><span data-stu-id="7dbca-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="7dbca-120">Alla andra inställningar ändrar den associerade principen för säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="7dbca-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="7dbca-121">När du tar bort Valv princip för bifogade filer tas regeln för säkra bifogade filer och den tillhörande principen för säkra bifogade filer bort.</span><span class="sxs-lookup"><span data-stu-id="7dbca-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="7dbca-122">I Exchange Online PowerShell eller fristående EOP PowerShell hanterar du policyn och regeln separat.</span><span class="sxs-lookup"><span data-stu-id="7dbca-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="7dbca-123">Mer information finns i avsnittet Använda Exchange Online PowerShell eller [fristående EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) för att konfigurera Valv principer för bifogade filer längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="7dbca-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="7dbca-124">I det globala inställningsområdet i Valv för bifogade filer konfigurerar du funktioner som inte är beroende Valv principer för bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="7dbca-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="7dbca-125">Anvisningar finns i [Aktivera Valv för bifogade filer SharePoint, OneDrive,](turn-on-mdo-for-spo-odb-and-teams.md) Microsoft Teams och [Valv dokument i Microsoft 365 E5](safe-docs.md).</span><span class="sxs-lookup"><span data-stu-id="7dbca-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7dbca-126">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="7dbca-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7dbca-127">Du kan öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="7dbca-127">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="7dbca-128">Om du vill gå direkt **Valv bifogade filer** använder du <https://security.microsoft.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="7dbca-128">To go directly to the **Safe Attachments** page, use <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="7dbca-129">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="7dbca-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="7dbca-130">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="7dbca-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="7dbca-131">Du behöver behörighet innan du kan göra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="7dbca-131">You need permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="7dbca-132">Om du vill skapa, ändra och ta bort Valv-principer för  bifogade  filer måste du vara medlem i rollgrupperna Organisationshantering eller Säkerhetsadministratör i Microsoft 365 Defender-portalen  och medlem i rollgruppen Organisationshantering i Exchange Online. </span><span class="sxs-lookup"><span data-stu-id="7dbca-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="7dbca-133">För skrivskyddade åtkomst Valv principer för bifogade filer måste du vara  medlem i rollgrupperna **Global Reader** eller Säkerhetsläsare i Microsoft 365 Defender portalen.</span><span class="sxs-lookup"><span data-stu-id="7dbca-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Microsoft 365 Defender portal.</span></span>

  <span data-ttu-id="7dbca-134">Mer information finns i [Behörigheter i Microsoft 365 Defender och](permissions-microsoft-365-security-center.md) Behörigheter i [Exchange Online.](/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="7dbca-134">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="7dbca-135">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="7dbca-135">**Notes**:</span></span>

  - <span data-ttu-id="7dbca-136">Om du lägger till användare i Azure Active Directory-rollen i Administrationscenter för Microsoft 365 får användarna de  behörigheter som krävs i Microsoft 365 Defender-portalen och behörigheter för andra funktioner Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7dbca-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="7dbca-137">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="7dbca-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="7dbca-138">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="7dbca-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="7dbca-139">Vi rekommenderar inställningar för att Valv principer för bifogade filer i Valv [Inställningar för bifogade filer.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="7dbca-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="7dbca-140">Det kan ta upp till 30 minuter innan en ny eller uppdaterad princip tillämpas.</span><span class="sxs-lookup"><span data-stu-id="7dbca-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a><span data-ttu-id="7dbca-141">Använda Microsoft 365 Defender för att skapa principer för Valv och bilagor</span><span class="sxs-lookup"><span data-stu-id="7dbca-141">Use the Microsoft 365 Defender portal to create Safe Attachments policies</span></span>

<span data-ttu-id="7dbca-142">När du skapar Valv egen princip för bifogade filer i Microsoft 365 Defender-portalen skapas en regel för säker bifogad fil och tillhörande princip för säkra bifogade filer samtidigt med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="7dbca-142">Creating a custom Safe Attachments policy in the Microsoft 365 Defender portal creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="7dbca-143">I portalen Microsoft 365 Defender du till Principer för **&-& e-&** principer för hotprinciper \>  \>  \>  Valv \> **bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="7dbca-143">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="7dbca-144">På sidan **Valv klickar** du på Skapa ![ ikon ](../../media/m365-cc-sc-create-icon.png) **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="7dbca-144">On the **Safe Attachments** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="7dbca-145">Principguiden öppnas.</span><span class="sxs-lookup"><span data-stu-id="7dbca-145">The policy wizard opens.</span></span> <span data-ttu-id="7dbca-146">Konfigurera **följande inställningar på** sidan Namnge principen:</span><span class="sxs-lookup"><span data-stu-id="7dbca-146">On the **Name your policy** page, configure the following settings:</span></span>
   - <span data-ttu-id="7dbca-147">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="7dbca-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="7dbca-148">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="7dbca-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="7dbca-149">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="7dbca-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="7dbca-150">På sidan **Användare och domäner** som visas identifierar du de interna mottagare som principen gäller för (mottagarvillkor):</span><span class="sxs-lookup"><span data-stu-id="7dbca-150">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="7dbca-151">**Användare**: De angivna postlådorna, e-postanvändarna eller e-postkontakterna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="7dbca-151">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="7dbca-152">**Grupper**: De angivna distributionsgrupper, e-postaktiverade säkerhetsgrupper eller Microsoft 365-grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="7dbca-152">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="7dbca-153">**Domäner**: Alla mottagare i den angivna [godkända domänen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) i organisationen.</span><span class="sxs-lookup"><span data-stu-id="7dbca-153">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="7dbca-154">Klicka i lämplig ruta, börja skriva in ett värde och välj det värde du vill använda i resultatet.</span><span class="sxs-lookup"><span data-stu-id="7dbca-154">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="7dbca-155">Upprepa det här steget så många gånger som det behövs.</span><span class="sxs-lookup"><span data-stu-id="7dbca-155">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="7dbca-156">Om du vill ta bort ett befintligt värde klickar du Ta bort</span><span class="sxs-lookup"><span data-stu-id="7dbca-156">To remove an existing value, click remove</span></span> ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="7dbca-158">bredvid värdet.</span><span class="sxs-lookup"><span data-stu-id="7dbca-158">next to the value.</span></span>

   <span data-ttu-id="7dbca-159">För användare eller grupper kan du använda de flesta identifierare (namn, visningsnamn, alias, e-postadress, kontonamn osv.), men motsvarande visningsnamn visas i resultatet.</span><span class="sxs-lookup"><span data-stu-id="7dbca-159">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="7dbca-160">Om du vill visa alla tillgängliga värden för användare anger du en asterisk (\*) för sig själv.</span><span class="sxs-lookup"><span data-stu-id="7dbca-160">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="7dbca-161">Använd ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_) för flera värden i samma villkor.</span><span class="sxs-lookup"><span data-stu-id="7dbca-161">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="7dbca-162">Använd OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_) för olika villkor.</span><span class="sxs-lookup"><span data-stu-id="7dbca-162">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="7dbca-163">**Exkludera dessa användare, grupper och domäner**: Om du vill lägga till undantag för interna mottagare som principen gäller för (Mottagarundantag), väljer du det här alternativet och konfigurerar undantagen.</span><span class="sxs-lookup"><span data-stu-id="7dbca-163">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="7dbca-164">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="7dbca-164">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="7dbca-165">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="7dbca-165">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="7dbca-166">På **Inställningar** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="7dbca-166">On the **Settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="7dbca-167">**Valv bifogade filer som är okänt svar från** skadlig programvara: Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="7dbca-167">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>
     - <span data-ttu-id="7dbca-168">**Av:** Normalt rekommenderar vi inte det här värdet.</span><span class="sxs-lookup"><span data-stu-id="7dbca-168">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="7dbca-169">**Övervaka**</span><span class="sxs-lookup"><span data-stu-id="7dbca-169">**Monitor**</span></span>
     - <span data-ttu-id="7dbca-170">**Block:** Det här är standardvärdet och det rekommenderade värdet i standard- och strikt [förinställda säkerhetsprinciper.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="7dbca-170">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="7dbca-171">**Ersätt**</span><span class="sxs-lookup"><span data-stu-id="7dbca-171">**Replace**</span></span>
     - <span data-ttu-id="7dbca-172">**Dynamisk leverans (förhandsgranskningsfunktion)**</span><span class="sxs-lookup"><span data-stu-id="7dbca-172">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="7dbca-173">Dessa värden förklaras i Valv [för bifogade filer.](safe-attachments.md#safe-attachments-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="7dbca-173">These values are explained in [Safe Attachments policy settings](safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="7dbca-174">**Omdirigera** meddelanden med identifierade bifogade filer: Om du väljer Aktivera omdirigering kan du ange en e-postadress i rutan Skicka meddelanden som innehåller **blockerade,** övervakade eller ersatta bifogade filer i den angivna e-postadressrutan för att skicka meddelanden som innehåller bifogade filer som innehåller skadlig programvara för analys och undersökning.</span><span class="sxs-lookup"><span data-stu-id="7dbca-174">**Redirect messages with detected attachments**: If you select **Enable redirect**, you can specify an email address in the **Send messages that contain blocked, monitored, or replaced attachments to the specified email address** box to send messages that contain malware attachments for analysis and investigation.</span></span>

     <span data-ttu-id="7dbca-175">Rekommendationen för standard- och strikt-principinställningarna är att aktivera omdirigering.</span><span class="sxs-lookup"><span data-stu-id="7dbca-175">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="7dbca-176">Mer information finns i Valv [Inställningar för bifogade filer](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span><span class="sxs-lookup"><span data-stu-id="7dbca-176">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="7dbca-177">Använd svaret för identifiering av **bifogade filer** i Valv om genomsökningen inte kan **slutföras (timeout** eller fel): Åtgärden som anges av Valv Okänd respons på skadlig programvara tillämpas på meddelanden även om Valv Genomsökning av bifogade filer inte kan slutföras.</span><span class="sxs-lookup"><span data-stu-id="7dbca-177">**Apply the Safe Attachments detection response if scanning can't complete (timeout or errors)**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="7dbca-178">Om du valde det här alternativet ska du alltid välja **Aktivera omdirigering och** ange en e-postadress för att skicka meddelanden som innehåller bifogade filer som är bifogade till skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="7dbca-178">If you selected this option, always select **Enable redirect** and specify an email address to send messages that contain malware attachments.</span></span> <span data-ttu-id="7dbca-179">Annars kan meddelanden gå förlorade.</span><span class="sxs-lookup"><span data-stu-id="7dbca-179">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="7dbca-180">Klicka på **Nästa** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="7dbca-180">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="7dbca-181">Granska inställningarna på sidan **Granska** som visas.</span><span class="sxs-lookup"><span data-stu-id="7dbca-181">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="7dbca-182">Du kan välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet.</span><span class="sxs-lookup"><span data-stu-id="7dbca-182">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="7dbca-183">Eller så kan du klicka på **Föregående** eller välj den specifika sidan i guiden.</span><span class="sxs-lookup"><span data-stu-id="7dbca-183">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="7dbca-184">När du är klar klickar du på **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="7dbca-184">When you're finished, click **Submit**.</span></span>

7. <span data-ttu-id="7dbca-185">På bekräftelsesidan som visas klickar du på **Klar**.</span><span class="sxs-lookup"><span data-stu-id="7dbca-185">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a><span data-ttu-id="7dbca-186">Använda Microsoft 365 Defender för att visa principer Valv bifogade filer</span><span class="sxs-lookup"><span data-stu-id="7dbca-186">Use the Microsoft 365 Defender portal to view Safe Attachments policies</span></span>

1. <span data-ttu-id="7dbca-187">I portalen Microsoft 365 Defender du till Principer för **&-& e-&** principer för hotprinciper \>  \>  \>  Valv \> **bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="7dbca-187">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="7dbca-188">På **Valv bifogade** filer visas följande egenskaper i listan med principer:</span><span class="sxs-lookup"><span data-stu-id="7dbca-188">On the **Safe Attachments** page, the following properties are displayed in the list of policies:</span></span>
   - <span data-ttu-id="7dbca-189">**Namn**</span><span class="sxs-lookup"><span data-stu-id="7dbca-189">**Name**</span></span>
   - <span data-ttu-id="7dbca-190">**Status**</span><span class="sxs-lookup"><span data-stu-id="7dbca-190">**Status**</span></span>
   - <span data-ttu-id="7dbca-191">**Prioritet**</span><span class="sxs-lookup"><span data-stu-id="7dbca-191">**Priority**</span></span>

3. <span data-ttu-id="7dbca-192">När du väljer en princip genom att klicka på namnet visas principinställningarna i en utfällbladstext.</span><span class="sxs-lookup"><span data-stu-id="7dbca-192">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a><span data-ttu-id="7dbca-193">Använda Microsoft 365 Defender för att ändra principer för Valv och bilagor</span><span class="sxs-lookup"><span data-stu-id="7dbca-193">Use the Microsoft 365 Defender portal to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="7dbca-194">I portalen Microsoft 365 Defender du till Principer för **&-& e-&** principer för hotprinciper \>  \>  \>  Valv \> **bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="7dbca-194">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="7dbca-195">På sidan **Valv bifogade** filer väljer du en princip i listan genom att klicka på namnet.</span><span class="sxs-lookup"><span data-stu-id="7dbca-195">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="7dbca-196">I den utfällda menyn för principinformationen kan du välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet.</span><span class="sxs-lookup"><span data-stu-id="7dbca-196">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="7dbca-197">Mer information om inställningarna finns i avsnittet Använda Microsoft 365 Defender [för](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) att skapa Valv principer för bifogade filer längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="7dbca-197">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create Safe Attachments policies](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) section earlier in this article.</span></span>  

<span data-ttu-id="7dbca-198">Läs följande avsnitt om du vill aktivera eller inaktivera en princip eller ange prioritetsordning för principen.</span><span class="sxs-lookup"><span data-stu-id="7dbca-198">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="7dbca-199">Aktivera eller inaktivera principer Valv för bifogade filer</span><span class="sxs-lookup"><span data-stu-id="7dbca-199">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="7dbca-200">I portalen Microsoft 365 Defender du till Principer för **&-& e-&** principer för hotprinciper \>  \>  \>  Valv \> **bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="7dbca-200">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="7dbca-201">På sidan **Valv bifogade** filer väljer du en princip i listan genom att klicka på namnet.</span><span class="sxs-lookup"><span data-stu-id="7dbca-201">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="7dbca-202">Högst upp i den utfällda menyn principinformation ser du något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="7dbca-202">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="7dbca-203">**Princip inaktiverad**: Om du vill aktivera principen klickar du på ![ikonen Aktivera](../../media/m365-cc-sc-turn-on-off-icon.png) **Aktivera** .</span><span class="sxs-lookup"><span data-stu-id="7dbca-203">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="7dbca-204">**Princip aktiverad**: Om du vill inaktivera principen klickar du på ![ikonen Inaktivera](../../media/m365-cc-sc-turn-on-off-icon.png) **Inaktivera**.</span><span class="sxs-lookup"><span data-stu-id="7dbca-204">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="7dbca-205">I bekräftelsedialogrutan som visas klickar du på **Aktivera** eller **Inaktivera**.</span><span class="sxs-lookup"><span data-stu-id="7dbca-205">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="7dbca-206">Klicka **Stäng** i den utfällda menyn principinformation.</span><span class="sxs-lookup"><span data-stu-id="7dbca-206">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="7dbca-207">Tillbaka på huvudsidan kommer värdet **Status** för principen att vara **På** eller **Av**.</span><span class="sxs-lookup"><span data-stu-id="7dbca-207">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="7dbca-208">Ange prioriteten för principer Valv för bifogade filer</span><span class="sxs-lookup"><span data-stu-id="7dbca-208">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="7dbca-209">Som standard har Valv för bifogade filer en prioritet som baseras på i vilken ordning de skapades (nyare principer har lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="7dbca-209">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="7dbca-210">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="7dbca-210">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="7dbca-211">Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="7dbca-211">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="7dbca-212">För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="7dbca-212">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="7dbca-213">Valv Principer för bifogade filer visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0).</span><span class="sxs-lookup"><span data-stu-id="7dbca-213">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="7dbca-214">**Obs!** I Microsoft 365 Defender kan du bara ändra prioritet för Valv för bifogade filer när du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="7dbca-214">**Note**: In the Microsoft 365 Defender portal, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="7dbca-215">I PowerShell kan du åsidosätta standardprioritet när du skapar regeln om säkra bifogade filer (vilket kan påverka prioriteringen för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="7dbca-215">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="7dbca-216">Om du vill ändra prioriteten för en princip klickar du på **Öka prioritet** eller **Minska prioritet** i egenskaperna för principen (du kan inte direkt ändra numret för **Prioritet** i Microsoft 365 Defender-portalen).</span><span class="sxs-lookup"><span data-stu-id="7dbca-216">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="7dbca-217">Det är bara meningsfullt att ändra prioritet för en princip om du har flera principer.</span><span class="sxs-lookup"><span data-stu-id="7dbca-217">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="7dbca-218">I portalen Microsoft 365 Defender du till Principer för **&-& e-&** principer för hotprinciper \>  \>  \>  Valv \> **bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="7dbca-218">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="7dbca-219">På sidan **Valv bifogade** filer väljer du en princip i listan genom att klicka på namnet.</span><span class="sxs-lookup"><span data-stu-id="7dbca-219">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="7dbca-220">Högst upp i den utfällliga policyinformationen  som visas  visas Öka prioritet eller Minska prioritet baserat på det aktuella prioritetsvärdet och antalet principer:</span><span class="sxs-lookup"><span data-stu-id="7dbca-220">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of policies:</span></span>
   - <span data-ttu-id="7dbca-221">Principen med **prioritetsvärdet** **0** har bara alternativet **Minska** prioritet tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="7dbca-221">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="7dbca-222">Principen med det lägsta **prioritetsvärdet** (till exempel **3)** har endast alternativet **Öka** prioritet tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="7dbca-222">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="7dbca-223">Om du har tre eller fler principer har principerna mellan de högsta och lägsta prioritetsvärdena både alternativen Öka **prioritet** **och Minska** prioritet tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="7dbca-223">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="7dbca-224">Klicka ![ikonen Öka prioritet](../../media/m365-cc-sc-increase-icon.png) **Öka prioritet** eller ![Ikonen Minska prioritet](../../media/m365-cc-sc-decrease-icon.png) **Minska prioritet** om du vill ändra värdet **Prioritet**.</span><span class="sxs-lookup"><span data-stu-id="7dbca-224">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="7dbca-225">Klicka **Stäng** i den utfällda menyn principinformation när du är klar.</span><span class="sxs-lookup"><span data-stu-id="7dbca-225">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a><span data-ttu-id="7dbca-226">Använda Microsoft 365 Defender för att ta bort principer för Valv och bilagor</span><span class="sxs-lookup"><span data-stu-id="7dbca-226">Use the Microsoft 365 Defender portal to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="7dbca-227">I portalen Microsoft 365 Defender du till Principer för **&-& e-&** principer för hotprinciper \>  \>  \>  Valv \> **bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="7dbca-227">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="7dbca-228">På sidan **Valv bifogade** filer väljer du en anpassad princip i listan genom att klicka på namnet på principen.</span><span class="sxs-lookup"><span data-stu-id="7dbca-228">On the **Safe Attachments** page, select a custom policy from the list by clicking on the name of the policy.</span></span>

3. <span data-ttu-id="7dbca-229">Längst upp i den utfällda menyn policyinformation som visas klickar du på ![ikonen Fler åtgärder](../../media/m365-cc-sc-more-actions-icon.png) **Fler åtgärder** \> ![ikonen Ta bort princip](../../media/m365-cc-sc-delete-icon.png) **Ta bort princip**.</span><span class="sxs-lookup"><span data-stu-id="7dbca-229">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="7dbca-230">I bekräftelsedialogrutan som visas klickar du på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="7dbca-230">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="7dbca-231">Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer Valv för bifogade filer</span><span class="sxs-lookup"><span data-stu-id="7dbca-231">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="7dbca-232">Som tidigare beskrivits består en princip Valv bifogade filer av en princip för säker bifogad fil och en regel för säker bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="7dbca-232">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="7dbca-233">I PowerShell syns skillnaden mellan principer för säkra bifogade filer och regler för säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="7dbca-233">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="7dbca-234">Du hanterar principer för säkra bifogade filer med cmdletarna **\* -SafeAttachmentPolicy** och hanterar regler för säkra bifogade filer med cmdlets **\* -SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="7dbca-234">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="7dbca-235">I PowerShell skapar du först principen för säkra bifogade filer. Sedan skapar du den regel för säkra bifogade filer som identifierar principen som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="7dbca-235">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="7dbca-236">I PowerShell ändrar du inställningarna i principen för säkra bifogade filer och regeln om säker bifogad fil separat.</span><span class="sxs-lookup"><span data-stu-id="7dbca-236">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="7dbca-237">När du tar bort en princip för säkra bifogade filer från PowerShell tas motsvarande regel för säkra bifogade filer inte bort automatiskt, och vice versa.</span><span class="sxs-lookup"><span data-stu-id="7dbca-237">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="7dbca-238">Använda PowerShell för att skapa Valv principer för bifogade filer</span><span class="sxs-lookup"><span data-stu-id="7dbca-238">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="7dbca-239">Att skapa Valv en princip för bifogade filer i PowerShell är en process i två steg:</span><span class="sxs-lookup"><span data-stu-id="7dbca-239">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="7dbca-240">Skapa principen för säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="7dbca-240">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="7dbca-241">Skapa den regel för säkra bifogade filer som anger principen för säkra bifogade filer som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="7dbca-241">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="7dbca-242">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="7dbca-242">**Notes**:</span></span>

- <span data-ttu-id="7dbca-243">Du kan skapa en ny regel för säkra bifogade filer och tilldela en befintlig princip för säkra bifogade filer som inte har associerats till den.</span><span class="sxs-lookup"><span data-stu-id="7dbca-243">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="7dbca-244">En regel för säkra bifogade filer kan inte associeras med mer än en princip för säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="7dbca-244">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="7dbca-245">Du kan konfigurera följande inställningar för nya principer för säkra bifogade filer i PowerShell som inte är tillgängliga i Microsoft 365 Defender-portalen förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="7dbca-245">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id="7dbca-246">Skapa den nya principen som _inaktiverad (aktiverad_ `$false` på **cmdleten New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="7dbca-246">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="7dbca-247">Ange prioritet för principen vid skapande (_Prioritet_ _\<Number\>_ ) på **cmdleten New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="7dbca-247">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="7dbca-248">En ny princip för säkra bifogade filer som du skapar i PowerShell visas inte i Microsoft 365 Defender-portalen förrän du tilldelar principen till en regel för säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="7dbca-248">A new safe attachment policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="7dbca-249">Steg 1: Använda PowerShell för att skapa en princip för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="7dbca-249">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="7dbca-250">Använd följande syntax för att skapa en princip för säkra bifogade filer:</span><span class="sxs-lookup"><span data-stu-id="7dbca-250">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="7dbca-251">I det här exemplet skapas en princip för säkra bifogade filer med namnet Contoso Alla med följande värden:</span><span class="sxs-lookup"><span data-stu-id="7dbca-251">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="7dbca-252">Blockera meddelanden som innehåller skadlig programvara genom Valv dokumentskanning (vi använder inte parametern _Action_ och standardvärdet är `Block` ).</span><span class="sxs-lookup"><span data-stu-id="7dbca-252">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="7dbca-253">Omdirigering är aktiverat och meddelanden som innehåller skadlig programvara skickas till sec-ops@contoso.com för analys och undersökning.</span><span class="sxs-lookup"><span data-stu-id="7dbca-253">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="7dbca-254">Om Valv bifogade filer inte är tillgängligt eller stöter på fel, leverera inte meddelandet (vi använder inte parametern _ActionOnError_ och standardvärdet är `$true` ).</span><span class="sxs-lookup"><span data-stu-id="7dbca-254">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="7dbca-255">Detaljerad information om syntax och parametrar finns i [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="7dbca-255">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="7dbca-256">Steg 2: Använda PowerShell för att skapa en regel för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="7dbca-256">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="7dbca-257">Använd följande syntax för att skapa en regel för säkra bifogade filer:</span><span class="sxs-lookup"><span data-stu-id="7dbca-257">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="7dbca-258">I det här exemplet skapas en regel för säkra bifogade filer med namnet Contoso Alla med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="7dbca-258">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="7dbca-259">Regeln är kopplad till principen för säkra bifogade filer med namnet Contoso All.</span><span class="sxs-lookup"><span data-stu-id="7dbca-259">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="7dbca-260">Regeln gäller för alla mottagare i contoso.com domän.</span><span class="sxs-lookup"><span data-stu-id="7dbca-260">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="7dbca-261">Eftersom vi inte använder _parametern Priority_ används standardprioritet.</span><span class="sxs-lookup"><span data-stu-id="7dbca-261">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="7dbca-262">Regeln är aktiverad (vi använder inte parametern _Enabled_ och standardvärdet är `$true` ).</span><span class="sxs-lookup"><span data-stu-id="7dbca-262">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="7dbca-263">Detaljerad information om syntax och parametrar finns [i New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="7dbca-263">For detailed syntax and parameter information, see [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="7dbca-264">Använda PowerShell för att visa principer för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="7dbca-264">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="7dbca-265">Använd följande syntax för att visa befintliga principer för säkra bifogade filer:</span><span class="sxs-lookup"><span data-stu-id="7dbca-265">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="7dbca-266">Det här exemplet returnerar en sammanfattning av alla principer för säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="7dbca-266">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="7dbca-267">Det här exemplet returnerar detaljerad information om principen för säkra bifogade filer som heter Contoso-chefer.</span><span class="sxs-lookup"><span data-stu-id="7dbca-267">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="7dbca-268">Detaljerad information om syntax och parametrar finns i [Get-SafeAttachmentPolicy.](/powershell/module/exchange/get-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="7dbca-268">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="7dbca-269">Använda PowerShell för att visa regler för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="7dbca-269">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="7dbca-270">Om du vill visa befintliga regler för säkra bifogade filer använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="7dbca-270">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="7dbca-271">Det här exemplet returnerar en sammanfattning av alla regler för säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="7dbca-271">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="7dbca-272">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="7dbca-272">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="7dbca-273">Det här exemplet returnerar detaljerad information om regeln för säkra bifogade filer som heter Contoso-chefer.</span><span class="sxs-lookup"><span data-stu-id="7dbca-273">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="7dbca-274">Detaljerad information om syntax och parametrar finns i [Get-SafeAttachmentRule.](/powershell/module/exchange/get-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="7dbca-274">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="7dbca-275">Använda PowerShell för att ändra principer för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="7dbca-275">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="7dbca-276">Du kan inte byta namn på en princip för säkra bifogade filer i PowerShell **(cmdleten Set-SafeAttachmentPolicy** har ingen _namnparameter)._</span><span class="sxs-lookup"><span data-stu-id="7dbca-276">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="7dbca-277">När du byter namn Valv en princip för Valv bifogade filer i Microsoft 365 Defender-portalen byter du bara namn på regeln om säkra bifogade _filer._</span><span class="sxs-lookup"><span data-stu-id="7dbca-277">When you rename a Safe Attachments policy in the Microsoft 365 Defender portal, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="7dbca-278">Annars är samma inställningar tillgängliga när du skapar en princip för säkra bifogade filer enligt beskrivningen i steg [1:](#step-1-use-powershell-to-create-a-safe-attachment-policy) Använda PowerShell för att skapa en princip för säkra bifogade filer längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="7dbca-278">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="7dbca-279">Använd följande syntax för att ändra en princip för säkra bifogade filer:</span><span class="sxs-lookup"><span data-stu-id="7dbca-279">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="7dbca-280">Detaljerad information om syntax och parametrar finns i [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="7dbca-280">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="7dbca-281">Använda PowerShell för att ändra regler för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="7dbca-281">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="7dbca-282">Den enda inställning som inte är tillgänglig när du ändrar en regel för säkra bifogade filer i PowerShell är parametern _Enabled_ som gör att du kan skapa en inaktiverad regel.</span><span class="sxs-lookup"><span data-stu-id="7dbca-282">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="7dbca-283">Nästa avsnitt innehåller information om hur du aktiverar eller inaktiverar befintliga regler för säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="7dbca-283">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="7dbca-284">Annars är samma inställningar tillgängliga när du skapar en regel som beskrivs i steg [2:](#step-2-use-powershell-to-create-a-safe-attachment-rule) Använd PowerShell för att skapa en regel för säkra bifogade filer längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="7dbca-284">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="7dbca-285">Använd följande syntax för att ändra en regel för säkra bifogade filer:</span><span class="sxs-lookup"><span data-stu-id="7dbca-285">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="7dbca-286">Detaljerad information om syntax och parametrar finns i [Set-SafeAttachmentRule.](/powershell/module/exchange/set-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="7dbca-286">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="7dbca-287">Använda PowerShell för att aktivera eller inaktivera regler för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="7dbca-287">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="7dbca-288">Om du aktiverar eller inaktiverar en regel för säkra bifogade filer i PowerShell aktiveras eller inaktiveras hela Valv-principen för bifogade filer (regeln om säker bifogad fil och principen för bifogade filer).</span><span class="sxs-lookup"><span data-stu-id="7dbca-288">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="7dbca-289">Om du vill aktivera eller inaktivera en regel för säkra bifogade filer i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="7dbca-289">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="7dbca-290">I det här exemplet inaktiveras regeln för säker bifogad fil med namnet Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="7dbca-290">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="7dbca-291">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="7dbca-291">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="7dbca-292">Detaljerad information om syntax och parametrar finns i [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) och [Disable-SafeAttachmentRule.](/powershell/module/exchange/disable-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="7dbca-292">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="7dbca-293">Använda PowerShell för att ange prioritet för regler för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="7dbca-293">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="7dbca-294">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="7dbca-294">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="7dbca-295">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="7dbca-295">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="7dbca-296">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="7dbca-296">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="7dbca-297">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="7dbca-297">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="7dbca-298">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="7dbca-298">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="7dbca-299">Om du vill ange prioriteten för en regel för säkra bifogade filer i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="7dbca-299">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="7dbca-300">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="7dbca-300">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="7dbca-301">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="7dbca-301">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="7dbca-302">**Obs!** Om du vill ange prioriteten för en ny regel när du skapar den använder du parametern _Priority_ i cmdleten **New-SafeAttachmentRule** i stället.</span><span class="sxs-lookup"><span data-stu-id="7dbca-302">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="7dbca-303">Detaljerad information om syntax och parametrar finns i [Set-SafeAttachmentRule.](/powershell/module/exchange/set-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="7dbca-303">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="7dbca-304">Använda PowerShell för att ta bort principer för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="7dbca-304">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="7dbca-305">När du använder PowerShell för att ta bort en princip för säkra bifogade filer, tas motsvarande regel för säkra bifogade filer inte bort.</span><span class="sxs-lookup"><span data-stu-id="7dbca-305">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="7dbca-306">Om du vill ta bort en princip för säkra bifogade filer i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="7dbca-306">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="7dbca-307">Det här exemplet tar bort principen för säkra bifogade filer med namnet Marknadsföringsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="7dbca-307">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="7dbca-308">Detaljerad information om syntax och parametrar finns i [Remove-SafeAttachmentPolicy.](/powershell/module/exchange/remove-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="7dbca-308">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="7dbca-309">Använda PowerShell för att ta bort regler för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="7dbca-309">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="7dbca-310">När du använder PowerShell för att ta bort en regel för säkra bifogade filer, tas motsvarande princip för säkra bifogade filer inte bort.</span><span class="sxs-lookup"><span data-stu-id="7dbca-310">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="7dbca-311">Om du vill ta bort en regel för säkra bifogade filer i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="7dbca-311">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="7dbca-312">I det här exemplet tas regeln om säker bifogad fil bort med namnet Marknadsföringsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="7dbca-312">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="7dbca-313">Detaljerad information om syntax och parametrar finns i [Remove-SafeAttachmentRule.](/powershell/module/exchange/remove-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="7dbca-313">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="7dbca-314">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="7dbca-314">How do you know these procedures worked?</span></span>

<span data-ttu-id="7dbca-315">Kontrollera att du har skapat, ändrat eller tagit bort Valv principer för bifogade filer genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="7dbca-315">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="7dbca-316">I portalen Microsoft 365 Defender du till Principer för **&-& e-&** principer för hotprinciper \>  \>  \>  Valv \> **bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="7dbca-316">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span> <span data-ttu-id="7dbca-317">Kontrollera listan med principer, deras **statusvärden** och deras **prioritetsvärden.**</span><span class="sxs-lookup"><span data-stu-id="7dbca-317">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="7dbca-318">Om du vill visa mer information väljer du principen i listan genom att klicka på namnet och visa informationen i den utfällovyn.</span><span class="sxs-lookup"><span data-stu-id="7dbca-318">To view more details, select the policy from the list by clicking on the name, and view the details in the fly out.</span></span>

- <span data-ttu-id="7dbca-319">I Exchange Online PowerShell eller Exchange Online Protection PowerShell ersätter du med namnet på principen eller regeln, kör följande kommando och \<Name\> kontrollerar inställningarna:</span><span class="sxs-lookup"><span data-stu-id="7dbca-319">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="7dbca-320">Kontrollera att Valv bifogade filer söker igenom meddelanden genom att titta i den tillgängliga Defender Office 365 av rapporter.</span><span class="sxs-lookup"><span data-stu-id="7dbca-320">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="7dbca-321">Mer information finns i [Visa rapporter för Defender för Office 365](view-reports-for-mdo.md) och Använda [Utforskaren i Microsoft 365 Defender portal.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="7dbca-321">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>
