---
title: Arbeta med kommunikation i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery det enkelt att hantera arbetsflödet för meddelanden om juridiskt förvaring kring avisering av dokument i juridiska undersökningar.
ms.openlocfilehash: 28b719a83cbc1608ad5468e401a8b7946cb8da5f
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/17/2020
ms.locfileid: "52161507"
---
# <a name="work-with-communications-in-advanced-ediscovery"></a><span data-ttu-id="6cd49-103">Arbeta med kommunikation i Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="6cd49-103">Work with communications in Advanced eDiscovery</span></span>

<span data-ttu-id="6cd49-104">Advanced eDiscovery tillåter juridiska avdelningar att förenkla sina processer kring uppföljning och distribution av aviseringar om juridiska frågor.</span><span class="sxs-lookup"><span data-stu-id="6cd49-104">Advanced eDiscovery allows legal departments to simplify their processes around tracking and distributing legal hold notifications.</span></span> <span data-ttu-id="6cd49-105">Det juridiska verktyget för kommunikation gör det möjligt för juridiska avdelningar att hantera och automatisera hela processen för juridiska frågor, från inledande aviseringar, till påminnelser och eskalering, allt på ett och samma ställe.</span><span class="sxs-lookup"><span data-stu-id="6cd49-105">The custodian communications tool enables legal departments to manage and automate the entire legal hold process, from initial notifications, to reminders, and to escalations, all in one location.</span></span>

## <a name="what-is-a-legal-hold-notification"></a><span data-ttu-id="6cd49-106">Vad är en avisering om juridiskt betalningskavisering?</span><span class="sxs-lookup"><span data-stu-id="6cd49-106">What is a legal hold notification?</span></span>

<span data-ttu-id="6cd49-107">Ett meddelande om bevarande av juridiska skäl (kallas även bevarande av juridiska *skäl)* är ett meddelande som skickas från en organisations juridiska avdelning till anställda, personal eller tjänsteanställda med data som kan vara relevanta för en juridisk undersökning.</span><span class="sxs-lookup"><span data-stu-id="6cd49-107">A legal hold (also known as a *litigation hold*) notice is a notification sent from an organization’s legal department to employees, contingent staff, or custodians of data that may be relevant to a legal investigation.</span></span> <span data-ttu-id="6cd49-108">De här meddelandena instruerar biblioteken att bevara elektroniskt lagrad information samt allt innehåll som kan vara relevant för en aktiv eller väntande juridisk fråga.</span><span class="sxs-lookup"><span data-stu-id="6cd49-108">These notifications instruct custodians to preserve electronically stored information as well as any content that may be relevant to an active or impending legal matter.</span></span> <span data-ttu-id="6cd49-109">Juridiska grupper måste veta att varje enskild vårdnadshavare har tagit emot, läst, förstått och har gått med på att följa de givna instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="6cd49-109">Legal teams must know that each custodian has received, read, understood, and has agreed to comply with the given instructions.</span></span>

## <a name="the-legal-hold-notification-process"></a><span data-ttu-id="6cd49-110">Processen för att meddela om juridiskt väntande arbete</span><span class="sxs-lookup"><span data-stu-id="6cd49-110">The legal hold notification process</span></span>

<span data-ttu-id="6cd49-111">En organisation har en skyldighet att bevara relevant information när den lär sig om en pågående rättstvist eller regelundersökning.</span><span class="sxs-lookup"><span data-stu-id="6cd49-111">An organization has a duty to preserve relevant information when it learns about an impending litigation or regulatory investigation.</span></span> <span data-ttu-id="6cd49-112">I syfte att uppfylla bevarandekraven för en undersökning bör organisationen omedelbart informera potentiella vårdnadshavare om sin plikt att bevara relevant information.</span><span class="sxs-lookup"><span data-stu-id="6cd49-112">To comply with the preservation requirements of an investigation, the organization should immediately inform potential custodians about their duty to preserve relevant information.</span></span>

<span data-ttu-id="6cd49-113">Med Advanced eDiscovery kan juridiska team skapa och anpassa arbetsflödet för aviseringar om juridiskt håll.</span><span class="sxs-lookup"><span data-stu-id="6cd49-113">With Advanced eDiscovery, legal teams can create and customize their legal hold notification workflow.</span></span> <span data-ttu-id="6cd49-114">Det dokumentariska kommunikationsverktygen gör det möjligt för juridiska grupper att konfigurera följande meddelanden och arbetsflöden:</span><span class="sxs-lookup"><span data-stu-id="6cd49-114">The custodian communications tool lets legal teams to configure the following notices and workflows:</span></span>

1. <span data-ttu-id="6cd49-115">**Meddelande om utfärdning:** Ett meddelande om juridiskt betalningsanhåll utfärdas (eller initieras) av en avisering från den juridiska avdelningen till vårdnadshavare som kan ha relevant information om ärendet.</span><span class="sxs-lookup"><span data-stu-id="6cd49-115">**Issuance notice:** A legal hold notice is issued (or initiated) by a notification from the legal department to custodians who may have relevant information about the case matter.</span></span> <span data-ttu-id="6cd49-116">Det här meddelandet instruerar biblioteken att bevara all information som kan behövas för upptäckt.</span><span class="sxs-lookup"><span data-stu-id="6cd49-116">This notice instructs the custodians to preserve any information that may be needed for discovery.</span></span>

2. <span data-ttu-id="6cd49-117">**Meddelande om ny utfärdning:** Under ett ärende kan det hända att biblioteksianer måste bevara ytterligare innehåll (eller mindre innehåll) än tidigare begärt.</span><span class="sxs-lookup"><span data-stu-id="6cd49-117">**Re-Issuance notice:** During a case, custodians may be required to preserve additional content (or less content) than was previously requested.</span></span> <span data-ttu-id="6cd49-118">I det här scenariot kan du uppdatera det befintliga meddelandet om förvaring och utfärda det på ny tid till biblioteksförfattare.</span><span class="sxs-lookup"><span data-stu-id="6cd49-118">For this scenario, you can update the existing hold notice and re-issue it to custodians.</span></span>

3. <span data-ttu-id="6cd49-119">**Meddelande:** När en fråga har lösts och den som har förser den inte längre med bevarandekrav kan den vårdnadshavaren frisläppas från ärendet.</span><span class="sxs-lookup"><span data-stu-id="6cd49-119">**Release notice:** Once a matter is resolved and the custodian is no longer subject to a preservation requirement, the custodian can be released from the case.</span></span> <span data-ttu-id="6cd49-120">Dessutom kan du meddela den som talar om att han eller hon inte längre behöver bevara innehållet, samt ange hur han eller hon ska återuppta den normala arbetsaktiviteten med avseende på data.</span><span class="sxs-lookup"><span data-stu-id="6cd49-120">Additionally, you can notify the custodian that they are no longer required to preserve content, and provide instructions about how to resume their normal work activity with regard to their data.</span></span>

4. <span data-ttu-id="6cd49-121">**Påminnelser och eskalering:** I vissa fall räcker det inte att utfärda ett meddelande för att uppfylla kraven för juridisk upptäckt.</span><span class="sxs-lookup"><span data-stu-id="6cd49-121">**Reminders and escalations:** In some instances, just issuing a notice isn't enough to satisfy legal discovery requirements.</span></span> <span data-ttu-id="6cd49-122">Med varje meddelande kan juridiska grupper schemalägga en uppsättning arbetsflöden för påminnelse och eskalering så att de automatiskt följer upp med o svarare dokumenter.</span><span class="sxs-lookup"><span data-stu-id="6cd49-122">With each notification, legal teams can schedule a set of reminder and escalation workflows to automatically follow up with unresponsive custodians.</span></span>

   - <span data-ttu-id="6cd49-123">**Påminnelser:** När en avisering om juridiskt tillstånd har utfärdats eller om utfärdats till en uppsättning bibliotekare kan en organisation ställa in påminnelser för att varna icke svarare snektiver.</span><span class="sxs-lookup"><span data-stu-id="6cd49-123">**Reminders:** After a legal hold notice has been issued or re-issued to a set of custodians, an organization can set up reminders to alert unresponsive custodians.</span></span>

   - <span data-ttu-id="6cd49-124">**Eskalering:** I vissa fall kan en juridisk grupp konfigurera ett eskaleringsarbetsflöde för att meddela att obehöriga personer och deras chef inte svarar om han eller hon inte svarar.</span><span class="sxs-lookup"><span data-stu-id="6cd49-124">**Escalations:** In some cases, if a custodian remains unresponsive even after a set of reminders over a period of time, the legal team can set up an escalation workflow to notify unresponsive custodians and their manager.</span></span>

<span data-ttu-id="6cd49-125">Mer information om hur du hanterar den efterföljande kommunikationsprocessen finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="6cd49-125">For more information about managing the custodian communication process, see the following:</span></span> 

- [<span data-ttu-id="6cd49-126">Skapa ett meddelande om juridiskt väntande</span><span class="sxs-lookup"><span data-stu-id="6cd49-126">Create a legal hold notice</span></span>](create-hold-notification.md)

- [<span data-ttu-id="6cd49-127">Använda kommunikationsredigeraren</span><span class="sxs-lookup"><span data-stu-id="6cd49-127">Use the communications editor</span></span>](using-communications-editor.md)

- [<span data-ttu-id="6cd49-128">Hantera undantagsaviseringar</span><span class="sxs-lookup"><span data-stu-id="6cd49-128">Manage hold notifications</span></span>](manage-hold-notification.md)

- [<span data-ttu-id="6cd49-129">Bekräfta en undantagsavisering</span><span class="sxs-lookup"><span data-stu-id="6cd49-129">Acknowledge a hold notification</span></span>](acknowledge-hold-notification.md)