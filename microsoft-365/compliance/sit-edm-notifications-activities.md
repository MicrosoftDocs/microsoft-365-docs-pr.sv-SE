---
title: Skapa meddelande för exakta datamatchningsaktiviteter (förhandsversion)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Lär dig att skapa aviseringar för exakta datamatchningsaktiviteter.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2e2f67ef0f276211483519bd5e246e4e041b2b15
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162037"
---
# <a name="create-notifications-for-exact-data-match-activities-preview"></a>Skapa meddelande för exakta datamatchningsaktiviteter (förhandsversion)

När du [skapar anpassade typer av känslig information med exakt datamatchning (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) finns det ett antal aktiviteter som har skapats i [granskningsloggen](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log). Du kan använda cmdleten [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) PowerShell för att skapa meddelande som visar när dessa aktiviteter inträffar:

- CreateSchema
- EditSchema
- RemoveSchema
- UploadDataFailed
- UploadDataCompleted

> [!NOTE]
> Möjligheten att skapa meddelande för EDM-aktiviteter är endast tillgänglig för World Wide- och GCC-moln.

## <a name="pre-requisites"></a>Förutsättningar

Det konto du använder måste vara något av följande:

- en global administratör
- efterlevnadsadministratör
- Exchange Online-administratör

Läs mer om DLP-behörigheter i [Behörigheter](data-loss-prevention-policies.md#permissions).

EDM-baserad klassificering ingår i dessa prenumerationer

- Office 365 E5
- Microsoft 365 E5
- Microsoft 365 E5 Compliance
- Microsoft E5/A5 Information Protection och styrning

Läs mer om DLP-licensiering i [licensieringsvägledning för Microsoft 365 för säkerhet och efterlevnad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)

## <a name="configure-notifications-for-edm-activities"></a>Konfigurera meddelande för EDM-aktiviteter

1. Ansluta till [Säkerhets- och efterlevnadscenter PowerShell](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps) 

2. Kör cmdleten `New-ProtectionAlert` med den aktivitet som du vill skapa meddelande för.  Om du, till exempel, vill få ett meddelande när åtgärden inträffade i **UploadDataCompleted**, kör

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

för de **UploadDataFailed** kan du köra

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a>Relaterade artiklar

- [Skapa anpassade typer av känslig information med exakt datamatchning U(EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps)