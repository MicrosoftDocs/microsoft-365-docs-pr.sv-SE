---
title: Säkra bilagor för SharePoint, OneDrive och Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Läs mer om Microsoft Defender Office 365 för filer i SharePoint Online, OneDrive för företag och Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a74a75f12a758b9b116a3f752624df38f338d0d1
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878226"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="1f89b-103">Säkra bilagor för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1f89b-103">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1f89b-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="1f89b-104">**Applies to**</span></span>
- [<span data-ttu-id="1f89b-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="1f89b-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1f89b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1f89b-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1f89b-107">Valv Bifogade filer för SharePoint, OneDrive och Microsoft Teams i [Microsoft Defender för Office 365](whats-new-in-defender-for-office-365.md) ger ytterligare ett skyddslager för filer som redan har genomsökts vid uppladdningen av den vanliga motor för virus i [Microsoft 365.](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="1f89b-107">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="1f89b-108">Valv Bifogade filer SharePoint, OneDrive filer och Microsoft Teams hjälper till att identifiera och blockera befintliga filer som identifieras som skadliga på gruppwebbplatser och dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="1f89b-108">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="1f89b-109">Valv Bifogade filer SharePoint, OneDrive och Microsoft Teams är inte aktiverade som standard.</span><span class="sxs-lookup"><span data-stu-id="1f89b-109">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="1f89b-110">Om du vill aktivera den går [du till Aktivera Valv för SharePoint, OneDrive och Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="1f89b-110">To turn it on, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="1f89b-111">Hur Valv bifogade filer SharePoint, OneDrive och Microsoft Teams fungerar</span><span class="sxs-lookup"><span data-stu-id="1f89b-111">How Safe Attachments for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="1f89b-112">När Valv bifogade filer för SharePoint, OneDrive och Microsoft Teams är aktiverat och identifierar en fil som skadlig är filen låst med direkt integrering med filbutikerna.</span><span class="sxs-lookup"><span data-stu-id="1f89b-112">When Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="1f89b-113">Följande bild visar ett exempel på en skadlig fil som upptäckts i ett bibliotek.</span><span class="sxs-lookup"><span data-stu-id="1f89b-113">The following image shows an example of a malicious file detected in a library.</span></span>

![Filer i OneDrive för företag där en identifierades som skadlig](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="1f89b-115">Även om den blockerade filen fortfarande finns med i dokumentbiblioteket och i webb-, mobil- eller datorprogram kan andra inte öppna, kopiera, flytta eller dela filen.</span><span class="sxs-lookup"><span data-stu-id="1f89b-115">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="1f89b-116">Men de kan ta bort den blockerade filen.</span><span class="sxs-lookup"><span data-stu-id="1f89b-116">But they can delete the blocked file.</span></span>

<span data-ttu-id="1f89b-117">Här är ett exempel på hur en blockerad fil ser ut på en mobil enhet:</span><span class="sxs-lookup"><span data-stu-id="1f89b-117">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![Ta bort en blockerad fil från OneDrive för företag från OneDrive-mobilappen](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="1f89b-119">Som standard kan personer ladda ned en blockerad fil.</span><span class="sxs-lookup"><span data-stu-id="1f89b-119">By default, people can download a blocked file.</span></span> <span data-ttu-id="1f89b-120">Så här ser nedladdningen av en blockerad fil ut på en mobil enhet:</span><span class="sxs-lookup"><span data-stu-id="1f89b-120">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![En blockerad fil hämtas i OneDrive för företag](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="1f89b-122">SharePoint Onlineadministratörer kan hindra användare från att ladda ned skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="1f89b-122">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="1f89b-123">Instruktioner finns i Använda [SharePoint Online PowerShell för att hindra användare från att hämta skadliga filer.](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)</span><span class="sxs-lookup"><span data-stu-id="1f89b-123">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="1f89b-124">Mer information om användarupplevelsen när en fil har identifierats som skadlig finns i Vad kan jag göra när en skadlig fil hittas i [SharePoint Online, OneDrive eller Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span><span class="sxs-lookup"><span data-stu-id="1f89b-124">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="1f89b-125">Visa information om skadliga filer som upptäckts Valv bifogade filer för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1f89b-125">View information about malicious files detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="1f89b-126">Filer som identifieras som skadliga av Valv Bifogade filer för SharePoint, OneDrive och Microsoft Teams visas i rapporter för [Microsoft Defender för Office 365](view-reports-for-mdo.md) och i [Utforskaren (och](threat-explorer.md)identifieringar i realtid).</span><span class="sxs-lookup"><span data-stu-id="1f89b-126">Files that are identified as malicious by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams will show up in [reports for Microsoft Defender for Office 365](view-reports-for-mdo.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="1f89b-127">Efter maj 2018, när en fil identifieras som skadlig av Valv Bifogade filer för SharePoint, OneDrive och Microsoft Teams, finns filen även i karantän.</span><span class="sxs-lookup"><span data-stu-id="1f89b-127">As of May 2018, when a file is identified as malicious by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, the file is also available in quarantine.</span></span> <span data-ttu-id="1f89b-128">Mer information finns i Använda [Defender Microsoft 365 portalen](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)för att hantera filer i karantän i Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="1f89b-128">For more information, see [Use the Microsoft 365 Defender portal to manage quarantined files in Defender for Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="1f89b-129">Tänk på följande punkter</span><span class="sxs-lookup"><span data-stu-id="1f89b-129">Keep these points in mind</span></span>

- <span data-ttu-id="1f89b-130">Defender för Office 365 genomsöker inte alla filer i SharePoint Online, OneDrive för företag eller Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1f89b-130">Defender for Office 365 will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="1f89b-131">Detta är avsiktligt.</span><span class="sxs-lookup"><span data-stu-id="1f89b-131">This is by design.</span></span> <span data-ttu-id="1f89b-132">Filer genomsöks asynkront.</span><span class="sxs-lookup"><span data-stu-id="1f89b-132">Files are scanned asynchronously.</span></span> <span data-ttu-id="1f89b-133">I processen används delning och gästaktivitetshändelser tillsammans med smart heuristics och hotsignaler för att identifiera skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="1f89b-133">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="1f89b-134">Kontrollera att dina SharePoint är konfigurerade för att använda [det moderna använda-upplevelsen.](/sharepoint/guide-to-sharepoint-modern-experience)</span><span class="sxs-lookup"><span data-stu-id="1f89b-134">Make sure your SharePoint sites are configured to use the [Modern experience](/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="1f89b-135">Defender Office 365 skydd gäller oavsett om det moderna eller den klassiska vyn används. Men visuella indikatorerna för att en fil blockeras är endast tillgängliga i det moderna användande programmet.</span><span class="sxs-lookup"><span data-stu-id="1f89b-135">Defender for Office 365 protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="1f89b-136">Valv Bifogade filer i SharePoint, OneDrive och Microsoft Teams är en del av organisationens övergripande strategi för skydd mot hot, som omfattar skydd mot skräppost och skadlig programvara i Exchange Online Protection (EOP) samt Valv-länkar och Valv-bilagor i Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="1f89b-136">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="1f89b-137">Mer information finns i [Skydda mot hot i Office 365](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="1f89b-137">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
