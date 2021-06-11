---
title: Rapportera falska positiva eller falska negativa resultat efter automatiserad undersökning i Microsoft Defender för Office 365
description: Har något missats eller identifierats felaktigt av AIR i Microsoft Defender för Office 365? Lär dig hur du skickar falska positiva eller falska negativa tal till Microsoft för analys.
keywords: automatiserad, undersökning, avisering, utlösare, åtgärd, åtgärd, falsk positiv, falsk negativ
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
ms.prod: m365-security
ms.date: 01/29/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 287bd9cd4dda6ccb152e93908a409e036eab9cc7
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878886"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Så här rapporterar du falska positiva/negativa tal i automatiska undersöknings- och svarsfunktioner

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Om funktioner för automatiserad undersökning och svar [(AIR) Office 365](automated-investigation-response-office.md) har missat eller felaktigt identifierat något finns det åtgärder som ditt säkerhetsteam kan vidta för att åtgärda det. Sådana åtgärder omfattar:

- [Rapportera ett falskt positivt/negativt resultat till Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Justera aviseringar](#adjust-an-alert-to-prevent-false-positives-from-recurring) (vid behov). och
- [Ångra åtgärder som har vidtagits](#undo-a-remediation-action).

Använd den här artikeln som en guide.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Rapportera ett falskt positivt/negativt till Microsoft för analys

Om AIR i Microsoft Defender för Office 365 missade ett e-postmeddelande, en e-postbilaga, en URL-adress i ett e-postmeddelande eller en URL-adress i en Office-fil kan du skicka misstänkt skräppost, nätt många webbadresser och filer till [Microsoft för Office 365-skanning.](admin-submission.md)

Du kan också [skicka en fil till Microsoft för analys av skadlig programvara.](https://www.microsoft.com/wdsi/filesubmission)

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Justera en avisering för att förhindra att falska positiva resultat upprepas

Om en avisering utlöses av legitimt bruk eller om aviseringen är felaktig kan du hantera [aviseringar i Cloud App Security portalen.](/cloud-app-security/managing-alerts)

Om din organisation utöver Office 365 använder [Microsoft Defender](/windows/security/threat-protection) för Endpoint så behandlas en fil, IP-adress, URL eller domän som skadlig programvara på en enhet, även om det är säkert, så kan du skapa en anpassad indikator med åtgärden ["Tillåt"](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)för din enhet.

## <a name="undo-a-remediation-action"></a>Ångra en åtgärd

Om en åtgärd har vidtagits för ett e-postmeddelande, en e-postbilaga eller en URL och objektet egentligen inte är ett hot, kan säkerhetsåtgärdsteamet i de flesta fall ångra åtgärden och vidta åtgärder för att förhindra att meddelandet felaktigt visas som ett hot. Du kan antingen [använda Hotutforskaren](#undo-an-action-using-threat-explorer) [eller fliken Åtgärder för en undersökning](#undo-an-action-in-the-action-center) för att ångra en åtgärd.

> [!IMPORTANT]
> Kontrollera att du har nödvändiga behörigheter innan du försöker utföra följande uppgifter.

### <a name="undo-an-action-using-threat-explorer"></a>Ångra en åtgärd med hjälp av Hotutforskaren

Med Threat Explorer kan ditt säkerhetsåtgärdsteam hitta ett e-postmeddelande som påverkas av en åtgärd och eventuellt ångra åtgärden.

<br>

****

|Scenario|Ångra-alternativ|Mer information|
|---|---|---|
|Ett e-postmeddelande har dirigerats till en användares skräppostmapp|<ul><li>Flytta meddelandet till användarens Borttaget-mapp</li><li>Flytta meddelandet till användarens inkorg</li><li>Ta bort meddelandet</li></ul>|[Hitta och undersöka skadlig e-post som levererats i Office 365](investigate-malicious-email-that-was-delivered.md)|
|Ett e-postmeddelande eller en fil har satts i karantän|<ul><li>Släpp e-postmeddelandet eller filen</li><li> Ta bort e-postmeddelandet eller filen</li></ul>|[Hantera meddelanden i karantän som administratör](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a>Ångra en åtgärd i Åtgärdscenter

I Åtgärdscenter kan du se åtgärder som har vidtagits och eventuellt ångra åtgärden.

1. Gå till Microsoft 365 Defender-portalen ( <https://security.microsoft.com> ).
2. Välj Åtgärdscenter i **navigeringsfönstret.**
3. Välj fliken **Historik** för att visa listan över slutförda åtgärder.
4. Markera ett objekt. Den utfällna rutan öppnas.
5. Välj Ångra i den utfällade **rutan.** (Knappen Ångra finns bara för  åtgärder som kan ångras.)

## <a name="see-also"></a>Se även

- [Microsoft Defender för Office 365](defender-for-office-365.md)
- [Automatiserade undersökningar i Microsoft Defender för Office 365](office-365-air.md)
