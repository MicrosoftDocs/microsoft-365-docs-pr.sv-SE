---
title: Installera Microsoft Project eller Microsoft Visio på Microsoft Managed Desktop-enheter
description: Information om hur du installerar Microsoft Project eller Microsoft Visio på Microsoft Managed Desktop-enheter
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c8690db17c71fd5ce604fd9165fee7e54a41c639
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126833"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="fcb4a-104">Installera Microsoft Project eller Microsoft Visio på Microsoft Managed Desktop-enheter</span><span class="sxs-lookup"><span data-stu-id="fcb4a-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="fcb4a-105">Microsoft Project och Microsoft Visio kräver att specifika steg installeras på Microsoft Managed Desktop-enheter.</span><span class="sxs-lookup"><span data-stu-id="fcb4a-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fcb4a-106">Det här avsnittet dokumenterar förutsättningarna och installationsprocessen för dessa program.</span><span class="sxs-lookup"><span data-stu-id="fcb4a-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fcb4a-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="fcb4a-107">Prerequisites</span></span>

<span data-ttu-id="fcb4a-108">Administratörer bör kontrollera att de uppfyller dessa förutsättningar:</span><span class="sxs-lookup"><span data-stu-id="fcb4a-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="fcb4a-109">**Licenskvantiteter** – Rätt mängd Microsoft Project- och Microsoft Visio-licenser måste vara tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="fcb4a-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="fcb4a-110">Microsoft Managed Desktop stöder för närvarande endast 64-bitarsversioner av dessa program.</span><span class="sxs-lookup"><span data-stu-id="fcb4a-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="fcb4a-111">**Licensnamn** - Lämpliga licensnamn för dessa program är:</span><span class="sxs-lookup"><span data-stu-id="fcb4a-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="fcb4a-112">**Microsoft Project** – Project Online Professional eller Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="fcb4a-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="fcb4a-113">**Microsoft Visio** - Visio Online Plan 2</span><span class="sxs-lookup"><span data-stu-id="fcb4a-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="fcb4a-114">**Företagsportal** - Företagsportalen måste vara tillgänglig i din klientorganisation för att användarna ska kunna installera dessa program.</span><span class="sxs-lookup"><span data-stu-id="fcb4a-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="fcb4a-115">Om företagsportalen inte distribueras i din klientorganisation läser du [Företagsportalen](company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="fcb4a-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="fcb4a-116">Distribuera Project och Visio för Microsoft Managed Desktop-enheter</span><span class="sxs-lookup"><span data-stu-id="fcb4a-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="fcb4a-117">Microsoft Managed Desktop lägger till Microsoft Project och Microsoft Visio som två Win32-program i Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="fcb4a-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="fcb4a-118">Vi kommer också att skapa två grupper i Azure Active Directory som kommer att tilldelas motsvarande program med avsikten "Tillgänglig".</span><span class="sxs-lookup"><span data-stu-id="fcb4a-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="fcb4a-119">**Så här distribuerar du Project och Visio** Lägg till användaren i lämplig grupp så blir programmet tillgängligt i företagsportalen.</span><span class="sxs-lookup"><span data-stu-id="fcb4a-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="fcb4a-120">Det kan ta några minuter att synkronisera, men sedan kan användarna installera apparna från Företagsportalen.</span><span class="sxs-lookup"><span data-stu-id="fcb4a-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="fcb4a-121">Namn på Azure AD-grupp</span><span class="sxs-lookup"><span data-stu-id="fcb4a-121">Azure AD Group name</span></span> | <span data-ttu-id="fcb4a-122">Vilka användare ska tilldela?</span><span class="sxs-lookup"><span data-stu-id="fcb4a-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="fcb4a-123">Moderna arbetsplats-office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="fcb4a-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="fcb4a-124">Användare som behöver Project</span><span class="sxs-lookup"><span data-stu-id="fcb4a-124">Users needing Project</span></span>
<span data-ttu-id="fcb4a-125">Moderna arbetsplats-office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="fcb4a-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="fcb4a-126">Användare som behöver Visio</span><span class="sxs-lookup"><span data-stu-id="fcb4a-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="fcb4a-127">Kommunicera ändringar</span><span class="sxs-lookup"><span data-stu-id="fcb4a-127">Communicate changes</span></span>
<span data-ttu-id="fcb4a-128">Det är viktigt för IT-administratörer att låta sina användare veta hur de installerar Project och Visio.</span><span class="sxs-lookup"><span data-stu-id="fcb4a-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="fcb4a-129">Detta inkluderar:</span><span class="sxs-lookup"><span data-stu-id="fcb4a-129">This includes:</span></span> 
- <span data-ttu-id="fcb4a-130">Meddela användarna när dessa program är tillgängliga för dem.</span><span class="sxs-lookup"><span data-stu-id="fcb4a-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="fcb4a-131">Instruktioner om hur du installerar dessa program från företagsportalen.</span><span class="sxs-lookup"><span data-stu-id="fcb4a-131">Instructions on how to install these applications from the Company Portal.</span></span>
