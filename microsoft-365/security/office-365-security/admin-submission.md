---
title: Administratörsinlämningar i Office 365, O365-inlagor, office 365-skräppostproblem, O365 falskt negativt, skicka in phish i Office 365, skicka e-post för skanning, misstänkt e-post i Office 365, skanna ett e-postmeddelande, låta Microsoft söka efter phish, låta Microsoft söka efter skräppost, skicka in e-post, skicka e-post, skumma e-post, dålig skådespelare post, misstänkt, opålitlig e-post, rapportera phish e-post till Microsoft, rapportera phish e-post till Microsoft, rapportera skadlig e-post till Microsoft, rapportera bluff e-post till Microsoft, rapportera skadlig kod i e-post till Microsoft, spam e-post i inkorgskontoret 365, virus i e-postkonto 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Läs om hur du skickar misstänkta e-postmeddelanden, misstänkta nätfiskemeddelanden, skräppost och andra potentiellt skadliga meddelanden, webbadresser och filer från office 365-klienten till Microsoft för skanning.
ms.openlocfilehash: 539d09f03a8a9c5956f2d1e3584f893b0e4ffbb4
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033620"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="b5da3-103">Använd administratörsöverföring för att skicka misstänkt skräppost, phish, webbadresser och filer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="b5da3-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="b5da3-104">Om du är administratör i en Office 365-organisation med postlådor i Exchange Online kan du använda portalen Inlämningar i Office 365 Security & Compliance Center för att skicka e-postmeddelanden, webbadresser och bilagor till Microsoft för skanning.</span><span class="sxs-lookup"><span data-stu-id="b5da3-104">If you're an admin in an Office 365 organization with mailboxes in Exchange Online, you can use the Submissions portal in the Office 365 Security & Compliance Center to submit email messages, URLs and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="b5da3-105">När du skickar ett e-postmeddelande får du information om alla policyer som kan ha tillåtit inkommande e-post till din klientorganisation, samt granskning av eventuella webbadresser och bilagor med posten.</span><span class="sxs-lookup"><span data-stu-id="b5da3-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="b5da3-106">Principer som kan ha tillåtit ett e-postmeddelande inkluderar en enskild användares säkra avsänningslista samt principer på klientnivå, till exempel regler för Exchange-e-postflöde (kallas även transportregler).</span><span class="sxs-lookup"><span data-stu-id="b5da3-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="b5da3-107">Andra sätt att skicka e-postmeddelanden, webbadresser och bilagor till Microsoft finns i</span><span class="sxs-lookup"><span data-stu-id="b5da3-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b5da3-108">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="b5da3-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b5da3-109">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b5da3-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b5da3-110">Om du vill **Submission** gå direkt <https://protection.office.com/reportsubmission>till sidan Inlämning använder du .</span><span class="sxs-lookup"><span data-stu-id="b5da3-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="b5da3-111">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b5da3-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="b5da3-112">Information om hur du använder Windows PowerShell för att ansluta till fristående Exchange Online Protection PowerShell finns i artikeln om att [ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="b5da3-112">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b5da3-113">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="b5da3-113">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="b5da3-114">Om du vill lägga till, ändra och ta bort principer för skräppost måste du vara medlem i rollgrupperna **Organisationshantering,** **Säkerhetsadministratör**eller **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="b5da3-114">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="b5da3-115">Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter för Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b5da3-115">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="b5da3-116">Mer information om hur användare kan skicka meddelanden och filer till Microsoft finns [i Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="b5da3-116">For more information about how users can submit messages and files to Microsoft see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="b5da3-117">Så här dirigerar du misstänkt innehåll till Microsoft för Office 365-skanning</span><span class="sxs-lookup"><span data-stu-id="b5da3-117">How to direct suspicious content to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="b5da3-118">Om du vill skicka innehåll till Microsoft klickar du på knappen **Ny inlämning** längst upp till vänster på inlämningssidan.</span><span class="sxs-lookup"><span data-stu-id="b5da3-118">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="b5da3-119">Ett utfällbart till höger på sidan visas med möjlighet att skicka antingen ett e-postmeddelande, en URL eller en fil.</span><span class="sxs-lookup"><span data-stu-id="b5da3-119">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="b5da3-120">Skicka ett tvivelaktigt e-postmeddelande till Microsoft</span><span class="sxs-lookup"><span data-stu-id="b5da3-120">Submit a questionable email to Microsoft</span></span>

![Exempel på skicka e-post](../../media/submission-flyout-email.PNG)

1. <span data-ttu-id="b5da3-122">Om du vill skicka ett e-postmeddelande väljer du **e-post** och anger **e-postnätverksmeddelande-ID** eller laddar upp e-postfilen.</span><span class="sxs-lookup"><span data-stu-id="b5da3-122">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span>

2. <span data-ttu-id="b5da3-123">Ange vilka mottagare som du vill köra principkontrollen mot.</span><span class="sxs-lookup"><span data-stu-id="b5da3-123">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="b5da3-124">Principkontrollen avgör om e-postmeddelandet kringgås genomsökning på grund av principer på användar- eller klientnivå.</span><span class="sxs-lookup"><span data-stu-id="b5da3-124">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span>

3. <span data-ttu-id="b5da3-125">Ange om e-postmeddelandet ska ha blockerats eller inte.</span><span class="sxs-lookup"><span data-stu-id="b5da3-125">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="b5da3-126">Om e-postmeddelandet skulle ha blockerats anger du om det ska ha blockerats som skräppost, nätfiske eller skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="b5da3-126">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="b5da3-127">Om du inte är säker på vilken typ det kan vara, använd ditt bästa omdöme.</span><span class="sxs-lookup"><span data-stu-id="b5da3-127">If you are not sure what type it might be, use your best judgment.</span></span>

   - <span data-ttu-id="b5da3-128">Om filtret kringgådes på grund av principer vid inlämning visas information om den principen.</span><span class="sxs-lookup"><span data-stu-id="b5da3-128">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   - <span data-ttu-id="b5da3-129">Om filtret inte kringgådes på grund av en eller flera principer slutförs genomsökningen på flera minuter.</span><span class="sxs-lookup"><span data-stu-id="b5da3-129">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="b5da3-130">Du ser ytterligare information om inlämningen genom att klicka på statuslänken.</span><span class="sxs-lookup"><span data-stu-id="b5da3-130">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="b5da3-131">Detta inkluderar resultaten av policykontrollen och återscan dom.</span><span class="sxs-lookup"><span data-stu-id="b5da3-131">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="b5da3-132">Observera att detta inte kör e-postmeddelandet via office 365 ATP full filtrering stack igen men kör en partiell rescan baserat på vissa attribut för e-post, URL eller fil.</span><span class="sxs-lookup"><span data-stu-id="b5da3-132">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

4. <span data-ttu-id="b5da3-133">Klicka på knappen **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="b5da3-133">Click the **Submit** button.</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="b5da3-134">Skicka en misstänkt WEBBADRESS till Microsoft</span><span class="sxs-lookup"><span data-stu-id="b5da3-134">Send a suspect URL to Microsoft</span></span>

![Exempel på skicka e-post](../../media/submission-url-flyout.png)

1. <span data-ttu-id="b5da3-136">Om du vill skicka in en URL väljer du **URL** från utfällbara.</span><span class="sxs-lookup"><span data-stu-id="b5da3-136">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="b5da3-137">Skriv in den fullständiga URL:en inklusive protokollet (**https://**).</span><span class="sxs-lookup"><span data-stu-id="b5da3-137">Type in the full URL including the protocol (**https://**).</span></span>

   <span data-ttu-id="b5da3-138">Om du har valt **Ska ha filtrerats**anger du om webbadressen är nätfiske eller skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="b5da3-138">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="b5da3-139">Klicka på knappen **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="b5da3-139">Click the **Submit** button.</span></span>

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="b5da3-140">Skicka en misstänkt fil till Microsoft</span><span class="sxs-lookup"><span data-stu-id="b5da3-140">Submit a suspected file to Microsoft</span></span>

![Exempel på skicka e-post](../../media/submission-file-flyout.PNG)

1. <span data-ttu-id="b5da3-142">Om du vill skicka en fil väljer du **Arkiv** från det utfällbara fönstret och överför filen som du vill skanna.</span><span class="sxs-lookup"><span data-stu-id="b5da3-142">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span>

2. <span data-ttu-id="b5da3-143">Klicka på knappen **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="b5da3-143">Click the **Submit** button.</span></span>
