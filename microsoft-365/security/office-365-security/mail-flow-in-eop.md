---
title: E-postflöde i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa om alternativen för att konfigurera e-postflöde och routning i Exchange Online Protection (EOP).
ms.openlocfilehash: c58981afaadf2c4083b6a6db99c74cf9544715c3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827731"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="89753-103">E-postflöde i EOP</span><span class="sxs-lookup"><span data-stu-id="89753-103">Mail flow in EOP</span></span>

<span data-ttu-id="89753-104">I Microsoft 365-organisationer med Exchange Online-postlådor eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor kan alla meddelanden som skickas till organisationen passera genom EOP innan dina anställda ser dem.</span><span class="sxs-lookup"><span data-stu-id="89753-104">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="89753-105">Du har alternativ för att dirigera meddelanden som passerar genom EOP för bearbetning innan de cirkuleras till dina anställdas inkorgar.</span><span class="sxs-lookup"><span data-stu-id="89753-105">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="89753-106">Arbeta med meddelanden och alternativ för meddelande åtkomst</span><span class="sxs-lookup"><span data-stu-id="89753-106">Working with messages and message access options</span></span>

<span data-ttu-id="89753-107">EOP erbjuder flexibilitet i hur dina meddelanden routas.</span><span class="sxs-lookup"><span data-stu-id="89753-107">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="89753-108">I följande avsnitt förklaras anvisningar i e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="89753-108">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="89753-109">[Använda katalogbaserade Edge-spärr för att avvisa meddelanden som skickats till ogiltiga mottagare](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Beskriver den mappbaserade Edge blockera-funktionen som låter dig avvisa meddelanden för ogiltiga mottagare i tjänst nätverkets perimeter.</span><span class="sxs-lookup"><span data-stu-id="89753-109">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="89753-110">[Visa eller redigera hanterade domäner i EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) beskriver hur du hanterar domäner som är kopplade till din EOP-tjänst.</span><span class="sxs-lookup"><span data-stu-id="89753-110">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="89753-111">Om du lägger till under domäner i din organisation kan EOP-tjänsten hjälpa dig hantera dem också.</span><span class="sxs-lookup"><span data-stu-id="89753-111">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="89753-112">Läs mer om under domäner i [Aktivera e-postflöde för under domäner i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span><span class="sxs-lookup"><span data-stu-id="89753-112">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="89753-113">[Konfigurera e-postflöde med kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introducerar kontakter och visar hur du kan använda dem för att anpassa e-postdirigering.</span><span class="sxs-lookup"><span data-stu-id="89753-113">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="89753-114">Scenarion inkluderar säker kommunikation med en partner organisation och att konfigurera en smart värd.</span><span class="sxs-lookup"><span data-stu-id="89753-114">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="89753-115">[Förbättrad filtrering för kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) beskriver hur du konfigurerar anslutningar om din e-post dirigeras till en tjänst eller enhet innan EOP.</span><span class="sxs-lookup"><span data-stu-id="89753-115">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="89753-116">I fristående EOP-organisationer måste du utföra ett par konfigurations steg för att säkerställa att skräp post dirigeras korrekt till varje användares skräppost-e-postmapp.</span><span class="sxs-lookup"><span data-stu-id="89753-116">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="89753-117">Dessa beskrivs i [Konfigurera fristående EOP för att skicka skräp post till skräppostmappen i hybrid miljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span><span class="sxs-lookup"><span data-stu-id="89753-117">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="89753-118">Om du inte vill flytta meddelanden till varje användares skräppost-mapp kan du välja en annan åtgärd genom att redigera principer för skräp post (kallas även för innehålls filter principer).</span><span class="sxs-lookup"><span data-stu-id="89753-118">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="89753-119">Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="89753-119">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="89753-120">Bekräfta e-postflöde</span><span class="sxs-lookup"><span data-stu-id="89753-120">Verify mail flow</span></span>

<span data-ttu-id="89753-121">Om du vill kontrol lera att EOP-konfigurationen, inklusive din anslutnings konfiguration, fungerar som den ska, kan du läsa avsnittet "Hur vet du att den här uppgiften fungerade?"</span><span class="sxs-lookup"><span data-stu-id="89753-121">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?"</span></span> <span data-ttu-id="89753-122">avsnitt i [Konfigurera din EOP-tjänst](set-up-your-eop-service.md).</span><span class="sxs-lookup"><span data-stu-id="89753-122">section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="89753-123">[Testa e-postflöde genom att verifiera dina Microsoft 365-kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) finns anvisningar för testning av att ditt e-postflöde är korrekt konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="89753-123">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
