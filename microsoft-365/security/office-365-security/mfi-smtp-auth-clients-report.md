---
title: SMTP-AUTH-klienter inblick och rapport i instrument panelen för e-postflöde
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära dig hur du använder SMTP AUTH inblick och rapport i instrument panelen för e-postflöde i säkerhets & Compliance Center för att övervaka e-avsändare i organisationen som använder autentiserad SMTP (SMTP AUTH) för att skicka e-postmeddelanden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: afceb767f6ebfeed96deb6362e05bb088b548c3d
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029168"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>SMTP-AUTH-klienter inblick och rapportera i säkerhets & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**SMTP-AUTH-klienterna** inblickar i [instrument panelen för e-postflöden](mail-flow-insights-v2.md) och den tillhör ande [SMTP-authn-rapporten](#smtp-auth-clients-report) i [säkerhets & Compliance Center](https://protection.office.com) markerar användning av SMTP auth client-klientprogrammet för överföring av användare eller system konton i din organisation. Det här bakåtkompatibla protokollet (som använder slut punkts smtp.office365.com) endast erbjuder grundläggande inloggningsautentisering och är känsligt för att användas av obehöriga konton för att skicka e-post. Med inblick och rapport kan du söka efter ovanlig aktivitet för SMTP-profilens e-postinlägg. Det visar också TLS-dataanvändningen för klienter eller enheter med SMTP-autentisering.

Widgeten visar antalet användare eller tjänst konton som har använt SMTP Authentication Protocol under de senaste 7 dagarna.

![Widget för SMTP-AUTH-klienter i instrument panelen för e-postflöde i säkerhets & Compliance Center](../../media/mfi-smtp-auth-clients-report-widget.png)

Om du klickar på antalet meddelanden i widgeten visas en **SMTP-AUTH-klienter** . Den utfällbara vyn visar en sammanslagen vy av TLS-användning och volymerna under den senaste veckan.

![Information utfälld när du klickar på widgeten SMTP-AUTH-klienter i instrument panelen för e-postflöde](../../media/mfi-smtp-auth-clients-report-details.png)

Du kan klicka på länken **SMTP-AUTH-klienter** för att gå till rapporten SMTP-AUTH-klienter enligt beskrivningen i nästa avsnitt.

## <a name="smtp-auth-clients-report"></a>Rapporten SMTP Auth-klienter

### <a name="report-view-for-the-smtp-auth-clients-report"></a>Rapportvy för rapporten SMTP-AUTH-klienter

Som standard visar rapporten data för de senaste 7 dagarna, men data är tillgängliga under de senaste 90 dagarna.

Avsnittet Översikt innehåller följande diagram:

- **Visa data genom: skicka volym**: diagrammet visar som standard antalet SMTP auth client-meddelanden som skickades från alla domäner (**Visa data för: alla avsändare** är markerade som standard). Du kan filtrera resultaten till en viss avsändares domän genom att klicka på **Visa data för** och välja avsändar domänen i list rutan. Om du hovrar över en viss data punkt (dag) visas antalet meddelanden.

  ![Skicka vyn volym i rapporten SMTP-AUTH-klienter i säkerhets & efterlevnad](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- **Visa data genom: TLS-användning**: diagrammet visar procent andelen av TLS-användning för alla SMTP auth client-meddelanden under den valda tids perioden. I det här diagrammet kan du identifiera och vidta åtgärder för användare och system konton som fortfarande använder äldre versioner av TLS.

  ![Vyn användning av TLS i rapporten SMTP-AUTH-klienter i säkerhets & efterlevnad](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

Om du klickar på **filter** i en rapportvy kan du ange ett datum intervall med **start datum** och **slutdatum**.

Klicka på **rapporten Request** för att få en mer detaljerad version av rapporten i ett e-postmeddelande. Du kan ange datum intervallet och mottagarna för att få rapporten.

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>Vyn detaljerad tabell för rapporten SMTP-AUTH-klienter

Om du klickar på **Visa informations tabell** beror informationen som visas på diagrammet du tittade på:

- **Visa data genom: skicka volym**: följande information visas i en tabell:

  - **Avsändarens adress**
  - **Antal meddelanden**

  Om du markerar en rad visas samma detaljer i en utfällbar lista.

- **Visa data genom: TLS-användning**: följande information visas i en tabell:

  - **Avsändarens adress**
  - **TLS 1.0%**<sup>\*</sup>
  - **TLS 1.1%**<sup>\*</sup>
  - **TLS 1.2%**<sup>\*</sup>
  - **Antal meddelanden**

  <sup>\*</sup> I den här kolumnen visas både procent andelen och antalet meddelanden från avsändaren.

Om du klickar på **filter** i en detaljerad tabellvy kan du ange ett datum intervall med **start datum** och **slutdatum**.

Om du markerar en rad visas liknande information i en utfällbar lista:

![Information som utfälls från tabellen information i vyn TLS-användning i SMTP-authn-klienter](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

Klicka på **rapporten Request** för att få en mer detaljerad version av rapporten i ett e-postmeddelande. Du kan ange datum intervallet och mottagarna för att få rapporten.

Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.

## <a name="related-topics"></a>Relaterade ämnen

Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).
