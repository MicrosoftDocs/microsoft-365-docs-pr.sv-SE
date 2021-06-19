---
title: Översikt över Microsoft 365 Defender API:er
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
ms.openlocfilehash: 2ca601c3c68df9f9f1cc4fb90bcfbe907850ce91
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029735"
---
# <a name="overview-of-microsoft-365-defender-apis"></a><span data-ttu-id="71ec1-104">Översikt över Microsoft 365 Defender API:er</span><span class="sxs-lookup"><span data-stu-id="71ec1-104">Overview of Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="71ec1-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="71ec1-105">**Applies to:**</span></span>

- <span data-ttu-id="71ec1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71ec1-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71ec1-107">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="71ec1-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="71ec1-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="71ec1-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="71ec1-109">Microsoft 365 Defender är uppbyggt på en plattform som är integrationsklar.</span><span class="sxs-lookup"><span data-stu-id="71ec1-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="71ec1-110">Använd API:Microsoft 365 Defender för att automatisera arbetsflöden baserat på delade incidenter och avancerade tabeller för sökning.</span><span class="sxs-lookup"><span data-stu-id="71ec1-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="71ec1-111">**[Kö för kombinerade incidenter](api-incident.md)** – Fokusera på vad som är viktigt genom att gruppera hela attackomfånget och alla påverkade tillgångar under incident-API:t.</span><span class="sxs-lookup"><span data-stu-id="71ec1-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="71ec1-112">**[Skydd](api-advanced-hunting.md)** mot hot för flera produkter – Använd säkerhetsteamets organisationskunskaper till att leta efter komprometterade tecken på kompromisser genom att skapa egna anpassade frågor för att gå igenom rådata som samlas in över flera skyddsprodukter.</span><span class="sxs-lookup"><span data-stu-id="71ec1-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="71ec1-113">Använd [Streaming API för](../defender-endpoint/raw-data-export.md) att skicka händelser och aviseringar i realtid från instanser när de inträffar i en enda dataström.</span><span class="sxs-lookup"><span data-stu-id="71ec1-113">Use the [Streaming API](../defender-endpoint/raw-data-export.md) to ship real-time events and alerts from instances as they occur within a single data stream.</span></span>

<span data-ttu-id="71ec1-114">Tillsammans med dessa Microsoft 365 Defender-specifika API:er visar var och en av våra andra säkerhetsprodukter ytterligare [API:er](api-articles.md) så att du kan använda deras unika funktioner.</span><span class="sxs-lookup"><span data-stu-id="71ec1-114">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="71ec1-115">Övergången till den enhetliga portalen bör inte påverka PowerBi-instrumentpanelerna baserade på Microsoft Defender för slutpunkts-API:er.</span><span class="sxs-lookup"><span data-stu-id="71ec1-115">The transition to the unified portal should not affect the PowerBi dashboards based on Microsoft Defender for Endpoint APIs.</span></span> <span data-ttu-id="71ec1-116">Du kan fortsätta att arbeta med befintliga API:er oavsett den interaktiva portalövergången.</span><span class="sxs-lookup"><span data-stu-id="71ec1-116">You can continue to work with the existing APIs regardless of the interactive portal transition.</span></span>

## <a name="learn-more"></a><span data-ttu-id="71ec1-117">Mer information</span><span class="sxs-lookup"><span data-stu-id="71ec1-117">Learn more</span></span>

| <span data-ttu-id="71ec1-118">**Förstå hur du får åtkomst till API:er**</span><span class="sxs-lookup"><span data-stu-id="71ec1-118">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="71ec1-119">Läs mer om API-kvoter och licensiering</span><span class="sxs-lookup"><span data-stu-id="71ec1-119">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="71ec1-120">Få åtkomst Microsoft 365 Defender API:er</span><span class="sxs-lookup"><span data-stu-id="71ec1-120">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="71ec1-121">**Skapa appar**</span><span class="sxs-lookup"><span data-stu-id="71ec1-121">**Build apps**</span></span> |
| [<span data-ttu-id="71ec1-122">Skapa en Hello world-app</span><span class="sxs-lookup"><span data-stu-id="71ec1-122">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="71ec1-123">Skapa ett program för att komma Microsoft 365 Defender API:er för en användares räkning</span><span class="sxs-lookup"><span data-stu-id="71ec1-123">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="71ec1-124">Skapa ett program för åtkomst Microsoft 365 Defender utan en användare</span><span class="sxs-lookup"><span data-stu-id="71ec1-124">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="71ec1-125">Skapa ett program med partner med flera klientorganisationens åtkomst Microsoft 365 Defender API:er</span><span class="sxs-lookup"><span data-stu-id="71ec1-125">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="71ec1-126">**Felsöka och underhålla dina appar**</span><span class="sxs-lookup"><span data-stu-id="71ec1-126">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="71ec1-127">Förstå API-felkoder</span><span class="sxs-lookup"><span data-stu-id="71ec1-127">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="71ec1-128">Hantera hemligheter i dina appar med Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="71ec1-128">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="71ec1-129">Implementera OAuth 2.0-auktorisering för användar logga in</span><span class="sxs-lookup"><span data-stu-id="71ec1-129">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |