---
title: Aktivera obegränsad arkivering – hjälp för administratörer
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: 'För administratörer: Lär dig hur du aktiverar automatiskt expanderande arkivering, vilket ger användarna obegränsad lagring för Exchange Online postlådor. Du kan aktivera automatisk expandering av arkivering för hela organisationen eller bara för vissa användare.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ac5661ac43ed9c0f35eba20007f0c4c4406ebf20
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162248"
---
# <a name="enable-unlimited-archiving---admin-help"></a>Aktivera obegränsad arkivering – hjälp för administratörer

Du kan använda den Exchange Online automatiskt expanderande arkiveringsfunktionen för att aktivera obegränsat lagringsutrymme för arkivpostlådor. När automatiskt expanderande arkivering är aktiverat läggs ytterligare lagringsutrymme automatiskt till i en användares arkivpostlåda när den närmar sig lagringsgränsen. Resultatet är en obegränsad lagringskapacitet för postlådor. Du kan aktivera automatisk expandering av arkivering för alla i organisationen eller bara för vissa användare. Mer information om automatiskt expanderande arkivering finns i [Översikt över obegränsat arkivering i Office 365](unlimited-archiving.md).

## <a name="before-you-enable-auto-expanding-archiving"></a>Innan du aktiverar automatisk expandering av arkivering

- Du måste vara global administratör i organisationen eller medlem i rollgruppen Organisationshantering i Exchange Online-organisationen för att kunna aktivera automatisk expandering av arkivering för hela organisationen eller för specifika användare. Alternativt måste du vara medlem i en rollgrupp som har tilldelats rollen E-postmottagare för att kunna aktivera automatisk arkivering för specifika användare.

- En användares arkivpostlåda måste aktiveras innan du kan aktivera automatisk expandering av arkivering. En användare måste ha tilldelats en licens Exchange Online abonnemang 2 för att aktivera arkivpostlådan. Om en användare har tilldelats en Exchange Online abonnemang 1-licens måste du tilldela dem en separat licens Exchange Online - arkivering aktivera arkivpostlådan. Se [Aktivera arkivpostlådor i Säkerhets- & Säkerhets- och efterlevnadscenter.](enable-archive-mailboxes.md)

- Du kan också använda PowerShell för att aktivera arkivpostlådor. I avsnittet [Mer information finns](#more-information) ett exempel på PowerShell-kommandot som du kan använda för att aktivera arkivpostlådor för alla användare i organisationen.

- Automatiskt expanderande arkivering som också har stöd för delade postlådor. För att aktivera arkivet för en delad postlåda krävs en Exchange Online abonnemang 2-licens eller en Exchange Online abonnemang 1-licens med Exchange Online - arkivering licens.

- Automatiskt expanderande arkivering hindrar dig från att återställa eller återställa en [inaktiv postlåda.](inactive-mailboxes-in-office-365.md#what-are-inactive-mailboxes) Det innebär att om du aktiverar automatisk expandering av arkivering för en postlåda och postlådan vid ett senare tillfälle görs inaktiv kan du inte återställa den [inaktiva](recover-an-inactive-mailbox.md) postlådan (genom att konvertera den till en aktiv postlåda) eller återställa den [(genom](restore-an-inactive-mailbox.md) att sammanfoga innehållet till en befintlig postlåda). Om automatiskt expanderande arkivering är aktiverat för en inaktiv postlåda kan du bara återställa data genom att använda verktyget Innehållssökning i efterlevnadscentret för Microsoft 365 för att exportera data från postlådan och importera till en annan postlåda. Mer information finns i avsnittet "Inaktiva postlådor och automatiskt expanderande arkiv" i [Översikt över inaktiva postlådor.](inactive-mailboxes-in-office-365.md#inactive-mailboxes-and-auto-expanding-archives)

- Du kan inte använda Exchange eller Säkerhetscenter för säkerhet och & för att aktivera automatiskt expanderande arkivering. Du måste använda Exchange Online PowerShell. Information om hur du ansluter Exchange Online organisationen med fjärr-PowerShell finns Anslut [i Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>Aktivera automatisk expandering av arkivering för hela organisationen

Du kan aktivera automatisk expandering av arkivering för hela organisationen. När du aktiverar det aktiveras automatiskt expanderande arkivering för befintliga användarpostlådor och för nya användarpostlådor som skapas. När du skapar användarpostlådor måste du aktivera användarens huvudarkivpostlåda så att den automatiskt expanderande arkiveringsfunktionen fungerar för den nya användarpostlådan.
  
1. [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)

2. Kör följande kommando i Exchange Online PowerShell för att aktivera automatisk expandering av arkivering för hela organisationen.

    ```powershell
    Set-OrganizationConfig -AutoExpandingArchive
    ```

## <a name="enable-auto-expanding-archiving-for-specific-users"></a>Aktivera automatiskt expanderande arkivering för specifika användare

I stället för att aktivera automatisk expandering av arkivering för varje användare i organisationen kan du bara aktivera den för specifika användare. Det kan vara bra att göra det eftersom bara vissa användare kanske har behov av en stor lagringskapacitet.
  
När du aktiverar automatisk expandering av arkivering för en viss användare och användarens postlåda i bevarande eller tilldelad till en bevarandeprincip görs följande två konfigurationsändringar:
  
- Lagringskvoten för användarens primära arkivpostlåda ökar med 10 GB (från 100 GB till 110 GB). Lagringsvarningskvoten ökar också med 10 GB (från 90 GB till 100 GB).

- Lagringskvoten för mappen Återställningsbara objekt i användarens primära postlåda ökar med 10 GB (också från 100 GB till 110 GB). Varningskvoten för återställningsbara objekt ökar också med 10 GB (från 90 GB till 100 GB). De här ändringarna är endast tillämpliga om postlådan är bevarande eller tilldelad till en bevarandeprincip.

Det extra utrymmet läggs till för att förhindra lagringsproblem som kan uppstå innan det automatiskt expanderande arkivet etableras. Ytterligare lagringsutrymme  *läggs inte till*  när du aktiverar automatisk expandering av arkivering för hela organisationen, enligt beskrivningen i föregående avsnitt.
  
1. [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)

2. Kör följande kommando i Exchange Online PowerShell för att aktivera automatiskt expanderande arkivering för en viss användare. Som tidigare förklarats måste användarens arkivpostlåda (huvudarkiv) vara aktiverad innan du kan aktivera automatisk expansion av arkivering för den användaren.

    ```powershell
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```

> [!IMPORTANT]
> I en Exchange-hybriddistribution kan du inte använda kommandot **Enable-Mailbox -AutoExpandingArchive** för att aktivera automatiskt expanderande arkivering för en viss användare vars primära postlåda är lokal och vars arkivpostlåda är molnbaserad. Om du vill aktivera automatiskt expanderande arkivering för molnbaserade arkivpostlådor i en Exchange-hybriddistribution måste du köra kommandot **Set-OrganizationConfig -AutoExpandingArchive** i Exchange Online PowerShell för att aktivera automatiskt expanderande arkivering för hela organisationen. Om både en användares primära postlådor och arkivpostlådor är molnbaserade kan du använda kommandot **Enable-Mailbox -AutoExpandingArchive** för att aktivera automatiskt expanderande arkivering för den specifika användaren.
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>Kontrollera att automatiskt expanderande arkivering är aktiverat

Kontrollera att automatiskt expanderande arkivering är aktiverat för organisationen genom att köra följande kommando i Exchange Online PowerShell.

```powershell
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

Värdet för  `True` anger att automatiskt expanderande arkivering har aktiverats för organisationen. 
  
Kontrollera att automatiskt expanderande arkivering är aktiverat för en viss användare genom att köra följande kommando i Exchange Online PowerShell.
  
```powershell
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```

Värdet för  `True` anger att automatiskt expanderande arkivering är aktiverat för användaren.
  
Du kan avgöra om automatiskt expanderande arkivering har aktiverats för inaktiva postlådor genom att köra följande kommando Exchange Online PowerShell.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL UserPrincipalName,AutoExpandingArchiveEnabled
```

Värdet anger  `True` att automatiskt expanderande arkivering är aktiverat för den inaktiva postlådan. Värdet för `False` anger att automatiskt expanderande arkivering inte har aktiverats.

Tänk på följande när du aktiverar automatisk arkivering:
  
- Om du kör **kommandot Set-OrganizationConfig -AutoExpandingArchive** för att aktivera automatisk expandering av arkivering för organisationen behöver du inte köra **Enable-Mailbox -AutoExpandingArchive** för enskilda postlådor. När du kör cmdleten **Set-OrganizationConfig** för att aktivera automatiskt expanderande arkivering för organisationen ändras inte egenskapen  *AutoExpandingArchiveEnabled*  för användarpostlådor till `True` .

- På samma sätt ändras inte värdena för postlådeegenskaperna  *ArchiveQuota*  och  *ArchiveWarningQuota*  när du aktiverar automatisk expandering av arkivering. När du aktiverar automatiskt expanderande arkivering för en användarpostlåda och egenskapen  *AutoExpandingArchiveEnabled*  sätts egenskaperna  `True`  *ArchiveQuota*  och  *ArchiveWarningQuota*  till. Här är ett exempel på de här postlådeegenskaperna när automatisk expandering av arkivering har aktiverats för en användares postlåda. 

    ![Egenskaperna ArchiveQuota och ArchiveWarningQuota ignoreras när du aktiverar automatiskt expanderande arkivering](../media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

## <a name="more-information"></a>Mer information

- Du kan också använda PowerShell för att aktivera arkivpostlådor. Du kan till exempel köra följande kommando i Exchange Online PowerShell för att aktivera arkivpostlådor för alla användare vars arkivpostlåda inte redan är aktiverad.

    ```powershell
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- När du aktiverar automatisk expandering av arkivering för organisationen eller för en viss användare konverteras en arkivpostlåda till ett automatiskt expanderande arkiv när arkivpostlådan (inklusive mappen Återställningsbara objekt) når 90 GB. Det kan ta upp till 30 dagar innan det extra lagringsutrymmet etableras.

- När du aktiverar automatisk expandering av arkivering kan det inte stängas av. Administratörer kan dessutom inte justera lagringskvoten för automatiskt expanderande arkivering.

- Automatiskt expanderande arkivering stöds för molnbaserade arkivpostlådor i en Exchange för användare som har en lokal primär postlåda. När automatisk expandering av arkivering har aktiverats för en molnbaserad arkivpostlåda kan du dock inte ta bort den arkivpostlådan från den lokala Exchange organisationen. Automatiskt expanderande arkivering stöds inte för lokala postlådor i någon version av Exchange Server.

- En lista över Outlook-klienter som användare kan använda för att komma åt objekt i det extra lagringsutrymmet i arkivpostlådan finns i avsnittet "Outlook-krav för åtkomst till objekt i ett automatiskt expanderat arkiv" i Översikt över obegränsat [arkivering](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).

- Som tidigare förklarats läggs 10 GB till lagringskvoten för användarens primära arkivpostlåda (och i mappen Återställningsbara objekt om postlådan är i förvaring) när du kör kommandot **Enable-Mailbox -AutoExpandingArchive.** Det ger ytterligare lagringsutrymme tills det automatiskt utökade lagringsutrymmet har etablerats (vilket kan ta upp till 30 dagar). Det extra lagringsutrymmet läggs inte till när du kör **Set-OrganizationConfig -AutoExpandingArchive** för att aktivera automatiskt expanderande arkivering för alla postlådor i organisationen. Om du har aktiverat automatisk expandering av arkivering för hela organisationen, men behöver lägga till ytterligare 10 GB lagringsutrymme för en viss användare, kan du köra kommandot **Enable-Mailbox -AutoExpandingArchive** för den postlådan. Du får ett felmeddelande om att automatiskt expanderande arkivering redan har aktiverats, men att det extra lagringsutrymmet läggs till i postlådan.

> [!IMPORTANT]
> Automatiskt expanderande arkivering stöds bara för postlådor som används för enskilda användare eller delade postlådor med en tillväxtfrekvens som inte överskrider 1 GB per dag. Journaler, transportregler och regler för automatisk vidarebefordran kan inte användas för att kopiera meddelanden till en arkivpostlåda för arkivering. En användares arkivpostlåda är endast avsedd för den användaren. Microsoft förbehåller sig rätten att neka obegränsad arkivering i fall där en användares arkivpostlåda används för att lagra arkivdata för andra användare eller i andra fall av olämplig användning.