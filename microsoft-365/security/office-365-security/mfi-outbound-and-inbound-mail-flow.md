---
title: Information om utgående och inkommande e-postflöde på instrumentpanelen för e-postflöde
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Administratörer kan läsa mer om information om utgående och inkommande e-postflöde på instrumentpanelen för e-postflöde i & Säkerhets- och efterlevnadscenter.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 87c5bd9ab0d550f50feabbb96176debbe04863e5
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289455"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="626af-103">Information om utgående och inkommande e-postflöde i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="626af-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="626af-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="626af-104">**Applies to**</span></span>
- [<span data-ttu-id="626af-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="626af-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="626af-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="626af-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="626af-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="626af-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="626af-108">Instrumentpanelen **för e-postflöde** i [](mail-flow-insights-v2.md) efterlevnadscentret för [& utgående](https://protection.office.com) och inkommande [](view-mail-flow-reports.md#connector-report) e-post i instrumentpanelen för e-postflöde kombinerar informationen från kopplingsrapporten och den tidigare **TLS-översiktsrapporten** på ett och samma ställe.</span><span class="sxs-lookup"><span data-stu-id="626af-108">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="626af-109">Widgeten visar den TLS-kryptering som används för anslutningen när meddelanden levereras till och från din organisation.</span><span class="sxs-lookup"><span data-stu-id="626af-109">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="626af-110">Anslutningarna som upprättas med andra e-posttjänster krypteras av TLS när TLS erbjuds av båda sidor.</span><span class="sxs-lookup"><span data-stu-id="626af-110">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="626af-111">Widgeten ger en ögonblicksbild av den senaste veckans e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="626af-111">The widget offers a snapshot of the last week of mail flow.</span></span>

![Widget för utgående och inkommande e-postflöde på instrumentpanelen för e-postflöde & Säkerhets- och efterlevnadscenter](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="626af-113">Informationen i widgeten är relaterad till kopplingar och TLS-meddelandeskydd i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="626af-113">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="626af-114">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="626af-114">For more information, see these topics:</span></span>

- [<span data-ttu-id="626af-115">Konfigurera e-postflöde med kopplingar</span><span class="sxs-lookup"><span data-stu-id="626af-115">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="626af-116">Hur Exchange Online använder TLS för att skydda e-postanslutningar</span><span class="sxs-lookup"><span data-stu-id="626af-116">How Exchange Online uses TLS to secure email connections</span></span>](../../compliance/exchange-online-uses-tls-to-secure-email-connections.md)
- [<span data-ttu-id="626af-117">Teknisk referensinformation om kryptering i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="626af-117">Technical reference details about encryption in Microsoft 365</span></span>](../../compliance/technical-reference-details-about-encryption.md)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="626af-118">Meddelande som skyddas under transport (av TLS)</span><span class="sxs-lookup"><span data-stu-id="626af-118">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="626af-119">När du klickar **på Visa** information på widgeten visas TLS-skyddet för meddelanden som matas in och lämnar organisationen i det meddelande som skyddas under överföring **(av TLS).**</span><span class="sxs-lookup"><span data-stu-id="626af-119">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![Meddelanden skyddade under överföring (av TLS) som visas när du klickar på Visa information på widgeten Utgående och inkommande e-post](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="626af-121">För närvarande är TLS 1.2 den säkraste versionen av TLS som erbjuds av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="626af-121">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="626af-122">Ofta måste du känna till den TLS-kryptering som används för granskningar av efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="626af-122">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="626af-123">Du har förmodligen inte en direkt relation med de flesta käll- och mål-e-postservrarna (du äger dem inte och Microsoft har det inte), så du har inte många alternativ för att förbättra den TLS-kryptering som används av de servrarna.</span><span class="sxs-lookup"><span data-stu-id="626af-123">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="626af-124">Men du kan använda kopplingar [för](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) att säkerställa bästa tillgängliga TLS-skydd för meddelanden som skickas mellan dina e-postservrar och Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="626af-124">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="626af-125">E-postflödet mellan Microsoft 365 och dina egna e-postservrar eller servrar som tillhör dina partner är ofta viktigare och känsligare än vanliga meddelanden, så du bör tillämpa extra säkerhet och extra säkerhet på dessa meddelanden.</span><span class="sxs-lookup"><span data-stu-id="626af-125">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="626af-126">Du kan uppgradera eller åtgärda dina egna e-postservrar för att förbättra den TLS-kryptering som används, eller kontakta dina partners för att göra samma sak.</span><span class="sxs-lookup"><span data-stu-id="626af-126">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="626af-127">Kopplingsrapporten **visar** både e-postflödesvolym och TLS-kryptering för meddelanden som använder dina Microsoft 365-kopplingar.</span><span class="sxs-lookup"><span data-stu-id="626af-127">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="626af-128">Du kan klicka på **kopplingens rapportlänk** för att gå till [kopplingsrapporten.](view-mail-flow-reports.md#connector-report)</span><span class="sxs-lookup"><span data-stu-id="626af-128">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="626af-129">Följande information kan vara tillgänglig på sidan **med kopplingsrapporten** om det associerade villkoret har upptäckts:</span><span class="sxs-lookup"><span data-stu-id="626af-129">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="626af-130">**Inkommande partneranslutning ser ett betydande TLS1.0-e-postflöde**</span><span class="sxs-lookup"><span data-stu-id="626af-130">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="626af-131">**Inkommande OnPremises-koppling ser betydande TLS1.0-e-postflöde**</span><span class="sxs-lookup"><span data-stu-id="626af-131">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="626af-132">För TLS 1.0-anslutningar måste du få din e-postserver eller din partners server uppgraderad eller åtgärdad för att undvika problem när TLS 1.0-supporten så småningom är inaktuell i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="626af-132">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="626af-133">Se även</span><span class="sxs-lookup"><span data-stu-id="626af-133">See also</span></span>

<span data-ttu-id="626af-134">Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinsikter i Säkerhets- & Efterlevnadscenter.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="626af-134">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
