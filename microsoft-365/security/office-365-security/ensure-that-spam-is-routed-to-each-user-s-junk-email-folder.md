---
title: Konfigurera EOP till skräppost i hybridmiljöer
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
description: Administratörer kan lära sig hur du dirigerar skräppost till mappar för skräppost från användare i hybridmiljö för Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a5b4d16c864b25c4d47910f0dd69f0ed3e71a0de
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209481"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a>Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer

> [!IMPORTANT]
> Det här avsnittet är endast för fristående EOP-kunder i hybridmiljöer. Det här avsnittet gäller inte Microsoft 365-kunder med Exchange Online-postlådor.

Om du är en fristående Exchange Online Protection (EOP) kund i en hybridmiljö, måste du konfigurera din lokala Exchange-organisation för att känna igen och översätta spam filtrering domar av EOP, så att skräppost regeln i den lokala postlådan kan flytta meddelanden till skräppostmappen.

Specifikt måste du skapa regler för e-postflöde (kallas även transportregler) i din lokala Exchange-organisation med villkor som hittar meddelanden med någon av följande EOP-rubriker och värden mot skräppost och åtgärder som anger att skräppostförtroendenivån (SCL) för dessa meddelanden ska vara 6:

- `X-Forefront-Antispam-Report: SFV:SPM`(meddelande markerat som skräppost genom skräppostfiltrering)

- `X-Forefront-Antispam-Report: SFV:SKS`(meddelande markerat som skräppost via regler för e-postflöde i EOP före skräppostfiltrering)

- `X-Forefront-Antispam-Report: SFV:SKB`(meddelande markerat som skräppost genom skräppostfiltrering på grund av att avsändarens e-postadress eller e-postdomän finns i listan över blockerade avsändare eller den blockerade domänlistan i EOP)

Mer information om dessa rubrikvärden finns i [Rubriker för skräppostmeddelanden](anti-spam-message-headers.md).

I det här avsnittet beskrivs hur du skapar dessa regler för e-postflöde (EAC) och Exchange Management Shell (Exchange PowerShell) i den lokala Exchange-organisationen.

> [!TIP]
> I stället för att leverera meddelandena till den lokala användarens skräppostmapp kan du konfigurera anti-spam-principer i EOP för att sätta skräppostmeddelanden i karantän i EOP. Mer information finns [i Konfigurera principer mot skräppost i EOP](configure-your-spam-filter-policies.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste tilldelas behörigheter i den lokala Exchange-miljön innan du kan göra dessa procedurer. Du måste ha tilldelats rollen **Transportregler,** som tilldelas rollerna **Organisationshantering,** **Efterlevnadshantering**och **Arkivhandling** som standard. Mer information finns i [Lägga till medlemmar i en rollgrupp](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).

- Om och när ett meddelande levereras till mappen Skräppost i en lokal Exchange-organisation styrs av en kombination av följande inställningar:

  - Parametervärdet _SCLJunkThreshold_ på [cmdlet Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) i Exchange Management Shell. Standardvärdet är 4, vilket innebär att en SCL på 5 eller högre bör leverera meddelandet till användarens skräppostmapp.

  - Parametervärdet _SCLJunkThreshold_ på cmdlet [set-postlådan](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) i Exchange Management Shell. Standardvärdet är tomt ($null), vilket innebär att organisationsinställningen används.

  Mer information finns i [SCL-tröskelvärden (Exchange spam Confidence Level).](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)

  - Om skräppostregeln är aktiverad på postlådan (parametervärdet _Aktiverad_ $true på cmdleten [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) i Exchange Management Shell). Det är skräppostregeln som faktiskt flyttar meddelandet till mappen Skräppost efter leverans. Som standard är skräppostregeln aktiverad på postlådor. Mer information finns i [Konfigurera inställningar för antispam för Exchange på postlådor](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).
  
- Om du vill öppna EAC på en Exchange Server finns [i Administrationscenter för Exchange i Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center). Om du vill öppna Exchange Management Shell finns i [https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) .

- Mer information om regler för e-postflöde i lokalt Exchange finns i följande avsnitt:

  - [Regler för e-postflöde i Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Villkor och undantag för e-postflödesregel (predikat) i Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Regelåtgärder för e-postflöde i Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Använd EAC för att skapa regler för e-postflöde som anger SCL för EOP-skräppostmeddelanden

1. Gå till Regler för **e-postflöde** i EAC \> **Rules**.

2. Klicka på **Lägg** ![ till-ikonen ](../../media/ITPro-EAC-AddIcon.png) och välj Skapa en ny **regel** i listrutan som visas.

3. Konfigurera följande inställningar på sidan **Ny regel** som öppnas:

   - **Namn**: Ange ett unikt, beskrivande namn för regeln. Till exempel:

     - EOP SFV:SPM till SCL 6

     - EOP SFV:SKS till SCL 6

     - EOP SFV:SKB till SCL 6

   - Klicka på **Fler alternativ**.

   - **Använd den här regeln om**: Välj ett **meddelandehuvud** \> **innehåller något av dessa ord**.

     I **textrubriken Retur finns Ange ord** mening som visas, gör följande steg:

     - Klicka på **Ange text**. I dialogrutan **Ange rubriknamn** som visas anger du **X-Forefront-Antispam-Report** och klickar sedan på **OK**.

     - Klicka på **Ange ord**. I dialogrutan **Ange ord eller fraser** som visas anger du ett av EOP:s värden för skräpposthuvudet **(SFV:SPM,** **SFV:SKS**eller **SFV:SKB**), klicka på **Ikonen Lägg till** lägg till och klicka sedan på ![ ](../../media/ITPro-EAC-AddIcon.png) **OK**.

   - **Gör så här:** Välj **Ändra meddelandeegenskaper** \> **Ange scl (Spam Confidence Level)**.

     I dialogrutan **Ange SCL** som visas väljer du **6** (standardvärdet är **5**).

   När du är klar klickar du på **Spara**

Upprepa dessa steg för de återstående EOP spam dom värden **(SFV: SPM,** **SFV:SKS**, eller **SFV:SKB**).

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a>Använd Exchange Management Shell för att skapa regler för e-postflöde som anger SCL för EOP-skräppostmeddelanden

Använd följande syntax för att skapa de tre reglerna för e-postflöde:

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

Till exempel:

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

Detaljerad information om syntax och parametrar finns i [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Så här kontrollerar du att du har konfigurerat fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljö:

- Gå till Regler för **e-postflöde** i EAC, \> **Rules**välj regeln och klicka sedan på Ikonen **Redigera** redigering för att ![ verifiera ](../../media/ITPro-EAC-EditIcon.png) inställningarna.

- I Exchange Management Shell ersätter du \< RuleName \> med namnet på e-postflödesregeln och rul följande kommando för att verifiera inställningarna:

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- I ett externt e-postsystem **som inte skannar utgående meddelanden efter skräppost**skickar du ett allmänt test för oönskat massmeddelande (GTUBE) till en berörd mottagare och bekräftar att det levereras till mappen Skräppost. Ett GTUBE-meddelande liknar EICAR-textfilen (European Institute for Computer Antivirus Research) för att testa inställningar för skadlig kod.

  Om du vill skicka ett GTUBE-meddelande tar du med följande text i brödtexten i ett e-postmeddelande på en enda rad, utan blanksteg eller radbrytningar:

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
