---
title: Köra en administratörsrapport för rollgrupp i fristående EOP
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
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om hur man kör en administratörs grupp rapport i fristående Exchange Online Protection (EOP). Den här rapporten loggar när en administratör lägger till eller tar bort medlemmar från administratörs roll grupper, loggar EOP varje gång.
ms.openlocfilehash: f2f3e32a818825d14c02b2bbffdc136e82f83013
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200487"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>Köra en administratörsrapport för rollgrupp i fristående EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor när en administratör lägger till eller tar bort medlemmar från administratörs roll grupper loggar tjänsten in varje förekomst. Mer information om roll grupper i fristående EOP finns i [behörigheter i fristående EOP](feature-permissions-in-eop.md).

När du kör en rapport i administratörs gruppen för administratörer i administrations centret för Exchange (UK) visas posterna som Sök Resultat och innehåller de roll grupper som påverkas, vem som ändrade roll gruppens medlemskap och när och vilka medlemskaps uppdateringar som har gjorts. Använd den här rapporten för att övervaka ändringar av de administrativa behörigheter som tilldelats användare i organisationen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Om du vill öppna administrations centret för Exchange går du till [administrations Center för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna. Specifikt måste du ha rollen gransknings loggar eller skrivskyddade loggar, som är tilldelad till ComplianceManagement, i (globala administratörer) och SecurityAdministrator roll grupper som standard. Mer information finns i [behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd UK för att ändra listan över medlemmar i roll grupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Information om tangent bords gen vägar som kan gälla för procedurerna i det här avsnittet finns i kortkommandon [för administrations centret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Har du problem? Be om hjälp i [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Använda rapporten UK för att köra en administratörs roll

Kör rapporten administratörs grupp för att hitta ändringarna av roll grupperna för hantering i organisationen inom en viss tidsram.

1. Gå till granskning i **överensstämmelse hantering** i UK \> **Auditing**och välj sedan **kör en administratörs grupp rapport för administratörer**.

2. I sidan **Sök efter ändringar av gruppen Administratörer** som öppnas konfigurerar du följande inställningar:

   - **Start datum** och **slutdatum**: Ange ett datum intervall. Som standard söker rapporten efter ändringar som gjorts i administratörs roll grupper under de senaste två veckorna.

   - **Välj roll grupper**: som standard genomsöks alla roll grupper. Om du vill filtrera resultaten efter specifika roll grupper klickar du på **Välj roll grupper**. I dialog rutan som visas väljer du en roll grupp och klickar på **Lägg till >**. Upprepa det här steget så många gånger som behövs och klicka sedan på **OK** när du är klar.

3. När du är klar klickar du på **Sök**.

Om några ändringar hittas med de villkor du angett visas de i fönstret resultat. Klicka på en roll grupp i Sök resultatet för att visa ändringarna i informations fönstret.

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Om du har kört en administratörs rapport för administratörer visas roll grupper som har ändrats inom datum intervallet i fönstret Sök resultat. Om det inte finns några resultat ändras inga roll grupper i det angivna datum intervallet. Om du tror att det borde finnas resultat, ändra datum intervallet och kör sedan rapporten igen.

## <a name="monitor-changes-to-role-group-membership"></a>Övervaka ändringar i roll grupp medlemskap

När medlemmar läggs till eller tas bort från en roll grupp indikerar Sök resultaten som visas i informations fönstret att roll grupp medlemskapet har uppdaterats och visar en lista över aktuella medlemmar. Resultaten anger inte uttryckligen vilken användare som lades till eller togs bort.

För att avgöra om en användare har lagts till eller tagits bort måste du jämföra två separata poster i rapporten. Låt oss titta på följande logg poster för roll gruppen **helpdesk** :

> 1/27/2018 4:43 PM <br> Lösen <br> Uppdaterade medlemmar: administratör; annb; florencef; pilarp <br> 2/06/2018 10:09 AM <br> Lösen <br> Uppdaterade medlemmar: administratör; annb; florencef; pilarp; tonip <br> 2/19/2018 2:12 PM <br> Lösen <br> Uppdaterade medlemmar: administratör; annb; florencef; tonip

I det här exemplet utförde administratörs användar kontot följande ändringar:

- I 2/06/2018 La de in användaren tonip.

- På 2/19/2018 har de tagit bort användaren pilarp.

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>Använda fristående Exchange Online PowerShell för att söka efter Gransknings logg poster

Du kan använda Exchange Online PowerShell för att söka efter poster för gransknings loggar som uppfyller de villkor du anger. En lista över Sök villkor finns i [Sök-AdminAuditLog Sök kriterier](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet). Den här proceduren använder cmdleten **search-AdminAuditLog** och visar Sök resultat i Exchange Online PowerShell. Du kan använda denna cmdlet när du behöver returnera en uppsättning resultat som överskrider de gränser som är definierade för **New-AdminAuditLogSearch-** cmdleten eller i rapporteringen för UK-granskningen.

Använd följande syntax för att söka i den Gransknings logg efter villkor du anger.

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> Cmdleten **search-AdminAuditLog** returnerar högst 1 000-loggpost som standard. Använd parametern _ResultSize_ för att ange upp till 250 000-loggnings poster. Eller Använd värdet `Unlimited` för att returnera alla poster.

I det här exemplet utförs en sökning efter alla gransknings loggar med följande villkor:

- **Start datum**: 08/04/2018

- **Slutdatum**: 10/03/2018

- **Användar-ID**: Davids, Chris Kima

- **Cmdlet**: **set-Mailbox**

- **Parametrar**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

I det här exemplet söker du efter ändringar som gjorts i en viss post låda. Det är användbart om du felsöker eller om du behöver ange information för en undersökning. Följande kriterier används:

- **Start datum**: 05/01/2018

- **Slutdatum**: 10/03/2018

- **Objekt-ID**: contoso.com/users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

Om dina sökningar returnerar många logg poster rekommenderar vi att du använder proceduren i **använda Exchange Online PowerShell för att söka efter poster för gransknings logg och skickar resultat till en mottagare** längre ned i det här avsnittet. Proceduren i avsnittet skickar en XML-fil som en e-postbilaga till de mottagare som du anger, vilket gör att du enkelt kan extrahera de data du är intresse rad av.

Detaljerad information om syntax och parametrar finns i [sökAdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Visa information om Gransknings logg poster

Cmdleten **search-AdminAuditLog** returnerar fälten som beskrivs i [gransknings loggens innehåll](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents). För de fält som returneras av cmdleten, två fält, **CmdletParameters** och **ModifiedProperties**, innehåller ytterligare information som inte visas som standard.

Om du vill visa innehållet i fälten **CmdletParameters** och **ModifiedProperties** följer du stegen nedan. Eller så kan du använda proceduren i **använda Exchange Online PowerShell för att söka efter poster för gransknings logg och skicka resultat till en mottagare** senare i det här avsnittet för att skapa en XML-fil.

I den här proceduren används följande koncept:

- [about_Arrays](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [about_Variables](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

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
