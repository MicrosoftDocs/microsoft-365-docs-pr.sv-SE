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
ms.openlocfilehash: 2931171d8e2dcd26593904385aec872c8967abf4
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213358"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a>Ange en postlåda för användarinlämningar av skräppost och nätfiskemeddelanden i Exchange Online

I Microsoft 365-organisationer med Exchange Online-postlådor kan du ange en postlåda för att ta emot meddelanden som användarna rapporterar som skadliga eller inte skadliga. När användare skickar meddelanden med de olika rapporteringsalternativen kan du använda den här postlådan för att avlyssna meddelanden (endast skicka till den anpassade postlådan) eller ta emot kopior av meddelanden (skicka till den anpassade postlådan och Microsoft). Den här funktionen fungerar med följande alternativ för meddelanderapportering:

- [Tillägget Rapportmeddelande](enable-the-report-message-add-in.md)

- [Inbyggd rapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (tidigare kallat Outlook Web App)

Du kan också konfigurera meddelanderapporteringsverktyg från tredje part för att vidarebefordra meddelanden till den postlåda som du anger.

Genom att leverera rapporterade meddelanden till en anpassad postlåda i stället för direkt till Microsoft kan administratörerna selektivt och manuellt rapportera meddelanden till Microsoft med hjälp av [admin-inlämning](admin-submission.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till sidan **Användares inlämningar** använder du <https://protection.office.com/userSubmissionsReportMessage> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Om du vill konfigurera postlådan för användaröverföringar måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.** Mer information om rollgrupper i säkerhets- och efterlevnadscentret finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Använda Security & Compliance Center för att konfigurera postlådan för användarinlämningar

1. Gå till användarinlämningar för **&-efterlevnadsprincipen** i Security & Compliance Center \> **Policy** \> **User submissions**.

2. På sidan **Användares inlämningar** som visas väljer du något av följande alternativ:

   - **Aktivera funktionen Rapportmeddelande för Outlook (rekommenderas):** Välj det här alternativet om du använder tillägget Rapportmeddelande eller den inbyggda rapporteringen i Outlook på webben och sedan konfigurerar följande inställningar:

     - **Anpassa bekräftelsemeddelandet för slutanvändare:** Klicka på den här länken. Konfigurera följande inställningar i det utfällbara meddelandet **Anpassa bekräftelsemeddelandet** som visas:

       - **Innan du skickar in**: I **meddelanderutorna** **Rubrik** och Bekräftelse anger du den beskrivande text som användarna ser innan de rapporterar ett meddelande med tillägget Rapportmeddelande. Du kan använda variabeln %type% för att inkludera inlämningstypen (skräp, inte skräp, phish, etc.).

         Som nämnts läggs även följande text till i anmälan:

         > Din e-post skickas som den är till Microsoft för analys. Vissa e-postmeddelanden kan innehålla personlig eller känslig information.

       - **Efter inlämning:** Klicka på ![ ikonen Expandera ](../../media/scc-expand-icon.png) . I meddelanderutorna **Rubrik** och **Bekräftelse** anger du den beskrivande text som användarna ser när de har rapporterat ett meddelande med tillägget Rapportmeddelande. Du kan använda variabeln %type% för att inkludera inlämningstypen.

      Klicka på **Spara** när du är klar. Om du vill ta bort dessa värden klickar du på **Återställ** igen på sidan **Användares inlämningar.**

   - **Skicka de rapporterade meddelandena till**: Gör något av följande val:

     - **Microsoft (Rekommenderas)**: Brevlådan för användarinlämningar används inte (alla rapporterade meddelanden går till Microsoft).

     - **Microsoft och en anpassad postlåda**: Ange e-postadressen till en befintlig Exchange Online-postlåda i rutan som visas. Distributionsgrupper är inte tillåtna.

     - **Anpassad postlåda**: Ange e-postadressen till en befintlig Exchange Online-postlåda i rutan som visas. Distributionsgrupper är inte tillåtna.

     När du är klar klickar du på **Bekräfta**.

     ![Skicka rapporterade meddelanden till Microsoft och en anpassad postlåda](../../media/user-submission-enable-outlook-report-message.png)

   - **Inaktivera funktionen Rapportmeddelande för Outlook:** Välj det här alternativet om du använder rapporteringsverktyg från tredje part i stället för tillägget Rapportmeddelande eller den inbyggda rapporteringen i Outlook på webben och sedan konfigurerar följande inställningar:

     Välj **Använd den här anpassade postlådan för att ta emot användarrapporterade inlämningar**. I rutan som visas anger du e-postadressen till en befintlig postlåda eller e-postadressen till den postlåda som du vill skapa.

     När du är klar klickar du på **Bekräfta**.

     ![Skicka rapporterade meddelanden till en anpassad postlåda med hjälp av verktyg från tredje part](../../media/user-submission-disable-outlook-report-message.png)
