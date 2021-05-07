---
title: Läs mer om Microsofts Efterlevnadstillägg (förhandsversion)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Med Microsofts Efterlevnadstillägg utökas övervakning och kontroll av filaktiviteter och skyddsåtgärder mot Google Chrome-webbläsaren
ms.openlocfilehash: c8a5795b3be8b393fd3a934504449bf6db0c2f01
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162936"
---
# <a name="learn-about-the-microsoft-compliance-extension-preview"></a>Läs mer om Microsofts Efterlevnadstillägg (förhandsversion)

[Dataförlustskydd för slutpunkt (slutpunkt DLP)](endpoint-dlp-learn-about.md) utökar funktionerna för aktivitetsövervakning och skydd i [Microsoft 365 dataförlustskydd (DLP)](dlp-learn-about-dlp.md) till känsliga objekt som finns på Windows 10-enheter. När enheter har installerats i efterlevnadslösningar för Microsoft 365 blir informationen om vad användare gör med känsliga objekt synlig i [aktivitetsutforskaren](data-classification-activity-explorer.md) och du kan vidta skyddsåtgärder för dessa objekt via [DLP-principer](create-test-tune-dlp-policy.md).

När Microsofts efterlevnadstillägg har installerats på en Windows 10-enhet kan organisationer övervaka när en användare försöker komma åt eller ladda upp ett känsligt objekt till en molntjänst med hjälp av Google Chrome och vidta skyddsåtgärder via DLP.  

## <a name="activities-you-can-monitor-and-take-action-on"></a>Aktiviteter som du kan övervaka och vidta åtgärder för

Med Microsofts efterlevnadstillägg kan du granska och hantera följande typer av aktiviteter som användare gör med känsliga objekt på enheter med Windows 10.

aktivitet |beskrivning  | principåtgärder som stöds|
|---------|---------|---------|
|fil kopierad till molnet  | Identifierar när en användare försöker ladda upp ett känsligt objekt till en begränsad tjänstdomän via webbläsaren Chrome |granska, blockera|
|fil utskriven  |Identifierar när en användare försöker skriva ut ett känsligt objekt som är öppet i webbläsaren Chrome till en lokal skrivare eller nätverksskrivare |granska, blockera med åsidosättning, blockera|
|fil kopierad till Urklipp |Identifierar när en användare försöker kopiera information från ett känsligt objekt som visas i webbläsaren Chrome och klistrar sedan in den i ett annat program, en annan process eller ett annat objekt. |granska, blockera med åsidosättning, blockera|
|fil kopierad till flyttbar lagring    | Identifierar när en användare försöker kopiera ett känsligt objekt eller information från ett känsligt objekt som är öppet i webbläsaren Chrome till ett flyttbart medium eller USB-enhet |granska, blockera med åsidosättning, blockera|
|fil kopierad till nätverksresurs  |Identifierar när en användare försöker kopiera ett känsligt objekt eller information från ett känsligt objekt som är öppet i webbläsaren Chrome till en nätverksresurs eller mappad nätverksenhet.|granska, blockera med åsidosättning, blockera |

## <a name="deployment-process"></a>Distributionsprocess
1. [Komma igång med dataförlustskydd för slutpunkt](endpoint-dlp-getting-started.md)
2. [Registreringsverktyg och metoder för Windows 10-enheter](dlp-configure-endpoints.md)
3. [Installera tillägget på dina Windows 10-enheter](dlp-chrome-get-started.md)
4. [Skapa eller redigera DLP-principer](create-test-tune-dlp-policy.md) som begränsar uppladdning till molntjänst eller åtkomst av icke-tillåtet webbläsaråtgärder och tillämpa dem på dina Windows 10-enheter

## <a name="next-steps"></a>Nästa steg

Se [Komma igång med Microsofts Efterlevnadstillägg](dlp-chrome-get-started.md) för fullständiga distributionsprocedurer och scenarier.

## <a name="see-also"></a>Se även

- [Komma igång med Microsofts Efterlevnadstillägg](dlp-chrome-get-started.md)
- [Läs mer om dataförlustskydd för slutpunkt i Microsoft 365](endpoint-dlp-learn-about.md)
- [Komma igång med Microsoft dataförlustskydd för slutpunkt](endpoint-dlp-getting-started.md)
- [Använda Microsoft dataförlustskydd för slutpunkt](endpoint-dlp-using.md)
- [Mer information om dataförlustskydd](dlp-learn-about-dlp.md)
- [Skapa, testa och justera en DLP-princip](create-test-tune-dlp-policy.md)
- [Kom igång med Aktivitetsutforskaren](data-classification-activity-explorer.md)
- [Microsoft Defender för Endpoint](https://docs.microsoft.com/windows/security/threat-protection/)
- [Hantering av insiderrisk](insider-risk-management.md)
