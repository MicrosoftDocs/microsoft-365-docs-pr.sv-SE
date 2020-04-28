---
title: DeviceFileCertificateInfo-tabellen i det avancerade jaktschemat
description: Lär dig mer om filsigneringsinformation i tabellen DeviceFileCertificateInfo i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, digital signatur, certifikat, filsignering, DeviceFileCertificateInfo
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
ms.openlocfilehash: fcbd487aeed633176c86fd22bfcd156be02fea22
ms.sourcegitcommit: b6c4b514b2cb6739af949780d7e2a5a5c8dcc161
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43900799"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="2127a-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="2127a-104">DeviceFileCertificateInfo</span></span>

<span data-ttu-id="2127a-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="2127a-105">**Applies to:**</span></span>
- <span data-ttu-id="2127a-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="2127a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="2127a-107">Tabellen `DeviceFileCertificateInfo` i det [avancerade jaktschemat](advanced-hunting-overview.md) innehåller information om certifikat för filsignering.</span><span class="sxs-lookup"><span data-stu-id="2127a-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="2127a-108">I den här tabellen används data som erhållits från certifikatverifieringsaktiviteter som regelbundet utförs på filer på slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="2127a-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="2127a-109">Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="2127a-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2127a-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="2127a-110">Column name</span></span> | <span data-ttu-id="2127a-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="2127a-111">Data type</span></span> | <span data-ttu-id="2127a-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2127a-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="2127a-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="2127a-113">datetime</span></span> | <span data-ttu-id="2127a-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="2127a-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="2127a-115">Sträng</span><span class="sxs-lookup"><span data-stu-id="2127a-115">string</span></span> | <span data-ttu-id="2127a-116">Unik identifierare för maskinen i tjänsten</span><span class="sxs-lookup"><span data-stu-id="2127a-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="2127a-117">Sträng</span><span class="sxs-lookup"><span data-stu-id="2127a-117">string</span></span> | <span data-ttu-id="2127a-118">Fullständigt kvalificerat domännamn (FQDN) för maskinen</span><span class="sxs-lookup"><span data-stu-id="2127a-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="2127a-119">Sträng</span><span class="sxs-lookup"><span data-stu-id="2127a-119">string</span></span> | <span data-ttu-id="2127a-120">SHA-1 i den akt som den registrerade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="2127a-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="2127a-121">Boolean</span><span class="sxs-lookup"><span data-stu-id="2127a-121">boolean</span></span> | <span data-ttu-id="2127a-122">Anger om filen är signerad</span><span class="sxs-lookup"><span data-stu-id="2127a-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="2127a-123">Sträng</span><span class="sxs-lookup"><span data-stu-id="2127a-123">string</span></span> | <span data-ttu-id="2127a-124">Anger om signaturinformation lästes som inbäddat innehåll i själva filen eller lästes från en extern katalogfil</span><span class="sxs-lookup"><span data-stu-id="2127a-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="2127a-125">Sträng</span><span class="sxs-lookup"><span data-stu-id="2127a-125">string</span></span> | <span data-ttu-id="2127a-126">Information om undertecknaren av filen</span><span class="sxs-lookup"><span data-stu-id="2127a-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="2127a-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="2127a-127">string</span></span> | <span data-ttu-id="2127a-128">Unikt hash-värde som identifierar undertecknaren</span><span class="sxs-lookup"><span data-stu-id="2127a-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="2127a-129">Sträng</span><span class="sxs-lookup"><span data-stu-id="2127a-129">string</span></span> | <span data-ttu-id="2127a-130">Information om den utfärdande certifikatutfärdaren</span><span class="sxs-lookup"><span data-stu-id="2127a-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="2127a-131">Sträng</span><span class="sxs-lookup"><span data-stu-id="2127a-131">string</span></span> | <span data-ttu-id="2127a-132">Unikt hash-värde som identifierar utfärdande certifikatutfärdarh (CA)</span><span class="sxs-lookup"><span data-stu-id="2127a-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="2127a-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="2127a-133">string</span></span> | <span data-ttu-id="2127a-134">Identifierare för certifikatet som är unikt för den utfärdande certifikatutfärdaren</span><span class="sxs-lookup"><span data-stu-id="2127a-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="2127a-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="2127a-135">string</span></span> |  <span data-ttu-id="2127a-136">JSON-matris med url:er för nätverksresurser som innehåller certifikat och listor över återkallade certifikat (CRL:er)</span><span class="sxs-lookup"><span data-stu-id="2127a-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="2127a-137">Datetime</span><span class="sxs-lookup"><span data-stu-id="2127a-137">datetime</span></span> | <span data-ttu-id="2127a-138">Datum och tid då certifikatet skapades</span><span class="sxs-lookup"><span data-stu-id="2127a-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="2127a-139">Datetime</span><span class="sxs-lookup"><span data-stu-id="2127a-139">datetime</span></span> | <span data-ttu-id="2127a-140">Datum och tid då certifikatet har angetts för att upphöra att gälla</span><span class="sxs-lookup"><span data-stu-id="2127a-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="2127a-141">Datetime</span><span class="sxs-lookup"><span data-stu-id="2127a-141">datetime</span></span> | <span data-ttu-id="2127a-142">Datum och tid då certifikatet kontrasignerades</span><span class="sxs-lookup"><span data-stu-id="2127a-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="2127a-143">Boolean</span><span class="sxs-lookup"><span data-stu-id="2127a-143">boolean</span></span> | <span data-ttu-id="2127a-144">Anger om filen är betrodd baserat på resultaten av winverifytrust-funktionen, som söker efter okänd rotcertifikatinformation, ogiltiga signaturer, återkallade certifikat och andra tvivelaktiga attribut</span><span class="sxs-lookup"><span data-stu-id="2127a-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="2127a-145">Boolean</span><span class="sxs-lookup"><span data-stu-id="2127a-145">boolean</span></span> | <span data-ttu-id="2127a-146">Anger om undertecknaren av rotcertifikatet är Microsoft</span><span class="sxs-lookup"><span data-stu-id="2127a-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="2127a-147">Lång</span><span class="sxs-lookup"><span data-stu-id="2127a-147">long</span></span> | <span data-ttu-id="2127a-148">Händelseidentifierare baserat på en upprepande räknare.</span><span class="sxs-lookup"><span data-stu-id="2127a-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="2127a-149">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp.</span><span class="sxs-lookup"><span data-stu-id="2127a-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="2127a-150">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="2127a-150">Related topics</span></span>
- [<span data-ttu-id="2127a-151">Proaktivt jakt efter hot</span><span class="sxs-lookup"><span data-stu-id="2127a-151">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2127a-152">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="2127a-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2127a-153">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="2127a-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2127a-154">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="2127a-154">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2127a-155">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="2127a-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2127a-156">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="2127a-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
