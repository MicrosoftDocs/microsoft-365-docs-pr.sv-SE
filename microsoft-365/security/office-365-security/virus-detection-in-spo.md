---
title: Virusskydd i SharePoint Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Lär dig mer om hur SharePoint Online identifierar virus i filer som användare laddar upp och förhindrar att användare laddar ned och synkroniserar filerna.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0e58fa8dc8b30c5bc6ff5db1508d8b7f9189b73a
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653515"
---
# <a name="virus-detection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="67396-103">Virus identifiering i SharePoint Online, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="67396-103">Virus detection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="67396-104">Microsoft 365 skyddar din miljö mot skadlig program vara genom att upptäcka virus i filer som användare laddar upp till SharePoint Online, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="67396-104">Microsoft 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="67396-105">Filer kan genomsökas efter virus när de har laddats upp.</span><span class="sxs-lookup"><span data-stu-id="67396-105">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="67396-106">Om en fil är infekterad anges en egenskap så att användare inte kan ladda ned eller synkronisera filen.</span><span class="sxs-lookup"><span data-stu-id="67396-106">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67396-107">Dessa Antivirus funktioner i SharePoint Online är ett sätt att innehålla virus.</span><span class="sxs-lookup"><span data-stu-id="67396-107">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="67396-108">De är inte avsedda som en enda försvars punkt mot skadlig program vara för din miljö.</span><span class="sxs-lookup"><span data-stu-id="67396-108">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="67396-109">Vi uppmuntrar alla kunder att utvärdera och implementera skydd mot skadlig program vara på olika lager och tillämpa metod tips för att skydda företagets infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="67396-109">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="67396-110">Mer information om strategier och metod tips finns i [säkerhets översikt](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="67396-110">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="67396-111">Vad händer när en angripen fil laddas upp till SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="67396-111">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="67396-112">Microsoft 365 använder en vanlig Antivirus funktion.</span><span class="sxs-lookup"><span data-stu-id="67396-112">Microsoft 365 uses a common virus detection engine.</span></span> <span data-ttu-id="67396-113">Motorn körs asynkront i SharePoint Online och vissa filer genomsöks efter att de har laddats upp.</span><span class="sxs-lookup"><span data-stu-id="67396-113">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="67396-114">Heuristik används för att avgöra vilka filer som genomsöks.</span><span class="sxs-lookup"><span data-stu-id="67396-114">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="67396-115">När en fil hittas som innehåller ett virus flaggas den så att den inte kan hämtas igen.</span><span class="sxs-lookup"><span data-stu-id="67396-115">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="67396-116">I april 2018 tog vi bort 25 MB-gränsen för inlästa filer.</span><span class="sxs-lookup"><span data-stu-id="67396-116">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="67396-117">Så här gör du:</span><span class="sxs-lookup"><span data-stu-id="67396-117">Here's what happens:</span></span>

1. <span data-ttu-id="67396-118">En användare laddar upp en fil till SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="67396-118">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="67396-119">SharePoint Online bestämmer om filen uppfyller villkoren för en sökning.</span><span class="sxs-lookup"><span data-stu-id="67396-119">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="67396-120">Antivirus verktyget söker igenom filen.</span><span class="sxs-lookup"><span data-stu-id="67396-120">The virus detection engine scans the file.</span></span>

4. <span data-ttu-id="67396-121">Om ett virus hittas anger Antivirus motorn en egenskap för filen som anger att den är smittad.</span><span class="sxs-lookup"><span data-stu-id="67396-121">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="67396-122">Vad händer när en användare försöker ladda ned en infekterad fil med webbläsaren?</span><span class="sxs-lookup"><span data-stu-id="67396-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="67396-123">Om en fil är infekterad kan användare inte ladda ned filen från SharePoint Online med hjälp av webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="67396-123">If a file is infected, users can't download the file from SharePoint Online by using the browser.</span></span>

<span data-ttu-id="67396-124">Så här gör du:</span><span class="sxs-lookup"><span data-stu-id="67396-124">Here's what happens:</span></span>

1. <span data-ttu-id="67396-125">En användare öppnar en webbläsare och försöker ladda ned en angripen fil från SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="67396-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>

2. <span data-ttu-id="67396-126">Användaren får ett varnings meddelande om att ett virus har hittats.</span><span class="sxs-lookup"><span data-stu-id="67396-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="67396-127">Användaren kan välja att ladda ner filen och försöka rensa den med hjälp av sitt eget antivirus program.</span><span class="sxs-lookup"><span data-stu-id="67396-127">The user is given the option to download the file and attempt to clean it using their own antivirus software.</span></span>

> [!NOTE]
>
> <span data-ttu-id="67396-128">Du kan använda parametern *DisallowInfectedFileDownload* i cmdleten [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) i SharePoint Online PowerShell för att förhindra att användare laddar ned en angripen fil, även i fönstret antivirus varning.</span><span class="sxs-lookup"><span data-stu-id="67396-128">You can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading an infected file, even in the anti-virus warning window.</span></span>
>
> <span data-ttu-id="67396-129">Tänk på att när du aktiverar *DisallowInfectedFileDownload* -parametern är det också bra att komma åt de identifierade/blockerade filerna helt och hållet för användare och administratörer.</span><span class="sxs-lookup"><span data-stu-id="67396-129">Also keep in mind, that as soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completly blocked for users and administrators.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="67396-130">Vad händer när en OneDrive-synkroniseringsklient försöker synkronisera en infekterad fil?</span><span class="sxs-lookup"><span data-stu-id="67396-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="67396-131">Om användarna synkroniserar filer med den nya synkroniseringsklienten för OneDrive (OneDrive.exe) eller den föregående synkroniseringsklienten för OneDrive för företag (Groove.exe) om en fil innehåller ett virus laddas inte synkroniseringsklienten.</span><span class="sxs-lookup"><span data-stu-id="67396-131">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="67396-132">Synkroniseringsklienten visar ett meddelande om att filen inte kan synkroniseras.</span><span class="sxs-lookup"><span data-stu-id="67396-132">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-office-365-atp"></a><span data-ttu-id="67396-133">Utökade funktioner med Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="67396-133">Extended capabilities with Office 365 ATP</span></span>

<span data-ttu-id="67396-134">Kunder som har aktiverat Office 365 ATP för SharePoint, OneDrive och Microsoft Teams [aktiverar ATP för SharePoint, OneDrive och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) för att använda säkerhets & Compliance Center för att hantera filer i karantänen för av-och ATP-identifieringar.</span><span class="sxs-lookup"><span data-stu-id="67396-134">Customers who enabled Office 365 ATP for Sharepoint, OneDrive, and Microsoft Teams [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) are able to use the Security & Compliance Center to manage quarantined files for AV and ATP detections.</span></span> <span data-ttu-id="67396-135">[Endast ATP: Använd säkerhets & Compliance Center för att hantera filer i karantän](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span><span class="sxs-lookup"><span data-stu-id="67396-135">[ATP Only: Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="more-information"></a><span data-ttu-id="67396-136">Mer information</span><span class="sxs-lookup"><span data-stu-id="67396-136">More information</span></span>

<span data-ttu-id="67396-137">Se [skydda mot hot](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) och [Aktivera ATP för SharePoint, OneDrive och Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) om du vill ha mer information om hur du konfigurerar SharePoint Online Antivirus.</span><span class="sxs-lookup"><span data-stu-id="67396-137">See [Protect against threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) for more information on how to configure SharePoint Online antivirus.</span></span>


