---
title: Konfigurera principer för säkra bifogade filer i Microsoft Defender för Office 365
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
description: Läs mer om hur du definierar principer för säkra bifogade filer för att skydda organisationen från skadliga filer i e-postmeddelanden.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e96babff19ea981b953d35929813b1e08c000e32
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071201"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="02531-103">Konfigurera principer för säkra bifogade filer i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="02531-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="02531-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="02531-104">**Applies to**</span></span>
- [<span data-ttu-id="02531-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="02531-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="02531-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="02531-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="02531-107">Den här artikeln är avsedd för företagskunder som har [Microsoft Defender för Office 365](whats-new-in-defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="02531-107">This article is intended for business customers who have [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md).</span></span> <span data-ttu-id="02531-108">Om du är hemanvändare och vill ha information om skanning av bifogade filer i Outlook kan du läsa [Mer Outlook.com säkerhet.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="02531-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="02531-109">Säkra bifogade filer är en funktion i Microsoft Defender för [Office 365](whats-new-in-defender-for-office-365.md) som använder en virtuell miljö för att kontrollera bifogade filer i inkommande e-postmeddelanden när de har genomsökts av skydd mot skadlig programvara [i Exchange Online Protection (EOP),](anti-malware-protection.md)men innan de levereras till mottagarna.</span><span class="sxs-lookup"><span data-stu-id="02531-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="02531-110">Mer information finns i Säkra [bifogade filer i Microsoft Defender för Office 365.](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="02531-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](safe-attachments.md).</span></span>

<span data-ttu-id="02531-111">Det finns ingen inbyggd eller standardprincip för säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="02531-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="02531-112">För att kunna skanna bifogade filer i e-postmeddelanden måste du skapa en eller flera principer för säkra bifogade filer enligt beskrivningen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="02531-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="02531-113">Du kan konfigurera principer för säkra bifogade filer i Säkerhets- och efterlevnadscenter för & eller i PowerShell (Exchange Online PowerShell för kvalificerade Microsoft 365-organisationer med postlådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor men med tilläggsprenumerationer för Defender för Office 365).</span><span class="sxs-lookup"><span data-stu-id="02531-113">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="02531-114">De grundläggande elementen i en princip för säkra bifogade filer är:</span><span class="sxs-lookup"><span data-stu-id="02531-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="02531-115">**Principen för** säkra bifogade filer: Anger åtgärder för okänd identifiering av skadlig programvara, om du vill skicka meddelanden med bifogade filer från skadlig programvara till en viss e-postadress och om meddelanden ska levereras om genomsökningen efter säkra bifogade filer inte kan slutföras.</span><span class="sxs-lookup"><span data-stu-id="02531-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="02531-116">**Regeln för säkra bifogade** filer: Anger prioritet och mottagarfilter (vem principen gäller för).</span><span class="sxs-lookup"><span data-stu-id="02531-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="02531-117">Skillnaden mellan dessa två element är inte uppenbara när du hanterar säkerhet och säkerhet i & efterlevnadscenter:</span><span class="sxs-lookup"><span data-stu-id="02531-117">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="02531-118">När du skapar en princip för säkra bifogade filer skapar du i själva verket en regel för säkra bifogade filer och den associerade principen för säkra bifogade filer samtidigt som du använder samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="02531-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="02531-119">När du ändrar en princip för säkra bifogade filer ändras regeln för säkra bifogade filer när du ändrar inställningar för namn, prioritet, aktiverad eller inaktiverad, och mottagarfilter.</span><span class="sxs-lookup"><span data-stu-id="02531-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="02531-120">Alla andra inställningar ändrar den associerade principen för säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="02531-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="02531-121">När du tar bort en princip för säkra bifogade filer tas regeln för säkra bifogade filer och den tillhörande principen för säkra bifogade filer bort.</span><span class="sxs-lookup"><span data-stu-id="02531-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="02531-122">I Exchange Online PowerShell eller fristående EOP PowerShell hanterar du policyn och regeln separat.</span><span class="sxs-lookup"><span data-stu-id="02531-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="02531-123">Mer information finns i avsnittet Använda [Exchange Online PowerShell eller fristående EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) för att konfigurera principer för säkra bifogade filer längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="02531-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="02531-124">I det globala inställningsområdet i inställningarna för säkra bifogade filer konfigurerar du funktioner som inte är beroende av principer för säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="02531-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="02531-125">Anvisningar finns i [Aktivera säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) och Säkra dokument i Microsoft [365 E5.](safe-docs.md)</span><span class="sxs-lookup"><span data-stu-id="02531-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="02531-126">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="02531-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="02531-127">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="02531-127">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="02531-128">För att gå direkt till sidan **Säkra bifogade** filer använder du <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="02531-128">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="02531-129">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="02531-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="02531-130">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="02531-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="02531-131">Du måste ha tilldelats behörigheter innan du kan utföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="02531-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="02531-132">Om du vill skapa, ändra och ta bort principer för säkra  bifogade filer måste du vara medlem  i rollgrupperna  Organisationshantering eller Säkerhetsadministratör i säkerhets- och efterlevnadscentret för & och medlem i rollgruppen Organisationshantering i Exchange Online. </span><span class="sxs-lookup"><span data-stu-id="02531-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="02531-133">För skrivskyddade åtkomst till principer för säkra bifogade filer måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare** i Säkerhets- och & Säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="02531-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Security & Compliance Center.</span></span>

  <span data-ttu-id="02531-134">Mer information finns i [Behörigheter i Säkerhets- & och Behörigheter](permissions-in-the-security-and-compliance-center.md) i Exchange [Online.](/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="02531-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="02531-135">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="02531-135">**Notes**:</span></span>

  - <span data-ttu-id="02531-136">Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="02531-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="02531-137">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="02531-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="02531-138">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="02531-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="02531-139">Vi rekommenderar inställningar för principer för säkra bifogade filer i inställningarna [för säkra bifogade filer.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="02531-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="02531-140">Det kan ta upp till 30 minuter innan en ny eller uppdaterad princip tillämpas.</span><span class="sxs-lookup"><span data-stu-id="02531-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="02531-141">Använd säkerhets- och & för att skapa principer för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="02531-141">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="02531-142">När du skapar en egen princip för säkra bifogade filer i Säkerhets- och &-efterlevnadscentret skapas en regel för säkra bifogade filer och att tillhörande princip för säkra bifogade filer samtidigt används med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="02531-142">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="02531-143">I Säkerhets- & säkerhets- och efterlevnadscenter går **du** till ATP för \>  \> **hothanteringspolicy för säkra bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="02531-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="02531-144">På sidan **Säkra bifogade** filer klickar du på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="02531-144">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="02531-145">Guiden **Ny princip för bifogade** filer öppnas.</span><span class="sxs-lookup"><span data-stu-id="02531-145">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="02531-146">Konfigurera **följande inställningar på** sidan Namnge principen:</span><span class="sxs-lookup"><span data-stu-id="02531-146">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="02531-147">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="02531-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="02531-148">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="02531-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="02531-149">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="02531-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="02531-150">Konfigurera **följande** inställningar på sidan Inställningar som visas:</span><span class="sxs-lookup"><span data-stu-id="02531-150">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="02531-151">**Okänd information om säkra bifogade filer :** Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="02531-151">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="02531-152">**Av:** Normalt rekommenderar vi inte det här värdet.</span><span class="sxs-lookup"><span data-stu-id="02531-152">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="02531-153">**Övervaka**</span><span class="sxs-lookup"><span data-stu-id="02531-153">**Monitor**</span></span>
     - <span data-ttu-id="02531-154">**Block:** Det här är standardvärdet och det rekommenderade värdet i standard- och strikt [förinställda säkerhetsprinciper.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="02531-154">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="02531-155">**Ersätt**</span><span class="sxs-lookup"><span data-stu-id="02531-155">**Replace**</span></span>
     - <span data-ttu-id="02531-156">**Dynamisk leverans (förhandsgranskningsfunktion)**</span><span class="sxs-lookup"><span data-stu-id="02531-156">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="02531-157">De här värdena förklaras i [principinställningarna för säkra bifogade filer.](safe-attachments.md#safe-attachments-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="02531-157">These values are explained in [Safe Attachments policy settings](safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="02531-158">**Skicka** bilagan till följande e-postadress: För åtgärdsvärdena **Block**,  **Bildskärm** eller Ersätt kan du välja Aktivera omdirigering för att skicka meddelanden som innehåller bifogade filer från skadlig programvara till den angivna interna eller externa e-postadressen för analys och undersökning. </span><span class="sxs-lookup"><span data-stu-id="02531-158">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="02531-159">Rekommendationen för standard- och strikt-principinställningarna är att aktivera omdirigering.</span><span class="sxs-lookup"><span data-stu-id="02531-159">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="02531-160">Mer information finns i Inställningarna [för säkra bifogade filer.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="02531-160">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="02531-161">**Använd markeringen ovan** om genomsökning av skadlig programvara för  bifogade filer på tider eller fel inträffar: Åtgärden som anges av okänt svar på säkra bifogade filer används på meddelanden även om genomsökning av säkra bifogade filer inte kan slutföras.</span><span class="sxs-lookup"><span data-stu-id="02531-161">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="02531-162">Om du valde det här alternativet ska du alltid **välja Aktiverad omdirigering.**</span><span class="sxs-lookup"><span data-stu-id="02531-162">If you selected this option, always select **Enabled redirect**.</span></span> <span data-ttu-id="02531-163">Annars kan meddelanden gå förlorade.</span><span class="sxs-lookup"><span data-stu-id="02531-163">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="02531-164">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="02531-164">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="02531-165">På sidan **Används på** som visas identifierar du de interna mottagare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="02531-165">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="02531-166">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="02531-166">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="02531-167">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="02531-167">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="02531-168">Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="02531-168">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="02531-169">Klicka **på Lägg till ett villkor.**</span><span class="sxs-lookup"><span data-stu-id="02531-169">Click **Add a condition**.</span></span> <span data-ttu-id="02531-170">I listrutan som visas väljer du ett villkor under **Används om:**</span><span class="sxs-lookup"><span data-stu-id="02531-170">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="02531-171">**Mottagaren är: Anger** en eller flera postlådor, e-postanvändare eller e-postkontakter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="02531-171">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="02531-172">**Mottagaren är medlem i**: Anger en eller flera grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="02531-172">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="02531-173">**Mottagande domän är**: Anger mottagare i en eller flera av de godkända domänerna som har konfigurerats i din organisation.</span><span class="sxs-lookup"><span data-stu-id="02531-173">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="02531-174">När du har valt villkoret visas motsvarande listruta med rutan **Valfri av dessa.**</span><span class="sxs-lookup"><span data-stu-id="02531-174">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="02531-175">Klicka i rutan och bläddra igenom listan med värden du vill välja.</span><span class="sxs-lookup"><span data-stu-id="02531-175">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="02531-176">Klicka i rutan och börja skriva för att filtrera listan och välja ett värde.</span><span class="sxs-lookup"><span data-stu-id="02531-176">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="02531-177">Om du vill lägga till ytterligare värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="02531-177">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="02531-178">Om du vill ta bort enskilda poster klickar **du på Ta** bort ikon för ![ ](../../media/scc-remove-icon.png) värdet.</span><span class="sxs-lookup"><span data-stu-id="02531-178">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="02531-179">Om du vill ta bort hela villkoret klickar du **på Ta** bort ikon ![ för ](../../media/scc-remove-icon.png) villkoret.</span><span class="sxs-lookup"><span data-stu-id="02531-179">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="02531-180">Om du vill lägga till ytterligare ett villkor klickar **du på Lägg till ett** villkor och väljer ett återstående värde under Används **om**.</span><span class="sxs-lookup"><span data-stu-id="02531-180">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="02531-181">Om du vill lägga till undantag klickar **du på Lägg till ett** villkor och väljer ett undantag under Utom **om**.</span><span class="sxs-lookup"><span data-stu-id="02531-181">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="02531-182">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="02531-182">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="02531-183">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="02531-183">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="02531-184">Granska **inställningarna på sidan** Granska dina inställningar som visas.</span><span class="sxs-lookup"><span data-stu-id="02531-184">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="02531-185">Du kan klicka **på Redigera** för varje inställning för att ändra den.</span><span class="sxs-lookup"><span data-stu-id="02531-185">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="02531-186">Klicka på Slutför när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="02531-186">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="02531-187">Använd Säkerhets- och & för att visa principer för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="02531-187">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="02531-188">I Säkerhets- & säkerhets- och efterlevnadscenter går **du** till ATP för \>  \> **hothanteringspolicy för säkra bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="02531-188">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="02531-189">På sidan **Säkra bifogade** filer väljer du en princip i listan och klickar på den (markera inte kryssrutan).</span><span class="sxs-lookup"><span data-stu-id="02531-189">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="02531-190">Principinformationen visas i en flyg ut</span><span class="sxs-lookup"><span data-stu-id="02531-190">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="02531-191">Använda Säkerhets- och & för att ändra principer för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="02531-191">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="02531-192">I Säkerhets- & säkerhets- och efterlevnadscenter går **du** till ATP för \>  \> **hothanteringspolicy för säkra bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="02531-192">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="02531-193">På sidan **Säkra bifogade** filer väljer du en princip i listan och klickar på den (markera inte kryssrutan).</span><span class="sxs-lookup"><span data-stu-id="02531-193">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="02531-194">I den utfällna menyn med principinformation klickar du på **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="02531-194">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="02531-195">De tillgängliga inställningarna i flyget som visas är identiska med de som beskrivs i använda säkerhets- och & för att skapa principer för [säkra bifogade](#use-the-security--compliance-center-to-create-safe-attachments-policies) filer.</span><span class="sxs-lookup"><span data-stu-id="02531-195">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="02531-196">Läs följande avsnitt om du vill aktivera eller inaktivera en princip eller ange prioritetsordning för principen.</span><span class="sxs-lookup"><span data-stu-id="02531-196">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="02531-197">Aktivera eller inaktivera principer för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="02531-197">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="02531-198">I Säkerhets- & säkerhets- och efterlevnadscenter går **du** till ATP för \>  \> **hothanteringspolicy för säkra bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="02531-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="02531-199">Observera värdet i **kolumnen** Status:</span><span class="sxs-lookup"><span data-stu-id="02531-199">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="02531-200">Flytta reglaget åt vänster</span><span class="sxs-lookup"><span data-stu-id="02531-200">Move the toggle to the left</span></span> ![Inaktivera principen](../../media/scc-toggle-off.png) <span data-ttu-id="02531-202">för att inaktivera principen.</span><span class="sxs-lookup"><span data-stu-id="02531-202">to disable the policy.</span></span>

   - <span data-ttu-id="02531-203">Flytta reglaget åt höger</span><span class="sxs-lookup"><span data-stu-id="02531-203">Move the toggle to the right</span></span> ![Aktivera princip](../../media/scc-toggle-on.png) <span data-ttu-id="02531-205">för att aktivera principen.</span><span class="sxs-lookup"><span data-stu-id="02531-205">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="02531-206">Ange prioritet för principer för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="02531-206">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="02531-207">Som standard prioriteras principer för säkra bifogade filer baserat på i vilken ordning de skapades (nyare principer har lägre prioritet än äldre principer).</span><span class="sxs-lookup"><span data-stu-id="02531-207">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="02531-208">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="02531-208">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="02531-209">Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="02531-209">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="02531-210">För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="02531-210">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="02531-211">Principer för säkra bifogade filer visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0).</span><span class="sxs-lookup"><span data-stu-id="02531-211">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="02531-212">**Obs!** I säkerhets- & säkerhets- och efterlevnadscentret kan du bara ändra prioriteten för principen för säkra bifogade filer när du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="02531-212">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="02531-213">I PowerShell kan du åsidosätta standardprioritet när du skapar regeln om säkra bifogade filer (vilket kan påverka prioriteringen för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="02531-213">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="02531-214">Du ändrar prioriteten för en princip genom att flytta principen uppåt eller nedåt i listan (du kan inte ändra **prioritetsnumret** direkt i Säkerhets- och efterlevnadscenter).</span><span class="sxs-lookup"><span data-stu-id="02531-214">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="02531-215">I Säkerhets- & säkerhets- och efterlevnadscenter går **du** till ATP för \>  \> **hothanteringspolicy för säkra bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="02531-215">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="02531-216">På sidan **Säkra bifogade** filer väljer du en princip i listan och klickar på den (markera inte kryssrutan).</span><span class="sxs-lookup"><span data-stu-id="02531-216">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="02531-217">I den policyinformation som visas klickar du på knappen med tillgänglig prioritet.</span><span class="sxs-lookup"><span data-stu-id="02531-217">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="02531-218">Principen för säkra bifogade filer med **prioritetsvärdet** **0** har endast **knappen Minska** prioritet tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="02531-218">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="02531-219">Principen för säkra bifogade filer med det lägsta **värdet** (till exempel **3)** har endast knappen **Öka** prioritet tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="02531-219">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="02531-220">Om du har tre eller fler principer för säkra bifogade filer, har principer mellan de högsta och lägsta prioritetsvärdena både knapparna Öka prioritet **och Minska** prioritet tillgängliga. </span><span class="sxs-lookup"><span data-stu-id="02531-220">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="02531-221">Klicka **på Öka prioritet** eller Minska **prioritet** om du vill ändra värdet **för** Prioritet.</span><span class="sxs-lookup"><span data-stu-id="02531-221">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="02531-222">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="02531-222">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="02531-223">Använda Säkerhets- och & för att ta bort principer för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="02531-223">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="02531-224">I Säkerhets- & säkerhets- och efterlevnadscenter går **du** till ATP för \>  \> **hothanteringspolicy för säkra bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="02531-224">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="02531-225">På sidan **Säkra bifogade** filer väljer du en princip i listan och klickar på den (markera inte kryssrutan).</span><span class="sxs-lookup"><span data-stu-id="02531-225">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="02531-226">I policyinformationen som visas klickar du på Ta **bort princip** och sedan på **Ja i** varningsdialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="02531-226">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="02531-227">Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="02531-227">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="02531-228">Som tidigare beskrivits består en princip för säkra bifogade filer av en princip för säker bifogad fil och en regel för säker bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="02531-228">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="02531-229">I PowerShell syns skillnaden mellan principer för säkra bifogade filer och regler för säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="02531-229">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="02531-230">Du hanterar principer för säkra bifogade filer med cmdletarna **\* -SafeAttachmentPolicy** och hanterar regler för säkra bifogade filer med cmdlets **\* -SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="02531-230">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="02531-231">I PowerShell skapar du först principen för säkra bifogade filer. Sedan skapar du den regel för säkra bifogade filer som identifierar principen som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="02531-231">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="02531-232">I PowerShell ändrar du inställningarna i principen för säkra bifogade filer och regeln om säker bifogad fil separat.</span><span class="sxs-lookup"><span data-stu-id="02531-232">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="02531-233">När du tar bort en princip för säkra bifogade filer från PowerShell tas motsvarande regel för säkra bifogade filer inte bort automatiskt, och vice versa.</span><span class="sxs-lookup"><span data-stu-id="02531-233">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="02531-234">Använda PowerShell för att skapa principer för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="02531-234">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="02531-235">Att skapa en princip för säkra bifogade filer i PowerShell är en process i två steg:</span><span class="sxs-lookup"><span data-stu-id="02531-235">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="02531-236">Skapa principen för säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="02531-236">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="02531-237">Skapa den regel för säkra bifogade filer som anger principen för säkra bifogade filer som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="02531-237">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="02531-238">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="02531-238">**Notes**:</span></span>

- <span data-ttu-id="02531-239">Du kan skapa en ny regel för säkra bifogade filer och tilldela en befintlig princip för säkra bifogade filer som inte har associerats till den.</span><span class="sxs-lookup"><span data-stu-id="02531-239">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="02531-240">En regel för säkra bifogade filer kan inte associeras med mer än en princip för säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="02531-240">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="02531-241">Du kan konfigurera följande inställningar för nya principer för säkra bifogade filer i PowerShell som inte är tillgängliga i Säkerhets- och &-efterlevnadscenter förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="02531-241">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="02531-242">Skapa den nya principen som _inaktiverad (aktiverad_ `$false` på **cmdleten New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="02531-242">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="02531-243">Ange prioritet för principen vid skapande (_Prioritet_ _\<Number\>_ ) på **cmdleten New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="02531-243">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="02531-244">En ny princip för säkra bifogade filer som du skapar i PowerShell visas inte i Säkerhets- och &-efterlevnadscenter förrän du tilldelar principen till en regel för säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="02531-244">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="02531-245">Steg 1: Använda PowerShell för att skapa en princip för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="02531-245">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="02531-246">Använd följande syntax för att skapa en princip för säkra bifogade filer:</span><span class="sxs-lookup"><span data-stu-id="02531-246">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="02531-247">I det här exemplet skapas en princip för säkra bifogade filer med namnet Contoso Alla med följande värden:</span><span class="sxs-lookup"><span data-stu-id="02531-247">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="02531-248">Blockera meddelanden som innehåller skadlig programvara genom genomsökning av säkra dokument (vi använder inte parametern _Action_ och standardvärdet är `Block` ).</span><span class="sxs-lookup"><span data-stu-id="02531-248">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="02531-249">Omdirigering är aktiverat och meddelanden som innehåller skadlig programvara skickas till sec-ops@contoso.com för analys och undersökning.</span><span class="sxs-lookup"><span data-stu-id="02531-249">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="02531-250">Om genomsökning av säkra bifogade filer inte är tillgängligt eller stöter på fel levereras inte meddelandet (vi använder inte parametern _ActionOnError_ och standardvärdet är `$true` ).</span><span class="sxs-lookup"><span data-stu-id="02531-250">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="02531-251">Detaljerad information om syntax och parametrar finns i [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="02531-251">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="02531-252">Steg 2: Använda PowerShell för att skapa en regel för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="02531-252">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="02531-253">Använd följande syntax för att skapa en regel för säkra bifogade filer:</span><span class="sxs-lookup"><span data-stu-id="02531-253">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="02531-254">I det här exemplet skapas en regel för säkra bifogade filer med namnet Contoso Alla med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="02531-254">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="02531-255">Regeln är kopplad till principen för säkra bifogade filer med namnet Contoso All.</span><span class="sxs-lookup"><span data-stu-id="02531-255">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="02531-256">Regeln gäller för alla mottagare i contoso.com domän.</span><span class="sxs-lookup"><span data-stu-id="02531-256">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="02531-257">Eftersom vi inte använder _parametern Priority_ används standardprioritet.</span><span class="sxs-lookup"><span data-stu-id="02531-257">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="02531-258">Regeln är aktiverad (vi använder inte parametern _Enabled_ och standardvärdet är `$true` ).</span><span class="sxs-lookup"><span data-stu-id="02531-258">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="02531-259">Detaljerad information om syntax och parametrar finns [i New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="02531-259">For detailed syntax and parameter information, see [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="02531-260">Använda PowerShell för att visa principer för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="02531-260">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="02531-261">Använd följande syntax för att visa befintliga principer för säkra bifogade filer:</span><span class="sxs-lookup"><span data-stu-id="02531-261">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="02531-262">Det här exemplet returnerar en sammanfattning av alla principer för säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="02531-262">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="02531-263">Det här exemplet returnerar detaljerad information om principen för säkra bifogade filer som heter Contoso-chefer.</span><span class="sxs-lookup"><span data-stu-id="02531-263">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="02531-264">Detaljerad information om syntax och parametrar finns i [Get-SafeAttachmentPolicy.](/powershell/module/exchange/get-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="02531-264">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="02531-265">Använda PowerShell för att visa regler för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="02531-265">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="02531-266">Om du vill visa befintliga regler för säkra bifogade filer använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="02531-266">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="02531-267">Det här exemplet returnerar en sammanfattning av alla regler för säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="02531-267">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="02531-268">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="02531-268">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="02531-269">Det här exemplet returnerar detaljerad information om regeln för säkra bifogade filer som heter Contoso-chefer.</span><span class="sxs-lookup"><span data-stu-id="02531-269">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="02531-270">Detaljerad information om syntax och parametrar finns i [Get-SafeAttachmentRule.](/powershell/module/exchange/get-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="02531-270">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="02531-271">Använda PowerShell för att ändra principer för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="02531-271">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="02531-272">Du kan inte byta namn på en princip för säkra bifogade filer i PowerShell **(cmdleten Set-SafeAttachmentPolicy** har ingen _namnparameter)._</span><span class="sxs-lookup"><span data-stu-id="02531-272">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="02531-273">När du byter namn på en princip för säkra bifogade filer i Säkerhets- & Säkerhets- och efterlevnadscenter byter du bara namn på regeln om säkra bifogade _filer._</span><span class="sxs-lookup"><span data-stu-id="02531-273">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="02531-274">Annars är samma inställningar tillgängliga när du skapar en princip för säkra bifogade filer enligt beskrivningen i steg [1:](#step-1-use-powershell-to-create-a-safe-attachment-policy) Använda PowerShell för att skapa en princip för säkra bifogade filer längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="02531-274">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="02531-275">Använd följande syntax för att ändra en princip för säkra bifogade filer:</span><span class="sxs-lookup"><span data-stu-id="02531-275">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="02531-276">Detaljerad information om syntax och parametrar finns i [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="02531-276">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="02531-277">Använda PowerShell för att ändra regler för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="02531-277">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="02531-278">Den enda inställning som inte är tillgänglig när du ändrar en regel för säkra bifogade filer i PowerShell är parametern _Enabled_ som gör att du kan skapa en inaktiverad regel.</span><span class="sxs-lookup"><span data-stu-id="02531-278">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="02531-279">Nästa avsnitt innehåller information om hur du aktiverar eller inaktiverar befintliga regler för säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="02531-279">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="02531-280">Annars är samma inställningar tillgängliga när du skapar en regel som beskrivs i steg [2:](#step-2-use-powershell-to-create-a-safe-attachment-rule) Använd PowerShell för att skapa en regel för säkra bifogade filer längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="02531-280">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="02531-281">Använd följande syntax för att ändra en regel för säkra bifogade filer:</span><span class="sxs-lookup"><span data-stu-id="02531-281">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="02531-282">Detaljerad information om syntax och parametrar finns i [Set-SafeAttachmentRule.](/powershell/module/exchange/set-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="02531-282">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="02531-283">Använda PowerShell för att aktivera eller inaktivera regler för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="02531-283">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="02531-284">Om du aktiverar eller inaktiverar en regel för säkra bifogade filer i PowerShell aktiveras eller inaktiveras hela principen för bifogade filer (regeln för säkra bifogade filer och principen för bifogade filer).</span><span class="sxs-lookup"><span data-stu-id="02531-284">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="02531-285">Om du vill aktivera eller inaktivera en regel för säkra bifogade filer i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="02531-285">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="02531-286">I det här exemplet inaktiveras regeln för säker bifogad fil med namnet Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="02531-286">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="02531-287">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="02531-287">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="02531-288">Detaljerad information om syntax och parametrar finns i [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) och [Disable-SafeAttachmentRule.](/powershell/module/exchange/disable-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="02531-288">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="02531-289">Använda PowerShell för att ange prioritet för regler för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="02531-289">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="02531-290">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="02531-290">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="02531-291">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="02531-291">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="02531-292">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="02531-292">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="02531-293">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="02531-293">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="02531-294">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="02531-294">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="02531-295">Om du vill ange prioriteten för en regel för säkra bifogade filer i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="02531-295">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="02531-296">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="02531-296">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="02531-297">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="02531-297">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="02531-298">**Obs!** Om du vill ange prioriteten för en ny regel när du skapar den använder du parametern _Priority_ i cmdleten **New-SafeAttachmentRule** i stället.</span><span class="sxs-lookup"><span data-stu-id="02531-298">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="02531-299">Detaljerad information om syntax och parametrar finns i [Set-SafeAttachmentRule.](/powershell/module/exchange/set-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="02531-299">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="02531-300">Använda PowerShell för att ta bort principer för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="02531-300">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="02531-301">När du använder PowerShell för att ta bort en princip för säkra bifogade filer, tas motsvarande regel för säkra bifogade filer inte bort.</span><span class="sxs-lookup"><span data-stu-id="02531-301">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="02531-302">Om du vill ta bort en princip för säkra bifogade filer i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="02531-302">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="02531-303">Det här exemplet tar bort principen för säkra bifogade filer med namnet Marknadsföringsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="02531-303">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="02531-304">Detaljerad information om syntax och parametrar finns i [Remove-SafeAttachmentPolicy.](/powershell/module/exchange/remove-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="02531-304">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="02531-305">Använda PowerShell för att ta bort regler för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="02531-305">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="02531-306">När du använder PowerShell för att ta bort en regel för säkra bifogade filer, tas motsvarande princip för säkra bifogade filer inte bort.</span><span class="sxs-lookup"><span data-stu-id="02531-306">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="02531-307">Om du vill ta bort en regel för säkra bifogade filer i PowerShell använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="02531-307">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="02531-308">I det här exemplet tas regeln om säker bifogad fil bort med namnet Marknadsföringsavdelningen.</span><span class="sxs-lookup"><span data-stu-id="02531-308">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="02531-309">Detaljerad information om syntax och parametrar finns i [Remove-SafeAttachmentRule.](/powershell/module/exchange/remove-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="02531-309">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="02531-310">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="02531-310">How do you know these procedures worked?</span></span>

<span data-ttu-id="02531-311">Kontrollera att du har skapat, ändrat eller tagit bort principer för säkra bifogade filer genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="02531-311">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="02531-312">I Säkerhets- & säkerhets- och efterlevnadscenter går **du** till ATP för \>  \> **hothanteringspolicy för säkra bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="02531-312">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="02531-313">Kontrollera listan med principer, deras **statusvärden** och deras **prioritetsvärden.**</span><span class="sxs-lookup"><span data-stu-id="02531-313">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="02531-314">Om du vill visa mer information väljer du principen i listan och visar informationen i den utfäll plats du vill ha.</span><span class="sxs-lookup"><span data-stu-id="02531-314">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="02531-315">I Exchange Online PowerShell eller Exchange Online Protection PowerShell ersätter du med namnet på principen eller regeln, kör följande kommando \<Name\> och kontrollerar inställningarna:</span><span class="sxs-lookup"><span data-stu-id="02531-315">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="02531-316">Kontrollera att Säkra bifogade filer söker igenom meddelanden genom att titta i tillgängliga Defender-rapporter för Office 365-rapporter.</span><span class="sxs-lookup"><span data-stu-id="02531-316">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="02531-317">Mer information finns i Visa rapporter för Defender för [Office 365](view-reports-for-mdo.md) och Använda Utforskaren i [Säkerhets- & efterlevnadscenter.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="02531-317">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
