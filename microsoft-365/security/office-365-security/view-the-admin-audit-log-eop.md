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
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Administratörer kan läsa om hur de visar och söker i granskningsloggen för administratörer i fristående Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5ed1d1eb121c06e6f5727e8782ba1d8bc8d23a99
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908132"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>Visa administratörsgranskningsloggen i fristående EOP

**Gäller för**
- [Exchange Online Protection fristående](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kan du använda Administrationscenter för Exchange (EAC) eller fristående EOP PowerShell för att söka efter och visa poster i granskningsloggen för administratörer.

I granskningsloggen för administratörer registrerar du specifika åtgärder, baserat på fristående EOP PowerShell-cmdlets, som utförs av administratörer och användare som har tilldelats administratörsbehörighet. Posterna i administratörsgranskningsloggen ger dig information om vilken cmdlet som körts, vilka parametrar som användes, vem som körde cmdleten och vilka objekt som påverkades.

> [!NOTE]
>
> - Granskningsloggning för administratörer är aktiverat som standard och du kan inte inaktivera den.
>
> - I granskningsloggen för administratörer spelas inte åtgärder in baserat på cmdlets som börjar med verben **Hämta,** **Sök** eller **Testa.**
>
> - Granskningsloggposter sparas i 90 dagar. När en post är äldre än 90 dagar tas den bort

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Information om hur du öppnar administrationscentret för Exchange finns [i Administrationscenter för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter i Exchange Online Protection innan du kan utföra procedurerna i den här artikeln. Mer specifikt behöver  du  rollen Granskningsloggar eller Visningsskyddade granskningsloggar som tilldelas rollgrupperna Organisationshantering, Efterlevnadshantering och **Säkerhetsadministratör** som standard.  Mer information finns i [Behörigheter i fristående EOP](feature-permissions-in-eop.md) och Använda EAC för att [ändra listan över medlemmar i rollgrupper.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Mer information om kortkommandon som kan gälla för procedurerna i den här artikeln finns i Kortkommandon för [Administrationscenter för Exchange i Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Har du problem? Be om hjälp i [Forumet för Exchange Online Protection.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>Använda EAC för att visa granskningsloggen för administratören

1. Gå till Granskning av efterlevnadshantering **i** EAC \> **och** välj sedan **Kör granskningsloggrapport för administratör.**

2. På sidan Sök efter ändringar i **administratörsrollgrupper** som öppnas väljer du startdatum och slutdatum (standardintervallet är de senaste två veckorna) och väljer sedan **Sök**.   Alla konfigurationsändringar som gjorts under den angivna tidsperioden visas och kan sorteras med hjälp av följande information:

   - **Datum:** Datum och tid då konfigurationsändringen gjordes. Datum och tid lagras i UTC-format (Coordinated Universal Time).

   - **Cmdlet:** Namnet på den cmdlet som användes för att göra konfigurationsändringen.

   - **Användare**: Namnet på användarkontot för den användare som gjorde konfigurationsändringen.

     Upp till 5 000 poster visas på flera sidor. Ange ett mindre datumintervall om du behöver begränsa resultatet. Om du väljer ett enskilt sökresultat visas följande ytterligare information i informationsfönstret:

   - **Ändrad objekt:** Objektet som ändrades av cmdleten.

   - **Parametrar (Parameter:Värde)**: Cmdlet-parametrarna som användes och alla värden som anges med parametern.

3. Om du vill skriva ut en viss granskningsloggpost väljer **du knappen** Skriv ut i informationsfönstret.

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>Använda fristående EOP PowerShell för att visa granskningsloggen för administratörer

Du kan använda fristående EOP PowerShell för att söka efter granskningsloggposter som uppfyller de villkor du anger. Använd följande syntax:

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**Anmärkningar**:

- Du kan bara använda _parametern Parameters_ tillsammans med _Cmdlets-parametern._

- Parametern _ObjectIds_ filtrerar resultaten av objektet som ändrades av cmdleten. Ett giltigt värde beror på hur objektet representeras i granskningsloggen. Ett exempel:

  - Namn
  - Canonical distinguished name (till exempel contoso.com/Users/Akia Al-Zuhairi)

  Du måste förmodligen använda andra filtreringsparametrar i den här cmdleten för att begränsa resultatet och identifiera de typer av objekt som du är intresserad av.

- Parametern _UserIds_ filtrerar resultatet av den användare som gjorde ändringen (som körde cmdleten).

- Om du anger  ett datum-/tidsvärde utan en tidszon för parametrarna _Startdatum_ och Slutdatum anges värdet i UTC (Coordinated Universal Time). Om du vill ange ett datum-/tidsvärde för den här parametern använder du något av följande alternativ:

  - Ange datum-/tidsvärdet i UTC: Till exempel "2016-05-06 14:30:00z".

  - Ange datum-/tidsvärdet som en formel som konverterar datum/tid i din lokala tidszon till UTC: till exempel `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` . Mer information finns i [Hämta datum.](/powershell/module/microsoft.powershell.utility/get-date)

- Cmdleten returnerar högst 1 000 loggposter som standard. Använd _parametern ResultSize_ till att ange upp till 250 000 loggposter. Du kan också använda värdet `Unlimited` för att returnera alla poster.

I det här exemplet utförs en sökning efter alla granskningsloggposter med följande kriterier:

- **Startdatum:** 4 augusti 2019
- **Slutdatum:** 3 oktober 2019
- **Cmdlets**: Update-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

Detaljerad information om syntax och parametrar finns [i Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Visa information om granskningsloggposter

**Cmdlet:en Search-AdminAuditLog** returnerar de fält som beskrivs i avsnittet Granskningslogginnehåll längre fram i den här artikeln. [](#audit-log-contents) Av de fält som returneras av cmdleten innehåller två fält, **CmdletParameters** **och ModifiedProperties,** ytterligare information som inte returneras som standard.

Gör så här om du vill visa innehållet i fälten **CmdletParameters** och **ModifiedProperties.**

1. Bestäm vilka kriterier du vill söka efter, kör cmdleten **Search-AdminAuditLog** och lagra resultaten i en variabel med hjälp av följande kommando.

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. Varje granskningsloggpost lagras som ett matriselement i variabeln `$Results` . Du kan välja ett matriselement genom att ange dess matriselementindex. Matriselementindex börjar med noll (0) för det första matriselementet. Om du till exempel vill hämta det femte matriselementet, som har indexet 4, använder du följande kommando.

    ```PowerShell
    $Results[4]
    ```

3. Föregående kommando returnerar loggposten som lagrats i matriselement 4. Använd följande kommandon för att visa innehållet i fälten **CmdletParameters** och **ModifiedProperties** för den här loggposten.

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. Om du vill visa innehållet i **fälten CmdletParameters** eller **ModifiedParameters** i en annan loggpost ändrar du matriselementindexet.

## <a name="audit-log-contents"></a>Granska logginnehåll

Varje granskningsloggpost innehåller den information som beskrivs i följande tabell. Granskningsloggen innehåller en eller flera granskningsloggposter.

****

|Fält|Beskrivning|
|---|---|
|`RunspaceId`|Det här fältet används internt av EOP.|
|`ObjectModified`|Det här fältet innehåller det objekt som ändrades av den cmdlet som anges i `CmdletName` fältet.|
|`CmdletName`|Det här fältet innehåller namnet på den cmdlet som körts av användaren i `Caller` fältet.|
|`CmdletParameters`|Det här fältet innehåller de parametrar som angavs när cmdleten `CmdletName` i fältet körts. Det värde som anges med parametern, om det finns något, lagras också i det här fältet, men inte visas i standardutdata.|
|`ModifiedProperties`|Det här fältet innehåller de egenskaper som har ändrats för objektet i `ObjectModified` fältet. Det gamla värdet för egenskapen och det nya värdet som lagrats är samma som det som lagrats i det här fältet, men inte visas i standardutdata.|
|`Caller`|Det här fältet innehåller användarkontot för användaren som körde cmdleten i `CmdletName` fältet.|
|`ExternalAccess`|Det här fältet används internt av EOP.|
|`Succeeded`|Det här fältet anger om cmdleten i `CmdletName` fältet har körts. Värdet är antingen `True` eller `False` .|
|`Error`|Det här fältet innehåller det felmeddelande som genereras om cmdleten `CmdletName` i fältet inte kunde slutföras.|
|`RunDate`|Det här fältet innehåller datum och tid då cmdleten `CmdletName` i fältet körts. Datum och tid lagras i UTC-format (Coordinated Universal Time).|
|`OriginatingServer`|Det här fältet anger den server där cmdleten som anges i `CmdletName` fältet körs.|
|`ClientIP`|Det här fältet används internt av EOP.|
|`SessionId`|Det här fältet används internt av EOP.|
|`AppId`|Det här fältet används internt av EOP.|
|`ClientAppId`|Det här fältet används internt av EOP.|
|`Identity`|Det här fältet används internt av EOP.|
|`IsValid`|Det här fältet används internt av EOP.|
|`ObjectState`|Det här fältet används internt av EOP.|
|