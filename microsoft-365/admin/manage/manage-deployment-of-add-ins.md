---
title: Hantera distribution av tillägg i administrationscentret
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Lär dig att distribuera tillägg till användare och grupper i organisationen med hjälp av Centraliserad distribution i administrationscentret.
ms.openlocfilehash: e71afad19690d3a05dc5f06bc0718861cb22f12d
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399734"
---
# <a name="manage-deployment-of-add-ins-in-the-microsoft-365-admin-center"></a>Hantera distribution av tillägg i Administrationscenter för Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Office-tillägg hjälper dig att anpassa dina dokument och effektivisera ditt sätt att komma åt information på webben (se [Börja använda Office-tillägget](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)). Som administratör kan du distribuera Office-tillägg för användarna i organisationen. Du kan göra detta med hjälp av funktionen Centraliserad distribution i Microsoft 365 administrationscenter.
  
Centraliserad distribution är det rekommenderade och mest funktionsrika sättet för de flesta administratörer att distribuera tillägg till användare och grupper inom en organisation. Mer information om hur du tar reda på om din organisation kan stödja centraliserad distribution finns [i Avgöra om centraliserad distribution av tillägg fungerar för din organisation](centralized-deployment-of-add-ins.md).
  
Centraliserad distribution ger följande fördelar:
  
- En global administratör kan tilldela ett tillägg direkt till en användare, till flera användare via en grupp eller till alla i klienten.
    
- När det aktuella Office-programmet startar hämtas tillägget automatiskt för användaren. Om tillägget stöder tilläggskommandon visas tillägget automatiskt i menyfliksområdet i Office-programmet.
    
- Tillägg visas inte längre för användare om administratören inaktiverar eller tar bort tillägget, eller om användaren tas bort från Azure Active Directory eller från en grupp som tillägget har tilldelats.
    
> [!NOTE]
>  För Word, Excel och PowerPoint används en [SharePoint-appkatalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) för att distribuera tillägg till användare i en lokal miljö utan anslutning till Microsoft 365 och/eller stöd för SharePoint-tillägg som krävs. > För Outlook använder Exchange-kontrollpanelen för att distribuera i en lokal miljö utan anslutning till Microsoft 365. > 
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Rekommenderad metod för distribution av Office-tillägg

Överväg att distribuera tillägg i en stegvis metod för att se till att distributionen av tillägget fungerar smidigt. Vi rekommenderar följande plan:
  
1. Rulla ut tillägget till en liten uppsättning affärsintressenter och medlemmar på IT-avdelningen. Utvärdera om distributionen lyckades och gå i så fall vidare till steg 2.
    
2. Utbyggnad till en större uppsättning individer inom företaget som kommer att använda tillägget. Återigen utvärdera resultat och, om allt gick bra, gå till nästa steg i en fullständig distribution.
    
3. Fullständig utrullning för att rikta målgruppen för användare.
    
Beroende på målgruppens storlek kanske du vill lägga till eller ta bort utrullningssteg.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Distribuera ett Office-tillägg med administrationscentret

Innan du börjar läser du [Ta reda på om centraliserad distribution av tillägg fungerar för din organisation](centralized-deployment-of-add-ins.md).

  
1. Gå till sidan Inställningar **Settings** \> **i administrationscentret.**
    
2. Välj **Distribuera tillägg** högst upp på sidan. På översiktssidan väljer du **Nästa**.
    
3. Välj ett alternativ och följ instruktionerna.
  
4. Om du valde alternativet att lägga till ett tillägg från Office Store kan du nu göra ditt tilläggsval. Observera att du kan visa tillgängliga tillägg via kategorier av **Förslag för dig,** **Betyg**eller **Namn**. Det finns bara kostnadsfria tillägg att lägga till från Office Store. Betalda tillägg stöds inte för närvarande. När du har valt ditt tillägg måste du godkänna några ytterligare villkor för att kunna fortsätta. <br/><br/> Med alternativet Office Store görs uppdateringar och förbättringar av tillägget automatiskt tillgängliga för användare utan att du behöver göra något.

5. På nästa sida väljer du **Alla,** **Specifika användare/grupper** eller **Bara jag** för att ange vem tillägget ska distribueras till. Använd sökrutan för att hitta de användare eller grupper som du vill distribuera tillägget till. <br/>Läs om de andra tillstånd som gäller för ett tillägg. Se [Tilläggstillstånd](#add-in-states) senare i det här avsnittet.
  
6. Välj **Distribuera**.
  
7. En grön bock visas när tillägget har distribuerats. Du kan följa instruktionerna på sidan för att testa att tillägget har distribuerats.

> [!NOTE]
> Användare kan behöva starta om Office för att se att tilläggsikonen visas i menyfliksområdet i appen. Det kan ta upp till 12 timmar innan Outlook-tillägg visas i användarnas menyfliksområdet.
    
8. När du är klar väljer du **Nästa**. Om du har distribuerat till bara dig själv kan du välja **Ändra vem som har åtkomst till tillägget** för att distribuera till fler användare.



Om du har distribuerat tillägget till andra medlemmar i organisationen följer du instruktionerna som visas för att effektivt meddela distributionen av tillägget. <br/>Nu visas ditt tillägg tillsammans med andra appar i Microsoft 365.
  
Det är en bra idé att informera de användare och grupper som du distribuerade tillägget till så att de vet att det är tillgängligt. Överväg att skicka ett e-postmeddelande till dem som beskriver när och hur du använder tillägget och förklarar hur tillägget kan hjälpa dem att göra sitt jobb bättre. Inkludera eller länka till relevant hjälpinnehåll eller vanliga frågor som kan hjälpa till om användarna har problem med tillägget.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Överväganden när du tilldelar ett tillägg till användare och grupper

Administratörer kan tilldela ett tillägg till alla eller till specifika användare och grupper. Varje alternativ har konsekvenser:
  
- **Alla**: Som namnet antyder tilldelar det här alternativet tillägget till varje användare i klienten. Använd det här alternativet sparsamt och endast för tillägg som verkligen är universella för din organisation. 
    
- **Användare**: Om du tilldelar ett tillägg till en enskild användare och sedan distribuerar tillägget till en ny användare måste du först lägga till den användaren. Detsamma gäller för att ta bort användare. 
    
- **Grupper**: Om du tilldelar ett tillägg till en grupp tilldelas användare som läggs till i gruppen automatiskt tillägget. Och när en användare tas bort från en grupp förlorar användaren åtkomst till tillägget. I båda fallen krävs ingen ytterligare åtgärd från dig som administratör. 

- **Bara jag:** Om du tilldelar ett tillägg till bara dig själv, tilldelar detta tillägget till endast ditt konto. Detta är idealiskt om du vill testa tillägget först.
    
Vilket alternativ som är rätt för din organisation beror på din konfiguration. Vi rekommenderar dock att du gör uppdrag via grupper. Som administratör kan det vara enklare att hantera tillägg med hjälp av grupper och styra medlemskapet i dessa grupper i stället för att behöva ändra de användare som tilldelas varje gång. Å andra sidan, i vissa situationer, kanske du vill begränsa åtkomsten till en mycket liten uppsättning användare och därför göra tilldelningar till specifika användare. Därför måste du hantera de tilldelade användarna manuellt.
  
### <a name="add-in-states"></a>Tilläggstillstånd

Ett tillägg kan antingen vara i läget **På** eller **Av.**
  
|**Statligt**|**Hur tillståndet inträffar**|**Effekt**|
|:-----|:-----|:-----|
|**Aktiva**  <br/> |Admin laddade upp tillägget och tilldelade det till användare eller grupper.  <br/> |Användare och grupper som tilldelats tillägget ser det i relevanta klienter.  <br/> |
|**Avstängd**  <br/> |Admin har inaktiverat tillägget.  <br/> |Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.  <br/> Om tilläggstillståndet ändras till Aktiv har användarna och grupperna åtkomst till det igen.  <br/> |
|**Deleted**  <br/> |Admin har tagit bort tillägget.  <br/> |Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.  <br/> |
   
Överväg att ta bort ett tillägg om ingen längre använder det. Det kan vara logiskt att stänga av ett tillägg om ett tillägg endast används under vissa tider på året.
  
### <a name="security-of-office-add-ins"></a>Säkerhet för Office-tillägg

Office-tillägg kombinerar en XML-manifestfil som innehåller vissa metadata om tillägget, men viktigast av allt pekar på ett webbprogram som innehåller all kod och logik. Tillägg kan variera i sina funktioner. Tillägg kan till exempel:
  
- Visa data.
    
- Läs en användares dokument för att tillhandahålla kontextuella tjänster.
    
- Läs och skriv data till och från en användares dokument för att ge användaren värde.
    
Mer information om vilka typer och funktioner för Office-tillägg finns i [plattformsöversikten för Office-tillägg,](https://go.microsoft.com/fwlink/p/?linkid=846362)särskilt avsnittet "Anatomi för ett Office-tillägg".
  
Om du vill interagera med användarens dokument måste tillägget deklarera vilken behörighet det behöver i manifestet. En javascript-api-åtkomstbehörighetsmodell på fem nivåer utgör grunden för sekretess och säkerhet för användare av tillägg till åtgärdsfönstret. Majoriteten av tilläggen i Office Store är lässkrivdokument på nivå med nästan alla tillägg som stöder åtminstone ReadDocument-nivån. Mer information om [behörighetsnivåerna finns i Begära behörigheter för API-användning i innehåll och tillägg i åtgärdsfönstret](https://go.microsoft.com/fwlink/p/?linkid=848863).
  
När du uppdaterar ett manifest är de typiska ändringarna i ett tilläggs ikon och text. Ibland ändras tilläggskommandon. Men behörigheterna för tillägget ändras inte. Webbprogrammet där all kod och logik för tilläggskörningarna kan ändras när som helst, vilket är webbprogrammens natur.
  
Uppdateringar för tillägg sker på följande sätt:
  
- **Tillägg för företagsrader:** I det här fallet, där en administratör uttryckligen laddade upp ett manifest, kräver tillägget att administratören överför en ny manifestfil för att stödja metadataändringar. Nästa gång de relevanta Office-programmen startas uppdateras tillägget. Webbprogrammet kan ändras när som helst. 

    > [!NOTE]
    > Admin behöver inte ta bort ett LOB-tillägg för att göra en uppdatering.   I avsnittet Tillägg kan admin helt enkelt klicka på LOB-tillägget och välja **uppdateringsknappen** i det nedre högra hörnet. Uppdateringen fungerar bara om versionen av det nya tillägget är större än det befintliga tillägget.   
    
- **Office Store-tillägg:** När en administratör valde ett tillägg från Office Store, om ett tillägg uppdateras i Office Store, uppdateras tillägget senare i Centraliserad distribution. Nästa gång de relevanta Office-programmen startas uppdateras tillägget. Webbprogrammet kan ändras när som helst. 

### <a name="edit-add-in-access"></a>Redigera tilläggsåtkomst

Efter distributionen kan administratörer också ändra användaråtkomsten till tillägg.

1. Gå till sidan **Settings**  >  **Inställningarstjänster & tillägg i administrationscentret.**

2. Välj det distribuerade tillägget.

3. Klicka på **Redigera** under **Vem har Access**.
4. Spara ändringarna.
    
### <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Förhindra hämtning av tillägg genom att stänga av Office Store för alla klienter (utom Outlook)

> [!NOTE]
> Outlook-tilläggsinstallation hanteras av en [annan process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).

Som organisation kanske du vill förhindra hämtning av nya Office-tillägg från Office Store. Detta kan användas tillsammans med centraliserad distribution för att säkerställa att endast organisationsgodkända tillägg distribueras till användare inom organisationen.
  
Så här inaktiverar du tilläggsförvärv:
  
1. I administrationscentret går du till sidan **Inställningar** \> [Tjänster och tillägg](https://go.microsoft.com/fwlink/p/?linkid=2053743).
    
3. Välj **Användarinlägda appar och tjänster**.
    
4. Avmarkera alternativet att låta användare komma åt Office-arkivet.

Detta förhindrar att alla användare hämtar följande tillägg från butiken.
  
- Tillägg för Word, Excel och PowerPoint 2016 från:
    
  - Windows
    
  - Mac
    
  - Office
    
    
- Förvärv som startar inom **AppSource**
    
- Tillägg i Microsoft 365
    
En användare som försöker komma åt arkivet ser följande meddelande: **Tyvärr har Microsoft 365 konfigurerats för att förhindra individuellt förvärv av Office Store-tillägg.**
  
Stöd för att stänga av Office Store finns i följande versioner:
  
- Windows: 16.0.9001 - För närvarande tillgänglig.
    
- Mac: 16.10.18011401 - För närvarande tillgänglig.
    
- iOS: 2.9.18010804 - För närvarande tillgänglig.
    
- Webben - För närvarande tillgänglig.
    
Detta hindrar inte en administratör från att använda centraliserad distribution för att tilldela ett tillägg från Office Store.
  
Om du vill förhindra att en användare loggar in med ett Microsoft-konto kan du begränsa inloggningen så att den bara använder organisationskontot. Mer information finns [här](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).
 
  
## <a name="minors-and-acquiring-add-ins-from-the-store"></a>Minderåriga och förvärva tillägg från Store

Den allmänna dataskyddsförordningen (GDPR) är en EU-förordning som träder i kraft den 25 maj 2018. Det ger användarna rätt till och skydd av sina uppgifter. En av aspekterna av GDPR är att minderåriga inte kan få sina personuppgifter skickade till parter som deras förälder eller vårdnadshavare inte har godkänt. Den specifika ålder som definieras som minderårig beror på den region där personen är belägen.
  
Regioner som har lagstadgade bestämmelser om föräldrarnas samtycke inkluderar USA, Sydkorea, Storbritannien och Eu ropeiska unionen. För dessa regioner blockeras en minderårig (via Azure Active Directory) från att få nya Office-tillägg från Store och köra tillägg som tidigare har förvärvats. För länder utan lagstadgade bestämmelser kommer det inte att finnas några nedladdningsrestriktioner.
  
En användare bedöms vara en minderårig baserat på data som anges i Azure Active Directory. Klientadministratören ansvarar för att deklarera den lagliga åldersgruppen och föräldrarnas samtycke för den användaren.
  
Om föräldern/vårdnadshavaren samtycker till en minderårig med hjälp av ett specifikt tillägg kan klientadministratören använda centraliserad distribution för att distribuera tillägget till alla minderåriga som har medgivande.
  
För att vara GDPR-kompatibel för minderåriga måste du se till att en av följande versioner av Office distribueras i din skola/organisation.
  
 **För Word, Excel, PowerPoint och Project:** 
  
|||
|:-----|:-----|
|**Plattform** <br/> |**Byggnummer** <br/> |
|Microsoft 365-appar för företag (månadskanal)  <br/> |9001.2138   <br/> |
|Microsoft 365 Apps for enterprise (Halvårskanal)  <br/> |8431.2159  <br/> |
|Office 2016 för Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 för Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 för Mac  <br/> |16.11.18020200  <br/> |
|Office för webben  <br/> |EJ TILLÄMPLIGT  <br/> |
   
 **För Outlook:** 
  
|||
|:-----|:-----|
|**Plattform** <br/> |**Byggnummer** <br/> |
|Outlook 2016 för Windows (MSI)  <br/> |Skapa ingen TBD  <br/> |
|Outlook 2016 för Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 för Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook Mobile för iOS  <br/> |2.75.0  <br/> |
|Outlook mobile för Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |EJ TILLÄMPLIGT  <br/> |
   
 **Office 2013-krav**
  
Word, Excel och PowerPoint 2013 för Windows stöder samma mindre kontroller om Active Directory Authentication Library (ADAL) är aktiverat. Det finns två alternativ för efterlevnad, som förklaras härnäst.
  
- **Aktivera ADAL**. I den hÃ¤r artikeln beskrivs hur du aktiverar ADAL för Office 2013: [HÃ¤r Ã¤ger microsoft 365 modern autentisering med Office-klienter](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).<br/>Du måste också ange registernycklarna så att de aktiverar ADAL enligt beskrivningen i [Aktivera modern autentisering för Office 2013 på Windows-enheter](../security-and-compliance/enable-modern-authentication.md).<br/>Dessutom måste du installera följande apriluppdateringar för Office 2013:
    
  - [Beskrivning av säkerhetsuppdateringen för Office 2013: 10 april 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [3 april 2018, uppdatering för Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Aktivera inte ADAL**. Om du inte kan aktivera ADAL i Office 2013 är vår rekommendation att använda Grupprincip för att stänga av Store för kontorskunderna. Information om hur du inaktiverar appen för Office-inställningarna finns [här](https://technet.microsoft.com/library/cc178992.aspx).
    
## <a name="end-user-experience-with-add-ins"></a>Slutanvändarens upplevelse med tillägg

Nu när du har distribuerat tillägget kan dina slutanvändare börja använda det i sina Office-program (se [Börja använda Office-tillägget](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)). Tillägget visas på alla plattformar som tillägget stöder.
  
Om tillägget stöder tilläggskommandon visas kommandona i menyfliksområdet i Office. I följande exempel visas kommandot **Sökcitning** för tillägget **Källhänvisning.** 

![Menyfliksområdet i Office med sökhänvisning](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Om det distribuerade tillägget inte stöder tilläggskommandon eller om du vill visa alla distribuerade tillägg kan du visa dem via **Mina tillägg**. 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>I Word 2016, Excel 2016 eller PowerPoint 2016

1. Välj **Infoga \> mina tillägg**. 
    
2. Välj fliken **Hanterad administratör** i fönstret Office-tillägg. 
    
3. Dubbelklicka på det tillägg som du distribuerade tidigare (i det här exemplet **Citat** ). <br/>![Fliken Hanterad administratör på sidan Office-tillägg](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>I Outlook

1. I **menyfliksområdet Hem** väljer du **Hämta tillägg**.<br/>![Knappen Butik i Outlook](../../media/getaddinsicon.png)
  
2. Välj **Admin-hanterad** i den vänstra navigeringsfältet.

## <a name="delete-the-add-in"></a>Ta bort tillägget

Du kan också ta bort ett tillägg som har distribuerats.

1. Gå till sidan **Settings**  >  **Inställningarstjänster & tillägg i administrationscentret.**

2. Välj det distribuerade tillägget.

3. Klicka på **Ta bort tillägget**. Ta bort knappen Tillägg i det nedre högra hörnet.
4. Validera dina val och välj **Ta bort tillägget**.
  
## <a name="learn-more"></a>Mer information

Läs mer om hur du skapar och bygger [Office-tillägg](https://go.microsoft.com/fwlink/p/?linkid=846362).
  
[Använd Centraliserade PowerShell-cmdlets för att hantera tillägg](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).
  
[Felsöka: Användaren ser inte tillägg](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
