---
title: Hantera falska positiva eller falska negativ i AIR i Microsoft Threat Protection
description: Har något missats eller felaktigt upptäckts av AIR i Microsoft Threat Protection? Lär dig hur du skickar falska positiva eller falska negativ till Microsoft för analys.
keywords: automatiserad, utredning, alert, utlösa, åtgärd, sanering, falskt positivt, falskt negativt
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 4030469b54d9a3a9c6f2eaceae384d39ea7f3e20
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637086"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Hantera falska positiva identifieringar/negativ i automatiserade undersöknings- och svarsfunktioner

**Gäller:**
- Microsoft Hotskydd

Har [automatiserade undersöknings- och svarsfunktioner](mtp-autoir.md) i Microsoft Threat Protection missat eller felaktigt upptäckt något? Det finns åtgärder du kan vidta för att åtgärda det. Du kan:

- [Rapportera ett falskt positivt/negativt till Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);

- [Justera dina aviseringar](#adjust-an-alert-to-prevent-false-positives-from-recurring) (om det behövs); Och 

- [Ångra åtgärder för reparation som har vidtagits på enheter](#undo-a-remediation-action-that-was-taken-on-a-device). 

Använd den här artikeln som vägledning. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Rapportera ett falskt positivt/negativt till Microsoft för analys

|Objektet har missats eller upptäckts felaktigt |Tjänst  |Vad du ska göra  |
|---------|---------|---------|
|- E-postmeddelande <br/>- Bifogad fil i e-post <br/>- URL i ett e-postmeddelande<br/>- URL i en Office-fil      |[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[Skicka misstänkt skräppost, phish, webbadresser och filer till Microsoft för skanning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|Fil eller app på en enhet    |[Microsoft Defender Avancerat skydd](https://docs.microsoft.com/windows/security/threat-protection)         |[Skicka en fil till Microsoft för analys av skadlig kod](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Justera en avisering för att förhindra att falska positiva identifieringar upprepas

|Scenario |Tjänst |Vad du ska göra |
|--------|--------|--------|
|- En avisering utlöses av legitim användning <br/>- En varning är felaktig    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> eller <br/>[Azure avancerad hotidentifiering](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Hantera aviseringar i Cloud App Security-portalen](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|En fil, IP-adress, URL eller domän behandlas som skadlig kod på en enhet, även om den är säker|[Microsoft Defender Avancerat skydd](https://docs.microsoft.com/windows/security/threat-protection) |[Skapa en anpassad indikator med åtgärden Tillåt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Ångra en åtgärd som har vidtagits på en enhet

Om en reparationsåtgärd har vidtagits på en enhet (till exempel en Windows 10-enhet) och objektet faktiskt inte är ett hot, kan säkerhetsoperationsgruppen ångra reparationsåtgärden i [Åtgärdscenter](mtp-action-center.md).

> [!IMPORTANT]
> Kontrollera att du har de [behörigheter som krävs](mtp-action-center.md#required-permissions-for-action-center-tasks) innan du försöker utföra följande uppgift.

1. Gå [https://security.microsoft.com](https://security.microsoft.com) till och logga in. 

2. Välj **Åtgärdscenter**i navigeringsfönstret . 

3. Välj en åtgärd som du vill ångra på fliken **Historik.** Detta öppnar ett utfällbart.<br/>
    > [!TIP]
    > Använd filter för att begränsa resultatlistan. 

4. I utfällbara objekt för det markerade objektet väljer du **Öppna undersökningssida**.

5. Välj fliken **Åtgärder** i vyn Undersökningsinformation.

6. Markera ett objekt som har **statusen Slutförd**och leta efter en länk, till exempel **Godkänd**, i kolumnen **Beslut.** Detta öppnar ett utfällbart överläge med mer information om åtgärden.

7. Om du vill ångra åtgärden väljer du **Ta bort reparation**.

## <a name="related-articles"></a>Relaterade artiklar

- [Godkänna eller avvisa åtgärder relaterade till automatisk undersökning och svar](mtp-autoir-actions.md)

- [Läs mer om Åtgärdscentret](mtp-action-center.md)

- [Proaktivt jakt efter hot med avancerad jakt i Microsoft Threat Protection](advanced-hunting-overview.md)
