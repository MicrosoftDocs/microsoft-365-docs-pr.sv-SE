---
title: Granska och hantera åtgärder i Microsoft Defender för Office 365
keywords: AIR, autoIR, ATP, automatiserad, undersökning, svar, åtgärd, hot, avancerat, hot, skydd
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
ms.date: 01/29/2021
ms.openlocfilehash: 61e9df45419cc73dae27b86dad47e1938183593d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073657"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Granska och hantera åtgärder i Office 365

Eftersom automatiska undersökningar av e& och samarbetsinnehåll resulterar  i bedömningar, till exempel skadlig eller *misstänkt,* skapas vissa åtgärder. I Microsoft Defender för Office 365 kan åtgärder omfatta:
- Blockera en URL (tid för klickning)
- Mjuk borttagning av e-postmeddelanden och kluster
- Kvarantitiska e-postmeddelanden och e-postbilagor
- Stänga av vidarebefordran av extern e-post

Dessa åtgärder vidtas inte om inte och tills ditt säkerhetsoperationsteam godkänner dem. Vi rekommenderar att du granskar och godkänner eventuella väntande åtgärder så snart som möjligt så att de automatiserade undersökningarna kan slutföras i tid. I vissa fall kan du ångra en åtgärdsåtgärd.

**Gäller för**
- [Microsoft Defender för Office 365 abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="approve-or-reject-pending-actions"></a>Godkänna (eller avvisa) väntande åtgärder

1. Gå till Säkerhetscenter för Microsoft 365 ( <https://security.microsoft.com> ) och logga in.
2. Välj Åtgärdscenter i **navigeringsfönstret.**
3. Granska listan **över åtgärder** som väntar på godkännande på fliken Väntande.
4. Markera ett objekt i listan. Den utfällna rutan öppnas. 
5. Granska informationen i det utfällfönster som visas och gör sedan något av följande:
   - Välj **Sidan Öppna undersökning** om du vill visa mer information om undersökningen.
   - Välj **Godkänn** för att påbörja en väntande åtgärd.
   - Välj **Avvisa** för att förhindra att en väntande åtgärd vidtas.

## <a name="undo-one-remediation-action"></a>Ångra en åtgärd

1. Gå till Åtgärdscenter ( <https://security.microsoft.com/action-center> ) och logga in.
2. Välj **en åtgärd** som du vill ångra på fliken Historik.
3. I fönstret till höger på skärmen väljer du **Ångra**.

## <a name="undo-multiple-remediation-actions"></a>Ångra flera åtgärder

1. Gå till Åtgärdscenter ( <https://security.microsoft.com/action-center> ) och logga in.
2. Markera **de åtgärder** du vill ångra på fliken Historik. Se till att markera objekt som har samma åtgärdstyp. Ett utfällt fönster öppnas.
3. Välj Ångra i det utfällade fönstret.

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Ta bort en fil från karantän på flera enheter

1. Gå till Åtgärdscenter ( <https://security.microsoft.com/action-center> ) och logga in.
2. På fliken **Historik** väljer du en fil som har karantänfilen **Åtgärdstyp.**
3. I fönstret till höger på skärmen väljer du Använd för **fler X-instanser** av den här filen och sedan **Ångra**.

## <a name="next-steps"></a>Nästa steg

- [Använda Hotutforskaren](threat-explorer.md)
- [Så här rapporterar du falska positiva/negativa tal i automatiska undersöknings- och svarsfunktioner](air-report-false-positives-negatives.md)

## <a name="see-also"></a>Se även

- [Visa information och resultat från en automatiserad undersökning i Office 365](air-view-investigation-results.md)
