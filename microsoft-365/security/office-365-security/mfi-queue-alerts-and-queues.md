---
title: Köers inblick i instrument panelen för e-postflöde
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Administratörer kan lära dig hur du använder widgeten köer i instrument panelen för e-postflöde i säkerhets & Compliance Center för att övervaka misslyckade e-postflöden till deras lokala eller partner organisationer via utgående anslutningar.
ms.openlocfilehash: 79523533306e847988fa0d4e2dd70eca22f7c76c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826911"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>Köer inblickar i säkerhets & Compliance Center

När meddelanden inte kan skickas från din organisation till lokala eller partnersbaserade e-postservrar med kopplingar köas de i Microsoft 365. Vanliga exempel som orsakar det här problemet:

- Kopplingen är felaktigt konfigurerad.
- Nätverks-eller vägg ändringar har gjorts i din lokala miljö.

Microsoft 365 fortsätter att försöka leverera i 24 timmar. Efter 24 timmar upphör meddelanden att gälla och kommer att återföras till avsändare i rapporter som inte kunde levereras (kallas även för NDR eller studs meddelanden).

Om den köade e-postvolymen överskrider det fördefinierade tröskelvärdet (Standardvärdet är 200 meddelanden) finns informationen på följande platser:

- **Köerna** inblickar i [instrument panelen för e-postflöden](mail-flow-insights-v2.md) i säkerhets & Compliance Center. Mer information finns i [köerna under rubriken e-postflöde](#queues-insight-in-the-mail-flow-dashboard) i det här avsnittet.
  
- En avisering visas i de **senaste varningarna** instrument panelen för aviseringar i [säkerhets & Compliance Center](https://protection.office.com) (instrument panelen för**aviseringar** \> **Dashboard** eller <https://protection.office.com/alertsdashboard> ).

  ![Senaste meddelanden i instrument panelen för aviseringar i säkerhets & efterlevnad](../../media/mfi-queued-messages-alert.png)

- Administratörer får ett e-postmeddelande baserat på konfigurationen av den standard aviserings princip som heter **meddelanden har försen ATS**. Se nästa avsnitt om du vill konfigurera aviserings inställningarna för den här aviseringen.

  Mer information om aviserings principer finns i [aviserings principer i säkerhets & efterlevnad](../../compliance/alert-policies.md).

## <a name="customize-queue-alerts"></a>Anpassa aviseringar i kö

1. Gå till **aviserings** principer för varningar eller öppna i fönstret [säkerhets & efterlevnad](https://protection.office.com) \> **Alert policies** <https://protection.office.com/alertpolicies> .

2. Leta reda på och välj policyn som heter **meddelanden**på sidan **aviserings principer** .

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
