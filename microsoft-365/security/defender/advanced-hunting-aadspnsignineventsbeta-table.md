---
title: AADSpnSignInEventsBeta-tabell i den avancerade sökschemat
description: Läs mer om informationen som är kopplad till tabellen för azure Active Directory-tjänstens huvudnamn och inloggning av hanterade identiteter i det avancerade sökschemat
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
ms.openlocfilehash: 984e945107b6e0b41459659a7f2e9f649981e4b5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932601"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="fb94c-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="fb94c-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="fb94c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="fb94c-105">**Applies to:**</span></span>

- <span data-ttu-id="fb94c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fb94c-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="fb94c-107">Tabellen är för närvarande i betaversion och erbjuds inom kort för att du ska kunna leta igenom AAD-tjänstens huvudnamn och inloggningshändelser för hanterade identiteter i `AADSpnSignInEventsBeta` Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fb94c-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="fb94c-108">Så småningom flyttar vi all information i inloggningsschemat till `IdentityLogonEvents` tabellen.</span><span class="sxs-lookup"><span data-stu-id="fb94c-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span><br><br>
> <span data-ttu-id="fb94c-109">Kunder som har åtkomst till Microsoft 365 Defender via Azure Defenders integrerade Microsoft Defender för slutpunktslösning, men inte har licenser för Microsoft Defender för Office, Microsoft Defender för identitet eller Microsoft Cloud App Security, kommer inte att kunna se det här schemat.</span><span class="sxs-lookup"><span data-stu-id="fb94c-109">Customers who can access Microsoft 365 Defender through the Azure Defender’s integrated Microsoft Defender for Endpoint solution, but do not have licenses for Microsoft Defender for Office, Microsoft Defender for Identity, or Microsoft Cloud App Security, will not be able to view this schema.</span></span> 



<span data-ttu-id="fb94c-110">Tabellen `AADSpnSignInEventsBeta` i det avancerade schemat för sökning innehåller information om Azure Active Directory-tjänstens huvudnamn och inloggning av hanterade identiteter. Du kan läsa mer om de olika typerna av inloggningar i [Azure Active Directory-inloggningsaktivitetsrapporter – förhandsversion.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)</span><span class="sxs-lookup"><span data-stu-id="fb94c-110">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="fb94c-111">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="fb94c-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="fb94c-112">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)</span><span class="sxs-lookup"><span data-stu-id="fb94c-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="fb94c-113">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="fb94c-113">Column name</span></span>     | <span data-ttu-id="fb94c-114">Datatyp</span><span class="sxs-lookup"><span data-stu-id="fb94c-114">Data type</span></span> | <span data-ttu-id="fb94c-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fb94c-115">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="fb94c-116">datetime</span><span class="sxs-lookup"><span data-stu-id="fb94c-116">datetime</span></span>      | <span data-ttu-id="fb94c-117">Datum och tid då posten skapades</span><span class="sxs-lookup"><span data-stu-id="fb94c-117">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="fb94c-118">sträng</span><span class="sxs-lookup"><span data-stu-id="fb94c-118">string</span></span>        | <span data-ttu-id="fb94c-119">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="fb94c-119">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="fb94c-120">sträng</span><span class="sxs-lookup"><span data-stu-id="fb94c-120">string</span></span>        | <span data-ttu-id="fb94c-121">Unikt ID för programmet</span><span class="sxs-lookup"><span data-stu-id="fb94c-121">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="fb94c-122">boolesk</span><span class="sxs-lookup"><span data-stu-id="fb94c-122">boolean</span></span>       | <span data-ttu-id="fb94c-123">Anger om inloggningen initierades med en hanterad identitet</span><span class="sxs-lookup"><span data-stu-id="fb94c-123">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="fb94c-124">int</span><span class="sxs-lookup"><span data-stu-id="fb94c-124">int</span></span>        | <span data-ttu-id="fb94c-125">Innehåller felkoden om ett inloggningsfel uppstår.</span><span class="sxs-lookup"><span data-stu-id="fb94c-125">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="fb94c-126">Gå till för att hitta en beskrivning av en specifik <https://aka.ms/AADsigninsErrorCodes> felkod.</span><span class="sxs-lookup"><span data-stu-id="fb94c-126">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="fb94c-127">sträng</span><span class="sxs-lookup"><span data-stu-id="fb94c-127">string</span></span>        | <span data-ttu-id="fb94c-128">Unikt ID för inloggningshändelsen</span><span class="sxs-lookup"><span data-stu-id="fb94c-128">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="fb94c-129">sträng</span><span class="sxs-lookup"><span data-stu-id="fb94c-129">string</span></span>        | <span data-ttu-id="fb94c-130">Namnet på tjänstens huvudnamn som startade inloggningen</span><span class="sxs-lookup"><span data-stu-id="fb94c-130">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="fb94c-131">sträng</span><span class="sxs-lookup"><span data-stu-id="fb94c-131">string</span></span>        | <span data-ttu-id="fb94c-132">Unikt ID för tjänstens huvudnamn som initierade inloggningen</span><span class="sxs-lookup"><span data-stu-id="fb94c-132">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="fb94c-133">sträng</span><span class="sxs-lookup"><span data-stu-id="fb94c-133">string</span></span>        | <span data-ttu-id="fb94c-134">Visningsnamn för den resurs som har åtkomst</span><span class="sxs-lookup"><span data-stu-id="fb94c-134">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="fb94c-135">sträng</span><span class="sxs-lookup"><span data-stu-id="fb94c-135">string</span></span>        | <span data-ttu-id="fb94c-136">Unikt ID för den resurs som används</span><span class="sxs-lookup"><span data-stu-id="fb94c-136">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="fb94c-137">sträng</span><span class="sxs-lookup"><span data-stu-id="fb94c-137">string</span></span>        | <span data-ttu-id="fb94c-138">Unikt ID för klientorganisationen för den resurs som används</span><span class="sxs-lookup"><span data-stu-id="fb94c-138">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="fb94c-139">sträng</span><span class="sxs-lookup"><span data-stu-id="fb94c-139">string</span></span>        | <span data-ttu-id="fb94c-140">IP-adress tilldelad till slutpunkten och används under relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="fb94c-140">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `Country`          | <span data-ttu-id="fb94c-141">sträng</span><span class="sxs-lookup"><span data-stu-id="fb94c-141">string</span></span>        | <span data-ttu-id="fb94c-142">Kod med två bokstäver som anger landet där klientens IP-adress är geolocerad</span><span class="sxs-lookup"><span data-stu-id="fb94c-142">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="fb94c-143">sträng</span><span class="sxs-lookup"><span data-stu-id="fb94c-143">string</span></span>        | <span data-ttu-id="fb94c-144">Delstat där inloggningen inträffade, om tillgänglig</span><span class="sxs-lookup"><span data-stu-id="fb94c-144">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="fb94c-145">sträng</span><span class="sxs-lookup"><span data-stu-id="fb94c-145">string</span></span>        | <span data-ttu-id="fb94c-146">Ort där kontoanvändaren finns</span><span class="sxs-lookup"><span data-stu-id="fb94c-146">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="fb94c-147">sträng</span><span class="sxs-lookup"><span data-stu-id="fb94c-147">string</span></span>        | <span data-ttu-id="fb94c-148">Koordinaterna för inloggning i nord till syd</span><span class="sxs-lookup"><span data-stu-id="fb94c-148">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="fb94c-149">sträng</span><span class="sxs-lookup"><span data-stu-id="fb94c-149">string</span></span>        | <span data-ttu-id="fb94c-150">Koordinaterna för inloggningsplatsen öst till väst</span><span class="sxs-lookup"><span data-stu-id="fb94c-150">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="fb94c-151">sträng</span><span class="sxs-lookup"><span data-stu-id="fb94c-151">string</span></span>        | <span data-ttu-id="fb94c-152">Unikt ID för begäran</span><span class="sxs-lookup"><span data-stu-id="fb94c-152">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="fb94c-153">sträng</span><span class="sxs-lookup"><span data-stu-id="fb94c-153">string</span></span> | <span data-ttu-id="fb94c-154">Unikt ID för händelsen</span><span class="sxs-lookup"><span data-stu-id="fb94c-154">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="fb94c-155">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="fb94c-155">Related articles</span></span>

-   [<span data-ttu-id="fb94c-156">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="fb94c-156">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="fb94c-157">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="fb94c-157">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="fb94c-158">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="fb94c-158">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="fb94c-159">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="fb94c-159">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)