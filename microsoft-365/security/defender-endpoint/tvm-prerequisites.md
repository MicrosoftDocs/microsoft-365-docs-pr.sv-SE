---
title: Krav & behörigheter – Hantering av hot och säkerhetsrisker
description: Innan du börjar Hantering av hot och säkerhetsrisker bör du kontrollera att du har rätt konfigurationer och behörigheter.
keywords: behörighet & hantering av säkerhetsrisker, behörighetsbehörigheter Hantering av hot och säkerhetsrisker, Microsoft Defender för slutpunkt-TVM-behörighetskrav och hantering av säkerhetsrisker
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
ms.openlocfilehash: c0544665ea4e9b1ceafa645a2dcc96a224b0c242
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843956"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a>Krav & behörigheter – Hantering av hot och säkerhetsrisker

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Hot och hantering av säkerhetsrisker](next-gen-threat-and-vuln-mgt.md)
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
> Windows 10 Version 1903 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- Förs över [till Microsoft Intune](/mem/intune/fundamentals/what-is-intune) och [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) för att hjälpa till att åtgärda hot som Hantering av hot och säkerhetsrisker. Om du använder Konfigurationshanteraren uppdaterar du konsolen till den senaste versionen.
    - **Obs!** Om Intune-anslutningen är aktiverad får du ett alternativ för att skapa en Intune-säkerhetsaktivitet när du skapar en åtgärdsbegäran. Det här alternativet visas inte om anslutningen inte har angetts.
- Ha minst en rekommendation för säkerhet som kan visas på sidan enhet
- Är märkta eller markerade som hanterade tillsammans

## <a name="relevant-permission-options"></a>Relevanta behörighetsalternativ

1. Logga in på Microsoft Defender Säkerhetscenter konto med en tilldelad säkerhetsadministratör eller global administratörsroll.
2. I navigeringsfönstret väljer du **Inställningar > Roller**.

Mer information finns i [Skapa och hantera roller för rollbaserad åtkomstkontroll](user-roles.md)

### <a name="view-data"></a>Visa data

- **Säkerhetsåtgärder** – visa alla data i säkerhetsåtgärder i portalen
- **Hot och hantering av säkerhetsrisker** – Hantering av hot och säkerhetsrisker data i portalen

### <a name="active-remediation-actions"></a>Aktiva åtgärdsåtgärder

- **Säkerhetsåtgärder** – Vidta svarsåtgärder, godkänna eller stänga väntande åtgärder, hantera tillåtna/blockerade listor för automatisering och indikatorer
- **Hot och hantering av säkerhetsrisker – Undantagshantering** – Skapa nya undantag och hantera aktiva undantag
- **Hot och hantering av säkerhetsrisker - Åtgärdshantering** - Skicka in nya begäran om åtgärder, skapa ärenden och hantera befintliga åtgärdsaktiviteter

Mer information finns i [Behörighetsalternativ för RBAC](user-roles.md#permission-options)

## <a name="related-articles"></a>Relaterade artiklar

- [Översikt över hantering av säkerhetsrisker hot och hot](next-gen-threat-and-vuln-mgt.md)
- [Operativsystem och plattformar som stöds](tvm-supported-os.md)
- [Tilldela enhetsvärde](tvm-assign-device-value.md)
- [Hot och hantering av säkerhetsrisker instrumentpanel](tvm-dashboard-insights.md)

