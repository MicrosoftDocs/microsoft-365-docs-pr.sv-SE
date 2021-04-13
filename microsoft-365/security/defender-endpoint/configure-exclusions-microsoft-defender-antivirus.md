---
title: Konfigurera undantag för Microsoft Defender AV-skanningar
description: Du kan undanta filer (inklusive filer som ändrats av angivna processer) och mappar från att genomsökas av Microsoft Defender AV. Validera dina undantag med PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 47db9b4451a885c92ca4fda0f87f0150415d3338
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691508"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>Konfigurera och validera undantag för genomsökningar för Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan utesluta vissa filer, mappar, processer och process öppna filer från genomsökningar för Microsoft Defender Antivirus. Sådana undantag gäller för [schemalagda genomsökningar](scheduled-catch-up-scans-microsoft-defender-antivirus.md) [,](run-scan-microsoft-defender-antivirus.md)skanningar på begäran och [alltid realtidsskydd och övervakning.](configure-real-time-protection-microsoft-defender-antivirus.md) Undantag för process öppna filer gäller endast realtidsskydd.

## <a name="configure-and-validate-exclusions"></a>Konfigurera och validera undantag

Information om hur du konfigurerar och validerar undantag finns i följande avsnitt:

- [Konfigurera och validera undantag baserat på filnamn, filnamnstillägg och mappplats](configure-extension-file-exclusions-microsoft-defender-antivirus.md). Det här gör att du kan utesluta filer från genomsökningar från Microsoft Defender Antivirus baserat på deras filtillägg, filnamn eller plats.

- [Konfigurera och validera undantag för filer som öppnas med processer](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md). Det här gör att du kan utesluta filer från genomsökningar som har öppnats av en viss process.

## <a name="recommendations-for-defining-exclusions"></a>Rekommendationer för att definiera undantag

Om du definierar undantag sänks skyddet som erbjuds av Microsoft Defender Antivirus. Du bör alltid utvärdera riskerna som är associerade med att implementera undantag och du bör endast utesluta filer som du är säker på inte är skadliga.

Följande är en lista med rekommendationer som du bör tänka på när du definierar undantag:  

- Undantag är tekniskt ett skyddsgap – överväg alltid ytterligare åtgärder när du definierar undantag. Åtgärder kan vara så enkla som att se till att den undantagna platsen har lämpliga åtkomstkontrolllistor, granskningspolicy, bearbetas av en uppdaterad programvara osv.

- Granska undantagen med jämna mellanrum. Kontrollera om och tillämpa minskningarna som en del av granskningsprocessen.

- Helst bör du undvika att definiera proaktiva undantag. Exkludera till exempel inte något bara för att du tror att det kan vara ett problem i framtiden. Använd undantag endast för specifika problem – oftast kring prestanda eller ibland kring programkompatibilitet som undantag kan minimera.

- Granska ändringarna i undantagslistan. Säkerhetsadministratören bör behålla tillräckligt många sammanhang kring varför ett visst undantag har lagts till. Du bör kunna ge svar med specifika skäl till varför en viss sökväg uteslöts.

## <a name="related-articles"></a>Relaterade artiklar

- [Undantag för Microsoft Defender Antivirus i Windows Server 2016](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Vanliga misstag att undvika när du definierar undantag](common-exclusion-mistakes-microsoft-defender-antivirus.md)