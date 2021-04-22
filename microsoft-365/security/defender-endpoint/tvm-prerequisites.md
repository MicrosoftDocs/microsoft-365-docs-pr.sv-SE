---
title: Krav & - hantering av hot och sårbarhet
description: Innan du börjar använda hantering av hot och hot bör du kontrollera att du har rätt konfigurationer och behörigheter.
keywords: villkor & säkerhetshanteringsbehörigheter förutsättningar, behörigheter för hantering av hot och sårbarhet, Microsoft Defender för slutpunkt-TVM-behörighetsförutsättningarna, sårbarhetshantering
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0df348e3a5564720468d95d7b23578f9dcad9294
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935191"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a>Krav & - hantering av hot och sårbarhet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Hantering av hot och sårbarhet](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Kontrollera att dina enheter:

- Introduceras till Microsoft Defender för Slutpunkt
- Kör [operativsystem och plattformar som stöds](tvm-supported-os.md)
- Ha följande obligatoriska uppdateringar installerade och distribuerade i nätverket för att förbättra utvärderingsfrekvensen för sårbarheter:

> Version | Säkerhetsuppdatering, KB-nummer och länk
> :---|:---
> Windows 10 Version 1709 | [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) och [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
> Windows 10 Version 1803 | [KB4493464](https://support.microsoft.com/help/4493464) och [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
> Windows 10 Version 1809 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> Windows 10 version 1903 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- Är onboarded to [Microsoft Intune and](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)  [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) to help remediate threats found by threat and vulnerability management. Om du använder Konfigurationshanteraren uppdaterar du konsolen till den senaste versionen.
    - **Obs!** Om Intune-anslutningen är aktiverad får du ett alternativ för att skapa en Intune-säkerhetsaktivitet när du skapar en åtgärdsbegäran. Det här alternativet visas inte om anslutningen inte har angetts.
- Ha minst en rekommendation för säkerhet som kan visas på sidan enhet
- Är märkta eller markerade som hanterade tillsammans

## <a name="relevant-permission-options"></a>Relevanta behörighetsalternativ

1. Logga in på Microsoft Defender Säkerhetscenter med ett konto med en tilldelad säkerhetsadministratör eller global administratörsroll.
2. I navigeringsfönstret väljer du **Inställningar > Roller**.

Mer information finns i [Skapa och hantera roller för rollbaserad åtkomstkontroll](user-roles.md)

### <a name="view-data"></a>Visa data

- **Säkerhetsåtgärder** – visa alla data i säkerhetsåtgärder i portalen
- **Hantering av hot och sårbarhet** – visa data om hot och sårbarhetshantering i portalen

### <a name="active-remediation-actions"></a>Aktiva åtgärdsåtgärder

- **Säkerhetsåtgärder** – Vidta svarsåtgärder, godkänna eller stänga väntande åtgärder, hantera tillåtna/blockerade listor för automatisering och indikatorer
- **Hantering av hot och sårbarhet – Undantagshantering** – Skapa nya undantag och hantera aktiva undantag
- **Hantering av hot och sårbarhet - Åtgärdshantering** - Skicka in nya åtgärdsförfrågningar, skapa ärenden och hantera befintliga åtgärdsaktiviteter

Mer information finns i [Behörighetsalternativ för RBAC](user-roles.md#permission-options)

## <a name="related-articles"></a>Relaterade artiklar

- [Översikt över hot- och sårbarhetshantering](next-gen-threat-and-vuln-mgt.md)
- [Operativsystem och plattformar som stöds](tvm-supported-os.md)
- [Tilldela enhetsvärde](tvm-assign-device-value.md)
- [Instrumentpanel för hantering av hot och hot](tvm-dashboard-insights.md)

