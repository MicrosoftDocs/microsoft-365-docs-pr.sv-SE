---
title: Skräppostmeddelanden från slutanvändare i Office 36
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
description: När en administratör aktiverar skräppostmeddelanden från slutanvändare i anti-spam-principer får meddelandemottagarna regelbundna meddelanden om sina meddelanden i karantän.
ms.openlocfilehash: 67dbf311c37ae61c007b78110522033d79c0b161
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857156"
---
# <a name="end-user-spam-notifications-in-office-365"></a><span data-ttu-id="ba986-103">Skräppostmeddelanden från slutanvändare i Office 365</span><span class="sxs-lookup"><span data-stu-id="ba986-103">End-user spam notifications in Office 365</span></span>

<span data-ttu-id="ba986-104">Karantän innehåller potentiellt farliga eller oönskade meddelanden i Office 365-organisationer med postlådor i Exchange Online- eller fristående Exchange Online Protection -organisationer (EOP) utan Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="ba986-104">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="ba986-105">Mer information finns [i Karantän i Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="ba986-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="ba986-106">Som standard inaktiveras skräppostmeddelanden för slutanvändare i anti-spam-principer.</span><span class="sxs-lookup"><span data-stu-id="ba986-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="ba986-107">När en administratör [aktiverar skräppostmeddelanden från slutanvändare](configure-your-spam-filter-policies.md)får meddelandemottagarna regelbundna meddelanden om sina meddelanden som sattes i karantän som skräppost, massmeddelanden eller (från och med april 2020) nätfiske.</span><span class="sxs-lookup"><span data-stu-id="ba986-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md), message recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="ba986-108">I oktober 2019 tog vi bort möjligheten att släppa meddelanden i karantän direkt från slutanvändarnas skräppostmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="ba986-108">In October 2019, we removed the ability to release quarantined messages directly from end-user spam notifications.</span></span> <span data-ttu-id="ba986-109">I stället kan användarna nu gå till Office 365 Security & Compliance Center för att släppa sina meddelanden i karantän (antingen direkt eller genom att klicka på **Granska** i meddelandet).</span><span class="sxs-lookup"><span data-stu-id="ba986-109">Instead, users can now go to the Office 365 Security & Compliance Center to release their quarantined messages (either directly, or by clicking **Review** in the notification).</span></span> <span data-ttu-id="ba986-110">Mer information finns i [Hitta och släpp meddelanden i karantän som användare i Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="ba986-110">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span> <br/><br/> <span data-ttu-id="ba986-111">Meddelanden som har satts i karantän som nätfiske med högt förtroende, skadlig kod eller postflödesregler (kallas även transportregler) är endast tillgängliga för administratörer.</span><span class="sxs-lookup"><span data-stu-id="ba986-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="ba986-112">Mer information finns i [Sök efter och släpp meddelanden i karantän som administratör i Office 365](find-and-release-quarantined-messages-as-an-administrator.md).</span><span class="sxs-lookup"><span data-stu-id="ba986-112">For more information, see [Find and release quarantined messages as an admin in Office 365](find-and-release-quarantined-messages-as-an-administrator.md).</span></span>

<span data-ttu-id="ba986-113">Ett skräppostmeddelande från slutanvändaren innehåller följande information för varje meddelande i karantän:</span><span class="sxs-lookup"><span data-stu-id="ba986-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="ba986-114">**Avsändare:** Skicka namn och e-postadress för meddelandet i karantän.</span><span class="sxs-lookup"><span data-stu-id="ba986-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="ba986-115">**Ämne**: Ämnesradstexten i meddelandet i karantän.</span><span class="sxs-lookup"><span data-stu-id="ba986-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="ba986-116">**Datum**: Datum och tid (i UTC) som meddelandet sattes i karantän.</span><span class="sxs-lookup"><span data-stu-id="ba986-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="ba986-117">**Blockera avsändare:** Klicka på den här länken om du vill lägga till avsändaren i listan Blockerade avsändare.</span><span class="sxs-lookup"><span data-stu-id="ba986-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span>

- <span data-ttu-id="ba986-118">**Granska:** Klicka på den här länken om du vill ansluta karantänen i säkerhets- & Compliance Center, där du kan frigöra, ta bort eller rapportera dina meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="ba986-118">**Review**: Click this link to go the the Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span>

![Exempel på skräppost anmälan från slutanvändare](../../media/end-user-spam-notification.png)
