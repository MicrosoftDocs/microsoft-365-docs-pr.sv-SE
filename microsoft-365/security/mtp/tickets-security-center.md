---
title: Skapa och spåra ServiceNow-biljetter i Microsoft 365-säkerhetscentret
description: Lär dig hur du skapar och spårar biljetter i ServiceNow från Microsoft 365-säkerhetscenter.
keywords: säkerhet, Microsoft 365, M365, säker poäng, säkerhetscenter, ServiceNow, biljetter, uppgifter
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
ms.openlocfilehash: 48512cf2fff802509ebaa14ca69d3ca02908902e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45087939"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a><span data-ttu-id="ade09-104">Skapa och spåra ServiceNow-biljetter i Microsoft 365-säkerhetscentret</span><span class="sxs-lookup"><span data-stu-id="ade09-104">Create and track ServiceNow tickets in the Microsoft 365 security center</span></span>

<span data-ttu-id="ade09-105">[Microsoft 365-säkerhetscentret](overview-security-center.md) har förbättrats med möjligheten att skapa och spåra biljetter i ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="ade09-105">The [Microsoft 365 security center](overview-security-center.md) has been enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> [<span data-ttu-id="ade09-106">Läs mer om ServiceNow</span><span class="sxs-lookup"><span data-stu-id="ade09-106">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="ade09-107">I säkerhetscentret kan säkerhetsadministratörer skicka en förbättringsåtgärd för [Microsoft Secure Score](microsoft-secure-score.md) direkt till ServiceNow och skapa en biljett.</span><span class="sxs-lookup"><span data-stu-id="ade09-107">In the security center, security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="ade09-108">Både incidenthantering och ändringshanteringsbiljetter kan skapas.</span><span class="sxs-lookup"><span data-stu-id="ade09-108">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="ade09-109">De kan sedan spåras på säkerhetscentrets startsida och ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="ade09-109">They can then be tracked in the security center home page, and ServiceNow.</span></span>

- [<span data-ttu-id="ade09-110">**Läs mer om förutsättningar, datautbyte och felsökning**</span><span class="sxs-lookup"><span data-stu-id="ade09-110">**Learn about prerequisites, data exchange, and troubleshooting**</span></span>](tickets.md)
- <span data-ttu-id="ade09-111">**Hantera ServiceNow-biljetter i efterlevnadscentret** (kommer snart)</span><span class="sxs-lookup"><span data-stu-id="ade09-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="ade09-112">Ansluta Microsoft 365-säkerhetscenter till ServiceNow</span><span class="sxs-lookup"><span data-stu-id="ade09-112">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="ade09-113">Gå till startsidan för Microsoft 365-säkerhetscentret för att se ServiceNow-anslutningskortet.</span><span class="sxs-lookup"><span data-stu-id="ade09-113">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![Använder du ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="ade09-115">Välj "Anslut till ServiceNow" för att gå till servicenow-inställningssidan.</span><span class="sxs-lookup"><span data-stu-id="ade09-115">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="ade09-116">Följ instruktionerna för att auktorisera Microsoft 365 Connector-appen.</span><span class="sxs-lookup"><span data-stu-id="ade09-116">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="ade09-117">Innan du godkänner anslutningen mellan Microsoft 365 security center och ServiceNow ska du se till att du använder den användarinloggning och lösenord för integrering som du skapade i installationsstegen.</span><span class="sxs-lookup"><span data-stu-id="ade09-117">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="ade09-118">Använd inte dina personliga inloggningsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="ade09-118">Do not use your personal credentials.</span></span>

<span data-ttu-id="ade09-119">När du har följt anvisningarna och auktoriserat anslutningen kan du visa anslutningsstatusen på både microsoft 365-säkerhetscentrets anslutningssida och i ServiceNow Microsoft 365 Ticketing Connector App-upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="ade09-119">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="ade09-120">Nu är du redo att börja skapa uppgifter!</span><span class="sxs-lookup"><span data-stu-id="ade09-120">Now you are all set to start creating tasks!</span></span>

### <a name="troubleshooting"></a><span data-ttu-id="ade09-121">Felsökning</span><span class="sxs-lookup"><span data-stu-id="ade09-121">Troubleshooting</span></span>

<span data-ttu-id="ade09-122">Lär dig vanliga fel som kan uppstå i anslutningsprocessen och hur du kan minska dem i [felsökningsavsnittet](tickets.md#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="ade09-122">Learn common errors you may encounter in the connection process, and how to mitigate them, in the [troubleshooting section](tickets.md#troubleshooting).</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="ade09-123">Skapa en uppgift och dela den till ServiceNow</span><span class="sxs-lookup"><span data-stu-id="ade09-123">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="ade09-124">När integreringen har konfigurerats skapar du ServiceNow-uppgifter baserat på specifika microsoft secure score-förbättringsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="ade09-124">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="ade09-125">Gå till alla förbättringsåtgärder i Secure Score i Microsoft 365 security center-portalen och välj ikonen "dela".</span><span class="sxs-lookup"><span data-stu-id="ade09-125">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the "share" icon.</span></span> <span data-ttu-id="ade09-126">Ett av listrutan är ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="ade09-126">One of the dropdown options is ServiceNow.</span></span>

![ServiceNow-delning i Secure Score](../../media/servicenow-share.png)

<span data-ttu-id="ade09-128">En aktivitet genereras där du kan ange prioritet och redigera namn, beskrivning eller förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="ade09-128">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="ade09-129">När alla obligatoriska fält har fyllts i skickar du uppgiften till ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="ade09-129">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="ade09-130">Uppgiften visas i ServiceNow som en microsoft 365-begäran om säkerhet och konfigurationsändring.</span><span class="sxs-lookup"><span data-stu-id="ade09-130">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="ade09-131">Spåra biljetter</span><span class="sxs-lookup"><span data-stu-id="ade09-131">Track tickets</span></span>

<span data-ttu-id="ade09-132">När ServiceNow-biljetter för ändringshantering och incidenthantering har skapats visas de på kort på startsidan för Microsoft 365-säkerhetscentret.</span><span class="sxs-lookup"><span data-stu-id="ade09-132">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="ade09-133">Från dessa kort kan du skapa en biljett, visa alla biljetter eller hantera ServiceNow-konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="ade09-133">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow ändringshanteringsbiljetter](../../media/change-management-375.png)  ![ServiceNow incidenthanteringsbiljetter](../../media/incident-management-375.png)

<span data-ttu-id="ade09-136">Om du vill återupprätta eller hantera din ServiceNow-integrering i Microsoft 365-säkerhetscentret väljer du **Hantera ServiceNow-konfiguration** på något av korten.</span><span class="sxs-lookup"><span data-stu-id="ade09-136">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="ade09-137">Därifrån tar du bort den aktuella ServiceNow-anslutningen och anpassar biljetttillståndsnamn.</span><span class="sxs-lookup"><span data-stu-id="ade09-137">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="ade09-138">Med ServiceNow-biljetter synliga i Microsoft 365-säkerhetscentret bor dina uppgifter på en plats där de kan spåras och hanteras tillsammans med dina andra säkerhetsinstrumentpanelobjekt.</span><span class="sxs-lookup"><span data-stu-id="ade09-138">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="resources"></a><span data-ttu-id="ade09-139">Resurser</span><span class="sxs-lookup"><span data-stu-id="ade09-139">Resources</span></span>

- [<span data-ttu-id="ade09-140">Läs mer om förutsättningar, datautbyte och felsökning</span><span class="sxs-lookup"><span data-stu-id="ade09-140">Learn about prerequisites, data exchange, and troubleshooting</span></span>](tickets.md)
- [<span data-ttu-id="ade09-141">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="ade09-141">Microsoft Secure Score</span></span>](microsoft-secure-score.md)