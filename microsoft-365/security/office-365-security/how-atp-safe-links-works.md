---
title: Så här fungerar Safe Links i Office 365 ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Funktionen Säkra länkar ger snabb verifiering av hyperlänkar i Office-dokument och i e-postmeddelanden. Läs den här artikeln om du vill veta hur ATP Safe Links fungerar.
ms.openlocfilehash: c87eef2afbb3a694d9906de0c6c43bfeb576782b
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806799"
---
# <a name="how-office-365-atp-safe-links-works"></a><span data-ttu-id="0ed70-104">Så här fungerar Safe Links i Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="0ed70-104">How Office 365 ATP Safe Links works</span></span>
> [!IMPORTANT] 
> <span data-ttu-id="0ed70-105">För att Office 365 ATP Safe Links ska fungera korrekt måste alla Office 365-tjänster vara i samma version.</span><span class="sxs-lookup"><span data-stu-id="0ed70-105">For Office 365 ATP Safe Links to operate correctly, all of the Office 365 services need to be at the same version.</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="0ed70-106">Så här fungerar ATP Safe Links med webbadresser i e-post</span><span class="sxs-lookup"><span data-stu-id="0ed70-106">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="0ed70-107">På en hög nivå fungerar så här [för ATP Safe Links-skydd](atp-safe-links.md) för webbadresser i e-post (finns i Office 365, inte lokalt):</span><span class="sxs-lookup"><span data-stu-id="0ed70-107">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="0ed70-108">Personer får e-postmeddelanden, varav vissa innehåller webbadresser.</span><span class="sxs-lookup"><span data-stu-id="0ed70-108">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="0ed70-109">All e-post går via Exchange Online Protection, där IP-filter (Internet Protocol) och kuvertfilter, signaturbaserat skydd mot skadlig kod, skräppost- och anti-malware-filter tillämpas.</span><span class="sxs-lookup"><span data-stu-id="0ed70-109">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="0ed70-110">E-post kommer i människors inkorgar.</span><span class="sxs-lookup"><span data-stu-id="0ed70-110">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="0ed70-111">En användare loggar in på Office 365 och går till sin e-postkorg.</span><span class="sxs-lookup"><span data-stu-id="0ed70-111">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="0ed70-112">Användaren öppnar ett e-postmeddelande och klickar på en WEBBADRESS i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="0ed70-112">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="0ed70-113">Funktionen FÖR betrodda LÄNKAR i ATP kontrollerar omedelbart webbadressen innan webbplatsen öppnas.</span><span class="sxs-lookup"><span data-stu-id="0ed70-113">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="0ed70-114">WEBBADRESSEN identifieras som blockerad, skadlig eller säker.</span><span class="sxs-lookup"><span data-stu-id="0ed70-114">The URL is identified as blocked, malicious, or safe.</span></span>
        
   - <span data-ttu-id="0ed70-115">Om webbadressen är till en webbplats som ingår i organisationens [anpassade blockerade webbadresser öppnas](set-up-a-custom-blocked-urls-list-wtih-atp.md)en [varningssida.](atp-safe-links-warning-pages.md)</span><span class="sxs-lookup"><span data-stu-id="0ed70-115">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="0ed70-116">Om webbadressen är till en webbplats som har fastställts vara skadlig öppnas en [varningssida.](atp-safe-links-warning-pages.md)</span><span class="sxs-lookup"><span data-stu-id="0ed70-116">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="0ed70-117">Om webbadressen går till en nedladdningsbar fil och organisationens [ATP Safe Links-principer](set-up-atp-safe-links-policies.md) är konfigurerade för att skanna sådant innehåll kontrolleras den nedladdningsbara filen.</span><span class="sxs-lookup"><span data-stu-id="0ed70-117">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="0ed70-118">Om webbadressen bedöms vara säker öppnas webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="0ed70-118">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="0ed70-119">Så här fungerar ATP Safe Links med webbadresser i Office-dokument</span><span class="sxs-lookup"><span data-stu-id="0ed70-119">How ATP Safe Links works with URLs in Office documents</span></span> 

<span data-ttu-id="0ed70-120">På en hög nivå fungerar så här för [ATP Safe Links-skydd](atp-safe-links.md) för webbadresser i Office 365 ProPlus- eller Business Premium-program (aktuella versioner av Word, Excel och PowerPoint på Windows, Mac eller i en webbläsare, Office-appar på iOS- eller Android-enheter, Visio på Windows, OneNote i en webbläsare):</span><span class="sxs-lookup"><span data-stu-id="0ed70-120">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Office 365 ProPlus or Business Premium applications (current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a browser, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser):</span></span>
  
1. <span data-ttu-id="0ed70-121">Personer har installerat Office 365 ProPlus eller Business Premium på sin dator, smartphone eller surfplatta.</span><span class="sxs-lookup"><span data-stu-id="0ed70-121">People have installed Office 365 ProPlus or Business Premium on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="0ed70-122">(Eller så använder de Office i sin webbläsare.)</span><span class="sxs-lookup"><span data-stu-id="0ed70-122">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="0ed70-123">En användare öppnar ett Word, Excel, PowerPoint, OneNote (i webbläsaren) eller Visio (på skrivbordet) och loggar in på Office 365 Enterprise med sitt arbets- eller skolkonto.</span><span class="sxs-lookup"><span data-stu-id="0ed70-123">A user opens a Word, Excel, PowerPoint, OneNote (in the browser), or Visio (on desktop), and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="0ed70-124">Dokumentet innehåller webbadresser.</span><span class="sxs-lookup"><span data-stu-id="0ed70-124">The document contains URLs.</span></span>
    
3. <span data-ttu-id="0ed70-125">När användaren klickar på en URL i dokumentet kontrolleras länken av tjänsten ATP Safe Links.</span><span class="sxs-lookup"><span data-stu-id="0ed70-125">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
   - <span data-ttu-id="0ed70-126">Om webbadressen är till en webbplats som ingår i organisationens [anpassade blockerade webbadresser](set-up-a-custom-blocked-urls-list-wtih-atp.md)visas användaren på en [varningssida](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="0ed70-126">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="0ed70-127">Om webbadressen är till en webbplats som har fastställts vara skadlig, tas användaren till en [varningssida](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="0ed70-127">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="0ed70-128">Om webbadressen går till en nedladdningsbar fil och [ATP Safe Links-principerna](set-up-atp-safe-links-policies.md) är konfigurerade för att skanna sådana nedladdningar kontrolleras den nedladdningsbara filen.</span><span class="sxs-lookup"><span data-stu-id="0ed70-128">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="0ed70-129">Om webbadressen anses säker, användaren tas till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="0ed70-129">If the URL is considered safe, the user is taken to the website.</span></span>
      
   - <span data-ttu-id="0ed70-130">Om URL-kontrollen misslyckas utlöses inte skyddet för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="0ed70-130">If the URL check fails, Safe Links' protection will not trigger.</span></span> <span data-ttu-id="0ed70-131">På skrivbordsklienterna kommer användaren att varnas innan du fortsätter till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="0ed70-131">On the desktop clients, the user will be warned before proceeding through to the site.</span></span>
      
> [!NOTE]
> <span data-ttu-id="0ed70-132">Det kan ta flera sekunder i början av varje session att kontrollera att användaren har ATP Safe Links for Office aktiverat.</span><span class="sxs-lookup"><span data-stu-id="0ed70-132">It may take several seconds at the beginning of each session to verify that the user has ATP Safe Links for Office enabled.</span></span> 
      
