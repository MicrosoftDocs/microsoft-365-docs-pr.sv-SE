---
title: Det här kommer att komma till Microsofts säkra Poäng
description: Här beskrivs vilka nya ändringar som kommer till Microsofts säkra poäng i säkerhets Center för Microsoft 365.
keywords: Microsoft säkra poäng, säkra poäng, Office 365 säkra poäng, säkerhets poäng, Microsoft 365 säkerhets Center, förbättrings åtgärder
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 82ec67cae86525c055b2232667cccb603830d15f
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779254"
---
# <a name="whats-coming-to-microsoft-secure-score"></a><span data-ttu-id="ba359-104">Det här kommer att komma till Microsofts säkra Poäng</span><span class="sxs-lookup"><span data-stu-id="ba359-104">What's coming to Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="ba359-105">Vi håller på att göra några ändringar i närmaste framtid och gör [Microsoft säkert Poäng](microsoft-secure-score.md) en bättre representant för din säkerhets Posture och bättre användbarhet.</span><span class="sxs-lookup"><span data-stu-id="ba359-105">We're making some changes in the near future to make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability.</span></span> <span data-ttu-id="ba359-106">Ditt Poäng och högsta möjliga poäng kan förändras.</span><span class="sxs-lookup"><span data-stu-id="ba359-106">Your score and the maximum possible score may change.</span></span>

## <a name="proposed-changes"></a><span data-ttu-id="ba359-107">Föreslagna ändringar</span><span class="sxs-lookup"><span data-stu-id="ba359-107">Proposed changes</span></span>

### <a name="november-2020"></a><span data-ttu-id="ba359-108">November 2020</span><span class="sxs-lookup"><span data-stu-id="ba359-108">November 2020</span></span>

<span data-ttu-id="ba359-109">Ta bort möjligheten att skapa ServiceNow biljetter genom säkra poäng genom att gå till **dela > ServiceNow** .</span><span class="sxs-lookup"><span data-stu-id="ba359-109">Removing the ability to create ServiceNow tickets through Secure Score by going to **Share > ServiceNow** .</span></span>

- <span data-ttu-id="ba359-110">För hands perioden för ServiceNow-kopplingen är slut.</span><span class="sxs-lookup"><span data-stu-id="ba359-110">The preview period for the ServiceNow connector is ending.</span></span> <span data-ttu-id="ba359-111">Den här funktionen kommer inte längre att vara tillgänglig i slutet av 2020.</span><span class="sxs-lookup"><span data-stu-id="ba359-111">This capability will no longer available by the end of 2020.</span></span> <span data-ttu-id="ba359-112">Tack för din feedback och fortsatta support medan vi bestämmer nästa steg.</span><span class="sxs-lookup"><span data-stu-id="ba359-112">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="ba359-113">Lägga till 18 förbättrings åtgärder relaterade till Microsoft Defender för slut punkt (tidigare Microsoft Defender ATP):</span><span class="sxs-lookup"><span data-stu-id="ba359-113">Adding 18 improvement actions related to Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

<span data-ttu-id="ba359-114">Rekommenderade problem med attack ytan (ASR):</span><span class="sxs-lookup"><span data-stu-id="ba359-114">Attack Surface Reduction (ASR) related recommendations:</span></span>
- <span data-ttu-id="ba359-115">Blockera körbart innehåll från e-postklient och WebPost</span><span class="sxs-lookup"><span data-stu-id="ba359-115">Block executable content from email client and webmail</span></span>
- <span data-ttu-id="ba359-116">Blockera alla Office-program från att skapa underordnade processer</span><span class="sxs-lookup"><span data-stu-id="ba359-116">Block all Office applications from creating child processes</span></span>
- <span data-ttu-id="ba359-117">Blockera Office-program från att skapa körbart innehåll</span><span class="sxs-lookup"><span data-stu-id="ba359-117">Block Office applications from creating executable content</span></span>
- <span data-ttu-id="ba359-118">Blockera Office-program från att injicera kod i andra processer</span><span class="sxs-lookup"><span data-stu-id="ba359-118">Block Office applications from injecting code into other processes</span></span>
- <span data-ttu-id="ba359-119">Blockera java script eller VBScript från att starta hämtat körbart innehåll</span><span class="sxs-lookup"><span data-stu-id="ba359-119">Block JavaScript or VBScript from launching downloaded executable content</span></span>
- <span data-ttu-id="ba359-120">Blockera körning av potentiellt Obfuscated-skript</span><span class="sxs-lookup"><span data-stu-id="ba359-120">Block execution of potentially obfuscated scripts</span></span>
- <span data-ttu-id="ba359-121">Blockera Win32 API-samtal från Office-makron</span><span class="sxs-lookup"><span data-stu-id="ba359-121">Block Win32 API calls from Office macros</span></span>
- <span data-ttu-id="ba359-122">Blockera körbara filer från att köras såvida de inte uppfyller villkoren för ett förekomst-, ålder eller betrott lista</span><span class="sxs-lookup"><span data-stu-id="ba359-122">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
- <span data-ttu-id="ba359-123">Använd avancerat skydd mot utpressnings tro Jan</span><span class="sxs-lookup"><span data-stu-id="ba359-123">Use advanced protection against ransomware</span></span>
- <span data-ttu-id="ba359-124">Blockera autentiseringsuppgifter som stjäls från Windows Local Security Authority Subsystem (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="ba359-124">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
- <span data-ttu-id="ba359-125">Blockera skapande av processer från PSExec-och WMI-kommandon</span><span class="sxs-lookup"><span data-stu-id="ba359-125">Block process creations originating from PSExec and WMI commands</span></span>
- <span data-ttu-id="ba359-126">Blockera icke-betrodda och osignerade processer som körs från USB</span><span class="sxs-lookup"><span data-stu-id="ba359-126">Block untrusted and unsigned processes that run from USB</span></span>
- <span data-ttu-id="ba359-127">Blockera Office-kommunikationsprogram från att skapa underordnade processer</span><span class="sxs-lookup"><span data-stu-id="ba359-127">Block Office communication application from creating child processes</span></span>
- <span data-ttu-id="ba359-128">Blockera Adobe Reader från att skapa underordnade processer</span><span class="sxs-lookup"><span data-stu-id="ba359-128">Block Adobe Reader from creating child processes</span></span>
- <span data-ttu-id="ba359-129">Blockera beständighet via WMI-prenumeration</span><span class="sxs-lookup"><span data-stu-id="ba359-129">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="ba359-130">Service rekommendationer:</span><span class="sxs-lookup"><span data-stu-id="ba359-130">Services related recommendations:</span></span>
- <span data-ttu-id="ba359-131">Åtgärda den icke-citerade tjänst Sök vägen för Windows-tjänster</span><span class="sxs-lookup"><span data-stu-id="ba359-131">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="ba359-132">Ändra sökvägen till den körbara filen till en gemensam skyddad plats</span><span class="sxs-lookup"><span data-stu-id="ba359-132">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="ba359-133">Ändra tjänst konto för att undvika cachelagrat lösen ord i Windows-registret</span><span class="sxs-lookup"><span data-stu-id="ba359-133">Change service account to avoid cached password in windows registry</span></span>

## <a name="related-resources"></a><span data-ttu-id="ba359-134">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="ba359-134">Related resources</span></span>

- [<span data-ttu-id="ba359-135">Översikt över Microsofts säkra Poäng</span><span class="sxs-lookup"><span data-stu-id="ba359-135">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="ba359-136">Utvärdera säkerhets genom övergå molnet</span><span class="sxs-lookup"><span data-stu-id="ba359-136">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="ba359-137">Spåra din Microsoft säkra Poäng historik och uppfylla målen</span><span class="sxs-lookup"><span data-stu-id="ba359-137">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="ba359-138">Vad är nytt</span><span class="sxs-lookup"><span data-stu-id="ba359-138">What's new</span></span>](microsoft-secure-score-whats-new.md)
