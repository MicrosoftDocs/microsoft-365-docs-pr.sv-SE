---
title: Ange språk-och tids zoner i Microsoft-bokningar
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 94af3e22-aca6-4e91-8b91-1cd5a02a9ea8
description: Ändra språk-och tids zons inställningar i Microsoft-bokningar. Om bokningarna skapas på fel tid kan det bero på att den inte är aktive rad.
ms.openlocfilehash: 07e5dde2a896610ee079063943aff24ec69ba721
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/09/2020
ms.locfileid: "47420203"
---
# <a name="set-language-and-time-zones-in-microsoft-bookings"></a><span data-ttu-id="30a61-104">Ange språk-och tids zoner i Microsoft-bokningar</span><span class="sxs-lookup"><span data-stu-id="30a61-104">Set language and time zones in Microsoft Bookings</span></span>

<span data-ttu-id="30a61-105">Om du använder Microsoft-bokningar och bokningar skapas på fel gång kan det hända att dina tids zons inställningar måste ändras.</span><span class="sxs-lookup"><span data-stu-id="30a61-105">If you are using Microsoft Bookings and bookings are created at the wrong time, then your time zone settings might need to be changed.</span></span> <span data-ttu-id="30a61-106">Om vissa bokningar är på fel språk kan du behöva ändra dina språk inställningar.</span><span class="sxs-lookup"><span data-stu-id="30a61-106">Likewise, if some bookings are in the wrong language, you might need to change your language settings.</span></span>

<span data-ttu-id="30a61-107">Det finns två separata inställningar för språk och tidszon för bokningar.</span><span class="sxs-lookup"><span data-stu-id="30a61-107">There are two separate language and time zone settings for Bookings.</span></span> <span data-ttu-id="30a61-108">Den första inställningen styr tids zonen för boknings kalender och anges med hjälp av Outlook på webben inställningar för den personliga kalendern för den inloggade användaren.</span><span class="sxs-lookup"><span data-stu-id="30a61-108">The first setting controls the language and time zone of the booking calendar and is set using the Outlook on the web settings for the personal calendar of the logged-in user.</span></span> <span data-ttu-id="30a61-109">Den andra inställningen påverkar den boknings sida för självbetjäning som kunderna använder och är inställd på en "nationella inställningar"-sida som styr språk-och tidszon för den aktuella sidan.</span><span class="sxs-lookup"><span data-stu-id="30a61-109">The second setting affects the self-service booking page that your customers use and is set using a "regional settings" page that controls language and time zone only for that page.</span></span>

> [!NOTE]
> <span data-ttu-id="30a61-110">Bokningar är som standard aktiverade för kunder som har Microsoft 365 Business Standard, Microsoft 365 a3 eller Microsoft 365 A5.</span><span class="sxs-lookup"><span data-stu-id="30a61-110">Bookings is turned on by default for customers who have the Microsoft 365 Business Standard, Microsoft 365 A3, or Microsoft 365 A5 subscriptions.</span></span> <span data-ttu-id="30a61-111">Bokningar är också tillgängliga för kunder som har Office 365 Enterprise E3 och Office 365 Enterprise, E5, men det är inaktiverat som standard.</span><span class="sxs-lookup"><span data-stu-id="30a61-111">Bookings is also available to customers who have Office 365 Enterprise E3 and Office 365 Enterprise E5, but it is turned off by default.</span></span> <span data-ttu-id="30a61-112">Kom igång genom att läsa [få till gång till Microsoft-bokningar](get-access.md).</span><span class="sxs-lookup"><span data-stu-id="30a61-112">To get started, see [Get access to Microsoft Bookings](get-access.md).</span></span> <span data-ttu-id="30a61-113">Om du vill aktivera eller inaktivera uppslagning kan du läsa [Aktivera och inaktivera en organisation](turn-bookings-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="30a61-113">To turn Bookings on or off, see [Turn Bookings on or off for your organization](turn-bookings-on-or-off.md).</span></span>

## <a name="setting-language-and-time-zone-for-a-booking-calendar"></a><span data-ttu-id="30a61-114">Ange språk och tidszon för en boknings kalender</span><span class="sxs-lookup"><span data-stu-id="30a61-114">Setting language and time zone for a booking calendar</span></span>

<span data-ttu-id="30a61-115">Boknings kalendern använder den inloggade användarens språk-och tids zons inställningar.</span><span class="sxs-lookup"><span data-stu-id="30a61-115">The booking calendar uses the logged-in user’s language and time zone settings.</span></span> <span data-ttu-id="30a61-116">Exempel: om den inloggade användarens tidszon är inställd på Eastern Standard Time (EST) visar boknings kalender befintliga start-och slut tider för avtalad tid i EST.</span><span class="sxs-lookup"><span data-stu-id="30a61-116">For example, If the logged-in user’s time zone is set to Eastern Standard Time (EST), then the booking calendar will show existing appointment start and end times in EST.</span></span> <span data-ttu-id="30a61-117">Den här tids zonen angavs ursprungligen när användarens Microsoft 365 och Outlook på webb kontona skapades.</span><span class="sxs-lookup"><span data-stu-id="30a61-117">This time zone was originally set when the user’s Microsoft 365 and Outlook on the web accounts were created.</span></span>

<span data-ttu-id="30a61-118">Så här anger du språk och tidszon för en boknings kalender:</span><span class="sxs-lookup"><span data-stu-id="30a61-118">To set the language and time zone for the booking calendar:</span></span>

1. <span data-ttu-id="30a61-119">Logga in på Microsoft 365 och välj Outlook-panelen på Start sidan (som visas i skärm bilden nedan) eller i Microsoft 365-startprogrammet.</span><span class="sxs-lookup"><span data-stu-id="30a61-119">Log into Microsoft 365 and select the Outlook tile on the landing page (as shown in the screenshot below) or in the Microsoft 365 App Launcher.</span></span>

   ![Bild av Outlook-panelen på Microsoft 365-Sidan](../media/bookings-outlook-tile.png)

1. <span data-ttu-id="30a61-121">När Outlook öppnas väljer du **kugg hjuls ikonen** i det övre högra hörnet av skärmen för att öppna dina inställningar för privat dator och konto och söker efter "tidszon" i sökrutan i **inställnings** panelen.</span><span class="sxs-lookup"><span data-stu-id="30a61-121">After Outlook opens, select the **gear icon** in the upper, right-hand corner of the screen to open your personal and account settings, then search for “time zone” in the **Settings** panel search box.</span></span> <span data-ttu-id="30a61-122">Panelen uppdateras och visar dina nuvarande personliga språk-och tids zons inställningar för det här kontot.</span><span class="sxs-lookup"><span data-stu-id="30a61-122">The panel will update to show your current personal language and time zone settings for this account.</span></span> <span data-ttu-id="30a61-123">Som vi nämnt ovan styr den här inställningen också språk-och tids zonen i boknings kalendern.</span><span class="sxs-lookup"><span data-stu-id="30a61-123">As noted above, this setting also controls the language and time zone of the booking calendar.</span></span>

1. <span data-ttu-id="30a61-124">Ändra språk eller tidszon genom att välja den nedrullningsbara List rutan i **området språk eller aktuell** tidszon och välja önskad inställning.</span><span class="sxs-lookup"><span data-stu-id="30a61-124">Change the language or time zone by selecting the drop-down arrow in the **Language or Current time zone** box and choosing the desired setting.</span></span>

1. <span data-ttu-id="30a61-125">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="30a61-125">Click **Save**.</span></span> <span data-ttu-id="30a61-126">Inställnings panelen stängs, Outlook på webben startas om och nya inställningar för språk och tidszon tillämpas.</span><span class="sxs-lookup"><span data-stu-id="30a61-126">The Settings panel closes, Outlook on the web restarts, and the new language and time zone settings are applied.</span></span>

## <a name="setting-the-language-and-time-zone-for-the-booking-page"></a><span data-ttu-id="30a61-127">Ange språk och tidszon för boknings sidan</span><span class="sxs-lookup"><span data-stu-id="30a61-127">Setting the language and time zone for the booking page</span></span>

1. <span data-ttu-id="30a61-128">I Microsoft 365 väljer du Start programmet och väljer sedan **bokningar**.</span><span class="sxs-lookup"><span data-stu-id="30a61-128">In Microsoft 365, select the app launcher, and then select **Bookings**.</span></span>

1. <span data-ttu-id="30a61-129">I navigerings fönstret väljer du **boka sida** och väljer **ändra inställningar för språk och tidszon**.</span><span class="sxs-lookup"><span data-stu-id="30a61-129">In the navigation pane, select **Booking page** and select **Change language and time zone settings**.</span></span>

   ![Skärm bild: länken Ändra språk-och tids zons inställningar](../media/bookings-region-language-timezone-settings.png)

1. <span data-ttu-id="30a61-131">Välj språk och aktuell tidszon och välj OK.</span><span class="sxs-lookup"><span data-stu-id="30a61-131">Select your language and current time zone and choose OK.</span></span>

   ![Skärm bild: språk-och tids zons inställningar](../media/bookings-region-timezone-settings.png)
