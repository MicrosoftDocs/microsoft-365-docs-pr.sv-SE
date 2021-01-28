---
title: Köers inblick i instrument panelen för e-postflöde
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Administratörer kan lära dig hur du använder widgeten köer i instrument panelen för e-postflöde i säkerhets & Compliance Center för att övervaka misslyckade e-postflöden till deras lokala eller partner organisationer via utgående anslutningar.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 73e97cbbd05e298013e9e686053a969d587ad5cf
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029156"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>Köer inblickar i säkerhets & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


När meddelanden inte kan skickas från din organisation till lokala eller partnersbaserade e-postservrar med kopplingar köas de i Microsoft 365. Vanliga exempel som orsakar det här problemet:

- Kopplingen är felaktigt konfigurerad.
- Nätverks-eller vägg ändringar har gjorts i din lokala miljö.

Microsoft 365 fortsätter att försöka leverera i 24 timmar. Efter 24 timmar upphör meddelanden att gälla och kommer att återföras till avsändare i rapporter som inte kunde levereras (kallas även för NDR eller studs meddelanden).

Om den köade e-postvolymen överskrider det fördefinierade tröskelvärdet (Standardvärdet är 200 meddelanden) finns informationen på följande platser:

- **Köerna** inblickar i [instrument panelen för e-postflöden](mail-flow-insights-v2.md) i [säkerhets & Compliance Center](https://protection.office.com). Mer information finns i [köer i avsnittet e-postflöde](#queues-insight-in-the-mail-flow-dashboard) i den här artikeln.

- En avisering visas i de **senaste varningarna** instrument panelen för aviseringar i [säkerhets & Compliance Center](https://protection.office.com) (instrument panelen för **aviseringar** \>  eller <https://protection.office.com/alertsdashboard> ).

  ![Senaste meddelanden i instrument panelen för aviseringar i säkerhets & efterlevnad](../../media/mfi-queued-messages-alert.png)

- Administratörer får ett e-postmeddelande baserat på konfigurationen av den standard aviserings princip som heter **meddelanden har försen ATS**. Se nästa avsnitt om du vill konfigurera aviserings inställningarna för den här aviseringen.

  Mer information om aviserings principer finns i [aviserings principer i säkerhets & efterlevnad](../../compliance/alert-policies.md).

## <a name="customize-queue-alerts"></a>Anpassa aviseringar i kö

1. Gå till **aviserings** principer för varningar eller öppna i fönstret [säkerhets & efterlevnad](https://protection.office.com) \>  <https://protection.office.com/alertpolicies> .

2. Leta reda på och välj policyn som heter **meddelanden** på sidan **aviserings principer** .

3. I **meddelandet har fördröjd** utfällning som öppnas kan du aktivera eller inaktivera aviseringen och konfigurera aviserings inställningarna.

   ![Meddelanden har fördröjts med aviserings princip uppgifter säkerhets & efterlevnad](../../media/mfi-queued-messages-alert-policy.png)

   - **Status**: du kan aktivera eller inaktivera aviseringen.

   - **E-postmottagare** och **daglig meddelande gräns**: Klicka på **Redigera** för att konfigurera följande inställningar:

4. Konfigurera aviserings inställningarna genom att klicka på **Redigera**. I redigera utfällbar **princip** som visas konfigurerar du följande inställningar:

   - **Skicka e-postmeddelanden**: standardvärdet är på.
   - **E-postmottagare**: standardvärdet är **TenantAdmins**.
   - **Daglig meddelande gräns**: standardvärdet är **ingen gräns**.
   - **Tröskelvärde**: standardvärdet är 200.

   ![Aviserings inställningar i meddelanden har fördröjts med aviserings princip uppgifter säkerhets & efterlevnad](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. När du är klar klickar du på **Spara** och **Stäng**.

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>Köers inblick i instrument panelen för e-postflöde

Även om den köade meddelande volymen inte har överskridit tröskelvärdet och genererat en avisering kan du ändå använda **köer** i [instrument panelen för e-postflöde](mail-flow-insights-v2.md) för att visa meddelanden som har placerats i kö i mer än en timme och vidta åtgärder innan antalet köade meddelanden blir för stora.

![Widgeten för köer i instrument panelen för säkerhets &](../../media/mfi-queues-widget.png)

Om du klickar på antalet meddelanden i widgeten visas en utfällbar **meddelande** med följande information:

- **Antal köade meddelanden**
- **Anslutnings namn**: Klicka på kopplingens namn för att hantera kopplingen i administrations centret för Exchange (UK).
- **Start tid för kö**
- **Äldsta meddelanden har upphört**
- **Mål Server**
- **Sista IP-adress**
- **Senaste fel**
- **Så här löser du problemet**: vanliga problem och lösningar finns tillgängliga. Om du har en lösning på att länken **nu** är tillgänglig klickar du på den för att åtgärda problemet. Annars kan du klicka på eventuella tillgängliga länkar för mer information om felet och möjliga lösningar.

![Information efter att du klickat på ärende köerna i instrument panelen för e-postflöde](../../media/mfi-queues-details.png)

Samma utfällda meddelande visas när du klickar på **Visa kö** i **meddelandet har fördröjts** .

![Meddelanden har fördröjts med aviserings informationen i centret för säkerhets &](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a>Se även

Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).
