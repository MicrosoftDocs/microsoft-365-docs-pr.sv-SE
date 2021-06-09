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
description: Administratören kan läsa mer om alternativen för att konfigurera e-postflöde och e-Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9636025796aee1ba2027edff38a16f131974134f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842500"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="11c8c-103">E-postflöde i EOP</span><span class="sxs-lookup"><span data-stu-id="11c8c-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="11c8c-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="11c8c-104">**Applies to**</span></span>
- [<span data-ttu-id="11c8c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="11c8c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="11c8c-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="11c8c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="11c8c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="11c8c-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="11c8c-108">I Microsoft 365 organisationer som har Exchange Online-postlådor eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor passerar alla meddelanden som skickas till din organisation via EOP innan medarbetarna ser dem.</span><span class="sxs-lookup"><span data-stu-id="11c8c-108">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="11c8c-109">Du har alternativ för hur du dirigerar meddelanden som passerar genom EOP för bearbetning innan de dirigeras till dina anställdas inkorgar.</span><span class="sxs-lookup"><span data-stu-id="11c8c-109">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="11c8c-110">Arbeta med alternativ för meddelanden och meddelandeåtkomst</span><span class="sxs-lookup"><span data-stu-id="11c8c-110">Working with messages and message access options</span></span>

<span data-ttu-id="11c8c-111">EOP ger flexibilitet i hur dina meddelanden dirigeras.</span><span class="sxs-lookup"><span data-stu-id="11c8c-111">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="11c8c-112">I följande avsnitt förklaras stegen i e-postflödet.</span><span class="sxs-lookup"><span data-stu-id="11c8c-112">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="11c8c-113">[Använda katalogbaserad Edge-blockering för att avvisa meddelanden som skickas till ogiltiga mottagare](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Här beskrivs den katalogbaserade gränsblockeringsfunktionen som gör att du kan avvisa meddelanden till ogiltiga mottagare på tjänstens nätverks perimeter.</span><span class="sxs-lookup"><span data-stu-id="11c8c-113">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="11c8c-114">[Visa eller redigera godkända domäner i EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) beskriver hur du hanterar domäner som är kopplade till EOP-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="11c8c-114">[View or edit accepted domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="11c8c-115">Om du lägger till underdomäner i organisationen kan EOP-tjänsten hjälpa dig att hantera även dessa.</span><span class="sxs-lookup"><span data-stu-id="11c8c-115">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="11c8c-116">Läs mer om underdomäner i [Aktivera e-postflöde för underdomäner i Exchange Online.](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)</span><span class="sxs-lookup"><span data-stu-id="11c8c-116">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="11c8c-117">[Genom att konfigurera e-postflödet med kopplingar](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduceras kopplingar och du ser hur du kan använda dem för att anpassa e-postdirigeringen.</span><span class="sxs-lookup"><span data-stu-id="11c8c-117">[Configure mail flow using connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="11c8c-118">Scenarierna omfattar att säkerställa säker kommunikation med en partnerorganisation och konfigurera en smart värd.</span><span class="sxs-lookup"><span data-stu-id="11c8c-118">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="11c8c-119">[Förbättrad filtrering för kopplingar beskriver](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) hur du konfigurerar kopplingar om din e-post dirigeras till en tjänst eller enhet före EOP.</span><span class="sxs-lookup"><span data-stu-id="11c8c-119">[Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="11c8c-120">I hybridmiljöer där EOP skyddar lokala Exchange-postlådor måste du konfigurera e-postflödesregler (kallas även för transportregler) i lokalt Exchange för att översätta utfallet av skräppostfiltreringen i EOP så att regeln för skräppost kan flytta meddelandet till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="11c8c-120">In hybrid environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="11c8c-121">Mer information finns i [Konfigurera EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).</span><span class="sxs-lookup"><span data-stu-id="11c8c-121">For details, see [Configure EOP to deliver spam to the Junk Email folder in hybrid environments](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).</span></span> <span data-ttu-id="11c8c-122">Om du inte vill flytta meddelanden till varje användares skräppostmapp kan du välja en annan åtgärd genom att redigera principerna för skräppostskydd (kallas även principer för innehållsfilter).</span><span class="sxs-lookup"><span data-stu-id="11c8c-122">If you don't  want to move messages to each user's Junk Email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="11c8c-123">Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="11c8c-123">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="11c8c-124">Kontrollera e-postflödet</span><span class="sxs-lookup"><span data-stu-id="11c8c-124">Verify mail flow</span></span>

<span data-ttu-id="11c8c-125">Kontrollera att EOP-konfigurationen, inklusive anslutningskonfigurationen, fungerar som den ska genom att gå till "Hur vet du att uppgiften fungerade?"</span><span class="sxs-lookup"><span data-stu-id="11c8c-125">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?"</span></span> <span data-ttu-id="11c8c-126">i Konfigurera [EOP-tjänsten](/exchange/standalone-eop/set-up-your-eop-service).</span><span class="sxs-lookup"><span data-stu-id="11c8c-126">section in [Set up your EOP service](/exchange/standalone-eop/set-up-your-eop-service).</span></span>

<span data-ttu-id="11c8c-127">[Testa e-postflödet genom att verifiera Microsoft 365-anslutningarna](/exchange/mail-flow-best-practices/test-mail-flow) ger instruktioner för att testa att e-postflödet är korrekt inställt.</span><span class="sxs-lookup"><span data-stu-id="11c8c-127">[Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
