---
title: Hantera postlådegranskning
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
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
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
ms.custom: seo-marvel-apr2020
description: Granskningsloggning för postlådor är aktiverat som standard i Microsoft 365 (kallas även standardgranskning av postlådor eller postlådegranskning på som standard). Det innebär att vissa åtgärder som utförs av postlådeägare, ombud och administratörer loggas automatiskt i en granskningslogg för postlådor, där du kan söka efter aktiviteter som utförs för postlådan.
ms.openlocfilehash: c77e96adfee40027beb653c9e725141fc8d7a8fe
ms.sourcegitcommit: 2cf7293d610a676726ac891b89366e23810d9142
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52866649"
---
# <a name="manage-mailbox-auditing"></a>Hantera postlådegranskning

Från och med januari 2019 startar Microsoft granskningsloggning för postlådor som standard för alla organisationer. Det innebär att vissa åtgärder som utförs av postlådeägare, ombud och administratörer loggas automatiskt, och motsvarande granskningsposter för postlådor blir tillgängliga när du söker efter dem i granskningsloggen för postlådan. Innan postlådegranskning var aktiverat som standard var du tvungen att manuellt aktivera den för alla användarpostlådor i organisationen.

Här är några fördelar med postlådegranskning som standard:

- Granskning aktiveras automatiskt när du skapar en ny postlåda. Du behöver inte aktivera det manuellt för nya användare.
- Du behöver inte hantera postlådeåtgärder som granskas. En fördefinierad uppsättning postlådeåtgärder granskas som standard för varje inloggningstyp (administratör, ombud och ägare).
- När Microsoft släpper en ny postlådeåtgärd kan åtgärden läggas till automatiskt i listan över postlådeåtgärder som granskas som standard (beroende på om användaren har rätt licens). Det innebär att du inte behöver övervaka lägga till nya åtgärder för postlådor.
- Du har en konsekvent princip för postlådegranskning i hela organisationen (eftersom du granskar samma åtgärder för alla postlådor).

> [!NOTE]
>
> - Det viktiga att komma ihåg när granskning av postlådor släpps som standard är att du inte behöver göra något för att hantera postlådegranskning. Men om du vill veta mer, anpassa granskning av postlådor från standardinställningarna eller inaktivera den helt och hållet kan den här artikeln hjälpa dig.
> - Som standard är endast granskningshändelser för postlådor för E5-användare tillgängliga i granskningsloggsökningar i Säkerhets- och &-efterlevnadscentret eller via API:t för hanteringsaktivitet Office 365 posthantering. Mer information finns i avsnittet [Mer information](#more-information) i den här artikeln.

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>Kontrollera att postlådegranskning är aktiverat som standard

Om du vill verifiera att postlådegranskning är aktiverat som standard för organisationen kör du följande kommando i [Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

Värdet False **anger** att postlådegranskning är aktiverat som standard för organisationen. Inställningen för postlådegranskning åsidosätter som standard inställningen för postlådegranskning för specifika postlådor. Om till exempel postlådegranskning är inaktiverat för en postlåda (egenskapen *AuditEnabled* är **False** för postlådan) granskas fortfarande standardåtgärder för postlådan, eftersom postlådegranskning som standard är aktiverad för organisationen.

Om du vill att postlådegranskning ska vara inaktiverad för specifika postlådor kan du konfigurera omkoppling av postlådegranskning för postlådans ägare och andra användare som har delegerats åtkomst till postlådan. Mer information finns i avsnittet [Åsidosätta granskningsloggning för](#bypass-mailbox-audit-logging) postlådor i den här artikeln.

> [!NOTE]
> När postlådegranskning är aktiverat som standard för organisationen ändras inte egenskapen *AuditEnabled* för berörda postlådor från **Falskt** till **Sant.** Med andra ord ignorerar postlådegranskning som standard egenskapen *AuditEnabled* för postlådor.

## <a name="supported-mailbox-types"></a>Postlådetyper som stöds

I följande tabell visas de postlådetyper som för närvarande stöds av postlådegranskning som standard:

<br>

****

|Postlådetyp|Stöds|
|---|:---:|
|Användarpostlådor|![Bockmarkering](../media/checkmark.png)|
|Delade postlådor|![Bockmarkering](../media/checkmark.png)|
|Microsoft 365 Grupppostlådor|![Bockmarkering](../media/checkmark.png)|
|Resurspostlådor||
|Postlådor i gemensamma mappar||
|

## <a name="logon-types-and-mailbox-actions"></a>Inloggningstyper och postlådeåtgärder

Inloggningstyper klassificerar användaren som gjorde de granskade åtgärderna för postlådan. I följande lista beskrivs de inloggningstyper som används i granskningsloggning för postlådor:

- **Ägare:** Postlådans ägare (det konto som är kopplat till postlådan).
- **Ombud:**
  - En användare som har tilldelats behörigheterna SendAs, SendOnBehalf eller FullAccess till en annan postlåda.
  - En administratör som har tilldelats behörigheten FullAccess till en användares postlåda.
- **Administratör:**
  - Postlådan genomsöks med något av följande Microsoft eDiscovery-verktyg:
    - Innehållssökning i efterlevnadscentret.
    - eDiscovery eller Advanced eDiscovery i efterlevnadscentret.
    - In-Place eDiscovery i Exchange Online.
  - Postlådan nås med hjälp Microsoft Exchange Server MAPI-redigeraren.

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>Postlådeåtgärder för användarpostlådor och delade postlådor

I följande tabell beskrivs de postlådeåtgärder som är tillgängliga i granskningsloggningen för postlådor för användares postlådor och delade postlådor.

- En bockmarkering ( ![Bockmarkering](../media/checkmark.png)) anger att postlådeåtgärden kan loggas för inloggningstypen (alla åtgärder är inte tillgängliga för alla inloggningstyper).
- En asterisk ( <sup>\*</sup> ) efter bockmarkeringen anger att postlådeåtgärden loggas som standard för inloggningstypen.
- Kom ihåg att en administratör med fullständig behörighet till en postlåda betraktas som ombud.

<br>

****

|Postlådeåtgärd|Beskrivning|Administratör|Delegera|Ägare|
|---|---|:---:|:---:|:---:|
|**AddFolderPermissions**|Även om det här värdet accepteras som en postlådeåtgärd ingår det redan i åtgärden **UpdateFolderPermissions** och granskas inte separat. Använd med andra ord inte det här värdet.||||
|**ApplyRecord**|Ett objekt märks som en post.|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|
|**Copy**|Ett meddelande kopierades till en annan mapp.|![Bockmarkering](../media/checkmark.png)|||
|**Create**|Ett objekt har skapats i mappen Kalender, Kontakter, Anteckningar eller Uppgifter i postlådan (till exempel skapas en ny mötesförfrågan). Åtgärden att skapa, skicka eller ta emot ett meddelande granskas inte. Åtgärden att skapa en e-postmapp granskas inte heller.|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)|
|**FolderBind**|En postlådemapp kunde nås. Den här åtgärden loggas också när administratören eller ombudet öppnar postlådan. <br/><br/> **Obs!** Granskningsposter för åtgärder som utförts av ombud konsolideras. En granskningspost genereras för åtkomst till enskilda mappar inom en 24-timmarsperiod.|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|**HardDelete**|Ett meddelande togs bort från mappen återställningsbara objekt.|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|
|**MailboxLogin**|Användaren loggade in i postlådan.|||![Bockmarkering](../media/checkmark.png)|
|**MailItemsAccessed**|**Obs!** Det här värdet är endast tillgängligt för användare av tilläggsprenumerationen E5 eller E5 för efterlevnad. Mer information finns i [Konfigurera avancerad granskning i Microsoft 365](set-up-advanced-audit.md). <p> E-postdata används av e-postprotokoll och -klienter.|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|
|**MessageBind**|**Obs!** Det här värdet är endast tillgängligt för E3-användare (användare utan tilläggsprenumerationer för E5 eller E5 för efterlevnad). <p> Ett meddelande visades i förhandsgranskningsfönstret eller öppnades av en administratör.|![Bockmarkering](../media/checkmark.png)|||
|**ModifyFolderPermissions**|Även om det här värdet accepteras som en postlådeåtgärd ingår det redan i åtgärden **UpdateFolderPermissions** och granskas inte separat. Använd med andra ord inte det här värdet.|||||
|**Move**|Ett meddelande flyttades till en annan mapp.|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|
|**MoveToDeletedItems**|Ett meddelande togs bort och flyttades till mappen Borttaget.|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|
|**RecordDelete**|Ett objekt som märks som en post togs bort mjukt (flyttades till mappen Återställningsbara objekt). Objekt som har etiketter som poster kan inte tas bort permanent (rensas från mappen för permanent borttagna objekt).|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|
|**RemoveFolderPermissions**|Även om det här värdet accepteras som en postlådeåtgärd ingår det redan i åtgärden **UpdateFolderPermissions** och granskas inte separat. Använd med andra ord inte det här värdet.||||
|**SearchQueryInitiated**|**Obs!** Det här värdet är endast tillgängligt för användare av tilläggsprenumerationen E5 eller E5 för efterlevnad. Mer information finns i [Konfigurera avancerad granskning i Microsoft 365](set-up-advanced-audit.md). <p> En person använder Outlook (Windows, Mac, iOS, Android eller Outlook på webben) eller appen E-post för Windows 10 för att söka efter objekt i en postlåda.|||![Bockmarkering](../media/checkmark.png)|
|**Send**|**Obs!** Det här värdet är endast tillgängligt för användare av tilläggsprenumerationen E5 eller E5 för efterlevnad. Mer information finns i [Konfigurera avancerad granskning i Microsoft 365](set-up-advanced-audit.md). <p> Användaren skickar ett e-postmeddelande, svarar på ett e-postmeddelande eller vidarebefordrar ett e-postmeddelande.|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>||![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|Ett meddelande skickades med behörigheten Skicka som. Det innebär att en annan användare skickade meddelandet som om det kom från postlådans ägare.|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|Ett meddelande skickades med behörigheten Skicka för. Det innebär att en annan användare skickade meddelandet åt postlådans ägare. Vem meddelandet skickades för och vem som faktiskt skickade meddelandet visas för mottagaren i meddelandet.|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|Ett meddelande togs bort permanent eller togs bort från mappen Borttaget. Mjuka borttagna objekt flyttas till mappen för permanent borttagna objekt.|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|
|**Uppdatera**|Ett meddelande eller dess egenskaper har ändrats.|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|En kalenderdelegering har tilldelats till en postlåda. Kalenderdelegering ger någon annan i samma organisation behörighet att hantera postlådeägarens kalender.|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>||![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|
|**UpdateComplianceTag**|En annan bevarandeetikett används på ett e-postobjekt (ett objekt kan bara ha en tilldelad bevarandeetikett).|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|
|**UpdateFolderPermissions**|En mappbehörighet har ändrats. Mappbehörigheten avgör vilka användare i organisationen som kan komma åt mappar i en postlåda och meddelanden som finns i dessa mappar.|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|
|**UpdateInboxRules**|En inkorgsregel har lagts till, tagits bort eller ändrats. Inkorgsregler används för att bearbeta meddelanden i användarens inkorg baserat på angivna villkor och vidta åtgärder när villkoren i en regel uppfylls, till exempel flytta ett meddelande till en angiven mapp eller ta bort ett meddelande.|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|
|

> [!IMPORTANT]
> Om du har anpassat postlådeåtgärderna  som ska granskas för alla inloggningstyper innan postlådegranskning aktiverats som standard i organisationen bevaras de anpassade inställningarna för postlådan och skrivs inte över av standardåtgärderna för postlådor enligt beskrivningen i det här avsnittet. Om du vill återställa åtgärderna i granskningspostlådan till sina [](#restore-the-default-mailbox-actions) standardvärden (som du kan göra när som helst) läser du avsnittet Återställa standardpostlådeåtgärderna längre fram i den här artikeln.

### <a name="mailbox-actions-for-microsoft-365-group-mailboxes"></a>Postlådeåtgärder för Microsoft 365 postlådor i gruppen

Postlådegranskning är på som standard innebär granskningsloggning för postlådor i Microsoft 365-grupppostlådor, men du kan inte anpassa det som loggas (du kan inte lägga till eller ta bort postlådeåtgärder som loggas för någon inloggningstyp).

I följande tabell beskrivs de postlådeåtgärder som loggas som standard på e Microsoft 365 postlådor för varje inloggningstyp.

Kom ihåg att en administratör med behörigheten Fullständig åtkomst till Microsoft 365 grupppostlådan betraktas som ombud.

<br>

****

|Postlådeåtgärd|Beskrivning|Administratör|Delegera|Ägare|
|---|---|:---:|:---:|:---:|
|**Create**|Skapa ett kalenderobjekt. Åtgärden att skapa, skicka eller ta emot ett meddelande granskas inte.|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>||
|**HardDelete**|Ett meddelande togs bort från mappen återställningsbara objekt.|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|
|**MoveToDeletedItems**|Ett meddelande togs bort och flyttades till mappen Borttaget.|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|Ett meddelande skickades med behörigheten Skicka som.|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|Ett meddelande skickades med behörigheten Skicka för.|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|Ett meddelande togs bort permanent eller togs bort från mappen Borttaget. Mjuka borttagna objekt flyttas till mappen för permanent borttagna objekt.|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|
|**Uppdatera**|Ett meddelande eller dess egenskaper har ändrats.|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|![Bockmarkering](../media/checkmark.png)<sup>\*</sup>|
|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>Kontrollera att postlådeåtgärder loggas för varje inloggningstyp

Postlådegranskning på som standard lägger till en ny *DefaultAuditSet-egenskap* för alla postlådor. Värdet för den här egenskapen anger om standardpostlådeåtgärderna (hanteras av Microsoft) granskas för postlådan.

Om du vill visa värdet för användarpostlådor eller delade postlådor ersätter du med namn, alias, e-postadress eller huvudnamn (användarnamn) för postlådan och kör följande kommando i \<MailboxIdentity\> Exchange Online PowerShell:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

Om du vill visa värdet Microsoft 365 postlådor i gruppen ersätter du med namn, alias eller e-postadress för den delade postlådan och kör följande kommando \<MailboxIdentity\> i Exchange Online PowerShell:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

Värdet `Admin, Delegate, Owner` anger:

- Postlådeåtgärderna för alla tre inloggningstyperna granskas. Det här är det enda värdet som visas på Microsoft 365 postlådor i gruppen.
- En administratör *har inte ändrat* de granskade postlådeåtgärderna för någon inloggningstyp för en användarpostlåda eller en delad postlåda. Observera att det här är standardtillståndet när postlådegranskning är aktiverat som standard i organisationen.

Om en administratör någon gång har ändrat postlådeåtgärder som granskas för en inloggningstyp (med hjälp av parametrarna *AuditAdmin,* *AuditDelegate* och *AuditOwner* i cmdleten **Set-Mailbox)** kommer egenskapsvärdet att vara annorlunda.

Värdet för egenskapen `Owner` *DefaultAuditSet för en* användarpostlåda eller en delad postlåda anger till exempel:

- Postlådeåtgärderna för postlådans ägare granskas.
- De granskade postlådeåtgärderna `Delegate` för `Admin` och inloggningstyperna har ändrats från standardåtgärderna.

Ett tomt värde för egenskapen *DefaultAuditSet* anger att postlådeåtgärder för alla tre inloggningstyperna har ändrats för användarpostlådan eller en delad postlåda.

Mer information finns i avsnittet Ändra [eller återställa postlådeåtgärder som loggats som standard](#change-or-restore-mailbox-actions-logged-by-default) i den här artikeln

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>Visa postlådeåtgärder som loggas på postlådor

Om du vill visa de postlådeåtgärder som för närvarande är inloggade på användarpostlådor eller delade postlådor ersätter du med namnet, alias, e-postadressen eller användarens huvudnamn (användarnamn) för postlådan och kör ett eller flera av följande kommandon \<MailboxIdentity\> i Exchange Online PowerShell.

> [!NOTE]
> Även om du kan lägga till bytet till följande `-GroupMailbox` **Get-Mailbox-kommandon** för Microsoft 365 grupppostlådor, tro inte de värden som returneras. De standardåtgärder och statiska postlådeåtgärder som granskas för Microsoft 365-grupppostlådor beskrivs i avsnittet Postlådeåtgärder för [e Microsoft 365 postlådor](#mailbox-actions-for-microsoft-365-group-mailboxes) tidigare i den här artikeln.

#### <a name="owner-actions"></a>Ägaråtgärder

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a>Delegera åtgärder

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a>Administrationsåtgärder

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>Ändra eller återställa postlådeåtgärder som loggats som standard

Som tidigare förklarats är en av de viktigaste fördelarna med att postlådegranskning är som standard: du behöver inte hantera postlådeåtgärder som granskas. Microsoft gör detta åt dig och vi lägger automatiskt till åtgärder i nya postlådor som ska granskas som standard när de släpps.

Organisationen kan dock behöva granska en annan uppsättning postlådeåtgärder för användarpostlådor och delade postlådor. Procedurerna i det här avsnittet visar hur du ändrar postlådeåtgärder som granskas för varje inloggningstyp och hur du återgår till de standardåtgärder som hanteras av Microsoft.

> [!IMPORTANT]
> Om du använder följande procedurer för att anpassa postlådeåtgärder som loggas på användarpostlådor eller delade postlådor, granskas inte nya standardpostlådeåtgärder som släppts av Microsoft automatiskt för dessa postlådor. Du måste manuellt lägga till eventuella nya postlådeåtgärder i den anpassade listan med åtgärder.

### <a name="change-the-mailbox-actions-to-audit"></a>Ändra postlådeåtgärderna till granska

Du kan använda parametrarna *AuditAdmin,* *AuditDelegate* och *AuditOwner* i cmdleten **Set-Mailbox** till att ändra postlådeåtgärder som granskas för användarpostlådor och delade postlådor (granskade åtgärder för Microsoft 365-grupppostlådor kan inte anpassas).

Du kan använda två olika metoder för att ange postlådeåtgärder:

- *Ersätt* (skriva över) befintliga postlådeåtgärder med hjälp av följande syntax: `action1,action2,...actionN` .
- *Lägg till eller ta* bort postlådeåtgärder utan att påverka andra befintliga värden genom att använda följande syntax: `@{Add="action1","action2",..."actionN"}` eller `@{Remove="action1","action2",..."actionN"}` .

Det här exemplet ändrar åtgärderna för administratörspostlådan för postlådan "Gabriela Laureano" genom att skriva över standardåtgärderna med SoftDelete och HardDelete.

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

I det här exemplet läggs åtgärden MailboxLogin till i postlådans laura@contoso.onmicrosoft.com.

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

Det här exemplet tar bort ombudsåtgärden MoveToDeletedItems för postlådan Gruppdiskussion.

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

Oavsett vilken metod du använder får anpassning av åtgärder i granskade postlådor för användarpostlådor eller delade postlådor följande resultat:

- För den inloggningstyp som du har anpassat hanteras inte längre de granskade postlådeåtgärderna av Microsoft.
- Inloggningstypen du har anpassat visas inte längre i egenskapsvärdet *DefaultAuditSet* för postlådan enligt [beskrivningen ovan.](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)

### <a name="restore-the-default-mailbox-actions"></a>Återställa standardåtgärder i postlådan

> [!NOTE]
> Följande procedurer gäller inte för e Microsoft 365 postlådor för grupper (de är begränsade till standardåtgärderna enligt beskrivningen [här](#mailbox-actions-for-microsoft-365-group-mailboxes)).

Om du har anpassat postlådeåtgärder som granskas för en användarpostlåda eller en delad postlåda kan du återställa standardåtgärderna för postlådan för en eller alla inloggningstyper med hjälp av följande syntax:

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

Du kan ange flera *DefaultAuditSet-värden* avgränsade med kommatecken

Det här exemplet återställer de granskade standardpostlådeåtgärderna för alla inloggningstyper på mark@contoso.onmicrosoft.com.

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

Det här exemplet återställer de granskade standardpostlådeåtgärderna för inloggningstypen Administratör för postlådan i chris@contoso.onmicrosoft.com, men lämnar kvar de anpassade granskade postlådeåtgärderna för inloggningstyperna Ombud och Ägare.

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

Återställning av standardgranskning av postlådeåtgärder för en inloggningstyp har följande resultat:

- Den aktuella listan med postlådeåtgärder ersätts med standardpostlådeåtgärderna för inloggningstypen.
- Nya postlådeåtgärder som släpps av Microsoft läggs automatiskt till i listan över granskade åtgärder för inloggningstypen.
- Egenskapsvärdet *DefaultAuditSet* för postlådan uppdateras så att det omfattar återställd inloggningstyp.

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>Inaktivera postlådegranskning som standard för din organisation

Du kan inaktivera postlådegranskning som standard för hela organisationen genom att köra följande kommando i Exchange Online PowerShell:

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

Om du inaktiverar postlådegranskning som standard får du följande resultat:

- Postlådegranskning är inaktiverat för organisationen.
- Från det att du inaktiverade postlådegranskning som standard granskas inga postlådeåtgärder, även om granskning har aktiverats för en postlåda (egenskapen *AuditEnabled* för postlådan är **True**).
- Postlådegranskning är inte aktiverat för nya postlådor och om du anger egenskapen *AuditEnabled* för en ny eller befintlig postlåda till **True** ignoreras den.
- Alla inställningar för att kringgå postlådekopplingar (konfigurerade med hjälp av **cmdleten Set-MailboxAuditBypassAssociation)** ignoreras.
- Befintliga granskningsposter för postlådor behålls tills åldersgränsen för granskningsloggen för posten går ut.

### <a name="turn-on-mailbox-auditing-on-by-default"></a>Aktivera postlådegranskning som standard

Om du vill aktivera postlådegranskning igen för organisationen kör du följande kommando i Exchange Online PowerShell:

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>Kringgå granskningsloggning för postlådor

Du kan för närvarande inte inaktivera granskning av postlådor för specifika postlådor när postlådegranskning är aktiverad som standard i din organisation. Till exempel ignoreras *inställningen för postlådeegenskapen AuditEnabled* **till** False.

Du kan dock fortfarande använda cmdleten **Set-MailboxAuditBypassAssociation** i Exchange Online  PowerShell för att förhindra att några och alla postlådeåtgärder från angivna användare loggas, oavsett var åtgärderna sker. Till exempel:

- Åtgärder som utförs av de förbikopplade användarna loggas inte.
- Ombudsåtgärder som utförts av förbikopplingsanvändare i andra användares postlådor (inklusive delade postlådor) loggas inte.
- Administratörsåtgärder som utförs av förbikopplade användare loggas inte.

Om du vill åsidosätta granskningsloggning för postlådor för en viss användare ersätter du med användarens namn, e-postadress, alias eller huvudnamn \<MailboxIdentity\> (användarnamn) och kör följande kommando:

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

Kör följande kommando för att kontrollera att granskning kringgås för den angivna användaren:

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

Värdet **True anger** att granskningsloggning för postlådor kringgås för användaren.

## <a name="more-information"></a>Mer information

- Även om granskningsloggning för postlådor som standard är aktiverad för alla organisationer [](search-the-audit-log-in-security-and-compliance.md) returnerar endast användare med E & 5-licenser granskningslogghändelser för postlådor i granskningsloggsökningar i Säkerhets- och efterlevnadscenter eller via API:t för [hanteringsaktivitet](/office/office-365-management-api/office-365-management-activity-api-reference) i Office 365 som **standard.**

  Om du vill hämta granskningsloggposter för postlådor för användare utan E5-licenser kan du:

  - Aktivera postlådegranskning manuellt för enskilda postlådor (kör kommandot `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` ). När du har gjort det kan du använda granskningsloggsökningar i Säkerhets- & eller via API:t Office 365 för hanteringsaktivitet.
  
    > [!NOTE]
    > Om postlådegranskning redan verkar vara aktiverad för postlådan, men sökningarna inte returnerar några resultat, så kan du ändra värdet för parametern _AuditEnabled_ till och `$false` sedan tillbaka till `$true` .
  
  - Använd följande cmdlets i Exchange Online PowerShell:
    - [Search-MailboxAuditLog för](/powershell/module/exchange/search-mailboxauditlog) att söka i granskningsloggen för postlådor för specifika användare.
    - [New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) för att söka i granskningsloggen för postlådor för specifika användare och få resultatet skickat via e-post till vissa mottagare.

  - Använd Exchange (EAC) i Exchange Online för att göra följande:
    - [Exportera granskningsloggar för postlådor](/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)
    - [Köra en rapport om postlådeåtkomst som inte är en ägare](/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- Som standard behålls granskningsloggposter för postlådor i 90 dagar innan de tas bort. Du kan ändra åldersgränsen för granskningsloggposter med hjälp av parametern *AuditLogAgeLimit* i cmdleten **Set-Mailbox** Exchange Online PowerShell. Men om du ökar det här värdet kan du inte söka efter händelser som är äldre än 90 dagar i granskningsloggen.

  Om du ökar åldersgränsen måste du använda cmdleten [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) i Exchange Online PowerShell för att söka i användarens granskningslogg för postlådor efter poster som är äldre än 90 dagar.

- Om du har ändrat egenskapen *AuditLogAgeLimit* för en postlåda innan postlådegranskning aktiveras som standard för organisationen, ändras inte postlådans befintliga åldersgräns för granskningsloggen. Med andra ord påverkar postlådegranskning som standard inte den aktuella åldersgränsen för postlådegranskningsposter.

- Om du vill *ändra värdet i AuditLogAgeLimit* Microsoft 365 en grupppostlåda måste du ta med växeln `-GroupMailbox` i kommandot **Set-Mailbox.**

- Granskningsloggposter för postlådor lagras i en undermapp (med namnet Granskningar) i mappen Återställningsbara objekt i varje *användares* postlåda. Tänk på följande om granskningsposter för postlådor och mappen Återställningsbara objekt:

  - Granskningsposter för postlådor räknas in i lagringskvoten för mappen återställningsbara objekt, som är 30 GB som standard (varningskvoten är 20 GB). Lagringskvoten ökas automatiskt till 100 GB (med en varningskvot på 90 GB) när:
    - Ett is hold is placed on a mailbox.
    - Postlådan har tilldelats en bevarandeprincip i efterlevnadscentret.

  - Granskningsposter för postlådor räknas också mot [mappgränsen för mappen Återställningsbara objekt.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits) Högst 3 miljoner objekt (granskningsposter) kan lagras i undermappen Granskningar.

    > [!NOTE]
    > Det är inte troligt att postlådegranskning som standard påverkar lagringskvoten eller mappgränsen för mappen återställningsbara objekt.

    - Du kan köra följande kommando i Exchange Online PowerShell för att visa storlek och antal objekt i undermappen Granskningar i mappen Återställningsbara objekt:

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - Du kan inte direkt komma åt en granskningsloggpost i mappen Återställningsbara objekt. I stället använder du cmdleten **Search-MailboxAuditLog** eller söker i granskningsloggen för att hitta och visa granskningsposter för postlådor.

- Om en postlåda sätts på bevarande eller tilldelas till en bevarandeprincip i efterlevnadscentret behålls granskningsloggposter fortfarande under den tid som anges av postlådans *AuditLogAgeLimit-egenskap* (90 dagar som standard). Om du vill behålla granskningsloggposter längre för postlådor som är på plats måste du öka postlådans *AuditLogAgeLimit-värde.*

- I en multigeomiljö stöds inte granskning av flera geopostlådor. Om en användare till exempel har tilldelats behörigheter för att komma åt en delad postlåda på en annan geo plats loggas inte postlådeåtgärder som utförs av den användaren i granskningsloggen för postlådan för den delade postlådan.
