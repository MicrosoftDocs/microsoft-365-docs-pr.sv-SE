---
title: Vad är skillnaden mellan skräppost och massutskick?
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
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig om skillnaderna mellan skräppost (skräppost) och massutskick av e-post (grå e-post) i Exchange Online Protection (EOP).
ms.openlocfilehash: 6936028aa7bda538f0e49429d22f28c7a78cdb36
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208458"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="9dd08-103">Vad är skillnaden mellan skräppost och massutskick av e-post i EOP?</span><span class="sxs-lookup"><span data-stu-id="9dd08-103">What's the difference between junk email and bulk email in EOP?</span></span>

<span data-ttu-id="9dd08-104">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor frågar kunderna ibland: "Vad är skillnaden mellan skräppost och massutskick av e-post?"</span><span class="sxs-lookup"><span data-stu-id="9dd08-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="9dd08-105">Det här avsnittet förklarar skillnaden och beskriver de kontroller som är tillgängliga i EOP.</span><span class="sxs-lookup"><span data-stu-id="9dd08-105">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="9dd08-106">**Skräppost** är skräppost, som är oönskade och allmänt oönskade meddelanden (när de identifieras korrekt).</span><span class="sxs-lookup"><span data-stu-id="9dd08-106">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="9dd08-107">Som standard avvisar EOP skräppost baserat på ryktet för käll-e-postservern.</span><span class="sxs-lookup"><span data-stu-id="9dd08-107">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="9dd08-108">Om ett meddelande skickas källa IP-inspektion, det skickas till spam filtrering.</span><span class="sxs-lookup"><span data-stu-id="9dd08-108">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="9dd08-109">Om meddelandet klassificeras som skräppost genom skräppostfiltrering levereras meddelandet (som standard) till de avsedda mottagarna och flyttas till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="9dd08-109">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="9dd08-110">Du kan konfigurera de åtgärder som ska vidtas för att filtrera domar för skräppost.</span><span class="sxs-lookup"><span data-stu-id="9dd08-110">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="9dd08-111">Instruktioner finns [i Konfigurera principer mot skräppost i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9dd08-111">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="9dd08-112">Om du inte håller med om omdömet om skräppostfiltrering kan du rapportera meddelanden som du anser vara skräppost eller icke-skräppost till Microsoft på flera sätt, enligt beskrivningen i [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="9dd08-112">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="9dd08-113">**Massutskick av e-post** (kallas även _grå e-post)_ är svårare att klassificera.</span><span class="sxs-lookup"><span data-stu-id="9dd08-113">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="9dd08-114">Medan spam är ett ständigt hot, bulk e-post är ofta engångsannonser eller meddelanden marknadsföring.</span><span class="sxs-lookup"><span data-stu-id="9dd08-114">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="9dd08-115">Vissa användare vill ha massmeddelanden (och i själva verket har de medvetet registrerat sig för att ta emot dem), medan andra användare anser bulk e-post vara spam.</span><span class="sxs-lookup"><span data-stu-id="9dd08-115">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="9dd08-116">Vissa användare vill till exempel ta emot annonsmeddelanden från Contoso Corporation eller inbjudningar till en kommande konferens om cybersäkerhet, medan andra användare anser att samma meddelanden är skräppost.</span><span class="sxs-lookup"><span data-stu-id="9dd08-116">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="9dd08-117">Mer information om hur massmeddelande identifieras finns i [BCL (Bulk complaint level) i EOP](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="9dd08-117">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="9dd08-118">Så här hanterar du massutskick av e-post</span><span class="sxs-lookup"><span data-stu-id="9dd08-118">How to manage bulk email</span></span>

<span data-ttu-id="9dd08-119">På grund av den blandade reaktionen på massutskick av e-post finns det inte universell vägledning som gäller för varje organisation.</span><span class="sxs-lookup"><span data-stu-id="9dd08-119">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="9dd08-120">Anti-spam-polisen har en standard BCL tröskel som används för att identifiera mass-e-post som skräppost.</span><span class="sxs-lookup"><span data-stu-id="9dd08-120">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="9dd08-121">Administratörer kan öka eller sänka tröskelvärdet.</span><span class="sxs-lookup"><span data-stu-id="9dd08-121">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="9dd08-122">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="9dd08-122">For more information, see the following topics:</span></span>

- <span data-ttu-id="9dd08-123">[Konfigurera principer mot skräppost i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9dd08-123">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="9dd08-124">EOP:s policyinställningar för skräppost mot skräppost</span><span class="sxs-lookup"><span data-stu-id="9dd08-124">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="9dd08-125">Ett annat alternativ som är lätt att förbise: om en användare klagar över att ta emot mass-e-post, men meddelandena är från välrenommerade avsändare som passerar skräppostfiltrering i EOP, har användaren kontrollera om ett alternativ för att avsluta prenumerationen i massmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="9dd08-125">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
