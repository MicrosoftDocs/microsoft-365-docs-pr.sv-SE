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
description: Lär dig mer om hur SharePoint Online identifierar virus i filer som användare laddar upp och hindrar användare från att hämta eller synkronisera filerna.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 60d696769ea402e6e2d0e52a1f6633e7962b8329
ms.sourcegitcommit: f2275d2fbc17a8b5b5da723c7353d3f36c6fb2a7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2020
ms.locfileid: "45029614"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="2b3d7-103">Virusskydd i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2b3d7-103">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="2b3d7-104">Microsoft 365 kan skydda din miljö från skadlig kod genom att upptäcka virus i filer som användare laddar upp till SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-104">Microsoft 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="2b3d7-105">Filer kan sökas efter virus när de har laddats upp.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-105">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="2b3d7-106">Om det visar sig att en fil är infekterad anges en egenskap så att användarna inte kan hämta eller synkronisera filen.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-106">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b3d7-107">Dessa antivirusfunktioner i SharePoint Online är ett sätt att innehålla virus.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-107">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="2b3d7-108">De är inte avsedda som en enda försvarspunkt mot skadlig kod för din miljö.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-108">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="2b3d7-109">Vi uppmuntrar alla kunder att bedöma och implementera skydd mot skadlig kod på olika lager och tillämpa bästa praxis för att skydda företagets infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-109">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="2b3d7-110">Mer information om strategier och metodtips finns i [Översikt över säkerhet](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="2b3d7-110">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="2b3d7-111">Vad händer när en infekterad fil överförs till SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="2b3d7-111">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="2b3d7-112">Microsoft 365 använder en vanlig virusdetekteringsmotor.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-112">Microsoft 365 uses a common virus detection engine.</span></span> <span data-ttu-id="2b3d7-113">Motorn körs asynkront i SharePoint Online och söker igenom vissa filer när de har laddats upp.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-113">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="2b3d7-114">Heuristik används för att avgöra vilka filer som skannas.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-114">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="2b3d7-115">När en fil visar sig innehålla ett virus flaggas den så att den inte kan hämtas igen.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-115">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="2b3d7-116">I april 2018 tog vi bort gränsen på 25 MB för skannade filer.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-116">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="2b3d7-117">Så här går det till:</span><span class="sxs-lookup"><span data-stu-id="2b3d7-117">Here's what happens:</span></span>

1. <span data-ttu-id="2b3d7-118">En användare laddar upp en fil till SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-118">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="2b3d7-119">SharePoint Online avgör om filen uppfyller kriterierna för en genomsökning.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-119">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="2b3d7-120">Virusdetekteringsmotorn söker igenom filen.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-120">The virus detection engine scans the file.</span></span>

4. <span data-ttu-id="2b3d7-121">Om ett virus hittas anger virusmotorn en egenskap på filen som anger att den är infekterad.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-121">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="2b3d7-122">Vad händer när en användare försöker hämta en infekterad fil med hjälp av webbläsaren?</span><span class="sxs-lookup"><span data-stu-id="2b3d7-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="2b3d7-123">Om en fil är infekterad kan användarna inte hämta filen från SharePoint Online med hjälp av webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-123">If a file is infected, users can't download the file from SharePoint Online by using the browser.</span></span>

<span data-ttu-id="2b3d7-124">Så här går det till:</span><span class="sxs-lookup"><span data-stu-id="2b3d7-124">Here's what happens:</span></span>

1. <span data-ttu-id="2b3d7-125">En användare öppnar en webbläsare och försöker hämta en infekterad fil från SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>

2. <span data-ttu-id="2b3d7-126">Användaren får en varning om att ett virus har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="2b3d7-127">Användaren ges möjlighet att ladda ner filen och försöka rengöra den med sitt eget antivirusprogram.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-127">The user is given the option to download the file and attempt to clean it using their own antivirus software.</span></span>

> [!NOTE]
> <span data-ttu-id="2b3d7-128">Du kan använda parametern *DisallowInfectedFileDownload* på cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) i SharePoint Online PowerShell för att förhindra att användare hämtar en infekterad fil, även i varningsfönstret mot virus.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-128">You can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading an infected file, even in the anti-virus warning window.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="2b3d7-129">Vad händer när OneDrive-synkroniseringsklienten försöker synkronisera en infekterad fil?</span><span class="sxs-lookup"><span data-stu-id="2b3d7-129">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="2b3d7-130">Oavsett om användarna synkroniserar filer med den nya OneDrive-synkroniseringsklienten (OneDrive.exe) eller den tidigare Synkroniseringsklienten för OneDrive för företag (Groove.exe), om en fil innehåller ett virus, hämtas den inte synkroniseringsklienten.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-130">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="2b3d7-131">Synkroniseringsklienten visar ett meddelande om att filen inte kan synkroniseras.</span><span class="sxs-lookup"><span data-stu-id="2b3d7-131">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="more-information"></a><span data-ttu-id="2b3d7-132">Mer information</span><span class="sxs-lookup"><span data-stu-id="2b3d7-132">More information</span></span>

<span data-ttu-id="2b3d7-133">Mer information om hur du [konfigurerar](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) SharePoint Online-antivirus finns i Skydda mot hot [och Aktivera ATP för SharePoint, OneDrive och Microsoft Teams.](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="2b3d7-133">See [Protect against threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) for more information on how to configure SharePoint Online antivirus.</span></span>


