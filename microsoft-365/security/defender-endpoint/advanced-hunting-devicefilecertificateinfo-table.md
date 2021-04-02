---
title: Tabellen DeviceFileCertificateInfo i det avancerade sökschemat
description: Mer information om filsignering i tabellen DeviceFileCertificateInfo i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, digital signature, certificate, file signing, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: f693c54828d8ede1d21167817f77b875ab5680ce
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499170"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="c20b7-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="c20b7-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c20b7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c20b7-105">**Applies to:**</span></span>
- [<span data-ttu-id="c20b7-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c20b7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="c20b7-107">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="c20b7-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c20b7-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="c20b7-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="c20b7-109">Tabellen `DeviceFileCertificateInfo` i det avancerade schemat för [sökning](advanced-hunting-overview.md) innehåller information om filsigneringscertifikat.</span><span class="sxs-lookup"><span data-stu-id="c20b7-109">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="c20b7-110">I den här tabellen används data som inhämtats från aktiviteter för certifikatverifiering regelbundet som utförs på filer på slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="c20b7-110">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="c20b7-111">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökningsschema.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="c20b7-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="c20b7-112">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="c20b7-112">Column name</span></span> | <span data-ttu-id="c20b7-113">Datatyp</span><span class="sxs-lookup"><span data-stu-id="c20b7-113">Data type</span></span> | <span data-ttu-id="c20b7-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c20b7-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c20b7-115">datetime</span><span class="sxs-lookup"><span data-stu-id="c20b7-115">datetime</span></span> | <span data-ttu-id="c20b7-116">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="c20b7-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="c20b7-117">sträng</span><span class="sxs-lookup"><span data-stu-id="c20b7-117">string</span></span> | <span data-ttu-id="c20b7-118">Unikt ID för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="c20b7-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c20b7-119">sträng</span><span class="sxs-lookup"><span data-stu-id="c20b7-119">string</span></span> | <span data-ttu-id="c20b7-120">Fullständigt kvalificerat domännamn (FQDN) för enheten</span><span class="sxs-lookup"><span data-stu-id="c20b7-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `SHA1` | <span data-ttu-id="c20b7-121">sträng</span><span class="sxs-lookup"><span data-stu-id="c20b7-121">string</span></span> | <span data-ttu-id="c20b7-122">SHA-1 för filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="c20b7-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="c20b7-123">boolesk</span><span class="sxs-lookup"><span data-stu-id="c20b7-123">boolean</span></span> | <span data-ttu-id="c20b7-124">Anger om filen är signerad</span><span class="sxs-lookup"><span data-stu-id="c20b7-124">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="c20b7-125">sträng</span><span class="sxs-lookup"><span data-stu-id="c20b7-125">string</span></span> | <span data-ttu-id="c20b7-126">Anger om signaturinformation har lästs som inbäddat innehåll i själva filen eller läst från en extern katalogfil</span><span class="sxs-lookup"><span data-stu-id="c20b7-126">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="c20b7-127">sträng</span><span class="sxs-lookup"><span data-stu-id="c20b7-127">string</span></span> | <span data-ttu-id="c20b7-128">Information om den som signerar filen</span><span class="sxs-lookup"><span data-stu-id="c20b7-128">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="c20b7-129">sträng</span><span class="sxs-lookup"><span data-stu-id="c20b7-129">string</span></span> | <span data-ttu-id="c20b7-130">Unikt hashvärde som identifierar undertecknaren</span><span class="sxs-lookup"><span data-stu-id="c20b7-130">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="c20b7-131">sträng</span><span class="sxs-lookup"><span data-stu-id="c20b7-131">string</span></span> | <span data-ttu-id="c20b7-132">Information om den utfärdar certifikatutfärdaren (CA)</span><span class="sxs-lookup"><span data-stu-id="c20b7-132">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="c20b7-133">sträng</span><span class="sxs-lookup"><span data-stu-id="c20b7-133">string</span></span> | <span data-ttu-id="c20b7-134">Unikt hash-värde som identifierar den certifikatutfärdare som utfärdar certifikatutfärdaren (CA)</span><span class="sxs-lookup"><span data-stu-id="c20b7-134">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="c20b7-135">sträng</span><span class="sxs-lookup"><span data-stu-id="c20b7-135">string</span></span> | <span data-ttu-id="c20b7-136">Identifierare för certifikatet som är unikt för den certifikatutfärdare som utfärdar certifikatet (CA)</span><span class="sxs-lookup"><span data-stu-id="c20b7-136">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="c20b7-137">sträng</span><span class="sxs-lookup"><span data-stu-id="c20b7-137">string</span></span> |  <span data-ttu-id="c20b7-138">JSON-matris med URL:er för nätverksresurser som innehåller certifikat och listor över återkallade certifikat (CRL)</span><span class="sxs-lookup"><span data-stu-id="c20b7-138">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="c20b7-139">datetime</span><span class="sxs-lookup"><span data-stu-id="c20b7-139">datetime</span></span> | <span data-ttu-id="c20b7-140">Datum och tid då certifikatet skapades</span><span class="sxs-lookup"><span data-stu-id="c20b7-140">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="c20b7-141">datetime</span><span class="sxs-lookup"><span data-stu-id="c20b7-141">datetime</span></span> | <span data-ttu-id="c20b7-142">Datum och tid då certifikatet är inställt på att upphöra</span><span class="sxs-lookup"><span data-stu-id="c20b7-142">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="c20b7-143">datetime</span><span class="sxs-lookup"><span data-stu-id="c20b7-143">datetime</span></span> | <span data-ttu-id="c20b7-144">Datum och tid då certifikatet var räknare</span><span class="sxs-lookup"><span data-stu-id="c20b7-144">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="c20b7-145">boolesk</span><span class="sxs-lookup"><span data-stu-id="c20b7-145">boolean</span></span> | <span data-ttu-id="c20b7-146">Anger om filen är betrodd baserat på resultaten av WinVerifyTrust-funktionen som söker efter okänd rotcertifikatinformation, ogiltiga signaturer, återkallade certifikat och andra tveksamma attribut</span><span class="sxs-lookup"><span data-stu-id="c20b7-146">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="c20b7-147">boolesk</span><span class="sxs-lookup"><span data-stu-id="c20b7-147">boolean</span></span> | <span data-ttu-id="c20b7-148">Anger om undertecknaren av rotcertifikatet är Microsoft</span><span class="sxs-lookup"><span data-stu-id="c20b7-148">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="c20b7-149">long</span><span class="sxs-lookup"><span data-stu-id="c20b7-149">long</span></span> | <span data-ttu-id="c20b7-150">Händelseidentifierare baserat på en räknare för upprepande händelser.</span><span class="sxs-lookup"><span data-stu-id="c20b7-150">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="c20b7-151">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp.</span><span class="sxs-lookup"><span data-stu-id="c20b7-151">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |


## <a name="related-topics"></a><span data-ttu-id="c20b7-152">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="c20b7-152">Related topics</span></span>
- [<span data-ttu-id="c20b7-153">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="c20b7-153">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c20b7-154">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="c20b7-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c20b7-155">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="c20b7-155">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
