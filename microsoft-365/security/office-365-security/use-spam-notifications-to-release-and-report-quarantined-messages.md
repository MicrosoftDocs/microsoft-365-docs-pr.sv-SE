---
title: Skräppostmeddelanden för slutanvändare i Microsoft 365
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
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig mer om skräppostmeddelanden för slutanvändare för meddelanden i karantän i Exchange Online Protection (EOP).
ms.openlocfilehash: 7d4cf21ade504e999dc5b53ad9062977369561c6
ms.sourcegitcommit: 4ce28ad4d17d336106c1720d65349f19f9e90e04
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2020
ms.locfileid: "44294247"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="ade4a-103">Använda skräppostmeddelanden för att släppa och rapportera meddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="ade4a-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="ade4a-104">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor lagrar karantänen potentiellt farliga eller oönskade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="ade4a-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="ade4a-105">Mer information finns [i Meddelanden i karantän i EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="ade4a-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="ade4a-106">Som standard inaktiveras skräppostmeddelanden för slutanvändare i policyer mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="ade4a-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="ade4a-107">När en administratör [aktiverar skräppostmeddelanden](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)för slutanvändare får mottagarna (inklusive delade postlådor) regelbundna meddelanden om sina meddelanden som har satts i karantän som skräppost, massmeddelande eller (från och med april 2020) nätfiske.</span><span class="sxs-lookup"><span data-stu-id="ade4a-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="ade4a-108">Meddelanden som har satts i karantän som nätfiske, skadlig kod eller via regler för e-postflöde (kallas även transportregler) är endast tillgängliga för administratörer.</span><span class="sxs-lookup"><span data-stu-id="ade4a-108">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="ade4a-109">Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="ade4a-109">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="ade4a-110">Ett skräppostmeddelande för slutanvändare innehåller följande information för varje meddelande i karantän:</span><span class="sxs-lookup"><span data-stu-id="ade4a-110">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="ade4a-111">**Avsändare**: Skicka namn och e-postadress för det i karantänmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="ade4a-111">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="ade4a-112">**Ämne**: Ämnesradens text i det i karantänsmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="ade4a-112">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="ade4a-113">**Datum**: Datum och tid (i UTC) som meddelandet sattes i karantän.</span><span class="sxs-lookup"><span data-stu-id="ade4a-113">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="ade4a-114">**Blockera avsändare:** Klicka på den här länken om du vill lägga till avsändaren i listan Blockerade avsändare.</span><span class="sxs-lookup"><span data-stu-id="ade4a-114">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="ade4a-115">Mer information finns i [Blockera en e-postavsändare i Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="ade4a-115">For more information, see [Block a mail sender in Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="ade4a-116">**Släpp:** För spam (inte phish) meddelanden, kan du släppa meddelandet här utan att gå till Karantän Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="ade4a-116">**Release**: For spam (not phish) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="ade4a-117">**Granska**: Klicka på den här länken om du vill gå till Karantän i Security & Compliance Center, där du kan släppa, ta bort eller rapportera dina meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="ade4a-117">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span> <span data-ttu-id="ade4a-118">Mer information finns i [Hitta och släppa meddelanden i karantän som användare i EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="ade4a-118">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Exempel på skräppostmeddelanden för slutanvändare](../../media/end-user-spam-notification.png)
