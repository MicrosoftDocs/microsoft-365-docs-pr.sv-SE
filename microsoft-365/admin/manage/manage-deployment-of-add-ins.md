---
title: Hantera distribution av Office 365-tillägg i administrationscentret
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Lär dig att distribuera tillägg till användare och grupper i organisationen med hjälp av centraliserad distribution i administrationscentret.
ms.openlocfilehash: b2fe57bd2b3b51ac5097723613c608580da06bea
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42806552"
---
# <a name="manage-deployment-of-office-365-add-ins-in-the-microsoft-365-admin-center"></a>Hantera distribution av Office 365-tillägg i administrationscentret för Microsoft 365

Office-tillägg hjälper dig att anpassa dina dokument och effektivisera hur du får tillgång till information på webben (se [Börja använda ditt Office-tillägg](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)). Som administratör kan du distribuera Office-tillägg för användarna i organisationen. Du kan göra detta med hjälp av funktionen Centraliserad distribution i administrationscentret för Microsoft 365.
  
Centraliserad distribution är det rekommenderade och mest funktionsrika sättet för de flesta administratörer att distribuera tillägg till användare och grupper inom en organisation. Mer information om hur du tar reda på om din organisation kan stödja centraliserad distribution finns i [Ta reda på om centraliserad distribution av tillägg fungerar för din Office 365-organisation](centralized-deployment-of-add-ins.md).
  
Centraliserad distribution ger följande fördelar:
  
- En global administratör kan tilldela en tilläggsenhet direkt till en användare, till flera användare via en grupp eller till alla i klienten.
    
- När det relevanta Office-programmet startar hämtas tillägget automatiskt för användaren. Om tillägget stöder tilläggskommandon visas tillägget automatiskt i menyfliksområdet i Office-programmet.
    
- Tillägg visas inte längre för användare om administratören inaktiverar eller tar bort tillägget, eller om användaren tas bort från Azure Active Directory eller från en grupp som tillägget har tilldelats.
    
> [!NOTE]
>  För Word använder Excel och PowerPoint en [SharePoint-appkatalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) för att distribuera tillägg till användare i en lokal miljö utan anslutning till Office 365 och/eller support för SharePoint-tillägg som krävs. > För Outlook använder Exchange-kontrollpanelen för att distribuera i en lokal miljö utan anslutning till Office 365. > 
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Rekommenderad metod för distribution av Office-tillägg

Överväg att rulla ut tillägg i en stegvis metod för att säkerställa att din tilläggsdistribution går smidigt. Vi rekommenderar följande plan:
  
1. Distribuera tillägget till en liten uppsättning affärsintressenter och medlemmar på IT-avdelningen. Utvärdera om distributionen lyckades och gå i så fall vidare till steg 2.
    
2. Utrullning till en större uppsättning personer inom företaget som kommer att använda tillägget. Återigen, utvärdera resultat och, om allt gick bra, gå till nästa steg i en fullständig distribution.
    
3. Fullständig utrullning till målgrupp för användare.
    
Beroende på målgruppens storlek kanske du vill lägga till eller ta bort utrullningssteg.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Distribuera ett Office-tillägg med hjälp av administrationscentret

Innan du börjar läser du [Ta reda på om centraliserad distribution av tillägg fungerar för din Office 365-organisation](centralized-deployment-of-add-ins.md).

  
1. Gå till sidan **Inställningar** \> **sÃ¤ndelsen i administrationscentret.**
    
2. Välj **Distribuera tillägg** högst upp på sidan. Välj **Nästa**på översiktssidan.
    
3. Välj ett alternativ och följ instruktionerna.
  
4. Om du har valt alternativet att lägga till ett tillägg från Office Store kan du nu göra ditt tillägg. Observera att du kan visa tillgängliga tillägg via kategorier av Förslag på betyg för **dig,** **Betyg**eller **Namn**. Endast kostnadsfria tillägg finns att lägga till från Office Store. Betalda tillägg stöds inte för närvarande. När du har valt ditt tillägg måste du godkänna ytterligare villkor för att kunna fortsätta. <br/><br/> Med alternativet Office Store görs uppdateringar och förbättringar av tillägget automatiskt tillgängliga för användare utan ditt ingripande.

5. På nästa sida väljer du **Alla,** **Specifika användare/grupper** eller **Bara jag för** att ange vem tillägget ska distribueras till. Använd sökrutan för att hitta de användare eller grupper som du vill distribuera tillägget till. <br/>Läs mer om de andra tillstånden som gäller för ett tillägg. Se [tillägg senare](#add-in-states) i det här avsnittet.
  
6. Välj **Distribuera**.
  
7. En grön bock visas när tillägget har distribuerats. Du kan följa instruktionerna på sidan för att testa att tillägget har distribuerats.

> [!NOTE]
> Användare kan behöva starta om Office för att se tilläggsikonen visas i menyfliksområdet i appen. Det kan ta upp till 12 timmar att visa outlook-tillägg i outlook-menyfliksområdet.
    
8. När du är klar väljer du **Nästa**. Om du har distribuerat till dig själv kan du välja **Ändra vem som har åtkomst till tillägg** för att distribuera till fler användare.



Om du har distribuerat tillägget till andra medlemmar i organisationen än dig själv följer du instruktionerna som visas för att effektivt kunna meddela distributionen av tillägget. <br/>Nu ser du ditt tillägg tillsammans med andra appar i Office 365.
  
Det är en bra idé att informera användare och grupper som du distribuerade tillägget till så att de vet att det är tillgängligt. Överväg att skicka ett e-postmeddelande till dem som beskriver när och hur du använder tillägget och förklarar hur tillägget kan hjälpa dem att göra sitt jobb bättre. Inkludera eller länka till relevant hjälpinnehåll eller vanliga frågor som kan hjälpa om användarna har problem med tillägget.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Överväganden när du tilldelar ett tillägg till användare och grupper

Administratörer kan tilldela ett tillägg till alla eller till specifika användare och grupper. Varje alternativ har konsekvenser:
  
- **Alla:** Som namnet antyder tilldelas det här alternativet tillägget till varje användare i klienten. Använd det här alternativet sparsamt och endast för tillägg som verkligen är universella för din organisation. 
    
- **Användare**: Om du tilldelar ett tillägg till en enskild användare, sedan distribuera tillägget till en ny användare, måste du först lägga till den användaren. Detsamma gäller för att ta bort användare. 
    
- **Grupper**: Om du tilldelar ett tillägg till en grupp tilldelas användare som läggs till i gruppen automatiskt tillägget. Och när en användare tas bort från en grupp förlorar användaren åtkomsttill tillägget. I båda fallen krävs ingen ytterligare åtgärd från dig som administratör. 

- **Bara jag:** Om du tilldelar ett tillägg till bara dig själv, tilldelar detta tillägget till endast ditt konto. Detta är idealiskt om du vill testa tillägget först.
    
Alternativet som är rätt för din organisation beror på din konfiguration. Vi rekommenderar dock att du gör uppdrag via grupper. Som administratör kan det vara lättare att hantera tillägg med hjälp av grupper och styra medlemskap i dessa grupper i stället för att behöva ändra de användare som tilldelats varje gång. Å andra sidan, i vissa situationer, kanske du vill begränsa åtkomsten till en mycket liten uppsättning användare och därmed göra tilldelningar till specifika användare. Därför måste du hantera de tilldelade användarna manuellt.
  
### <a name="add-in-states"></a>Tilläggslägen

Ett tillägg kan antingen vara i **på-** eller **av-tillståndet.**
  
|**Statligt**|**Hur tillståndet inträffar**|**Effekt**|
|:-----|:-----|:-----|
|**Aktiva**  <br/> |Admin laddade upp tillägget och tilldelade det till användare eller grupper.  <br/> |Användare och grupper som tilldelats tillägget ser det i relevanta klienter.  <br/> |
|**Avstängd**  <br/> |Admin har inaktiverat tillägget.  <br/> |Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.  <br/> Om tilläggstillståndet ändras till Aktiv får användarna och grupperna åtkomst till det igen.  <br/> |
|**Deleted**  <br/> |Admin har tagit bort tillägget.  <br/> |Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.  <br/> |
   
Överväg att ta bort ett tillägg om ingen använder det längre. Om du inaktiverar ett tillägg kan det vara meningsfullt om ett tillägg endast används under specifika tider på året.
  
### <a name="security-of-office-add-ins"></a>Office-tillägg för säkerhet

Office-tillägg kombinerar en XML-manifestfil som innehåller vissa metadata om tillägget, men viktigast av allt pekar på ett webbprogram som innehåller all kod och logik. Tillägg kan variera i deras funktioner. Tillägg kan till exempel:
  
- Visa data.
    
- Läs en användares dokument för att tillhandahålla kontextuella tjänster.
    
- Läsa och skriva data till och från en användares dokument för att ge värde till den användaren.
    
Mer information om funktionerna i Office-tillägg finns i [Översikt över Office-tillägg](https://go.microsoft.com/fwlink/p/?linkid=846362), särskilt avsnittet "Anatomi för ett Office-tillägg".
  
Om du vill interagera med användarens dokument måste tillägget deklarera vilken behörighet det behöver i manifestet. En modell för åtkomstbehörigheter för JavaScript-API på fem nivåer ger grunden för sekretess och säkerhet för användare av tillägg till åtgärdsfönstret. Majoriteten av tilläggen i Office Store är skrivdokument på nivå med nästan alla tillägg som stöder minst ReadDocument-nivån. Mer information om behörighetsnivåerna finns i [Begära behörigheter för API-användning i innehålls- och åtgärdsfönstertillägg](https://go.microsoft.com/fwlink/p/?linkid=848863).
  
När du uppdaterar ett manifest är de typiska ändringarna till ett tilläggs ikon och text. Ibland ändras tilläggskommandon. Behörigheterna för tillägget ändras dock inte. Webbprogrammet där all kod och logik för tilläggskörningarkan ändras när som helst, vilket är webbprogrammens natur.
  
Uppdateringar för tillägg sker på följande sätt:
  
- **Tillägg för företagsline-företag:** I det här fallet, där en administratör uttryckligen har laddat upp ett manifest, kräver tillägget att administratören laddar upp en ny manifestfil för att stödja metadataändringar. Nästa gång de relevanta Office-programmen startar uppdateras tillägget. Webbprogrammet kan ändras när som helst. 

    > [!NOTE]
    > Admin behöver inte ta bort ett LOB-tillägg för att göra en uppdatering.   I avsnittet Tillägg kan Admin helt enkelt klicka på LOB-tillägget och välja **uppdateringsknappen** längst ned till höger. Uppdateringen fungerar bara om versionen av det nya tillägget är större än det befintliga tillägget.   
    
- **Office Store-tillägg:** När en administratör har valt ett tillägg från Office Store uppdateras tillägget senare i centraliserad distribution om ett tillägg uppdateras i Office Store. Nästa gång de relevanta Office-programmen startar uppdateras tillägget. Webbprogrammet kan ändras när som helst. 

### <a name="edit-add-in-access"></a>Redigera åtkomst till tillägg

Efter distributionen kan administratörer också ändra användaråtkomsten till tillägg.

1. Gå till sidan **Inställningar** > & tillägg i**administrationscentret.**

2. Markera det distribuerade tillägget.

3. Klicka på **Redigera** under **Vem har Access**.
4. Spara ändringarna.
    
### <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Förhindra hämtningar av tillägg genom att stänga av Office Store för alla klienter (utom Outlook)

> [!NOTE]
> Outlook-tilläggsinstallationen hanteras av en [annan process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).

Som organisation kanske du vill förhindra nedladdning av nya Office-tillägg från Office Store. Detta kan användas tillsammans med centraliserad distribution för att säkerställa att endast organisationsgodkända tillägg distribueras till användare inom organisationen.
  
Så här inaktiverar du inhämtning av tillägg:
  
1. I administrationscentret går du till sidan **Inställningar** \> [Tjänster och tillägg](https://go.microsoft.com/fwlink/p/?linkid=2053743).
    
3. Välj **Användarägda appar och tjänster**.
    
4. Avmarkera alternativet om du vill att användarna ska kunna komma åt Office Store.

Detta förhindrar att alla användare förvärvar följande tillägg från butiken.
  
- Tillägg för Word, Excel och PowerPoint 2016 från:
    
  - Windows
    
  - Mac
    
  - Office
    
  - iOS (endast iPad)
    
- Förvärv som börjar inom **AppSource**
    
- Tillägg i Office 365
    
En användare som försöker komma åt butiken visas följande meddelande: **Tyvärr har Office 365 konfigurerats för att förhindra individuell förvärv av Office Store-tillägg.**
  
Det finns stöd för att stänga av Office Store i följande versioner:
  
- Windows: 16.0.9001 - För närvarande tillgänglig.
    
- Mac: 16.10.18011401 - För närvarande tillgänglig.
    
- iOS: 2.9.18010804 - För närvarande tillgänglig.
    
- Webben - För närvarande tillgänglig.
    
Detta hindrar inte en administratör från att använda centraliserad distribution för att tilldela ett tillägg från Office Store.
  
Om du vill förhindra att en användare loggar in med ett Microsoft-konto kan du begränsa inloggning så att endast organisationskontot används. För mer information, titta [här](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).
 
  
## <a name="minors-and-acquiring-add-ins-from-the-store"></a>Minderåriga och förvärv av tillägg från Store

Den allmänna dataskyddsförordningen (GDPR) är en EU-förordning som träder i kraft den 25 maj 2018. Det ger användarna rätt till och skydd av sina uppgifter. En av aspekterna av GDPR är att minderåriga inte kan få sina personuppgifter skickade till parter som deras förälder eller vårdnadshavare inte har godkänt. Den specifika ålder som definieras som minderårig beror på den region där personen befinner sig.
  
Regioner som har lagstadgade bestämmelser om föräldrarnas samtycke är Förenta staterna, Sydkorea, Storbritannien och Europeiska unionen. För dessa regioner blockeras en minderårig (via Azure Active Directory) från att hämta nya Office-tillägg från Store och köra tillägg som tidigare har förvärvats. För länder utan lagstadgade bestämmelser kommer det inte att finnas några nedladdningsrestriktioner.
  
En användare bedöms vara minderårig baserat på data som anges i Azure Active Directory. Klientadministratören ansvarar för att deklarera den juridiska åldersgruppen och föräldrarnas samtycke till den användaren.
  
Om föräldern/vårdnadshavaren samtycker till ett minderårigt med hjälp av ett visst tillägg kan klientadministratören använda centraliserad distribution för att distribuera tillägget till alla minderåriga som har samtycke.
  
För att vara GDPR-kompatibel för minderåriga måste du se till att en av följande versioner av Office distribueras i din skola/organisation.
  
 **För Word, Excel, PowerPoint och Project:** 
  
|||
|:-----|:-----|
|**Plattform** <br/> |**Bygg nummer** <br/> |
|Office 2016 ProPlus Månadsvis för Windows  <br/> |9001.2138   <br/> |
|Office 2016 ProPlus Halvårsvis  <br/> |8431.2159  <br/> |
|Office 2016 för Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 för Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 för Mac  <br/> |16.11.18020200  <br/> |
|Office 2016 för iOS (endast iPad)  <br/> |2.12.18032600  <br/> |
|Office för webben  <br/> |EJ TILLÄMPLIGT  <br/> |
   
 **För Outlook:** 
  
|||
|:-----|:-----|
|**Plattform** <br/> |**Bygg nummer** <br/> |
|Outlook 2016 för Windows (MSI)  <br/> |Skapa ingen TBD  <br/> |
|Outlook 2016 för Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 för Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook mobile för iOS  <br/> |2.75.0  <br/> |
|Outlook-mobil för Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |EJ TILLÄMPLIGT  <br/> |
   
 **Office 2013-krav**
  
Word, Excel och PowerPoint 2013 för Windows stöder samma mindre kontroller om ADAL (Active Directory Authentication Library) är aktiverat. Det finns två alternativ för efterlevnad, som förklaras härnäst.
  
- **Aktivera ADAL**. I den här artikeln beskrivs hur du aktiverar ADAL för Office 2013: [Använda modern autentisering i Office 365 med Office-klienter](https://support.office.com/article/776c0036-66fd-41cb-8928-5495c0f9168a).<br/>Du måste också ange registernycklarna för att aktivera ADAL enligt beskrivningen i [Aktivera modern autentisering för Office 2013 på Windows-enheter](../security-and-compliance/enable-modern-authentication.md).<br/>Dessutom måste du installera följande apriluppdateringar för Office 2013:
    
  - [Beskrivning av säkerhetsuppdateringen för Office 2013: 10 april 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [3 april 2018, uppdatering för Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Aktivera inte ADAL**. Om du inte kan aktivera ADAL i Office 2013 är vår rekommendation att använda grupprincipen för att stänga av Store för kontorsklienterna. Information om hur du inaktiverar appen för Office-inställningar finns [här](https://technet.microsoft.com/library/cc178992.aspx).
    
## <a name="end-user-experience-with-add-ins"></a>Slutanvändarupplevelse med tillägg

Nu när du har distribuerat tillägget kan slutanvändarna börja använda det i sina Office-program (se [Börja använda ditt Office-tillägg](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)). Tillägget visas på alla plattformar som tillägget stöder.
  
Om tillägget stöder tilläggskommandon visas kommandona i menyfliksområdet i Office. I följande exempel visas kommandot **Sökkällning** för tillägget **Källhänvisningar.** 

![Menyfliksområdet i Office med sökkällningar](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Om det distribuerade tillägget inte stöder tilläggskommandon eller om du vill visa alla distribuerade tillägg kan du visa dem via **Mina tillägg**. 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>I Word 2016, Excel 2016 eller PowerPoint 2016

1. Välj ** \> Infoga mina tillägg**. 
    
2. Välj fliken **Admin Hanterad** i fönstret Office-tillägg. 
    
3. Dubbelklicka på det tillägg som du distribuerade tidigare (i det här exemplet **Citeringar** ). <br/>![Fliken Admin hanterad på sidan Office-tillägg](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>I Outlook

1. Välj Hämta tillägg **i menyfliksområdet**i **menyfliksområdet** hem .<br/>![Knappen Lagra i Outlook](../../media/getaddinsicon.png)
  
2. Välj **Admin-hanterad** i vänster nav.

## <a name="delete-the-add-in"></a>Ta bort tillägget

Du kan också ta bort ett tillägg som har distribuerats.

1. Gå till sidan **Inställningar** > & tillägg i**administrationscentret.**

2. Markera det distribuerade tillägget.

3. Klicka på **Ta bort tillägg**. Ta bort knappen Tillägg i det nedre högra hörnet.
4. Validera dina val och välj **Ta bort tillägg**.
  
## <a name="learn-more"></a>Mer information

Läs mer om hur du skapar och bygger [Office-tillägg](https://go.microsoft.com/fwlink/p/?linkid=846362).
  
[Använd centraliserade PowerShell-cmdlets för distribution för att hantera tillägg](https://support.office.com/article/94f4e86d-b8e5-42dd-b558-e6092f830ec9).
  
[Felsöka: Användaren ser inte tillägg](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
