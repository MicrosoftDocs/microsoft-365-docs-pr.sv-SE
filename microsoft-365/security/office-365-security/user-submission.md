---
title: Ange en postlåda för användarinlämningar av skräppost och nätfiskemeddelanden
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur du konfigurerar en postlåda för att samla in skräppost och nätfiske e-post som rapporteras av användare.
ms.openlocfilehash: d3ff44957864e3d5e959d6252d1d538cc715ae92
ms.sourcegitcommit: 8d9509e617ede7cc5ba933c54fb9300d2d1c6344
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/22/2020
ms.locfileid: "44347813"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a>Ange en postlåda för användarinlämningar av skräppost och nätfiskemeddelanden i Exchange Online

I Microsoft 365-organisationer med Exchange Online-postlådor kan du ange en postlåda för att ta emot meddelanden som användarna rapporterar som skadliga eller inte skadliga. När användare skickar meddelanden med de olika rapporteringsalternativen kan du använda den här postlådan för att avlyssna meddelanden (endast skicka till den anpassade postlådan) eller ta emot kopior av meddelanden (skicka till den anpassade postlådan och Microsoft). Den här funktionen fungerar med följande alternativ för meddelanderapportering:

- [Tillägget Rapportmeddelande](enable-the-report-message-add-in.md)

- [Inbyggd rapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (tidigare kallat Outlook Web App)

  > [!NOTE]
  > Om rapporteringen har [inaktiverats i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)åsidosätter inställningen om du aktiverar användarinlämningar här och gör det möjligt för användare att rapportera meddelanden i Outlook på webben igen.

Du kan också konfigurera meddelanderapporteringsverktyg från tredje part för att vidarebefordra meddelanden till den postlåda som du anger.

Genom att leverera rapporterade meddelanden till en anpassad postlåda i stället för direkt till Microsoft kan administratörerna selektivt och manuellt rapportera meddelanden till Microsoft med hjälp av [admin-inlämning](admin-submission.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till sidan **Användares inlämningar** använder du <https://protection.office.com/userSubmissionsReportMessage> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna. Om du vill konfigurera postlådan för användaröverföringar måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.** Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Använda Security & Compliance Center för att konfigurera postlådan för användarinlämningar

1. Gå till användarinlämningar för **&-efterlevnadsprincipen** i Security & Compliance Center \> **Policy** \> **User submissions**.

2. På sidan **Användares inlämningar** som visas väljer du något av följande alternativ:

   a. **Aktivera funktionen Rapportmeddelande för Outlook (rekommenderas):** Välj det här alternativet om du använder tillägget Rapportmeddelande eller den inbyggda rapporteringen i Outlook på webben och sedan konfigurerar följande inställningar:

      - **Anpassa bekräftelsemeddelandet för slutanvändare:** Klicka på den här länken. Konfigurera följande inställningar i det utfällbara meddelandet **Anpassa bekräftelsemeddelandet** som visas:

      - **Innan du skickar in**: I **meddelanderutorna** **Rubrik** och Bekräftelse anger du den beskrivande text som användarna ser innan de rapporterar ett meddelande med tillägget Rapportmeddelande. Du kan använda variabeln %type% för att inkludera inlämningstypen (skräp, inte skräp, phish, etc.).

        Som nämnts, om du väljer ett alternativ som skickar de rapporterade meddelandena till Microsoft, läggs även följande text till i meddelandet:

        > Din e-post skickas som den är till Microsoft för analys. Vissa e-postmeddelanden kan innehålla personlig eller känslig information.

      - **Efter inlämning:** Klicka på ![ ikonen Expandera ](../../media/scc-expand-icon.png) . I meddelanderutorna **Rubrik** och **Bekräftelse** anger du den beskrivande text som användarna ser när de har rapporterat ett meddelande med tillägget Rapportmeddelande. Du kan använda variabeln %type% för att inkludera inlämningstypen.

      Klicka på **Spara** när du är klar. Om du vill ta bort dessa värden klickar du på **Återställ** igen på sidan **Användares inlämningar.**

      - **Skicka de rapporterade meddelandena till**: Gör något av följande val:

        - **Microsoft (Rekommenderas)**: Brevlådan för användarinlämningar används inte (alla rapporterade meddelanden går till Microsoft).

        - **Microsoft och en anpassad postlåda**: Ange e-postadressen till en befintlig Exchange Online-postlåda i rutan som visas. Distributionsgrupper är inte tillåtna. Användarinlämningar går till både Microsoft för analys och till den anpassade postlådan för din administratör eller säkerhetsoperationsteam att analysera.

        - **Anpassad postlåda**: Ange e-postadressen till en befintlig Exchange Online-postlåda i rutan som visas. Distributionsgrupper är inte tillåtna. Använd det här alternativet om du vill att meddelandet bara ska gå till en administratör eller säkerhetsoperationsgruppen för analys först. Meddelanden går inte till Microsoft om inte administratören vidarebefordrar det själva.

        > [!NOTE]
        > Amerikanska regeringsorganisationer (GCC, GCC-H och DoD) kan bara konfigurera **anpassad postlåda**. De andra två alternativen är inaktiverade. 

      När du är klar klickar du på **Bekräfta**.

      > [!CAUTION]
      > Om du har [inaktiverat skräppostrapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) med Outlook i principerna för webbpostlådor, men konfigurerar någon av de tidigare inställningarna för att rapportera meddelanden till Microsoft, kan användarna rapportera meddelanden till Microsoft i Outlook på webben med tillägget Rapportmeddelande.

   - **Inaktivera funktionen Rapportmeddelande för Outlook:** Välj det här alternativet om du använder rapporteringsverktyg från tredje part i stället för tillägget Rapportmeddelande eller den inbyggda rapporteringen i Outlook på webben och sedan konfigurerar följande inställningar:

      Välj **Använd den här anpassade postlådan för att ta emot användarrapporterade inlämningar**. I rutan som visas anger du e-postadressen till en befintlig postlåda som redan finns i Office 365. Detta måste vara en befintlig postlåda i Exchange Online som kan ta emot e-post.

      När du är klar klickar du på **Bekräfta**.

## <a name="message-submission-format"></a>Format för meddelandeöverföring

Meddelanden som skickas till anpassade postlådor måste följa ett specifikt e-postformat för inlämning. Ämnet (kuvertrubriken) för inlämningen bör vara i detta format:

`SafetyAPIAction|NetworkMessgeId|SenderIp|FromAddress|(Message Subject)`

var SafetyAPIAction är ett av följande heltalsvärden:

- 1: Skräp
- 2: NotJunk
- 3: Phish

I följande exempel:

- Meddelandet rapporteras som Phish.
- Nätverksmeddelande-ID är 49871234-6dc6-43e8-abcd-08d797f20abe.
- Avsändarens IP är 167.220.232.101.
- Från-adressen är test@contoso.com.
- Meddelandets ämnesrad är "test phish submission"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

Meddelanden som inte följer det här formatet visas inte korrekt i portalen för inlämningar.
