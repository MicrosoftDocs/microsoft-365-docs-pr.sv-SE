---
title: Felsöka AzCopy i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Felsöka fel för Azure AzCopy vid inläsning av icke-Office 365-data för felåtgärder i Advanced eDiscovery.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: f34b47762601a3cc66b46fd8a2691c0fb87d3354
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162030"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="c480f-103">Felsöka AzCopy i Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c480f-103">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="c480f-104">När du läser in data eller dokument som inte är Microsoft 365 eller dokument för felreparation i Advanced eDiscovery tillhandahåller användargränssnittet ett Azure AzCopy-kommando som innehåller parametrarna för platsen där de filer du vill ladda upp lagras och azure-lagringsplatsen som filerna ska laddas upp till.</span><span class="sxs-lookup"><span data-stu-id="c480f-104">When loading non-Microsoft 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="c480f-105">Om du vill ladda upp dina dokument kopierar du det här kommandot och kör det sedan i en kommandotolk på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="c480f-105">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="c480f-106">På följande skärmbild visas ett exempel på ett AzCopy-kommando:</span><span class="sxs-lookup"><span data-stu-id="c480f-106">The follow screenshot shows an example of an AzCopy command:</span></span>

![Upload filer som inte är Microsoft 365 filer](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="c480f-108">Vanligtvis fungerar det kommando som tillhandahålls när du kör det.</span><span class="sxs-lookup"><span data-stu-id="c480f-108">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="c480f-109">Det kan dock finnas tillfällen när kommandot som visas inte körs.</span><span class="sxs-lookup"><span data-stu-id="c480f-109">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="c480f-110">Här är några möjliga orsaker.</span><span class="sxs-lookup"><span data-stu-id="c480f-110">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="c480f-111">Den version av AzCopy som stöds är inte installerad på den lokala datorn</span><span class="sxs-lookup"><span data-stu-id="c480f-111">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="c480f-112">För stunden måste du använda AzCopy v8.1 för att läsa in icke-Microsoft 365-data i Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="c480f-112">At this time, you must use AzCopy v8.1 to load non-Microsoft 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="c480f-113">Kommandot AzCopy som visas på **filsidan för Upload** som visas på föregående skärmbild returnerar ett fel om du inte använder AzCopy v8.1.</span><span class="sxs-lookup"><span data-stu-id="c480f-113">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="c480f-114">Information om hur du installerar den [här versionen finns i Överföra data med AzCopy v8.1 på Windows](/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="c480f-114">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="c480f-115">AzCopy är inte installerat på den lokala datorn eller är inte installerat på standardplatsen</span><span class="sxs-lookup"><span data-stu-id="c480f-115">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="c480f-116">Om AzCopy inte är installerat eller om det är installerat på en annan plats än standardplatsen för installation (d.v.s. ) kan följande felmeddelande visas när du kör `%ProgramFiles(x86)%` kommandot AzCopy:</span><span class="sxs-lookup"><span data-stu-id="c480f-116">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

> <span data-ttu-id="c480f-117">Det går inte att hitta den angivna sökvägen.</span><span class="sxs-lookup"><span data-stu-id="c480f-117">The system cannot find the path specified.</span></span>

<span data-ttu-id="c480f-118">Om AzCopy inte är installerat på den lokala datorn hittar du installationsinformationen under Överför data med [AzCopy v8.1 på Windows](/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="c480f-118">If AzCopy isn't installed on the local computer, you can find installation information in [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="c480f-119">Se till att installera den på standardplatsen.</span><span class="sxs-lookup"><span data-stu-id="c480f-119">Be sure to install it in the default location.</span></span>

<span data-ttu-id="c480f-120">Om AzCopy är installerat, men det installeras på en annan plats än standardplatsen, kan du kopiera kommandot, klistra in det i en textfil och sedan ändra sökvägen till den plats där AzCopy är installerad.</span><span class="sxs-lookup"><span data-stu-id="c480f-120">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="c480f-121">Om Azcopy till exempel finns i kan du ändra den `%ProgramFiles%` första delen av kommandot från till `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` .</span><span class="sxs-lookup"><span data-stu-id="c480f-121">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="c480f-122">När du har gör den här ändringen kopierar du den från textfilen och kör den i kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="c480f-122">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="c480f-123">Om AzCopy är installerat på en annan plats än standardplatsen för installation bör du överväga att avinstallera det och sedan installera om det på standardplatsen.</span><span class="sxs-lookup"><span data-stu-id="c480f-123">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="c480f-124">Det här hjälper till att förhindra det här problemet i framtiden.</span><span class="sxs-lookup"><span data-stu-id="c480f-124">This will help prevent this issue in the future.</span></span>