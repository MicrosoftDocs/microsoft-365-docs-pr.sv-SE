---
title: Filtrering av webbinnehåll
description: Använd webbinnehållsfiltrering i Microsoft Defender ATP för att spåra och reglera åtkomsten till webbplatser baserat på deras innehållskategorier.
keywords: webbskydd, skydd mot webbhot, surfning, övervakning, rapporter, kort, domänlista, säkerhet, nätfiske, skadlig kod, sårbarhet, webbplatser, nätverksskydd, Edge, Internet Explorer, Chrome, Firefox, webbläsare
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: dd1b21b306d40ab03fa518f48c8a0bc985191f69
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071761"
---
# <a name="web-content-filtering"></a><span data-ttu-id="af81e-104">Filtrering av webbinnehåll</span><span class="sxs-lookup"><span data-stu-id="af81e-104">Web content filtering</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="af81e-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="af81e-105">**Applies to:**</span></span>
- [<span data-ttu-id="af81e-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="af81e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="af81e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af81e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="af81e-108">**Webbinnehållsfiltrering är för närvarande i offentlig förhandsversion**</span><span class="sxs-lookup"><span data-stu-id="af81e-108">**Web content filtering is currently in public preview**</span></span><br>
> <span data-ttu-id="af81e-109">Den här förhandsversionen tillhandahålls utan ett servicenivåavtal och rekommenderas inte för produktionsarbetsbelastningar.</span><span class="sxs-lookup"><span data-stu-id="af81e-109">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="af81e-110">Vissa funktioner kanske inte stöds eller kan ha begränsade funktioner.</span><span class="sxs-lookup"><span data-stu-id="af81e-110">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="af81e-111">Mer information finns i [Förhandsversionsfunktioner för Microsoft Defender för slutpunkt.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="af81e-111">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

><span data-ttu-id="af81e-112">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="af81e-112">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="af81e-113">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="af81e-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="af81e-114">Webbinnehållsfiltrering är [en del av webbskyddsfunktionerna](web-protection-overview.md) i Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="af81e-114">Web content filtering is part of [Web protection](web-protection-overview.md) capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="af81e-115">Det gör att din organisation kan spåra och reglera åtkomsten till webbplatser baserat på deras innehållskategorier.</span><span class="sxs-lookup"><span data-stu-id="af81e-115">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="af81e-116">Många av dessa webbplatser, även om de inte är skadliga, kan vara problematiska på grund av regelefterlevnad, bandbreddsanvändning eller andra problem.</span><span class="sxs-lookup"><span data-stu-id="af81e-116">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

<span data-ttu-id="af81e-117">Konfigurera principer i din enhetsgrupper för att blockera vissa kategorier.</span><span class="sxs-lookup"><span data-stu-id="af81e-117">Configure policies across your device groups to block certain categories.</span></span> <span data-ttu-id="af81e-118">När en kategori blockeras förhindrar du att användare i angivna enhetsgrupper kommer åt URL-adresser som är kopplade till kategorin.</span><span class="sxs-lookup"><span data-stu-id="af81e-118">Blocking a category prevents users within specified device groups from accessing URLs associated with the category.</span></span> <span data-ttu-id="af81e-119">URL-adresser granskas automatiskt för alla kategorier som inte blockeras.</span><span class="sxs-lookup"><span data-stu-id="af81e-119">For any category that's not blocked, the URLs are automatically audited.</span></span> <span data-ttu-id="af81e-120">Användarna kan komma åt URL-adresser utan störningar och du samlar in åtkomststatistik för att skapa ett mer anpassat principbeslut.</span><span class="sxs-lookup"><span data-stu-id="af81e-120">Your users can access the URLs without disruption, and you'll gather access statistics to help create a more custom policy decision.</span></span> <span data-ttu-id="af81e-121">Användarna ser ett blockeringsmeddelande om ett element på sidan de visar är att ringa samtal till en blockerad resurs.</span><span class="sxs-lookup"><span data-stu-id="af81e-121">Your users will see a block notification if an element on the page they're viewing is making calls to a blocked resource.</span></span>

<span data-ttu-id="af81e-122">Webbinnehållsfiltrering är tillgängligt i de större webbläsarna, med block som utförs av Windows Defender SmartScreen (Microsoft Edge) och Network Protection (Chrome, Firefox, Och Opera).</span><span class="sxs-lookup"><span data-stu-id="af81e-122">Web content filtering is available on the major web browsers, with blocks performed by Windows Defender SmartScreen (Microsoft Edge) and Network Protection (Chrome, Firefox, Brave and Opera).</span></span> <span data-ttu-id="af81e-123">Mer information om webbläsarstöd finns i avsnittet krav.</span><span class="sxs-lookup"><span data-stu-id="af81e-123">For more information about browser support, see the prerequisites section.</span></span>

<span data-ttu-id="af81e-124">Sammanfattning av fördelarna:</span><span class="sxs-lookup"><span data-stu-id="af81e-124">Summarizing the benefits:</span></span>

- <span data-ttu-id="af81e-125">Användare hindras från att komma åt webbplatser i blockerade kategorier, oavsett om de surfar lokalt eller inte</span><span class="sxs-lookup"><span data-stu-id="af81e-125">Users are prevented from accessing websites in blocked categories, whether they're browsing on-premises or away</span></span>
- <span data-ttu-id="af81e-126">Distribuera enkelt principer till grupper av användare med hjälp av enhetsgrupper som definierats [i Microsoft Defender för slutpunktsrollbaserade inställningar för åtkomstkontroll](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)</span><span class="sxs-lookup"><span data-stu-id="af81e-126">Conveniently deploy policies to groups of users using device groups defined in [Microsoft Defender for Endpoint role-based access control settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)</span></span>
- <span data-ttu-id="af81e-127">Access-webbrapporter på samma centrala plats, med synlighet över faktiska block och webbanvändning</span><span class="sxs-lookup"><span data-stu-id="af81e-127">Access web reports in the same central location, with visibility over actual blocks and web usage</span></span>

## <a name="user-experience"></a><span data-ttu-id="af81e-128">Användarupplevelse</span><span class="sxs-lookup"><span data-stu-id="af81e-128">User experience</span></span>

<span data-ttu-id="af81e-129">Blockeringen för webbläsare som stöds av tredje part tillhandahålls av Network Protection, som ger ett popup-meddelande på systemnivå om en blockerad anslutning för användaren.</span><span class="sxs-lookup"><span data-stu-id="af81e-129">The blocking experience for 3rd party supported browsers is provided by Network Protection, which provides a system-level toast notifying the user of a blocked connection.</span></span> 

<span data-ttu-id="af81e-130">Om du vill ha en mer användarvänlig upplevelse i webbläsaren kan du använda Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="af81e-130">For a more user-friendly in-browser experience, consider using Microsoft Edge.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="af81e-131">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="af81e-131">Prerequisites</span></span>

<span data-ttu-id="af81e-132">Innan du provar den här funktionen bör du kontrollera att du har följande krav:</span><span class="sxs-lookup"><span data-stu-id="af81e-132">Before trying out this feature, make sure you have the following requirements:</span></span>

- <span data-ttu-id="af81e-133">Windows 10 Enterprise, E5-licens ELLER Microsoft 365 E3 + Microsoft 365 E5-säkerhets tillägg.</span><span class="sxs-lookup"><span data-stu-id="af81e-133">Windows 10 Enterprise E5 license OR Microsoft 365 E3 + Microsoft 365 E5 Security add-on.</span></span>
- <span data-ttu-id="af81e-134">Åtkomst till Microsoft Defender Säkerhetscenter-portalen</span><span class="sxs-lookup"><span data-stu-id="af81e-134">Access to Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="af81e-135">Enheter som kör Windows 10 Anniversary Update (version 1607) eller senare med den senaste Mo MOB-uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="af81e-135">Devices running Windows 10 Anniversary Update (version 1607) or later with the latest MoCAMP update.</span></span>

<span data-ttu-id="af81e-136">Om Windows Defender SmartScreen inte är aktiverat tar nätverksskydd över blockeringen.</span><span class="sxs-lookup"><span data-stu-id="af81e-136">If Windows Defender SmartScreen isn't turned on, Network Protection will take over the blocking.</span></span> <span data-ttu-id="af81e-137">Nätverksskyddet [måste aktiveras](enable-network-protection.md) på enheten.</span><span class="sxs-lookup"><span data-stu-id="af81e-137">It requires [enabling Network Protection](enable-network-protection.md) on the device.</span></span> <span data-ttu-id="af81e-138">Chrome, Firefox, Firefox och Opera är för närvarande webbläsare från tredje part där den här funktionen är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="af81e-138">Chrome, Firefox, Brave, and Opera are currently 3rd party browsers in which this feature is enabled.</span></span>

## <a name="data-handling"></a><span data-ttu-id="af81e-139">Datahantering</span><span class="sxs-lookup"><span data-stu-id="af81e-139">Data handling</span></span>

<span data-ttu-id="af81e-140">Vi följer den region som du har valt att använda som en del av dina [Microsoft Defender för slutpunktsdatahanteringsinställningar.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="af81e-140">We will follow whichever region you have elected to use as part of your [Microsoft Defender for Endpoint data handling settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/data-storage-privacy).</span></span> <span data-ttu-id="af81e-141">Dina data lämnar inte datacentret i den regionen.</span><span class="sxs-lookup"><span data-stu-id="af81e-141">Your data will not leave the data center in that region.</span></span> <span data-ttu-id="af81e-142">Dessutom kommer dina data inte att delas med någon tredje part, inklusive våra dataleverantörer.</span><span class="sxs-lookup"><span data-stu-id="af81e-142">In addition, your data will not be shared with any third-parties, including our data providers.</span></span>

## <a name="turn-on-web-content-filtering"></a><span data-ttu-id="af81e-143">Aktivera webbinnehållsfiltrering</span><span class="sxs-lookup"><span data-stu-id="af81e-143">Turn on web content filtering</span></span>

<span data-ttu-id="af81e-144">I den vänstra navigeringsmenyn väljer du **Inställningar > Allmänt > Avancerade funktioner.**</span><span class="sxs-lookup"><span data-stu-id="af81e-144">From the left-hand navigation menu, select **Settings > General > Advanced Features**.</span></span> <span data-ttu-id="af81e-145">Bläddra nedåt tills du ser posten för **webbinnehållsfiltrering**.</span><span class="sxs-lookup"><span data-stu-id="af81e-145">Scroll down until you see the entry for **Web content filtering**.</span></span> <span data-ttu-id="af81e-146">Ändra växlingsknappen till **På** **och Spara inställningar.**</span><span class="sxs-lookup"><span data-stu-id="af81e-146">Switch the toggle to **On** and **Save preferences**.</span></span>

### <a name="configure-web-content-filtering-policies"></a><span data-ttu-id="af81e-147">Konfigurera principer för filtrering av webbinnehåll</span><span class="sxs-lookup"><span data-stu-id="af81e-147">Configure web content filtering policies</span></span>

<span data-ttu-id="af81e-148">Principer för filtrering av webbinnehåll anger vilka webbplatskategorier som blockeras i vilka enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="af81e-148">Web content filtering policies specify which site categories are blocked on which device groups.</span></span> <span data-ttu-id="af81e-149">Du hanterar principerna genom att gå till **Inställningar > eller > på Webbinnehållsfiltrering.**</span><span class="sxs-lookup"><span data-stu-id="af81e-149">To manage the policies, go to **Settings > Rules > Web content filtering**.</span></span>

<span data-ttu-id="af81e-150">Använd filtret för att hitta principer som innehåller vissa blockerade kategorier eller som tillämpas på specifika enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="af81e-150">Use the filter to locate policies that contain certain blocked categories or are applied to specific device groups.</span></span>

### <a name="create-a-policy"></a><span data-ttu-id="af81e-151">Skapa en princip</span><span class="sxs-lookup"><span data-stu-id="af81e-151">Create a policy</span></span>

<span data-ttu-id="af81e-152">Så här lägger du till en ny princip:</span><span class="sxs-lookup"><span data-stu-id="af81e-152">To add a new policy:</span></span>

1. <span data-ttu-id="af81e-153">Välj **Lägg till princip** på sidan för **webbinnehållsfiltrering** i **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="af81e-153">Select **Add policy** on the **Web content filtering** page in **Settings**.</span></span>
2. <span data-ttu-id="af81e-154">Ange ett namn.</span><span class="sxs-lookup"><span data-stu-id="af81e-154">Specify a name.</span></span>
3. <span data-ttu-id="af81e-155">Markera de kategorier som ska blockeras.</span><span class="sxs-lookup"><span data-stu-id="af81e-155">Select the categories to block.</span></span> <span data-ttu-id="af81e-156">Använd expanderikonen för att helt expandera varje överordnad kategori och välja specifika kategorier för webbinnehåll.</span><span class="sxs-lookup"><span data-stu-id="af81e-156">Use the expand icon to fully expand each parent category and select specific web content categories.</span></span>
4. <span data-ttu-id="af81e-157">Ange principens omfattning.</span><span class="sxs-lookup"><span data-stu-id="af81e-157">Specify the policy scope.</span></span> <span data-ttu-id="af81e-158">Välj enhetsgrupper för att ange var principen ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="af81e-158">Select the device groups to specify where to apply the policy.</span></span> <span data-ttu-id="af81e-159">Det är bara enheter i de valda enhetsgrupperna som hindras från att komma åt webbplatser i de valda kategorierna.</span><span class="sxs-lookup"><span data-stu-id="af81e-159">Only devices in the selected device groups will be prevented from accessing websites in the selected categories.</span></span>
5. <span data-ttu-id="af81e-160">Granska sammanfattningen och spara principen.</span><span class="sxs-lookup"><span data-stu-id="af81e-160">Review the summary and save the policy.</span></span> <span data-ttu-id="af81e-161">Det kan ta upp till 2 timmar innan principuppdateringen tillämpas på dina valda enheter.</span><span class="sxs-lookup"><span data-stu-id="af81e-161">The policy refresh may take up to 2 hours to apply to your selected devices.</span></span>

<span data-ttu-id="af81e-162">Tips: Du kan distribuera en princip utan att välja en kategori i en enhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="af81e-162">Tip: You can deploy a policy without selecting any category on a device group.</span></span> <span data-ttu-id="af81e-163">Den här åtgärden skapar en princip för granskning bara för att hjälpa dig att förstå användarbeteendet innan du skapar en blockeringsprincip.</span><span class="sxs-lookup"><span data-stu-id="af81e-163">This action will create an audit only policy, to help you understand user behavior before creating a block policy.</span></span>

>[!NOTE]
><span data-ttu-id="af81e-164">Om du tar bort en princip eller ändrar enhetsgrupper samtidigt kan det orsaka en fördröjning i principdistributionen.</span><span class="sxs-lookup"><span data-stu-id="af81e-164">If you are removing a policy or changing device groups at the same time, this might cause a delay in policy deployment.</span></span>

>[!IMPORTANT]
><span data-ttu-id="af81e-165">Att blockera kategorin "Okategoriserad" kan leda till oväntade och oönskade resultat.</span><span class="sxs-lookup"><span data-stu-id="af81e-165">Blocking the "Uncategorized" category may lead to unexpected and undesired results.</span></span>  

### <a name="allow-specific-websites"></a><span data-ttu-id="af81e-166">Tillåt specifika webbplatser</span><span class="sxs-lookup"><span data-stu-id="af81e-166">Allow specific websites</span></span>

<span data-ttu-id="af81e-167">Du kan åsidosätta kategorin blockerad i webbinnehållsfiltrering om du vill tillåta en enda webbplats genom att skapa en egen indikatorprincip.</span><span class="sxs-lookup"><span data-stu-id="af81e-167">It's possible to override the blocked category in web content filtering to allow a single site by creating a custom indicator policy.</span></span> <span data-ttu-id="af81e-168">Principen för anpassad indikator ersätter webbinnehållsfiltreringsprincipen när den tillämpas på enhetsgruppen i fråga.</span><span class="sxs-lookup"><span data-stu-id="af81e-168">The custom indicator policy will supersede the web content filtering policy when it's applied to the device group in question.</span></span>

1. <span data-ttu-id="af81e-169">Skapa en anpassad indikator i Microsoft Defender Säkerhetscenter genom att gå till URL:en **för**  >    >  **inställningsindikatorer/lägg till**  >  **objekt för domän**</span><span class="sxs-lookup"><span data-stu-id="af81e-169">Create a custom indicator in the Microsoft Defender Security Center by going to **Settings** > **Indicators** > **URL/Domain** > **Add Item**</span></span>
2. <span data-ttu-id="af81e-170">Ange domänen för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="af81e-170">Enter the domain of the site</span></span>
3. <span data-ttu-id="af81e-171">Ställ in principåtgärden på **Tillåt**.</span><span class="sxs-lookup"><span data-stu-id="af81e-171">Set the policy action to **Allow**.</span></span>  

### <a name="reporting-inaccuracies"></a><span data-ttu-id="af81e-172">Rapportering av felaktigheter</span><span class="sxs-lookup"><span data-stu-id="af81e-172">Reporting inaccuracies</span></span>

<span data-ttu-id="af81e-173">Om du träffar på en domän som felaktigt har kategoriserats kan du rapportera felaktigheter direkt till oss från rapportsidan Webbinnehållsfiltrering.</span><span class="sxs-lookup"><span data-stu-id="af81e-173">If you encounter a domain that has been incorrectly categorized, you can report inaccuracies directly to us from the Web Content Filtering reports page.</span></span> <span data-ttu-id="af81e-174">Den här funktionen är endast tillgänglig i det nya säkerhetscentret för Microsoft 365 (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="af81e-174">This feature is available only in the new Microsoft 365 security center (security.microsoft.com).</span></span>

<span data-ttu-id="af81e-175">Om du vill rapportera en felaktigheter navigerar du till Rapporter > skydd mot > information om **webbinnehållsfiltrering > Domäner**.</span><span class="sxs-lookup"><span data-stu-id="af81e-175">To report an inaccuracy, navigate to **Reports > Web protection > Web Content Filtering Details > Domains**.</span></span> <span data-ttu-id="af81e-176">På fliken Domäner i webbinnehållsfiltreringsrapporterna visas en ellips bredvid var och en av domänerna.</span><span class="sxs-lookup"><span data-stu-id="af81e-176">On the domains tab of our Web Content Filtering reports, you will see an ellipsis beside each of the domains.</span></span> <span data-ttu-id="af81e-177">Hovra över de här ellipsen **och välj Rapportinaccuracy**.</span><span class="sxs-lookup"><span data-stu-id="af81e-177">Hover over this ellipsis and select **Report Inaccuracy**.</span></span>

<span data-ttu-id="af81e-178">En panel öppnas där du kan välja prioritet och lägga till ytterligare information, till exempel den föreslagna kategorin för omkategorisering.</span><span class="sxs-lookup"><span data-stu-id="af81e-178">A panel will open where you can select the priority and add additional details such as the suggested category for re-categorization.</span></span> <span data-ttu-id="af81e-179">När du har slutfört formuläret väljer du **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="af81e-179">Once you complete the form, select **Submit**.</span></span> <span data-ttu-id="af81e-180">Vår grupp kommer att granska begäran inom en arbetsdag.</span><span class="sxs-lookup"><span data-stu-id="af81e-180">Our team will review the request within one business day.</span></span> <span data-ttu-id="af81e-181">Skapa en anpassad indikator för tillåt för omedelbar [blockering.](indicator-ip-domain.md)</span><span class="sxs-lookup"><span data-stu-id="af81e-181">For immediate unblocking, create a [custom allow indicator](indicator-ip-domain.md).</span></span>

## <a name="web-content-filtering-cards-and-details"></a><span data-ttu-id="af81e-182">Filtreringskort och information för webbinnehåll</span><span class="sxs-lookup"><span data-stu-id="af81e-182">Web content filtering cards and details</span></span>

<span data-ttu-id="af81e-183">Välj **Rapporter > för webbskydd om** du vill visa kort med information om filtrering av webbinnehåll och skydd mot webbhot.</span><span class="sxs-lookup"><span data-stu-id="af81e-183">Select **Reports > Web protection** to view cards with information about web content filtering and web threat protection.</span></span> <span data-ttu-id="af81e-184">På följande kort får du sammanfattningsinformation om filtrering av webbinnehåll.</span><span class="sxs-lookup"><span data-stu-id="af81e-184">The following cards provide summary information about web content filtering.</span></span>

### <a name="web-activity-by-category"></a><span data-ttu-id="af81e-185">Webbaktivitet efter kategori</span><span class="sxs-lookup"><span data-stu-id="af81e-185">Web activity by category</span></span>

<span data-ttu-id="af81e-186">Det här kortet visar de överordnade webbinnehållskategorierna med den största ökningen eller minskning av antalet åtkomstförsök.</span><span class="sxs-lookup"><span data-stu-id="af81e-186">This card lists the parent web content categories with the largest increase or decrease in the number of access attempts.</span></span> <span data-ttu-id="af81e-187">Förstå förändrat webbaktivitetsmönster i organisationen från de senaste 30 dagarna, 3 månaderna eller 6 månaderna.</span><span class="sxs-lookup"><span data-stu-id="af81e-187">Understand drastic changes in web activity patterns in your organization from last 30 days, 3 months, or 6 months.</span></span> <span data-ttu-id="af81e-188">Välj ett kategorinamn om du vill visa mer information.</span><span class="sxs-lookup"><span data-stu-id="af81e-188">Select a category name to view more information.</span></span>

<span data-ttu-id="af81e-189">Under de första 30 dagarna av den här funktionen kanske organisationen inte har tillräckligt med data för att visa den här informationen.</span><span class="sxs-lookup"><span data-stu-id="af81e-189">In the first 30 days of using this feature, your organization might not have enough data to display this information.</span></span>

![Bild av webbaktivitet efter kategorikort](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a><span data-ttu-id="af81e-191">Sammanfattningskort för webbinnehållsfiltrering</span><span class="sxs-lookup"><span data-stu-id="af81e-191">Web content filtering  summary card</span></span>

<span data-ttu-id="af81e-192">På det här kortet visas fördelningen av blockerade åtkomstförsök mellan de olika överordnade webbinnehållskategorierna.</span><span class="sxs-lookup"><span data-stu-id="af81e-192">This card displays the distribution of blocked access attempts across the different parent web content categories.</span></span> <span data-ttu-id="af81e-193">Välj en av de färgade staplarna om du vill visa mer information om en viss överordnad webbkategori.</span><span class="sxs-lookup"><span data-stu-id="af81e-193">Select one of the colored bars to view more information about a specific parent web category.</span></span>

![Bild på sammanfattningskort för filtrering av webbinnehåll](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a><span data-ttu-id="af81e-195">Sammanfattningskort för webbaktivitet</span><span class="sxs-lookup"><span data-stu-id="af81e-195">Web activity summary card</span></span>

<span data-ttu-id="af81e-196">På det här kortet visas det totala antalet begäranden om webbinnehåll i alla URL:er.</span><span class="sxs-lookup"><span data-stu-id="af81e-196">This card displays the total number of requests for web content in all URLs.</span></span>

![Bild på sammanfattningskort för webbaktivitet](images/web-activity-summary.png)

### <a name="view-card-details"></a><span data-ttu-id="af81e-198">Visa kortinformation</span><span class="sxs-lookup"><span data-stu-id="af81e-198">View card details</span></span>

<span data-ttu-id="af81e-199">Du kommer åt **rapportinformationen för varje** kort genom att välja en tabellrad eller en färgad stapel i diagrammet på kortet.</span><span class="sxs-lookup"><span data-stu-id="af81e-199">You can access the **Report details** for each card by selecting a table row or colored bar from the chart in the card.</span></span> <span data-ttu-id="af81e-200">Rapportinformationssidan för varje kort innehåller omfattande statistiska data om kategorier av webbinnehåll, webbplatsdomäner och enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="af81e-200">The report details page for each card contains extensive statistical data about web content categories, website domains, and device groups.</span></span>

![Bild på information om webbskyddsrapporten](images/web-protection-report-details.png)

- <span data-ttu-id="af81e-202">**Webbkategorier:** Visar de webbinnehållskategorier som har haft åtkomstförsök i organisationen.</span><span class="sxs-lookup"><span data-stu-id="af81e-202">**Web categories**: Lists the web content categories that have had access attempts in your organization.</span></span> <span data-ttu-id="af81e-203">Välj en specifik kategori för att öppna en utfällbladstext för sammanfattningen.</span><span class="sxs-lookup"><span data-stu-id="af81e-203">Select a specific category to open a summary flyout.</span></span>

- <span data-ttu-id="af81e-204">**Domäner**: Visar de webbdomäner som har använts eller blockerats i organisationen.</span><span class="sxs-lookup"><span data-stu-id="af81e-204">**Domains**: Lists the web domains that have been accessed or blocked in your organization.</span></span> <span data-ttu-id="af81e-205">Välj en viss domän om du vill visa detaljerad information om den domänen.</span><span class="sxs-lookup"><span data-stu-id="af81e-205">Select a specific domain to view detailed information about that domain.</span></span>

- <span data-ttu-id="af81e-206">**Enhetsgrupper:** Visar alla enhetsgrupper som har skapat webbaktivitet i organisationen</span><span class="sxs-lookup"><span data-stu-id="af81e-206">**Device groups**: Lists all the device groups that have generated web activity in your organization</span></span>

<span data-ttu-id="af81e-207">Använd tidsintervallsfiltret längst upp till vänster på sidan för att välja en tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="af81e-207">Use the time range filter at the top left of the page to select a time period.</span></span> <span data-ttu-id="af81e-208">Du kan också filtrera informationen eller anpassa kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="af81e-208">You can also filter the information or customize the columns.</span></span> <span data-ttu-id="af81e-209">Markera en rad för att öppna ett utfällt fönster med ännu mer information om det markerade objektet.</span><span class="sxs-lookup"><span data-stu-id="af81e-209">Select a row to open a flyout pane with even more information about the selected item.</span></span>

## <a name="errors-and-issues"></a><span data-ttu-id="af81e-210">Fel och problem</span><span class="sxs-lookup"><span data-stu-id="af81e-210">Errors and issues</span></span>

### <a name="limitations-and-known-issues-in-this-preview"></a><span data-ttu-id="af81e-211">Begränsningar och kända problem i den här förhandsversionen</span><span class="sxs-lookup"><span data-stu-id="af81e-211">Limitations and known issues in this preview</span></span>

- <span data-ttu-id="af81e-212">Endast Microsoft Edge stöds om enhetens OS-konfiguration är Server (cmd > Systeminfo > OS Configuration).</span><span class="sxs-lookup"><span data-stu-id="af81e-212">Only Microsoft Edge is supported if your device's OS configuration is Server (cmd > Systeminfo > OS Configuration).</span></span> <span data-ttu-id="af81e-213">Nätverksskydd stöds endast i inspektera-läge på serverenheter, som ansvarar för att skydda trafiken mellan webbläsare som stöds.</span><span class="sxs-lookup"><span data-stu-id="af81e-213">Network Protection is only supported in Inspect mode on Server devices, which is responsible for securing traffic across supported 3rd party browsers.</span></span>

- <span data-ttu-id="af81e-214">Enheter som inte tilldelats visas med felaktiga data i rapporten.</span><span class="sxs-lookup"><span data-stu-id="af81e-214">Unassigned devices will have incorrect data shown within the report.</span></span> <span data-ttu-id="af81e-215">I rapportens information > pivot för enhetsgrupper visas eventuellt en rad med ett tomt enhetsgruppsfält.</span><span class="sxs-lookup"><span data-stu-id="af81e-215">In the Report details > Device groups pivot, you may see a row with a blank Device Group field.</span></span> <span data-ttu-id="af81e-216">Den här gruppen innehåller dina otilldelade enheter innan de läggs till i den angivna gruppen.</span><span class="sxs-lookup"><span data-stu-id="af81e-216">This group contains your unassigned devices before they get put into your specified group.</span></span> <span data-ttu-id="af81e-217">Rapporten för den här raden kanske inte innehåller korrekt antal enheter eller antal åtkomstvärden.</span><span class="sxs-lookup"><span data-stu-id="af81e-217">The report for this row may not contain an accurate count of devices or access counts.</span></span>

## <a name="related-topics"></a><span data-ttu-id="af81e-218">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="af81e-218">Related topics</span></span>

- [<span data-ttu-id="af81e-219">Översikt över webbskydd</span><span class="sxs-lookup"><span data-stu-id="af81e-219">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="af81e-220">Skydd mot webbhot</span><span class="sxs-lookup"><span data-stu-id="af81e-220">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="af81e-221">Övervaka webbsäkerhet</span><span class="sxs-lookup"><span data-stu-id="af81e-221">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="af81e-222">Svara på webbhot</span><span class="sxs-lookup"><span data-stu-id="af81e-222">Respond to web threats</span></span>](web-protection-response.md)
