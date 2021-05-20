---
title: Funktionsreferens för Innehållssökning
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Den här artikeln innehåller referensinformation om verktyget eDiscovery för innehållssökning i Microsoft 365 Efterlevnadscenter som hjälper dig få mer information om innehållssökning.
ms.openlocfilehash: 14660b4cfcd09f5346fa8d0d901880d0a6c774c2
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538489"
---
# <a name="feature-reference-for-content-search"></a>Funktionsreferens för Innehållssökning

I den här artikeln beskrivs funktioner och funktionalitet för innehållssökning.

## <a name="content-search-limits"></a>Begränsningar för innehållssökning

En beskrivning av begränsningarna för innehållssökning finns i [Begränsningar för innehållssökning](limits-for-content-search.md).
  
## <a name="building-a-search-query"></a>Skapa en sökfråga

Detaljerad information om hur du skapar en sökfråga, använder booleska sökoperatorer och sökvillkor samt söker efter olika typer av känslig information och innehåll som delas med användare utanför organisationen finns i [Nyckelordsfrågor och sökvillkor för innehållssökning ](keyword-queries-and-search-conditions.md).
  
Tänk på följande när du använder nyckelordslistan för att skapa en sökfråga.
  
- Du måste markera kryssrutan **Visa nyckelordslista** och sedan skriva varje nyckelord på en separat rad när du skapar en sökfråga där nyckelorden (eller nyckelordsfraserna) på varje rad har kopplats samman med operatorn **OR**. Om du klistrar in en lista med nyckelord i nyckelordsrutan eller trycker på **Retur** när du har skrivit ett nyckelord kopplas de inte samman med operatorn **OR**. Här är ett felaktigt och ett korrekt exempel på hur du lägger till en lista med nyckelord.
    
    **Fel**
    
    ![Det felaktiga sättet att formatera en nyckelordslista (genom att klistra in listan i nyckelordsrutan)](../media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    **Rätt**
    
    ![Rätt sätt att formatera en nyckelordslista (genom att markera kryssrutan och sedan klistra in listan)](../media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
- Du kan också förbereda en lista med nyckelord eller nyckelordsfraser i en Excel-fil eller en fil med oformaterad text och sedan kopiera och klistra in listan i nyckelordslistan. För att göra det måste du markera kryssrutan **Visa nyckelordslista**. Klicka sedan på den första raden i nyckelordslistan och klistra in listan. Varje rad från Excel eller textfilen klistras in på en separat rad i nyckelordslistan. 
    
- När du har skapat en fråga med hjälp av nyckelordslistan bör du kontrollera frågesyntaxen för att försäkra dig om att sökfrågan ser ut som du tänkt dig. I sökfrågan som visas under **Fråga** i informationsfönstret avgränsas nyckelorden med texten **(c:s)**. Detta anger att nyckelorden är sammankopplade med en logisk operator som har en liknande funktion som operatorn **OR**. Och om sökfrågan innehåller villkor avgränsas nyckelorden och villkoren med texten **(c:c)**. Detta anger att nyckelorden är sammankopplade med en logisk operator som har en liknande funktion som operatorn **AND**. Här är ett exempel på hur en sökfråga (visas i informationsfönstret) kan se ut när du använder nyckelordslistan och ett villkor. 
    
    ![Exempel på en fråga som skapas när du använder nyckelordslistan och ett villkor](../media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
- När du kör en innehållssökning söker Microsoft 365 automatiskt igenom din sökfråga efter tecken som inte stöds och efter booleska operatorer som inte är versaler. Tecken som inte stöds är ofta dolda och leder vanligtvis till sökfel eller returnerar oväntade resultat. Mer information om vilka tecken som kontrolleras finns i [Kontrollera om det finns fel i din innehållssökningsfråga](check-your-content-search-query-for-errors.md).
    
- Om din sökfråga innehåller nyckelord med icke-engelska tecken (till exempel kinesiska tecken) kan du klicka på **Frågespråk-land/region**![Ikonen Frågespråk – land/region i Innehållssökning](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) och välja en kod (i formatet språk-land/region) för sökningen. Standardalternativet för språk/region är neutralt. Hur vet du om du behöver ändra språkinställningen för en innehållssökning? Om du vet att vissa innehållsplatser som du söker på innehåller icke-engelska tecken och sökningen inte returnerar några resultat kan det bero på språkinställningen.
  
## <a name="partially-indexed-items"></a>Delvis indexerade objekt

- Delvis indexerade objekt i postlådor tas med i de uppskattade sökresultaten. Delvis indexerade objekt från SharePoint och OneDrive tas inte med i de uppskattade sökresultaten. Mer information finns i [Delvis indexerade objekt i eDiscovery](partially-indexed-items-in-content-search.md).

## <a name="searching-onedrive-accounts"></a>Söka i OneDrive-konton

- Information om hur du samlar in en lista med URL-adresser för OneDrive-webbplatserna i organisationen finns i [Skapa en lista över alla OneDrive-platser i organisationen](/onedrive/list-onedrive-urls). Med skriptet i den här artikeln skapas en textfil som innehåller en lista över alla OneDrive-webbplatser. Om du vill köra det här skriptet måste du installera och använda SharePoint Online Management Shell. Se till att du lägger till URL-adressen för organisationens Min Webbplats-domän för alla OneDrive-webbplatser som du vill söka på. Det här är domänen som innehåller alla dina OneDrive-webbplatser, till exempel `https://contoso-my.sharepoint.com`. Exempel på en URL-adress för en användares OneDrive-webbplats: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.
    
    Om ett användarhuvudnamn (UPN) ändras, vilket är ovanligt, ändras URL-adressen för användarens OneDrive-plats för att ta med det nya användarhuvudnamnet. I så fall måste du ändra innehållssökningen genom att lägga till användarens nya OneDrive-URL och ta bort den gamla. Mer information finns i [Hur UPN-ändringar påverkar OneDrive-URL:en](/onedrive/upn-changes).
  
## <a name="searching-microsoft-teams-and-microsoft-365-groups"></a>Söka i Microsoft Teams och Microsoft 365-grupper

Du kan söka i postlådan som är kopplad till ett Microsoft Teams-team eller en Microsoft 365-grupp. Eftersom Microsoft Teams-team bygger på Microsoft 365-grupper fungerar sökningen i dem på liknande sätt. I båda fallen genomsöks bara gruppens eller teamets postlåda. Grupp- eller teammedlemmarnas postlådor genomsöks inte. Om du vill söka i dem måste du lägga till dem i sökningen.
  
Tänk på följande när du söker efter innehåll i Microsoft Teams-team och Microsoft 365-grupper.
  
- Om du vill söka efter innehåll i Teams-team och Microsoft 365-grupper måste du ange postlådan och SharePoint-webbplatsen som är kopplade till en grupp.

- Innehåll från privata kanaler lagras i varje användares postlåda, inte i den gemensamma postlådan. Om du vill söka efter innehåll i privata kanaler kan du se [eDiscovery för privata kanaler](/microsoftteams/ediscovery-investigation#ediscovery-of-private-channels).
    
- Kör cmdleten **Get-UnifiedGroup** i Exchange Online om du vill visa egenskaper för ett team eller en Microsoft 365-grupp. Det här är ett bra sätt att hämta URL-adressen för den webbplatsen som är kopplad till ett team eller en grupp. Följande kommando visar till exempel valda egenskaper för en Microsoft 365-grupp som heter Senior Leadership Team: 
    
  ```text
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  ```

    > [!NOTE]
    > För att kunna köra cmdleten **Get-UnifiedGroup** måste du ha tilldelats rollen View-Only Recipients i Exchange Online eller vara medlem i en rollgrupp som har tilldelats rollen View-Only Recipients. 
  
- Vid en genomsökning av en användares postlåda genomsöks inte något team eller någon Microsoft 365-grupp som användaren är medlem i. Och när du söker i ett team eller i en Microsoft 365-grupp genomsöks bara den gruppostlåda och gruppwebbplats som du anger. Gruppmedlemmarnas postlådor och OneDrive för företag-konton genomsöks inte, såvida du inte uttryckligen lägger till dem i sökningen.

- Om du vill hämta en lista över medlemmarna i ett team eller i en Microsoft 365-grupp kan du visa egenskaperna på sidan **Start \> Grupper** i Administrationscenter för Microsoft 365. Eller så kan du köra följande kommando i Exchange Online PowerShell: 

  ```powershell
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
  ```

    > [!NOTE]
    > För att kunna köra cmdleten **Get-UnifiedGroupLinks** måste du ha tilldelats rollen View-Only Recipients i Exchange Online eller vara medlem i en rollgrupp som har tilldelats rollen View-Only Recipients. 
  
- De konversationer som ingår i en Teams-kanal lagras i postlådan som är kopplad till teamet. På samma sätt lagras filer som teammedlemmar delar i en kanal på teamets SharePoint-webbplats. Därför måste du lägga till teampostlådan och SharePoint-webbplatsen som en innehållsplats när du ska söka efter konversationer och filer i en kanal.
    
- Du kan också lagra konversationer som ingår i chattlistan i Teams i Exchange Online-postlådan för de användare som deltar i chatten. Och de filer som en användare delar i chattkonversationer lagras i OneDrive för företag-kontot för den användare som delar filen. Därför måste du lägga till enskilda användarpostlådor och OneDrive för företag-konton som innehållsplatser när du söker i konversationer och filer i chattlistan.
    
    > [!NOTE]
    > I en Exchange-hybriddistribution kan användare med en lokal postlåda delta i konversationer som ingår i chattlistan i Teams. I så fall är innehållet i dessa konversationer också sökbart eftersom det sparas på en molnbaserad lagringsplats (en så kallad *molnbaserad postlåda för lokala användare*) för användare som har en lokal postlåda. Mer information finns i [Söka efter Teams chattdata för lokala användare](search-cloud-based-mailboxes-for-on-premises-users.md).
  
- Alla team- och gruppkanaler innehåller en wiki-sida för anteckningar och samarbete. Wiki-innehållet sparas automatiskt i en MHT-fil. Den här filen lagras i dokumentbiblioteket för Teams-wikidata på teamets SharePoint-webbplats. Med verktyget Innehållssökning kan du söka på wiki-sidan genom att ange teamets SharePoint-webbplats som innehållsplats för sökning.

    > [!NOTE]
    > Möjligheten att söka på wiki-sidan för en grupp eller kanal (när du söker på teamets SharePoint-webbplats) släpptes den 22 juni 2017. Du kan söka på wiki-sidor som sparats eller uppdaterats från och med det datumet. Du kan inte söka på wiki-sidor som sparats eller uppdaterats före det datumet.

- Sammanfattningsinformation för möten och samtal i en Teams-kanal lagras också i postlådorna för de användare som har ringt in till mötet eller samtalet. Det betyder att du kan använda innehållssökning för att söka i sammanfattningsposterna. Sammanfattningsinformation omfattar:
  
  - Datum, startdatum, sluttid och varaktighet för ett möte eller samtal

  - Datum och tid då varje deltagare gick med i eller lämnade mötet eller samtalet

  - Samtal som skickats till röstbrevlådan

  - Missade eller obesvarade samtal

  - Vidarekopplingar av samtal (visas som två separata samtal)

  Det kan ta upp till 8 timmar innan sammanfattningsposterna för möten och samtal blir tillgängliga för sökning.

  Mötessammanfattningar identifieras som **Möte** i fältet **Typ** i sökresultat och samtalssammanfattningar identifieras som **Samtal**. Konversationer som ingår i en Teams-kanal och gruppchattar identifieras som **Snabbmeddelande** i fältet **Typ**.
  
  ![Teams-möten, samtal och gruppchattar identifieras i fältet Typ](../media/O365-ContentSearch-Teams-MessageKind.png)

   Mer information finns i artikeln [Microsoft Teams lanserar eDiscovery för samtal och möten](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-launches-ediscovery-for-calling-and-meetings/ba-p/210947).

- Kortinnehåll som genereras av appar i Teams-kanaler, enskilda chattar och gruppchattar lagras i postlådor och är sökbara. Ett *kort* är en användargränssnittsbehållare för ett litet innehåll. Kort kan ha flera egenskaper och bifogade filer, och kan innehålla knappar som kan utlösa kortåtgärder. Mer information finns i [Kort](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

  Precis som annat Teams-innehåll beror lagringen av kortinnehållet på var kortet användes. Innehållet för kort som används i en Teams-kanal lagras i Teams-gruppostlådan. Kortinnehållet för enskilda chattar och gruppchattar lagras i chattdeltagarnas postlådor.

  Om du vill söka efter kortinnehåll kan du använda `kind:microsoftteams`- eller `itemclass:IPM.SkypeTeams.Message`-sökvillkor. När du granskar sökresultat har kortinnehåll som genererats av robotar i en Teams-kanal **Avsändare/författare**-e-postegenskapen `<appname>@teams.microsoft.com`, där `appname` är namnet på appen som genererade kortinnehållet. Om kortinnehållet genererades av en användare identifierar **Avsändare/författare** användaren.

  När du visar kortinnehåll i innehållssökningsresultat visas innehållet som en bifogad fil i meddelandet. Den bifogade filen heter `appname.html`, där `appname` är namnet på appen som genererade kortinnehållet. Följande skärmbilder visar hur kortinnehåll (för en app som heter Asana) visas i Teams och i resultatet av en sökning.

  **Kortinnehåll i Teams**

  ![Kortinnehåll i Teams-kanalmeddelande](../media/CardContentTeams.png)

  **Kortinnehåll i sökresultat**
  
  ![Samma kortinnehåll i resultatet av en innehållssökning](../media/CardContentEdiscoverySearchResults.png)

  > [!NOTE]
  > Om du vill visa bilder från kortinnehåll i sökresultat (till exempel bockmarkeringarna på föregående skärmbild) måste du vara inloggad i Teams (på https://teams.microsoft.com) på en annan flik i samma webbläsarsession som du använder för att visa sökresultaten. Annars visas bildplatshållare.

- Du kan använda e-postegenskapen **Kind** eller sökvillkoret **Meddelandetyp** för att söka specifikt efter innehåll i Teams.
  
  - Om du vill använda egenskapen **Kind** i en nyckelordsfråga skriver du `kind:microsoftteams` i rutan **Nyckelord** för en sökfråga.

    ![Använda kind:microsoftteams i rutan Nyckelord](../media/O365-ContentSearch-Teams-Keywords.png)
  
  - Om du vill använda ett sökvillkor lägger du till **Meddelandetyp** och använder värdet `microsoftteams`.

    ![Använd villkoret Medddelandetyp med värdet microsoftteams.](../media/O365-ContentSearch-Teams-MessageKindCondition.png)

   Villkor är logiskt kopplade till nyckelordsfrågan med operatorn **AND**. Det innebär att ett objekt måste matcha både nyckelordsfrågan och sökvillkoret för att returneras i sökresultatet. Mer information finns i avsnittet ”Riktlinjer för användning av villkor” i [Nyckelordsfrågor och sökvillkor för innehållssökning.](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)
  
## <a name="searching-yammer-groups"></a>Söka i Yammer-grupper

Du kan använda e-postegenskapen **ItemClass** eller sökvillkoret **Typ** för att söka specifikt efter konversationsobjekt i Yammer-grupper.

  - Om du vill använda egenskapen **ItemClass** i nyckelordsfrågan kan du skriva ett (eller alla) av följande egenskap:värde-par i rutan **Nyckelord** i en sökfråga:

     - ItemClass:IPM.Yammer.message
     - ItemClass:IPM.Yammer.poll
     - ItemClass:IPM.Yammer.praise
     - ItemClass:IPM.Yammer.question
  
    Du kan till exempel använda följande sökfråga för att returnera Yammer-meddelanden och Yammer-beröm:

    ![Söka efter Yammer-objekt med egenskapen ItemClass](../media/YammerContentSearch1.png)
  
  - Du kan också använda e-postvillkoret **Typ** och välja **Yammer-meddelanden** om du vill returnera Yammer-objekt. Följande sökfråga returnerar till exempel alla Yammer-konversationsobjekt som innehåller nyckelordet ”konfidentiellt”. 

    ![Söka efter Yammer-konversationsobjekt med villkorskortet Typ](../media/YammerContentSearch2.png)

## <a name="searching-inactive-mailboxes"></a>Söka i inaktiva postlådor

Du kan söka i inaktiva postlådor i en innehållssökning. Om du vill hämta en lista över inaktiva postlådor i din organisation kör du kommandot `Get-Mailbox -InactiveMailboxOnly` i Exchange Online PowerShell. Du kan också gå till **Informationsstyrning** \> **Kvarhållning** i Säkerhets- och efterlevnadscenter och sedan klicka på **Mer**![Ellips i navigeringsfält](../media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **Inaktiva postlådor**.
  
Här är några saker att tänka på vid sökning i inaktiva postlådor.

- Om en användarpostlåda ingår i en befintlig innehållssökning och den postlådan inaktiveras kommer postlådan fortfarande att ingå i innehållssökningen efter att den har inaktiverats.

- Ibland kan en användare ha en aktiv postlåda och en inaktiv postlåda med samma SMTP-adress. I så fall genomsöks bara den specifika postlåda som du väljer som plats för innehållssökningen. Om du lägger till en användares postlåda i en sökning kan du med andra ord inte ta för givet att både användarens aktiva postlåda och inaktiva postlåda genomsöks. Endast den postlåda som du uttryckligen lägger till i sökningen genomsöks.

- Om du vill söka i en inaktiv postlåda kan du skapa en innehållssökning med hjälp av Säkerhets- och efterlevnadscenter PowerShell. Det gör du genom att lägga till en punkt (. ) före e-postadressen för den inaktiva postlådan. Följande kommando skapar till exempel en innehållssökning som söker i en inaktiv postlåda med e-postadressen pavelb@contoso.onmicrosoft.com:

   ```powershell
   New-ComplianceSearch -Name InactiveMailboxSearch -ExchangeLocation .pavelb@contoso.onmicrosoft.com -AllowNotFoundExchangeLocationsEnabled $true
   ```

- Vi rekommenderar starkt att du undviker att ha en aktiv postlåda och inaktiv postlåda med samma SMTP-adress. Om du behöver återanvända en SMTP-adress som har tilldelats en inaktiv postlåda rekommenderar vi att du återställer den inaktiva postlådan eller återställer innehållet i den inaktiva postlådan till en aktiv postlåda (eller arkivet för en aktiv postlåda) och sedan tar bort den inaktiva postlådan. Mer information finns i något av följande avsnitt:

  - [Återskapa en inaktiv postlåda i Office 365](recover-an-inactive-mailbox.md)

  - [Återställa en inaktiv postlåda i Office 365](restore-an-inactive-mailbox.md)

  - [Ta bort en inaktiv postlåda i Office 365](delete-an-inactive-mailbox.md)

## <a name="searching-disconnected-or-de-licensed-mailboxes"></a>Söka i frånkopplade eller avlicensierade postlådor

Om Exchange Online-licensen (eller hela Microsoft 365-licensen) tas bort från ett användarkonto eller i Azure Active Directory blir användarens postlåda en *frånkopplad* postlåda. Det innebär att postlådan inte längre är kopplad till användarkontot. Det här händer när du söker i frånkopplade postlådor:

- Om licensen tas bort från en postlåda blir postlådan inte längre sökbar. 

- Om en befintlig innehållssökning innehåller en postlåda som licensen har tagits bort för, returneras inga sökresultat från den frånkopplade postlådan om du kör innehållssökningen igen.

- Om du skapar en innehållssökning med cmdleten **New-ComplianceSearch** och anger en frånkopplad postlåda som den Exchange-innehållsplats som du ska söka på, returneras inga sökresultat från den frånkopplade postlådan.

Om du behöver bevara data i en frånkopplad postlåda så att de är sökbara måste du skapa ett bevarande för postlådan innan du tar bort licensen. På så sätt bevaras data och den frånkopplade postlådan är sökbar tills bevarandet tas bort. Mer information finns i [Identifiera typen av undantag som tillämpas på en Exchange Online-postlåda](identify-a-hold-on-an-exchange-online-mailbox.md).

## <a name="searching-for-content-in-a-sharepoint-multi-geo-environment"></a>Söka efter innehåll i en SharePoint Multi-Geo-miljö

Om en eDiscovery-hanterare behöver söka efter innehåll i SharePoint och OneDrive i olika regioner i en [SharePoint Multi-Geo-miljö](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md) måste du göra följande:

1. Skapa ett separat användarkonto för varje satellitgeoplats som eDiscovery-hanteraren behöver söka i. Om du vill söka efter innehåll på webbplatser på den geoplatsen måste eDiscovery-hanteraren logga in på det konto som du skapade för platsen och sedan köra en innehållssökning.

2. Skapa ett sökbehörighetsfilter för varje satellitgeoplats (och motsvarande användarkonto) som eDiscovery-hanteraren behöver söka i. Varje sökbehörighetsfilter begränsar innehållssökningens omfattning till en viss geoplats när eDiscovery-hanteraren är inloggad på det användarkonto som är kopplat till platsen.

> [!TIP]
> Du behöver inte använda den här strategin när du använder sökverktyget i [Advanced eDiscovery](overview-ediscovery-20.md). Det beror på att alla datacenter genomsöks när du söker på SharePoint-webbplatser och i OneDrive-konton i Advanced eDiscovery. Du behöver bara använda den här strategin med regionsspecifika användarkonton och sökbehörighetsfilter när du använder verktyget Innehållssökning och kör sökningar som är associerade med [eDiscovery-fall](./get-started-core-ediscovery.md).

Anta till exempel att en eDiscovery-hanterare behöver söka efter SharePoint- och OneDrive-innehåll på satellitplatser i Nordamerika, Europa och Asien/Stillahavsområdet. Det första steget är att skapa tre användarkonton, ett för varje plats. Nästa steg är att skapa tre sökbehörighetsfilter, ett för varje plats *och* motsvarande användarkonto. Här är exempel på de tre sökbehörighetsfiltren för det här scenariot. I vart och ett av dessa exempel anger **Region** SharePoint-datacentrets plats för denna geo och parametern **Användare** anger motsvarande användarkonto.

**Nordamerika**

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-NAM" -Users ediscovery-nam@contoso.com -Region NAM -Action ALL
```

**Europa**

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-EUR" -Users ediscovery-eur@contoso.com -Region EUR -Action ALL
```

**Asien/Stillahavsområdet**

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-APC" -Users ediscovery-apc@contoso.com -Region APC -Action ALL
```

Tänk på följande när du söker efter innehåll i flera Multi-Geo-miljöer med hjälp av sökbehörighetsfilter:

- Parametern **Region** dirigerar sökningar till den angivna satellitplatsen. Om en eDiscovery-hanterare endast söker på SharePoint- och OneDrive-webbplatser utanför den region som anges i sökbehörighetsfiltret returneras inga sökresultat. 

- Parametern **Region** kontrollerar inte sökningar i Exchange-postlådor. Alla datacenter genomsöks när du söker i postlådor.

Mer information om hur du använder sökbehörighetsfilter i en Multi-Geo-miljö finns i avsnittet ”Söka och exportera innehåll i Multi-Geo-miljöer” i [Konfigurera efterlevnadsgränser för eDiscovery-undersökningar](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments).
