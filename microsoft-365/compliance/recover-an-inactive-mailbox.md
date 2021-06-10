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
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
ms.custom: seo-marvel-apr2020
description: Lär dig hur du återställer innehållet i en inaktiv postlåda i Office 365 genom att konvertera den till en ny postlåda som innehåller innehållet i den inaktiva postlådan.
ms.openlocfilehash: e7f5ea9e3d47bf6b7ee6de495d2f5f47984cdf8f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162215"
---
# <a name="recover-an-inactive-mailbox"></a>Återställa en inaktiv postlåda

En inaktiv postlåda (en typ av mjuk borttagna postlådor) används för att bevara en tidigare anställds e-post när han eller hon lämnar organisationen. Om den anställde återgår till organisationen eller om en annan anställd tar över den tidigare anställdes arbetsuppgifter finns det två sätt att göra innehållet i den inaktiva postlådan tillgängligt för en användare:

- **Återställa en inaktiv postlåda.** Om den tidigare anställde återgår till organisationen, eller om en ny anställd anställs för att ta på sig arbetsansvaret för den tidigare anställde, kan du återställa innehållet i den inaktiva postlådan. Den här metoden konverterar den inaktiva postlådan till en ny, aktiv postlåda som innehåller innehållet i den inaktiva postlådan. När den har återställts finns den inaktiva postlådan inte längre. Procedurerna i det här avsnittet beskriver den här metoden.

- **Återställa en inaktiv postlåda.** Om en annan anställd tar på sig den tidigare anställdes arbetsuppgifter, eller om en annan användare behöver åtkomst till innehållet i den inaktiva postlådan, kan du återställa (eller sammanfoga) innehållet i den inaktiva postlådan till en befintlig postlåda. Du kan också återställa arkivet från en inaktiv postlåda. Procedurerna för den här metoden finns i [Återställa en inaktiv postlåda i Office 365](restore-an-inactive-mailbox.md).

I avsnittet [Mer information](#more-information) finns mer information om skillnaderna mellan att återställa och återställa en inaktiv postlåda, och en beskrivning av vad som händer när en inaktiv postlåda återställs.

> [!NOTE]
> Du kan inte återställa en inaktiv postlåda som konfigurerats med ett automatiskt expanderande arkiv. Om du behöver återställa data från en inaktiv postlåda med ett automatiskt expanderande arkiv kan du använda innehållssökning för att exportera data från postlådan och sedan importera till en annan postlåda. Instruktioner finns i följande avsnitt:
>
> - [Innehållssökning](content-search.md)
> - [Exportera sökresultat för innehåll](export-search-results.md)

## <a name="requirements-to-recover-an-inactive-mailbox"></a>Krav för att återställa en inaktiv postlåda

- Du måste använda Exchange Online PowerShell för att återställa en inaktiv postlåda. Du kan inte använda Exchange (EAC). Stegvisa anvisningar finns i [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Kör följande kommando för att hämta identitetsinformation för inaktiva postlådor i organisationen.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  Använd informationen som returneras av det här kommandot för att återställa en viss inaktiv postlåda.

## <a name="recover-inactive-mailboxes"></a>Återställa inaktiva postlådor

Använd **cmdlet:en Ny** postlåda med parametern  *InactiveMailbox till*  att återställa en inaktiv postlåda.

1. Skapa en variabel som innehåller egenskaperna för den inaktiva postlådan.

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > I det föregående kommandot använder du värdet för egenskapen **DistinguishedName eller** **ExchangeGUID** för att identifiera den inaktiva postlådan. De här egenskaperna är unika för varje postlåda i organisationen, men det är möjligt att en aktiv och en inaktiv postlåda kan ha samma primära SMTP-adress.

2. I det här exemplet används egenskaperna från det föregående kommandot och den inaktiva postlådan återställs till en aktiv postlåda för användaren Ann Beebe. Kontrollera att värdena som anges för  *parametrarna Name*  och  *MicrosoftOnlineServicesID*  är unika inom organisationen.

   ```powershell
   New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
   ```

   Den primära SMTP-adressen för den återställda inaktiva postlådan har samma värde som det som anges av *parametern MicrosoftOnlineServicesID.*

När du återställer en inaktiv postlåda skapas också ett nytt användarkonto. Du måste aktivera det här användarkontot genom att tilldela en licens. Information om hur du tilldelar Microsoft 365 administrationscentret finns i Lägga till [användare och tilldela licenser samtidigt.](../admin/add-users/add-users.md)

## <a name="more-information"></a>Mer information

- **Vad är den största skillnaden mellan att återställa och återställa en inaktiv postlåda?** När du återställer en inaktiv postlåda konverteras postlådan till en ny postlåda, innehållet och mappstrukturen för den inaktiva postlådan behålls och postlådan länkas till ett nytt användarkonto. När den har återställts finns den inaktiva postlådan inte längre och eventuella ändringar av innehållet i den nya postlådan påverkar innehållet som ursprungligen var på plats i den inaktiva postlådan. Och när du återställer en inaktiv postlåda kopieras innehållet bara till en annan postlåda. Den inaktiva postlådan bevaras och förblir en inaktiv postlåda. Ändringar som görs i innehållet i målpostlådan påverkar inte det ursprungliga innehållet som hålls i den inaktiva postlådan. Du kan fortfarande söka i den inaktiva postlådan med hjälp av In-Place eDiscovery, dess innehåll kan återställas till en annan postlåda eller återställas eller tas bort senare.

- **Vad händer när du återställer en inaktiv postlåda?** När du återställer en inaktiv postlåda sker följande:

  - Det håll som gällde för en inaktiv postlåda ändras eller tas bort beroende på vilken typ av kvart som tillämpats på den inaktiva postlådan innan den återskapades.

    - **Bevarande av juridiska skäl.** Om Bevarande av juridiska skäl har aktiverats för den inaktiva postlådan tas den bort från den återskapade postlådan.

    - **Håll på plats i In-Place** tas bort från den återskapade postlådan. Det innebär att den återskapade postlådan tas bort som en källpostlåda från ett In-Place eller en In-Place eDiscovery-sökning.

    - **Microsoft 365 med Bevarandelås.** Om den inaktiva postlådan tilldelades en bevarandeprincip med bevarandelås (en så kallad låst bevarandeprincip) tilldelas den återskapade postlådan samma låsta bevarandeprincip. Mer information om låsta bevarandeprinciper finns i [ Använda bevarandelås för att begränsa[ändringar av bevarandeprinciper och bevarandeprinciper.](retention-preservation-lock.md)

    - **Microsoft 365 bevarandeprincip utan bevarandelås.** Den inaktiva postlådan tas bort från alla olåsta e Microsoft 365 och bevarandeprinciper som tillämpats på den. Bevarande av juridiska skäl är aktiverat för den återställda postlådan för att förhindra borttagning av postlådeinnehåll baserat på bevarandeprinciper för hela organisationen som tar bort innehåll som är äldre än en viss ålder. Du kan behålla bevarande av juridiska skäl eller ta bort bevarande av juridiska skäl. Mer information finns i Skapa [bevarande av juridiska skäl.](create-a-litigation-hold.md)

  - Återställningsperioden för enstaka objekt (som definieras av egenskapen **RetainDeletedItemsFor** mailbox) är inställd på 30 dagar. När du skapar en ny postlåda i Exchange Online bevarandetiden vanligtvis 14 dagar. Om du sätter det här värdet till det högsta värdet på 30 dagar får du mer tid till att återställa data som tagits bort permanent från den inaktiva postlådan. Du kan också inaktivera återställning av enstaka objekt eller ställa in återställningsperioden för enstaka objekt tillbaka till standardvärdet 14 dagar. Mer information finns i Aktivera [eller inaktivera återställning av enstaka objekt för en postlåda.](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-single-item-recovery)

  - Bevarande av bevarande är aktiverat och varaktigheten för bevarande är inställd på 30 dagar. Det innebär att standardprincipen för Exchange-bevarande och alla organisationsomfattande eller Exchange-omfattande Microsoft 365-bevarandeprinciper som är tilldelade till den nya postlådan inte bearbetas på 30 dagar. Det ger den återkommande medarbetaren eller den nya ägaren av den återställda inaktiva postlådan tid att hantera de gamla meddelandena. Annars kan bevarandeprincipen i Exchange eller Microsoft 365 ta bort gamla postlådeobjekt (eller flytta objekt till arkivpostlådan om den är aktiverad) som har upphört att gälla baserat på de inställningar som konfigurerats för bevarandeprinciperna i Exchange eller Microsoft 365. Efter 30 dagar upphör bevarandet att gälla, egenskapen **RetentionHoldEnabled** för postlåda sätts till **False** och assistenten för hanterade mappar börjar bearbeta principerna som tilldelats postlådan. Om du inte behöver den här tiden kan du bara ta bort bevarandet. Du kan också öka varaktigheten för bevarandet med hjälp av kommandot **Set-Mailbox -EndDateForRetentionHold.** Mer information finns i Skapa [bevarande av en postlåda.](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold)

- **Sätt ett bevarande för den återskapade postlådan om du behöver behålla det ursprungliga tillståndet för den inaktiva postlådan.** Om du vill förhindra att den nya postlådans ägare eller bevarandeprincip permanent tar bort meddelanden från den återställda inaktiva postlådan kan du placera postlådan på Bevarande av juridiska skäl. Mer information finns i Skapa [bevarande av juridiska skäl.](./create-a-litigation-hold.md)

- **Vilket användar-ID kan du använda när du återställer en inaktiv postlåda?** När du återställer en inaktiv postlåda kan värdet som du anger för  *parametern MicrosoftOnlineServicesID*  vara ett annat än det ursprungliga värdet som var kopplat till den inaktiva postlådan. Du kan också använda det ursprungliga användar-ID:t. Men som tidigare beskrivits kontrollerar du att värdena som används för  *Name*  och  *MicrosoftOnlineServicesID*  är unika i din organisation när du återställer den inaktiva postlådan.

- **Vad händer om lagringstiden för den inaktiva postlådan inte har gått ut?** Om en inaktiv postlåda togs bort mjukt för mindre än 30 dagar sedan kan du inte återställa den med hjälp av kommandot Ny postlåda **-InactiveMailbox.** Du måste återställa det genom att återställa motsvarande användarkonto. Mer information finns i Ta [bort en användare från organisationen.](../admin/add-users/delete-a-user.md)

- **Hur vet du om den mjuk borttagna postlådans kvarhållningsperiod för en inaktiv postlåda har upphört att gälla?** Kör följande kommando.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | Format-List ExternalDirectoryObjectId
  ```

  Om det inte finns något värde för egenskapen **ExternalDirectoryObjectId** har kvarhållningsperioden för postlådan upphört att gälla och du kan återställa den inaktiva postlådan genom att köra kommandot **Ny postlåda -InactiveMailbox.** Om det finns ett värde för egenskapen **ExternalDirectoryObjectId** har bevarandeperioden för den borttagna postlådan inte upphört att gälla och du måste återställa postlådan genom att återställa användarkontot. Se [Ta bort en användare från organisationen.](../admin/add-users/delete-a-user.md)

- **Överväg att aktivera arkivpostlådan när du har återskapat en inaktiv postlåda.** Då kan den återkommande användaren eller den nya medarbetaren flytta gamla meddelanden till arkivpostlådan. När bevarandet upphör att gälla flyttar arkiveringsprincipen som är en del av standardprincipen för bevarande i Exchange som tilldelats Exchange Online-postlådor objekt som är två år eller äldre till arkivpostlådan. Om du inte aktiverar arkivpostlådan finns objekt som är äldre än två år kvar i användarens primära postlåda. Mer information finns i Aktivera [arkivpostlådor.](enable-archive-mailboxes.md)