---
title: Ta bort en inaktiv postlåda
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: När du inte längre behöver bevara innehållet i en inaktiv Microsoft 365 kan du ta bort den inaktiva postlådan permanent.
ms.openlocfilehash: 077a71bfdd82721e0992e5d14073aa037b7cfd1b
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162926"
---
# <a name="delete-an-inactive-mailbox"></a>Ta bort en inaktiv postlåda

En inaktiv postlåda används för att bevara en tidigare anställds e-post när de har lämnar organisationen. När du inte längre behöver bevara innehållet i en inaktiv postlåda kan du ta bort den inaktiva postlådan permanent genom att ta bort bevarandet. Det är också möjligt att flera inkorgar kan placeras i en inaktiv postlåda. En inaktiv postlåda kan till exempel spärras för bevarande av juridiska skäl och på ett eller flera In-Place inkorgar. Dessutom kan en bevarandeprincip (skapas i säkerhets- och efterlevnadscentret i Office 365 eller Microsoft 365) tillämpas på den inaktiva postlådan. Du måste ta bort alla bevarandeprinciper och bevarandeprinciper från en inaktiv postlåda för att ta bort den. När du har tagit bort principer för kvarhållning och kvarhållning markeras den inaktiva postlådan för borttagning och tas bort permanent när den har bearbetats.
  
> [!IMPORTANT]
> Medan vi fortsätter att investera på olika sätt för att bevara postlådeinnehållet presenterar vi att innehållet i In-Place Holds har Exchange i administrationscentret. Det innebär att du bör använda principer för kvarhållning av juridiska skäl och bevarandeprinciper för att skapa en inaktiv postlåda. Från och med den 1 juli 2020 kan du inte skapa nya In-Place i Exchange Online. Men du kan fortfarande ändra varaktigheten för ett aktivt In-Place som gjorts på en inaktiv postlåda. Men med början den 1 oktober 2020 kan du inte ändra varaktigheten för varaktigheten. Du kan bara ta bort en inaktiv postlåda genom att ta bort In-Place inaktiv. Befintliga inaktiva postlådor som finns på In-Place behålls fortfarande tills brytningen tas bort. Mer information om hur du tar In-Place [eDiscovery-verktyg finns i Slutet av äldre eDiscovery-verktyg.](legacy-ediscovery-retirement.md)
  
I avsnittet [Mer information finns](#more-information) en beskrivning av vad som händer när inkorgarna har tagits bort från en inaktiv postlåda.
  
## <a name="before-you-delete-an-inactive-mailbox"></a>Innan du tar bort en inaktiv postlåda

- Du måste använda PowerShell Exchange Online ta bort ett bevarande av juridiska skäl från en inaktiv postlåda. Du kan inte använda Exchange (EAC). Stegvisa anvisningar finns i [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Du kan kopiera innehållet i en inaktiv postlåda till en annan postlåda innan du tar bort den inaktiva postlådan och tar bort den. Mer information finns i [Återställa en inaktiv postlåda i Office 365](restore-an-inactive-mailbox.md).

- Om du tar bort bevarandeprincipen eller bevarandeprincipen från en inaktiv postlåda och bevarandeperioden för den mjukt borttagna postlådan för postlådan har upphört att gälla, tas postlådan bort permanent. När den har tagits bort går det inte att återställa den. Se till att du inte längre behöver innehållet i postlådan innan du tar bort det. Om du vill återaktivera en inaktiv postlåda kan du återställa den. Mer information finns i [Återställa en inaktiv postlåda i Office 365](recover-an-inactive-mailbox.md).

- Mer information om inaktiva postlådor finns i [Inaktiva postlådor i Office 365](inactive-mailboxes-in-office-365.md).

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Steg 1: Identifiera eventuella spärrade e-postlådor i inaktiva postlådor

Som tidigare nämnts kan bevarande av juridiska skäl, In-Place bevarandeprincip eller bevarandeprincip placeras i en inaktiv postlåda. Det första steget är att identifiera spärrade e-postlådor i inaktiva postlådor.
  
Kör följande kommando för att visa information om inaktiva postlådor i organisationen.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

Värdet för **True för** egenskapen **LitigationHoldEnabled** anger att den inaktiva postlådan finns på Bevarande av juridiska skäl. Om ett In-Place inaktiv postlåda placeras på en inaktiv postlåda visas GUID för holden som värde för egenskapen **InPlaceHolds.** Följande resultat för två inaktiva postlådor visar till exempel att bevarande av juridiska skäl sätts på Ann Beebe och att en policy för bevarande av In-Place och bevarande placeras på Pilar Pinilla.
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, mbxba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> Om många spärrade In-Place eller bevarandeprinciper placeras på en inaktiv postlåda visas inte alla In-Place-guid för håll visas. Du kan köra följande kommando för att visa alla GUID:er i egenskapen InPlaceHolds:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
Mer information om vilka som är spärrade finns i Identifiera typ av [spärrade objekt i en postlåda.](identify-a-hold-on-an-exchange-online-mailbox.md)

## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>Steg 2: Ta bort ett väntande från en inaktiv postlåda

När du har identifierat vilken typ av spärrade objekt som har placerats på den inaktiva postlådan (och om det finns flera spärrade objekt) är nästa steg att ta bort de spärrade objekten i postlådan. Som tidigare nämnts måste du ta bort alla som är spärrade för att permanent ta bort en inaktiv postlåda.
  
### <a name="remove-a-litigation-hold"></a>Ta bort bevarande av juridiska skäl

Som tidigare nämnts måste du använda Windows PowerShell ta bort bevarande av juridiska skäl från en inaktiv postlåda. Du kan inte använda EAC. Kör följande kommando för att ta bort bevarande av juridiska skäl.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> Det bästa sättet att identifiera en inaktiv postlåda är att använda det unika namnet eller det unika Exchange GUID-värdet. Om du använder något av dessa värden undviker du att ange fel postlåda av misstag. 
  
### <a name="remove-an-inactive-mailbox-from-a-retention-policy"></a>Ta bort en inaktiv postlåda från en bevarandeprincip

Proceduren för att ta bort en inaktiv postlåda från Microsoft 365 bevarandeprincip beror på om den inaktiva postlådans bevarandeprincip är organisationsomfattande eller explicit. på vilken typ av bevarandeprincip som tilldelas till den inaktiva postlådan.

- Organisationsomfattande bevarandeprinciper som tilldelats alla postlådor i organisationen. Använd **cmdlet Get-OrganizationConfig** i Exchange Online PowerShell för att få information om bevarandeprinciper för hela organisationen.

- Specifika bevarandeprinciper för plats som tilldelats specifika postlådor. Det här är principer som tilldelas till innehållsplatser för specifika användare. Använd **cmdleten Get-Mailbox -IncludeInactiveMailbox** i Exchange Online PowerShell för att få information om bevarandeprinciper som tilldelats till specifika inaktiva postlådor.

#### <a name="remove-an-inactive-mailbox-from-an-organization-wide-retention-policy"></a>Ta bort en inaktiv postlåda från en bevarandeprincip för hela organisationen

Kör följande kommando i Exchange Online PowerShell för att utesluta en inaktiv postlåda från en bevarandeprincip för hela organisationen.

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromOrgHolds <retention policy GUID without prefix or suffix>
```

Mer information om att identifiera organisationsomfattande bevarandeprinciper som tillämpas på en inaktiv postlåda och skaffa GUID för en bevarandeprincip finns i avsnittet Get-OrganizationConfig i Identifiera typ av bevarande som gjorts för en [postlåda.](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig)

Alternativt kan du köra följande kommando för att ta bort den inaktiva postlådan från alla organisationsomfattande principer:

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromAllOrgHolds
```

#### <a name="remove-an-inactive-mailbox-from-a-specific-location-retention-policy"></a>Ta bort en inaktiv postlåda från en viss bevarandeprincip för plats

Kör följande kommando i Säkerhets- [& Compliance Center PowerShell för](/powershell/exchange/connect-to-scc-powershell) att ta bort en inaktiv postlåda från en explicit bevarandeprincip.

```powershell
Set-RetentionCompliancePolicy -Identity <retention policy GUID without prefix or suffix> -AddExchangeLocationException <identity of inactive mailbox>
```

Mer information om att identifiera specifika platsbevarandeprinciper som tillämpas på en inaktiv postlåda och skaffa GUID för en bevarandeprincip finns i avsnittet "Get-Mailbox" i Så här identifierar du typen av bevarande som har placerats i en [postlåda.](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox)

### <a name="remove-in-place-holds"></a>Ta bort In-Place in innehåller

 Det finns två sätt att ta bort ett In-Place från en inaktiv postlåda: 
  
- **Ta bort In-Place Håll ned-objektet**. Om den inaktiva postlåda som du vill ta bort permanent är den enda källpostlådan för ett In-Place-objekt, kan du bara ta bort In-Place Håll objekt. 

    > [!NOTE]
    > Du måste inaktivera holden innan du kan ta bort ett objekt In-Place På. Om du försöker ta bort In-Place ett Håll-objekt som har aktiverats för att hålla får du ett felmeddelande. 
  
- **Ta bort den inaktiva postlådan som en källpostlåda i ett In-Place på**. Om du vill behålla andra källpostlådor för ett In-Place-objekt kan du ta bort den inaktiva postlådan från listan med källpostlådor och behålla In-Place-objekt.

#### <a name="delete-an-in-place-hold"></a>Ta bort ett In-Place håll

1. Skapa en variabel som innehåller egenskaperna för den In-Place som du vill ta bort. Använd det In-Place guiD för håll som du fick i steg [1:](#step-1-identify-the-holds-on-an-inactive-mailbox)Identifiera antalet i en inaktiv postlåda .

   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. Inaktivera alternativet för att hålla In-Place håll.

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. Ta bort In-Place håll.

   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="remove-an-inactive-mailbox-from-an-in-place-hold"></a>Ta bort en inaktiv postlåda från ett In-Place postlåda

Om In-Place innehåller ett stort antal källpostlådor är det möjligt att den inaktiva postlådan  inte visas på sidan Källor i EAC. Upp till 3 000 postlådor  visas på sidan Källor när du redigerar ett In-Place på plats. Om en inaktiv postlåda inte  finns med på sidan Källor kan du använda PowerShell Exchange Online ta bort den från sidan In-Place Postlådan. 
  
1. Skapa en variabel som innehåller egenskaperna för den In-Place som är placerat på den inaktiva postlådan. Använd det In-Place guiD för håll som du fick i steg [1:](#step-1-identify-the-holds-on-an-inactive-mailbox)Identifiera antalet i en inaktiv postlåda .

    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. Kontrollera att den inaktiva postlådan visas som en källpostlåda för In-Place postlådan. 

   ```powershell
   $InPlaceHold.Sources
   ```

   > [!NOTE]
   > Egenskapen *Sources* för egenskapen In-Place Identifierar källpostlådorna med deras *LegacyExchangeDN-egenskaper.* Eftersom den här egenskapen unikt identifierar inaktiva  postlådor förhindrar du att fel postlåda tas bort med egenskapen Sources från In-Place Hold. På så sätt undviker du också problem om två postlådor har samma alias eller SMTP-adress. 

3. Ta bort den inaktiva postlådan från listan över källpostlådor i variabeln. Se till att använda **LegacyExchangeDN** för den inaktiva postlåda som returnerades av kommandot i föregående steg. 

    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    Med följande kommando tas till exempel den inaktiva postlådan bort för Pilar Pinilla.

    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. Kontrollera att den inaktiva postlådan tas bort från listan över källpostlådor i variabeln.

   ```powershell
   $InPlaceHold.Sources
   ```

5. Ändra In-Place med den uppdaterade listan över källpostlådor, som inte innehåller den inaktiva postlådan.

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. Kontrollera att den inaktiva postlådan tas bort från listan över källpostlådor för In-Place postlådan.

   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a>Mer information

- **En inaktiv postlåda är en typ av mjuk borttagna postlåda.** I Exchange Online är en mjuk borttagna postlåda en postlåda som har tagits bort men kan återställas inom en viss bevarandeperiod. En tidigare inaktiv postlåda blir tillgänglig som en mjuk borttagna postlåda om Exchange Online i 183 dagar. Det innebär att postlådan kan återställas inom 183 dagar efter att den tagits bort mjukt. Efter 183 dagar markeras en mjuk borttagen postlåda för permanent borttagning och kan inte återställas.

- **Vad händer när du har tagit bort borttagningen av en inaktiv postlåda?** Postlådan behandlas som andra mjuk borttagna postlådor och markeras för permanent borttagning efter att den mjuka bevarandeperioden på 183 dagar har löpt ut. Bevarandetiden startar det datum då postlådan först blev inaktiv. Det här datumet kallas för mjuk borttagningsdatum, det datum då motsvarande användarkonto togs bort eller när Exchange Online-postlådan togs bort med cmdleten **Remove-Mailbox.** Det mjukt borttagna datumet är inte det datum då du tog bort det.

- **Tas en inaktiv postlåda bort permanent direkt efter att brytningen har tagits bort?** En tidigare inaktiv postlåda blir tillgänglig med mjuk borttagning i 183 dagar. Efter 183 dagar markeras postlådan för permanent borttagning.

- **Hur visar du information om en inaktiv postlåda när du har tagit bort det?** När ett håll har tagits bort och den inaktiva postlådan återställs till en mjuk borttagen postlåda returneras den inte med hjälp av parametern *InactiveMailboxOnly* med cmdlet:en **Get-Mailbox.** Men du kan visa information om postlådan med hjälp av **kommandot Get-Mailbox -SoftDeletedMailbox.** Till exempel:

  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox,WasInactiveMailbox,InactiveMailboxRetireTime
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 6/16/2020 1:19:04 AM
  IsInactiveMailbox      : False
  WasInactiveMailbox     : True
  InactiveMailboxRetireTime : 9/30/2020 11:16:23 PM
  ```

  I exemplet ovan identifierar egenskapen *WhenSoftDeleted* det mjukt borttagna datumet, som i det här exemplet är 16 juni 2020. Egenskapen *WasInactiveMailbox* visas som eftersom `True` den tidigare var en inaktiv postlåda. Postlådan tas bort permanent 183 dagar efter den 30 september 2020.

