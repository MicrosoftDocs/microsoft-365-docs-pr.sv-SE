---
title: ATP-säkra Länkar för team, safelinks, säkra länkar, blockera skadliga länkar, Office 365 ATP, teams Safe Links, hindra användare från att klicka på felaktiga länkar, illasinnade länkar
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
description: Teams kommer nu att ha till gång till säkra länkar när du klickar på. Oavsett om du använder chattar 1-i-1-chatt, mellan grupper eller i kanaler och på flikar, om du har ett abonnemang på Office 365 ATP kan du aktivera och använda den här säkerhetsfunktionen.
ms.openlocfilehash: 362fb37b352a77aea07b899b707dbf4ac3d440d5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198757"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a><span data-ttu-id="78be7-104">Säkra länkar i Teams</span><span class="sxs-lookup"><span data-stu-id="78be7-104">Safe Links in Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> <span data-ttu-id="78be7-105">Den här funktionen är i **offentlig för hands version** för kunder i Microsoft Teams-programmet (tryck) enligt februari 2020.</span><span class="sxs-lookup"><span data-stu-id="78be7-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="78be7-106">Den här anteckningen tas bort från artikeln när säkra Länkar för team är mer tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="78be7-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="78be7-107">Microsoft Teams, ett Microsoft Cloud-baserat program för att hantera ditt arbete använder redan säkra bifogade filer (för Office 365), men nu kommer du åt säkra länkar när du klickar på den.</span><span class="sxs-lookup"><span data-stu-id="78be7-107">Microsoft Teams, a Microsoft cloud-based application for managing your work, already uses Safe Attachments (for Office 365), but it will now have access to Safe Links at the time of your click.</span></span> <span data-ttu-id="78be7-108">Oavsett om du använder chattar, gruppchatt, kanaler eller flikar om du har ett abonnemang på Office 365 ATP kan du aktivera och använda den här säkerhets åtgärden.</span><span class="sxs-lookup"><span data-stu-id="78be7-108">Whether you're using Chats, Group Chats, Channels, or Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span> <span data-ttu-id="78be7-109">Mer information om licensierings kraven finns i [Microsoft 365 licens rådgivning för tjänster på klient organisations nivå](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="78be7-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="78be7-110">Så här fungerar det:</span><span class="sxs-lookup"><span data-stu-id="78be7-110">Here's how it works:</span></span>

1. <span data-ttu-id="78be7-111">När du startar Teams-programmet kontrollerar Microsoft 365 att användaren tillhör en organisation som har Office 365 ATP och att användaren ingår i en Active Safe Links-princip med skydd aktiverat för Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="78be7-111">When you start the Teams application, Microsoft 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="78be7-112">Om ovanstående stämmer val IDE ras URL-adresser vid tiden för Klicka i chatt, gruppchattar, kanaler och på flikar för den användaren.</span><span class="sxs-lookup"><span data-stu-id="78be7-112">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>

## <a name="what-will-users-experience"></a><span data-ttu-id="78be7-113">Vad händer med användare?</span><span class="sxs-lookup"><span data-stu-id="78be7-113">What will users experience?</span></span>

<span data-ttu-id="78be7-114">Alla skyddade användare får denna upplevelse med farliga webb adresser:</span><span class="sxs-lookup"><span data-stu-id="78be7-114">All protected users will have this experience with hazardous URLs:</span></span>

- <span data-ttu-id="78be7-115">Om länken klickade på en grupp konversation, gruppchatt eller från kanaler visas en sida i standard webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="78be7-115">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="78be7-116">Om länken klickade på en Fäst flik visas sidan i användar gränssnittet på fliken och alternativet att öppna i webbläsaren kommer att avaktiveras av säkerhets skäl.</span><span class="sxs-lookup"><span data-stu-id="78be7-116">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="78be7-117">Denna användare kommer att blockeras från att gå vidare till URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="78be7-117">This user will be blocked from proceeding to the URL's site.</span></span>

<span data-ttu-id="78be7-118">Om användaren som skickade länken inte är skyddad av Office 365 ATP är han eller hon fri att klicka på URL-adressen på sin dator och lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="78be7-118">If the user who sent the link isn't protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="78be7-119">Det gör det dubblerat viktigt för administratörer att vara medvetna om vilka deras skyddade användare och bör vara.</span><span class="sxs-lookup"><span data-stu-id="78be7-119">This makes it doubly important for administrators to be aware of who their protected users are and should be.</span></span>

![En Safe Links för Teams-sidan rapporterar en skadlig länk och blockerar transitering till sidan.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="78be7-121">Om du klickar på knappen *gå tillbaka* på den här sidan i Teams stängs det (eller så kan användarna få en tom sida).</span><span class="sxs-lookup"><span data-stu-id="78be7-121">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="78be7-122">Om du klickar på länken igen kommer du att få en ny utvärdering av webbplatsens rykte så att sidan visas igen.</span><span class="sxs-lookup"><span data-stu-id="78be7-122">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
> <span data-ttu-id="78be7-123">I vissa Microsoft 365-administratörer aktive ras meddelandet **Fortsätt ändå** på sidan blockera.</span><span class="sxs-lookup"><span data-stu-id="78be7-123">Some Microsoft 365 admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="78be7-124">Men om Safe Links mäter ryktet hos en webbplats och hittar den inte längre behöver du bara klicka-och-genom.</span><span class="sxs-lookup"><span data-stu-id="78be7-124">However, if Safe Links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="78be7-125">Det rekommenderas inte att användare kringgår säkerhets åtgärder.</span><span class="sxs-lookup"><span data-stu-id="78be7-125">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="78be7-126">Var god ange detta innan du aktiverar Fortsätt ändå.</span><span class="sxs-lookup"><span data-stu-id="78be7-126">Please weigh this into your considerations before enabling Continue Anyway.</span></span>
