---
title: Fixa insikter om långsamma flödesregler
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan ta reda på hur de kan använda insikter i artikeln om långsamma e-postflödesregler i Säkerhets- och efterlevnadscenter för & för att identifiera och åtgärda ineffektiva eller bryta e-postflödesregler (kallas även transportregler) i organisationen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 51ffa92402fd3e7c9e76115642426d3cce0a9e19
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207070"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="eabcd-103">Åtgärda insikter om långsamt e-postflödesregler i & Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="eabcd-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="eabcd-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="eabcd-104">**Applies to**</span></span>
- [<span data-ttu-id="eabcd-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="eabcd-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="eabcd-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="eabcd-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="eabcd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eabcd-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="eabcd-108">Ineffektiva e-postflödesregler (kallas även transportregler) kan leda till fördröjningar i e-postflödet för din organisation.</span><span class="sxs-lookup"><span data-stu-id="eabcd-108">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="eabcd-109">Den här insikten rapporterar e-postflödesregler som påverkar organisationens e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="eabcd-109">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="eabcd-110">Exempel på sådana typer av regler är:</span><span class="sxs-lookup"><span data-stu-id="eabcd-110">Examples of these types of rules include:</span></span>

- <span data-ttu-id="eabcd-111">Villkor som används **Är medlem i** stora grupper.</span><span class="sxs-lookup"><span data-stu-id="eabcd-111">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="eabcd-112">Villkor som använder komplexa reguljära uttryck (regex) mönstermatchning.</span><span class="sxs-lookup"><span data-stu-id="eabcd-112">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="eabcd-113">Villkor som använder innehållskontrollen i bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="eabcd-113">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="eabcd-114">Insikten **åtgärda problem med**  långsamma e-postflödesregler i området Rekommenderas för dig på instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för [&](https://protection.office.com) meddelar dig när en e-postflödesregel tar för lång tid att slutföra. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="eabcd-114">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span>

<span data-ttu-id="eabcd-115">Den här insikten visas bara när villkoret har upptäckts (om du inte har några e-postslingor kan du inte se insikten).</span><span class="sxs-lookup"><span data-stu-id="eabcd-115">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="eabcd-116">Du kan använda det här meddelandet för att identifiera och finjustera e-postflödesregler för att minska e-postflödesfördröjningar.</span><span class="sxs-lookup"><span data-stu-id="eabcd-116">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Åtgärda insikt i regler för långsamt e-postflöde i området Rekommenderas för dig på instrumentpanelen för e-postflöde](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="eabcd-118">När du klickar **på Visa information** om widgeten visas en utfäll tillgänglig meny med mer information:</span><span class="sxs-lookup"><span data-stu-id="eabcd-118">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="eabcd-119">**Regel:** Du kan hovra över sammanfattningen för att se alla villkor, undantag och åtgärder för regeln.</span><span class="sxs-lookup"><span data-stu-id="eabcd-119">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="eabcd-120">Du kan klicka på sammanfattningen för att redigera regeln i Administrationscenter för Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="eabcd-120">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="eabcd-121">**Antal meddelanden som utvärderats**  : Du kan [](message-trace-scc.md) klicka på Visa exempelmeddelanden för att visa meddelandespårningsresultaten för ett exempel på meddelanden som påverkades av regeln.</span><span class="sxs-lookup"><span data-stu-id="eabcd-121">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="eabcd-122">**Genomsnittlig tid för varje meddelande**</span><span class="sxs-lookup"><span data-stu-id="eabcd-122">**Average time spent on each message**</span></span>
- <span data-ttu-id="eabcd-123">**Mediantid i ett meddelande**: Det mittersta värdet som separerar den övre halvan från den nedre halvan av tidsdata.</span><span class="sxs-lookup"><span data-stu-id="eabcd-123">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![Information som visas när du klickar på Visa information på åtgärda information för långsamt e-postflödesregler](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="eabcd-125">Mer information om villkor och undantag i e-postflödesregler finns i Villkor för e-postflödesregel och undantag [(predikat) i Exchange Online.](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)</span><span class="sxs-lookup"><span data-stu-id="eabcd-125">For more information about conditions and exceptions in mail flow rules, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="see-also"></a><span data-ttu-id="eabcd-126">Se även</span><span class="sxs-lookup"><span data-stu-id="eabcd-126">See also</span></span>

<span data-ttu-id="eabcd-127">Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinformation i Säkerhets- & efterlevnadscenter.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="eabcd-127">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>