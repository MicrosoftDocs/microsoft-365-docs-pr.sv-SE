---
title: Administratörsgranskning för rapporterade meddelanden
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Lär dig hur du granskar meddelanden som rapporteras och ger feedback till användarna.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 217f5ebb1692d68b5dc70988888bf78d4bd36a0c
ms.sourcegitcommit: d0c160e89e17f451199bc4a85699effd2d935213
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52893734"
---
# <a name="admin-review-for-reported-messages"></a>Administratörsgranskning för rapporterade meddelanden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> Informationen i den här artikeln gäller en förhandsversion av en produkt som kan komma att ändras väsentligt innan den släpps till kommersiellt bruk. Det här dokumentet tillhandahålls endast för utvärderings- och utforskningssyfte.

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365 organisationer med Exchange Online-postlådor och Microsoft Defender för Office 365 kan administratörer nu skicka tillbaka mallade meddelanden till slutanvändarna när de har granskat rapporterade meddelanden. Det kan anpassas för din organisation och utifrån administratörens bedömning också.

Den här funktionen är utformad för att ge feedback till användarna men påverkar inte bedömningarna av meddelanden i systemet. Om du vill hjälpa Microsoft att uppdatera och förbättra filter måste du skicka meddelanden för analys med hjälp av [administratörsinskick.](admin-submission.md)

Du kan bara markera och meddela användarna om [granskningsresultat](report-false-positives-and-false-negatives.md)om meddelandet har rapporterats som falskt positivt eller falskt negativa.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du öppnar Microsoft 365 Defender-portalen på <https://security.microsoft.com/> . Använd för att gå **direkt till sidan** Inskickade <https://security.microsoft.com/reportsubmission> material.

- Du måste vara medlem i någon av följande rollgrupper för att kunna ändra konfigurationen för användarinskick:
  - Organisationshantering eller säkerhetsadministratör i [Microsoft 365 Defender-portalen](permissions-microsoft-365-security-center.md).
  - Organisationshantering i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

- Du behöver också åtkomst till Exchange Online PowerShell. Om kontot som du försöker använda inte har åtkomst till Exchange Online PowerShell visas felmeddelandet Ange en e-postadress i *din domän.* Mer information om hur du aktiverar eller inaktiverar åtkomst till Exchange Online PowerShell finns i följande avsnitt:
  - [Aktivera eller inaktivera åtkomst till Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [Klientåtkomstregler i Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a>Konfigurera meddelanden som används för att meddela användarna

1. I Microsoft 365 Defender-portalen går du till Principer för **&-&** e-& principer för hot andra avsnittet \>  \>  \>  \> **Användarrapporterade meddelandeinställningar**.

2. Om du vill ange avsändarens visningsnamn på sidan Användarinskickade användare markerar du kryssrutan för  Ange Office 365-e-postadress som ska användas som avsändare under avsnittet E-postaviseringar för **administratörsgranskningsresultat** och anger det namn du vill använda.  Det här är den e-postadress som visas i Outlook svar skickas till.

3. Om du vill anpassa någon av mallarna klickar du på Anpassa **e-postavisering**. I den här utfällningen kan du bara anpassa följande:
    - Fiske
    - Skräppost
    - Inga hot hittades
    - Utbildning om information
    - Sidfot

4. Klicka på **Spara** när du är klar. Om du vill ta bort dessa värden **klickar du på** Ta bort på sidan Användarinskick.
