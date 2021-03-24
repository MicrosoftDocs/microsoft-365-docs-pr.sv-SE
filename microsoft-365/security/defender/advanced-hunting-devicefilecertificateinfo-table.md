---
title: Tabellen DeviceFileCertificateInfo i det avancerade sökschemat
description: Mer information om filsignering i tabellen DeviceFileCertificateInfo i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, digital signature, certificate, file signing, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 00e10c84c4bcb20f2e018bf05033b5b2235fd9ae
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071577"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="d2837-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="d2837-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d2837-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="d2837-105">**Applies to:**</span></span>
- <span data-ttu-id="d2837-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d2837-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d2837-107">Tabellen `DeviceFileCertificateInfo` i det avancerade schemat för [sökning](advanced-hunting-overview.md) innehåller information om filsigneringscertifikat.</span><span class="sxs-lookup"><span data-stu-id="d2837-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="d2837-108">I den här tabellen används data som inhämtats från aktiviteter för certifikatverifiering regelbundet som utförs på filer på slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="d2837-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="d2837-109">Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="d2837-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d2837-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="d2837-110">Column name</span></span> | <span data-ttu-id="d2837-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="d2837-111">Data type</span></span> | <span data-ttu-id="d2837-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d2837-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d2837-113">datetime</span><span class="sxs-lookup"><span data-stu-id="d2837-113">datetime</span></span> | <span data-ttu-id="d2837-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="d2837-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="d2837-115">sträng</span><span class="sxs-lookup"><span data-stu-id="d2837-115">string</span></span> | <span data-ttu-id="d2837-116">Unikt ID för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="d2837-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d2837-117">sträng</span><span class="sxs-lookup"><span data-stu-id="d2837-117">string</span></span> | <span data-ttu-id="d2837-118">Fullständigt kvalificerat domännamn (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="d2837-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="d2837-119">sträng</span><span class="sxs-lookup"><span data-stu-id="d2837-119">string</span></span> | <span data-ttu-id="d2837-120">SHA-1 för filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="d2837-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="d2837-121">boolesk</span><span class="sxs-lookup"><span data-stu-id="d2837-121">boolean</span></span> | <span data-ttu-id="d2837-122">Anger om filen är signerad</span><span class="sxs-lookup"><span data-stu-id="d2837-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="d2837-123">sträng</span><span class="sxs-lookup"><span data-stu-id="d2837-123">string</span></span> | <span data-ttu-id="d2837-124">Anger om signaturinformation har lästs som inbäddat innehåll i själva filen eller läst från en extern katalogfil</span><span class="sxs-lookup"><span data-stu-id="d2837-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="d2837-125">sträng</span><span class="sxs-lookup"><span data-stu-id="d2837-125">string</span></span> | <span data-ttu-id="d2837-126">Information om den som signerar filen</span><span class="sxs-lookup"><span data-stu-id="d2837-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="d2837-127">sträng</span><span class="sxs-lookup"><span data-stu-id="d2837-127">string</span></span> | <span data-ttu-id="d2837-128">Unikt hashvärde som identifierar undertecknaren</span><span class="sxs-lookup"><span data-stu-id="d2837-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="d2837-129">sträng</span><span class="sxs-lookup"><span data-stu-id="d2837-129">string</span></span> | <span data-ttu-id="d2837-130">Information om den utfärdar certifikatutfärdaren (CA)</span><span class="sxs-lookup"><span data-stu-id="d2837-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="d2837-131">sträng</span><span class="sxs-lookup"><span data-stu-id="d2837-131">string</span></span> | <span data-ttu-id="d2837-132">Unikt hash-värde som identifierar den certifikatutfärdare som utfärdar certifikatutfärdaren (CA)</span><span class="sxs-lookup"><span data-stu-id="d2837-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="d2837-133">sträng</span><span class="sxs-lookup"><span data-stu-id="d2837-133">string</span></span> | <span data-ttu-id="d2837-134">Identifierare för certifikatet som är unikt för den certifikatutfärdare som utfärdar certifikatet (CA)</span><span class="sxs-lookup"><span data-stu-id="d2837-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="d2837-135">sträng</span><span class="sxs-lookup"><span data-stu-id="d2837-135">string</span></span> |  <span data-ttu-id="d2837-136">JSON-matris med URL:er för nätverksresurser som innehåller certifikat och listor över återkallade certifikat (CRL)</span><span class="sxs-lookup"><span data-stu-id="d2837-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="d2837-137">datetime</span><span class="sxs-lookup"><span data-stu-id="d2837-137">datetime</span></span> | <span data-ttu-id="d2837-138">Datum och tid då certifikatet skapades</span><span class="sxs-lookup"><span data-stu-id="d2837-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="d2837-139">datetime</span><span class="sxs-lookup"><span data-stu-id="d2837-139">datetime</span></span> | <span data-ttu-id="d2837-140">Datum och tid då certifikatet är inställt på att upphöra</span><span class="sxs-lookup"><span data-stu-id="d2837-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="d2837-141">datetime</span><span class="sxs-lookup"><span data-stu-id="d2837-141">datetime</span></span> | <span data-ttu-id="d2837-142">Datum och tid då certifikatet var räknare</span><span class="sxs-lookup"><span data-stu-id="d2837-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="d2837-143">boolesk</span><span class="sxs-lookup"><span data-stu-id="d2837-143">boolean</span></span> | <span data-ttu-id="d2837-144">Anger om filen är betrodd baserat på resultaten av WinVerifyTrust-funktionen som söker efter okänd rotcertifikatinformation, ogiltiga signaturer, återkallade certifikat och andra tveksamma attribut</span><span class="sxs-lookup"><span data-stu-id="d2837-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="d2837-145">boolesk</span><span class="sxs-lookup"><span data-stu-id="d2837-145">boolean</span></span> | <span data-ttu-id="d2837-146">Anger om undertecknaren av rotcertifikatet är Microsoft</span><span class="sxs-lookup"><span data-stu-id="d2837-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="d2837-147">long</span><span class="sxs-lookup"><span data-stu-id="d2837-147">long</span></span> | <span data-ttu-id="d2837-148">Händelseidentifierare baserat på en räknare för upprepande händelser.</span><span class="sxs-lookup"><span data-stu-id="d2837-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="d2837-149">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp.</span><span class="sxs-lookup"><span data-stu-id="d2837-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="d2837-150">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="d2837-150">Related topics</span></span>
- [<span data-ttu-id="d2837-151">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="d2837-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d2837-152">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="d2837-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d2837-153">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="d2837-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d2837-154">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="d2837-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d2837-155">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="d2837-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d2837-156">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="d2837-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
