---
title: Få incident meddelanden i Microsoft 365 Defender
description: Lär dig hur du skapar regler för att få e-postaviseringar för händelser i Microsoft 365 Defender
keywords: incident, e-post, e-Notfications, konfigurera, användare, post låda, e-post, incidenter
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f25be4de3f25db869957474c3cb32b20e9f7aa53
ms.sourcegitcommit: 88d358d778804b26d5e41c53b4f725d01a78112b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49848897"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="9e337-104">Få incident meddelanden via e-post</span><span class="sxs-lookup"><span data-stu-id="9e337-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9e337-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9e337-105">**Applies to:**</span></span>
- <span data-ttu-id="9e337-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e337-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9e337-107">Du kan ställa in Microsoft 365 Defender för att meddela dig via e-post varje gång det uppstår nya tillbud eller nya uppdateringar till befintliga incidenter.</span><span class="sxs-lookup"><span data-stu-id="9e337-107">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="9e337-108">Du kan välja att få aviseringar baserat på allvarlighets graden och per enhets grupp.</span><span class="sxs-lookup"><span data-stu-id="9e337-108">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="9e337-109">Du kan också välja att bara få ett meddelande vid den första uppdateringen per olycka.</span><span class="sxs-lookup"><span data-stu-id="9e337-109">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="9e337-110">Du kan lägga till eller ta bort mottagare i e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="9e337-110">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="9e337-111">Nya mottagare meddelas om incidenter när de har lagts till.</span><span class="sxs-lookup"><span data-stu-id="9e337-111">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="9e337-112">E-postmeddelandet innehåller viktig information om händelsen, till exempel namn, allvarlighets grad och kategorier, bland annat.</span><span class="sxs-lookup"><span data-stu-id="9e337-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="9e337-113">Du kan även gå direkt till incidenter så att du kan påbörja undersökningen omedelbart.</span><span class="sxs-lookup"><span data-stu-id="9e337-113">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="9e337-114">Mer information om hur du undersöker problem finns i [undersöka incidenter i Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span><span class="sxs-lookup"><span data-stu-id="9e337-114">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span></span>

>[!NOTE]
><span data-ttu-id="9e337-115">Du måste ha behörigheten Hantera säkerhets inställningar för att konfigurera inställningar för e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="9e337-115">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="9e337-116">Om du har valt att använda grundläggande behörighets hantering kan användare med rollen som säkerhets administratör eller global administratör konfigurera e-postaviseringar åt dig.</span><span class="sxs-lookup"><span data-stu-id="9e337-116">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="9e337-117">Om din organisation använder rollbaserad åtkomst kontroll (RBAC) kan du välja att bara skapa, redigera, ta bort och ta emot meddelanden baserat på de enhets grupper som du får hantera.</span><span class="sxs-lookup"><span data-stu-id="9e337-117">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="9e337-118">Skapa regler för problem meddelanden</span><span class="sxs-lookup"><span data-stu-id="9e337-118">Create rules for incident notifications</span></span>

<span data-ttu-id="9e337-119">Skapa en ny regel och anpassa inställningarna för e-postaviseringar om du vill ställa in ett första meddelande.</span><span class="sxs-lookup"><span data-stu-id="9e337-119">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="9e337-120">I navigerings fönstret väljer du **Inställningar** för  >  **incident epost meddelanden**.</span><span class="sxs-lookup"><span data-stu-id="9e337-120">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="9e337-121">Välj **Lägg till objekt**.</span><span class="sxs-lookup"><span data-stu-id="9e337-121">Select **Add item**.</span></span>
3. <span data-ttu-id="9e337-122">Ge regeln ett namn i **namn** och ange en **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="9e337-122">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![Fönstret Skapa regel för e-notifs](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="9e337-124">Välj **Nästa** för att gå till **aviserings inställningar**.</span><span class="sxs-lookup"><span data-stu-id="9e337-124">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="9e337-125">Här kan du ange:</span><span class="sxs-lookup"><span data-stu-id="9e337-125">Here you can specify:</span></span>
    - <span data-ttu-id="9e337-126">**Aviserings allvarlighets grad** – Välj aviseringens allvarlighets grad som kommer att utlösa en incident avisering.</span><span class="sxs-lookup"><span data-stu-id="9e337-126">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="9e337-127">Om du till exempel bara vill bli informerad om problem med hög allvarlighets grad väljer du High.</span><span class="sxs-lookup"><span data-stu-id="9e337-127">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="9e337-128">**Enhets gruppens omfattning** – den här List rutan visar alla enhets grupper som användaren kan komma åt.</span><span class="sxs-lookup"><span data-stu-id="9e337-128">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="9e337-129">Välj vilka enhets grupper som du vill skapa incident regler för.</span><span class="sxs-lookup"><span data-stu-id="9e337-129">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="9e337-130">**Meddela bara vid den första förekomsten per händelse** – om du väljer det här alternativet skickas ett e-postmeddelande endast för den första aviseringen som matchar dina andra val.</span><span class="sxs-lookup"><span data-stu-id="9e337-130">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="9e337-131">Senare uppdateringar eller larm som rör händelsen utlöser inte ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="9e337-131">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="9e337-132">**Inkludera organisationens namn** -visar om kund namnet visas i e-postmeddelandet eller inte.</span><span class="sxs-lookup"><span data-stu-id="9e337-132">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="9e337-133">**Inkludera klient organisationens specifika Portal länk** -lägger till en länk med klient organisationens ID för att tillåta åtkomst till en viss klient organisation.</span><span class="sxs-lookup"><span data-stu-id="9e337-133">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![Fönstret medd. inställningar för notifs e-post](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="9e337-135">Välj **Nästa** för att gå till avsnittet **mottagare** .</span><span class="sxs-lookup"><span data-stu-id="9e337-135">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="9e337-136">Här kan du ange e-postadresser som får e-postaviseringar om incidenten.</span><span class="sxs-lookup"><span data-stu-id="9e337-136">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="9e337-137">Välj **Lägg till en mottagare** efter varje e-postadress.</span><span class="sxs-lookup"><span data-stu-id="9e337-137">Select **Add a recipient** after typing every email address.</span></span>

    ![Fönstret Lägg till mottagare för e-notifs](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="9e337-139">Välj **sedan nästa** för att gå till **gransknings regel** så att du kan se alla inställningar som är associerade med den nya regeln.</span><span class="sxs-lookup"><span data-stu-id="9e337-139">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="9e337-140">Mottagarna kommer att få eventuella problem meddelanden via e-post baserat på inställningarna.</span><span class="sxs-lookup"><span data-stu-id="9e337-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e337-141">Se även</span><span class="sxs-lookup"><span data-stu-id="9e337-141">See also</span></span>
- [<span data-ttu-id="9e337-142">Incidenter översikt i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e337-142">Incidents overview in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [<span data-ttu-id="9e337-143">Prioritera incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e337-143">Prioritize incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [<span data-ttu-id="9e337-144">Undersök incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e337-144">Investigate incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

