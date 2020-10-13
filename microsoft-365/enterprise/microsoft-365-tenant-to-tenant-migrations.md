---
title: Microsoft 365-migrering till klient organisation
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: Lär dig hur du migrerar Microsoft 365-innehavare.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 17aabbd945c6dec699384eb9f203029255ae62f6
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447156"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a><span data-ttu-id="ad433-103">Microsoft 365-migrering till klient organisation</span><span class="sxs-lookup"><span data-stu-id="ad433-103">Microsoft 365 tenant-to-tenant migrations</span></span>

<span data-ttu-id="ad433-104">Det finns flera arkitektur funktioner för fusioner, förvärv, divestitures och andra scenarier som kan leda till att du migrerar en befintlig Microsoft 365-klient organisation till en ny klient organisation.</span><span class="sxs-lookup"><span data-stu-id="ad433-104">There are several architecture approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> <span data-ttu-id="ad433-105">De flesta kunder kan samar beta med Microsoft Consulting Services eller en Microsoft-partner för att migrera klient organisationer, inklusive användning av verktyg från tredje part för att migrera innehåll.</span><span class="sxs-lookup"><span data-stu-id="ad433-105">Most customers work with Microsoft Consulting Services or a Microsoft partner to migrate tenants, including using third-party tools to migrate content.</span></span> 

<span data-ttu-id="ad433-106">Använd en [arkitektur modell för klient](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf) organisations klient organisation för att förstå hur du planerar för migrering av Microsoft 365-klient organisationer och stegen i en migrering.</span><span class="sxs-lookup"><span data-stu-id="ad433-106">Use the [Tenant-to-tenant migration architecture model](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf) to understand how to plan for Microsoft 365 tenant-to-tenant migrations and the steps of a migration.</span></span>

<span data-ttu-id="ad433-107">[![Användarmigrering för klient organisation](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf)</span><span class="sxs-lookup"><span data-stu-id="ad433-107">[![Tenant-to-tenant migration model](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf)</span></span> 

<span data-ttu-id="ad433-108">Du kan också ladda ned den här modellen i [PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) eller [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.vsdx) -format och skriva ut den på Letter, Legal eller Tabloid (11 x 17) pappers storlek.</span><span class="sxs-lookup"><span data-stu-id="ad433-108">You can also download this model in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) or [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.vsdx) formats and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

<span data-ttu-id="ad433-109">Den här modellen ger vägledning och en utgångs punkt för planering med avsnitt på:</span><span class="sxs-lookup"><span data-stu-id="ad433-109">This model provides guidance and a starting-point for planning with sections on:</span></span>

- <span data-ttu-id="ad433-110">Mappning av affärs scenarier till arkitektur metoder</span><span class="sxs-lookup"><span data-stu-id="ad433-110">Mapping of business scenarios to architecture approaches</span></span>
- <span data-ttu-id="ad433-111">Utformning</span><span class="sxs-lookup"><span data-stu-id="ad433-111">Design considerations</span></span>

<span data-ttu-id="ad433-112">Den här modellen innehåller också detaljerade exempel på:</span><span class="sxs-lookup"><span data-stu-id="ad433-112">This model also contains detailed examples of:</span></span>

- <span data-ttu-id="ad433-113">Ett migrerings flöde</span><span class="sxs-lookup"><span data-stu-id="ad433-113">A single event migration flow</span></span>
- <span data-ttu-id="ad433-114">Ett steg i fasen migration</span><span class="sxs-lookup"><span data-stu-id="ad433-114">A phased migration flow</span></span>
- <span data-ttu-id="ad433-115">Ett klient organisations-eller flödes schema</span><span class="sxs-lookup"><span data-stu-id="ad433-115">A tenant move or split flow</span></span>
