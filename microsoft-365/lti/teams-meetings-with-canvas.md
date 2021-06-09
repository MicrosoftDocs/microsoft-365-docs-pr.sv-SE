---
title: Använda Microsoft Teams möten med Canvas
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrera Microsoft Teams möten med Canvas
ms.openlocfilehash: 8ccf1c1d45d38fa4a92b556146744a2c17cd5105
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821925"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a><span data-ttu-id="389a3-103">Använda Microsoft Teams möten med Canvas</span><span class="sxs-lookup"><span data-stu-id="389a3-103">Use Microsoft Teams meetings with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="389a3-104">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="389a3-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="389a3-105">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="389a3-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="389a3-106">Microsoft Teams möten är en LTI-app (Learning Tools Interoperability) som hjälper lärare och elever att enkelt navigera mellan sina LMS (Learning Management System) och Teams.</span><span class="sxs-lookup"><span data-stu-id="389a3-106">Microsoft Teams meetings is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="389a3-107">Användare kan komma åt sina klassteam som är kopplade till kursen direkt från LMS.</span><span class="sxs-lookup"><span data-stu-id="389a3-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="389a3-108">Microsoft Office 365 Administratör</span><span class="sxs-lookup"><span data-stu-id="389a3-108">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="389a3-109">Innan du hanterar Microsoft Teams-integreringen i Instructure Canvas är det viktigt att ha Canvass **Microsoft-Teams-Sync-for-Canvas Azure-app** godkänd av din institutions Microsoft Office 365-administratör i Microsoft Azure-innehavaren innan du slutför Canvas-administratörskonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="389a3-109">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="389a3-110">Logga in på Canvas.</span><span class="sxs-lookup"><span data-stu-id="389a3-110">Sign in to Canvas.</span></span>
 
2. <span data-ttu-id="389a3-111">Välj **adminlänken** i det globala navigeringsfältet och välj sedan ditt konto.</span><span class="sxs-lookup"><span data-stu-id="389a3-111">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="389a3-112">I administratörsnavigeringen väljer **Inställningar** och sedan **fliken** Integrationer.</span><span class="sxs-lookup"><span data-stu-id="389a3-112">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span> 

4. <span data-ttu-id="389a3-113">Ange microsofts klientorganisationsnamn och inloggningsattribut.</span><span class="sxs-lookup"><span data-stu-id="389a3-113">Enter your Microsoft tenant name and login attribute.</span></span> 

   <span data-ttu-id="389a3-114">Attributet Login används för att associera Canvas-användaren med en Azure Active Directory användare.</span><span class="sxs-lookup"><span data-stu-id="389a3-114">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span> 

5. <span data-ttu-id="389a3-115">Välj **Uppdatera Inställningar klar.**</span><span class="sxs-lookup"><span data-stu-id="389a3-115">Select **Update Settings** once done.</span></span>

6. <span data-ttu-id="389a3-116">Om du vill godkänna åtkomst för Canvas **microsoft-Teams-Sync-for-Canvas Azure-app** väljer du **länken Bevilja åtkomst för klientorganisation.**</span><span class="sxs-lookup"><span data-stu-id="389a3-116">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="389a3-117">Du omdirigeras till slutpunkten för administratörsmedgivande för Microsoft-identitetsplattformen.</span><span class="sxs-lookup"><span data-stu-id="389a3-117">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![behörigheter](media/permissions.png)

7. <span data-ttu-id="389a3-119">Välj **Acceptera**.</span><span class="sxs-lookup"><span data-stu-id="389a3-119">Select **Accept**.</span></span>
 
8. <span data-ttu-id="389a3-120">Aktivera Microsoft Teams genom att aktivera växlingsknappen.</span><span class="sxs-lookup"><span data-stu-id="389a3-120">Enable the Microsoft Teams sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a><span data-ttu-id="389a3-122">Canvas-administratör</span><span class="sxs-lookup"><span data-stu-id="389a3-122">Canvas Admin</span></span>

<span data-ttu-id="389a3-123">Konfigurera integreringen Microsoft Teams LTI 1.3.</span><span class="sxs-lookup"><span data-stu-id="389a3-123">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="389a3-124">Som Canvas-administratör måste du lägga till LTI Microsoft Teams möten i din miljö.</span><span class="sxs-lookup"><span data-stu-id="389a3-124">As a Canvas Admin, you'll need to add the Microsoft Teams meetings LTI app within your environment.</span></span> <span data-ttu-id="389a3-125">Anteckna LTI-klient-ID för appen.</span><span class="sxs-lookup"><span data-stu-id="389a3-125">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="389a3-126">Microsoft Teams -170000000000703</span><span class="sxs-lookup"><span data-stu-id="389a3-126">Microsoft Teams meetings - 170000000000703</span></span>

1. <span data-ttu-id="389a3-127">Access **Admin settings**  >  **Apps**.</span><span class="sxs-lookup"><span data-stu-id="389a3-127">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="389a3-128">Välj **+ App för** att lägga Teams LTI-appar.</span><span class="sxs-lookup"><span data-stu-id="389a3-128">Select **+ App** to add the Teams LTI apps.</span></span> 
 
   ![externa appar](media/external-apps.png)

3. <span data-ttu-id="389a3-130">Välj **Efter klient-ID** för konfigurationstyp.</span><span class="sxs-lookup"><span data-stu-id="389a3-130">Select **By Client ID** for configuration type.</span></span>

   ![lägg till app](media/add-app.png)

4. <span data-ttu-id="389a3-132">Ange det klient-ID som tillhandahålls och välj sedan **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="389a3-132">Enter the Client ID provided, and then select **Submit**.</span></span>
   
   <span data-ttu-id="389a3-133">Du ser namnet på det Microsoft Teams LTI-appnamnet för möten för klient-ID:t som bekräftelse.</span><span class="sxs-lookup"><span data-stu-id="389a3-133">You'll notice the Microsoft Teams meetings LTI app name for the Client ID for confirmation.</span></span> 

5. <span data-ttu-id="389a3-134">Välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="389a3-134">Select **Install**.</span></span>

   <span data-ttu-id="389a3-135">LTI Microsoft Teams möten läggs till i listan över externa appar.</span><span class="sxs-lookup"><span data-stu-id="389a3-135">The Microsoft Teams meetings LTI app will be added to the list of external apps.</span></span>
