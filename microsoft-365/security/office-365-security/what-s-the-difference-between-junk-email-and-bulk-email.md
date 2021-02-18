---
title: Vad &apos; är skillnaden mellan skräppost och massutskick?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig mer om skillnaderna mellan skräppost och massutskick (grå e-post) i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c656ed1807b451ae03ecfeb0f220f5d7b902c7ac
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290651"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="2da21-103">Vad är skillnaden mellan skräppost och massutskick i EOP?</span><span class="sxs-lookup"><span data-stu-id="2da21-103">What's the difference between junk email and bulk email in EOP?</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2da21-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="2da21-104">**Applies to**</span></span>
- [<span data-ttu-id="2da21-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2da21-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2da21-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="2da21-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="2da21-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2da21-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="2da21-108">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection (EOP) utan Exchange Online-postlådor frågar kunderna ibland: "Vad är skillnaden mellan skräppost och massutskick?"</span><span class="sxs-lookup"><span data-stu-id="2da21-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="2da21-109">I det här avsnittet beskrivs skillnaden och de kontroller som är tillgängliga i EOP.</span><span class="sxs-lookup"><span data-stu-id="2da21-109">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="2da21-110">**Skräppost är** skräppost, som är oönskade och oönskade oönskade meddelanden (när de identifieras korrekt).</span><span class="sxs-lookup"><span data-stu-id="2da21-110">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="2da21-111">Som standard avvisas skräppost av EOP baserat på ryktet hos käll-e-postservern.</span><span class="sxs-lookup"><span data-stu-id="2da21-111">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="2da21-112">Om ett meddelande klarar käll-IP-kontrollen skickas det till skräppostfiltrering.</span><span class="sxs-lookup"><span data-stu-id="2da21-112">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="2da21-113">Om meddelandet klassificeras som skräppost med hjälp av skräppostfiltrering levereras meddelandet (som standard) till de avsedda mottagarna och flyttas till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="2da21-113">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="2da21-114">Du kan konfigurera åtgärderna för filtrering av skräppost.</span><span class="sxs-lookup"><span data-stu-id="2da21-114">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="2da21-115">Instruktioner finns i Konfigurera [principer för skydd mot skräppost i EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="2da21-115">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="2da21-116">Om du inte är nöjd med skräppostfiltreringen kan du rapportera meddelanden som du anser vara skräppost eller icke-skräppost till Microsoft på flera olika sätt, enligt beskrivningen i Rapportera meddelanden och filer till [Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="2da21-116">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="2da21-117">**Massutskick** (kallas även _grå post)_ är svårare att klassificera.</span><span class="sxs-lookup"><span data-stu-id="2da21-117">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="2da21-118">Skräppost är ett konstant hot, men massutskick är ofta bara en gång reklam- eller marknadsföringsmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="2da21-118">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="2da21-119">Vissa användare vill att stora e-postmeddelanden (och faktiskt avsiktligt har registrerat sig för att ta emot dem), medan andra användare anser att massutskick är skräppost.</span><span class="sxs-lookup"><span data-stu-id="2da21-119">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="2da21-120">Vissa användare vill till exempel få reklammeddelanden från Contoso Corporation eller inbjudningar till en kommande konferens om cybersäkerhet, medan andra användare ser samma meddelanden som skräppost.</span><span class="sxs-lookup"><span data-stu-id="2da21-120">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="2da21-121">Mer information om hur massutskick identifieras finns i Nivå för gruppklagomål [(BCL) i EOP.](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="2da21-121">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="2da21-122">Hantera massutskick</span><span class="sxs-lookup"><span data-stu-id="2da21-122">How to manage bulk email</span></span>

<span data-ttu-id="2da21-123">På grund av den blandade reaktionen mot massutskick finns det inte någon universell vägledning som gäller för varje organisation.</span><span class="sxs-lookup"><span data-stu-id="2da21-123">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="2da21-124">Skräppostskyddsprinciper har en standardtröskel för BCL som används för att identifiera massutskick som skräppost.</span><span class="sxs-lookup"><span data-stu-id="2da21-124">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="2da21-125">Administratörer kan öka eller minska tröskelvärdet.</span><span class="sxs-lookup"><span data-stu-id="2da21-125">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="2da21-126">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="2da21-126">For more information, see the following topics:</span></span>

- <span data-ttu-id="2da21-127">[Konfigurera principer för skydd mot skräppost i EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="2da21-127">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="2da21-128">Principinställningar för EOP-skydd mot skräppost</span><span class="sxs-lookup"><span data-stu-id="2da21-128">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="2da21-129">Ett annat alternativ som är lätt att missat: om en användare klagar på att få massutskick av e-post, men meddelandena kommer från betrodda avsändare som klarar skräppostfiltreringen i EOP, kan du be användaren att avregistrera sig från prenumerationen i massmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="2da21-129">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
