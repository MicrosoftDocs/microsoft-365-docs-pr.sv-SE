---
title: Så här rapporterar du falska positiva eller falska negativ i automatisk undersökning och svar i Office 365
description: Har något missats eller upptäckts felaktigt av Office 365 Advanced Threat Protection? Lär dig hur du skickar falska positiva eller falska negativ till Microsoft för analys.
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
ms.date: 05/15/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 2dd67af62a400f3e217f146e6d0ee213d74ad99a
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262420"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Så här rapporterar du falska positiva identifieringar/negativ i automatiserade undersöknings- och svarsfunktioner

**Gäller:**
- Office 365 Avancerat skydd

Har funktioner för [automatisk undersökning och respons (AIR) i Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) missat eller felidentifierade något? Det finns åtgärder du kan vidta för att åtgärda det. Du kan:
- [Rapportera ett falskt positivt/negativt till Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Justera dina aviseringar](#adjust-an-alert-to-prevent-false-positives-from-recurring) (om det behövs); Och 
- [Ångra åtgärder för reparation som har vidtagits på enheter](#undo-a-remediation-action). 

Använd den här artikeln som vägledning. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Rapportera ett falskt positivt/negativt till Microsoft för analys

Om Office 365 AIR missade ett e-postmeddelande, en e-postbilaga, en URL i ett e-postmeddelande eller en URL i en Office-fil kan du [skicka misstänkt skräppost, phish, URL:er och filer till Microsoft för Office 365-skanning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).

Du kan också [skicka en fil till Microsoft för analys av skadlig kod](https://www.microsoft.com/wdsi/filesubmission).

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Justera en avisering för att förhindra att falska positiva identifieringar upprepas

Om en avisering utlöses av legitim användning eller aviseringen är felaktig kan du [hantera aviseringar i Cloud App Security-portalen](https://docs.microsoft.com/cloud-app-security/managing-alerts).

Om din organisation använder [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) utöver Office 365 och en fil, IP-adress, URL eller domän behandlas som skadlig kod på en enhet, även om det är säkert, kan du skapa en anpassad indikator med åtgärden Tillåt för din [enhet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).

## <a name="undo-a-remediation-action"></a>Ångra en åtgärd

I de flesta fall, om en reparationsåtgärd har vidtagits på ett e-postmeddelande, en e-postbilaga eller webbadress, och objektet faktiskt inte är ett hot, kan säkerhetsoperationsteamet ångra reparationsåtgärden och vidta åtgärder för att förhindra att det falska positiva upprepas. Du kan antingen använda [Threat Explorer](#undo-an-action-using-threat-explorer) eller fliken Åtgärder för att en [undersökning ska](#undo-an-action-using-the-actions-tab-for-an-investigation) ångra en åtgärd. 

> [!IMPORTANT]
> Kontrollera att du har de behörigheter som krävs innan du försöker utföra följande uppgifter.

### <a name="undo-an-action-using-threat-explorer"></a>Ångra en åtgärd med Hjälp av Threat Explorer

Med Threat Explorer kan säkerhetsoperationsteamet hitta ett e-postmeddelande som påverkas av en åtgärd och eventuellt ångra åtgärden.

|Scenario  |Ångra alternativ  |Mer information |
|---------|---------|---------|
|Ett e-postmeddelande dirigerades till en användares skräppostmapp     |- Flytta meddelandet till användarens mapp Borttaget<br/>- Flytta meddelandet till användarens inkorg <br/>- Ta bort meddelandet          |[Hitta och undersöka skadlig e-post som levererades i Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered) |
|Ett e-postmeddelande eller en fil har satts i karantän     |- Släpp e-post eller fil <br/>- Ta bort e-post eller fil         |[Hantera meddelanden och filer i karantän som administratör i Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files) |


### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a>Ångra en åtgärd med hjälp av fliken Åtgärder för en undersökning

I åtgärdscentret kan du se åtgärder för reparation som har vidtagits och eventuellt ångra åtgärden.

1. Gå till [https://protection.office.com](https://protection.office.com) och logga in. Detta tar dig till Security & Compliance Center.

2. Gå till **Hot management**  >  **Undersökningar**.

3. I listan över undersökningar väljer du ikonen **Öppna i nytt fönster** bredvid ett objekts ID.

4. Välj fliken **Åtgärder.**

5. Markera ett objekt som har **statusen Slutförd**och leta efter en länk, till exempel **Godkänd**, i kolumnen **Beslut.** Detta öppnar ett utfällbart överläge med mer information om åtgärden.

6. Om du vill ångra åtgärden väljer du **Ta bort reparation**.

## <a name="related-articles"></a>Relaterade artiklar

[Office 365 Avancerat skydd](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[Komma igång med automatisk undersökning och svar (AIR) i Office 365](office-365-air.md)