---
title: Använd regler för e-postflöde för att se vad dina användare rapporterar till Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur de använder regler för e-postflöde (kallas även transport regler) för att ta emot kopior av meddelanden som användare rapporterar till Microsoft.
ms.openlocfilehash: 0f3046c9d1962366ffd75353347b6cf7b72afd14
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659862"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Använd regler för e-postflöde för att se vad dina användare rapporterar till Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor finns det flera sätt för användare att rapportera meddelanden till Microsoft för analys enligt beskrivningen i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

Du kan skapa en regel för e-postflöde (kallas även för en transport regel) som letar efter meddelanden som användare rapporterar till Microsoft och du kan konfigurera mottagarnas mottagare för att få kopior av dessa rapporterade meddelanden.

Du kan skapa regeln för e-postflöden i administrations centret för Exchange (UK) och PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med post lådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste tilldelas behörigheter i Exchange Online eller Exchange Online Protection innan du kan göra det i den här artikeln. För det specifika måste du ha rollen **Transport regel** , som är tilldelad till **organisations hantering**, **hantering av efterlevnad** (globala administratörer) och roll grupperna **Arkiv handlings hantering** som standard.

  Mer information finns i följande avsnitt:

  - [Behörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [Behörigheter i fristående EOP](feature-permissions-in-eop.md)
  - [Använda UK ändra listan över medlemmar i roll grupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Om du vill öppna UK i Exchange Online läser du [administrations Center för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center). Information om hur du öppnar UK i fristående EOP finns i [administrations Center för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Mer information om regler för e-postflöden i Exchange Online och fristående EOP finns i följande avsnitt:
  - [Regler för e-postflöde (transport regler) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [Villkor och undantag för e-postflödes regel (predikat) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [Åtgärder för e-postflödes regler i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Använd UK för att skapa en regel för e-postflöde för att ta emot kopior av rapporterade meddelanden

1. Gå till regler för **e-postflöde** i UK \> .

2. Klicka på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) och välj sedan **skapa en ny regel**.

3. På sidan **ny regel** som öppnas konfigurerar du följande inställningar:

   - **Namn**: Ange ett unikt, beskrivande namn för regeln. Till exempel rapporteras hemliga kopior till Microsoft.

   - Klicka på **fler alternativ**.

   - **Använd den här regeln om**: Välj **mottagarens** \> **adress innehåller något av följande ord**: i dialog rutan **Ange ord eller fraser** som visas anger du ett av nedanstående värden, klickar på **Lägg** till ![ Lägg till ikonen ](../../media/ITPro-EAC-AddIcon.png) och upprepar tills du har angett alla värden.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     Om du vill redigera en post markerar du den och klickar på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) . För att ta bort en post markerar du den och klickar på **ta bort** ![ ikonen Ta bort ](../../media/ITPro-EAC-DeleteIcon.png) .

     När du är klar klickar du på **OK**.

   - **Gör följande**: Välj **Lägg till mottagare** \> **i rutan hemlig kopia**. Leta upp och markera de mottagare som du vill lägga till i dialog rutan som visas. När du är klar klickar du på **OK**.

4. Du kan göra ytterligare val för att granska regeln, testa regeln, aktivera regeln under en viss tids period och andra inställningar. Vi rekommenderar att du testar regeln innan du använder den.

5. Klicka på **Spara** när du är klar.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Använd PowerShell för att skapa en regel för e-postflöde för att ta emot kopior av rapporterade meddelanden

I det här exemplet skapas en ny e-postflödes regel med namnet hemlig kopia som rapporteras till Microsoft och som letar efter e-postmeddelanden som rapporteras till Microsoft med de metoder som beskrivs i den här artikeln och lägger till användarna laura@contoso.com och julia@contoso.com som mottagare av hemlig kopia.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Detaljerad information om syntax och parametrar finns i [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Gör något av följande om du vill kontrol lera att du har konfigurerat ett regel för e-postflöde för att få kopior av rapporterade meddelanden:

- Gå till regler för **e-postflöde** i UK och \>  \> Välj regeln \> Klicka på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) och kontrol lera inställningarna.

- I PowerShell kör du följande kommando för att kontrol lera inställningarna:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Skicka ett test meddelande till en av rapporterings-e-postadresser och bekräfta resultaten.
