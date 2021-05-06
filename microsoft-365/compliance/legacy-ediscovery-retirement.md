---
title: Utfasning av äldre eDiscovery-verktyg
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: In-Place eDiscovery och In-Place Hold (och motsvarande PowerShell-cmdlets) i Exchange Online kommer att dras tillbaka under de första halvan av 2020. Både Search-Mailbox och Advanced eDiscovery v1.0 dras tillbaka inom samma tidsperiod.
ms.openlocfilehash: 48a20b9e73c5379325afb715a86c4945385fd0b9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161851"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>Utfasning av äldre eDiscovery-verktyg

> [!IMPORTANT]
> Microsoft har utvärderat situationen för allmän hälsa och vi förstår vilken inverkan det har på våra kunder. Vi vill vara starka partner och ansvariga globala människor. För att underlätta dina många kostnader kommer vi att fördröja den schemalagda tillbakatagandet av de äldre eDiscovery-verktygen som beskrivs i den här artikeln med tre månader. **De uppdaterade slutdatumen visas nedan.**

Under åren har Microsoft tillhandahållit eDiscovery-verktyg som gör att du kan söka, förhandsgranska och exportera e-postinnehåll från Exchange Online. Dessa verktyg är dock inte längre ett effektivt sätt att söka efter innehåll som inte är Exchange i andra Microsoft 365-tjänster, till exempel SharePoint Online och Microsoft 365 Grupper. Microsoft erbjuder andra eDiscovery-verktyg som hjälper dig att söka efter en mängd olika eDiscovery-Microsoft 365 innehåll. Och vi har arbetat hårt med att införliva de mest aktuella och kraftfulla eDiscovery-funktionerna i [Microsoft 365 efterlevnadscenter.](https://compliance.microsoft.com) På så sätt kan organisationer svara på juridiska, interna och andra dokumentförfrågningar om innehåll i många Microsoft 365 tjänster, inklusive Exchange Online.

Som ett resultat av den här nya och förbättrade eDiscovery-funktionen i efterlevnadscentret för Microsoft 365 tar vi bort följande eDiscovery-relaterade funktioner för sökning efter e-postinnehåll i Exchange Online och Microsoft 365:

- [Lokal eDiscovery](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) [och på plats](/exchange/security-and-compliance/create-or-remove-in-place-holds) i administrationscentret Exchange på plats.

- De Exchange Online PowerShell-cmdlets som stöder In-Place eDiscovery och In-Place Holds (dessa cmdlets identifieras tillsammans som **-MailboxSearch* cmdlets). Det inkluderar följande cmdlets:

  - [Ny postlådesökning](/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](/powershell/module/exchange/stop-mailboxsearch)

  - [Set-MailboxSearch](/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > Cmdletarna [Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch) och [Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) blir tillgängliga när de andra cmdletarna ****-MailboxSearch*** har dragits tillbaka så att du kan använda dem för att hjälpa dig med övergången till andra verktyg för eDiscovery och eDiscovery-sökning. Men efter ett visst datum (som anges nedan) kommer Microsoft Support inte längre att stödja dessa två cmdlets.

- [Cmdlet:en Search-Mailbox](/powershell/module/exchange/search-mailbox) i Exchange Online PowerShell.

- Följande åtgärder i API:t Exchange Webbtjänster:

   - [GetSearchableMailboxes](/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 Advanced eDiscovery v1.0](./overview-ediscovery-20.md), som är den första versionen av Advanced eDiscovery som nås via ett Core eDiscovery-ärende i Office 365 Security & Compliance Center. Att vi tar Advanced eDiscovery v1.0 påverkar inte din möjlighet att skapa och hantera Core eDiscovery-ärenden.

> [!NOTE]
> Den eDiscovery-funktionalitet som dras tillbaka gäller endast molnbaserade versioner av Microsoft 365 och Office 365. eDiscovery-funktioner i lokala versioner Exchange och SharePoint kommer att få stöd tills vidare.

I följande avsnitt i den här artikeln får du vägledning om varje funktion som ska dras tillbaka. Den här informationen innehåller tidslinjer och alternativa verktyg som du kan använda i stället för det indragna verktyget.

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>In-Place eDiscovery och In-Place i administrationscentret Exchange eDiscovery 

Efter det ursprungliga meddelandet den 1 juli 2017 kommer funktionen In-Place för eDiscovery & i administrationscentret för Exchange (EAC) att tas bort. På In-Place eDiscovery & innehåll i EAC kunde du söka, spärra och exportera innehåll från Exchange Online. In-Place med eDiscovery kan du också kopiera sökresultat till en identifieringspostlåda så att du eller andra eDiscovery-hanterare kan granska innehåll och göra det tillgängligt för juridiska begäranden, reglerande och offentliga förfrågningar.

Eftersom alla dessa funktioner (förutom att kopiera sökresultat till en identifieringspostlåda) nu finns tillgängliga i innehållssökningen, eDiscovery- och Advanced eDiscovery-verktygen i [efterlevnadscentret](./microsoft-365-compliance-center.md) för Microsoft 365 (med förbättrad funktionalitet, tillförlitlighet och stöd för ett brett utbud av Microsoft 365-tjänster) rekommenderar vi att du börjar använda dessa verktyg så snart som möjligt. I tabellen nedan finns en lista över de verktyg du kan använda i stället för In-Place eDiscovery och In-Place Hold.

### <a name="scope-of-affected-organizations"></a>Omfattningen av berörda organisationer

- Office 365 och Microsoft 365 Enterprise organisationer

- Office 365 och Microsoft 365 Education organisationer

- Office 365 och Microsoft 365 myndigheter. Det omfattar GCC, GCC Hög och DoD

- Office 365 Tyskland

### <a name="timeline-for-retirement"></a>Tidslinje för att gå i retirement

- 1 juli 2020: Du kan inte skapa nya sökningar och innehåller, men du kan fortfarande köra, redigera och ta bort befintliga sökningar på egen risk. Microsoft Support kommer inte längre att In-Place eDiscovery-& i EAC.

- 1 oktober 2020: In-Place eDiscovery & Funktioner för kvarhåller i EAC placeras i skrivskyddsläge. Det innebär att du bara kan ta bort befintliga sökningar och rymmer.

### <a name="alternative-tools"></a>Alternativa verktyg

I följande tabell beskrivs andra verktyg som du kan använda för att ersätta de befintliga funktioner som dras tillbaka.

<table>
<thead>
<tr class="header">
<th>Funktioner</th>
<th>Alternativt verktyg</th>
<th>Kommentarer</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Sök, exportera och håll i juridiska syften</td>
<td>Core eDiscovery-ärenden i Microsoft 365 efterlevnadscenter </td>
<td><p>Användning av funktionerna i grundläggande eDiscovery-ärenden ger funktionell paritet för eDiscovery In-Place och eDiscovery In-Place holds. Det inkluderar följande:</p>
<ul>
<li>
<p>Sökskalor till miljontals platser</p>
</li>
<li>
<p>Högre tillförlitlighet när du söker efter, exporterar och placerar innehåll i isat innehåll</p>
</li>
<li>
<p>Söka efter innehåll i Exchange Online, SharePoint Online, OneDrive för företag, Skype för företag, Microsoft Teams, Yammer Grupper, Microsoft 365 Grupper och annat innehåll som lagrats i Office 365-program</p></li></ul>
</td>
</tr>
<tr class="even">
<td>Bevarande för bevarandeändamål</td>
<td>Bevarandeprinciper i Microsoft 365 efterlevnadscenter</td>
<td><p>Du kan använda bevarandeprinciper för att behålla innehåll och, om du vill, ta bort det efter att bevarandetiden gått ut. Andra funktioner är:</p>
<ul>
<li>
<p>Tillämpa principer på hela organisationen </p>
</li><li>
<p>Tillämpa principer på specifika innehållsplatser som Exchange Online, SharePoint Online, OneDrive för företag, Skype för företag, Microsoft Teams och Office 365 Grupper</p></li>
<li>
<p>Tillämpa principer på specifika användare</p></li></ul>
<p>Mer information finns i Läs <a href="/microsoft-365/compliance/retention-policies">mer om bevarandeprinciper och bevarandeetiketter.</a></td>
</tr>
<tr class="odd">
<td>Kopiera e-postsökresultat till en identifieringspostlåda för granskning</td><td>Granska uppsättningar Advanced eDiscovery v2.0</td>
<td><p>Det har aldrig Microsoft 365 enklare att granska innehåll i en 2010-webbplats. Granskningsuppsättningar har många bra funktioner för att minska tiden och de data som behövs för att granska, inklusive:</p>
<ul>
<li><p>Utför snabba sökfrågor och filtrera innehåll i en granskningsuppsättning</p></li>
<li><p>Analysera innehåll i en uppsättning med granskning; Det här inkluderar e-posttrådning, identifiering av nästan dubbletter, teman-analys och predictive-kodning</p></li>
<li><p>Tagga dokument i en granskningsuppsättning</p></li>
<li><p>Tagga förslag för att identifiera innehåll för juristklientbehörighet</p></li></ul>
<p>Mer information finns i <a href="/microsoft-365/compliance/overview-ediscovery-20">Översikt över Advanced eDiscovery lösning i Microsoft 365</a>.</p>
<p>
<p>Du kan också exportera sökresultatet till PST-filer och sedan använda Microsoft 365-importtjänsten för att importera PST-filerna till en identifieringspostlåda. Stegvisa instruktioner finns i Använda nätverksuppladdning <a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">för att importera PST-filer till Office 365.</a>
</tr>
<tr class=even>
  <td>Kopiera meddelanden från en postlåda till en annan postlåda</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Tilldela behörigheter till en postlåda</a></td>
  <td>Om du vill ge en person åtkomst till en annan användares e-post (t.ex. när en anställd lämnar organisationen och du behöver ge en annan person åtkomst till den före detta anställdas e-post) rekommenderar vi att du tilldelar den personen behörighet för att komma åt den tidigare anställdas postlåda. I stället för att kopiera postlådeobjekt till en annan användarpostlåda eller en delad postlåda behöver du bara tilldela en användare behörighet att komma åt källpostlådan.</td>
  
  </tr>
<tr class="odd">
<td>Återställa objekt från mappen återställningsbara objekt</td>
  <td><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>Du kan återställa permanent borttagna objekt <i></i> (kallas även mjuka borttagna objekt) i postlådor, så länge bevarandeperioden för borttagna objekt för ett objekt inte har gått ut. Mer information finns i <a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">mappen Återställningsbara objekt i Exchange Online</a>.</td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>Vanliga frågor och svar om eDiscovery In-Place eDiscovery In-Place holds

**Jag använder funktionen för att kopiera sökresultat i eDiscoveryIn-Place i eDiscovery & i EAC för att kopiera sökresultat till en identifieringspostlåda för granskning av jurister. Vilka alternativ har jag nu?**

Det finns två sätt att replikera den här funktionen idag. Det första är att använda [granskningsuppsättningar i Advanced eDiscovery v2.0](./view-documents-in-review-set.md). Granskningsuppsättningar har många av de funktioner som du ser i ett traditionellt granskningsverktyg som snabbsökning av dokument, taggning, e-posttrådning, när duplicerad gruppering, temananalys och förutsägelsekodning. Om du fortfarande vill använda identifieringspostlådor för granskning är det andra alternativet att exportera sökresultatet till PST-filer och sedan importera PST-filerna till en identifieringspostlåda med hjälp av [pst-importfunktionen](use-network-upload-to-import-pst-files.md) i Microsofts efterlevnadscenter.

**Hur styr jag vilka innehållsplatser (till exempel postlådor eller webbplatser) som kan en eDiscovery-hanterare söka med de nya verktygen?**

I Microsoft 365 används även efterlevnadsgränser [för](set-up-compliance-boundaries.md) att styra vilka innehållsplatser en eDiscovery-hanterare kan söka i. Efterlevnadsgränser är användbara i myndigheter som behöver hålla sig inom agenturgränser eller multinationella företag som behöver ta hänsyn till geografiskt sett.

**Hur flyttar jag mina aktuella sökningar och rymmer till Microsoft 365 kompatibilitetscenter?**

Det är möjligt att migrera eDiscoveryIn-Place och eDiscovery-sökningar från EAC genom att använda PowerShell. Anvisningar finns i Migrera [sökningar och kvarhåller från EAC till Microsoft 365 efterlevnadscenter.](./migrate-legacy-ediscovery-searches-and-holds.md)

## <a name="-mailboxsearch-cmdlets"></a>\*-MailboxSearch-cmdlets

Enligt det ursprungliga meddelandet meddelades den 1 juli 2017 i administrationscentret i Exchange kommer funktionen In-Place eDiscovery & Hold och motsvarande **\* -MailboxSearch-cmdlets** att dras tillbaka. Dessa cmdlets ger användarna möjlighet att söka, behålla och exportera postlådeinnehåll för juridiska begäranden, föreskrifter och offentliga begäranden.

Eftersom dessa funktioner nu är tillgängliga i [<span class="underline">efterlevnadscentret</span>](./microsoft-365-compliance-center.md) för Microsoft 365 och Office 365 Säkerhets- och & Security & Compliance Center PowerShell med bättre prestanda och skalbarhet, bör du använda dessa förbättrade cmdlets. Dessa cmdlets inkluderar [<span class="underline"> \* -ComplianceCase</span>](/powershell/module/exchange/get-compliancecase), [<span class="underline"> \* -ComplianceSearch</span>](/powershell/module/exchange/get-compliancesearch), [<span class="underline"> \* -CaseHoldPolicy</span>](/powershell/module/exchange/get-caseholdpolicy), [<span class="underline"> \* -CaseHoldRule</span>](/powershell/module/exchange/get-caseholdrule)och [<span class="underline"> \* -ComplianceSearchAction.</span>](/powershell/module/exchange/get-compliancesearchaction)

### <a name="scope-of-affected-organizations"></a>Omfattningen av berörda organisationer

- Office 365 och Microsoft 365 Enterprise organisationer

- Office 365 och Microsoft 365 Education organisationer

- Office 365 och Microsoft 365 myndigheter. Det omfattar GCC, GCC Hög och DoD

- Office 365 Tyskland

### <a name="timeline"></a>Tidslinje

- 1 juli 2020: Du kan inte  använda Ny postlådaSnabbsökning för att skapa nya eDiscovery-sökningar och In-Place-inkorgar för In-Place, men du kan fortfarande använda cmdlets för att köra, redigera och ta bort befintliga sökningar och behålla dem på egen risk. Microsoft Support ger inte längre hjälp för dessa typer av sökningar och rymmer.

- 1 oktober 2020: Som tidigare nämnts kommer In-Place eDiscovery & Holds-funktionen i EAC att placeras i skrivskyddsläge. Det innebär också att du inte kan använda cmdlet:arna Ny postlådesökning, Starta postlådesökning eller **Set-MailboxSearch.**  Du kan bara hämta och ta bort befintliga sökningar och spärrade sökningar.

### <a name="alternative-tools"></a>Alternativa verktyg

I följande tabell beskrivs andra verktyg som du kan använda för att ersätta de befintliga funktioner som dras tillbaka.

<table>
<thead>
<tr class="header">
<th>Funktioner</th>
<th>Alternativa verktyg</th>
<th>Kommentarer</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Sök och exportera</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Cmdlet:arna ComplianceSearch och ComplianceSearchAction samarbetar för att hjälpa dig att söka efter och exportera innehåll. Du kan skapa en ny sökning och visa sökberäkningen med hjälp av cmdletarna <strong>New-</strong>, <strong>Get-</strong>och <strong>Start-ComplianceSearch.</strong> Sedan kan du exportera <strong>sökresultatet med New-ComplianceSearchAction-cmdleten.</strong> Du måste fortfarande använda huvudverktyget för eDiscovery i kompatibilitetscentret för Microsoft 365 för att ladda ned sökresultatet till din lokala dator.</p>
<p>
<p><strong>Obs!</strong> Om du använder dessa cmdlets för att skapa sökningar som inte är kopplade till ett <strong></strong> grundläggande eDiscovery-fall finns dessa sökningar på sidan Innehållssökning i kompatibilitetscentret för Microsoft 365.</p></td>
</tr>
<tr class="even">
<td>Håll innehåll i en postlåda</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldrule</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Kvarhåller i Microsoft 365 måste associeras med ett efterlevnadsfall. Skapa först ett efterlevnadsfall och skapa sedan ett CaseHoldPolicy och ett CaseHoldRule.</p>
<p><strong>Obs!</strong> Om du skapar ett CaseHoldPolicy utan att skapa CaseHoldRule kommer det inte att fungera tills CaseHoldRule har skapats och kopplats till CaseHoldPolicy. Mer information finns i dokumentationen till cmdleten.</p></td>
</tr>
<tr class="odd">
<td>Kopiera sökresultat till en identifieringspostlåda</td>
<td>Ingen</td>
<td>Den här funktionen ersätts inte direkt eftersom den inte ger tillgång till alla Microsoft 365 tjänster. Se vanliga frågor och svar nedan för alternativa lösningar.</td>
</tr>
  <tr class=even>
  <td>Kopiera meddelanden från en postlåda till en annan postlåda</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Tilldela behörigheter till en postlåda</a></td>
  <td>Om du vill ge en person åtkomst till en annan användares e-post (t.ex. när en anställd lämnar organisationen och du behöver ge en annan person åtkomst till den före detta anställdas e-post) rekommenderar vi att du tilldelar den personen behörighet för att komma åt den tidigare anställdas postlåda. I stället för att kopiera postlådeobjekt till en annan användarpostlåda eller en delad postlåda behöver du bara tilldela en användare behörighet att komma åt källpostlådan.</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>Vanliga frågor och svar om cmdlets *** -MailboxSearch**

**Vi använder kopieringssökning för att exportera e-postmeddelanden eller snabbmeddelanden för andra e-dataidentifierings- och juridiska undersökningar. Vilka andra alternativ har vi efter att dessa cmdlets har dragits tillbaka?**

[<span class="underline">Microsoft Graph-API:er</span>](https://developer.microsoft.com/en-us/graph) tillhandahåller ett antal metoder för att extrahera data för analys och andra syften som är mycket mer flexibel och skalbara än de **\* med -MailboxSearch-cmdlets.**

**Hur migrerar jag sökningar och rymmer till Microsoft 365 kompatibilitetscenter?**

Det är möjligt att migrera eDiscoveryIn-Place och eDiscovery-sökningar och eDiscovery-Exchange-administrationscentret med hjälp av ett PowerShell-skript. Mer information finns i Migrera [äldre eDiscovery-sökningar och eDiscovery-sökningar som Microsoft 365 kompatibilitetscenter.](migrate-legacy-eDiscovery-searches-and-holds.md)

**Kan jag ta bort eller hämta sökningar efter att cmdletarna har dragits tillbaka?**

Ja, även om vi tar bort möjligheten att skapa och ändra sökningar kan du fortfarande använda **Get-MailboxSearch** och **Remove-MailboxSearch** tills vidare. Du riskerar emellertid att använda dessa cmdlets på egen risk efter att de tas ur bruk och Microsoft Support kommer inte längre att kunna erbjuda hjälp.

## <a name="search-mailbox-cmdlet"></a>Search-Mailbox cmdlet

**Cmdlet:en Search-Mailbox** i Exchange Online PowerShell dras tillbaka som ursprungligen meddelades i en varning i cmdlet-utdata från och med 2018. **Cmdlet:en Search-Mailbox** användes ursprungligen för att söka i en användares postlåda och tömma skadligt innehåll. Vi rekommenderar att du börjar använda cmdletarna **New-ComplianceSearch** och **New-ComplianceSearchAction** i Office 365 Security & Compliance Center PowerShell för att söka efter och tömma innehåll. För en inbyggd säkerhetsupplevelse ger säkerhetsfunktionerna [<span class="underline">i Microsoft 365</span>](../security/index.yml) ett kraftfullt skydd för e-post och många andra Microsoft-tjänster.

### <a name="scope-of-affected-organizations"></a>Omfattningen av berörda organisationer

- Office 365 och Microsoft 365 Enterprise organisationer

- Office 365 och Microsoft 365 Education organisationer

- Office 365 och Microsoft 365 myndigheter. Det omfattar GCC, GCC Hög och DoD

- Office 365 Tyskland

### <a name="timeline"></a>Tidslinje

-  1 juli 2020:  Cmdlet:en sökpostlåda är inte längre tillgänglig och Microsoft Support ger inte längre någon hjälp.

### <a name="alternative-tools"></a>Alternativa verktyg

I följande tabell beskrivs andra verktyg som du kan använda för att ersätta de befintliga funktioner som dras tillbaka.

<table>
<thead>
<tr class="header">
<th>Funktioner</th>
<th>Alternativa verktyg</th>
<th>Kommentarer</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Söka i en postlåda</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></a></p></td>
<td><p>Cmdlet:arna ComplianceSearch och ComplianceSearchAction samarbetar för att hjälpa dig att söka efter och exportera innehåll. Du kan skapa en ny sökning och visa sökberäkningen med hjälp av cmdletarna <strong>New-</strong>, <strong>Get-</strong>och <strong>Start-ComplianceSearch.</strong> Du kan sedan exportera <strong>sökresultatet med kommandot New-ComplianceSearchAction -Export.</strong> Du måste fortfarande använda huvudverktyget för eDiscovery i kompatibilitetscentret för Microsoft 365 för att ladda ned sökresultatet till din lokala dator.</p></p>
</td>
</tr>
<tr class="even">
<td>Ta bort massutskick från en postlåda</td>
<td><p><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Konfigurera en princip för arkivering och borttagning för postlådor</span></a></p>
<p></p></td>
<td><p>Administratörer kan skapa en princip för arkivering och borttagning som automatiskt flyttar objekt till en användares arkivpostlåda och automatiskt tar bort objekt från postlådan.</p>
</td>
</tr>
<tr class="even">
<td>Kopiera sökresultat till en identifieringspostlåda</td>
<td> </td>
<td>Den här funktionen ersätts inte direkt eftersom den inte ger tillgång till alla Microsoft 365 tjänster. Alternativa lösningar finns i avsnittet Vanliga frågor och svar i <strong>*-MailboxSearch cmdlets.</strong> </td>
</tr>
<tr class=odd>
  <td>Kopiera meddelanden från en postlåda till en annan postlåda</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Tilldela behörigheter till en postlåda</a></td>
  <td>Om du vill ge en person åtkomst till en annan användares e-post (t.ex. när en anställd lämnar organisationen och du behöver ge en annan person åtkomst till den före detta anställdas e-post) rekommenderar vi att du tilldelar den personen behörighet för att komma åt den tidigare anställdas postlåda. I stället för att kopiera postlådeobjekt till en annan användarpostlåda eller en delad postlåda behöver du bara tilldela en användare behörighet att komma åt källpostlådan.</td>
</tr>
<tr class=even>
  <td>Ta bort meddelanden från en postlåda</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>Cmdlet:arna ComplianceSearch och ComplianceSearchAction samarbetar för att hjälpa dig att söka efter och rensa innehåll. Du kan skapa och köra en sökning med cmdletarna <strong>New-ComplianceSearch</strong> och <strong>New-ComplianceSearch,</strong> och sedan kan du rensa innehållet med kommandot <strong>New-ComplianceSearchAction -Purge -PurgeType.</strong> Mer information finns i Söka <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">efter och ta bort meddelanden.</span></a></p>
</td>
</tr>
<tr class="odd"> 
<td>Ta bort meddelanden från en postlåda</td>
<td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Tilldela behörigheter till en postlåda</a></td>
<td>Om du vill ta bort meddelanden från en postlåda tilldelar du en administratörsbehörighet för att få åtkomst till den anställdas postlåda. Meddelanden kan tas bort och återanvändas om de behövs och dra nytta av de inbyggda funktionerna för sökning och visning i Outlook.</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Exchange API-åtgärder för webbtjänster

De här åtgärderna i API:t för Exchange Web Services används av In-Place funktionen för eDiscovery &-innehåll i administrationscentret för Exchange och motsvarande **\* -MailboxSearch-cmdlets** i Exchange Online PowerShell. De kommer också att tas bort när de andra äldre eDiscovery-verktygen tas bort.

### <a name="scope-of-affected-organizations"></a>Omfattningen av berörda organisationer

- Office 365 och Microsoft 365 Enterprise organisationer

- Office 365 och Microsoft 365 Education organisationer

- Office 365 och Microsoft 365 myndigheter. Det omfattar GCC, GCC Hög och DoD

- Office 365 Tyskland

### <a name="timeline"></a>Tidslinje

- 1 juli 2020: Operationerna GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes och GetHoldOnMailboxes är inte längre tillgängliga och Microsoft Support kommer inte längre att ge hjälp.

## <a name="advanced-ediscovery-v10"></a>Advanced eDiscovery v1.0

Advanced eDiscovery v1.0, som är den version av Advanced eDiscovery som är tillgänglig i ett grundläggande eDiscovery-fall genom att klicka på Byt **till Advanced eDiscovery**, dras tillbaka. Funktionerna har ersatts av den nya [Advanced eDiscovery](./ediscovery.md) lösningen i Microsoft 365 efterlevnadscenter.

Så här tar du reda på om din organisation använder Advanced eDiscovery v1.0:

1. Gå till [säkerhets- Office 365 för & säkerhets- och efterlevnadscenter.](https://protection.office.com)

2. I det vänstra navigeringsfönstret i säkerhets- & efterlevnadscenter klickar du på **eDiscovery > eDiscovery** och öppnar ett Core eDiscovery-ärende.

3. Om du ser knappen **Advanced eDiscovery** till-Advanced eDiscovery kommer 1.0-versionen av Advanced eDiscovery att dras tillbaka. Möjligheten att skapa och hantera ärenden i Core eDiscovery påverkas inte. Endast möjligheten att lägga till och analysera ärendedata i Advanced eDiscovery v1.0 (genom att klicka på Växla till **Advanced eDiscovery**) dras tillbaka.

Den nya Advanced eDiscovery-lösningen i Microsoft 365 (kallas även *Advanced eDiscovery v2.0)* innehåller alla funktioner i den ursprungliga lösningen, men innehåller nu en avancerad metod för att identifiera innehåll i andra Microsoft 365-tjänster, samla in innehållet och sedan lägga till det i en granskningsuppsättning där granskare kan dra nytta av snabba sökfrågor, taggning och analysfunktioner för att underlätta för relevanta dokument. Advanced eDiscovery nu förbättrad bearbetning och inbyggda visningsprogram för både Microsoft- och andra filtyper än Microsoft finns det en fullständig lista över filtyper och metadatafält som stöds [finns här.](./document-metadata-fields-in-advanced-ediscovery.md) [](./supported-filetypes-ediscovery20.md) Den nya Advanced eDiscovery-lösningen ger dessutom en kraftfull, effektiv hanteringsfunktion som gör att du kan använda innehåll i olika tjänster, meddela användarna om innehåll som inte kan spärras och spårade svar, allt i ett Advanced eDiscovery fall.

Så här öppnar Advanced eDiscovery v2.0:

1. Gå till Microsoft 365 [efterlevnadscenter.](https://compliance.microsoft.com)

2. I det vänstra navigeringsfönstret i Microsoft 365 kompatibilitetscenter klickar du på **Visa alla** och sedan på **eDiscovery > Advanced**.

För stunden rekommenderar vi att du börjar övergå från ditt eDiscovery-arbetsflöde till det nya Advanced eDiscovery funktioner. Om det behövs kan du arkivera dina Advanced eDiscovery 1,0-ärenden genom att exportera innehållet och lagra det offline. Även om du fortfarande kan komma åt Advanced eDiscovery v1.0 i befintliga fall fram till den 31 december 2020 ger Microsoft Support inte support efter den 1 oktober 2020. Se följande tidslinje för mer information.

### <a name="scope-of-affected-organizations"></a>Omfattningen av berörda organisationer

- Office 365 och Microsoft 365 Enterprise organisationer

- Office 365 och Microsoft 365 Education organisationer

- Office 365 och Microsoft 365 myndigheter. Det omfattar GCC, GCC Hög och DoD

- Office 365 Tyskland

### <a name="timeline"></a>Tidslinje

- 1 juli 2020: Du kan inte skapa nya ärenden Advanced eDiscovery v1.0.

- 1 oktober 2020: Du kan inte lägga till nya data (Förbereda sökresultat för Advanced eDiscovery) i några ärenden. Du kan fortsätta arbeta med data på egen risk. Microsoft Support ger inte längre någon hjälp. 

- 31 december 2020: Du kan inte komma åt olika Advanced eDiscovery mot 1.0.

### <a name="alternative-tools"></a>Alternativa verktyg

Den [Advanced eDiscovery lösningen](./overview-ediscovery-20.md) i Microsoft 365 för efterlevnad.