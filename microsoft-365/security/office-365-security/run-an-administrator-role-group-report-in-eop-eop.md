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
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan ta reda på hur de kör rapporten om administratörsrollgrupper i fristående Exchange Online Protection (EOP). Den här rapporten loggar när en administratör lägger till medlemmar i eller tar bort medlemmar från administratörsrollgrupper.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d778e807a087a5e29b31645457d4a81bd05c5649
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288025"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>Köra en administratörsrapport för rollgrupp i fristående EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
-  [Exchange Online Protection fristående](exchange-online-protection-overview.md)

I fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor loggar tjänsten varje förekomst när en administratör lägger till medlemmar i eller tar bort medlemmar från administratörsrollgrupper. Mer information om rollgrupper i fristående EOP finns i [Behörigheter i fristående EOP.](feature-permissions-in-eop.md)

När du kör en rapport om administratörsrollgrupp i administrationscentret för Exchange (EAC) visas poster som sökresultat och omfattar de rollgrupper som påverkas, vem som ändrade medlemskap i rollgrupper och när och vilka medlemskapsuppdateringar som gjordes. Använd den här rapporten för att övervaka ändringar av administratörsbehörigheter som användare i organisationen har tilldelats.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Information om hur du öppnar administrationscentret för Exchange finns [i administrationscentret för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Du måste ha tilldelats behörigheter i Exchange Online Protection innan du kan utföra procedurerna i den här artikeln. Mer specifikt behöver du  **rollen** Granskningsloggar eller Visningsskyddade granskningsloggar som tilldelas rollgrupperna Organisationshantering, Efterlevnadshantering och **Säkerhetsadministratör** som standard.   Mer information finns i [Behörigheter i fristående EOP](feature-permissions-in-eop.md) [och Använda EAC för att ändra listan över medlemmar i rollgrupper.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Mer information om kortkommandon som kan gälla för procedurerna i den här artikeln finns i Kortkommandon för [administrationscentret för Exchange i Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Har du problem? Be om hjälp i [forumet för Exchange Online Protection.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Använda EAC för att köra rapporten över administratörsrollgrupper

Kör rapporten över administratörsrollgrupper för att hitta ändringarna i hanteringsrollgrupper inom ett visst tidsintervall.

1. Gå till granskning av efterlevnadshantering **i** EAC \> **och** välj sedan Kör **en administratörsrollgrupprapport.**

2. På sidan **Sök efter ändringar i administratörsrollgrupper** som öppnas konfigurerar du följande inställningar:

   - **Startdatum och** **slutdatum: Ange** ett datumintervall. Som standard söker rapporten efter ändringar gjorda i administratörsrollgrupper under de senaste två veckorna.

   - **Välj rollgrupper:** Som standard genomsöks alla rollgrupper. Om du vill filtrera resultatet efter specifika rollgrupper klickar du **på Välj rollgrupper.** Markera en rollgrupp i dialogrutan som visas och klicka på **lägg till ->.** Upprepa det här steget så många gånger det behövs och klicka sedan på **OK** när du är klar.

3. Klicka på Sök när du är **klar.**

Om några ändringar hittas med hjälp av villkoret du angav visas de i resultatfönstret. Klicka på en rollgrupp i sökresultatet för att se ändringarna i informationsfönstret.

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Om du har kört en rapport över administratörsrollgrupper visas rollgrupper som har ändrats inom datumintervallet i sökresultatet. Om det inte finns några resultat har inga ändringar av rollgrupper skett inom det angivna datumintervallet. Om du tror att det bör finnas resultat ändrar du datumintervallet och kör rapporten igen.

## <a name="monitor-changes-to-role-group-membership"></a>Övervaka ändringar av rollgruppsmedlemskap

När medlemmar läggs till i eller tas bort från en rollgrupp visar sökresultatet i informationsfönstret att rollgruppmedlemskapet har uppdaterats och de aktuella medlemmarna visas i en lista. Resultatet anger inte uttryckligen vilken användare som har lagts till eller tagits bort.

Om du vill avgöra om en användare har lagts till eller tagits bort måste du jämföra två separata poster i rapporten. Låt oss till exempel titta på följande loggposter för **rollgruppen HelpDesk:**

> 2018-01-27 16:43 <br> Administratör <br> Uppdaterade medlemmar: Administratör;annb,tack;pilarp <br> 2/06/2018 10:09 AM <br> Administratör <br> Uppdaterade medlemmar: Administratör;annb;tack;pilarp;tonip <br> 2018-02-19 14:12 <br> Administratör <br> Uppdaterade medlemmar: Administrator;annb;varf;tonip

I det här exemplet har administratörsanvändarkontot gjort följande ändringar:

- Den 2/6/2018 lade de till användaren tonip.
- Den 19 februari 2018 tog de bort användaren Pilarp.

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>Använda fristående Exchange Online PowerShell för att söka efter granskningsloggposter

Du kan använda Exchange Online PowerShell för att söka efter granskningsloggposter som uppfyller de villkor du anger. En lista med sökvillkor finns i [sökvillkoren Search-AdminAuditLog.](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet) Den här proceduren **använder cmdleten Search-AdminAuditLog** och visar sökresultat i Exchange Online PowerShell. Du kan använda den här cmdleten när du behöver returnera en uppsättning resultat som överskrider gränserna som definierats i cmdleten **New-AdminAuditLogSearch** eller i EAC-granskningsrapporteringsrapporterna.

Använd följande syntax om du vill söka i granskningsloggen efter villkor du anger.

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> Cmdleten **Search-AdminAuditLog** returnerar högst 1 000 loggposter som standard. Använd _parametern ResultSize_ till att ange upp till 250 000 loggposter. Du kan också använda värdet `Unlimited` för att returnera alla poster.

I det här exemplet utförs en sökning efter alla granskningsloggposter med följande villkor:

- **Startdatum:** 2018-08-04
- **Slutdatum:** 2018-10-03
- **Användar-IDs**: `davids` , `chrisd` , `kima`
- **Cmdlets:** **Set-Mailbox**
- **Parametrar:** _ProhibitSendQuota,_ _ProhibitSendReceiveQuota,_ _IssueWarningQuota,_ _MaxSendSize,_ _MaxReceiveSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

I det här exemplet genomsöks ändringar som gjorts i en viss postlåda. Det här är användbart om du felsöker eller behöver ange information för en undersökning. Följande villkor används:

- **Startdatum:** 2018-05-01
- **Slutdatum:** 2018-10-03
- **Objekt-ID:** contoso.com/Users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

Om dina sökningar returnerar många loggposter rekommenderar vi att du använder proceduren som anges i **Use Exchange Online PowerShell** för att söka efter granskningsloggposter och skicka resultat till en mottagare senare i den här artikeln. Proceduren i avsnittet skickar en XML-fil som en e-postbilaga till de mottagare du anger, så att det blir enklare att extrahera de data du är intresserad av.

Detaljerad information om syntax och parametrar finns [i Sök-AdminAuditLog.](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)

### <a name="view-details-of-audit-log-entries"></a>Visa information om granskningsloggposter

Cmdleten **Search-AdminAuditLog** returnerar fälten som beskrivs i [granskningsloggens innehåll.](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents) Av de fält som returneras av cmdleten innehåller två fält, **CmdletParameters** och **ModifiedProperties,** ytterligare information som inte kan visas som standard.

Gör så här om du vill visa innehållet i fälten **CmdletParameters** och **ModifiedProperties.** Du kan också använda proceduren i Använda **Exchange Online PowerShell** för att söka efter granskningsloggposter och skicka resultat till en mottagare senare i den här artikeln för att skapa en XML-fil.

I den här proceduren används följande begrepp:

- [about_Arrays](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [about_Variables](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. Bestäm vilka villkor du vill söka efter, kör cmdleten **Search-AdminAuditLog** och lagra resultaten i en variabel med följande kommando.

   ```PowerShell
   $Results = Search-AdminAuditLog <search criteria>
   ```

2. Varje granskningsloggpost lagras som ett matriselement i `$Results` variabeln. Du kan välja ett matriselement genom att ange dess index för matriselement. Matriselementindex börjar med noll (0) för det första matriselementet. Om du till exempel vill hämta det femte matriselementet, som har indexet 4, använder du följande kommando.

   ```PowerShell
   $Results[4]
   ```

3. Föregående kommando returnerar loggposten som lagrats i matriselement 4. Använd följande kommandon för att visa innehållet i fälten **CmdletParameters** och **ModifiedProperties** för den här loggposten.

   ```PowerShell
   $Results[4].CmdletParameters
   $Results[4].ModifiedProperties
   ```

4. Om du vill visa innehållet i **fälten CmdletParameters** eller **ModifiedParameters** i en annan loggpost ändrar du index för matriselement.
