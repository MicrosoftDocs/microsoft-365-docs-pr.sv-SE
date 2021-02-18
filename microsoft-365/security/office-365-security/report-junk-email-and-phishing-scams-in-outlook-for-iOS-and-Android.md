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
ms.openlocfilehash: e3e3a2d77c978649e7496d09f78301add397fb9d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289179"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="20781-103">Rapportera skräppost och nätfiske i Outlook för iOS och Android i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="20781-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="20781-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="20781-104">**Applies to**</span></span>
- [<span data-ttu-id="20781-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="20781-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="20781-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="20781-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="20781-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="20781-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="20781-108">I Microsoft 365-organisationer med postlådor i Exchange Online eller lokala postlådor som använder [modern hybridautentisering](../../enterprise/hybrid-modern-auth-overview.md)kan du använda de inbyggda rapporteringsalternativen i Outlook för iOS och Android för att skicka falska positiva identifieringar (bra e-post som har markerats som skräppost), falska negativa identifieringar (felaktig e-post tillåten) och nätfiskemeddelanden till Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="20781-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="20781-109">Vad behöver du veta innan du börjar</span><span class="sxs-lookup"><span data-stu-id="20781-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="20781-110">För bästa användarinskickning rekommenderar vi att du använder rapportmeddelandet och tilläggen för nätfiske. Mer information finns i Aktivera tillägget [Rapportmeddelande](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) och Aktivera tillägget [Rapportfiske.](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in)</span><span class="sxs-lookup"><span data-stu-id="20781-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) and [Enable the Report Phishing add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) for more information.</span></span>

- <span data-ttu-id="20781-111">Om du är administratör i en organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen Inskickade i Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="20781-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="20781-112">Mer information finns i Använda [administrationsinskick för att skicka misstänkt skräppost, phish, URL:er och filer till Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="20781-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="20781-113">Du kan konfigurera rapporterade meddelanden som ska kopieras eller omdirigeras till en postlåda som du anger.</span><span class="sxs-lookup"><span data-stu-id="20781-113">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="20781-114">Mer information finns i principer [för användarinskick.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="20781-114">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="20781-115">Mer information om hur du rapporterar meddelanden till Microsoft finns [i Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="20781-115">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="20781-116">Om skräppostrapportering är inaktiverad för Outlook i principen för användarinskickning flyttas skräppost- eller nätfiskemeddelanden till mappen Skräppost och rapporteras inte till din administratör eller Microsoft.</span><span class="sxs-lookup"><span data-stu-id="20781-116">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>