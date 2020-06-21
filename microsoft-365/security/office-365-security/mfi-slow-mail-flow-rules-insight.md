---
title: Insikt om långsamma e-postflödesregler
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 5/3/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig mer om insikten om långsamma regler för e-postflöde i instrumentpanelen för säkerhets- & compliance.
ms.openlocfilehash: 52ddb6bf5ab6998309fd3122c59636c14b3da1dd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819370"
---
# <a name="slow-mail-flow-rules-insight"></a><span data-ttu-id="a69ed-103">Insikt om långsamma e-postflödesregler</span><span class="sxs-lookup"><span data-stu-id="a69ed-103">Slow mail flow rules insight</span></span>

<span data-ttu-id="a69ed-104">Ineffektiva regler för e-postflöde (kallas även transportregler) kan leda till fördröjningar i e-postflödet för din organisation.</span><span class="sxs-lookup"><span data-stu-id="a69ed-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="a69ed-105">Den här insikten rapporterar regler för e-postflöde som påverkar organisationens e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="a69ed-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="a69ed-106">Exempel på dessa typer av regler är:</span><span class="sxs-lookup"><span data-stu-id="a69ed-106">Examples of these types of rules are:</span></span>

- <span data-ttu-id="a69ed-107">Villkor som används **Är medlem i** för stora grupper.</span><span class="sxs-lookup"><span data-stu-id="a69ed-107">Conditions that use **Is member of** for large groups.</span></span>

- <span data-ttu-id="a69ed-108">Villkor som använder komplexa reguljära uttryck (regex) mönster matchning.</span><span class="sxs-lookup"><span data-stu-id="a69ed-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>

- <span data-ttu-id="a69ed-109">Villkor som använder innehållskontroll i bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="a69ed-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="a69ed-110">Insikten hjälper dig att identifiera och finjustera regler för e-postflöde för att minska fördröjningar i e-postflödet.</span><span class="sxs-lookup"><span data-stu-id="a69ed-110">The insight will help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![En långsam insikt om e-postflödesregler i instrumentpanelen för e-postflödet i Security & Compliance Center](../../media/1dd90faa-f065-4b10-8b47-d35dc127fc26.png)

<span data-ttu-id="a69ed-112">När du klickar på **Visa information**visas ett utfällbart fönster där du kan granska regeln.</span><span class="sxs-lookup"><span data-stu-id="a69ed-112">When you click **View details**, a flyout pane appears where you can review the rule.</span></span> <span data-ttu-id="a69ed-113">I det utfällbara fönstret kan du även klicka på **Visa exempelmeddelanden** för att se vilken typ av meddelanden som påverkas av regeln.</span><span class="sxs-lookup"><span data-stu-id="a69ed-113">In the flyout pane, can also click **view sample messages** to see what kind of messages are impacted by the rule.</span></span>

![Utfällbart fönster efter att ha klickat på Visa information i en långsam insikt om regler för e-postflöde i instrumentpanelen för e-postflödet](../../media/2cbd43b7-1f21-4338-a70c-7b50de5c69cd.png)

## <a name="related-topics"></a><span data-ttu-id="a69ed-115">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="a69ed-115">Related topics</span></span>

<span data-ttu-id="a69ed-116">Mer information om andra insikter om e-postflöde i instrumentpanelen för e-postflödet finns [i Insikterna för e-postflöde i Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="a69ed-116">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
