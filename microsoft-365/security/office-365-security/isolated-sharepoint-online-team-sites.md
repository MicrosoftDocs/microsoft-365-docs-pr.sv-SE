---
title: Isolerade SharePoint Online-gruppwebbplatser
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: Lär dig mer om isolerade SharePoint Online-gruppwebbplatser, inklusive användning, krav och funktioner som de kan användas med.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 056c6f2a463d38dd27b26d484995280dddedf436
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286591"
---
# <a name="isolated-sharepoint-online-team-sites"></a><span data-ttu-id="32323-103">Isolerade SharePoint Online-gruppwebbplatser</span><span class="sxs-lookup"><span data-stu-id="32323-103">Isolated SharePoint Online team sites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="32323-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="32323-104">**Applies to**</span></span>
- [<span data-ttu-id="32323-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="32323-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="32323-106">Microsoft Defender för Office 365 Abonnemang 1</span><span class="sxs-lookup"><span data-stu-id="32323-106">Microsoft Defender for Office 365 plan 1</span></span>](office-365-atp.md)
- <span data-ttu-id="32323-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="32323-107">SharePoint Online</span></span> 

 <span data-ttu-id="32323-108">**Sammanfattning:** Lär dig mer om hur du använder isolerade SharePoint Online-gruppwebbplatser.</span><span class="sxs-lookup"><span data-stu-id="32323-108">**Summary:** Learn about the uses for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="32323-109">SharePoint Online-gruppwebbplatser är ett enkelt sätt att snabbt skapa en plats för samarbete.</span><span class="sxs-lookup"><span data-stu-id="32323-109">SharePoint Online team sites are an easy way to quickly create a space for collaboration.</span></span> <span data-ttu-id="32323-110">Användare kan arbeta tillsammans med anteckningar, dokument, artiklar, en kalender och andra resurser i Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="32323-110">Users can work together on notes, documents, articles, a calendar, and other resources in Microsoft Office 365.</span></span> <span data-ttu-id="32323-111">SharePoint Online-gruppwebbplatser baseras på en Microsoft 365-grupp och har en förenklad administrationsmodell som tillåter öppet samarbete med en privat uppsättning gruppmedlemmar eller med hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="32323-111">SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization.</span></span> <span data-ttu-id="32323-112">Med en standardinställd SharePoint Online-gruppwebbplats kan medlemmar i Microsoft 365-gruppen bjuda in andra användare och styra behörighetsinställningar.</span><span class="sxs-lookup"><span data-stu-id="32323-112">A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span></span>

<span data-ttu-id="32323-113">Ibland måste dock åtkomsten till webbplatser styras av gruppmedlemskap och behörighetsnivåer i SharePoint Online som hanteras av SharePoint-administratörer.</span><span class="sxs-lookup"><span data-stu-id="32323-113">However, you'll sometimes need site access to be controlled by group memberships, and SharePoint Online permission levels managed by SharePoint administrators.</span></span> <span data-ttu-id="32323-114">Vi kallar det här för en isolerad webbplats, som isoleras till den uppsättning användare som samarbetar, visar dess innehåll eller administrerar webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="32323-114">We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site.</span></span> <span data-ttu-id="32323-115">Du kan behöva en isolerad webbplats av följande anledningar:</span><span class="sxs-lookup"><span data-stu-id="32323-115">You might need an isolated site for the following:</span></span>

- <span data-ttu-id="32323-116">Ett hemligt projekt i organisationen.</span><span class="sxs-lookup"><span data-stu-id="32323-116">A secret project within your organization.</span></span>

- <span data-ttu-id="32323-117">Placeringen av mycket känslig eller värdefull immateriell egendom för organisationen.</span><span class="sxs-lookup"><span data-stu-id="32323-117">The location for highly-sensitive or valuable intellectual property for your organization.</span></span>

- <span data-ttu-id="32323-118">Resurserna för en rättsåtgärd som vidtas av organisationen eller som den utsätts för.</span><span class="sxs-lookup"><span data-stu-id="32323-118">The resources for a legal action taken by your organization or that to which it is being subjected.</span></span>

- <span data-ttu-id="32323-119">För att dela en Microsoft 365-prenumeration mellan flera organisationer som har en viss överlappning men som till största del fungerar som separata affärsenheter.</span><span class="sxs-lookup"><span data-stu-id="32323-119">To share a Microsoft 365 subscription between multiple organizations that have some overlap, but for the most part exist as separate business entities.</span></span>

<span data-ttu-id="32323-120">Här är kraven för en isolerad webbplats:</span><span class="sxs-lookup"><span data-stu-id="32323-120">Here are the requirements of an isolated site:</span></span>

- <span data-ttu-id="32323-121">Bara SharePoint Online-administratörer kan utföra webbplatsadministration, vilket omfattar gruppmedlemskap för åtkomst till webbplatsen och konfigurering av anpassade behörigheter.</span><span class="sxs-lookup"><span data-stu-id="32323-121">Only SharePoint Online administrators can perform site administration, which includes group membership for access to the site and configuring custom permissions.</span></span>

- <span data-ttu-id="32323-122">Webbplatsens medlemmar kan inte bjuda in andra medlemmar till gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="32323-122">Members of the site cannot invite other members to the team site.</span></span>

- <span data-ttu-id="32323-123">Användare som inte är medlem i den isolerade webbplatsen kan inte begära åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="32323-123">Users who are not members of the isolated site cannot request access to the site.</span></span> <span data-ttu-id="32323-124">För dem visas en åtkomst nekas-webbsida när de försöker öppna en webbadress kopplad till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="32323-124">They will receive an access denied web page when they attempt to access any URL associated with the site.</span></span>

<span data-ttu-id="32323-125">Kompromissen med att kräva centraliserad åtkomstkontroll och anpassade behörigheter av SharePoint Online-administratören är att webbplatsen förblir isolerad med tiden.</span><span class="sxs-lookup"><span data-stu-id="32323-125">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time.</span></span> <span data-ttu-id="32323-126">Till exempel kan inte nuvarande medlemmar avsiktligt eller oavsiktligt, bjuda in eller konfigurera anpassade behörigheter för andra användare i Microsoft 365-prenumerationer som inte ska vara medlemmar i webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="32323-126">For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span></span>

<span data-ttu-id="32323-127">En isolerad webbplats kan användas med andra funktioner, till exempel:</span><span class="sxs-lookup"><span data-stu-id="32323-127">An isolated site can be used with other features, such as:</span></span>

- <span data-ttu-id="32323-128">IRM (Information Rights Management) för att se till att resurserna på webbplatsen förblir krypterade, även om de laddas ned lokalt och laddas upp på en annan webbplats som tillgänglig för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="32323-128">Information Rights Management to ensure that the resources on the site remain encrypted, even if they are downloaded locally and uploaded to another site that is available to the entire organization.</span></span>

- <span data-ttu-id="32323-129">Skydd mot dataförlust för att förhindra att användare skickar webbplatsens resurser, till exempel filer, i e-post.</span><span class="sxs-lookup"><span data-stu-id="32323-129">Data loss prevention to prevent users from sending the resources of the site, such as files, in email.</span></span>

## <a name="next-steps"></a><span data-ttu-id="32323-130">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="32323-130">Next steps</span></span>

<span data-ttu-id="32323-131">Om du vill prova en isolerad SharePoint Online-gruppwebbplats i en utvärderingsprenumeration läser du de stegvisa anvisningarna i [Miljö för utveckling/testning för isolerad SharePoint Online-gruppwebbplats](isolated-sharepoint-online-team-site-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="32323-131">To try out an isolated SharePoint Online team site in a trial subscription, see the step-by-step instructions in [Isolated SharePoint Online team site dev/test environment](isolated-sharepoint-online-team-site-dev-test-environment.md).</span></span>

<span data-ttu-id="32323-132">När du är redo att distribuera en isolerad SharePoint Online-gruppwebbplats i produktion kan du läsa de steg för steg-informationen om utformning i [Utforma en isolerad SharePoint Online-gruppwebbplats](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="32323-132">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="32323-133">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="32323-133">Related topics</span></span>

[<span data-ttu-id="32323-134">Utforma en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="32323-134">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="32323-135">Hantera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="32323-135">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="32323-136">Distribuera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="32323-136">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
