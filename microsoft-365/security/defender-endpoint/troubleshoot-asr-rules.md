---
title: Rapportera och felsöka Microsoft Defender för SLUTPUNKT ASR-regler
description: I det här avsnittet beskrivs hur du rapporterar och felsöker Microsoft Defender för Slutpunkt ASR-regler
keywords: Minskningsregler för attackytan, asr, hips, host intrusion prevention system, protection rules, anti-exploit, antiexploit, exploit, prevention av smitta, microsoft defender för slutpunkt
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c043e97d6c02e4f41d000e9ce8cfea4a0950252a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246259"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-atp-asr-rules"></a><span data-ttu-id="69f42-104">Rapportera och felsöka Microsoft Defender för ATP ASR-regler</span><span class="sxs-lookup"><span data-stu-id="69f42-104">Report and troubleshoot Microsoft Defender for ATP ASR Rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="69f42-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="69f42-105">**Applies to:**</span></span>

- [<span data-ttu-id="69f42-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="69f42-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="69f42-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="69f42-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="69f42-108">Det Microsoft 365 säkerhetscentret är det nya gränssnittet för övervakning och hantering av säkerhet i dina Microsoft-identiteter, data, enheter, appar och infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="69f42-108">The Microsoft 365 security center is the new interface for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span> <span data-ttu-id="69f42-109">Här kan du enkelt se säkerhetshälsa för din organisation, konfigurera enheter, användare och appar och få aviseringar om misstänkt aktivitet.</span><span class="sxs-lookup"><span data-stu-id="69f42-109">Here you can easily view the security health of your organization, act to configure devices, users, and apps, and get alerts for suspicious activity.</span></span> <span data-ttu-id="69f42-110">Säkerhetscentret Microsoft 365 avsett för säkerhetsadministratörer och säkerhetsgrupper för att bättre kunna hantera och skydda organisationen.</span><span class="sxs-lookup"><span data-stu-id="69f42-110">The Microsoft 365 security center is intended for security admins and security operations teams to better manage and protect their organization.</span></span> <span data-ttu-id="69f42-111">Besök säkerhetscentret Microsoft 365 på https://security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="69f42-111">Visit the Microsoft 365 security center at https://security.microsoft.com.</span></span>
<span data-ttu-id="69f42-112">I Microsoft 365 säkerhetscenter erbjuder vi dig en fullständig titt på aktuella konfigurationer och händelser för ASR-regler på din resurs.</span><span class="sxs-lookup"><span data-stu-id="69f42-112">In Microsoft 365 security center, we offer you a complete look at the current ASR rules configuration and events in your estate.</span></span> <span data-ttu-id="69f42-113">Observera att dina enheter måste vara onboarded in i Microsoft Defender för Endpoint-tjänsten för att dessa rapporter ska fyllas i.</span><span class="sxs-lookup"><span data-stu-id="69f42-113">Note that your devices must be onboarded into the Microsoft Defender for Endpoint service for these reports to be populated.</span></span>
<span data-ttu-id="69f42-114">Här är en skärmbild från säkerhetscentret Microsoft 365 (under Rapporter **enheter Minska**  >    >  **attackytan).**</span><span class="sxs-lookup"><span data-stu-id="69f42-114">Here's a screenshot from the Microsoft 365 security center (under **Reports** > **Devices** > **Attack surface reduction**).</span></span> <span data-ttu-id="69f42-115">På enhetsnivå väljer du **Konfiguration i** fönstret För att **minska attackytan.**</span><span class="sxs-lookup"><span data-stu-id="69f42-115">At the device level, select **Configuration** from the **Attack surface reduction rules** pane.</span></span> <span data-ttu-id="69f42-116">Följande skärm visas, där du kan välja en specifik enhet och kontrollera dess enskilda konfiguration av ASR-regler.</span><span class="sxs-lookup"><span data-stu-id="69f42-116">The following screen is displayed, where you can select a specific device and check its individual ASR rule configuration.</span></span>

:::image type="content" source="images/asrrulesnew.png" alt-text="Skärmen ASR-regler":::

## <a name="microsoft-defender-for-endpoint--advanced-hunting"></a><span data-ttu-id="69f42-118">Microsoft Defender för slutpunkt – avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="69f42-118">Microsoft Defender for Endpoint – Advanced hunting</span></span>

<span data-ttu-id="69f42-119">En av de mest kraftfulla funktionerna i Microsoft Defender för Endpoint är avancerad sökning.</span><span class="sxs-lookup"><span data-stu-id="69f42-119">One of the most powerful features of Microsoft Defender for Endpoint is advanced hunting.</span></span> <span data-ttu-id="69f42-120">Om du inte är bekant med avancerad sökning kan du referera till att [proaktivt leta efter hot med avancerad sökning.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="69f42-120">If you're unfamiliar with advanced hunting, refer [proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

<span data-ttu-id="69f42-121">Avancerad sökning är ett frågebaserat verktyg (Kusto Query Language) som du kan använda för att utforska upp till 30 dagar efter de registrerade (rådata) som MDE-slutpunktsidentifiering och svar (Identifiering och åtgärd på slutpunkt) samlar in från alla dina datorer.</span><span class="sxs-lookup"><span data-stu-id="69f42-121">Advanced hunting is a query-based (Kusto Query Language) threat-hunting tool that lets you explore up to 30 days of the captured (raw) data, that MDE Endpoint Detection and Response (EDR) collects from all your machines.</span></span> <span data-ttu-id="69f42-122">Genom avancerad sökning kan du proaktivt kontrollera händelser för att hitta intressanta indikatorer och enheter.</span><span class="sxs-lookup"><span data-stu-id="69f42-122">Through advanced hunting, you can proactively inspect events to locate interesting indicators and entities.</span></span> <span data-ttu-id="69f42-123">Den flexibla åtkomsten till data hjälper till att undvika en fast uppgift om både kända och potentiella hot.</span><span class="sxs-lookup"><span data-stu-id="69f42-123">The flexible access to data helps unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="69f42-124">Genom avancerad sökning kan du extrahera ASR-regelinformation, skapa rapporter och få ingående information om kontexten för en viss ASR-regelgranskning eller blockhändelse.</span><span class="sxs-lookup"><span data-stu-id="69f42-124">Through advanced hunting, it's possible to extract ASR rules information, create reports, and get in-depth information on the context of a given ASR rule audit or block event.</span></span>

<span data-ttu-id="69f42-125">ASR-regelhändelser är tillgängliga att köra frågor från tabellen DeviceEvents i avsnittet om avancerad sökning i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="69f42-125">ASR rules events are available to be queried from the DeviceEvents table in the advanced hunting section of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="69f42-126">Till exempel kan en enkel fråga som den nedan rapportera alla händelser som har ASR-regler som datakälla, under de senaste 30 dagarna, och summera dem med antalet ActionType, som i det här fallet är den faktiska kodnamnet för ASR-regeln.</span><span class="sxs-lookup"><span data-stu-id="69f42-126">For example, a simple query such as the one below can report all the events that have ASR rules as data source, for the last 30 days, and will summarize them by the ActionType count, that in this case it will be the actual codename of the ASR rule.</span></span>

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="Avancerad fråga om sökning":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="avancerad skärm för sökning":::

<span data-ttu-id="69f42-129">Med avancerad sökning kan du utforma frågorna efter dina önskemål, så att du kan se vad som händer, oavsett om du vill hitta något på en enskild dator eller om du vill extrahera insikter från hela miljön.</span><span class="sxs-lookup"><span data-stu-id="69f42-129">With advanced hunting you can shape the queries to your liking, so that you can see what is happening, regardless of whether you want to pinpoint something on an individual machine, or you want to extract insights from your entire environment.</span></span>

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a><span data-ttu-id="69f42-130">Microsoft Defender för slutpunktsdatortidslinje</span><span class="sxs-lookup"><span data-stu-id="69f42-130">Microsoft Defender for Endpoint machine timeline</span></span>

<span data-ttu-id="69f42-131">Ett alternativ till avancerad sökning, men med en smalare omfattning, är tidslinjen för Microsoft Defender för Endpoint-datorn.</span><span class="sxs-lookup"><span data-stu-id="69f42-131">An alternative to advanced hunting, but with a narrower scope, is the Microsoft Defender for Endpoint machine timeline.</span></span> <span data-ttu-id="69f42-132">Du kan visa alla insamlade händelser för en enhet under de senaste sex månaderna i Microsoft Defender Säkerhetscenter genom att gå till listan Datorer, välja en viss dator och sedan klicka på fliken Tidslinje.</span><span class="sxs-lookup"><span data-stu-id="69f42-132">You can view all the collected events of a device, for the past six months, in the Microsoft Defender Security Center, by going to the Machines list, select a given machine, and then click on the Timeline tab.</span></span>

<span data-ttu-id="69f42-133">På bilden nedan visas en skärmbild av vyn Tidslinje över dessa händelser på en viss slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="69f42-133">Pictured below is a screenshot of the Timeline view of these events on a given endpoint.</span></span>  <span data-ttu-id="69f42-134">I den här vyn kan du filtrera händelselistan baserat på valfri händelsegrupp i fönstret till höger.</span><span class="sxs-lookup"><span data-stu-id="69f42-134">From this view, you can filter the events list based on any of the Event Groups along the right-side pane.</span></span> <span data-ttu-id="69f42-135">Du kan också aktivera eller inaktivera flaggade och utförliga händelser när du visar aviseringar och bläddrar genom den historiska tidslinjen.</span><span class="sxs-lookup"><span data-stu-id="69f42-135">You can also enable or disable Flagged and Verbose events while viewing alerts and scrolling through the historical timeline.</span></span>

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="tidslinje i Microsoft Defender Säkerhetscenter":::

## <a name="how-to-troubleshoot-asr-rules"></a><span data-ttu-id="69f42-137">Felsöka ASR-regler?</span><span class="sxs-lookup"><span data-stu-id="69f42-137">How to troubleshoot ASR rules?</span></span>

<span data-ttu-id="69f42-138">Det första och mest direkta sättet är att kontrollera lokalt på en Windows-enhet, som ASR-regler aktiveras (och deras konfiguration) är att använda PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="69f42-138">The first and most immediate way is to check locally, on a Windows device, which ASR rules are enabled (and their configuration) is by using the PowerShell cmdlets.</span></span>

<span data-ttu-id="69f42-139">Här är några andra informationskällor som kan Windows som hjälper dig felsöka påverkan på och åtgärd för ASR-regler.</span><span class="sxs-lookup"><span data-stu-id="69f42-139">Here are a few other sources of information that Windows offers, to troubleshoot ASR rules’ impact and operation.</span></span>

### <a name="querying-which-rules-are-active"></a><span data-ttu-id="69f42-140">Fråga vilka regler som är aktiva</span><span class="sxs-lookup"><span data-stu-id="69f42-140">Querying which rules are active</span></span>
<span data-ttu-id="69f42-141">Ett av de enklaste sätten att avgöra om ASR-regler redan är aktiverade, och är via en PowerShell-cmdlet, Get-MpPreference.</span><span class="sxs-lookup"><span data-stu-id="69f42-141">One of the easiest ways to determine if ASR rules are already enabled—and, is through a PowerShell cmdlet, Get-MpPreference.</span></span>
<span data-ttu-id="69f42-142">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="69f42-142">Here's an example:</span></span>

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="skaffa mppreference-skript":::

<span data-ttu-id="69f42-144">Det finns flera ASR-regler aktiva, med olika konfigurerade åtgärder.</span><span class="sxs-lookup"><span data-stu-id="69f42-144">There are multiple ASR rules active, with different configured actions.</span></span>

<span data-ttu-id="69f42-145">Om du vill visa informationen om ASR-regler ovan kan du använda egenskaperna **AttackSurfaceReductionRules_Ids** och/eller **AttackSurfaceReductionRules_Actions**.</span><span class="sxs-lookup"><span data-stu-id="69f42-145">To expand the above information on ASR rules, you can use the properties **AttackSurfaceReductionRules_Ids** and/or **AttackSurfaceReductionRules_Actions**.</span></span>

<span data-ttu-id="69f42-146">Exempel:</span><span class="sxs-lookup"><span data-stu-id="69f42-146">Example:</span></span>

<span data-ttu-id="69f42-147">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span><span class="sxs-lookup"><span data-stu-id="69f42-147">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span></span>

:::image type="content" source="images/getmpref-examplenew.png" alt-text="exempel på hämta slutledning":::

<span data-ttu-id="69f42-149">Ovan visas alla ID:er för ASR-regler som har en annan inställning än 0 (Ej konfigurerad).</span><span class="sxs-lookup"><span data-stu-id="69f42-149">The above shows all the IDs for ASR rules that have a setting different from 0 (Not Configured).</span></span>

<span data-ttu-id="69f42-150">Nästa steg är att lista de faktiska åtgärderna (block eller granskning) som varje regel är konfigurerad med.</span><span class="sxs-lookup"><span data-stu-id="69f42-150">The next step is then to list the actual actions (Block or Audit) that each rule is configured with.</span></span> 

<span data-ttu-id="69f42-151">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span><span class="sxs-lookup"><span data-stu-id="69f42-151">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span></span>

:::image type="content" source="images/getmpref-example2new.png" alt-text="get mppreference example2":::

### <a name="querying-blocking-and-auditing-events"></a><span data-ttu-id="69f42-153">Frågeblockering och granskningshändelser</span><span class="sxs-lookup"><span data-stu-id="69f42-153">Querying blocking and auditing events</span></span>
<span data-ttu-id="69f42-154">ASR-regelhändelser kan visas i Windows Defender loggen.</span><span class="sxs-lookup"><span data-stu-id="69f42-154">ASR rule events can be viewed within the Windows Defender log.</span></span>

<span data-ttu-id="69f42-155">Du kommer åt det genom Windows Loggboken och bläddra till **Program-** och  >  **tjänstloggar Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operational**.</span><span class="sxs-lookup"><span data-stu-id="69f42-155">To access it, open Windows Event Viewer, and browse to **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

:::image type="content" source="images/eventviewerscrnew.png" alt-text="loggboken scr":::

## <a name="microsoft-defender-malware-protection-logs"></a><span data-ttu-id="69f42-157">Skyddsloggar för Microsoft Defender Malware</span><span class="sxs-lookup"><span data-stu-id="69f42-157">Microsoft Defender Malware Protection Logs</span></span>
<span data-ttu-id="69f42-158">Du kan också visa regelhändelser via det Microsoft Defender Antivirus dedikerade kommandoradsverktyget, som kallas , som kan användas för att hantera och konfigurera, och automatisera `*mpcmdrun.exe*` uppgifter vid behov.</span><span class="sxs-lookup"><span data-stu-id="69f42-158">You can also view rule events through the Microsoft Defender Antivirus dedicated command-line tool, called `*mpcmdrun.exe*`, that can be used to manage and configure, and automate tasks if needed.</span></span>

<span data-ttu-id="69f42-159">Du hittar det här verktyget i *%ProgramFiles%\Windows Defender\MpCmdRun.exe*.</span><span class="sxs-lookup"><span data-stu-id="69f42-159">You can find this utility in *%ProgramFiles%\Windows Defender\MpCmdRun.exe*.</span></span> <span data-ttu-id="69f42-160">Du måste köra den från en upphöjd kommandotolk (det vill säga kör som administratör).</span><span class="sxs-lookup"><span data-stu-id="69f42-160">You must run it from an elevated command prompt (that is, run as Admin).</span></span>

<span data-ttu-id="69f42-161">Om du vill generera supportinformation skriver *duMpCmdRun.exe -getfiles*.</span><span class="sxs-lookup"><span data-stu-id="69f42-161">To generate the support information, type *MpCmdRun.exe -getfiles*.</span></span> <span data-ttu-id="69f42-162">Efter ett tag paketeras flera loggar till ett arkiv (MpSupportFiles.cab) och görs tillgängliga i *C:\ProgramData\Microsoft\Windows Defender\Support.*</span><span class="sxs-lookup"><span data-stu-id="69f42-162">After a while, several logs will be packaged into an archive (MpSupportFiles.cab) and made available in *C:\ProgramData\Microsoft\Windows Defender\Support*.</span></span>

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="skyddsloggar för skadlig programvara":::

<span data-ttu-id="69f42-164">Extrahera det arkivet så har du många filer tillgängliga för felsökning.</span><span class="sxs-lookup"><span data-stu-id="69f42-164">Extract that archive and you'll have many files available for troubleshooting purposes.</span></span>

<span data-ttu-id="69f42-165">De mest relevanta filerna är följande:</span><span class="sxs-lookup"><span data-stu-id="69f42-165">The most relevant files are as follows:</span></span>

- <span data-ttu-id="69f42-166">**MPOperationalEvents.txt** – Den här filen innehåller samma informationsnivå som finns i Loggboken Windows Defender filens driftlogg.</span><span class="sxs-lookup"><span data-stu-id="69f42-166">**MPOperationalEvents.txt** - This file contains same level of information found in Event Viewer for Windows Defender’s Operational log.</span></span>
- <span data-ttu-id="69f42-167">**MPRegistry.txt** – I den här filen kan du analysera alla Windows Defender konfigurationer från det att supportloggarna har fångats in.</span><span class="sxs-lookup"><span data-stu-id="69f42-167">**MPRegistry.txt** – In this file you will can analyze all the current Windows Defender configurations, from the moment the support logs were captured.</span></span>
- <span data-ttu-id="69f42-168">**MPLog.txt** – Den här loggen innehåller mer utförlig information om alla åtgärder/åtgärder i Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="69f42-168">**MPLog.txt** – This log contains more verbose information about all the actions/operations of the Windows Defender.</span></span>
