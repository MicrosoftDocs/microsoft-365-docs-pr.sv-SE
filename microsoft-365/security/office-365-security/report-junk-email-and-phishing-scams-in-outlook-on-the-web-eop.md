---
title: Rapportera skräppost och nätfiske i Outlook på webben
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa mer om de inbyggda alternativen för skräppost, inte skräppost och nätfiske i Outlook på webben (Outlook Web App) i Exchange Online, och hur de inaktiverar rapporteringsalternativen för användare.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1139871f5929ff9fef29e980b7614e5bc7b92570
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788313"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="d09d8-103">Rapportera skräppost och nätfiske i Outlook på webben i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d09d8-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d09d8-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="d09d8-104">**Applies to**</span></span>
- [<span data-ttu-id="d09d8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d09d8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d09d8-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="d09d8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d09d8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d09d8-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="d09d8-108">I Microsoft 365 organisationer med postlådor i Exchange Online eller lokala postlådor med [modern hybridautentisering](../../enterprise/hybrid-modern-auth-overview.md)kan du skicka falska positiva identifieringar (bra e-post som har markerats som skräppost), falska negativa identifieringar (felaktig e-post tillåts) och nätfiskemeddelanden till Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="d09d8-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d09d8-109">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="d09d8-109">What do you need to know before you begin?</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d09d8-110">Vi rekommenderar tilläggen Rapportmeddelande eller Rapportera nätfiske för användarinskick.</span><span class="sxs-lookup"><span data-stu-id="d09d8-110">We recommend the Report Message add-in or the Report Phishing add-in for user submissions.</span></span> <span data-ttu-id="d09d8-111">Mer information finns i [Aktivera rapportmeddelandet eller tilläggen för rapportfiske.](./enable-the-report-message-add-in.md) Vi rekommenderar inte den inbyggda rapporteringsupplevelsen i Outlook eftersom den inte kan använda principen för [användarinskicking.](./user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="d09d8-111">For more information, see [Enable the Report Message or the Report Phishing add-ins](./enable-the-report-message-add-in.md). We don't recommend the built-in reporting experience in Outlook because it can't use the [user submission policy](./user-submission.md).</span></span>

- <span data-ttu-id="d09d8-112">Om du är administratör i en organisation med Exchange Online postlådor rekommenderar vi att du använder portalen för sändning i Säkerhets- & efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="d09d8-112">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="d09d8-113">Mer information finns i Använda [administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="d09d8-113">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="d09d8-114">Administratörer kan inaktivera eller aktivera möjligheten för användare att rapportera meddelanden till Microsoft i Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="d09d8-114">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="d09d8-115">Mer information finns i [avsnittet Inaktivera eller aktivera skräppostrapportering i Outlook på webben längre](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="d09d8-115">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="d09d8-116">Du kan konfigurera rapporterade meddelanden så att de kopieras eller omdirigeras till en postlåda som du anger.</span><span class="sxs-lookup"><span data-stu-id="d09d8-116">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="d09d8-117">Mer information finns i Principer [för användarinskick.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="d09d8-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="d09d8-118">Mer information om hur du rapporterar meddelanden till Microsoft finns [i Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="d09d8-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="d09d8-119">Inaktivera eller aktivera skräppostrapportering i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="d09d8-119">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="d09d8-120">Som standard kan användare rapportera falska positiva meddelanden som skräppost, falska negativa tal och nätfiskemeddelanden till Microsoft för analys Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="d09d8-120">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="d09d8-121">Administratörer kan konfigurera Outlook på principer för webbpostlådor i Exchange Online PowerShell för att hindra användare från att rapportera skräppost som falska positiva identifieringar och falskt negativa identifieringar av skräppost till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d09d8-121">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="d09d8-122">Du kan inte inaktivera möjligheten för användare att rapportera nätfiskemeddelanden till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d09d8-122">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d09d8-123">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="d09d8-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d09d8-124">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d09d8-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="d09d8-125">Du måste ha tilldelats behörigheter i Exchange Online innan du kan utföra procedurerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="d09d8-125">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="d09d8-126">Specifikt behöver du **rollerna Mottagarprinciper** eller E-postmottagare, som tilldelas rollgrupperna **Organisationshantering** och **Mottagarhantering** som standard. </span><span class="sxs-lookup"><span data-stu-id="d09d8-126">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="d09d8-127">Mer information om rollgrupper i Exchange Online finns i [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo) och Ändra [rollgrupper i Exchange Online.](/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="d09d8-127">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="d09d8-128">Varje organisation har en standardprincip som heter OwaMailboxPolicy-Default, men du kan skapa anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="d09d8-128">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="d09d8-129">Anpassade principer tillämpas på begränsade användare före standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="d09d8-129">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="d09d8-130">Mer information om Outlook webbpostlådeprinciper finns i Outlook på principer för [webbpostlådor i Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span><span class="sxs-lookup"><span data-stu-id="d09d8-130">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="d09d8-131">Om du inaktiverar skräppostrapporteringen inaktiveras inte möjligheten att markera ett meddelande som skräppost eller inte skräppost i Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="d09d8-131">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="d09d8-132">Om du markerar ett meddelande i mappen Skräppost och **klickar på Inte** skräppost Flyttar du fortfarande tillbaka meddelandet till \>  Inkorgen.</span><span class="sxs-lookup"><span data-stu-id="d09d8-132">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="d09d8-133">Om du markerar ett meddelande  i en annan e-postmapp och klickar på Skräppost \>  flyttas det fortfarande till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="d09d8-133">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="d09d8-134">Vad som inte längre är tillgängligt är alternativet att rapportera meddelandet till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d09d8-134">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="d09d8-135">Använda Exchange Online PowerShell för att inaktivera eller aktivera skräppostrapportering i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="d09d8-135">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="d09d8-136">Om du vill hitta Outlook information om postlådeprinciperna för webben och status för skräppostrapportering kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="d09d8-136">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="d09d8-137">Inaktivera eller aktivera skräppostrapportering i Outlook på webben med följande syntax:</span><span class="sxs-lookup"><span data-stu-id="d09d8-137">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="d09d8-138">Det här exemplet inaktiverar skräppostrapportering i standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="d09d8-138">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="d09d8-139">I det här exemplet möjliggörs rapportering av skräppost i den anpassade principen contoso-hanterare.</span><span class="sxs-lookup"><span data-stu-id="d09d8-139">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="d09d8-140">Detaljerad information om syntax och parametrar finns i [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) och [Set-OwaMailboxPolicy.](/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="d09d8-140">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="d09d8-141">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="d09d8-141">How do you know this worked?</span></span>

<span data-ttu-id="d09d8-142">Kontrollera att du har aktiverat eller inaktiverat skräppostrapportering i Outlook på webben genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="d09d8-142">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="d09d8-143">I Exchange Online PowerShell kör du följande kommando och verifierar värdet för egenskapen **ReportJunkEmailEnabled:**</span><span class="sxs-lookup"><span data-stu-id="d09d8-143">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="d09d8-144">Öppna en användares postlåda i Outlook på webben, markera ett meddelande  i Inkorgen, klicka på Skräppost och kontrollera att meddelandet inte visas eller \>  inte.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d09d8-144">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="d09d8-145">Öppna en användares postlåda i Outlook på webben, markera ett meddelande i  mappen Skräppost, klicka på Skräppost och kontrollera att meddelandet visas eller \>  inte.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d09d8-145">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="d09d8-146"><sup>\*</sup> Användare kan dölja uppmaningen att rapportera meddelandet samtidigt som de rapporterar meddelandet.</span><span class="sxs-lookup"><span data-stu-id="d09d8-146"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="d09d8-147">Så här kontrollerar du den Outlook på webben:</span><span class="sxs-lookup"><span data-stu-id="d09d8-147">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="d09d8-148">Klicka **Inställningar** ![ Outlook på ikonen för webbinställningar ](../../media/owa-settings-icon.png) \> **Visa Outlook alla inställningar** \> **Skräppost.**</span><span class="sxs-lookup"><span data-stu-id="d09d8-148">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="d09d8-149">Kontrollera värdet **i** avsnittet Rapportering: Fråga **innan du skickar en rapport**.</span><span class="sxs-lookup"><span data-stu-id="d09d8-149">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Outlook för skräppostrapportering på webben](../../media/owa-junk-email-reporting-options.png)
