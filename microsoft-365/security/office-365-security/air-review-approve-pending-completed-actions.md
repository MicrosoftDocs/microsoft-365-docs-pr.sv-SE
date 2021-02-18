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
description: Läs mer om åtgärder för automatisk undersökning och svar i Microsoft Defender för Office 365 abonnemang 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: a11e9ee6a4c2426951fe2b4aa4f2dd08d1931f1c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287119"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Granska och hantera åtgärder i Office 365

Eftersom automatiska undersökningar av e& och samarbetsinnehåll resulterar  i bedömningsresultat, till exempel skadliga eller *misstänkta,* skapas vissa åtgärder. I Microsoft Defender för Office 365 kan åtgärder omfatta:
- Blockera en URL (tid för klickning)
- Mjuk borttagning av e-postmeddelanden och kluster
- Kvartil som e-post eller e-postbilagor
- Stänga av vidarebefordran av extern e-post

Dessa åtgärder vidtas inte om inte och tills säkerhetsteamet godkänner dem. Vi rekommenderar att du granskar och godkänner alla väntande åtgärder så snart som möjligt så att de automatiserade undersökningarna slutförs i tid. I vissa fall kan du ångra en åtgärdsåtgärd.

**Gäller för**
- [Microsoft Defender för Office 365 abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

## <a name="approve-or-reject-pending-actions"></a>Godkänna (eller avvisa) väntande åtgärder

1. Gå till Microsoft 365 [https://security.microsoft.com](https://security.microsoft.com) säkerhetscenter) och logga in.
2. Välj Åtgärdscenter i **navigeringsfönstret.**
3. Granska **listan över åtgärder** som väntar på godkännande på fliken Väntande.
4. Markera ett objekt i listan. Det utfällfönster som visas. 
5. Granska informationen i det utfällfönster och gör sedan något av följande:
   - Välj **sidan Öppna undersökning** om du vill visa mer information om undersökningen.
   - Välj **Godkänn** för att påbörja en väntande åtgärd.
   - Välj **Avvisa** om du vill förhindra att en väntande åtgärd vidtas.

## <a name="undo-one-remediation-action"></a>Ångra en åtgärdsåtgärd

1. Gå till Åtgärdscenter [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () och logga in.
2. Välj en **åtgärd** som du vill ångra på fliken Historik.
3. Välj Ångra i fönstret till höger på **skärmen.**

## <a name="undo-multiple-remediation-actions"></a>Ångra flera åtgärder

1. Gå till Åtgärdscenter [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () och logga in.
2. Markera **de** åtgärder som du vill ångra på fliken Historik. Se till att markera objekt som har samma åtgärdstyp. Ett utfällt fönster öppnas.
3. Välj Ångra i det utfällade fönstret.

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Ta bort en fil från karantän på flera enheter

1. Gå till Åtgärdscenter [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () och logga in.
2. Välj en **fil** som har karantänfilen åtgärdstyp på **fliken Historik.**
3. I fönstret till höger på skärmen väljer du Använd för **fler X-förekomster** av den här filen och sedan **Ångra.**

## <a name="next-steps"></a>Nästa steg

- [Använda HotUtforskaren](threat-explorer.md)
- [Hur du rapporterar falska positiva/negativa tal i automatiserad undersökning och svarsfunktioner](air-report-false-positives-negatives.md)

## <a name="see-also"></a>Se även

- [Visa information och resultat av en automatiserad undersökning i Office 365](air-view-investigation-results.md)
