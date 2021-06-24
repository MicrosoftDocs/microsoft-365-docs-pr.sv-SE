---
title: Granska och hantera åtgärdsåtgärder i Microsoft Defender för Office 365
keywords: AIR, autoIR, Microsoft Defender för Slutpunkt, automatiserad, undersökning, svar, åtgärd, hot, avancerat, hot, skydd
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Läs mer om åtgärder i funktioner för automatisk undersökning och svar i Microsoft Defender för Office 365 abonnemang 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 06/10/2021
ms.openlocfilehash: 987771616acfd2f2faf425e525505b320155388e
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108541"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Granska och hantera åtgärdsåtgärder i Office 365

**Gäller för**
- [Microsoft Defender för Office 365 abonnemang 2](defender-for-office-365.md)

Eftersom automatiska undersökningar av e& och samarbetsinnehåll resulterar  i bedömningar, till exempel skadlig eller *misstänkt,* skapas vissa åtgärder. I Microsoft Defender Office 365 kan åtgärder som vidtas omfattar:

- Mjuk borttagning av e-postmeddelanden och kluster
- Stänga av vidarebefordran av extern e-post

Dessa åtgärder vidtas inte om inte och tills ditt säkerhetsoperationsteam godkänner dem. Vi rekommenderar att du granskar och godkänner eventuella väntande åtgärder så snart som möjligt så att de automatiserade undersökningarna kan slutföras i tid. I vissa fall kan du ändra din skickade åtgärd.  Du måste vara en del av rollen & först ta bort innan du vidtar några åtgärder.

## <a name="approve-or-reject-pending-actions"></a>Godkänna (eller avvisa) väntande åtgärder
Det finns fyra olika sätt att hitta och vidta åtgärder för automatisk undersökning:

- [Incidentkö](https://security.microsoft.com/incidents)
- [Åtgärdscenter](https://security.microsoft.com/action-center/pending)
- Själva undersökningen (åtkomst via incident eller från en avisering)
- [Kön för undersöknings- och åtgärdsundersökningar](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a>Incidentkö

1. Öppna Microsoft 365 Defender ( <https://security.microsoft.com> ) och logga in.
2. I navigeringsfönstret väljer du **Incidenter & eller > Incidenter.**
3. Välj namnet på ett incident så öppnas sammanfattningssidan.
4. Välj fliken **Bevis och** svar.
5. Markera ett objekt i listan. Sidofönstret öppnas.
6. Godkänn eller avvisa åtgärder i sidofönstret.

## <a name="investigation-queue"></a>Undersökningskö

1. Öppna Microsoft 365 Defender ( <https://security.microsoft.com> ) och logga in.
2. Navigera från sidan aviseringar/incidenter.
3. På sidan Undersökning går du till fliken **Väntande** åtgärder.
4. Markera ett objekt i listan. Sidofönstret öppnas.
5. Godkänn eller avvisa åtgärder i sidofönstret.

## <a name="action-center"></a>Åtgärdscenter

1. Öppna Microsoft 365 Defender ( <https://security.microsoft.com> ) och logga in.
2. Välj Åtgärdscenter i **navigeringsfönstret.**
3. Granska listan **över åtgärder** som väntar på godkännande på fliken Väntande.
   - Välj **Sidan Öppna undersökning** om du vill visa mer information om undersökningen.
   - Välj **Godkänn** för att påbörja en väntande åtgärd.
   - Välj **Avvisa** för att förhindra att en väntande åtgärd vidtas.

## <a name="investigation-and-remediation-investigations-queue"></a>Kön för undersöknings- och åtgärdsundersökningar

1. Öppna Microsoft 365 Defender ( <https://security.microsoft.com> ) och logga in.
2. Öppna väntande undersökningar.
3. På sidan Undersökning går du till fliken **Väntande** åtgärder.
4. Markera ett objekt i listan. Sidofönstret öppnas.
5. Godkänn eller avvisa åtgärder i sidofönstret.

## <a name="change-or-undo-one-remediation-action"></a>Ändra eller ångra en åtgärd

Det finns två olika sätt att ändra din skickade åtgärd:

- Via det [enhetliga åtgärdscentret](https://security.microsoft.com/action-center).
- Fast Office [åtgärdscenter](https://security.microsoft.com/threatincidents).

## <a name="change-or-undo-through-the-unified-action-center"></a>Ändra eller ångra i det enhetliga åtgärdscentret

1. Gå till [det enhetliga åtgärdscentret](https://security.microsoft.com/action-center) och logga in.
2. På fliken **Historik** väljer du en åtgärd som du vill ändra eller ångra.
3. I fönstret till höger på skärmen väljer du lämplig åtgärd **(flytta** till **Inkorgen,** gå till **skräppost,** flytta till borttagna objekt, **mjuk** borttagning eller **permanent borttagning**).

## <a name="change-or-undo-through-the-office-action-center"></a>Ändra eller ångra i Office åtgärdscenter

1. Gå till [Office åtgärdscenter](https://security.microsoft.com/threatincidents) och logga in.
2. Markera lämplig åtgärd.
3. I sidofönstret klickar du på posten för inskickade e-postmeddelanden och väntar på att listan läses in.
4. Vänta på åtgärdsknappen högst upp för att aktivera och välj knappen Åtgärd för att ändra åtgärdstyp.
5. Då skapas lämpliga åtgärder.

## <a name="next-steps"></a>Nästa steg

- [Använda Hotutforskaren](threat-explorer.md)
- [Admin/Manuella åtgärder](remediate-malicious-email-delivered-office-365.md)
- [Så här rapporterar du falska positiva/negativa tal i automatiska undersöknings- och svarsfunktioner](air-report-false-positives-negatives.md)

## <a name="see-also"></a>Se även

- [Visa information och resultat av en automatiserad undersökning i Office 365](air-view-investigation-results.md)
