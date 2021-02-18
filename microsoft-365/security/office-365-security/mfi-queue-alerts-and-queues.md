---
title: Köinsikter i instrumentpanelen för e-postflöde
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Administratörer kan lära sig att använda widgeten Köer i instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för & för att övervaka ett misslyckat e-postflöde till sina lokala organisationer eller partnerorganisationer via utgående anslutningar.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ca8ee5ea37fa5a63b8035572059e419c400d66f3
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289443"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>Köinsikter i säkerhets- & Efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

När meddelanden inte kan skickas från din organisation till dina lokala e-postservrar eller partner-e-postservrar med hjälp av kopplingar, är meddelandena i kö i Microsoft 365. Vanliga exempel som kan orsaka detta villkor är:

- Kopplingen är felaktigt konfigurerad.
- Det har skett nätverks- eller brandväggsändringar i din lokala miljö.

Microsoft 365 fortsätter att försöka leverera igen i 24 timmar. Efter 24 timmar förfaller meddelandena och returneras till avsändarna i rapporter om utebliven leverans (kallas även NDR-rapporter eller icke-leveranskavsändarmeddelanden).

Om den fördefinierade e-postvolymen överskrider det fördefinierade tröskelvärdet (standardvärdet är 200 meddelanden) är informationen tillgänglig på följande platser:

- **Köinsikter** i [instrumentpanelen för e-postflöde](mail-flow-insights-v2.md) i [& Säkerhets- och efterlevnadscenter.](https://protection.office.com) Mer information finns i [köinsikter i instrumentpanelen för e-postflöde](#queues-insight-in-the-mail-flow-dashboard) i den här artikeln.

- En avisering visas i **instrumentpanelen för senaste** aviseringar i [säkerhets- & (instrumentpanelen](https://protection.office.com) för aviseringar \>  <https://protection.office.com/alertsdashboard> eller).

  ![Senaste aviseringar i instrumentpanelen för aviseringar i Säkerhets- & Efterlevnadscenter](../../media/mfi-queued-messages-alert.png)

- Administratörer får ett e-postmeddelande baserat på konfigurationen av standardaviseringsprincipen **med namnet Meddelanden har fördröjts.** Information om hur du konfigurerar aviseringsinställningarna för den här aviseringen finns i nästa avsnitt.

  Mer information om aviseringsprinciper finns i [Aviseringsprinciper i Säkerhets- & Efterlevnadscenter.](../../compliance/alert-policies.md)

## <a name="customize-queue-alerts"></a>Anpassa köaviseringar

1. Gå till [aviseringsprinciperna eller öppna i säkerhets-](https://protection.office.com)och **&** säkerhets- \>  och efterlevnadscentret. <https://protection.office.com/alertpolicies>

2. Sök efter **och välj** principen Meddelanden har fördröjts på sidan **Aviseringsprinciper.**

3. I meddelandet **har fördröjts** och öppnats kan du aktivera eller inaktivera aviseringen och konfigurera aviseringsinställningarna.

   ![Meddelanden har fördröjts med information om avisering & Säkerhets- och efterlevnadscenter](../../media/mfi-queued-messages-alert-policy.png)

   - **Status:** Du kan aktivera eller inaktivera aviseringen.

   - **Gräns för** **e-postmottagare och daglig** avisering: **Klicka på** Redigera för att konfigurera följande inställningar:

4. Om du vill konfigurera meddelandeinställningarna klickar du på **Redigera.** Konfigurera följande **inställningar i** den utfällna menyn Redigera princip som visas:

   - **Skicka e-postaviseringar:** Standardvärdet är på.
   - **E-postmottagare:** Standardvärdet är **TenantAdmins.**
   - **Daglig meddelandegräns:** Standardvärdet är **Ingen gräns.**
   - **Tröskelvärde:** Standardvärdet är 200.

   ![Meddelandeinställningar i meddelanden har fördröjts med information om säkerhets- & Efterlevnadscenter](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. Klicka på Spara och Stäng **när** du är **klar.**

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>Köinsikter i instrumentpanelen för e-postflöde

Även om volymen för det köade meddelandet inte har överskridit tröskelvärdet  och genererat [](mail-flow-insights-v2.md) en avisering kan du fortfarande använda köinsikterna i instrumentpanelen för e-postflöde för att se meddelanden som har köats i mer än en timme och vidta åtgärder innan antalet köade meddelanden blir för stora.

![Widget för köer i instrumentpanelen för e-postflöde i Säkerhets- & Efterlevnadscenter](../../media/mfi-queues-widget.png)

Om du klickar på antalet meddelanden  på widgeten visas en utfällbara meddelandekö med följande information:

- **Antal meddelanden i kö**
- **Kopplingsnamn:** Klicka på kopplingsnamnet för att hantera kopplingen i administrationscentret för Exchange (EAC).
- **Starttid för kö**
- **Äldsta meddelanden har förfallit**
- **Målserver**
- **Senaste IP-adress**
- **Senaste felet**
- **Så här åtgärdar** du problemet: Vanliga problem och lösningar finns tillgängliga. Om länken Åtgärda **det nu** är tillgänglig kan du klicka på den för att åtgärda problemet. Annars klickar du på de tillgängliga länkarna för att få mer information om felet och möjliga lösningar.

![Information när du klickar på köinsikter på instrumentpanelen för e-postflöde](../../media/mfi-queues-details.png)

Samma utfällbara bild visas när du **klickar på Visa kö** i information om ett meddelande har **fördröjts.**

![Meddelanden har fördröjts i säkerhets- & Efterlevnadscenter](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a>Se även

Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinsikter i Säkerhets- & Efterlevnadscenter.](mail-flow-insights-v2.md)
