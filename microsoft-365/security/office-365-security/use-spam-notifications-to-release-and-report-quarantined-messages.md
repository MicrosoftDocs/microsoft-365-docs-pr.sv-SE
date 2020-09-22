---
title: Meddelanden om avanmälan till slutanvändare i Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
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
description: Administratörer kan lära sig om skräp post meddelanden för meddelanden i karantän i Exchange Online Protection (EOP).
ms.openlocfilehash: 9d1da6c4db245ecb065a5a076f2bc6a9c275c494
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195825"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="f7a69-103">Använda skräp post meddelanden för att frigöra och rapportera översatta meddelanden</span><span class="sxs-lookup"><span data-stu-id="f7a69-103">Use user spam notifications to release and report quarantined messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f7a69-104">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor lagrar karantänen potentiellt farliga eller oönskade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="f7a69-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="f7a69-105">Mer information finns i [karantän meddelanden i EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="f7a69-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="f7a69-106">Som standard är skräp post meddelanden avaktiverade i principer för skräp post.</span><span class="sxs-lookup"><span data-stu-id="f7a69-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="f7a69-107">När en administratör [aktiverar skräp post meddelanden för slutanvändare](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), får mottagarna (inklusive delade post lådor med Automappning aktiverat) regelbundna meddelanden om sina meddelanden som sattes i karantän som skräp post, Mass utskick eller (från april 2020) nätfiske.</span><span class="sxs-lookup"><span data-stu-id="f7a69-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="f7a69-108">För delade post lådor stöds inte skräp post meddelanden för användare som har tilldelats behörigheten Full Access-behörighet till den delade post lådan.</span><span class="sxs-lookup"><span data-stu-id="f7a69-108">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="f7a69-109">Mer information finns i [använda UK för att redigera delegerade post lådor](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span><span class="sxs-lookup"><span data-stu-id="f7a69-109">For more information, see [Use the EAC to edit shared mailbox delegation](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="f7a69-110">Det går inte att skicka skräp post till slutanvändaren för grupper.</span><span class="sxs-lookup"><span data-stu-id="f7a69-110">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="f7a69-111">Meddelanden som satts i karantän som nätfiske, skadlig program vara eller enligt regler för e-postflöde (kallas även transport regler) är endast tillgängliga för administratörer.</span><span class="sxs-lookup"><span data-stu-id="f7a69-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="f7a69-112">Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="f7a69-112">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="f7a69-113">Ett skräp post meddelande för slutanvändare innehåller följande information för varje meddelande i karantän:</span><span class="sxs-lookup"><span data-stu-id="f7a69-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="f7a69-114">**Avsändare**: skicka namn och e-postadress till det uppsatta meddelandet.</span><span class="sxs-lookup"><span data-stu-id="f7a69-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="f7a69-115">**Ämne**: ämnes raden i det mellanliggande meddelandet.</span><span class="sxs-lookup"><span data-stu-id="f7a69-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="f7a69-116">**Datum**: det datum och den tid (i UTC) som meddelandet satts i karantän.</span><span class="sxs-lookup"><span data-stu-id="f7a69-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="f7a69-117">**Spärra avsändare**: Klicka på den här länken för att lägga till avsändaren i listan med spärrade avsändare.</span><span class="sxs-lookup"><span data-stu-id="f7a69-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="f7a69-118">Mer information finns i [blockera en e-avsändare](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="f7a69-118">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="f7a69-119">**Version**: för skräp post meddelanden (inte nätfiske) kan du släppa meddelandet här utan att gå till karantänen säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="f7a69-119">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="f7a69-120">**Granska**: Klicka på den här länken om du vill gå till karantän i säkerhets & Compliance Center, där du kan (beroende på varför meddelandet satts i karantän), släpp, ta bort eller rapportera dina meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="f7a69-120">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="f7a69-121">Mer information finns i [hitta och släppa meddelanden i karantän som en användare i EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="f7a69-121">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Exempel på påminnelse om slutanvändare](../../media/end-user-spam-notification.png)
