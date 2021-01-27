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
description: Lär dig hur du definierar principer för säkra bifogade filer för att skydda din organisation från skadliga filer via e-post.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5a26d214fe99d0053bf178d7d85a0b526d64f887
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988086"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="8dbea-103">Konfigurera principer för säkra bifogade filer i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="8dbea-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="8dbea-104">Den här artikeln är avsedd för företagskunder som har [Microsoft Defender för Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="8dbea-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="8dbea-105">Om du är hem användare letar efter information om genomsökning av bifogade filer i Outlook, se [avancerad Outlook.com säkerhet](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="8dbea-105">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="8dbea-106">Säkra bifogade filer är en funktion i [Microsoft Defender för Office 365](office-365-atp.md) som använder en virtuell miljö för att kontrol lera bilagor i inkommande e-postmeddelanden efter att de har skannats av [skydd mot skadlig program vara i Exchange Online Protection (EOP)](anti-malware-protection.md), men innan de levereras till mottagarna.</span><span class="sxs-lookup"><span data-stu-id="8dbea-106">Safe Attachments is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="8dbea-107">Mer information finns i avsnitten [om säkra bifogade filer i Microsoft Defender för Office 365](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="8dbea-107">For more information, see [Safe Attachments in Microsoft Defender for Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="8dbea-108">Det finns ingen inbyggd eller standard princip för säker bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="8dbea-108">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="8dbea-109">Om du vill söka efter säkra bilagor i e-postbilagor måste du skapa en eller flera principer för säker bifogad fil enligt beskrivningen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="8dbea-109">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="8dbea-110">Du kan konfigurera principer för säkra bifogade filer i fältet säkerhets & efterlevnad eller i PowerShell (Exchange Online PowerShell för kvalificerade Microsoft 365-organisationer med post lådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor, men med Defender för Office 365-tilläggs prenumerationer).</span><span class="sxs-lookup"><span data-stu-id="8dbea-110">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="8dbea-111">De grundläggande delarna i en policy för principer för bifogade filer är:</span><span class="sxs-lookup"><span data-stu-id="8dbea-111">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="8dbea-112">**Principen för säker bifogad fil**: anger åtgärderna för okända identifieringar av skadlig program vara om du vill skicka meddelanden med bifogade filer till en viss e-postadress och om det inte går att slutföra säkra bilagor.</span><span class="sxs-lookup"><span data-stu-id="8dbea-112">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="8dbea-113">**Regeln för säker bifogad fil**: anger de prioritets-och mottagar filter (som principen gäller för).</span><span class="sxs-lookup"><span data-stu-id="8dbea-113">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="8dbea-114">Skillnaden mellan dessa två element är inte uppenbar när du hanterar Safe Attachment-principer i säkerhets & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="8dbea-114">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="8dbea-115">När du skapar en policy för säker bifogade filer skapar du verkligen en regel för säker bifogad fil och den associerade principen för säker bifogad fil samtidigt med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="8dbea-115">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="8dbea-116">När du ändrar en policy för en säker bifogad fil kan inställningar som gäller namn, prioritet, aktive rad eller inaktive rad och mottagar filter ändra regeln för säker bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="8dbea-116">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="8dbea-117">Alla andra inställningar ändrar den associerade principen för säker bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="8dbea-117">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="8dbea-118">När du tar bort en princip för säker bifogad fil tas reglerna för den säkra bifogade filen och den associerade principen för säker bifogade filer bort</span><span class="sxs-lookup"><span data-stu-id="8dbea-118">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="8dbea-119">I Exchange Online PowerShell eller fristående EOP PowerShell hanterar du policyn och regeln separat.</span><span class="sxs-lookup"><span data-stu-id="8dbea-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="8dbea-120">Mer information finns i [använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för säker bifogade filer](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="8dbea-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="8dbea-121">I området globala inställningar i inställningar för säker bifogade filer konfigurerar du funktioner som inte är beroende av principer för säker bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="8dbea-121">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="8dbea-122">Anvisningar finns i [Aktivera säkra bifogade filer för SharePoint-, OneDrive-och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) och [Safe-dokument i Microsoft 365 E5](safe-docs.md).</span><span class="sxs-lookup"><span data-stu-id="8dbea-122">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8dbea-123">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="8dbea-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8dbea-124">Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="8dbea-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8dbea-125">Använd om du vill gå direkt till sidan **betrodda bifogade filer** <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="8dbea-125">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="8dbea-126">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="8dbea-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="8dbea-127">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="8dbea-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="8dbea-128">Du måste tilldelas behörigheter innan du kan utföra åtgärderna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="8dbea-128">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="8dbea-129">För att skapa, ändra och ta bort principer för säkra länkar måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** i säkerhets & Compliance Center **och** en medlem i roll gruppen **organisations hantering** i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8dbea-129">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="8dbea-130">Om du vill ha skrivskyddad åtkomst till principer för säkra länkar måste du vara medlem i roll grupperna **global läsare** eller **säkerhets läsare** i säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="8dbea-130">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Security & Compliance Center.</span></span>

  <span data-ttu-id="8dbea-131">Mer information finns i [behörigheter i säkerhets & efterlevnad för Center](permissions-in-the-security-and-compliance-center.md) och [behörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="8dbea-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="8dbea-132">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="8dbea-132">**Notes**:</span></span>

  - <span data-ttu-id="8dbea-133">Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8dbea-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="8dbea-134">Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="8dbea-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="8dbea-135">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="8dbea-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="8dbea-136">De rekommenderade inställningarna för principer för säkra bifogade filer finns i [Inställningar för säkra bifogade filer](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span><span class="sxs-lookup"><span data-stu-id="8dbea-136">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="8dbea-137">Tillåt upp till 30 minuter för att en ny eller uppdaterad princip ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="8dbea-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="8dbea-138">Skapa principer för säkra bifogade filer med hjälp av säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="8dbea-138">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="8dbea-139">Om du skapar en anpassad princip för säker bifogade filer i säkerhets & Compliance Center skapas regeln för säker bifogad fil och den associerade principen för säker bifogad fil med samma namn för båda.</span><span class="sxs-lookup"><span data-stu-id="8dbea-139">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="8dbea-140">I säkerhets & Compliance Center kan du gå till **Threat Management** \> **policy** - \> **säkra bifogade filer**.</span><span class="sxs-lookup"><span data-stu-id="8dbea-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="8dbea-141">På sidan **betrodda bifogade filer** klickar du på **skapa**.</span><span class="sxs-lookup"><span data-stu-id="8dbea-141">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="8dbea-142">Guiden **ny princip för säkert bifogade filer** öppnas.</span><span class="sxs-lookup"><span data-stu-id="8dbea-142">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="8dbea-143">På sidan **namnge din policy** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="8dbea-143">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="8dbea-144">**Namn**: Ange ett unikt, beskrivande namn på principen.</span><span class="sxs-lookup"><span data-stu-id="8dbea-144">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="8dbea-145">**Beskrivning**: Ange en valfri beskrivning av principen.</span><span class="sxs-lookup"><span data-stu-id="8dbea-145">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="8dbea-146">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="8dbea-146">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="8dbea-147">På sidan **Inställningar** som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="8dbea-147">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8dbea-148">**Säkra bifogade filer okänt antivirus program**: Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="8dbea-148">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="8dbea-149">**Av**: vanligt vis rekommenderar vi inte det här värdet.</span><span class="sxs-lookup"><span data-stu-id="8dbea-149">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="8dbea-150">**Övervaka**</span><span class="sxs-lookup"><span data-stu-id="8dbea-150">**Monitor**</span></span>
     - <span data-ttu-id="8dbea-151">**Block**: det här är standardvärdet och det rekommenderade värdet i säkerhets principer för standard-och Strict- [förvalda](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8dbea-151">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="8dbea-152">**Byter**</span><span class="sxs-lookup"><span data-stu-id="8dbea-152">**Replace**</span></span>
     - <span data-ttu-id="8dbea-153">**Dynamisk leverans (för hands version)**</span><span class="sxs-lookup"><span data-stu-id="8dbea-153">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="8dbea-154">Dessa värden förklaras i [princip inställningar för säkra bifogade filer](atp-safe-attachments.md#safe-attachments-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="8dbea-154">These values are explained in [Safe Attachments policy settings](atp-safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="8dbea-155">**Skicka bilagan till följande e-post adress**: för åtgärds värden **blockera**, **övervaka** eller **ersätta** kan du välja **Aktivera omdirigering** för att skicka meddelanden som innehåller bifogade filer med skadlig kod till angiven intern eller extern e-postadress för analys och undersökning.</span><span class="sxs-lookup"><span data-stu-id="8dbea-155">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="8dbea-156">Rekommendationen för standard-och strikta princip inställningar är att aktivera omdirigering.</span><span class="sxs-lookup"><span data-stu-id="8dbea-156">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="8dbea-157">Mer information finns i [Inställningar för säkra bifogade filer](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span><span class="sxs-lookup"><span data-stu-id="8dbea-157">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="8dbea-158">**Använda ovanstående markering om genomsökning av skadlig kod för bifogade filer eller fel inträffar**: åtgärden som anges av **osäkra bifogade filer inget svar på skadlig program** vara tas med när säkra bilagor inte kan slutföras.</span><span class="sxs-lookup"><span data-stu-id="8dbea-158">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="8dbea-159">Om du har valt det här alternativet, Välj alltid **aktiverat omdirigering**.</span><span class="sxs-lookup"><span data-stu-id="8dbea-159">If you selected this option, always select **Enabled redirect**.</span></span> <span data-ttu-id="8dbea-160">Annars kan meddelanden gå förlorade.</span><span class="sxs-lookup"><span data-stu-id="8dbea-160">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="8dbea-161">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="8dbea-161">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="8dbea-162">**På sidan som** visas anger du vilka interna mottagare som principen gäller för.</span><span class="sxs-lookup"><span data-stu-id="8dbea-162">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="8dbea-163">Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget.</span><span class="sxs-lookup"><span data-stu-id="8dbea-163">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="8dbea-164">Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="8dbea-164">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="8dbea-165">Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="8dbea-165">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="8dbea-166">Klicka på **Lägg till ett villkor**.</span><span class="sxs-lookup"><span data-stu-id="8dbea-166">Click **Add a condition**.</span></span> <span data-ttu-id="8dbea-167">I den nedrullningsbara List rutan som visas väljer du ett villkor under **används om**:</span><span class="sxs-lookup"><span data-stu-id="8dbea-167">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="8dbea-168">**Mottagaren är**: anger en eller flera post lådor, e-postkonton eller e-postkontakter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="8dbea-168">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="8dbea-169">**Mottagaren är medlem i**: anger en eller flera grupper i din organisation.</span><span class="sxs-lookup"><span data-stu-id="8dbea-169">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="8dbea-170">**Mottagande domän är**: Anger mottagare i en eller flera av de godkända domänerna som har konfigurerats i din organisation.</span><span class="sxs-lookup"><span data-stu-id="8dbea-170">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="8dbea-171">När du har valt villkoret visas en motsvarande listruta med en **av dessa** rutor.</span><span class="sxs-lookup"><span data-stu-id="8dbea-171">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="8dbea-172">Klicka i rutan och bläddra igenom listan med värden att välja.</span><span class="sxs-lookup"><span data-stu-id="8dbea-172">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="8dbea-173">Klicka i rutan och börja skriva för att filtrera listan och välja ett värde.</span><span class="sxs-lookup"><span data-stu-id="8dbea-173">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="8dbea-174">Om du vill lägga till fler värden klickar du i ett tomt område i rutan.</span><span class="sxs-lookup"><span data-stu-id="8dbea-174">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="8dbea-175">Om du vill ta bort enskilda poster klickar du på **ta bort** - ![ ikonen ](../../media/scc-remove-icon.png) för värdet.</span><span class="sxs-lookup"><span data-stu-id="8dbea-175">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="8dbea-176">Om du vill ta bort hela villkoret klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="8dbea-176">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="8dbea-177">Om du vill lägga till ytterligare villkor klickar du på **Lägg till ett villkor** och väljer ett återstående värde under **används om**.</span><span class="sxs-lookup"><span data-stu-id="8dbea-177">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="8dbea-178">Om du vill lägga till undantag klickar du på **Lägg till ett villkor** och väljer ett undantag under **utom om**.</span><span class="sxs-lookup"><span data-stu-id="8dbea-178">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="8dbea-179">Inställningarna och beteendet är likadana som villkoren.</span><span class="sxs-lookup"><span data-stu-id="8dbea-179">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="8dbea-180">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="8dbea-180">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="8dbea-181">Granska inställningarna på sidan **Granska inställningar** som visas.</span><span class="sxs-lookup"><span data-stu-id="8dbea-181">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="8dbea-182">Du kan klicka på **Redigera** på varje inställning för att ändra den.</span><span class="sxs-lookup"><span data-stu-id="8dbea-182">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="8dbea-183">När du är klar klickar du på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="8dbea-183">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="8dbea-184">Använda säkerhets & Compliance Center för att visa principer för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="8dbea-184">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="8dbea-185">I säkerhets & Compliance Center kan du gå till **Threat Management** \> **policy** - \> **säkra bifogade filer**.</span><span class="sxs-lookup"><span data-stu-id="8dbea-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="8dbea-186">På sidan **betrodda bifogade filer** väljer du en princip i listan och klickar på den (markerar inte kryss rutan).</span><span class="sxs-lookup"><span data-stu-id="8dbea-186">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="8dbea-187">Princip detaljerna visas i ett flyg utåt</span><span class="sxs-lookup"><span data-stu-id="8dbea-187">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="8dbea-188">Använda säkerhets & Compliance Center för att ändra principer för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="8dbea-188">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="8dbea-189">I säkerhets & Compliance Center kan du gå till **Threat Management** \> **policy** - \> **säkra bifogade filer**.</span><span class="sxs-lookup"><span data-stu-id="8dbea-189">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="8dbea-190">På sidan **betrodda bifogade filer** väljer du en princip i listan och klickar på den (markerar inte kryss rutan).</span><span class="sxs-lookup"><span data-stu-id="8dbea-190">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="8dbea-191">I princip informationen som visas klickar du på **Redigera princip**.</span><span class="sxs-lookup"><span data-stu-id="8dbea-191">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="8dbea-192">Tillgängliga inställningar i rutan Lägg på som visas är identiska med de som beskrivs i avsnittet [använda säkerhets & efterlevnad för att skapa principer för säker bifogade filer](#use-the-security--compliance-center-to-create-safe-attachments-policies) .</span><span class="sxs-lookup"><span data-stu-id="8dbea-192">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="8dbea-193">Om du vill aktivera eller inaktivera en princip eller ange prioritetsordning för principer kan du läsa följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="8dbea-193">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="8dbea-194">Aktivera eller inaktivera principer för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="8dbea-194">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="8dbea-195">I säkerhets & Compliance Center kan du gå till **Threat Management** \> **policy** - \> **säkra bifogade filer**.</span><span class="sxs-lookup"><span data-stu-id="8dbea-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="8dbea-196">Observera värdet i kolumnen **status** :</span><span class="sxs-lookup"><span data-stu-id="8dbea-196">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="8dbea-197">Flytta reglaget till vänster</span><span class="sxs-lookup"><span data-stu-id="8dbea-197">Move the toggle to the left</span></span> ![Inaktivera princip](../../media/scc-toggle-off.png) <span data-ttu-id="8dbea-199">Om du vill inaktivera principen.</span><span class="sxs-lookup"><span data-stu-id="8dbea-199">to disable the policy.</span></span>

   - <span data-ttu-id="8dbea-200">Flytta reglaget till höger</span><span class="sxs-lookup"><span data-stu-id="8dbea-200">Move the toggle to the right</span></span> ![Aktivera princip](../../media/scc-toggle-on.png) <span data-ttu-id="8dbea-202">för att aktivera policyn.</span><span class="sxs-lookup"><span data-stu-id="8dbea-202">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="8dbea-203">Ange prioritet för principer för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="8dbea-203">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="8dbea-204">Som standard ges principer för säkra bifogade filer en prioritet som baseras på den ordning de skapades i (nyare principer är lägre prioritet än äldre regler).</span><span class="sxs-lookup"><span data-stu-id="8dbea-204">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="8dbea-205">Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet).</span><span class="sxs-lookup"><span data-stu-id="8dbea-205">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="8dbea-206">Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="8dbea-206">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="8dbea-207">För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="8dbea-207">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="8dbea-208">Principer för säkra bifogade filer visas i den ordning de behandlas (den första principen har **prioritet** svärdet 0).</span><span class="sxs-lookup"><span data-stu-id="8dbea-208">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="8dbea-209">**Obs!** i säkerhets & Compliance Center kan du bara ändra prioriteten för principen för säkra bifogade filer när du har skapat den.</span><span class="sxs-lookup"><span data-stu-id="8dbea-209">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="8dbea-210">I PowerShell kan du åsidosätta standard prioriteten när du skapar regeln för Safe Attachments (som kan påverka prioriteten för befintliga regler).</span><span class="sxs-lookup"><span data-stu-id="8dbea-210">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="8dbea-211">Du ändrar prioriteten för en princip genom att flytta principen uppåt eller nedåt i listan (du kan inte ändra **prioritetsnumret** direkt i Säkerhets- och efterlevnadscenter).</span><span class="sxs-lookup"><span data-stu-id="8dbea-211">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="8dbea-212">I säkerhets & Compliance Center kan du gå till **Threat Management** \> **policy** - \> **säkra bifogade filer**.</span><span class="sxs-lookup"><span data-stu-id="8dbea-212">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="8dbea-213">På sidan **betrodda bifogade filer** väljer du en princip i listan och klickar på den (markerar inte kryss rutan).</span><span class="sxs-lookup"><span data-stu-id="8dbea-213">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="8dbea-214">I den princip information som visas klickar du på knappen tillgänglig prioritet.</span><span class="sxs-lookup"><span data-stu-id="8dbea-214">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="8dbea-215">Principen för säkra bifogade filer med **prioritet** svärdet **0** har bara knappen **minska prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="8dbea-215">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="8dbea-216">Principen för säkra bifogade filer med lägst **prioritet** (till exempel **3**) har bara knappen **öka prioritet** tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="8dbea-216">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="8dbea-217">Om du har tre eller fler principer för säkra bifogade filer har principer mellan de högsta och lägsta prioriteterna både knappen **öka prioritet** och knappen för att **minska prioriteten** tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="8dbea-217">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="8dbea-218">Klicka på **öka prioritet** eller **minska prioritet** för att ändra **prioritet** svärdet.</span><span class="sxs-lookup"><span data-stu-id="8dbea-218">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="8dbea-219">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="8dbea-219">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="8dbea-220">Använda säkerhets & efterlevnad för att ta bort principer för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="8dbea-220">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="8dbea-221">I säkerhets & Compliance Center kan du gå till **Threat Management** \> **policy** - \> **säkra bifogade filer**.</span><span class="sxs-lookup"><span data-stu-id="8dbea-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="8dbea-222">På sidan **betrodda bifogade filer** väljer du en princip i listan och klickar på den (markerar inte kryss rutan).</span><span class="sxs-lookup"><span data-stu-id="8dbea-222">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="8dbea-223">I princip detaljerna som visas klickar du på **ta bort princip** och sedan på **Ja** i varnings dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="8dbea-223">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="8dbea-224">Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för skyddade bifogade filer</span><span class="sxs-lookup"><span data-stu-id="8dbea-224">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="8dbea-225">Som du redan har beskrivit innehåller en policy för säker bifogade filer och en regel för säker bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="8dbea-225">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="8dbea-226">I PowerShell är skillnaden mellan principer för säker bilaga och regler för säker bifogad fil synlig.</span><span class="sxs-lookup"><span data-stu-id="8dbea-226">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="8dbea-227">Du hanterar principer för säker bilaga genom att använda cmdletarna **\* -SafeAttachmentPolicy** och du hanterar regler för säkerhets bilagor genom att använda cmdlet **\* -SafeAttachmentRule** .</span><span class="sxs-lookup"><span data-stu-id="8dbea-227">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="8dbea-228">I PowerShell skapar du principen för säker bifogad fil först och skapar sedan regeln för säker bifogad fil som identifierar den princip som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="8dbea-228">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="8dbea-229">I PowerShell ändrar du inställningarna för principen för säker bifogad fil och regeln för säker bifogad fil separat.</span><span class="sxs-lookup"><span data-stu-id="8dbea-229">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="8dbea-230">När du tar bort en princip för en säker bifogad fil från PowerShell tas inte motsvarande regel för säker bilaga automatiskt bort och vice versa.</span><span class="sxs-lookup"><span data-stu-id="8dbea-230">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="8dbea-231">Använda PowerShell för att skapa principer för säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="8dbea-231">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="8dbea-232">Att skapa en policy för säker bifogad fil i PowerShell är en process i två steg:</span><span class="sxs-lookup"><span data-stu-id="8dbea-232">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="8dbea-233">Skapa principen för säker bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="8dbea-233">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="8dbea-234">Skapa regeln för säker bifogad fil som anger den policy för säker bifogad fil som regeln gäller för.</span><span class="sxs-lookup"><span data-stu-id="8dbea-234">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="8dbea-235">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="8dbea-235">**Notes**:</span></span>

- <span data-ttu-id="8dbea-236">Du kan skapa en ny regel för en säker bilaga och koppla en befintlig, icke associerad princip för säker bifogad fil till den.</span><span class="sxs-lookup"><span data-stu-id="8dbea-236">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="8dbea-237">En regel för säker bifogad fil kan inte kopplas till fler än en princip för säker bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="8dbea-237">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="8dbea-238">Du kan konfigurera följande inställningar i nya principer för säker bifogade filer i PowerShell som inte är tillgängliga i säkerhets & Compliance Center förrän du har skapat principen:</span><span class="sxs-lookup"><span data-stu-id="8dbea-238">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="8dbea-239">Skapa den nya principen som inaktive rad (_aktive rad_ `$false` på **New-SafeAttachmentRule-** cmdleten).</span><span class="sxs-lookup"><span data-stu-id="8dbea-239">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="8dbea-240">Ange prioriteten för principen när den skapas (_prioritet_ _\<Number\>_ ) på den **nya SafeAttachmentRule-** cmdleten.</span><span class="sxs-lookup"><span data-stu-id="8dbea-240">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="8dbea-241">En ny princip för säker bifogad fil som du skapar i PowerShell visas inte i säkerhets & Compliance Center förrän du tilldelar principen till en regel för säker bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="8dbea-241">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="8dbea-242">Steg 1: använda PowerShell för att skapa en policy för säker bifogad fil</span><span class="sxs-lookup"><span data-stu-id="8dbea-242">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="8dbea-243">Använd den här syntaxen om du vill skapa en policy för säker bifogad fil:</span><span class="sxs-lookup"><span data-stu-id="8dbea-243">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="8dbea-244">I det här exemplet skapas en policy för säker bifogad fil med namnet contoso alla med följande värden:</span><span class="sxs-lookup"><span data-stu-id="8dbea-244">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="8dbea-245">Blockera meddelanden som innehåller skadlig kod för genomsökning av säkra dokument (vi använder inte parametern _åtgärd_ och standardvärdet `Block` ).</span><span class="sxs-lookup"><span data-stu-id="8dbea-245">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="8dbea-246">Omdirigering är aktiverat och meddelanden som innehåller skadlig kod skickas till sec-ops@contoso.com för analys och undersökning.</span><span class="sxs-lookup"><span data-stu-id="8dbea-246">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="8dbea-247">Om det inte går att söka efter säkra bifogade filer eller om du stöter på fel ska du inte skicka meddelandet (vi använder inte parametern _ActionOnError_ och standardvärdet `$true` ).</span><span class="sxs-lookup"><span data-stu-id="8dbea-247">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="8dbea-248">Detaljerad information om syntax och parametrar finns i [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="8dbea-248">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="8dbea-249">Steg 2: använda PowerShell för att skapa en regel för säker bifogad fil</span><span class="sxs-lookup"><span data-stu-id="8dbea-249">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="8dbea-250">Använd den här syntaxen om du vill skapa en regel för en säker bifogad fil:</span><span class="sxs-lookup"><span data-stu-id="8dbea-250">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="8dbea-251">I det här exemplet skapas en Safe Attachment-regel med namnet contoso alla med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="8dbea-251">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="8dbea-252">Regeln kopplas till principen för säker bifogad fil med namnet contoso all.</span><span class="sxs-lookup"><span data-stu-id="8dbea-252">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="8dbea-253">Regeln gäller för alla mottagare i contoso.com-domänen.</span><span class="sxs-lookup"><span data-stu-id="8dbea-253">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="8dbea-254">Eftersom vi inte använder _prioritets_ parametern används standard prioriteten.</span><span class="sxs-lookup"><span data-stu-id="8dbea-254">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="8dbea-255">Regeln är aktive rad (vi använder inte den _aktiverade_ parametern och standardvärdet är `$true` ).</span><span class="sxs-lookup"><span data-stu-id="8dbea-255">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="8dbea-256">Detaljerad information om syntax och parametrar finns i [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="8dbea-256">For detailed syntax and parameter information, see [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="8dbea-257">Använda PowerShell för att visa principer för säker bifogad fil</span><span class="sxs-lookup"><span data-stu-id="8dbea-257">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="8dbea-258">Använd följande syntax för att visa befintliga principer för säker bifogade filer:</span><span class="sxs-lookup"><span data-stu-id="8dbea-258">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="8dbea-259">I det här exemplet returneras en sammanfattnings lista över alla principer för säker bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="8dbea-259">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="8dbea-260">I det här exemplet returneras detaljerad information för principen för säker bifogad fil med contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="8dbea-260">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="8dbea-261">Detaljerad information om syntax och parametrar finns i [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="8dbea-261">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="8dbea-262">Använda PowerShell för att visa regler för säkerhets bifogade filer</span><span class="sxs-lookup"><span data-stu-id="8dbea-262">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="8dbea-263">Använd följande syntax för att visa befintliga regler för säker bifogade filer:</span><span class="sxs-lookup"><span data-stu-id="8dbea-263">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="8dbea-264">I det här exemplet returneras en sammanfattande lista över alla regler för säker bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="8dbea-264">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="8dbea-265">Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="8dbea-265">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="8dbea-266">I det här exemplet returneras detaljerad information för regeln för den säkra bifogade filen contoso-chefer.</span><span class="sxs-lookup"><span data-stu-id="8dbea-266">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="8dbea-267">Detaljerad information om syntax och parametrar finns i [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="8dbea-267">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="8dbea-268">Använda PowerShell för att ändra principer för säker bifogad fil</span><span class="sxs-lookup"><span data-stu-id="8dbea-268">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="8dbea-269">Det går inte att byta namn på en policy för säker bifogad fil i PowerShell (cmdleten **set-SafeAttachmentPolicy** , har ingen _namn_ parameter).</span><span class="sxs-lookup"><span data-stu-id="8dbea-269">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="8dbea-270">När du byter namn på en princip för ett säkert bifogade filer i säkerhets & Compliance Center byts du bara namn på _regeln_ för säker bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="8dbea-270">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="8dbea-271">I annat fall är samma inställningar tillgängliga när du skapar en policy för säker bifogad fil enligt beskrivningen i [steg 1: använda PowerShell för att skapa en policy för säker bifogad fil](#step-1-use-powershell-to-create-a-safe-attachment-policy) i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="8dbea-271">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="8dbea-272">Använd den här syntaxen om du vill ändra en policy för en säker bifogad fil:</span><span class="sxs-lookup"><span data-stu-id="8dbea-272">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="8dbea-273">Detaljerad information om syntax och parametrar finns i [set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="8dbea-273">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="8dbea-274">Använda PowerShell för att ändra regler för säkerhets bifogade filer</span><span class="sxs-lookup"><span data-stu-id="8dbea-274">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="8dbea-275">Den enda inställning som inte är tillgänglig när du ändrar en regel för en säker bilaga i PowerShell är den _aktiverade_ parametern som gör att du kan skapa en inaktive rad regel.</span><span class="sxs-lookup"><span data-stu-id="8dbea-275">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="8dbea-276">Information om hur du aktiverar eller inaktiverar befintliga regler för säker bifogad fil finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="8dbea-276">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="8dbea-277">I annat fall är samma inställningar tillgängliga när du skapar en regel enligt beskrivningen i [steg 2: använda PowerShell för att skapa en regel för säker bifogad fil](#step-2-use-powershell-to-create-a-safe-attachment-rule) i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="8dbea-277">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="8dbea-278">Om du vill ändra en regel för en säker bifogad fil använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="8dbea-278">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="8dbea-279">Detaljerad information om syntax och parametrar finns i [set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="8dbea-279">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="8dbea-280">Använda PowerShell för att aktivera eller inaktivera regler för säker bifogad fil</span><span class="sxs-lookup"><span data-stu-id="8dbea-280">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="8dbea-281">Aktivering eller inaktive ring av en regel för säker bifogad fil i PowerShell aktiverar eller inaktiverar hela den här principen för bifogade filer (Safe Attachment-regeln).</span><span class="sxs-lookup"><span data-stu-id="8dbea-281">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="8dbea-282">Använd den här syntaxen om du vill aktivera eller inaktivera en regel för en säker bilaga i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8dbea-282">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="8dbea-283">I det här exemplet inaktive ras regeln för den säkra bifogade filen marknadsförings avdelningen.</span><span class="sxs-lookup"><span data-stu-id="8dbea-283">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="8dbea-284">I det här exemplet aktiveras samma regel.</span><span class="sxs-lookup"><span data-stu-id="8dbea-284">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="8dbea-285">Detaljerad information om syntax och parametrar finns i [Aktivera-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) och [disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="8dbea-285">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="8dbea-286">Använda PowerShell för att ange prioritet för regler för säker bifogad fil</span><span class="sxs-lookup"><span data-stu-id="8dbea-286">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="8dbea-287">Det högsta prioritetsvärde du kan ange för en regel är 0.</span><span class="sxs-lookup"><span data-stu-id="8dbea-287">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="8dbea-288">Det lägsta värde du kan ange beror på antalet regler.</span><span class="sxs-lookup"><span data-stu-id="8dbea-288">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="8dbea-289">Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4.</span><span class="sxs-lookup"><span data-stu-id="8dbea-289">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="8dbea-290">Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler.</span><span class="sxs-lookup"><span data-stu-id="8dbea-290">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="8dbea-291">Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.</span><span class="sxs-lookup"><span data-stu-id="8dbea-291">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="8dbea-292">Använd följande syntax för att ange prioriteten för en regel för en säker bilaga i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8dbea-292">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="8dbea-293">I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2.</span><span class="sxs-lookup"><span data-stu-id="8dbea-293">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="8dbea-294">Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’</span><span class="sxs-lookup"><span data-stu-id="8dbea-294">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="8dbea-295">**Obs!** om du vill ange prioriteten för en ny regel när du skapar den kan du använda _prioritets_ parametern i **New-SafeAttachmentRule** cmdlet i stället.</span><span class="sxs-lookup"><span data-stu-id="8dbea-295">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="8dbea-296">Detaljerad information om syntax och parametrar finns i [set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="8dbea-296">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="8dbea-297">Använda PowerShell för att ta bort principer för säker bifogad fil</span><span class="sxs-lookup"><span data-stu-id="8dbea-297">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="8dbea-298">När du använder PowerShell för att ta bort en princip för säker bifogad fil tas inte motsvarande regel för säker bifogad fil bort.</span><span class="sxs-lookup"><span data-stu-id="8dbea-298">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="8dbea-299">Använd den här syntaxen om du vill ta bort en princip för säker bifogad fil i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8dbea-299">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="8dbea-300">Det här exemplet tar bort policyn för säker bifogad fil med namnet marknadsförings avdelning.</span><span class="sxs-lookup"><span data-stu-id="8dbea-300">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="8dbea-301">Detaljerad information om syntax och parametrar finns i [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="8dbea-301">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="8dbea-302">Använda PowerShell för att ta bort regler för säker bilaga</span><span class="sxs-lookup"><span data-stu-id="8dbea-302">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="8dbea-303">När du använder PowerShell för att ta bort en regel för säker bifogad fil tas inte motsvarande princip för säker bifogad fil bort.</span><span class="sxs-lookup"><span data-stu-id="8dbea-303">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="8dbea-304">Använd den här syntaxen om du vill ta bort en regel för en säker bilaga i PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8dbea-304">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="8dbea-305">Det här exemplet tar bort regeln marknadsförings avdelning.</span><span class="sxs-lookup"><span data-stu-id="8dbea-305">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="8dbea-306">Detaljerad information om syntax och parametrar finns i [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="8dbea-306">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="8dbea-307">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="8dbea-307">How do you know these procedures worked?</span></span>

<span data-ttu-id="8dbea-308">Gör något av följande om du vill kontrol lera att du har skapat, ändrat eller tagit bort principer för säker bifogade filer:</span><span class="sxs-lookup"><span data-stu-id="8dbea-308">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="8dbea-309">I säkerhets & Compliance Center kan du gå till **Threat Management** \> **policy** - \> **säkra bifogade filer**.</span><span class="sxs-lookup"><span data-stu-id="8dbea-309">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="8dbea-310">Verifiera listan med principer, deras **status** värden och deras **prioriterade** värden.</span><span class="sxs-lookup"><span data-stu-id="8dbea-310">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="8dbea-311">Om du vill visa mer information väljer du den i listan och visar detaljerna i Lägg utåt.</span><span class="sxs-lookup"><span data-stu-id="8dbea-311">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="8dbea-312">I Exchange Online PowerShell eller Exchange Online Protection PowerShell ersätter du \<Name\> med namnet på principen eller regeln, kör följande kommando och kontrollerar inställningarna:</span><span class="sxs-lookup"><span data-stu-id="8dbea-312">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="8dbea-313">Kontrol lera att de säkra bifogade filerna skannar meddelanden genom att titta i de tillgängliga Defender för Office 365-rapporterna.</span><span class="sxs-lookup"><span data-stu-id="8dbea-313">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="8dbea-314">Mer information finns i [Visa rapporter för Defender för Office 365](view-reports-for-atp.md) och [använda utforskaren i säkerhets & Compliance Center](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="8dbea-314">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
