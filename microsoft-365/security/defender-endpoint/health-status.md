---
title: Undersöka problem med agenthälsa
description: Lär dig mer om de värden som returneras när du kör hälsokommandot mdatp
keywords: mdatp-status, kommando, hälsa, status, kommando, onboarding-status
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: acc75a931cb14a7aab729c09a7b835fb9f26d1d1
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281306"
---
# <a name="investigate-agent-health-issues"></a>Undersöka problem med agenthälsa

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Följande tabell innehåller information om de värden som returneras när du kör `mdatp health` kommandot och deras motsvarande beskrivningar.

| Värde | Beskrivning |
|-|-|
| automatic_definition_update_enabled | Sant om automatiska uppdateringar av antivirusdefinitioner är aktiverade, annars falskt. |
|  cloud_automatic_sample_submission_consent | Aktuellt exempel på sändningsnivå. Kan vara något av följande värden:     <br><br>  - **Inga**: Inga misstänkta exempel skickas till Microsoft.  <br> <br>     - **Valv**: Endast misstänkta exempel som inte innehåller personligt identifierbar information skickas automatiskt. Det här är standardvärdet för den här inställningen.    <br> <br>   - **Alla**: Alla misstänkta exempel skickas till Microsoft.   |
| cloud_diagnostic_enabled | Sant om valfri insamling av diagnostikdata är aktiverat, annars falskt. Mer information om Defender för Endpoint och andra produkter och tjänster som Microsoft Defender Antivirus och Windows 10 finns i [Microsofts sekretesspolicy.](https://go.microsoft.com/fwlink/?linkid=827576) |
| cloud_enabled | Sant om moln levererat skydd är aktiverat, annars falskt. |
| conflicting_applications | Lista över program som eventuellt står i konflikt med Microsoft Defender för Endpoint. Den här listan innehåller, men är inte begränsad till, andra säkerhetsprodukter och andra program som kan orsaka kompatibilitetsproblem. |
| definitions_status | Status för antivirusdefinitioner. |
| definitions_updated | Datum och tid för den senaste uppdateringen av antivirusdefinitionen. |
| definitions_updated_minutes_ago | Antal minuter sedan den senaste uppdateringen av antivirusdefinitionen. |
| definitions_version | Antivirusdefinitionsversion. |
| edr_client_version | Version av Identifiering och åtgärd på slutpunkt som körs på enheten. |
| edr_configuration_version | Identifiering och åtgärd på slutpunkt konfigurationsversion. |
| edr_device_tags | Lista med taggar kopplade till enheten. |
| edr_group_ids | Grupp-ID som enheten är associerad med. |
| edr_machine_id | Enhetsidentifierare som används i Microsoft Defender Säkerhetscenter. |
| engine_version | Version av antivirusmotorn. |
| felfri | Sant om produkten är felfri, annars falskt. |
| licensierad | Sant om enheten är onboarded till en klientorganisation, annars falskt. |
| log_level | Aktuell loggnivå för produkten. |
| machine_guid | Unikt datoridentifierare som används av antiviruskomponenten. |
| network_protection_status                 | Status för nätverksskyddskomponenten (endast macOS). Kan vara något av följande värden:       <br> <br>- **start** – nätverksskyddet startar  <br> <br>     - **failed_to_start** – Det gick inte att starta nätverksskyddet på grund av ett fel   <br> <br>    - **startad** – nätverksskydd körs för närvarande på enheten     <br> <br>  - **omstart –** nätverksskyddet startar för närvarande om   <br> <br>    - **stoppa** – nätverksskyddet stoppas     <br> <br>  - **stoppad** – Nätverksskyddet körs inte |
| org_id | Organisation som enheten är onboarded till. Om enheten ännu inte är tillgänglig för någon organisation skrivs den här ut inte ut. Mer information om onboarding finns i [Onboard to Microsoft Defender för Endpoint](onboarding.md). |
| passive_mode_enabled | Sant om antiviruskomponenten är inställd på att köras i passiv form, annars falskt. |
| product_expiration | Datum och tid då den aktuella produktversionen når slutet av supporten. |
| real_time_protection_available | Sant om komponenten med realtidsskydd är felfri, annars falskt. |
| real_time_protection_enabled | Sant om antivirusskydd i realtid är aktiverat, annars falskt. |
| real_time_protection_subsystem | Undersystem som används för realtidsskydd. Om realtidsskyddet inte fungerar som förväntat skrivs det här ut inte ut. |
| release_ring | Släpp uppringning. Mer information finns i   [Distributionsringar](deployment-rings.md). |