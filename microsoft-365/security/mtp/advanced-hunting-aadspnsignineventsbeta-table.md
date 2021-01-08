---
title: AADSpnSignInEventsBeta-tabell i det avancerade jakt-schemat
description: Lär dig mer om den information som är kopplad till tabellen för inloggnings händelser för Azure Active Directory-tjänsten och det avancerade Antivirus schema
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, AlertInfo, avisering, enheter, bevis, fil, IP-adress, enhet, dator, användare, konto, identitet, AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 42acf24ce9b941fffb1ce0ed4b67216bd8c1de47
ms.sourcegitcommit: 4482c174e0e68e0fbbc7ad9ef6b0e78dc34ac85a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/08/2021
ms.locfileid: "49784305"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="ceff8-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="ceff8-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="ceff8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ceff8-105">**Applies to:**</span></span>

- <span data-ttu-id="ceff8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ceff8-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="ceff8-107">`AADSpnSignInEventsBeta`Tabellen finns för närvarande i Beta versionen och erbjuds på ett kortsiktigt sätt så att du kan gå igenom alla inloggnings händelser för Azure Active Directory-tjänsten (AAD) och hanterad identitet.</span><span class="sxs-lookup"><span data-stu-id="ceff8-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="ceff8-108">Vi kommer slutligen att flytta all information om inloggnings schema till `IdentityLogonEvents` tabellen.</span><span class="sxs-lookup"><span data-stu-id="ceff8-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span><br><br>
> <span data-ttu-id="ceff8-109">Kunder som kan komma åt Microsoft 365 Defender via Azure säkerhets centrets integrerade Microsoft Defender för slut punkts lösning, men inte har licenser för Microsoft Defender för Office, Microsoft Defender för identitet eller Microsoft Cloud App Security, kan inte visa detta schema.</span><span class="sxs-lookup"><span data-stu-id="ceff8-109">Customers who can access Microsoft 365 Defender through the Azure Security Center’s integrated Microsoft Defender for Endpoint solution, but do not have licenses for Microsoft Defender for Office, Microsoft Defender for Identity, or Microsoft Cloud App Security, will not be able to view this schema.</span></span> 



<span data-ttu-id="ceff8-110">`AADSpnSignInEventsBeta`Tabellen i det avancerade jakt-schemat innehåller information om Azure Active Directory-tjänstens huvud konto och inloggnings uppgifter för hanterade identiteter. Du kan läsa mer om olika typer av inloggnings uppgifter i [Azure Active Directory-inloggnings aktivitets rapporter – för hands version](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span><span class="sxs-lookup"><span data-stu-id="ceff8-110">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="ceff8-111">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="ceff8-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="ceff8-112">Information om andra tabeller i det avancerade jakt schema finns i [referens för avancerad jakt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span><span class="sxs-lookup"><span data-stu-id="ceff8-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="ceff8-113">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="ceff8-113">Column name</span></span>     | <span data-ttu-id="ceff8-114">Datatyp</span><span class="sxs-lookup"><span data-stu-id="ceff8-114">Data type</span></span> | <span data-ttu-id="ceff8-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ceff8-115">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="ceff8-116">datetime</span><span class="sxs-lookup"><span data-stu-id="ceff8-116">datetime</span></span>      | <span data-ttu-id="ceff8-117">Datum och tid när posten skapades</span><span class="sxs-lookup"><span data-stu-id="ceff8-117">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="ceff8-118">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="ceff8-118">string</span></span>        | <span data-ttu-id="ceff8-119">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="ceff8-119">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="ceff8-120">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="ceff8-120">string</span></span>        | <span data-ttu-id="ceff8-121">Unik identifierare för programmet</span><span class="sxs-lookup"><span data-stu-id="ceff8-121">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="ceff8-122">returtyp</span><span class="sxs-lookup"><span data-stu-id="ceff8-122">boolean</span></span>       | <span data-ttu-id="ceff8-123">Anger om inloggningen initierats av en hanterad identitet</span><span class="sxs-lookup"><span data-stu-id="ceff8-123">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="ceff8-124">signera</span><span class="sxs-lookup"><span data-stu-id="ceff8-124">int</span></span>        | <span data-ttu-id="ceff8-125">Innehåller felkoden om ett inloggnings fel inträffar.</span><span class="sxs-lookup"><span data-stu-id="ceff8-125">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="ceff8-126">För att hitta en beskrivning av en specifik felkod, gå till <https://aka.ms/AADsigninsErrorCodes> .</span><span class="sxs-lookup"><span data-stu-id="ceff8-126">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="ceff8-127">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="ceff8-127">string</span></span>        | <span data-ttu-id="ceff8-128">Unik identifierare för inloggnings händelsen</span><span class="sxs-lookup"><span data-stu-id="ceff8-128">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="ceff8-129">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="ceff8-129">string</span></span>        | <span data-ttu-id="ceff8-130">Namnet på tjänstens huvud namn som initierade inloggningen</span><span class="sxs-lookup"><span data-stu-id="ceff8-130">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="ceff8-131">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="ceff8-131">string</span></span>        | <span data-ttu-id="ceff8-132">Unik identifierare för tjänstens huvud namn som initierade inloggningen</span><span class="sxs-lookup"><span data-stu-id="ceff8-132">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="ceff8-133">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="ceff8-133">string</span></span>        | <span data-ttu-id="ceff8-134">Visnings namn för den åtkomst som används för resursen</span><span class="sxs-lookup"><span data-stu-id="ceff8-134">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="ceff8-135">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="ceff8-135">string</span></span>        | <span data-ttu-id="ceff8-136">Unik identifierare för den åtkomst som används för resursen</span><span class="sxs-lookup"><span data-stu-id="ceff8-136">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="ceff8-137">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="ceff8-137">string</span></span>        | <span data-ttu-id="ceff8-138">Unik identifierare för innehavaren av resursen</span><span class="sxs-lookup"><span data-stu-id="ceff8-138">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="ceff8-139">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="ceff8-139">string</span></span>        | <span data-ttu-id="ceff8-140">IP-adress tilldelad till slut punkten och används under relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="ceff8-140">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `CountryCode`          | <span data-ttu-id="ceff8-141">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="ceff8-141">string</span></span>        | <span data-ttu-id="ceff8-142">Kod med två bokstäver som anger det land där klient-IP-adressen finns</span><span class="sxs-lookup"><span data-stu-id="ceff8-142">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="ceff8-143">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="ceff8-143">string</span></span>        | <span data-ttu-id="ceff8-144">Ange var inloggningen inträffar, om den är tillgänglig</span><span class="sxs-lookup"><span data-stu-id="ceff8-144">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="ceff8-145">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="ceff8-145">string</span></span>        | <span data-ttu-id="ceff8-146">Ort där konto användaren finns</span><span class="sxs-lookup"><span data-stu-id="ceff8-146">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="ceff8-147">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="ceff8-147">string</span></span>        | <span data-ttu-id="ceff8-148">Norr till syd-koordinaterna för inloggnings platsen</span><span class="sxs-lookup"><span data-stu-id="ceff8-148">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="ceff8-149">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="ceff8-149">string</span></span>        | <span data-ttu-id="ceff8-150">Östra till väst-koordinater för inloggnings platsen</span><span class="sxs-lookup"><span data-stu-id="ceff8-150">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="ceff8-151">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="ceff8-151">string</span></span>        | <span data-ttu-id="ceff8-152">Unik identifierare för begäran</span><span class="sxs-lookup"><span data-stu-id="ceff8-152">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="ceff8-153">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="ceff8-153">string</span></span> | <span data-ttu-id="ceff8-154">Unik identifierare för händelsen</span><span class="sxs-lookup"><span data-stu-id="ceff8-154">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="ceff8-155">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="ceff8-155">Related articles</span></span>

-   [<span data-ttu-id="ceff8-156">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="ceff8-156">AADSignInEventsBeta</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [<span data-ttu-id="ceff8-157">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="ceff8-157">Advanced hunting overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="ceff8-158">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="ceff8-158">Learn the query language</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="ceff8-159">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="ceff8-159">Understand the schema</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

