---
title: Tabellen DeviceFileCertificateInfo i det avancerade sökschemat
description: Mer information om filsignering i tabellen DeviceFileCertificateInfo i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, Microsoft 365 Defender, microsoft 365, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, digital signatur, certifikat, filsignering, DeviceFileCertificateInfo
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
ms.openlocfilehash: 1f894f3fc8cff2113004ff9c9e34ec2ca0144799
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023219"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="411ec-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="411ec-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="411ec-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="411ec-105">**Applies to:**</span></span>
- <span data-ttu-id="411ec-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="411ec-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="411ec-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="411ec-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="411ec-108">Tabellen `DeviceFileCertificateInfo` i det avancerade schemat för [sökning](advanced-hunting-overview.md) innehåller information om filsigneringscertifikat.</span><span class="sxs-lookup"><span data-stu-id="411ec-108">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="411ec-109">I den här tabellen används data som inhämtats från aktiviteter för certifikatverifiering regelbundet som utförs på filer på slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="411ec-109">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="411ec-110">Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="411ec-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="411ec-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="411ec-111">Column name</span></span> | <span data-ttu-id="411ec-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="411ec-112">Data type</span></span> | <span data-ttu-id="411ec-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="411ec-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="411ec-114">datetime</span><span class="sxs-lookup"><span data-stu-id="411ec-114">datetime</span></span> | <span data-ttu-id="411ec-115">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="411ec-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="411ec-116">sträng</span><span class="sxs-lookup"><span data-stu-id="411ec-116">string</span></span> | <span data-ttu-id="411ec-117">Unikt ID för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="411ec-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="411ec-118">sträng</span><span class="sxs-lookup"><span data-stu-id="411ec-118">string</span></span> | <span data-ttu-id="411ec-119">Fullständigt kvalificerat domännamn (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="411ec-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="411ec-120">sträng</span><span class="sxs-lookup"><span data-stu-id="411ec-120">string</span></span> | <span data-ttu-id="411ec-121">SHA-1 för filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="411ec-121">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="411ec-122">boolesk</span><span class="sxs-lookup"><span data-stu-id="411ec-122">boolean</span></span> | <span data-ttu-id="411ec-123">Anger om filen är signerad</span><span class="sxs-lookup"><span data-stu-id="411ec-123">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="411ec-124">sträng</span><span class="sxs-lookup"><span data-stu-id="411ec-124">string</span></span> | <span data-ttu-id="411ec-125">Anger om signaturinformation har lästs som inbäddat innehåll i själva filen eller läst från en extern katalogfil</span><span class="sxs-lookup"><span data-stu-id="411ec-125">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="411ec-126">sträng</span><span class="sxs-lookup"><span data-stu-id="411ec-126">string</span></span> | <span data-ttu-id="411ec-127">Information om den som signerar filen</span><span class="sxs-lookup"><span data-stu-id="411ec-127">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="411ec-128">sträng</span><span class="sxs-lookup"><span data-stu-id="411ec-128">string</span></span> | <span data-ttu-id="411ec-129">Unikt hashvärde som identifierar undertecknaren</span><span class="sxs-lookup"><span data-stu-id="411ec-129">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="411ec-130">sträng</span><span class="sxs-lookup"><span data-stu-id="411ec-130">string</span></span> | <span data-ttu-id="411ec-131">Information om den utfärdar certifikatutfärdaren (CA)</span><span class="sxs-lookup"><span data-stu-id="411ec-131">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="411ec-132">sträng</span><span class="sxs-lookup"><span data-stu-id="411ec-132">string</span></span> | <span data-ttu-id="411ec-133">Unikt hash-värde som identifierar den certifikatutfärdare som utfärdar certifikatutfärdaren (CA)</span><span class="sxs-lookup"><span data-stu-id="411ec-133">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="411ec-134">sträng</span><span class="sxs-lookup"><span data-stu-id="411ec-134">string</span></span> | <span data-ttu-id="411ec-135">Identifierare för certifikatet som är unikt för den certifikatutfärdare som utfärdar certifikatet (CA)</span><span class="sxs-lookup"><span data-stu-id="411ec-135">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="411ec-136">sträng</span><span class="sxs-lookup"><span data-stu-id="411ec-136">string</span></span> |  <span data-ttu-id="411ec-137">JSON-matris med URL:er för nätverksresurser som innehåller certifikat och listor över återkallade certifikat (CRL)</span><span class="sxs-lookup"><span data-stu-id="411ec-137">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="411ec-138">datetime</span><span class="sxs-lookup"><span data-stu-id="411ec-138">datetime</span></span> | <span data-ttu-id="411ec-139">Datum och tid då certifikatet skapades</span><span class="sxs-lookup"><span data-stu-id="411ec-139">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="411ec-140">datetime</span><span class="sxs-lookup"><span data-stu-id="411ec-140">datetime</span></span> | <span data-ttu-id="411ec-141">Datum och tid då certifikatet är inställt på att upphöra</span><span class="sxs-lookup"><span data-stu-id="411ec-141">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="411ec-142">datetime</span><span class="sxs-lookup"><span data-stu-id="411ec-142">datetime</span></span> | <span data-ttu-id="411ec-143">Datum och tid då certifikatet var räknare</span><span class="sxs-lookup"><span data-stu-id="411ec-143">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="411ec-144">boolesk</span><span class="sxs-lookup"><span data-stu-id="411ec-144">boolean</span></span> | <span data-ttu-id="411ec-145">Anger om filen är betrodd baserat på resultaten av WinVerifyTrust-funktionen som söker efter okänd rotcertifikatinformation, ogiltiga signaturer, återkallade certifikat och andra tveksamma attribut</span><span class="sxs-lookup"><span data-stu-id="411ec-145">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="411ec-146">boolesk</span><span class="sxs-lookup"><span data-stu-id="411ec-146">boolean</span></span> | <span data-ttu-id="411ec-147">Anger om undertecknaren av rotcertifikatet är Microsoft</span><span class="sxs-lookup"><span data-stu-id="411ec-147">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="411ec-148">long</span><span class="sxs-lookup"><span data-stu-id="411ec-148">long</span></span> | <span data-ttu-id="411ec-149">Händelseidentifierare baserat på en räknare för upprepande händelser.</span><span class="sxs-lookup"><span data-stu-id="411ec-149">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="411ec-150">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp.</span><span class="sxs-lookup"><span data-stu-id="411ec-150">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="411ec-151">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="411ec-151">Related topics</span></span>
- [<span data-ttu-id="411ec-152">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="411ec-152">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="411ec-153">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="411ec-153">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="411ec-154">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="411ec-154">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="411ec-155">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="411ec-155">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="411ec-156">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="411ec-156">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="411ec-157">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="411ec-157">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
