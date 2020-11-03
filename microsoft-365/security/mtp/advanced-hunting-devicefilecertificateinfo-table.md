---
title: DeviceFileCertificateInfo-tabell i det avancerade jakt-schemat
description: Lär dig mer om fil signerings information i tabellen DeviceFileCertificateInfo för Advanced jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, digital signatur, certifikat, fil signering, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 9291d9f113fdc1c082b38d92399c1dee646b523d
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846176"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="f5e8c-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="f5e8c-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f5e8c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f5e8c-105">**Applies to:**</span></span>
- <span data-ttu-id="f5e8c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f5e8c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f5e8c-107">`DeviceFileCertificateInfo`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om fil signerings certifikat.</span><span class="sxs-lookup"><span data-stu-id="f5e8c-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="f5e8c-108">I den här tabellen används data som hämtats från certifikat verifierings aktiviteter regelbundet på filer på slut punkter.</span><span class="sxs-lookup"><span data-stu-id="f5e8c-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="f5e8c-109">Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="f5e8c-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f5e8c-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="f5e8c-110">Column name</span></span> | <span data-ttu-id="f5e8c-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="f5e8c-111">Data type</span></span> | <span data-ttu-id="f5e8c-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f5e8c-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f5e8c-113">datetime</span><span class="sxs-lookup"><span data-stu-id="f5e8c-113">datetime</span></span> | <span data-ttu-id="f5e8c-114">Datum och tid när händelsen registrerades</span><span class="sxs-lookup"><span data-stu-id="f5e8c-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="f5e8c-115">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f5e8c-115">string</span></span> | <span data-ttu-id="f5e8c-116">Unik identifierare för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="f5e8c-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="f5e8c-117">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f5e8c-117">string</span></span> | <span data-ttu-id="f5e8c-118">Det fullständigt kvalificerade domän namnet (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="f5e8c-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="f5e8c-119">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f5e8c-119">string</span></span> | <span data-ttu-id="f5e8c-120">SHA-1 av filen som den inspelade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="f5e8c-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="f5e8c-121">returtyp</span><span class="sxs-lookup"><span data-stu-id="f5e8c-121">boolean</span></span> | <span data-ttu-id="f5e8c-122">Anger om filen är signerad</span><span class="sxs-lookup"><span data-stu-id="f5e8c-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="f5e8c-123">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f5e8c-123">string</span></span> | <span data-ttu-id="f5e8c-124">Anger om signaturinformation lästes som inbäddat innehåll i filen eller läses från en extern katalog fil</span><span class="sxs-lookup"><span data-stu-id="f5e8c-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="f5e8c-125">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f5e8c-125">string</span></span> | <span data-ttu-id="f5e8c-126">Information om undertecknaren av filen</span><span class="sxs-lookup"><span data-stu-id="f5e8c-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="f5e8c-127">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f5e8c-127">string</span></span> | <span data-ttu-id="f5e8c-128">Unikt hashvärde identifierar undertecknaren</span><span class="sxs-lookup"><span data-stu-id="f5e8c-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="f5e8c-129">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f5e8c-129">string</span></span> | <span data-ttu-id="f5e8c-130">Information om utfärdande av certifikat utfärdare (CA)</span><span class="sxs-lookup"><span data-stu-id="f5e8c-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="f5e8c-131">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f5e8c-131">string</span></span> | <span data-ttu-id="f5e8c-132">Unikt hashvärde identifieras som utfärdar certifikat utfärdare (CA)</span><span class="sxs-lookup"><span data-stu-id="f5e8c-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="f5e8c-133">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f5e8c-133">string</span></span> | <span data-ttu-id="f5e8c-134">Identifierare för det certifikat som är unikt för den utfärdande certifikat utfärdaren (CA)</span><span class="sxs-lookup"><span data-stu-id="f5e8c-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="f5e8c-135">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="f5e8c-135">string</span></span> |  <span data-ttu-id="f5e8c-136">JSON-matris som visar URL-adresserna för nätverks resurser som innehåller certifikat och listor över återkallade certifikat (CRL)</span><span class="sxs-lookup"><span data-stu-id="f5e8c-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="f5e8c-137">datetime</span><span class="sxs-lookup"><span data-stu-id="f5e8c-137">datetime</span></span> | <span data-ttu-id="f5e8c-138">Datum och tid då certifikatet skapades</span><span class="sxs-lookup"><span data-stu-id="f5e8c-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="f5e8c-139">datetime</span><span class="sxs-lookup"><span data-stu-id="f5e8c-139">datetime</span></span> | <span data-ttu-id="f5e8c-140">Datum och tid då certifikatet är inställt på att upphöra</span><span class="sxs-lookup"><span data-stu-id="f5e8c-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="f5e8c-141">datetime</span><span class="sxs-lookup"><span data-stu-id="f5e8c-141">datetime</span></span> | <span data-ttu-id="f5e8c-142">Datum och tid då certifikatet undertecknades</span><span class="sxs-lookup"><span data-stu-id="f5e8c-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="f5e8c-143">returtyp</span><span class="sxs-lookup"><span data-stu-id="f5e8c-143">boolean</span></span> | <span data-ttu-id="f5e8c-144">Anger om filen är betrodd baserat på resultatet av WinVerifyTrust-funktionen, som söker efter information om okända rot certifikat, ogiltiga signaturer, återkallade certifikat och andra fråge bara attribut</span><span class="sxs-lookup"><span data-stu-id="f5e8c-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="f5e8c-145">returtyp</span><span class="sxs-lookup"><span data-stu-id="f5e8c-145">boolean</span></span> | <span data-ttu-id="f5e8c-146">Anger om undertecknaren hos rot certifikatet är Microsoft</span><span class="sxs-lookup"><span data-stu-id="f5e8c-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="f5e8c-147">tids</span><span class="sxs-lookup"><span data-stu-id="f5e8c-147">long</span></span> | <span data-ttu-id="f5e8c-148">Händelse identifierare baserad på en upprepande räknare.</span><span class="sxs-lookup"><span data-stu-id="f5e8c-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="f5e8c-149">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna enhets namn och tidsstämpel.</span><span class="sxs-lookup"><span data-stu-id="f5e8c-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="f5e8c-150">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="f5e8c-150">Related topics</span></span>
- [<span data-ttu-id="f5e8c-151">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="f5e8c-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f5e8c-152">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="f5e8c-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f5e8c-153">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="f5e8c-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f5e8c-154">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="f5e8c-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f5e8c-155">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="f5e8c-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f5e8c-156">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="f5e8c-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
