---
title: Samla in information om eDiscovery-diagnostik
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du samlar in eDiscovery-diagnostikinformation för ett Microsoft Support-ärende.
ms.openlocfilehash: b2441e0b7af8a82e24a8acca9e000e954e1c8964
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362600"
---
# <a name="collect-ediscovery-diagnostic-information"></a><span data-ttu-id="a84be-103">Samla in information om eDiscovery-diagnostik</span><span class="sxs-lookup"><span data-stu-id="a84be-103">Collect eDiscovery diagnostic information</span></span>

<span data-ttu-id="a84be-104">Ibland behöver Microsofts supporttekniker specifik information om ditt problem när du öppnar ett supportfall som är relaterat till Core eDiscovery eller Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a84be-104">Occasionally Microsoft Support engineers require specific information about your issue when you open a support case related to Core eDiscovery or Advanced eDiscovery.</span></span> <span data-ttu-id="a84be-105">Den här artikeln innehåller vägledning om hur du samlar in diagnostikinformation som supporttekniker kan undersöka och lösa problem.</span><span class="sxs-lookup"><span data-stu-id="a84be-105">This article provides guidance on how to collect diagnostic information to help support engineers investigate and resolve issues.</span></span> <span data-ttu-id="a84be-106">Vanligtvis behöver du inte samla in den här informationen förrän du ombeds att göra det av en Microsoft-supporttekniker.</span><span class="sxs-lookup"><span data-stu-id="a84be-106">Typically, you don't need to collect this information until asked to do so by a Microsoft Support engineer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a84be-107">Utdata från cmdlets och diagnostisk information som beskrivs i den här artikeln kan innehålla känslig information om rättstvister eller interna undersökningar i organisationen.</span><span class="sxs-lookup"><span data-stu-id="a84be-107">The output from the cmdlets and diagnostic information described in this article may include sensitive information about litigation or internal investigations in your organization.</span></span> <span data-ttu-id="a84be-108">Innan du skickar rådata för diagnostikinformation till Microsoft Support bör du granska informationen och göra om känslig information (till exempel namn eller annan information om parter i en rättstvist eller undersökning) genom att ersätta den med `XXXXXXX` .</span><span class="sxs-lookup"><span data-stu-id="a84be-108">Before sending the raw diagnostic information to Microsoft Support, you should review the information and redact any sensitive information (such as names or other information about parties to litigation or investigation) by replacing it with `XXXXXXX`.</span></span> <span data-ttu-id="a84be-109">Om du använder den här metoden anger det också för Microsoft Support-teknikern att informationen har omactats.</span><span class="sxs-lookup"><span data-stu-id="a84be-109">Using this method will also indicate to the Microsoft Support engineer that information was redacted.</span></span>

## <a name="collect-diagnostic-information-for-core-ediscovery"></a><span data-ttu-id="a84be-110">Samla in diagnostikinformation för bas-eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a84be-110">Collect diagnostic information for Core eDiscovery</span></span>

<span data-ttu-id="a84be-111">Insamling av diagnostikinformation för Core eDiscovery är cmdlet-baserad, så du måste använda Security & Compliance Center PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a84be-111">Collecting diagnostic information for Core eDiscovery is cmdlet-based, so you'll have to use Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="a84be-112">Följande PowerShell-exempel kör cmdlets och sparar sedan utdata i en viss textfil.</span><span class="sxs-lookup"><span data-stu-id="a84be-112">The following PowerShell examples will run cmdlets and then save the output to a specified text file.</span></span> <span data-ttu-id="a84be-113">I de flesta supportärenden behöver du bara köra något av dessa kommandon.</span><span class="sxs-lookup"><span data-stu-id="a84be-113">In most support cases, you should only have to run one of these commands.</span></span>

<span data-ttu-id="a84be-114">Om du vill köra följande cmdlets [ansluter du till </span> Säkerhets- & Compliance Center PowerShell.](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="a84be-114">To run the following cmdlets, [connect to Security & Compliance Center PowerShell</span>](/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="a84be-115">När du är ansluten kör du ett eller flera av följande kommandon och ersätter platshållarna med de faktiska objektnamnen.</span><span class="sxs-lookup"><span data-stu-id="a84be-115">After you're connected, run one or more of the following commands and be sure to replace placeholders with the actual object names.</span></span>

<span data-ttu-id="a84be-116">När du har granskat den genererade textfilen och omformaterat känslig information skickar du den till Microsoft Support-tekniker som arbetar på ditt ärende.</span><span class="sxs-lookup"><span data-stu-id="a84be-116">After reviewing the generated text file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>

> [!NOTE]
> <span data-ttu-id="a84be-117">Du kan även köra kommandona i det här avsnittet för  att samla in diagnostikinformation för de sökningar och exporter som visas på sidan Innehållssökning i Microsoft 365 Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="a84be-117">You can also run the commands in this section to collect diagnostic information for the searches and exports listed on the **Content search** page in the Microsoft 365 compliance center.</span></span>

### <a name="collect-information-about-searches"></a><span data-ttu-id="a84be-118">Samla in information om sökningar</span><span class="sxs-lookup"><span data-stu-id="a84be-118">Collect information about searches</span></span>

<span data-ttu-id="a84be-119">Följande kommando samlar in information som är användbar när du undersöker problem med en innehållssökning eller en sökning som är kopplad till ett Grundläggande eDiscovery-ärende.</span><span class="sxs-lookup"><span data-stu-id="a84be-119">The following command collects information that's helpful when investigating issues with a Content search or a search associated with a Core eDiscovery case.</span></span>

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a><span data-ttu-id="a84be-120">Samla in information om sökåtgärder</span><span class="sxs-lookup"><span data-stu-id="a84be-120">Collect information about search actions</span></span>

<span data-ttu-id="a84be-121">Följande kommando samlar in information för att undersöka problem med att förhandsgranska, exportera eller rensa resultatet av en innehållssökning eller en sökning kopplad till ett Core eDiscovery-ärende.</span><span class="sxs-lookup"><span data-stu-id="a84be-121">The following command collects information to investigate problems with previewing, exporting, or purging the results of a Content search or a search associated with a Core eDiscovery case.</span></span> <span data-ttu-id="a84be-122">Du kan identifiera namnet på sökåtgärden genom att klicka på en export som visas på **fliken Exporter.** Identifiera namnen på förhandsgransknings- och rensningsåtgärderna genom att köra **cmdlet:en Get-ComplianceSearchAction** för att visa en lista över alla åtgärder.</span><span class="sxs-lookup"><span data-stu-id="a84be-122">You can identify the name of the search action by clicking an export that's listed on the **Exports** tab. To identify the names of preview and purge actions, you can run the **Get-ComplianceSearchAction** cmdlet to display a list of all actions.</span></span> <span data-ttu-id="a84be-123">Formatet för sökåtgärdsnamnet är uppbyggt av att lägga till `_Preview` , eller efter namnet på motsvarande `_Export` `_Purge` sökning.</span><span class="sxs-lookup"><span data-stu-id="a84be-123">The format for the search action name is constructed by appending `_Preview`, `_Export`, or `_Purge` to the name of the corresponding search.</span></span>

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a><span data-ttu-id="a84be-124">Samla in information om eDiscovery-kvarhåller</span><span class="sxs-lookup"><span data-stu-id="a84be-124">Collect information about eDiscovery holds</span></span>

<span data-ttu-id="a84be-125">Om ett undantag för eDiscovery som är kopplat till ett Core eDiscovery-ärende inte fungerar som förväntat, kör du följande kommando för att samla in information om principen för undantag och tillhörande regel för undantag för eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a84be-125">When an eDiscovery hold associated with a Core eDiscovery case isn't functioning as expected, run the following command to collect information about the Case Hold Policy and associated Case Hold Rule for the eDiscovery hold.</span></span> <span data-ttu-id="a84be-126">Principen *Case hold name* i följande kommando är samma som namnet på eDiscovery-holden.</span><span class="sxs-lookup"><span data-stu-id="a84be-126">The *Case hold policy name* in the following command is the same as the name of the eDiscovery hold.</span></span> <span data-ttu-id="a84be-127">Du kan identifiera det här namnet på **flikarna Som** innehåller i Core eDiscovery-ärendet.</span><span class="sxs-lookup"><span data-stu-id="a84be-127">You can identify this name on the **Holds** tabs in the Core eDiscovery case.</span></span>

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a><span data-ttu-id="a84be-128">Samla in all ärendeinformation</span><span class="sxs-lookup"><span data-stu-id="a84be-128">Collect all case information</span></span>

<span data-ttu-id="a84be-129">Ibland står det inte vilken information som krävs av Microsoft Support för att undersöka problemet.</span><span class="sxs-lookup"><span data-stu-id="a84be-129">Sometimes, it's not apparent what information is required by Microsoft Support to investigate your issue.</span></span> <span data-ttu-id="a84be-130">I det här fallet kan du samla in all diagnostikinformation för ett grundläggande e-dataidentifieringsfall.</span><span class="sxs-lookup"><span data-stu-id="a84be-130">In this situation, you can collect all of the diagnostics information for a Core eDiscovery case.</span></span> <span data-ttu-id="a84be-131">Namnet *på core-eDiscovery-ärendet* i följande kommando är samma som namnet på ett ärende som visas på sidan **Core eDiscovery** i Microsoft 365 Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="a84be-131">The *Core eDiscovery case name* in the following command is the same as the name of a case that's displayed on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span>

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{$_|fl;"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a><span data-ttu-id="a84be-132">Samla in diagnostikinformation för Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a84be-132">Collect diagnostic information for Advanced eDiscovery</span></span>

<span data-ttu-id="a84be-133">På **Inställningar** i ett Advanced eDiscovery kan du snabbt kopiera diagnostisk information för ärendet.</span><span class="sxs-lookup"><span data-stu-id="a84be-133">The **Settings** tab in an Advanced eDiscovery case lets you quickly copy the diagnostic information for the case.</span></span> <span data-ttu-id="a84be-134">Diagnostikinformationen sparas i Urklipp så att du kan klistra in den i en textfil och skicka den till Microsoft Support.</span><span class="sxs-lookup"><span data-stu-id="a84be-134">The diagnostic information is saved to the clipboard so you can paste it to a text file and send to Microsoft Support.</span></span>

1. <span data-ttu-id="a84be-135">Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com/) och klicka sedan på Visa > **eDiscovery-> Avancerat.**</span><span class="sxs-lookup"><span data-stu-id="a84be-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Show all > eDiscovery > Advanced**.</span></span>

2. <span data-ttu-id="a84be-136">Markera ett ärende och klicka sedan **på Inställningar** ärendet.</span><span class="sxs-lookup"><span data-stu-id="a84be-136">Select a case and then click the **Settings** tab.</span></span>

3. <span data-ttu-id="a84be-137">Klicka **på Markera under** **Ärendeinformation.**</span><span class="sxs-lookup"><span data-stu-id="a84be-137">Under **Case Information**, click **Select**.</span></span>

4. <span data-ttu-id="a84be-138">På den utfällade sidan klickar **du på Kopiera diagnostikinformation** för att kopiera informationen till Urklipp.</span><span class="sxs-lookup"><span data-stu-id="a84be-138">On the flyout page, click **Copy diagnostic information** to copy the info to the clipboard.</span></span>

5. <span data-ttu-id="a84be-139">Öppna en textfil (i Anteckningar) och klistra sedan in informationen i textfilen.</span><span class="sxs-lookup"><span data-stu-id="a84be-139">Open a text file (in Notepad) and then paste the information in the text file.</span></span>

6. <span data-ttu-id="a84be-140">Spara textfilen och ge den ett namn som `AeD Diagnostic Info YYYY.MM.DD` liknar den (till exempel `AeD Diagnostic Info 2020.11.03` ).</span><span class="sxs-lookup"><span data-stu-id="a84be-140">Save the text file and name it something like `AeD Diagnostic Info YYYY.MM.DD` (for example, `AeD Diagnostic Info 2020.11.03`).</span></span>

<span data-ttu-id="a84be-141">När du har granskat filen och skickat den till Microsofts supporttekniker som arbetar på ditt ärende.</span><span class="sxs-lookup"><span data-stu-id="a84be-141">After reviewing the file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>
