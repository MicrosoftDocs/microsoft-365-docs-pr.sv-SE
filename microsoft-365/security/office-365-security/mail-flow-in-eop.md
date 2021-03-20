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
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: Administratören kan läsa mer om alternativen för att konfigurera e-postflöde och e-postdirigering i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 043f093c801725cdf006c7c3afe7672e67d9fcef
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907032"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="f884a-103">E-postflöde i EOP</span><span class="sxs-lookup"><span data-stu-id="f884a-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f884a-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="f884a-104">**Applies to**</span></span>
- [<span data-ttu-id="f884a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f884a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f884a-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="f884a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="f884a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f884a-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="f884a-108">I Microsoft 365-organisationer med Exchange Online-postlådor eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor passerar alla meddelanden som skickas till din organisation via EOP innan de anställda ser dem.</span><span class="sxs-lookup"><span data-stu-id="f884a-108">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="f884a-109">Du har alternativ för hur du dirigerar meddelanden som passerar genom EOP för bearbetning innan de dirigeras till dina anställdas inkorgar.</span><span class="sxs-lookup"><span data-stu-id="f884a-109">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="f884a-110">Arbeta med alternativ för meddelanden och meddelandeåtkomst</span><span class="sxs-lookup"><span data-stu-id="f884a-110">Working with messages and message access options</span></span>

<span data-ttu-id="f884a-111">EOP ger flexibilitet i hur dina meddelanden dirigeras.</span><span class="sxs-lookup"><span data-stu-id="f884a-111">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="f884a-112">I följande avsnitt förklaras stegen i e-postflödet.</span><span class="sxs-lookup"><span data-stu-id="f884a-112">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="f884a-113">[Använda katalogbaserad Edge-blockering för att avvisa meddelanden som skickas till ogiltiga mottagare](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Här beskrivs den katalogbaserade gränsblockeringsfunktionen som gör att du kan avvisa meddelanden till ogiltiga mottagare på tjänstens nätverks perimeter.</span><span class="sxs-lookup"><span data-stu-id="f884a-113">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="f884a-114">[I Visa eller Redigera hanterade domäner i EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) beskrivs hur du hanterar domäner som är kopplade till EOP-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f884a-114">[View or Edit Managed Domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="f884a-115">Om du lägger till underdomäner i organisationen kan EOP-tjänsten hjälpa dig att hantera även dessa.</span><span class="sxs-lookup"><span data-stu-id="f884a-115">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="f884a-116">Läs mer om underdomäner i [Aktivera e-postflöde för underdomäner i Exchange Online.](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)</span><span class="sxs-lookup"><span data-stu-id="f884a-116">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="f884a-117">[Genom att konfigurera e-postflödet med kopplingar](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduceras kopplingar och du ser hur du kan använda dem för att anpassa e-postdirigeringen.</span><span class="sxs-lookup"><span data-stu-id="f884a-117">[Configure mail flow using connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="f884a-118">Scenarierna omfattar att säkerställa säker kommunikation med en partnerorganisation och konfigurera en smart värd.</span><span class="sxs-lookup"><span data-stu-id="f884a-118">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="f884a-119">[Förbättrad filtrering för kopplingar beskriver](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) hur du konfigurerar kopplingar om din e-post dirigeras till en tjänst eller enhet före EOP.</span><span class="sxs-lookup"><span data-stu-id="f884a-119">[Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="f884a-120">I fristående EOP-organisationer måste du utföra ett par konfigurationssteg för att se till att skräppost dirigeras korrekt till varje användares skräppostmapp.</span><span class="sxs-lookup"><span data-stu-id="f884a-120">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="f884a-121">Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)</span><span class="sxs-lookup"><span data-stu-id="f884a-121">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="f884a-122">Om du inte vill flytta meddelanden till varje användares skräppostmapp kan du välja en annan åtgärd genom att redigera principerna för skydd mot skräppost (kallas även principer för innehållsfilter).</span><span class="sxs-lookup"><span data-stu-id="f884a-122">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="f884a-123">Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f884a-123">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="f884a-124">Kontrollera e-postflödet</span><span class="sxs-lookup"><span data-stu-id="f884a-124">Verify mail flow</span></span>

<span data-ttu-id="f884a-125">Kontrollera att EOP-konfigurationen, inklusive anslutningskonfigurationen, fungerar som den ska genom att gå till "Hur vet du att uppgiften fungerade?"</span><span class="sxs-lookup"><span data-stu-id="f884a-125">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?"</span></span> <span data-ttu-id="f884a-126">i Konfigurera [EOP-tjänsten](set-up-your-eop-service.md).</span><span class="sxs-lookup"><span data-stu-id="f884a-126">section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="f884a-127">[Testa e-postflödet genom att verifiera dina Microsoft 365-kopplingar](/exchange/mail-flow-best-practices/test-mail-flow) ger instruktioner för att testa att e-postflödet är korrekt inställt.</span><span class="sxs-lookup"><span data-stu-id="f884a-127">[Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>