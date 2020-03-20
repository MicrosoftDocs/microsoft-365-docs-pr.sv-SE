---
title: Minska spam-meddelanden i Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: 07824c51-2c45-4005-8596-03c0d7c4ff2a
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_IP
description: Lär dig de vanligaste sätten att minska spam- och skräppost-meddelanden i Office 365.
ms.openlocfilehash: 132c56d3faa0876cc6f7e7d42a433ae0a3a6a5d5
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42809356"
---
# <a name="how-to-reduce-spam-email-in-office-365"></a>Minska spam-meddelanden i Office 365

 **Får du för mycket spam-meddelanden i Office 365? Gör så här.**

Vi rekommenderar starkt att du rapporterar falskt negativa meddelanden genom [att använda tillägget Rapportera meddelanden](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) för att förbättra våra filter. Du kan också skicka meddelandet med hjälp av [Inlämningsutforskaren](admin-submission.md).

> [!TIP]
> Om du tror att meddelandet är skräppost och det finns i mappen skräppost ska du inte vara något problem. Om du inte vill att den ska visas alls i postlådan ska du ändra antispam-principen för att placera meddelandet i karantän. Mer information om att placera ett meddelande i karantän finns i [Placera e-postmeddelanden i karantän med Office 365](quarantine-email-messages.md).

## <a name="fixing-allowed-spam"></a>Åtgärda tillåten spam

Vanligtvis ser vi att kunder får skräppost i sin inkorg på grund av felaktiga konfigurationer. Den vanligaste är att konfigurera dina domäner i en regel för e-postflöde (kallas även för en transportregel) för att kringgå filter eller för att visa en lista över dina domäner i listan över tillåtna/säkra avsändare. Det är inte bra eftersom de här meddelandena hoppar över spam-filtrering och kunde ha fångats, så att skapa [betrodda avsändarlistor](create-safe-sender-lists-in-office-365.md) måste anses som en tillfällig lösning.

## <a name="solutions-to-other-common-causes-of-getting-too-much-spam"></a>Lösningar till andra vanliga orsaker till att få alltför mycket spam-meddelanden

För att skydda dig från att få för mycket spam-meddelanden kräver Exchange Online Protection (EOP) att administratörer slutför några uppgifter. Om du inte är administratör för din Office 365-klientorganisation och får för mycket spam-meddelanden kanske du vill arbeta tillsammans med din administratör på de här uppgifterna. Annars kan du gå vidare till avsnittet användare.

### <a name="for-admins"></a>För administratörer

- **Ange Office 365 för dina DNS-poster**: för att EOP ska tillhandahålla bästa skydd måste bytaren för e-post (MX) DNS-poster för alla domäner pekas på Office 365 och bara för Office 365. Se [Skapa DNS-poster för Office 365 när du hanterar dina DNS-poster](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).

- **Aktivera skräppostregeln för alla postlådor**. Som standard är alternativet för spam-filtrering inställt på **flytta meddelandet till mappen skräppost**. Om det här är den föredragna och aktuella principen för spam måste varje postlåda [också ha en regel för skräppost aktiverat](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). Om du vill kontrollera det kan du köra cmdleten **get-MailboxJunkEmailConfiguration** på en eller flera postlådor. Du kan till exempel kontrollera alla postlådor genom att köra följande kommando i [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):

  ```powershell
  Get-MailboxJunkEmailConfiguration -Identity * | Where {$_.Enabled -eq $false}
  ```

  När du tittar på resultatet ska egenskapens värde för **Aktiverat** vara `True`. Om den är `False` kan du köra följande kommando för att ändra det:

  ```powershell
  Set-MailboxJunkEmailConfiguration -Identity $values.UserPrincipalName -Enabled $true
  ```

- **Skapa regler för e-postflöde i lokal Exchange Server**: om du använder Exchange Online Protection, men dina postlådor finns i den lokala Exchange-servern, måste du skapa ett par regler för e-postflöde i den lokala Exchange-servern. Se [Anvisningarna för endast EOP](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj900470(v=exchg.150)).

- **Markera massutskick-meddelanden som spam**: Massutskick-meddelanden är e-postmeddelanden som användare kan ha registrerat sig för, men som fortfarande kan vara oönskade. I meddelandehuvudet hittar du egenskapen BCL (Bulk Confidence Level) i rubriken X-Microsoft-Antispam. Om värdet för BCL är mindre än tröskelvärdet som anges i spam-filtret vill du kanske justera tröskelvärdet så att den här typen av massutskicks-meddelanden markeras som spam-meddelanden i stället. Olika användare har olika toleranser och inställningar för [hur massutskick-meddelanden](https://docs.microsoft.com/office365/SecurityCompliance/bulk-complaint-level-values) hanteras. Du kan skapa olika principer och regler för olika användarinställningar.

- **Blockera omedelbart en avsändare**: i de fall där du vill blockera en avsändare direkt, kan du blockera med e-postadress, domän eller IP-adress. Mer information finns i [Skapa listor för blockerade avsändare i Office 365](create-block-sender-lists-in-office-365.md). En anmärkning i en lista tillåtna användare hos en slutanvändare kan åsidosätta ett blockering som anges av administratören.

- **Aktivera tillägget rapportera meddelande för användare**: Vi rekommenderar starkt att du [aktiverar tillägget rapportera meddelande för användare](enable-the-report-message-add-in.md).

- **Använd [Inlämningsutforskare](admin-submission.md)**: administratörer kan nu skicka e-postmeddelanden med hjälp av fil- eller nätverksmeddelande-ID, URL:er och filer för genomsökning av Microsoft i Office 365. Som administratör kan du också visa feedback som dina användare skickar och använda alla mönster för att ändra inställningar som kan orsaka problem.

- **Aktivera [DKIM](use-dkim-to-validate-outbound-email.md)**: om du vill signera alla utgående meddelanden för att öka säkerheten i din domän och klientorganisation.

  > [!TIP]
  > När du har aktiverat DKIM måste du aktivera [DMARC](use-dkim-to-validate-outbound-email.md) eftersom den här posten kommer att verifiera om DKIM och SPF fungerar som de ska. Vanligtvis har falska e-postmeddelanden inte signaturen eftersom O365 hanterar din privata och offentliga symmetriska nyckel.

### <a name="for-users"></a>För användare

- **Aktivera regeln för skräppost och kontrollera listan Tillåt**. Kontrollera av att åtgärdsregeln för skräppost är aktiverad och att avsändaren eller avsändarens domän inte ställts in på att kringgås i din personliga lista över tillåtna. Det bästa sättet att komma åt de här inställningarna är från [Blockera eller tillåt (inställningar för skräppost-meddelande)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46). Medan du är där kan du också välja att blockera avsändarens e-postadress eller domän.

- **Rapportera spam till Microsoft** anmäl spam-meddelanden till Microsoft genom att använda [använd tillägget Rapportera meddelanden](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).

- **Avbryta prenumerationen på massutskick-meddelande**. Om meddelandet är något som du har registrerat dig för (nyhetsbrev, produktmeddelanden osv.) och innehåller en länk för att avbryta prenumerationen från en tillförlitlig källa kan det vara bra att avbryta prenumerationen. Office 365 behandlar vanligtvis inte dessa meddelanden som spam. Du kan också välja att spärra avsändaren eller be administratören att göra en ändring som gör att alla massutskick-meddelanden behandlas som spam.
