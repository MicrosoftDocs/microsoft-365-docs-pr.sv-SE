---
title: Konfigurera EOP till skräp post i hybrid miljöer
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa mer om hur du dirigerar skräp post till e-postmappar för användare i Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 15acc9ad87fa0c785998895d026dae036d9ddd7b
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547670"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>Konfigurera fristående EOP för att skicka skräp post till skräppostmappen i hybrid miljöer

> [!IMPORTANT]
> Det här avsnittet gäller endast för fristående EOP-kunder i hybrid miljöer. Det här avsnittet gäller inte för Microsoft 365-kunder med Exchange Online-postlådor.

Om du är en fristående Exchange Online Protection-kund (EOP) i en hybrid miljö måste du konfigurera den lokala Exchange-organisationen för att känna igen och översätta skräp post filtrerings verdicts för EOP, så att skräp post regeln i den lokala post lådan kan flytta meddelanden till mappen skräp post.

Specifikt måste du skapa regler för e-postflöden (kallas även transport regler) i din lokala Exchange-organisation med villkor som returnerar meddelanden med något av följande EOP skydd mot skräp post och värden, och åtgärder som ställer in den SCL (spam) för dessa meddelanden till 6:

- `X-Forefront-Antispam-Report: SFV:SPM` (meddelande som marker ATS som skräp post vid filtrering av skräp post)

- `X-Forefront-Antispam-Report: SFV:SKS` (meddelande som marker ATS som skräp post av regler för e-postflöde i EOP före skräp post filtrering)

- `X-Forefront-Antispam-Report: SFV:SKB` (meddelande som marker ATS som skräp post genom filtrering av skräp post på grund av avsändarens e-postadress eller e-postdomän i listan Blockerade avsändare eller listan blockerade domäner i EOP)

Mer information om dessa rubrik värden finns i [meddelande rubriker med skräp post](anti-spam-message-headers.md).

I det här avsnittet beskrivs hur du skapar de här e-postflödena för Exchange Admin Center (UK) och i Exchange Management Shell (Exchange PowerShell) i den lokala Exchange-organisationen.

> [!TIP]
> I stället för att skicka meddelanden till den lokala användarens skräppost-mapp kan du konfigurera principer för skräp post i EOP till skräp post meddelanden i EOP. Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste ha behörighet i den lokala Exchange-miljön innan du kan utföra dessa procedurer. Specifikt måste du ha tilldelats rollen **transport regler** , som tilldelats rollerna **organisations hantering**, **regelefterlevnad**och hantering av **Arkiv handlingar** . Mer information finns i [lägga till medlemmar i en roll grupp](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).

- Om och när ett meddelande skickas till mappen skräp post i en lokal Exchange-organisation styrs av en kombination av följande inställningar:

  - Parametern _SCLJunkThreshold_ i cmdleten [set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) i Exchange Management Shell. Standardvärdet är 4, vilket innebär att en SCL på 5 eller högre ska skicka meddelandet till användarens mapp för skräp post.

  - Värdet på parametern _SCLJunkThreshold_ i cmdleten [set-post låda](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) i Exchange Management Shell. Standardvärdet är blank ($null), vilket innebär att organisations inställningen används.

  Mer information finns i [tröskelvärden för skydd mot skräp post (SCL)](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).

  - Om regeln för skräp post är aktive rad på post lådan (det _aktiverade_ parametervärdet är $true i cmdleten [set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) i Exchange Management Shell). Det är skräp post regeln som faktiskt flyttar meddelandet till mappen skräp post efter leverans. Regeln för skräp post är aktive rad som standard för post lådor. Mer information finns i [Konfigurera inställningar för Exchange-antispam i post lådor](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).

- Information om hur du öppnar UK på en Exchange-Server finns i [administrations Center för Exchange i Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center). Information om hur du öppnar Exchange Management Shell finns i [Öppna Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).

- Mer information om regler för e-postflöden finns i följande avsnitt:

  - [Regler för e-postflöde i Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Villkor och undantag (predikat) i Exchange Server för regel för e-postflöde](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Åtgärder för e-postflödes regel i Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Använd UK för att skapa regler för e-postflöden som anger SCL för EOP spam-meddelanden

1. Gå till regler för **e-postflöde** i UK \> **Rules**.

2. Klicka på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) och välj **skapa en ny regel** i list rutan som visas.

3. På sidan **ny regel** som öppnas konfigurerar du följande inställningar:

   - **Namn**: Ange ett unikt, beskrivande namn för regeln. Ett exempel:

     - EOP SFV: SPM till SCL 6

     - EOP SFV: SKS till SCL 6

     - EOP SFV: SKB till SCL 6

   - Klicka på **fler alternativ**.

   - **Använd den här regeln om**: Välj **en meddelande rubrik** \> **innehåller något av dessa ord**.

     I **text rubriken ange ord** mening som visas gör du följande:

     - Klicka på **Ange text**. I dialog rutan **Ange rubrik namn** anger du **X-Forefront-antispam-Report** och klickar sedan på **OK**.

     - Klicka på  **Ange ord**. I dialog rutan **Ange ord eller fraser** som visas anger du ett av värdena för EOP spam (**SFV: SPM**, **SFV: SKS**eller **SFV: SKB**), klickar på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) och sedan på **OK**.

   - **Gör följande**: Välj **ändra meddelande egenskaper** \> **ange nivån för skräp post (SCL)**.

     I dialog rutan **Ange SCL** väljer du **6** (Standardvärdet är **5**).

   När du är klar klickar du på **Spara**

Upprepa de här stegen för återstående EOP spam Verdict värden (**SFV: SPM**, **SFV: SKS**eller **SFV: SKB**).

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Använd Exchange Management Shell för att skapa regler för e-postflöden som anger SCL för EOP spam-meddelanden

Använd följande syntax för att skapa de tre reglerna för e-postflöden:

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

Ett exempel:

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

Detaljerad information om syntax och parametrar finns i [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Gör något av följande om du vill kontrol lera att fristående EOP har kon figurer ATS för att skicka skräp post till skräppost-mappen i hybrid miljö:

- Gå till regler för **e-postflöde** i UK, \> **Rules**Välj regeln och klicka sedan på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) för att bekräfta inställningarna.

- I Exchange Management Shell ersätter du \<RuleName\> med namnet på regeln för e-postflöde och RUL följande kommando för att verifiera inställningarna:

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- I ett externt e-postsystem **som inte skannar utgående meddelanden för skräp post**kan du skicka ett allmänt test till en mottagare och bekräfta att det levereras till mappen skräp post. Ett GTUBE-meddelande liknar EICAR-textfilen (European Institute for Computer Antivirus Research) för att testa inställningar för skadlig kod.

  Skicka ett GTUBE meddelande genom att lägga till följande text i bröd texten i ett e-postmeddelande på en enda rad, utan blank steg eller rad brytningar:

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
