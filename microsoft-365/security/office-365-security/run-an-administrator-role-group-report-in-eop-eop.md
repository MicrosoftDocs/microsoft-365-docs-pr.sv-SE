---
title: Kör en rapport över administratörsrollgrupper i fristående EOP
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
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig hur du kör en administratörsrollgruppsrapport i fristående Exchange Online Protection (EOP). Den här rapporten loggar när en administratör lägger till medlemmar i eller tar bort medlemmar från administratörsrollgrupper, EOP loggar varje förekomst.
ms.openlocfilehash: f5641e9900c786f976d05cdeeec148caab12a03d
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209181"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>Kör en rapport över administratörsrollgrupper i fristående EOP

I fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor, när en administratör lägger till medlemmar i eller tar bort medlemmar från administrativa rollgrupper, loggar tjänsten varje förekomst. Mer information om rollgrupper i fristående EOP finns [i Behörigheter i fristående EOP](feature-permissions-in-eop.md).

När du kör en administratörsrollgruppsrapport i Administrationscenter för Exchange (EAC) visas poster som sökresultat och inkluderar de rollgrupper som påverkas, vem som har ändrat rollgruppsmedlemskapet och när och vilka medlemsuppdateringar som gjordes. Använd den här rapporten om du vill övervaka ändringar av de administrativa behörigheter som tilldelats användare i organisationen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Om du vill öppna administrationscentret för Exchange finns [i Administrationscenter för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Du behöver rollen Granskningsloggar eller granskningsloggar för endast granskning, som tilldelas rollgrupperna ComplianceManagement, OrganizationManagement (global admins) och SecurityAdministrator som standard. Mer information finns [i Behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd EAC ändra listan över medlemmar i rollgrupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns [i Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Har du problem? Be om hjälp i Forumet för [Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Använda EAC för att köra en administratörsrollgruppsrapport

Kör rapporten administratörsrollgrupp för att hitta ändringarna i hanteringsrollgrupper i organisationen inom en viss tidsram.

1. Gå till Granskning av **efterlevnadshantering** i EAC \> **Auditing**och välj sedan Kör **en administratörsrollgruppsrapport**.

2. Konfigurera följande inställningar på sidan **Sök efter ändringar i administratörsrollgrupper** som öppnas:

   - **Startdatum** och **slutdatum**: Ange ett datumintervall. Som standard söker rapporten efter ändringar som gjorts i administratörsrollgrupper under de senaste två veckorna.

   - **Välj rollgrupper**: Som standard genomsöks alla rollgrupper. Om du vill filtrera resultaten efter specifika rollgrupper klickar du på **Välj rollgrupper**. I dialogrutan som visas markerar du en rollgrupp och klickar på **Lägg till ->**. Upprepa det här steget så många gånger som behövs och klicka sedan på **OK** när du är klar.

3. När du är klar klickar du på **Sök**.

Om några ändringar hittas med hjälp av de angivna villkoren visas de i resultatfönstret. Klicka på en rollgrupp i sökresultaten om du vill se ändringarna i informationsfönstret.

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Om du har kört en rapport över administratörsrollgrupper visas rollgrupper som har ändrats inom datumintervallet i sökresultatfönstret. Om det inte finns några resultat har inga ändringar av rollgrupper skett inom det angivna datumintervallet. Om du tycker att det ska finnas resultat ändrar du datumintervallet och kör rapporten igen.

## <a name="monitor-changes-to-role-group-membership"></a>Övervaka ändringar i rollgruppsmedlemskap

När medlemmar läggs till eller tas bort från en rollgrupp anger sökresultaten i informationsfönstret att rollgruppens medlemskap har uppdaterats och de aktuella medlemmarna visas. Resultaten anger inte uttryckligen vilken användare som har lagts till eller tagits bort.

För att avgöra om en användare har lagts till eller tagits bort måste du jämföra två separata poster i rapporten. Låt oss till exempel titta på följande loggposter för **rollgruppen HelpDesk:**

> 2018-01-27 16:43 <br> Administratör <br> Uppdaterade medlemmar: Administratör;annb,florencef;pilarp <br> 2018-06-06 10:09 <br> Administratör <br> Uppdaterade medlemmar: Administratör;annb;florencef;pilarp;tonip <br> 2018-02-19 14:12 <br> Administratör <br> Uppdaterade medlemmar: Administratör;annb;florencef;tonip

I det här exemplet har administratörsanvändarkontot gjort följande ändringar:

- Den 2018-02-06 lade de till användarens tonip.

- Den 2018-02-19 tog de bort användarens pilarp.

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>Använd fristående Exchange Online PowerShell för att söka efter granskningsloggposter

Du kan använda Exchange Online PowerShell för att söka efter granskningsloggposter som uppfyller de kriterier du anger. En lista över sökvillkor finns i [Administratörsgranskningsloggning](https://technet.microsoft.com/library/22b17eb8-d8ee-4599-b202-d6a7928c20d9.aspx). Den här proceduren använder cmdleten **Search-AdminAuditLog** och visar sökresultat i Exchange Online PowerShell. Du kan använda den här cmdleten när du behöver returnera en uppsättning resultat som överskrider de gränser som definierats i cmdleten **New-AdminAuditLogSearch** eller i EAC Audit Reporting-rapporterna.

Om du vill söka i granskningsloggen efter villkor som du anger använder du följande syntax.

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> **Cmdlet search-adminAuditLog** returnerar som standard högst 1 000 loggposter. Använd parametern _ResultSize_ för att ange upp till 250 000 loggposter. Du kan också använda värdet `Unlimited` för att returnera alla transaktioner.

I det här exemplet söker du efter alla granskningsloggposter med följande villkor:

- **Startdatum**: 2018-08-04

- **Slutdatum**: 2018-10-03

- **Användar-ID:** Davids, Chrisd, Kima

- **Cmdlets**: **Set-Mailbox**

- **Parametrar**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

I det här exemplet söker du efter ändringar som gjorts i en viss postlåda. Detta är användbart om du felsöker eller om du behöver ange information för en undersökning. Följande kriterier används:

- **Startdatum**: 2018-05-01

- **Slutdatum**: 2018-10-03

- **Objekt-ID:** contoso.com/Users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

Om dina sökningar returnerar många loggposter rekommenderar vi att du använder proceduren i **Använd Exchange Online PowerShell för att söka efter granskningsloggposter och skicka resultat till en mottagare** senare i det här avsnittet. Proceduren i det avsnittet skickar en XML-fil som en e-postbilaga till de mottagare du anger, så att du lättare kan extrahera de data du är intresserad av.

Detaljerad syntax- och parameterinformation finns i [Sök-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-adminauditlog).

### <a name="view-details-of-audit-log-entries"></a>Visa information om granskningsloggposter

**Cmdlet search-adminAuditLog** returnerar de fält som beskrivs i avsnittet "Granskningslogginnehåll i [granskningsloggning](https://technet.microsoft.com/library/22b17eb8-d8ee-4599-b202-d6a7928c20d9.aspx)av administratörer . Av de fält som returneras av cmdlet, två fält, **CmdletParameters** och **ModifiedProperties**, innehåller ytterligare information som inte kan visas som standard.

Om du vill visa innehållet i fälten **CmdletParameters** och **ModifiedProperties** använder du följande steg. Du kan också använda proceduren i **Använda Exchange Online PowerShell för att söka efter granskningsloggposter och skicka resultat till en mottagare** senare i det här avsnittet för att skapa en XML-fil.

I den här proceduren används följande begrepp:

- [about_Arrays](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [about_Variables](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

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