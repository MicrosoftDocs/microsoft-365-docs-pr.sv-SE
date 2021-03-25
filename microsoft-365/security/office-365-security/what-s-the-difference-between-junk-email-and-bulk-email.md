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
description: Administratörer kan ta reda på skillnaderna mellan skräppost och massutskick (grå e-post) i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fc9c94946c3da2f9a14f45070a86c557a5c7dc85
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207553"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="db492-103">Vad är skillnaden mellan skräppost och massutskick i EOP?</span><span class="sxs-lookup"><span data-stu-id="db492-103">What's the difference between junk email and bulk email in EOP?</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="db492-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="db492-104">**Applies to**</span></span>
- [<span data-ttu-id="db492-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="db492-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="db492-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="db492-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="db492-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db492-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="db492-108">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor frågar kunderna ibland: "Vad är skillnaden mellan skräppost och massutskick?"</span><span class="sxs-lookup"><span data-stu-id="db492-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="db492-109">I det här avsnittet beskrivs skillnaden och de kontroller som är tillgängliga i EOP.</span><span class="sxs-lookup"><span data-stu-id="db492-109">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="db492-110">**Skräppost är** skräppost, som är oönskade och oönskade oönskade meddelanden (när de identifieras korrekt).</span><span class="sxs-lookup"><span data-stu-id="db492-110">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="db492-111">Som standard avvisar EOP skräppost baserat på ryktet hos käll-e-postservern.</span><span class="sxs-lookup"><span data-stu-id="db492-111">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="db492-112">Om ett meddelande klarar käll-IP-kontrollen skickas det till skräppostfiltrering.</span><span class="sxs-lookup"><span data-stu-id="db492-112">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="db492-113">Om meddelandet klassificeras som skräppost av skräppostfiltrering levereras meddelandet (som standard) till de avsedda mottagarna och flyttas till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="db492-113">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="db492-114">Du kan konfigurera åtgärderna för filtrering av skräppost.</span><span class="sxs-lookup"><span data-stu-id="db492-114">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="db492-115">Anvisningar finns i Konfigurera [principer för skydd mot skräppost i EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="db492-115">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="db492-116">Om du inte håller med om skräppostfiltreringens bedömning kan du rapportera meddelanden som du anser vara skräppost eller icke-skräppost till Microsoft på flera olika sätt, enligt beskrivningen i Rapportera meddelanden och filer till [Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="db492-116">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="db492-117">**Massutskick** (kallas även _grå e-post_) är svårare att klassificera.</span><span class="sxs-lookup"><span data-stu-id="db492-117">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="db492-118">Skräppost är ett konstant hot, men massutskick är ofta bara reklam- eller marknadsföringsmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="db492-118">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="db492-119">Vissa användare vill ha massutskick av e-postmeddelanden (och faktiskt avsiktligt registrerat sig för att ta emot dem), medan andra användare anser att massutskick är skräppost.</span><span class="sxs-lookup"><span data-stu-id="db492-119">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="db492-120">Vissa användare vill till exempel få reklammeddelanden från Contoso Corporation eller inbjudningar till en kommande konferens om cybersäkerhet, medan andra användare ser samma meddelanden som skräppost.</span><span class="sxs-lookup"><span data-stu-id="db492-120">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="db492-121">Mer information om hur massutskick identifieras finns i Nivå för mass klagomål [(BCL) i EOP.](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="db492-121">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="db492-122">Hantera massutskick</span><span class="sxs-lookup"><span data-stu-id="db492-122">How to manage bulk email</span></span>

<span data-ttu-id="db492-123">På grund av den blandade reaktionen på massutskick finns det inte någon universell vägledning som gäller för alla organisationer.</span><span class="sxs-lookup"><span data-stu-id="db492-123">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="db492-124">Skräppostskyddsprinciper har en standardtröskel för BCL som används för att identifiera massutskick som skräppost.</span><span class="sxs-lookup"><span data-stu-id="db492-124">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="db492-125">Administratörer kan öka eller minska tröskelvärdet.</span><span class="sxs-lookup"><span data-stu-id="db492-125">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="db492-126">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="db492-126">For more information, see the following topics:</span></span>

- <span data-ttu-id="db492-127">[Konfigurera principer för skydd mot skräppost i EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="db492-127">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="db492-128">Principinställningar för skydd mot skräppost i EOP</span><span class="sxs-lookup"><span data-stu-id="db492-128">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

<span data-ttu-id="db492-129">Ett annat alternativ som är lätt att missat: om en användare klagar på att få massutskick av e-post, men meddelandena kommer från betrodda avsändare som klarar skräppostfiltreringen i EOP, bör du be användaren att kontrollera prenumerationen i e-postmeddelandet med massutskick.</span><span class="sxs-lookup"><span data-stu-id="db492-129">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
