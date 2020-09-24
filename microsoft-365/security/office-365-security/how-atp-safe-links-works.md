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
description: Med funktionen för säkra länkar kan du klicka på verifiering av hyperlänkar i Office-dokument och i e-postmeddelanden. Läs den här artikeln för att få reda på hur säkerhets länkar i ATP fungerar.
ms.openlocfilehash: e19d3a1f93d11cd9873e6b5fad9952b018e0a481
ms.sourcegitcommit: 1522a6471e0c5254a6d0f592e1f4dfacd1dd473a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2020
ms.locfileid: "48245887"
---
# <a name="how-atp-safe-links-works"></a><span data-ttu-id="cbc61-104">Så fungerar ATP – säkra länkar</span><span class="sxs-lookup"><span data-stu-id="cbc61-104">How ATP Safe Links works</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT] 
> <span data-ttu-id="cbc61-105">För att Office 365 ska få säkra Länkar för att fungera korrekt måste alla tjänsterna finnas i samma version.</span><span class="sxs-lookup"><span data-stu-id="cbc61-105">For Office 365 ATP Safe Links to operate correctly, all of the services need to be at the same version.</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="cbc61-106">Hur säkerhets Länkar för ATP fungerar med URL: er via e-post</span><span class="sxs-lookup"><span data-stu-id="cbc61-106">How ATP Safe Links works with URLs in email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]
 <span data-ttu-id="cbc61-107">med URL: er via e-post</span><span class="sxs-lookup"><span data-stu-id="cbc61-107">with URLs in email</span></span>

<span data-ttu-id="cbc61-108">På en hög nivå, så här gör du så här för att skydda dina URL [-adresser i](atp-safe-links.md) e-post (som finns i Office 365, inte lokalt):</span><span class="sxs-lookup"><span data-stu-id="cbc61-108">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="cbc61-109">Personer får e-postmeddelanden, varav vissa innehåller URL: er.</span><span class="sxs-lookup"><span data-stu-id="cbc61-109">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="cbc61-110">All e-post går genom Exchange Online Protection, där IP (Internet Protocol) och kuvert filter, signaturbaserade skydd mot skadlig program vara samt filter mot skräp post.</span><span class="sxs-lookup"><span data-stu-id="cbc61-110">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="cbc61-111">E-post anländer till personers inkorgar.</span><span class="sxs-lookup"><span data-stu-id="cbc61-111">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="cbc61-112">En användare loggar in i Office 365 och går till deras e-postinkorg.</span><span class="sxs-lookup"><span data-stu-id="cbc61-112">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="cbc61-113">Användaren öppnar ett e-postmeddelande och klickar på en URL i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="cbc61-113">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="cbc61-114">Med funktionen för Safet ATP-länkar kontrol leras URL-adressen omedelbart innan webbplatsen öppnas.</span><span class="sxs-lookup"><span data-stu-id="cbc61-114">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="cbc61-115">URL: en identifieras som blockerad, skadlig eller säker.</span><span class="sxs-lookup"><span data-stu-id="cbc61-115">The URL is identified as blocked, malicious, or safe.</span></span>
        
   - <span data-ttu-id="cbc61-116">Om URL-adressen är till en webbplats som ingår i organisationens [anpassade lista över blockerade URL-adresser](set-up-a-custom-blocked-urls-list-atp.md)öppnas en [varnings sida](atp-safe-links-warning-pages.md) .</span><span class="sxs-lookup"><span data-stu-id="cbc61-116">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="cbc61-117">Om URL-adressen är till en webbplats som har bedömts vara skadlig visas en [varnings sida](atp-safe-links-warning-pages.md) .</span><span class="sxs-lookup"><span data-stu-id="cbc61-117">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="cbc61-118">Om URL-adressen går till en nedladdnings bar fil och organisationens [principer för Safet ATP-länkar](set-up-atp-safe-links-policies.md) är konfigurerade för genomsökning av sådant innehåll är den nedladdnings bara filen markerad.</span><span class="sxs-lookup"><span data-stu-id="cbc61-118">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="cbc61-119">Om webb adressen är säker öppnas webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="cbc61-119">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="cbc61-120">Hur säkerhets Länkar för ATP fungerar med URL: er i Office-dokument</span><span class="sxs-lookup"><span data-stu-id="cbc61-120">How ATP Safe Links works with URLs in Office documents</span></span>

<span data-ttu-id="cbc61-121">På en hög nivå, så här gör du så här för att skydda dina URL [-adresser i](atp-safe-links.md) Microsoft 365-appar för Enterprise-eller Business Premium-program (aktuella versioner av Word, Excel och PowerPoint på Windows, Mac eller i en webbläsare, Office-appar på iOS-eller Android-enheter, Visio på Windows, OneNote i en webbläsare):</span><span class="sxs-lookup"><span data-stu-id="cbc61-121">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Microsoft 365 Apps for enterprise or Business Premium applications (current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a browser, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser):</span></span>
  
1. <span data-ttu-id="cbc61-122">Personer har installerat Microsoft 365-appar för företag eller företag Premium på sin dator, smartphone eller surfplatta.</span><span class="sxs-lookup"><span data-stu-id="cbc61-122">People have installed Microsoft 365 Apps for enterprise or Business Premium on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="cbc61-123">(Eller så använder de Office i webbläsaren.)</span><span class="sxs-lookup"><span data-stu-id="cbc61-123">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="cbc61-124">En användare öppnar ett ord, Excel, PowerPoint, OneNote (i webbläsaren) eller Visio (på Skriv bordet) och loggar in på Office 365 Enterprise med sitt arbets-eller skol konto.</span><span class="sxs-lookup"><span data-stu-id="cbc61-124">A user opens a Word, Excel, PowerPoint, OneNote (in the browser), or Visio (on desktop), and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="cbc61-125">Dokumentet innehåller URL: er.</span><span class="sxs-lookup"><span data-stu-id="cbc61-125">The document contains URLs.</span></span>
    
3. <span data-ttu-id="cbc61-126">När användaren klickar på en URL i dokumentet kontrol leras länken av tjänsten ATP Safe Links.</span><span class="sxs-lookup"><span data-stu-id="cbc61-126">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
   - <span data-ttu-id="cbc61-127">Om URL-adressen är till en webbplats som ingår i organisationens [anpassade lista över blockerade URL-adresser](set-up-a-custom-blocked-urls-list-atp.md), kommer användaren till en [varnings sida](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="cbc61-127">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="cbc61-128">Om URL-adressen är till en webbplats som har bedömts vara skadlig, kommer användaren till en [varnings sida](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="cbc61-128">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="cbc61-129">Om URL-adressen går till en nedladdnings bar fil och [principer för Safet ATP-länkar](set-up-atp-safe-links-policies.md) är konfigurerade för att söka igenom sådana nedladdningar är nedladdnings bar fil markerad.</span><span class="sxs-lookup"><span data-stu-id="cbc61-129">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="cbc61-130">Om URL: en anses vara säker kommer användaren till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="cbc61-130">If the URL is considered safe, the user is taken to the website.</span></span>
      
   - <span data-ttu-id="cbc61-131">Om webb adress kontrollen inte fungerar utlöses inte säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="cbc61-131">If the URL check fails, Safe Links' protection will not trigger.</span></span> <span data-ttu-id="cbc61-132">Användaren får ett varnings meddelande innan de fortsätter genom till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="cbc61-132">On the desktop clients, the user will be warned before proceeding through to the site.</span></span>
      
> [!NOTE]
> <span data-ttu-id="cbc61-133">Det kan ta flera sekunder i början av varje session att kontrol lera att användaren har Safet ATP-Länkar för Office.</span><span class="sxs-lookup"><span data-stu-id="cbc61-133">It may take several seconds at the beginning of each session to verify that the user has ATP Safe Links for Office enabled.</span></span> 
      
