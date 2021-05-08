---
title: Ställ in undantag för Microsoft Defender Antivirus genomsökningar
description: Du kan undanta filer (inklusive filer som ändrats av angivna processer) och mappar från att genomsökas Microsoft Defender Antivirus. Validera dina undantag med PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 7065aa7cd1975b2f5a38e79da8618ba3efdcdac5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275126"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>Konfigurera och validera undantag för Microsoft Defender Antivirus genomsökningar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan utesluta vissa filer, mappar, processer och process öppna filer Microsoft Defender Antivirus genomsökningar. Sådana undantag gäller för [schemalagda genomsökningar](scheduled-catch-up-scans-microsoft-defender-antivirus.md) [,](run-scan-microsoft-defender-antivirus.md)skanningar på begäran och [alltid realtidsskydd och övervakning.](configure-real-time-protection-microsoft-defender-antivirus.md) Undantag för process öppna filer gäller endast realtidsskydd.

## <a name="configure-and-validate-exclusions"></a>Konfigurera och validera undantag

Information om hur du konfigurerar och validerar undantag finns i följande avsnitt:

- [Konfigurera och validera undantag baserat på filnamn, filnamnstillägg och mappplats](configure-extension-file-exclusions-microsoft-defender-antivirus.md). Du kan utesluta filer Microsoft Defender Antivirus genomsökningar baserat på deras filnamnstillägg, filnamn eller plats.

- [Konfigurera och validera undantag för filer som öppnas med processer](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md). Du kan utesluta filer från genomsökningar som har öppnats genom en viss process.

## <a name="recommendations-for-defining-exclusions"></a>Rekommendationer för att definiera undantag

> [!IMPORTANT]
> Microsoft Defender Antivirus omfattar många automatiska undantag baserade på kända operativsystemsbeteenden och vanliga hanteringsfiler, till exempel de som används i företagshantering, databashantering och andra företagsscenarier och situationer.  
> 
> Om du definierar undantag sänks det skydd som Microsoft Defender Antivirus. Du bör alltid utvärdera riskerna som är associerade med att implementera undantag och du bör endast utesluta filer som du är säker på inte är skadliga.

Tänk på följande när du definierar undantag:  

- Undantag är tekniskt sett ett skyddsgap. Överväg alltid åtgärder när du definierar undantag. Andra åtgärder kan vara så enkla som att se till att den undantagna platsen har lämpliga åtkomstkontrolllistor, granskningspolicy, bearbetas av en uppdaterad programvara osv.

- Granska undantagen med jämna mellanrum. Kontrollera och tillämpa minskningarna på nytt under granskningsprocessen.

- Undvik helst att definiera undantag som avser att vara proaktiva. Exkludera till exempel inte något bara för att du tror att det kan vara ett problem i framtiden. Använd undantag endast för specifika problem, till exempel de som rör prestanda eller programkompatibilitet som undantag kan minimera.

- Granska ändringarna i undantagslistan. Säkerhetsadministratören bör behålla tillräckligt många sammanhang kring varför ett visst undantag har lagts till. Du bör kunna ge svar med specifika skäl till varför en viss sökväg uteslöts.

## <a name="related-articles"></a>Relaterade artiklar

- [Microsoft Defender Antivirus undantag i Windows Server 2016](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Vanliga misstag att undvika när man definierar undantag](common-exclusion-mistakes-microsoft-defender-antivirus.md)
