---
title: Konfigurera behörighetsfiltrering för innehållssökning
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: Använd filtrering av behörigheter för innehållssökning för att låta en eDiscovery-hanterare endast söka i en delmängd av postlådor och webbplatser i organisationen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 654df250fb6816c215a3a3e28bd6456c6f88ab6e
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022480"
---
# <a name="configure-permissions-filtering-for-content-search"></a>Konfigurera behörighetsfiltrering för innehållssökning

Du kan använda filtrering av sökbehörigheter så att en eDiscovery-hanterare bara kan söka i en delmängd postlådor och webbplatser i organisationen. Du kan också använda behörighetsfiltrering för att låta samma eDiscovery-hanterare endast söka efter postlådor eller webbplatsinnehåll som uppfyller ett visst sökvillkor. Du kan till exempel låta en eDiscovery-hanterare söka i endast postlådorna för användare på en viss plats eller avdelning. Det gör du genom att skapa ett filter som använder ett mottagarfilter som stöds för att begränsa vilka postlådor en viss användare eller grupp av användare kan söka i. Du kan också skapa ett filter som anger vilket postlådeinnehåll en användare kan söka efter. Detta görs genom att skapa ett filter som använder en sökbar meddelandeegenskap. På samma sätt kan du låta en eDiscovery-hanterare bara söka SharePoint webbplatser i organisationen. Det gör du genom att skapa ett filter som begränsar vilken webbplats som kan sökas. Du kan också skapa ett filter som anger vilket webbplatsinnehåll som kan genomsökas. Detta görs genom att skapa ett filter som använder en sökbar webbplatsegenskap.

Du kan också använda filtrering av sökbehörigheter för att skapa logiska gränser (kallas efterlevnadsgränser) inom en organisation som styr användarinnehållsplatser (till exempel postlådor, SharePoint-webbplatser och OneDrive-konton) som vissa eDiscovery-hanterare kan söka i. Mer information finns i [Konfigurera efterlevnadsgränser för eDiscovery-undersökningar i Office 365.](tagging-and-assessment-in-advanced-ediscovery.md)
  
Filtrering av sökbehörigheter stöds av funktionen Innehållssökning i Säkerhets- & efterlevnadscenter. Med de här fyra cmdletarna kan du konfigurera och hantera filter för sökbehörighet:
  
[New-ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[Set-ComplianceSecurityFilter](#set-compliancesecurityfilter)

[Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="requirements-to-configure-permissions-filtering"></a>Krav för att konfigurera behörighetsfiltrering

- Om du vill köra cmdlet:arna för säkerhetsfilter för efterlevnad måste du vara medlem i rollgruppen Organisationshantering i säkerhets- & Efterlevnadscenter. Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

- Du måste ansluta till både PowerShell Exchange Online säkerhets- & säkerhets- och säkerhetscenter för att kunna använda cmdlets för efterlevnadssäkerhetsfilter. Detta är nödvändigt eftersom dessa cmdlets kräver åtkomst till postlådeegenskaper, och det är därför du måste ansluta till Exchange Online PowerShell. Se anvisningarna i nästa avsnitt.

- Mer information om filter för sökbehörighet finns i avsnittet Mer [information.](#more-information)

- Filtrering av sökbehörigheter tillämpas på inaktiva postlådor, vilket innebär att du kan använda innehållsfiltrering för postlådor för att begränsa vem som kan söka i en inaktiv postlåda. Mer information om filtrering av behörigheter och inaktiva postlådor finns i avsnittet Mer [information.](#more-information)

- Filtrering av sökbehörigheter kan inte användas för att begränsa vem som kan söka i gemensamma mappar i Exchange.

- Det finns ingen gräns för antalet sökbehörighetsfilter som kan skapas i en organisation. Men sökprestandan påverkas när det finns fler än 100 sökbehörighetsfilter. Om du vill hålla antalet sökbehörighetsfilter i organisationen så få som möjligt skapar du filter som kombinerar regler för Exchange, SharePoint och OneDrive i ett enda filter när det är möjligt.

## <a name="connect-to-exchange-online-and-security--compliance-center-powershell-in-a-single-session"></a>Anslut att Exchange Online och säkerhets- & PowerShell i en enda session

Innan du kan köra skriptet i det här avsnittet måste du hämta och installera Exchange Online PowerShell V2-modulen. Mer information finns i [Om Exchange Online PowerShell V2-modul](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).

1. Spara följande text i en Windows PowerShell skriptfil med hjälp av ett filnamnssuffix **som.ps1**. Du kan till exempel spara den i en fil med namnet **ConnectEXO-SCC.ps1**.

    ```powershell
    Import-Module ExchangeOnlineManagement
    $UserCredential = Get-Credential
    Connect-ExchangeOnline -Credential $UserCredential -ShowBanner:$false
    Connect-IPPSSession -Credential $UserCredential
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. Öppna ett skript på Windows PowerShell dator, gå till mappen där skriptet som du skapade i föregående steg finns och kör sedan skriptet. till exempel:

    ```powershell
    .\ConnectEXO-SCC.ps1
    ```

Hur vet du om det fungerade? När du har kört skriptet importeras cmdlets från Exchange Online Security & Compliance PowerShell till den lokala Windows PowerShell sessionen. Om du inte får några felmeddelande kunde du ansluta. Ett snabbt test är att köra Exchange Online- & säkerhets- och efterlevnadscenter. Du kan till exempel köra Och **Get-Mailbox och** **Get-ComplianceSearch.**

Information om felsökning av PowerShell-anslutningsfel finns i:

- [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#how-do-you-know-this-worked)

- [Anslut till Säkerhets- och efterlevnadscenter i PowerShell](/powershell/exchange/connect-to-scc-powershell#how-do-you-know-this-worked).

## <a name="new-compliancesecurityfilter"></a>New-ComplianceSecurityFilter

**New-ComplianceSecurityFilter används** för att skapa ett sökbehörighetsfilter. I följande tabell beskrivs parametrarna för den här cmdleten. Alla parametrar krävs för att skapa ett säkerhetsfilter för efterlevnad.
  
| Parameter | Beskrivning |
|:-----|:-----|
| _Åtgärd_ <br/> | Parametern  _Action_ anger den typ av sökåtgärd som filtret tillämpas på. De möjliga åtgärderna för innehållssökning är:  <br/><br/> **Exportera:** Filtret används när du exporterar sökresultat.  <br/> **Förhandsgranska:** Filtret används när du förhandsgranskar sökresultat.  <br/> **Rensa:** Filtret används när du rensar sökresultat.  <br/> **Sök:** Filtret används när du kör en sökning.  <br/> **Alla:** Filtret används i alla sökåtgärder.  <br/> |
| _FilterName_ <br/> |Parametern  _FilterName_ anger namnet på behörighetsfiltret. Namnet används för att identitetsidentiteta ett filter när du använder cmdlet:arna **Get-ComplianceSecurityFilter,** **Set-ComplianceSecurityFilter** och **Remove-ComplianceSecurityFilter.**  <br/> |
| _Filter_ <br/> | _Parametern_ Filters anger sökvillkoren för säkerhetsfiltret för efterlevnad. Du kan skapa tre olika typer av filter:  <br/><br/> **Postlåda eller OneDrive filtrering:** Den här typen av filter anger postlådorna och OneDrive de tilldelade användarna (anges med parametern _Users)_ kan söka. Syntaxen för den här typen av filter **är Mailbox_** _MailboxPropertyName,_ där _MailboxPropertyName_ anger en postlådeeegenskap som används för att begränsa postlådor och OneDrive-konton som kan sökas. Postlådefiltret skulle till exempel göra det möjligt för användaren som tilldelats det här filtret att endast söka i postlådor och OneDrive-konton som har värdet "Såd den här användaren" i egenskapen `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` CustomAttribute10.  <br/>  Alla filtrerbara mottagaregenskaper som stöds kan användas för _egenskapen MailboxPropertyName._ En lista över egenskaper som stöds finns [i Filtrerbara egenskaper för parametern -RecipientFilter.](/powershell/exchange/recipientfilter-properties)  <br/><br/> **Filtrering av postlådeinnehåll:** Den här typen av filter används på det innehåll som kan sökas. Den anger postlådans innehåll som de tilldelade användarna kan söka efter. Syntaxen för den här typen av filter **är MailboxContent_** SökbartEgenskapNamn: värde , där  _SökbartEgenskapnamn_ anger en KQL-egenskap (Keyword Query Language) som kan anges i en innehållssökning. Exempelvis skulle innehållsfiltret i postlådan göra det möjligt för användaren som tilldelats filtret att endast söka efter meddelanden som skickats till mottagare  `MailboxContent_recipients:contoso.com` i contoso.com domän.  <br/>  En lista över sökbara meddelandeegenskaper finns i [Nyckelordsfrågor och sökvillkor för Innehållssökning.](keyword-queries-and-search-conditions.md) <br/> <br/> **Viktigt!**  Ett enda sökfilter kan inte innehålla ett postlådefilter eller ett innehållsfilter för postlådan. Om du vill kombinera dessa i ett enda filter måste du använda en [filterlista](#using-a-filters-list-to-combine-filter-types).  Men ett filter kan innehålla en mer komplex fråga av samma typ. Exempel:  `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`  <br/><br/> **Filtrering av webbplats- och webbplatsinnehåll:** Det finns två SharePoint och OneDrive för företag webbplatsrelaterade filter som du kan använda för att ange vilket webbplats- eller webbplatsinnehåll som de tilldelade användarna kan söka i:  <br/><br/> - **Site_** _SearchableSiteProperty_ <br/> - **SiteContent_** _SearchableSiteProperty_ <br/><br/>  De här två filtren är inte samma som de andra. Till exempel  `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` och returnera samma  `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` resultat. Men för att hjälpa dig att identifiera vad ett filter gör kan du använda för att ange webbplatsrelaterade egenskaper (till exempel en webbplats-URL) och för att ange innehållsrelaterade egenskaper (till exempel  `Site_`  `SiteContent_` dokumenttyper. Filtret skulle till exempel  `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` tillåta att användaren som tilldelats det här filtret endast söker efter innehåll i https://contoso.sharepoint.com/sites/doctors webbplatssamlingen. Filtret gör  `"SiteContent_FileExtension -eq 'docx'"` att användaren som tilldelat det här filtret endast kan söka efter Word-dokument (Word 2007 och senare).  <br/><br/>  En lista över sökbara webbplatsegenskaper finns i [Översikt över crawlade och hanterade egenskaper i SharePoint](/SharePoint/technical-reference/crawled-and-managed-properties-overview). Egenskaper som är markerade **med Ja** i **kolumnen Frågebar** kan användas för att skapa ett webbplats- eller webbplatsinnehållsfilter.  <br/><br/> **Viktigt!** Du måste skapa ett sökbehörighetsfilter för att uttryckligen hindra användare från att söka på innehållsplatser i en viss tjänst (till exempel hindra en användare från att söka i en Exchange-postlåda eller någon annan SharePoint webbplats). Med andra ord hindrar inte användare att söka i postlådor om de skapar ett filter med sökbehörigheter som gör att en användare kan söka på alla SharePoint-webbplatser i organisationen. Om du till exempel vill tillåta SharePoint att bara söka på SharePoint webbplatser måste du skapa ett filter som hindrar dem från att söka i postlådor. Om du vill tillåta Exchange att bara söka i postlådor måste du skapa ett filter som hindrar dem från att söka på webbplatser.           |
| _Användare_ <br/> |_Parametern_ Users anger de användare som får filtret tillämpat på sina innehållssökningar. Identifiera användare med deras alias eller primära SMTP-adress. Du kan ange flera värden avgränsade med kommatecken, eller så kan du tilldela filtret till alla användare genom att använda **värdet Alla**.  <br/> Du kan också använda  _parametern Users_ till att ange en rollgrupp & Säkerhets- och efterlevnadscenter. Då kan du skapa en anpassad rollgrupp och sedan tilldela rollgruppen ett filter med sökbehörigheter. Anta till exempel att du har en anpassad rollgrupp för eDiscovery-chefer för USA:s dotterbolag till ett multinationellt företag. Du kan använda  _parametern_ Users till att ange den här rollgruppen (med hjälp av egenskapen Namn för rollgruppen) och sedan använda  _filterparametern_ till att bara tillåta att postlådor i USA genomsöks.  <br/> Du kan inte ange distributionsgrupper med den här parametern.  <br/> |
   
### <a name="using-a-filters-list-to-combine-filter-types"></a>Använda en filterlista för att kombinera filtertyper

En *filterlista* är ett filter som innehåller ett postlådefilter och ett webbplatsfilter avgränsade med kommatecken. Att använda en filterlista är den enda metoden som stöds för att kombinera olika typer av filter. I följande exempel skiljer ett kommatecken mellan postlådan **och** **webbplatsfiltren:**

```powershell
-Filters "Mailbox_CustomAttribute10 -eq 'OttawaUsers'", "Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"
```

När ett filter som innehåller en filterlista bearbetas under en innehållssökning skapas två sökbehörighetsfilter från filterlistan: ett för varje filter som avgränsas med kommatecken. I exemplet ovan skulle alltså ett filter för sökningsbehörigheter för postlådor och ett filter för webbplatssökningsbehörigheter skapas. 

Ett alternativ till att använda en filterlista är att skapa två separata sökbehörighetsfilter. I exemplet ovan skulle du alltså skapa ett filter för postlådans attribut och ett filter för webbplatsattributet. I båda fallen blir resultaten desamma. Det spelar ingen roll om du använder en filterlista eller skapar separata sökbehörighetsfilter.

Tänk på följande när du använder en filterlista:

- Du måste använda en filterlista för att skapa ett filter som innehåller ett **postlådefilter** och ett **MailboxContent-filter.**

- Varje komponent i en filterlista kan innehålla en komplex filtersyntax. Till exempel kan postlådan och webbplatsfilter innehålla flera filter avgränsade med operatorn **-eller:**

   ```powershell
   -Filters "Mailbox_Department -eq 'CohoWinery' -or Mailbox_CustomAttribute10 -eq 'CohoUsers'", "Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'"
   ```

## <a name="examples-of-creating-search-permissions-filters"></a>Exempel på hur du skapar sökbehörighetsfilter

Här är exempel på hur cmdleten **New-ComplianceSecurityFilter** kan användas för att skapa ett sökbehörighetsfilter. 
  
I det här exemplet kan användaren annb@contoso.com att utföra alla åtgärder för innehållssökning endast för postlådor i Kanada. Det här filtret innehåller den tresiffriga numeriska landskoden för Kanada från ISO 3166-1.

```powershell
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'" -Action All
```

I det här exemplet kan användarna donh and su koda till endast postlådor som har värdet "Marknadsföring" för postlådeegenskapen CustomAttribute1.

```powershell
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'" -Action Search
```

I det här exemplet kan medlemmar i rollgruppen "identifieringshanterare i USA" utföra alla åtgärder för innehållssökning endast på postlådor i USA. Det här filtret innehåller den tresiffriga numeriska landskoden för USA från ISO 3166-1.
  
```powershell
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryCode  -eq '840'" -Action All
```

I det här exemplet kan medlemmar i rollgruppen för eDiscovery-hanteraren söka i endast postlådorna för medlemmar i distributionsgruppen För användare av så gott som möjligt. Med Get-DistributionGroup-cmdleten i Exchange Online PowerShell används för att hitta medlemmarna i gruppen Användare av användare.
  
```powershell
$DG = Get-DistributionGroup "Ottawa Users"
```

```powershell
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```

Det här exemplet hindrar en användare från att ta bort innehåll från postlådorna för medlemmar i distributionsgruppen För ledningsgruppen. Med Get-DistributionGroup-cmdleten Exchange Online PowerShell används för att hitta medlemmar i ledningsgruppen.

```powershell
$DG = Get-DistributionGroup "Executive Team"
```

```powershell
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users All -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" -Action Purge
```

I det här exemplet kan medlemmar OneDrive den anpassade rollgruppen för eDiscovery-hanterare endast söka efter innehåll OneDrive för företag andra platser i organisationen.

```powershell
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```

> [!NOTE]
> För att begränsa användare till att söka på specifika webbplatser använder  `Site_Path` du filtret , som i föregående exempel. Det  `Site_Site` går inte att använda. 
  
Det här exemplet begränsar användaren att utföra alla åtgärder för innehållssökning endast på e-postmeddelanden som skickas under kalenderåret 2015.

```powershell
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```

I likhet med föregående exempel begränsar det här exemplet användaren att utföra alla innehållssökningsåtgärder på dokument som senast ändrades någon gång under kalenderåret 2015.

```powershell
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```

Det här exemplet förhindrar att medlemmar i rollgruppen "OneDrive identifieringshanterare" kan utföra innehållssökningsåtgärder på någon postlåda i organisationen. 

```powershell
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```

Det här exemplet hindrar alla i organisationen från att söka efter e-postmeddelanden som har skickats eller tagits emot av annater eller sarad.

```powershell
New-ComplianceSecurityFilter -FilterName NoSaraJanet -Users All -Filters "MailboxContent_Participants -notlike 'janets@contoso.onmicrosoft.com' -and MailboxContent_Participants -notlike 'sarad@contoso.onmicrosoft.com'" -Action Search
```

I det här exemplet används en filterlista för att kombinera postlåde- och webbplatsfilter.

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

**Get-ComplianceSecurityFilter används för** att returnera en lista med sökbehörighetsfilter. Använd  _parametern FilterName_ för att returnera information för ett specifikt sökfilter. 
  
## <a name="set-compliancesecurityfilter"></a>Set-ComplianceSecurityFilter

**Set-ComplianceSecurityFilter används för** att ändra ett befintligt sökbehörighetsfilter. Den enda obligatoriska parametern är  _FilterName_. 
  
| Parameter | Beskrivning |
|:-----|:-----|
| _Åtgärd_| Parametern  _Action_ anger den typ av sökåtgärd som filtret tillämpas på. De möjliga åtgärderna för innehållssökning är: <br/><br/> **Exportera:** Filtret används när du exporterar sökresultat.  <br/> **Förhandsgranska:** Filtret används när du förhandsgranskar sökresultat.  <br/> **Rensa:** Filtret används när du rensar sökresultat.  <br/> **Sök:** Filtret används när du kör en sökning.  <br/> **Alla:** Filtret används i alla sökåtgärder.  <br/> |
| _FilterName_|Parametern  _FilterName_ anger namnet på behörighetsfiltret. |
| _Filter_| _Parametern_ Filters anger sökvillkoren för säkerhetsfiltret för efterlevnad. Du kan skapa två olika typer av filter: <br/><br/>**Postlåda och OneDrive filtrering:** Den här typen av filter anger postlådorna och OneDrive de tilldelade användarna (anges med parametern _Users)_ kan söka. Syntaxen för den här typen av filter **är Mailbox_** _MailboxPropertyName,_ där  _MailboxPropertyName_ anger en postlådeeegenskap som används för att begränsa vilka postlådor som kan genomsökas. Postlådefiltret skulle till exempel kunna låta användaren som tilldelats det här filtret söka endast i postlådor som har värdet "Så här ser det ut" i  `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` egenskapen CustomAttribute10.  Alla filtrerbara mottagaregenskaper som stöds kan användas för _egenskapen MailboxPropertyName._ En lista över egenskaper som stöds finns [i Filtrerbara egenskaper för parametern -RecipientFilter.](/powershell/exchange/recipientfilter-properties) <br/><br/>**Filtrering av postlådeinnehåll:** Den här typen av filter används på det innehåll som kan sökas. Den anger postlådans innehåll som de tilldelade användarna kan söka efter. Syntaxen för den här typen av filter är **MailboxContent_** _SearchablePropertyName:value,_ där  _SearchablePropertyName_ anger en KQL-egenskap (Keyword Query Language) som kan anges i en innehållssökning. Exempelvis skulle innehållsfiltret i postlådan göra det möjligt för användaren som tilldelats filtret att endast söka efter meddelanden som skickats till mottagare  `MailboxContent_recipients:contoso.com` i contoso.com domän.  En lista över sökbara meddelandeegenskaper finns i [Nyckelordsfrågor för innehållssökning](keyword-queries-and-search-conditions.md). <br/><br/>**Filtrering av webbplats- och webbplatsinnehåll:** Det finns två SharePoint och OneDrive för företag webbplatsrelaterade filter som du kan använda för att ange vilket webbplats- eller webbplatsinnehåll som de tilldelade användarna kan söka i: <br/><br/>- **Site_** *SearchableSiteProperty* <br/>- **SiteContent** _ *SearchableSiteProperty*<br/><br/>De här två filtren är inte samma som de andra. Till  `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` exempel, och  `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` returnerar samma resultat. Men för att hjälpa dig att identifiera vad ett filter gör kan du använda för att ange webbplatsrelaterade egenskaper (till exempel en webbplats-URL) och för att ange innehållsrelaterade egenskaper (till exempel  `Site_`  `SiteContent_` dokumenttyper. Filtret skulle till exempel  `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` tillåta att användaren som tilldelats det här filtret endast söker efter innehåll i https://contoso.spoppe.com/sites/doctors webbplatssamlingen. Filtret gör  `"SiteContent_FileExtension -eq 'docx'"` att användaren som tilldelat det här filtret endast kan söka efter Word-dokument (Word 2007 och senare).  <br/><br/>En lista över sökbara webbplatsegenskaper finns i [Översikt över crawlade och hanterade egenskaper i SharePoint](/SharePoint/technical-reference/crawled-and-managed-properties-overview). Egenskaper som är markerade **med Ja** i **kolumnen Frågebar** kan användas för att skapa ett webbplats- eller webbplatsinnehållsfilter. <br/><br/>          |
| _Användare_|_Parametern_ Users anger de användare som får filtret tillämpat på sina innehållssökningar. Eftersom det här är en egenskap med flera värden skriver du över den befintliga listan med användare om du anger en användare eller grupp av användare med den här parametern. Se följande exempel för syntaxen för att lägga till och ta bort markerade användare. <br/><br/>Du kan också använda  _parametern Users_ till att ange en rollgrupp & Säkerhets- och efterlevnadscenter. Då kan du skapa en anpassad rollgrupp och sedan tilldela rollgruppen ett filter med sökbehörigheter. Anta till exempel att du har en anpassad rollgrupp för eDiscovery-chefer för USA:s dotterbolag till ett multinationellt företag. Du kan använda  _parametern_ Users till att ange den här rollgruppen (med hjälp av egenskapen Namn för rollgruppen) och sedan använda  _filterparametern_ till att bara tillåta att postlådor i USA genomsöks. <br/><br/>Du kan inte ange distributionsgrupper med den här parametern. |

## <a name="examples-of-changing-search-permissions-filters"></a>Exempel på ändring av sökbehörighetsfilter

De här exemplen visar hur du använder cmdletarna **Get-ComplianceSecurityFilter** och **Set-ComplianceSecurityFilter** för att lägga till eller ta bort en användare i den befintliga listan över användare som filtret är kopplat till. När du lägger till eller tar bort användare från ett filter anger du användaren med hjälp av deras SMTP-adress. 
  
I det här exemplet läggs en användare till i filtret.

```powershell
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```powershell
$filterusers.users.add("pilarp@contoso.com")
```

```powershell
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```

Det här exemplet tar bort en användare från filtret.

```powershell
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```powershell
$filterusers.users.remove("annb@contoso.com")
```

```powershell
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```

## <a name="remove-compliancesecurityfilter"></a>Remove-ComplianceSecurityFilter

**Remove-ComplianceSecurityFilter används** för att ta bort ett sökfilter. Använd  _parametern FilterName_ för att ange filtret du vill ta bort. 
  
## <a name="more-information"></a>Mer information

- **Hur fungerar filtrering av sökbehörigheter?** Behörighetsfiltret läggs till i sökfrågan när en innehållssökning körs. Behörighetsfiltret sammanfogas till sökfrågan av **operatorn AND** Boolean. Du har till exempel ett behörighetsfilter som gör att Bob kan utföra alla sökåtgärder på postlådorna för medlemmar i distributionsgruppen Arbetar. Sedan kör Bob en innehållssökning på alla postlådor i organisationen med sökfrågan  `sender:jerry@adatum.com` . Eftersom behörighetsfiltret och sökfrågan logiskt kombineras av en **OCH-operator** returnerar sökningen ett meddelande som skickats av jerry@adatum.com till någon medlem i distributionsgruppen Workers. 
    
- **Vad händer om du har flera sökbehörighetsfilter?** I en innehållssökningsfråga kombineras flera behörighetsfilter av **ELLER** booleska operatorer. Resultatet returneras om något av filtren är sant. I en innehållssökning kombineras sedan  alla filter (kombinerade av ELLER-operatorer) med sökfrågan av **OCH-operatorn.** Vi tar exemplet ovan, där ett sökfilter tillåter att Bob bara söker i postlådorna för medlemmarna i distributionsgruppen Workers. Sedan skapar vi ett annat filter som hindrar Bob från att söka i Bobbys postlåda ("Mailbox_Alias -ne 'Den'"). Vi utgår också från att Han är medlem i gruppen Arbetar. När Bob kör en innehållssökning (från föregående exempel) för alla postlådor i organisationen returneras sökresultat för Bobs postlåda även om du har använt filter för att förhindra att Bob söker i Bobs postlåda. Det beror på att det första filtret, som gör att Bob kan söka i gruppen Arbetar, är sant. Och eftersom Magnus är medlem i gruppen Workers kan Bob söka i Bobbys postlåda. 
    
- **Fungerar filtrering av sökbehörigheter för inaktiva postlådor?** Ja, du kan använda innehållsfilter för postlådor och postlådor för att begränsa vem som kan söka i inaktiva postlådor i organisationen. Precis som en vanlig postlåda måste en inaktiv postlåda konfigureras med den mottagaregenskap som används för att skapa ett behörighetsfilter. Om det behövs kan du använda **kommandot Get-Mailbox -InactiveMailboxOnly** för att visa egenskaperna för inaktiva postlådor. Mer information finns i Skapa [och hantera inaktiva postlådor i Office 365](create-and-manage-inactive-mailboxes.md).
    
- **Fungerar filtrering av sökbehörigheter för gemensamma mappar?** Nej. Som tidigare förklarats kan filtrering av sökbehörigheter inte användas för att begränsa vem som kan söka i gemensamma mappar i Exchange. Objekt i gemensamma mappplatser kan till exempel inte uteslutas från sökresultatet av ett behörighetsfilter. 

- **Förhindrar det att användare söker på alla innehållsplatser i en viss tjänst från att söka på innehållsplatser i en annan tjänst?** Nej. Som tidigare förklarats måste du skapa ett sökbehörighetsfilter för att uttryckligen hindra användare från att söka på innehållsplatser i en viss tjänst (till exempel förhindra en användare från att söka i en Exchange-postlåda eller någon annan SharePoint-webbplats). Med andra ord hindrar inte användare att söka i postlådor om de skapar ett filter med sökbehörigheter som gör att en användare kan söka på alla SharePoint-webbplatser i organisationen. Om du till exempel vill tillåta SharePoint att bara söka på SharePoint webbplatser måste du skapa ett filter som hindrar dem från att söka i postlådor. Om du vill tillåta Exchange att bara söka i postlådor måste du skapa ett filter som hindrar dem från att söka på webbplatser.

- **Räknas sökbehörighetsfilter mot teckenbegränsningar i sökfrågan?** Ja. Sökbehörighetsfilter räknas mot teckenbegränsningen för sökfrågor. Mer information finns i [Begränsningar i Advanced eDiscovery](limits-ediscovery20.md).

