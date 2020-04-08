---
title: Karantän i Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
description: Karantän i Office 365 innehåller potentiellt farliga eller oönskade meddelanden. Administratörer och slutanvändare kan komma åt karantän.
ms.openlocfilehash: a11b4a0d86cfc5f74636d3a9f89cf598320d1ebf
ms.sourcegitcommit: 053d42480d8aa3792ecb0027ddd53d383a029474
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/07/2020
ms.locfileid: "42940963"
---
# <a name="quarantine-in-office-365"></a><span data-ttu-id="34db3-104">Karantän i Office 365</span><span class="sxs-lookup"><span data-stu-id="34db3-104">Quarantine in Office 365</span></span>

<span data-ttu-id="34db3-105">Om du är en Office 365-kund med postlådor i Exchange Online eller en fristående Exchange Online Protection-kund (EOP) utan Exchange Online-postlådor, är karantän tillgänglig för att lagra potentiellt farliga eller oönskade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="34db3-105">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="34db3-106">Policyer mot skadlig kod sätter automatiskt ett meddelande i karantän om *någon* bifogad fil visar sig innehålla skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="34db3-106">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="34db3-107">Mer information finns [i Konfigurera principer mot skadlig kod i Office 365](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="34db3-107">For more information, see [Configure anti-malware policies in Office 365](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="34db3-108">Som standard, anti-spam polisen karantän phishing-meddelanden, och leverera skräppost och bulk e-postmeddelanden till användarens skräppostmapp.</span><span class="sxs-lookup"><span data-stu-id="34db3-108">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="34db3-109">Men du kan också skapa och anpassa anti-spam-policyer för att sätta skräppost och massmeddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="34db3-109">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="34db3-110">Mer information finns i [Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="34db3-110">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="34db3-111">Både användare och administratörer kan arbeta med meddelanden i karantän:</span><span class="sxs-lookup"><span data-stu-id="34db3-111">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="34db3-112">Administratörer kan arbeta med alla typer av meddelanden i karantän för alla användare.</span><span class="sxs-lookup"><span data-stu-id="34db3-112">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="34db3-113">Endast administratörer kan arbeta med meddelanden som har satts i karantän som skadlig kod, nätfiske med högt förtroende eller som ett resultat av regler för e-postflöde (kallas även transportregler).</span><span class="sxs-lookup"><span data-stu-id="34db3-113">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="34db3-114">Mer information finns i [Hantera meddelanden och filer i karantän som administratör i Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="34db3-114">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="34db3-115">Användare kan arbeta med meddelanden i karantän där de är mottagare om meddelandet har satts i karantän som skräppost, massmeddelande eller (från och med april 2020) nätfiske.</span><span class="sxs-lookup"><span data-stu-id="34db3-115">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="34db3-116">Mer information finns i [Hitta och släppa meddelanden i karantän som användare i Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="34db3-116">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="34db3-117">För att förhindra att användare hanterar sina egna nätfiskemeddelanden i karantän kan administratörer konfigurera en annan åtgärd för **e-nätfiskefiltreringsdomen** i policyer för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="34db3-117">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="34db3-118">Mer information finns i [Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="34db3-118">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="34db3-119">Administratörer och användare kan rapportera falska positiva identifieringar till Microsoft i karantän.</span><span class="sxs-lookup"><span data-stu-id="34db3-119">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="34db3-120">Mer information om, karantän finns i [Vanliga frågor och svar](quarantine-faq.md)om karantän i karantän .</span><span class="sxs-lookup"><span data-stu-id="34db3-120">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
