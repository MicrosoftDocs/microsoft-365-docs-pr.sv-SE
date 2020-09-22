---
title: Så fungerar ATP – säkra bifogade filer
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du kan skydda din organisation från skadliga filer med hjälp av säkra bifogade filer för Office 365.
ms.openlocfilehash: d13674a5d3e769fc10a1f5fd2fd80a4f07c063de
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201483"
---
# <a name="how-atp-safe-attachments-works"></a><span data-ttu-id="329d1-103">Så fungerar ATP – säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="329d1-103">How ATP Safe Attachments works</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="329d1-104">Med funktionen för säker e-poståtkomst för ATP kontrol leras användarna i din organisation.</span><span class="sxs-lookup"><span data-stu-id="329d1-104">The ATP Safe Attachments feature checks email attachments for people in your organization.</span></span> <span data-ttu-id="329d1-105">När det finns en princip för att skydda ett ATP-filer på plats och någon som täcks av den policyn visar deras e-post i Office 365, kontrol leras deras e-postbilagor och lämpliga åtgärder vidtas, baserat på dina principer för säker åtkomst</span><span class="sxs-lookup"><span data-stu-id="329d1-105">When an ATP Safe Attachments policy is in place and someone covered by that policy views their email in Office 365, their email attachments are checked and appropriate actions are taken, based on your ATP Safe Attachments policies.</span></span> <span data-ttu-id="329d1-106">Beroende på hur dina principer är definierade kan andra fortsätta att arbeta utan att veta att de har skickat skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="329d1-106">Depending on how your policies are defined, people can continue working without ever knowing they were sent malicious files.</span></span>
  
<span data-ttu-id="329d1-107">Här är två exempel på säkra filer för ATP-säkerhet på jobbet.</span><span class="sxs-lookup"><span data-stu-id="329d1-107">Here are two examples of ATP Safe Attachments at work.</span></span>
  
- <span data-ttu-id="329d1-108">**Exempel 1: e-postbilaga** Antag att Aaron Lee får ett e-postmeddelande med en bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="329d1-108">**Example 1: Email attachment** Suppose that Lee receives an email message that has an attachment.</span></span> <span data-ttu-id="329d1-109">Det är inte uppenbart för Aaron Lee om den bifogade filen är säker eller om den faktiskt innehåller skadlig program vara som är utformad för att stjäla Aaron Lee.</span><span class="sxs-lookup"><span data-stu-id="329d1-109">It is not obvious to Lee whether that attachment is safe or actually contains malware designed to steal Lee's user credentials.</span></span> <span data-ttu-id="329d1-110">I Aaron Lee organisation är en säkerhets administratör som har definierat en policy för säkerhet för ATP-filer för antal dagar sedan.</span><span class="sxs-lookup"><span data-stu-id="329d1-110">In Lee's organization, a security administrator defined an ATP Safe Attachments policy a few days ago.</span></span> <span data-ttu-id="329d1-111">Med funktionen för säker e-postbilagor öppnas och testas den bifogade filen i en virtuell miljö innan Aaron Lee tas emot.</span><span class="sxs-lookup"><span data-stu-id="329d1-111">With the ATP Safe Attachments feature, the email attachment is opened and tested in a virtual environment before Lee receives it.</span></span> <span data-ttu-id="329d1-112">Om den bifogade filen bedöms vara skadlig tas den bort automatiskt.</span><span class="sxs-lookup"><span data-stu-id="329d1-112">If the attachment is determined to be malicious, it will be removed automatically.</span></span> <span data-ttu-id="329d1-113">Om den bifogade filen är säker öppnas den som förväntat när Aaron Lee klickar på den.</span><span class="sxs-lookup"><span data-stu-id="329d1-113">If the attachment is safe, it will open as expected when Lee clicks on it.</span></span>

- <span data-ttu-id="329d1-114">**Exempel 2: fil i SharePoint Online** Antag att Jean har tagit emot en fil och ladda upp den till ett bibliotek i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="329d1-114">**Example 2: File in SharePoint Online** Suppose that Jean received a file and uploaded it into a library in SharePoint Online.</span></span> <span data-ttu-id="329d1-115">Jean delar länken till filen med resten av gruppen, och vet inte att filen faktiskt är skadlig.</span><span class="sxs-lookup"><span data-stu-id="329d1-115">Jean shares the link to the file with the rest of the team, not knowing that the file is actually malicious.</span></span> <span data-ttu-id="329d1-116">Lyckligt vis kommer [ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) att identifiera den skadliga filen och blockera den.</span><span class="sxs-lookup"><span data-stu-id="329d1-116">Fortunately, [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) detects the malicious file and blocks it.</span></span> <span data-ttu-id="329d1-117">Ett par dagar senare kan Chris öppna dokumentet.</span><span class="sxs-lookup"><span data-stu-id="329d1-117">A few days later, Chris goes to open the document.</span></span> <span data-ttu-id="329d1-118">Men Chris kan se att filen är där kan Chris inte öppna eller dela den, vilket skyddar Chris användare från den skadliga filen.</span><span class="sxs-lookup"><span data-stu-id="329d1-118">Although Chris can see the file is there, Chris cannot open or share it, which protects Chris's computer and others from the malicious file.</span></span>

<span data-ttu-id="329d1-119">Säkerhets principer för ATP-säkerhet kan användas för vissa personer eller grupper i din organisation eller till hela domänen.</span><span class="sxs-lookup"><span data-stu-id="329d1-119">ATP Safe Attachments policies can be applied to specific people or groups in your organization, or to your entire domain.</span></span> <span data-ttu-id="329d1-120">Dessutom kan principer för säkra bifogade filer för ATP konfigureras för användning av bifogade filer för plats hållare när faktiska bilagor skannas.</span><span class="sxs-lookup"><span data-stu-id="329d1-120">In addition, ATP Safe Attachments policies can be configured to use placeholder attachments while actual attachments are being scanned.</span></span> <span data-ttu-id="329d1-121">Mer information finns i **[Konfigurera principer för säkrade säkerhets meddelanden för ATP i Office 365](set-up-atp-safe-attachments-policies.md)**.</span><span class="sxs-lookup"><span data-stu-id="329d1-121">To learn more, see **[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)**.</span></span>

> [!NOTE]
> <span data-ttu-id="329d1-122">ATP Safe Attachments scanning sker i samma region där dina data finns.</span><span class="sxs-lookup"><span data-stu-id="329d1-122">ATP Safe Attachments scanning takes place in the same region where your data resides.</span></span> <span data-ttu-id="329d1-123">Mer information om data Center geografi finns i [var finns dina data?](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="329d1-123">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 

