---
title: Grunderna om tilldelning
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: ''
ms.custom:
- commerce_licensing
description: Läs mer om den nya funktionen för tilldelningar.
ms.date: 03/17/2021
ms.openlocfilehash: 949e06d4bf54405e0045f8c7512a04b1b5cc22c0
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327136"
---
# <a name="allotment-basics"></a><span data-ttu-id="90e31-103">Grunderna om tilldelning</span><span class="sxs-lookup"><span data-stu-id="90e31-103">Allotment basics</span></span>

<span data-ttu-id="90e31-104">Licenstilldelningar låter dig ange licensbegränsningar och delegera hanteringen av licenstilldelningen till endast de produkter och licensbegränsningar som du väljer.</span><span class="sxs-lookup"><span data-stu-id="90e31-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="90e31-105">Tilldelningar använder gruppbaserad licensiering för att tilldela licenser till användarna.</span><span class="sxs-lookup"><span data-stu-id="90e31-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="90e31-106">Licensbegränsningar ger ytterligare kontroll över hur många licenser som tilldelas användarna i grupperna.</span><span class="sxs-lookup"><span data-stu-id="90e31-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="90e31-107">Så även när antalet användare i dina grupper ökar kan du se till att du håller dig inom den licensgräns som du har angett för din tilldelning.</span><span class="sxs-lookup"><span data-stu-id="90e31-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="90e31-108">Du kan också delegera hanteringen av dina ombud.</span><span class="sxs-lookup"><span data-stu-id="90e31-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="90e31-109">Delegerade ägare till tilldelning får åtkomst till administrationscentret, men kan bara se och hantera licenserna i de licenser de äger.</span><span class="sxs-lookup"><span data-stu-id="90e31-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="90e31-110">Det ger mer detaljerad delegering av licenshantering inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="90e31-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="90e31-111">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="90e31-111">Prerequisites</span></span>

<span data-ttu-id="90e31-112">Du måste uppfylla licenskraven för [gruppbaserad licensiering.](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="90e31-112">You must meet the licensing requirements for [group-based licensing](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="90e31-113">Du kan använda tilldelningar med valfri produkt som är tillgänglig för användare:</span><span class="sxs-lookup"><span data-stu-id="90e31-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="90e31-114">Office-paket och fristående produkter</span><span class="sxs-lookup"><span data-stu-id="90e31-114">Office suites and standalone products</span></span>
- <span data-ttu-id="90e31-115">Enterprise- och Mobility-produkter</span><span class="sxs-lookup"><span data-stu-id="90e31-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="90e31-116">Dynamics 365-produkter</span><span class="sxs-lookup"><span data-stu-id="90e31-116">Dynamics 365 products</span></span>

<span data-ttu-id="90e31-117">Följande produkter kan inte användas med alternativ:</span><span class="sxs-lookup"><span data-stu-id="90e31-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="90e31-118">Microsoft Store-appar</span><span class="sxs-lookup"><span data-stu-id="90e31-118">Microsoft Store apps</span></span>
- <span data-ttu-id="90e31-119">Evig programvara eller programvara som tilldelas direkt till en användare om ingen licens ingår.</span><span class="sxs-lookup"><span data-stu-id="90e31-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="90e31-120">Azure-resurser</span><span class="sxs-lookup"><span data-stu-id="90e31-120">Azure resources</span></span>

<span data-ttu-id="90e31-121">Du måste vara global administratör eller licensadministratör för att komma igång med en tilldelning.</span><span class="sxs-lookup"><span data-stu-id="90e31-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="90e31-122">Komma igång</span><span class="sxs-lookup"><span data-stu-id="90e31-122">Getting started</span></span>

<span data-ttu-id="90e31-123">Funktionen för tilldelningar är tillgänglig i en privat förhandsgranskning för bara ett litet antal kunder.</span><span class="sxs-lookup"><span data-stu-id="90e31-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="90e31-124">Om du är intresserad av att ansluta kan du fylla i följande formulär: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup) .</span><span class="sxs-lookup"><span data-stu-id="90e31-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>