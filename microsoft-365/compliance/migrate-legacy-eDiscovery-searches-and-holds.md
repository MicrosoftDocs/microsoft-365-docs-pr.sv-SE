---
title: Migrera äldre eDiscovery-sökningar och eDiscovery-Microsoft 365 efterlevnadscenter
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: aaae5e6bddc48f29cc0766fe26a1976672c7dd49
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310816"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="6151d-102">Migrera äldre eDiscovery-sökningar och eDiscovery-Microsoft 365 efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="6151d-102">Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="6151d-103">Efterlevnadscentret för Microsoft 365 ger en förbättrad upplevelse för eDiscovery-användning, inklusive högre tillförlitlighet, bättre prestanda och många funktioner som är skräddarsydda för eDiscovery-arbetsflöden, inklusive fall där innehåll kan struktureras efter område, granskningsuppsättningar för att granska innehåll och analys för att underlätta granskning av data, till exempel närplicerad gruppering, e-posttrådning, temananalys och prognostiska kodning.</span><span class="sxs-lookup"><span data-stu-id="6151d-103">The Microsoft 365 compliance center provides an improved experience for eDiscovery usage, including: higher reliability, better performance, and many features tailored to eDiscovery workflows including cases to organize your content by matter, review sets to review content and analytics to help cull data for review such as near-duplicate grouping, email threading, themes analysis, and predictive coding.</span></span>

<span data-ttu-id="6151d-104">För att hjälpa kunder att dra nytta av de nya och förbättrade funktionerna innehåller den här artikeln grundläggande vägledning om hur du migrerar eDiscovery-sökningar och In-Place-sökningar från administrationscentret för Exchange till efterlevnadscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6151d-104">To help customers take advantage of the new and improved functionality, this article provides basic guidance on how to migrate In-Place eDiscovery searches and holds from the Exchange admin center to the Microsoft 365 compliance center.</span></span>

> [!NOTE]
> <span data-ttu-id="6151d-105">Eftersom det finns många olika scenarier innehåller den här artikeln allmän vägledning för hur man gör för att göra övergången till ett grundläggande eDiscovery-ärende i Microsoft 365 efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="6151d-105">Because there are many different scenarios, this article provides general guidance to transition searches and holds to a core eDiscovery case in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="6151d-106">Att använda eDiscovery-ärenden är inte alltid obligatoriskt, men de lägger till en extra säkerhetsnivå genom att du kan tilldela behörigheter för att styra vem som har åtkomst till eDiscovery-ärendena i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6151d-106">Using eDiscovery cases aren't always required, but they add an extra layer of security by letting you assign permissions to control who has access to the eDiscovery cases in your organization.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6151d-107">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="6151d-107">Before you begin</span></span>

- <span data-ttu-id="6151d-108">Du måste vara medlem i rollgruppen för eDiscovery Manager i Säkerhets- och &-efterlevnadscenter för att kunna köra PowerShell-kommandona som beskrivs i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="6151d-108">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the PowerShell commands described in this article.</span></span> <span data-ttu-id="6151d-109">Du måste också vara medlem i rollgruppen för Identifieringshantering Exchange administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="6151d-109">You also have to be a member of the Discovery Management role group in the Exchange admin center.</span></span>

- <span data-ttu-id="6151d-110">Den här artikeln innehåller vägledning om hur du skapar en eDiscovery-hold.</span><span class="sxs-lookup"><span data-stu-id="6151d-110">This article provides guidance on how to create an eDiscovery hold.</span></span> <span data-ttu-id="6151d-111">Principen för håll tillämpas på postlådor genom en asynkron process.</span><span class="sxs-lookup"><span data-stu-id="6151d-111">The hold policy will be applied to mailboxes through an asynchronous process.</span></span> <span data-ttu-id="6151d-112">När du skapar ett eDiscovery-värde måste du skapa både ett CaseHoldPolicy- och CaseHoldRule, annars skapas inte detta värde och innehållsplatser kommer inte att vara på plats.</span><span class="sxs-lookup"><span data-stu-id="6151d-112">When creating an eDiscovery hold, you must create both a CaseHoldPolicy and CaseHoldRule, otherwise the hold will not be created and content locations will not be placed on hold.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell-and-security--compliance-center-powershell"></a><span data-ttu-id="6151d-113">Steg 1: Anslut att Exchange Online PowerShell och Security & Compliance Center PowerShell</span><span class="sxs-lookup"><span data-stu-id="6151d-113">Step 1: Connect to Exchange Online PowerShell and Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="6151d-114">Det första steget är att ansluta till Exchange Online PowerShell och Security & Compliance Center PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6151d-114">The first step is to connect to Exchange Online PowerShell and Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="6151d-115">Du kan kopiera följande skript, klistra in det i ett PowerShell-fönster och sedan köra det.</span><span class="sxs-lookup"><span data-stu-id="6151d-115">You can copy the following script, paste it into a PowerShell window and then run it.</span></span> <span data-ttu-id="6151d-116">Du uppmanas att ange autentiseringsuppgifter för organisationen som du vill ansluta till.</span><span class="sxs-lookup"><span data-stu-id="6151d-116">You'll be prompted for credentials for the organization that you want to connect to.</span></span> 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $sccSession -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

<span data-ttu-id="6151d-117">Du måste köra kommandona i följande steg i den här PowerShell-sessionen.</span><span class="sxs-lookup"><span data-stu-id="6151d-117">You need to run the commands in the following steps in this PowerShell session.</span></span>

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a><span data-ttu-id="6151d-118">Steg 2: Få en lista över alla In-Place eDiscovery-sökningar med hjälp av Get-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="6151d-118">Step 2: Get a list of In-Place eDiscovery searches by using Get-MailboxSearch</span></span>

<span data-ttu-id="6151d-119">När du har autentiserat kan du få en lista In-Place eDiscovery-sökningar genom att köra cmdleten **Get-MailboxSearch.**</span><span class="sxs-lookup"><span data-stu-id="6151d-119">After you've authenticated, you can get a list of In-Place eDiscovery searches by running the **Get-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="6151d-120">Kopiera och klistra in följande kommando i PowerShell och kör det sedan.</span><span class="sxs-lookup"><span data-stu-id="6151d-120">Copy and paste the following command into PowerShell and then run it.</span></span> <span data-ttu-id="6151d-121">En lista med sökningar visas med deras namn och status för eventuella In-Place.</span><span class="sxs-lookup"><span data-stu-id="6151d-121">A list of searches will be listed with their names and the status of any In-Place Holds.</span></span>

```powershell
Get-MailboxSearch
```

<span data-ttu-id="6151d-122">Cmdlet-utdata kommer att se ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="6151d-122">The cmdlet output will be similar to the following:</span></span>

![PowerShell-exempel Get-MailboxSearch](../media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a><span data-ttu-id="6151d-124">Steg 3: Få information om hur In-Place eDiscovery-sökningar och hur In-Place som ska migreras</span><span class="sxs-lookup"><span data-stu-id="6151d-124">Step 3: Get information about the In-Place eDiscovery searches and In-Place Holds you want to migrate</span></span>

<span data-ttu-id="6151d-125">Du kommer återigen att **använda cmdleten Get-MailboxSearch,** men nu för att få egenskaperna för sökningen.</span><span class="sxs-lookup"><span data-stu-id="6151d-125">Again you will use the **Get-MailboxSearch** cmdlet, but this time to get the properties of the search.</span></span> <span data-ttu-id="6151d-126">Du kan lagra de här egenskaperna i en variabel för senare användning.</span><span class="sxs-lookup"><span data-stu-id="6151d-126">You can store these properties in a variable for use later.</span></span> <span data-ttu-id="6151d-127">I följande exempel lagras resultatet av **cmdleten Get-MailboxSearch** i en variabel och sedan visas egenskaperna för sökningen.</span><span class="sxs-lookup"><span data-stu-id="6151d-127">The following example stores the results of the **Get-MailboxSearch** cmdlet in a variable and then displays the properties of the search.</span></span>

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

<span data-ttu-id="6151d-128">Utdata för dessa två kommandon kommer att se ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="6151d-128">The output of these two commands will be similar to the following:</span></span>

![Exempel på PowerShell-utdata från Get-MailboxSearch för en enskild sökning](../media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> <span data-ttu-id="6151d-130">Varaktigheten för det In-Place i det här exemplet är obegränsad *(ItemHoldPeriod: Unlimited*).</span><span class="sxs-lookup"><span data-stu-id="6151d-130">The duration of the In-Place Hold in this example is indefinite (*ItemHoldPeriod: Unlimited*).</span></span> <span data-ttu-id="6151d-131">Det här är typiskt för scenarier för e-dataidentifiering och juridisk undersökning.</span><span class="sxs-lookup"><span data-stu-id="6151d-131">This is typical for eDiscovery and legal investigation scenarios.</span></span> <span data-ttu-id="6151d-132">Om varaktigheten för bevarandet har ett annat värde än ett obegränsat värde beror det sannolikt på att bevarandet används för att behålla innehåll i ett bevarandescenario.</span><span class="sxs-lookup"><span data-stu-id="6151d-132">If the hold duration has is different value than indefinite, the reason is likely because the hold is being used to retain content in a retention scenario.</span></span> <span data-ttu-id="6151d-133">I stället för att använda eDiscovery-cmdlets i Security & Compliance Center PowerShell för bevarandescenarier rekommenderar vi att du använder [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy) och [New-RetentionComplianceRule](/powershell/module/exchange/new-retentioncompliancerule) för att behålla innehåll.</span><span class="sxs-lookup"><span data-stu-id="6151d-133">Instead of using the eDiscovery cmdlets in Security & Compliance Center PowerShell for retention scenarios, we recommend that you use [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy) and [New-RetentionComplianceRule](/powershell/module/exchange/new-retentioncompliancerule) to retain content.</span></span> <span data-ttu-id="6151d-134">Resultatet av att använda dessa cmdlets påminner om att använda **New-CaseHoldPolicy** och **New-CaseHoldRule**, men du kan ange en bevarandeperiod och en bevarandeåtgärd, till exempel ta bort innehåll efter att lagringsperioden gått ut.</span><span class="sxs-lookup"><span data-stu-id="6151d-134">The result of using these cmdlets will be similar to using **New-CaseHoldPolicy** and **New-CaseHoldRule**, but you'll able to specify a retention period and a retention action, such as deleting content after the retention period expires.</span></span> <span data-ttu-id="6151d-135">Om du använder cmdlet:arna för bevarande behöver du inte associera bevarandet med ett eDiscovery-ärende.</span><span class="sxs-lookup"><span data-stu-id="6151d-135">Also, using the retention cmdlets don't require you to associate the retention holds with an eDiscovery case.</span></span>

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="6151d-136">Steg 4: Skapa ett ärende i Microsoft 365 efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="6151d-136">Step 4: Create a case in the Microsoft 365 Compliance center</span></span>

<span data-ttu-id="6151d-137">Om du vill skapa ett eDiscovery-ärende måste du skapa ett eDiscovery-ärende att koppla holden till.</span><span class="sxs-lookup"><span data-stu-id="6151d-137">To create an eDiscovery hold, you have to create an eDiscovery case to associate the hold with.</span></span> <span data-ttu-id="6151d-138">I följande exempel skapas ett eDiscovery-ärende med ett namn som du väljer.</span><span class="sxs-lookup"><span data-stu-id="6151d-138">The following example creates an eDiscovery case using a name of your choice.</span></span> <span data-ttu-id="6151d-139">Vi lagrar egenskaperna för det nya ärendet i en variabel för användning senare.</span><span class="sxs-lookup"><span data-stu-id="6151d-139">We will store the properties of the new case in a variable for use later.</span></span> <span data-ttu-id="6151d-140">Du kan visa de egenskaperna genom att köra `$case | FL` kommandot när du har skapat ärendet.</span><span class="sxs-lookup"><span data-stu-id="6151d-140">You can view those properties by running the `$case | FL` command after you create the case.</span></span>

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```
![Exempel på hur kommandot New-ComplianceCase körs](../media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a><span data-ttu-id="6151d-142">Steg 5: Skapa eDiscovery-hållen</span><span class="sxs-lookup"><span data-stu-id="6151d-142">Step 5: Create the eDiscovery hold</span></span>

<span data-ttu-id="6151d-143">När ärendet har skapats kan du skapa ett ärende och koppla det till det ärende som du skapade i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="6151d-143">After the case is created, you can create the hold and associate it with the case that you created in the previous step.</span></span> <span data-ttu-id="6151d-144">Det är viktigt att komma ihåg att du måste skapa både en princip för undantag från ärende och en regel för undantag.</span><span class="sxs-lookup"><span data-stu-id="6151d-144">It's important to remember that you must create both a case hold policy and a case hold rule.</span></span> <span data-ttu-id="6151d-145">Om regeln om undantag inte skapas efter att du skapat principen för undantag för ärende skapas inte undantag för eDiscovery och inget innehåll sätts på undantag.</span><span class="sxs-lookup"><span data-stu-id="6151d-145">If the case hold rule isn't created after you created case hold policy, the eDiscovery hold will not be created and any content won't be placed on hold.</span></span>

<span data-ttu-id="6151d-146">Kör följande kommandon för att skapa den eDiscovery-hold som du vill migrera.</span><span class="sxs-lookup"><span data-stu-id="6151d-146">Run the following commands to re-create the eDiscovery hold that you want to migrate.</span></span> <span data-ttu-id="6151d-147">I de här exemplen används egenskaperna In-Place från steg 3 som du vill migrera.</span><span class="sxs-lookup"><span data-stu-id="6151d-147">These examples use the properties from In-Place Hold from Step 3 that you want to migrate.</span></span> <span data-ttu-id="6151d-148">Det första kommandot skapar en ny princip för ärendesparning och sparar egenskaperna på en variabel.</span><span class="sxs-lookup"><span data-stu-id="6151d-148">The first command creates a new case hold policy and saves the properties to a variable.</span></span> <span data-ttu-id="6151d-149">Det andra kommandot skapar motsvarande undantagsregel.</span><span class="sxs-lookup"><span data-stu-id="6151d-149">The second command creates the corresponding case hold rule.</span></span>

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![Exempel på användning av cmdlets för NewCaseHoldPolicy och NewCaseHoldRule](../media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a><span data-ttu-id="6151d-151">Steg 6: Verifiera eDiscovery-hållen</span><span class="sxs-lookup"><span data-stu-id="6151d-151">Step 6: Verify the eDiscovery hold</span></span>

<span data-ttu-id="6151d-152">För att kontrollera att det inte gick att skapa ett väntande jobb är det bra att kontrollera att statusen för att hålla distributionen är lyckad.</span><span class="sxs-lookup"><span data-stu-id="6151d-152">To make sure there were no issues in creating the hold, it's good to check that the hold distribution status is successful.</span></span> <span data-ttu-id="6151d-153">Distribution innebär att hastet har tillämpats på alla innehållsplatser som anges i *parametern ExchangeLocation* i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="6151d-153">Distribution means that the hold has been applied to all the content locations specified in the *ExchangeLocation* parameter in the previous step.</span></span> <span data-ttu-id="6151d-154">Det kan du göra genom att köra **cmdleten Get-CaseHoldPolicy.**</span><span class="sxs-lookup"><span data-stu-id="6151d-154">To do this, you can run the **Get-CaseHoldPolicy** cmdlet.</span></span> <span data-ttu-id="6151d-155">Eftersom egenskaperna som sparades på *den $policy-variabel* som du skapade i föregående steg inte uppdateras automatiskt i variabeln måste du köra cmdleten igen för att verifiera att fördelningen har lyckats.</span><span class="sxs-lookup"><span data-stu-id="6151d-155">Because the properties saved to the *$policy* variable that you created in the previous step aren't automatically updated in the variable, you need to rerun the cmdlet to verify that distribution is successful.</span></span> <span data-ttu-id="6151d-156">Det kan ta mellan 5 minuter och 24 timmar för principer för ärende hold att distribueras.</span><span class="sxs-lookup"><span data-stu-id="6151d-156">It can take between 5 minutes and 24 hours for case hold policies to be successfully distributed.</span></span>

<span data-ttu-id="6151d-157">Kör följande kommando för att verifiera att eDiscovery-behållarna har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="6151d-157">Run the following command to verify that the eDiscovery hold has been successfully distributed.</span></span>

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

<span data-ttu-id="6151d-158">Värdet för **Lyckades** för egenskapen *DistributionStatus* anger att fältet har placerats på innehållsplatserna.</span><span class="sxs-lookup"><span data-stu-id="6151d-158">The value of **Success** for the *DistributionStatus* property indicates the hold was successfully placed on the content locations.</span></span> <span data-ttu-id="6151d-159">Om fördelningen ännu inte är klar visas **värdet Väntande.**</span><span class="sxs-lookup"><span data-stu-id="6151d-159">If the distribution is not yet complete, a value of **Pending** is displayed.</span></span>

![PowerShell Get-CaseHoldPolicy exempel](../media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a><span data-ttu-id="6151d-161">Steg 7: Skapa sökningen</span><span class="sxs-lookup"><span data-stu-id="6151d-161">Step 7: Create the search</span></span>

<span data-ttu-id="6151d-162">Det sista steget är att skapa sökningen som du identifierade i steg 3 igen och koppla den till ärendet.</span><span class="sxs-lookup"><span data-stu-id="6151d-162">The last step is to re-create the search that you identified in Step 3 and associate it with the case.</span></span> <span data-ttu-id="6151d-163">När du har skapat sökningen kan du köra den med hjälp av **cmdleten Start-ComplianceSearch** eller köra den senare.</span><span class="sxs-lookup"><span data-stu-id="6151d-163">After you create the search, you can run it by using the **Start-ComplianceSearch** cmdlet or run at a later time.</span></span>

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![PowerShell New-ComplianceSearch exempel](../media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="6151d-165">Steg 8: Kontrollera ärendet, håll kvar och sök i Microsoft 365 kompatibilitetscenter</span><span class="sxs-lookup"><span data-stu-id="6151d-165">Step 8: Verify the case, hold, and search in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="6151d-166">Kontrollera att allt är korrekt inställt genom att gå till Microsoft 365 efterlevnadscenter på och klicka på [https://compliance.microsoft.com](https://compliance.microsoft.com) **eDiscovery > Core**.</span><span class="sxs-lookup"><span data-stu-id="6151d-166">To make sure that everything is set up correctly, go to the Microsoft 365 compliance center at [https://compliance.microsoft.com](https://compliance.microsoft.com), and click **eDiscovery > Core**.</span></span>

![Microsoft 365 Efterlevnadscenter för eDiscovery](../media/MigrateLegacyeDiscovery7.png)

<span data-ttu-id="6151d-168">Det ärende som du skapade i steg 3 visas på **sidan Bas-eDiscovery.**</span><span class="sxs-lookup"><span data-stu-id="6151d-168">The case that you created in Step 3 is listed on the **Core eDiscovery** page.</span></span> <span data-ttu-id="6151d-169">Öppna ärendet och lägg sedan märke till det ärende du skapade i steg 4 på **fliken** Håll. Du kan välja att hålla på plats om du vill se information på den utfällliga sidan, inklusive antalet postlådor som är inhållna och distributionsstatus.</span><span class="sxs-lookup"><span data-stu-id="6151d-169">Open the case and then notice the hold that you created in Step 4 in listed on the **Hold** tab. You can select the hold to see details on the flyout page, including the number of mailboxes the hold is applied to and the distribution status.</span></span>

![eDiscovery som sätts i Microsoft 365 efterlevnadscenter](../media/MigrateLegacyeDiscovery8.png)

<span data-ttu-id="6151d-171">Sökningen som du skapade i steg 7 visas på **fliken Sökningar** för ärendet.</span><span class="sxs-lookup"><span data-stu-id="6151d-171">The search that you created in Step 7 is listed on the **Searches** tab of the case.</span></span>

![Sökning efter eDiscovery-fall i Microsoft 365 efterlevnadscenter](../media/MigrateLegacyeDiscovery9.png)

<span data-ttu-id="6151d-173">Om du migrerar en In-Place eDiscovery-sökning men inte associerar den med ett eDiscovery-fall visas den på sidan Innehållssökning i efterlevnadscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6151d-173">If you migrate an In-Place eDiscovery search but don't associate it with an eDiscovery case, it will be listed on the Content search page in the Microsoft 365 compliance center.</span></span>

## <a name="more-information"></a><span data-ttu-id="6151d-174">Mer information</span><span class="sxs-lookup"><span data-stu-id="6151d-174">More information</span></span>

- <span data-ttu-id="6151d-175">Mer information om eDiscovery In-Place och eDiscovery & i administrationscentret för Exchange finns i:</span><span class="sxs-lookup"><span data-stu-id="6151d-175">For more information about In-Place eDiscovery & Holds in the Exchange admin center, see:</span></span>
  
  - [<span data-ttu-id="6151d-176">Lokal eDiscovery</span><span class="sxs-lookup"><span data-stu-id="6151d-176">In-Place eDiscovery</span></span>](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [<span data-ttu-id="6151d-177">Lokalt bevarande och bevarande av juridiska skäl</span><span class="sxs-lookup"><span data-stu-id="6151d-177">In-Place Hold and Litigation Hold</span></span>](/exchange/security-and-compliance/in-place-and-litigation-holds)

- <span data-ttu-id="6151d-178">Mer information om PowerShell-cmdlets som används i artikeln finns i:</span><span class="sxs-lookup"><span data-stu-id="6151d-178">For more information about the PowerShell cmdlets used in the article, see:</span></span>

  - [<span data-ttu-id="6151d-179">Get-MailboxSearch</span><span class="sxs-lookup"><span data-stu-id="6151d-179">Get-MailboxSearch</span></span>](/powershell/module/exchange/get-mailboxsearch)
  
  - [<span data-ttu-id="6151d-180">New-ComplianceCase</span><span class="sxs-lookup"><span data-stu-id="6151d-180">New-ComplianceCase</span></span>](/powershell/module/exchange/new-compliancecase)

  - [<span data-ttu-id="6151d-181">New-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="6151d-181">New-CaseHoldPolicy</span></span>](/powershell/module/exchange/new-caseholdpolicy)
  
  - [<span data-ttu-id="6151d-182">New-CaseHoldrule</span><span class="sxs-lookup"><span data-stu-id="6151d-182">New-CaseHoldRule</span></span>](/powershell/module/exchange/new-caseholdrule)

  - [<span data-ttu-id="6151d-183">Get-CaseHoldPolicy</span><span class="sxs-lookup"><span data-stu-id="6151d-183">Get-CaseHoldPolicy</span></span>](/powershell/module/exchange/get-caseholdpolicy)
  
  - [<span data-ttu-id="6151d-184">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="6151d-184">New-ComplianceSearch</span></span>](/powershell/module/exchange/new-compliancesearch)

  - [<span data-ttu-id="6151d-185">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="6151d-185">Start-ComplianceSearch</span></span>](/powershell/module/exchange/start-compliancesearch)

- <span data-ttu-id="6151d-186">Mer information om hur Microsoft 365 och efterlevnadscenter finns i [Översikt över Microsoft 365 kompatibilitetscenter.](microsoft-365-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="6151d-186">For more information about the Microsoft 365 compliance center, see [Overview of the Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span>