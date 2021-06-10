---
title: Hantera spärrade Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Lär dig hur du placerar innehåll i biblioteken och deras datakällor för att bevara relevant innehåll för ditt Advanced eDiscovery fall.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 70390a933de788a6b1190e42b5087b85a175b9a2
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "52162633"
---
# <a name="manage-holds-in-advanced-ediscovery"></a>Hantera spärrade Advanced eDiscovery

Du kan använda ett Advanced eDiscovery för att skapa innehåll som kan vara relevant för ditt ärende. Med hjälp Advanced eDiscovery kan du placera plats för bibliotekserare och deras datakällor. Dessutom kan du placera ett icke-förinhållet förvaring för postlådor och OneDrive för företag webbplatser. Du kan också placera ett område på grupppostlådan, på SharePoint webbplats och på OneDrive för företag webbplats för en Microsoft 365 grupp. På samma sätt kan du placera ett område på postlådan och webbplatsen som är kopplade till Microsoft Teams. När du placerar innehållsplatser i förvaring behålls innehållet tills du släpper den som äger innehållet, tar bort en specifik dataplats eller tar bort principen för förvaring helt och hållet.

## <a name="manage-custodian-based-holds"></a>Hantera innnniskt kvarhållen plats

I vissa fall kanske du har en uppsättning vårdnadshavare som du har identifierat och har beslutat att bevara deras data i samband med detta ärende. I Advanced eDiscovery exempel läggs användaren och de valda datakällorna automatiskt till i en princip för att vara vårdnadshavare.

Så här visar du principen för den som håller i den hären:

1. I kompatibilitetscentret Microsoft 365 du på **eDiscovery > Avancerat för** att visa en lista över ärenden i organisationen.

2. Gå till fliken **Källor för** att lägga till tabellerna i ditt ärende. Mer information om hur du kan lägga till och placera den andre i ett Advanced eDiscovery fall finns i Lägga till vårdnadshavare [för ett ärende.](add-custodians-to-case.md) Om du redan har lagt till målsare och lagt till dem i förvaring, går du till steg 3.

3. Gå till fliken **Inhåll** och klicka **på Det duknarna Fäst. \<HoldId>**

4. På den utfällade sidan visas statistik för principen. Du kan också utföra åtgärder som att tillämpa en fråga på din egen förvaring. Mer information om hur du skapar en hold-fråga och använder villkor finns [i Nyckelordsfrågor och sökvillkor för Innehållssökning.](keyword-queries-and-search-conditions.md)

## <a name="manage-non-custodial-holds"></a>Hantera icke-sövade kvarhåll

När du skapar ett område kan du välja mellan följande alternativ för att begränsa innehållet som hålls på de angivna innehållsplatserna:

- Du skapar ett oändligt område där allt innehåll har satts på plats. Alternativt kan du skapa ett frågebaserat rymmer där endast innehåll som överensstämmer med en sökfråga sätts i hold-tid.
  
- Du kan ange ett datumintervall för endast innehåll som har skickats, tagits emot eller skapats inom det datumintervallet. Du kan också välja att behålla allt innehåll oavsett när det skickades, togs emot eller skapades.

Så här skapar du ett icke-avsenings hold för ett Advanced eDiscovery fall:

1. I kompatibilitetscentret Microsoft 365 du på **eDiscovery > Avancerat för** att visa en lista över ärenden i organisationen.
  
2. Klicka **på** Öppna bredvid det ärende som du vill skapa plats för.
  
3. På startsidan för ärendet klickar du på fliken **Spärrar.**
  
4. På fliken **Spärrar** klickar du på **Skapa**.
  
5. Ge **håll platsnamnet** på sidan Namnge din plats. Namnet på det hållna måste vara unikt inom organisationen.
 
6. (Valfritt) I rutan **Beskrivning** lägger du till en beskrivning av hållen.
  
7. Klicka på **Nästa**.
  
8. Välj de innehållsplatser som du vill skapa en plats för. Du kan placera postlådor, webbplatser och gemensamma mappar i arkivet.

   1. **Exchange -e-post** – Klicka på Välj **användare,** grupper eller team och klicka sedan på Välj **användare,** grupper eller team igen för att ange vilka postlådor som ska vara på plats. Använd sökrutan för att hitta användarpostlådor och distributionsgrupper (för att undanta gruppmedlemmars postlådor) som ska uteslutas. Du kan också placera ett hold på den associerade postlådan för en Microsoft 365 grupp eller ett Microsoft Team. Markera kryssrutan användare, grupp och grupp, klicka **på Välj** och klicka sedan på **Klar**.
 
      > [!NOTE]
      > När du klickar **på Välj användare,** grupper eller team för att ange vilka postlådor som ska markeras som väntande är postlådeväljaren som visas tom. Det här är för att förbättra prestandan. Om du vill lägga till personer i den här listan skriver du ett namn (minst 3 tecken) i sökrutan.

   1. **SharePoint webbplatser** – klicka  på Välj  webbplatser och klicka sedan på Välj webbplatser igen för att SharePoint ange OneDrive för företag webbplatser som ska vara i holden. Skriv in URL-adressen för varje webbplats som du vill utesluta. Du kan också lägga till URL-adressen för SharePoint för en Microsoft 365 grupp eller ett Microsoft-team. Klicka **på** Välj och sedan på **Klar**.

      > [!NOTE]
      > URL-adressen för en användares OneDrive konto innehåller användarens huvudnamn (UPN) (till `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` exempel). I de sällsynta fall då en persons UPN ändras ändras även OneDrive URL:en så att det nya UPN ingår. Om en användares OneDrive-konto ingår i ett icke-inträktande förvaring och deras UPN ändras måste du uppdatera förvaringen och peka på den nya OneDrive URL. Mer information finns i [Hur UPN-ändringar påverkar OneDrive-URL:en](/onedrive/upn-changes).

   1. **Exchange mappar –** Flytta växlingsknappen till positionen Alla för att placera alla gemensamma mappar i Exchange Online organisationen på plats. Observera att du inte kan välja att vissa gemensamma mappar ska vara på plats. Låt växlingsknappen vara inställd **på** Ingen om du inte vill använda gemensamma mappar.

9. När du är klar med att lägga till innehållsplatser i rymmer klickar du på **Nästa**.
  
10. Så här skapar du ett frågebaserat tillstånd med villkor: Annars klickar du bara på **Nästa.**
    
    - I rutan under **Nyckelord skriver** du en sökfråga i rutan så att endast det innehåll som uppfyller sökvillkoren har satts i fält. Du kan ange nyckelord, meddelandeegenskaper eller dokumentegenskaper, till exempel filnamn. Du kan också använda mer komplexa frågor som använder en boolesk operator som AND, OR eller NOT. Om du lämnar nyckelordsrutan tom kommer allt innehåll på de angivna innehållsplatserna att släppas.

    - Klicka  **på** Lägg till villkor om du vill lägga till ett eller flera villkor för att begränsa sökningen efter holden. Varje villkor lägger till en sats i KQL-sökfrågan som skapas och körs när du skapar villkoret. Du kan till exempel ange ett datumintervall så att e-postmeddelanden eller webbplatsdokument som skapats inom det datumintervallet sätts på plats. Ett villkor är logiskt kopplat till nyckelordsfrågan (anges i nyckelordsrutan) av operatorn OCH. Det innebär att objekt måste uppfylla både nyckelordsfrågan och villkoret som ska släppas.

     Mer information om hur du skapar en sökfråga och använder villkor finns [i Nyckelordsfrågor och sökvillkor för Innehållssökning.](/office365/SecurityCompliance/keyword-queries-and-search-conditions)

11. När du har konfigurerat ett frågebaserat håll klickar du på **Nästa.**

12. Granska inställningarna och klicka sedan på Skapa **det här standardinställningarna**.

## <a name="view-hold-statistics"></a>Visa statistik för håll

Efter en stund visas information om det nya spärrade objektet i informationsfönstret på **fliken** Spärrar för det valda spärrade objektet. Den här informationen omfattar antalet postlådor och webbplatser som är på plats och statistik om innehållet som har satts i is hold, t.ex. det totala antalet och storleken på objekt som har placerats som väntande och den senaste gången statistik för hållen beräknades. Med hjälp av den här statistiken kan du se hur mycket innehåll som är relaterat till eDiscovery-ärendet hålls kvar.

Tänk på följande när det gäller att samla in statistik:

- Det totala antalet objekt som är på plats anger antalet objekt från alla innehållskällor som har satts på plats. Om du har skapat ett frågebaserat rymmer visar den här statistiken antalet objekt som matchar frågan.
  
- I antalet objekt som är i lager ingår även icke indexerade objekt på innehållsplatserna. Observera att om du skapar ett frågebaserat rymmer, sätts alla icke indexerade objekt på innehållsplatserna i lager. Det omfattar icke indexerade objekt som inte uppfyller sökvillkoren för ett frågebaserat område och icke indexerade objekt som kan hamna utanför ett datumintervallsvillkor. Det här skiljer sig från vad som händer när du kör en innehållssökning, där icke indexerade objekt som inte matchar sökfrågan eller exkluderas av ett datumintervallvillkor inte inkluderas i sökresultaten. Mer information om icke indexerade objekt finns i [Delvis indexerade objekt i Innehållssökning i Office 365.](partially-indexed-items-in-content-search.md) 

- Du kan få fram den senaste hållna statistiken genom att klicka på Uppdatera statistik för att köra en sökberäkning som beräknar det aktuella antalet objekt som är väntande.

- Om det behövs klickar du på Uppdatera i verktygsfältet för att uppdatera statistik för hållen i informationsfönstret.

- Det är vanligt att antalet objekt som är på plats ökar med tiden eftersom användare vars postlåda eller webbplats är på plats ofta skickar eller tar emot nya e-postmeddelanden och SharePoint och OneDrive för företag dokument.

- Om en SharePoint-webbplats eller ett OneDrive-konto flyttas till ett annat område i en geomiljö, tas inte statistiken för den webbplatsen med i hold-statistiken. Innehållet på webbplatsen är dock fortfarande på plats. Om en webbplats flyttas till en annan region uppdateras inte URL-adressen som visas i platsen. Du måste redigera url-adressen för att kunna hålla kvar och uppdatera den.

## <a name="place-a-hold-on-microsoft-teams-and-office-365-groups"></a>Skapa ett väntande Microsoft Teams och Office 365 grupper

Microsoft Teams bygger på Office 365 grupper. Att sätta dem i is i Advanced eDiscovery påminner mycket om dem.

- **Hur mappar jag ytterligare en Microsoft 365 grupper eller Microsoft Teams webbplats till en vårdnadshavare? Och hur gör jag för att sätta ett annat håll för Microsoft 365 grupper och Microsoft Teams?** Microsoft Teams bygger på Microsoft 365 grupper. Att sätta dem i ett eDiscovery-ärende är därför snarlikt. Tänk på följande när du placerar Microsoft 365 grupper och Microsoft Teams på plats.
  - Om du vill placera innehåll Microsoft 365 grupper och Microsoft Teams i en grupp måste du ange postlådan och SharePoint som är kopplade till en grupp eller ett team.
  
  - Kör **cmdlet:en Get-UnifiedGroup** i Exchange Online vill visa egenskaper för en Microsoft 365 grupp eller Microsoft Team. Det här är ett bra sätt att få webbadressen för webbplatsen som är kopplad till en Microsoft 365 grupp eller ett Microsoft-team. Följande kommando visar till exempel valda egenskaper för en Microsoft 365 som heter Ledningsgrupp:


    ```console
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > För att kunna köra cmdleten Get-UnifiedGroup måste du ha tilldelats rollen View-Only Recipients i Exchange Online eller vara medlem i en rollgrupp som har tilldelats rollen View-Only Recipients.

 - När en användares postlåda genomsöks genomsöks Microsoft 365 grupp eller Microsoft Team som användaren är medlem i. På samma sätt gäller att när du placerar Microsoft 365 grupp- eller Microsoft-gruppplats är det bara grupppostlådan och gruppwebbplatsen som är väntad. Postlådorna och OneDrive för företag gruppmedlemmarna är inte undantagna såvida du inte uttryckligen lägger till dem som brevlådor eller placerar deras datakällor på undantag. Om du behöver använda en Microsoft 365-grupp eller Microsoft-team som förvaring för en specifik vårdnadshavare kan du därför mappa gruppwebbplatsen och grupppostlådan till den insmfördel han/hon (se Hantera biblioteksmedlemmar i Advanced eDiscovery). Om Microsoft 365 grupp eller Microsoft-team inte är utkällbart till en enda person, bör du överväga att lägga till källan i ett icke-ljudhav. 
 
 - Om du vill visa en lista över medlemmarna i en Microsoft 365-grupp eller Microsoft Team kan du visa egenskaperna på sidan Start > Grupper i Microsoft 365 administrationscenter. Eller så kan du köra följande kommando i Exchange Online PowerShell:

   ```powershell
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > För att kunna köra cmdleten **Get-UnifiedGroupLinks** måste du ha tilldelats rollen View-Only Recipients i Exchange Online eller vara medlem i en rollgrupp som har tilldelats rollen View-Only Recipients.

- Kanalkonversationer som ingår i en Microsoft Teams lagras i postlådan som är kopplad till teamet. På samma sätt lagras filer som teammedlemmar delar i en kanal på teamets SharePoint-webbplats. Därför måste du placera Microsoft Team-postlådan och en SharePoint på plats för att behålla konversationer och filer i en kanal.
  
- Du kan också lagra konversationer som finns med i Microsoft Teams chatt i postlådan för användaren som deltar i chatten.  Filer som en användare delar i chattkonversationer lagras OneDrive för företag på den användare som delar filen. Därför måste du placera de enskilda användarnas postlådor och OneDrive för företag på platser för att behålla konversationer och filer i chattlistan. 
  
- Alla Microsoft Team- eller teamkanaler innehåller en Wiki för anteckningar och samarbete. Wiki-innehållet sparas automatiskt i en MHT-fil. Den här filen lagras i dokumentbiblioteket för Teams-wikidata på teamets SharePoint-webbplats. Du kan placera innehållet på Wiki-webbplatsen i stället genom att placera teamets SharePoint webbplats på plats.

  > [!NOTE]
  > Funktionen för att behålla Wiki-innehåll för ett Microsoft-team eller en teamkanal (när du placerar teamets SharePoint-webbplats på plats) släpptes den 22 juni 2017. Om en gruppwebbplats är på plats behålls Wiki-innehållet från och med det datumet. Men om en gruppwebbplats är på plats och wiki-innehållet togs bort före den 22 juni 2017 fanns inte wiki-innehållet kvar.
