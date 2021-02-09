---
title: Tabellen AADSpnSignInEventsBeta i det avancerade sökschemat
description: Läs mer om information om azure Active Directory-tjänstens huvudnamn och inloggningshändelser för hanterade identiteter i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, cyberhot, skydd mot cyberhot, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, Aviseringinfo, avisering, enheter, bevis, fil, IP-adress, enhet, dator, användare, konto, identitet, AAD
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3eba2459fd9a0af1963ca8d1446b22fc0b1bdb93
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145409"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="0e60f-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="0e60f-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="0e60f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="0e60f-105">**Applies to:**</span></span>

- <span data-ttu-id="0e60f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0e60f-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="0e60f-107">Tabellen är för närvarande i betaversion och erbjuds på kort sikt så att du kan jaga via `AADSpnSignInEventsBeta` AAD-tjänstens huvudnamn (Azure Active Directory) och hanterade identitetsin signeringshändelser.</span><span class="sxs-lookup"><span data-stu-id="0e60f-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="0e60f-108">Så småningom flyttar vi all information i inloggningsschemat till `IdentityLogonEvents` tabellen.</span><span class="sxs-lookup"><span data-stu-id="0e60f-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span><br><br>
> <span data-ttu-id="0e60f-109">Kunder som kan komma åt Microsoft 365 Defender via Azure Säkerhetscenters integrerade Microsoft Defender för slutpunktslösning, men inte har licenser för Microsoft Defender för Office, Microsoft Defender för identitet eller Microsoft Cloud App Security, kommer inte att kunna se det här schemat.</span><span class="sxs-lookup"><span data-stu-id="0e60f-109">Customers who can access Microsoft 365 Defender through the Azure Security Center’s integrated Microsoft Defender for Endpoint solution, but do not have licenses for Microsoft Defender for Office, Microsoft Defender for Identity, or Microsoft Cloud App Security, will not be able to view this schema.</span></span> 



<span data-ttu-id="0e60f-110">Tabellen `AADSpnSignInEventsBeta` i det avancerade utbildningsschemat innehåller information om Azure Active Directory-tjänstens huvudnamn och inloggningar för hanterade identiteter. Du kan läsa mer om de olika typerna av inloggningar i [azure Active Directory-inloggningsrapporter](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)– förhandsversion.</span><span class="sxs-lookup"><span data-stu-id="0e60f-110">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="0e60f-111">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="0e60f-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="0e60f-112">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)</span><span class="sxs-lookup"><span data-stu-id="0e60f-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="0e60f-113">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="0e60f-113">Column name</span></span>     | <span data-ttu-id="0e60f-114">Datatyp</span><span class="sxs-lookup"><span data-stu-id="0e60f-114">Data type</span></span> | <span data-ttu-id="0e60f-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0e60f-115">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="0e60f-116">datetime</span><span class="sxs-lookup"><span data-stu-id="0e60f-116">datetime</span></span>      | <span data-ttu-id="0e60f-117">Datum och tid då posten skapades</span><span class="sxs-lookup"><span data-stu-id="0e60f-117">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="0e60f-118">sträng</span><span class="sxs-lookup"><span data-stu-id="0e60f-118">string</span></span>        | <span data-ttu-id="0e60f-119">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="0e60f-119">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="0e60f-120">sträng</span><span class="sxs-lookup"><span data-stu-id="0e60f-120">string</span></span>        | <span data-ttu-id="0e60f-121">Unikt ID för programmet</span><span class="sxs-lookup"><span data-stu-id="0e60f-121">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="0e60f-122">boolesk</span><span class="sxs-lookup"><span data-stu-id="0e60f-122">boolean</span></span>       | <span data-ttu-id="0e60f-123">Anger om inloggningen initierades med en hanterad identitet</span><span class="sxs-lookup"><span data-stu-id="0e60f-123">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="0e60f-124">int</span><span class="sxs-lookup"><span data-stu-id="0e60f-124">int</span></span>        | <span data-ttu-id="0e60f-125">Innehåller felkoden om det uppstår ett inloggningsfel.</span><span class="sxs-lookup"><span data-stu-id="0e60f-125">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="0e60f-126">Gå till en beskrivning av en specifik <https://aka.ms/AADsigninsErrorCodes> felkod.</span><span class="sxs-lookup"><span data-stu-id="0e60f-126">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="0e60f-127">sträng</span><span class="sxs-lookup"><span data-stu-id="0e60f-127">string</span></span>        | <span data-ttu-id="0e60f-128">Unikt ID för inloggningshändelsen</span><span class="sxs-lookup"><span data-stu-id="0e60f-128">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="0e60f-129">sträng</span><span class="sxs-lookup"><span data-stu-id="0e60f-129">string</span></span>        | <span data-ttu-id="0e60f-130">Namnet på tjänstens huvudnamn som initierade inloggningen</span><span class="sxs-lookup"><span data-stu-id="0e60f-130">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="0e60f-131">sträng</span><span class="sxs-lookup"><span data-stu-id="0e60f-131">string</span></span>        | <span data-ttu-id="0e60f-132">Unikt ID för tjänstens huvudnamn som initierade inloggningen</span><span class="sxs-lookup"><span data-stu-id="0e60f-132">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="0e60f-133">sträng</span><span class="sxs-lookup"><span data-stu-id="0e60f-133">string</span></span>        | <span data-ttu-id="0e60f-134">Visningsnamn för resursen som har åtkomst</span><span class="sxs-lookup"><span data-stu-id="0e60f-134">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="0e60f-135">sträng</span><span class="sxs-lookup"><span data-stu-id="0e60f-135">string</span></span>        | <span data-ttu-id="0e60f-136">Unikt ID för den resurs som används</span><span class="sxs-lookup"><span data-stu-id="0e60f-136">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="0e60f-137">sträng</span><span class="sxs-lookup"><span data-stu-id="0e60f-137">string</span></span>        | <span data-ttu-id="0e60f-138">Unikt ID för klientorganisationen för resursen som används</span><span class="sxs-lookup"><span data-stu-id="0e60f-138">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="0e60f-139">sträng</span><span class="sxs-lookup"><span data-stu-id="0e60f-139">string</span></span>        | <span data-ttu-id="0e60f-140">IP-adress som tilldelats slutpunkten och som används under relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="0e60f-140">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `Country`          | <span data-ttu-id="0e60f-141">sträng</span><span class="sxs-lookup"><span data-stu-id="0e60f-141">string</span></span>        | <span data-ttu-id="0e60f-142">Kod med två bokstäver som anger landet där klient-IP-adressen är geolokal</span><span class="sxs-lookup"><span data-stu-id="0e60f-142">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="0e60f-143">sträng</span><span class="sxs-lookup"><span data-stu-id="0e60f-143">string</span></span>        | <span data-ttu-id="0e60f-144">Delstat där inloggningen inträffade, om tillgänglig</span><span class="sxs-lookup"><span data-stu-id="0e60f-144">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="0e60f-145">sträng</span><span class="sxs-lookup"><span data-stu-id="0e60f-145">string</span></span>        | <span data-ttu-id="0e60f-146">Ort där kontoanvändaren finns</span><span class="sxs-lookup"><span data-stu-id="0e60f-146">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="0e60f-147">sträng</span><span class="sxs-lookup"><span data-stu-id="0e60f-147">string</span></span>        | <span data-ttu-id="0e60f-148">Koordinaterna för inloggningsplats för nord till syd</span><span class="sxs-lookup"><span data-stu-id="0e60f-148">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="0e60f-149">sträng</span><span class="sxs-lookup"><span data-stu-id="0e60f-149">string</span></span>        | <span data-ttu-id="0e60f-150">Inloggningsplatsens koordinater för öst till väst</span><span class="sxs-lookup"><span data-stu-id="0e60f-150">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="0e60f-151">sträng</span><span class="sxs-lookup"><span data-stu-id="0e60f-151">string</span></span>        | <span data-ttu-id="0e60f-152">Unik identifierare för begäran</span><span class="sxs-lookup"><span data-stu-id="0e60f-152">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="0e60f-153">sträng</span><span class="sxs-lookup"><span data-stu-id="0e60f-153">string</span></span> | <span data-ttu-id="0e60f-154">Unikt ID för händelsen</span><span class="sxs-lookup"><span data-stu-id="0e60f-154">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="0e60f-155">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="0e60f-155">Related articles</span></span>

-   [<span data-ttu-id="0e60f-156">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="0e60f-156">AADSignInEventsBeta</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [<span data-ttu-id="0e60f-157">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="0e60f-157">Advanced hunting overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="0e60f-158">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="0e60f-158">Learn the query language</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="0e60f-159">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="0e60f-159">Understand the schema</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

