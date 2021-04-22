---
title: Planera för programvara och programvaruversioner som slutar på grund av support
description: Upptäck och planera för program- och programvaruversioner som inte längre stöds och inte får säkerhetsuppdateringar.
keywords: Hantering av hot och sårbarhet, Microsoft Defender för Endpoint tvm-säkerhetsrekommendationer, rekommendation om cybersäkerhet, rekommendation om säkerhet på åtgärd
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8e8fc228b8856df03b580e748bf00efc8d4333c3
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934135"
---
# <a name="plan-for-end-of-support-software-and-software-versions-with-threat-and-vulnerability-management"></a><span data-ttu-id="a5b22-104">Planera för slutet av supportprogramvara och programvaruversioner med hot och sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="a5b22-104">Plan for end-of-support software and software versions with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a5b22-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a5b22-105">**Applies to:**</span></span>

- [<span data-ttu-id="a5b22-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a5b22-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="a5b22-107">Hantering av hot och sårbarhet</span><span class="sxs-lookup"><span data-stu-id="a5b22-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="a5b22-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5b22-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a5b22-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="a5b22-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a5b22-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="a5b22-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="a5b22-111">Supporten för programvara eller programversioner (EOS, kallas även slutet på livscykeln, EOL), innebär att de inte längre kommer att få support eller service, och att de inte får säkerhetsuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="a5b22-111">End-of-support (EOS), otherwise known as end-of-life (EOL), for software or software versions means that they will no longer be supported or serviced, and will not receive security updates.</span></span> <span data-ttu-id="a5b22-112">När du använder programvara eller programvaruversioner utan att ha avslutat supporten utser du organisationen för att skapa säkerhetsbrister, juridiska och finansiella risker.</span><span class="sxs-lookup"><span data-stu-id="a5b22-112">When you use software or software versions with ended support, you're exposing your organization to security vulnerabilities, legal, and financial risks.</span></span>

<span data-ttu-id="a5b22-113">Det är centralt för säkerhet- och IT-administratörer att samarbeta och se till att organisationens programvaruinventering har konfigurerats för optimala resultat, efterlevnad och ett hälsosamt nätverks-ekosystem.</span><span class="sxs-lookup"><span data-stu-id="a5b22-113">It's crucial for Security and IT Administrators to work together and ensure that the organization's software inventory is configured for optimal results, compliance, and a healthy network ecosystem.</span></span> <span data-ttu-id="a5b22-114">De bör granska alternativen för att ta bort eller ersätta program som stöds i slutet av supporten och uppdateringsversionerna som inte längre stöds.</span><span class="sxs-lookup"><span data-stu-id="a5b22-114">They should examine the options to remove or replace apps that have reached end-of-support and update versions that are no longer supported.</span></span> <span data-ttu-id="a5b22-115">Det är bäst att skapa och implementera en plan **innan supportdatumen** är slut.</span><span class="sxs-lookup"><span data-stu-id="a5b22-115">It's best to create and implement a plan **before** the end of support dates.</span></span>

## <a name="find-software-or-software-versions-that-are-no-longer-supported"></a><span data-ttu-id="a5b22-116">Hitta program- och programvaruversioner som inte längre stöds</span><span class="sxs-lookup"><span data-stu-id="a5b22-116">Find software or software versions that are no longer supported</span></span>

1. <span data-ttu-id="a5b22-117">Från menyn för hantering av hot och sårbarhet går du till [**rekommendationer om säkerhet.**](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="a5b22-117">From the threat and vulnerability management menu, navigate to [**Security recommendations**](tvm-security-recommendation.md).</span></span>
2. <span data-ttu-id="a5b22-118">Gå till **panelen Filter** och leta efter avsnittet med taggar.</span><span class="sxs-lookup"><span data-stu-id="a5b22-118">Go to the **Filters** panel and look for the tags section.</span></span> <span data-ttu-id="a5b22-119">Markera ett eller flera av EOS-taggalternativen.</span><span class="sxs-lookup"><span data-stu-id="a5b22-119">Select one or more of the EOS tag options.</span></span> <span data-ttu-id="a5b22-120">Använd **sedan**.</span><span class="sxs-lookup"><span data-stu-id="a5b22-120">Then **Apply**.</span></span>

    ![Skärmbildstaggar som säger EOS-programvara, EOS-versioner och kommande EOS-versioner.](images/tvm-eos-tag.png)

3. <span data-ttu-id="a5b22-122">Du ser en lista med rekommendationer relaterade till programvara med upphört med support, programvaruversioner som upphör och versioner med kommande support upphör.</span><span class="sxs-lookup"><span data-stu-id="a5b22-122">You'll see a list of recommendations related to software with ended support, software versions that are end of support, or versions with upcoming end of support.</span></span> <span data-ttu-id="a5b22-123">De här taggarna visas också på [sidan för programvaruinventering.](tvm-software-inventory.md)</span><span class="sxs-lookup"><span data-stu-id="a5b22-123">These tags are also visible in the [software inventory](tvm-software-inventory.md) page.</span></span>

    ![Rekommendationer med EOS-tagg.](images/tvm-eos-tags-column.png)

## <a name="list-of-versions-and-dates"></a><span data-ttu-id="a5b22-125">Lista över versioner och datum</span><span class="sxs-lookup"><span data-stu-id="a5b22-125">List of versions and dates</span></span>

<span data-ttu-id="a5b22-126">Om du vill visa en lista över versioner som snart har supporten har gått ut, eller snart har supporten, och dessa datum, följer du stegen nedan:</span><span class="sxs-lookup"><span data-stu-id="a5b22-126">To view a list of versions that have reached end of support, or end or support soon, and those dates, follow the below steps:</span></span>

1. <span data-ttu-id="a5b22-127">Ett meddelande visas i den utfällliga säkerhetsrekommendationerna för programvara med versioner där supporten har gått ut, eller snart kommer att upphöra med support.</span><span class="sxs-lookup"><span data-stu-id="a5b22-127">A message will appear in the security recommendation flyout for software with versions that have reached end of support, or will reach end of support soon.</span></span>

    ![Skärmbild av länken för versionsdistribution.](images/eos-upcoming-eos.png)

2. <span data-ttu-id="a5b22-129">Välj länken **för versionsdistribution** för att gå till sidan för programvarugranskning.</span><span class="sxs-lookup"><span data-stu-id="a5b22-129">Select the **version distribution** link to go to the software drill-down page.</span></span> <span data-ttu-id="a5b22-130">Där visas en filtrerad lista med versioner med taggar som identifierar dem som supporten är slut eller kommande support avslutas.</span><span class="sxs-lookup"><span data-stu-id="a5b22-130">There, you can see a filtered list of versions with tags identifying them as end of support, or upcoming end of support.</span></span>

    ![Skärmbild av sidan för software drilldown med slutet av supportprogramvaran.](images/software-drilldown-eos.png)

3. <span data-ttu-id="a5b22-132">Välj någon av versionerna i tabellen som ska öppnas.</span><span class="sxs-lookup"><span data-stu-id="a5b22-132">Select one of the versions in the table to open.</span></span> <span data-ttu-id="a5b22-133">Till exempel version 10.0.18362.1.</span><span class="sxs-lookup"><span data-stu-id="a5b22-133">For example, version 10.0.18362.1.</span></span> <span data-ttu-id="a5b22-134">En utfälling visas när supportdatumet är slut.</span><span class="sxs-lookup"><span data-stu-id="a5b22-134">A flyout will appear with the end of support date.</span></span>

    ![Skärmbild av supportens datum.](images/version-eos-date.png)

<span data-ttu-id="a5b22-136">När du har identifierat vilka program- och programvaruversioner som är sårbara på grund av deras status vid slutet av supporten måste du bestämma dig för om du vill uppdatera eller ta bort dem från organisationen.</span><span class="sxs-lookup"><span data-stu-id="a5b22-136">Once you identify which software and software versions are vulnerable due to their end-of-support status, you must decide whether to update or remove them from your organization.</span></span> <span data-ttu-id="a5b22-137">Om du gör det minskar risken för risker för organisationer och avancerade fortlöpande hot.</span><span class="sxs-lookup"><span data-stu-id="a5b22-137">Doing so will lower your organizations exposure to vulnerabilities and advanced persistent threats.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a5b22-138">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="a5b22-138">Related topics</span></span>

- [<span data-ttu-id="a5b22-139">Översikt över hot- och sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="a5b22-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="a5b22-140">Säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="a5b22-140">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="a5b22-141">Programvaruinventering</span><span class="sxs-lookup"><span data-stu-id="a5b22-141">Software inventory</span></span>](tvm-software-inventory.md)
