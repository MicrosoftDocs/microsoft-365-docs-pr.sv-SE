---
title: Återställa en inaktiv postlåda
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: Lär dig att återställa (eller sammanfoga) innehållet i en inaktiv postlåda till en befintlig postlåda i Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bc9039d21f76affce7f58f1f83597dd9e5eb4ecf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161999"
---
# <a name="restore-an-inactive-mailbox"></a>Återställa en inaktiv postlåda

En inaktiv postlåda (en typ av mjuk borttagna postlådor) används för att behålla en tidigare anställds e-post när han eller hon lämnar organisationen. Om en annan anställd tar på sig jobbansvaret för den avsvlade medarbetaren eller om den anställde återgår till din organisation finns det två sätt som du kan göra innehållet i den inaktiva postlådan tillgängligt för en användare:

- **Återställa en inaktiv postlåda** Om en annan anställd tar på sig jobbansvaret för den avsade medarbetaren, eller om en annan användare behöver åtkomst till innehållet i den inaktiva postlådan, kan du återställa (eller sammanfoga) innehållet i den inaktiva postlådan till en befintlig postlåda. Du kan också återställa arkivet från en inaktiv postlåda. När den har återställts sparas den inaktiva postlådan, som behålls som en inaktiv postlåda. I det här avsnittet beskrivs hur du återställer en inaktiv postlåda.

- **Återställa en inaktiv postlåda** Om den avgående medarbetaren återgår till organisationen, eller om en ny anställd anställs för att ta på sig arbetsansvaret för den avs avlidna medarbetaren, kan du återställa innehållet i den inaktiva postlådan. Med den här metoden konverteras den inaktiva postlådan till en ny postlåda som innehåller innehållet från den inaktiva postlådan. När den har återställts finns den inaktiva postlådan inte längre. Stegvisa instruktioner finns i Återställa en [inaktiv postlåda i Office 365.](recover-an-inactive-mailbox.md)

Mer information [finns i](#more-information) avsnittet Mer information i den här artikeln om skillnaderna mellan att återställa och återställa en inaktiv postlåda.

> [!NOTE]
> Du kan inte återställa en inaktiv postlåda som konfigurerats med ett automatiskt expanderande arkiv. Om du behöver återställa data från en inaktiv postlåda med ett automatiskt expanderande arkiv kan du använda innehållssökning för att exportera data från postlådan och sedan importera till en annan postlåda. Instruktioner finns i följande avsnitt:
>
> - [Innehållssökning](content-search.md)
> - [Exportera sökresultat för innehåll](export-search-results.md)

## <a name="requirements-to-restore-an-inactive-mailbox"></a>Krav för att återställa en inaktiv postlåda

- Du måste använda Exchange Online PowerShell för att återställa en inaktiv postlåda. Du kan inte använda Exchange (EAC). Stegvisa instruktioner finns i Skapa [Anslut-Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

- Kör följande kommando i Exchange Online PowerShell för att få identitetsinformation för inaktiva postlådor i organisationen.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  Använd informationen som returneras av det här kommandot för att återställa en specifik inaktiv postlåda.

- Mer information om inaktiva postlådor finns i [Inaktiva postlådor i Office 365](inactive-mailboxes-in-office-365.md).

## <a name="restore-inactive-mailboxes"></a>Återställa inaktiva postlådor

Använd **cmdleten New-MailboxRestoreRequest** med parametrarna  _SourceMailbox_ och  _TargetMailbox_ till att återställa innehållet i en inaktiv postlåda till en befintlig postlåda. Mer information om hur du använder denna cmdlet finns [i New-MailboxRestoreRequest](/powershell/module/exchange/new-mailboxrestorerequest).

1. Skapa en variabel som innehåller egenskaperna för den inaktiva postlådan.

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > I det föregående kommandot använder du värdet för egenskapen **DistinguishedName eller** **ExchangeGUID** för att identifiera den inaktiva postlådan. De här egenskaperna är unika för varje postlåda i organisationen, men det är möjligt att en aktiv och en inaktiv postlåda kan ha samma primära SMTP-adress.

2. Återställa innehållet i den inaktiva postlådan till en befintlig postlåda. Innehållet i den inaktiva postlådan (källpostlådan) slås ihop till motsvarande mappar i den befintliga postlådan (målpostlådan).

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
   ```

   Alternativt kan du ange en mapp på översta nivån i målpostlådan där innehållet ska återställas från den inaktiva postlådan. Om den angivna målmappen eller målmappstrukturen inte redan finns i målpostlådan skapas den under återställningsprocessen.

   I det här exemplet kopieras postlådeobjekt och undermappar från en inaktiv postlåda till en mapp med namnet "Inaktiv postlåda" i målpostlådans mappstruktur på den översta nivån.

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```

## <a name="restore-the-archive-from-an-inactive-mailbox"></a>Återställa arkivet från en inaktiv postlåda

Om en inaktiv postlåda har en arkivpostlåda kan du återställa den till en befintlig postlådas arkivpostlåda. Om du vill återställa arkivet från en inaktiv postlåda måste du lägga till _växlarna SourceIsArchive_ och _TargetIsArchive_ till kommandot som används för att återställa en inaktiv postlåda.

1. Skapa en variabel som innehåller egenskaperna för den inaktiva postlådan.

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!NOTE]
   > I det föregående kommandot använder du värdet för egenskapen **DistinguishedName eller** **ExchangeGUID** för att identifiera den inaktiva postlådan. De här egenskaperna är unika för varje postlåda i organisationen, men det är möjligt att en aktiv och en inaktiv postlåda kan ha samma primära SMTP-adress.

2. Återställ innehållet i arkivet från den inaktiva postlådan (källarkiv) till arkivet i en befintlig postlåda (målarkiv). I det här exemplet kopieras innehållet från källarkivet till en mapp med namnet "Inaktivt postlådearkiv" i målpostlådans arkiv.

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
   ```

## <a name="more-information"></a>Mer information

- **Vad är den största skillnaden mellan att återställa och återställa en inaktiv postlåda?** När du återställer en inaktiv postlåda konverteras den i princip till en ny postlåda, innehållet och mappstrukturen för den inaktiva postlådan behålls och postlådan länkas till ett nytt användarkonto. När den har återställts finns den inaktiva postlådan inte längre och eventuella ändringar av innehållet i den nya postlådan påverkar innehållet som ursprungligen var på plats i den inaktiva postlådan. Och när du återställer en inaktiv postlåda kopieras innehållet bara till en annan postlåda. Den inaktiva postlådan bevaras och förblir en inaktiv postlåda. Ändringar som görs i innehållet i målpostlådan påverkar inte det ursprungliga innehållet som hålls i den inaktiva postlådan. Du kan fortfarande söka i den [](content-search.md)inaktiva postlådan med hjälp av verktyget Innehållssökning, innehållet kan återställas till en annan postlåda eller återställas eller tas bort senare.

- **Hur hittar jag inaktiva postlådor?** Om du vill visa en lista över inaktiva postlådor i organisationen och visa information som är användbar för att återställa en inaktiv postlåda kan du köra det här kommandot.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **Använd bevarande av juridiska skäl eller Microsoft 365 bevarandeprincip för att behålla inaktivt innehåll i postlådan.** Om du vill behålla statusen för en inaktiv postlåda när den har [](create-a-litigation-hold.md) återställts kan du placera målpostlådan i Bevarande av juridiska skäl eller tillämpa [en Microsoft 365 bevarandeprincip](retention.md) innan du återställer den inaktiva postlådan. Det här förhindrar permanent borttagning av objekt från den inaktiva postlådan när de återställts till målpostlådan.

- **Aktivera bevarande av målpostlådan innan du återställer en inaktiv postlåda.** Eftersom objekt i postlådan från en inaktiv postlåda kan vara gamla kan det vara bra att aktivera bevarande av målpostlådan innan du återställer en inaktiv postlåda. När du rymmer en postlåda bearbetas inte bevarandeprincipen som tilldelats postlådan förrän bevarandet tas bort eller tills bevarandetiden går ut. Det ger ägaren av målpostlådan tid att hantera gamla meddelanden från den inaktiva postlådan. Annars kan bevarandeprincipen ta bort gamla objekt (eller flytta objekt till arkivpostlådan, om den är aktiverad) som har upphört att gälla baserat på de bevarandeinställningar som konfigurerats för målpostlådan. Mer information finns i Skapa [ett bevarande av en postlåda i Exchange Online](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold).

- **Vad gör bytet AllowLegacyDNMismatch?** I de tidigare exemplen för att återställa en inaktiv postlåda används växeln **AllowLegacyDNMismatch** för att tillåta återställning av den inaktiva postlådan till en annan målpostlåda. I ett vanligt återställningsscenario är målet att återställa innehåll där käll- och målpostlådorna är samma postlåda. Som standard kontrollerar cmdleten **New-MailboxRequest** att värdet för egenskapen **LegacyExchangeDN** för käll- och målpostlådorna är detsamma. Det förhindrar att du av misstag återställer en källpostlåda till fel målpostlåda. Om du försöker återställa en inaktiv postlåda utan att använda **växeln AllowLegacyDNMismatch** kan det hända att kommandot misslyckas om käll- och målpostlådorna har olika värden för **egenskapen LegacyExchangeDN.**

- **Du kan använda andra parametrar med New-MailboxRestoreRequest för att implementera olika återställningsscenarier för inaktiva postlådor.** Du kan till exempel köra det här kommandot för att återställa arkivet från den inaktiva postlådan till målpostlådans primära postlåda.

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  Du kan också återställa den inaktiva primära postlådan till målpostlådans arkiv genom att köra det här kommandot.

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- **Vad gör parametern TargetRootFolder?** Som tidigare förklarats kan du använda parametern **TargetRootFolder** till att ange en mapp högst upp i mappstrukturen (kallas även roten) i målpostlådan där du kan återställa innehållet i den inaktiva postlådan. Om du inte använder den här parametern sammanfogas postlådeobjekt från den inaktiva postlådan till motsvarande standardmappar i målpostlådan och anpassade mappar skapas på ny plats i roten på målpostlådan. Följande illustrationer visar de här skillnaderna mellan att inte använda och använda **parametern TargetRootFolder.**

  **Mapphierarki i målpostlådan när parametern TargetRootFolder inte används**

  ![Skärmbild när parametern TargetRootFolder inte används](../media/76a759af-f483-4d1c-8cc7-243435b5562e.png)

  **Mapphierarki i målpostlådan när parametern TargetRootFolder används**

  ![Skärmbild när parametern TargetRootFolder används](../media/300da592-7323-48db-b8a4-07012259d113.png)