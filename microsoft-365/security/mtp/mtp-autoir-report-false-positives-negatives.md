---
title: Hantera falska positiva eller falska negativa tal i AIR i Microsoft 365 Defender
description: Har något missats eller identifierats felaktigt av AIR i Microsoft 365 Defender? Lär dig hur du skickar falska positiva eller falska negativa tal till Microsoft för analys.
keywords: automatiserad, undersökning, avisering, utlösare, åtgärd, falsk positiv eller falsk negativ
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: dbef240e28258d1ac4000c05538d0ce073a9d910
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930360"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Hantera falska positiva/negativa tal i automatisk undersökning och svarsfunktioner

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Har [automatisk undersökning och svar i](mtp-autoir.md) Microsoft 365 Defender missat eller felaktigt upptäckt något? Det finns åtgärder du kan vidta för att åtgärda det. Du kan:

- [Rapportera ett falskt positivt/negativt värde till Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);

- [Justera dina aviseringar](#adjust-an-alert-to-prevent-false-positives-from-recurring) (om det behövs). och 

- [Ångra åtgärder som har vidtagits på enheter.](#undo-a-remediation-action-that-was-taken-on-a-device) 

Använd den här artikeln som en guide. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Rapportera ett falskt positivt/negativt till Microsoft för analys

|Objekt som har missats eller identifierats fel |Tjänst  |Vad kan jag göra?  |
|---------|---------|---------|
|- E-postmeddelande <br/>- E-postbilaga <br/>- URL i ett e-postmeddelande<br/>- URL i en Office-fil      |[Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[Skicka misstänkt skräppost, phish, URL:er och filer till Microsoft för genomsökning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|Fil eller app på en enhet    |[Microsoft Defender för Endpoint](https://docs.microsoft.com/windows/security/threat-protection)         |[Skicka en fil till Microsoft för analys av skadlig programvara](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Justera en avisering för att förhindra att falska positiva resultat upprepas

|Scenario |Tjänst |Vad kan jag göra? |
|--------|--------|--------|
|- En avisering utlöses av legitimt bruk <br/>- En avisering är felaktig    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> eller <br/>[Avancerad identifiering av Azure-hot](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Hantera aviseringar i Cloud App Security-portalen](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|En fil, IP-adress, URL eller domän behandlas som skadlig programvara på en enhet, trots att den är säker|[Microsoft Defender för Endpoint](https://docs.microsoft.com/windows/security/threat-protection) |[Skapa en anpassad indikator med åtgärden "Tillåt"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Ångra en åtgärdsåtgärd som har vidtagits på en enhet

Om en åtgärdsåtgärd har vidtagits på en enhet (till exempel en Windows 10-enhet) och objektet egentligen inte är ett hot kan säkerhetsåtgärdsteamet ångra åtgärden i [Åtgärdscenter.](mtp-action-center.md)

> [!IMPORTANT]
> Kontrollera att du har [de behörigheter som](mtp-action-center.md#required-permissions-for-action-center-tasks) behövs innan du försöker utföra följande uppgift.

1. Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in. 

2. Välj Åtgärdscenter i **navigeringsfönstret.** 

3. Välj en **åtgärd** som du vill ångra på fliken Historik. Då öppnas en utfällblad.<br/>
    > [!TIP]
    > Använd filter för att begränsa resultatlistan. 

4. Välj sidan Öppna undersökning i den utfäll plats som är markerad för **det markerade objektet.**

5. Välj fliken Åtgärder i vyn **undersökningsinformation.**

6. Markera ett objekt som har **statusen Slutförd** och leta efter en länk, till exempel **Godkänd,** i **kolumnen** Beslut. Då öppnas en utfällblad med mer information om åtgärden.

7. Om du vill ångra åtgärden väljer **du Ta bort åtgärd.**

## <a name="see-also"></a>Se även

- [Visa information och resultat från en automatiserad undersökning](mtp-autoir-results.md)
- [Proaktiv sökning efter hot med avancerad sökning i Microsoft 365 Defender](advanced-hunting-overview.md)
