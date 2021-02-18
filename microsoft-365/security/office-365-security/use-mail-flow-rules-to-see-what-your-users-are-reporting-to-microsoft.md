---
title: Använd regler för e-postflöde för att se vad dina användare rapporterar till Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig att använda e-postflödesregler (kallas även transportregler) för att ta emot kopior av meddelanden som användare rapporterar till Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 40e87fec3bfd8ed4402713ca7ec45499bb50c68e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287611"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Använd regler för e-postflöde för att se vad dina användare rapporterar till Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection (EOP) utan Exchange Online-postlådor finns det flera sätt för användare att rapportera meddelanden till Microsoft för analys enligt beskrivningen i Rapportera meddelanden och filer till [Microsoft.](report-junk-email-messages-to-microsoft.md)

Du kan skapa en e-postflödesregel (kallas även transportregel) som söker efter meddelanden som användare rapporterar till Microsoft, och du kan konfigurera mottagare av hemlig kopia att ta emot kopior av dessa rapporterade meddelanden.

Du kan skapa e-postflödesregeln i administrationscentret för Exchange (EAC) och PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste ha tilldelats behörigheter i Exchange Online eller Exchange Online Protection innan du kan utföra procedurerna i den här artikeln. Specifikt behöver du rollen **Transportregler,** som tilldelas rollgrupperna Organisationshantering, Efterlevnadshantering **(globala** administratörer) och Hantering av arkivhandlingar som standard.  

  Mer information finns i följande avsnitt:

  - [Behörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [Behörigheter i fristående EOP](feature-permissions-in-eop.md)
  - [Använd EAC för att ändra listan över medlemmar i rollgrupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Information om hur du öppnar EAC i Exchange Online finns [i administrationscentret för Exchange i Exchange Online.](https://docs.microsoft.com/Exchange/exchange-admin-center) Information om hur du öppnar EAC i fristående EOP finns i [administrationscentret för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Mer information om e-postflödesregler i Exchange Online och fristående EOP finns i följande avsnitt:
  - [E-postflödesregler (transportregler) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [Villkor för e-postflödesregel och undantag (predikat) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [Åtgärder för e-postflödesregel i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Använda EAC för att skapa en e-postflödesregel för att ta emot kopior av rapporterade meddelanden

1. Gå till E-postflödesregler **i** \> EAC.

2. Klicka **på ikonen** Lägg till lägg till och välj sedan Skapa en ny ![ ](../../media/ITPro-EAC-AddIcon.png) **regel.**

3. Konfigurera **följande inställningar** på sidan Ny regel som öppnas:

   - **Namn:** Ange ett unikt, beskrivande namn för regeln. Till exempel har Hemlig kopia av meddelanden rapporterats till Microsoft.

   - Klicka **på Fler alternativ.**

   - Använd den här  regeln **om:** Välj mottagarens adress innehåller något av följande ord: I dialogrutan Ange ord eller fraser som visas anger du något av följande värden, klickar på Lägg till ikon och upprepar \>  **tills** du har angett alla  ![ ](../../media/ITPro-EAC-AddIcon.png) värden.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     Om du vill redigera en post markerar du den och **klickar på ikonen** ![ ](../../media/ITPro-EAC-EditIcon.png) Redigera. Om du vill ta bort en post markerar du den och klickar **på ikonen Ta** ![ ](../../media/ITPro-EAC-DeleteIcon.png) bort.

     Klicka på OK när du är **klar.**

   - **Gör så här:** Välj **Lägg till** \> **mottagare i rutan Hemlig kopia.** I dialogrutan som visas går du till och väljer de mottagare som du vill lägga till. Klicka på OK när du är **klar.**

4. Du kan göra ytterligare val för att granska regeln, testa regeln, aktivera regeln under en viss tidsperiod och andra inställningar. Vi rekommenderar att du testar regeln innan du tillämpar den.

5. Klicka på **Spara** när du är klar.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Använda PowerShell för att skapa en e-postflödesregel för att ta emot kopior av rapporterade meddelanden

Det här exemplet skapar en ny e-postflödesregel med namnet Hemlig kopia av meddelanden som rapporterats till Microsoft och som söker efter e-postmeddelanden som rapporteras till Microsoft med de metoder som beskrivs i den här artikeln, och lägger till användarna laura@contoso.com och julia@contoso.com som mottagare av hemlig kopia.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Detaljerad information om syntax och parametrar finns i [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

För att verifiera att du har konfigurerat ett e-postflödesregler för att ta emot kopior av rapporterade meddelanden gör du något av följande:

- Gå till E-postflödesregler **i E-postflöde** genom att klicka på \>  \> ikonen Redigera \> och kontrollera  ![ ](../../media/ITPro-EAC-EditIcon.png) inställningarna.

- Kör följande kommando i PowerShell för att verifiera inställningarna:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Skicka ett testmeddelande till en av de rapporterande e-postadresserna och verifiera resultatet.
