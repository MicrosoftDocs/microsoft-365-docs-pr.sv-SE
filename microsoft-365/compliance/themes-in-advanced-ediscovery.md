---
title: Teman – eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Använd teman i Advanced eDiscovery ordna uppsättningar genom att hitta det mest framträdande temat i varje dokument.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/26/2020
ms.locfileid: "52161617"
---
# <a name="themes-in-advanced-ediscovery"></a><span data-ttu-id="643bc-103">Teman i Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="643bc-103">Themes in Advanced eDiscovery</span></span>

<span data-ttu-id="643bc-104">Hur skriver en person ett dokument?</span><span class="sxs-lookup"><span data-stu-id="643bc-104">How does a person write a document?</span></span> <span data-ttu-id="643bc-105">De börjar oftast med en eller flera idéer som de vill förmedla i dokumentet och skriver med ord som passar idéerna.</span><span class="sxs-lookup"><span data-stu-id="643bc-105">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="643bc-106">Ju vanligare en idé är, desto vanligare är de ord som är relaterade till den idén.</span><span class="sxs-lookup"><span data-stu-id="643bc-106">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="643bc-107">Det här informerar även om hur personer använder dokument.</span><span class="sxs-lookup"><span data-stu-id="643bc-107">This informs how people consume documents as well.</span></span> <span data-ttu-id="643bc-108">Det som är viktigt att förstå när du läser ett dokument är de idéer som dokumentet försöker förmedla, vilka idéer som visas var, och vilka relationer mellan idéerna är.</span><span class="sxs-lookup"><span data-stu-id="643bc-108">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="643bc-109">Det kan utökas till hur en person vill använda en uppsättning dokument.</span><span class="sxs-lookup"><span data-stu-id="643bc-109">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="643bc-110">De vill se vilka idéer som finns i uppsättningarna och vilka dokument som talar om dessa idéer.</span><span class="sxs-lookup"><span data-stu-id="643bc-110">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="643bc-111">Dessutom, om de hittar ett visst dokument av intresse, vill de kunna se dokument som diskutera liknande idéer.</span><span class="sxs-lookup"><span data-stu-id="643bc-111">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="643bc-112">Funktionen Teman i Advanced eDiscovery försöker efterlikna hur människor skäl  till dokument genom att analysera de teman som diskuteras i en granskningsuppsättning och tilldela ett tema till dokument i granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="643bc-112">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="643bc-113">I Advanced eDiscovery teman går ett steg längre och identifierar det *mest framträdande temat* i varje dokument.</span><span class="sxs-lookup"><span data-stu-id="643bc-113">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="643bc-114">Det mest framträdande temat är det som visas oftast i ett dokument.</span><span class="sxs-lookup"><span data-stu-id="643bc-114">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="643bc-115">Hur fungerar teman?</span><span class="sxs-lookup"><span data-stu-id="643bc-115">How does Themes work?</span></span>

<span data-ttu-id="643bc-116">Med funktionen Teman analyseras dokument med text i en granskningsuppsättning för att tolka vanliga teman som visas i alla dokument i granskningsuppsättningen.</span><span class="sxs-lookup"><span data-stu-id="643bc-116">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="643bc-117">Advanced eDiscovery tilldelar dessa teman till de dokument där de visas.</span><span class="sxs-lookup"><span data-stu-id="643bc-117">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="643bc-118">Det etiketterar också varje tema med de ord som används i de dokument som är representativa för temat.</span><span class="sxs-lookup"><span data-stu-id="643bc-118">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="643bc-119">Eftersom ett dokument kan innehålla olika typer av ämnen, Advanced eDiscovery ofta flera teman för dokument.</span><span class="sxs-lookup"><span data-stu-id="643bc-119">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="643bc-120">Temat som visas mest framträdande i ett dokument har angetts som dess mest framträdande tema.</span><span class="sxs-lookup"><span data-stu-id="643bc-120">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>
