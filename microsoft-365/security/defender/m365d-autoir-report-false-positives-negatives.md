---
title: Hantera falska positiva resultat eller falska negativa resultat i AIR i Microsoft 365 Defender
description: Har något missats eller identifierats felaktigt av AIR i Microsoft 365 Defender? Lär dig hur du skickar falska positiva eller falska negativa tal till Microsoft för analys.
keywords: automatiserad, undersökning, avisering, åtgärd, falskt positivt, falskt negativt
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 8658b08f0d3948d6d23486ec885486e8bbfdf273
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068911"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Hantera falska positiva/negativa i automatiska undersöknings- och svarsfunktioner

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

Falska positiva/negativa kan ibland uppstå med någon lösning för skydd mot hot. Om [automatisk undersökning och svarsfunktioner](m365d-autoir.md) i Microsoft 365 Defender missade eller felaktigt identifierade något finns det åtgärder som ditt säkerhetsteam kan vidta:

- [Rapportera falskt positivt/negativt till Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Justera dina aviseringar](#adjust-an-alert-to-prevent-false-positives-from-recurring) (om det behövs). och 
- [Ångra åtgärder som har vidtagits på enheter](#undo-a-remediation-action-that-was-taken-on-a-device). 

I följande avsnitt beskrivs hur du utför de här uppgifterna.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Rapportera ett falskt positivt/negativt till Microsoft för analys

|Objekt som har missats eller identifierats felaktigt |Tjänst  |Vad kan jag göra?  |
|---------|---------|---------|
|- E-postmeddelande <br/>- E-postbilaga <br/>- URL i ett e-postmeddelande<br/>- URL i en Office-fil      |[Microsoft Defender för Office 365](/microsoft-365/security/defender-365-security/defender-for-office-365)        |[Skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft för genomsökning](../defender-365-security/admin-submission.md)         |
|Fil eller app på en enhet    |[Microsoft Defender för Endpoint](/windows/security/threat-protection)         |[Skicka en fil till Microsoft för analys av skadlig programvara](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Justera en avisering för att förhindra att falska positiva resultat upprepas

|Scenario |Tjänst |Vad kan jag göra? |
|--------|--------|--------|
|- En avisering som utlöses av legitimt bruk <br/>- En avisering är felaktig    |[Microsoft Cloud App Security](/cloud-app-security)<br/> eller <br/>[Avancerad identifiering av hot i Azure](/azure/security/fundamentals/threat-detection)         |[Hantera aviseringar i Cloud App Security-portalen](/cloud-app-security/managing-alerts)         |
|En fil, IP-adress, URL eller domän behandlas som skadlig kod på en enhet, trots att den är säker|[Microsoft Defender för Endpoint](/windows/security/threat-protection) |[Skapa en anpassad indikator med åtgärden "Tillåt"](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Ångra en åtgärdsåtgärd som har vidtagits på en enhet

Om en åtgärdsåtgärd har vidtagits för en entitet (till exempel en enhet eller ett e-postmeddelande) och den berörda enheten faktiskt inte är ett hot, kan ditt säkerhetsåtgärdsteam ångra åtgärden i [Åtgärdscenter.](m365d-action-center.md)

1. Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in. 
2. Välj Åtgärdscenter i **navigeringsfönstret.** 
3. Välj **en åtgärd** som du vill ångra på fliken Historik. Den utfällna rutan öppnas.
4. Välj Ångra i den utfällade **rutan.**

> [!TIP]
> Se [Ångra slutförda åtgärder.](m365d-autoir-actions.md#undo-completed-actions)

## <a name="see-also"></a>Se även

- [Visa information och resultat från en automatiserad undersökning](m365d-autoir-results.md)
- [Proaktiv sökning efter hot med avancerad sökning i Microsoft 365 Defender](advanced-hunting-overview.md)
- [Adressera falska positiva/negativa tal i Microsoft Defender för Endpoint](/windows/security/threat-protection/microsoft-defender-atp/defender-endpoint-false-positives-negatives)