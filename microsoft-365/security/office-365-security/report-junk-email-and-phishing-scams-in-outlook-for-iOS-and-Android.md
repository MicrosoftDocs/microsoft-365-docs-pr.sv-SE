---
title: Rapportera skräp post och nätfiske i Outlook för iOS och Android
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
description: Administratörer kan läsa om de inbyggda skräp posten, inte skräp post och nätfiske-alternativen i Outlook för iOS och Android.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d702ab1d97c07c3e38430a9a7beff5f14db7b60a
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029286"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="17151-103">Rapportera skräp post och nätfiske i Outlook för iOS och Android i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="17151-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="17151-104">I Microsoft 365-organisationer med post lådor i Exchange Online eller lokala post lådor med [hybrid modern inloggningsautentisering](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)kan du använda de inbyggda rapporterings alternativen i Outlook för iOS och Android för att skicka falska positiva (e-postmeddelanden markerade som skräp post), falskt negativ (dålig e-post) och nätfiske-meddelanden till Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="17151-104">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="17151-105">Vad behöver du veta innan du börjar</span><span class="sxs-lookup"><span data-stu-id="17151-105">What do you need to know before you begin</span></span>

- <span data-ttu-id="17151-106">Om du är administratör i en organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen för säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="17151-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="17151-107">Mer information finns i [använda administratörs överföring för att skicka misstänkt skräp post, Phish, URL: er och filer till Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="17151-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="17151-108">Du kan konfigurera vilka meddelanden som ska kopieras eller dirigeras om till en post låda som du anger.</span><span class="sxs-lookup"><span data-stu-id="17151-108">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="17151-109">Mer information finns i [principer för användar profiler](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="17151-109">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="17151-110">Mer information om hur du rapporterar meddelanden till Microsoft finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="17151-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="17151-111">Om skräp post rapportering är inaktiverat för Outlook i princip för användar överföring flyttas skräp post eller nätfiske-meddelanden till skräppostmappen och inte rapporteras till din administratör eller Microsoft.</span><span class="sxs-lookup"><span data-stu-id="17151-111">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="17151-112">Rapportera skräp post och nät fiske meddelanden i Outlook för iOS och Android</span><span class="sxs-lookup"><span data-stu-id="17151-112">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="17151-113">Använd följande steg för att rapportera skräp post och nät fiske meddelanden för iOS och Android för meddelanden i Inkorgen, eller annan e-postmapp, utom skräp posten:</span><span class="sxs-lookup"><span data-stu-id="17151-113">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="17151-114">Markera ett eller flera meddelanden.</span><span class="sxs-lookup"><span data-stu-id="17151-114">Select one or more messages.</span></span>
2. <span data-ttu-id="17151-115">I det övre högra hörnet trycker du på de tre lodräta punkterna.</span><span class="sxs-lookup"><span data-stu-id="17151-115">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="17151-116">Åtgärd-menyn öppnas.</span><span class="sxs-lookup"><span data-stu-id="17151-116">The action menu opens.</span></span>

   ![Rapportera skräp post eller nätfiske via åtgärd-menyn](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="17151-118">Tryck på **Rapportera skräp post** och välj sedan **skräp** post eller **nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="17151-118">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![Rapportera skräp post eller nätfiske](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="17151-120">I dialog rutan som visas kan du välja **rapport** eller **Nej**.</span><span class="sxs-lookup"><span data-stu-id="17151-120">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="17151-121">Om du väljer **Nej**, om du tryckte på **skräp** post flyttas meddelandet till mappen skräp post om du tryckte på **nätfiske** flyttas meddelandet till mappen Borttaget.</span><span class="sxs-lookup"><span data-stu-id="17151-121">On selecting **No Thanks**, if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="17151-122">Välj **rapport** om du även vill skicka en kopia av meddelandet till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="17151-122">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![Rapportera alternativ för skräp post eller nätfiske](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="17151-124">Om du ändrar dig väljer du **Ångra** i popup-meddelandet som visas.</span><span class="sxs-lookup"><span data-stu-id="17151-124">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="17151-125">Meddelandet finns kvar i mappen Inkorgen.</span><span class="sxs-lookup"><span data-stu-id="17151-125">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="17151-126">Rapportera icke-skräppost meddelanden från mappen skräp post i Outlook för iOS och Android</span><span class="sxs-lookup"><span data-stu-id="17151-126">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="17151-127">I mappen skräp post följer du stegen nedan för att rapportera skräp post som falsk.</span><span class="sxs-lookup"><span data-stu-id="17151-127">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="17151-128">Markera ett eller flera meddelanden.</span><span class="sxs-lookup"><span data-stu-id="17151-128">Select one or more messages.</span></span>
2. <span data-ttu-id="17151-129">I det övre högra hörnet trycker du på de tre lodräta punkterna.</span><span class="sxs-lookup"><span data-stu-id="17151-129">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="17151-130">Åtgärd-menyn öppnas.</span><span class="sxs-lookup"><span data-stu-id="17151-130">The action menu opens.</span></span>

   ![Rapportera inte skräp post från åtgärd-menyn](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="17151-132">Tryck på **inte skräp post**.</span><span class="sxs-lookup"><span data-stu-id="17151-132">Tap **Not junk**.</span></span>

<span data-ttu-id="17151-133">En popup-avisering visas där e-postmeddelandet har flyttats till Inkorgen.</span><span class="sxs-lookup"><span data-stu-id="17151-133">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="17151-134">Om du ändrar dig väljer du **Ångra** på popup-meddelandet.</span><span class="sxs-lookup"><span data-stu-id="17151-134">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="17151-135">E-postmeddelandet finns kvar i skräppostmappen.</span><span class="sxs-lookup"><span data-stu-id="17151-135">The email remains in the Junk folder.</span></span>
