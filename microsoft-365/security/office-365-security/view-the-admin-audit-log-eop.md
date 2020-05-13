---
title: Visa administratörsgranskningsloggen i fristående EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Administratörer kan lära sig att visa och söka i administratörsgranskningsloggen i fristående Exchange Online Protection (EOP).
ms.openlocfilehash: 3aedebc97ccd32c1641510017a276ddbe4770633
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208482"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>Visa administratörsgranskningsloggen i fristående EOP

I fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kan du använda Administrationscenter för Exchange (EAC) eller fristående EOP PowerShell för att söka efter och visa poster i administratörsgranskningsloggen.

Administratörsgranskningsloggen registrerar specifika åtgärder, baserat på fristående EOP PowerShell-cmdletar, som utförs av administratörer och användare som har tilldelats administratörsbehörighet. Posterna i administratörsgranskningsloggen ger dig information om vad cmdlet kördes, vilka parametrar som användes, vem som körde cmdleten och vilka objekt som påverkades.

> [!NOTE]
> <ul><li>Administratörsgranskningsloggning är aktiverat som standard och du kan inte inaktivera den.</li><li>Administratörsgranskningsloggen registrerar inte åtgärder baserat på cmdlets som börjar med verben **Get**, **Search**eller **Test**.</li><li>Granskningsloggposter sparas i 90 dagar. När en post är äldre än 90 dagar tas den bort</li></ul>

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Om du vill öppna administrationscentret för Exchange finns [i Administrationscenter för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Du behöver rollen Granskningsloggar eller granskningsloggar för endast granskning, som tilldelas rollgrupperna ComplianceManagement, OrganizationManagement (global admins) och SecurityAdministrator som standard. Mer information finns [i Behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd EAC ändra listan över medlemmar i rollgrupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns [i Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Har du problem? Be om hjälp i Forumet för [Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>Använd EAC för att visa administratörsgranskningsloggen

1. Gå till Granskning av **efterlevnadshantering** i EAC \> **Auditing**och välj sedan Kör rapporten **för administratörsgranskningsloggen**.

2. På sidan **Sök efter ändringar på administratörsrollgrupper** som öppnas väljer du ett **startdatum** och **slutdatum** (standardintervallet är de senaste två veckorna) och välj sedan **Sök**. Alla konfigurationsändringar som görs under den angivna tidsperioden visas och kan sorteras med hjälp av följande information:

   - **Datum**: Datum och tid då konfigurationsändringen gjordes. Datum och tid lagras i UTC-format (Coordinated Universal Time).

   - **Cmdlet**: Namnet på den cmdlet som användes för att göra konfigurationen ändras.

   - **Användare**: Namnet på användarkontot för den användare som gjorde konfigurationsändringen.

     Upp till 5000 poster visas på flera sidor. Ange ett mindre datumintervall om du behöver begränsa resultaten. Om du väljer ett enskilt sökresultat visas följande ytterligare information i informationsfönstret:

   - **Objektet har ändrats**: Objektet som har ändrats av cmdleten.

   - **Parametrar (parameter:Värde)**: De cmdletparametrar som användes och alla värden som anges med parametern.

3. Om du vill skriva ut en viss granskningsloggpost väljer du knappen **Skriv ut** i informationsfönstret.

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>Använd fristående EOP PowerShell för att visa administratörsgranskningsloggen

Du kan använda fristående EOP PowerShell för att söka efter granskningsloggposter som uppfyller de villkor du anger. Använd följande syntax:

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**Anmärkningar**:

- Du kan bara använda _parametern Parametrar_ tillsammans med parametern _Cmdlets._

- Parametern _ObjectIds filtrerar_ resultatet efter objektet som ändrades av cmdleten. Ett giltigt värde beror på hur objektet representeras i granskningsloggen. Till exempel:

  - Namn
  - Kanoniskt unikt namn (till exempel contoso.com/Users/Akia Al-Zuhairi)

  Du kommer förmodligen att behöva använda andra filtreringsparametrar på den här cmdleten för att begränsa resultaten och identifiera vilka typer av objekt som du är intresserad av.

- Parametern _UserIds_ filtrerar resultatet av den användare som gjorde ändringen (som körde cmdleten).

- Om du anger ett datum-/tidsvärde utan tidszon för _parametrarna StartDate_ och _EndDate_ finns värdet i Coordinated Universal Time (UTC). Om du vill ange ett datum-/tidsvärde för den här parametern använder du något av följande alternativ:

  - Ange datum-/tidsvärdet i UTC: Till exempel "2016-05-06 14:30:00z".

  - Ange datum-/tidsvärdet som en formel som konverterar datum/tid i den lokala tidszonen till UTC: Till exempel `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` . Mer information finns i [Hämta datum](https://go.microsoft.com/fwlink/p/?LinkID=113313).

- Cmdlet returnerar som standard högst 1 000 loggposter. Använd parametern _ResultSize_ för att ange upp till 250 000 loggposter. Du kan också använda värdet `Unlimited` för att returnera alla transaktioner.

I det här exemplet söker du efter alla granskningsloggposter med följande villkor:

- **Startdatum**: 4 augusti 2019
- **Slutdatum**: 3 oktober 2019
- **Cmdlets**: Update-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

Detaljerad syntax- och parameterinformation finns i [Sök-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Visa information om granskningsloggposter

**Cmdlet search-adminAuditLog** returnerar de fält som beskrivs i avsnittet [Granskningslogginnehåll](#audit-log-contents) senare i det här avsnittet. Av de fält som returneras av cmdlet, två fält, **CmdletParameters** och **ModifiedProperties**, innehåller ytterligare information som inte returneras som standard.

Om du vill visa innehållet i fälten **CmdletParameters** och **ModifiedProperties** använder du följande steg.

1. Bestäm vilka villkor du vill söka efter, kör cmdleten **Sök-AdminAuditLog** och lagra resultaten i en variabel med följande kommando.

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. Varje granskningsloggpost lagras som ett matriselement i variabeln `$Results` . Du kan markera ett matriselement genom att ange dess matriselementindex. Matriselementindex börjar vid noll (0) för det första matriselementet. Om du till exempel vill hämta det 5:e matriselementet, som har ett index på 4, använder du följande kommando.

    ```PowerShell
    $Results[4]
    ```

3. Föregående kommando returnerar loggposten som lagras i matriselement 4. Om du vill visa innehållet i fälten **CmdletParameters** och **ModifiedProperties** för den här loggposten använder du följande kommandon.

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. Om du vill visa innehållet i fälten **CmdletParameters** eller **ModifiedParameters** i en annan loggpost ändrar du matriselementindexet.

## <a name="audit-log-contents"></a>Innehåll i granskningsloggen

Varje granskningsloggpost innehåller den information som beskrivs i följande tabell. Granskningsloggen innehåller en eller flera granskningsloggposter.

|||
|---|---|
|**Fält**|**Beskrivning**|
|`RunspaceId`|Det här fältet används internt av EOP.|
|`ObjectModified`|Det här fältet innehåller det objekt som har ändrats av den cmdlet som anges i `CmdletName` fältet .|
|`CmdletName`|Det här fältet innehåller namnet på den cmdlet som kördes av användaren i `Caller` fältet .|
|`CmdletParameters`|Det här fältet innehåller de parametrar som angavs när cmdleten i `CmdletName` fältet kördes. Också lagras i det här fältet, men inte synlig i standardutdata, är det värde som anges med parametern, om någon.|
|`ModifiedProperties`|Det här fältet innehåller de egenskaper som har ändrats för objektet i `ObjectModified` fältet. Också lagras i det här fältet, men inte synlig i standardutdata, är det gamla värdet för egenskapen och det nya värdet som lagrades.|
|`Caller`|Det här fältet innehåller användarkontot för den användare som körde cmdleten i `CmdletName` fältet .|
|`ExternalAccess`|Det här fältet används internt av EOP.|
|`Succeeded`|Det här fältet anger om cmdleten i `CmdletName` fältet kördes. Värdet är antingen `True` eller `False` .|
|`Error`|Det här fältet innehåller felmeddelandet som genereras om cmdleten i `CmdletName` fältet inte kunde slutföras.|
|`RunDate`|Det här fältet innehåller datum och tid då cmdleten i `CmdletName` fältet kördes. Datum och tid lagras i UTC-format (Coordinated Universal Time).|
|`OriginatingServer`|Det här fältet anger den server där den cmdlet som anges i `CmdletName` fältet kördes.|
|`ClientIP`|Det här fältet används internt av EOP.|
|`SessionId`|Det här fältet används internt av EOP.|
|`AppId`|Det här fältet används internt av EOP.|
|`ClientAppId`|Det här fältet används internt av EOP.|
|`Identity`|Det här fältet används internt av EOP.|
|`IsValid`|Det här fältet används internt av EOP.|
|`ObjectState`|Det här fältet används internt av EOP.|
|
