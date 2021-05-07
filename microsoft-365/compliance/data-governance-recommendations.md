---
title: Hur innehåll identifieras för rekommendationer om datastyrning
f1.keywords:
- NOCSH
ms.author: brendonb
author: cabailey
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365 Säkerhetscenter och Microsoft 365 Efterlevnadscenter ger rekommendationer för datastyrning baserat på din organisations aktuella konfiguration och låter dig konfigurera med några klick. Vissa av de här rekommendationerna identifierar specifikt innehåll i din organisation och ger sedan rekommenderade steg för att hantera innehållet. En rekommendation kanske, till exempel, identifierar objekt som innehåller verksamhetskritiskt innehåll (t.ex. rätt till förtrolig kommunikation mellan advokat och klient eller information om sekretessavtal) och sedan låter dig automatiskt lägga till en etikett för de objekten för att säkerställa att de klassificeras och behålls efter behov. Det här avsnittet innehåller rekommendationer om datastyrning som du kan se och beskriver vilket innehåll som upptäcks för att utlösa det.
ms.openlocfilehash: 9a022369fb783a498971c91664fa6532472d8589
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162147"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="3e316-106">Hur innehåll identifieras för rekommendationer om datastyrning</span><span class="sxs-lookup"><span data-stu-id="3e316-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="3e316-107">Microsoft 365 Säkerhetscenter och Microsoft 365 Efterlevnadscenter ger rekommendationer för datastyrning baserat på din organisations aktuella konfiguration och låter dig konfigurera med några klick.</span><span class="sxs-lookup"><span data-stu-id="3e316-107">The Microsoft 365 security center and Microsoft 365 compliance center provide recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks.</span></span> <span data-ttu-id="3e316-108">Vissa av de här rekommendationerna identifierar specifikt innehåll i din organisation och ger sedan rekommenderade steg för att hantera innehållet.</span><span class="sxs-lookup"><span data-stu-id="3e316-108">Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content.</span></span> <span data-ttu-id="3e316-109">En rekommendation kanske, till exempel, identifierar objekt som innehåller verksamhetskritiskt innehåll (t.ex. rätt till förtrolig kommunikation mellan advokat och klient eller information om sekretessavtal) och sedan låter dig automatiskt lägga till en etikett för de objekten för att säkerställa att de klassificeras och behålls efter behov.</span><span class="sxs-lookup"><span data-stu-id="3e316-109">For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they're classified and retained as needed.</span></span>

<span data-ttu-id="3e316-110">Det här avsnittet innehåller rekommendationer om datastyrning som du kan se och beskriver vilket innehåll som upptäcks för att utlösa det.</span><span class="sxs-lookup"><span data-stu-id="3e316-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="3e316-111">Rensa röstmeddelanden</span><span class="sxs-lookup"><span data-stu-id="3e316-111">Clean up voicemail</span></span>

<span data-ttu-id="3e316-112">Den här rekommendationen visas när e-postmeddelanden identifieras som meddelandetypen ‘Röstmeddelanden’ upptäcks i användarnas postlådor.</span><span class="sxs-lookup"><span data-stu-id="3e316-112">This recommendation appears when email messages identified as the message type 'voicemail' are detected in users' mailboxes.</span></span> <span data-ttu-id="3e316-113">Läs mer om [meddelandeegenskaper i Exchange](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span><span class="sxs-lookup"><span data-stu-id="3e316-113">Learn more about [message properties in Exchange](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="3e316-114">Etikett för innehåll i förtrolig kommunikation mellan advokat och klient</span><span class="sxs-lookup"><span data-stu-id="3e316-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="3e316-115">Den här rekommendationen visas när något av följande kriterier uppfylls.</span><span class="sxs-lookup"><span data-stu-id="3e316-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="3e316-116">Valfri kombination av dessa nyckelord identifieras i brödtexten i ett e-postmeddelande:</span><span class="sxs-lookup"><span data-stu-id="3e316-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="3e316-117">AKP</span><span class="sxs-lookup"><span data-stu-id="3e316-117">ACP</span></span>
    - <span data-ttu-id="3e316-118">Rätt till förtrolig kommunikation mellan advokat och klient</span><span class="sxs-lookup"><span data-stu-id="3e316-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="3e316-119">Rätt till förtrolig kommunikation mellan advokat – klient</span><span class="sxs-lookup"><span data-stu-id="3e316-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="3e316-120">Advokat klient privilegium</span><span class="sxs-lookup"><span data-stu-id="3e316-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="3e316-121">Alla kombinationer av dessa nyckelord kan identifieras i SharePoint- eller OneDrive-filer:</span><span class="sxs-lookup"><span data-stu-id="3e316-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="3e316-122">AKP</span><span class="sxs-lookup"><span data-stu-id="3e316-122">ACP</span></span>
    - <span data-ttu-id="3e316-123">Rätt till förtrolig kommunikation mellan advokat och klient\*</span><span class="sxs-lookup"><span data-stu-id="3e316-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="3e316-124">Advokat klient privilegium</span><span class="sxs-lookup"><span data-stu-id="3e316-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="3e316-125">Behålla ljudfiler</span><span class="sxs-lookup"><span data-stu-id="3e316-125">Retain audio files</span></span>

<span data-ttu-id="3e316-126">Den här rekommendationen visas när någon av följande filtyper identifieras i SharePoint eller OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3e316-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="3e316-127">.MP3</span><span class="sxs-lookup"><span data-stu-id="3e316-127">.MP3</span></span>
- <span data-ttu-id="3e316-128">.WMA</span><span class="sxs-lookup"><span data-stu-id="3e316-128">.WMA</span></span>
- <span data-ttu-id="3e316-129">.WAV</span><span class="sxs-lookup"><span data-stu-id="3e316-129">.WAV</span></span>
- <span data-ttu-id="3e316-130">.RA</span><span class="sxs-lookup"><span data-stu-id="3e316-130">.RA</span></span>
- <span data-ttu-id="3e316-131">.RAM</span><span class="sxs-lookup"><span data-stu-id="3e316-131">.RAM</span></span>
- <span data-ttu-id="3e316-132">.RM</span><span class="sxs-lookup"><span data-stu-id="3e316-132">.RM</span></span>
- <span data-ttu-id="3e316-133">.MID</span><span class="sxs-lookup"><span data-stu-id="3e316-133">.MID</span></span>
- <span data-ttu-id="3e316-134">.OGG</span><span class="sxs-lookup"><span data-stu-id="3e316-134">.OGG</span></span>
- <span data-ttu-id="3e316-135">.AIFF</span><span class="sxs-lookup"><span data-stu-id="3e316-135">.AIFF</span></span>
- <span data-ttu-id="3e316-136">.PCM</span><span class="sxs-lookup"><span data-stu-id="3e316-136">.PCM</span></span>
- <span data-ttu-id="3e316-137">.AAC</span><span class="sxs-lookup"><span data-stu-id="3e316-137">.AAC</span></span>
- <span data-ttu-id="3e316-138">.FLAC</span><span class="sxs-lookup"><span data-stu-id="3e316-138">.FLAC</span></span>
- <span data-ttu-id="3e316-139">.ALAC</span><span class="sxs-lookup"><span data-stu-id="3e316-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="3e316-140">Behålla CAD-filer</span><span class="sxs-lookup"><span data-stu-id="3e316-140">Retain CAD files</span></span>

<span data-ttu-id="3e316-141">Den här rekommendationen visas när någon av följande filtyper identifieras i SharePoint eller OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3e316-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="3e316-142">.3DXML</span><span class="sxs-lookup"><span data-stu-id="3e316-142">.3DXML</span></span>
- <span data-ttu-id="3e316-143">.ACIS</span><span class="sxs-lookup"><span data-stu-id="3e316-143">.ACIS</span></span>
- <span data-ttu-id="3e316-144">.ARC</span><span class="sxs-lookup"><span data-stu-id="3e316-144">.ARC</span></span>
- <span data-ttu-id="3e316-145">.ASM</span><span class="sxs-lookup"><span data-stu-id="3e316-145">.ASM</span></span>
- <span data-ttu-id="3e316-146">.CAT\*</span><span class="sxs-lookup"><span data-stu-id="3e316-146">.CAT\*</span></span>
- <span data-ttu-id="3e316-147">.CGR</span><span class="sxs-lookup"><span data-stu-id="3e316-147">.CGR</span></span>
- <span data-ttu-id="3e316-148">.DW\*</span><span class="sxs-lookup"><span data-stu-id="3e316-148">.DW\*</span></span>
- <span data-ttu-id="3e316-149">.DX\*</span><span class="sxs-lookup"><span data-stu-id="3e316-149">.DX\*</span></span>
- <span data-ttu-id="3e316-150">.EDRW</span><span class="sxs-lookup"><span data-stu-id="3e316-150">.EDRW</span></span>
- <span data-ttu-id="3e316-151">.IAM</span><span class="sxs-lookup"><span data-stu-id="3e316-151">.IAM</span></span>
- <span data-ttu-id="3e316-152">.IGES</span><span class="sxs-lookup"><span data-stu-id="3e316-152">.IGES</span></span>
- <span data-ttu-id="3e316-153">.IGS</span><span class="sxs-lookup"><span data-stu-id="3e316-153">.IGS</span></span>
- <span data-ttu-id="3e316-154">.IPT</span><span class="sxs-lookup"><span data-stu-id="3e316-154">.IPT</span></span>
- <span data-ttu-id="3e316-155">.JT</span><span class="sxs-lookup"><span data-stu-id="3e316-155">.JT</span></span>
- <span data-ttu-id="3e316-156">.MF1</span><span class="sxs-lookup"><span data-stu-id="3e316-156">.MF1</span></span>
- <span data-ttu-id="3e316-157">.NEU</span><span class="sxs-lookup"><span data-stu-id="3e316-157">.NEU</span></span>
- <span data-ttu-id="3e316-158">.PAR</span><span class="sxs-lookup"><span data-stu-id="3e316-158">.PAR</span></span>
- <span data-ttu-id="3e316-159">.PKG</span><span class="sxs-lookup"><span data-stu-id="3e316-159">.PKG</span></span>
- <span data-ttu-id="3e316-160">.PRC</span><span class="sxs-lookup"><span data-stu-id="3e316-160">.PRC</span></span>
- <span data-ttu-id="3e316-161">.PRT</span><span class="sxs-lookup"><span data-stu-id="3e316-161">.PRT</span></span>
- <span data-ttu-id="3e316-162">.PSM</span><span class="sxs-lookup"><span data-stu-id="3e316-162">.PSM</span></span>
- <span data-ttu-id="3e316-163">.PWD</span><span class="sxs-lookup"><span data-stu-id="3e316-163">.PWD</span></span>
- <span data-ttu-id="3e316-164">.SLD\*</span><span class="sxs-lookup"><span data-stu-id="3e316-164">.SLD\*</span></span>
- <span data-ttu-id="3e316-165">.STEP</span><span class="sxs-lookup"><span data-stu-id="3e316-165">.STEP</span></span>
- <span data-ttu-id="3e316-166">.STL</span><span class="sxs-lookup"><span data-stu-id="3e316-166">.STL</span></span>
- <span data-ttu-id="3e316-167">.STP</span><span class="sxs-lookup"><span data-stu-id="3e316-167">.STP</span></span>
- <span data-ttu-id="3e316-168">.U3D</span><span class="sxs-lookup"><span data-stu-id="3e316-168">.U3D</span></span>
- <span data-ttu-id="3e316-169">.UNV</span><span class="sxs-lookup"><span data-stu-id="3e316-169">.UNV</span></span>
- <span data-ttu-id="3e316-170">.VRML</span><span class="sxs-lookup"><span data-stu-id="3e316-170">.VRML</span></span>
- <span data-ttu-id="3e316-171">.WRL</span><span class="sxs-lookup"><span data-stu-id="3e316-171">.WRL</span></span>
- <span data-ttu-id="3e316-172">.X_\*</span><span class="sxs-lookup"><span data-stu-id="3e316-172">.X_\*</span></span>
- <span data-ttu-id="3e316-173">.XAS</span><span class="sxs-lookup"><span data-stu-id="3e316-173">.XAS</span></span>
- <span data-ttu-id="3e316-174">.XMT\*</span><span class="sxs-lookup"><span data-stu-id="3e316-174">.XMT\*</span></span>
- <span data-ttu-id="3e316-175">.XPR</span><span class="sxs-lookup"><span data-stu-id="3e316-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="3e316-176">Behålla bildfiler</span><span class="sxs-lookup"><span data-stu-id="3e316-176">Retain image files</span></span>

<span data-ttu-id="3e316-177">Den här rekommendationen visas när någon av följande filtyper identifieras i SharePoint eller OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3e316-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="3e316-178">.JPEG</span><span class="sxs-lookup"><span data-stu-id="3e316-178">.JPEG</span></span>
- <span data-ttu-id="3e316-179">.GIF</span><span class="sxs-lookup"><span data-stu-id="3e316-179">.GIF</span></span>
- <span data-ttu-id="3e316-180">.TIF\*</span><span class="sxs-lookup"><span data-stu-id="3e316-180">.TIF\*</span></span>
- <span data-ttu-id="3e316-181">.BMP</span><span class="sxs-lookup"><span data-stu-id="3e316-181">.BMP</span></span>
- <span data-ttu-id="3e316-182">.PNG</span><span class="sxs-lookup"><span data-stu-id="3e316-182">.PNG</span></span>
- <span data-ttu-id="3e316-183">.RAW</span><span class="sxs-lookup"><span data-stu-id="3e316-183">.RAW</span></span>
- <span data-ttu-id="3e316-184">.PSD</span><span class="sxs-lookup"><span data-stu-id="3e316-184">.PSD</span></span>
- <span data-ttu-id="3e316-185">.PSP</span><span class="sxs-lookup"><span data-stu-id="3e316-185">.PSP</span></span>
- <span data-ttu-id="3e316-186">.JPG</span><span class="sxs-lookup"><span data-stu-id="3e316-186">.JPG</span></span>
- <span data-ttu-id="3e316-187">.EXIF</span><span class="sxs-lookup"><span data-stu-id="3e316-187">.EXIF</span></span>
- <span data-ttu-id="3e316-188">.PPM</span><span class="sxs-lookup"><span data-stu-id="3e316-188">.PPM</span></span>
- <span data-ttu-id="3e316-189">.PGM</span><span class="sxs-lookup"><span data-stu-id="3e316-189">.PGM</span></span>
- <span data-ttu-id="3e316-190">.PBM</span><span class="sxs-lookup"><span data-stu-id="3e316-190">.PBM</span></span>
- <span data-ttu-id="3e316-191">.PNM</span><span class="sxs-lookup"><span data-stu-id="3e316-191">.PNM</span></span>
- <span data-ttu-id="3e316-192">.WEBP</span><span class="sxs-lookup"><span data-stu-id="3e316-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="3e316-193">Behålla material med sekretessavtal innehåll</span><span class="sxs-lookup"><span data-stu-id="3e316-193">Retain NDA content</span></span> 

<span data-ttu-id="3e316-194">Den här rekommendationen visas när något av följande kriterier uppfylls.</span><span class="sxs-lookup"><span data-stu-id="3e316-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="3e316-195">Valfri kombination av dessa nyckelord identifieras i brödtexten i ett e-postmeddelande:</span><span class="sxs-lookup"><span data-stu-id="3e316-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="3e316-196">Sekretessavtal</span><span class="sxs-lookup"><span data-stu-id="3e316-196">NDA</span></span>
    - <span data-ttu-id="3e316-197">"Sekretess-avtal"</span><span class="sxs-lookup"><span data-stu-id="3e316-197">"Non-Disclosure Agreement"</span></span>
    - <span data-ttu-id="3e316-198">"Sekretess avtal"</span><span class="sxs-lookup"><span data-stu-id="3e316-198">"Non Disclosure Agreement"</span></span>

- <span data-ttu-id="3e316-199">Alla kombinationer av dessa nyckelord identifieras i .PDF eller .DOC-filer i SharePoint eller OneDrive:</span><span class="sxs-lookup"><span data-stu-id="3e316-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="3e316-200">Sekretessavtal</span><span class="sxs-lookup"><span data-stu-id="3e316-200">NDA</span></span>
    - <span data-ttu-id="3e316-201">Sekretess-avtal</span><span class="sxs-lookup"><span data-stu-id="3e316-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="3e316-202">Behålla programutvecklingsfiler</span><span class="sxs-lookup"><span data-stu-id="3e316-202">Retain software development files</span></span>

<span data-ttu-id="3e316-203">Den här rekommendationen visas när någon av följande filtyper identifieras i SharePoint eller OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3e316-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="3e316-204">.ASAX</span><span class="sxs-lookup"><span data-stu-id="3e316-204">.ASAX</span></span>
- <span data-ttu-id="3e316-205">.ASM</span><span class="sxs-lookup"><span data-stu-id="3e316-205">.ASM</span></span>
- <span data-ttu-id="3e316-206">.ASP\*</span><span class="sxs-lookup"><span data-stu-id="3e316-206">.ASP\*</span></span>
- <span data-ttu-id="3e316-207">.BAT</span><span class="sxs-lookup"><span data-stu-id="3e316-207">.BAT</span></span>
- <span data-ttu-id="3e316-208">.CONFIG</span><span class="sxs-lookup"><span data-stu-id="3e316-208">.CONFIG</span></span>
- <span data-ttu-id="3e316-209">.CS</span><span class="sxs-lookup"><span data-stu-id="3e316-209">.CS</span></span>
- <span data-ttu-id="3e316-210">.CSS</span><span class="sxs-lookup"><span data-stu-id="3e316-210">.CSS</span></span>
- <span data-ttu-id="3e316-211">.DISCO</span><span class="sxs-lookup"><span data-stu-id="3e316-211">.DISCO</span></span>
- <span data-ttu-id="3e316-212">.HTM\*</span><span class="sxs-lookup"><span data-stu-id="3e316-212">.HTM\*</span></span>
- <span data-ttu-id="3e316-213">.INC</span><span class="sxs-lookup"><span data-stu-id="3e316-213">.INC</span></span>
- <span data-ttu-id="3e316-214">.JAD</span><span class="sxs-lookup"><span data-stu-id="3e316-214">.JAD</span></span>
- <span data-ttu-id="3e316-215">.JAVA</span><span class="sxs-lookup"><span data-stu-id="3e316-215">.JAVA</span></span>
- <span data-ttu-id="3e316-216">.JS\*</span><span class="sxs-lookup"><span data-stu-id="3e316-216">.JS\*</span></span>
- <span data-ttu-id="3e316-217">.LIB</span><span class="sxs-lookup"><span data-stu-id="3e316-217">.LIB</span></span>
- <span data-ttu-id="3e316-218">.O</span><span class="sxs-lookup"><span data-stu-id="3e316-218">.O</span></span>
- <span data-ttu-id="3e316-219">.PHP</span><span class="sxs-lookup"><span data-stu-id="3e316-219">.PHP</span></span>
- <span data-ttu-id="3e316-220">.RC</span><span class="sxs-lookup"><span data-stu-id="3e316-220">.RC</span></span>
- <span data-ttu-id="3e316-221">.RESX</span><span class="sxs-lookup"><span data-stu-id="3e316-221">.RESX</span></span>
- <span data-ttu-id="3e316-222">.RPT</span><span class="sxs-lookup"><span data-stu-id="3e316-222">.RPT</span></span>
- <span data-ttu-id="3e316-223">.RSS</span><span class="sxs-lookup"><span data-stu-id="3e316-223">.RSS</span></span>
- <span data-ttu-id="3e316-224">.SCPT</span><span class="sxs-lookup"><span data-stu-id="3e316-224">.SCPT</span></span>
- <span data-ttu-id="3e316-225">.SRC</span><span class="sxs-lookup"><span data-stu-id="3e316-225">.SRC</span></span>
- <span data-ttu-id="3e316-226">.VB\*</span><span class="sxs-lookup"><span data-stu-id="3e316-226">.VB\*</span></span>
- <span data-ttu-id="3e316-227">.WSF</span><span class="sxs-lookup"><span data-stu-id="3e316-227">.WSF</span></span>
- <span data-ttu-id="3e316-228">.XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="3e316-228">.XCODEPROJ</span></span>
- <span data-ttu-id="3e316-229">.XML</span><span class="sxs-lookup"><span data-stu-id="3e316-229">.XML</span></span>
- <span data-ttu-id="3e316-230">.XSD</span><span class="sxs-lookup"><span data-stu-id="3e316-230">.XSD</span></span>
- <span data-ttu-id="3e316-231">.XSL\*</span><span class="sxs-lookup"><span data-stu-id="3e316-231">.XSL\*</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="3e316-232">Behålla videofiler</span><span class="sxs-lookup"><span data-stu-id="3e316-232">Retain video files</span></span>

<span data-ttu-id="3e316-233">Den här rekommendationen visas när någon av följande filtyper identifieras i SharePoint eller OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3e316-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="3e316-234">.AVCHD</span><span class="sxs-lookup"><span data-stu-id="3e316-234">.AVCHD</span></span>
- <span data-ttu-id="3e316-235">.AVI</span><span class="sxs-lookup"><span data-stu-id="3e316-235">.AVI</span></span>
- <span data-ttu-id="3e316-236">.FLV</span><span class="sxs-lookup"><span data-stu-id="3e316-236">.FLV</span></span>
- <span data-ttu-id="3e316-237">.MOV</span><span class="sxs-lookup"><span data-stu-id="3e316-237">.MOV</span></span>
- <span data-ttu-id="3e316-238">.MP2V</span><span class="sxs-lookup"><span data-stu-id="3e316-238">.MP2V</span></span>
- <span data-ttu-id="3e316-239">.MP4</span><span class="sxs-lookup"><span data-stu-id="3e316-239">.MP4</span></span>
- <span data-ttu-id="3e316-240">.MP4V</span><span class="sxs-lookup"><span data-stu-id="3e316-240">.MP4V</span></span>
- <span data-ttu-id="3e316-241">.MPE</span><span class="sxs-lookup"><span data-stu-id="3e316-241">.MPE</span></span>
- <span data-ttu-id="3e316-242">.MPEG</span><span class="sxs-lookup"><span data-stu-id="3e316-242">.MPEG</span></span>
- <span data-ttu-id="3e316-243">.MPEG1</span><span class="sxs-lookup"><span data-stu-id="3e316-243">.MPEG1</span></span>
- <span data-ttu-id="3e316-244">.MPEG2</span><span class="sxs-lookup"><span data-stu-id="3e316-244">.MPEG2</span></span>
- <span data-ttu-id="3e316-245">.MPEG4</span><span class="sxs-lookup"><span data-stu-id="3e316-245">.MPEG4</span></span>
- <span data-ttu-id="3e316-246">.MPG</span><span class="sxs-lookup"><span data-stu-id="3e316-246">.MPG</span></span>
- <span data-ttu-id="3e316-247">.MPG2</span><span class="sxs-lookup"><span data-stu-id="3e316-247">.MPG2</span></span>
- <span data-ttu-id="3e316-248">.MPG4</span><span class="sxs-lookup"><span data-stu-id="3e316-248">.MPG4</span></span>
- <span data-ttu-id="3e316-249">.WMV</span><span class="sxs-lookup"><span data-stu-id="3e316-249">.WMV</span></span>
- <span data-ttu-id="3e316-250">.XMV</span><span class="sxs-lookup"><span data-stu-id="3e316-250">.XMV</span></span>