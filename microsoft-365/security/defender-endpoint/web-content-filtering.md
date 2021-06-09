---
title: Filtrering av webbinnehåll
description: Använd webbinnehållsfiltrering i Microsoft Defender för Endpoint för att spåra och reglera åtkomsten till webbplatser baserat på deras innehållskategorier.
keywords: webbskydd, skydd mot webbhot, surfning, övervakning, rapporter, kort, domänlista, säkerhet, nätfiske, skadlig kod, sårbarhet, webbplatser, nätverksskydd, Edge, Internet Explorer, Chrome, Firefox, webbläsare
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a16e3eb8f6f7eae9fbaa82c9fd978f4fef429818
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822328"
---
# <a name="web-content-filtering"></a><span data-ttu-id="5888f-104">Filtrering av webbinnehåll</span><span class="sxs-lookup"><span data-stu-id="5888f-104">Web content filtering</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5888f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="5888f-105">**Applies to:**</span></span>
- [<span data-ttu-id="5888f-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="5888f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5888f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5888f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="5888f-108">**Webbinnehållsfiltrering är för närvarande i offentlig förhandsversion**</span><span class="sxs-lookup"><span data-stu-id="5888f-108">**Web content filtering is currently in public preview**</span></span><br>
> <span data-ttu-id="5888f-109">Den här förhandsversionen tillhandahålls utan ett servicenivåavtal och rekommenderas inte för produktionsarbetsbelastningar.</span><span class="sxs-lookup"><span data-stu-id="5888f-109">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="5888f-110">Vissa funktioner kanske inte stöds eller kan ha begränsade funktioner.</span><span class="sxs-lookup"><span data-stu-id="5888f-110">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="5888f-111">Mer information finns i [Förhandsversionsfunktioner för Microsoft Defender för slutpunkt.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="5888f-111">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

> [!TIP]
> <span data-ttu-id="5888f-112">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="5888f-112">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5888f-113">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="5888f-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="5888f-114">Webbinnehållsfiltrering är [en del av webbskyddsfunktionerna](web-protection-overview.md) i Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5888f-114">Web content filtering is part of [Web protection](web-protection-overview.md) capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="5888f-115">Det gör att din organisation kan spåra och reglera åtkomsten till webbplatser baserat på deras innehållskategorier.</span><span class="sxs-lookup"><span data-stu-id="5888f-115">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="5888f-116">Många av dessa webbplatser, även om de inte är skadliga, kan vara problematiska på grund av regelefterlevnad, bandbreddsanvändning eller andra problem.</span><span class="sxs-lookup"><span data-stu-id="5888f-116">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

<span data-ttu-id="5888f-117">Konfigurera principer i din enhetsgrupper för att blockera vissa kategorier.</span><span class="sxs-lookup"><span data-stu-id="5888f-117">Configure policies across your device groups to block certain categories.</span></span> <span data-ttu-id="5888f-118">När en kategori blockeras förhindrar du att användare i angivna enhetsgrupper kommer åt URL-adresser som är kopplade till kategorin.</span><span class="sxs-lookup"><span data-stu-id="5888f-118">Blocking a category prevents users within specified device groups from accessing URLs associated with the category.</span></span> <span data-ttu-id="5888f-119">URL-adresser granskas automatiskt för alla kategorier som inte blockeras.</span><span class="sxs-lookup"><span data-stu-id="5888f-119">For any category that's not blocked, the URLs are automatically audited.</span></span> <span data-ttu-id="5888f-120">Användarna kan komma åt URL-adresser utan störningar och du samlar in åtkomststatistik för att skapa ett mer anpassat principbeslut.</span><span class="sxs-lookup"><span data-stu-id="5888f-120">Your users can access the URLs without disruption, and you'll gather access statistics to help create a more custom policy decision.</span></span> <span data-ttu-id="5888f-121">Användarna ser ett blockeringsmeddelande om ett element på sidan de visar är att ringa samtal till en blockerad resurs.</span><span class="sxs-lookup"><span data-stu-id="5888f-121">Your users will see a block notification if an element on the page they're viewing is making calls to a blocked resource.</span></span>

<span data-ttu-id="5888f-122">Webbinnehållsfiltrering är tillgängligt i de större webbläsarna, med block som utförs av Windows Defender SmartScreen (Microsoft Edge) och Nätverksskydd (Chrome, Firefox, Och Opera).</span><span class="sxs-lookup"><span data-stu-id="5888f-122">Web content filtering is available on the major web browsers, with blocks performed by Windows Defender SmartScreen (Microsoft Edge) and Network Protection (Chrome, Firefox, Brave and Opera).</span></span> <span data-ttu-id="5888f-123">Mer information om webbläsarstöd finns i avsnittet krav.</span><span class="sxs-lookup"><span data-stu-id="5888f-123">For more information about browser support, see the prerequisites section.</span></span>

<span data-ttu-id="5888f-124">Sammanfattning av fördelarna:</span><span class="sxs-lookup"><span data-stu-id="5888f-124">Summarizing the benefits:</span></span>

- <span data-ttu-id="5888f-125">Användare hindras från att komma åt webbplatser i blockerade kategorier, oavsett om de surfar lokalt eller inte</span><span class="sxs-lookup"><span data-stu-id="5888f-125">Users are prevented from accessing websites in blocked categories, whether they're browsing on-premises or away</span></span>
- <span data-ttu-id="5888f-126">Ditt säkerhetsteam kan enkelt distribuera principer till grupper av användare med hjälp av enhetsgrupper som definierats i Microsoft Defender för [slutpunktsrollbaserade inställningar för åtkomstkontroll](/microsoft-365/security/defender-endpoint/rbac)</span><span class="sxs-lookup"><span data-stu-id="5888f-126">Your security team can conveniently deploy policies to groups of users using device groups defined in [Microsoft Defender for Endpoint role-based access control settings](/microsoft-365/security/defender-endpoint/rbac)</span></span>
- <span data-ttu-id="5888f-127">Säkerhetsteamet kan komma åt webbrapporter på samma centrala plats, med synlighet över faktiska block och webbanvändning</span><span class="sxs-lookup"><span data-stu-id="5888f-127">Your security team can access web reports in the same central location, with visibility over actual blocks and web usage</span></span>

## <a name="user-experience"></a><span data-ttu-id="5888f-128">Användarupplevelse</span><span class="sxs-lookup"><span data-stu-id="5888f-128">User experience</span></span>

<span data-ttu-id="5888f-129">Blockeringen för webbläsare som stöds av tredje part tillhandahålls av Network Protection, som ger ett popup-meddelande på systemnivå om en blockerad anslutning för användaren.</span><span class="sxs-lookup"><span data-stu-id="5888f-129">The blocking experience for 3rd party supported browsers is provided by Network Protection, which provides a system-level toast notifying the user of a blocked connection.</span></span> <span data-ttu-id="5888f-130">Om du vill ha en mer användarvänlig upplevelse i webbläsaren kan du använda Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="5888f-130">For a more user-friendly, in-browser experience, consider using Microsoft Edge.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5888f-131">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="5888f-131">Prerequisites</span></span>

<span data-ttu-id="5888f-132">Innan du provar den här funktionen bör du kontrollera att du uppfyller följande krav:</span><span class="sxs-lookup"><span data-stu-id="5888f-132">Before trying out this feature, make sure you meet the following requirements:</span></span>

- <span data-ttu-id="5888f-133">Windows 10 Enterprise E5 Microsoft 365 E5, Microsoft 365 E5 Security, Microsoft 365 E3 + Microsoft 365 E5 Security eller Microsoft Defender för slutpunkten som är fristående licens.</span><span class="sxs-lookup"><span data-stu-id="5888f-133">Windows 10 Enterprise E5, Microsoft 365 E5, Microsoft 365 E5 Security, Microsoft 365 E3 + Microsoft 365 E5 Security add-on or the Microsoft Defender for Endpoint standalone license.</span></span> 
- <span data-ttu-id="5888f-134">Åtkomst till Microsoft Defender Säkerhetscenter portal ( https://securitycenter.windows.com) .</span><span class="sxs-lookup"><span data-stu-id="5888f-134">Access to Microsoft Defender Security Center portal (https://securitycenter.windows.com).</span></span>
- <span data-ttu-id="5888f-135">Enheter som Windows 10 Anniversary Update (version 1607) eller senare med den senaste uppdateringen av Microsoft Defender-program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="5888f-135">Devices running Windows 10 Anniversary Update (version 1607) or later with the latest Microsoft Defender antimalware engine update.</span></span>

## <a name="data-handling"></a><span data-ttu-id="5888f-136">Datahantering</span><span class="sxs-lookup"><span data-stu-id="5888f-136">Data handling</span></span>

<span data-ttu-id="5888f-137">Data lagras i den region som valdes som en del av dina inställningar för [Microsoft Defender för Slutpunktsdatahantering.](data-storage-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="5888f-137">Data is stored in the region that was selected as part of your [Microsoft Defender for Endpoint data handling settings](data-storage-privacy.md).</span></span> <span data-ttu-id="5888f-138">Dina data lämnar inte datacentret i den regionen.</span><span class="sxs-lookup"><span data-stu-id="5888f-138">Your data will not leave the data center in that region.</span></span> <span data-ttu-id="5888f-139">Dessutom kommer dina data inte att delas med någon tredje part, inklusive våra dataleverantörer.</span><span class="sxs-lookup"><span data-stu-id="5888f-139">In addition, your data will not be shared with any third-parties, including our data providers.</span></span>

## <a name="turn-on-web-content-filtering"></a><span data-ttu-id="5888f-140">Aktivera webbinnehållsfiltrering</span><span class="sxs-lookup"><span data-stu-id="5888f-140">Turn on web content filtering</span></span>

<span data-ttu-id="5888f-141">I den vänstra navigeringsmenyn väljer du **Inställningar**  >    >  **Avancerade funktioner.**</span><span class="sxs-lookup"><span data-stu-id="5888f-141">From the left-hand navigation menu, select **Settings** > **General** > **Advanced Features**.</span></span> <span data-ttu-id="5888f-142">Bläddra nedåt tills du ser posten för **webbinnehållsfiltrering**.</span><span class="sxs-lookup"><span data-stu-id="5888f-142">Scroll down until you see the entry for **Web content filtering**.</span></span> <span data-ttu-id="5888f-143">Ändra växlingsknappen till **På** **och Spara inställningar.**</span><span class="sxs-lookup"><span data-stu-id="5888f-143">Switch the toggle to **On** and **Save preferences**.</span></span>

### <a name="configure-web-content-filtering-policies"></a><span data-ttu-id="5888f-144">Konfigurera principer för filtrering av webbinnehåll</span><span class="sxs-lookup"><span data-stu-id="5888f-144">Configure web content filtering policies</span></span>

<span data-ttu-id="5888f-145">Principer för filtrering av webbinnehåll anger vilka webbplatskategorier som blockeras i vilka enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="5888f-145">Web content filtering policies specify which site categories are blocked on which device groups.</span></span> <span data-ttu-id="5888f-146">Gå till Regelfiltrering av **webbinnehåll Inställningar** för att  >    >  **hantera principerna.**</span><span class="sxs-lookup"><span data-stu-id="5888f-146">To manage the policies, go to **Settings** > **Rules** > **Web content filtering**.</span></span>

<span data-ttu-id="5888f-147">Använd filtret för att hitta principer som innehåller vissa blockerade kategorier eller som tillämpas på specifika enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="5888f-147">Use the filter to locate policies that contain certain blocked categories or are applied to specific device groups.</span></span>

### <a name="create-a-policy"></a><span data-ttu-id="5888f-148">Skapa en princip</span><span class="sxs-lookup"><span data-stu-id="5888f-148">Create a policy</span></span>

<span data-ttu-id="5888f-149">Så här lägger du till en ny princip:</span><span class="sxs-lookup"><span data-stu-id="5888f-149">To add a new policy:</span></span>

1. <span data-ttu-id="5888f-150">Välj **Lägg till princip** på sidan för **webbinnehållsfiltrering** i **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="5888f-150">Select **Add policy** on the **Web content filtering** page in **Settings**.</span></span>

2. <span data-ttu-id="5888f-151">Ange ett namn.</span><span class="sxs-lookup"><span data-stu-id="5888f-151">Specify a name.</span></span>

3. <span data-ttu-id="5888f-152">Markera de kategorier som ska blockeras.</span><span class="sxs-lookup"><span data-stu-id="5888f-152">Select the categories to block.</span></span> <span data-ttu-id="5888f-153">Använd expanderikonen för att helt expandera varje överordnad kategori och välja specifika kategorier för webbinnehåll.</span><span class="sxs-lookup"><span data-stu-id="5888f-153">Use the expand icon to fully expand each parent category and select specific web content categories.</span></span>

4. <span data-ttu-id="5888f-154">Ange principens omfattning.</span><span class="sxs-lookup"><span data-stu-id="5888f-154">Specify the policy scope.</span></span> <span data-ttu-id="5888f-155">Välj enhetsgrupper för att ange var principen ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="5888f-155">Select the device groups to specify where to apply the policy.</span></span> <span data-ttu-id="5888f-156">Det är bara enheter i de valda enhetsgrupperna som hindras från att komma åt webbplatser i de valda kategorierna.</span><span class="sxs-lookup"><span data-stu-id="5888f-156">Only devices in the selected device groups will be prevented from accessing websites in the selected categories.</span></span>

5. <span data-ttu-id="5888f-157">Granska sammanfattningen och spara principen.</span><span class="sxs-lookup"><span data-stu-id="5888f-157">Review the summary and save the policy.</span></span> <span data-ttu-id="5888f-158">Det kan ta upp till 2 timmar innan principuppdateringen tillämpas på dina valda enheter.</span><span class="sxs-lookup"><span data-stu-id="5888f-158">The policy refresh may take up to 2 hours to apply to your selected devices.</span></span>

> [!NOTE]
> - <span data-ttu-id="5888f-159">Du kan distribuera en princip utan att välja en kategori i en enhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="5888f-159">You can deploy a policy without selecting any category on a device group.</span></span> <span data-ttu-id="5888f-160">Den här åtgärden skapar en princip för granskning bara för att hjälpa dig att förstå användarbeteendet innan du skapar en blockeringsprincip.</span><span class="sxs-lookup"><span data-stu-id="5888f-160">This action will create an audit only policy, to help you understand user behavior before creating a block policy.</span></span>
> - <span data-ttu-id="5888f-161">Om du tar bort en princip eller ändrar enhetsgrupper samtidigt kan det orsaka en fördröjning i principdistributionen.</span><span class="sxs-lookup"><span data-stu-id="5888f-161">If you are removing a policy or changing device groups at the same time, this might cause a delay in policy deployment.</span></span>
> - <span data-ttu-id="5888f-162">Att blockera kategorin "Okategoriserad" kan leda till oväntade och oönskade resultat.</span><span class="sxs-lookup"><span data-stu-id="5888f-162">Blocking the "Uncategorized" category may lead to unexpected and undesired results.</span></span>  

### <a name="allow-specific-websites"></a><span data-ttu-id="5888f-163">Tillåt specifika webbplatser</span><span class="sxs-lookup"><span data-stu-id="5888f-163">Allow specific websites</span></span>

<span data-ttu-id="5888f-164">Du kan åsidosätta kategorin blockerad i webbinnehållsfiltrering om du vill tillåta en enda webbplats genom att skapa en egen indikatorprincip.</span><span class="sxs-lookup"><span data-stu-id="5888f-164">It's possible to override the blocked category in web content filtering to allow a single site by creating a custom indicator policy.</span></span> <span data-ttu-id="5888f-165">Principen för anpassad indikator ersätter webbinnehållsfiltreringsprincipen när den tillämpas på enhetsgruppen i fråga.</span><span class="sxs-lookup"><span data-stu-id="5888f-165">The custom indicator policy will supersede the web content filtering policy when it's applied to the device group in question.</span></span>

1. <span data-ttu-id="5888f-166">Du kan skapa en anpassad indikator i Microsoft Defender Säkerhetscenter genom att gå **Inställningar**  >    >  **URL/Domain**  >  **Add Item**.</span><span class="sxs-lookup"><span data-stu-id="5888f-166">Create a custom indicator in the Microsoft Defender Security Center by going to **Settings** > **Indicators** > **URL/Domain** > **Add Item**.</span></span>

2. <span data-ttu-id="5888f-167">Ange domänen för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="5888f-167">Enter the domain of the site.</span></span>

3. <span data-ttu-id="5888f-168">Ställ in principåtgärden på **Tillåt**.</span><span class="sxs-lookup"><span data-stu-id="5888f-168">Set the policy action to **Allow**.</span></span>  

### <a name="reporting-inaccuracies"></a><span data-ttu-id="5888f-169">Rapportering av felaktigheter</span><span class="sxs-lookup"><span data-stu-id="5888f-169">Reporting inaccuracies</span></span>

<span data-ttu-id="5888f-170">Om du träffar på en domän som felaktigt har kategoriserats kan du rapportera felaktigheter direkt till oss från rapportsidan Webbinnehållsfiltrering.</span><span class="sxs-lookup"><span data-stu-id="5888f-170">If you encounter a domain that has been incorrectly categorized, you can report inaccuracies directly to us from the Web Content Filtering reports page.</span></span> <span data-ttu-id="5888f-171">Den här funktionen är endast tillgänglig i det Microsoft 365 säkerhetscentret (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="5888f-171">This feature is available only in the new Microsoft 365 security center (security.microsoft.com).</span></span>

<span data-ttu-id="5888f-172">Om du vill rapportera en säkerhet går du till Reports  >  **Web Protection Web Content** Filtering  >  **Details**  >  **Domains**.</span><span class="sxs-lookup"><span data-stu-id="5888f-172">To report an inaccuracy, navigate to **Reports** > **Web protection** > **Web Content Filtering Details** > **Domains**.</span></span> <span data-ttu-id="5888f-173">På fliken Domäner i webbinnehållsfiltreringsrapporterna visas en ellips bredvid var och en av domänerna.</span><span class="sxs-lookup"><span data-stu-id="5888f-173">On the domains tab of our Web Content Filtering reports, you will see an ellipsis beside each of the domains.</span></span> <span data-ttu-id="5888f-174">Hovra över de här ellipsen **och välj Rapportinaccuracy**.</span><span class="sxs-lookup"><span data-stu-id="5888f-174">Hover over this ellipsis and select **Report Inaccuracy**.</span></span>

<span data-ttu-id="5888f-175">En panel öppnas där du kan välja prioritet och lägga till ytterligare information, till exempel den föreslagna kategorin för omkategorisering.</span><span class="sxs-lookup"><span data-stu-id="5888f-175">A panel will open where you can select the priority and add additional details such as the suggested category for re-categorization.</span></span> <span data-ttu-id="5888f-176">När du har slutfört formuläret väljer du **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="5888f-176">Once you complete the form, select **Submit**.</span></span> <span data-ttu-id="5888f-177">Vår grupp kommer att granska begäran inom en arbetsdag.</span><span class="sxs-lookup"><span data-stu-id="5888f-177">Our team will review the request within one business day.</span></span> <span data-ttu-id="5888f-178">Skapa en anpassad indikator för tillåt för omedelbar [blockering.](indicator-ip-domain.md)</span><span class="sxs-lookup"><span data-stu-id="5888f-178">For immediate unblocking, create a [custom allow indicator](indicator-ip-domain.md).</span></span>

## <a name="web-content-filtering-cards-and-details"></a><span data-ttu-id="5888f-179">Filtreringskort och information för webbinnehåll</span><span class="sxs-lookup"><span data-stu-id="5888f-179">Web content filtering cards and details</span></span>

<span data-ttu-id="5888f-180">Välj **Rapporter**  >  **Webbskydd om** du vill visa kort med information om webbinnehållsfiltrering och skydd mot webbhot.</span><span class="sxs-lookup"><span data-stu-id="5888f-180">Select **Reports** > **Web protection** to view cards with information about web content filtering and web threat protection.</span></span> <span data-ttu-id="5888f-181">På följande kort får du sammanfattningsinformation om filtrering av webbinnehåll.</span><span class="sxs-lookup"><span data-stu-id="5888f-181">The following cards provide summary information about web content filtering.</span></span>

### <a name="web-activity-by-category"></a><span data-ttu-id="5888f-182">Webbaktivitet efter kategori</span><span class="sxs-lookup"><span data-stu-id="5888f-182">Web activity by category</span></span>

<span data-ttu-id="5888f-183">Det här kortet visar de överordnade webbinnehållskategorierna med den största ökningen eller minskning av antalet åtkomstförsök.</span><span class="sxs-lookup"><span data-stu-id="5888f-183">This card lists the parent web content categories with the largest increase or decrease in the number of access attempts.</span></span> <span data-ttu-id="5888f-184">Förstå förändrat webbaktivitetsmönster i organisationen från de senaste 30 dagarna, 3 månaderna eller 6 månaderna.</span><span class="sxs-lookup"><span data-stu-id="5888f-184">Understand drastic changes in web activity patterns in your organization from last 30 days, 3 months, or 6 months.</span></span> <span data-ttu-id="5888f-185">Välj ett kategorinamn om du vill visa mer information.</span><span class="sxs-lookup"><span data-stu-id="5888f-185">Select a category name to view more information.</span></span>

<span data-ttu-id="5888f-186">Under de första 30 dagarna av den här funktionen kanske organisationen inte har tillräckligt med data för att visa den här informationen.</span><span class="sxs-lookup"><span data-stu-id="5888f-186">In the first 30 days of using this feature, your organization might not have enough data to display this information.</span></span>

![Bild av webbaktivitet efter kategorikort](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a><span data-ttu-id="5888f-188">Sammanfattningskort för webbinnehållsfiltrering</span><span class="sxs-lookup"><span data-stu-id="5888f-188">Web content filtering  summary card</span></span>

<span data-ttu-id="5888f-189">På det här kortet visas fördelningen av blockerade åtkomstförsök mellan de olika överordnade webbinnehållskategorierna.</span><span class="sxs-lookup"><span data-stu-id="5888f-189">This card displays the distribution of blocked access attempts across the different parent web content categories.</span></span> <span data-ttu-id="5888f-190">Välj en av de färgade staplarna om du vill visa mer information om en viss överordnad webbkategori.</span><span class="sxs-lookup"><span data-stu-id="5888f-190">Select one of the colored bars to view more information about a specific parent web category.</span></span>

![Bild på sammanfattningskort för filtrering av webbinnehåll](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a><span data-ttu-id="5888f-192">Sammanfattningskort för webbaktivitet</span><span class="sxs-lookup"><span data-stu-id="5888f-192">Web activity summary card</span></span>

<span data-ttu-id="5888f-193">På det här kortet visas det totala antalet begäranden om webbinnehåll i alla URL:er.</span><span class="sxs-lookup"><span data-stu-id="5888f-193">This card displays the total number of requests for web content in all URLs.</span></span>

![Bild på sammanfattningskort för webbaktivitet](images/web-activity-summary.png)

### <a name="view-card-details"></a><span data-ttu-id="5888f-195">Visa kortinformation</span><span class="sxs-lookup"><span data-stu-id="5888f-195">View card details</span></span>

<span data-ttu-id="5888f-196">Du kommer åt **rapportinformationen för varje** kort genom att välja en tabellrad eller en färgad stapel i diagrammet på kortet.</span><span class="sxs-lookup"><span data-stu-id="5888f-196">You can access the **Report details** for each card by selecting a table row or colored bar from the chart in the card.</span></span> <span data-ttu-id="5888f-197">Rapportinformationssidan för varje kort innehåller omfattande statistiska data om kategorier av webbinnehåll, webbplatsdomäner och enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="5888f-197">The report details page for each card contains extensive statistical data about web content categories, website domains, and device groups.</span></span>

![Bild på information om webbskyddsrapporten](images/web-protection-report-details.png)

- <span data-ttu-id="5888f-199">**Webbkategorier:** Visar de webbinnehållskategorier som har haft åtkomstförsök i organisationen.</span><span class="sxs-lookup"><span data-stu-id="5888f-199">**Web categories**: Lists the web content categories that have had access attempts in your organization.</span></span> <span data-ttu-id="5888f-200">Välj en specifik kategori för att öppna en utfällbladstext för sammanfattningen.</span><span class="sxs-lookup"><span data-stu-id="5888f-200">Select a specific category to open a summary flyout.</span></span>

- <span data-ttu-id="5888f-201">**Domäner**: Visar de webbdomäner som har använts eller blockerats i organisationen.</span><span class="sxs-lookup"><span data-stu-id="5888f-201">**Domains**: Lists the web domains that have been accessed or blocked in your organization.</span></span> <span data-ttu-id="5888f-202">Välj en viss domän om du vill visa detaljerad information om den domänen.</span><span class="sxs-lookup"><span data-stu-id="5888f-202">Select a specific domain to view detailed information about that domain.</span></span>

- <span data-ttu-id="5888f-203">**Enhetsgrupper:** Visar alla enhetsgrupper som har skapat webbaktivitet i organisationen</span><span class="sxs-lookup"><span data-stu-id="5888f-203">**Device groups**: Lists all the device groups that have generated web activity in your organization</span></span>

<span data-ttu-id="5888f-204">Använd tidsintervallsfiltret längst upp till vänster på sidan för att välja en tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="5888f-204">Use the time range filter at the top left of the page to select a time period.</span></span> <span data-ttu-id="5888f-205">Du kan också filtrera informationen eller anpassa kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="5888f-205">You can also filter the information or customize the columns.</span></span> <span data-ttu-id="5888f-206">Markera en rad för att öppna ett utfällt fönster med ännu mer information om det markerade objektet.</span><span class="sxs-lookup"><span data-stu-id="5888f-206">Select a row to open a flyout pane with even more information about the selected item.</span></span>

## <a name="errors-and-issues"></a><span data-ttu-id="5888f-207">Fel och problem</span><span class="sxs-lookup"><span data-stu-id="5888f-207">Errors and issues</span></span>

### <a name="limitations-and-known-issues-in-this-preview"></a><span data-ttu-id="5888f-208">Begränsningar och kända problem i den här förhandsversionen</span><span class="sxs-lookup"><span data-stu-id="5888f-208">Limitations and known issues in this preview</span></span>

- <span data-ttu-id="5888f-209">Endast Microsoft Edge om enhetens OS-konfiguration är Server **(cmd**  >  **Systeminfo**  >  **OS Configuration).**</span><span class="sxs-lookup"><span data-stu-id="5888f-209">Only Microsoft Edge is supported if your device's OS configuration is Server (**cmd** > **Systeminfo** > **OS Configuration**).</span></span> <span data-ttu-id="5888f-210">Nätverksskydd stöds endast i inspektera-läge på serverenheter, som ansvarar för att skydda trafiken mellan webbläsare som stöds.</span><span class="sxs-lookup"><span data-stu-id="5888f-210">Network Protection is only supported in Inspect mode on Server devices, which is responsible for securing traffic across supported 3rd party browsers.</span></span>

- <span data-ttu-id="5888f-211">Enheter som inte tilldelats visas med felaktiga data i rapporten.</span><span class="sxs-lookup"><span data-stu-id="5888f-211">Unassigned devices will have incorrect data shown within the report.</span></span> <span data-ttu-id="5888f-212">I **rapportens**  >  **detaljenhetsgrupper** visas eventuellt en rad med ett tomt enhetsgruppsfält.</span><span class="sxs-lookup"><span data-stu-id="5888f-212">In the **Report details** > **Device groups** pivot, you might see a row with a blank Device Group field.</span></span> <span data-ttu-id="5888f-213">Den här gruppen innehåller dina otilldelade enheter innan de läggs till i den angivna gruppen.</span><span class="sxs-lookup"><span data-stu-id="5888f-213">This group contains your unassigned devices before they get put into your specified group.</span></span> <span data-ttu-id="5888f-214">Rapporten för den här raden kanske inte innehåller rätt antal enheter eller antal åtkomstvärden.</span><span class="sxs-lookup"><span data-stu-id="5888f-214">The report for this row might not contain an accurate count of devices or access counts.</span></span>

- <span data-ttu-id="5888f-215">Rapporterna för webbinnehållsfiltrering är för närvarande begränsade till att visa de 5 000 högsta posterna.</span><span class="sxs-lookup"><span data-stu-id="5888f-215">Web Content Filtering reports are currently limited to showing the top 5000 records.</span></span> <span data-ttu-id="5888f-216">Till exempel visar rapporten Domäner endast det högsta antalet 5 000 domäner för en viss filterfråga, om tillämpligt.</span><span class="sxs-lookup"><span data-stu-id="5888f-216">For example, the Domains report will only show a maximum of the top 5000 domains for a given filter query, if applicable.</span></span> 


