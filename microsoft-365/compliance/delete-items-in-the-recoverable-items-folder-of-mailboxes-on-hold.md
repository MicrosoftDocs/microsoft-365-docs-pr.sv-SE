---
title: Ta bort objekt i mappen Återställningsbara objekt i en molnpostlåda som är på plats
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
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
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: Lär dig hur administratörer kan ta bort objekt i en användares Återställningsbara objekt-mapp för en Exchange Online postlåda, även om postlådan har satts i juridiskt betalningskrävs.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 776113bcd6141c4f01c2da61f0bd71f99cffd3e2
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326648"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold"></a>Ta bort objekt i mappen Återställningsbara objekt i molnbaserade postlådor som är på plats

Mappen Återställningsbara objekt för en e Exchange Online postlåda finns för att skydda från oavsiktlig eller skadlig borttagning. Den används också för att lagra objekt som behålls och används av efterlevnadsfunktioner, till exempel kvarhållna objekt och eDiscovery-sökningar. I vissa situationer kan dock organisationer ha data som oavsiktligt behålls i mappen för permanent borttagna objekt som de måste ta bort. En användare kanske till exempel oavsiktligt skickar eller vidarebefordrar ett e-postmeddelande som innehåller känslig information eller information som kan få allvarliga konsekvenser. Även om meddelandet tas bort permanent kan det behållas ett obestämt tidsdefinierat sätt eftersom ett juridiskt hastigt meddelande har placerats i postlådan. Det här scenariot *kallas för data* spill eftersom data oavsiktligt har *spillts* till Office 365. I de här situationerna kan du ta bort objekt i en användares Återställningsbara objekt-mapp för en Exchange Online-postlåda, även om postlådan är i enlighet med någon av de olika funktionerna för Office 365. Dessa typer av kvarhållning omfattar kvarhållning av juridiska skäl, In-Place kvarhållning av juridiska skäl, eDiscovery-kvarhållning och kvarhållningsprinciper som skapats i säkerhets- och efterlevnadscentret i Office 365 eller Microsoft 365.

I den här artikeln förklaras hur administratörer kan ta bort objekt från mappen återställningsbara objekt för molnbaserade postlådor som är på plats. Den här proceduren omfattar att inaktivera åtkomst till postlådan och inaktivera återställning av enstaka objekt, inaktivera assistenten för hanterade mappar från att bearbeta postlådan, tillfälligt ta bort rymmert, ta bort objekt från mappen återställningsbara objekt och sedan återställa postlådan till föregående konfiguration. Så här gör du:
  
[Steg 1: Samla in information om postlådan](#step-1-collect-information-about-the-mailbox)

[Steg 2: Förbereda postlådan](#step-2-prepare-the-mailbox)

[Steg 3: Ta bort alla spärrade e-postlådor från postlådan](#step-3-remove-all-holds-from-the-mailbox)

[Steg 4: Ta bort fördröjningen från postlådan](#step-4-remove-the-delay-hold-from-the-mailbox)

[Steg 5: Ta bort objekt i mappen för permanent borttagna objekt](#step-5-delete-items-in-the-recoverable-items-folder)

[Steg 6: Återställ postlådan till det tidigare tillståndet](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> Procedurerna som beskrivs i den här artikeln leder till att data tas bort permanent (rensas) från en Exchange Online postlåda. Det innebär att meddelanden som du tar bort från mappen för permanent borttagna objekt inte kan återställas och är inte tillgängliga för juridisk upptäckt eller andra efterlevnadssyften. Om du vill ta bort meddelanden från en postlåda som har satts på bevarande som en del av bevarande av juridiska skäl, In-Place-bevarande, eDiscovery-bevarande eller kvarhållningsprincip som skapats i säkerhets- och efterlevnadscentret, kontrollerar du med din arkiveringshantering eller juridiska avdelningar innan du tar bort bevarandet. Organisationen kan ha en princip som definierar om en postlåda som är väntad eller ett data spill har prioritet.
  
## <a name="before-you-delete-items"></a>Innan du tar bort objekt

- Om du vill skapa och köra en innehållssökning måste du vara medlem i rollgruppen eDiscovery Manager eller ha tilldelats hanteringsrollen för efterlevnadssökning. Om du vill ta bort meddelanden måste du vara medlem i rollgruppen Organisationshantering eller ha tilldelats hanteringsrollen för sökning och rensning. Mer information om hur du lägger till användare i en rollgrupp finns i [Tilldela eDiscovery-behörigheter i Säkerhets- och efterlevnadscenter](./assign-ediscovery-permissions.md).

- Proceduren som beskrivs i den här artikeln stöds inte för inaktiva postlådor. Det beror på att du inte kan tillämpa en bevarandeprincip (eller bevarandeprincip) på en inaktiv postlåda igen när du har tagit bort den. När du tar bort ett väntande objekt från en inaktiv postlåda ändras det till en normal, mjuk borttagna postlåda och tas bort permanent från organisationen när den har bearbetats av assistenten för hanterade mappar.

- Du kan inte utföra den här proceduren för en postlåda som har tilldelats bevarandeinställningar med en princip som är låst med hjälp av Bevarandelås. Det beror på att det här låset hindrar dig från att ta bort eller exkludera postlådan från principen och att inaktivera assistenten för hanterade mappar för postlådan. Mer information om hur du låser bevarandeprinciper finns i [Använda bevarandelås för att begränsa ändringar av bevarandeprinciper och bevarandeprinciper.](retention-preservation-lock.md)

- Om en postlåda inte har aktiverats för återställning (eller inte har aktiverats för återställning av enstaka objekt) kan du ta bort objekten från mappen återställningsbara objekt. Mer information om hur du gör detta finns i [Söka efter och ta bort e-postmeddelanden i organisationen.](./search-for-and-delete-messages-in-your-organization.md)
  
## <a name="step-1-collect-information-about-the-mailbox"></a>Steg 1: Samla in information om postlådan

Det första steget är att samla in valda egenskaper från målpostlådan som påverkar den här proceduren. Se till att skriva ned inställningarna eller spara dem i en textfil eftersom du kommer att ändra vissa av dessa egenskaper och sedan återgå till de ursprungliga värdena i steg 6, när du har tagit bort objekt från mappen återställningsbara objekt. Här är en lista över postlådeegenskaperna som du behöver samla in.
  
- *SingleItemRecoveryEnabled*  och  *RetainDeletedItemsFor*. Om det behövs inaktiverar du enskild återställning och ökar lagringstiden för borttagna objekt i steg 3.

- *LitigationHoldEnabled* och *InPlaceHolds.* Du måste identifiera alla som sätts i postlådan så att du tillfälligt kan ta bort dem i steg 3. I avsnittet [Mer information](#more-information) finns tips om hur du identifierar det typkparent som kan placeras i en postlåda.

Dessutom måste du hämta klientåtkomstinställningarna för postlådan så att du tillfälligt kan inaktivera dem så att ägaren (eller andra användare) inte kan komma åt postlådan under den här proceduren. Slutligen får du den aktuella storleken och antalet objekt i mappen Återställningsbara objekt. När du har tagit bort objekt i mappen återställningsbara objekt i steg 5 använder du den här informationen för att verifiera att objekten har tagits bort.
  
1. [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Se till att använda ett användarnamn och lösenord för ett administratörskonto som har tilldelats lämpliga hanteringsroller i Exchange Online.

2. Kör följande kommando för att få information om återställning av enstaka objekt och bevarandeperiod för borttagna objekt.

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   Om återställning av enstaka objekt är aktiverat måste du inaktivera den i steg 2. Om bevarandetiden för borttagna objekt inte är inställd på 30 dagar (maxvärdet i Exchange Online) kan du öka den i steg 2.

3. Kör följande kommando för att hämta postlådans åtkomstinställningar.

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   Du inaktiverar alla dessa åtkomstmetoder i steg 2.

4. Kör följande kommando för att få information om kvarhållnings- och bevarandeprinciper som tillämpas på postlådan.

    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```

    > [!TIP]
    > Om det finns för många värden i egenskapen  *InPlaceHolds*  och inte alla visas kan du köra kommandot för att visa  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` varje värde på en separat rad.
  
5. Kör följande kommando för att få information om bevarandeprinciper som gäller hela organisationen. 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```

   Om organisationen har bevarandeprinciper för hela organisationen måste du utesluta postlådan från de här principerna i steg 3. Det kan ta upp till 24 timmar innan ändringen replikeras.

    > [!TIP]
    > Om det finns för många värden i egenskapen  *InPlaceHolds*  och inte alla visas kan du köra kommandot för att visa  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` varje värde på en separat rad. 
  
6. Kör följande kommando för att avgöra om ett fördröjnings efterföljande kommando tillämpas på postlådan.

   ```powershell
   Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
   ```

   Om värdet för egenskapen *DelayHoldApplied* eller *DelayReleaseHoldApplied* är satt till **True** tillämpas ett fördröjnings hold-värde på postlådan och måste tas bort. Mer information om kvarhåller fördröjningar finns i [Steg 4: Ta bort fördröjning från postlådan.](#step-4-remove-the-delay-hold-from-the-mailbox)

   Om värdet för någon av egenskaperna är **Falskt** tillämpas inget fördröjningsvärde på postlådan och du kan hoppa över steg 4.

7. Kör följande kommando för att få aktuell storlek och totalt antal objekt i mappar och undermappar i mappen Återställningsbara objekt i användarens primära postlåda.

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Om användarens arkivpostlåda är aktiverad kör du följande kommando för att få storlek och totalt antal objekt i mappar och undermappar i mappen Återställningsbara objekt i arkivpostlådan. 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   När du tar bort objekt i steg 5 kan du välja att ta bort objekt i mappen Återställningsbara objekt i användarens primära arkivpostlåda. Om automatisk expandering av arkivering är aktiverat för postlådan tas inte objekt i en arkivpostlåda med delad verksamhet bort.
  
## <a name="step-2-prepare-the-mailbox"></a>Steg 2: Förbereda postlådan

När du har samlat in och sparat information om postlådan är nästa steg att förbereda postlådan genom att utföra följande uppgifter:
  
- **Inaktivera klientåtkomst till postlådan** så att postlådans ägare inte kan komma åt postlådan och ändra postlådedata i den här proceduren.

- **Öka** lagringstiden för borttagna objekt till 30 dagar (maxvärdet i Exchange Online) så att objekt inte rensas från mappen Återställningsbara objekt innan du kan ta bort dem i steg 5.

- **Inaktivera återställning av** enstaka objekt så att objekten inte bevaras (under hela bevarandetiden för borttagna objekt) när du har tagit bort dem från mappen Återställningsbara objekt i steg 5.

- **Inaktivera assistenten för hanterade** mappar så att den inte bearbetar postlådan och behåller de objekt som du tar bort i steg 5.

Utför följande steg i Exchange Online PowerShell.
  
1. Kör följande kommando för att inaktivera all klientåtkomst till postlådan. Kommandosyntaxen förutsätter att alla klientåtkomstmetoder har aktiverats i postlådan.

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

    > [!NOTE]
    > Det kan ta upp till 60 minuter att inaktivera alla klientåtkomstmetoder till postlådan. Observera att om du inaktiverar de här åtkomstmetoderna kopplas inte postlådans ägare bort om de är inloggade. Om ägaren inte är inloggad kan han eller hon inte komma åt postlådan när de här åtkomstmetoderna har inaktiverats.
  
2. Kör följande kommando för att öka lagringstiden för borttagna objekt som högst 30 dagar. Detta förutsätter att den aktuella inställningen är mindre än 30 dagar.

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. Kör följande kommando för att inaktivera återställning av enstaka objekt.

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

    > [!NOTE]
    > Det kan ta upp till 60 minuter att inaktivera återställning av enstaka objekt. Ta inte bort objekt i mappen återställningsbara objekt förrän den här perioden har gått ut. 
  
4. Kör följande kommando för att förhindra assistenten för hanterade mappar från att bearbeta postlådan. Som tidigare förklarats kan du inaktivera assistenten för hanterade mappar endast om en bevarandeprincip med ett bevarandelås inte tillämpas på postlådan. 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>Steg 3: Ta bort alla spärrade e-postlådor från postlådan

Det sista steget innan du kan ta bort objekt från mappen för permanent borttagna objekt är att ta bort alla spärrade objekt (som du identifierade i steg 1) som placerats i postlådan. Alla spärrade objekt måste tas bort för att objekten inte ska behållas efter att du har tagit bort dem från mappen för permanent borttagna objekt. Följande avsnitt innehåller information om hur du tar bort olika typer av innehåll i en postlåda. I avsnittet [Mer information](#more-information) finns tips om hur du identifierar det typkparent som kan placeras i en postlåda. Mer information finns i Identifiera [typen av väntande objekt som placerats i en Exchange Online postlåda.](identify-a-hold-on-an-exchange-online-mailbox.md)
  
> [!CAUTION]
> Som tidigare beskrivits bör du kontrollera med din hantering av arkivhandlingar eller juridiska avdelningar innan du tar bort ett arkivhandlingar från en postlåda. 
  
### <a name="litigation-hold"></a>Bevarande av juridiska skäl
  
Kör följande kommando i Exchange Online PowerShell för att ta bort bevarande av juridiska skäl från postlådan.

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

> [!NOTE]
> På liknande sätt som du inaktiverar klientåtkomstmetoder och återställning av enstaka objekt kan det ta upp till 60 minuter att ta bort bevarande av juridiska skäl. Ta inte bort objekt från mappen återställningsbara objekt förrän den här perioden har gått ut. 
  
### <a name="in-place-hold"></a>In-Place på
  
Kör följande kommando i Exchange Online PowerShell för att identifiera det In-Place som finns i postlådan. Använd GUID för det In-Place som du identifierade i steg 1.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

När du har identifierat In-Place kan du använda administrationscentret för Exchange (EAC) eller Exchange Online PowerShell för att ta bort postlådan från servern. Mer information finns i Skapa [eller ta bort en In-Place .](/exchange/security-and-compliance/create-or-remove-in-place-holds)
  
### <a name="retention-policies-applied-to-specific-mailboxes"></a>Bevarandeprinciper som tillämpas på specifika postlådor
  
Kör följande kommando i [Säkerhets- & Säkerhets- och efterlevnadscenter PowerShell](/powershell/exchange/exchange-online-powershell) för att identifiera den bevarandeprincip som tillämpas på postlådan. Det här kommandot returnerar även eventuella Teams konversationsbevarandeprinciper som tillämpats på en postlåda. Använd GUID (utan prefixet) för `mbx` `skp` den bevarandeprincip du identifierade i steg 1.

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

När du har identifierat bevarandeprincipen går du till sidan Bevarande av **informationsstyrning** i Säkerhets- och efterlevnadscenter för &, redigerar den bevarandeprincip som du identifierade i föregående steg och tar bort postlådan från listan över mottagare som ingår i bevarandeprincipen.  >  
  
### <a name="organization-wide-retention-policies"></a>Bevarandeprinciper för hela organisationen
  
Bevarandeprinciper som Exchange hela organisationen Teams hela organisationen tillämpas på alla postlådor i organisationen. De tillämpas på organisationsnivå (inte postlådenivå) och returneras när du kör cmdlet **get-OrganizationConfig** i steg 1. Kör följande kommando i [Säkerhets- & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell) för att identifiera bevarandeprinciper som gäller hela organisationen. Använd GUID (inte inklusive  `mbx` prefixet) för de organisationsomfattande kvarhållningsprinciper som du identifierade i steg 1.

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

När du har identifierat bevarandeprinciperna för hela organisationen går du till sidan Bevarande av informationsstyrning i Säkerhets- och efterlevnadscenter för &, redigerar varje organisationsomfattande bevarandeprincip som du identifierade i föregående steg och lägger till postlådan i listan med uteslutna  >   mottagare. Om du gör det här tas användarens postlåda bort från bevarandeprincipen. Det kan ta upp till 24 timmar innan ändringen replikeras.

### <a name="retention-labels"></a>Kvarhållningsetiketter

När en användare använder en etikett som har konfigurerats för att behålla innehåll eller behålla och sedan ta bort innehåll för en mapp eller ett objekt i postlådan sätts egenskapen *ComplianceTagHoldApplied-postlåda* till **True.** När detta inträffar anses postlådan vara bevarande, som om den hade satts på bevarande av juridiska skäl eller har tilldelats en bevarandeprincip.

Om du vill visa värdet för *egenskapen ComplianceTagHoldApplied* kör du följande kommando i Exchange Online PowerShell:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

När du har identifierat att en postlåda är på bevarande eftersom en bevarandeetikett tillämpas på en mapp eller ett objekt kan du använda verktyget Innehållssökning i säkerhets- och efterlevnadscentret för att söka efter etiketterade objekt med hjälp av sökvillkoret ComplianceTag. Mer information finns i avsnittet "Sökvillkor" i [Nyckelordsfrågor och sökvillkor för innehållssökning.](keyword-queries-and-search-conditions.md#conditions-for-common-properties)

Mer information om etiketter finns i Läs [mer om bevarandeprinciper och bevarandeetiketter.](retention.md)

### <a name="ediscovery-holds"></a>eDiscovery-undantag
  
Kör följande kommandon i [Säkerhets- & Efterlevnadscenter PowerShell](/powershell/exchange/connect-to-scc-powershell) för att identifiera det ärende som är kopplat till ett eDiscovery-ärende (kallas *eDiscovery-fodral)* som tillämpas på postlådan. Använd GUID (utan  `UniH` prefixet) för det eDiscovery-håll du identifierade i steg 1. Det andra kommandot visar namnet på det eDiscovery-fall som fältet är kopplat till. Det tredje kommandot visar namnet på meddelandet.
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

När du har identifierat namnet på eDiscovery-ärendet och ärendet går du till sidan **eDiscovery** \> **eDiscovery** i efterlevnadscentret, öppnar ärendet och tar bort postlådan från servern. Mer information om hur du identifierar eDiscovery-innehåll finns i avsnittet "eDiscovery-innehåll" i Identifiera typen av spärrade eDiscovery-innehåll som [Exchange Online postlåda.](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>Steg 4: Ta bort fördröjningen från postlådan

När någon typ av kvarhållning tas bort från en postlåda sätts värdet för postlådeegenskapen *DelayHoldApplied* eller *DelayReleaseHoldApplied* till **True.** Detta inträffar nästa gång assistenten för hanterade mappar bearbetar postlådan och upptäcker att ett väntande objekt har tagits bort. Det här kallas för *väntande* arbete och innebär att den faktiska borttagningen av väntande åtgärder fördröjs i 30 dagar för att förhindra att data tas bort permanent från postlådan. (Syftet med ett väntande tillfälle är att ge administratörer möjlighet att söka efter eller återställa postlådeobjekt som kommer att tas bort när ett väntande objekt tas bort.)  När ett bevarande av en fördröjning sätts på postlådan anses postlådan fortfarande vara satt på bevarande under en obegränsad tid, som om postlådan var bevarande av juridiska skäl. Efter 30 dagar går undantaget ut och Microsoft 365 försöker automatiskt ta bort undantaget (genom att sätta egenskapen *DelayHoldApplied* eller *DelayReleaseHoldApplied* till **False**) så att undantaget tas bort. Mer information om ett väntande väntande finns i avsnittet "Hantera postlådor som är väntande" i Hur du identifierar typen av väntande på [en Exchange Online postlåda.](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)

Om värdet för egenskapen *DelayHoldApplied* eller *DelayReleaseHoldApplied* är inställd på **Sant** kör du något av följande kommandon för att ta bort fördröjningen:

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

Eller

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Du måste ha tilldelats rollen Juridiskt betalningskällvärde i Exchange Online använda parametern *RemoveDelayHoldApplied* eller *RemoveDelayReleaseHoldApplied.*

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>Steg 5: Ta bort objekt i mappen för permanent borttagna objekt

Nu är du redo att ta bort objekt i mappen återställningsbara objekt med hjälp av cmdletarna [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) och [New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) i Security & Compliance Center PowerShell.

Om du vill söka efter objekt som finns i mappen för återställningsbara objekt rekommenderar vi att du utför en *riktad samling*. Det innebär att du bara begränsar sökningen till objekt som finns i mappen återställningsbara objekt. Det kan du göra genom att köra skriptet i [artikeln Använd innehållssökning för riktade samlingar.](use-content-search-for-targeted-collections.md) Det här skriptet returnerar värdet för egenskapen mapp-ID för alla undermappar i målmappen återställningsbara objekt. Sedan använder du mapp-ID:t i en sökfråga för att returnera objekt som finns i den mappen.

Här är en översikt över processen för att söka efter och ta bort objekt i en användares Återställningsbara objekt-mapp:

1. Kör skriptet för den riktade samlingen som returnerar mapp-ID:erna för alla mappar i målanvändarens postlåda. Skriptet ansluter till Exchange Online PowerShell och säkerhets- & Compliance PowerShell i samma PowerShell-session. Mer information finns i [Köra skriptet för att få en lista över mappar för en postlåda.](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site)

2. Kopiera mapp-ID:erna för alla undermappar i mappen Återställningsbara objekt. Alternativt kan du omdirigera utdata från skriptet till en textfil.

   Här är en lista och beskrivning av undermapparna i mappen Återställningsbara objekt som du kan söka efter och ta bort objekt från:

   - **Borttagningar:** Innehåller mjukt borttagna objekt vars bevarandeperiod för borttagna objekt inte har förfallit. Användare kan återställa mjukt borttagna objekt från den här undermappen med hjälp av verktyget Återställ borttagna objekt i Outlook.

   - **Rensningar:** Innehåller permanent borttagna objekt vars bevarandeperiod för borttagna objekt har förfallit. Användare kan också ta bort objekt permanent genom att tömma mappen Återställningsbara objekt. Om postlådan är i holdt behålls permanent borttagna objekt. Den här undermappen visas inte för slutanvändare.

   - **DiscoveryHolds:** Innehåller permanent borttagna objekt som har bevarats genom en eDiscovery-bevarande eller en bevarandeprincip. Den här undermappen visas inte för slutanvändare.

   - **Fästen:** Innehåller permanent borttagna objekt från Teams och andra molnbaserade appar som har bevarats genom en bevarandeprincip eller annan typ av bevarande. Den här undermappen visas inte för slutanvändare.

3. Använd **cmdleten New-ComplianceSearch** (i Security & Compliance Center PowerShell) eller använd verktyget innehållssökning i efterlevnadscentret för att skapa en innehållssökning som returnerar objekt från målanvändarens Återställningsbara objekt-mapp. Det kan du göra genom att inkludera FolderId i sökfrågan för alla undermappar som du vill söka i. Följande fråga returnerar till exempel alla meddelanden i undermapparna Rensningar och eDiscoveryHolds:

   ```text
   folderid:<folder ID of Purges subfolder> OR folderid:<folder ID of DiscoveryHolds subfolder>
   ```

   Mer information och exempel om hur du kör innehållssökningar som använder egenskapen mapp-ID finns i Använda ett [mapp-ID eller för att utföra en riktad samling](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection).

   > [!NOTE]
   > Om du använder cmdleten **New-ComplianceSearch** för att söka i mappen Återställningsbara objekt ska du köra sökningen med cmdleten **Start-ComplianceSearch.**

4. När du har skapat en innehållssökning och verifierat att den returnerar objekten som du vill ta bort använder du kommandot `New-ComplianceSearchAction -Purge -PurgeType HardDelete` (i Security & Compliance Center PowerShell) för att permanent ta bort de objekt som returnerades av innehållssökningen som du skapade i föregående steg. Du kan till exempel köra ett kommando som liknar följande kommando:

   ```powershell
   New-ComplianceSearchAction -SearchName "RecoverableItems" -Purge -PurgeType HardDelete
   ```

5. Maximalt 10 objekt per postlåda tas bort när du kör föregående kommando. Det innebär att du kanske måste köra kommandot flera gånger för att ta bort alla objekt som du vill ta bort `New-ComplianceSearchAction -Purge` i mappen för permanent borttagna objekt. Om du vill ta bort ytterligare objekt måste du först ta bort åtgärden för tidigare efterlevnadssökning. Det gör du genom att köra `Remove-ComplianceSearchAction` cmdleten. Om du till exempel vill ta bort den rensningsåtgärd som körts i föregående steg kör du följande kommando:

   ```powershell
   Remove-ComplianceSearchAction "RecoverableItems_Purge"
   ```

   När du har gjort det kan du skapa en ny sökåtgärd för efterlevnadsrensning för att ta bort fler objekt. Du måste ta bort alla åtgärder innan du skapar en ny.

   Om du vill visa en lista över efterlevnadssökningsåtgärderna kan du köra `Get-ComplianceSearchAction` cmdleten. Rensningsåtgärder identifieras med `_Purge` ett tillägg i söknamnet.

### <a name="verify-that-items-were-deleted"></a>Kontrollera att objekten har tagits bort

Om du vill kontrollera att du har tagit bort objekt från mappen Återställningsbara objekt i en postlåda använder du cmdleten **Get-MailboxFolderStatistics** i Exchange Online PowerShell för att kontrollera storlek och antal objekt i mappen för permanent borttagna objekt. Du kan jämföra den här statistiken med den statistik du hämtade i steg 1.
  
Kör följande kommando för att få aktuell storlek och totalt antal objekt i mappar och undermappar i mappen Återställningsbara objekt i användarens primära postlåda.
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

Kör följande kommando för att få storlek och totalt antal objekt i mappar och undermappar i mappen Återställningsbara objekt i användarens arkivpostlåda.

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>Steg 6: Återställ postlådan till det tidigare tillståndet

Det sista steget är att återställa postlådan till föregående konfiguration. Det innebär att du återställer egenskaperna som du ändrade i steg 2 och återapplicering av de håll som du tog bort i steg 3. Detta omfattar följande:
  
- Ändra tillbaka det borttagna objektets bevarandeperiod till det tidigare värdet. Du kan också bara låta den här uppsättningen vara 30 dagar, det högsta värdet i Exchange Online.

- Återaktivera återställning av enstaka objekt.

- Aktivera klientåtkomstmetoderna så att ägaren kan komma åt postlådan.

- Tillämpa bevarandeprinciper och bevarandeprinciper som du har tagit bort på nytt.

- Aktivera assistenten för hanterade mappar för att bearbeta postlådan.

> [!IMPORTANT]
> Vi rekommenderar att du väntar 24 timmar efter att du har tillämpat en bevarande- eller bevarandeprincip på nytt (och verifierat att den är på plats) innan du aktiverar assistenten för hanterade mappar för att bearbeta postlådan på nytt.
  
Utför följande steg (i den angivna sekvensen) i Exchange Online PowerShell.
  
1. Kör följande kommando för att ändra tillbaka bevarandetiden för borttagna objekt till dess ursprungliga värde. Det här förutsätter att den föregående inställningen är mindre än 30 dagar. till exempel 14 dagar.

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. Kör följande kommando för att återaktivera återställning av enstaka objekt.

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. Kör följande kommando för att återaktivera alla klientåtkomstmetoder till postlådan.

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. Tillämpa på nytt det som du har tagit bort i steg 3. Gör något av följande beroende på typen av kvart.

    **Bevarande av juridiska skäl**

    Kör följande kommando för att återaktivera bevarande av juridiska skäl för postlådan.

    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **Håll på plats**

    Använd EAC (eller Exchange Online PowerShell) för att lägga till postlådan i In-Place postlådan.

    **Bevarandeprinciper som tillämpas på specifika postlådor**

    Använd Säkerhets- & efterlevnadscenter för att lägga till postlådan i bevarandeprincipen igen. Gå till sidan Bevarande av **informationsstyrning** i & Säkerhets- och efterlevnadscenter, redigera bevarandeprincipen och lägg till postlådan i listan över mottagare som bevarandeprincipen tillämpas  >   på.

    **Bevarandeprinciper för hela organisationen**

    Om du har tagit bort en bevarandeprincip för hela organisationen Exchange hela organisationen genom att utesluta den från principen använder du Säkerhets- och efterlevnadscenter för & för att ta bort postlådan från listan med uteslutna användare. Gå till sidan Bevarande av **informationsstyrning** i & Säkerhets- och efterlevnadscenter, redigera den organisationsomfattande bevarandeprincipen och ta bort postlådan från listan med  >   uteslutna mottagare. Om du gör det här återanvändas bevarandeprincipen i användarens postlåda.

    **eDiscovery-ärende som sätts i kvar**

    Använd Säkerhets- & efterlevnadscenter för att lägga till postlådan i det ärende som är kopplat till ett eDiscovery-ärende. Gå till sidan **eDiscovery**  >  **eDiscovery,** öppna ärendet och lägg till postlådan i väntande tid. 

5. Kör följande kommando för att låta assistenten för hanterade mappar bearbeta postlådan igen. Som tidigare nämnts rekommenderar vi att du väntar 24 timmar efter att du har tillämpat en princip för bevarande eller bevarande igen (och verifierat att den är på plats) innan du aktiverar assistenten för hanterade mappar igen.

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. Kontrollera att postlådan har återställts till den tidigare konfigurationen genom att köra följande kommandon och sedan jämföra inställningarna med de inställningar som du hämtade i steg 1.

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a>Mer information

Här är en tabell som beskriver hur du identifierar olika typer av originalvärden baserat på värdena i egenskapen *InPlaceHolds* när du kör cmdlet:arna **Get-Mailbox** eller **Get-OrganizationConfig.** Mer detaljerad information finns i Identifiera [typen av väntande objekt som placerats i en Exchange Online postlåda.](identify-a-hold-on-an-exchange-online-mailbox.md)

Som tidigare förklarats måste du ta bort alla bevarande- och bevarandeprinciper från en postlåda innan du kan ta bort objekt i mappen för permanent borttagna objekt.
  
| Typ av håll | Exempelvärde | Så här identifierar du väntande tid |
|:-----|:-----|:-----|
|Bevarande av juridiska skäl  <br/> | `True` <br/> |Egenskapen  *LitigationHoldEnabled*  är inställd på  `True` .  <br/> |
|In-Place på  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |Egenskapen  *InPlaceHolds*  innehåller GUID för det In-Place håll som finns i postlådan. Det här är ett bra In-Place eftersom GUID inte börjar med ett prefix.  <br/> Du kan använda kommandot i Exchange Online PowerShell för att få information om `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` In-Place på postlådan.  <br/> |
| Bevarandeprinciper i säkerhets- & säkerhets- och efterlevnadscenter som tillämpas på specifika postlådor  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> eller  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |När du kör **cmdlet:en Get-Mailbox** innehåller egenskapen  *InPlaceHolds*  även GUID:er för bevarandeprinciper som tillämpas på postlådan. Du kan identifiera bevarandeprinciper eftersom GUID börjar med  `mbx` prefixet. Om GUID för kvarhållningsprincipen börjar med prefixet, som anger att bevarandeprincipen tillämpas på alla `skp` Skype för företag konversationer.  <br/> Om du vill identiteten för den bevarandeprincip som tillämpas på postlådan kör du följande kommando i Security & Compliance Center PowerShell: <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Se till att ta bort  `mbx`  `skp` prefixet eller när du kör det här kommandot.  <br/> |
|Bevarandeprinciper för hela organisationen i Säkerhets- & Säkerhets- och efterlevnadscenter  <br/> |Inget värde  <br/> eller  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696` (anger att postlådan är undantagen från en princip som gäller för hela organisationen)  <br/> |Även om egenskapen  *InPlaceHolds*  är tom när du kör cmdleten **Get-Mailbox** kan det fortfarande finnas en eller flera bevarandeprinciper för hela organisationen som tillämpas på postlådan.  <br/> Du kan verifiera detta genom att köra kommandot i Exchange Online PowerShell för att få en lista med `Get-OrganizationConfig | FL InPlaceHolds` GUID:er för bevarandeprinciper för hela organisationen. Det GUID för organisationsomfattande bevarandeprinciper som tillämpas Exchange postlådor börjar med `mbx` prefixet, till exempel `mbxa3056bb15562480fadb46ce523ff7b02` .  <br/> Om du vill identiteten för den organisationsomfattande bevarandeprincip som tillämpas på postlådan kör du följande kommando i Security & Compliance Center PowerShell: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Om en postlåda är undantagen från en organisationsomfattande bevarandeprincip visas GUID för bevarandeprincipen i egenskapen  *InPlaceHolds*  för användarens postlåda när du kör cmdleten **Get-Mailbox.** identifieras det med prefixet  `-mbx` – till exempel  `-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|eDiscovery case hold in the Security & Compliance Center  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |Egenskapen  *InPlaceHolds*  innehåller också GUID för alla håll som är kopplade till ett eDiscovery-ärende i säkerhets- och &-efterlevnadscentret som kan placeras i postlådan. Du ser att detta är ett eDiscovery-ärende som kan innehållas eftersom GUID börjar med  `UniH` prefixet.  <br/> Du kan använda cmdleten i Security & Compliance Center PowerShell för att få information om eDiscovery-ärendet som är kopplat till ärendet för  `Get-CaseHoldPolicy` postlådan. Du kan till exempel köra kommandot för att visa namnet på det ärende som finns  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` i postlådan. Se till att ta bort  `UniH` prefixet när du kör det här kommandot.  <br/><br/> Kör följande kommandon för att identitetsidentifiera eDiscovery-ärendet som är kopplat till eDiscovery-ärendet för postlådan:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`
