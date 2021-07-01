---
title: Placera en In-Place på en mjukt borttagna postlåda i Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du skapar ett In-Place för en mjukt borttagna postlåda så att den blir inaktiv och bevarar innehållet.
ms.openlocfilehash: d72a5407bfafabed30466447e404cdd4196678ae
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226101"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>Placera en In-Place på en mjukt borttagna postlåda i Exchange Online

Lär dig hur du skapar ett In-Place för en mjukt borttagna postlåda så att den blir inaktiv och bevarar innehållet. Sedan kan du använda Microsoft-verktyg för eDiscovery för att söka i den inaktiva postlådan.

> [!IMPORTANT]
> Medan vi fortsätter att investera på olika sätt för att bevara postlådeinnehållet tillkännager vi att In-Place Holds i administrationscentret för Exchange (EAC) kommer att gå ur. Från och med den 1 juli 2020 kan du inte skapa nya In-Place i Exchange Online. Men du kan fortfarande hantera e-In-Place i EAC eller med hjälp av **cmdleten Set-MailboxSearch** i Exchange Online PowerShell. Men med början den 1 oktober 2020 kan du inte hantera nya In-Place. Du tar bara bort dem i EAC eller med cmdleten **Remove-MailboxSearch.** Mer information om hur du tar In-Place [eDiscovery-verktyg finns i Slutet av äldre eDiscovery-verktyg.](legacy-ediscovery-retirement.md)

Du kanske har en situation där en person har lämnat organisationen och deras motsvarande användarkonto och postlåda har tagits bort. Därefter inser du att det finns information i postlådan som måste bevaras. Vad kan du göra? Om den borttagna postlådans bevarandeperiod inte har förfallit kan du placera en In-Place på den borttagna postlådan (en så kallad mjuk borttagna postlåda) och göra den till en inaktiv postlåda. En  *inaktiv postlåda*  används för att bevara en tidigare anställds e-post när han eller hon lämnar organisationen. Innehållet i en inaktiv postlåda bevaras under tiden den inaktiva In-Place som placerades på den mjukt borttagna postlådan när den gjordes inaktiv. När postlådan har gjorts inaktiv kan du söka i postlådan med hjälp av In-Place eDiscovery i Exchange Online, innehållssökning i säkerhets- & och efterlevnadscentret eller eDiscovery Center i SharePoint Online.

> [!NOTE]
> I Exchange Online är en mjuk borttagna postlåda en postlåda som har tagits bort men kan återställas inom en viss bevarandeperiod. Bevarandetiden för den mjukt borttagna postlådan i Exchange Online är 30 dagar. Det innebär att postlådan kan återställas (eller göras till en inaktiv postlåda) inom 30 dagar efter att den togs bort. Efter 30 dagar markeras en mjuk borttagen postlåda för permanent borttagning och kan inte återställas eller göras inaktiv.

## <a name="requirements-for-in-place-holds"></a>Krav för In-Place rymmer

- Du måste använda cmdleten **New-MailboxSearch** i Windows PowerShell placera en In-Place på en mjuk borttagna postlåda. Du kan inte använda administrationscentret Exchange (EAC) eller eDiscovery Center i SharePoint Online.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Kör följande kommando för att få identitetsinformation om mjukt borttagna postlådor i organisationen.

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- Mer information om inaktiva postlådor finns i [Översikt över inaktiva postlådor i Office 365](inactive-mailboxes-in-office-365.md).

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>Placera en In-Place på en mjuk borttagna postlåda för att göra den till en inaktiv postlåda

Använd **cmdleten New-MailboxSearch** till att göra en mjuk borttagna postlåda till en inaktiv postlåda. Mer information finns i [Ny postlådesökning](/powershell/module/exchange/new-mailboxsearch).

1. Skapa en variabel som innehåller egenskaperna för den mjukt borttagna postlådan.

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > I det föregående kommandot använder du värdet för egenskapen **DistinguishedName** eller **ExchangeGuid** för att identifiera den mjukt borttagna postlådan. De här egenskaperna är unika för varje postlåda i organisationen, men det är möjligt att en aktiv postlåda och en mjuk borttagna postlåda kan ha samma primära SMTP-adress.

2. Skapa en In-Place och placera den på den mjukt borttagna postlådan. I det här exemplet anges ingen varaktighet för håll. Det innebär att objekt kommer att hållas kvar ett obestämt tidsbestämt tidsenligt sätt eller tills det att det är ett väntande objekt tas bort från den inaktiva postlådan.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   Du kan också ange varaktigheten för att hålla på plats när du In-Place varaktigheten. Det här exemplet innehåller objekt i den inaktiva postlådan i ungefär 7 år.

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. Efter en liten stund kör du något av följande kommandon för att verifiera att den mjukt borttagna postlådan är en inaktiv postlåda.

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    Eller

   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>Mer information

När du gör en mjuk borttagna postlåda till en inaktiv postlåda kan du hantera postlådan på flera olika sätt. Mer information finns i:

- [Ändra kvarhållningstiden för en inaktiv postlåda](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Återställa en inaktiv postlåda](recover-an-inactive-mailbox.md)

- [Återställa en inaktiv postlåda](restore-an-inactive-mailbox.md)

- [Ta bort en inaktiv postlåda](delete-an-inactive-mailbox.md) (genom att ta bort brytningen)