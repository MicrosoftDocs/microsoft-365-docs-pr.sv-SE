---
title: Microsoft 365 att hantera skadade data
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: I den här artikeln förklaras datafel i Microsoft 365 och ansträngningar från Microsoft för att förhindra och återställa data.
ms.openlocfilehash: fabecf8e368813e2f895669edc19c3f74e305c35
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694507"
---
# <a name="dealing-with-data-corruption-in-microsoft-365"></a><span data-ttu-id="69609-103">Hantera datafel i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="69609-103">Dealing with Data Corruption in Microsoft 365</span></span>

<span data-ttu-id="69609-104">En av de utmanande aspekterna att köra en storskalig moln tjänst är att hantera datafel, med den stora volymen av data och oberoende system.</span><span class="sxs-lookup"><span data-stu-id="69609-104">One of the challenging aspects of running a large-scale cloud service is how to handle data corruption, given the large volume of data and independent systems.</span></span> <span data-ttu-id="69609-105">Datafel kan orsakas av:</span><span class="sxs-lookup"><span data-stu-id="69609-105">Data corruption can be caused by:</span></span>

- <span data-ttu-id="69609-106">Program eller infrastruktur program fel, skada vissa eller hela programmets tillstånd</span><span class="sxs-lookup"><span data-stu-id="69609-106">Application or infrastructure bugs, corrupting some or all of the application state</span></span>
- <span data-ttu-id="69609-107">Problem med maskin vara som ger förlust av data eller omöjligt att läsa data</span><span class="sxs-lookup"><span data-stu-id="69609-107">Hardware issues that result in lost data or an inability to read data</span></span>
- <span data-ttu-id="69609-108">Funktions fel för människa</span><span class="sxs-lookup"><span data-stu-id="69609-108">Human operational errors</span></span>
- <span data-ttu-id="69609-109">Illasinnade hackare och Disgruntled anställda</span><span class="sxs-lookup"><span data-stu-id="69609-109">Malicious hackers and disgruntled employees</span></span>
- <span data-ttu-id="69609-110">Incidenter i externa tjänster som medför förlust av data</span><span class="sxs-lookup"><span data-stu-id="69609-110">Incidents in external services that result in some loss of data</span></span>

<span data-ttu-id="69609-111">Eftersom större återhämtning i data integritet innebär färre incidenter för datafel är det möjligt att Microsoft 365 har funktioner för att förhindra korruption från att fungera, samt system och processer som gör att vi kan återställa data om det gör det.</span><span class="sxs-lookup"><span data-stu-id="69609-111">Because greater resiliency in data integrity means fewer data corruption incidents, Microsoft has built into Microsoft 365 protection mechanisms to prevent corruption from happening, as well as systems and processes that enable us to recover data if it does.</span></span> <span data-ttu-id="69609-112">Det finns kontroller och processer i de olika stegen i tekniska släpp processen för att öka återhämtning mot skadade data, inklusive:</span><span class="sxs-lookup"><span data-stu-id="69609-112">Checks and processes exist within the various stages of the engineering release process to increase resiliency against data corruption, including:</span></span>

- <span data-ttu-id="69609-113">System design</span><span class="sxs-lookup"><span data-stu-id="69609-113">System Design</span></span>
- <span data-ttu-id="69609-114">Kod organisation och struktur</span><span class="sxs-lookup"><span data-stu-id="69609-114">Code organization and structure</span></span>
- <span data-ttu-id="69609-115">Kod granskning</span><span class="sxs-lookup"><span data-stu-id="69609-115">Code review</span></span>
- <span data-ttu-id="69609-116">Enhets test, integrerings test och systemtest</span><span class="sxs-lookup"><span data-stu-id="69609-116">Unit tests, integration tests, and system tests</span></span>
- <span data-ttu-id="69609-117">Test/portar för rese kablar</span><span class="sxs-lookup"><span data-stu-id="69609-117">Trip wires tests/gates</span></span>

<span data-ttu-id="69609-118">I Microsoft 365-produktions miljöer säkerställer peer-replikering mellan data Center att det alltid finns flera aktiva kopior av alla data.</span><span class="sxs-lookup"><span data-stu-id="69609-118">Within Microsoft 365 production environments, peer replication between datacenters ensures that there are always multiple live copies of any data.</span></span> <span data-ttu-id="69609-119">Standard bilder och skript används för att återställa förlorade servrar och replikerade data används för att återställa kunddata.</span><span class="sxs-lookup"><span data-stu-id="69609-119">Standard images and scripts are used to recover lost servers, and replicated data is used to restore customer data.</span></span> <span data-ttu-id="69609-120">På grund av de inbyggda funktionerna för återhämtning och bearbetning av data är det bara att hantera säkerhets kopior av Microsoft 365 information om informations systemet (inklusive säkerhetsrelaterad dokumentation), med inbyggd replikering i SharePoint Online och med det interna kod databas verktyget, Source depå.</span><span class="sxs-lookup"><span data-stu-id="69609-120">Because of the built-in data resiliency checks and processes, Microsoft maintains backups only of Microsoft 365 information system documentation (including security-related documentation), using built-in replication in SharePoint Online and our internal code repository tool, Source Depot.</span></span> <span data-ttu-id="69609-121">Dokumentationen till systemet lagras i SharePoint Online och innehåller alla system-och program bilder.</span><span class="sxs-lookup"><span data-stu-id="69609-121">System documentation is stored in SharePoint Online, and Source Depot contains system and application images.</span></span> <span data-ttu-id="69609-122">Både SharePoint Online och Source depå använder versions hantering och replikeras i nära real tid.</span><span class="sxs-lookup"><span data-stu-id="69609-122">Both SharePoint Online and Source Depot use versioning and are replicated in near real time.</span></span>
