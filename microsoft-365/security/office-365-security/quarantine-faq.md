---
title: Vanliga frågor och svar om meddelanden i karantän
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratörer kan visa vanliga frågor och svar om meddelanden i karantän i Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 019f1c103ef1aaf7641072cd1259d22e83f0de4c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166933"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="203f4-103">Vanliga frågor och svar om meddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="203f4-103">Quarantined messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="203f4-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="203f4-104">**Applies to**</span></span>
- [<span data-ttu-id="203f4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="203f4-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="203f4-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="203f4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="203f4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="203f4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="203f4-108">Det här avsnittet innehåller vanliga frågor och svar om e-postmeddelanden i karantän för Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="203f4-108">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="203f4-109">Frågor och svar om skydd mot skräppost finns i Vanliga frågor och svar om skydd mot [skräppost.](anti-spam-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="203f4-109">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="203f4-110">Frågor och svar om skydd mot skadlig programvara finns i Vanliga frågor och svar om skydd mot [skadlig programvara.](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="203f4-110">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="203f4-111">Frågor och svar om skydd mot förfalskning finns i Vanliga frågor och svar om skydd mot [förfalskning.](anti-spoofing-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="203f4-111">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="203f4-112">Hur hanterar jag meddelanden som har satts i karantän för skadlig programvara?</span><span class="sxs-lookup"><span data-stu-id="203f4-112">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="203f4-113">Endast administratörer kan hantera meddelanden som har satts i karantän för skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="203f4-113">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="203f4-114">Mer information finns i [Hantera meddelanden i karantän och filer som administratör.](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="203f4-114">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="203f4-115">Hur sätt jag i karantän för skräppost?</span><span class="sxs-lookup"><span data-stu-id="203f4-115">How do I quarantine spam?</span></span>

<span data-ttu-id="203f4-116">Som standard levereras meddelanden som klassificeras som skräppost eller massutskick av skräppostfiltrering till användarens postlåda och flyttas till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="203f4-116">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="203f4-117">Men du kan skapa och konfigurera principer för skräppostskydd för att sätta skräppost i karantän eller massutskick av e-postmeddelanden i stället.</span><span class="sxs-lookup"><span data-stu-id="203f4-117">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="203f4-118">Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="203f4-118">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="203f4-119">Hur ger jag användare tillgång till karantän?</span><span class="sxs-lookup"><span data-stu-id="203f4-119">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="203f4-120">En användare måste ha ett giltigt konto för att komma åt sina egna meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="203f4-120">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="203f4-121">Fristående EOP kräver att användare representeras som e-postanvändare i EOP (skapas eller skapas manuellt via katalogsynkronisering).</span><span class="sxs-lookup"><span data-stu-id="203f4-121">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="203f4-122">Mer information om hur du hanterar användare i fristående EOP-miljöer finns i [Hantera e-postanvändare i EOP.](manage-mail-users-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="203f4-122">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="203f4-123">Vilka meddelanden kan slutanvändarna få åtkomst till i karantän?</span><span class="sxs-lookup"><span data-stu-id="203f4-123">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="203f4-124">Användare kan komma åt skräppost, massutskick och nätfiskemeddelanden i april 2020 där de är mottagare.</span><span class="sxs-lookup"><span data-stu-id="203f4-124">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="203f4-125">Slutanvändarna kan inte komma åt skadlig programvara i karantän, nätfiske med hög konfidens eller meddelanden som satts i karantän på grund av åtgärden Leverera meddelandet till den värdinde karantänen i e-postflödesregler (kallas även transportregler). </span><span class="sxs-lookup"><span data-stu-id="203f4-125">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="203f4-126">Mer information om användare som får åtkomst till meddelanden i karantän finns i [Hitta och släppa meddelanden i karantän som användare.](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="203f4-126">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="203f4-127">Hur länge sparas meddelanden i karantän?</span><span class="sxs-lookup"><span data-stu-id="203f4-127">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="203f4-128">Du konfigurerar hur länge skräppost, nätfiske och massutskick av e-postmeddelanden sparas i karantän genom att använda principer för skydd mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="203f4-128">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="203f4-129">Standardvärdet är 30 dagar, vilket också är det högsta.</span><span class="sxs-lookup"><span data-stu-id="203f4-129">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="203f4-130">Mer information finns i Konfigurera [principer för skydd mot skräppost i EOP](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="203f4-130">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="203f4-131">För meddelanden som satts i karantän av åtgärden e-postflödesregel leverera meddelandet till den värdinde karantänen, lagras meddelandena i karantän i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="203f4-131">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="203f4-132">Du kan inte konfigurera den här varaktigheten.</span><span class="sxs-lookup"><span data-stu-id="203f4-132">You can't configure this duration.</span></span>

<span data-ttu-id="203f4-133">När tidsperioden gått ut tas meddelandena bort och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="203f4-133">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="203f4-134">Kan jag släppa eller rapportera fler än ett meddelande i karantän åt gången?</span><span class="sxs-lookup"><span data-stu-id="203f4-134">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="203f4-135">I Säkerhets- & efterlevnadscenter kan du välja och släppa upp till 100 meddelanden i taget.</span><span class="sxs-lookup"><span data-stu-id="203f4-135">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="203f4-136">Administratörer kan använda cmdlet:arna [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) och [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) i Exchange Online PowerShell eller fristående EOP PowerShell för att hitta och släppa meddelanden i karantän samtidigt som de rapporterar falska positiva meddelanden i grupp.</span><span class="sxs-lookup"><span data-stu-id="203f4-136">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="203f4-137">Stöds jokertecken vid sökning efter meddelanden i karantän?</span><span class="sxs-lookup"><span data-stu-id="203f4-137">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="203f4-138">Kan jag söka efter meddelanden i karantän för en viss domän?</span><span class="sxs-lookup"><span data-stu-id="203f4-138">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="203f4-139">Jokertecken stöds inte i Säkerhets- & Säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="203f4-139">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="203f4-140">När du söker efter en avsändare måste du till exempel ange den fullständiga e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="203f4-140">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="203f4-141">Men du kan använda jokertecken i Exchange Online PowerShell eller fristående EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="203f4-141">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="203f4-142">Kopiera till exempel följande PowerShell-kod i Anteckningar och spara filen som .ps1 på en plats som är lätt att hitta (till exempel C:\Data\QuarantineRelease.ps1).</span><span class="sxs-lookup"><span data-stu-id="203f4-142">For example, copy the following PowerShell code into NotePad and save the file as .ps1 in a location that's easy for you to find (for example, C:\Data\QuarantineRelease.ps1).</span></span>

<span data-ttu-id="203f4-143">När du sedan ansluter till [Exchange Online PowerShell eller](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) Exchange Online Protection [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)kör du följande kommando för att köra skriptet:</span><span class="sxs-lookup"><span data-stu-id="203f4-143">Then, after you connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) or [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell), run the following command to run the script:</span></span>

```powershell
& C:\Data\QuarantineRelease.ps1
```

<span data-ttu-id="203f4-144">Skriptet gör följande:</span><span class="sxs-lookup"><span data-stu-id="203f4-144">The script does the following actions:</span></span>

- <span data-ttu-id="203f4-145">Hitta outgivna meddelanden som satts i karantän som skräppost från alla avsändare på fabrikam-domänen.</span><span class="sxs-lookup"><span data-stu-id="203f4-145">Find unreleased messages that were quarantined as spam from all senders in the fabrikam domain.</span></span> <span data-ttu-id="203f4-146">Det maximala antalet resultat är 50 000 (50 sidor med 1 000 resultat).</span><span class="sxs-lookup"><span data-stu-id="203f4-146">The maximum number of results is 50,000 (50 pages of 1000 results).</span></span>
- <span data-ttu-id="203f4-147">Spara resultatet i en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="203f4-147">Save the results to a CSV file.</span></span>
- <span data-ttu-id="203f4-148">Släpp matchande meddelanden i karantän till alla ursprungliga mottagare.</span><span class="sxs-lookup"><span data-stu-id="203f4-148">Release the matching quarantined messages to all original recipients.</span></span>

```powershell
$Page = 1
$List = $null

Do
{
Write-Host "Getting Page " $Page

$List = (Get-QuarantineMessage -Type Spam -PageSize 1000 -Page $Page | where {$_.Released -like "False" -and $_.SenderAddress -like "*fabrikam.com"})
Write-Host "                     " $List.count " rows in this page match"
Write-Host "                                                             Exporting list to appended CSV for logging"
$List | Export-Csv -Path "C:\Data\Quarantined Message Matches.csv" -Append -NoTypeInformation

Write-Host "Releasing page " $Page
$List | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}

$Page = $Page + 1

} Until ($Page -eq 50)
```

<span data-ttu-id="203f4-149">När du släppt ett meddelande kan du inte släppa det igen.</span><span class="sxs-lookup"><span data-stu-id="203f4-149">After you release a message, you can't release it again.</span></span>
