---
title: Grunderna i avrop
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
description: Lär dig mer om funktionen nya avrop.
ms.openlocfilehash: 2ab8efd637bb278faf6065559cab26cb7016975b
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638237"
---
# <a name="allotment-basics"></a><span data-ttu-id="76ecb-103">Grunderna i avrop</span><span class="sxs-lookup"><span data-stu-id="76ecb-103">Allotment basics</span></span>

<span data-ttu-id="76ecb-104">Med licens avrop kan du ange licens begränsningar och delegera hanteringen av licens tilldelningen till enbart de produkter och licens gränser som du väljer.</span><span class="sxs-lookup"><span data-stu-id="76ecb-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="76ecb-105">Avrop använder gruppbaserad licensiering för att tilldela licenser till användarna.</span><span class="sxs-lookup"><span data-stu-id="76ecb-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="76ecb-106">Licens gränser ger ökad kontroll över hur många licenser som är tilldelade användarna i din grupp.</span><span class="sxs-lookup"><span data-stu-id="76ecb-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="76ecb-107">Så även när antalet användare i gruppen ökar, kan du se till att du bevaras inom licens gränsen som du har angett för avropet.</span><span class="sxs-lookup"><span data-stu-id="76ecb-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="76ecb-108">Du kan också delegera hanteringen av dina avrop.</span><span class="sxs-lookup"><span data-stu-id="76ecb-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="76ecb-109">Delegerade tilldelnings ägare får till gång till administrations centret men kan bara se och hantera licenser i de avrop de äger.</span><span class="sxs-lookup"><span data-stu-id="76ecb-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="76ecb-110">Detta ger mer detaljerad delegering av licens hantering inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="76ecb-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="76ecb-111">Krav</span><span class="sxs-lookup"><span data-stu-id="76ecb-111">Prerequisites</span></span>

<span data-ttu-id="76ecb-112">Du måste uppfylla licensierings kraven för [gruppbaserad licensiering](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="76ecb-112">You must meet the licensing requirements for [group-based licensing](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="76ecb-113">Du kan använda avrop med vilken produkt som helst som är tillgänglig för användarna:</span><span class="sxs-lookup"><span data-stu-id="76ecb-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="76ecb-114">Office-paket och fristående produkter</span><span class="sxs-lookup"><span data-stu-id="76ecb-114">Office suites and standalone products</span></span>
- <span data-ttu-id="76ecb-115">Företags-och mobilitets produkter</span><span class="sxs-lookup"><span data-stu-id="76ecb-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="76ecb-116">Dynamics 365-produkter</span><span class="sxs-lookup"><span data-stu-id="76ecb-116">Dynamics 365 products</span></span>

<span data-ttu-id="76ecb-117">Följande produkter kan inte användas med avrop:</span><span class="sxs-lookup"><span data-stu-id="76ecb-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="76ecb-118">Microsoft Store-appar</span><span class="sxs-lookup"><span data-stu-id="76ecb-118">Microsoft Store apps</span></span>
- <span data-ttu-id="76ecb-119">Beständig program vara eller program vara som tilldelats direkt till en användare om det inte finns någon licens.</span><span class="sxs-lookup"><span data-stu-id="76ecb-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="76ecb-120">Azure-resurser</span><span class="sxs-lookup"><span data-stu-id="76ecb-120">Azure resources</span></span>

<span data-ttu-id="76ecb-121">Du måste vara global eller licens administratör för att komma igång med en avrop.</span><span class="sxs-lookup"><span data-stu-id="76ecb-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="76ecb-122">Komma igång</span><span class="sxs-lookup"><span data-stu-id="76ecb-122">Getting started</span></span>

<span data-ttu-id="76ecb-123">Funktionen avrop är tillgänglig endast för ett fåtal kunder i en privat förhands granskning.</span><span class="sxs-lookup"><span data-stu-id="76ecb-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="76ecb-124">Om du är intresse rad av att gå med kan du fylla i det här formuläret: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup) .</span><span class="sxs-lookup"><span data-stu-id="76ecb-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>
