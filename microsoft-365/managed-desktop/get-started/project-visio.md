---
title: Installera Microsoft Project eller Microsoft Visio på Microsoft Managed Station ära enheter
description: Information om hur du installerar Microsoft Project eller Microsoft Visio på Microsoft Managed Station ära enheter
keywords: Microsoft-hanterat skriv bord, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c04bcdf846bafaa7838ef5932c8de595f5035992
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950538"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="e748e-104">Installera Microsoft Project eller Microsoft Visio på Microsoft Managed Station ära enheter</span><span class="sxs-lookup"><span data-stu-id="e748e-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="e748e-105">Microsoft Project och Microsoft Visio kräver att specifika steg installeras på Microsoft Managed Station ära datorer.</span><span class="sxs-lookup"><span data-stu-id="e748e-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="e748e-106">I det här avsnittet beskrivs förutsättningar och installations processen för dessa program.</span><span class="sxs-lookup"><span data-stu-id="e748e-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e748e-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="e748e-107">Prerequisites</span></span>

<span data-ttu-id="e748e-108">Administratörer bör kontrol lera att de uppfyller följande krav:</span><span class="sxs-lookup"><span data-stu-id="e748e-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="e748e-109">**Licens mängder** -det korrekta beloppet för Microsoft Project-och Microsoft Visio-licenser måste vara tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="e748e-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="e748e-110">Microsoft Managed Desktop stöder för närvarande endast 64-bitars versioner av dessa program.</span><span class="sxs-lookup"><span data-stu-id="e748e-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="e748e-111">**Licens namn** -lämpliga licens namn för dessa program är:</span><span class="sxs-lookup"><span data-stu-id="e748e-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="e748e-112">**Microsoft Project** – Project Online Professional eller Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="e748e-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="e748e-113">**Microsoft Visio** – Visio Online abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="e748e-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="e748e-114">**Företags Portal** -företags portalen måste vara tillgänglig i klient organisationen för att användarna ska kunna installera dessa program.</span><span class="sxs-lookup"><span data-stu-id="e748e-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="e748e-115">Om företags portalen inte distribueras i din klient organisation, se [företags Portal](company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="e748e-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="e748e-116">Distribuera Project och Visio för Microsoft hanterade Station ära enheter</span><span class="sxs-lookup"><span data-stu-id="e748e-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="e748e-117">Microsoft Managed Desktop lägger till Microsoft Project och Microsoft Visio som två Win32-program i Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="e748e-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="e748e-118">Dessutom skapas två grupper i Azure Active Directory som tilldelas motsvarande program med avsikten "tillgänglig".</span><span class="sxs-lookup"><span data-stu-id="e748e-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="e748e-119">**Distribuera Project och Visio** Lägga till användaren i en lämplig grupp så blir programmet tillgänglig i företags portalen.</span><span class="sxs-lookup"><span data-stu-id="e748e-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="e748e-120">Det kan ta några minuter att synkronisera, men sedan kan användarna installera programmen från företags portalen.</span><span class="sxs-lookup"><span data-stu-id="e748e-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="e748e-121">Azure AD-gruppnamn</span><span class="sxs-lookup"><span data-stu-id="e748e-121">Azure AD Group name</span></span> | <span data-ttu-id="e748e-122">Vilka användare ska tilldelas?</span><span class="sxs-lookup"><span data-stu-id="e748e-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="e748e-123">Modern arbets plats – Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="e748e-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="e748e-124">Användare som behöver projekt</span><span class="sxs-lookup"><span data-stu-id="e748e-124">Users needing Project</span></span>
<span data-ttu-id="e748e-125">Modern arbets plats – Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="e748e-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="e748e-126">Användare som behöver Visio</span><span class="sxs-lookup"><span data-stu-id="e748e-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="e748e-127">Kommunicera ändringar</span><span class="sxs-lookup"><span data-stu-id="e748e-127">Communicate changes</span></span>
<span data-ttu-id="e748e-128">Det är viktigt för IT-administratörer att låta användarna veta hur de kan installera Project och Visio.</span><span class="sxs-lookup"><span data-stu-id="e748e-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="e748e-129">Detta inkluderar:</span><span class="sxs-lookup"><span data-stu-id="e748e-129">This includes:</span></span> 
- <span data-ttu-id="e748e-130">Meddela användarna när de är tillgängliga för dem.</span><span class="sxs-lookup"><span data-stu-id="e748e-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="e748e-131">Anvisningar för hur du installerar dessa program från företags portalen.</span><span class="sxs-lookup"><span data-stu-id="e748e-131">Instructions on how to install these applications from the Company Portal.</span></span>
