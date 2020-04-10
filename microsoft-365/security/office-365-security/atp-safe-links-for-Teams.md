---
title: Office 365 ATP Safe Links for Teams, safelinks, safe links, block malicious links, office 365 atp, Teams safe links, stop users from clicking bad links, malicious links, malicious links, office 365 atp, Teams safe links, stop users from clicking bad links, malicious links,
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Team kommer nu att ha tillgång till säkra länkar vid tidpunkten för ditt klick. Oavsett om du använder chattar 1-mot-1-chattar, mellan grupper eller i kanaler och flikar, om du har en prenumeration på Office 365 ATP, har du möjlighet att aktivera och använda den här säkerhetsfunktionen.
ms.openlocfilehash: 49a49bd41e71daf0afc9e7a24e79898ff98ad798
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212551"
---
<!--06/21/2019-->

# <a name="office-365-safe-links-in-teams"></a><span data-ttu-id="4f47d-104">Säkra office 365-länkar i team</span><span class="sxs-lookup"><span data-stu-id="4f47d-104">Office 365 Safe Links in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f47d-105">Den här funktionen finns i **Offentlig förhandsversion** för kunder i MICROSOFT Teams Technology Adoption Program (TAP) från och med den 28 februari 2020.</span><span class="sxs-lookup"><span data-stu-id="4f47d-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="4f47d-106">Den här anteckningen tas bort från artikeln när säkra länkar för teams är mer allmänt tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="4f47d-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="4f47d-107">Microsoft Teams, ett Molnbaserat Office 365-program för att hantera ditt arbete, använder redan säkra bilagor (för Office 365), men det har nu tillgång till säkra länkar när du klickar.</span><span class="sxs-lookup"><span data-stu-id="4f47d-107">Microsoft Teams, an Office 365 Cloud-based application for managing your work, already uses safe attachments (for Office 365), but it will now have access to safe links at the time of your click.</span></span> <span data-ttu-id="4f47d-108">Oavsett om du använder chattar 1-mot-1-chattar, mellan grupper eller i kanaler och flikar, om du har en prenumeration på Office 365 ATP, har du möjlighet att aktivera och använda den här säkerhetsåtgärden.</span><span class="sxs-lookup"><span data-stu-id="4f47d-108">Whether you're using chats 1-on-1 Chats, between Groups, or in Channels, and Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span>

<span data-ttu-id="4f47d-109">Så här fungerar det:</span><span class="sxs-lookup"><span data-stu-id="4f47d-109">Here's how it works:</span></span> 

1. <span data-ttu-id="4f47d-110">När du startar Teams-programmet kontrollerar Office 365 att användaren tillhör en organisation som har Office 365 ATP och att användaren ingår i en aktiv princip för säkra länkar med dess skydd aktiverat för Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4f47d-110">When you start the Teams application, Office 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="4f47d-111">Om ovanstående är sant valideras webbadresser vid klicktillfället i Chattar, Gruppchattar, Kanaler och i flikar för den användaren.</span><span class="sxs-lookup"><span data-stu-id="4f47d-111">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>

> [!NOTE]
> <span data-ttu-id="4f47d-112">Säkra länkar skyddar användare från länkar som skickas av gästanvändare, Federerade användare, klientanvändare.</span><span class="sxs-lookup"><span data-stu-id="4f47d-112">Safe links safeguards users from links sent by Guest users, Federated users, tenant users.</span></span> <span data-ttu-id="4f47d-113">Om användaren som är inloggad har säkra länkar för Teams aktiverade gäller skydd för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="4f47d-113">If the user logged in has safe links for Teams enabled, then safe links protections will apply.</span></span>
 
## <a name="what-will-users-experience"></a><span data-ttu-id="4f47d-114">Vad kommer användarna att uppleva?</span><span class="sxs-lookup"><span data-stu-id="4f47d-114">What will users experience?</span></span> 

<span data-ttu-id="4f47d-115">Alla skyddade användare kommer att ha den här upplevelsen med farliga webbadresser:</span><span class="sxs-lookup"><span data-stu-id="4f47d-115">All protected users will have this experience with hazardous URLs:</span></span> 

- <span data-ttu-id="4f47d-116">Om du klickar på länken från en Teams-konversation, gruppchatt eller från kanaler återges en sida i standardwebbläsaren.</span><span class="sxs-lookup"><span data-stu-id="4f47d-116">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="4f47d-117">Om du klickar på länken från en fäst flik visas sidan i teams-gränssnittet på den fliken och alternativet att öppna i webbläsaren inaktiveras av säkerhetsskäl.</span><span class="sxs-lookup"><span data-stu-id="4f47d-117">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="4f47d-118">Den här användaren kommer att blockeras från att gå vidare till webbadressens webbplats.</span><span class="sxs-lookup"><span data-stu-id="4f47d-118">This user will be blocked from proceeding to the URL's site.</span></span>

<span data-ttu-id="4f47d-119">Om användaren som skickade länken inte skyddas av Office 365 ATP kan han eller hon klicka på webbadressen på sin dator och lösa problemplatsen.</span><span class="sxs-lookup"><span data-stu-id="4f47d-119">If the user who sent the link isn't protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="4f47d-120">Detta gör det dubbelt viktigt för Office 365-administratörer att vara medvetna om vilka deras skyddade användare är och bör vara.</span><span class="sxs-lookup"><span data-stu-id="4f47d-120">This makes it doubly important for Office 365 Administrators to be aware of who their protected users are and should be.</span></span>

![En sida med säkra länkar för team som rapporterar en skadlig länk och blockerar överföring till sidan.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="4f47d-122">Om du klickar på knappen *Gå bakåt* på den här sidan i Teams stängs den (eller kan det leda till att en tom sida som användarna kan stänga ute).</span><span class="sxs-lookup"><span data-stu-id="4f47d-122">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="4f47d-123">Men om du klickar på länken igen kommer det att resultera i en ny bedömning av webbplatsens rykte så att den här sidan visas igen.</span><span class="sxs-lookup"><span data-stu-id="4f47d-123">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
><span data-ttu-id="4f47d-124">Vissa Office 365-administratörer aktiverar meddelandet **Fortsätt ändå** på blockeringssidan.</span><span class="sxs-lookup"><span data-stu-id="4f47d-124">Some Office 365 Admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="4f47d-125">Men om säkra länkar mäter rykte en webbplats och finner det saknas, bör ingen ytterligare klickning genomföras.</span><span class="sxs-lookup"><span data-stu-id="4f47d-125">However, if safe links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="4f47d-126">Det rekommenderas inte att användare kringgår säkerhetsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="4f47d-126">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="4f47d-127">Vänligen väg in detta i dina överväganden innan du aktiverar Fortsätt ändå.</span><span class="sxs-lookup"><span data-stu-id="4f47d-127">Please weigh this into your considerations before enabling Continue Anyway.</span></span> 

