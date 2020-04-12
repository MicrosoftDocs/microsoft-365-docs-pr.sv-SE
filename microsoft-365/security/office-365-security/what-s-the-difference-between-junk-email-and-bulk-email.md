---
title: Vad är skillnaden mellan skräppost och massutskick av e-post?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: I det här avsnittet beskrivs skillnaden mellan skräppost (skräppost) och massutskick av e-post och relaterade kontroller i Office 365.
ms.openlocfilehash: 41dedd02febc40b73dc585961487f89bbc6db54a
ms.sourcegitcommit: c876d58b34454f211b50ae5d06f193c1a1e5c4ff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/11/2020
ms.locfileid: "43230962"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a><span data-ttu-id="4b300-103">Vad är skillnaden mellan skräppost och massutskick av e-post?</span><span class="sxs-lookup"><span data-stu-id="4b300-103">What's the difference between junk email and bulk email?</span></span>

<span data-ttu-id="4b300-104">Office 365-kunder med postlådor i Exchange Online eller fristående Exchange Online Protection -kunder utan Exchange Online-postlådor frågar ibland: "Vad är skillnaden mellan skräppost och massutskick av e-post?"</span><span class="sxs-lookup"><span data-stu-id="4b300-104">Office 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="4b300-105">Det här avsnittet förklarar skillnaden och beskriver de kontroller som är tillgängliga i EOP.</span><span class="sxs-lookup"><span data-stu-id="4b300-105">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="4b300-106">**Skräppost** är skräppost, som är oönskade och allmänt oönskade meddelanden (när de identifieras korrekt).</span><span class="sxs-lookup"><span data-stu-id="4b300-106">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="4b300-107">Som standard avvisar EOP skräppost baserat på ryktet för käll-e-postservern.</span><span class="sxs-lookup"><span data-stu-id="4b300-107">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="4b300-108">Om ett meddelande skickas källa IP-inspektion, det skickas till spam filtrering.</span><span class="sxs-lookup"><span data-stu-id="4b300-108">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="4b300-109">Om meddelandet klassificeras som skräppost genom skräppostfiltrering levereras meddelandet (som standard) till de avsedda mottagarna och flyttas till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="4b300-109">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="4b300-110">Du kan konfigurera de åtgärder som ska vidtas för att filtrera domar för skräppost.</span><span class="sxs-lookup"><span data-stu-id="4b300-110">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="4b300-111">Instruktioner finns [i Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4b300-111">For instructions, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="4b300-112">Om du inte håller med om omdömet om skräppostfiltrering kan du rapportera meddelanden som du anser vara skräppost eller icke-skräppost till Microsoft på flera sätt, enligt beskrivningen i [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="4b300-112">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="4b300-113">**Massutskick av e-post** (kallas även _grå e-post)_ är svårare att klassificera.</span><span class="sxs-lookup"><span data-stu-id="4b300-113">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="4b300-114">Medan spam är ett ständigt hot, bulk e-post är ofta engångsannonser eller meddelanden marknadsföring.</span><span class="sxs-lookup"><span data-stu-id="4b300-114">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="4b300-115">Vissa användare vill ha massmeddelanden (och i själva verket har de medvetet registrerat sig för att ta emot dem), medan andra användare anser bulk e-post vara spam.</span><span class="sxs-lookup"><span data-stu-id="4b300-115">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="4b300-116">Vissa användare vill till exempel ta emot annonsmeddelanden från Contoso Corporation eller inbjudningar till en kommande konferens om cybersäkerhet, medan andra användare anser att samma meddelanden är skräppost.</span><span class="sxs-lookup"><span data-stu-id="4b300-116">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="4b300-117">Mer information om hur massutskick identifieras finns i [BCL (Bulk complaint level) i Office 365](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="4b300-117">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in Office 365](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="4b300-118">Så här hanterar du massutskick av e-post</span><span class="sxs-lookup"><span data-stu-id="4b300-118">How to manage bulk email</span></span>

<span data-ttu-id="4b300-119">På grund av den blandade reaktionen på massutskick av e-post finns det inte universell vägledning som gäller för varje organisation.</span><span class="sxs-lookup"><span data-stu-id="4b300-119">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="4b300-120">Anti-spam-policyer har en standard-BCL-tröskel som används för att identifiera massutskick av e-post som skräppost.</span><span class="sxs-lookup"><span data-stu-id="4b300-120">Anti-spam policies have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="4b300-121">Administratörer kan öka eller sänka tröskelvärdet.</span><span class="sxs-lookup"><span data-stu-id="4b300-121">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="4b300-122">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="4b300-122">For more information, see the following topics:</span></span>

- <span data-ttu-id="4b300-123">[Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4b300-123">[Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="4b300-124">EOP:s policyinställningar för skräppost mot skräppost</span><span class="sxs-lookup"><span data-stu-id="4b300-124">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="4b300-125">Ett annat alternativ som är lätt att förbise: om en användare klagar över att ta emot mass-e-post, men meddelandena är från välrenommerade avsändare som passerar skräppostfiltrering i EOP, har användaren kontrollera om ett alternativ för att avsluta prenumerationen i massmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="4b300-125">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
