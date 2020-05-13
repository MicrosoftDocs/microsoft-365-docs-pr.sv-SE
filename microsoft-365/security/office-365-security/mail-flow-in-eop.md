---
title: E-postflöde i EOP
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
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: Administratören kan lära sig mer om alternativen för att konfigurera e-postflöde och routning i Exchange Online Protection (EOP).
ms.openlocfilehash: cb2ae7370d50fe32802ad5c279cc2170eb35f581
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208336"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="6832c-103">E-postflöde i EOP</span><span class="sxs-lookup"><span data-stu-id="6832c-103">Mail flow in EOP</span></span>

<span data-ttu-id="6832c-104">I Microsoft 365-organisationer med Exchange Online-postlådor eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor passerar alla meddelanden som skickas till din organisation EOP innan dina arbetare ser dem.</span><span class="sxs-lookup"><span data-stu-id="6832c-104">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="6832c-105">Du har alternativ för hur du dirigerar meddelanden som passerar via EOP för bearbetning innan de dirigeras till dina arbetskorgar.</span><span class="sxs-lookup"><span data-stu-id="6832c-105">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="6832c-106">Arbeta med meddelanden och alternativ för meddelandeåtkomst</span><span class="sxs-lookup"><span data-stu-id="6832c-106">Working with messages and message access options</span></span>

<span data-ttu-id="6832c-107">EOP erbjuder flexibilitet i hur dina meddelanden dirigeras.</span><span class="sxs-lookup"><span data-stu-id="6832c-107">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="6832c-108">I följande avsnitt beskrivs steg i e-postflödesprocessen.</span><span class="sxs-lookup"><span data-stu-id="6832c-108">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="6832c-109">[Använda katalogbaserad kantblockering för att avvisa meddelanden som skickas till ogiltiga mottagare](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) I artikeln beskrivs funktionen Directory Based Edge Blocking som gör att du kan avvisa meddelanden för ogiltiga mottagare vid tjänstnätverkets omkrets.</span><span class="sxs-lookup"><span data-stu-id="6832c-109">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="6832c-110">[Visa eller redigera hanterade domäner i EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) beskriver hur du hanterar domäner som är associerade med din EOP-tjänst.</span><span class="sxs-lookup"><span data-stu-id="6832c-110">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="6832c-111">Om du lägger till underdomäner i din organisation kan din EOP-tjänst hjälpa dig att hantera dessa också.</span><span class="sxs-lookup"><span data-stu-id="6832c-111">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="6832c-112">Läs mer om underdomäner på [Aktivera e-postflöde för underdomäner i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span><span class="sxs-lookup"><span data-stu-id="6832c-112">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="6832c-113">[Konfigurera e-postflöde med kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introducerar kopplingar och visar hur du kan använda dem för att anpassa e-postroutning.</span><span class="sxs-lookup"><span data-stu-id="6832c-113">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="6832c-114">Scenarier inkluderar att säkerställa säker kommunikation med en partnerorganisation och konfigurera en smart värd.</span><span class="sxs-lookup"><span data-stu-id="6832c-114">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="6832c-115">[Förbättrad filtrering för anslutningsappar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) beskriver hur du konfigurerar kopplingar om din e-post dirigeras till en tjänst eller enhet före EOP.</span><span class="sxs-lookup"><span data-stu-id="6832c-115">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="6832c-116">I fristående EOP-organisationer måste du utföra ett par konfigurationssteg för att säkerställa att skräppost dirigeras korrekt till varje användares skräppostmapp.</span><span class="sxs-lookup"><span data-stu-id="6832c-116">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="6832c-117">Dessa beskrivs i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span><span class="sxs-lookup"><span data-stu-id="6832c-117">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="6832c-118">Om du inte vill flytta meddelanden till varje användares skräppostmapp kan du välja en annan åtgärd genom att redigera dina policyer mot skräppost (kallas även principer för innehållsfilter).</span><span class="sxs-lookup"><span data-stu-id="6832c-118">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="6832c-119">Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6832c-119">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="6832c-120">Verifiera e-postflöde</span><span class="sxs-lookup"><span data-stu-id="6832c-120">Verify mail flow</span></span>

<span data-ttu-id="6832c-121">Om du vill kontrollera att eop-konfigurationen, inklusive anslutningskonfigurationen, fungerar korrekt läser du "Hur vet du att den här uppgiften fungerade?"</span><span class="sxs-lookup"><span data-stu-id="6832c-121">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?"</span></span> <span data-ttu-id="6832c-122">i [Konfigurera din EOP-tjänst](set-up-your-eop-service.md).</span><span class="sxs-lookup"><span data-stu-id="6832c-122">section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="6832c-123">[Testa e-postflödet genom att validera dina Microsoft 365-kontakter](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) innehåller instruktioner för hur du testar att e-postflödet är korrekt konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="6832c-123">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
