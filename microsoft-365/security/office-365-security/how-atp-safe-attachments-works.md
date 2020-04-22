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
ms.collection:
- M365-security-compliance
description: Funktionen Säkra bilagor ger snabb verifiering av e-postbilagor. Använd Säkra bilagor för att skydda din organisation från skadliga filer som personer skickar eller ta emot via e-post.
ms.openlocfilehash: e53d95a52c6990b5e0b4ff81f42414a34b1e606e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638028"
---
# <a name="how-atp-safe-attachments-works"></a><span data-ttu-id="f2ce1-104">Så fungerar ATP – säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="f2ce1-104">How ATP Safe Attachments works</span></span>

## <a name="how-it-works"></a><span data-ttu-id="f2ce1-105">Så här fungerar det</span><span class="sxs-lookup"><span data-stu-id="f2ce1-105">How it works</span></span>

<span data-ttu-id="f2ce1-106">Funktionen Betrodda atp-bilagor kontrollerar e-postbilagor för personer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="f2ce1-106">The ATP Safe Attachments feature checks email attachments for people in your organization.</span></span> <span data-ttu-id="f2ce1-107">När en ATP-princip för säkra bilagor finns på plats och någon som omfattas av den principen visar sin e-post i Office 365 kontrolleras deras e-postbilagor och lämpliga åtgärder vidtas, baserat på dina ATP-principer för säkra bilagor.</span><span class="sxs-lookup"><span data-stu-id="f2ce1-107">When an ATP Safe Attachments policy is in place and someone covered by that policy views their email in Office 365, their email attachments are checked and appropriate actions are taken, based on your ATP Safe Attachments policies.</span></span> <span data-ttu-id="f2ce1-108">Beroende på hur dina principer definieras kan användarna fortsätta arbeta utan att någonsin veta att de har skickats skadliga filer.</span><span class="sxs-lookup"><span data-stu-id="f2ce1-108">Depending on how your policies are defined, people can continue working without ever knowing they were sent malicious files.</span></span>
  
<span data-ttu-id="f2ce1-109">Här är två exempel på ATP Säkra bilagor på jobbet.</span><span class="sxs-lookup"><span data-stu-id="f2ce1-109">Here are two examples of ATP Safe Attachments at work.</span></span>
  
- <span data-ttu-id="f2ce1-110">**Exempel 1: Bifogad e-post** Anta att Lee får ett e-postmeddelande som har en bifogad fil.</span><span class="sxs-lookup"><span data-stu-id="f2ce1-110">**Example 1: Email attachment** Suppose that Lee receives an email message that has an attachment.</span></span> <span data-ttu-id="f2ce1-111">Det är inte självklart att Lee om denna bilaga är säker eller faktiskt innehåller skadlig kod för att stjäla Lees användaruppgifter.</span><span class="sxs-lookup"><span data-stu-id="f2ce1-111">It is not obvious to Lee whether that attachment is safe or actually contains malware designed to steal Lee's user credentials.</span></span> <span data-ttu-id="f2ce1-112">I Lees organisation definierade en säkerhetsadministratör en ATP Safe Attachments-princip för några dagar sedan.</span><span class="sxs-lookup"><span data-stu-id="f2ce1-112">In Lee's organization, a security administrator defined an ATP Safe Attachments policy a few days ago.</span></span> <span data-ttu-id="f2ce1-113">Med funktionen BETRODDa ATP-bilagor öppnas och testas e-postbilagan i en virtuell miljö innan Lee tar emot den.</span><span class="sxs-lookup"><span data-stu-id="f2ce1-113">With the ATP Safe Attachments feature, the email attachment is opened and tested in a virtual environment before Lee receives it.</span></span> <span data-ttu-id="f2ce1-114">Om den bifogade filen bedöms vara skadlig tas den bort automatiskt.</span><span class="sxs-lookup"><span data-stu-id="f2ce1-114">If the attachment is determined to be malicious, it will be removed automatically.</span></span> <span data-ttu-id="f2ce1-115">Om bilagan är säker öppnas den som förväntat när Lee klickar på den.</span><span class="sxs-lookup"><span data-stu-id="f2ce1-115">If the attachment is safe, it will open as expected when Lee clicks on it.</span></span>

- <span data-ttu-id="f2ce1-116">**Exempel 2: Fil i SharePoint Online** Anta att Jean tog emot en fil och laddade upp den till ett bibliotek i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f2ce1-116">**Example 2: File in SharePoint Online** Suppose that Jean received a file and uploaded it into a library in SharePoint Online.</span></span> <span data-ttu-id="f2ce1-117">Jean delar länken till filen med resten av teamet, utan att veta att filen faktiskt är skadlig.</span><span class="sxs-lookup"><span data-stu-id="f2ce1-117">Jean shares the link to the file with the rest of the team, not knowing that the file is actually malicious.</span></span> <span data-ttu-id="f2ce1-118">Lyckligtvis identifierar [ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) den skadliga filen och blockerar den.</span><span class="sxs-lookup"><span data-stu-id="f2ce1-118">Fortunately, [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) detects the malicious file and blocks it.</span></span> <span data-ttu-id="f2ce1-119">Några dagar senare öppnar Chris dokumentet.</span><span class="sxs-lookup"><span data-stu-id="f2ce1-119">A few days later, Chris goes to open the document.</span></span> <span data-ttu-id="f2ce1-120">Även om Chris kan se att filen finns där, kan Chris inte öppna eller dela den, vilket skyddar Chris dator och andra från den skadliga filen.</span><span class="sxs-lookup"><span data-stu-id="f2ce1-120">Although Chris can see the file is there, Chris cannot open or share it, which protects Chris's computer and others from the malicious file.</span></span>

<span data-ttu-id="f2ce1-121">ATP Principer för säkra bilagor kan tillämpas på specifika personer eller grupper i organisationen eller på hela domänen.</span><span class="sxs-lookup"><span data-stu-id="f2ce1-121">ATP Safe Attachments policies can be applied to specific people or groups in your organization, or to your entire domain.</span></span> <span data-ttu-id="f2ce1-122">Dessutom kan ATP-principer för säkra bifogade filer konfigureras för att använda platshållarbilagor medan faktiska bilagor genomsöks.</span><span class="sxs-lookup"><span data-stu-id="f2ce1-122">In addition, ATP Safe Attachments policies can be configured to use placeholder attachments while actual attachments are being scanned.</span></span> <span data-ttu-id="f2ce1-123">Mer information finns i **[Konfigurera principer för betrodda bifogade filer i Office 365.](set-up-atp-safe-attachments-policies.md)**</span><span class="sxs-lookup"><span data-stu-id="f2ce1-123">To learn more, see **[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)**.</span></span>

> [!NOTE]
> <span data-ttu-id="f2ce1-124">ATP-skanning av säkra bilagor sker i samma region där dina data finns.</span><span class="sxs-lookup"><span data-stu-id="f2ce1-124">ATP Safe Attachments scanning takes place in the same region where your data resides.</span></span> <span data-ttu-id="f2ce1-125">Mer information om datacentergeografi finns i [Var finns dina data?](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="f2ce1-125">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 

