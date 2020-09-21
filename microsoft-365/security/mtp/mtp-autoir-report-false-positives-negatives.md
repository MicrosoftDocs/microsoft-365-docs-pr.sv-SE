---
title: Hantera falskta positiva eller falska negativa negativ i luften i Microsoft Threat Protection
description: Har något missats eller felaktigt upptäckts av AIR i Microsoft Threat Protection? Lär dig hur du skickar falska positiva eller falska negativa negativ till Microsoft för analys.
keywords: automatiserad, undersökning, avisering, utlösare, åtgärd, reparation, falskt positivt, falskt negativt
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: ace9ab8e5b73e4a4310b476c8954b0be81faaa66
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962329"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Hantera felaktiga positiva/negativa negativ i automatiserade undersökningar och svars funktioner

**Gäller för:**
- Microsoft Hotskydd

Lyckades en [Automatisk undersökning och svars funktion](mtp-autoir.md) i Microsoft Threat Protection missar något? Det finns några åtgärder du kan vidta för att åtgärda det. Du kan:

- [Rapportera en falsk positiv/negativ till Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);

- [Justera dina meddelanden](#adjust-an-alert-to-prevent-false-positives-from-recurring) (vid behov); och 

- [Ångra reparations åtgärder som har utförts på enheter](#undo-a-remediation-action-that-was-taken-on-a-device). 

Använd den här artikeln som en guide. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Rapportera en falsk positiv/negativ till Microsoft för analys

|Objektet missade eller upptäcktes felaktigt |Tjänst  |Vad kan jag göra?  |
|---------|---------|---------|
|-E-postmeddelande <br/>-E-postbilaga <br/>-URL i ett e-postmeddelande<br/>-URL i en Office-fil      |[Office 365 Avancerat skydd](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[Skicka misstänkt spam, Phish, webb adresser och filer till Microsoft för genomsökning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|Fil eller app på en enhet    |[Microsoft Defender Avancerat skydd](https://docs.microsoft.com/windows/security/threat-protection)         |[Skicka en fil till Microsoft för analys av skadlig program vara](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Justera en avisering för att förhindra falsk negativ från återkommande

|Ovanligt |Tjänst |Vad kan jag göra? |
|--------|--------|--------|
|-En notifiering utlöses av en legitim användning <br/>-En avisering är felaktig    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> eller <br/>[Avancerad hot identifiering för Azure](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Hantera aviseringar i Cloud App Security Portal](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|En fil, IP-adress, URL eller domän behandlas som skadlig program vara på en enhet, trots att det är säkert|[Microsoft Defender Avancerat skydd](https://docs.microsoft.com/windows/security/threat-protection) |[Skapa en anpassad indikator med åtgärden "Tillåt"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Ångra en reparations åtgärd som har utförts på en enhet

Om en åtgärd för reparation har utförts på en enhet (till exempel en Windows 10-enhet) och objektet inte är ett hot kan säkerhets åtgärds gruppen ångra reparations åtgärden i [Åtgärds centret](mtp-action-center.md).

> [!IMPORTANT]
> Kontrol lera att du har [nödvändig behörighet](mtp-action-center.md#required-permissions-for-action-center-tasks) innan du försöker utföra följande uppgift.

1. Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in. 

2. I navigerings fönstret väljer du **Åtgärds Center**. 

3. På fliken **Historik** väljer du en åtgärd som du vill ångra. Då öppnas en utfällbar meny.<br/>
    > [!TIP]
    > Använd filter för att begränsa resultat listan. 

4. Välj **Öppna undersöknings sida**i utfällning för det markerade objektet.

5. I vyn undersöknings information väljer du fliken **åtgärder** .

6. Markera ett objekt som har statusen **slutförd**och leta efter en länk, till exempel **godkänd**, i kolumnen **beslut** . Då öppnas en utfällbar lista med mer information om åtgärden.

7. Om du vill ångra åtgärden väljer du **ta bort reparation**.

## <a name="see-also"></a>Se även

- [Visa information och resultat från en automatisk undersökning](mtp-autoir-results.md)
- [Det står proaktivt för problem med avancerad jakt i Microsoft Threat Protection](advanced-hunting-overview.md)
