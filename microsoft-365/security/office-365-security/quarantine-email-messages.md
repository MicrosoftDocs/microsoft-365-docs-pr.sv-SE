---
title: E-postmeddelanden i karantän
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig mer om karantän i Exchange Online Protection (EOP) som innehåller potentiellt farliga eller oönskade meddelanden.
ms.openlocfilehash: 77eea3140fb96faec4fb5a749422c2bd9da85b45
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202477"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="c30f5-103">E-postmeddelanden i karantän i EOP</span><span class="sxs-lookup"><span data-stu-id="c30f5-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="c30f5-104">I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor är det möjligt att hålla farliga eller oönskade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="c30f5-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="c30f5-105">Principer mot skadlig program vara automatiskt karantän ett meddelande *om en* bifogad fil hittas för att innehålla skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="c30f5-105">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="c30f5-106">Mer information finns i [Konfigurera principer för skydd mot skadlig program vara i EOP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c30f5-106">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="c30f5-107">Som standard bevarar antivirus program nät fiske meddelanden och skickar skräp post och Mass utskick via e-post till användarens mapp för skräp post.</span><span class="sxs-lookup"><span data-stu-id="c30f5-107">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="c30f5-108">Men du kan också skapa och anpassa principer för skräp post till skräp post och Mass utskick via e-post.</span><span class="sxs-lookup"><span data-stu-id="c30f5-108">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="c30f5-109">Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c30f5-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="c30f5-110">Både användare och administratörer kan arbeta med meddelanden i karantän:</span><span class="sxs-lookup"><span data-stu-id="c30f5-110">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="c30f5-111">Administratörer kan arbeta med alla typer av meddelanden i karantän för alla användare.</span><span class="sxs-lookup"><span data-stu-id="c30f5-111">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="c30f5-112">Endast administratörer kan arbeta med meddelanden som satts i karantän som skadlig program vara, högsäker nät fiske eller resultat av regler för e-postflöde (kallas även transport regler).</span><span class="sxs-lookup"><span data-stu-id="c30f5-112">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="c30f5-113">Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="c30f5-113">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="c30f5-114">Användarna kan arbeta med meddelanden i karantän när de är en mottagare om meddelandet sattes i karantän som skräp post, Mass utskick eller (från april 2020) nätfiske.</span><span class="sxs-lookup"><span data-stu-id="c30f5-114">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="c30f5-115">Mer information finns i [hitta och släppa meddelanden i karantän som en användare i EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="c30f5-115">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="c30f5-116">Administratörer kan konfigurera en annan åtgärd för Verdict för att förhindra att användare hanterar sina egna **nät fiske meddelanden** .</span><span class="sxs-lookup"><span data-stu-id="c30f5-116">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="c30f5-117">Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c30f5-117">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="c30f5-118">Administratörer och användare kan rapportera falska positiva positiv till Microsoft i karantän.</span><span class="sxs-lookup"><span data-stu-id="c30f5-118">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="c30f5-119">Mer information om karantän finns i [vanliga frågor om karantän](quarantine-faq.md).</span><span class="sxs-lookup"><span data-stu-id="c30f5-119">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
