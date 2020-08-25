---
title: Skapa och spåra ServiceNow biljetter i säkerhets Center för Microsoft 365
description: Lär dig hur du skapar och spårar biljetter i ServiceNow från Microsoft 365 Security Center.
keywords: säkerhet, Microsoft 365, M365, säker poäng, säkerhets Center, ServiceNow, biljetter, uppgifter
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: bd5bf8533d38337c063acdf0dda073e4961e416a
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867251"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a><span data-ttu-id="c3168-104">Skapa och spåra ServiceNow biljetter i säkerhets Center för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c3168-104">Create and track ServiceNow tickets in the Microsoft 365 security center</span></span>

<span data-ttu-id="c3168-105">[Säkerhets Center för Microsoft 365](overview-security-center.md) har förbättrats med möjligheten att skapa och spåra biljetter i ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="c3168-105">The [Microsoft 365 security center](overview-security-center.md) has been enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> [<span data-ttu-id="c3168-106">Lär dig mer om ServiceNow</span><span class="sxs-lookup"><span data-stu-id="c3168-106">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="c3168-107">I säkerhets Center kan säkerhets administratörer skicka en åtgärd för [säker Poäng](microsoft-secure-score.md) förbättring direkt till ServiceNow och skapa en biljett.</span><span class="sxs-lookup"><span data-stu-id="c3168-107">In the security center, security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="c3168-108">Både hantering av problem och hantering av ändringar kan skapas.</span><span class="sxs-lookup"><span data-stu-id="c3168-108">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="c3168-109">Spåra biljetter i säkerhets centrets start sida och ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="c3168-109">Track tickets in the security center home page and ServiceNow.</span></span>

- [<span data-ttu-id="c3168-110">**Läs mer om förutsättningar, data utbyte och fel sökning**</span><span class="sxs-lookup"><span data-stu-id="c3168-110">**Learn about prerequisites, data exchange, and troubleshooting**</span></span>](tickets.md)
- <span data-ttu-id="c3168-111">**Hantera ServiceNow biljetter i överensstämmelse Center** (kommer snart)</span><span class="sxs-lookup"><span data-stu-id="c3168-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="c3168-112">Ansluta Microsoft 365 säkerhets Center till ServiceNow</span><span class="sxs-lookup"><span data-stu-id="c3168-112">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="c3168-113">Gå till start sidan för Microsoft 365 säkerhets Center för att se ServiceNow-anslutnings kortet.</span><span class="sxs-lookup"><span data-stu-id="c3168-113">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![Använder du ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="c3168-115">Välj "Anslut till ServiceNow" för att gå till sidan för inställning av ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="c3168-115">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="c3168-116">Följ instruktionerna för att auktorisera Microsoft 365 Connector-appen.</span><span class="sxs-lookup"><span data-stu-id="c3168-116">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="c3168-117">Innan du godkänner anslutningen mellan Microsoft 365 säkerhets Center och ServiceNow bör du kontrol lera att du använder den inloggning och det lösen ord som du skapade i installations stegen.</span><span class="sxs-lookup"><span data-stu-id="c3168-117">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="c3168-118">Använd inte dina personliga autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="c3168-118">Do not use your personal credentials.</span></span>

<span data-ttu-id="c3168-119">När du har följt anvisningarna och godkänt anslutningen kan du Visa anslutnings statusen på sidan för Microsoft 365 Security Centre-anslutningen och i ServiceNow Microsoft 365 Ticking Connector.</span><span class="sxs-lookup"><span data-stu-id="c3168-119">After you've followed the directions and authorized the connection, view the connection status in the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="c3168-120">Nu är du redo att börja skapa aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="c3168-120">Now you're all set to start creating tasks!</span></span>

### <a name="troubleshooting"></a><span data-ttu-id="c3168-121">Felsökning</span><span class="sxs-lookup"><span data-stu-id="c3168-121">Troubleshooting</span></span>

<span data-ttu-id="c3168-122">Lär dig mer om vanliga fel som kan komma att visas i anslutnings processen och hur du minskar dem i [avsnittet fel sökning](tickets.md#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="c3168-122">Learn common errors you may come across in the connection process, and how to mitigate them, in the [troubleshooting section](tickets.md#troubleshooting).</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="c3168-123">Skapa en uppgift och dela den med ServiceNow</span><span class="sxs-lookup"><span data-stu-id="c3168-123">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="c3168-124">När integrationen är aktive rad kan du skapa ServiceNow uppgifter baserat på specifika åtgärder för [säker Poäng](microsoft-secure-score.md) förbättring.</span><span class="sxs-lookup"><span data-stu-id="c3168-124">Once the integration is set up, create ServiceNow tasks based on specific [Microsoft Secure Score](microsoft-secure-score.md) improvement actions.</span></span> <span data-ttu-id="c3168-125">Gå till alla åtgärder för säker Poäng förbättring i säkerhets Center för Microsoft 365 och välj **dela**.</span><span class="sxs-lookup"><span data-stu-id="c3168-125">Go to any Secure Score improvement action in the Microsoft 365 security center, and select **Share**.</span></span> <span data-ttu-id="c3168-126">Ett av de nedrullningsbara alternativen är ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="c3168-126">One of the dropdown options is ServiceNow.</span></span>

<span data-ttu-id="c3168-127">En aktivitet skapas där du kan ange prioritet och redigera namn, beskrivning eller förfallo datum.</span><span class="sxs-lookup"><span data-stu-id="c3168-127">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="c3168-128">När alla obligatoriska fält är ifyllda skickar du uppgiften till ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="c3168-128">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="c3168-129">Aktiviteten visas i ServiceNow som en begäran om ändring av en Microsoft 365-säkerhet och-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="c3168-129">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="c3168-130">Spåra biljetter</span><span class="sxs-lookup"><span data-stu-id="c3168-130">Track tickets</span></span>

<span data-ttu-id="c3168-131">När ServiceNow för hantering av ändringar har skapats visas de på kort på Start sidan för Microsoft 365 säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="c3168-131">Once ServiceNow change management and incident management tickets have been created, they're displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="c3168-132">Från dessa kort kan du skapa en biljett, Visa alla biljetter eller hantera ServiceNow-konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="c3168-132">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow för ändrings hantering](../../media/change-management-375.png)  ![ServiceNow ärende hantering biljetter](../../media/incident-management-375.png)

<span data-ttu-id="c3168-135">Om du vill etablera eller hantera din ServiceNow-integrering i säkerhets Center för Microsoft 365 väljer du **Hantera ServiceNow-konfiguration** på något av korten.</span><span class="sxs-lookup"><span data-stu-id="c3168-135">To reprovision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="c3168-136">Därifrån kan du ta bort den aktuella ServiceNow-anslutningen och anpassa namn på biljett status.</span><span class="sxs-lookup"><span data-stu-id="c3168-136">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="c3168-137">Med ServiceNow biljetter som visas i Microsoft 365 Security Center är dina uppgifter aktiva på en plats där de kan spåras och behandlas på andra säkerhets instrument paneler.</span><span class="sxs-lookup"><span data-stu-id="c3168-137">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="resources"></a><span data-ttu-id="c3168-138">Resurser</span><span class="sxs-lookup"><span data-stu-id="c3168-138">Resources</span></span>

- [<span data-ttu-id="c3168-139">Läs mer om förutsättningar, data utbyte och fel sökning</span><span class="sxs-lookup"><span data-stu-id="c3168-139">Learn about prerequisites, data exchange, and troubleshooting</span></span>](tickets.md)
- [<span data-ttu-id="c3168-140">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="c3168-140">Microsoft Secure Score</span></span>](microsoft-secure-score.md)