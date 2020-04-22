---
title: ATP Säkra länkar för teams, safelinks, säkra länkar, blockera skadliga länkar, office 365 atp, Teams säkra länkar, stoppa användare från att klicka på dåliga länkar, skadliga länkar
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
ms.openlocfilehash: 88fe9756188eb16a2347d3c0cd4a98b4003ff457
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636004"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a><span data-ttu-id="0b611-104">Säkra länkar i team</span><span class="sxs-lookup"><span data-stu-id="0b611-104">Safe Links in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0b611-105">Den här funktionen finns i **Offentlig förhandsversion** för kunder i MICROSOFT Teams Technology Adoption Program (TAP) från och med den 28 februari 2020.</span><span class="sxs-lookup"><span data-stu-id="0b611-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="0b611-106">Den här anteckningen tas bort från artikeln när säkra länkar för teams är mer allmänt tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="0b611-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="0b611-107">Microsoft Teams, ett molnbaserat microsoftprogram för att hantera ditt arbete, använder redan säkra bilagor (för Office 365), men det har nu tillgång till säkra länkar när du klickar.</span><span class="sxs-lookup"><span data-stu-id="0b611-107">Microsoft Teams, a Microsoft cloud-based application for managing your work, already uses safe attachments (for Office 365), but it will now have access to safe links at the time of your click.</span></span> <span data-ttu-id="0b611-108">Oavsett om du använder chattar 1-mot-1-chattar, mellan grupper eller i kanaler och flikar, om du har en prenumeration på Office 365 ATP, har du möjlighet att aktivera och använda den här säkerhetsåtgärden.</span><span class="sxs-lookup"><span data-stu-id="0b611-108">Whether you're using chats 1-on-1 Chats, between Groups, or in Channels, and Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span>

<span data-ttu-id="0b611-109">Så här fungerar det:</span><span class="sxs-lookup"><span data-stu-id="0b611-109">Here's how it works:</span></span> 

1. <span data-ttu-id="0b611-110">När du startar Teams-programmet kontrollerar Microsoft 365 att användaren tillhör en organisation som har Office 365 ATP och att användaren ingår i en aktiv princip för säkra länkar med dess skydd aktiverat för Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0b611-110">When you start the Teams application, Microsoft 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="0b611-111">Om ovanstående är sant valideras webbadresser vid klicktillfället i Chattar, Gruppchattar, Kanaler och i flikar för den användaren.</span><span class="sxs-lookup"><span data-stu-id="0b611-111">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>
 
## <a name="what-will-users-experience"></a><span data-ttu-id="0b611-112">Vad kommer användarna att uppleva?</span><span class="sxs-lookup"><span data-stu-id="0b611-112">What will users experience?</span></span> 

<span data-ttu-id="0b611-113">Alla skyddade användare kommer att ha den här upplevelsen med farliga webbadresser:</span><span class="sxs-lookup"><span data-stu-id="0b611-113">All protected users will have this experience with hazardous URLs:</span></span> 

- <span data-ttu-id="0b611-114">Om du klickar på länken från en Teams-konversation, gruppchatt eller från kanaler återges en sida i standardwebbläsaren.</span><span class="sxs-lookup"><span data-stu-id="0b611-114">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="0b611-115">Om du klickar på länken från en fäst flik visas sidan i teams-gränssnittet på den fliken och alternativet att öppna i webbläsaren inaktiveras av säkerhetsskäl.</span><span class="sxs-lookup"><span data-stu-id="0b611-115">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="0b611-116">Den här användaren kommer att blockeras från att gå vidare till webbadressens webbplats.</span><span class="sxs-lookup"><span data-stu-id="0b611-116">This user will be blocked from proceeding to the URL's site.</span></span>

<span data-ttu-id="0b611-117">Om användaren som skickade länken inte skyddas av Office 365 ATP kan han eller hon klicka på webbadressen på sin dator och lösa problemplatsen.</span><span class="sxs-lookup"><span data-stu-id="0b611-117">If the user who sent the link isn't protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="0b611-118">Detta gör det dubbelt viktigt för administratörer att vara medvetna om vilka deras skyddade användare är och bör vara.</span><span class="sxs-lookup"><span data-stu-id="0b611-118">This makes it doubly important for administrators to be aware of who their protected users are and should be.</span></span>

![En sida med säkra länkar för team som rapporterar en skadlig länk och blockerar överföring till sidan.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="0b611-120">Om du klickar på knappen *Gå bakåt* på den här sidan i Teams stängs den (eller kan det leda till att en tom sida som användarna kan stänga ute).</span><span class="sxs-lookup"><span data-stu-id="0b611-120">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="0b611-121">Men om du klickar på länken igen kommer det att resultera i en ny bedömning av webbplatsens rykte så att den här sidan visas igen.</span><span class="sxs-lookup"><span data-stu-id="0b611-121">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
><span data-ttu-id="0b611-122">Vissa Microsoft 365-administratörer aktiverar meddelandet **Fortsätt ändå** på blockeringssidan.</span><span class="sxs-lookup"><span data-stu-id="0b611-122">Some Microsoft 365 admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="0b611-123">Men om säkra länkar mäter rykte en webbplats och finner det saknas, bör ingen ytterligare klickning genomföras.</span><span class="sxs-lookup"><span data-stu-id="0b611-123">However, if safe links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="0b611-124">Det rekommenderas inte att användare kringgår säkerhetsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="0b611-124">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="0b611-125">Vänligen väg in detta i dina överväganden innan du aktiverar Fortsätt ändå.</span><span class="sxs-lookup"><span data-stu-id="0b611-125">Please weigh this into your considerations before enabling Continue Anyway.</span></span> 

