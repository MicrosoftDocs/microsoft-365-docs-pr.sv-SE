---
title: Vidta åtgärder för avancerade jaktfrågeresultat i Microsoft Threat Protection
description: Ta snabbt itu med hot och påverkade tillgångar i dina avancerade jaktfrågeresultat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, vidta åtgärder
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4ebf220472db69d48127b805256e15246bd400cb
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552754"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="c44bf-104">Vidta åtgärder för avancerade jaktfrågeresultat</span><span class="sxs-lookup"><span data-stu-id="c44bf-104">Take action on advanced hunting query results</span></span>

<span data-ttu-id="c44bf-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="c44bf-105">**Applies to:**</span></span>
- <span data-ttu-id="c44bf-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="c44bf-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="c44bf-107">Du kan snabbt innehålla hot eller hantera komprometterade tillgångar som du hittar i [avancerad jakt](advanced-hunting-overview.md) med kraftfulla och omfattande åtgärdsalternativ.</span><span class="sxs-lookup"><span data-stu-id="c44bf-107">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="c44bf-108">Med dessa alternativ kan du:</span><span class="sxs-lookup"><span data-stu-id="c44bf-108">With these options, you can:</span></span>

- <span data-ttu-id="c44bf-109">Vidta olika åtgärder på enheter</span><span class="sxs-lookup"><span data-stu-id="c44bf-109">Take various actions on devices</span></span>
- <span data-ttu-id="c44bf-110">Karantänfiler</span><span class="sxs-lookup"><span data-stu-id="c44bf-110">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="c44bf-111">Nödvändiga behörigheter</span><span class="sxs-lookup"><span data-stu-id="c44bf-111">Required permissions</span></span>
<span data-ttu-id="c44bf-112">För att kunna vidta åtgärder genom avancerad jakt behöver du en roll i Microsoft Defender ATP med [behörighet att skicka åtgärder för reparation på enheter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span><span class="sxs-lookup"><span data-stu-id="c44bf-112">To be able to take action through advanced hunting, you need a role in Microsoft Defender ATP with [permissions to submit remediation actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="c44bf-113">Om du inte kan vidta åtgärder kontaktar du en global administratör om du vill ha följande behörighet:</span><span class="sxs-lookup"><span data-stu-id="c44bf-113">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="c44bf-114">*Aktiva åtgärder för reparation > hot- och sårbarhetshantering - Reparationshantering*</span><span class="sxs-lookup"><span data-stu-id="c44bf-114">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="c44bf-115">Vidta olika åtgärder på enheter</span><span class="sxs-lookup"><span data-stu-id="c44bf-115">Take various actions on devices</span></span>
<span data-ttu-id="c44bf-116">Du kan vidta följande åtgärder på enheter som identifieras av `DeviceId` kolumnen i frågeresultaten:</span><span class="sxs-lookup"><span data-stu-id="c44bf-116">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="c44bf-117">Isolera berörda enheter för att innehålla en infektion eller förhindra att attacker rör sig i sidled</span><span class="sxs-lookup"><span data-stu-id="c44bf-117">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="c44bf-118">Samla in utredningspaket för att få mer kriminalteknisk information</span><span class="sxs-lookup"><span data-stu-id="c44bf-118">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="c44bf-119">Kör en antivirussökning för att hitta och ta bort hot med hjälp av de senaste uppdateringarna av säkerhetsinformation</span><span class="sxs-lookup"><span data-stu-id="c44bf-119">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="c44bf-120">Starta en automatiserad undersökning för att kontrollera och åtgärda hot på enheten och eventuellt andra berörda enheter</span><span class="sxs-lookup"><span data-stu-id="c44bf-120">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="c44bf-121">Begränsa appkörningen till endast Microsoft-signerade körbara filer, förhindra efterföljande hotaktivitet via skadlig kod eller andra ej betrodda körbara filer</span><span class="sxs-lookup"><span data-stu-id="c44bf-121">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="c44bf-122">Om du vill veta mer om hur dessa svarsåtgärder utförs via Microsoft Defender ATP [läser du om svarsåtgärder på enheter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span><span class="sxs-lookup"><span data-stu-id="c44bf-122">To learn more about how these response actions are performed through Microsoft Defender ATP, [read about response actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="c44bf-123">Karantänfiler</span><span class="sxs-lookup"><span data-stu-id="c44bf-123">Quarantine files</span></span>
<span data-ttu-id="c44bf-124">Du kan distribuera *karantänåtgärden* på filer så att de automatiskt sätts i karantän när de påträffas.</span><span class="sxs-lookup"><span data-stu-id="c44bf-124">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="c44bf-125">När du väljer den här åtgärden kan du välja mellan följande kolumner för att identifiera vilka filer i frågeresultatet som ska sättas i karantän:</span><span class="sxs-lookup"><span data-stu-id="c44bf-125">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="c44bf-126">`SHA1`— I de mest avancerade jakttabellerna är detta SHA-1 i filen som påverkades av den registrerade åtgärden.</span><span class="sxs-lookup"><span data-stu-id="c44bf-126">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="c44bf-127">Om en fil till exempel kopierades är det den kopierade filen.</span><span class="sxs-lookup"><span data-stu-id="c44bf-127">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="c44bf-128">`InitiatingProcessSHA1`— I de mest avancerade jakttabellerna är detta den akt som ansvarar för att inleda den registrerade åtgärden.</span><span class="sxs-lookup"><span data-stu-id="c44bf-128">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="c44bf-129">Om till exempel en underordnad process startades är det den överordnade processen.</span><span class="sxs-lookup"><span data-stu-id="c44bf-129">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="c44bf-130">`SHA256`— Detta är SHA-256-motsvarigheten till den fil som identifieras av `SHA1` kolumnen.</span><span class="sxs-lookup"><span data-stu-id="c44bf-130">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="c44bf-131">`InitiatingProcessSHA256`— Detta är SHA-256-motsvarigheten till den fil som identifieras av `InitiatingProcessSHA1` kolumnen.</span><span class="sxs-lookup"><span data-stu-id="c44bf-131">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="c44bf-132">Om du vill veta mer om hur karantänåtgärder vidtas och hur filer kan återställas [läser du om svarsåtgärder på filer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span><span class="sxs-lookup"><span data-stu-id="c44bf-132">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="c44bf-133">För att hitta filer och sätta dem i karantän bör frågeresultatet även innehålla `DeviceId` värden som enhetsidentifierare.</span><span class="sxs-lookup"><span data-stu-id="c44bf-133">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="c44bf-134">Vidta åtgärder</span><span class="sxs-lookup"><span data-stu-id="c44bf-134">Take action</span></span>
<span data-ttu-id="c44bf-135">Om du vill vidta någon av de beskrivna åtgärderna markerar du en eller flera poster i frågeresultatet och väljer sedan **Vidta åtgärder**.</span><span class="sxs-lookup"><span data-stu-id="c44bf-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="c44bf-136">En guide guidar dig genom processen att välja och sedan skicka in önskade åtgärder.</span><span class="sxs-lookup"><span data-stu-id="c44bf-136">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Bild på vald post med panel för att kontrollera posten](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="c44bf-138">Granska vidtagna åtgärder</span><span class="sxs-lookup"><span data-stu-id="c44bf-138">Review actions taken</span></span>
<span data-ttu-id="c44bf-139">Varje åtgärd registreras individuellt i [åtgärdscentret](mtp-action-center.md) under **ÅtgärdscenterHistorik**  >  **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span><span class="sxs-lookup"><span data-stu-id="c44bf-139">Each action is individually recorded in the [action center](mtp-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="c44bf-140">Gå till åtgärdscentret för att kontrollera status för varje åtgärd.</span><span class="sxs-lookup"><span data-stu-id="c44bf-140">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="c44bf-141">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="c44bf-141">Related topics</span></span>
- [<span data-ttu-id="c44bf-142">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="c44bf-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c44bf-143">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="c44bf-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c44bf-144">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="c44bf-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="c44bf-145">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="c44bf-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c44bf-146">Översikt över åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="c44bf-146">Action center overview</span></span>](mtp-action-center.md)