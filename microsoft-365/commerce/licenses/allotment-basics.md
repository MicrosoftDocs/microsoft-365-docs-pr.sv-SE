---
title: Grunderna i tilldelning
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- commerce
ms.custom: ''
description: Läs mer om den nya kolonilotter funktionen.
ms.openlocfilehash: d1f926165678b57ec46195d525f2fcdaa6976501
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632419"
---
# <a name="allotment-basics"></a><span data-ttu-id="72a63-103">Grunderna i tilldelning</span><span class="sxs-lookup"><span data-stu-id="72a63-103">Allotment basics</span></span>

<span data-ttu-id="72a63-104">Med licenstilldelningar kan du ange licensgränser och delegera hanteringen av licenstilldelning till endast de produkter och licensgränser som du väljer.</span><span class="sxs-lookup"><span data-stu-id="72a63-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="72a63-105">Avrop använder gruppbaserad licensiering för att tilldela licenser till dina användare.</span><span class="sxs-lookup"><span data-stu-id="72a63-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="72a63-106">Licensgränser ger ytterligare kontroll över hur många licenser som tilldelas användarna i dina grupper.</span><span class="sxs-lookup"><span data-stu-id="72a63-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="72a63-107">Så även när antalet användare i dina grupper ökar, kan du se till att du håller dig inom licensgränsen som du har angett för din tilldelning.</span><span class="sxs-lookup"><span data-stu-id="72a63-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="72a63-108">Du kan också delegera hanteringen av dina tilldelningar.</span><span class="sxs-lookup"><span data-stu-id="72a63-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="72a63-109">Delegerade tilldelningsägare får tillgång till administrationscentret, men kan bara se och hantera licenserna i de kolonilotter de äger.</span><span class="sxs-lookup"><span data-stu-id="72a63-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="72a63-110">Detta ger mer detaljerad delegering av licenshantering inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="72a63-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="72a63-111">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="72a63-111">Prerequisites</span></span>

<span data-ttu-id="72a63-112">Du måste uppfylla licenskraven för [gruppbaserad licensiering](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="72a63-112">You must meet the licensing requirements for [group-based licensing](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="72a63-113">Du kan använda avrop med valfri produkt som är tillgänglig för användare:</span><span class="sxs-lookup"><span data-stu-id="72a63-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="72a63-114">Office-paket och fristående produkter</span><span class="sxs-lookup"><span data-stu-id="72a63-114">Office suites and standalone products</span></span>
- <span data-ttu-id="72a63-115">Produkter för företag och mobilitet</span><span class="sxs-lookup"><span data-stu-id="72a63-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="72a63-116">Dynamics 365-produkter</span><span class="sxs-lookup"><span data-stu-id="72a63-116">Dynamics 365 products</span></span>

<span data-ttu-id="72a63-117">Följande produkter kan inte användas med tilldelningar:</span><span class="sxs-lookup"><span data-stu-id="72a63-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="72a63-118">Microsoft Store-appar</span><span class="sxs-lookup"><span data-stu-id="72a63-118">Microsoft Store apps</span></span>
- <span data-ttu-id="72a63-119">Evig programvara eller programvara som är direkt tilldelad en användare om det inte finns någon licens inblandad.</span><span class="sxs-lookup"><span data-stu-id="72a63-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="72a63-120">Azure-resurser</span><span class="sxs-lookup"><span data-stu-id="72a63-120">Azure resources</span></span>

<span data-ttu-id="72a63-121">Du måste vara global administratör eller licensadministratör för att komma igång med en tilldelning.</span><span class="sxs-lookup"><span data-stu-id="72a63-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="72a63-122">Komma igång</span><span class="sxs-lookup"><span data-stu-id="72a63-122">Getting started</span></span>

<span data-ttu-id="72a63-123">Tilldelningsfunktionen är tillgänglig i en privat förhandsversion för endast ett litet antal kunder.</span><span class="sxs-lookup"><span data-stu-id="72a63-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="72a63-124">Om du är intresserad av att gå [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup)med, fyll i det här formuläret: .</span><span class="sxs-lookup"><span data-stu-id="72a63-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>
