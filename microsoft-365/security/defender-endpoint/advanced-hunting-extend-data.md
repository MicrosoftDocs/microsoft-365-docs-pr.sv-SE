---
title: Utöka den avancerade söktäckningen med rätt inställningar
description: Kontrollera granskningsinställningarna på Windows-enheter och andra inställningar för att se till att du får den mest omfattande informationen under avancerad sökning
keywords: avancerad sökning, incident, pivot, entitet, granskningsinställningar, användarkontohantering, hantering av säkerhetsgrupper, hot efter hot, sökning efter cyberhot, sökning, fråga, telemetri, mdatp, Microsoft Defender ATP, Microsoft Defender för slutpunkt, Windows Defender, Windows Defender ATP, Windows Defender Avancerat skydd
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
ms.date: 10/10/2020
ms.technology: mde
ms.openlocfilehash: ea2524cb214d3cf7c784162a472722727cf0d57c
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500617"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a><span data-ttu-id="b1c60-104">Utöka den avancerade söktäckningen med rätt inställningar</span><span class="sxs-lookup"><span data-stu-id="b1c60-104">Extend advanced hunting coverage with the right settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b1c60-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b1c60-105">**Applies to:**</span></span>
- [<span data-ttu-id="b1c60-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="b1c60-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<span data-ttu-id="b1c60-107">[Avancerad sökning](advanced-hunting-overview.md) är beroende av data från hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="b1c60-107">[Advanced hunting](advanced-hunting-overview.md) relies on data coming from across your organization.</span></span> <span data-ttu-id="b1c60-108">För att få så omfattande data som möjligt bör du kontrollera att du har rätt inställningar i motsvarande datakällor.</span><span class="sxs-lookup"><span data-stu-id="b1c60-108">To get the most comprehensive data possible, ensure that you have the correct settings in the corresponding data sources.</span></span>

## <a name="advanced-security-auditing-on-windows-devices"></a><span data-ttu-id="b1c60-109">Avancerad säkerhetsgranskning på Windows-enheter</span><span class="sxs-lookup"><span data-stu-id="b1c60-109">Advanced security auditing on Windows devices</span></span>

<span data-ttu-id="b1c60-110">Aktivera de här avancerade granskningsinställningarna för att säkerställa att du får data om aktiviteter på dina enheter, inklusive lokal kontohantering, hantering av lokala säkerhetsgrupper och skapande av tjänster.</span><span class="sxs-lookup"><span data-stu-id="b1c60-110">Turn on these advanced auditing settings to ensure you get data about activities on your devices, including local account management, local security group management, and service creation.</span></span>

<span data-ttu-id="b1c60-111">Data</span><span class="sxs-lookup"><span data-stu-id="b1c60-111">Data</span></span> | <span data-ttu-id="b1c60-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b1c60-112">Description</span></span> | <span data-ttu-id="b1c60-113">Schematabell</span><span class="sxs-lookup"><span data-stu-id="b1c60-113">Schema table</span></span> | <span data-ttu-id="b1c60-114">Så här konfigurerar du</span><span class="sxs-lookup"><span data-stu-id="b1c60-114">How to configure</span></span>
-|-|-|-
<span data-ttu-id="b1c60-115">Kontohantering</span><span class="sxs-lookup"><span data-stu-id="b1c60-115">Account management</span></span> | <span data-ttu-id="b1c60-116">Händelser som skapats med olika `ActionType` värden som anger när ett lokalt konto skapas, tas bort och andra kontorelaterade aktiviteter</span><span class="sxs-lookup"><span data-stu-id="b1c60-116">Events captured as various `ActionType` values indicating local account creation, deletion, and other account-related activities</span></span> | [<span data-ttu-id="b1c60-117">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="b1c60-117">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="b1c60-118">– Distribuera en princip för avancerad säkerhetsgranskning: [Hantera användarkonton](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span><span class="sxs-lookup"><span data-stu-id="b1c60-118">- Deploy an advanced security audit policy: [Audit User Account Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span></span><br> <span data-ttu-id="b1c60-119">- [Läs mer om avancerade principer för säkerhetsgranskning](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="b1c60-119">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="b1c60-120">Hantering av säkerhetsgrupper</span><span class="sxs-lookup"><span data-stu-id="b1c60-120">Security group management</span></span> | <span data-ttu-id="b1c60-121">Händelser som fångas som olika `ActionType` värden som anger att lokala säkerhetsgrupper skapas och andra aktiviteter för lokal grupphantering</span><span class="sxs-lookup"><span data-stu-id="b1c60-121">Events captured as various `ActionType` values indicating local security group creation and other local group management activities</span></span> | [<span data-ttu-id="b1c60-122">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="b1c60-122">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="b1c60-123">- Distribuera en princip för avancerad säkerhetsgranskning: [Granskning av grupphantering för säkerhetsgrupper](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span><span class="sxs-lookup"><span data-stu-id="b1c60-123">- Deploy an advanced security audit policy: [Audit Security Group Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span></span><br> <span data-ttu-id="b1c60-124">- [Läs mer om avancerade principer för säkerhetsgranskning](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="b1c60-124">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="b1c60-125">Tjänstinstallation</span><span class="sxs-lookup"><span data-stu-id="b1c60-125">Service installation</span></span> | <span data-ttu-id="b1c60-126">Händelser som fångats `ActionType` med värdet , som anger att en tjänst har `ServiceInstalled` skapats</span><span class="sxs-lookup"><span data-stu-id="b1c60-126">Events captured with the `ActionType` value `ServiceInstalled`, indicating that a service has been created</span></span> | [<span data-ttu-id="b1c60-127">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="b1c60-127">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="b1c60-128">- Distribuera en princip för avancerad säkerhetsgranskning: [Granskningssäkerhetssystemtillägg](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span><span class="sxs-lookup"><span data-stu-id="b1c60-128">- Deploy an advanced security audit policy: [Audit Security System Extension](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span></span><br> <span data-ttu-id="b1c60-129">- [Läs mer om avancerade principer för säkerhetsgranskning](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="b1c60-129">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>

## <a name="related-topics"></a><span data-ttu-id="b1c60-130">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="b1c60-130">Related topics</span></span>

- [<span data-ttu-id="b1c60-131">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="b1c60-131">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b1c60-132">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="b1c60-132">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b1c60-133">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="b1c60-133">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="b1c60-134">Arbeta med frågeresultat</span><span class="sxs-lookup"><span data-stu-id="b1c60-134">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="b1c60-135">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="b1c60-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b1c60-136">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="b1c60-136">Custom detections overview</span></span>](overview-custom-detections.md)
