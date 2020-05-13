---
title: E-postmeddelanden i karantän
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
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig mer om karantän i Exchange Online Protection (EOP) som innehåller potentiellt farliga eller oönskade meddelanden.
ms.openlocfilehash: 71a5f32fe6888d751bf2c4020fca4df671ac96d1
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208288"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="bf2bd-103">E-postmeddelanden i karantän i EOP</span><span class="sxs-lookup"><span data-stu-id="bf2bd-103">Quarantined email messages in EOP</span></span>

<span data-ttu-id="bf2bd-104">I Microsoft 365-organisationer med postlådor i Exchange Online- eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor är karantän tillgänglig för att lagra potentiellt farliga eller oönskade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="bf2bd-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="bf2bd-105">Policyer mot skadlig kod sätter automatiskt ett meddelande i karantän om *någon* bifogad fil visar sig innehålla skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="bf2bd-105">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="bf2bd-106">Mer information finns i [Konfigurera principer mot skadlig kod i EOP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bf2bd-106">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="bf2bd-107">Som standard, anti-spam polisen karantän phishing-meddelanden, och leverera skräppost och bulk e-postmeddelanden till användarens skräppostmapp.</span><span class="sxs-lookup"><span data-stu-id="bf2bd-107">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="bf2bd-108">Men du kan också skapa och anpassa anti-spam-policyer för att sätta skräppost och massmeddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="bf2bd-108">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="bf2bd-109">Mer information finns [i Konfigurera principer mot skräppost i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bf2bd-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="bf2bd-110">Både användare och administratörer kan arbeta med meddelanden i karantän:</span><span class="sxs-lookup"><span data-stu-id="bf2bd-110">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="bf2bd-111">Administratörer kan arbeta med alla typer av meddelanden i karantän för alla användare.</span><span class="sxs-lookup"><span data-stu-id="bf2bd-111">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="bf2bd-112">Endast administratörer kan arbeta med meddelanden som har satts i karantän som skadlig kod, nätfiske med högt förtroende eller som ett resultat av regler för e-postflöde (kallas även transportregler).</span><span class="sxs-lookup"><span data-stu-id="bf2bd-112">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="bf2bd-113">Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="bf2bd-113">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="bf2bd-114">Användare kan arbeta med meddelanden i karantän där de är mottagare om meddelandet har satts i karantän som skräppost, massmeddelande eller (från och med april 2020) nätfiske.</span><span class="sxs-lookup"><span data-stu-id="bf2bd-114">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="bf2bd-115">Mer information finns i [Hitta och släppa meddelanden i karantän som användare i EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="bf2bd-115">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="bf2bd-116">För att förhindra att användare hanterar sina egna nätfiskemeddelanden i karantän kan administratörer konfigurera en annan åtgärd för **e-nätfiskefiltreringsdomen** i policyer för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="bf2bd-116">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="bf2bd-117">Mer information finns [i Konfigurera principer mot skräppost i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bf2bd-117">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="bf2bd-118">Administratörer och användare kan rapportera falska positiva identifieringar till Microsoft i karantän.</span><span class="sxs-lookup"><span data-stu-id="bf2bd-118">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="bf2bd-119">Mer information om, karantän finns i [Vanliga frågor och svar](quarantine-faq.md)om karantän i karantän .</span><span class="sxs-lookup"><span data-stu-id="bf2bd-119">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
