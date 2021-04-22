---
title: Få incidentmeddelanden via e-post i Microsoft 365 Defender
description: Lär dig hur du skapar regler för att få e-postaviseringar för incidenter i Microsoft 365 Defender
keywords: incident, e-post, e-postmeddelanden, konfigurera, användare, postlåda, e-post, incidenter, analysera, svara
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
ms.openlocfilehash: 7ba21e08f72760654993335764df00e78abc87b2
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939724"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="5d815-104">Få incidentaviseringar via e-post</span><span class="sxs-lookup"><span data-stu-id="5d815-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5d815-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="5d815-105">**Applies to:**</span></span>
- <span data-ttu-id="5d815-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d815-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="5d815-107">Du kan konfigurera Microsoft 365 Defender så att din personal får ett e-postmeddelande om nya incidenter eller uppdateringar av befintliga incidenter.</span><span class="sxs-lookup"><span data-stu-id="5d815-107">You can set up Microsoft 365 Defender to notify your staff with an email about new incidents or updates to existing incidents.</span></span> <span data-ttu-id="5d815-108">Du kan välja att få aviseringar baserat på:</span><span class="sxs-lookup"><span data-stu-id="5d815-108">You can choose to get notifications based on:</span></span>

- <span data-ttu-id="5d815-109">Incidentens allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="5d815-109">Incident severity.</span></span>
- <span data-ttu-id="5d815-110">Enhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="5d815-110">Device group.</span></span>
- <span data-ttu-id="5d815-111">Endast vid den första uppdateringen per incident.</span><span class="sxs-lookup"><span data-stu-id="5d815-111">Only on the first update per incident.</span></span>

<span data-ttu-id="5d815-112">E-postmeddelandet innehåller viktig information om incidenten, bland annat incidentens namn, allvarlighetsgrad och kategorier.</span><span class="sxs-lookup"><span data-stu-id="5d815-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="5d815-113">Du kan också gå direkt till incidenten och börja analysera direkt.</span><span class="sxs-lookup"><span data-stu-id="5d815-113">You can also go directly to the incident and start your analysis right away.</span></span> <span data-ttu-id="5d815-114">Mer information finns i [Analysera incidenter.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="5d815-114">For more information, see [Analyze incidents](investigate-incidents.md).</span></span>

<span data-ttu-id="5d815-115">Du kan lägga till eller ta bort mottagare i e-postaviseringarna.</span><span class="sxs-lookup"><span data-stu-id="5d815-115">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="5d815-116">Nya mottagare får ett meddelande om incidenter när de har lagts till.</span><span class="sxs-lookup"><span data-stu-id="5d815-116">New recipients get notified about incidents after they're added.</span></span> 

>[!NOTE]
><span data-ttu-id="5d815-117">Du behöver behörigheten Hantera säkerhetsinställningar för att konfigurera inställningar för e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="5d815-117">You need the 'Manage security settings' permission to configure email notification settings.</span></span> <span data-ttu-id="5d815-118">Om du har valt att använda grundläggande behörighetshantering kan användare med roller som säkerhetsadministratör eller global administratör konfigurera e-postaviseringar åt dig.</span><span class="sxs-lookup"><span data-stu-id="5d815-118">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="5d815-119">På samma sätt kan du, om din organisation använder rollbaserad åtkomstkontroll (RBAC), bara skapa, redigera, ta bort och ta emot meddelanden baserat på enhetsgrupper som du har behörighet att hantera.</span><span class="sxs-lookup"><span data-stu-id="5d815-119">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-a-rule-for-email-notifications"></a><span data-ttu-id="5d815-120">Skapa en regel för e-postaviseringar</span><span class="sxs-lookup"><span data-stu-id="5d815-120">Create a rule for email notifications</span></span>

<span data-ttu-id="5d815-121">Följ de här anvisningarna för att skapa en ny regel och anpassa inställningarna för e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="5d815-121">Follow these steps to create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="5d815-122">I navigeringsfönstret väljer du Inställningar **> Microsoft 365 Defender och > e-postmeddelanden om incidenter**.</span><span class="sxs-lookup"><span data-stu-id="5d815-122">In the navigation pane, select **Settings > Microsoft 365 Defender > Incident email notifications**.</span></span>
2. <span data-ttu-id="5d815-123">Välj **Lägg till objekt.**</span><span class="sxs-lookup"><span data-stu-id="5d815-123">Select **Add item**.</span></span>
3. <span data-ttu-id="5d815-124">Skriv **regelnamnet** och en beskrivning på sidan Grunder och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="5d815-124">On the **Basics** page, type the rule name and a description, and then select **Next**.</span></span>
4. <span data-ttu-id="5d815-125">På sidan **Meddelandeinställningar** konfigurerar du:</span><span class="sxs-lookup"><span data-stu-id="5d815-125">On the **Notification settings** page, configure:</span></span>
    - <span data-ttu-id="5d815-126">**Aviserings allvarlighetsgrad** – Välj den aviserings allvarlighetsgrad som utlöser en incidentavisering.</span><span class="sxs-lookup"><span data-stu-id="5d815-126">**Alert severity** - Choose the alert severities that will trigger an incident notification.</span></span> <span data-ttu-id="5d815-127">Om du till exempel bara vill informeras om incidenter med hög allvarlighetsgrad väljer du **Hög.**</span><span class="sxs-lookup"><span data-stu-id="5d815-127">For example, if you only want to be informed about high-severity incidents, select **High**.</span></span>
    - <span data-ttu-id="5d815-128">**Enhetsgruppomfattning** – Du kan ange alla enhetsgrupper eller välja i listan över enhetsgrupper i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="5d815-128">**Device group scope** - You can specify all device groups or select from the list of device groups in your tenant.</span></span>
    - <span data-ttu-id="5d815-129">**Meddela endast vid första förekomsten per incident** – Välj om du bara vill ha en avisering på den första aviseringen som matchar dina andra val.</span><span class="sxs-lookup"><span data-stu-id="5d815-129">**Only notify on first occurrence per incident** - Select if you want a notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="5d815-130">Senare uppdateringar eller aviseringar relaterade till händelsen skickar inte ytterligare meddelanden.</span><span class="sxs-lookup"><span data-stu-id="5d815-130">Later updates or alerts related to the incident won't send additional notifications.</span></span>
    - <span data-ttu-id="5d815-131">**Inkludera organisationens namn i e-postmeddelandet** – Välj om du vill att organisationens namn ska visas i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="5d815-131">**Include organization name in the email** - Select if you want your organization name to appear in the email notification.</span></span>
    - <span data-ttu-id="5d815-132">**Inkludera klientspecifik portallänk** – välj om du vill lägga till en länk med klientorganisations-ID:t i e-postmeddelandet för åtkomst till en viss Microsoft 365-klient.</span><span class="sxs-lookup"><span data-stu-id="5d815-132">**Include tenant-specific portal link** - Select if you want to add a link with the tenant ID in the email notification for access to a specific Microsoft 365 tenant.</span></span>

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="Meddelandeinställningar för incidentmeddelanden":::

5. <span data-ttu-id="5d815-134">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="5d815-134">Select **Next**.</span></span> <span data-ttu-id="5d815-135">På sidan **Mottagare** lägger du till de e-postadresser som ska ta emot incidentaviseringarna.</span><span class="sxs-lookup"><span data-stu-id="5d815-135">On the **Recipients** page, add the email addresses that will receive the incident notifications.</span></span> <span data-ttu-id="5d815-136">Välj **Lägg till** när du har skrivit varje ny e-postadress.</span><span class="sxs-lookup"><span data-stu-id="5d815-136">Select **Add** after typing each new email address.</span></span> <span data-ttu-id="5d815-137">Om du vill testa aviseringar och se till att mottagarna får dem i inkorgarna väljer du **Skicka test-e-post.**</span><span class="sxs-lookup"><span data-stu-id="5d815-137">To test notifications and ensure that the recipients receive them in the inboxes, select **Send test email**.</span></span> 
6. <span data-ttu-id="5d815-138">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="5d815-138">Select **Next**.</span></span> <span data-ttu-id="5d815-139">Granska **inställningarna för** regeln på sidan Granska regel och välj sedan **Skapa regel.**</span><span class="sxs-lookup"><span data-stu-id="5d815-139">On the **Review rule** page, review the settings of the rule, and then select **Create rule**.</span></span> <span data-ttu-id="5d815-140">Mottagarna får incidentaviseringar via e-post baserat på inställningarna.</span><span class="sxs-lookup"><span data-stu-id="5d815-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

<span data-ttu-id="5d815-141">Om du vill redigera en befintlig regel väljer du den i listan med regler.</span><span class="sxs-lookup"><span data-stu-id="5d815-141">To edit an existing rule, select it from the list of rules.</span></span> <span data-ttu-id="5d815-142">I fönstret med regelnamnet väljer du **Redigera regel** och gör ändringarna på sidorna **Grunder,** **Meddelandeinställningar** **och** Mottagare.</span><span class="sxs-lookup"><span data-stu-id="5d815-142">On the pane with the rule name, select **Edit rule** and make your changes on the **Basics**, **Notification settings**, and **Recipients** pages.</span></span>

<span data-ttu-id="5d815-143">Om du vill redigera en befintlig regel väljer du den i listan med regler.</span><span class="sxs-lookup"><span data-stu-id="5d815-143">To edit an existing rule, select it from the list of rules.</span></span> <span data-ttu-id="5d815-144">I fönstret med regelnamnet väljer du Ta **bort**.</span><span class="sxs-lookup"><span data-stu-id="5d815-144">On the pane with the rule name, select **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d815-145">Se även</span><span class="sxs-lookup"><span data-stu-id="5d815-145">See also</span></span>
- [<span data-ttu-id="5d815-146">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="5d815-146">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="5d815-147">Prioritera incidenter</span><span class="sxs-lookup"><span data-stu-id="5d815-147">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="5d815-148">Analysera incidenter</span><span class="sxs-lookup"><span data-stu-id="5d815-148">Analyze incidents</span></span>](investigate-incidents.md)
