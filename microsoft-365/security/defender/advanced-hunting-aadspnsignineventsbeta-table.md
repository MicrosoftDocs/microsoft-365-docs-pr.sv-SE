---
title: AADSpnSignInEventsBeta-tabell i den avancerade sökschemat
description: Läs mer om information som är Azure Active Directory huvudnamn för tjänsten och inloggningshändelser för hanterad identitet i tabellen för avancerad sökning
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account, identity, AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f74972bcd5d0ddaab58d82b72a55991fda44e3b1
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583550"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="26452-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="26452-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="26452-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="26452-105">**Applies to:**</span></span>

- <span data-ttu-id="26452-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="26452-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="26452-107">Tabellen är för närvarande i betaversion och erbjuds inom kort för att du ska kunna jaga `AADSpnSignInEventsBeta` Azure Active Directory-tjänstens huvudnamn och hanterade identitetsin signeringshändelser.</span><span class="sxs-lookup"><span data-stu-id="26452-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="26452-108">Så småningom flyttar vi all information i inloggningsschemat till `IdentityLogonEvents` tabellen.</span><span class="sxs-lookup"><span data-stu-id="26452-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span>



<span data-ttu-id="26452-109">Tabellen `AADSpnSignInEventsBeta` i det avancerade sökschemat innehåller information om hur Azure Active Directory huvudnamn och inloggningar av hanterade identiteter. Du kan läsa mer om de olika typerna av inloggningar Azure Active Directory [i inloggningsaktivitetsrapporter – förhandsversion.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)</span><span class="sxs-lookup"><span data-stu-id="26452-109">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="26452-110">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="26452-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="26452-111">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)</span><span class="sxs-lookup"><span data-stu-id="26452-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="26452-112">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="26452-112">Column name</span></span>     | <span data-ttu-id="26452-113">Datatyp</span><span class="sxs-lookup"><span data-stu-id="26452-113">Data type</span></span> | <span data-ttu-id="26452-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="26452-114">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="26452-115">datetime</span><span class="sxs-lookup"><span data-stu-id="26452-115">datetime</span></span>      | <span data-ttu-id="26452-116">Datum och tid då posten skapades</span><span class="sxs-lookup"><span data-stu-id="26452-116">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="26452-117">sträng</span><span class="sxs-lookup"><span data-stu-id="26452-117">string</span></span>        | <span data-ttu-id="26452-118">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="26452-118">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="26452-119">sträng</span><span class="sxs-lookup"><span data-stu-id="26452-119">string</span></span>        | <span data-ttu-id="26452-120">Unikt ID för programmet</span><span class="sxs-lookup"><span data-stu-id="26452-120">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="26452-121">boolesk</span><span class="sxs-lookup"><span data-stu-id="26452-121">boolean</span></span>       | <span data-ttu-id="26452-122">Anger om inloggningen initierades med en hanterad identitet</span><span class="sxs-lookup"><span data-stu-id="26452-122">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="26452-123">int</span><span class="sxs-lookup"><span data-stu-id="26452-123">int</span></span>        | <span data-ttu-id="26452-124">Innehåller felkoden om ett inloggningsfel uppstår.</span><span class="sxs-lookup"><span data-stu-id="26452-124">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="26452-125">Gå till för att hitta en beskrivning av en specifik <https://aka.ms/AADsigninsErrorCodes> felkod.</span><span class="sxs-lookup"><span data-stu-id="26452-125">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="26452-126">sträng</span><span class="sxs-lookup"><span data-stu-id="26452-126">string</span></span>        | <span data-ttu-id="26452-127">Unikt ID för inloggningshändelsen</span><span class="sxs-lookup"><span data-stu-id="26452-127">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="26452-128">sträng</span><span class="sxs-lookup"><span data-stu-id="26452-128">string</span></span>        | <span data-ttu-id="26452-129">Namnet på tjänstens huvudnamn som startade inloggningen</span><span class="sxs-lookup"><span data-stu-id="26452-129">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="26452-130">sträng</span><span class="sxs-lookup"><span data-stu-id="26452-130">string</span></span>        | <span data-ttu-id="26452-131">Unikt ID för tjänstens huvudnamn som initierade inloggningen</span><span class="sxs-lookup"><span data-stu-id="26452-131">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="26452-132">sträng</span><span class="sxs-lookup"><span data-stu-id="26452-132">string</span></span>        | <span data-ttu-id="26452-133">Visningsnamn för den resurs som har åtkomst</span><span class="sxs-lookup"><span data-stu-id="26452-133">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="26452-134">sträng</span><span class="sxs-lookup"><span data-stu-id="26452-134">string</span></span>        | <span data-ttu-id="26452-135">Unikt ID för den resurs som används</span><span class="sxs-lookup"><span data-stu-id="26452-135">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="26452-136">sträng</span><span class="sxs-lookup"><span data-stu-id="26452-136">string</span></span>        | <span data-ttu-id="26452-137">Unikt ID för klientorganisationen för den resurs som används</span><span class="sxs-lookup"><span data-stu-id="26452-137">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="26452-138">sträng</span><span class="sxs-lookup"><span data-stu-id="26452-138">string</span></span>        | <span data-ttu-id="26452-139">IP-adress tilldelad till slutpunkten och används under relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="26452-139">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `Country`          | <span data-ttu-id="26452-140">sträng</span><span class="sxs-lookup"><span data-stu-id="26452-140">string</span></span>        | <span data-ttu-id="26452-141">Kod med två bokstäver som anger landet där klientens IP-adress är geolocerad</span><span class="sxs-lookup"><span data-stu-id="26452-141">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="26452-142">sträng</span><span class="sxs-lookup"><span data-stu-id="26452-142">string</span></span>        | <span data-ttu-id="26452-143">Delstat där inloggningen inträffade, om tillgänglig</span><span class="sxs-lookup"><span data-stu-id="26452-143">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="26452-144">sträng</span><span class="sxs-lookup"><span data-stu-id="26452-144">string</span></span>        | <span data-ttu-id="26452-145">Ort där kontoanvändaren finns</span><span class="sxs-lookup"><span data-stu-id="26452-145">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="26452-146">sträng</span><span class="sxs-lookup"><span data-stu-id="26452-146">string</span></span>        | <span data-ttu-id="26452-147">Koordinaterna för inloggning i nord till syd</span><span class="sxs-lookup"><span data-stu-id="26452-147">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="26452-148">sträng</span><span class="sxs-lookup"><span data-stu-id="26452-148">string</span></span>        | <span data-ttu-id="26452-149">Koordinaterna för inloggningsplatsen öst till väst</span><span class="sxs-lookup"><span data-stu-id="26452-149">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="26452-150">sträng</span><span class="sxs-lookup"><span data-stu-id="26452-150">string</span></span>        | <span data-ttu-id="26452-151">Unikt ID för begäran</span><span class="sxs-lookup"><span data-stu-id="26452-151">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="26452-152">sträng</span><span class="sxs-lookup"><span data-stu-id="26452-152">string</span></span> | <span data-ttu-id="26452-153">Unikt ID för händelsen</span><span class="sxs-lookup"><span data-stu-id="26452-153">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="26452-154">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="26452-154">Related articles</span></span>

-   [<span data-ttu-id="26452-155">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="26452-155">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="26452-156">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="26452-156">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="26452-157">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="26452-157">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="26452-158">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="26452-158">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)