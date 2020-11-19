---
title: Nyheter i Microsoft 365 Defender
description: Här listas de nya funktionerna i Microsoft 365 Defender
keywords: Nyheter i Microsoft Threat Protection, ga, allmänt tillgängliga, funktioner, tillgängliga, ny
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: ade93bf8c89077c117ada764478cc74f4a5f14cc
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357325"
---
# <a name="whats-new-in-microsoft-365-defender"></a><span data-ttu-id="9e28d-104">Nyheter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e28d-104">What's new in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="9e28d-105">Vill du uppleva Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="9e28d-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="9e28d-106">Du kan [utvärdera det i en labb miljö](https://aka.ms/mtp-trial-lab) eller [köra ett pilot projekt i produktionen](https://aka.ms/m365d-pilotplaybook).</span><span class="sxs-lookup"><span data-stu-id="9e28d-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="9e28d-107">Följande funktioner är allmänt tillgängliga (GA) i den senaste versionen av Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9e28d-107">The following features are generally available (GA) in the latest release of Microsoft 365 Defender.</span></span>

<span data-ttu-id="9e28d-108">RSS-feed: få ett meddelande när den här sidan uppdateras genom att kopiera och klistra in följande webb adress i din feed-läsare:</span><span class="sxs-lookup"><span data-stu-id="9e28d-108">RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader:</span></span>
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
> <span data-ttu-id="9e28d-109">Vill du uppleva Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="9e28d-109">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="9e28d-110">Du kan [utvärdera det i en labb miljö](https://aka.ms/mtp-trial-lab) eller [köra ett pilot projekt i produktionen](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="9e28d-110">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook)</span></span>
>

## <a name="september-2020"></a><span data-ttu-id="9e28d-111">September 2020</span><span class="sxs-lookup"><span data-stu-id="9e28d-111">September 2020</span></span>
- [<span data-ttu-id="9e28d-112">IdentityDirectoryEvents tabell</span><span class="sxs-lookup"><span data-stu-id="9e28d-112">IdentityDirectoryEvents table</span></span>](advanced-hunting-identitydirectoryevents-table.md) <br> <span data-ttu-id="9e28d-113">Hitta händelser som berör en lokal domänkontrollant som kör Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="9e28d-113">Find events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="9e28d-114">Den här [avancerade](advanced-hunting-overview.md) schema tabellen för ökningar täcker ett antal identitets relaterade händelser och system händelser på domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="9e28d-114">This [advanced hunting](advanced-hunting-overview.md) schema table covers a range of identity-related events and system events on the domain controller.</span></span>
- [<span data-ttu-id="9e28d-115">Funktionen AssignedIPAddresses ()</span><span class="sxs-lookup"><span data-stu-id="9e28d-115">AssignedIPAddresses() function</span></span>](advanced-hunting-assignedipaddresses-function.md) <br> <span data-ttu-id="9e28d-116">Med den här funktionen kan du snabbt skaffa de senaste IP-adresserna till en enhet eller de senaste IP-adresserna från en viss tid.</span><span class="sxs-lookup"><span data-stu-id="9e28d-116">Use this function in your advanced hunting queries to quickly obtain the latest IP addresses assigned to a device or the most recent IP addresses from a specific time.</span></span>

## <a name="july-2020"></a><span data-ttu-id="9e28d-117">Juli 2020</span><span class="sxs-lookup"><span data-stu-id="9e28d-117">July 2020</span></span>
- [<span data-ttu-id="9e28d-118">Funktionen FileProfile ()</span><span class="sxs-lookup"><span data-stu-id="9e28d-118">FileProfile() function</span></span>](advanced-hunting-fileprofile-function.md) <br> <span data-ttu-id="9e28d-119">Använd den här funktionen när du vill utöka resultaten med fullständig fil information.</span><span class="sxs-lookup"><span data-stu-id="9e28d-119">Use this function in your advanced hunting queries to enrich results with comprehensive file information.</span></span>
- [<span data-ttu-id="9e28d-120">Identitets-och program tabeller</span><span class="sxs-lookup"><span data-stu-id="9e28d-120">Identity and app tables</span></span>](advanced-hunting-schema-tables.md)<br> <span data-ttu-id="9e28d-121">Få insyn i autentiseringsmetoderna, Active Directory-frågor och program relaterade aktiviteter med tabellerna [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)och [AppFileEvents](advanced-hunting-appfileevents-table.md) i det avancerade antivirus programmet.</span><span class="sxs-lookup"><span data-stu-id="9e28d-121">Get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>
- [<span data-ttu-id="9e28d-122">Gå på jakt</span><span class="sxs-lookup"><span data-stu-id="9e28d-122">Go hunt</span></span>](advanced-hunting-go-hunt.md)<br> <span data-ttu-id="9e28d-123">Snabbt pivotera en olycka för att inspektera en viss händelse, en användare, en enhet eller andra typer av enheter i en avancerad jakt.</span><span class="sxs-lookup"><span data-stu-id="9e28d-123">Quickly pivot from investigating an incident to inspecting a specific event, a user, a device, or other entity types on advanced hunting.</span></span>

## <a name="june-2020"></a><span data-ttu-id="9e28d-124">Juni 2020</span><span class="sxs-lookup"><span data-stu-id="9e28d-124">June 2020</span></span>
- <span data-ttu-id="9e28d-125">Twitter-feed</span><span class="sxs-lookup"><span data-stu-id="9e28d-125">Twitter feed</span></span> <br> <span data-ttu-id="9e28d-126">Få den senaste säkerhets forskningen, Hot intelligens, produkt nyheter och mer-direkt i instrument panelen.</span><span class="sxs-lookup"><span data-stu-id="9e28d-126">Get the latest security research, threat intelligence, product news, and more - right inside the dashboard.</span></span>
- [<span data-ttu-id="9e28d-127">EmailPostDeliveryEvents schema tabell</span><span class="sxs-lookup"><span data-stu-id="9e28d-127">EmailPostDeliveryEvents schema table</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) <br> <span data-ttu-id="9e28d-128">Ta med information om åtgärder efter leverans av dina e-postmeddelanden i dina frågor om avancerad jakt.</span><span class="sxs-lookup"><span data-stu-id="9e28d-128">Incorporate information about post-delivery actions taken on email messages in your advanced hunting queries.</span></span>
- [<span data-ttu-id="9e28d-129">Inspektera poster i avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="9e28d-129">Inspect records in advanced hunting</span></span>](advanced-hunting-query-results.md#drill-down-from-query-results) <br> <span data-ttu-id="9e28d-130">Kontrol lera snabbt poster i frågeresultatet med den nya informations panelen.</span><span class="sxs-lookup"><span data-stu-id="9e28d-130">Quickly inspect records in your query results with the new details panel.</span></span>

## <a name="may-2020"></a><span data-ttu-id="9e28d-131">Maj 2020</span><span class="sxs-lookup"><span data-stu-id="9e28d-131">May 2020</span></span>
- [<span data-ttu-id="9e28d-132">Anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="9e28d-132">Custom detections</span></span>](custom-detections-overview.md) <br> <span data-ttu-id="9e28d-133">Använd de avancerade frågorna för att skapa anpassade identifierings regler som automatiskt övervakas för och svarar på säkerhets händelser och system tillstånd.</span><span class="sxs-lookup"><span data-stu-id="9e28d-133">Use advanced hunting queries to create custom detection rules that automatically monitor for and respond to security events and system states.</span></span>

## <a name="february-2020"></a><span data-ttu-id="9e28d-134">Februari 2020</span><span class="sxs-lookup"><span data-stu-id="9e28d-134">February 2020</span></span>
- [<span data-ttu-id="9e28d-135">Incidenter</span><span class="sxs-lookup"><span data-stu-id="9e28d-135">Incidents</span></span>](incidents-overview.md) <br> <span data-ttu-id="9e28d-136">Veta exakt var en attack startas och annan information som hjälper dig att se omfattningen av angreppet.</span><span class="sxs-lookup"><span data-stu-id="9e28d-136">Know exactly where an attack started and other details to help you see the extent of the attack.</span></span>
- [<span data-ttu-id="9e28d-137">Automatiska undersökningar och svar</span><span class="sxs-lookup"><span data-stu-id="9e28d-137">Automated investigation and response</span></span>](mtp-autoir.md) <br> <span data-ttu-id="9e28d-138">AIR gör det möjligt för din säkerhets policy att markant öka organisationens kapacitet att hantera säkerhets varningar och-händelser.</span><span class="sxs-lookup"><span data-stu-id="9e28d-138">AIR enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span>
- [<span data-ttu-id="9e28d-139">Avancerade jakt förbättringar</span><span class="sxs-lookup"><span data-stu-id="9e28d-139">Advanced hunting enhancements</span></span>](advanced-hunting-overview.md) <br> <span data-ttu-id="9e28d-140">Det står proaktivt för hot via den moderna arbets ytan med Kusto frågespråk och ett säkerhetsoptimerat schema.</span><span class="sxs-lookup"><span data-stu-id="9e28d-140">Proactively hunt for threats across the modern workspace with Kusto Query Language and a security-optimized schema.</span></span>

## <a name="march-2019"></a><span data-ttu-id="9e28d-141">Mars 2019</span><span class="sxs-lookup"><span data-stu-id="9e28d-141">March 2019</span></span>
- <span data-ttu-id="9e28d-142">Avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="9e28d-142">Advanced hunting</span></span> <br> <span data-ttu-id="9e28d-143">Landnings sida till olika jakt funktioner som gör att du kan hitta hot som påverkar e-post och data, enheter och identiteter.</span><span class="sxs-lookup"><span data-stu-id="9e28d-143">Landing page to various hunting capabilities that let you proactively find threats affecting email and data, devices, and identities.</span></span>
- [<span data-ttu-id="9e28d-144">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="9e28d-144">Microsoft Secure Score</span></span>](microsoft-secure-score.md) <br> <span data-ttu-id="9e28d-145">Mätning av en organisations säkerhets Posture, med ett högre nummer som indikerar fler förbättrings åtgärder.</span><span class="sxs-lookup"><span data-stu-id="9e28d-145">Measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="9e28d-146">Om du följer säkerhets poängen kan du skydda din organisation mot hot.</span><span class="sxs-lookup"><span data-stu-id="9e28d-146">Following the Security Score recommendations can protect your organization from threats.</span></span> 
- [<span data-ttu-id="9e28d-147">Rapporter</span><span class="sxs-lookup"><span data-stu-id="9e28d-147">Reports</span></span>](monitoring-and-reporting.md) <br>  <span data-ttu-id="9e28d-148">Har en värd för kort som omfattar en mängd olika områden som säkerhets analyser och administratörer kan spåra under deras dagliga drift.</span><span class="sxs-lookup"><span data-stu-id="9e28d-148">Features a host of cards covering a variety of areas that security analysts and administrators track as part of their day-to-day operations.</span></span>
