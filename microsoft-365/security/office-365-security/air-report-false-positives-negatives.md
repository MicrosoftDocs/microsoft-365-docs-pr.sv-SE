---
title: Rapportera falska positiva eller falska negativa tal efter en automatiserad undersökning i Microsoft Defender för Office 365
description: Har något missats eller identifierats felaktigt av AIR i Microsoft Defender för Office 365? Lär dig hur du skickar falska positiva eller falska negativa tal till Microsoft för analys.
keywords: automatiserad, undersökning, avisering, utlösare, åtgärd, falsk positiv, falsk negativ
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 8a91a55d9598b5e780474315ddf1f7019e593fed
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406168"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Hur du rapporterar falska positiva/negativa tal i automatiserad undersökning och svarsfunktioner

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Om funktioner för automatisk undersökning och svar [(AIR) i Office 365](automated-investigation-response-office.md) missade eller felaktigt identifierat något finns det åtgärder som teamet kan vidta för att åtgärda det. Sådana åtgärder omfattar:

- [Rapportera ett falskt positivt/negativt värde till Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Justera aviseringar](#adjust-an-alert-to-prevent-false-positives-from-recurring) (vid behov). och
- [Ångra åtgärder som har vidtas.](#undo-a-remediation-action)

Använd den här artikeln som en guide.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Rapportera ett falskt positivt/negativt till Microsoft för analys

Om AIR i Microsoft Defender för Office 365 missade ett e-postmeddelande, en e-postbilaga, en URL-adress i ett e-postmeddelande eller en URL-adress i en Office-fil kan du skicka misstänkt [skräppost, phish, URL:er](admin-submission.md)och filer till Microsoft för Office 365-skanning.

Du kan också [skicka en fil till Microsoft för analys av skadlig programvara.](https://www.microsoft.com/wdsi/filesubmission)

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Justera en avisering för att förhindra att falska positiva resultat upprepas

Om en avisering utlöses av legitimt bruk eller om aviseringen är felaktig kan du hantera [aviseringar i Cloud App Security-portalen.](https://docs.microsoft.com/cloud-app-security/managing-alerts)

Om din organisation använder [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) för Slutpunkt utöver Office 365 och en fil, IP-adress, URL eller domän behandlas som skadlig programvara på en enhet, även om det är säkert, kan du skapa en anpassad indikator med åtgärden ["Tillåt"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)för din enhet.

## <a name="undo-a-remediation-action"></a>Ångra en åtgärdsåtgärd

Om en åtgärdsåtgärd har vidtagits för ett e-postmeddelande, en e-postbilaga eller en URL,och objektet egentligen inte är ett hot, kan säkerhetsåtgärdsteamet i de flesta fall ångra åtgärden och vidta åtgärder för att förhindra att meddelandet felaktigt är återkommande. Du kan använda antingen [Hotutforskaren](#undo-an-action-using-threat-explorer) eller [fliken Åtgärder för en undersökning](#undo-an-action-in-the-action-center) för att ångra en åtgärd.

> [!IMPORTANT]
> Kontrollera att du har de behörigheter som behövs innan du försöker utföra följande uppgifter.

### <a name="undo-an-action-using-threat-explorer"></a>Ångra en åtgärd med Hjälp av Hotutforskaren

Med Threat Explorer kan ditt säkerhetsteam hitta ett e-postmeddelande som påverkas av en åtgärd och eventuellt ångra åtgärden.

|Scenario|Ångra alternativ|Mer information|
|---|---|---|
|Ett e-postmeddelande har dirigerats till en användares skräppostmapp|- Flytta meddelandet till användarens borttagna objekt-mapp<br/>- Flytta meddelandet till användarens inkorg<br/>- Ta bort meddelandet|[Hitta och undersöka skadlig e-post som levererats i Office 365](investigate-malicious-email-that-was-delivered.md)|
|Ett e-postmeddelande eller en fil har satts i karantän|- Släpp e-postmeddelandet eller filen<br/>- Ta bort e-postmeddelandet eller filen|[Hantera meddelanden i karantän som administratör](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a>Ångra en åtgärd i Åtgärdscenter

I Åtgärdscenter kan du se åtgärder som har vidtagits och eventuellt ångra åtgärden.

1. Gå till Microsoft 365 säkerhetscenter ( <https://security.microsoft.com> ).
2. Välj Åtgärdscenter i **navigeringsfönstret.**
3. Välj fliken **Historik** för att visa listan över slutförda åtgärder.
4. Markera ett objekt. Det utfällfönster som visas.
5. Välj Ångra i det utfällfönster **som visas.** (Det är bara åtgärder som kan ångras som har **knappen** Ångra.)

## <a name="see-also"></a>Se även

- [Microsoft Defender för Office 365](office-365-atp.md)
- [Automatiserade undersökningar i Microsoft Defender för Office 365](office-365-air.md)
