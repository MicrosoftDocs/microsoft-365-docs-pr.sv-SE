---
title: DeviceFileCertificateInfo-tabell i det avancerade schemat för sökning
description: Läs mer om filsigneringsinformation i tabellen DeviceFileCertificateInfo i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, digital signatur, certifikat, filsignering, DeviceFileCertificateInfo
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e35e8e86f6814a5f90a7921f71ccab7247fcc1bc
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931320"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="3434e-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="3434e-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3434e-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3434e-105">**Applies to:**</span></span>
- <span data-ttu-id="3434e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3434e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3434e-107">Tabellen `DeviceFileCertificateInfo` i det avancerade [utbildningsschemat](advanced-hunting-overview.md) innehåller information om filsigneringscertifikat.</span><span class="sxs-lookup"><span data-stu-id="3434e-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="3434e-108">I den här tabellen används data som hämtas från aktiviteter för certifikatverifiering som regelbundet utförs på filer på slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="3434e-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="3434e-109">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="3434e-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="3434e-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="3434e-110">Column name</span></span> | <span data-ttu-id="3434e-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="3434e-111">Data type</span></span> | <span data-ttu-id="3434e-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3434e-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="3434e-113">datetime</span><span class="sxs-lookup"><span data-stu-id="3434e-113">datetime</span></span> | <span data-ttu-id="3434e-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="3434e-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="3434e-115">sträng</span><span class="sxs-lookup"><span data-stu-id="3434e-115">string</span></span> | <span data-ttu-id="3434e-116">Unikt ID för datorn i tjänsten</span><span class="sxs-lookup"><span data-stu-id="3434e-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="3434e-117">sträng</span><span class="sxs-lookup"><span data-stu-id="3434e-117">string</span></span> | <span data-ttu-id="3434e-118">Fullständigt kvalificerat domännamn (FQDN) för datorn</span><span class="sxs-lookup"><span data-stu-id="3434e-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="3434e-119">sträng</span><span class="sxs-lookup"><span data-stu-id="3434e-119">string</span></span> | <span data-ttu-id="3434e-120">SHA-1 för den fil som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="3434e-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="3434e-121">boolesk</span><span class="sxs-lookup"><span data-stu-id="3434e-121">boolean</span></span> | <span data-ttu-id="3434e-122">Anger om filen är signerad</span><span class="sxs-lookup"><span data-stu-id="3434e-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="3434e-123">sträng</span><span class="sxs-lookup"><span data-stu-id="3434e-123">string</span></span> | <span data-ttu-id="3434e-124">Anger om signaturinformation har lästs som inbäddat innehåll i själva filen eller lästs från en extern katalogfil</span><span class="sxs-lookup"><span data-stu-id="3434e-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="3434e-125">sträng</span><span class="sxs-lookup"><span data-stu-id="3434e-125">string</span></span> | <span data-ttu-id="3434e-126">Information om den som signerar filen</span><span class="sxs-lookup"><span data-stu-id="3434e-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="3434e-127">sträng</span><span class="sxs-lookup"><span data-stu-id="3434e-127">string</span></span> | <span data-ttu-id="3434e-128">Unikt hashvärde som identifierar undertecknaren</span><span class="sxs-lookup"><span data-stu-id="3434e-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="3434e-129">sträng</span><span class="sxs-lookup"><span data-stu-id="3434e-129">string</span></span> | <span data-ttu-id="3434e-130">Information om den certifikatutfärdare som utfärdar certifikatutfärdaren</span><span class="sxs-lookup"><span data-stu-id="3434e-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="3434e-131">sträng</span><span class="sxs-lookup"><span data-stu-id="3434e-131">string</span></span> | <span data-ttu-id="3434e-132">Unikt hash-värde som identifierar den certifikatutfärdare som utfärdats (CA)</span><span class="sxs-lookup"><span data-stu-id="3434e-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="3434e-133">sträng</span><span class="sxs-lookup"><span data-stu-id="3434e-133">string</span></span> | <span data-ttu-id="3434e-134">Identifierare för certifikatet som är unikt för den utfärdar certifikatutfärdaren (CA)</span><span class="sxs-lookup"><span data-stu-id="3434e-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="3434e-135">sträng</span><span class="sxs-lookup"><span data-stu-id="3434e-135">string</span></span> |  <span data-ttu-id="3434e-136">JSON-matris med WEBBADRESSer till nätverksresurser som innehåller certifikat och CRL-listor (Certificate Revocation Lists)</span><span class="sxs-lookup"><span data-stu-id="3434e-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="3434e-137">datetime</span><span class="sxs-lookup"><span data-stu-id="3434e-137">datetime</span></span> | <span data-ttu-id="3434e-138">Datum och tid då certifikatet skapades</span><span class="sxs-lookup"><span data-stu-id="3434e-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="3434e-139">datetime</span><span class="sxs-lookup"><span data-stu-id="3434e-139">datetime</span></span> | <span data-ttu-id="3434e-140">Datum och tid då certifikatet har ställts in att upphöra</span><span class="sxs-lookup"><span data-stu-id="3434e-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="3434e-141">datetime</span><span class="sxs-lookup"><span data-stu-id="3434e-141">datetime</span></span> | <span data-ttu-id="3434e-142">Datum och tid då certifikatet kontrasignerades</span><span class="sxs-lookup"><span data-stu-id="3434e-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="3434e-143">boolesk</span><span class="sxs-lookup"><span data-stu-id="3434e-143">boolean</span></span> | <span data-ttu-id="3434e-144">Anger om filen är betrodd baserat på resultaten av WinVerifyTrust-funktionen som söker efter okänd rotcertifikatinformation, ogiltiga signaturer, återkallade certifikat och andra frågebara attribut</span><span class="sxs-lookup"><span data-stu-id="3434e-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="3434e-145">boolesk</span><span class="sxs-lookup"><span data-stu-id="3434e-145">boolean</span></span> | <span data-ttu-id="3434e-146">Anger om undertecknaren av rotcertifikatet är Microsoft</span><span class="sxs-lookup"><span data-stu-id="3434e-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="3434e-147">long</span><span class="sxs-lookup"><span data-stu-id="3434e-147">long</span></span> | <span data-ttu-id="3434e-148">Händelseidentifierare baserade på en återkommande räknare.</span><span class="sxs-lookup"><span data-stu-id="3434e-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="3434e-149">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp.</span><span class="sxs-lookup"><span data-stu-id="3434e-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="3434e-150">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="3434e-150">Related topics</span></span>
- [<span data-ttu-id="3434e-151">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="3434e-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3434e-152">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="3434e-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3434e-153">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="3434e-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3434e-154">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="3434e-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3434e-155">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="3434e-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3434e-156">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="3434e-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
