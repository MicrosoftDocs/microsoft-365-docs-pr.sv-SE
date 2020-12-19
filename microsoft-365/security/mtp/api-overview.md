---
title: 'Översikt över Microsoft 365 Defender API: er'
description: 'Läs mer om tillgängliga API: er i Microsoft 365 Defender'
keywords: 'API, API: er, översikt, tillbud, tillbud, hot om, Microsoft 365 Defender'
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 1a75a561e60c05208e8ea302505f9644ac0bc044
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719196"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="76c3b-104">Översikt över Microsoft 365 Defender API: er</span><span class="sxs-lookup"><span data-stu-id="76c3b-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="76c3b-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="76c3b-105">**Applies to:**</span></span>

- <span data-ttu-id="76c3b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="76c3b-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="76c3b-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="76c3b-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="76c3b-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="76c3b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="76c3b-109">Microsoft 365 Defender är baserat på en integrations klar plattform.</span><span class="sxs-lookup"><span data-stu-id="76c3b-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="76c3b-110">Använd Microsoft 365 Defender API: er till att automatisera arbets flöden baserat på tabellerna delade incidenter och avancerade jakt.</span><span class="sxs-lookup"><span data-stu-id="76c3b-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="76c3b-111">Sammanslagen **[händelse i kö](api-incident.md)** -fokusera på vad som är kritiskt genom att gruppera hela attack omfattningen och alla aktiva till gångar tillsammans under API: t.</span><span class="sxs-lookup"><span data-stu-id="76c3b-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="76c3b-112">Stöldskydd **[mellan produkter](api-advanced-hunting.md)** – Använd din säkerhets grupps organisatoriska vetskap för att hitta inloggnings problem, genom att skapa egna anpassade frågor för att ändra rå data som samlats in över flera olika skydds produkter.</span><span class="sxs-lookup"><span data-stu-id="76c3b-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="76c3b-113">Tillsammans med dessa Microsoft 365 Defender-specifika API: er kan de andra säkerhets produkterna Visa [ytterligare API: er](api-articles.md) som hjälper dig att utnyttja deras unika funktioner.</span><span class="sxs-lookup"><span data-stu-id="76c3b-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>

## <a name="learn-more"></a><span data-ttu-id="76c3b-114">Mer information</span><span class="sxs-lookup"><span data-stu-id="76c3b-114">Learn more</span></span>

| <span data-ttu-id="76c3b-115">**Förstå hur du kommer åt API: erna**</span><span class="sxs-lookup"><span data-stu-id="76c3b-115">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="76c3b-116">Läs mer om API-kvoter och licensiering</span><span class="sxs-lookup"><span data-stu-id="76c3b-116">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="76c3b-117">Gå till API för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="76c3b-117">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="76c3b-118">**Skapa appar**</span><span class="sxs-lookup"><span data-stu-id="76c3b-118">**Build apps**</span></span> |
| [<span data-ttu-id="76c3b-119">Skapa en ' Hej världen '-App</span><span class="sxs-lookup"><span data-stu-id="76c3b-119">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="76c3b-120">Skapa en app för att få åtkomst till Microsoft 365 Defender API: er för en användares räkning</span><span class="sxs-lookup"><span data-stu-id="76c3b-120">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="76c3b-121">Skapa en app för åtkomst till Microsoft 365 Defender utan en användare</span><span class="sxs-lookup"><span data-stu-id="76c3b-121">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="76c3b-122">Skapa en app med åtkomst för flera innehavare partner till Microsoft 365 Defender API: er</span><span class="sxs-lookup"><span data-stu-id="76c3b-122">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="76c3b-123">**Felsöka och underhålla dina appar**</span><span class="sxs-lookup"><span data-stu-id="76c3b-123">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="76c3b-124">Förstå API-felkoder</span><span class="sxs-lookup"><span data-stu-id="76c3b-124">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="76c3b-125">Hantera hemligheter i dina appar med Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="76c3b-125">Manage secrets in your apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="76c3b-126">Implementera OAuth 2,0-auktorisering för användarens inloggning</span><span class="sxs-lookup"><span data-stu-id="76c3b-126">Implement OAuth 2.0 authorization for user sign in</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
