---
title: Visa administratörsgranskningsloggen i fristående EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Administratörer kan lära sig att visa och söka i administratörs gransknings loggen i fristående Exchange Online Protection (EOP).
ms.openlocfilehash: 8890ab8f2f2db01ed6bd22657a9bea8f77b25d08
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825083"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>Visa administratörsgranskningsloggen i fristående EOP

I fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor kan du använda Exchange Admin Center (UK) eller fristående EOP PowerShell för att söka efter och Visa poster i administratörs gransknings loggen.

Administratörs gransknings loggen registrerar specifika åtgärder baserat på fristående EOP PowerShell-cmdlets, som utförs av administratörer och användare som har tilldelats administratörs behörighet. Poster i administratörs gransknings loggen ger dig information om vilken cmdlet som kördes, vilka parametrar som användes, vem som körde cmdleten och vilka objekt som påverkades.

> [!NOTE]
>
> - Loggning för administratörs granskning är aktiverat som standard och kan inte inaktive ras.
>
> - Administratörs gransknings loggen spelar inte in åtgärder baserat på cmdlets som börjar med verben **Get**, **search**eller **test**.
>
> - Gransknings logg poster bevaras i 90 dagar. När en post är äldre än 90 dagar raderas den

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Om du vill öppna administrations centret för Exchange går du till [administrations Center för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna. Specifikt måste du ha rollen gransknings loggar eller skrivskyddade loggar, som är tilldelad till ComplianceManagement, i (globala administratörer) och SecurityAdministrator roll grupper som standard. Mer information finns i [behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd UK för att ändra listan över medlemmar i roll grupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Information om tangent bords gen vägar som kan gälla för procedurerna i det här avsnittet finns i kortkommandon [för administrations centret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Har du problem? Be om hjälp i [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>Använda UK för att Visa administratörs gransknings loggen

1. Gå till granskning i **överensstämmelse hantering** i UK \> **Auditing**och välj sedan **kör rapporten administratörs Gransknings logg**.

2. Välj ett **start datum** och **slutdatum** i listan **Sök efter ändringar på sidan för administratörs roller** som öppnas och välj sedan **Sök**. Alla konfigurations ändringar som görs under den angivna tids perioden visas och kan sorteras med hjälp av följande information:

   - **Datum**: det datum och den tid då konfigurations ändringen gjordes. Datum och tid sparas i UTC-format (Coordinated Universal Time).

   - **Cmdlet**: namnet på den cmdlet som användes för att göra konfigurations ändringen.

   - **Användare**: namnet på användar kontot för den användare som gjorde konfigurations ändringen.

     Upp till 5000-poster visas på flera sidor. Ange ett kortare datum intervall om du vill begränsa resultatet. Om du väljer ett enskilt Sök resultat visas följande information i informations fönstret:

   - **Objekt ändrat**: objektet som ändrades av cmdleten.

   - **Parametrar (parameter: värde)**: cmdlet-parametrarna som användes och alla värden som anges med parametern.

3. Om du vill skriva ut en viss Gransknings logg post väljer du knappen **Skriv ut** i informations fönstret.

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>Använd fristående EOP PowerShell för att Visa administratörs gransknings loggen

Du kan använda fristående EOP PowerShell för att söka efter poster för gransknings loggar som uppfyller de villkor du anger. Använd följande syntax:

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**Anmärkningar**:

- Du kan bara använda parametern _Parameters_ tillsammans med parametern _cmdlets_ .

- Parametern _ObjectIds_ filtrerar resultaten efter det objekt som har ändrats av cmdleten. Ett giltigt värde beror på hur objektet visas i gransknings loggen. Till exempel:

  - Namn
  - Kanoniskt unikt namn (till exempel contoso.com/Users/Akia Al-Zuhairi)

  Du kommer troligen att behöva använda andra filtrerings parametrar för denna cmdlet för att begränsa resultaten och identifiera vilka typer av objekt du är intresse rad av.

- Parametern _UserIds_ filtrerar resultaten av användaren som gjorde ändringen (som körde cmdleten).

- För parametrarna _StartDate_ och _EndDate_ om du anger ett datum-och tids värde utan en tidszon är värdet i Coordinated Universal Time (UTC). Om du vill ange ett datum/tid-värde för den här parametern använder du något av följande alternativ:

  - Ange datum-och tids värden i UTC: till exempel "2016-05-06 14:30:00Z".

  - Ange datum-och tids värden som en formel som konverterar datum/tid i din lokala tidszon till UTC: till exempel `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` . Mer information finns i [Hämta-datum](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).

- Cmdleten returnerar högst 1 000 loggnings poster som standard. Använd parametern _ResultSize_ för att ange upp till 250 000-loggnings poster. Eller Använd värdet `Unlimited` för att returnera alla poster.

I det här exemplet utförs en sökning efter alla gransknings loggar med följande villkor:

- **Start datum**: 4 augusti 2019
- **Slutdatum**: 3 oktober 2019
- **Cmdletar**: Update-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

Detaljerad information om syntax och parametrar finns i [sökAdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Visa information om Gransknings logg poster

Cmdleten **search-AdminAuditLog** returnerar fälten som beskrivs i avsnittet [granska logg innehåll](#audit-log-contents) längre ned i det här avsnittet. För de fält som returneras av cmdleten, två fält, **CmdletParameters** och **ModifiedProperties**, innehåller ytterligare information som inte returneras som standard.

Om du vill visa innehållet i fälten **CmdletParameters** och **ModifiedProperties** följer du stegen nedan.

1. Välj de villkor du vill söka efter, kör **Sök-AdminAuditLog** cmdlet och lagra resultatet i en variabel med hjälp av följande kommando.

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. Varje post för gransknings logg sparas som ett mat ris element i variabeln `$Results` . Du kan välja ett mat ris element genom att ange dess mat ris element index. Mat ris element index börjar med noll (0) för det första mat ris elementet. Om du till exempel vill hämta femte mat ris elementet, som har index 4, använder du följande kommando.

    ```PowerShell
    $Results[4]
    ```

3. Föregående kommando returnerar den loggpost som är lagrad i mat ris element 4. Använd följande kommandon för att visa innehållet i fälten **CmdletParameters** och **ModifiedProperties** för den här logg posten.

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. Om du vill visa innehållet i fälten **CmdletParameters** eller **ModifiedParameters** i en annan loggpost ändrar du mat ris element indexet.

## <a name="audit-log-contents"></a>Innehåll i gransknings loggen

Varje gransknings loggpost innehåller den information som beskrivs i följande tabell. Gransknings loggen innehåller en eller flera Gransknings logg poster.

****

|Radfält|Beskrivning|
|---|---|
|`RunspaceId`|Det här fältet används internt av EOP.|
|`ObjectModified`|Det här fältet innehåller objektet som ändrades av den cmdlet som anges i `CmdletName` fältet.|
|`CmdletName`|Det här fältet innehåller namnet på den cmdlet som kördes av användaren i `Caller` fältet.|
|`CmdletParameters`|Det här fältet innehåller de parametrar som angavs när cmdleten i `CmdletName` fältet kördes. I det här fältet, men inte visas i standardutdata, är det värde som anges med parametern, om det finns något.|
|`ModifiedProperties`|Det här fältet innehåller de egenskaper som har ändrats för objektet i `ObjectModified` fältet. I det här fältet, men inte visas i standardutdata, är det gamla värdet för egenskapen och det nya värdet som har lagrats.|
|`Caller`|Det här fältet innehåller användar kontot för den användare som körde cmdleten i `CmdletName` fältet.|
|`ExternalAccess`|Det här fältet används internt av EOP.|
|`Succeeded`|Det här fältet anger om cmdleten i `CmdletName` fältet lyckades. Värdet är antingen `True` eller `False` .|
|`Error`|Det här fältet innehåller fel meddelandet som skapas om cmdleten i `CmdletName` fältet inte gick att slutföra.|
|`RunDate`|I det här fältet visas det datum och den tid då cmdleten i `CmdletName` fältet kördes. Datum och tid sparas i UTC-format (Coordinated Universal Time).|
|`OriginatingServer`|I det här fältet visas den server där cmdleten som anges i `CmdletName` fältet kördes.|
|`ClientIP`|Det här fältet används internt av EOP.|
|`SessionId`|Det här fältet används internt av EOP.|
|`AppId`|Det här fältet används internt av EOP.|
|`ClientAppId`|Det här fältet används internt av EOP.|
|`Identity`|Det här fältet används internt av EOP.|
|`IsValid`|Det här fältet används internt av EOP.|
|`ObjectState`|Det här fältet används internt av EOP.|
|
