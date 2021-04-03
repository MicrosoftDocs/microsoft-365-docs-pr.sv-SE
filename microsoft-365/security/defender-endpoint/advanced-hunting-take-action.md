---
title: Vidta åtgärder för avancerade frågeresultat efter sökning i Microsoft Threat Protection
description: Hantera snabbt hot och påverkade tillgångar i dina avancerade frågeresultat för sökning
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, custom detections, schema, kusto, avoid timeout, command lines, process id
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: d1dbe226cef5e94b36fcd6c35b839118b200f85e
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500538"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="52fd7-104">Vidta åtgärder för avancerade frågeresultat för sökning</span><span class="sxs-lookup"><span data-stu-id="52fd7-104">Take action on advanced hunting query results</span></span>

<span data-ttu-id="52fd7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="52fd7-105">**Applies to:**</span></span>
- [<span data-ttu-id="52fd7-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="52fd7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="52fd7-107">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="52fd7-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="52fd7-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="52fd7-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="52fd7-109">Du kan snabbt innehålla hot eller adresser komprometterade tillgångar som du hittar i [avancerad sökning](advanced-hunting-overview.md) med hjälp av kraftfulla och omfattande åtgärdsalternativ.</span><span class="sxs-lookup"><span data-stu-id="52fd7-109">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="52fd7-110">Med de här alternativen kan du:</span><span class="sxs-lookup"><span data-stu-id="52fd7-110">With these options, you can:</span></span>

- <span data-ttu-id="52fd7-111">Vidta olika åtgärder på enheter</span><span class="sxs-lookup"><span data-stu-id="52fd7-111">Take various actions on devices</span></span>
- <span data-ttu-id="52fd7-112">Sätt filer i karantän</span><span class="sxs-lookup"><span data-stu-id="52fd7-112">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="52fd7-113">Behörighet som krävs</span><span class="sxs-lookup"><span data-stu-id="52fd7-113">Required permissions</span></span>

<span data-ttu-id="52fd7-114">För att kunna vidta åtgärder via avancerad sökning måste du ha en roll i Defender för Endpoint med behörighet att skicka [åtgärder på enheter](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options).</span><span class="sxs-lookup"><span data-stu-id="52fd7-114">To be able to take action through advanced hunting, you need a role in Defender for Endpoint with [permissions to submit remediation actions on devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options).</span></span> <span data-ttu-id="52fd7-115">Om du inte kan vidta någon åtgärd kontaktar du en global administratör för att få följande behörighet:</span><span class="sxs-lookup"><span data-stu-id="52fd7-115">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="52fd7-116">*Aktiva åtgärdsåtgärder > hantering av hot och sårbarhet – åtgärdshantering*</span><span class="sxs-lookup"><span data-stu-id="52fd7-116">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="52fd7-117">Vidta olika åtgärder på enheter</span><span class="sxs-lookup"><span data-stu-id="52fd7-117">Take various actions on devices</span></span>

<span data-ttu-id="52fd7-118">Du kan utföra följande åtgärder på enheter som identifieras av `DeviceId` kolumnen i frågeresultatet:</span><span class="sxs-lookup"><span data-stu-id="52fd7-118">You can take the following actions on devices identified by the `DeviceId` column in your query results:</span></span>

- <span data-ttu-id="52fd7-119">Isolera påverkade enheter för att isolera en smitta eller förhindra attacker från att röra sig fritt</span><span class="sxs-lookup"><span data-stu-id="52fd7-119">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="52fd7-120">Samla in undersökningspaket för att få mer teknisk information</span><span class="sxs-lookup"><span data-stu-id="52fd7-120">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="52fd7-121">Kör en antivirussökning för att hitta och ta bort hot med de senaste säkerhetsintelligensuppdateringarna</span><span class="sxs-lookup"><span data-stu-id="52fd7-121">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="52fd7-122">Initiera en automatiserad undersökning för att kontrollera och åtgärda hot på enheten och eventuellt andra enheter som påverkas</span><span class="sxs-lookup"><span data-stu-id="52fd7-122">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="52fd7-123">Begränsa programkörningen till endast Microsoft-signerade körbara filer, förhindra efterföljande aktivitet med hot genom skadlig programvara eller andra körbara filer som inte är betrodda</span><span class="sxs-lookup"><span data-stu-id="52fd7-123">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="52fd7-124">Mer information om hur de här svarsåtgärderna utförs via Defender för Slutpunkt finns [i om svarsåtgärder på enheter.](respond-machine-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="52fd7-124">To learn more about how these response actions are performed through Defender for Endpoint, [read about response actions on devices](respond-machine-alerts.md).</span></span>

## <a name="quarantine-files"></a><span data-ttu-id="52fd7-125">Sätt filer i karantän</span><span class="sxs-lookup"><span data-stu-id="52fd7-125">Quarantine files</span></span>

<span data-ttu-id="52fd7-126">Du kan distribuera *karantänåtgärden* på filer så att de automatiskt sätts i karantän när de påträffas.</span><span class="sxs-lookup"><span data-stu-id="52fd7-126">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="52fd7-127">När du väljer den här åtgärden kan du välja mellan följande kolumner för att identifiera vilka filer i frågan som ska sätts i karantän:</span><span class="sxs-lookup"><span data-stu-id="52fd7-127">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="52fd7-128">`SHA1` — I de flesta avancerade tabeller för sökning är det SHA-1 i filen som påverkades av den inspelade åtgärden.</span><span class="sxs-lookup"><span data-stu-id="52fd7-128">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="52fd7-129">Om en fil till exempel kopierades är det den kopierade filen.</span><span class="sxs-lookup"><span data-stu-id="52fd7-129">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="52fd7-130">`InitiatingProcessSHA1` — I de flesta avancerade söktabeller är det här filen som ansvarar för att initiera den inspelade åtgärden.</span><span class="sxs-lookup"><span data-stu-id="52fd7-130">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="52fd7-131">Om till exempel en underordnad process startades skulle det här vara den överordnade processen.</span><span class="sxs-lookup"><span data-stu-id="52fd7-131">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="52fd7-132">`SHA256` — Det här är SHA-256-motsvarigheten till filen som identifieras av `SHA1` kolumnen.</span><span class="sxs-lookup"><span data-stu-id="52fd7-132">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="52fd7-133">`InitiatingProcessSHA256` — Det här är SHA-256-motsvarigheten till filen som identifieras av `InitiatingProcessSHA1` kolumnen.</span><span class="sxs-lookup"><span data-stu-id="52fd7-133">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="52fd7-134">Mer information om hur åtgärder i karantän vidtas och hur filer kan återställas finns [i svarsåtgärder på filer.](respond-file-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="52fd7-134">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](respond-file-alerts.md).</span></span>

>[!NOTE]
><span data-ttu-id="52fd7-135">För att hitta filer och sätta dem i karantän bör frågeresultatet även `DeviceId` innehålla värden som enhetsidentifierare.</span><span class="sxs-lookup"><span data-stu-id="52fd7-135">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="52fd7-136">Vidta åtgärder</span><span class="sxs-lookup"><span data-stu-id="52fd7-136">Take action</span></span>

<span data-ttu-id="52fd7-137">Om du vill utföra någon av de åtgärder som beskrivs markerar du en eller flera poster i frågeresultatet och väljer **sedan Vidta åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="52fd7-137">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="52fd7-138">En guide vägleder dig genom processen med att välja och sedan skicka dina föredragna åtgärder.</span><span class="sxs-lookup"><span data-stu-id="52fd7-138">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Bild av markerad post med panel för att kontrollera posten](images/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="52fd7-140">Granska åtgärder som har vidtagits</span><span class="sxs-lookup"><span data-stu-id="52fd7-140">Review actions taken</span></span>

<span data-ttu-id="52fd7-141">Varje åtgärd registreras individuellt i åtgärdscenter, under **Historik för åtgärdscenter**  >   ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span><span class="sxs-lookup"><span data-stu-id="52fd7-141">Each action is individually recorded in the action center, under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="52fd7-142">Gå till åtgärdscenter för att kontrollera status för varje åtgärd.</span><span class="sxs-lookup"><span data-stu-id="52fd7-142">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="52fd7-143">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="52fd7-143">Related topics</span></span>

- [<span data-ttu-id="52fd7-144">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="52fd7-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="52fd7-145">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="52fd7-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="52fd7-146">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="52fd7-146">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="52fd7-147">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="52fd7-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="52fd7-148">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="52fd7-148">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="52fd7-149">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="52fd7-149">Custom detections overview</span></span>](overview-custom-detections.md)
