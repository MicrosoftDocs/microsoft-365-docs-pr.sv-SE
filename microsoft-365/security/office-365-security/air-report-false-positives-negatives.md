---
title: Rapportera falsk positiv eller falskt negativ efter en automatiserad undersökning i Microsoft Defender för Office 365
description: Har något missats eller felaktigt upptäckts av AIR i Microsoft Defender för Office 365? Lär dig hur du skickar falska positiva eller falska negativa negativ till Microsoft för analys.
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
ms.date: 09/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.custom:
- autoir
ms.openlocfilehash: 27edc44145e7b61768d9caf00a3f308e8561d708
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357405"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Rapportera falskta positiva eller negativa negativ i den automatiska undersökningen och svars funktionerna

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Gäller för:**
- Microsoft Defender för Office 365

Har [automatiserade undersökningar och svar (Air) i Office 365](automated-investigation-response-office.md) missats eller inte känner till något? Det finns några åtgärder du kan vidta för att åtgärda det. Du kan:

- [Rapportera en falsk positiv/negativ till Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Justera dina meddelanden](#adjust-an-alert-to-prevent-false-positives-from-recurring) (vid behov); och
- [Ångra reparations åtgärder som vidtogs](#undo-a-remediation-action).

Använd den här artikeln som en guide.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Rapportera en falsk positiv/negativ till Microsoft för analys

Om luften i Microsoft Defender för Office 365 missade ett e-postmeddelande, en e-postbilaga, en URL i ett e-postmeddelande eller en URL i en Office-fil kan du [Skicka misstänkt skräp post, Phish, webb adresser och filer till Microsoft för Office 365-genomsökning](admin-submission.md).

Du kan också [skicka en fil till Microsoft för analys av skadlig program vara](https://www.microsoft.com/wdsi/filesubmission).

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Justera en avisering för att förhindra falsk negativ från återkommande

Om en avisering utlöses av en legitim användning eller om aviseringen inte stämmer kan du [Hantera aviseringar i Cloud App Security-portalen](https://docs.microsoft.com/cloud-app-security/managing-alerts).

Om din organisation använder [Microsoft Defender för slut punkt](https://docs.microsoft.com/windows/security/threat-protection) utöver Office 365 behandlas en fil, IP-adress, URL eller domän som skadlig program vara på en enhet, trots att det är säkert kan du [skapa en egen indikator med en "Tillåt"-åtgärd för enheten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).

## <a name="undo-a-remediation-action"></a>Ångra en åtgärd för reparation

I de flesta fall kan en reparations åtgärd vidtas i ett e-postmeddelande, en e-postbilaga eller en URL-adress, och objektet är egentligen inte ett hot, men din säkerhets åtgärds grupp återställer åtgärden och vidtar åtgärder för att förhindra att det falska positiva värdet för återkommande. Du kan antingen använda [Threat Explorer](#undo-an-action-using-threat-explorer) eller [fliken åtgärder för att få en undersökning](#undo-an-action-using-the-actions-tab-for-an-investigation) för att ångra en åtgärd.

> [!IMPORTANT]
> Kontrol lera att du har nödvändig behörighet innan du försöker utföra följande uppgifter.

### <a name="undo-an-action-using-threat-explorer"></a>Ångra en åtgärd med hjälp av Threat Explorer

Med Threat Explorer kan säkerhets åtgärds gruppen Hitta ett e-postmeddelande som påverkas av en åtgärd och eventuellt ångra åtgärden.

****

|Ovanligt|Ångra-alternativ|Mer information|
|---|---|---|
|Ett e-postmeddelande dirigerades till en användares mapp för skräp post|<ul><li>Flytta meddelandet till användarens mapp för borttagna objekt</li><li>Flytta meddelandet till användarens inkorg</li><li>Ta bort meddelandet</li></ul>|[Hitta och undersöka skadlig e-post som har levererats i Office 365](investigate-malicious-email-that-was-delivered.md)|
|Ett e-postmeddelande eller en fil sattes i karantän|<ul><li>Släpp e-postmeddelandet eller filen</li><li>Ta bort e-postmeddelandet eller filen</li></ul>|[Hantera meddelanden i karantän som administratör](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a>Ångra en åtgärd på fliken åtgärder för en undersökning

I åtgärds Center kan du se åtgärds åtgärder som vidtogs och eventuellt ångra åtgärden.

1. Gå till [https://protection.office.com](https://protection.office.com) och logga in. Då kommer du till säkerhets & Compliance Center.

2. Gå till **Threat Management**  >  **utredningar**.

3. I listan över undersökningar väljer du ikonen **Öppna i nytt fönster** bredvid ett objekts ID.

4. Välj fliken **åtgärder** .

5. Markera ett objekt som har statusen **slutförd** och leta efter en länk, till exempel **godkänd**, i kolumnen **beslut** . Då öppnas en utfällbar lista med mer information om åtgärden.

6. Om du vill ångra åtgärden väljer du **ta bort reparation**.

## <a name="related-articles"></a>Relaterade artiklar

[Microsoft Defender för Office 365](office-365-atp.md)

[LUFT i Microsoft Defender för Office 365](office-365-air.md)
