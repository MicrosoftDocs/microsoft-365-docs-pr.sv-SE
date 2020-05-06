---
title: Så fungerar ATP – säkra länkar
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
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Funktionen Säkra länkar ger snabb verifiering av hyperlänkar i Office-dokument och i e-postmeddelanden. Läs den här artikeln om du vill veta hur ATP Safe Links fungerar.
ms.openlocfilehash: e79c44b91eb5de7564058b4dc50c94d2a4223f08
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046370"
---
# <a name="how-atp-safe-links-works"></a><span data-ttu-id="d3975-104">Så fungerar ATP – säkra länkar</span><span class="sxs-lookup"><span data-stu-id="d3975-104">How ATP Safe Links works</span></span>
> [!IMPORTANT] 
> <span data-ttu-id="d3975-105">För att Office 365 ATP Safe Links ska fungera korrekt måste alla tjänster vara i samma version.</span><span class="sxs-lookup"><span data-stu-id="d3975-105">For Office 365 ATP Safe Links to operate correctly, all of the services need to be at the same version.</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="d3975-106">Så här fungerar ATP Safe Links med webbadresser i e-post</span><span class="sxs-lookup"><span data-stu-id="d3975-106">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="d3975-107">På en hög nivå fungerar så här [för ATP Safe Links-skydd](atp-safe-links.md) för webbadresser i e-post (finns i Office 365, inte lokalt):</span><span class="sxs-lookup"><span data-stu-id="d3975-107">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="d3975-108">Personer får e-postmeddelanden, varav vissa innehåller webbadresser.</span><span class="sxs-lookup"><span data-stu-id="d3975-108">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="d3975-109">All e-post går via Exchange Online Protection, där IP-filter (Internet Protocol) och kuvertfilter, signaturbaserat skydd mot skadlig kod, skräppost- och anti-malware-filter tillämpas.</span><span class="sxs-lookup"><span data-stu-id="d3975-109">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="d3975-110">E-post kommer i människors inkorgar.</span><span class="sxs-lookup"><span data-stu-id="d3975-110">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="d3975-111">En användare loggar in på Office 365 och går till sin e-postkorg.</span><span class="sxs-lookup"><span data-stu-id="d3975-111">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="d3975-112">Användaren öppnar ett e-postmeddelande och klickar på en WEBBADRESS i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="d3975-112">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="d3975-113">Funktionen FÖR betrodda LÄNKAR i ATP kontrollerar omedelbart webbadressen innan webbplatsen öppnas.</span><span class="sxs-lookup"><span data-stu-id="d3975-113">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="d3975-114">WEBBADRESSEN identifieras som blockerad, skadlig eller säker.</span><span class="sxs-lookup"><span data-stu-id="d3975-114">The URL is identified as blocked, malicious, or safe.</span></span>
        
   - <span data-ttu-id="d3975-115">Om webbadressen är till en webbplats som ingår i organisationens [anpassade blockerade webbadresser öppnas](set-up-a-custom-blocked-urls-list-atp.md)en [varningssida.](atp-safe-links-warning-pages.md)</span><span class="sxs-lookup"><span data-stu-id="d3975-115">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="d3975-116">Om webbadressen är till en webbplats som har fastställts vara skadlig öppnas en [varningssida.](atp-safe-links-warning-pages.md)</span><span class="sxs-lookup"><span data-stu-id="d3975-116">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="d3975-117">Om webbadressen går till en nedladdningsbar fil och organisationens [ATP Safe Links-principer](set-up-atp-safe-links-policies.md) är konfigurerade för att skanna sådant innehåll kontrolleras den nedladdningsbara filen.</span><span class="sxs-lookup"><span data-stu-id="d3975-117">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="d3975-118">Om webbadressen bedöms vara säker öppnas webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="d3975-118">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="d3975-119">Så här fungerar ATP Safe Links med webbadresser i Office-dokument</span><span class="sxs-lookup"><span data-stu-id="d3975-119">How ATP Safe Links works with URLs in Office documents</span></span> 

<span data-ttu-id="d3975-120">På en hög nivå fungerar så här för [ATP Safe Links-skydd](atp-safe-links.md) för webbadresser i Microsoft 365 Apps för företag eller Business Premium-program (aktuella versioner av Word, Excel och PowerPoint på Windows, Mac eller i en webbläsare, Office-appar på iOS- eller Android-enheter, Visio på Windows, OneNote i en webbläsare):</span><span class="sxs-lookup"><span data-stu-id="d3975-120">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Microsoft 365 Apps for enterprise or Business Premium applications (current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a browser, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser):</span></span>
  
1. <span data-ttu-id="d3975-121">Personer har installerat Microsoft 365 Apps för företag eller Business Premium på sin dator, smartphone eller surfplatta.</span><span class="sxs-lookup"><span data-stu-id="d3975-121">People have installed Microsoft 365 Apps for enterprise or Business Premium on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="d3975-122">(Eller så använder de Office i sin webbläsare.)</span><span class="sxs-lookup"><span data-stu-id="d3975-122">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="d3975-123">En användare öppnar ett Word, Excel, PowerPoint, OneNote (i webbläsaren) eller Visio (på skrivbordet) och loggar in på Office 365 Enterprise med sitt arbets- eller skolkonto.</span><span class="sxs-lookup"><span data-stu-id="d3975-123">A user opens a Word, Excel, PowerPoint, OneNote (in the browser), or Visio (on desktop), and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="d3975-124">Dokumentet innehåller webbadresser.</span><span class="sxs-lookup"><span data-stu-id="d3975-124">The document contains URLs.</span></span>
    
3. <span data-ttu-id="d3975-125">När användaren klickar på en URL i dokumentet kontrolleras länken av tjänsten ATP Safe Links.</span><span class="sxs-lookup"><span data-stu-id="d3975-125">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
   - <span data-ttu-id="d3975-126">Om webbadressen är till en webbplats som ingår i organisationens [anpassade blockerade webbadresser](set-up-a-custom-blocked-urls-list-atp.md)visas användaren på en [varningssida](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="d3975-126">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="d3975-127">Om webbadressen är till en webbplats som har fastställts vara skadlig, tas användaren till en [varningssida](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="d3975-127">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="d3975-128">Om webbadressen går till en nedladdningsbar fil och [ATP Safe Links-principerna](set-up-atp-safe-links-policies.md) är konfigurerade för att skanna sådana nedladdningar kontrolleras den nedladdningsbara filen.</span><span class="sxs-lookup"><span data-stu-id="d3975-128">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="d3975-129">Om webbadressen anses säker, användaren tas till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="d3975-129">If the URL is considered safe, the user is taken to the website.</span></span>
      
   - <span data-ttu-id="d3975-130">Om URL-kontrollen misslyckas utlöses inte skyddet för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="d3975-130">If the URL check fails, Safe Links' protection will not trigger.</span></span> <span data-ttu-id="d3975-131">På skrivbordsklienterna kommer användaren att varnas innan du fortsätter till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="d3975-131">On the desktop clients, the user will be warned before proceeding through to the site.</span></span>
      
> [!NOTE]
> <span data-ttu-id="d3975-132">Det kan ta flera sekunder i början av varje session att kontrollera att användaren har ATP Safe Links for Office aktiverat.</span><span class="sxs-lookup"><span data-stu-id="d3975-132">It may take several seconds at the beginning of each session to verify that the user has ATP Safe Links for Office enabled.</span></span> 
      
