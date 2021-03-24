---
title: Översikt över Microsoft 365 Defender-API:er
description: Läs mer om tillgängliga API:er i Microsoft 365 Defender
keywords: api, apis, översikt, incident, incidenter, hotsökning, microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 14553f3891fd81a672b62fa0575f6c253fbb0224
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068977"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="36740-104">Översikt över Microsoft 365 Defender-API:er</span><span class="sxs-lookup"><span data-stu-id="36740-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="36740-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="36740-105">**Applies to:**</span></span>

- <span data-ttu-id="36740-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36740-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36740-107">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="36740-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="36740-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="36740-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="36740-109">Microsoft 365 Defender är byggt på en plattform som är integrationsklar.</span><span class="sxs-lookup"><span data-stu-id="36740-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="36740-110">Använd Microsoft 365 Defender-API:er för att automatisera arbetsflöden baserat på delade tabeller för incidenter och avancerad sökning.</span><span class="sxs-lookup"><span data-stu-id="36740-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="36740-111">**[Kö för kombinerade incidenter](api-incident.md)** – Fokusera på vad som är viktigt genom att gruppera hela attackomfånget och alla påverkade tillgångar under incident-API:t.</span><span class="sxs-lookup"><span data-stu-id="36740-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="36740-112">**[Skydd](api-advanced-hunting.md)** mot hot för flera produkter – Använd säkerhetsteamets organisationskunskaper till att leta efter komprometterade tecken på kompromisser genom att skapa egna anpassade frågor för att gå igenom rådata som samlas in över flera skyddsprodukter.</span><span class="sxs-lookup"><span data-stu-id="36740-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="36740-113">Tillsammans med dessa Microsoft 365 Defender-specifika API:er visar var och en av våra andra säkerhetsprodukter ytterligare [API:er](api-articles.md) så att du kan använda deras unika funktioner.</span><span class="sxs-lookup"><span data-stu-id="36740-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>

## <a name="learn-more"></a><span data-ttu-id="36740-114">Mer information</span><span class="sxs-lookup"><span data-stu-id="36740-114">Learn more</span></span>

| <span data-ttu-id="36740-115">**Förstå hur du får åtkomst till API:er**</span><span class="sxs-lookup"><span data-stu-id="36740-115">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="36740-116">Läs mer om API-kvoter och licensiering</span><span class="sxs-lookup"><span data-stu-id="36740-116">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="36740-117">Åtkomst till Microsoft 365 Defender-API:er</span><span class="sxs-lookup"><span data-stu-id="36740-117">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="36740-118">**Skapa appar**</span><span class="sxs-lookup"><span data-stu-id="36740-118">**Build apps**</span></span> |
| [<span data-ttu-id="36740-119">Skapa en Hello world-app</span><span class="sxs-lookup"><span data-stu-id="36740-119">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="36740-120">Skapa en app för åtkomst till Microsoft 365 Defender-API:er för en användares räkning</span><span class="sxs-lookup"><span data-stu-id="36740-120">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="36740-121">Skapa en app för att komma åt Microsoft 365 Defender utan en användare</span><span class="sxs-lookup"><span data-stu-id="36740-121">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="36740-122">Skapa en app med partner med flera klientorganisationens åtkomst till Microsoft 365 Defender-API:er</span><span class="sxs-lookup"><span data-stu-id="36740-122">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="36740-123">**Felsöka och underhålla dina appar**</span><span class="sxs-lookup"><span data-stu-id="36740-123">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="36740-124">Förstå API-felkoder</span><span class="sxs-lookup"><span data-stu-id="36740-124">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="36740-125">Hantera hemligheter i dina appar med Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="36740-125">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="36740-126">Implementera OAuth 2.0-auktorisering för användar logga in</span><span class="sxs-lookup"><span data-stu-id="36740-126">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |