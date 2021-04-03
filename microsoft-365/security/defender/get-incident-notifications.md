---
title: Få incidentmeddelanden i Microsoft 365 Defender
description: Lär dig hur du skapar regler för att få e-postaviseringar för incidenter i Microsoft 365 Defender
keywords: incident, e-post, e-postmeddelanden, konfigurera, användare, postlåda, e-post, incidenter
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fec2263599f3ed727d3d9d70023927084eb1c094
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501076"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="9bd96-104">Få incidentaviseringar via e-post</span><span class="sxs-lookup"><span data-stu-id="9bd96-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9bd96-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9bd96-105">**Applies to:**</span></span>
- <span data-ttu-id="9bd96-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bd96-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9bd96-107">Du kan konfigurera Microsoft 365 Defender så att du får ett e-postmeddelande varje gång det finns nya incidenter eller nya uppdateringar av befintliga incidenter.</span><span class="sxs-lookup"><span data-stu-id="9bd96-107">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="9bd96-108">Du kan välja att få aviseringar utifrån allvarlighetsgrad eller enhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="9bd96-108">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="9bd96-109">Du kan också välja att bara få ett meddelande vid den första uppdateringen per incident.</span><span class="sxs-lookup"><span data-stu-id="9bd96-109">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="9bd96-110">Du kan lägga till eller ta bort mottagare i e-postaviseringarna.</span><span class="sxs-lookup"><span data-stu-id="9bd96-110">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="9bd96-111">Nyligen tillagda mottagare får ett meddelande om incidenter när de har lagts till.</span><span class="sxs-lookup"><span data-stu-id="9bd96-111">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="9bd96-112">E-postmeddelandet innehåller viktig information om incidenten, bland annat incidentens namn, allvarlighetsgrad och kategorier.</span><span class="sxs-lookup"><span data-stu-id="9bd96-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="9bd96-113">Du kan också gå direkt till incidenterna så att du kan börja din undersökning direkt.</span><span class="sxs-lookup"><span data-stu-id="9bd96-113">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="9bd96-114">Mer information om hur du undersöker incidenter [finns i Undersöka incidenter i Microsoft 365 Defender.](./investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="9bd96-114">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](./investigate-incidents.md).</span></span>

>[!NOTE]
><span data-ttu-id="9bd96-115">Du behöver behörigheten Hantera säkerhetsinställningar för att konfigurera inställningar för e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="9bd96-115">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="9bd96-116">Om du har valt att använda grundläggande behörighetshantering kan användare med roller som säkerhetsadministratör eller global administratör konfigurera e-postaviseringar åt dig.</span><span class="sxs-lookup"><span data-stu-id="9bd96-116">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="9bd96-117">På samma sätt kan du, om din organisation använder rollbaserad åtkomstkontroll (RBAC), bara skapa, redigera, ta bort och ta emot meddelanden baserat på enhetsgrupper som du har behörighet att hantera.</span><span class="sxs-lookup"><span data-stu-id="9bd96-117">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="9bd96-118">Skapa regler för incidentmeddelanden</span><span class="sxs-lookup"><span data-stu-id="9bd96-118">Create rules for incident notifications</span></span>

<span data-ttu-id="9bd96-119">Om du vill konfigurera din första e-postavisering för incidenter skapar du en ny regel och anpassar inställningarna för e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="9bd96-119">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="9bd96-120">Välj Inställningar Incident-e-postaviseringar   >  **i navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="9bd96-120">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="9bd96-121">Välj **Lägg till objekt.**</span><span class="sxs-lookup"><span data-stu-id="9bd96-121">Select **Add item**.</span></span>
3. <span data-ttu-id="9bd96-122">Ge regeln ett namn i **Namn och** ange en **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="9bd96-122">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![Skapa regelfönster för meddelanden om incidenter](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="9bd96-124">Välj **Nästa för** att gå till **Meddelandeinställningar**.</span><span class="sxs-lookup"><span data-stu-id="9bd96-124">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="9bd96-125">Här kan du ange:</span><span class="sxs-lookup"><span data-stu-id="9bd96-125">Here you can specify:</span></span>
    - <span data-ttu-id="9bd96-126">**Aviserings allvarlighetsgrad** – Välj den aviserings allvarlighetsgrad som utlöser en incidentavisering.</span><span class="sxs-lookup"><span data-stu-id="9bd96-126">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="9bd96-127">Om du till exempel bara vill informeras om incidenter med hög allvarlighetsgrad väljer du Hög.</span><span class="sxs-lookup"><span data-stu-id="9bd96-127">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="9bd96-128">**Enhetsgruppomfattning** – I den här listrutan visas alla enhetsgrupper som användaren kan komma åt.</span><span class="sxs-lookup"><span data-stu-id="9bd96-128">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="9bd96-129">Välj vilken enhetsgrupper du skapar aviseringsregler för.</span><span class="sxs-lookup"><span data-stu-id="9bd96-129">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="9bd96-130">**Meddela endast vid första förekomsten per incident** – Om du väljer det här alternativet skickas bara en e-postavisering i den första aviseringen som matchar dina andra val.</span><span class="sxs-lookup"><span data-stu-id="9bd96-130">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="9bd96-131">Senare uppdateringar eller aviseringar relaterade till händelsen utlöser inte någon avisering.</span><span class="sxs-lookup"><span data-stu-id="9bd96-131">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="9bd96-132">**Inkludera organisationsnamn** – anger om kundnamnet visas i e-postmeddelandet eller inte.</span><span class="sxs-lookup"><span data-stu-id="9bd96-132">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="9bd96-133">**Inkludera klientspecifik portallänk – Lägger** till en länk med klientorganisations-ID:t för att tillåta åtkomst till en viss klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="9bd96-133">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![Fönstret Notif-inställningar för incident-e-postmeddelanden](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="9bd96-135">Välj **Nästa** för att gå **till avsnittet** Mottagare.</span><span class="sxs-lookup"><span data-stu-id="9bd96-135">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="9bd96-136">Här kan du ange e-postadresser som ska ta emot e-postaviseringarna.</span><span class="sxs-lookup"><span data-stu-id="9bd96-136">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="9bd96-137">Välj **Lägg till en mottagare när** du har skrivit varje e-postadress.</span><span class="sxs-lookup"><span data-stu-id="9bd96-137">Select **Add a recipient** after typing every email address.</span></span>

    ![Fönstret Lägg till mottagare för meddelanden om incidenter](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="9bd96-139">Välj Nästa **för att** gå till Granska regel **så** att du kan se alla inställningar som är kopplade till den nya regeln.</span><span class="sxs-lookup"><span data-stu-id="9bd96-139">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="9bd96-140">Mottagarna får incidentaviseringar via e-post baserat på inställningarna.</span><span class="sxs-lookup"><span data-stu-id="9bd96-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="9bd96-141">Se även</span><span class="sxs-lookup"><span data-stu-id="9bd96-141">See also</span></span>
- [<span data-ttu-id="9bd96-142">Översikt över incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bd96-142">Incidents overview in Microsoft 365 Defender</span></span>](./incidents-overview.md)
- [<span data-ttu-id="9bd96-143">Prioritera incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bd96-143">Prioritize incidents in Microsoft 365 Defender</span></span>](./incident-queue.md)
- [<span data-ttu-id="9bd96-144">Undersöka incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bd96-144">Investigate incidents in Microsoft 365 Defender</span></span>](./investigate-incidents.md)
