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
ms.openlocfilehash: e9550ce6357ddf19041e752c17e8bd844cba1a11
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726492"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a>Ange en postlåda för användarinlämningar av skräppost och nätfiskemeddelanden i Exchange Online

I Microsoft 365-organisationer med Exchange Online-postlådor kan du ange en postlåda för att ta emot meddelanden som användarna rapporterar som skadliga eller inte skadliga. När användare skickar meddelanden med de olika rapporteringsalternativen kan du använda den här postlådan för att avlyssna meddelanden (skicka till endast den anpassade postlådan) eller ta emot kopior av meddelanden (skicka till den anpassade postlådan och Microsoft). Den här funktionen fungerar med följande alternativ för meddelanderapportering:

- [Tillägget Rapportmeddelande](enable-the-report-message-add-in.md)

- [Inbyggd rapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (tidigare känd som Outlook Web App)

  > [!NOTE]
  > Om rapporteringen har [inaktiverats i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)åsidosätts den inställningen om du aktiverar användarinlämningar här och gör det möjligt för användare att rapportera meddelanden i Outlook på webben igen.

Du kan också konfigurera meddelanderapporteringsverktyg från tredje part för att vidarebefordra meddelanden till den postlåda som du anger.

Genom att leverera rapporterade meddelanden till en anpassad postlåda i stället för direkt till Microsoft kan administratörerna selektivt och manuellt rapportera meddelanden till Microsoft med hjälp av [admin-inlämning](admin-submission.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till sidan **Användares inlämningar** använder du <https://protection.office.com/userSubmissionsReportMessage> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste tilldelas behörigheter innan du kan göra procedurerna i det här avsnittet:

  - Om du vill ändra konfigurationen för användaröverföringar måste du vara medlem i någon av följande rollgrupper:

    - **Organisationshantering** eller **säkerhetsadministratör** i [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Organisationshantering** eller **hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - För skrivskyddad åtkomst till användarinlämningar måste du vara medlem i någon av följande rollgrupper:

    - **Säkerhetsläsaren** i [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Endast visningsorganisation i** [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Använda Security & Compliance Center för att konfigurera postlådan för användarinlämningar

1. Gå till användarinlämningar för **&-efterlevnadsprincipen** i Security & Compliance \> **Policy** \> **Center**.

2. På sidan **Användares inlämningar** som visas väljer du något av följande alternativ:

   a. **Aktivera funktionen Rapportmeddelande för Outlook (rekommenderas):** Välj det här alternativet om du använder tillägget Rapportmeddelande eller den inbyggda rapporteringen i Outlook på webben och sedan konfigurerar följande inställningar:

      - **Anpassa bekräftelsemeddelandet för slutanvändare:** Klicka på den här länken. Konfigurera följande inställningar i det utfällbara meddelandet **Anpassa bekräftelsemeddelandet** som visas:

      - **Innan du skickar in**: I **meddelanderutorna** **Rubrik** och Bekräftelse anger du den beskrivande text som användarna ser innan de rapporterar ett meddelande med tillägget Rapportmeddelande. Du kan använda variabeln %type% för att inkludera inlämningstypen (skräp, inte skräp, phish, etc.).

        Som nämnts, om du väljer ett alternativ som skickar de rapporterade meddelandena till Microsoft, läggs även följande text till i meddelandet:

        > Din e-post skickas som den är till Microsoft för analys. Vissa e-postmeddelanden kan innehålla personlig eller känslig information.

      - **Efter inlämning:** Klicka på ![ ikonen Expandera ](../../media/scc-expand-icon.png) . I rutorna **Rubrik** och **Bekräftelse anger** du den beskrivande text som användarna ser när de har rapporterat ett meddelande med tillägget Rapportmeddelande. Du kan använda variabeln %type% för att inkludera inlämningstypen.

      Klicka på **Spara** när du är klar. Om du vill ta bort dessa värden klickar du på **Återställ** igen på sidan **Användares inlämningar.**

      - **Skicka de rapporterade meddelandena till**: Gör något av följande val:

        - **Microsoft (Rekommenderas)**: Brevlådan för användarinlämningar används inte (alla rapporterade meddelanden går till Microsoft).

        - **Microsoft och en anpassad postlåda**: Ange e-postadressen till en befintlig Exchange Online-postlåda i rutan som visas. Distributionsgrupper är inte tillåtna. Användarinlämningar går till både Microsoft för analys och till den anpassade postlådan för din administratör eller säkerhetsoperationsteam att analysera.

        - **Anpassad postlåda**: Ange e-postadressen till en befintlig Exchange Online-postlåda i rutan som visas. Distributionsgrupper är inte tillåtna. Använd det här alternativet om du vill att meddelandet bara ska gå till en administratör eller säkerhetsoperationsgruppen för analys först. Meddelanden går inte till Microsoft om inte administratören vidarebefordrar det själva.

        > [!NOTE]
        > Amerikanska regeringsorganisationer (GCC, GCC-H och DoD) kan bara konfigurera **anpassad postlåda**. De andra två alternativen är inaktiverade. 

      När du är klar klickar du på **Bekräfta**.

      > [!CAUTION]
      > Om du har [inaktiverat skräppostrapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) med Outlook på webbpostlådeprinciperna, men konfigurerar någon av de tidigare inställningarna för att rapportera meddelanden till Microsoft, kan användarna rapportera meddelanden till Microsoft i Outlook på webben med tillägget Rapportmeddelande.

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
- Avsändare IP är 167.220.232.101.
- Från-adressen är test@contoso.com.
- Meddelandets ämnesrad är "test phish submission"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

Meddelanden som inte följer det här formatet visas inte korrekt i portalen för inlämningar.
