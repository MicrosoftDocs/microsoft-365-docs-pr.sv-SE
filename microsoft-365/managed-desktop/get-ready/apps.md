---
title: Appar i Microsoft Hanterat skrivbord
description: Förklarar hur appar hanteras, inklusive hur du paketerar, distribuerar och ger stöd för dem.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 571acc9c240fc0243998050ac3013258a2f85a3e
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52028950"
---
# <a name="apps-in-microsoft-managed-desktop"></a><span data-ttu-id="86a7b-104">Appar i Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="86a7b-104">Apps in Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a><span data-ttu-id="86a7b-105">Appar i allmänhet</span><span class="sxs-lookup"><span data-stu-id="86a7b-105">Apps generally</span></span>

<span data-ttu-id="86a7b-106">Microsoft inkluderar vissa viktiga appar tillsammans med den Microsoft 365 E3 eller E5-licens som krävs för att delta i Microsoft Hanterat skrivbord.</span><span class="sxs-lookup"><span data-stu-id="86a7b-106">Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop.</span></span> <span data-ttu-id="86a7b-107">Men även om vi tillhandahåller dessa appar har du fortfarande vissa ansvarsområden och åtgärder som måste slutföras.</span><span class="sxs-lookup"><span data-stu-id="86a7b-107">However, even though we provide these apps, you still have certain responsibilities and actions to complete.</span></span>

<span data-ttu-id="86a7b-108">Du kan också distribuera ytterligare program som inte är Microsoft-program till användarna för självbetjäning via Företagsportal eller en obligatorisk bakgrundsinstallation, allt med hjälp av Microsoft Intune:s distributionsförlopp.</span><span class="sxs-lookup"><span data-stu-id="86a7b-108">You can also deploy additional non-Microsoft apps to your users for self-service through the Company Portal or a required background installation, all using Microsoft Intune’s deployment pipeline.</span></span> 

## <a name="apps-provided-by-microsoft"></a><span data-ttu-id="86a7b-109">Appar som tillhandahålls av Microsoft</span><span class="sxs-lookup"><span data-stu-id="86a7b-109">Apps provided by Microsoft</span></span>

<span data-ttu-id="86a7b-110">Som en del av Microsoft Hanterat skrivbord-licensen ingår 64-bitarsversioner av apparna i Microsoft 365-appar för företag Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype för företag och OneNote.) Klicka-och-kör-versioner Microsoft Project och Visio inte ingår  som standard, men du kan begära att de läggs till.</span><span class="sxs-lookup"><span data-stu-id="86a7b-110">Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, and OneNote.) Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but you can request them to be added.</span></span> <span data-ttu-id="86a7b-111">Mer information om apparna finns i Installera [Microsoft Project eller Microsoft Visio på Microsoft Hanterat skrivbord enheter.](../get-started/project-visio.md)</span><span class="sxs-lookup"><span data-stu-id="86a7b-111">For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a><span data-ttu-id="86a7b-112">Vad Microsoft gör för att stödja de appar vi tillhandahåller</span><span class="sxs-lookup"><span data-stu-id="86a7b-112">What Microsoft does to support the apps we provide</span></span>

<span data-ttu-id="86a7b-113">Microsoft kommer att tillhandahålla fullständiga tjänster för distribution, uppdatering och support för de Microsoft 365-appar för företag program.</span><span class="sxs-lookup"><span data-stu-id="86a7b-113">Microsoft will provide full service for the deployment, update, and support for the included Microsoft 365 Apps for enterprise apps.</span></span> <span data-ttu-id="86a7b-114">Klicka-och-kör-versioner av Microsoft Project och Visio  ingår inte som standard, men Microsoft Hanterat skrivbord tillhandahåller distributionsgrupper där IT-administratören kan hantera licenser och distribuera programmen på rätt sätt för din organisation.</span><span class="sxs-lookup"><span data-stu-id="86a7b-114">Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but Microsoft Managed Desktop will provide deployment groups allowing your IT administrator to manage licenses and deploy these applications appropriately for your organization.</span></span> <span data-ttu-id="86a7b-115">Microsoft ger support för användare av dessa program via Microsoft Hanterat skrivbord-supportkanalerna.</span><span class="sxs-lookup"><span data-stu-id="86a7b-115">Microsoft will support users of these applications through the Microsoft Managed Desktop support channels.</span></span>

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a><span data-ttu-id="86a7b-116">Vad du behöver göra för att stödja de appar vi tillhandahåller</span><span class="sxs-lookup"><span data-stu-id="86a7b-116">What you need to do to support the apps we provide</span></span>

<span data-ttu-id="86a7b-117">Det finns fortfarande vissa saker du behöver göra med de här apparna:</span><span class="sxs-lookup"><span data-stu-id="86a7b-117">There are still certain things you need to do with these apps:</span></span>

- <span data-ttu-id="86a7b-118">**Tilldela licenser** – Du ansvarar för att skaffa och tilldela licenser till användarna för Microsoft 365-appar för företag.</span><span class="sxs-lookup"><span data-stu-id="86a7b-118">**Assign licenses** - You are responsible for obtaining and assigning the appropriate licenses to users for Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="86a7b-119">**Lägga till användare i** säkerhetsgrupper – Om du använder Microsoft Project eller Visio måste IT-administratören lägga till de användarna i rätt distributionsgrupper.</span><span class="sxs-lookup"><span data-stu-id="86a7b-119">**Add users to security groups** - If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="86a7b-120">IT-administratörer är också ansvariga för att återta licenser från dessa användare om de lämnar företaget.</span><span class="sxs-lookup"><span data-stu-id="86a7b-120">IT administrators are also responsible for reclaiming licenses from those users if they leave the company.</span></span>
- <span data-ttu-id="86a7b-121">Distribuera Microsoft 365 tillägg – Om du behöver tillägg för något av **Microsoft 365-appar för företag-programmen** distribuerar du dem centralt precis som andra Windows 32-program.</span><span class="sxs-lookup"><span data-stu-id="86a7b-121">**Deploy Microsoft 365 Add-ons** - If you need any Add-ons for any of the Microsoft 365 Apps for enterprise apps, deploy them centrally like any other Windows 32 app.</span></span> 

## <a name="apps-you-provide"></a><span data-ttu-id="86a7b-122">Appar som du tillhandahåller</span><span class="sxs-lookup"><span data-stu-id="86a7b-122">Apps you provide</span></span>

<span data-ttu-id="86a7b-123">Du har förmodligen andra appar som du behöver för verksamheten.</span><span class="sxs-lookup"><span data-stu-id="86a7b-123">You probably have other apps you need for your business operations.</span></span> <span data-ttu-id="86a7b-124">De här apparna kan endast distribueras Microsoft Hanterat skrivbord enheter med hjälp Microsoft Intune distributionsförlopp.</span><span class="sxs-lookup"><span data-stu-id="86a7b-124">These apps can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="86a7b-125">Mer information om programdistribution finns i Distribuera [program till Microsoft Hanterat skrivbord enheter.](../get-started/deploy-apps.md)</span><span class="sxs-lookup"><span data-stu-id="86a7b-125">For more information about application deployment follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span></span>

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a><span data-ttu-id="86a7b-126">Förbereda egna appar för inkludering i Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="86a7b-126">Preparing your own apps for inclusion in Microsoft Managed Desktop</span></span>
<span data-ttu-id="86a7b-127">Granska dina appar och kontrollera:</span><span class="sxs-lookup"><span data-stu-id="86a7b-127">Review your apps, checking:</span></span>

- <span data-ttu-id="86a7b-128">Ingen av apparna är förbjudna eller har begränsat beteende enligt beskrivningen [Microsoft Hanterat skrivbord appkrav.](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="86a7b-128">None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
- <span data-ttu-id="86a7b-129">Apparna måste vara klara att hantera Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="86a7b-129">Apps must be ready for management by Microsoft Intune.</span></span> <span data-ttu-id="86a7b-130">Mer information om det här avsnittet finns [i Windows 10 programdistribution med hjälp Microsoft Intune](/intune/apps-windows-10-app-deploy) och Lägga till appar i [Microsoft Intune](/intune/apps-add).</span><span class="sxs-lookup"><span data-stu-id="86a7b-130">For more about this topic, see [Windows 10 app deployment using Microsoft Intune](/intune/apps-windows-10-app-deploy) and [Add apps to Microsoft Intune](/intune/apps-add).</span></span>
- <span data-ttu-id="86a7b-131">Andra paketeringskrav som till exempel tillhandahålla licensnycklar, avtal med licensvillkor och förinställning av serveranslutningar.</span><span class="sxs-lookup"><span data-stu-id="86a7b-131">Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="86a7b-132">Steg för att förbereda dig</span><span class="sxs-lookup"><span data-stu-id="86a7b-132">Steps to get ready</span></span>

1. <span data-ttu-id="86a7b-133">Granska [Krav för Microsoft Hanterat skrivbord](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="86a7b-133">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="86a7b-134">Använda [utvärderingsverktyg för beredskap](readiness-assessment-tool.md).</span><span class="sxs-lookup"><span data-stu-id="86a7b-134">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="86a7b-135">Förutsättningar för gästkonton</span><span class="sxs-lookup"><span data-stu-id="86a7b-135">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="86a7b-136">Nätverkskonfiguration för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="86a7b-136">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="86a7b-137">Förbereda certifikat och nätverksprofiler för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="86a7b-137">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="86a7b-138">Förbereda åtkomst till lokala resurser för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="86a7b-138">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. <span data-ttu-id="86a7b-139">[Appar i Microsoft Hanterat skrivbord](apps.md) (den här artikeln)</span><span class="sxs-lookup"><span data-stu-id="86a7b-139">[Apps in Microsoft Managed Desktop](apps.md) (This article)</span></span>
8. [<span data-ttu-id="86a7b-140">Förbereda mappade enheter för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="86a7b-140">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="86a7b-141">Förbereda utskriftsresurser för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="86a7b-141">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
