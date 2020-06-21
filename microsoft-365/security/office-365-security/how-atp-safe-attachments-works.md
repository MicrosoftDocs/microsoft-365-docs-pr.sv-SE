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
description: Lär dig hur du skyddar organisationen från skadliga filer med ATP-säkra bilagor för Office 365.
ms.openlocfilehash: f4f355d4def1f108a72854c3796e0e9373cb5ef1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819406"
---
# <a name="how-atp-safe-attachments-works"></a><span data-ttu-id="807e9-103">Så fungerar ATP – säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="807e9-103">How ATP Safe Attachments works</span></span>

<span data-ttu-id="807e9-104">Funktionen Betrodda atp-bilagor kontrollerar e-postbilagor för personer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="807e9-104">The ATP Safe Attachments feature checks email attachments for people in your organization.</span></span> <span data-ttu-id="807e9-105">När en ATP-princip för säkra bilagor finns på plats och någon som omfattas av den principen visar sin e-post i Office 365 kontrolleras deras e-postbilagor och lämpliga åtgärder vidtas, baserat på dina ATP-principer för säkra bilagor.</span><span class="sxs-lookup"><span data-stu-id="807e9-105">When an ATP Safe Attachments policy is in place and someone covered by that policy views their email in Office 365, their email attachments are checked and appropriate actions are taken, based on your ATP Safe Attachments policies.</span></span> <span data-ttu-id="807e9-106">Beroende på hur dina principer definieras kan användarna fortsätta arbeta utan att någonsin veta att de har skickats skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="807e9-106">Depending on how your policies are defined, people can continue working without ever knowing they were sent malicious files.</span></span>
  
<span data-ttu-id="807e9-107">Här är två exempel på ATP Säkra bilagor på jobbet.</span><span class="sxs-lookup"><span data-stu-id="807e9-107">Here are two examples of ATP Safe Attachments at work.</span></span>
  
- <span data-ttu-id="807e9-108">**Exempel 1: Bifogad e-post** Anta att Lee får ett e-postmeddelande som har en bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="807e9-108">**Example 1: Email attachment** Suppose that Lee receives an email message that has an attachment.</span></span> <span data-ttu-id="807e9-109">Det är inte självklart att Lee om denna bilaga är säker eller faktiskt innehåller skadlig kod för att stjäla Lees användarreferenser.</span><span class="sxs-lookup"><span data-stu-id="807e9-109">It is not obvious to Lee whether that attachment is safe or actually contains malware designed to steal Lee's user credentials.</span></span> <span data-ttu-id="807e9-110">I Lees organisation definierade en säkerhetsadministratör en ATP Safe Attachments-princip för några dagar sedan.</span><span class="sxs-lookup"><span data-stu-id="807e9-110">In Lee's organization, a security administrator defined an ATP Safe Attachments policy a few days ago.</span></span> <span data-ttu-id="807e9-111">Med funktionen BETRODDa BILAGOR via ATP öppnas och testas e-postbilagan i en virtuell miljö innan Lee tar emot den.</span><span class="sxs-lookup"><span data-stu-id="807e9-111">With the ATP Safe Attachments feature, the email attachment is opened and tested in a virtual environment before Lee receives it.</span></span> <span data-ttu-id="807e9-112">Om den bifogade filen bedöms vara skadlig tas den bort automatiskt.</span><span class="sxs-lookup"><span data-stu-id="807e9-112">If the attachment is determined to be malicious, it will be removed automatically.</span></span> <span data-ttu-id="807e9-113">Om bilagan är säker öppnas den som förväntat när Lee klickar på den.</span><span class="sxs-lookup"><span data-stu-id="807e9-113">If the attachment is safe, it will open as expected when Lee clicks on it.</span></span>

- <span data-ttu-id="807e9-114">**Exempel 2: Fil i SharePoint Online** Anta att Jean tog emot en fil och laddade upp den till ett bibliotek i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="807e9-114">**Example 2: File in SharePoint Online** Suppose that Jean received a file and uploaded it into a library in SharePoint Online.</span></span> <span data-ttu-id="807e9-115">Jean delar länken till filen med resten av teamet, utan att veta att filen faktiskt är skadlig.</span><span class="sxs-lookup"><span data-stu-id="807e9-115">Jean shares the link to the file with the rest of the team, not knowing that the file is actually malicious.</span></span> <span data-ttu-id="807e9-116">Lyckligtvis identifierar [ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) den skadliga filen och blockerar den.</span><span class="sxs-lookup"><span data-stu-id="807e9-116">Fortunately, [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) detects the malicious file and blocks it.</span></span> <span data-ttu-id="807e9-117">Några dagar senare öppnar Chris dokumentet.</span><span class="sxs-lookup"><span data-stu-id="807e9-117">A few days later, Chris goes to open the document.</span></span> <span data-ttu-id="807e9-118">Även om Chris kan se att filen finns där, kan Chris inte öppna eller dela den, vilket skyddar Chris dator och andra från den skadliga filen.</span><span class="sxs-lookup"><span data-stu-id="807e9-118">Although Chris can see the file is there, Chris cannot open or share it, which protects Chris's computer and others from the malicious file.</span></span>

<span data-ttu-id="807e9-119">ATP Principer för säkra bifogade filer kan tillämpas på specifika personer eller grupper i organisationen eller på hela domänen.</span><span class="sxs-lookup"><span data-stu-id="807e9-119">ATP Safe Attachments policies can be applied to specific people or groups in your organization, or to your entire domain.</span></span> <span data-ttu-id="807e9-120">Dessutom kan ATP-principer för säkra bifogade filer konfigureras för att använda platshållarbilagor medan faktiska bilagor genomsöks.</span><span class="sxs-lookup"><span data-stu-id="807e9-120">In addition, ATP Safe Attachments policies can be configured to use placeholder attachments while actual attachments are being scanned.</span></span> <span data-ttu-id="807e9-121">Mer information finns **[i Konfigurera principer för betrodda bifogade filer i Office 365.](set-up-atp-safe-attachments-policies.md)**</span><span class="sxs-lookup"><span data-stu-id="807e9-121">To learn more, see **[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)**.</span></span>

> [!NOTE]
> <span data-ttu-id="807e9-122">ATP-skanning av säkra bilagor sker i samma region där dina data finns.</span><span class="sxs-lookup"><span data-stu-id="807e9-122">ATP Safe Attachments scanning takes place in the same region where your data resides.</span></span> <span data-ttu-id="807e9-123">Mer information om datacentergeografi finns i [Var finns dina data?](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="807e9-123">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 

