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
ms.openlocfilehash: 3af1dcfec165c88a18cbc0d8cbf6866bb6398adc
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668363"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="a6a52-104">Få incident meddelanden via e-post</span><span class="sxs-lookup"><span data-stu-id="a6a52-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!IMPORTANT]
> <span data-ttu-id="a6a52-105">Funktionen e-postaviseringar för incidenter finns för närvarande i offentlig för hands version.</span><span class="sxs-lookup"><span data-stu-id="a6a52-105">The email notifications for incidents feature is currently in public preview.</span></span> <span data-ttu-id="a6a52-106">Viss information om den här funktionen kan komma att ändras innan du är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a6a52-106">Some information about this feature may change before commercial availability.</span></span> <span data-ttu-id="a6a52-107">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="a6a52-107">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="a6a52-108">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a6a52-108">**Applies to:**</span></span>
- <span data-ttu-id="a6a52-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6a52-109">Microsoft 365 Defender</span></span>

<span data-ttu-id="a6a52-110">Du kan ställa in Microsoft 365 Defender för att meddela dig via e-post varje gång det uppstår nya tillbud eller nya uppdateringar till befintliga incidenter.</span><span class="sxs-lookup"><span data-stu-id="a6a52-110">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="a6a52-111">Du kan välja att få aviseringar baserat på allvarlighets graden och per enhets grupp.</span><span class="sxs-lookup"><span data-stu-id="a6a52-111">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="a6a52-112">Du kan också välja att bara få ett meddelande vid den första uppdateringen per olycka.</span><span class="sxs-lookup"><span data-stu-id="a6a52-112">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="a6a52-113">Du kan lägga till eller ta bort mottagare i e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="a6a52-113">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="a6a52-114">Nya mottagare meddelas om incidenter när de har lagts till.</span><span class="sxs-lookup"><span data-stu-id="a6a52-114">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="a6a52-115">E-postmeddelandet innehåller viktig information om händelsen, till exempel namn, allvarlighets grad och kategorier, bland annat.</span><span class="sxs-lookup"><span data-stu-id="a6a52-115">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="a6a52-116">Du kan även gå direkt till incidenter så att du kan påbörja undersökningen omedelbart.</span><span class="sxs-lookup"><span data-stu-id="a6a52-116">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="a6a52-117">Mer information om hur du undersöker problem finns i [undersöka incidenter i Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span><span class="sxs-lookup"><span data-stu-id="a6a52-117">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span></span>

>[!NOTE]
><span data-ttu-id="a6a52-118">Du måste ha behörigheten Hantera säkerhets inställningar för att konfigurera inställningar för e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="a6a52-118">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="a6a52-119">Om du har valt att använda grundläggande behörighets hantering kan användare med rollen som säkerhets administratör eller global administratör konfigurera e-postaviseringar åt dig.</span><span class="sxs-lookup"><span data-stu-id="a6a52-119">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="a6a52-120">Om din organisation använder rollbaserad åtkomst kontroll (RBAC) kan du välja att bara skapa, redigera, ta bort och ta emot meddelanden baserat på de enhets grupper som du får hantera.</span><span class="sxs-lookup"><span data-stu-id="a6a52-120">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="a6a52-121">Skapa regler för problem meddelanden</span><span class="sxs-lookup"><span data-stu-id="a6a52-121">Create rules for incident notifications</span></span>

<span data-ttu-id="a6a52-122">Skapa en ny regel och anpassa inställningarna för e-postaviseringar om du vill ställa in ett första meddelande.</span><span class="sxs-lookup"><span data-stu-id="a6a52-122">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="a6a52-123">I navigerings fönstret väljer du **Inställningar** för  >  **incident epost meddelanden**.</span><span class="sxs-lookup"><span data-stu-id="a6a52-123">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="a6a52-124">Välj **Lägg till objekt**.</span><span class="sxs-lookup"><span data-stu-id="a6a52-124">Select **Add item**.</span></span>
3. <span data-ttu-id="a6a52-125">Ge regeln ett namn i **namn** och ange en **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="a6a52-125">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![Fönstret Skapa regel för e-notifs](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="a6a52-127">Välj **Nästa** för att gå till **aviserings inställningar**.</span><span class="sxs-lookup"><span data-stu-id="a6a52-127">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="a6a52-128">Här kan du ange:</span><span class="sxs-lookup"><span data-stu-id="a6a52-128">Here you can specify:</span></span>
    - <span data-ttu-id="a6a52-129">**Aviserings allvarlighets grad** – Välj aviseringens allvarlighets grad som kommer att utlösa en incident avisering.</span><span class="sxs-lookup"><span data-stu-id="a6a52-129">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="a6a52-130">Om du till exempel bara vill bli informerad om problem med hög allvarlighets grad väljer du High.</span><span class="sxs-lookup"><span data-stu-id="a6a52-130">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="a6a52-131">**Enhets gruppens omfattning** – den här List rutan visar alla enhets grupper som användaren kan komma åt.</span><span class="sxs-lookup"><span data-stu-id="a6a52-131">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="a6a52-132">Välj vilka enhets grupper som du vill skapa incident regler för.</span><span class="sxs-lookup"><span data-stu-id="a6a52-132">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="a6a52-133">**Meddela bara vid den första förekomsten per händelse** – om du väljer det här alternativet skickas ett e-postmeddelande endast för den första aviseringen som matchar dina andra val.</span><span class="sxs-lookup"><span data-stu-id="a6a52-133">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="a6a52-134">Senare uppdateringar eller larm som rör händelsen utlöser inte ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="a6a52-134">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="a6a52-135">**Inkludera organisationens namn** -visar om kund namnet visas i e-postmeddelandet eller inte.</span><span class="sxs-lookup"><span data-stu-id="a6a52-135">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="a6a52-136">**Inkludera klient organisationens specifika Portal länk** -lägger till en länk med klient organisationens ID för att tillåta åtkomst till en viss klient organisation.</span><span class="sxs-lookup"><span data-stu-id="a6a52-136">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![Fönstret medd. inställningar för notifs e-post](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="a6a52-138">Välj **Nästa** för att gå till avsnittet **mottagare** .</span><span class="sxs-lookup"><span data-stu-id="a6a52-138">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="a6a52-139">Här kan du ange e-postadresser som får e-postaviseringar om incidenten.</span><span class="sxs-lookup"><span data-stu-id="a6a52-139">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="a6a52-140">Välj **Lägg till en mottagare** efter varje e-postadress.</span><span class="sxs-lookup"><span data-stu-id="a6a52-140">Select **Add a recipient** after typing every email address.</span></span>

    ![Fönstret Lägg till mottagare för e-notifs](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="a6a52-142">Välj **sedan nästa** för att gå till **gransknings regel** så att du kan se alla inställningar som är associerade med den nya regeln.</span><span class="sxs-lookup"><span data-stu-id="a6a52-142">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="a6a52-143">Mottagarna kommer att få eventuella problem meddelanden via e-post baserat på inställningarna.</span><span class="sxs-lookup"><span data-stu-id="a6a52-143">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6a52-144">Se även</span><span class="sxs-lookup"><span data-stu-id="a6a52-144">See also</span></span>
- [<span data-ttu-id="a6a52-145">Incidenter översikt i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6a52-145">Incidents overview in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [<span data-ttu-id="a6a52-146">Prioritera incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6a52-146">Prioritize incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [<span data-ttu-id="a6a52-147">Undersök incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6a52-147">Investigate incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

