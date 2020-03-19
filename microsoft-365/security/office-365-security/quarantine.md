---
title: Karantän
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: e9eecdde-dcc2-4283-a820-98d1e740e4f
ms.collection:
- M365-security-compliance
description: Läs mer om värdbaserade karantän för Exchange Online och Exchange Online Protection.
ms.openlocfilehash: ea803a4681a12647f57cf17839d26fb391222364
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42856887"
---
# <a name="quarantine"></a><span data-ttu-id="455bf-103">Karantän</span><span class="sxs-lookup"><span data-stu-id="455bf-103">Quarantine</span></span>

<span data-ttu-id="455bf-104">Följande avsnitt innehåller information om den värdbaserade karantänen för både Exchange Online- och Exchange Online Protection (EOP) administratörer och slutanvändare:</span><span class="sxs-lookup"><span data-stu-id="455bf-104">The following topics provide information about the hosted quarantine for both Exchange Online and Exchange Online Protection (EOP) admins and end users:</span></span>

- <span data-ttu-id="455bf-105">[Vanliga frågor om karantän](quarantine-faq.md) – Ger allmänna frågor och svar om karantänen för både administratörer och slutanvändare</span><span class="sxs-lookup"><span data-stu-id="455bf-105">[Quarantine FAQ](quarantine-faq.md) - Provides general questions and answers about the quarantine for both admins and end users</span></span>

- <span data-ttu-id="455bf-106">[Hantera meddelanden och filer i karantän som administratör i Office 365](manage-quarantined-messages-and-files.md): Beskriver hur administratörer kan hitta och släppa alla meddelanden som finns i karantänen i Administrationscenter för Exchange (EAC) och eventuellt rapportera det som ett falskt positivt meddelande (inte skräppost) till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="455bf-106">[Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md): Describes how admins can find and release any message that resides in the quarantine in the Exchange admin center (EAC), and optionally report it as a false positive (not junk) message to Microsoft.</span></span>

- <span data-ttu-id="455bf-107">[Hitta och släpp meddelanden i karantän som användare i Office 365:](find-and-release-quarantined-messages-as-a-user.md)Beskriver hur slutanvändare kan hitta och släppa sina egna skräppostmeddelanden i användargränssnittet för skräppostkarantän och rapportera dem som inte skräppost till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="455bf-107">[Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md): Describes how end users can find and release their own spam-quarantined messages in the spam quarantine user interface, and report them as not junk to Microsoft.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="455bf-108">För att komma åt slutanvändarens skräppostkarant karantän måste slutanvändarna ha ett giltigt användar-ID och lösenord för Office 365.</span><span class="sxs-lookup"><span data-stu-id="455bf-108">In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="455bf-109">EOP-kunder som skyddar lokala postlådor måste vara giltiga e-postanvändare som skapats via katalogsynkronisering eller EAC.</span><span class="sxs-lookup"><span data-stu-id="455bf-109">EOP customers protecting on-premises mailboxes must be valid email users created via directory synchronization or the EAC.</span></span> <span data-ttu-id="455bf-110">Mer information om hur du hanterar användare kan EOP-administratörer referera till [Hantera e-postanvändare i EOP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="455bf-110">For more information about managing users, EOP admins can refer to [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span> <span data-ttu-id="455bf-111">För fristående EOP-kunder rekommenderar vi att du använder katalogsynkronisering och aktiverar katalogbaserad kantblockering. Mer information finns i [Använda katalogbaserad kantblockering för att avvisa meddelanden som skickas till ogiltiga mottagare](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span><span class="sxs-lookup"><span data-stu-id="455bf-111">For EOP standalone customers, we recommend using directory synchronization and enabling Directory Based Edge Blocking; for more information, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>
