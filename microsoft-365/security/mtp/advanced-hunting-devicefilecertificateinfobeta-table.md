---
title: DeviceFileCertificateInfoBeta-tabellen i det avancerade jaktschemat
description: Läs mer om filsigneringsinformation i tabellen DeviceFileCertificateInfoBeta i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, digital signatur, certifikat, filsignering, DeviceFileCertificateInfoBeta
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: c1d6b9170f0cc236f2656ce2adb596c31d9ee2bd
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809706"
---
# <a name="devicefilecertificateinfobeta"></a><span data-ttu-id="f4c65-104">DeviceFileCertificateInfoBeta</span><span class="sxs-lookup"><span data-stu-id="f4c65-104">DeviceFileCertificateInfoBeta</span></span>

<span data-ttu-id="f4c65-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="f4c65-105">**Applies to:**</span></span>
- <span data-ttu-id="f4c65-106">Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="f4c65-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="f4c65-107">Tabellen `DeviceFileCertificateInfoBeta` i det [avancerade jaktschemat](advanced-hunting-overview.md) innehåller information om certifikat för filsignering.</span><span class="sxs-lookup"><span data-stu-id="f4c65-107">The `DeviceFileCertificateInfoBeta` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="f4c65-108">I den här tabellen används data som erhållits från certifikatverifieringsaktiviteter som regelbundet utförs på filer på slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="f4c65-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="f4c65-109">Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="f4c65-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f4c65-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="f4c65-110">Column name</span></span> | <span data-ttu-id="f4c65-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="f4c65-111">Data type</span></span> | <span data-ttu-id="f4c65-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f4c65-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f4c65-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="f4c65-113">datetime</span></span> | <span data-ttu-id="f4c65-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="f4c65-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="f4c65-115">Sträng</span><span class="sxs-lookup"><span data-stu-id="f4c65-115">string</span></span> | <span data-ttu-id="f4c65-116">Unik identifierare för maskinen i tjänsten</span><span class="sxs-lookup"><span data-stu-id="f4c65-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="f4c65-117">Sträng</span><span class="sxs-lookup"><span data-stu-id="f4c65-117">string</span></span> | <span data-ttu-id="f4c65-118">Fullständigt kvalificerat domännamn (FQDN) för maskinen</span><span class="sxs-lookup"><span data-stu-id="f4c65-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="f4c65-119">Sträng</span><span class="sxs-lookup"><span data-stu-id="f4c65-119">string</span></span> | <span data-ttu-id="f4c65-120">SHA-1 i den akt som den registrerade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="f4c65-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="f4c65-121">Boolean</span><span class="sxs-lookup"><span data-stu-id="f4c65-121">boolean</span></span> | <span data-ttu-id="f4c65-122">Anger om filen är signerad</span><span class="sxs-lookup"><span data-stu-id="f4c65-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="f4c65-123">Sträng</span><span class="sxs-lookup"><span data-stu-id="f4c65-123">string</span></span> | <span data-ttu-id="f4c65-124">Anger om signaturinformation lästes som inbäddat innehåll i själva filen eller lästes från en extern katalogfil</span><span class="sxs-lookup"><span data-stu-id="f4c65-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="f4c65-125">Sträng</span><span class="sxs-lookup"><span data-stu-id="f4c65-125">string</span></span> | <span data-ttu-id="f4c65-126">Information om undertecknaren av filen</span><span class="sxs-lookup"><span data-stu-id="f4c65-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="f4c65-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="f4c65-127">string</span></span> | <span data-ttu-id="f4c65-128">Unikt hash-värde som identifierar undertecknaren</span><span class="sxs-lookup"><span data-stu-id="f4c65-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="f4c65-129">Sträng</span><span class="sxs-lookup"><span data-stu-id="f4c65-129">string</span></span> | <span data-ttu-id="f4c65-130">Information om den utfärdande certifikatutfärdaren</span><span class="sxs-lookup"><span data-stu-id="f4c65-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="f4c65-131">Sträng</span><span class="sxs-lookup"><span data-stu-id="f4c65-131">string</span></span> | <span data-ttu-id="f4c65-132">Unikt hash-värde som identifierar utfärdande certifikatutfärdarh (CA)</span><span class="sxs-lookup"><span data-stu-id="f4c65-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="f4c65-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="f4c65-133">string</span></span> | <span data-ttu-id="f4c65-134">Identifierare för certifikatet som är unikt för den utfärdande certifikatutfärdaren</span><span class="sxs-lookup"><span data-stu-id="f4c65-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="f4c65-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="f4c65-135">string</span></span> |  <span data-ttu-id="f4c65-136">JSON-matris med url:er för nätverksresurser som innehåller certifikat och listor över återkallade certifikat (CRL:er)</span><span class="sxs-lookup"><span data-stu-id="f4c65-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="f4c65-137">Datetime</span><span class="sxs-lookup"><span data-stu-id="f4c65-137">datetime</span></span> | <span data-ttu-id="f4c65-138">Datum och tid då certifikatet skapades</span><span class="sxs-lookup"><span data-stu-id="f4c65-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="f4c65-139">Datetime</span><span class="sxs-lookup"><span data-stu-id="f4c65-139">datetime</span></span> | <span data-ttu-id="f4c65-140">Datum och tid då certifikatet har angetts för att upphöra att gälla</span><span class="sxs-lookup"><span data-stu-id="f4c65-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="f4c65-141">Datetime</span><span class="sxs-lookup"><span data-stu-id="f4c65-141">datetime</span></span> | <span data-ttu-id="f4c65-142">Datum och tid då certifikatet kontrasignerades</span><span class="sxs-lookup"><span data-stu-id="f4c65-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="f4c65-143">Boolean</span><span class="sxs-lookup"><span data-stu-id="f4c65-143">boolean</span></span> | <span data-ttu-id="f4c65-144">Anger om filen är betrodd baserat på resultaten av winverifytrust-funktionen, som söker efter okänd rotcertifikatinformation, ogiltiga signaturer, återkallade certifikat och andra tvivelaktiga attribut</span><span class="sxs-lookup"><span data-stu-id="f4c65-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="f4c65-145">Boolean</span><span class="sxs-lookup"><span data-stu-id="f4c65-145">boolean</span></span> | <span data-ttu-id="f4c65-146">Anger om undertecknaren av rotcertifikatet är Microsoft</span><span class="sxs-lookup"><span data-stu-id="f4c65-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="f4c65-147">Lång</span><span class="sxs-lookup"><span data-stu-id="f4c65-147">long</span></span> | <span data-ttu-id="f4c65-148">Händelseidentifierare baserat på en upprepande räknare.</span><span class="sxs-lookup"><span data-stu-id="f4c65-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="f4c65-149">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp.</span><span class="sxs-lookup"><span data-stu-id="f4c65-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="f4c65-150">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="f4c65-150">Related topics</span></span>
- [<span data-ttu-id="f4c65-151">Proaktivt jakt efter hot</span><span class="sxs-lookup"><span data-stu-id="f4c65-151">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f4c65-152">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="f4c65-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f4c65-153">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="f4c65-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f4c65-154">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="f4c65-154">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f4c65-155">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="f4c65-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f4c65-156">Tillämpa metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="f4c65-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
