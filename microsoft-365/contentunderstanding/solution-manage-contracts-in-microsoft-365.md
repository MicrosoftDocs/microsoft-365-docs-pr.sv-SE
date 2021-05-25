---
title: Hantera kontrakt med en Microsoft 365 lösning
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
ms.collection: m365solution-managecontracts
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Lär dig hur du hanterar kontrakt med en Microsoft 365 lösning av SharePoint Syntex, SharePoint listor, Microsoft Teams och Power Automate.
ms.openlocfilehash: 219ab13eb5787bef566ede0c5dc856da29d96837
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651290"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a><span data-ttu-id="dd152-103">Hantera kontrakt med en Microsoft 365 lösning</span><span class="sxs-lookup"><span data-stu-id="dd152-103">Manage contracts using a Microsoft 365 solution</span></span>

<span data-ttu-id="dd152-104">I den här artikeln beskrivs hur du skapar en kontraktshanteringslösning för organisationen med hjälp SharePoint Syntex och komponenter i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd152-104">This article describes how to create a contracts management solution for your organization by using SharePoint Syntex and components of Microsoft 365.</span></span> <span data-ttu-id="dd152-105">Det ger dig ett ramverk som hjälper dig att planera och skapa en lösning som passar dina unika affärsbehov.</span><span class="sxs-lookup"><span data-stu-id="dd152-105">It provides you with a framework to help you plan and create a solution that fits your unique business needs.</span></span> <span data-ttu-id="dd152-106">Även om den här lösningen inte passar dina affärsbehov som helhet kan delar av den användas i din planering för att skapa en anpassad lösning för kontraktshantering.</span><span class="sxs-lookup"><span data-stu-id="dd152-106">Even if this solution doesn't suit your business needs as a whole, parts of it can be adopted in your planning to create a custom contract management solution.</span></span>

<span data-ttu-id="dd152-107">*Det här innehållet innehåller dokument Microsoft 365 en lösning som utvecklats av Thomas ThomasBach med Teamet modern arbetslösningsstrategi på Microsoft.*</span><span class="sxs-lookup"><span data-stu-id="dd152-107">*This content set documents a Microsoft 365 solution developed by Thomas Molbach with the Modern Work Solution Strategy Team at Microsoft.*</span></span>

## <a name="identify-the-business-problem"></a><span data-ttu-id="dd152-108">Identifiera affärsproblemet</span><span class="sxs-lookup"><span data-stu-id="dd152-108">Identify the business problem</span></span>

<span data-ttu-id="dd152-109">Det första steget när du planerar ditt kontraktshanteringssystem är att förstå problemet du försöker lösa.</span><span class="sxs-lookup"><span data-stu-id="dd152-109">The first step in planning your contract management system is to understand the problem you're trying to solve.</span></span> <span data-ttu-id="dd152-110">För den här lösningen måste fyra viktiga problem åtgärdas:</span><span class="sxs-lookup"><span data-stu-id="dd152-110">For this solution, four key issues need to be addressed:</span></span>

- <span data-ttu-id="dd152-111">**Identifiera kontrakt**.</span><span class="sxs-lookup"><span data-stu-id="dd152-111">**Identify contracts**.</span></span> <span data-ttu-id="dd152-112">Din organisation arbetar med många dokument, till exempel fakturor, kontrakt, arbetsutdrag och så vidare.</span><span class="sxs-lookup"><span data-stu-id="dd152-112">Your organization works with many documents, such as invoices, contracts, statements of work, and so on.</span></span>  <span data-ttu-id="dd152-113">Vissa är digitala tillgångar som skickas via e-post och vissa är papperstillgångar som skickas via traditionell e-post.</span><span class="sxs-lookup"><span data-stu-id="dd152-113">Some are digital assets sent through email, and some are paper assets sent through traditional mail.</span></span> <span data-ttu-id="dd152-114">Du behöver ett sätt att identifiera alla kundkontrakt i alla andra dokument och sedan klassificera dem som sådana.</span><span class="sxs-lookup"><span data-stu-id="dd152-114">You need a way to identify all customer contracts from all other documents, and then classifying them as such.</span></span>

- <span data-ttu-id="dd152-115">**Spåra historik för kontraktsgodkännanden**.</span><span class="sxs-lookup"><span data-stu-id="dd152-115">**Track the history of contract approvals**.</span></span> <span data-ttu-id="dd152-116">Din organisation behöver ett tillförlitligt sätt att ta reda på om kontrakt har godkänts eller avvisats och om betalningen har bearbetats.</span><span class="sxs-lookup"><span data-stu-id="dd152-116">Your organization needs a reliable way to find whether contracts have been either approved or rejected, and whether payment has been processed.</span></span> 

- <span data-ttu-id="dd152-117">**Webbplats för hantering av godkännanden av avtal.**</span><span class="sxs-lookup"><span data-stu-id="dd152-117">**Site to manage contract approvals**.</span></span> <span data-ttu-id="dd152-118">Din organisation måste skapa en webbplats för samarbete där alla nödvändiga intressenter enkelt kan granska kontrakt.</span><span class="sxs-lookup"><span data-stu-id="dd152-118">Your organization needs to set up a collaborative site in which all required stakeholders can easily review contracts.</span></span> <span data-ttu-id="dd152-119">Intressenter bör vid behov kunna granska hela avtalet, men det är mest viktigt att se flera nyckelfält från varje kontrakt (till exempel kundnamn, inköpsordernummer och total kostnad).</span><span class="sxs-lookup"><span data-stu-id="dd152-119">Stakeholders should be able to review the whole contract if needed, but mostly care about seeing several key fields from each contract (for example, customer name, PO number, and total cost).</span></span> <span data-ttu-id="dd152-120">Intressenterna bör enkelt kunna godkänna eller avvisa inkommande kontrakt.</span><span class="sxs-lookup"><span data-stu-id="dd152-120">Stakeholders should be able to easily approve or reject incoming contracts.</span></span>

- <span data-ttu-id="dd152-121">**Route reviewed contracts**.</span><span class="sxs-lookup"><span data-stu-id="dd152-121">**Route reviewed contracts**.</span></span> <span data-ttu-id="dd152-122">Godkända och avvisade kontrakt måste dirigeras genom ett visst arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="dd152-122">Approved and rejected contracts need to be routed through a specific workflow.</span></span> <span data-ttu-id="dd152-123">Godkända kontrakt måste dirigeras till en tredjepartsansökan för betalningsbearbetning.</span><span class="sxs-lookup"><span data-stu-id="dd152-123">Approved contracts need to be routed to a third-party application for payment processing.</span></span> <span data-ttu-id="dd152-124">Avvisade kontrakt måste dirigeras för ytterligare granskning.</span><span class="sxs-lookup"><span data-stu-id="dd152-124">Rejected contracts need to be routed for additional review.</span></span>

## <a name="overview-of-the-solution"></a><span data-ttu-id="dd152-125">Översikt över lösningen</span><span class="sxs-lookup"><span data-stu-id="dd152-125">Overview of the solution</span></span>

  ![Översikt över lösningen med hjälp SharePoint Syntex, SharePoint, Teams och Power Automate.](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

<span data-ttu-id="dd152-127">Den här lösningen för kontraktshantering innehåller fyra komponenter Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="dd152-127">This contract management solution guidance includes four components of Microsoft 365:</span></span>

- <span data-ttu-id="dd152-128">**Microsoft SharePoint Syntex**: Skapa modeller för att identifiera och klassificera kontraktsfilerna och extrahera lämplig data från dem.</span><span class="sxs-lookup"><span data-stu-id="dd152-128">**Microsoft SharePoint Syntex**: Create models to identify and classify your contract files and then extract the appropriate data from them.</span></span>

- <span data-ttu-id="dd152-129">**Microsoft SharePoint listor:** Använd den formatering som är tillgänglig i moderna SharePoint för att presentera kontrakt i ett företagsvänligt format.</span><span class="sxs-lookup"><span data-stu-id="dd152-129">**Microsoft SharePoint lists**: Use the formatting available in modern SharePoint lists to present contracts in a business-friendly format.</span></span>

- <span data-ttu-id="dd152-130">**Microsoft Teams:** Använd funktionerna i en Teams kanal och tillhörande flikar så att dina intressenter kan granska och hantera kontrakt.</span><span class="sxs-lookup"><span data-stu-id="dd152-130">**Microsoft Teams**: Use the functionality of a Teams channel and associated tabs to allow your stakeholders to review and manage contracts.</span></span>

- <span data-ttu-id="dd152-131">**Power Automate:** Använd flöden för att styra kontrakt genom godkännandeprocessen och sedan till ett tredjepartsprogram för betalning.</span><span class="sxs-lookup"><span data-stu-id="dd152-131">**Power Automate**: Use flows to guide contracts through the approval process, and then to a third-party application for payment.</span></span>

### <a name="how-it-all-works"></a><span data-ttu-id="dd152-132">Så här fungerar allt</span><span class="sxs-lookup"><span data-stu-id="dd152-132">How it all works</span></span>

  ![Diagram över lösningen som visar arbetsflödet för att ladda upp dokument, extrahera data, meddela intressenter och godkänna eller avvisa avtalet.](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. <span data-ttu-id="dd152-134">Dokument laddas upp till ett SharePoint ett dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="dd152-134">Documents are uploaded to a SharePoint document library.</span></span> <span data-ttu-id="dd152-135">En SharePoint med en förstå-modell för Syntex-dokument har använts i dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="dd152-135">A SharePoint Syntex document understanding model has been applied to the document library.</span></span> <span data-ttu-id="dd152-136">Varje fil kontrolleras för att se om någon matchar en typ av innehåll av typen "kontrakt" som filen letar efter.</span><span class="sxs-lookup"><span data-stu-id="dd152-136">It checks each file to see if any match a "contract" content type it's trained to look for.</span></span> <span data-ttu-id="dd152-137">Om en matchning hittas klassificeras filen som ett "kontrakt" och innehållstypen för dokumentet uppdateras.</span><span class="sxs-lookup"><span data-stu-id="dd152-137">If it finds a match, it classifies the file as a "contract" and updates the content type for the document.</span></span>

2. <span data-ttu-id="dd152-138">Modellen hämtar även specifika data från varje kontraktsfil som intressenter är intresserade av, till exempel *klient,* leverantörer och *avgiftsbelopp.*</span><span class="sxs-lookup"><span data-stu-id="dd152-138">The model also pulls out specific data from each contract file that stakeholders are interested in seeing, such as the *Client*, *Contractor*, and *Fee amount*.</span></span>

    <span data-ttu-id="dd152-139">Följande sida är ett exempel på ett kontrakt som modellen har utbildning för att identifiera.</span><span class="sxs-lookup"><span data-stu-id="dd152-139">The following page is an example of a contract that the model is trained to identify.</span></span>

      ![Exempel på ett kontrakt.](../media/content-understanding/contract.png)

3. <span data-ttu-id="dd152-141">I Microsoft Teams är alla intressenter medlemmar i en säker Teams kanal där alla kontrakt i dokumentbiblioteket visas för godkännande eller avvisning.</span><span class="sxs-lookup"><span data-stu-id="dd152-141">In Microsoft Teams, all stakeholders are members of a secure Teams channel in which all contracts in the document library are visible for approval or rejection.</span></span> <span data-ttu-id="dd152-142">Med hjälp Teams funktioner meddelas alla intressenter när nya kontrakt behöver granskas.</span><span class="sxs-lookup"><span data-stu-id="dd152-142">By using Teams functionality, all stakeholders are notified when new contracts need to be reviewed.</span></span>
 
4. <span data-ttu-id="dd152-143">Med hjälp Power Automate flyttas kontrakt genom godkännandeprocessen i Teams kanalen.</span><span class="sxs-lookup"><span data-stu-id="dd152-143">By using Power Automate, contracts are moved through the approval process in the Teams channel.</span></span> <span data-ttu-id="dd152-144">När en medlem godkänner ett avtal ändras kontraktsstatusen för att godkännas, alla medlemmar meddelas via ett Teams-inlägg och ett radobjekt skapas för att visa att avtalet är klart för utbetalning.</span><span class="sxs-lookup"><span data-stu-id="dd152-144">When a member approves a contract, the contract status is changed to approve, all members are notified through a Teams post, and a line item is created to show that the contract is ready for payout.</span></span> <span data-ttu-id="dd152-145">Den här processen kan utökas till att skriva direkt till en betalningsansökan från tredje part.</span><span class="sxs-lookup"><span data-stu-id="dd152-145">This process can be extended to write directly to a third-party financial application for payment.</span></span>

5.  <span data-ttu-id="dd152-146">När en medlem avvisar ett kontrakt ändras statusen till avvisad och alla medlemmar meddelas via ett Teams inlägg.</span><span class="sxs-lookup"><span data-stu-id="dd152-146">When a member rejects a contract, the status is changed to rejected, and all members are notified through a Teams post.</span></span>

6. <span data-ttu-id="dd152-147">Resultatet av den här lösningen är en automatiserad affärsprocess för din organisation.</span><span class="sxs-lookup"><span data-stu-id="dd152-147">The end result of this solution is an automated business process for your organization.</span></span> <span data-ttu-id="dd152-148">Anställda kan enkelt använda den anpassade panelvyn i Teams initiera och övervaka arbetsflödet för godkännande av dina dokument.</span><span class="sxs-lookup"><span data-stu-id="dd152-148">Employees can easily use the custom tile view in Teams to initiate and monitor the approval workflow of your documents.</span></span> 

     ![Fliken Kontrakt.](../media/content-understanding/tile-view.png)

## <a name="create-the-solution"></a><span data-ttu-id="dd152-150">Skapa lösningen</span><span class="sxs-lookup"><span data-stu-id="dd152-150">Create the solution</span></span>

<span data-ttu-id="dd152-151">I nästa avsnitt får du detaljerad information om hur du konfigurerar din lösning för kontraktshantering.</span><span class="sxs-lookup"><span data-stu-id="dd152-151">The next sections will go into detail about how to configure your contracts management solution.</span></span> <span data-ttu-id="dd152-152">Den är uppdelad i tre steg:</span><span class="sxs-lookup"><span data-stu-id="dd152-152">It's divided into three steps:</span></span>

- [<span data-ttu-id="dd152-153">Steg 1. Använda SharePoint Syntex för att identifiera kontraktsfiler och extrahera data</span><span class="sxs-lookup"><span data-stu-id="dd152-153">Step 1. Use SharePoint Syntex to identify contract files and extract data</span></span>](solution-manage-contracts-step1.md)
- [<span data-ttu-id="dd152-154">Steg 2. Använd Microsoft Teams för att skapa din kanal för kontraktshantering</span><span class="sxs-lookup"><span data-stu-id="dd152-154">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)
- [<span data-ttu-id="dd152-155">Steg 3. Använd Power Automate för att skapa ett flöde för att bearbeta dina kontrakt</span><span class="sxs-lookup"><span data-stu-id="dd152-155">Step 3. Use Power Automate to create your flow to process your contracts</span></span>](solution-manage-contracts-step3.md)
