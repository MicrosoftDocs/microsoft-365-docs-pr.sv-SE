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
description: Administratörer kan ta reda på hur de kan använda information om åtgärda långsam e-postflödesregler i Säkerhets- & och efterlevnadscenter för att identifiera och åtgärda ineffektiva eller trasiga e-postflödesregler (kallas även transportregler) i organisationen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7f084735decda922b5bcc57c029f2b384114d30
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150790"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="3d610-103">Åtgärda information om regler för långsamt e-postflöde & Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="3d610-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3d610-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="3d610-104">**Applies to**</span></span>
- [<span data-ttu-id="3d610-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3d610-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="3d610-106">Microsoft Defender för Office 365 abonnemang 1 och abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="3d610-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="3d610-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3d610-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="3d610-108">Ineffektiva e-postflödesregler (kallas även transportregler) kan leda till e-postflödesfördröjningar för organisationen.</span><span class="sxs-lookup"><span data-stu-id="3d610-108">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="3d610-109">Den här insikten rapporterar e-postflödesregler som påverkar organisationens e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="3d610-109">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="3d610-110">Exempel på dessa typer av regler är:</span><span class="sxs-lookup"><span data-stu-id="3d610-110">Examples of these types of rules include:</span></span>

- <span data-ttu-id="3d610-111">Villkor som använder **Är medlem i** stora grupper.</span><span class="sxs-lookup"><span data-stu-id="3d610-111">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="3d610-112">Villkor som använder komplexa reguljära uttryck (regex) mönstermatchning.</span><span class="sxs-lookup"><span data-stu-id="3d610-112">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="3d610-113">Villkor som använder innehåll som checkar in bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="3d610-113">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="3d610-114">Insikten **för Åtgärda** långsamt  e-postflödesregler [](mail-flow-insights-v2.md) i området Rekommenderas för dig på instrumentpanelen för e-postflöde i Säkerhets- [& och](https://protection.office.com) efterlevnadscenter meddelar dig när en e-postflödesregel tar för lång tid att slutföra.</span><span class="sxs-lookup"><span data-stu-id="3d610-114">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span>

<span data-ttu-id="3d610-115">Den här insikten visas bara när villkoret har upptäckts (om du inte har några e-postslingor kan du inte se insikten).</span><span class="sxs-lookup"><span data-stu-id="3d610-115">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="3d610-116">Du kan använda det här meddelandet för att identifiera och finjustera e-postflödesregler för att minska e-postflödesfördröjningar.</span><span class="sxs-lookup"><span data-stu-id="3d610-116">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Åtgärda insikter för långsamt e-postflödesregler i området Rekommenderas för dig på instrumentpanelen för e-postflöde](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="3d610-118">När du klickar **på Visa** information på widgeten visas en utfäll tillgänglig meny med mer information:</span><span class="sxs-lookup"><span data-stu-id="3d610-118">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="3d610-119">**Regel:** Du kan hovra över sammanfattningen för att se alla villkor, undantag och åtgärder för regeln.</span><span class="sxs-lookup"><span data-stu-id="3d610-119">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="3d610-120">Klicka på sammanfattningen om du vill redigera regeln i administrationscentret för Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="3d610-120">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="3d610-121">**Antal meddelanden som utvärderats**  : Du kan [](message-trace-scc.md) klicka på Visa exempelmeddelanden för att visa meddelandespårningsresultaten för ett exempel på meddelanden som har påverkats av regeln.</span><span class="sxs-lookup"><span data-stu-id="3d610-121">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="3d610-122">**Genomsnittlig tid för varje meddelande**</span><span class="sxs-lookup"><span data-stu-id="3d610-122">**Average time spent on each message**</span></span>
- <span data-ttu-id="3d610-123">**Mediantiden för ett meddelande:** Det mittersta värdet som separerar den övre halvan från den nedre halvan av tidsdata.</span><span class="sxs-lookup"><span data-stu-id="3d610-123">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![Information som visas när du klickar på Visa information på insikten Åtgärda långsam e-postflödesregler](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="3d610-125">Mer information om villkor och undantag i e-postflödesregler finns i Villkoren för e-postflödesregel och undantag [(predikat) i Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)</span><span class="sxs-lookup"><span data-stu-id="3d610-125">For more information about conditions and exceptions in mail flow rules, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="see-also"></a><span data-ttu-id="3d610-126">Se även</span><span class="sxs-lookup"><span data-stu-id="3d610-126">See also</span></span>

<span data-ttu-id="3d610-127">Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinsikter i Säkerhets- & Efterlevnadscenter.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="3d610-127">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
