---
title: Skräppostmeddelanden för slutanvändare i Office 36
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: När en administratör aktiverar skräppostmeddelanden för slutanvändare i policyer mot skräppost får mottagarna av meddelanden periodiska meddelanden om sina meddelanden i karantän.
ms.openlocfilehash: 6cde4681d7ea3ef5795201e9a2816b7224ad36f6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895065"
---
# <a name="end-user-spam-notifications-in-office-365"></a><span data-ttu-id="83619-103">Skräppostmeddelanden för slutanvändare i Office 365</span><span class="sxs-lookup"><span data-stu-id="83619-103">End-user spam notifications in Office 365</span></span>

<span data-ttu-id="83619-104">Karantänen innehåller potentiellt farliga eller oönskade meddelanden i Office 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="83619-104">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="83619-105">Mer information finns [i Karantän i Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="83619-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="83619-106">Som standard inaktiveras skräppostmeddelanden för slutanvändare i policyer mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="83619-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="83619-107">När en administratör [aktiverar skräppostmeddelanden](configure-your-spam-filter-policies.md)för slutanvändare får meddelandemottagarna regelbundna meddelanden om sina meddelanden som har satts i karantän som skräppost, massmeddelande eller (från och med april 2020) nätfiske.</span><span class="sxs-lookup"><span data-stu-id="83619-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md), message recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="83619-108">I oktober 2019 tog vi bort möjligheten att släppa meddelanden i karantän direkt från skräppostmeddelanden från slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="83619-108">In October 2019, we removed the ability to release quarantined messages directly from end-user spam notifications.</span></span> <span data-ttu-id="83619-109">I stället kan användare nu gå till Office 365 Security & Compliance Center för att släppa sina meddelanden i karantän (antingen direkt eller genom att klicka på **Granska** i meddelandet).</span><span class="sxs-lookup"><span data-stu-id="83619-109">Instead, users can now go to the Office 365 Security & Compliance Center to release their quarantined messages (either directly, or by clicking **Review** in the notification).</span></span> <span data-ttu-id="83619-110">Mer information finns i [Hitta och släppa meddelanden i karantän som användare i Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="83619-110">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span> <br/><br/> <span data-ttu-id="83619-111">Meddelanden som har satts i karantän som nätfiske, skadlig kod eller via regler för e-postflöde (kallas även transportregler) är endast tillgängliga för administratörer.</span><span class="sxs-lookup"><span data-stu-id="83619-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="83619-112">Mer information finns i [Hantera meddelanden och filer i karantän som administratör i Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="83619-112">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="83619-113">Ett skräppostmeddelande för slutanvändare innehåller följande information för varje meddelande i karantän:</span><span class="sxs-lookup"><span data-stu-id="83619-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="83619-114">**Avsändare**: Skicka namn och e-postadress för det i karantänmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="83619-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="83619-115">**Ämne**: Ämnesradens text i det i karantänsmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="83619-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="83619-116">**Datum**: Datum och tid (i UTC) som meddelandet sattes i karantän.</span><span class="sxs-lookup"><span data-stu-id="83619-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="83619-117">**Blockera avsändare:** Klicka på den här länken om du vill lägga till avsändaren i listan Blockerade avsändare.</span><span class="sxs-lookup"><span data-stu-id="83619-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span>

- <span data-ttu-id="83619-118">**Granska**: Klicka på den här länken om du vill gå till karantänen i Security & Compliance Center, där du kan släppa, ta bort eller rapportera dina meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="83619-118">**Review**: Click this link to go the the Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span>

![Exempel på skräppostmeddelanden för slutanvändare](../../media/end-user-spam-notification.png)
