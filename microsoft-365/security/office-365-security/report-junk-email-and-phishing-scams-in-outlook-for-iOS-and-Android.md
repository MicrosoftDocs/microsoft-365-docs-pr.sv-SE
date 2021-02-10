---
title: Rapportera skräppost och nätfiske i Outlook för iOS och Android
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
description: Administratörer kan läsa mer om de inbyggda alternativen för skräppost, inte skräppost och nätfiske i Outlook för iOS och Android.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 58027f7589280b1266cddc8cfbf44db9e4f0ece4
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166825"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="930ae-103">Rapportera skräppost och nätfiske i Outlook för iOS och Android i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="930ae-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="930ae-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="930ae-104">**Applies to**</span></span>
- [<span data-ttu-id="930ae-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="930ae-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="930ae-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="930ae-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="930ae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="930ae-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="930ae-108">I Microsoft 365-organisationer med postlådor i Exchange Online eller lokala postlådor som använder [modern hybridautentisering](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)kan du använda de inbyggda rapporteringsalternativen i Outlook för iOS och Android för att skicka falska positiva identifieringar (bra e-post som har markerats som skräppost), falska negativa identifieringar (felaktig e-post tillåten) och nätfiskemeddelanden till Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="930ae-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="930ae-109">Vad behöver du veta innan du börjar</span><span class="sxs-lookup"><span data-stu-id="930ae-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="930ae-110">Om du är administratör i en organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen Inskickade i Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="930ae-110">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="930ae-111">Mer information finns i Använda administratörs inskickat material för att skicka misstänkt [skräppost, phish, URL:er och filer till Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="930ae-111">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="930ae-112">Du kan konfigurera rapporterade meddelanden som ska kopieras eller omdirigeras till en postlåda som du anger.</span><span class="sxs-lookup"><span data-stu-id="930ae-112">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="930ae-113">Mer information finns i principer [för användarinskick.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="930ae-113">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="930ae-114">Mer information om hur du rapporterar meddelanden till Microsoft finns [i Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="930ae-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="930ae-115">Om skräppostrapportering är inaktiverad för Outlook i användarinskickingsprincipen flyttas skräppost- eller nätfiskemeddelanden till mappen Skräppost och rapporteras inte till din administratör eller Microsoft.</span><span class="sxs-lookup"><span data-stu-id="930ae-115">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="930ae-116">Rapportera skräppost och nätfiskemeddelanden i Outlook för iOS och Android</span><span class="sxs-lookup"><span data-stu-id="930ae-116">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="930ae-117">Använd följande steg för att rapportera skräppost och nätfiskemeddelanden för iOS och Android för meddelanden i Inkorgen eller någon annan e-postmapp utom Skräppost:</span><span class="sxs-lookup"><span data-stu-id="930ae-117">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="930ae-118">Markera ett eller flera meddelanden.</span><span class="sxs-lookup"><span data-stu-id="930ae-118">Select one or more messages.</span></span>
2. <span data-ttu-id="930ae-119">Tryck på de tre lodräta punkterna i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="930ae-119">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="930ae-120">Åtgärdsmenyn öppnas.</span><span class="sxs-lookup"><span data-stu-id="930ae-120">The action menu opens.</span></span>

   ![Rapportera skräppost och nätfiske i åtgärdsmenyn](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="930ae-122">Tryck **på Rapportera skräppost** och välj sedan **Skräppost** eller **nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="930ae-122">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![Rapportera skräppost och nätfiske](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="930ae-124">I dialogrutan som visas kan du välja Rapport **eller** **Nej tack.**</span><span class="sxs-lookup"><span data-stu-id="930ae-124">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="930ae-125">Om du **väljer Nej** tack  flyttas meddelandet till mappen Skräppost om du  trycker på Meddelandet flyttas till mappen Borttaget om du trycker på Nätfiske.</span><span class="sxs-lookup"><span data-stu-id="930ae-125">On selecting **No Thanks**, if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="930ae-126">Välj **Rapport** för att även skicka en kopia av meddelandet till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="930ae-126">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![Rapportalternativ för skräppost- och nätfiskemeddelanden](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="930ae-128">Om du ändrar dig väljer du **Ångra i** popup-meddelandet som visas.</span><span class="sxs-lookup"><span data-stu-id="930ae-128">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="930ae-129">Meddelandet finns kvar i mappen Inkorgen.</span><span class="sxs-lookup"><span data-stu-id="930ae-129">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="930ae-130">Rapportera meddelanden som inte är skräppost från skräppostmappen i Outlook för iOS och Android</span><span class="sxs-lookup"><span data-stu-id="930ae-130">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="930ae-131">Använd följande steg i skräppostmappen för att rapportera skräppost med falska positiva resultat:</span><span class="sxs-lookup"><span data-stu-id="930ae-131">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="930ae-132">Markera ett eller flera meddelanden.</span><span class="sxs-lookup"><span data-stu-id="930ae-132">Select one or more messages.</span></span>
2. <span data-ttu-id="930ae-133">Tryck på de tre lodräta punkterna i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="930ae-133">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="930ae-134">Åtgärdsmenyn öppnas.</span><span class="sxs-lookup"><span data-stu-id="930ae-134">The action menu opens.</span></span>

   ![Rapportera inte skräppost från åtgärdsmenyn](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="930ae-136">Tryck **på Inte skräppost.**</span><span class="sxs-lookup"><span data-stu-id="930ae-136">Tap **Not junk**.</span></span>

<span data-ttu-id="930ae-137">En avisering visas om att e-postmeddelandet har flyttats till Inkorgen.</span><span class="sxs-lookup"><span data-stu-id="930ae-137">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="930ae-138">Om du ändrar dig väljer du Ångra **i** aviseringen.</span><span class="sxs-lookup"><span data-stu-id="930ae-138">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="930ae-139">E-postmeddelandet ligger kvar i skräppostmappen.</span><span class="sxs-lookup"><span data-stu-id="930ae-139">The email remains in the Junk folder.</span></span>
