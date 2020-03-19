---
title: Använda skräppostmeddelanden för slutanvändare för att släppa och rapportera skräppostmeddelanden i karantän
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4b250bc9-0056-4426-8397-7b4398f1b026
ms.collection:
- M365-security-compliance
description: 'Användare som ser ett skräppostmeddelande från slutanvändaren om e-post i karantän kan vidta dessa åtgärder i meddelandena. '
ms.openlocfilehash: 4d53e4866733ba0d3de96f068297a342c134e5ac
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42811488"
---
# <a name="use-end-user-spam-notifications-to-release-and-report-spam-quarantined-messages"></a><span data-ttu-id="1e4cd-103">Använda skräppostmeddelanden för slutanvändare för att släppa och rapportera skräppostmeddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="1e4cd-103">Use end-user spam notifications to release and report spam-quarantined messages</span></span>

<span data-ttu-id="1e4cd-104">Om administratören aktiverar skräppostmeddelanden för slutanvändare får du ett meddelande om meddelanden som innehåller meddelanden som är avsedda för postlådan och som identifierades som skräppost och i stället sattes i karantän.</span><span class="sxs-lookup"><span data-stu-id="1e4cd-104">If your administrator enables end-user spam notifications, you'll receive a notification message that lists messages intended for your mailbox that were identified as spam and quarantined instead.</span></span> <span data-ttu-id="1e4cd-105">Det här meddelandet innehåller antalet meddelanden i karantän i skräppost och datum och tid (i universell koordinerad tid (UTC)) för det senaste meddelandet i listan.</span><span class="sxs-lookup"><span data-stu-id="1e4cd-105">This message includes the number of spam-quarantined messages listed, and the date and time (in Universal Coordinated Time (UTC)) of the last message in the list.</span></span> <span data-ttu-id="1e4cd-106">I den här listan kan du visa följande information om varje meddelande:</span><span class="sxs-lookup"><span data-stu-id="1e4cd-106">From this list, you can view the following information about each message:</span></span>

- <span data-ttu-id="1e4cd-107">**Avsändare**: Avsändarens namn och e-postadress för det i karantänmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="1e4cd-107">**Sender**: The sender name and email address of the quarantined message.</span></span>

- <span data-ttu-id="1e4cd-108">**Ämne**: Ämnesradens text i det i karantänsmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="1e4cd-108">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="1e4cd-109">**Datum**: Datum och tid (i UTC) som meddelandet sattes i karantän.</span><span class="sxs-lookup"><span data-stu-id="1e4cd-109">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="1e4cd-110">**Storlek:** Storleken på det i karantänmeddelandet, i kbs (kilobyte).</span><span class="sxs-lookup"><span data-stu-id="1e4cd-110">**Size**: The size of the quarantined message, in kilobytes (KBs).</span></span>

<span data-ttu-id="1e4cd-111">Du kan utföra följande åtgärder för varje meddelande:</span><span class="sxs-lookup"><span data-stu-id="1e4cd-111">You can perform the following actions on each message:</span></span>

- <span data-ttu-id="1e4cd-112">**Släpp till Inkorgen:** Om du klickar på den här länken skickas meddelandet till inkorgen där du kan visa det.</span><span class="sxs-lookup"><span data-stu-id="1e4cd-112">**Release to Inbox**: Clicking this link sends the message to your inbox where you can view it.</span></span>

- <span data-ttu-id="1e4cd-113">**Rapport som inte skräp:** Klicka på denna länk skickar en kopia av meddelandet till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="1e4cd-113">**Report as Not Junk**: Clicking this link sends a copy of the message to Microsoft for analysis.</span></span> <span data-ttu-id="1e4cd-114">Skräppostteamet utvärderar och analyserar meddelandet och justerar reglerna för skräppostfilter så att meddelandet går igenom, beroende på analysresultaten.</span><span class="sxs-lookup"><span data-stu-id="1e4cd-114">The spam team evaluates and analyzes the message, and, depending on the results of the analysis, adjusts the anti-spam filter rules to allow the message through.</span></span>

> [!NOTE]
> <span data-ttu-id="1e4cd-115">Meddelanden som sätts i karantän på grund av en e-postflödesregel (kallas även a) ingår inte i meddelanden om skräppost till slutanvändaren i karantän.</span><span class="sxs-lookup"><span data-stu-id="1e4cd-115">Messages that are quarantined due to a mail flow rule (also known as a ) match are not included in end user spam quarantined messages.</span></span> <span data-ttu-id="1e4cd-116">Endast skräppostmeddelanden i karantän visas.</span><span class="sxs-lookup"><span data-stu-id="1e4cd-116">Only spam-quarantined messages are listed.</span></span> <br/><br/>  <span data-ttu-id="1e4cd-117">Du kan bara släppa ett meddelande och rapportera det som ett falskt positivt (inte skräppost) en gång.</span><span class="sxs-lookup"><span data-stu-id="1e4cd-117">You can only release a message and report it as a false positive (not junk) once.</span></span>
