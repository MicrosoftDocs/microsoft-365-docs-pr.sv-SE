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
ms.openlocfilehash: 2c95f7b32d0d395e164d218c994b1608d36018d5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207408"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="50a78-103">Rapportera skräppost och nätfiske i Outlook för iOS och Android i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="50a78-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="50a78-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="50a78-104">**Applies to**</span></span>
- [<span data-ttu-id="50a78-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="50a78-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="50a78-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="50a78-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="50a78-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="50a78-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="50a78-108">I Microsoft 365-organisationer med postlådor i Exchange Online eller lokala postlådor med [modern hybridautentisering](../../enterprise/hybrid-modern-auth-overview.md)kan du skicka falska positiva identifieringar (bra e-post som markerats som skräppost), falska negativa identifieringar (felaktig e-post tillåts) och nätfiskemeddelanden till Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="50a78-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="50a78-109">Vad behöver du veta innan du börjar</span><span class="sxs-lookup"><span data-stu-id="50a78-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="50a78-110">För att du ska kunna skicka in rapporten på bästa sätt rekommenderar vi att du använder tilläggen Rapportmeddelande och Rapport vid nätfiske. Mer information [finns i Aktivera tillägget Rapportmeddelande](./enable-the-report-message-add-in.md) och Aktivera tillägget [Rapportfiske.](./enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="50a78-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](./enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](./enable-the-report-phish-add-in.md) for more information.</span></span>

- <span data-ttu-id="50a78-111">Om du är administratör i en organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen för sändning i Säkerhets- och & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="50a78-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="50a78-112">Mer information finns i Använda [administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="50a78-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="50a78-113">Du kan konfigurera rapporterade meddelanden så att de kopieras eller omdirigeras till en postlåda som du anger.</span><span class="sxs-lookup"><span data-stu-id="50a78-113">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="50a78-114">Mer information finns i Principer [för användarinskick.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="50a78-114">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="50a78-115">Mer information om hur du rapporterar meddelanden till Microsoft finns [i Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="50a78-115">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="50a78-116">Om skräppostrapportering är inaktiverat för Outlook i principen för användarinskicking flyttas skräppost- eller nätfiskemeddelanden till mappen Skräppost och rapporteras inte till din administratör eller Microsoft.</span><span class="sxs-lookup"><span data-stu-id="50a78-116">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>