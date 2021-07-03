---
title: Förbereda utskriftsresurser för Microsoft Hanterat skrivbord
description: Viktiga steg för att se till att utskriften fungerar smidigt
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 3f77074aa11e9dc82c8fac9763fdebfd2fc49d99
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287215"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a><span data-ttu-id="fb2f8-104">Förbereda utskriftsresurser för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="fb2f8-104">Prepare printing resources for Microsoft Managed Desktop</span></span>

<span data-ttu-id="fb2f8-105">När du gör dig redo att registrera dig Microsoft Hanterat skrivbord bör du utvärdera dina utskriftskrav och bestämma rätt metod för din miljö.</span><span class="sxs-lookup"><span data-stu-id="fb2f8-105">As you get ready to enroll in Microsoft Managed Desktop, you should evaluate your printing requirements and determine the right approach for your environment.</span></span> <span data-ttu-id="fb2f8-106">Det finns tre alternativ:</span><span class="sxs-lookup"><span data-stu-id="fb2f8-106">You have three options:</span></span>

- <span data-ttu-id="fb2f8-107">Distribuera Microsofts universalutskriftslösning för att göra det enkelt Microsoft Hanterat skrivbord att identifiera skrivare.</span><span class="sxs-lookup"><span data-stu-id="fb2f8-107">Deploy the Microsoft Universal Print solution to make it easy for Microsoft Managed Desktop devices to discover printers.</span></span> <span data-ttu-id="fb2f8-108">Mer information finns i Vad [är Universell utskrift.](/universal-print/fundamentals/universal-print-whatis)</span><span class="sxs-lookup"><span data-stu-id="fb2f8-108">For more information, see [What is Universal Print](/universal-print/fundamentals/universal-print-whatis).</span></span>
- <span data-ttu-id="fb2f8-109">Distribuera skrivare direkt med hjälp av ett anpassat PowerShell-skript.</span><span class="sxs-lookup"><span data-stu-id="fb2f8-109">Deploy printers directly by using a custom PowerShell script.</span></span> <span data-ttu-id="fb2f8-110">Följ anvisningarna i [avsnittet Konfigurera lokala](#set-up-local-printers) skrivare.</span><span class="sxs-lookup"><span data-stu-id="fb2f8-110">Follow the steps in the [Set up local printers](#set-up-local-printers) section.</span></span>
- <span data-ttu-id="fb2f8-111">Använd en lösning som inte är en Microsoft-lösning för molnutskrift som är Windows 10 enheter som är anslutna till en Azure Active Directory domän.</span><span class="sxs-lookup"><span data-stu-id="fb2f8-111">Use a non-Microsoft cloud printing solution that is compatible with Windows 10 devices that are joined to an Azure Active Directory domain.</span></span> <span data-ttu-id="fb2f8-112">Lösningen måste uppfylla programvarukraven för Microsoft Hanterat skrivbord.</span><span class="sxs-lookup"><span data-stu-id="fb2f8-112">The solution must meet the software requirements for Microsoft Managed Desktop.</span></span> <span data-ttu-id="fb2f8-113">Mer information finns i Microsoft Hanterat skrivbord [för appar.](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="fb2f8-113">For more information, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
 
<span data-ttu-id="fb2f8-114">I samtliga fall om skrivardrivrutinerna inte är tillgängliga från Microsoft Update eller Microsoft Store måste du själv hämta dem och paketera dem för distribution till dina Microsoft Hanterat skrivbord-enheter med Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="fb2f8-114">In all cases, if the printer drivers are not available from Microsoft Update or the Microsoft Store, you'll have to obtain them yourself and have them packaged for deployment to your Microsoft Managed Desktop devices with Microsoft Intune.</span></span> <span data-ttu-id="fb2f8-115">Mer information finns i [Fristående Intune – Win32-apphantering](/mem/intune/apps/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="fb2f8-115">For more, see [Intune Standalone - Win32 app management](/mem/intune/apps/apps-win32-app-management)</span></span>

## <a name="set-up-local-printers"></a><span data-ttu-id="fb2f8-116">Konfigurera lokala skrivare</span><span class="sxs-lookup"><span data-stu-id="fb2f8-116">Set up local printers</span></span>

<span data-ttu-id="fb2f8-117">Om du har bestämt dig för att distribuera skrivare med hjälp av ett anpassat PowerShell-skript och har förberett utskriftsresurserna följer du de här stegen för att distribuera delade skrivare:</span><span class="sxs-lookup"><span data-stu-id="fb2f8-117">If you've decided to deploy printers by using a custom PowerShell script and have prepared the printing resources, follow these steps to have shared printers deployed:</span></span>

1. <span data-ttu-id="fb2f8-118">Gå till Microsoft Hanterat skrivbord portalen.</span><span class="sxs-lookup"><span data-stu-id="fb2f8-118">Navigate to the Microsoft Managed Desktop portal.</span></span>
2. <span data-ttu-id="fb2f8-119">Skicka en begäran med etiketten *Skrivardistribution* i **avsnittet Support > supportförfrågningar** i administrationsportalen med följande information:</span><span class="sxs-lookup"><span data-stu-id="fb2f8-119">Submit a request labeled *Printer deployment* in the **Support > Support requests** section of the Admin Portal, providing these details:</span></span>
    - <span data-ttu-id="fb2f8-120">Alla UNC-sökvägar till delade skrivarplatser som måste distribueras för Microsoft Hanterat skrivbord enheter</span><span class="sxs-lookup"><span data-stu-id="fb2f8-120">All UNC paths to shared printer locations that will need to be deployed for Microsoft Managed Desktop devices</span></span>
    - <span data-ttu-id="fb2f8-121">Användargrupper som kräver åtkomst till dessa delade skrivare</span><span class="sxs-lookup"><span data-stu-id="fb2f8-121">User groups that require access to these shared printers</span></span>
3. <span data-ttu-id="fb2f8-122">I administrationsportalen meddelas du när begäran har slutförts.</span><span class="sxs-lookup"><span data-stu-id="fb2f8-122">Using the Admin Portal, we'll let you know when the request has been completed.</span></span> <span data-ttu-id="fb2f8-123">Först distribuerar vi bara konfigurationen till enheter i testdistributionsgruppen.</span><span class="sxs-lookup"><span data-stu-id="fb2f8-123">Initially we'll only deploy the configuration to devices in the Test deployment group.</span></span>
4. <span data-ttu-id="fb2f8-124">Du måste testa och bekräfta om konfigurationen fungerar som förväntat.</span><span class="sxs-lookup"><span data-stu-id="fb2f8-124">You must test and confirm whether the configuration works as you expect.</span></span> <span data-ttu-id="fb2f8-125">Svara genom att använda **fliken** Diskussion i supportbegäran och meddela oss när du har slutfört testningen.</span><span class="sxs-lookup"><span data-stu-id="fb2f8-125">Reply by using the **Discussion** tab in the Support request to let us know when you've completed your testing.</span></span>
5. <span data-ttu-id="fb2f8-126">Sedan distribuerar vi konfigurationen till andra distributionsgrupper.</span><span class="sxs-lookup"><span data-stu-id="fb2f8-126">We'll then deploy the configuration to the other deployment groups.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="fb2f8-127">Steg för att förbereda dig</span><span class="sxs-lookup"><span data-stu-id="fb2f8-127">Steps to get ready</span></span>

1. <span data-ttu-id="fb2f8-128">Granska [Krav för Microsoft Hanterat skrivbord](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="fb2f8-128">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="fb2f8-129">Använda [utvärderingsverktyg för beredskap](readiness-assessment-tool.md).</span><span class="sxs-lookup"><span data-stu-id="fb2f8-129">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="fb2f8-130">Förutsättningar för gästkonton</span><span class="sxs-lookup"><span data-stu-id="fb2f8-130">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="fb2f8-131">Nätverkskonfiguration för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="fb2f8-131">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="fb2f8-132">Förbereda certifikat och nätverksprofiler för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="fb2f8-132">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="fb2f8-133">Förbereda åtkomst till lokala resurser för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="fb2f8-133">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="fb2f8-134">Appar i Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="fb2f8-134">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="fb2f8-135">Förbereda mappade enheter för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="fb2f8-135">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. <span data-ttu-id="fb2f8-136">[Förbereda utskriftsresurser för Microsoft Hanterat skrivbord](printing.md) (den här artikeln)</span><span class="sxs-lookup"><span data-stu-id="fb2f8-136">[Prepare printing resources for Microsoft Managed Desktop](printing.md) (This article)</span></span>
