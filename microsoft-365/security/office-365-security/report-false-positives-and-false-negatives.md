---
title: Rapportera falska positiva och falska negativa i Outlook
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Lär dig hur du rapporterar falska positiva och falska negativa Outlook i funktionen Rapportmeddelande.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 84a5b697f8a4b46cf79c542485bfafb396328f5c
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789249"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="a1521-103">Rapportera falska positiva och falska negativa i Outlook</span><span class="sxs-lookup"><span data-stu-id="a1521-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a1521-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="a1521-104">**Applies to**</span></span>
- [<span data-ttu-id="a1521-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a1521-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a1521-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="a1521-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a1521-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1521-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="a1521-108">Om du är administratör i en Microsoft 365 organisation med Exchange Online postlådor rekommenderar vi att du använder portalen för inskickade inskickade material i Säkerhets- & efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="a1521-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="a1521-109">Mer information finns i Använda [administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="a1521-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="a1521-110">I Microsoft 365-organisationer med postlådor i Exchange Online eller lokala postlådor med modern hybridautentisering kan du skicka falska positiva identifieringar (bra e-postmeddelanden som har blockerats eller skickats till skräppostmappen) och falska negativa identifieringar (oönskad e-post eller nätfingr som skickats till inkorgen) till Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="a1521-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a1521-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="a1521-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a1521-112">För bästa möjliga användarinskickning använder du tilläggen Rapportmeddelande eller Rapport nätfiske.</span><span class="sxs-lookup"><span data-stu-id="a1521-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="a1521-113">Den inbyggda upplevelsen för att rapportera skräppost och nätfiske i Outlook kan inte använda principen [för användarinskicking.](./user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="a1521-113">The built-in experience for reporting junk or phishing in Outlook can't use the [user submission policy](./user-submission.md).</span></span> <span data-ttu-id="a1521-114">Vi rekommenderar att du använder tilläggen Rapportmeddelande eller Nätfiskerapport i stället.</span><span class="sxs-lookup"><span data-stu-id="a1521-114">We recommend using the Report Message add-in or the Report Phishing add-in instead.</span></span>

- <span data-ttu-id="a1521-115">Tillägget Rapportmeddelande och tillägget Rapport nätfiske fungerar för alla Outlook plattformar (Outlook på webben, iOS, Android och skrivbordet).</span><span class="sxs-lookup"><span data-stu-id="a1521-115">The the Report Message add-in and the Report Phishing add-in work for Outlook in all platforms (Outlook on the web, iOS, Android, and Desktop).</span></span>

- <span data-ttu-id="a1521-116">Om du är administratör i en organisation med Exchange Online postlådor använder du portalen för inskickade inskickade uppgifter i säkerhets- & efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="a1521-116">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="a1521-117">Mer information finns i Använda [administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="a1521-117">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="a1521-118">Du kan konfigurera så att meddelanden skickas direkt till Microsoft, en postlåda som du anger eller båda.</span><span class="sxs-lookup"><span data-stu-id="a1521-118">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="a1521-119">Mer information finns i Principer [för användarinskick.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="a1521-119">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="a1521-120">Mer information om hur du hämtar och aktiverar rapportmeddelandet eller tilläggen för rapportfiske finns i Aktivera rapportmeddelandet eller tilläggen för [rapportfiske.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="a1521-120">For more information on how to get and enable the Report Message or the Report Phishing add-ins, see [Enable the Report Message or the Report Phishing add-ins](enable-the-report-message-add-in.md).</span></span>

- <span data-ttu-id="a1521-121">Mer information om hur du rapporterar meddelanden till Microsoft finns [i Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="a1521-121">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="a1521-122">Använda funktionen Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="a1521-122">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="a1521-123">Rapportera skräppost och nätfiskemeddelanden</span><span class="sxs-lookup"><span data-stu-id="a1521-123">Report junk and phishing messages</span></span>

<span data-ttu-id="a1521-124">För meddelanden i Inkorgen eller någon annan e-postmapp utom Skräppost använder du följande metod för att rapportera skräppost och nätfiske:</span><span class="sxs-lookup"><span data-stu-id="a1521-124">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="a1521-125">Välj **ellipsen** Fler åtgärder längst upp till höger i det markerade meddelandet, välj **Rapportera** meddelande i listrutan och välj sedan **Skräppost** eller **Nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="a1521-125">Select the **More actions** ellipses on the top-right corner of the selected message, select **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>

   ![Rapportmeddelande – fler åtgärder](../../media/report-message-more-actions.png)
   
   ![Rapportmeddelande – skräppost och nätfiske](../../media/report-message-junk-phishing.png)

2. <span data-ttu-id="a1521-128">De valda meddelandena skickas till Microsoft för analys och:</span><span class="sxs-lookup"><span data-stu-id="a1521-128">The selected messages will be sent to Microsoft for analysis and:</span></span>
   - <span data-ttu-id="a1521-129">Flyttades till mappen Skräppost om de rapporterades som skräppost.</span><span class="sxs-lookup"><span data-stu-id="a1521-129">Moved to the Junk Email folder if they were reported as spam.</span></span>
   - <span data-ttu-id="a1521-130">Borttagna om de rapporterats som nätfiske.</span><span class="sxs-lookup"><span data-stu-id="a1521-130">Deleted if they were reported as phishing.</span></span>

### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="a1521-131">Rapportera meddelanden som inte är skräppost</span><span class="sxs-lookup"><span data-stu-id="a1521-131">Report messages that are not junk</span></span>

1. <span data-ttu-id="a1521-132">Välj **ellipsen** Fler åtgärder i det övre högra hörnet av det markerade meddelandet, välj **Rapportera** meddelande i listrutan och välj sedan **Inte skräppost.**</span><span class="sxs-lookup"><span data-stu-id="a1521-132">Select the **More actions** ellipses on the top-right corner of the selected message, select **Report message** from the dropdown menu, and then select **Not Junk**.</span></span>

   ![Rapportmeddelande – fler åtgärder](../../media/report-message-more-actions.png)
   
   ![Rapportmeddelande – inte skräppost](../../media/report-message-not-junk.png)

2. <span data-ttu-id="a1521-135">Det markerade meddelandet skickas till Microsoft för analys och flyttas till Inkorgen eller någon annan angiven mapp.</span><span class="sxs-lookup"><span data-stu-id="a1521-135">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="a1521-136">Visa och granska rapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="a1521-136">View and review reported messages</span></span>

<span data-ttu-id="a1521-137">Om du vill granska meddelanden som användare rapporterar till Microsoft har du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="a1521-137">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="a1521-138">Använd portalen för administrationsinskick.</span><span class="sxs-lookup"><span data-stu-id="a1521-138">Use the Admin Submissions portal.</span></span> <span data-ttu-id="a1521-139">Mer information finns i [Visa användarinskick till Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="a1521-139">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>
- <span data-ttu-id="a1521-140">Skapa en e-postflödesregel (kallas även transportregel) för att skicka kopior av rapporterade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="a1521-140">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="a1521-141">Instruktioner finns i Använda [e-postflödesregler för att se vad användarna rapporterar till Microsoft.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="a1521-141">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>
