---
title: Förbereda skrivarresurser för Microsoft Hanterat skrivbord
description: Viktiga steg för att se till att utskriften fungerar smidigt
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 971644aafabda733bf745fae278bdfeeed3282e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574553"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a><span data-ttu-id="21526-104">Förbereda skrivarresurser för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="21526-104">Prepare printing resources for Microsoft Managed Desktop</span></span>

<span data-ttu-id="21526-105">När du gör dig redo att registrera dig i Microsoft Managed Desktop bör du utvärdera dina utskriftskrav och bestämma rätt metod för din miljö.</span><span class="sxs-lookup"><span data-stu-id="21526-105">As you get ready to enroll in Microsoft Managed Desktop, you should evaluate your printing requirements and determine the right approach for your environment.</span></span> <span data-ttu-id="21526-106">Det finns tre alternativ:</span><span class="sxs-lookup"><span data-stu-id="21526-106">You have three options:</span></span>
 
- <span data-ttu-id="21526-107">Distribuera Microsoft Universal Print-lösningen för att göra det enkelt för Microsoft Managed Desktop-enheter att identifiera skrivare.</span><span class="sxs-lookup"><span data-stu-id="21526-107">Deploy the Microsoft Universal Print solution to make it easy for Microsoft Managed Desktop devices to discover printers.</span></span> <span data-ttu-id="21526-108">Mer information finns i Vad [är Universell utskrift.](/universal-print/fundamentals/universal-print-whatis)</span><span class="sxs-lookup"><span data-stu-id="21526-108">For more information, see [What is Universal Print](/universal-print/fundamentals/universal-print-whatis).</span></span>
- <span data-ttu-id="21526-109">Distribuera skrivare direkt med hjälp av ett anpassat PowerShell-skript.</span><span class="sxs-lookup"><span data-stu-id="21526-109">Deploy printers directly by using a custom PowerShell script.</span></span> <span data-ttu-id="21526-110">Följ anvisningarna i [avsnittet Konfigurera lokala](#set-up-local-printers) skrivare.</span><span class="sxs-lookup"><span data-stu-id="21526-110">Follow the steps in the [Set up local printers](#set-up-local-printers) section.</span></span>
- <span data-ttu-id="21526-111">Använd en lösning som inte är en Microsoft-lösning för molnutskrift som är kompatibel med Windows 10-enheter som är anslutna till en Azure Active Directory-domän.</span><span class="sxs-lookup"><span data-stu-id="21526-111">Use a non-Microsoft cloud printing solution that is compatible with Windows 10 devices that are joined to an Azure Active Directory domain.</span></span> <span data-ttu-id="21526-112">Lösningen måste uppfylla programvarukraven för Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="21526-112">The solution must meet the software requirements for Microsoft Managed Desktop.</span></span> <span data-ttu-id="21526-113">Mer information finns i [Appkrav för Microsoft Managed Desktop.](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="21526-113">For more information, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
 
<span data-ttu-id="21526-114">Om skrivardrivrutinerna inte är tillgängliga från Microsoft Update eller Microsoft Store måste du i samtliga fall skaffa dem själv och paketera dem för distribution till dina Microsoft Managed Desktop-enheter med Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="21526-114">In all cases, if the printer drivers are not available from Microsoft Update or the Microsoft Store, you'll have to obtain them yourself and have them packaged for deployment to your Microsoft Managed Desktop devices with Microsoft Intune.</span></span> <span data-ttu-id="21526-115">Mer information finns i [Fristående Intune – Win32-apphantering](/mem/intune/apps/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="21526-115">For more, see [Intune Standalone - Win32 app management](/mem/intune/apps/apps-win32-app-management)</span></span>

## <a name="set-up-local-printers"></a><span data-ttu-id="21526-116">Konfigurera lokala skrivare</span><span class="sxs-lookup"><span data-stu-id="21526-116">Set up local printers</span></span>

<span data-ttu-id="21526-117">Om du har bestämt dig för att distribuera skrivare med hjälp av ett anpassat PowerShell-skript och har förberett utskriftsresurserna följer du de här stegen för att distribuera delade skrivare:</span><span class="sxs-lookup"><span data-stu-id="21526-117">If you've decided to deploy printers by using a custom PowerShell script and have prepared the printing resources, follow these steps to have shared printers deployed:</span></span>

1.  <span data-ttu-id="21526-118">Gå till Microsoft Managed Desktop-portalen.</span><span class="sxs-lookup"><span data-stu-id="21526-118">Navigate to the Microsoft Managed Desktop portal.</span></span>
2.  <span data-ttu-id="21526-119">Skicka en begäran med etiketten *Skrivardistribution* i **avsnittet Support > supportförfrågningar** i administrationsportalen med följande information:</span><span class="sxs-lookup"><span data-stu-id="21526-119">Submit a request labeled *Printer deployment* in the **Support > Support requests** section of the Admin Portal, providing these details:</span></span>
    - <span data-ttu-id="21526-120">Alla UNC-sökvägar till delade skrivarplatser som måste distribueras för Microsoft Managed Desktop-enheter</span><span class="sxs-lookup"><span data-stu-id="21526-120">All UNC paths to shared printer locations that will need to be deployed for Microsoft Managed Desktop devices</span></span>
    - <span data-ttu-id="21526-121">Användargrupper som kräver åtkomst till dessa delade skrivare</span><span class="sxs-lookup"><span data-stu-id="21526-121">User groups that require access to these shared printers</span></span>
3.  <span data-ttu-id="21526-122">I administrationsportalen meddelas du när begäran har slutförts.</span><span class="sxs-lookup"><span data-stu-id="21526-122">Using the Admin Portal, we'll let you know when the request has been completed.</span></span> <span data-ttu-id="21526-123">Först distribuerar vi bara konfigurationen till enheter i testdistributionsgruppen.</span><span class="sxs-lookup"><span data-stu-id="21526-123">Initially we'll only deploy the configuration to devices in the Test deployment group.</span></span>
4.  <span data-ttu-id="21526-124">Du måste testa och bekräfta om konfigurationen fungerar som förväntat.</span><span class="sxs-lookup"><span data-stu-id="21526-124">You must test and confirm whether the configuration works as you expect.</span></span> <span data-ttu-id="21526-125">Svara genom att använda **fliken** Diskussion i supportbegäran och meddela oss när du har slutfört testningen.</span><span class="sxs-lookup"><span data-stu-id="21526-125">Reply by using the **Discussion** tab in the Support request to let us know when you've completed your testing.</span></span>
5.  <span data-ttu-id="21526-126">Sedan distribuerar vi konfigurationen till andra distributionsgrupper.</span><span class="sxs-lookup"><span data-stu-id="21526-126">We'll then deploy the configuration to the other deployment groups.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="21526-127">Steg för att förbereda dig</span><span class="sxs-lookup"><span data-stu-id="21526-127">Steps to get ready</span></span>

1. <span data-ttu-id="21526-128">Granska [Krav för Microsoft Managed Desktop](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="21526-128">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="21526-129">Använda [utvärderingsverktyg för beredskap](readiness-assessment-tool.md).</span><span class="sxs-lookup"><span data-stu-id="21526-129">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="21526-130">Förutsättningar för gästkonton</span><span class="sxs-lookup"><span data-stu-id="21526-130">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="21526-131">Nätverks konfiguration för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="21526-131">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="21526-132">Förbereda certifikat och nätverks profiler för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="21526-132">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="21526-133">Förbereda lokala resurser till gång för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="21526-133">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="21526-134">Appar på Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="21526-134">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="21526-135">Förbereda mappade enheter för Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="21526-135">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. <span data-ttu-id="21526-136">[Förbereda utskriftsresurser för Microsoft Managed Desktop](printing.md) (den här artikeln)</span><span class="sxs-lookup"><span data-stu-id="21526-136">[Prepare printing resources for Microsoft Managed Desktop](printing.md) (This article)</span></span>
