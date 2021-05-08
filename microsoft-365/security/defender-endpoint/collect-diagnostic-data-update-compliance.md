---
title: Samla in diagnostikdata för uppdateringsefterlevnad och Windows Defender Microsoft Defender Antivirus
description: Använd ett verktyg för att samla in data för felsökning av problem med uppdateringsefterlevnad när du använder tillägget Microsoft Defender Antivirus Assessment i
keywords: felsökning, fel, korrigering, uppdateringsefterlevnad, oms, bildskärm, rapport, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 2aaf3d1c650713a7f6cfb7b9abb9f2232013d6db
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274802"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-av-assessment"></a><span data-ttu-id="4b906-104">Samla in diagnostikdata för uppdateringsefterlevnad för Microsoft Defender AV Assessment</span><span class="sxs-lookup"><span data-stu-id="4b906-104">Collect Update Compliance diagnostic data for Microsoft Defender AV Assessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4b906-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="4b906-105">**Applies to:**</span></span>

- [<span data-ttu-id="4b906-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="4b906-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="4b906-107">I den här artikeln beskrivs hur du samlar in diagnostikdata som kan användas av Microsofts support- och teknikteam för att felsöka problem som kan uppstå när du använder avsnittet Microsoft Defender AV Assessment i tillägget Uppdateringsefterlevnad.</span><span class="sxs-lookup"><span data-stu-id="4b906-107">This article describes how to collect diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues you may encounter when using the Microsoft Defender AV Assessment section in the Update Compliance add-in.</span></span>

<span data-ttu-id="4b906-108">Innan du försöker med den här processen bör du läsa [Felsöka Microsoft Defender Antivirus,](troubleshoot-reporting.md)uppfylla alla krav och vidta andra föreslagna felsökningssteg.</span><span class="sxs-lookup"><span data-stu-id="4b906-108">Before attempting this process, ensure you have read [Troubleshoot Microsoft Defender Antivirus reporting](troubleshoot-reporting.md), met all require prerequisites, and taken any other suggested troubleshooting steps.</span></span>

<span data-ttu-id="4b906-109">På minst två enheter som inte rapporterar eller visas i Uppdateringsefterlevnad hämtar du .cab-diagnostikfilen genom att göra följande:</span><span class="sxs-lookup"><span data-stu-id="4b906-109">On at least two devices that are not reporting or showing up in Update Compliance, obtain the .cab diagnostic file by taking the following steps:</span></span>

1. <span data-ttu-id="4b906-110">Öppna en version på administratörsnivå av kommandotolken på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="4b906-110">Open an administrator-level version of the command prompt as follows:</span></span>
        
    <span data-ttu-id="4b906-111">a.</span><span class="sxs-lookup"><span data-stu-id="4b906-111">a.</span></span> <span data-ttu-id="4b906-112">Öppna **Start-menyn.**</span><span class="sxs-lookup"><span data-stu-id="4b906-112">Open the **Start** menu.</span></span>

    <span data-ttu-id="4b906-113">b.</span><span class="sxs-lookup"><span data-stu-id="4b906-113">b.</span></span> <span data-ttu-id="4b906-114">Skriv **cmd**.</span><span class="sxs-lookup"><span data-stu-id="4b906-114">Type **cmd**.</span></span> <span data-ttu-id="4b906-115">Högerklicka på **Kommandotolken och** klicka på **Kör som administratör.**</span><span class="sxs-lookup"><span data-stu-id="4b906-115">Right-click on **Command Prompt** and click **Run as administrator**.</span></span>

    <span data-ttu-id="4b906-116">c.</span><span class="sxs-lookup"><span data-stu-id="4b906-116">c.</span></span> <span data-ttu-id="4b906-117">Ange administratörsautentiseringsuppgifter eller godkänn uppmaningen.</span><span class="sxs-lookup"><span data-stu-id="4b906-117">Enter administrator credentials or approve the prompt.</span></span>
        
2. <span data-ttu-id="4b906-118">Navigera till Windows Defender katalogen.</span><span class="sxs-lookup"><span data-stu-id="4b906-118">Navigate to the Windows Defender directory.</span></span> <span data-ttu-id="4b906-119">Som standard är det här `C:\Program Files\Windows Defender` .</span><span class="sxs-lookup"><span data-stu-id="4b906-119">By default, this is `C:\Program Files\Windows Defender`.</span></span>

3. <span data-ttu-id="4b906-120">Skriv in följande kommando och tryck sedan på **Retur**</span><span class="sxs-lookup"><span data-stu-id="4b906-120">Type the following command, and then press **Enter**</span></span>
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. <span data-ttu-id="4b906-121">En .cab genereras som innehåller olika diagnostikloggar.</span><span class="sxs-lookup"><span data-stu-id="4b906-121">A .cab file will be generated that contains various diagnostic logs.</span></span> <span data-ttu-id="4b906-122">Platsen för filen anges i utdata i kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="4b906-122">The location of the file will be specified in the output in the command prompt.</span></span> <span data-ttu-id="4b906-123">Platsen är som standard `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="4b906-123">By default, the location is `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span>

5. <span data-ttu-id="4b906-124">Kopiera dessa .cab till en plats som Kan nås av Microsoft Support.</span><span class="sxs-lookup"><span data-stu-id="4b906-124">Copy these .cab files to a location that can be accessed by Microsoft support.</span></span> <span data-ttu-id="4b906-125">Ett exempel kan vara en lösenordsskyddad OneDrive som du kan dela med oss.</span><span class="sxs-lookup"><span data-stu-id="4b906-125">An example could be a password-protected OneDrive folder that you can share with us.</span></span>

6. <span data-ttu-id="4b906-126">Skicka ett e-postmeddelande <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">med hjälp av e-postmallen</a>för uppdateringsefterlevnad och fyll i mallen med följande information:</span><span class="sxs-lookup"><span data-stu-id="4b906-126">Send an email using the <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Update Compliance support email template</a>, and fill out the template with the following information:</span></span>
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a><span data-ttu-id="4b906-127">Se även</span><span class="sxs-lookup"><span data-stu-id="4b906-127">See also</span></span>

- [<span data-ttu-id="4b906-128">Felsöka Windows Defender Microsoft Defender Antivirus rapportering</span><span class="sxs-lookup"><span data-stu-id="4b906-128">Troubleshoot Windows Defender Microsoft Defender Antivirus reporting</span></span>](troubleshoot-reporting.md)