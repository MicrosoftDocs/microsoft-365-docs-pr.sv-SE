---
title: Vidta åtgärder för frågor om avancerad jakt fråga i Microsoft Threat Protection
description: Adressera hot och berörda till gångar snabbt och påverkas av dina frågor
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, åtgärd
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 7250feffa69cc1a6cc37908a599dff0fab6c5e6c
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429665"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="74a25-104">Vidta åtgärder för avancerade frågor</span><span class="sxs-lookup"><span data-stu-id="74a25-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="74a25-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="74a25-105">**Applies to:**</span></span>
- <span data-ttu-id="74a25-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="74a25-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="74a25-107">Du kan snabbt ta med hot eller adresser som äventyrade till gångar som du hittar i [Avancerad jakt](advanced-hunting-overview.md) med kraftfulla och omfattande åtgärds alternativ.</span><span class="sxs-lookup"><span data-stu-id="74a25-107">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="74a25-108">Med dessa alternativ kan du:</span><span class="sxs-lookup"><span data-stu-id="74a25-108">With these options, you can:</span></span>

- <span data-ttu-id="74a25-109">Utföra olika åtgärder på enheter</span><span class="sxs-lookup"><span data-stu-id="74a25-109">Take various actions on devices</span></span>
- <span data-ttu-id="74a25-110">Quarantine-filer</span><span class="sxs-lookup"><span data-stu-id="74a25-110">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="74a25-111">Nödvändiga behörigheter</span><span class="sxs-lookup"><span data-stu-id="74a25-111">Required permissions</span></span>
<span data-ttu-id="74a25-112">För att kunna vidta åtgärder genom avancerad jakt måste du ha en roll i Microsoft Defender ATP med [behörigheter för att skicka reparations åtgärder på enheter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span><span class="sxs-lookup"><span data-stu-id="74a25-112">To be able to take action through advanced hunting, you need a role in Microsoft Defender ATP with [permissions to submit remediation actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="74a25-113">Om du inte kan vidta en åtgärd kontaktar du en global administratör för att få följande behörighet:</span><span class="sxs-lookup"><span data-stu-id="74a25-113">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="74a25-114">*Aktiva reparations åtgärder > hot och sårbarhet hantering – reparations hantering*</span><span class="sxs-lookup"><span data-stu-id="74a25-114">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="74a25-115">Utföra olika åtgärder på enheter</span><span class="sxs-lookup"><span data-stu-id="74a25-115">Take various actions on devices</span></span>
<span data-ttu-id="74a25-116">Du kan utföra följande åtgärder på enheter som identifieras av `DeviceId` kolumnen i frågans resultat:</span><span class="sxs-lookup"><span data-stu-id="74a25-116">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="74a25-117">Isolera berörda enheter för att innehålla en infektion eller förhindra att attacker kan flyttas senare</span><span class="sxs-lookup"><span data-stu-id="74a25-117">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="74a25-118">Samla in ett Forensic-paket för att få mer information</span><span class="sxs-lookup"><span data-stu-id="74a25-118">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="74a25-119">Kör en Antivirus sökning för att hitta och ta bort hot med de senaste säkerhets uppdateringarna</span><span class="sxs-lookup"><span data-stu-id="74a25-119">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="74a25-120">Starta en automatiserad undersökning för att kontrol lera och åtgärda hot på enheten och möjligen andra berörda enheter</span><span class="sxs-lookup"><span data-stu-id="74a25-120">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="74a25-121">Begränsa program körning till endast Microsoft-signerade körbara filer, förhindra efterföljande hot-aktiviteter genom att använda skadlig program vara eller andra obetrodda program</span><span class="sxs-lookup"><span data-stu-id="74a25-121">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="74a25-122">Om du vill veta mer om hur dessa svars åtgärder utförs via Microsoft Defender ATP [läser du om svars åtgärder på enheter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span><span class="sxs-lookup"><span data-stu-id="74a25-122">To learn more about how these response actions are performed through Microsoft Defender ATP, [read about response actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="74a25-123">Quarantine-filer</span><span class="sxs-lookup"><span data-stu-id="74a25-123">Quarantine files</span></span>
<span data-ttu-id="74a25-124">Du kan distribuera *karantän* åtgärden på filer så att de automatiskt satts i karantän när de påträffas.</span><span class="sxs-lookup"><span data-stu-id="74a25-124">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="74a25-125">När du väljer den här åtgärden kan du välja mellan följande kolumner för att identifiera vilka filer i frågeresultatet som ska visas:</span><span class="sxs-lookup"><span data-stu-id="74a25-125">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="74a25-126">`SHA1` – I de flesta avancerade jakt tabeller är detta SHA-1 för filen som påverkades av den registrerade åtgärden.</span><span class="sxs-lookup"><span data-stu-id="74a25-126">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="74a25-127">Om du till exempel kopierar en fil, blir detta den kopierade filen.</span><span class="sxs-lookup"><span data-stu-id="74a25-127">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="74a25-128">`InitiatingProcessSHA1` – I de flesta avancerade jakt tabeller är detta den fil som är ansvarig för att inleda den inspelade åtgärden.</span><span class="sxs-lookup"><span data-stu-id="74a25-128">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="74a25-129">Om till exempel en underordnad process är det den överordnade processen.</span><span class="sxs-lookup"><span data-stu-id="74a25-129">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="74a25-130">`SHA256` — Det här är SHA-256-motsvarigheten till filen som identifieras av `SHA1` kolumnen.</span><span class="sxs-lookup"><span data-stu-id="74a25-130">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="74a25-131">`InitiatingProcessSHA256` — Det här är SHA-256-motsvarigheten till filen som identifieras av `InitiatingProcessSHA1` kolumnen.</span><span class="sxs-lookup"><span data-stu-id="74a25-131">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="74a25-132">Läs mer om hur du gör för att få mer information om hur karantäns åtgärder vidtas och hur filer kan återställas [med svars åtgärder på filer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span><span class="sxs-lookup"><span data-stu-id="74a25-132">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="74a25-133">Om du vill söka efter filer och karantän kan frågeresultatet innehålla `DeviceId` värden som enhets identifierare.</span><span class="sxs-lookup"><span data-stu-id="74a25-133">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="74a25-134">Utför åtgärd</span><span class="sxs-lookup"><span data-stu-id="74a25-134">Take action</span></span>
<span data-ttu-id="74a25-135">Om du vill använda någon av de beskrivna åtgärderna markerar du en eller flera poster i frågeresultatet och väljer sedan **vidta åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="74a25-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="74a25-136">En guide vägleder dig genom processen att välja och sedan skicka dina önskade åtgärder.</span><span class="sxs-lookup"><span data-stu-id="74a25-136">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Bild av den valda posten med panelen för kontroll av posten](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="74a25-138">Gransknings åtgärder som utförs</span><span class="sxs-lookup"><span data-stu-id="74a25-138">Review actions taken</span></span>
<span data-ttu-id="74a25-139">Varje åtgärd registreras individuellt i [Åtgärds centret](mtp-action-center.md) under **Åtgärds Center**  >  **Historik** ([Security.Microsoft.com/Action-Center/History](https://security.microsoft.com/action-center/history)).</span><span class="sxs-lookup"><span data-stu-id="74a25-139">Each action is individually recorded in the [action center](mtp-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="74a25-140">Gå till åtgärds centret för att kontrol lera status för varje åtgärd.</span><span class="sxs-lookup"><span data-stu-id="74a25-140">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="74a25-141">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="74a25-141">Related topics</span></span>
- [<span data-ttu-id="74a25-142">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="74a25-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="74a25-143">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="74a25-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="74a25-144">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="74a25-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="74a25-145">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="74a25-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="74a25-146">Översikt över åtgärds centret</span><span class="sxs-lookup"><span data-stu-id="74a25-146">Action center overview</span></span>](mtp-action-center.md)
