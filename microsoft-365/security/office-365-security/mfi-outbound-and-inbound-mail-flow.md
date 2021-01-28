---
title: Utgående och inkommande e-postflöde i instrument panelen för e-postflöde
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
description: Administratörer kan lära sig mer om utgående och inkommande e-postflöde i instrument panelen för e-postflöde i säkerhets & Compliance Center.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e46a0ebf0c14e31462d1e86d8a8d8c08486337af
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029828"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="d5b30-103">Utgående och inkommande e-postflöde inblick i säkerhets-& Compliance Center</span><span class="sxs-lookup"><span data-stu-id="d5b30-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d5b30-104">Det **utgående och inkommande e-postflödet** inblickar i [instrument panelen för e-postflöden](mail-flow-insights-v2.md) i [säkerhets & Compliance Center](https://protection.office.com) kombinerar informationen från [kopplings rapporten](view-mail-flow-reports.md#connector-report) och den tidigare **TLS-översikten** på ett och samma ställe.</span><span class="sxs-lookup"><span data-stu-id="d5b30-104">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="d5b30-105">Widgeten visar TLS-kryptering som används för anslutningen när meddelanden levereras till och från din organisation.</span><span class="sxs-lookup"><span data-stu-id="d5b30-105">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="d5b30-106">De anslutningar som upprättas med andra e-posttjänster krypteras av TLS när TLS erbjuds på båda sidor.</span><span class="sxs-lookup"><span data-stu-id="d5b30-106">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="d5b30-107">Widgeten erbjuder en ögonblicks bild av den sista veckan i e-postflödet.</span><span class="sxs-lookup"><span data-stu-id="d5b30-107">The widget offers a snapshot of the last week of mail flow.</span></span>

![Widget för utgående och inkommande e-post i instrument panelen för e-postflöde i säkerhets & Compliance Center](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="d5b30-109">Informationen i widgeten är relaterad till kopplingar och skydd mot TLS-meddelanden i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d5b30-109">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="d5b30-110">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="d5b30-110">For more information, see these topics:</span></span>

- [<span data-ttu-id="d5b30-111">Konfigurera e-postflöde med kopplingar</span><span class="sxs-lookup"><span data-stu-id="d5b30-111">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="d5b30-112">Så här använder Exchange Online TLS för att skydda e-postanslutningar</span><span class="sxs-lookup"><span data-stu-id="d5b30-112">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="d5b30-113">Teknisk information om kryptering i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d5b30-113">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="d5b30-114">Meddelande skyddat i transit (via TLS)</span><span class="sxs-lookup"><span data-stu-id="d5b30-114">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="d5b30-115">När du klickar på **Visa information** i widgeten visas TLS **-** skyddet för meddelanden som anger och lämnar din organisation.</span><span class="sxs-lookup"><span data-stu-id="d5b30-115">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![Meddelanden skyddade i transit (av TLS) utfällda som visas när du klickar på Visa information i widgeten utgående och inkommande e-post](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="d5b30-117">För närvarande är TLS 1,2 den säkraste versionen av TLS som erbjuds av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d5b30-117">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="d5b30-118">Du behöver ofta veta vilken TLS-kryptering som används för granskning av efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="d5b30-118">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="d5b30-119">Du har antagligen inget direkt förhållande till de flesta käll-och mål-e-postservrar (du inte äger dem och inte heller Microsoft), så du har inte många alternativ för att förbättra TLS-krypteringen som används av dessa servrar.</span><span class="sxs-lookup"><span data-stu-id="d5b30-119">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="d5b30-120">Men du kan använda [kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) för att se till att det bästa tillgängliga TLS-skyddet för meddelanden som skickas mellan dina e-postservrar och Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d5b30-120">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="d5b30-121">E-postflöde mellan Microsoft 365 och dina egna e-postservrar eller servrar som tillhör dina partners är ofta mer viktigare än vanliga meddelanden, så du bör tillämpa extra säkerhet och vaksamhet på dessa meddelanden.</span><span class="sxs-lookup"><span data-stu-id="d5b30-121">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="d5b30-122">Du kan uppgradera eller fixa dina egna e-postservrar för att förbättra den TLS-kryptering som används, eller nå dina partners för att göra det.</span><span class="sxs-lookup"><span data-stu-id="d5b30-122">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="d5b30-123">I **kopplings rapporten** visas både mail flödes volym och TLS-kryptering för meddelanden som använder dina Microsoft 365-kopplingar.</span><span class="sxs-lookup"><span data-stu-id="d5b30-123">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="d5b30-124">Du kan klicka på **kopplings rapport** länken för att gå till [kopplings rapporten](view-mail-flow-reports.md#connector-report).</span><span class="sxs-lookup"><span data-stu-id="d5b30-124">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="d5b30-125">Följande insikter kan vara tillgängliga på **kopplings rapport** sidan om det associerade villkoret har identifierats:</span><span class="sxs-lookup"><span data-stu-id="d5b30-125">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="d5b30-126">**Inkommande partner Connector ser betydelsefullt TLS 1.0-e-postflöde**</span><span class="sxs-lookup"><span data-stu-id="d5b30-126">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="d5b30-127">**Inkommande OnPremises-koppling som ser betydelsefullt TLS 1.0-e-postflöde**</span><span class="sxs-lookup"><span data-stu-id="d5b30-127">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="d5b30-128">För TLS 1,0-anslutningar måste du verkligen få e-postservern eller din partners server att uppgraderas eller åtgärdas för att undvika problem när stöd för TLS 1,0 är föråldrat i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d5b30-128">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5b30-129">Se även</span><span class="sxs-lookup"><span data-stu-id="d5b30-129">See also</span></span>

<span data-ttu-id="d5b30-130">Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="d5b30-130">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
