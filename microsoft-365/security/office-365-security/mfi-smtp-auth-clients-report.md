---
title: SMTP-autentiseringsklienter rapport
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
description: Administratörer kan lära sig mer om SMTP-autentiseringsklienter i instrumentpanelen för e-postflödet i Security & Compliance Center.
ms.openlocfilehash: e80ee36fd7e94cc4dc2791f71ae594f0182b4269
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42807133"
---
# <a name="smtp-auth-clients-report"></a>SMTP-autentiseringsklienter rapport

I rapporten **SMTP Auth-klienter** framhäver du användningen av SMTP Auth-klientöverföringsprotokollet av användare eller systemkonton i organisationen. Det här äldre protokollet (som använder slutpunkten smtp.office365.com) erbjuder endast grundläggande autentisering och kan användas av komprometterade konton för att skicka e-post.  Med den här rapporten kan du söka efter ovanlig aktivitet. Den visar också TLS-användningsdata för klienter eller enheter som använder SMTP Auth.

Widgeten som visas i instrumentpanelen e-postflöde anger antalet användare eller tjänstkonton som har använt SMTP Auth-protokollet under de senaste 7 dagarna.

![SMTP-autentiseringsklienter rapporterar i instrumentpanelen för e-postflödet i Security & Compliance Center](../../media/smtp-auth-clients-report-selected.png)

Om du klickar på widgeten öppnas ett utfällbart utfällbart alternativ som ger en aggregerad vy över TLS-användningen och volymerna för den senaste veckan.

![Utfällbara i rapporten SMTP Auth-klienter](../../media/smtp-auth-clients-flyout.png)

När du klickar på länken **SMTP Auth Clients Report** visas två huvuddata pivoter och två datavyer. Data pivoter är **skicka volym** och **TLS-användning**. Datavyerna är diagrammet och detaljtabellen.

Vyn **Skicka volym** visar antalet meddelanden som skickades med SMTP-autentisering för det angivna tidsintervallet. Du kan justera intervallet genom att klicka på **Filter**. Diagrammet ordnas efter avsändatordomän. Du kan se separata data för varje domän genom att välja domänen i **listrutan Visa data.**

![Skicka volym i rapporten SMTP Auth Clients](../../media/smtp-auth-clients-report-sending-volume.png)

Du kan visa detaljerad information om avsändarna och deras meddelandeantal genom att klicka på **Visa informationstabell**. Om du vill återgå till diagrammet klickar du på **Visa rapport**.

![Informationstabell för att skicka volym i rapporten SMTP Auth Clients](../../media/smtp-auth-clients-report-details-sending-volume.png)

**TLS-användnings** pivot är viktigt på grund av den kommande utfasningen av TLS1.0 och TLS1.1 i Office 365. Många äldre enheter och program kan inte skicka e-post om de bara kan använda TLS1.0 med SMTP Auth. Med den här pivoten kan du identifiera och vidta åtgärder för användare och systemkonton som fortfarande använder äldre versioner av TLS.

![TLS-användning i rapporten SMTP Auth-klienter](../../media/smtp-auth-clients-report-tls-usage.png)

Du kan visa detaljerad information om avsändare, versioner av TLS som de använder med SMTP Auth och deras meddelande räknas genom att klicka på **Visa informationstabell**. Om du vill återgå till diagrammet klickar du på **Visa rapport**.

Du kan också hämta en mer detaljerad version av rapporten genom att klicka på Begäran rapport.

![Informationstabell för TLS-användning i rapporten SMTP Auth Clients](../../media/smtp-auth-clients-report-details-tls-usage.png)

## <a name="see-also"></a>Se även

Mer information om andra insikter om e-postflöde i instrumentpanelen för e-postflödet finns [i Insikterna för e-postflöde i Security & Compliance Center](mail-flow-insights-v2.md).
