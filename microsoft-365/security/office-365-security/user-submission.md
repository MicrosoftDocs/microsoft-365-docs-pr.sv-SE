---
title: Policy för användar inlägg
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratörer kan läsa hur du konfigurerar en post låda för att samla in skräp post och nätfiske som rapporteras av användare.
ms.openlocfilehash: 8f9da620643d46bf21a18eccc2047ad4361832cc
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865074"
---
# <a name="user-submissions-policy"></a>Policy för användar inlägg

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I Microsoft 365-organisationer med Exchange Online-postlådor kan du ange en post låda som tar emot meddelanden som användare rapporterar som skadlig eller inte skadlig. När användarna skickar meddelanden med olika rapporterings alternativ kan du använda den här post lådan för att avlyssna meddelanden (endast skicka till den anpassade post lådan) eller ta emot kopior av meddelanden (skicka till den anpassade post lådan och Microsoft). Den här funktionen fungerar med följande alternativ för meddelande rapportering:

- [Tillägget rapport](enable-the-report-message-add-in.md)

- [Tillägget rapportera nät fiske](enable-the-report-phish-add-in.md)

- [Inbyggd rapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (tidigare Outlook Web App)

- [Inbyggd rapportering i Outlook för iOS och Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > Om rapportering har [inaktiverats i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), åsidosätter du den inställningen och gör att användare kan rapportera meddelanden i Outlook på webben igen.

Du kan också konfigurera meddelande rapporterings verktyg från tredje part så att meddelanden vidarebefordras till den post låda som du anger.

Om du levererar rapporter till en egen post låda i stället för direkt till Microsoft kan administratören selektivt och manuellt rapportera meddelanden till Microsoft via [Administratörs överföring](admin-submission.md).

## <a name="custom-mailbox-prerequisites"></a>Anpassade krav för post lådor

Använd följande artiklar för att konfigurera förutsättningarna för att användare ska kunna rapportera meddelanden till din egen post låda:

- Hoppa över skräp post filtrering på den anpassade post lådan genom att skapa en regel för Exchange-flödesschema för att ange säkerhets nivån för skräp post. Se [använda UK för att skapa en regel för e-postflöde som anger SCL för ett meddelande](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) för att ange SCL till **-1**.

- Inaktivera genomsökning av bifogade filer för skadlig program vara i den anpassade post lådan. Använd [Konfigurera principer för säkra bifogade filer i Defender för Office 365](set-up-atp-safe-attachments-policies.md) för att skapa en policy för säker bifogade filer med inställningen **av** för **säkert bifogade filer med skadlig program vara**.

- Inaktivera URL-genomsökning för meddelanden i den anpassade post lådan. Använd [Konfigurera principer för säkra länkar i Defender för Office 365](set-up-atp-safe-links-policies.md) för att skapa en princip för säkra länkar med inställningen **av** för **Val av åtgärd för okända URL-adresser i meddelanden**.

- Skapa en princip för mot skadlig program vara för att inaktivera automatisk rensning av skadlig program vara. Se [använda säkerhets & Compliance Center för att skapa principer mot skadlig program](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) vara för att **Aktivera** **Automatisk borttagning av skadlig program vara** .

- Skapa en filter policy för skräp post för att avaktivera automatisk rensning (ZAP) för skräp post och nätfiske i den anpassade post lådan. Mer information finns i [använda säkerhets & Compliance Center för att skapa principer för skräp post](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) och avmarkera **kryss rutorna** för **skräp post ZAP** och **Phish ZAP**.

- Inaktivera skräp post regeln i den anpassade post lådan. Använd [Konfigurera inställningar för skräp post i Exchange Online-postlådor](configure-junk-email-settings-on-exo-mailboxes.md) för att inaktivera skräp post regeln. När det är inaktiverat kan EOP inte flytta meddelanden till mappen skräp post baserat på åtgärd för skräp post filtrering Verdict **flyttas meddelandet till mappen skräp post** eller säker lista-samlingen i post lådan.

När du har verifierat att post lådan uppfyller alla tillämpliga förutsättningar använder du [säkerhets & Compliance Center för att konfigurera post lådan för användar överföringar](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) (i den här artikeln).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till sidan **användar överföring** kan du använda <https://protection.office.com/userSubmissionsReportMessage> .

- Om du vill ändra konfigurationen för användar inlämningar måste du vara medlem i någon av följande roll grupper:

  - **Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).
  - **Organisations hantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Konfigurera e-postpost lådan för användare via säkerhets & efterlevnad

1. Gå till användar tillägget för **Threat Management** policy i säkerhets & efterlevnad \>  \> .

2. På sidan **användar inlägg** som visas väljer du något av följande alternativ:

   1. **Aktivera funktionen rapport meddelande för Outlook (rekommenderas)**: Välj det här alternativet om du använder tilläggsprogrammet rapportera tillägg, tillägget rapportera nät fiske eller den inbyggda rapporteringen i Outlook på webben och konfigurera sedan följande inställningar:

      - **Anpassa slutanvändarens bekräftelse meddelande**: Klicka på den här länken. Konfigurera följande inställningar i den utfällda **bekräftelse meddelandet** som visas:

      - **Före inlämning**: Ange den beskrivande text som användarna ser innan de rapporterar ett meddelande med hjälp av tillägget rapport eller rapport nät i meddelande rutan **rubrik** och **bekräftelse** . Du kan använda variabeln% Type% för att inkludera sändnings typen (skräp, inte skräp post, Phish, osv.).

        Om du väljer ett alternativ som skickar det rapporterade meddelandet till Microsoft läggs även följande text till i meddelandet:

        > Din e-post skickas till Microsoft för analys. Vissa e-postmeddelanden kan innehålla personlig eller känslig information.

      - **Efter sändning**: Klicka på ![ ikonen Expandera ](../../media/scc-expand-icon.png) . Ange den  beskrivande text som användarna ser efter att de har rapporterat ett meddelande med hjälp av tillägget rapport eller rapport nät.  Du kan använda variabel% Type% för att inkludera överförings typen.

      Klicka på **Spara** när du är klar. Om du vill rensa de här värdena klickar du på **Återställ** bakåt på sidan **användar inlägg** .

      - **Skicka rapporterade meddelanden till**: gör något av följande:

        - **Microsoft (rekommenderas)**: post lådan användar meddelanden används inte (alla rapporterade meddelanden skickas till Microsoft).

        - **Microsoft och en anpassad post låda**: i rutan som visas anger du e-postadressen för en befintlig Exchange Online-postlåda. Distributions grupper är inte tillåtet. Användar inlämningar kommer att gå till både Microsoft för analys och den anpassade post lådan för din administratör eller säkerhets åtgärd för att analysera.

        - **Anpassad post låda**: i rutan som visas anger du e-postadressen för en befintlig Exchange Online-postlåda. Distributions grupper är inte tillåtet. Använd det här alternativet om du vill att meddelandet endast ska skickas till en administratör eller säkerhets åtgärds teamet för analys. Meddelanden går inte till Microsoft såvida inte administratören vidarebefordrar det själva.

        > [!NOTE]
        > Amerikanska statliga organisationer (GCC, GCC-H och DoD) kan endast konfigurera **anpassade post lådor**. De två andra alternativen är inaktiverade.

      När du är klar klickar du på **Bekräfta**.

      > [!CAUTION]
      > Om du har [inaktiverat skräp post rapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) med hjälp av Outlook på principer för Internet-postlådor, men du konfigurerar något av de föregående inställningarna för att rapportera meddelanden till Microsoft, kan användarna rapportera meddelanden till Microsoft i Outlook på webben med hjälp av tilläggsprogrammet rapport meddelande eller rapport-nätfiske.

   - **Inaktivera funktionen rapport meddelande för Outlook**: Välj det här alternativet om du använder rapporterings verktyg från tredje part i stället för rapport tillägget, rapportens nätfiske-tillägg eller den inbyggda rapportering i Outlook på webben och konfigurera sedan följande inställningar:

      Välj **Använd den här anpassade post lådan för att ta emot inlämning av användare**. I rutan som visas anger du e-postadressen för en befintlig post låda som redan finns i Office 365. Detta måste vara en befintlig post låda i Exchange Online som kan ta emot e-post.

      När du är klar klickar du på **Bekräfta**.

## <a name="message-submission-format"></a>Meddelande överförings format

Meddelanden som skickas till anpassade post lådor måste följa ett visst e-postformat. Ämnets rubrik (Envelope) för sändningen ska vara i det här formatet:

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

där SafetyAPIAction är ett av följande heltals värden:

- 1: skräp post
- 2: inte skräp post
- 3: nätfiske

I följande exempel:

- Meddelandet rapporteras som nätfiske.
- Nätverks meddelandets ID är 49871234-6dc6-43e8-ABCD-08d797f20abe.
- Avsändarens IP är 167.220.232.101.
- Från-adressen är test@contoso.com.
- Meddelandets ämnesrad är "testa nätfiske"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

Meddelanden som inte följer det här formatet kommer inte att visas korrekt i portalen med inlämning.
