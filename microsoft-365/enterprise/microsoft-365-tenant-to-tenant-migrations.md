---
title: Migrering från Microsoft 365 till klientorganisation
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
description: Lär dig hur du migrerar Microsoft 365-klientorganisationen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f6e8277a7ca768db3a4a4acd2488859b7764a40c
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819720"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a><span data-ttu-id="9b607-103">Migrering från Microsoft 365 till klientorganisation</span><span class="sxs-lookup"><span data-stu-id="9b607-103">Microsoft 365 tenant-to-tenant migrations</span></span>

<span data-ttu-id="9b607-104">Det finns flera arkitekturscenarier för samgåenden, förvärv, företag och andra scenarier som kan leda till att du migrerar en befintlig Microsoft 365-klientorganisation till en ny klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="9b607-104">There are several architecture approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> <span data-ttu-id="9b607-105">De flesta kunder arbetar med Microsoft Consulting Services eller en Microsoft-partner för att migrera klientorganisationen, inklusive att använda verktyg från tredje part för att migrera innehåll.</span><span class="sxs-lookup"><span data-stu-id="9b607-105">Most customers work with Microsoft Consulting Services or a Microsoft partner to migrate tenants, including using third-party tools to migrate content.</span></span> 

<span data-ttu-id="9b607-106">Använd modellen [med migreringsarkitekturen](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) klientorganisation till klientorganisation för att förstå hur du planerar för Microsoft 365-klientorganisationens migreringar och stegen för en migrering.</span><span class="sxs-lookup"><span data-stu-id="9b607-106">Use the [Tenant-to-tenant migration architecture model](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) to understand how to plan for Microsoft 365 tenant-to-tenant migrations and the steps of a migration.</span></span>

<span data-ttu-id="9b607-107">[![Migreringsmodell för klientorganisation](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span><span class="sxs-lookup"><span data-stu-id="9b607-107">[![Tenant-to-tenant migration model](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span></span> 

<span data-ttu-id="9b607-108">Du kan ladda ned den här modellen i [PDF-format](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) och skriva ut den på papper i letter-, legal- eller tabloidstorlek (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="9b607-108">You download this model in [PDF](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) format and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

<span data-ttu-id="9b607-109">Den här modellen innehåller vägledning och en utgångspunkt för planering med avsnitt om:</span><span class="sxs-lookup"><span data-stu-id="9b607-109">This model provides guidance and a starting-point for planning with sections on:</span></span>

- <span data-ttu-id="9b607-110">Mappning av affärsscenarier till arkitektur närmar sig</span><span class="sxs-lookup"><span data-stu-id="9b607-110">Mapping of business scenarios to architecture approaches</span></span>
- <span data-ttu-id="9b607-111">Designöverväganden</span><span class="sxs-lookup"><span data-stu-id="9b607-111">Design considerations</span></span>

<span data-ttu-id="9b607-112">Den här modellen innehåller även detaljerade exempel på:</span><span class="sxs-lookup"><span data-stu-id="9b607-112">This model also contains detailed examples of:</span></span>

- <span data-ttu-id="9b607-113">Migreringsflöde för en enstaka händelse</span><span class="sxs-lookup"><span data-stu-id="9b607-113">A single event migration flow</span></span>
- <span data-ttu-id="9b607-114">Ett fasadt migreringsflöde</span><span class="sxs-lookup"><span data-stu-id="9b607-114">A phased migration flow</span></span>
- <span data-ttu-id="9b607-115">Flytta eller dela flöde för klientorganisation</span><span class="sxs-lookup"><span data-stu-id="9b607-115">A tenant move or split flow</span></span>
