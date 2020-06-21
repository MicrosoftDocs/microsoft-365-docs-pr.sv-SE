---
title: ATP för SharePoint, OneDrive och Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 03/19/2019
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Lär dig mer om avancerat skydd mot Office 365 för filer i SharePoint Online, OneDrive för företag och Microsoft Teams.
ms.openlocfilehash: e4a711d6554ffcb8e291d5b2154120d078995e94
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815415"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="0afbe-103">ATP för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0afbe-103">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="0afbe-104">Översikt över Office 365 ATP för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0afbe-104">Overview of Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="0afbe-105">Personer delar regelbundet filer och samarbetar med SharePoint, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0afbe-105">People regularly share files and collaborate using SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="0afbe-106">Med [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kan din organisation samarbeta på ett säkrare sätt.</span><span class="sxs-lookup"><span data-stu-id="0afbe-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can collaborate in a safer manner.</span></span> <span data-ttu-id="0afbe-107">ATP hjälper till att identifiera och blockera filer som identifieras som skadliga på gruppwebbplatser och dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="0afbe-107">ATP helps detect and block files that are identified as malicious in team sites and document libraries.</span></span>

## <a name="how-office-365-atp-operates"></a><span data-ttu-id="0afbe-108">Så här fungerar Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="0afbe-108">How Office 365 ATP operates</span></span>

<span data-ttu-id="0afbe-109">När en fil i SharePoint Online, OneDrive för företag och Microsoft Teams har identifierats som skadlig integreras ATP direkt med filarkiven för att låsa filen.</span><span class="sxs-lookup"><span data-stu-id="0afbe-109">When a file in SharePoint Online, OneDrive for Business, and Microsoft Teams has been identified as malicious, ATP directly integrates with the file stores to lock that file.</span></span> <span data-ttu-id="0afbe-110">Följande bild visar ett exempel på en skadlig fil som har identifierats i ett bibliotek.</span><span class="sxs-lookup"><span data-stu-id="0afbe-110">The following image shows an example of a malicious file detected in a library.</span></span>

![Filer i OneDrive för företag med en som har identifierats som skadlig](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="0afbe-112">Även om den blockerade filen fortfarande finns med i dokumentbiblioteket och webb-, mobil- eller skrivbordsprogram, kan den blockerade filen inte öppnas, kopieras, flyttas eller delas.</span><span class="sxs-lookup"><span data-stu-id="0afbe-112">Although the blocked file is still listed in the document library and web, mobile, or desktop applications, the blocked file cannot be opened, copied, moved, or shared.</span></span> <span data-ttu-id="0afbe-113">Andra kan dock ta bort en blockerad fil.</span><span class="sxs-lookup"><span data-stu-id="0afbe-113">People can, however, delete a blocked file.</span></span> <span data-ttu-id="0afbe-114">Här är ett exempel på hur det ser ut på en användares mobila enhet:</span><span class="sxs-lookup"><span data-stu-id="0afbe-114">Here's an example of what that looks like on a user's mobile device:</span></span>

![Ta bort en blockerad fil från OneDrive för företag från OneDrive-mobilappen](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="0afbe-116">Beroende på hur Microsoft 365 är konfigurerat kan det hända att personer kan hämta en blockerad fil eller inte.</span><span class="sxs-lookup"><span data-stu-id="0afbe-116">Depending on how Microsoft 365 is configured, people might or might not have the ability to download a blocked file.</span></span> <span data-ttu-id="0afbe-117">Så här ser det ut att hämta en blockerad fil på en användares mobila enhet:</span><span class="sxs-lookup"><span data-stu-id="0afbe-117">Here's what downloading a blocked file looks like on a user's mobile device:</span></span>

![Hämta en blockerad fil i OneDrive för företag](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="0afbe-119">Mer information finns i [Aktivera Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="0afbe-119">To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="0afbe-120">Tänk på dessa punkter</span><span class="sxs-lookup"><span data-stu-id="0afbe-120">Keep these points in mind</span></span>

- <span data-ttu-id="0afbe-121">ATP söker inte igenom varenda fil i SharePoint Online, OneDrive för företag eller Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0afbe-121">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="0afbe-122">Detta är avsiktligt.</span><span class="sxs-lookup"><span data-stu-id="0afbe-122">This is by design.</span></span> <span data-ttu-id="0afbe-123">Filer skannas asynkront, genom en process som använder delnings- och gästaktivitetshändelser tillsammans med smarta heuristik och hotsignaler för att identifiera skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="0afbe-123">Files are scanned asynchronously, through a process that uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="0afbe-124">Kontrollera att dina SharePoint-webbplatser är konfigurerade för att använda den [moderna upplevelsen](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span><span class="sxs-lookup"><span data-stu-id="0afbe-124">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="0afbe-125">När en fil identifieras som skadlig och blockerad kan andra se att detta har inträffat i den moderna upplevelsen, men inte den klassiska vyn.</span><span class="sxs-lookup"><span data-stu-id="0afbe-125">When a file is identified as malicious and blocked, people can see that this has occurred in the Modern experience, but not the Classic view.</span></span> <span data-ttu-id="0afbe-126">ATP-skydd gäller oavsett om den moderna upplevelsen eller den klassiska vyn används. Visuella indikatorer som en fil är blockerad finns dock bara i den moderna upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="0afbe-126">ATP protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are present only in the Modern experience.</span></span>

- <span data-ttu-id="0afbe-127">Filer som identifieras som skadliga i SharePoint Online, OneDrive för företag eller Microsoft Teams visas i [rapporter för avancerat skydd mot Office 365](view-reports-for-atp.md) och i [Explorer (och realtidsidentifieringar).](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="0afbe-127">Files that are identified as malicious in SharePoint Online, OneDrive for Business, or Microsoft Teams will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

- <span data-ttu-id="0afbe-128">ATP är en del av organisationens övergripande strategi för skydd av hot, som omfattar skydd mot skräppost och skadlig kod, samt säkra länkar och säkra bilagor.</span><span class="sxs-lookup"><span data-stu-id="0afbe-128">ATP is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection, as well as Safe Links and Safe Attachments.</span></span> <span data-ttu-id="0afbe-129">Mer information finns [i Skydda mot hot i Office 365](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="0afbe-129">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>

- <span data-ttu-id="0afbe-130">En SharePoint Online-administratör kan avgöra om personer ska kunna hämta filer som identifieras som skadliga.</span><span class="sxs-lookup"><span data-stu-id="0afbe-130">A SharePoint Online administrator can determine whether to enable people to download files that are detected as malicious.</span></span> <span data-ttu-id="0afbe-131">Detta görs genom att köra cmdleten Set-SPOTenant PowerShell med parametern DisallowInfectedFileDownload (se [Aktivera Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).</span><span class="sxs-lookup"><span data-stu-id="0afbe-131">This is done by running the Set-SPOTenant PowerShell cmdlet using a DisallowInfectedFileDownload parameter (see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).</span></span>

## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="0afbe-132">Karantän i ATP för SharePoint Online, OneDrive för företag och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0afbe-132">Quarantine in ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams</span></span>

 <span data-ttu-id="0afbe-133">Från och med slutet av maj 2018 utökas [karantänfunktionerna](quarantine-email-messages.md) i Security &amp; Compliance Center till ATP för SharePoint Online, OneDrive för företag och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0afbe-133">Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="0afbe-134">När en fil i SharePoint Online, OneDrive för företag eller Microsoft Teams identifieras som skadlig, förutom att ATP blockerar filen från att öppnas eller delas, inkluderas filen i en lista över objekt i karantän.</span><span class="sxs-lookup"><span data-stu-id="0afbe-134">When a file in SharePoint Online, OneDrive for Business, or Microsoft Teams is identified as malicious, in addition to ATP blocking the file from being opened or shared, that file is included in a list of quarantined items.</span></span> <span data-ttu-id="0afbe-135">(I säkerhets- &amp; Compliance Center, gå till **Threat Management** \> **Review** \> **Karantän** och filter för **filer**.)</span><span class="sxs-lookup"><span data-stu-id="0afbe-135">(In the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Quarantine** and filter for **Files**.)</span></span>

<span data-ttu-id="0afbe-136">Om du ingår i organisationens Microsoft 365 för företagssäkerhetsteam och har de behörigheter som krävs [som tilldelats i Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)kan du hämta, släppa, rapportera och ta bort filer som identifieras som skadliga av ATP från karantänen.</span><span class="sxs-lookup"><span data-stu-id="0afbe-136">If you're part of your organization's Microsoft 365 for business security team and have the necessary [permissions assigned in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can download, release, report, and delete files that are detected as malicious by ATP from quarantine.</span></span>

- <span data-ttu-id="0afbe-137">**Om du släpper och rapporterar** en fil tas ATP-blocket bort på filen på respektive gruppwebbplats eller dokumentbibliotek för SharePoint, OneDrive eller Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0afbe-137">**Releasing and reporting** a file removes the ATP block on the file in the respective team site or document library for SharePoint, OneDrive, or Microsoft Teams.</span></span> <span data-ttu-id="0afbe-138">Användarna kan sedan öppna, dela och hämta filen.</span><span class="sxs-lookup"><span data-stu-id="0afbe-138">Users are then able to open, share, and download the file.</span></span> <span data-ttu-id="0afbe-139">Och när alternativet **Skicka rapport till Microsoft** är markerat rapporteras filen som falskt positivt för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0afbe-139">And, when the **Send report to Microsoft** option is selected, the file is reported as a false positive to Microsoft.</span></span>

- <span data-ttu-id="0afbe-140">**Om du tar bort en fil** tas filen bort från karantänen. Filen är dock fortfarande blockerad från att öppnas eller delas.</span><span class="sxs-lookup"><span data-stu-id="0afbe-140">**Deleting a file** removes the file from quarantine; however, the file is still blocked from being opened or shared.</span></span> <span data-ttu-id="0afbe-141">Filen måste också tas bort i respektive dokumentbibliotek eller gruppwebbplats (SharePoint Online, OneDrive för företag eller Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="0afbe-141">The file must also be deleted in its respective document library or team site (SharePoint Online, OneDrive for Business, or Microsoft Teams).</span></span>

- <span data-ttu-id="0afbe-142">**Genom att hämta en fil** kan du hämta och analysera filen för eventuella falska positiva identifieringar.</span><span class="sxs-lookup"><span data-stu-id="0afbe-142">**Downloading a file** enables you to download and analyze the file for any false positives.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0afbe-143">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="0afbe-143">Next steps</span></span>

 - [<span data-ttu-id="0afbe-144">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0afbe-144">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-atp-for-spo-odb-and-teams.md)

 - [<span data-ttu-id="0afbe-145">Visa information om skadliga filer som upptäckts i SharePoint, OneDrive eller Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0afbe-145">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)

