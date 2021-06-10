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
description: Administratörer kan få mer information om insikter i utgående och inkommande e-postflöde i instrumentpanelen för e-postflöde i & Säkerhets- och efterlevnadscenter.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a3117223e466a4a7aad7edf25ecdbcf0a3de719
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207071"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="1c3d4-103">Information om utgående och inkommande e-postflöde i & Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="1c3d4-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1c3d4-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="1c3d4-104">**Applies to**</span></span>
- [<span data-ttu-id="1c3d4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1c3d4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1c3d4-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="1c3d4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1c3d4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c3d4-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1c3d4-108">Den utgående och **inkommande** e-postflödets insikt i instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för [&](https://protection.office.com) kombinerar informationen från kopplingsrapporten och den tidigare [](mail-flow-insights-v2.md) **TLS-översiktsrapporten** på ett och samma ställe. [](view-mail-flow-reports.md#connector-report)</span><span class="sxs-lookup"><span data-stu-id="1c3d4-108">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="1c3d4-109">Widgeten visar den TLS-kryptering som används för anslutningen när meddelanden levereras till och från din organisation.</span><span class="sxs-lookup"><span data-stu-id="1c3d4-109">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="1c3d4-110">Anslutningarna som upprättas med andra e-posttjänster krypteras med TLS när TLS erbjuds av båda sidor.</span><span class="sxs-lookup"><span data-stu-id="1c3d4-110">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="1c3d4-111">Widgeten ger en ögonblicksbild av den senaste veckans e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="1c3d4-111">The widget offers a snapshot of the last week of mail flow.</span></span>

![Widget för utgående och inkommande e-postflöde i instrumentpanelen för e-postflöde & Säkerhets- och efterlevnadscenter](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="1c3d4-113">Informationen i widgeten är relaterad till kopplingar och TLS-meddelandeskydd i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c3d4-113">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="1c3d4-114">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="1c3d4-114">For more information, see these topics:</span></span>

- [<span data-ttu-id="1c3d4-115">Konfigurera e-postflöde med kopplingar</span><span class="sxs-lookup"><span data-stu-id="1c3d4-115">Configure mail flow using connectors</span></span>](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="1c3d4-116">Hur Exchange Online TLS för att skydda e-postanslutningar</span><span class="sxs-lookup"><span data-stu-id="1c3d4-116">How Exchange Online uses TLS to secure email connections</span></span>](../../compliance/exchange-online-uses-tls-to-secure-email-connections.md)
- [<span data-ttu-id="1c3d4-117">Teknisk referensinformation om kryptering i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1c3d4-117">Technical reference details about encryption in Microsoft 365</span></span>](../../compliance/technical-reference-details-about-encryption.md)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="1c3d4-118">Meddelande som skyddas under överföring (av TLS)</span><span class="sxs-lookup"><span data-stu-id="1c3d4-118">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="1c3d4-119">När du klickar **på Visa** information på widgeten visas TLS-skyddet för meddelanden som skickas **(via TLS)** i den utfällade meddelandeskyddsvyn för meddelanden som skickas och lämnar organisationen.</span><span class="sxs-lookup"><span data-stu-id="1c3d4-119">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![Meddelanden som skyddas under överföring (med TLS) som visas när du klickar på Visa information om widgeten Utgående och inkommande e-post](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="1c3d4-121">För närvarande är TLS 1.2 den säkraste versionen av TLS som erbjuds av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c3d4-121">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="1c3d4-122">Ofta måste du känna till den TLS-kryptering som används för granskningar av efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="1c3d4-122">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="1c3d4-123">Du har förmodligen inte en direkt relation till de flesta käll- och mål-e-postservrarna (du äger dem inte och inte Microsoft), så du har inte många alternativ för att förbättra TLS-krypteringen som används av de servrarna.</span><span class="sxs-lookup"><span data-stu-id="1c3d4-123">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="1c3d4-124">Men du kan använda kopplingar [för att](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) säkerställa bästa tillgängliga TLS-skydd för meddelanden som skickas mellan dina e-postservrar och Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c3d4-124">But, you can use [connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="1c3d4-125">E-postflödet mellan Microsoft 365 och dina egna e-postservrar eller servrar som tillhör dina partners är ofta viktigare och känsligare än vanliga meddelanden, så du bör tillämpa extra säkerhet och uppmärksamhet på dessa meddelanden.</span><span class="sxs-lookup"><span data-stu-id="1c3d4-125">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="1c3d4-126">Du kan uppgradera eller åtgärda dina egna e-postservrar för att förbättra den TLS-kryptering som används, eller kontakta dina partners för att göra samma sak.</span><span class="sxs-lookup"><span data-stu-id="1c3d4-126">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="1c3d4-127">I **kopplingsrapporten visas** både volymen för e-postflödet och TLS-krypteringen för meddelanden som Microsoft 365-kopplingarna.</span><span class="sxs-lookup"><span data-stu-id="1c3d4-127">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="1c3d4-128">Du kan klicka på **kopplingsrapportlänken** om du vill gå till [kopplingsrapporten.](view-mail-flow-reports.md#connector-report)</span><span class="sxs-lookup"><span data-stu-id="1c3d4-128">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="1c3d4-129">Följande information kan vara tillgänglig på sidan **för kopplingsrapport** om det associerade villkoret har upptäckts:</span><span class="sxs-lookup"><span data-stu-id="1c3d4-129">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="1c3d4-130">**Inkommande partneranslutning ser betydande TLS1.0-e-postflöde**</span><span class="sxs-lookup"><span data-stu-id="1c3d4-130">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="1c3d4-131">**Inkommande onpremises-anslutning ser betydande TLS1.0-e-postflöde**</span><span class="sxs-lookup"><span data-stu-id="1c3d4-131">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="1c3d4-132">För TLS 1.0-anslutningar måste du få din e-postserver eller din partners server uppgraderad eller åtgärdad för att undvika problem när TLS 1.0-supporten så småningom är inaktuell i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c3d4-132">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c3d4-133">Se även</span><span class="sxs-lookup"><span data-stu-id="1c3d4-133">See also</span></span>

<span data-ttu-id="1c3d4-134">Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinformation i Säkerhets- & efterlevnadscenter.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="1c3d4-134">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>