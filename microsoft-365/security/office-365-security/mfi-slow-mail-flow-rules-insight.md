---
title: Fixa insikter om långsamma flödesregler
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig att använda åtgärds reglerna för långsam e-postflöde inblick i säkerhets & Compliance Center för att identifiera och åtgärda ineffektiva eller felaktiga regler för e-postflöde (kallas även transport regler) i organisationen.
ms.openlocfilehash: 6a2a3c42eadf3c621b34d2a21344eafd2618e669
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877543"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="84dac-103">Åtgärda regler för långsam e-postflöde inblick i centret för säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="84dac-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="84dac-104">Ineffektiva regler för e-postflöde (kallas även transport regler) kan leda till fördröjning i e-postflöden för din organisation.</span><span class="sxs-lookup"><span data-stu-id="84dac-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="84dac-105">Den här Insight rapporterar regler för e-postflöde som påverkar organisationens e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="84dac-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="84dac-106">Här följer exempel på dessa typer av regler:</span><span class="sxs-lookup"><span data-stu-id="84dac-106">Examples of these types of rules include:</span></span>

- <span data-ttu-id="84dac-107">De villkor som används **är medlemmar i** för stora grupper.</span><span class="sxs-lookup"><span data-stu-id="84dac-107">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="84dac-108">Villkor som använder regex-mönster matchning (komplext).</span><span class="sxs-lookup"><span data-stu-id="84dac-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="84dac-109">Villkor som använder innehålls kontroll i bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="84dac-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="84dac-110">Reglerna för att **åtgärda långsamma e-postflöde** är inblickade i det **rekommenderade för dig** -området i [instrument panelen för e-postflöde](mail-flow-insights-v2.md) i [säkerhets & efterlevnaden](https://protection.office.com) meddelar dig när det tar för lång tid att slutföra en regel för e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="84dac-110">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span> <span data-ttu-id="84dac-111">Denna inblick visas bara efter det att villkoret har identifierats (om du inte har några e-postloopar visas inte inblicken).</span><span class="sxs-lookup"><span data-stu-id="84dac-111">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="84dac-112">Du kan använda det här meddelandet för att identifiera och finjustera regler för e-postflöde för att minska fördröjningar för e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="84dac-112">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Åtgärda regler för långsam e-postflöde inblick i det rekommenderade för dig-området på instrument panelen för e-postflöde](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="84dac-114">När du klickar på **Visa information** i widgeten visas en utfällbar lista med mer information:</span><span class="sxs-lookup"><span data-stu-id="84dac-114">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="84dac-115">**Regel** : du kan hovra över sammanfattningen för att se alla villkor, undantag och åtgärder för regeln.</span><span class="sxs-lookup"><span data-stu-id="84dac-115">**Rule** : You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="84dac-116">Du kan klicka på sammanfattningen för att redigera regeln i administrations centret för Exchange (UK).</span><span class="sxs-lookup"><span data-stu-id="84dac-116">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="84dac-117">**Antal meddelanden som utvärderats** : du kan klicka på **Visa exempel meddelanden** [om du vill visa resultaten för](message-trace-scc.md) ett urval av de meddelanden som påverkade regeln.</span><span class="sxs-lookup"><span data-stu-id="84dac-117">**Number of messages evaluated** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="84dac-118">**Genomsnittlig tid som lagts ned på varje meddelande**</span><span class="sxs-lookup"><span data-stu-id="84dac-118">**Average time spent on each message**</span></span>
- <span data-ttu-id="84dac-119">**Median tid som lagts på ett meddelande** : det mittersta värdet som avgränsar den övre halvan från den nedre halvan av tidsdata.</span><span class="sxs-lookup"><span data-stu-id="84dac-119">**Median time spent on a message** : The middle value that separates the upper half from the lower half of time data.</span></span>

![Den utfällbara informationen som visas när du klickar på Visa information om regler för att åtgärda långsamma e-postflöde inblick](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="84dac-121">Mer information om villkor och undantag i regler för e-postflöden i Exchange Online finns i [villkor och undantag för e-postflödes regler (predikat) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span><span class="sxs-lookup"><span data-stu-id="84dac-121">For more information about conditions and exceptions in mail flow rules in Exchange Online, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="related-topics"></a><span data-ttu-id="84dac-122">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="84dac-122">Related topics</span></span>

<span data-ttu-id="84dac-123">Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="84dac-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
