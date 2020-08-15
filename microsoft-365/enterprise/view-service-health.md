---
title: Så här kontrollerar du Microsoft 365-tjänstens hälsa
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_ServiceHealthModern
- O365M_ServiceHealthModern
- O365E_ViewStatusServices
- O365E_ServiceHealthModern
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
- IWA160
ms.assetid: 932ad3ad-533c-418a-b938-6e44e8bc33b0
description: Se hälso statusen för Microsoft 365-tjänsterna innan du ringer support för att se om det finns ett aktivt tjänst avbrott.
ms.openlocfilehash: 49f7d3afd3c19cd4e9b6486db580082fe933b997
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694845"
---
# <a name="how-to-check-microsoft-365-service-health"></a><span data-ttu-id="02066-103">Så här kontrollerar du Microsoft 365-tjänstens hälsa</span><span class="sxs-lookup"><span data-stu-id="02066-103">How to check Microsoft 365 service health</span></span>

<span data-ttu-id="02066-104">[![Etikett som gör att du kan se att administrationscentret ändras och mer information finns på aka.ms/aboutM365preview.](../media/O365-Admin-AdminCenterChanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="02066-104">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/O365-Admin-AdminCenterChanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview?view=o365-worldwide)</span></span>

<span data-ttu-id="02066-105">Du kan se tillståndet för dina Microsoft-tjänster, inklusive Office på webben, Yammer, Microsoft Dynamics CRM och moln tjänster för mobila enheter, på sidan **tjänstens hälsa** i [administrations centret för Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339).</span><span class="sxs-lookup"><span data-stu-id="02066-105">You can view the health of your Microsoft services, including Office on the web, Yammer, Microsoft Dynamics CRM, and mobile device management cloud services, on the **Service health** page in the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339).</span></span> <span data-ttu-id="02066-106">Om du har problem med en molnbaserad tjänst kan du kontrollera tjänstens hälsa för att ta reda på om det är ett känt problem där en lösning är på gång innan du ringer supporten eller ägnar tid åt felsökning.</span><span class="sxs-lookup"><span data-stu-id="02066-106">If you are experiencing problems with a cloud service, you can check the service health to determine whether this is a known issue with a resolution in progress before you call support or spend time troubleshooting.</span></span>

<span data-ttu-id="02066-107">Om det inte går att logga in på service portalen kan du använda [sidan tjänst status](https://status.office365.com) för att kontrol lera kända problem som hindrar dig från att logga in på din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="02066-107">If you are unable to sign in to the service portal, you can use the [service status page](https://status.office365.com) to check for known issues preventing you from logging into your tenant.</span></span>
  
### <a name="how-to-check-service-health"></a><span data-ttu-id="02066-108">Kontrollera tjänstens hälsa</span><span class="sxs-lookup"><span data-stu-id="02066-108">How to check service health</span></span>

1. <span data-ttu-id="02066-109">Gå till administrations centret för Microsoft 365 på [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) och logga in med ett administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="02066-109">Go to the Microsoft 365 admin center at [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339), and sign in with an admin account.</span></span>

    > [!NOTE]
    > <span data-ttu-id="02066-110">Personer som har tilldelats rollen som global administratör eller tjänstadministratör kan visa tjänstens hälsa.</span><span class="sxs-lookup"><span data-stu-id="02066-110">People who are assigned the global admin or service administrator role can view service health.</span></span> <span data-ttu-id="02066-111">För att tillåta Exchange-, SharePoint- och Skype för företag-administratörer att visa tjänstens hälsa, måste de också tilldelas tjänstadministratörsrollen.</span><span class="sxs-lookup"><span data-stu-id="02066-111">To allow Exchange, SharePoint, and Skype for Business admins to view service health, they must also be assigned the Service admin role.</span></span> <span data-ttu-id="02066-112">Mer information om roller som kan visa tjänstens hälsa finns i [om administratörs roller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide#roles-available-in-the-microsoft-365-admin-center).</span><span class="sxs-lookup"><span data-stu-id="02066-112">For more information about roles that can view service health, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide#roles-available-in-the-microsoft-365-admin-center).</span></span>
  
2. <span data-ttu-id="02066-113">Om du inte använder det nya administrations centret väljer du alternativet **testa det nya administrations centret** i det övre högra hörnet på **Start** sidan.</span><span class="sxs-lookup"><span data-stu-id="02066-113">If you are not using the new admin center, on the **Home** page, select the **Try the new admin center** toggle in the upper-right corner.</span></span>

3. <span data-ttu-id="02066-114">Om du vill visa tjänstens status går du till **hälso**tillstånd i administrations centret  >  **Service health**eller väljer **tjänstens hälso** kort på **Start instrument panelen**.</span><span class="sxs-lookup"><span data-stu-id="02066-114">To view service health, in the admin center, go to **Health** > **Service health**, or select the **Service health** card on the **Home dashboard**.</span></span> <span data-ttu-id="02066-115">Instrument panels kortet visar om det finns ett aktivt tjänst problem och länkar till sidan för detaljerad **tjänst kontroll** .</span><span class="sxs-lookup"><span data-stu-id="02066-115">The dashboard card indicates whether there is an active service issue and links to the detailed **Service health** page.</span></span>
  
4. <span data-ttu-id="02066-116">På sidan **tjänstens hälsa** visas hälso statusen för varje moln tjänst i ett tabell format.</span><span class="sxs-lookup"><span data-stu-id="02066-116">On the **Service health** page, the health state of each cloud service is shown in a table format.</span></span>

   ![View of current issues in service health](../media/service-health-all-services.png)

<span data-ttu-id="02066-118">Fliken **alla tjänster** (standardvyn) visar alla tjänster och deras aktuella hälso status.</span><span class="sxs-lookup"><span data-stu-id="02066-118">The **All services** tab (the default view) shows all services and their current health state.</span></span> <span data-ttu-id="02066-119">En ikon och kolumnen **status** visar statusen för varje tjänst.</span><span class="sxs-lookup"><span data-stu-id="02066-119">An icon and the **Status** column indicate the state of each service.</span></span> 

<span data-ttu-id="02066-120">Om du vill filtrera vyn till tjänster som för närvarande har en olycka väljer du fliken **tillbud** högst upp på sidan.</span><span class="sxs-lookup"><span data-stu-id="02066-120">To filter your view to services currently experiencing an incident, select the **Incidents** tab at the top of the page.</span></span> <span data-ttu-id="02066-121">Om du väljer fliken **rådgivare** visas bara tjänster som redan har ett råd.</span><span class="sxs-lookup"><span data-stu-id="02066-121">Selecting the **Advisories** tab will show only services that currently have an advisory posted.</span></span> 

<span data-ttu-id="02066-122">På fliken **Historik** visas historiken över de incidenter och rådgivare som har åtgärd ATS.</span><span class="sxs-lookup"><span data-stu-id="02066-122">The **History** tab shows the history of incidents and advisories that have been resolved.</span></span>

<span data-ttu-id="02066-123">Om du upplever ett problem med en Microsoft 365-tjänst och inte ser den på sidan **tjänstens hälsa** kan du berätta om den genom att välja **rapportera ett problem**och fylla i den korta formen.</span><span class="sxs-lookup"><span data-stu-id="02066-123">If you're experiencing an issue with a Microsoft 365 service and you don’t see it listed on the **Service health** page, tell us about it by selecting **Report an issue**, and completing the short form.</span></span> <span data-ttu-id="02066-124">Vi kommer att titta på relaterade data och rapporter från andra organisationer för att se hur omfattande problemet är, och om det kom från vår tjänst.</span><span class="sxs-lookup"><span data-stu-id="02066-124">We’ll look at related data and reports from other organizations to see how widespread the issue is, and if it originated with our service.</span></span> <span data-ttu-id="02066-125">Om så är fallet lägger vi till det som ett nytt tillbud eller råd på sidan **tjänstens hälsa** , där du kan spåra dess upplösning.</span><span class="sxs-lookup"><span data-stu-id="02066-125">If it did, we’ll add it as a new incident or advisory on the **Service health** page, where you can track its resolution.</span></span> <span data-ttu-id="02066-126">Om det inte visas i listan i cirka 30 minuter bör du kontakta supporten för att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="02066-126">If you don’t see it appear on the list within about 30 minutes, consider contacting support to resolve the issue.</span></span>

<span data-ttu-id="02066-127">För att registrera dig för e-postaviseringar om nya incidenter som påverkar klient organisationens och status ändringar för en aktiv incident väljer du **Inställningar**, klicka på **Skicka Heath meddelanden via e-post**och ange sedan:</span><span class="sxs-lookup"><span data-stu-id="02066-127">To sign up for email notifications of new incidents that affect your tenant and status changes for an active incident, select **Preferences**, click **Send me service heath notifications in email**, and then specify:</span></span>

- <span data-ttu-id="02066-128">Upp till två e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="02066-128">Up to two email addresses.</span></span>
- <span data-ttu-id="02066-129">Om du vill få aviseringar eller rådgivare</span><span class="sxs-lookup"><span data-stu-id="02066-129">Whether you want notifications for incidents or advisories</span></span>
- <span data-ttu-id="02066-130">Tjänster som du vill meddela</span><span class="sxs-lookup"><span data-stu-id="02066-130">The services for which you want notification</span></span>

> [!NOTE]
> <span data-ttu-id="02066-131">Varje administratör kan ha sina inställningar inställda och ovanstående gräns för två e-postadresser är per administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="02066-131">Each admin can have their Preferences set and the above limit of two email address is per admin account.</span></span>

> [!TIP]
> <span data-ttu-id="02066-132">Du kan också använda [Microsoft 365 admin-appen](https://go.microsoft.com/fwlink/p/?linkid=627216) på din mobila enhet för att Visa tjänstens hälsa, vilket är ett bra sätt att fortsätta med push-meddelanden.</span><span class="sxs-lookup"><span data-stu-id="02066-132">You can also use the [Microsoft 365 Admin app](https://go.microsoft.com/fwlink/p/?linkid=627216) on your mobile device to view Service health, which is a great way to stay current with push notifications.</span></span> 
  
### <a name="view-details-of-posted-service-health"></a><span data-ttu-id="02066-133">Visa information om publicerad tjänsthälsa</span><span class="sxs-lookup"><span data-stu-id="02066-133">View details of posted service health</span></span>

<span data-ttu-id="02066-134">I vyn **alla tjänster** visas en sammanfattningsvy över rådgivare eller händelser när du väljer tjänstens status.</span><span class="sxs-lookup"><span data-stu-id="02066-134">On the **All services** view, selecting the service status will open a summary view of advisories or incidents.</span></span>
  
![En skärm bild som visar tjänstens råd](../media/service-health-advisory.png)

<span data-ttu-id="02066-136">Sammanfattningen av rådgivningen eller incidenten innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="02066-136">The advisory or incident summary provides the following information:</span></span>

- <span data-ttu-id="02066-137">**Rubrik** – en sammanfattning av problemet.</span><span class="sxs-lookup"><span data-stu-id="02066-137">**Title** - A summary of the problem.</span></span>
- <span data-ttu-id="02066-138">**Tjänst** -namnet på den berörda tjänsten.</span><span class="sxs-lookup"><span data-stu-id="02066-138">**Service** - The name of the affected service.</span></span>
- <span data-ttu-id="02066-139">**ID** -ett numeriskt ID för problemet.</span><span class="sxs-lookup"><span data-stu-id="02066-139">**ID** - A numeric identifier for the problem.</span></span>
- <span data-ttu-id="02066-140">**Status** – hur problemet påverkar tjänsten.</span><span class="sxs-lookup"><span data-stu-id="02066-140">**Status** - How this problem affects the service.</span></span>
- <span data-ttu-id="02066-141">**Start tid** -tiden när problemet påbörjades.</span><span class="sxs-lookup"><span data-stu-id="02066-141">**Start time** - The time when the issue started.</span></span>
- <span data-ttu-id="02066-142">**Uppdaterades senast** – den senaste gången tjänstens hälso meddelande uppdaterades.</span><span class="sxs-lookup"><span data-stu-id="02066-142">**Last updated** - The last time that the service health message was updated.</span></span> <span data-ttu-id="02066-143">Vi skickar vanliga meddelanden för att informera dig om att vi håller på att genomföra en lösning.</span><span class="sxs-lookup"><span data-stu-id="02066-143">We post frequent messages to let you know the progress that we're making in applying a solution.</span></span>

<span data-ttu-id="02066-144">Välj ärendets rubrik om du vill visa ärende detalj sidan som visar mer information om problemet, inklusive [historiken](#history) för alla meddelanden som publicerats medan vi arbetar med en lösning.</span><span class="sxs-lookup"><span data-stu-id="02066-144">Select the issue title to see the issue detail page, which shows more information about the issue, including the [history](#history) of all messages posted while we work on a solution.</span></span>

![En skärm bild som visar problem information](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a><span data-ttu-id="02066-146">Översätta information om tjänstens hälsa</span><span class="sxs-lookup"><span data-stu-id="02066-146">Translate service health details</span></span>

<span data-ttu-id="02066-p108">Eftersom förklaringar om tjänstens hälsa publiceras i realtid översätts de inte automatiskt till ditt språk, och information om en tjänsthändelse finns endast på engelska. Följ de här stegen om du vill översätta en förklaring:</span><span class="sxs-lookup"><span data-stu-id="02066-p108">Because service health explanations are posted in real-time, they are not automatically translated to your language and the details of a service event are in English only. To translate the explanation, follow these steps:</span></span>
  
1. <span data-ttu-id="02066-149">Gå till [Translator](https://www.bing.com/translator/).</span><span class="sxs-lookup"><span data-stu-id="02066-149">Go to [Translator](https://www.bing.com/translator/).</span></span>

2. <span data-ttu-id="02066-p109">På sidan **Tjänstens hälsa** väljer du en händelse eller rådgivning. Kopiera texten om problemet under **Visa information**.</span><span class="sxs-lookup"><span data-stu-id="02066-p109">On the **Service health** page, select an incident or advisory. Under **Show details**, copy the text about the issue.</span></span>

3. <span data-ttu-id="02066-152">Klistra in texten i Translator och välj **Översätt**.</span><span class="sxs-lookup"><span data-stu-id="02066-152">In Translator, paste the text and choose **Translate**.</span></span>

### <a name="definitions"></a><span data-ttu-id="02066-153">Definitioner</span><span class="sxs-lookup"><span data-stu-id="02066-153">Definitions</span></span>

<span data-ttu-id="02066-154">I de flesta avseenden kommer tjänsterna att visas som friska med ingen mer information.</span><span class="sxs-lookup"><span data-stu-id="02066-154">Most of the time, services will appear as healthy with no further information.</span></span> <span data-ttu-id="02066-155">Om ett problem inträffar i tjänsten identifieras problemet som rådgivning eller incident och aktuell status visas.</span><span class="sxs-lookup"><span data-stu-id="02066-155">When a service is having a problem, the issue is identified as either an advisory or an incident and shows a current status.</span></span>
  
> [!TIP]
> <span data-ttu-id="02066-156">Planerade underhållshändelser visas inte i tjänstens hälsa.</span><span class="sxs-lookup"><span data-stu-id="02066-156">Planned maintenance events aren't shown in service health.</span></span> <span data-ttu-id="02066-157">Du kan spåra planerade underhållshändelser genom att hålla dig uppdaterad i **Meddelandecenter**.</span><span class="sxs-lookup"><span data-stu-id="02066-157">You can track planned maintenance events by staying up to date with the **Message center**.</span></span> <span data-ttu-id="02066-158">Filtrera på meddelanden som kategoriserats som Planera för ändring för att ta reda på när ändringen ska ske, dess påverkan och vilka förberedelser som bör vidtas.</span><span class="sxs-lookup"><span data-stu-id="02066-158">Filter to messages categorized as Plan for change to find out when the change is going to happen, its effect, and how to prepare for it.</span></span> <span data-ttu-id="02066-159">Se [meddelande Center i Microsoft 365](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) för mer information.</span><span class="sxs-lookup"><span data-stu-id="02066-159">See [Message center in Microsoft 365](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) for more details.</span></span>
  
### <a name="incidents-and-advisories"></a><span data-ttu-id="02066-160">Incidenter och rådgivning</span><span class="sxs-lookup"><span data-stu-id="02066-160">Incidents and advisories</span></span>

| <span data-ttu-id="02066-161">Ikonen</span><span class="sxs-lookup"><span data-stu-id="02066-161">Icon</span></span> | <span data-ttu-id="02066-162">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="02066-162">Description</span></span> |
|:-----|:-----|
|![Information icon for advisory](../media/a7f5fd21-c760-4948-9bc1-50f7c8070e28.png)|<span data-ttu-id="02066-p112">Om ikonen för rådgivning visas för en tjänst betyder det att vi är medvetna om att ett problem påverkar vissa användare, men att tjänsten fortfarande är tillgänglig. Rådgivning innebär att det ofta finns en lösning på problemet, och problemet kan vara tillfälligt eller är begränsat i omfattning och påverkan på användare.</span><span class="sxs-lookup"><span data-stu-id="02066-p112">If a service has an advisory shown, we are aware of a problem that is affecting some users, but the service is still available. In an advisory, there is often a workaround to the problem and the problem may be intermittent or is limited in scope and user impact.</span></span>  <br/> |
|![Exclamation point icon for incident](../media/a636db57-6083-44dc-bbd5-556850804f17.png)|<span data-ttu-id="02066-p113">Om en aktiv incident visas för tjänsten är det ett kritiskt problem, vilket innebär att tjänsten eller en viktig funktion i tjänsten inte är tillgänglig. Användare kanske inte kan skicka och ta emot e-post eller inte kan logga in. Händelser har betydande påverkan på användarna. Om en händelse pågår tillhandahåller vi uppdateringar om undersökningen, åtgärder och bekräftar lösningen på hälsoinstrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="02066-p113">If a service has an active incident shown, it's a critical issue and the service or a major function of the service is unavailable. For example, users may be unable to send and receive email or unable to sign-in. Incidents will have noticeable impact to users. When there is an incident in progress, we will provide updates regarding the investigation, mitigation efforts, and confirmation of resolution in the Service health dashboard.</span></span>  <br/> |

### <a name="status-definitions"></a><span data-ttu-id="02066-171">Statusdefinitioner</span><span class="sxs-lookup"><span data-stu-id="02066-171">Status definitions</span></span>

| <span data-ttu-id="02066-172">Status</span><span class="sxs-lookup"><span data-stu-id="02066-172">Status</span></span> | <span data-ttu-id="02066-173">Definition</span><span class="sxs-lookup"><span data-stu-id="02066-173">Definition</span></span> |
|:-----|:-----|
|<span data-ttu-id="02066-174">**Undersöker**</span><span class="sxs-lookup"><span data-stu-id="02066-174">**Investigating**</span></span> | <span data-ttu-id="02066-175">Vi är medvetna om ett potentiellt problem och samlar mer information om vad som händer och dess påverkan.</span><span class="sxs-lookup"><span data-stu-id="02066-175">We're aware of a potential issue and are gathering more information about what's going on and the scope of impact.</span></span> |
|<span data-ttu-id="02066-176">**Tjänsteförsämring**</span><span class="sxs-lookup"><span data-stu-id="02066-176">**Service degradation**</span></span> | <span data-ttu-id="02066-p114">Vi har bekräftat att det finns ett problem som kan påverka användningen av en tjänst eller funktion. Den här statusen kan visas om till exempel en tjänst fungerar långsammare än vanligt, det sker oregelbundna avbrott eller om en funktion inte fungerar.</span><span class="sxs-lookup"><span data-stu-id="02066-p114">We've confirmed that there is an issue that may affect use of a service or feature. You might see this status if a service is performing more slowly than usual, there are intermittent interruptions, or if a feature isn't working, for example.</span></span> |
|<span data-ttu-id="02066-179">**Tjänsteavbrott**</span><span class="sxs-lookup"><span data-stu-id="02066-179">**Service interruption**</span></span> | <span data-ttu-id="02066-p115">Denna status visas om vi anser att ett problem påverkar möjligheten för användarna att använda tjänsten. I det här fallet är problemet betydande och kan upprepas konsekvent.</span><span class="sxs-lookup"><span data-stu-id="02066-p115">You'll see this status if we determine that an issue affects the ability for users to access the service. In this case, the issue is significant and can be reproduced consistently.</span></span> |
|<span data-ttu-id="02066-182">**Återställer tjänsten**</span><span class="sxs-lookup"><span data-stu-id="02066-182">**Restoring service**</span></span> | <span data-ttu-id="02066-183">Orsaken till problemet har hittats, vi vet vilka korrigerande åtgärder som ska göras och arbetar med att få tillbaka tjänsten i ett felfritt tillstånd.</span><span class="sxs-lookup"><span data-stu-id="02066-183">The cause of the issue has been identified, we know what corrective action to take, and are in the process of bringing the service back to a healthy state.</span></span> |
|<span data-ttu-id="02066-184">**Utökad återställning**</span><span class="sxs-lookup"><span data-stu-id="02066-184">**Extended recovery**</span></span> | <span data-ttu-id="02066-p116">Denna status anger att korrigerande åtgärder pågår för att återställa tjänsten för de flesta användare, men att det tar ett tag att nå alla berörda system. Du kan också få den här statusen om vi har gjort en tillfällig lösning för att minska påverkan medan vi jobbar på en permanent korrigering.</span><span class="sxs-lookup"><span data-stu-id="02066-p116">This status indicates that corrective action is in progress to restore service to most users but will take some time to reach all the affected systems. You might also see this status if we've made a temporary fix to reduce impact while we wait to apply a permanent fix.</span></span> |
|<span data-ttu-id="02066-187">**Undersökning uppskjuten**</span><span class="sxs-lookup"><span data-stu-id="02066-187">**Investigation suspended**</span></span> | <span data-ttu-id="02066-p117">Du ser den här statusen om vår detaljerade undersökning av ett potentiellt problem gör att vi måste begära ytterligare information från kunder för att kunna utvidga undersökningen. Om du behöver vidta några åtgärder meddelar vi dig vilka data eller loggar vi behöver.</span><span class="sxs-lookup"><span data-stu-id="02066-p117">If our detailed investigation of a potential issue results in a request for additional information from customers to allow us to investigate further, you'll see this status. If we need you to act, we'll let you know what data or logs we need.</span></span> |
|<span data-ttu-id="02066-190">**Tjänsten har återställts**</span><span class="sxs-lookup"><span data-stu-id="02066-190">**Service restored**</span></span> | <span data-ttu-id="02066-p118">Vi har bekräftat att korrigerande åtgärder har löst problemet och att tjänsten har återställts till ett felfritt läge. Om du vill ta reda på vad som var fel kan du visa information om problemet.</span><span class="sxs-lookup"><span data-stu-id="02066-p118">We've confirmed that corrective action has resolved the underlying problem and the service has been restored to a healthy state. To find out what went wrong, view the issue details.</span></span> |
|<span data-ttu-id="02066-193">**Falsk positiv**</span><span class="sxs-lookup"><span data-stu-id="02066-193">**False positive**</span></span> | <span data-ttu-id="02066-194">Efter en detaljerad undersökning har vi bekräftat att tjänsten är felfri och fungerar som den ska.</span><span class="sxs-lookup"><span data-stu-id="02066-194">After a detailed investigation, we’ve confirmed the service is healthy and operating as designed.</span></span> <span data-ttu-id="02066-195">Ingen inverkan på tjänsten observerades eller orsaken till att incidenten kom utanför tjänsten.</span><span class="sxs-lookup"><span data-stu-id="02066-195">No impact to the service was observed or the cause of the incident originated outside of the service.</span></span> |
|<span data-ttu-id="02066-196">**Rapport om efterhand efter tillbud**</span><span class="sxs-lookup"><span data-stu-id="02066-196">**Post-incident report published**</span></span> | <span data-ttu-id="02066-197">Vi har publicerat en rapport om att få ett specifikt problem som innehåller information om Rotors orsak och nästa steg för att säkerställa ett liknande problem.</span><span class="sxs-lookup"><span data-stu-id="02066-197">We’ve published a Post Incident Report for a specific issue that includes root cause information and next steps to ensure a similar issue doesn’t reoccur.</span></span> |

### <a name="history"></a><span data-ttu-id="02066-198">Historik</span><span class="sxs-lookup"><span data-stu-id="02066-198">History</span></span>

<span data-ttu-id="02066-199">Tjänstens tillstånd gör att du kan se aktuell hälso status och se historiken för alla tjänste rådgivare och händelser som påverkat din klient organisation under de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="02066-199">Service health lets you look at current health status and view the history of any service advisories and incidents that have affected your tenant in the past 30 days.</span></span> <span data-ttu-id="02066-200">Om du vill visa den senaste statusen för alla tjänster väljer du **Visa historik** på sidan ärende information.</span><span class="sxs-lookup"><span data-stu-id="02066-200">To view the past health of all services, select **View history** on the issue detail page.</span></span>
  
![Show link to health history](../media/service-health-view-history.png)
  
<span data-ttu-id="02066-202">En lista över alla meddelanden om tjänstens hälsa som publicerats inom den valda tidsramen visas enligt nedan:</span><span class="sxs-lookup"><span data-stu-id="02066-202">A list of all service health messages posted in the selected timeframe is displayed, as shown below:</span></span>
  
![View service health history](../media/service-health-history.png)
  
<span data-ttu-id="02066-204">Expandera en rad för att visa mer information om problemet.</span><span class="sxs-lookup"><span data-stu-id="02066-204">Expand any row to view more details about the issue.</span></span>
  
<span data-ttu-id="02066-205">För mer information om vårt engagemang för drift tid, se [transparenta åtgärder från Microsoft 365](https://go.microsoft.com/fwlink/?linkid=848695).</span><span class="sxs-lookup"><span data-stu-id="02066-205">For more information about our commitment to uptime, see [Transparent operations from Microsoft 365](https://go.microsoft.com/fwlink/?linkid=848695).</span></span>

## <a name="related-topics"></a><span data-ttu-id="02066-206">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="02066-206">Related topics</span></span>

<span data-ttu-id="02066-207">[Aktivitets rapporter i administrations centret](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 
 för Microsoft 365 [Inställningar för meddelande Center](https://docs.microsoft.com/microsoft-365/admin/manage/message-center?view=o365-worldwide#preferences11)</span><span class="sxs-lookup"><span data-stu-id="02066-207">[Activity Reports in the Microsoft 365 admin center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
[Message center Preferences](https://docs.microsoft.com/microsoft-365/admin/manage/message-center?view=o365-worldwide#preferences11)</span></span>
