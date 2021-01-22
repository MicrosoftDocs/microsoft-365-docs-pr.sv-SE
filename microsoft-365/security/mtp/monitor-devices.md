---
title: Enhetsövervakning & rapportering – Säkerhetscenter
description: Här beskrivs hur du kan hålla dina enheter säkra, uppdaterade och upptäcka potentiella hot i organisationen
keywords: säkerhet, skadlig programvara, Microsoft 365, M365, säkerhetscenter, bildskärm, rapport, enheter
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: b9580f904f9cc5043fa3e825007339ce66daaa72
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930504"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="634bb-104">Enhetsövervakning och -rapportering i Microsoft 365 säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="634bb-104">Device monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="634bb-105">Håll dina enheter säkra, uppdaterade och hitta potentiella hot i Säkerhetscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="634bb-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="634bb-106">Visa enhetsaviseringar</span><span class="sxs-lookup"><span data-stu-id="634bb-106">View device alerts</span></span>

<span data-ttu-id="634bb-107">Få uppdaterade aviseringar om intrångsaktivitet och andra hot på dina enheter från Microsoft Defender för Endpoint (tillgänglig med en E5-licens).</span><span class="sxs-lookup"><span data-stu-id="634bb-107">Get up-to-date alerts about breach activity and other threats on your devices from Microsoft Defender for Endpoint (available with an E5 license).</span></span> <span data-ttu-id="634bb-108">Microsoft 365 Säkerhetscenter övervakar effektivt dessa varningar på en hög nivå med hjälp av önskat arbetsflöde.</span><span class="sxs-lookup"><span data-stu-id="634bb-108">Microsoft 365 security center effectively monitors these alerts at a high level using your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="634bb-109">Övervaka varningar med hög effekt</span><span class="sxs-lookup"><span data-stu-id="634bb-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="634bb-110">Varje Microsoft Defender för slutpunktsavisering har en motsvarande allvarlighetsgrad (hög, medel, låg eller information).</span><span class="sxs-lookup"><span data-stu-id="634bb-110">Each Microsoft Defender for Endpoint alert has a corresponding severity (high, medium, low, or informational).</span></span> <span data-ttu-id="634bb-111">Den visar möjlig påverkan på nätverket om du blir utan uppvaknad.</span><span class="sxs-lookup"><span data-stu-id="634bb-111">It indicates potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="634bb-112">Använd **allvarlighetskortet för** enhetsaviseringar för att specifikt fokusera på varningar som är mer allvarliga och kan kräva omedelbar respons.</span><span class="sxs-lookup"><span data-stu-id="634bb-112">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="634bb-113">Från det här kortet kan du se mer information på Microsoft Defender Säkerhetscenter-portalen.</span><span class="sxs-lookup"><span data-stu-id="634bb-113">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![Allvarlighetskort för enhetsaviseringar](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="634bb-115">Förstå källor till aviseringar</span><span class="sxs-lookup"><span data-stu-id="634bb-115">Understand sources of alerts</span></span>

<span data-ttu-id="634bb-116">Microsoft Defender för Endpoint använder data från ett brett utbud av säkerhetsmätare och informationskällor för att generera varningar.</span><span class="sxs-lookup"><span data-stu-id="634bb-116">Microsoft Defender for Endpoint leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="634bb-117">Den kan till exempel använda identifieringsinformation från Microsoft Defender Antivirus och tredjepartsprogram mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="634bb-117">For example, it can use detection information from Microsoft Defender Antivirus and third-party antimalware.</span></span> <span data-ttu-id="634bb-118">Den kan också använda din egen anpassade hotinformation som tillhandahålls via webbtjänst-API:t.</span><span class="sxs-lookup"><span data-stu-id="634bb-118">It can also use your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="634bb-119">Kortet **för identifiering av enhetsaviseringar** visar fördelningen av aviseringar efter källa.</span><span class="sxs-lookup"><span data-stu-id="634bb-119">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="634bb-120">Spåra aktivitet relaterad till vissa källor, särskilt anpassade källor.</span><span class="sxs-lookup"><span data-stu-id="634bb-120">Track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="634bb-121">Du kan också använda kortet för att fokusera på varningar som kommer från sensorer som inte är konfigurerade för att automatiskt blockera skadlig aktivitet eller komponenter.</span><span class="sxs-lookup"><span data-stu-id="634bb-121">You can also use the card to focus on alerts coming from sensors that aren't configured to automatically block malicious activity or components.</span></span>

![Kortet För identifiering av enhetsaviseringar](../../media/device-alert-detection-sources.png)

<span data-ttu-id="634bb-123">Från det här kortet kan du se mer information på Microsoft Defender Säkerhetscenter-portalen.</span><span class="sxs-lookup"><span data-stu-id="634bb-123">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="634bb-124">Förstå vilka typer av hot som utlöser aviseringar</span><span class="sxs-lookup"><span data-stu-id="634bb-124">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="634bb-125">Microsoft Defender för Slutpunkt sorterar varje avisering i en kategori som representerar ett visst steg i attackkedja eller typ av hotkomponent.</span><span class="sxs-lookup"><span data-stu-id="634bb-125">Microsoft Defender for Endpoint sorts each alert into a category representing a certain stage in the attack chain or type of threat component.</span></span> <span data-ttu-id="634bb-126">En identifierade hotaktivitet kan till exempel kategoriseras som "rörelse av rörelse" för att ange att det fanns ett försök att nå andra enheter på nätverket.</span><span class="sxs-lookup"><span data-stu-id="634bb-126">For example, a detected threat activity might be categorized as "lateral movement" to indicate there was an attempt to reach other devices on the network.</span></span> <span data-ttu-id="634bb-127">Aktiviteten har troligen inträffat efter att attacker har fått ett första fot fäste.</span><span class="sxs-lookup"><span data-stu-id="634bb-127">The activity has likely occurred after attackers gained an initial foothold.</span></span> <span data-ttu-id="634bb-128">När en hotkomponent upptäcks kan den klassificeras allmänt som skadlig programvara eller särskilt som en specifik hottyp.</span><span class="sxs-lookup"><span data-stu-id="634bb-128">When detected, a threat component might be classified broadly as malware or specifically as a specific threat type.</span></span> <span data-ttu-id="634bb-129">Detta gäller utpressningstrojaner, autentiseringsuppgifter som stjäls eller andra typer av skadlig eller oönskad programvara.</span><span class="sxs-lookup"><span data-stu-id="634bb-129">Specifics include ransomware, credential stealing, or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="634bb-130">Kortet **med kategorier för enhetshot** visar fördelningen av aviseringar i dessa kategorier.</span><span class="sxs-lookup"><span data-stu-id="634bb-130">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="634bb-131">Använd den här informationen för att identifiera hotaktivitet, till exempel försök till autentiseringsstöld, som vanligtvis har högre effekt än social engineering-försök.</span><span class="sxs-lookup"><span data-stu-id="634bb-131">Use this information to identify threat activity, such as credential theft attempts, that usually have higher impact than social engineering attempts.</span></span> <span data-ttu-id="634bb-132">Du kan också övervaka potentiella hot som utpressningstrojaner.</span><span class="sxs-lookup"><span data-stu-id="634bb-132">You can also to monitor for potentially destructive threats like ransomware.</span></span>

![Kort med kategorier för enhetshot](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="634bb-134">Övervaka aktiva aviseringar</span><span class="sxs-lookup"><span data-stu-id="634bb-134">Monitor active alerts</span></span>

<span data-ttu-id="634bb-135">Statuskortet **för enhetsaviseringar** anger antalet aviseringar som inte har lösts och kan behöva åtgärdas.</span><span class="sxs-lookup"><span data-stu-id="634bb-135">The **Device alert status** card indicates the number of alerts that haven't been resolved and may require attention.</span></span> <span data-ttu-id="634bb-136">Från det här kortet kan du se mer information på Microsoft Defender Säkerhetscenter-portalen.</span><span class="sxs-lookup"><span data-stu-id="634bb-136">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![Statuskort för enhetsavisering](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="634bb-138">Övervaka klassificering av lösta aviseringar</span><span class="sxs-lookup"><span data-stu-id="634bb-138">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="634bb-139">När du löser en Microsoft Defender för Slutpunkt-avisering kan din säkerhetspersonal ange om en avisering har verifierats som:</span><span class="sxs-lookup"><span data-stu-id="634bb-139">When resolving a Microsoft Defender for Endpoint alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="634bb-140">En verklig varning som identifierar faktiska intrångsaktiviteter eller hotkomponenter</span><span class="sxs-lookup"><span data-stu-id="634bb-140">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="634bb-141">En falsk varning som felaktigt har upptäckt normal aktivitet</span><span class="sxs-lookup"><span data-stu-id="634bb-141">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="634bb-142">**Klassificeringskortet för** enhetsaviseringar visar om dina lösta varningar har klassificerats som sanna eller falska varningar.</span><span class="sxs-lookup"><span data-stu-id="634bb-142">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="634bb-143">Från det här kortet kan du visa mer information på Microsoft Defender Säkerhetscenter-portalen.</span><span class="sxs-lookup"><span data-stu-id="634bb-143">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="634bb-144">Obs! I vissa fall är klassificeringsinformation inte tillgänglig för vissa aviseringar.</span><span class="sxs-lookup"><span data-stu-id="634bb-144">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![Klassificeringskort för enhetsavisering](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="634bb-146">Övervaka att lösta aviseringar fastställs</span><span class="sxs-lookup"><span data-stu-id="634bb-146">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="634bb-147">Förutom att klassificera om en avisering är sann eller falsk vid en lösning kan din säkerhetspersonal ge ett avgörande.</span><span class="sxs-lookup"><span data-stu-id="634bb-147">Along with classifying whether an alert is true or false during resolution, your security staff can provide a determination.</span></span> <span data-ttu-id="634bb-148">Ett avgörande anger vilken typ av normal eller skadlig aktivitet som hittades vid valideringen av aviseringen.</span><span class="sxs-lookup"><span data-stu-id="634bb-148">A determination indicates the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="634bb-149">På **determinationskortet för enhetsavisering** visas vilken determination som tillhandahålls för varje avisering.</span><span class="sxs-lookup"><span data-stu-id="634bb-149">The **Device alert determination** card shows the determination provided for each alert.</span></span>

* <span data-ttu-id="634bb-150">**APT:** avancerat beständigt hot, som anger att den identifierade aktiviteten eller hotkomponenten är en del av en avancerad intrångskomponent som utformats för att få ett fothåll i det påverkade nätverket</span><span class="sxs-lookup"><span data-stu-id="634bb-150">**APT**: advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="634bb-151">**Skadlig** programvara: skadlig fil eller kod</span><span class="sxs-lookup"><span data-stu-id="634bb-151">**Malware**: malicious file or code</span></span>
* <span data-ttu-id="634bb-152">**Säkerhetspersonal**: normal aktivitet utförd av säkerhetspersonal</span><span class="sxs-lookup"><span data-stu-id="634bb-152">**Security personnel**: normal activity performed by security staff</span></span>
* <span data-ttu-id="634bb-153">**Säkerhetstestning:** aktivitet eller komponenter som är utformade för att simulera faktiska hot och som förväntas utlösa säkerhetsmätare och generera varningar</span><span class="sxs-lookup"><span data-stu-id="634bb-153">**Security testing**: activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="634bb-154">**Oönskad programvara:** appar och annan programvara som inte anses vara skadlig men som på annat sätt strider mot policyn eller acceptabla användningsstandarder</span><span class="sxs-lookup"><span data-stu-id="634bb-154">**Unwanted software**: apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="634bb-155">**Övriga:** andra avgöranden som inte omfattas av de angivna typerna</span><span class="sxs-lookup"><span data-stu-id="634bb-155">**Others**: any other determination that doesn't fall under the provided types</span></span>

<span data-ttu-id="634bb-156">Från det här kortet kan du visa mer information i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="634bb-156">From this card, you can view more information in Microsoft Defender Security Center.</span></span>

![Determinationskort för enhetsavisering](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="634bb-158">Förstå vilka enheter som är i riskzonen</span><span class="sxs-lookup"><span data-stu-id="634bb-158">Understand which devices are at risk</span></span>

<span data-ttu-id="634bb-159">**Enhetsskydd** visar risknivån för enheter.</span><span class="sxs-lookup"><span data-stu-id="634bb-159">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="634bb-160">Risknivån baseras på faktorer som typ och allvarlighetsgrad för aviseringar på enheten.</span><span class="sxs-lookup"><span data-stu-id="634bb-160">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![Kortet för enhetsskydd](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="634bb-162">Övervaka och rapportera status för Intune-hanterade enheter</span><span class="sxs-lookup"><span data-stu-id="634bb-162">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="634bb-163">Följande rapporter innehåller data från enheter som är registrerade i Intune.</span><span class="sxs-lookup"><span data-stu-id="634bb-163">The following reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="634bb-164">Data från ej registrerade enheter ingår inte.</span><span class="sxs-lookup"><span data-stu-id="634bb-164">Data from unenrolled devices isn't included.</span></span> <span data-ttu-id="634bb-165">Endast globala administratörer kan visa dessa kort.</span><span class="sxs-lookup"><span data-stu-id="634bb-165">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="634bb-166">Intune-registrerade enhetsdata omfattar:</span><span class="sxs-lookup"><span data-stu-id="634bb-166">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="634bb-167">Enhetsefterlevnad</span><span class="sxs-lookup"><span data-stu-id="634bb-167">Device compliance</span></span>
* <span data-ttu-id="634bb-168">Enheter med aktiv skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="634bb-168">Devices with active malware</span></span>
* <span data-ttu-id="634bb-169">Typer av skadlig programvara på enheter</span><span class="sxs-lookup"><span data-stu-id="634bb-169">Types of malware on devices</span></span>
* <span data-ttu-id="634bb-170">Skadlig programvara på enheter</span><span class="sxs-lookup"><span data-stu-id="634bb-170">Malware on devices</span></span>
* <span data-ttu-id="634bb-171">Enheter med identifiering av skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="634bb-171">Devices with malware detections</span></span>
* <span data-ttu-id="634bb-172">Användare med identifiering av skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="634bb-172">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="634bb-173">Övervaka enhetsefterlevnad</span><span class="sxs-lookup"><span data-stu-id="634bb-173">Monitor device compliance</span></span>

<span data-ttu-id="634bb-174">**Enhetsefterlevnad** visar hur många enheter som är registrerade i Intune och som uppfyller konfigurationsprinciper.</span><span class="sxs-lookup"><span data-stu-id="634bb-174">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![Enhetsefterlevnadskort](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="634bb-176">Upptäck enheter med identifiering av skadlig kod</span><span class="sxs-lookup"><span data-stu-id="634bb-176">Discover devices with malware detections</span></span>

<span data-ttu-id="634bb-177">**Identifiering av skadlig kod** på enheten anger antalet registrerade Intune-enheter med skadlig programvara som inte har lösts helt.</span><span class="sxs-lookup"><span data-stu-id="634bb-177">**Device malware detections** provide the number of Intune enrolled devices with malware that hasn't been fully resolved.</span></span> <span data-ttu-id="634bb-178">En brist på lösning kan vara på grund av väntande åtgärder, en omstart, en fullständig genomsökning, manuella användaråtgärder eller om åtgärden inte slutförts.</span><span class="sxs-lookup"><span data-stu-id="634bb-178">A lack of resolution can be because of pending actions, a restart, a full scan, manual user actions, or if the remediation action was not successfully completed.</span></span>

![Kortet för identifiering av skadlig kod på enheten](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="634bb-180">Förstå vilka typer av skadlig programvara som upptäckts</span><span class="sxs-lookup"><span data-stu-id="634bb-180">Understand the types of malware detected</span></span>

<span data-ttu-id="634bb-181">**Typer av skadlig programvara på** enheter visar olika typer av skadlig programvara som har upptäckts på enheter som är registrerade i Intune.</span><span class="sxs-lookup"><span data-stu-id="634bb-181">**Types of malware on devices** show different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="634bb-182">Du kan undersöka varje typ av information i Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="634bb-182">You can investigate each type in the Microsoft 365 security center.</span></span>

![Typer av skadlig programvara på kortet enheter](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="634bb-184">Förstå den specifika skadlig programvara som upptäckts på dina enheter</span><span class="sxs-lookup"><span data-stu-id="634bb-184">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="634bb-185">**Skadlig programvara på enheter** ger en lista över den specifika skadlig programvara som upptäckts på dina enheter.</span><span class="sxs-lookup"><span data-stu-id="634bb-185">**Malware on devices** provides a list of the specific malware detected on your devices.</span></span>

![Skadlig programvara på enheters kort](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="634bb-187">Förstå vilka enheter som har mest skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="634bb-187">Understand which devices have the most malware</span></span>

<span data-ttu-id="634bb-188">**Enheter med identifiering av skadlig kod** visar vilka enheter som har flest identifieringar av skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="634bb-188">**Devices with malware detections** show which devices have the most malware detections.</span></span> <span data-ttu-id="634bb-189">i Säkerhetscenter för Microsoft 365 kan du undersöka om skadlig programvara är aktiv, vem som använder enheten och dess hanteringsstatus i Intune.</span><span class="sxs-lookup"><span data-stu-id="634bb-189">in the Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![Enheter med kortet för identifiering av skadlig programvara](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="634bb-191">Förstå vilka användare som har de enheter som har mest skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="634bb-191">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="634bb-192">**Användare med identifiering av skadlig programvara** visar användare med enheter som har de flesta identifieringar av skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="634bb-192">**Users with malware detections** show users with devices that had the most malware detections.</span></span> <span data-ttu-id="634bb-193">I Säkerhetscenter för Microsoft 365 kan du se hur många enheter som har tilldelats till varje användare och mer information om varje enhet och typen av skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="634bb-193">In the Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![Användare med kortet för identifiering av skadlig programvara](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-attack-surface-reduction-rule-deployment-and-detections"></a><span data-ttu-id="634bb-195">Övervaka och hantera distribution och identifiering av minskningsregel för attackytor</span><span class="sxs-lookup"><span data-stu-id="634bb-195">Monitor and manage attack surface reduction rule deployment and detections</span></span>

<span data-ttu-id="634bb-196">[ASR-regler (Attack Surface Reduction)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) hjälper till att förhindra åtgärder och appar som vanligtvis används av sårbarhetssökning efter skadlig programvara för att smitta enheter.</span><span class="sxs-lookup"><span data-stu-id="634bb-196">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) help prevent actions and apps that are typically used by exploit-seeking malware to infect devices.</span></span> <span data-ttu-id="634bb-197">Dessa regler styr när och hur körbara filer kan köras.</span><span class="sxs-lookup"><span data-stu-id="634bb-197">These rules control when and how executables can run.</span></span> <span data-ttu-id="634bb-198">Du kan till exempel förhindra att JavaScript eller VBScript startar en nedladdad körbar fil, blockera Win32 API-anrop från Office-makron eller blockera processer som körs från USB-enheter.</span><span class="sxs-lookup"><span data-stu-id="634bb-198">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![Attackytans visitkort](../../media/attack-surface-reduction-rules.png)

<span data-ttu-id="634bb-200">Kortet **för minskning av attackytan** ger en översikt över distributionen av regler på dina enheter.</span><span class="sxs-lookup"><span data-stu-id="634bb-200">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="634bb-201">I det översta fältet på kortet visas det totala antalet enheter som finns i följande distributionsläge:</span><span class="sxs-lookup"><span data-stu-id="634bb-201">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="634bb-202">**Blockläge:** enheter med minst en regel konfigurerad för att blockera upptäckt aktivitet</span><span class="sxs-lookup"><span data-stu-id="634bb-202">**Block mode**: devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="634bb-203">**Granskningsläge:** enheter utan regler som anger att blockera upptäckt aktivitet, men har minst en regeluppsättning för att granska upptäckt aktivitet</span><span class="sxs-lookup"><span data-stu-id="634bb-203">**Audit mode**: devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="634bb-204">**Av:** enheter med alla ASR-regler inaktiverade</span><span class="sxs-lookup"><span data-stu-id="634bb-204">**Off**: devices with all ASR rules turned off</span></span>

<span data-ttu-id="634bb-205">På den nedre delen av det här kortet visas inställningar enligt regel på alla dina enheter.</span><span class="sxs-lookup"><span data-stu-id="634bb-205">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="634bb-206">Varje stapel anger antalet enheter som är inställda på att blockeras, granskningsidentifiering eller har regeln helt inaktiverad.</span><span class="sxs-lookup"><span data-stu-id="634bb-206">Each bar indicates the number of devices that are set to block, audit detection, or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="634bb-207">Visa ASR-identifieringar</span><span class="sxs-lookup"><span data-stu-id="634bb-207">View ASR detections</span></span>

<span data-ttu-id="634bb-208">Om du vill visa detaljerad information om ASR-regelidentifiering i nätverket väljer du Visa **identifieringar** på kortet för minskning av **attackytan.**</span><span class="sxs-lookup"><span data-stu-id="634bb-208">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="634bb-209">Fliken **Identifieringar** på sidan med detaljerad rapport öppnas.</span><span class="sxs-lookup"><span data-stu-id="634bb-209">The **Detections** tab in the detailed report page will open.</span></span>

![Fliken Identifieringar](../../media/detections-tab.png)

<span data-ttu-id="634bb-211">I diagrammet högst upp på sidan visas identifieringar över tidsstackningsidentifiering som har blockerats eller granskats.</span><span class="sxs-lookup"><span data-stu-id="634bb-211">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="634bb-212">Tabellen längst ned visar de senaste identifieringarna.</span><span class="sxs-lookup"><span data-stu-id="634bb-212">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="634bb-213">Använd följande information i tabellen för att förstå hur identifieringarna ser ut:</span><span class="sxs-lookup"><span data-stu-id="634bb-213">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="634bb-214">**Upptäckt fil:** filen, vanligtvis ett skript eller ett dokument, vars innehåll utlöste den misstänkta attackaktiviteten</span><span class="sxs-lookup"><span data-stu-id="634bb-214">**Detected file**: the file, typically a script or document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="634bb-215">**Regel:** namn som beskriver attackaktiviteterna som regeln har utformats för att fånga in.</span><span class="sxs-lookup"><span data-stu-id="634bb-215">**Rule**: name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="634bb-216">Läs om befintliga ASR-regler</span><span class="sxs-lookup"><span data-stu-id="634bb-216">Read about existing ASR rules</span></span>
* <span data-ttu-id="634bb-217">**Källapp:** programmet som läst in eller kört innehåll som utlöste den misstänkta attackaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="634bb-217">**Source app**: the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="634bb-218">Det kan vara ett legitimt program, till exempel en webbläsare, ett Office-program eller ett systemverktyg som PowerShell</span><span class="sxs-lookup"><span data-stu-id="634bb-218">It could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="634bb-219">**Publisher:** leverantören som släppte källappen</span><span class="sxs-lookup"><span data-stu-id="634bb-219">**Publisher**: the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="634bb-220">Granska inställningar för ASR-regler för enheter</span><span class="sxs-lookup"><span data-stu-id="634bb-220">Review device ASR rule settings</span></span>

<span data-ttu-id="634bb-221">Gå till **fliken Konfiguration på rapportsidan** för minskning av attackytan och granska regelinställningarna för enskilda enheter. </span><span class="sxs-lookup"><span data-stu-id="634bb-221">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="634bb-222">Välj en enhet för att få detaljerad information om huruvida varje regel är i blockläge, granskningsläge eller helt inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="634bb-222">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

![Fliken Konfiguration](../../media/configuration-tab.png)

<span data-ttu-id="634bb-224">Microsoft Intune tillhandahåller hanteringsfunktioner för dina ASR-regler.</span><span class="sxs-lookup"><span data-stu-id="634bb-224">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="634bb-225">Om du vill uppdatera inställningarna väljer du **Kom** igång **under** Konfigurera enheter på fliken för att öppna enhetshantering på Intune.</span><span class="sxs-lookup"><span data-stu-id="634bb-225">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="634bb-226">Undanta filer från ASR-regler</span><span class="sxs-lookup"><span data-stu-id="634bb-226">Exclude files from ASR rules</span></span>

<span data-ttu-id="634bb-227">Microsoft 365 Säkerhetscenter samlar in [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) namnen på filerna som du kanske vill utesluta från identifieringar genom regler för att minska attackytan.</span><span class="sxs-lookup"><span data-stu-id="634bb-227">Microsoft 365 security center collects the names of the [files you might want to exclude](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) from detections by attack surface reduction rules.</span></span> <span data-ttu-id="634bb-228">Genom att utesluta filer kan du minska antalet falska positiva identifieringar och använda minskningsregler för attackytan i blockläge med större säkerhet.</span><span class="sxs-lookup"><span data-stu-id="634bb-228">By excluding files, you can reduce false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="634bb-229">Undantagen hanteras i Microsoft Intune, men Microsoft 365 Säkerhetscenter innehåller ett analysverktyg som hjälper dig att förstå filerna.</span><span class="sxs-lookup"><span data-stu-id="634bb-229">The exclusions are managed on Microsoft Intune, but Microsoft 365 security center provides an analysis tool to help you understand the files.</span></span> <span data-ttu-id="634bb-230">Om du vill börja samla in filer för undantag går du **till fliken** Lägg till undantag på **rapportsidan för minskning av attackytan.**</span><span class="sxs-lookup"><span data-stu-id="634bb-230">To start collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

>[!NOTE]  
><span data-ttu-id="634bb-231">Verktyget analyserar identifieringar av alla minskningsregler för attackytan, men [endast vissa regler stöder undantag.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr)</span><span class="sxs-lookup"><span data-stu-id="634bb-231">The tool analyzes detections by all attack surface reduction rules, but [only some rules support exclusions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).</span></span>

![Fliken Lägg till undantag](../../media/add-exclusions-tab.png)

<span data-ttu-id="634bb-233">Tabellen innehåller alla filnamn som upptäckts av dina minskningsregler för attackytan.</span><span class="sxs-lookup"><span data-stu-id="634bb-233">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="634bb-234">Du kan välja filer för att granska effekterna av att utesluta dem:</span><span class="sxs-lookup"><span data-stu-id="634bb-234">You can select files to review the impact of excluding them:</span></span>

* <span data-ttu-id="634bb-235">Hur många färre identifieringar</span><span class="sxs-lookup"><span data-stu-id="634bb-235">How many fewer detections</span></span>
* <span data-ttu-id="634bb-236">Hur många färre enheter rapporterar identifieringarna</span><span class="sxs-lookup"><span data-stu-id="634bb-236">How many fewer devices report the detections</span></span>

<span data-ttu-id="634bb-237">Om du vill visa en lista över de markerade filerna med fullständiga sökvägar för undantag väljer du **Hämta undantagssökvägar.**</span><span class="sxs-lookup"><span data-stu-id="634bb-237">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="634bb-238">Loggar för ASR-regeln Blockera autentiseringsuppgifter som stjäls från Windows lokala säkerhetsutfärdares **undersystem (lsass.exe) fångar** källappens **lsass.exe.**</span><span class="sxs-lookup"><span data-stu-id="634bb-238">Logs for the ASR rule **Block credential stealing from the Windows local security authority subsystem (lsass.exe)** capture the source app **lsass.exe**.</span></span> <span data-ttu-id="634bb-239">Det är en vanlig systemfil, men fångas som den identifierade filen.</span><span class="sxs-lookup"><span data-stu-id="634bb-239">It is a normal system file, but captured as the detected file.</span></span> <span data-ttu-id="634bb-240">Därför innehåller den genererade listan med undantagssökvägar den här filen.</span><span class="sxs-lookup"><span data-stu-id="634bb-240">As a result, the generated list of exclusion paths will include this file.</span></span> <span data-ttu-id="634bb-241">Om du vill utesluta filen som utlöste den här **regeln ilsass.exe** ska du använda sökvägen till källappen i stället för den identifierade filen.</span><span class="sxs-lookup"><span data-stu-id="634bb-241">To exclude the file that triggered this rule instead of **lsass.exe**, use the path to the source app instead of the detected file.</span></span>

<span data-ttu-id="634bb-242">Du hittar källappen genom [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) att köra följande avancerade fråga för den här specifika regeln (identifierad med regel-ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span><span class="sxs-lookup"><span data-stu-id="634bb-242">To locate the source app, run the following [advanced hunting query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) for this specific rule (identified by rule ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a><span data-ttu-id="634bb-243">Söka efter undantag i filer</span><span class="sxs-lookup"><span data-stu-id="634bb-243">Check files for exclusion</span></span>

<span data-ttu-id="634bb-244">Innan du utesluter en fil från ASR rekommenderar vi att du kontrollerar filen för att avgöra om den verkligen inte är skadlig.</span><span class="sxs-lookup"><span data-stu-id="634bb-244">Before excluding a file from ASR, we recommend that you inspect the file to determine if it's indeed not malicious.</span></span>

<span data-ttu-id="634bb-245">Om du vill granska en fil använder [du filinformationssidan](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="634bb-245">To review a file, use the [file information page](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) on Microsoft Defender Security Center.</span></span> <span data-ttu-id="634bb-246">Sidan innehåller information om intrånget och förhållandet för virustotal antivirusidentifiering.</span><span class="sxs-lookup"><span data-stu-id="634bb-246">The page provides prevalence information and the VirusTotal antivirus detection ratio.</span></span> <span data-ttu-id="634bb-247">Du kan också använda sidan för att skicka filen för djupanalys.</span><span class="sxs-lookup"><span data-stu-id="634bb-247">You can also use the page to submit the file for deep analysis.</span></span>

<span data-ttu-id="634bb-248">Om du vill hitta en identifierad fil i Microsoft Defender Säkerhetscenter söker du efter alla ASR-identifieringar med hjälp av följande avancerade sökfråga:</span><span class="sxs-lookup"><span data-stu-id="634bb-248">To locate a detected file in Microsoft Defender Security Center, search for all ASR detections using the following advanced hunting query:</span></span>

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

<span data-ttu-id="634bb-249">Använd **SHA1** **ellerItierprocessSHA1** i resultaten för att söka efter filen med hjälp av det universella sökfältet i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="634bb-249">Use the **SHA1** or the **InitiatingProcessSHA1** in the results to search for the file using the universal search bar in Microsoft Defender Security Center.</span></span>
