---
title: Vad &apos; är skillnaden mellan skräp post och Mass utskick?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om skillnaderna mellan skräp post och Mass utskick (Gråskala) i Exchange Online Protection (EOP).
ms.openlocfilehash: 1e11f897a145f7b34acc81e1d132d6babac08979
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195485"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="853a5-103">Vad är skillnaden mellan skräp post och Mass utskick i EOP?</span><span class="sxs-lookup"><span data-stu-id="853a5-103">What's the difference between junk email and bulk email in EOP?</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="853a5-104">I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor ber kunderna dig ibland: "Vad är skillnaden mellan skräp post och Mass utskick?"</span><span class="sxs-lookup"><span data-stu-id="853a5-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="853a5-105">I det här avsnittet beskrivs skillnaden och beskriver de kontroller som är tillgängliga i EOP.</span><span class="sxs-lookup"><span data-stu-id="853a5-105">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="853a5-106">**Skräp posten** är skräp post, som inte är efterfrågad och är universellt oönskade (när den identifieras korrekt).</span><span class="sxs-lookup"><span data-stu-id="853a5-106">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="853a5-107">Som standard avvisar EOP inte skräp post baserat på e-postserverns rykte.</span><span class="sxs-lookup"><span data-stu-id="853a5-107">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="853a5-108">Om ett meddelande skickar en käll-IP-kontroll skickas det till skräp post filtrering.</span><span class="sxs-lookup"><span data-stu-id="853a5-108">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="853a5-109">Om meddelandet klassificeras som skräp post genom filtrering av skräp post är meddelandet (som standard) levererat till mottagarna och flyttas till mappen skräp post.</span><span class="sxs-lookup"><span data-stu-id="853a5-109">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="853a5-110">Du kan konfigurera åtgärderna så att de tas med i spam verdicts.</span><span class="sxs-lookup"><span data-stu-id="853a5-110">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="853a5-111">Anvisningar finns i [Konfigurera principer för skräp post i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="853a5-111">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="853a5-112">Om du inte samtycker till Verdict spam kan du rapportera meddelanden som du anser vara skräp post eller icke-skräp post till Microsoft på flera sätt, enligt beskrivningen i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="853a5-112">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="853a5-113">**Mass utskick via e-post** (kallas även _grå e-post_) är svårare att klassificera.</span><span class="sxs-lookup"><span data-stu-id="853a5-113">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="853a5-114">Skräp post är ett konstant hot, Mass utskick är ofta en engångs annonsering eller marknadsförings meddelande.</span><span class="sxs-lookup"><span data-stu-id="853a5-114">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="853a5-115">Vissa användare vill ha Mass utskick av e-post (och faktiskt har de tagit emot dem) medan andra användare anser att Mass utskick av e-post.</span><span class="sxs-lookup"><span data-stu-id="853a5-115">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="853a5-116">Vissa användare vill till exempel ta emot reklam meddelanden från Contoso Corporation eller inbjudningar till en kommande konferens på cyberterrorism säkerhet, medan andra användare anser att samma meddelande ska vara skräp post.</span><span class="sxs-lookup"><span data-stu-id="853a5-116">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="853a5-117">Mer information om hur Mass utskick identifieras finns i bulk- [nivå (BCL) i EOP](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="853a5-117">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="853a5-118">Hantera Mass utskick</span><span class="sxs-lookup"><span data-stu-id="853a5-118">How to manage bulk email</span></span>

<span data-ttu-id="853a5-119">På grund av den blandade högreaktioner till Mass utskick av e-post är det inte till hjälp för varje organisation.</span><span class="sxs-lookup"><span data-stu-id="853a5-119">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="853a5-120">Skydd mot skräp post har en standard tröskel för BCL som används för att identifiera Mass utskick via e-post.</span><span class="sxs-lookup"><span data-stu-id="853a5-120">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="853a5-121">Administratörer kan öka eller minska tröskelvärdet.</span><span class="sxs-lookup"><span data-stu-id="853a5-121">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="853a5-122">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="853a5-122">For more information, see the following topics:</span></span>

- <span data-ttu-id="853a5-123">[Konfigurera principer för skräp post i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="853a5-123">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="853a5-124">EOP princip inställningar för skräp post</span><span class="sxs-lookup"><span data-stu-id="853a5-124">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="853a5-125">Ett annat alternativ som är lätt att missa: om en användare klagande tar emot Mass utskick, men meddelanden kommer från välkända avsändare som skickar skräp post filtrering i EOP, måste användaren kontrol lera om det finns ett alternativ för att avbryta prenumerationen i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="853a5-125">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
