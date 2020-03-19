---
title: Administratörsinlämningar i Office 365, O365-inlagor, office 365-skräppostproblem, O365 falskt negativt, skicka in phish i Office 365, skicka e-post för skanning, misstänkt e-post i Office 365, skanna ett e-postmeddelande, låta Microsoft söka efter phish, låta Microsoft söka efter skräppost, skicka in e-post, skicka e-post, skumma e-post, dålig skådespelare post, misstänkt, opålitlig e-post, rapportera phish e-post till Microsoft, rapportera phish e-post till Microsoft, rapportera skadlig e-post till Microsoft, rapportera bluff e-post till Microsoft, rapportera skadlig kod i e-post till Microsoft, spam e-post i inkorgskontoret 365, virus i e-postkonto 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 08/06/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Läs om hur du skickar misstänkta e-postmeddelanden, misstänkta nätfiskemeddelanden, skräppost och andra potentiellt skadliga meddelanden, webbadresser och filer från office 365-klienten till Microsoft för skanning.
ms.openlocfilehash: b123aef485628728df9db27875117b47295975ad
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812261"
---
# <a name="how-to-submit-suspected-spam-phish-urls-and-files-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="72271-103">Så här skickar du in misstänkt skräppost, phish, URL:er och filer till Microsoft för Office 365-skanning</span><span class="sxs-lookup"><span data-stu-id="72271-103">How to submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="72271-104">Administratörer kan skicka e-postmeddelanden med hjälp av fil- eller nätverksmeddelande-ID, webbadresser och filer för skanning av Microsoft i Office 365.</span><span class="sxs-lookup"><span data-stu-id="72271-104">Admins can send emails by using file or network message ID, URLs, and files for scanning by Microsoft in Office 365.</span></span>
<span data-ttu-id="72271-105">Avsnittet uppdaterade inlämningar innehåller fortfarande användarrapporterade meddelanden och tillgängliga för alla kunder som använder EOP.</span><span class="sxs-lookup"><span data-stu-id="72271-105">The updated submissions section still includes user reported messages and available to all customers using EOP.</span></span>

<span data-ttu-id="72271-106">När du skickar ett e-postmeddelande får du information om alla policyer som kan ha tillåtit inkommande e-post till din klientorganisation, samt granskning av eventuella webbadresser och bilagor med posten.</span><span class="sxs-lookup"><span data-stu-id="72271-106">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="72271-107">Principer som kan ha tillåtit ett e-postmeddelande inkluderar en enskild användares säkra avsänningslista samt principer på klientnivå, till exempel regler för Exchange-e-postflöde (kallas även transportregler).</span><span class="sxs-lookup"><span data-stu-id="72271-107">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="72271-108">Så här dirigerar du misstänkt innehåll till Microsoft för Office 365-skanning</span><span class="sxs-lookup"><span data-stu-id="72271-108">How to direct suspicious content to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="72271-109">Om du vill skicka innehåll till Microsoft klickar du på knappen **Ny inlämning** längst upp till vänster på inlämningssidan.</span><span class="sxs-lookup"><span data-stu-id="72271-109">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="72271-110">Ett utfällbart till höger på sidan visas med möjlighet att skicka antingen ett e-postmeddelande, en URL eller en fil.</span><span class="sxs-lookup"><span data-stu-id="72271-110">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="72271-111">Skicka ett tvivelaktigt e-postmeddelande till Microsoft</span><span class="sxs-lookup"><span data-stu-id="72271-111">Submit a questionable email to Microsoft</span></span>

![Exempel på skicka e-post](../../media/submission-flyout-email.PNG)

1. <span data-ttu-id="72271-113">Om du vill skicka ett e-postmeddelande väljer du **e-post** och anger **e-postnätverksmeddelande-ID** eller laddar upp e-postfilen.</span><span class="sxs-lookup"><span data-stu-id="72271-113">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span>

2. <span data-ttu-id="72271-114">Ange vilka mottagare som du vill köra principkontrollen mot.</span><span class="sxs-lookup"><span data-stu-id="72271-114">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="72271-115">Principkontrollen avgör om e-postmeddelandet kringgås genomsökning på grund av principer på användar- eller klientnivå.</span><span class="sxs-lookup"><span data-stu-id="72271-115">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span>

3. <span data-ttu-id="72271-116">Ange om e-postmeddelandet ska ha blockerats eller inte.</span><span class="sxs-lookup"><span data-stu-id="72271-116">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="72271-117">Om e-postmeddelandet skulle ha blockerats anger du om det ska ha blockerats som skräppost, nätfiske eller skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="72271-117">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="72271-118">Om du inte är säker på vilken typ det kan vara, använd ditt bästa omdöme.</span><span class="sxs-lookup"><span data-stu-id="72271-118">If you are not sure what type it might be, use your best judgement.</span></span>

   - <span data-ttu-id="72271-119">Om filtret kringgådes på grund av principer vid inlämning visas information om den principen.</span><span class="sxs-lookup"><span data-stu-id="72271-119">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   - <span data-ttu-id="72271-120">Om filtret inte kringgådes på grund av en eller flera principer slutförs genomsökningen på flera minuter.</span><span class="sxs-lookup"><span data-stu-id="72271-120">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="72271-121">Du ser ytterligare information om inlämningen genom att klicka på statuslänken.</span><span class="sxs-lookup"><span data-stu-id="72271-121">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="72271-122">Detta inkluderar resultaten av policykontrollen och återscan dom.</span><span class="sxs-lookup"><span data-stu-id="72271-122">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="72271-123">Observera att detta inte kör e-postmeddelandet via office 365 ATP full filtrering stack igen men kör en partiell rescan baserat på vissa attribut för e-post, URL eller fil.</span><span class="sxs-lookup"><span data-stu-id="72271-123">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

4. <span data-ttu-id="72271-124">Klicka på knappen **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="72271-124">Click the **Submit** button.</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="72271-125">Skicka en misstänkt WEBBADRESS till Microsoft</span><span class="sxs-lookup"><span data-stu-id="72271-125">Send a suspect URL to Microsoft</span></span>

![Exempel på skicka e-post](../../media/submission-url-flyout.png)

1. <span data-ttu-id="72271-127">Om du vill skicka in en URL väljer du **URL** från utfällbara.</span><span class="sxs-lookup"><span data-stu-id="72271-127">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="72271-128">Skriv in den fullständiga URL:en inklusive protokollet (**https://**).</span><span class="sxs-lookup"><span data-stu-id="72271-128">Type in the full URL including the protocol (**https://**).</span></span>

   <span data-ttu-id="72271-129">Om du har valt **Ska ha filtrerats**anger du om webbadressen är nätfiske eller skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="72271-129">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="72271-130">Klicka på knappen **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="72271-130">Click the **Submit** button.</span></span>

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="72271-131">Skicka en misstänkt fil till Microsoft</span><span class="sxs-lookup"><span data-stu-id="72271-131">Submit a suspected file to Microsoft</span></span>

![Exempel på skicka e-post](../../media/submission-file-flyout.PNG)

1. <span data-ttu-id="72271-133">Om du vill skicka en fil väljer du **Arkiv** från det utfällbara fönstret och överför filen som du vill skanna.</span><span class="sxs-lookup"><span data-stu-id="72271-133">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span>

2. <span data-ttu-id="72271-134">Klicka på knappen **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="72271-134">Click the **Submit** button.</span></span>

## <a name="related-topics"></a><span data-ttu-id="72271-135">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="72271-135">Related topics</span></span>

[<span data-ttu-id="72271-136">Office 365 Avancerat hotskyddsplan 2</span><span class="sxs-lookup"><span data-stu-id="72271-136">Office 365 Advanced Threat Protection Plan 2</span></span>](office-365-ti.md)

[<span data-ttu-id="72271-137">Skydda mot hot i Office 365</span><span class="sxs-lookup"><span data-stu-id="72271-137">Protect against threats in Office 365</span></span>](protect-against-threats.md)

[<span data-ttu-id="72271-138">Visa rapporter för avancerat hotskydd för Office 365</span><span class="sxs-lookup"><span data-stu-id="72271-138">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
