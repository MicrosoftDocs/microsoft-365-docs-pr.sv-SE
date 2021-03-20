---
title: Konfigurera EOP för skräppost i hybridmiljöer
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig att dirigera skräppost till användarnas skräppostmappar i en Exchange Online Protection-hybridmiljö.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae6ee551d04b242891c9638d6d99d79240480d27
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910864"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>Konfigurera fristående EOP för att leverera skräppost till skräppostmappen i hybridmiljöer

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
-  [Exchange Online Protection fristående](exchange-online-protection-overview.md)

> [!IMPORTANT]
> Det här avsnittet gäller endast fristående EOP-kunder i hybridmiljöer. Det här avsnittet gäller inte för Microsoft 365-kunder med Exchange Online-postlådor.

Om du är en fristående Exchange Online Protection-kund (EOP) i en hybridmiljö måste du konfigurera den lokala Exchange-organisationen så att den känner igen och översätter EOP-filtreringsorden, så att skräppostregeln i den lokala postlådan kan flytta meddelanden till mappen Skräppost.

Specifikt måste du skapa e-postflödesregler (kallas även transportregler) i den lokala Exchange-organisationen med villkor som hittar meddelanden med någon av följande EOP-värden som skydd mot skräppost och åtgärder som anger SCL (Spam Confidence Level) för dessa meddelanden till 6:

- `X-Forefront-Antispam-Report: SFV:SPM` (meddelande som har markerats som skräppost med skräppostfiltrering)

- `X-Forefront-Antispam-Report: SFV:SKS` (Meddelande som har markerats som skräppost av e-postflödesregler i EOP före skräppostfiltrering)

- `X-Forefront-Antispam-Report: SFV:SKB` (Meddelande som har markerats som skräppost av skräppostfiltrering på grund av att avsändarens e-postadress eller e-postdomän finns med i listan över spärrade avsändare eller spärrade domäner i EOP)

Mer information om dessa huvudvärden finns i [Rubriker för skräppostskydd.](anti-spam-message-headers.md)

I det här avsnittet beskrivs hur du skapar dessa e-postflödesregler i administrationscentret för Exchange (EAC) och i Exchange Management Shell (Exchange PowerShell) i den lokala Exchange-organisationen.

> [!TIP]
> I stället för att leverera meddelanden till den lokala användarens skräppostmapp kan du konfigurera principer för skräppostskydd i EOP för att sätta skräppostmeddelanden i karantän i EOP. Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste ha tilldelats behörigheter i den lokala Exchange-miljön innan du kan utföra de här procedurerna. Specifikt måste du tilldelas rollen **Transportregler,** som tilldelas rollerna **Organisationshantering,** **Efterlevnadshantering** och **Hantering** av arkivhandlingar som standard. Mer information finns i Lägga [till medlemmar i en rollgrupp.](/Exchange/permissions/role-group-members#add-members-to-a-role-group)

- Om och när ett meddelande levereras till mappen Skräppost i en lokal Exchange-organisation styrs av en kombination av följande inställningar:

  - Parametervärdet _SCLJunkThreshold_ för [cmdleten Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) i Exchange Management Shell. Standardvärdet är 4, vilket innebär att SCL (SCL) på 5 eller senare ska leverera meddelandet till användarens skräppostmapp.

  - Parametervärdet _SCLJunkThreshold_ för [cmdleten Set-Mailbox](/powershell/module/exchange/set-mailbox) i Exchange Management Shell. Standardvärdet är tomt ($null), vilket betyder att organisationsinställningen används.

  Mer information finns i [Tröskelvärden för skräppost i Exchange.](/Exchange/antispam-and-antimalware/antispam-protection/scl)

  - Om skräppostregeln är aktiverad för postlådan _(parametervärdet_ Aktiverad $true i cmdleten [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration) i Exchange Management Shell). Det är skräppostregeln som faktiskt flyttar meddelandet till mappen Skräppost efter leveransen. Som standard är skräppostregeln aktiverad för postlådor. Mer information finns i Konfigurera [inställningar för skydd motspam i Exchange för postlådor.](/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)

- Information om hur du öppnar EAC på en Exchange-server finns i [Administrationscenter för Exchange i Exchange Server.](/Exchange/architecture/client-access/exchange-admin-center) Information om hur du öppnar Exchange Management Shell finns [i Öppna Exchange Management Shell.](/powershell/exchange/open-the-exchange-management-shell)

- Mer information om e-postflödesregler i lokal Exchange finns i följande avsnitt:

  - [E-postflödesregler i Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Villkor och undantag för e-postflödesregel (predikat) i Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Åtgärder för e-postflödesregel i Exchange Server](/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Använda EAC för att skapa e-postflödesregler som anger SCL för EOP-skräppostmeddelanden

1. Gå till E-postflödesregler **i** \> EAC.

2. Klicka **på** ![ Lägg till lägg ](../../media/ITPro-EAC-AddIcon.png) **till-ikonen och välj Skapa en** ny regel i listrutan som visas.

3. På sidan **Ny regel** som öppnas konfigurerar du följande inställningar:

   - **Namn**: Ange ett unikt, beskrivande namn för regeln. Ett exempel:

     - EOP SFV:SPM till SCL 6

     - EOP SFV:SKS till SCL 6

     - EOP SFV:SKB till SCL 6

   - Klicka **på Fler alternativ.**

   - **Använd den här regeln om:** **Välj ett** \> **meddelandehuvud som innehåller något av dessa ord**.

     I rubriken **Ange text inkluderar du Ange ord** mening som visas gör du följande:

     - Klicka **på Ange text**. I dialogrutan **Ange rubrik som** visas anger du **X-Forefront-Antispam-Report** och klickar sedan på **OK.**

     - Klicka **på Ange ord.** I  dialogrutan Ange ord eller fraser som visas anger du något av rubrikerna för EOP  **(SFV:SPM,** **SFV:SKS** eller **SFV:SKB),** klickar på Lägg till lägg till ikon och klickar sedan på ![ ](../../media/ITPro-EAC-AddIcon.png) **OK.**

   - **Gör följande:** Välj **Ändra meddelandeegenskaperNa** \> **Ange SCL -nivån (Spam Confidence Level).**

     I dialogrutan **Ange SCL** väljer du **6** (standardvärdet är **5**).

   När du är klar klickar du på **Spara**

Upprepa de här stegen för de återstående värdena för skräppost i EOP **(SFV:SPM,** **SFV:SKS** **eller SFV:SKB**).

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Använda Exchange Management Shell för att skapa e-postflödesregler som anger SCL för EOP-skräppostmeddelanden

Använd följande syntax för att skapa de tre e-postflödesreglerna:

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

Detaljerad information om syntax och parametrar finns i [New-TransportRule](/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Kontrollera att du har konfigurerat fristående EOP så att skräppost levereras till mappen Skräppost i hybridmiljön genom att göra något av följande:

- I EAC går du till **E-postflödesregler** , markerar regeln och \> klickar sedan på **Redigera** redigeringsikon för att ![ kontrollera ](../../media/ITPro-EAC-EditIcon.png) inställningarna.

- Ersätt med namnet på e-postflödesregeln i Exchange Management Shell och skapa följande kommando för \<RuleName\> att verifiera inställningarna:

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- I ett externt e-postsystem som inte söker igenom utgående meddelanden efter skräppost skickar du ett allmänt test för meddelanden med oombedd massutskick (GTUBE) till en mottagare som påverkas och bekräftar att det levereras till deras skräppostmapp. Ett GTUBE-meddelande liknar EICAR-textfilen (European Institute for Computer Antivirus Research) för att testa inställningar för skadlig kod.

  När du vill skicka ett GTUBE-meddelande ska du ta med följande text i brödtexten i ett e-postmeddelande på en enda rad, utan blanksteg eller radbrytningar:

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```