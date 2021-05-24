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
ms.openlocfilehash: 6f8c4fc327bfd467cdd1d0043c454e222e84125c
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625119"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="9875c-103">Rapportera falska positiva och falska negativa i Outlook</span><span class="sxs-lookup"><span data-stu-id="9875c-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9875c-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="9875c-104">**Applies to**</span></span>
- [<span data-ttu-id="9875c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9875c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9875c-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="9875c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9875c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9875c-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="9875c-108">Om du är administratör i en Microsoft 365 organisation med Exchange Online postlådor rekommenderar vi att du använder portalen för inskickade inskickade material i Säkerhets- & efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="9875c-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="9875c-109">Mer information finns i Använda [administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="9875c-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="9875c-110">I Microsoft 365-organisationer med postlådor i Exchange Online eller lokala postlådor med modern hybridautentisering kan du skicka falska positiva identifieringar (bra e-postmeddelanden som har blockerats eller skickats till skräppostmappen) och falska negativa identifieringar (oönskad e-post eller nätfingr som skickats till inkorgen) till Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="9875c-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email that was blocked or sent to junk folder) and false negatives (unwanted email or phish that was delivered to the inbox) to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9875c-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="9875c-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9875c-112">För bästa möjliga användarinskickning använder du tilläggen Rapportmeddelande eller Rapport nätfiske.</span><span class="sxs-lookup"><span data-stu-id="9875c-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

- <span data-ttu-id="9875c-113">Observera att det här tillägget fungerar för Outlook plattformar – på webben, iOS, Android och skrivbordet.</span><span class="sxs-lookup"><span data-stu-id="9875c-113">Note that this add-in works for Outlook in all platforms—on the web, iOS, Android, and Desktop.</span></span>

- <span data-ttu-id="9875c-114">Om du är administratör i en organisation med Exchange Online postlådor använder du portalen för inskickade inskickade uppgifter i säkerhets- & efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="9875c-114">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="9875c-115">Mer information finns i Använda [administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="9875c-115">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="9875c-116">Du kan konfigurera så att meddelanden skickas direkt till Microsoft, en postlåda som du anger eller båda.</span><span class="sxs-lookup"><span data-stu-id="9875c-116">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="9875c-117">Mer information finns i Principer [för användarinskick.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="9875c-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="9875c-118">Mer information om hur du hämtar och aktiverar rapportmeddelandet eller tilläggen för rapportfiske finns i Aktivera rapportmeddelandet eller tilläggen för [rapportfiske.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="9875c-118">For more information on how to get and enable the Report Message or the Report Phishing add-ins, see [Enable the Report Message or the Report Phishing add-ins](enable-the-report-message-add-in.md).</span></span>

- <span data-ttu-id="9875c-119">Mer information om hur du rapporterar meddelanden till Microsoft finns [i Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="9875c-119">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="9875c-120">Använda funktionen Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="9875c-120">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="9875c-121">Rapportera skräppost och nätfiskemeddelanden</span><span class="sxs-lookup"><span data-stu-id="9875c-121">Report junk and phishing messages</span></span>

<span data-ttu-id="9875c-122">För meddelanden i Inkorgen eller någon annan e-postmapp utom Skräppost använder du följande metod för att rapportera skräppost och nätfiske:</span><span class="sxs-lookup"><span data-stu-id="9875c-122">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="9875c-123">Klicka på **ellipsen** Fler åtgärder längst upp till höger  i det markerade meddelandet, klicka på Rapportera meddelande i den nedrullningsbara menyn och välj sedan **Skräppost** eller **Nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="9875c-123">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9875c-124">![Rapportmeddelande – fler åtgärder](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="9875c-124">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9875c-125">![Rapportmeddelande – skräppost och nätfiske](../../media/report-message-junk-phishing.png)</span><span class="sxs-lookup"><span data-stu-id="9875c-125">![Report Message - Junk and Phishing](../../media/report-message-junk-phishing.png)</span></span>

2. <span data-ttu-id="9875c-126">De valda meddelandena skickas till Microsoft för analys och:</span><span class="sxs-lookup"><span data-stu-id="9875c-126">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="9875c-127">Flyttades till mappen Skräppost om den rapporterades som skräppost.</span><span class="sxs-lookup"><span data-stu-id="9875c-127">Moved to the Junk Email folder if it was reported as spam.</span></span>

   - <span data-ttu-id="9875c-128">Borttagna om det har rapporterats som nätfiske.</span><span class="sxs-lookup"><span data-stu-id="9875c-128">Deleted if it was reported as phishing.</span></span>

### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="9875c-129">Rapportera meddelanden som inte är skräppost</span><span class="sxs-lookup"><span data-stu-id="9875c-129">Report messages that are not junk</span></span>

1. <span data-ttu-id="9875c-130">Klicka på **ellipsen** Fler åtgärder i det övre högra  hörnet av det markerade meddelandet, klicka på Rapportera meddelande i den nedrullningsbara menyn och klicka sedan **på Inte skräppost.**</span><span class="sxs-lookup"><span data-stu-id="9875c-130">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then click **Not Junk**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9875c-131">![Rapportmeddelande – fler åtgärder](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="9875c-131">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9875c-132">![Rapportmeddelande – inte skräppost](../../media/report-message-not-junk.png)</span><span class="sxs-lookup"><span data-stu-id="9875c-132">![Report Message - Not junk](../../media/report-message-not-junk.png)</span></span>

2. <span data-ttu-id="9875c-133">Det markerade meddelandet skickas till Microsoft för analys och flyttas till Inkorgen eller någon annan angiven mapp.</span><span class="sxs-lookup"><span data-stu-id="9875c-133">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="9875c-134">Visa och granska rapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="9875c-134">View and review reported messages</span></span>

<span data-ttu-id="9875c-135">Om du vill granska meddelanden som användare rapporterar till Microsoft har du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="9875c-135">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="9875c-136">Använd portalen för administrationsinskick.</span><span class="sxs-lookup"><span data-stu-id="9875c-136">Use the Admin Submissions portal.</span></span> <span data-ttu-id="9875c-137">Mer information finns i [Visa användarinskick till Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="9875c-137">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="9875c-138">Skapa en e-postflödesregel (kallas även transportregel) för att skicka kopior av rapporterade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="9875c-138">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="9875c-139">Instruktioner finns i Använda [e-postflödesregler för att se vad användarna rapporterar till Microsoft.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="9875c-139">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>
