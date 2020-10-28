---
title: Det här kommer att komma till Microsofts säkra Poäng
description: Här beskrivs vilka nya ändringar som kommer till Microsofts säkra poäng i säkerhets Center för Microsoft 365.
keywords: Microsoft säkra poäng, säkra poäng, Office 365 säkra poäng, säkerhets poäng, Microsoft 365 säkerhets Center, förbättrings åtgärder
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 82ec67cae86525c055b2232667cccb603830d15f
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779254"
---
# <a name="whats-coming-to-microsoft-secure-score"></a>Det här kommer att komma till Microsofts säkra Poäng

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Vi håller på att göra några ändringar i närmaste framtid och gör [Microsoft säkert Poäng](microsoft-secure-score.md) en bättre representant för din säkerhets Posture och bättre användbarhet. Ditt Poäng och högsta möjliga poäng kan förändras.

## <a name="proposed-changes"></a>Föreslagna ändringar

### <a name="november-2020"></a>November 2020

Ta bort möjligheten att skapa ServiceNow biljetter genom säkra poäng genom att gå till **dela > ServiceNow** .

- För hands perioden för ServiceNow-kopplingen är slut. Den här funktionen kommer inte längre att vara tillgänglig i slutet av 2020. Tack för din feedback och fortsatta support medan vi bestämmer nästa steg.

Lägga till 18 förbättrings åtgärder relaterade till Microsoft Defender för slut punkt (tidigare Microsoft Defender ATP):

Rekommenderade problem med attack ytan (ASR):
- Blockera körbart innehåll från e-postklient och WebPost
- Blockera alla Office-program från att skapa underordnade processer
- Blockera Office-program från att skapa körbart innehåll
- Blockera Office-program från att injicera kod i andra processer
- Blockera java script eller VBScript från att starta hämtat körbart innehåll
- Blockera körning av potentiellt Obfuscated-skript
- Blockera Win32 API-samtal från Office-makron
- Blockera körbara filer från att köras såvida de inte uppfyller villkoren för ett förekomst-, ålder eller betrott lista
- Använd avancerat skydd mot utpressnings tro Jan
- Blockera autentiseringsuppgifter som stjäls från Windows Local Security Authority Subsystem (lsass.exe)
- Blockera skapande av processer från PSExec-och WMI-kommandon
- Blockera icke-betrodda och osignerade processer som körs från USB
- Blockera Office-kommunikationsprogram från att skapa underordnade processer
- Blockera Adobe Reader från att skapa underordnade processer
- Blockera beständighet via WMI-prenumeration

Service rekommendationer:
- Åtgärda den icke-citerade tjänst Sök vägen för Windows-tjänster
- Ändra sökvägen till den körbara filen till en gemensam skyddad plats
- Ändra tjänst konto för att undvika cachelagrat lösen ord i Windows-registret

## <a name="related-resources"></a>Relaterade resurser

- [Översikt över Microsofts säkra Poäng](microsoft-secure-score.md)
- [Utvärdera säkerhets genom övergå molnet](microsoft-secure-score-improvement-actions.md)
- [Spåra din Microsoft säkra Poäng historik och uppfylla målen](microsoft-secure-score-history-metrics-trends.md)
- [Vad är nytt](microsoft-secure-score-whats-new.md)
