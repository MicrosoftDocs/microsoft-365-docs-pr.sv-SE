---
title: Vidta åtgärder för avancerade frågeresultat för sökning i Microsoft 365 Defender
description: Hantera snabbt hot och påverkade tillgångar i dina avancerade frågeresultat för sökning
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, take action
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 15eebbba102640a92f9c7712194aaef685a96cfb
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952614"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="dc340-104">Vidta åtgärder för avancerade frågeresultat för sökning</span><span class="sxs-lookup"><span data-stu-id="dc340-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="dc340-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="dc340-105">**Applies to:**</span></span>
- <span data-ttu-id="dc340-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dc340-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="dc340-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="dc340-107">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="dc340-108">Du kan snabbt innehålla hot eller adresser komprometterade tillgångar som du hittar i [avancerad sökning](advanced-hunting-overview.md) med hjälp av kraftfulla och omfattande åtgärdsalternativ.</span><span class="sxs-lookup"><span data-stu-id="dc340-108">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="dc340-109">Med de här alternativen kan du:</span><span class="sxs-lookup"><span data-stu-id="dc340-109">With these options, you can:</span></span>

- <span data-ttu-id="dc340-110">Vidta olika åtgärder på enheter</span><span class="sxs-lookup"><span data-stu-id="dc340-110">Take various actions on devices</span></span>
- <span data-ttu-id="dc340-111">Sätt filer i karantän</span><span class="sxs-lookup"><span data-stu-id="dc340-111">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="dc340-112">Behörighet som krävs</span><span class="sxs-lookup"><span data-stu-id="dc340-112">Required permissions</span></span>
<span data-ttu-id="dc340-113">För att kunna vidta åtgärder via avancerad sökning behöver du en roll i Microsoft Defender för Endpoint med behörighet att skicka [åtgärder på enheter.](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)</span><span class="sxs-lookup"><span data-stu-id="dc340-113">To be able to take action through advanced hunting, you need a role in Microsoft Defender for Endpoint with [permissions to submit remediation actions on devices](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="dc340-114">Om du inte kan vidta någon åtgärd kontaktar du en global administratör för att få följande behörighet:</span><span class="sxs-lookup"><span data-stu-id="dc340-114">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="dc340-115">*Aktiva åtgärdsåtgärder > hantering av hot och sårbarhet – åtgärdshantering*</span><span class="sxs-lookup"><span data-stu-id="dc340-115">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="dc340-116">Vidta olika åtgärder på enheter</span><span class="sxs-lookup"><span data-stu-id="dc340-116">Take various actions on devices</span></span>
<span data-ttu-id="dc340-117">Du kan vidta följande åtgärder på enheter som identifieras av `DeviceId` kolumnen i frågeresultatet:</span><span class="sxs-lookup"><span data-stu-id="dc340-117">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="dc340-118">Isolera påverkade enheter för att isolera en smitta eller förhindra attacker från att röra sig fritt</span><span class="sxs-lookup"><span data-stu-id="dc340-118">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="dc340-119">Samla in undersökningspaket för att få mer teknisk information</span><span class="sxs-lookup"><span data-stu-id="dc340-119">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="dc340-120">Kör en antivirussökning för att hitta och ta bort hot med de senaste säkerhetsintelligensuppdateringarna</span><span class="sxs-lookup"><span data-stu-id="dc340-120">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="dc340-121">Initiera en automatiserad undersökning för att kontrollera och åtgärda hot på enheten och eventuellt andra enheter som påverkas</span><span class="sxs-lookup"><span data-stu-id="dc340-121">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="dc340-122">Begränsa programkörningen till endast Microsoft-signerade körbara filer, förhindra efterföljande aktivitet med hot genom skadlig programvara eller andra körbara filer som inte är betrodda</span><span class="sxs-lookup"><span data-stu-id="dc340-122">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="dc340-123">Mer information om hur dessa svarsåtgärder utförs via Microsoft Defender för Slutpunkt finns [i om svarsåtgärder på enheter.](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)</span><span class="sxs-lookup"><span data-stu-id="dc340-123">To learn more about how these response actions are performed through Microsoft Defender for Endpoint, [read about response actions on devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="dc340-124">Sätt filer i karantän</span><span class="sxs-lookup"><span data-stu-id="dc340-124">Quarantine files</span></span>
<span data-ttu-id="dc340-125">Du kan distribuera *karantänåtgärden* på filer så att de automatiskt sätts i karantän när de påträffas.</span><span class="sxs-lookup"><span data-stu-id="dc340-125">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="dc340-126">När du väljer den här åtgärden kan du välja mellan följande kolumner för att identifiera vilka filer i frågan som ska sätts i karantän:</span><span class="sxs-lookup"><span data-stu-id="dc340-126">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="dc340-127">`SHA1` — I de flesta avancerade tabeller för sökning är det SHA-1 i filen som påverkades av den inspelade åtgärden.</span><span class="sxs-lookup"><span data-stu-id="dc340-127">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="dc340-128">Om en fil till exempel kopierades är det den kopierade filen.</span><span class="sxs-lookup"><span data-stu-id="dc340-128">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="dc340-129">`InitiatingProcessSHA1` — I de flesta avancerade söktabeller är det här filen som ansvarar för att initiera den inspelade åtgärden.</span><span class="sxs-lookup"><span data-stu-id="dc340-129">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="dc340-130">Om till exempel en underordnad process startades skulle det här vara den överordnade processen.</span><span class="sxs-lookup"><span data-stu-id="dc340-130">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="dc340-131">`SHA256` — Det här är SHA-256-motsvarigheten till filen som identifieras av `SHA1` kolumnen.</span><span class="sxs-lookup"><span data-stu-id="dc340-131">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="dc340-132">`InitiatingProcessSHA256` — Det här är SHA-256-motsvarigheten till filen som identifieras av `InitiatingProcessSHA1` kolumnen.</span><span class="sxs-lookup"><span data-stu-id="dc340-132">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="dc340-133">Mer information om hur åtgärder i karantän vidtas och hur filer kan återställas finns [i svarsåtgärder på filer.](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)</span><span class="sxs-lookup"><span data-stu-id="dc340-133">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="dc340-134">För att hitta filer och sätta dem i karantän bör frågeresultatet även `DeviceId` innehålla värden som enhetsidentifierare.</span><span class="sxs-lookup"><span data-stu-id="dc340-134">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="dc340-135">Vidta åtgärder</span><span class="sxs-lookup"><span data-stu-id="dc340-135">Take action</span></span>
<span data-ttu-id="dc340-136">Om du vill utföra någon av de åtgärder som beskrivs markerar du en eller flera poster i frågeresultatet och väljer **sedan Vidta åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="dc340-136">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="dc340-137">En guide vägleder dig genom processen med att välja och sedan skicka dina föredragna åtgärder.</span><span class="sxs-lookup"><span data-stu-id="dc340-137">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Bild av markerad post med panel för att kontrollera posten](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="dc340-139">Granska åtgärder som har vidtagits</span><span class="sxs-lookup"><span data-stu-id="dc340-139">Review actions taken</span></span>
<span data-ttu-id="dc340-140">Varje åtgärd registreras individuellt i [åtgärdscenter](m365d-action-center.md) under **Historik för åtgärdscenter**  >   [(security.microsoft.com/action-center/history).](https://security.microsoft.com/action-center/history)</span><span class="sxs-lookup"><span data-stu-id="dc340-140">Each action is individually recorded in the [action center](m365d-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="dc340-141">Gå till åtgärdscenter för att kontrollera status för varje åtgärd.</span><span class="sxs-lookup"><span data-stu-id="dc340-141">Go to the action center to check the status of each action.</span></span>
 
>[!NOTE]
><span data-ttu-id="dc340-142">Vissa tabeller i den här artikeln kanske inte är tillgängliga i Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="dc340-142">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="dc340-143">[Aktivera Microsoft 365 Defender för](m365d-enable.md) att leta efter hot med hjälp av fler datakällor.</span><span class="sxs-lookup"><span data-stu-id="dc340-143">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="dc340-144">Du kan flytta dina avancerade arbetsflöden för sökning från Microsoft Defender för Slutpunkt till Microsoft 365 Defender genom att följa stegen i Migrera avancerade sökfrågor från [Microsoft Defender för Slutpunkt.](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="dc340-144">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="dc340-145">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="dc340-145">Related topics</span></span>
- [<span data-ttu-id="dc340-146">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="dc340-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="dc340-147">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="dc340-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="dc340-148">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="dc340-148">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="dc340-149">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="dc340-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="dc340-150">Översikt över Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="dc340-150">Action center overview</span></span>](m365d-action-center.md)
