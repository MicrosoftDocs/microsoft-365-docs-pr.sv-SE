---
title: Skicka meddelanden manuellt till Microsoft för analys
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'Du och dina användare kan skicka falska negativa och falska positiva skräppostmeddelanden till Microsoft för analys. '
ms.openlocfilehash: 77807f710743d98dc2e1564f804b6a67add67def
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43529055"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Skicka meddelanden manuellt till Microsoft för analys

> [!NOTE]
> Om du är administratör i en Office 365-organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen Inlämningar i Office 365 Security & Compliance Center. Mer information finns i [Använda administratörsöverföring för att skicka misstänkt skräppost, phish, URL:er och filer till Microsoft](admin-submission.md).

Det kan vara frustrerande när användare i organisationen får skräppost eller nätfiskemeddelanden i inkorgen, eller om de inte får ett legitimt e-postmeddelande eftersom det är markerat som skräppost. Vi finjusterar ständigt våra skräppostfilter för att vara mer exakta.

Du och dina användare kan hjälpa den här processen genom att skicka in falska positiva identifieringar (bra e-post markerad som dålig), falska negativ (felaktig e-post tillåten) och nätfiskemeddelanden till Microsoft för analys.

> [!NOTE]
> På grund av den stora mängden inlagor som vi får kanske vi inte kan svara på alla förfrågningar om analys.

## <a name="submit-false-negatives-to-microsoft"></a>Skicka falska negativ till Microsoft

> [!TIP]
> I stället för att använda följande procedurer för att rapportera falska negativ kan användare i Outlook och Outlook på webben (tidigare kallat Outlook Web App) använda tillägget Rapportmeddelande för Microsoft Outlook. Information om hur du installerar och använder det här verktyget finns [i Aktivera tillägget Rapportmeddelande](enable-the-report-message-add-in.md).

Om du får ett meddelande som skickades genom skräppostfiltrering som borde ha identifierats som skräppost eller nätfiske kan du skicka meddelandet till microsofts team för skräppostanalys och Microsofts nätfiskeanalys efter behov. Analytikerna granskar meddelandet och lägger till det i de serviceomfattande filtren om det uppfyller klassificeringskriterierna.

1. Skapa ett nytt, tomt e-postmeddelande med någon av följande mottagare:

   - **Skräp:**`junk@office365.microsoft.com`

   - **Nätfiske:**`phish@office365.microsoft.com`

2. Dra och släpp skräppost- eller nätfiskemeddelandet i det nya meddelandet. Detta sparar skräppost- eller nätfiskemeddelandet som en bifogad fil i det nya meddelandet. Kopiera och klistra inte in innehållet i meddelandet eller vidarebefordra meddelandet (vi behöver det ursprungliga meddelandet så att vi kan inspektera meddelanderubrikerna).

   > [!NOTE]
   > <ul><li>Du kan bifoga flera meddelanden i det nya meddelandet. Kontrollera att alla meddelanden är av samma typ: antingen meddelanden om nätfiske eller skräppost.</li><li>Lämna brödtexten i det nya meddelandet tom.</li><li>Använd antingen MSG-format (standardformatet Outlook) eller .eml (standardformatet Outlook på webben) för de bifogade meddelandena.</li></ul>

3. När du är klar klickar du på **Skicka**.

> [!TIP]
> Administratörer har flera olika sätt att blockera specifika meddelanden som felidentifieras som skräppost. Mer information finns [i Skapa blockerade avsändarelistor i Office 365](create-block-sender-lists-in-office-365.md).

## <a name="submit-false-positives-to-microsoft"></a>Skicka falska positiva identifieringar till Microsoft

> [!TIP]
> I stället för att använda följande procedurer för att rapportera falska positiva identifieringar kan användare i Outlook och Outlook på webben använda tillägget Rapportmeddelande för Microsoft Outlook. Information om hur du installerar och använder det här verktyget finns [i Aktivera tillägget Rapportmeddelande](enable-the-report-message-add-in.md).

Om ett meddelande har identifierats felaktigt som skräppost kan du skicka meddelandet till Microsoft Spam Analysis Team. Analytikerna kommer att utvärdera meddelandet, och (beroende på resultaten av analysen) kan de serviceomfattande filtren justeras så att meddelandet går igenom.

1. Skapa ett nytt, tomt `not_junk@office365.microsoft.com` e-postmeddelande med som mottagare:

2. Dra och släpp det felidentifierade meddelandet i det nya meddelandet. Då sparas det felidentifierade meddelandet som en bifogad fil i det nya meddelandet. Kopiera och klistra inte in innehållet i meddelandet eller vidarebefordra meddelandet (vi behöver det ursprungliga meddelandet så att vi kan inspektera meddelanderubrikerna).

   > [!NOTE]
   > <ul><li>Du kan bifoga flera meddelanden i det nya meddelandet. Kontrollera att alla meddelanden är av samma typ: antingen nätfiskemeddelanden eller skräppostmeddelanden.</li><li>Lämna brödtexten i det nya meddelandet tom.</li><li>Använd antingen MSG-format (standardformatet Outlook) eller .eml (standardformatet Outlook på webben) för de bifogade meddelandena.</li></ul>

3. När du är klar klickar du på **Skicka**.

> [!TIP]
> Administratörer har flera olika sätt att tillåta specifika meddelanden att hoppa över skräppostfiltrering. Mer information finns [i Skapa listor över betrodda avsändare i Office 365](create-safe-sender-lists-in-office-365.md).

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Skapa en regel för e-postflöde för att ta emot kopior av meddelanden som rapporteras till Microsoft

Du kan skapa en regel för e-postflöde (kallas även en transportregel) som söker efter e-postmeddelanden som rapporteras till Microsoft med hjälp av de metoder som beskrivs i det här avsnittet, och du kan konfigurera mottagare av hemlig kopia så att de tar emot kopior av dessa rapporterade meddelanden.

Du kan skapa e-postflödesregeln i Administrationscenter för Exchange (EAC) och PowerShell (Exchange Online PowerShell för Office 365-kunder. Exchange Online Protection PowerShell för fristående EOP-kunder).

### <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste tilldelas behörigheter i Exchange Online innan du kan göra dessa procedurer. Du måste ha tilldelats rollen **Transportregler,** som tilldelas rollerna **Organisationshantering,** **Efterlevnadshantering**och **Arkivhandling** som standard. Mer information finns [i Hantera rollgrupper i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Information om hur du öppnar EAC i Exchange Online finns [i Administrationscenter för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Information om hur du använder Windows PowerShell för att ansluta till fristående Exchange Online Protection PowerShell finns i artikeln om att [ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Mer information om regler för e-postflöde i Exchange Online och fristående EOP finns i följande avsnitt:

  - [Regler för e-postflöde (transportregler) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Villkor och undantag för e-postflödesregel (predikat) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Regelåtgärder för e-postflöde i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

### <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Använda EAC för att skapa en regel för e-postflöde för att ta emot kopior av rapporterade meddelanden

1. Gå till **Regler för** **e-postflöde** \> i EAC .

2. Klicka på](../../media/ITPro-EAC-AddIcon.png) Ikonen Lägg **till** ![och välj sedan Skapa en ny **regel**.

3. Konfigurera följande inställningar på sidan **Ny regel** som öppnas:

   - **Namn**: Ange ett unikt, beskrivande namn för regeln. Till exempel hemlig kopia meddelanden som rapporterats till Microsoft.

   - Klicka på **Fler alternativ**.

   - **Använd den här regeln om:** Välj **Mottagaradressen** \> **innehåller något av dessa ord**: I dialogrutan Ange ord eller **fraser** anger du ett av följande värden, klickar på **Lägg till** ![ikon](../../media/ITPro-EAC-AddIcon.png)och upprepar tills du har angett alla värden.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     Om du vill redigera en post](../../media/ITPro-EAC-EditIcon.png)markerar du den och klickar på **Ikonen Redigera** ![redigering . Om du vill ta bort en](../../media/ITPro-EAC-DeleteIcon.png)post markerar du den och klickar på Ikonen Ta bort ta **bort** ![.

     När du är klar klickar du på **OK**.

   - **Gör så här:** Välj **Lägg till mottagare** \> **i rutan Hemlig kopia**. Leta reda på och markera de mottagare som du vill lägga till i dialogrutan som visas. När du är klar klickar du på **OK**.

4. Du kan göra ytterligare val för att granska regeln, testa regeln, aktivera regeln under en viss tidsperiod och andra inställningar. Vi rekommenderar att du testar regeln innan du tillämpar den.

5. Klicka på **Spara** när du är klar.

### <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Använda PowerShell för att skapa en regel för e-postflöde för att ta emot kopior av rapporterade meddelanden

I det här exemplet skapas en ny regel för e-postflöde med namnet Hemlig kopia meddelanden som rapporterats till Microsoft och som söker efter e-postmeddelanden som rapporteras till Microsoft med hjälp av de metoder som beskrivs i det här avsnittet och lägger till användarna laura@contoso.com och julia@contoso.com som mottagare av hemlig kopia.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Detaljerad information om syntax och parametrar finns i [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Så här kontrollerar du att du har konfigurerat regler för e-postflöde för att ta emot kopior av rapporterade meddelanden:

- Gå till EAC-regler för att skicka **Edit** ![till](../../media/ITPro-EAC-EditIcon.png) **E-postflödesregler** \> **Rules** \> och markera regeln \> klicka på Redigera redigera ikon och kontrollera inställningarna.

- I PowerShell kör du följande kommando för att verifiera inställningarna:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Skicka ett testmeddelanden till en av de rapporterande e-postadresserna och verifiera resultaten.
