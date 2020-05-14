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
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: Lär dig mer om isolerade SharePoint Online-gruppwebbplatser, inklusive användning, krav och funktioner som de kan användas med.
ms.openlocfilehash: 91d8394c40597dfc66c4df39f49223e472e7c663
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209049"
---
# <a name="isolated-sharepoint-online-team-sites"></a><span data-ttu-id="2f97a-103">Isolerade SharePoint Online-gruppwebbplatser</span><span class="sxs-lookup"><span data-stu-id="2f97a-103">Isolated SharePoint Online team sites</span></span>

 <span data-ttu-id="2f97a-104">**Sammanfattning:** Lär dig mer om hur du använder isolerade SharePoint Online-gruppwebbplatser.</span><span class="sxs-lookup"><span data-stu-id="2f97a-104">**Summary:** Learn about the uses for isolated SharePoint Online team sites.</span></span>
  
<span data-ttu-id="2f97a-105">SharePoint Online-gruppwebbplatser är ett enkelt sätt att snabbt skapa ett utrymme för samarbete med anteckningar, dokument, artiklar, kalender och andra resurser i Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="2f97a-105">SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365.</span></span> <span data-ttu-id="2f97a-106">SharePoint Online-gruppwebbplatser baseras på en Microsoft 365-grupp och har en förenklad administrationsmodell som tillåter öppet samarbete med en privat uppsättning gruppmedlemmar eller med hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="2f97a-106">SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization.</span></span> <span data-ttu-id="2f97a-107">Med en standardinställd SharePoint Online-gruppwebbplats kan medlemmar i Microsoft 365-gruppen bjuda in andra användare och styra behörighetsinställningar.</span><span class="sxs-lookup"><span data-stu-id="2f97a-107">A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span></span>
  
<span data-ttu-id="2f97a-108">Men i vissa fall kan du vilja skapa en SharePoint Online-gruppwebbplats för samarbete med strängare kontroll av behörigheterna för den webbplatsen genom gruppmedlemskap och SharePoint Online-behörighetsnivåer, som bara hanteras av SharePoint-administratörer.</span><span class="sxs-lookup"><span data-stu-id="2f97a-108">However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators.</span></span> <span data-ttu-id="2f97a-109">Vi kallar det här för en isolerad webbplats, som isoleras till den uppsättning användare som samarbetar, visar dess innehåll eller administrerar webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2f97a-109">We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site.</span></span> <span data-ttu-id="2f97a-110">Du kan behöva en isolerad webbplats av följande anledningar:</span><span class="sxs-lookup"><span data-stu-id="2f97a-110">You might need an isolated site for the following:</span></span>
  
- <span data-ttu-id="2f97a-111">Ett hemligt projekt i organisationen.</span><span class="sxs-lookup"><span data-stu-id="2f97a-111">A secret project within your organization.</span></span>
    
- <span data-ttu-id="2f97a-112">Placeringen av mycket känslig eller värdefull immateriell egendom för organisationen.</span><span class="sxs-lookup"><span data-stu-id="2f97a-112">The location for highly-sensitive or valuable intellectual property for your organization.</span></span>
    
- <span data-ttu-id="2f97a-113">Resurserna för en rättsåtgärd som vidtas av organisationen eller som den utsätts för.</span><span class="sxs-lookup"><span data-stu-id="2f97a-113">The resources for a legal action taken by your organization or that to which it is being subjected.</span></span>
    
- <span data-ttu-id="2f97a-114">För att dela en Microsoft 365-prenumeration mellan flera organisationer som har en viss överlappning men som till största del fungerar som separata affärsenheter.</span><span class="sxs-lookup"><span data-stu-id="2f97a-114">To share a Microsoft 365 subscription between multiple organizations that have some overlap, but for the most part exist as separate business entities.</span></span>
    
<span data-ttu-id="2f97a-115">Här är kraven för en isolerad webbplats:</span><span class="sxs-lookup"><span data-stu-id="2f97a-115">Here are the requirements of an isolated site:</span></span>
  
- <span data-ttu-id="2f97a-116">Bara SharePoint Online-administratörer kan utföra webbplatsadministration, vilket omfattar gruppmedlemskap för åtkomst till webbplatsen och konfigurering av anpassade behörigheter.</span><span class="sxs-lookup"><span data-stu-id="2f97a-116">Only SharePoint Online administrators can perform site administration, which includes group membership for access to the site and configuring custom permissions.</span></span>
    
- <span data-ttu-id="2f97a-117">Webbplatsens medlemmar kan inte bjuda in andra medlemmar till gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2f97a-117">Members of the site cannot invite other members to the team site.</span></span>
    
- <span data-ttu-id="2f97a-118">Användare som inte är medlem i den isolerade webbplatsen kan inte begära åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2f97a-118">Users who are not members of the isolated site cannot request access to the site.</span></span> <span data-ttu-id="2f97a-119">För dem visas en åtkomst nekas-webbsida när de försöker öppna en webbadress kopplad till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2f97a-119">They will receive an access denied web page when they attempt to access any URL associated with the site.</span></span>
    
<span data-ttu-id="2f97a-120">Kompromissen med att kräva centraliserad åtkomstkontroll och anpassade behörigheter av SharePoint Online-administratören är att webbplatsen förblir isolerad med tiden.</span><span class="sxs-lookup"><span data-stu-id="2f97a-120">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time.</span></span> <span data-ttu-id="2f97a-121">Till exempel kan inte nuvarande medlemmar avsiktligt eller oavsiktligt, bjuda in eller konfigurera anpassade behörigheter för andra användare i Microsoft 365-prenumerationer som inte ska vara medlemmar i webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2f97a-121">For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span></span>
  
<span data-ttu-id="2f97a-122">En isolerad webbplats kan användas med andra funktioner, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2f97a-122">An isolated site can be used with other features, such as:</span></span>
  
- <span data-ttu-id="2f97a-123">IRM (Information Rights Management) för att se till att resurserna på webbplatsen förblir krypterade, även om de laddas ned lokalt och laddas upp på en annan webbplats som tillgänglig för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="2f97a-123">Information Rights Management to ensure that the resources on the site remain encrypted, even if they are downloaded locally and uploaded to another site that is available to the entire organization.</span></span>
    
- <span data-ttu-id="2f97a-124">Skydd mot dataförlust för att förhindra att användare skickar webbplatsens resurser, till exempel filer, i e-post.</span><span class="sxs-lookup"><span data-stu-id="2f97a-124">Data loss prevention to prevent users from sending the resources of the site, such as files, in email.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="2f97a-125">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="2f97a-125">Next steps</span></span>

<span data-ttu-id="2f97a-126">Om du vill prova en isolerad SharePoint Online-gruppwebbplats i en utvärderingsprenumeration läser du de stegvisa anvisningarna i [Miljö för utveckling/testning för isolerad SharePoint Online-gruppwebbplats](isolated-sharepoint-online-team-site-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="2f97a-126">To try out an isolated SharePoint Online team site in a trial subscription, see the step-by-step instructions in [Isolated SharePoint Online team site dev/test environment](isolated-sharepoint-online-team-site-dev-test-environment.md).</span></span>
  
<span data-ttu-id="2f97a-127">När du är redo att distribuera en isolerad SharePoint Online-gruppwebbplats i produktion kan du läsa de steg för steg-informationen om utformning i [Utforma en isolerad SharePoint Online-gruppwebbplats](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="2f97a-127">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2f97a-128">Se även</span><span class="sxs-lookup"><span data-stu-id="2f97a-128">See Also</span></span>

[<span data-ttu-id="2f97a-129">Utforma en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="2f97a-129">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="2f97a-130">Hantera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="2f97a-130">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="2f97a-131">Distribuera en isolerad SharePoint Online-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="2f97a-131">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)


