---
title: Installera Microsoft Project eller Microsoft Visio på Microsoft Hanterat skrivbord enheter
description: Information om hur du installerar Microsoft Project eller Microsoft Visio på Microsoft Hanterat skrivbord enheter
keywords: Microsoft Hanterat skrivbord, Microsoft 365, Microsoft Project, Microsoft Visio
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
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="236d8-104">Installera Microsoft Project eller Microsoft Visio på Microsoft Hanterat skrivbord enheter</span><span class="sxs-lookup"><span data-stu-id="236d8-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="236d8-105">Microsoft Project och Microsoft Visio specifika steg för installation på alla Microsoft Hanterat skrivbord enheter.</span><span class="sxs-lookup"><span data-stu-id="236d8-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="236d8-106">I det här avsnittet finns information om förutsättningarna och installationen för dessa program.</span><span class="sxs-lookup"><span data-stu-id="236d8-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="236d8-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="236d8-107">Prerequisites</span></span>

<span data-ttu-id="236d8-108">Administratörer bör kontrollera att de uppfyller följande krav:</span><span class="sxs-lookup"><span data-stu-id="236d8-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="236d8-109">**Antal licenser** – Rätt mängd licenser Microsoft Project Och Microsoft Visio vara tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="236d8-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="236d8-110">Microsoft Hanterat skrivbord för närvarande endast 64-bitarsversioner av dessa program.</span><span class="sxs-lookup"><span data-stu-id="236d8-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="236d8-111">**Licensnamn** – Rätt licensnamn för dessa program är:</span><span class="sxs-lookup"><span data-stu-id="236d8-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="236d8-112">**Microsoft Project** – Project Online Professional eller Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="236d8-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="236d8-113">**Microsoft Visio** – Visio Online, abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="236d8-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="236d8-114">**Företagsportal** – Företagsportal måste vara tillgänglig i klientorganisationen för att användarna ska kunna installera programmen.</span><span class="sxs-lookup"><span data-stu-id="236d8-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="236d8-115">Om Företagsportal inte har distribuerats i klientorganisationen kan du gå till [Företagsportal](company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="236d8-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="236d8-116">Distribuera Project och Visio för Microsoft Hanterat skrivbord enheter</span><span class="sxs-lookup"><span data-stu-id="236d8-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="236d8-117">Microsoft Hanterat skrivbord lägger till Microsoft Project och Microsoft Visio som två Win32-program i Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="236d8-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="236d8-118">Vi kommer också att skapa två grupper Azure Active Directory som tilldelas till motsvarande program med avsikten "Tillgänglig".</span><span class="sxs-lookup"><span data-stu-id="236d8-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="236d8-119">**Distribuera Project och Visio** Lägg till användaren i lämplig grupp så blir programmet tillgängligt i Företagsportal.</span><span class="sxs-lookup"><span data-stu-id="236d8-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="236d8-120">Det kan ta några minuter att synkronisera, men sedan kan användarna installera apparna från Företagsportal.</span><span class="sxs-lookup"><span data-stu-id="236d8-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="236d8-121">Azure AD-gruppnamn</span><span class="sxs-lookup"><span data-stu-id="236d8-121">Azure AD Group name</span></span> | <span data-ttu-id="236d8-122">Vilka användare ska tilldelas?</span><span class="sxs-lookup"><span data-stu-id="236d8-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="236d8-123">Modern workplace-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="236d8-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="236d8-124">Användare som behöver Project</span><span class="sxs-lookup"><span data-stu-id="236d8-124">Users needing Project</span></span>
<span data-ttu-id="236d8-125">Modern workplace-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="236d8-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="236d8-126">Användare som behöver Visio</span><span class="sxs-lookup"><span data-stu-id="236d8-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="236d8-127">Informera om ändringar</span><span class="sxs-lookup"><span data-stu-id="236d8-127">Communicate changes</span></span>
<span data-ttu-id="236d8-128">It's important for IT administrators to let their users know how to install Project and Visio.</span><span class="sxs-lookup"><span data-stu-id="236d8-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="236d8-129">Detta omfattar följande:</span><span class="sxs-lookup"><span data-stu-id="236d8-129">This includes:</span></span> 
- <span data-ttu-id="236d8-130">Meddela användare när dessa program är tillgängliga för dem.</span><span class="sxs-lookup"><span data-stu-id="236d8-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="236d8-131">Anvisningar om hur du installerar programmen från Företagsportal.</span><span class="sxs-lookup"><span data-stu-id="236d8-131">Instructions on how to install these applications from the Company Portal.</span></span>
