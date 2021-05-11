---
title: Skapa eDiscovery-kvarhåller i en Core eDiscovery-ärende
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
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Du kan skapa ett bevarande som är kopplat till ett grundläggande e-dataidentifieringsfall i Microsoft 365 för att bevara innehåll som är relevant för en undersökning eller ett juridiskt ärende.
ms.openlocfilehash: 61bbe2e8d2713c2960105e2ec4eb4beffcd4306e
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311628"
---
# <a name="create-an-ediscovery-hold"></a>Skapa en eDiscovery-hold

Du kan använda ett grundläggande eDiscovery-ärende för att skapa innehåll som kan vara relevant för ärendet. Du kan skapa ett väntande Exchange postlådor OneDrive för företag konton för personer som du undersöker i ärendet. Du kan också skapa ett hold för postlådor och webbplatser som är kopplade till Microsoft Teams, Office 365 Grupper och Yammer Grupper. När du placerar innehållsplatser som platser i lager behålls innehållet tills du tar bort innehållsplats från rymmer eller tills du tar bort fråntagna platser.

När du har skapat ett eDiscovery-håll kan det ta upp till 24 timmar innan holden verkställs.

När du skapar ett område kan du välja mellan följande alternativ för att begränsa innehållet som bevaras på de angivna innehållsplatserna:
  
- Skapa ett oändligt håll där allt innehåll på de angivna platserna har satts på en hold-plats. Alternativt kan du skapa ett frågebaserat område där endast innehållet på de angivna platserna som matchar en sökfråga har satts i hold-läge.

- Ange ett datumintervall för att endast bevara innehållet som har skickats, tagits emot eller skapats inom det datumintervallet. Alternativt kan du hålla allt innehåll på angivna platser oavsett när det skickades, togs emot eller skapades.
  
## <a name="how-to-create-an-ediscovery-hold"></a>Så här skapar du ett eDiscovery-håll

Så här skapar du ett eDiscovery-värde som är kopplat till ett Core eDiscovery-ärende:
  
1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com) och logga in med inloggningsuppgifterna för användarkontot som har tilldelats lämpliga eDiscovery-behörigheter.

2. I det vänstra navigeringsfönstret i Microsoft 365 kompatibilitetscenter klickar du på Visa alla **och** sedan på **eDiscovery > Core**.

3. På sidan **Bas-eDiscovery** klickar du på namnet på det ärende som du vill skapa ett sådant ärende i.

4. På startsidan **för** ärendet klickar du på **fliken** Håll.
  
5. På sidan **Håll** klickar du på **Skapa**.

6. På sidan **Namnge din hold-guide** ger du plats åt sidan ett namn, lägger till en valfri beskrivning och klickar sedan på **Nästa.** Namnet på det hållna måste vara unikt inom organisationen.

7. På **sidan Välj platser** i guiden Välj platser väljer du de innehållsplatser som du vill skapa en plats för. Du kan placera postlådor, webbplatser och gemensamma mappar i arkivet.

    ![Välj platser för innehåll som ska vara på plats](../media/eDiscoveryHoldLocations.png)
  
   1. **Exchange postlådor**: Ställ in växlingsknappen på På och klicka sedan på Välj  **användare,** grupper eller team för att ange vilka postlådor som ska vara i paus. Använd sökrutan för att hitta användarnas postlådor och distributionsgrupper (för att skapa ett väntande på postlådorna för gruppmedlemmar). Du kan också placera ett is i den associerade postlådan för ett Microsoft-team, en Office 365 grupp och en Yammer grupp. Mer information om programdata som bevaras när en postlåda ställs i förvaring finns i Innehåll som lagrats i postlådor [för eDiscovery.](what-is-stored-in-exo-mailbox.md)

   1. **SharePoint webbplatser**: Ställ in växlingsknappen på  På och klicka sedan på Välj webbplatser för att SharePoint ange vilka OneDrive-konton som ska vara i paus.  Skriv URL-adressen för varje webbplats som du vill skapa en plats för. Du kan också lägga till URL-adressen för SharePoint för ett Microsoft-team, en Office 365 grupp eller en Yammer grupp.
  
   1. **Exchange mappar :** Ställ in växlingsknappen på **På** om du vill att alla gemensamma mappar Exchange Online organisationen ska vara i holden. Du kan inte välja att vissa gemensamma mappar ska vara på plats. Låt växlingsknappen vara inaktiverad om du inte vill använda gemensamma mappar.

   > [!NOTE]
   > Du måste lägga till minst en innehållsplats i rymmert. Annars visar statistiken för eDiscovery-information om att inga objekt är på plats.

8. När du är klar med att lägga till platser i isen klickar du på **Nästa**.

9. Så här skapar du en frågebaserad holda med nyckelord eller villkor. Klicka på Nästa om du vill behålla allt innehåll på de angivna **innehållsplatserna.**

    ![Skapa ett frågebaserat tillstånd med nyckelord och villkor](../media/eDiscoveryHoldQuery.png)
  
    1. I rutan under **Nyckelord skriver du** en fråga för att bevara endast det innehåll som matchar frågevillkoret. Du kan ange nyckelord, egenskaper för e-postmeddelanden och webbplatsegenskaper, till exempel filnamn. Du kan också använda mer komplexa frågor som använder en boolesk operator som **AND**, **OR** eller **NOT.**

    2. Klicka **på Lägg till** villkor om du vill lägga till ett eller flera villkor för att begränsa frågan för villkoret. Varje villkor lägger till en sats i KQL-sökfrågan som skapas och körs när du skapar villkoret. Du kan till exempel ange ett datumintervall så att e-postmeddelanden eller webbplatsdokument som skapades inom datumintervallet bevaras. Ett villkor är logiskt kopplat till nyckelordsfrågan (anges i **rutan Nyckelord)** och andra villkor av **OCH-operatorn.** Det innebär att objekt måste uppfylla både nyckelordsfrågan och villkoret som ska bevaras.

    Mer information om hur du skapar en sökfråga och använder villkor finns [i Nyckelordsfrågor och sökvillkor för eDiscovery.](keyword-queries-and-search-conditions.md)

10. När du har konfigurerat ett frågebaserat håll klickar du på **Nästa.**

11. Granska dina inställningar (och redigera dem om det behövs) och klicka sedan på **Skicka**.

## <a name="query-based-holds-placed-on-sites"></a>Frågebaserade spärrade platser på webbplatser

Tänk på följande när du placerar ett frågebaserat eDiscovery-kvar på dokument som finns på SharePoint webbplatser:

- Ett frågebaserat bevarande bevarar först alla dokument på en webbplats under en kort tidsperiod efter att de har tagits bort. Det innebär att när ett dokument tas bort flyttas det till biblioteket för bevarande av dokument även om det inte matchar villkoren för det frågebaserade bevarandet. Men borttagna dokument som inte matchar ett frågebaserat bevarande tas bort med ett tidsinställt jobb som bearbetar biblioteket för bevarande av dokument. Det tidsinställda jobbet körs regelbundet och jämför alla dokument i biblioteket för bevarande av dokument med de frågebaserade eDiscovery-objekten (och andra typer av kvarhållnings- och kvarhållningsprinciper). Det tidsinställda jobbet tar bort de dokument som inte matchar ett frågebaserat bevarande och bevarar de dokument som gör det.

- Frågebaserade bevaranden ska inte användas för att bevara dokument i en viss mapp eller på en viss webbplats eller genom att använda andra platsbaserade bevarandevillkor. Det kan leda till oavsiktliga resultat. Vi rekommenderar att du använder icke-platsbaserade bevarandevillkor, till exempel nyckelord, datumintervall eller andra dokumentegenskaper för att bevara webbplatsdokumenten.

## <a name="ediscovery-hold-statistics"></a>statistik för att bli insnäckt för e-dataidentifiering

När du har skapat ett eDiscovery-hold visas information om det nya holden på den utfällande sidan för det markerade antalet. Den här informationen omfattar antalet postlådor och webbplatser som är på plats och statistik om innehållet som har satts i is hold, t.ex. det totala antalet och storleken på objekt som har placerats som väntande och den senaste gången statistik för hållen beräknades. Med hjälp av denna statistik över hållen kan du se hur mycket innehåll som är relaterat till ärendet bevaras.
  
![Hold statistics](../media/eDiscoveryHoldStatistics.png)
  
Tänk på följande när det gäller statistik för eDiscovery-plats:
  
- Det totala antalet objekt som är på plats anger antalet objekt från alla innehållskällor som har satts på plats. Om du har skapat ett frågebaserat rymmer visar den här statistiken antalet objekt som matchar frågan.

- I antalet objekt som är i lager ingår även icke indexerade objekt på innehållsplatserna. Om du skapar ett frågebaserat rymmer sätts alla icke indexerade objekt på innehållsplatserna i lager. Det omfattar icke indexerade objekt som inte uppfyller sökvillkoren för ett frågebaserat område och icke indexerade objekt som kan hamna utanför ett datumintervallsvillkor. Det här skiljer sig från vad som händer när du kör en sökning, där icke indexerade objekt som inte matchar sökfrågan eller utesluts av ett datumintervallvillkor inte tas med i sökresultaten. Mer information om icke indexerade objekt finns i [Delvis indexerade objekt.](partially-indexed-items-in-content-search.md)

- Du kan få fram den  senaste hållna statistiken genom att klicka på Uppdatera statistik för att köra en sökning igen och beräkna det aktuella antalet objekt som är väntande.

- Det är vanligt att antalet objekt som är väntande ökar med tiden eftersom användare vars postlåda eller webbplats är på plats ofta skickar eller tar emot nya e-postmeddelanden och skapar nya dokument i SharePoint och OneDrive.

- Om en Exchange-postlåda, SharePoint-webbplats eller OneDrive-konto flyttas till ett annat område i en geomiljö, tas inte statistiken för webbplatsen med i hold-statistiken. Men innehållet på dessa platser kommer fortfarande att bevaras. Om en postlåda eller webbplats flyttas till en annan region uppdateras inte SMTP-adressen eller URL-adressen som visas i fältet automatiskt. Du måste redigera vänta och uppdatera URL- eller SMTP-adressen så att innehållsplatserna återigen tas med i hold-statistiken

## <a name="search-locations-on-ediscovery-hold"></a>Sökplatser vid eDiscovery-hold

När du [söker efter innehåll](search-for-content-in-core-ediscovery.md) i ett grundläggande eDiscovery-ärende kan du snabbt konfigurera sökningen för att bara söka på de innehållsplatser som är kopplade till ärendet.

Välj alternativet **Platser som är väntande** för att söka efter allt innehåll som har satts i lager. Om ärendet innehåller flera eDiscovery-innehåll kommer innehållsplatserna från allt innehåll att genomsökas när du väljer det här alternativet. Om en innehållsplats dessutom placerades på ett frågebaserat håll kommer endast de objekt som överensstämmer med frågan om att innehålla att sökas igenom när du kör sökningen. Med andra ord returneras endast det innehåll som matchar både villkoret för kvarande och sökvillkoren sökresultatet. Om en användare till exempel placerades i ett frågebaserat ärende som bevarar objekt som skickades eller skapades före ett visst datum skulle bara de objekten genomsökas. Detta sker genom att koppla ärende hold query och sökfrågan av en **OCH-operator.**

Här är några andra saker att tänka på när du söker efter platser vid eDiscovery-hold:

- Om en innehållsplats är en del av flera innehåll som  sätts i samma ärende kombineras frågorna av ELLER-operatorerna när du söker på innehållsplatsen med alternativet Allt ärendeinnehåll. På samma sätt gäller att om en innehållsplats är en del av två olika innehåll, där en är frågebaserad och den andra är ett oändligt område (där allt innehåll är spärrat), blir allt innehåll sök på grund av det oändligt hållna.

- Om en sökning är konfigurerad till att söka efter platser som är väntande och du ändrar ett eDiscovery-värde för ärendet (genom att lägga till eller ta bort en plats eller ändra en fråga om att varan är väntad) uppdateras sökkonfigurationen med de ändringarna. Du måste dock köra sökningen igen efter att hållen ändrats för att uppdatera sökresultaten.

- Om flera eDiscovery-platser som sätts på samma plats i ett e-dataidentifieringsfall och du väljer att söka platser som är spärrade är det maximala antalet nyckelord för sökfrågan 500. Det beror på att sökningen kombinerar alla frågebaserade rymmer genom att använda **operatorn** ELLER. Om det finns fler än 500 nyckelord i de kombinerade frågorna om spärrade frågor och sökfrågan genomsöks allt innehåll i postlådan, inte bara det innehåll som matchar det frågebaserade ärende som finns.

- Om ett lager för eDiscovery har statusen På **(väntande)** kan du fortfarande söka efter platser som är i vänteläge medan vänteläget är aktiverat.

## <a name="preserve-content-in-microsoft-teams"></a>Bevara innehåll i Microsoft Teams

Konversationer som ingår i en Microsoft Teams-kanal lagras i postlådan som är kopplad till Microsoft Team. På samma sätt lagras filer som teammedlemmar delar i en kanal på teamets SharePoint-webbplats. Därför måste du placera grupppostlådan och SharePoint på eDiscovery-plats för att bevara konversationer och filer i en kanal.

Alternativt kan lagras konversationer som ingår i chattlistan i Teams (kallas *1:1-chattar* eller *1:N* gruppchattar) i postlådorna för de användare som deltar i chatten. Och filer som användare delar i chattkonversationer lagras OneDrive användarens konto som delar filen. Du måste därför lägga till de enskilda användarpostlådorna och OneDrive-konton i ett eDiscovery-bevarande för att bevara konversationer och filer i chattlistan. Det är en bra idé att sätta ett område på postlådorna för medlemmar i ett Microsoft-team, förutom att placera grupppostlådan och webbplatsen på plats.

> [!NOTE]
> Om organisationen har en Exchange-hybriddistribution (eller din organisation synkroniserar en lokal Exchange-organisation med Office 365) och har aktiverat Microsoft Teams kan lokala användare använda Teams-chattprogrammet och delta i privat chattar och 1:N-gruppchattar. De här konversationerna lagras i molnbaserad lagring som är kopplat till en lokal användare. Om en lokal användare sätts på ett eDiscovery-område bevaras Teams-chattinnehållet i det molnbaserade lagringsutrymmet. Mer information finns i [Söka efter Teams chattdata för lokala användare](search-cloud-based-mailboxes-for-on-premises-users.md).

Mer information om att bevara Teams innehåll finns i Skapa en Microsoft Teams användare eller ett juridiskt [team.](/MicrosoftTeams/legal-hold)

### <a name="preserve-card-content"></a>Bevara kortinnehåll

På samma sätt lagras kortinnehåll som genereras av appar i Teams-kanaler, 1:1-chattar och 1:N-gruppchattar i postlådor och bevaras när en postlåda sätts på ett eDiscovery-förvaring. Ett *kort* är en användargränssnittsbehållare för ett litet innehåll. Kort kan ha flera egenskaper och bifogade filer och kan innehålla knappar som utlöser kortåtgärder. Mer information finns i [Kort](/microsoftteams/platform/task-modules-and-cards/what-are-cards). Precis som annat Teams-innehåll beror lagringen av kortinnehållet på var kortet användes. Innehållet för kort som används i en Teams-kanal lagras i Teams-gruppostlådan. Kortinnehållet för enskilda chattar och gruppchattar lagras i chattdeltagarnas postlådor.

### <a name="preserve-meeting-and-call-information"></a>Bevara mötesinformation och samtalsinformation

Sammanfattningsinformation för möten och samtal i en Teams lagras också i postlådorna för användare som ringt in till mötet eller samtalet. Det här innehållet bevaras också när ett eDiscovery-väntande sätts på användarnas postlådor.

### <a name="preserve-content-in-private-channels"></a>Bevara innehåll i privata kanaler

Från och med februari 2020 har vi också aktiverat möjligheten att bevara innehåll i privata kanaler. Eftersom privata kanalchattar lagras i chattdeltagarnas postlådor, bevarar du privata kanalchattar genom att placera en användarpostlåda på eDiscovery-plats. Och om en användarpostlåda placerades på ett eDiscovery-parkering före februari 2020 kommer lagringen nu att gälla automatiskt för privata kanalmeddelanden som lagrats i den postlådan. Bevarande av filer som delas i privata kanaler stöds också.

### <a name="preserve-wiki-content"></a>Bevara wiki-innehåll

Alla team- och teamkanaler innehåller även en Wiki för anteckningar och samarbete. Wiki-innehållet sparas automatiskt i en MHT-fil. Den här filen lagras i dokumentbiblioteket för Teams-wikidata på teamets SharePoint-webbplats. Du kan bevara wiki-innehållet genom att lägga till teamets webbplats SharePoint ett eDiscovery-område.

> [!NOTE]
> Den 22 juni 2017 släpptes funktionen för att bevara Wiki-innehåll för en team- eller teamkanal (när du placerar teamets SharePoint-webbplats på plats). Om en gruppwebbplats är på plats behålls Wiki-innehållet från och med det datumet. Men om en gruppwebbplats är på plats och wiki-innehållet togs bort före den 22 juni 2017, behålls inte Wiki-innehållet.

### <a name="office-365-groups"></a>Grupper i Office 365

Teams bygger på Office 365 grupper. Att placera Office 365 grupper i ett eDiscovery-innehåll liknar att skapa Teams på plats.

Tänk på följande när du placerar både Teams och Office 365 grupper i ett eDiscovery-väntande:

- Om du vill placera innehåll i Teams och Office 365 Grupper i en grupp, på en plats, måste du ange postlådan och SharePoint webbplats som är kopplad till en grupp eller ett team.

- Kör **cmdlet:en Get-UnifiedGroup** i [Exchange Online PowerShell för](/powershell/exchange/connect-to-exchange-online-powershell) att visa egenskaper Teams och Office 365 Grupper. Det här är ett bra sätt att hämta URL-adressen för webbplatsen som är kopplad till en grupp eller Office 365 grupp. Följande kommando visar till exempel valda egenskaper för en Office 365 som heter Senior Leadership Team:

    ```text
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > För att kunna köra cmdleten **Get-UnifiedGroup** måste du ha tilldelats rollen View-Only Recipients i Exchange Online eller vara medlem i en rollgrupp som har tilldelats rollen View-Only Recipients. 
  
- När en användares postlåda genomsöks genomsöks inte Office 365 grupp som användaren är medlem i. Och när du placerar en grupp- eller Office 365-grupp i eDiscovery-område är det endast grupppostlådan och gruppwebbplatsen som är väntad. Postlådorna och OneDrive för företag gruppmedlemmarna är inte undantagna om du inte uttryckligen lägger till dem i eDiscovery-undantagen. Om du av juridiska skäl måste använda en grupp- eller Office 365-grupp som grupp kan du lägga till postlådorna och OneDrive-kontona för grupp- eller gruppmedlemmar i samma grupp.

- Om du vill visa en lista över medlemmar i Office 365 grupp kan  du visa egenskaperna på sidan Grupper i Microsoft 365 administrationscenter. Eller så kan du köra följande kommando i Exchange Online PowerShell:

    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
    ```

    > [!NOTE]
    > För att kunna köra cmdleten **Get-UnifiedGroupLinks** måste du ha tilldelats rollen View-Only Recipients i Exchange Online eller vara medlem i en rollgrupp som har tilldelats rollen View-Only Recipients.

## <a name="preserve-content-in-onedrive-accounts"></a>Bevara innehåll i OneDrive konton

Om du vill samla in en lista med URL:er för OneDrive för företag-webbplatserna i organisationen så att du kan lägga till dem i ett väntande eller söka kopplat till ett e-dataidentifieringsfall, se Skapa en lista över alla [OneDrive platser i organisationen.](/onedrive/list-onedrive-urls) Skriptet i den här artikeln skapar en textfil som innehåller en lista över alla OneDrive webbplatser i organisationen. Om du vill köra det här skriptet måste du installera och använda SharePoint Online Management Shell. Se till att du lägger till URL-adressen för organisationens Min Webbplats-domän för alla OneDrive-webbplatser som du vill söka på. Det här är domänen som innehåller alla dina OneDrive-webbplatser, till exempel `https://contoso-my.sharepoint.com`. Exempel på en URL-adress för en användares OneDrive-webbplats: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.

> [!IMPORTANT]
> URL-adressen för en användares OneDrive konto innehåller användarens huvudnamn (UPN) (till `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` exempel). I de sällsynta fall då en persons UPN ändras ändras även OneDrive URL:en så att det nya UPN ingår. Om en användares OneDrive-konto är en del av ett eDiscovery-konto, gammalt och användarens UPN ändras, måste du uppdatera tillägget och du måste uppdatera tillägget och lägga till användarens nya URL för OneDrive och ta bort den gamla. Mer information finns i [Hur UPN-ändringar påverkar OneDrive-URL:en](/onedrive/upn-changes).

## <a name="removing-content-locations-from-an-ediscovery-hold"></a>Ta bort innehållsplatser från en eDiscovery-plats

När en postlåda, SharePoint webbplats eller ett OneDrive-konto tas bort från ett eDiscovery-område tillämpas *ett fördröjnings* kunna tillämpas. Det innebär att den faktiska borttagningen av holden fördröjs i 30 dagar för att förhindra att data tas bort permanent (rensas) från en innehållsplats. Det ger administratörer en möjlighet att söka efter eller återställa innehåll som kommer att rensas efter att ett eDiscovery-innehåll tagits bort. Information om hur fördröjnings hold fungerar för postlådor och webbplatser skiljer sig åt.

- **Postlådor:** Ett väntande fel placeras i en postlåda nästa gång assistenten för hanterade mappar bearbetar postlådan och upptäcker att ett eDiscovery-kvart har tagits bort. Specifikt tillämpas ett väntande på en postlåda när assistenten för hanterade mappar anger något av följande egenskaper för postlådan till **Sant:**

   - **DelayHoldApplied:** Den här egenskapen gäller e-postrelaterat innehåll (som genereras av personer som använder Outlook och Outlook på webben) som lagras i en användares postlåda.

   - **DelayReleaseHoldApplied:** Den här egenskapen gäller molnbaserat innehåll (som genereras av icke-Outlook-appar som Microsoft Teams, Microsoft Forms och Microsoft Yammer) som lagras i en användares postlåda. Molndata som genereras av en Microsoft-app lagras vanligtvis i en dold mapp i en användares postlåda.

   När ett bevarande av en fördröjning sätts för postlådan (när någon av de tidigare egenskaperna har ställts in på **Sant)** anses postlådan fortfarande vara väntad med obegränsad bevarandetid som om postlådan hade bevarande av juridiska skäl. Efter 30 dagar går undantaget ut och Microsoft 365 försöker automatiskt ta bort undantaget (genom att sätta egenskapen DelayHoldApplied eller DelayReleaseHoldApplied till **False**) så att undantaget tas bort. När någon av dessa egenskaper har angetts till **False** rensas motsvarande objekt som har markerats för borttagning nästa gång postlådan bearbetas av assistenten för hanterade mappar.

   Mer information finns i Hantera [postlådor som är väntande](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

- **SharePoint och OneDrive webbplatser:** Alla SharePoint eller OneDrive innehåll som behålls i biblioteket för bevarande av dokument tas inte bort under fördröjningsperioden på 30 dagar efter att en webbplats har tagits bort från ett eDiscovery-bevarande. Det här påminner om vad som händer när en webbplats släpps från en bevarandeprincip. Dessutom kan du inte ta bort innehållet manuellt i biblioteket för bevarande av dokument under fördröjningsperioden på 30 dagar. 

   Mer information finns i Släppa [en princip för bevarande.](retention.md#releasing-a-policy-for-retention)

Ett väntande ärende tillämpas även på platser som är spärrade när du stänger en eDiscovery-basfall, eftersom innehåll som sätts i innehåll är inaktiverat när ett ärende stängs. Mer information om hur du stänger ett ärende finns i [Stänga, öppna och ta bort ett Core eDiscovery-ärende.](close-reopen-delete-core-ediscovery-cases.md)

## <a name="ediscovery-hold-limits"></a>Begränsningar för eDiscovery-hold

I följande tabell finns begränsningar för eDiscovery-ärenden och e-dataidentifieringsärenden.

  | Beskrivning av gräns | Gräns |
  |:-----|:-----|
  |Maximalt antal ärenden för en organisation.  <br/> |Ingen gräns  <br/> |
  |Maximalt antal eDiscovery-rymmer för en organisation.  <br/> |10 000  <br/> |
  |Maximalt antal postlådor i ett enstaka eDiscovery-hold. Den här gränsen omfattar totalt antal användarpostlådor och postlådorna som är kopplade Microsoft 365 grupper, Microsoft Teams och Yammer grupper.  <br/> |1 000  <br/> |
  |Maximalt antal webbplatser i ett enstaka eDiscovery-hold. Den här gränsen omfattar det totala antalet OneDrive för företag, SharePoint webbplatser och webbplatser som är kopplade till grupper Microsoft 365, Microsoft Teams och Yammer grupper.  <br/> |100  <br/> |
  |Maximalt antal ärenden som visas på eDiscovery-startsidan och det maximala antalet objekt som visas på flikarna Spärrar, Sökningar och Exportera i ett ärende. <sup>1</sup> |1 000|
  |||

   > [!NOTE]
   > <sup>1</sup> Om du vill visa en lista över mer än 1 000 ärenden, spärrade ärenden, sökningar eller exporter kan du använda motsvarande PowerShell-cmdlet Office 365 Security & Compliance:
   >
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)
