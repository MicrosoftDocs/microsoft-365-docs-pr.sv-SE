---
title: Migreringar från Microsoft 365 till klientorganisation
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
ms.openlocfilehash: 09b2bc77333afaf1991064369846241328db85ff
ms.sourcegitcommit: a7d1b29a024b942c7d0d8f5fb9b5bb98a0036b68
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461649"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a><span data-ttu-id="6e959-103">Migreringar från Microsoft 365 till klientorganisation</span><span class="sxs-lookup"><span data-stu-id="6e959-103">Microsoft 365 tenant-to-tenant migrations</span></span>

<span data-ttu-id="6e959-104">Det finns flera arkitekturstrategier för sammanslagningar, förvärv, divestitures och andra scenarier som kan leda till att du migrerar en befintlig Microsoft 365-klientorganisation till en ny klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="6e959-104">There are several architecture approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> <span data-ttu-id="6e959-105">De flesta kunder arbetar med Microsoft Consulting Services eller en Microsoft-partner för att migrera klientorganisationen, inklusive att använda verktyg från tredje part för att migrera innehåll.</span><span class="sxs-lookup"><span data-stu-id="6e959-105">Most customers work with Microsoft Consulting Services or a Microsoft partner to migrate tenants, including using third-party tools to migrate content.</span></span> 

<span data-ttu-id="6e959-106">Använd modellen [med](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) migreringsarkitekturen klient till klientorganisation för att förstå hur du planerar för Microsoft 365-migreringar mellan klientorganisation och stegen för en migrering.</span><span class="sxs-lookup"><span data-stu-id="6e959-106">Use the [Tenant-to-tenant migration architecture model](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) to understand how to plan for Microsoft 365 tenant-to-tenant migrations and the steps of a migration.</span></span>

<span data-ttu-id="6e959-107">[![Migreringsmodell för klientorganisation till klientorganisation](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span><span class="sxs-lookup"><span data-stu-id="6e959-107">[![Tenant-to-tenant migration model](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span></span> 

<span data-ttu-id="6e959-108">Du laddar ned den här modellen i [PDF-format](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) och skriver ut den på papper i letter-, legal- eller tabloidformat (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="6e959-108">You download this model in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) format and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

<span data-ttu-id="6e959-109">Den här modellen innehåller vägledning och en utgångspunkt för planering med avsnitt om:</span><span class="sxs-lookup"><span data-stu-id="6e959-109">This model provides guidance and a starting-point for planning with sections on:</span></span>

- <span data-ttu-id="6e959-110">Mappning av affärsscenarier till arkitekturstrategier</span><span class="sxs-lookup"><span data-stu-id="6e959-110">Mapping of business scenarios to architecture approaches</span></span>
- <span data-ttu-id="6e959-111">Designöverväganden</span><span class="sxs-lookup"><span data-stu-id="6e959-111">Design considerations</span></span>

<span data-ttu-id="6e959-112">Den här modellen innehåller också detaljerade exempel på:</span><span class="sxs-lookup"><span data-stu-id="6e959-112">This model also contains detailed examples of:</span></span>

- <span data-ttu-id="6e959-113">Ett migreringsflöde för en händelse</span><span class="sxs-lookup"><span data-stu-id="6e959-113">A single event migration flow</span></span>
- <span data-ttu-id="6e959-114">Ett fasadt migreringsflöde</span><span class="sxs-lookup"><span data-stu-id="6e959-114">A phased migration flow</span></span>
- <span data-ttu-id="6e959-115">Ett flyttnings- eller delningsflöde för klientorganisation</span><span class="sxs-lookup"><span data-stu-id="6e959-115">A tenant move or split flow</span></span>
