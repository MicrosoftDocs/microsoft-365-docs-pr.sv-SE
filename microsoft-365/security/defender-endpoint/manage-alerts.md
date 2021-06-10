---
title: Hantera Microsoft Defender för slutpunktsaviseringar
description: Ändra status för aviseringar, skapa regler för att dölja aviseringar, skicka kommentarer och granska ändringshistorik för enskilda aviseringar med hjälp av menyn Hantera avisering.
keywords: hantera aviseringar, hantera, aviseringar, status, ny, pågående, löst, lösa aviseringar, dölja, stänga av, regler, sammanhang, historik, kommentarer, ändringar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f03c2209b369e6fb9e001452c53073daeb5fe1c6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187007"
---
# <a name="manage-microsoft-defender-for-endpoint-alerts"></a><span data-ttu-id="3f3cd-104">Hantera Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="3f3cd-104">Manage Microsoft Defender for Endpoint alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3f3cd-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3f3cd-105">**Applies to:**</span></span>
- [<span data-ttu-id="3f3cd-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="3f3cd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3f3cd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3f3cd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="3f3cd-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="3f3cd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3f3cd-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="3f3cd-110">Defender för Endpoint meddelar dig om möjliga skadliga händelser, attribut och sammanhangsberoende information via aviseringar.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-110">Defender for Endpoint notifies you of possible malicious events, attributes, and contextual information through alerts.</span></span> <span data-ttu-id="3f3cd-111">En sammanfattning av nya aviseringar visas i instrumentpanelen **för säkerhetsåtgärder,** och du kan komma åt alla aviseringar i **kön Aviseringar.**</span><span class="sxs-lookup"><span data-stu-id="3f3cd-111">A summary of new alerts is displayed in the **Security operations dashboard**, and you can access all alerts in the **Alerts queue**.</span></span>

<span data-ttu-id="3f3cd-112">Du kan hantera aviseringar genom att välja en avisering **i kön** Aviseringar eller **fliken** Aviseringar på sidan Enhet för en enskild enhet.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-112">You can manage alerts by selecting an alert in the **Alerts queue**, or the **Alerts** tab of the Device page for an individual device.</span></span>

<span data-ttu-id="3f3cd-113">Om du väljer en avisering på någon av dessa platser visas **fönstret Aviseringshantering**.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-113">Selecting an alert in either of those places brings up the **Alert management pane**.</span></span>

![Bild på fönstret för aviseringshantering och aviseringskön](images/atp-alerts-selected.png)

## <a name="link-to-another-incident"></a><span data-ttu-id="3f3cd-115">Länka till ett annat incident</span><span class="sxs-lookup"><span data-stu-id="3f3cd-115">Link to another incident</span></span>
<span data-ttu-id="3f3cd-116">Du kan skapa en ny händelse utifrån aviseringen eller länka till en befintlig händelse.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-116">You can create a new incident from the alert or link to an existing incident.</span></span> 

## <a name="assign-alerts"></a><span data-ttu-id="3f3cd-117">Tilldela aviseringar</span><span class="sxs-lookup"><span data-stu-id="3f3cd-117">Assign alerts</span></span>
<span data-ttu-id="3f3cd-118">Om en avisering ännu inte har tilldelats kan du välja **Tilldela till mig och** tilldela aviseringen till dig själv.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-118">If an alert is not yet assigned, you can select **Assign to me** to assign the alert to yourself.</span></span>


## <a name="suppress-alerts"></a><span data-ttu-id="3f3cd-119">Utelämna aviseringar</span><span class="sxs-lookup"><span data-stu-id="3f3cd-119">Suppress alerts</span></span>
<span data-ttu-id="3f3cd-120">Det kan finnas scenarier där du behöver hindra aviseringar från att visas i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-120">There might be scenarios where you need to suppress alerts from appearing in Microsoft Defender Security Center.</span></span> <span data-ttu-id="3f3cd-121">Med Defender för slutpunkt kan du skapa regler för särskilda varningar som är kända för att vara obesvarade, till exempel kända verktyg och processer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-121">Defender for Endpoint lets you create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span>

<span data-ttu-id="3f3cd-122">Regler som måste skapas utifrån en befintlig avisering.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-122">Suppression rules can be created from an existing alert.</span></span> <span data-ttu-id="3f3cd-123">De kan inaktiveras och återaktiveras om det behövs.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-123">They can be disabled and reenabled if needed.</span></span>

<span data-ttu-id="3f3cd-124">När en regel för regel skapas börjar den gälla från och med då regeln skapas.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-124">When a suppression rule is created, it will take effect from the point when the rule is created.</span></span> <span data-ttu-id="3f3cd-125">Regeln påverkar inte befintliga aviseringar som redan finns i kön, innan regeln skapas.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-125">The rule will not affect existing alerts already in the queue, prior to the rule creation.</span></span> <span data-ttu-id="3f3cd-126">Regeln kommer bara att tillämpas på aviseringar som uppfyller villkoren efter att regeln har skapats.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-126">The rule will only be applied on alerts that satisfy the conditions set after the rule is created.</span></span>

<span data-ttu-id="3f3cd-127">Det finns två sammanhang för en regel för kontext som du kan välja bland:</span><span class="sxs-lookup"><span data-stu-id="3f3cd-127">There are two contexts for a suppression rule that you can choose from:</span></span>

- <span data-ttu-id="3f3cd-128">**Varna inte på den här enheten**</span><span class="sxs-lookup"><span data-stu-id="3f3cd-128">**Suppress alert on this device**</span></span>
- <span data-ttu-id="3f3cd-129">**Hindra aviseringar i min organisation**</span><span class="sxs-lookup"><span data-stu-id="3f3cd-129">**Suppress alert in my organization**</span></span>

<span data-ttu-id="3f3cd-130">Med kontexten för regeln kan du anpassa vad som visas i portalen och se till att bara faktiska säkerhetsvarningar visas i portalen.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-130">The context of the rule lets you tailor what gets surfaced into the portal and ensure that only real security alerts are surfaced into the portal.</span></span>

<span data-ttu-id="3f3cd-131">Du kan använda exemplen i följande tabell för att hjälpa dig att välja kontext för en regel:</span><span class="sxs-lookup"><span data-stu-id="3f3cd-131">You can use the examples in the following table to help you choose the context for a suppression rule:</span></span>

| <span data-ttu-id="3f3cd-132">**Sammanhang**</span><span class="sxs-lookup"><span data-stu-id="3f3cd-132">**Context**</span></span>                           | <span data-ttu-id="3f3cd-133">**Definition**</span><span class="sxs-lookup"><span data-stu-id="3f3cd-133">**Definition**</span></span>                                                                                                                                              | <span data-ttu-id="3f3cd-134">**Exempelscenarier**</span><span class="sxs-lookup"><span data-stu-id="3f3cd-134">**Example scenarios**</span></span>                                                                                                                                                                                                  |
|:--------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="3f3cd-135">**Varna inte på den här enheten**</span><span class="sxs-lookup"><span data-stu-id="3f3cd-135">**Suppress alert on this device**</span></span>    | <span data-ttu-id="3f3cd-136">Aviseringar med samma aviseringsrubrik och endast på den specifika enheten ignoreras.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-136">Alerts with the same alert title and on that specific device only will be suppressed.</span></span> <br /><br /><span data-ttu-id="3f3cd-137">Alla andra aviseringar på enheten ignoreras inte.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-137">All other alerts on that device will not be suppressed.</span></span> | <ul><li><span data-ttu-id="3f3cd-138">En säkerhetsundersökning undersöker ett skadligt skript som har använts för att attacka andra enheter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-138">A security researcher is investigating a malicious script that has been used to attack other devices in your organization.</span></span></li><li><span data-ttu-id="3f3cd-139">En utvecklare skapar regelbundet PowerShell-skript åt sitt team.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-139">A developer regularly creates PowerShell scripts for their team.</span></span></li></ul> |
| <span data-ttu-id="3f3cd-140">**Hindra aviseringar i min organisation**</span><span class="sxs-lookup"><span data-stu-id="3f3cd-140">**Suppress alert in my organization**</span></span> | <span data-ttu-id="3f3cd-141">Aviseringar med samma aviseringstitel på alla enheter kommer att döljas.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-141">Alerts with the same alert title on any device will be suppressed.</span></span>                                                                                         | <ul><li><span data-ttu-id="3f3cd-142">Administrativa administratörsverktyg används av alla i organisationen.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-142">A benign administrative tool is used by everyone in your organization.</span></span></li></ul>                                                                                                                               |

### <a name="suppress-an-alert-and-create-a-new-suppression-rule"></a><span data-ttu-id="3f3cd-143">Ignorera en avisering och skapa en ny regel för att ignorera regeln:</span><span class="sxs-lookup"><span data-stu-id="3f3cd-143">Suppress an alert and create a new suppression rule:</span></span>
<span data-ttu-id="3f3cd-144">Skapa anpassade regler för att styra när aviseringar utelämnas eller matchas.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-144">Create custom rules to control when alerts are suppressed, or resolved.</span></span> <span data-ttu-id="3f3cd-145">Du kan styra kontexten för när en avisering utelämnas genom att ange aviseringsrubrik, Indikatorn på kompromettering och villkoren.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-145">You can control the context for when an alert is suppressed by specifying the alert title, Indicator of compromise, and the conditions.</span></span> <span data-ttu-id="3f3cd-146">När du har specificerat kontexten kan du konfigurera åtgärden och omfattningen för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-146">After specifying the context, you’ll be able to configure the action and scope on the alert.</span></span> 

1. <span data-ttu-id="3f3cd-147">Välj den avisering du vill dölja.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-147">Select the alert you'd like to suppress.</span></span> <span data-ttu-id="3f3cd-148">Detta visar fönstret **Aviseringshantering.**</span><span class="sxs-lookup"><span data-stu-id="3f3cd-148">This brings up the **Alert management** pane.</span></span>

2.  <span data-ttu-id="3f3cd-149">Välj **Skapa en regel för regel**.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-149">Select **Create a suppression rule**.</span></span>

    <span data-ttu-id="3f3cd-150">Du kan skapa ett sådana villkor med hjälp av de här attributen.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-150">You can create a suppression condition using these attributes.</span></span> <span data-ttu-id="3f3cd-151">En OCH-operator tillämpas mellan varje villkor, så att fall endast inträffar om alla villkor uppfylls.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-151">An AND operator is applied between each condition, so suppression occurs only if all conditions are met.</span></span>
    
    * <span data-ttu-id="3f3cd-152">Fil-SHA1</span><span class="sxs-lookup"><span data-stu-id="3f3cd-152">File SHA1</span></span>
    * <span data-ttu-id="3f3cd-153">Filnamn – jokertecken stöds</span><span class="sxs-lookup"><span data-stu-id="3f3cd-153">File name - wildcard supported</span></span>
    * <span data-ttu-id="3f3cd-154">Mappsökväg – jokertecken stöds</span><span class="sxs-lookup"><span data-stu-id="3f3cd-154">Folder path - wildcard supported</span></span>
    * <span data-ttu-id="3f3cd-155">IP-adress</span><span class="sxs-lookup"><span data-stu-id="3f3cd-155">IP address</span></span>
    * <span data-ttu-id="3f3cd-156">URL – jokertecken stöds</span><span class="sxs-lookup"><span data-stu-id="3f3cd-156">URL - wildcard supported</span></span>
    * <span data-ttu-id="3f3cd-157">Kommandorad – jokertecken som stöds</span><span class="sxs-lookup"><span data-stu-id="3f3cd-157">Command line - wildcard supported</span></span>

3. <span data-ttu-id="3f3cd-158">Välj **utlösande IOC.**</span><span class="sxs-lookup"><span data-stu-id="3f3cd-158">Select the **Triggering IOC**.</span></span>
    
4. <span data-ttu-id="3f3cd-159">Ange åtgärden och omfattningen för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-159">Specify the action and scope on the alert.</span></span> <br>
   <span data-ttu-id="3f3cd-160">Du kan automatiskt lösa en avisering eller dölja den från portalen.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-160">You can automatically resolve an alert or hide it from the portal.</span></span> <span data-ttu-id="3f3cd-161">Aviseringar som matchas automatiskt visas i den lösta delen av aviseringskön, aviseringssidan och enhetens tidslinje och visas som lösta i Defender för slutpunkts-API:er.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-161">Alerts that are automatically resolved will appear in the resolved section of the alerts queue, alert page, and device timeline and will appear as resolved across Defender for Endpoint APIs.</span></span> <br><br> <span data-ttu-id="3f3cd-162">Aviseringar som markeras som dolda döljs från hela systemet, både på enhetens associerade aviseringar och från instrumentpanelen och strömmas inte över Defender för slutpunkts-API:er.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-162">Alerts that are marked as hidden will be suppressed from the entire system, both on the device's associated alerts and from the dashboard and will not be streamed across Defender for Endpoint APIs.</span></span>


5. <span data-ttu-id="3f3cd-163">Ange ett regelnamn och en kommentar.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-163">Enter a rule name and a comment.</span></span>

6. <span data-ttu-id="3f3cd-164">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-164">Click **Save**.</span></span>

#### <a name="view-the-list-of-suppression-rules"></a><span data-ttu-id="3f3cd-165">Visa listan över regler för regler</span><span class="sxs-lookup"><span data-stu-id="3f3cd-165">View the list of suppression rules</span></span>

1. <span data-ttu-id="3f3cd-166">I navigeringsfönstret väljer du **Inställningar**  >  **aviseringsvarning**.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-166">In the navigation pane, select **Settings** > **Alert suppression**.</span></span>

2. <span data-ttu-id="3f3cd-167">Listan med regelregler visar alla regler som användare i organisationen har skapat.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-167">The list of suppression rules shows all the rules that users in your organization have created.</span></span>

<span data-ttu-id="3f3cd-168">Mer information om hur du hanterar regelsamlingsregler finns i [Hantera regelhantering](manage-suppression-rules.md)</span><span class="sxs-lookup"><span data-stu-id="3f3cd-168">For more information on managing suppression rules, see [Manage suppression rules](manage-suppression-rules.md)</span></span>

## <a name="change-the-status-of-an-alert"></a><span data-ttu-id="3f3cd-169">Ändra status för en avisering</span><span class="sxs-lookup"><span data-stu-id="3f3cd-169">Change the status of an alert</span></span>

<span data-ttu-id="3f3cd-170">Du kan kategorisera aviseringar (som **Ny,** **Pågår** eller **Löst**) genom att ändra deras status allt eftersom din undersökning fortskrider.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-170">You can categorize alerts (as **New**, **In Progress**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="3f3cd-171">På så sätt kan du organisera och hantera hur din grupp kan svara på aviseringar.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-171">This helps you organize and manage how your team can respond to alerts.</span></span>

<span data-ttu-id="3f3cd-172">En gruppledare kan till exempel granska alla **nya** aviseringar och välja att tilldela dem till kön **Pågår** för ytterligare analys.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-172">For example, a team leader can review all **New** alerts, and decide to assign them to the **In Progress** queue for further analysis.</span></span>

<span data-ttu-id="3f3cd-173">Gruppledaren kan också tilldela aviseringen  till kön Löst om de vet att aviseringen är från en enhet som är irrelevant (till exempel en som tillhör en säkerhetsadministratör) eller tas itu med via en tidigare avisering.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-173">Alternatively, the team leader might assign the alert to the **Resolved** queue if they know the alert is benign, coming from a device that is irrelevant (such as one belonging to a security administrator), or is being dealt with through an earlier alert.</span></span>



## <a name="alert-classification"></a><span data-ttu-id="3f3cd-174">Aviseringsklassificering</span><span class="sxs-lookup"><span data-stu-id="3f3cd-174">Alert classification</span></span>
<span data-ttu-id="3f3cd-175">Du kan välja att inte ange en klassificering eller om en avisering är en verklig avisering eller en falsk avisering.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-175">You can choose not to set a classification, or specify whether an alert is a true alert or a false alert.</span></span> <span data-ttu-id="3f3cd-176">Det är viktigt att ange klassificeringen sant positiv/falsk positiv.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-176">It's important to provide the classification of true positive/false positive.</span></span> <span data-ttu-id="3f3cd-177">Den här klassificeringen används för att övervaka aviseringskvaliteten och göra aviseringarna mer exakta.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-177">This classification is used to monitor alert quality, and make alerts more accurate.</span></span> <span data-ttu-id="3f3cd-178">Fältet "determination" definierar ytterligare återgivning för en "sant positiv" klassificering.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-178">The "determination" field defines additional fidelity for a "true positive" classification.</span></span> 

## <a name="add-comments-and-view-the-history-of-an-alert"></a><span data-ttu-id="3f3cd-179">Lägga till kommentarer och visa historiken för en avisering</span><span class="sxs-lookup"><span data-stu-id="3f3cd-179">Add comments and view the history of an alert</span></span>
<span data-ttu-id="3f3cd-180">Du kan lägga till kommentarer och visa historiska händelser om en avisering om du vill se tidigare ändringar i aviseringen.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-180">You can add comments and view historical events about an alert to see previous changes made to the alert.</span></span>

<span data-ttu-id="3f3cd-181">När en ändring eller kommentar görs i en avisering registreras den i **avsnittet Kommentarer och historik.**</span><span class="sxs-lookup"><span data-stu-id="3f3cd-181">Whenever a change or comment is made to an alert, it is recorded in the **Comments and history** section.</span></span>

<span data-ttu-id="3f3cd-182">Tillagda kommentarer visas direkt i fönstret.</span><span class="sxs-lookup"><span data-stu-id="3f3cd-182">Added comments instantly appear on the pane.</span></span>


## <a name="related-topics"></a><span data-ttu-id="3f3cd-183">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="3f3cd-183">Related topics</span></span>
- [<span data-ttu-id="3f3cd-184">Hantera undertryckande regler</span><span class="sxs-lookup"><span data-stu-id="3f3cd-184">Manage suppression rules</span></span>](manage-suppression-rules.md)
- [<span data-ttu-id="3f3cd-185">Visa och ordna kön Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="3f3cd-185">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="3f3cd-186">Undersöka Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="3f3cd-186">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="3f3cd-187">Undersöka en fil som är kopplad till en Microsoft Defender för slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="3f3cd-187">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="3f3cd-188">Undersöka enheter i listan Microsoft Defender för slutpunktsenheter</span><span class="sxs-lookup"><span data-stu-id="3f3cd-188">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="3f3cd-189">Undersöka en IP-adress som är kopplad till en Microsoft Defender för Slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="3f3cd-189">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="3f3cd-190">Undersöka en domän som är kopplad till en Microsoft Defender för slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="3f3cd-190">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="3f3cd-191">Undersöka ett användarkonto i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="3f3cd-191">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
