---
title: Grunderna för tilldelning
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
description: Läs mer om funktionen nya tilldelningar.
ms.openlocfilehash: 22f7c35b1a5baf97fb72f541d57da28adeeffbe4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812617"
---
# <a name="allotment-basics"></a><span data-ttu-id="c8b7b-103">Grunderna för tilldelning</span><span class="sxs-lookup"><span data-stu-id="c8b7b-103">Allotment basics</span></span>

<span data-ttu-id="c8b7b-104">Med licenstilldelningar kan du ange licensgränser och delegera hantering av licenstilldelning till endast de produkter och licensgränser som du väljer.</span><span class="sxs-lookup"><span data-stu-id="c8b7b-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="c8b7b-105">Tilldelningar använder gruppbaserad licensiering för att tilldela licenser till dina användare.</span><span class="sxs-lookup"><span data-stu-id="c8b7b-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="c8b7b-106">Licensgränser ger ökad kontroll över hur många licenser som tilldelas användarna i dina grupper.</span><span class="sxs-lookup"><span data-stu-id="c8b7b-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="c8b7b-107">Så även när antalet användare i dina grupper ökar kan du se till att du håller dig inom den licensgräns som du har angett för din tilldelning.</span><span class="sxs-lookup"><span data-stu-id="c8b7b-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="c8b7b-108">Du kan också delegera hanteringen av dina tilldelningar.</span><span class="sxs-lookup"><span data-stu-id="c8b7b-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="c8b7b-109">Delegerade tilldelningsägare får åtkomst till administrationscentret, men kan bara se och hantera licenserna i de tilldelningar de äger.</span><span class="sxs-lookup"><span data-stu-id="c8b7b-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="c8b7b-110">Detta ger mer detaljerad delegering av licenshantering inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="c8b7b-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c8b7b-111">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="c8b7b-111">Prerequisites</span></span>

<span data-ttu-id="c8b7b-112">Du måste uppfylla licenskraven för [gruppbaserad licensiering.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="c8b7b-112">You must meet the licensing requirements for [group-based licensing](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="c8b7b-113">Du kan använda tilldelningar med valfri Office 365-produkt som är tillgänglig för användare:</span><span class="sxs-lookup"><span data-stu-id="c8b7b-113">You can use allotments with any Office 365 product available to users:</span></span>

- <span data-ttu-id="c8b7b-114">Office-sviter och fristående produkter</span><span class="sxs-lookup"><span data-stu-id="c8b7b-114">Office suites and standalone products</span></span>
- <span data-ttu-id="c8b7b-115">Produkter inom företags- och mobilitet</span><span class="sxs-lookup"><span data-stu-id="c8b7b-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="c8b7b-116">Dynamics 365 produkter</span><span class="sxs-lookup"><span data-stu-id="c8b7b-116">Dynamics 365 products</span></span>

<span data-ttu-id="c8b7b-117">Följande produkter kan inte användas med tilldelningar:</span><span class="sxs-lookup"><span data-stu-id="c8b7b-117">The following products can’t be used with allotments:</span></span>

- <span data-ttu-id="c8b7b-118">Microsoft Store-appar</span><span class="sxs-lookup"><span data-stu-id="c8b7b-118">Microsoft Store apps</span></span>
- <span data-ttu-id="c8b7b-119">Evig programvara eller programvara som är direkt tilldelad en användare om det inte finns någon licens inblandad.</span><span class="sxs-lookup"><span data-stu-id="c8b7b-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="c8b7b-120">Azure-resurser</span><span class="sxs-lookup"><span data-stu-id="c8b7b-120">Azure resources</span></span>

<span data-ttu-id="c8b7b-121">Du måste vara en global administratör eller licensadministratör för att komma igång med en tilldelning.</span><span class="sxs-lookup"><span data-stu-id="c8b7b-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="c8b7b-122">Komma igång</span><span class="sxs-lookup"><span data-stu-id="c8b7b-122">Getting started</span></span>

<span data-ttu-id="c8b7b-123">Funktionen för tilldelningar är tillgänglig i en privat förhandsgranskning för endast ett litet antal kunder.</span><span class="sxs-lookup"><span data-stu-id="c8b7b-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="c8b7b-124">Om du är intresserad av att gå [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup)med fyller du i det här formuläret: .</span><span class="sxs-lookup"><span data-stu-id="c8b7b-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>
