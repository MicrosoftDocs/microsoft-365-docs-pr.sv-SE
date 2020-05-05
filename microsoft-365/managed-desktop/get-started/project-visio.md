---
title: Installera Microsoft Project eller Microsoft Visio på Microsoft Managed Desktop-enheter
description: Information om hur du installerar Microsoft Project eller Microsoft Visio på Microsoft Managed Desktop-enheter
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 450dbcb08cd0636dae575ecd2d5e9abadc5ceb25
ms.sourcegitcommit: 44e685a0b193e89de5befb1e1a3740eb31931799
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44022102"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="b309f-104">Installera Microsoft Project eller Microsoft Visio på Microsoft Managed Desktop-enheter</span><span class="sxs-lookup"><span data-stu-id="b309f-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="b309f-105">Microsoft Project och Microsoft Visio kräver att specifika steg installeras på Microsoft Managed Desktop-enheter.</span><span class="sxs-lookup"><span data-stu-id="b309f-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b309f-106">Det här avsnittet dokumenterar förutsättningarna och installationsprocessen för dessa program.</span><span class="sxs-lookup"><span data-stu-id="b309f-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b309f-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="b309f-107">Prerequisites</span></span>

<span data-ttu-id="b309f-108">Administratörer bör kontrollera att de uppfyller dessa förutsättningar:</span><span class="sxs-lookup"><span data-stu-id="b309f-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="b309f-109">**Licenskvantiteter** – Rätt mängd Microsoft Project- och Microsoft Visio-licenser måste vara tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="b309f-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="b309f-110">Microsoft Managed Desktop stöder för närvarande endast 64-bitarsversioner av dessa program.</span><span class="sxs-lookup"><span data-stu-id="b309f-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="b309f-111">**Licensnamn** - Lämpliga licensnamn för dessa program är:</span><span class="sxs-lookup"><span data-stu-id="b309f-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="b309f-112">**Microsoft Project** – Project Online Professional eller Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="b309f-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="b309f-113">**Microsoft Visio** - Visio Online Plan 2</span><span class="sxs-lookup"><span data-stu-id="b309f-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="b309f-114">**Företagsportal** - Företagsportalen måste vara tillgänglig i din klientorganisation för att användarna ska kunna installera dessa program.</span><span class="sxs-lookup"><span data-stu-id="b309f-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="b309f-115">Om företagsportalen inte distribueras i din klientorganisation läser du [Företagsportalen](company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="b309f-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="b309f-116">Distribuera Project och Visio för Microsoft Managed Desktop-enheter</span><span class="sxs-lookup"><span data-stu-id="b309f-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="b309f-117">När du har skickat in din supportbegäran skapar Microsoft Managed Desktop tre Azure AD-grupper och tre programdistributioner via Microsoft Intune för att distribuera apparna till din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="b309f-117">After you submit your support request, Microsoft Managed Desktop will create three Azure AD groups and three application deployments through Microsoft Intune to deploy the apps to your tenant.</span></span>  

<span data-ttu-id="b309f-118">**Så här distribuerar du Project och Visio**</span><span class="sxs-lookup"><span data-stu-id="b309f-118">**To deploy Project and Visio**</span></span>
1. <span data-ttu-id="b309f-119">**Lämna in en supportbegäran** IT-administratörer måste lämna in en supportbegäran för att göra dessa program tillgängliga för sina användare.</span><span class="sxs-lookup"><span data-stu-id="b309f-119">**File a support request** IT administrators need to file a support request to make these applications available their users.</span></span> <span data-ttu-id="b309f-120">Information om hur du kontaktar Microsoft Managed Desktop finns i [Administratörsstöd för Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span><span class="sxs-lookup"><span data-stu-id="b309f-120">For information on contacting Microsoft Managed Desktop, see [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span></span>
2. <span data-ttu-id="b309f-121">**Tilldela användare till nya Azure AD-grupper** Microsoft Managed Desktop skapar 3 Azure AD-grupper i din klientorganisation och 3 motsvarande programdistributioner.</span><span class="sxs-lookup"><span data-stu-id="b309f-121">**Assign users to new Azure AD groups** Microsoft Managed Desktop will create 3 Azure AD groups in your tenant and 3 corresponding application deployments.</span></span> <span data-ttu-id="b309f-122">IT-administratörer måste tilldela användarna till lämpliga grupper.</span><span class="sxs-lookup"><span data-stu-id="b309f-122">IT admins need to assign the users to the appropriate groups.</span></span>

>[!NOTE]
><span data-ttu-id="b309f-123">Tilldela användare till endast en av dessa Azure AD-grupper.</span><span class="sxs-lookup"><span data-stu-id="b309f-123">Assign users to only one of these Azure AD groups.</span></span> 

<span data-ttu-id="b309f-124">Namn på Azure AD-grupp</span><span class="sxs-lookup"><span data-stu-id="b309f-124">Azure AD Group name</span></span> | <span data-ttu-id="b309f-125">Vilka användare ska tilldela?</span><span class="sxs-lookup"><span data-stu-id="b309f-125">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="b309f-126">Moderna arbetsplats-office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="b309f-126">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="b309f-127">Användare som behöver Project</span><span class="sxs-lookup"><span data-stu-id="b309f-127">Users needing Project</span></span>
<span data-ttu-id="b309f-128">Moderna arbetsplats-office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="b309f-128">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="b309f-129">Användare som behöver Visio</span><span class="sxs-lookup"><span data-stu-id="b309f-129">Users needing Visio</span></span>

<span data-ttu-id="b309f-130">När de har tilldelats dessa grupper kommer program att vara tillgängliga i företagsportalen.</span><span class="sxs-lookup"><span data-stu-id="b309f-130">Once assigned to these groups, applications will be available in the Company Portal.</span></span> <span data-ttu-id="b309f-131">Det kan ta några minuter att synkronisera, men sedan kan användarna installera apparna från Företagsportalen.</span><span class="sxs-lookup"><span data-stu-id="b309f-131">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

## <a name="communicate-changes"></a><span data-ttu-id="b309f-132">Kommunicera ändringar</span><span class="sxs-lookup"><span data-stu-id="b309f-132">Communicate changes</span></span>
<span data-ttu-id="b309f-133">Det är viktigt för IT-administratörer att låta sina användare veta hur de installerar Project och Visio.</span><span class="sxs-lookup"><span data-stu-id="b309f-133">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="b309f-134">Detta inkluderar:</span><span class="sxs-lookup"><span data-stu-id="b309f-134">This includes:</span></span> 
- <span data-ttu-id="b309f-135">Meddela användarna när dessa program är tillgängliga för dem.</span><span class="sxs-lookup"><span data-stu-id="b309f-135">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="b309f-136">Instruktioner om hur du installerar dessa program från företagsportalen.</span><span class="sxs-lookup"><span data-stu-id="b309f-136">Instructions on how to install these applications from the Company Portal.</span></span>

>[!NOTE]
><span data-ttu-id="b309f-137">Användare måste stänga alla Office-program innan de installerar Microsoft Project eller Microsoft Visio från Företagsportalen.</span><span class="sxs-lookup"><span data-stu-id="b309f-137">Users must close all Office applications before installing Microsoft Project or Microsoft Visio from Company Portal.</span></span> 
