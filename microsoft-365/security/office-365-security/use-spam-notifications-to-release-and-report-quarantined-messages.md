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
description: I den här artikeln får du lära dig mer om skräppostmeddelanden för slutanvändare för meddelanden i karantän.
ms.openlocfilehash: 2a865130bf1fa0c09b5b68254fb604795b204c22
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035004"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="c775e-103">Använda skräppostmeddelanden för att släppa och rapportera meddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="c775e-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="c775e-104">Karantänen lagrar potentiellt farliga eller oönskade meddelanden i Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="c775e-104">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="c775e-105">Mer information finns i [Karantän i Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="c775e-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="c775e-106">Som standard inaktiveras skräppostmeddelanden för slutanvändare i policyer mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="c775e-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="c775e-107">När en administratör [aktiverar skräppostmeddelanden](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)för slutanvändare får mottagarna regelbundna meddelanden om sina meddelanden som har satts i karantän som skräppost, massmeddelande eller (från och med april 2020) nätfiske.</span><span class="sxs-lookup"><span data-stu-id="c775e-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="c775e-108">Meddelanden som har satts i karantän som nätfiske, skadlig kod eller via regler för e-postflöde (kallas även transportregler) är endast tillgängliga för administratörer.</span><span class="sxs-lookup"><span data-stu-id="c775e-108">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="c775e-109">Mer information finns i [Hantera meddelanden och filer i karantän som administratör i Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="c775e-109">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="c775e-110">Ett skräppostmeddelande för slutanvändare innehåller följande information för varje meddelande i karantän:</span><span class="sxs-lookup"><span data-stu-id="c775e-110">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="c775e-111">**Avsändare**: Skicka namn och e-postadress för det i karantänmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="c775e-111">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="c775e-112">**Ämne**: Ämnesradens text i det i karantänsmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="c775e-112">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="c775e-113">**Datum**: Datum och tid (i UTC) som meddelandet sattes i karantän.</span><span class="sxs-lookup"><span data-stu-id="c775e-113">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="c775e-114">**Blockera avsändare:** Klicka på den här länken om du vill lägga till avsändaren i listan Blockerade avsändare.</span><span class="sxs-lookup"><span data-stu-id="c775e-114">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="c775e-115">Mer information finns i [Blockera en e-postavsändare i Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="c775e-115">For more information, see [Block a mail sender in Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="c775e-116">**Släpp:** För spam (inte phish) meddelanden, kan du släppa meddelandet här utan att gå till Karantän Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="c775e-116">**Release**: For spam (not phish) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="c775e-117">**Granska**: Klicka på den här länken om du vill gå till Karantän i Security & Compliance Center, där du kan släppa, ta bort eller rapportera dina meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="c775e-117">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span> <span data-ttu-id="c775e-118">Mer information finns i [Hitta och släppa meddelanden i karantän som användare i Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="c775e-118">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Exempel på skräppostmeddelanden för slutanvändare](../../media/end-user-spam-notification.png)
