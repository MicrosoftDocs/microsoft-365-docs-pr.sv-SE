---
title: Insikten Åtgärda avsändardomän
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Administratörer kan lära sig mer om åtkomstbesiktningen av korrigeringsavsändaren i instrumentpanelen för e-postflödet i Security & Compliance Center.
ms.openlocfilehash: a416b4d15ff52a611f00a88de8440c749ff08ad3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635178"
---
# <a name="fix-sender-domain-insight"></a>Insikten Åtgärda avsändardomän

Microsoft 365 kräver meddelanden som skickas från interna lokala e-postmiljöer till Microsoft 365 för att uppfylla vissa säkerhetskriterier:

- Du har skapat en inkommande anslutningsapp i Microsoft 365 för att autentisera SMTP-anslutningar från den lokala e-postservern med hjälp av käll-IP-adressen eller ett certifikat.

- Du har konfigurerat din lokala e-postserver för att vidarebefordra e-post via Microsoft 365 till den externa världen.

- I konfigurationen är ett av följande satser sant:

  - Avsändarens e-postdomän är registrerad i din organisation. Mer information finns i Lägga till domäner i Office 365.

  - Din lokala e-postserver är konfigurerad för att använda ett certifikat för att skicka e-post till Microsoft 365, certifikatet innehåller eller matchar exakt ett domännamn som du har registrerat i Microsoft 365 och du har skapat en certifikatbaserad anslutningsapp i Microsoft 365 med den domänen. 

Meddelanden som inte uppfyller kriterierna kommer inte att tillskrivas organisationen och kan avvisas.

**Fix-domäninsikten** visar e-post från din lokala miljö som inte uppfyller kriterierna, hjälper dig att identifiera potentiellt komprometterade datorer och användarkonton i din lokala e-postmiljö och hjälper dig att vidta åtgärder för att åtgärda.

![Fix-domäninformationen i instrumentpanelen för e-postflödet i Security & Compliance Center](../../media/sender-domain-insight-selected.png)

När du klickar på **Visa information**tas du till en annan widget med mer information som visas i följande diagram:

![Widgeten Information i fix-domänens insikt](../../media/sender-domain-view-details.png)

Den inkommande anslutningsappen som användes för att leverera meddelandena till Office 365 visas. Du kan också klicka på **Visa exempelmeddelande-ID:er** för att se information om de meddelanden som skickades från din lokala e-postmiljö. Eftersom dessa meddelanden avvisades av Office 365 kan du inte använda meddelandespårning, men du kan använda exempelmeddelande-ID:n för att spåra meddelandena i din lokala e-postmiljö.

![Visa exempelmeddelande-ID:er i fix-domänens insikt](../../media/sender-domain-view-sample-message-ids.png)

## <a name="see-also"></a>Snabbreferens

Mer information om andra insikter om e-postflöde i instrumentpanelen för e-postflödet finns [i Insikterna för e-postflöde i Security & Compliance Center](mail-flow-insights-v2.md).
