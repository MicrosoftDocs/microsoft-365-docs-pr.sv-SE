---
title: Vidta åtgärder för avancerade frågeresultat för sökning i Microsoft 365 Defender
description: Hantera snabbt hot och påverkade tillgångar i dina avancerade frågeresultat för sökfrågor
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, vidta åtgärder
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9e8ad544cfe17d0d8e5c895e208b42ec56555565
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932184"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="8cc29-104">Vidta åtgärder för avancerade frågeresultat för sökning</span><span class="sxs-lookup"><span data-stu-id="8cc29-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8cc29-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="8cc29-105">**Applies to:**</span></span>
- <span data-ttu-id="8cc29-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8cc29-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="8cc29-107">Du kan snabbt innehålla hot eller hantera komprometterade tillgångar som du hittar på [avancerad](advanced-hunting-overview.md) sökning med hjälp av kraftfulla och omfattande åtgärdsalternativ.</span><span class="sxs-lookup"><span data-stu-id="8cc29-107">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="8cc29-108">Med dessa alternativ kan du:</span><span class="sxs-lookup"><span data-stu-id="8cc29-108">With these options, you can:</span></span>

- <span data-ttu-id="8cc29-109">Vidta olika åtgärder på enheter</span><span class="sxs-lookup"><span data-stu-id="8cc29-109">Take various actions on devices</span></span>
- <span data-ttu-id="8cc29-110">Sätt filer i karantän</span><span class="sxs-lookup"><span data-stu-id="8cc29-110">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="8cc29-111">Behörighet som krävs</span><span class="sxs-lookup"><span data-stu-id="8cc29-111">Required permissions</span></span>
<span data-ttu-id="8cc29-112">För att kunna vidta åtgärder via avancerad sökning behöver du en roll i Microsoft Defender för Endpoint med behörighet att skicka [åtgärder på enheter.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)</span><span class="sxs-lookup"><span data-stu-id="8cc29-112">To be able to take action through advanced hunting, you need a role in Microsoft Defender for Endpoint with [permissions to submit remediation actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="8cc29-113">Om du inte kan vidta någon åtgärd kan du kontakta en global administratör om att få följande behörighet:</span><span class="sxs-lookup"><span data-stu-id="8cc29-113">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="8cc29-114">*Aktiva åtgärder för > hantering av hot och sårbarhet – åtgärdshantering*</span><span class="sxs-lookup"><span data-stu-id="8cc29-114">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="8cc29-115">Vidta olika åtgärder på enheter</span><span class="sxs-lookup"><span data-stu-id="8cc29-115">Take various actions on devices</span></span>
<span data-ttu-id="8cc29-116">Du kan vidta följande åtgärder på enheter som identifieras av `DeviceId` kolumnen i frågeresultat:</span><span class="sxs-lookup"><span data-stu-id="8cc29-116">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="8cc29-117">Isolera påverkade enheter som innehåller en smitta eller förhindra attacker från att röra sig fritt</span><span class="sxs-lookup"><span data-stu-id="8cc29-117">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="8cc29-118">Samla in undersökningspaket för att få mer teknisk information</span><span class="sxs-lookup"><span data-stu-id="8cc29-118">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="8cc29-119">Kör en antivirussökning för att hitta och ta bort hot med de senaste säkerhetsintelligensuppdateringarna</span><span class="sxs-lookup"><span data-stu-id="8cc29-119">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="8cc29-120">Initiera en automatiserad undersökning för att kontrollera och åtgärda hot på enheten och eventuellt andra enheter som påverkas</span><span class="sxs-lookup"><span data-stu-id="8cc29-120">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="8cc29-121">Begränsa programkörningen till endast Microsoft-signerade körbara filer, förhindra efterföljande hotaktivitet genom skadlig kod eller andra körbara filer som inte är betrodda</span><span class="sxs-lookup"><span data-stu-id="8cc29-121">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="8cc29-122">Mer information om hur dessa svarsåtgärder utförs via Microsoft Defender för Slutpunkt finns [i artikeln om svarsåtgärder på enheter.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)</span><span class="sxs-lookup"><span data-stu-id="8cc29-122">To learn more about how these response actions are performed through Microsoft Defender for Endpoint, [read about response actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="8cc29-123">Sätt filer i karantän</span><span class="sxs-lookup"><span data-stu-id="8cc29-123">Quarantine files</span></span>
<span data-ttu-id="8cc29-124">Du kan distribuera *karantänåtgärden* för filer så att de sätts i karantän automatiskt när de påträffas.</span><span class="sxs-lookup"><span data-stu-id="8cc29-124">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="8cc29-125">När du väljer den här åtgärden kan du välja mellan följande kolumner för att identifiera vilka filer i frågan som ska karantäns:</span><span class="sxs-lookup"><span data-stu-id="8cc29-125">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="8cc29-126">`SHA1` — I de flesta avancerade söktabeller är det SHA-1 i filen som påverkades av den inspelade åtgärden.</span><span class="sxs-lookup"><span data-stu-id="8cc29-126">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="8cc29-127">Om en fil till exempel kopierades är det här den kopierade filen.</span><span class="sxs-lookup"><span data-stu-id="8cc29-127">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="8cc29-128">`InitiatingProcessSHA1` – I de flesta avancerade söktabeller är det den fil som ansvarar för att initiera den inspelade åtgärden.</span><span class="sxs-lookup"><span data-stu-id="8cc29-128">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="8cc29-129">Om till exempel en underordnad process startades, skulle detta vara den överordnade processen.</span><span class="sxs-lookup"><span data-stu-id="8cc29-129">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="8cc29-130">`SHA256` — Det här är SHA-256-motsvarigheten till filen som identifieras av `SHA1` kolumnen.</span><span class="sxs-lookup"><span data-stu-id="8cc29-130">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="8cc29-131">`InitiatingProcessSHA256` — Det här är SHA-256-motsvarigheten till filen som identifieras av `InitiatingProcessSHA1` kolumnen.</span><span class="sxs-lookup"><span data-stu-id="8cc29-131">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="8cc29-132">Mer information om hur åtgärder i karantän vidtas och hur filer kan återställas finns [i svarsåtgärder för filer.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)</span><span class="sxs-lookup"><span data-stu-id="8cc29-132">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="8cc29-133">För att hitta filer och sätta dem i karantän bör frågeresultaten också `DeviceId` innehålla värden som enhetsidentifierare.</span><span class="sxs-lookup"><span data-stu-id="8cc29-133">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="8cc29-134">Vidta åtgärder</span><span class="sxs-lookup"><span data-stu-id="8cc29-134">Take action</span></span>
<span data-ttu-id="8cc29-135">Om du vill utföra någon av de åtgärder som beskrivs markerar du en eller flera poster i frågeresultatet och väljer **sedan Vidta åtgärder.**</span><span class="sxs-lookup"><span data-stu-id="8cc29-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="8cc29-136">En guide vägleder dig genom processen att välja och sedan skicka dina föredragna åtgärder.</span><span class="sxs-lookup"><span data-stu-id="8cc29-136">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Bild på markerad post med panel för att kontrollera posten](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="8cc29-138">Granska åtgärder som har vidtagits</span><span class="sxs-lookup"><span data-stu-id="8cc29-138">Review actions taken</span></span>
<span data-ttu-id="8cc29-139">Varje åtgärd registreras individuellt i [åtgärdscenter](mtp-action-center.md) under **Historik för åtgärdscenter**  >   [(security.microsoft.com/action-center/history).](https://security.microsoft.com/action-center/history)</span><span class="sxs-lookup"><span data-stu-id="8cc29-139">Each action is individually recorded in the [action center](mtp-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="8cc29-140">Gå till åtgärdscenter och kontrollera status för varje åtgärd.</span><span class="sxs-lookup"><span data-stu-id="8cc29-140">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="8cc29-141">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="8cc29-141">Related topics</span></span>
- [<span data-ttu-id="8cc29-142">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="8cc29-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8cc29-143">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="8cc29-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8cc29-144">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="8cc29-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="8cc29-145">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="8cc29-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8cc29-146">Översikt över Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="8cc29-146">Action center overview</span></span>](mtp-action-center.md)
