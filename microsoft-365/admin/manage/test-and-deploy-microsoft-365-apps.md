---
title: Testa och distribuera Microsoft 365-appar efter partners i portalen För integrerade appar
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Hitta, testa och distribuera Microsoft- och Microsoft-partnerappar för användare och grupper i organisationen från portalen för integrerade appar i administrationscentret för Microsoft 365.
ms.openlocfilehash: dcd4a91d9e43c0a740094615cd3dca0b0e8bc0f6
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007063"
---
# <a name="test-and-deploy-microsoft-365-apps-by-partners-in-the-integrated-apps-portal"></a>Testa och distribuera Microsoft 365-appar efter partners i portalen För integrerade appar

I administrationscentret för Microsoft 365 får du flexibiliteten att distribuera appar för enstaka lager, anpassade affärsprogram och Microsoft 365-partnerappar från en enda plats. Du kommer åt platsen i inställningarna för Microsofts administrationscenter i integrerade appar. Genom att hitta, testa och helt distribuera köpta och licensierade appar av Microsoft-partner från portalen för integrerade appar är det praktiskt och effektivt att hålla företagstjänsterna uppdaterade.

Mer information om att köpa och licensiera Microsoft 365-appar från partner i din organisation finns i Hantera och distribuera [Microsoft 365-appar](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324)från administrationscentret för Microsoft 365.

Mer information om hur partners skapar dessa appar finns i Planera [ett SaaS-erbjudande för kommersiella marknadsplatser](https://go.microsoft.com/fwlink/?linkid=2158277)

Portalen för integrerade appar är endast tillgänglig för globala administratörer och endast för kunder världen över. Den här funktionen är inte tillgänglig i moln för myndigheter.

I portalen Integrerade appar visas en lista med appar, som innehåller enstaka appar och Microsoft 365-appar från partners som distribueras till din organisation. Endast webbappar, SPFx-appar, Office-tillägg och Teams-appar visas. För webbappar kan du se två typer av appar.

- SaaS-appar som är appsource.microsoft.com och kan distribueras av administratörer som ger medgivande för organisationens räkning.
- SAML-galleriprogram som är länkade till Office-tillägg.

## <a name="manage-apps-in-the-integrated-apps-portal"></a>Hantera appar i portalen Integrerade appar

Du kan hantera testning och distribution av köpta och licensierade Microsoft 365-appar från partners.

1. I administrationscentret väljer du **Inställningar** och sedan **Integrerade appar**.

2. Välj ett program med **Status** för **Fler appar tillgängligt** för att öppna **fönstret** Hantera. Status för fler **tillgängliga appar gör** att du vet att det finns fler integreringar från ISV-enheter som ännu inte har distribuerats.

3. Välj **Distribuera** på fliken **Översikt.** För vissa program måste du lägga till användare innan du kan välja Distribuera.

4. Välj  **Användare**, välj **Är det här en testdistribution** och välj sedan **Hela organisationen**, **Specifika användare/grupper** eller **Bara jag**. Du kan också välja **Testa distribution** om du föredrar att vänta med att distribuera programmet till hela organisationen. Vissa användare eller grupper kan vara en Microsoft 365-grupp, säkerhetsgrupp eller distributionsgrupp.

5. Välj **Uppdatera** och sedan **Klar**. Nu kan du välja Distribuera på fliken Översikt.

6. Granska programinformationen och välj sedan **Distribuera**.

7. Välj **Klar** på sidan Distribution slutförd och granska informationen om testet eller fullständig distribution på **fliken** Översikt.

8. Om programmet har statusen **Uppdatering väntar kan** du klicka på programmet för att öppna fönstret Hantera och uppdatera programmet.

## <a name="find-published-apps-for-testing-and-full-deployment"></a>Hitta publicerade appar för testning och fullständig distribution

Du kan söka efter, testa och helt distribuera publicerade program som inte redan visas i listan på sidan Integrerade appar. Genom att köpa och licensiera apparna från administrationscentret kan du lägga till Microsoft- och Microsoft-partnerappar i listan från en enda plats.

1. I det vänstra navigeringsfältet i administrationscentret väljer **du Inställningar** och sedan **Integrerade appar.**

2. Välj **Skaffa appar** för att visa apparna.

3. På sidan **Microsoft 365-appar** publicerade appar väljer du det program du vill distribuera genom att välja **Skaffa nu.** Apparna som visas främst är Word-, PowerPoint-, Excel-, Outlook-tillägg, Teams-appar och SharePoint-appar (byggt på SharePoint Framework-teknik). Godkänn behörigheterna och välj **Fortsätt.**

5. Välj **Distribuera** högst upp på sidan bredvid meddelandet som refererar till att väntar på att distribueras.

    Om den valda appen är länkad till ett SaaS-erbjudande via en ISV visas alla andra appar som är en del av det här länkade erbjudandet på sidan Konfiguration. Om du väljer att distribuera alla program väljer du **Nästa.** Annars väljer du **Redigera** och väljer vilka program du vill distribuera. För vissa program måste du lägga till användare innan du kan välja **Distribuera.**

6. Välj **Lägg till** användare , välj Är det här en **testdistribution** och välj sedan **Hela** organisationen eller **Specifika användare/grupper** eller Bara **jag.**

    Vissa användare/grupper kan vara en Microsoft 365-grupp, säkerhetsgrupp eller distribuerad grupp. Du kan också välja **Testa distribution** om du föredrar att vänta med att distribuera programmet till hela organisationen.

7. Välj **Nästa** för att komma till **sidan Acceptera begäran.** Appfunktionerna och behörigheterna för de olika apparna visas. Om appen behöver medgivande väljer du **Acceptera behörigheter**. Det är bara en global administratör som kan ge medgivande.

8. Välj **Nästa** för att granska distributionen och välj **Slutför distributionen.** Du kan visa distributionen från fliken **Översikt** genom att välja **Visa den här distributionen.** I administrationscentret för Microsoft 365 kan du se status för varje distribuerad app och det datum då du distribuerade programmet.

> [!NOTE]
> Om ett program tidigare har distribuerats från någon annan plats än portalen för integrerade appar är **distributionstypen** **Anpassad.**

## <a name="unsupported-scenarios"></a>Scenarier som inte stöds

Du kommer inte att kunna distribuera en app med en enda butik eller Microsoft 365-appar av partner från portalen för integrerade appar för följande scenarier.

- Samma tillägg är kopplat till mer än ett SaaS-erbjudande.
- SaaS-erbjudandet är länkat till tillägg, men integrerar inte med Microsoft Graph och inget AAD-app-ID tillhandahålls.
- SaaS-erbjudandet är länkat till tillägg, men AAD-app-ID för Microsoft Graph-integrering delas mellan flera SaaS-erbjudanden.

## <a name="upload-custom-line-of-business-apps-for-testing-and-full-deployment"></a>Ladda upp anpassade verksamhetsbaserade appar för testning och fullständig distribution

1. I det vänstra navigeringsfältet i administrationscentret väljer **du Inställningar** och sedan **Integrerade appar.**

2. Välj **Ladda upp anpassade appar**. Endast en anpassad programrad för Word, PowerPoint, Excel och Outlook stöds.

3. Ladda upp manifestfilen från din enhet eller lägg till en URL-länk. För vissa program måste du lägga till användare innan du kan välja Distribuera.

4. Välj **Lägg till** användare , välj Är det här en **testdistribution** och välj Hela **organisationen** eller **Specifika användare/grupper** eller Bara **jag.**

    Vissa användare/grupper kan vara en Microsoft 365-grupp, säkerhetsgrupp eller distribuerad grupp. Du kan också välja **Testa distribution** om du vill vänta med att distribuera programmet till hela organisationen.

5. Välj **Nästa** för att komma till **sidan Acceptera begäran.** Appfunktionerna och -behörigheterna för apparna visas. Om appen behöver medgivande väljer du **Acceptera behörigheter**. Det är bara en global administratör som kan ge medgivande.

6. Välj **Nästa** för att granska distributionen och välj **Slutför distributionen.** Du kan visa distributionen från fliken **Översikt** genom att välja **Visa den här distributionen.**

## <a name="prepare-to-deploy-add-ins-in-integrated-apps"></a>Förbereda distribution av tillägg i integrerade appar

Office-tillägg hjälper dig att anpassa dina dokument och förenkla åtkomsten till information på webben (se Börja använda dina Office-tillägg). 

Tillägg ger följande fördelar: 

- När det relevanta Office-programmet startas laddas tillägget ned automatiskt. Om tillägget har stöd för tilläggskommandon visas det automatiskt i Office-programmets menyfliksområde. 

- Tillägg visas inte längre för användarna om administratören stänger av eller tar bort tillägget, eller om användaren tas bort från Azure Active Directory eller från en grupp som tillägget har tilldelats. 

Tillägg stöds i tre skrivbordsplattformar: Windows-, Mac- och Online Office-program. Det stöds även i iOS och Android (endast Outlook Mobile-tillägg). 

Det kan ta upp till 24 timmar för ett tillägg att visas för klienten och alla användare. 

Idag kan både Exchange-administratörer och globala administratörer distribuera tillägg från integrerade appar.   

### <a name="before-you-begin"></a>Innan du börjar

Distribution av tillägg kräver att användarna använder Microsoft 365 Enterprise-licenser (E3/E5/F3) eller Microsoft 365 Business-licenser (Business Basic, Business Standard, Business Premium). Användarna måste också vara inloggade på Office med organisations-ID) och ha Exchange Online och aktiva Exchange Online-postlådor. Prenumerationskatalogen måste finnas i eller vara extern till Azure Active Directory. 

Distributionen stöder inte följande: 

- Tillägg som är inriktade på Word, Excel eller PowerPoint i Office 2013 
- En lokal katalogtjänst 
- Tilläggsdistribution till en Exchange-postlåda 
- Distribution av COM- (Component Object Model) eller VSTO-tillägg (Visual Studio Tools for Office). 
- Distributioner av Microsoft 365 som inte inkluderar Exchange Online, till exempel Microsoft 365-program för företag och Microsoft 365-program för företag.  

### <a name="office-requirements"></a>Office-krav 

För Word-, Excel- och PowerPoint-tillägg måste användarna använda något av följande: 
- På en Windows-enhet, version 1704 eller senare av Microsoft 365 Enterprise-licenser (E3/E5/F3) eller Microsoft 365 Business-licenser (Business Basic, Business Standard, Business Premium). 
- På Mac, version 15.34 eller senare. 

För Outlook måste användarna använda något av följande: 
- Version 1701 eller senare av Microsoft 365 Enterprise-licenser (E3/E5/F3) eller Microsoft 365 Business-licenser (Business Basic, Business Standard, Business Premium). 
- Version 1808 eller senare av Office Professional Plus 2019 eller Office Standard 2019. 
- Version 16.0.4494.1000 eller senare av Office Professional Plus 2016 (MSI) eller Office Standard 2016 (MSI).
    > [!NOTE]
    > MSI-versionerna av Outlook visar administratörsinstallerade tillägg i rätt Outlook-menyfliksområde, inte avsnittet Mina tillägg.  
- Version 15.0.4937.1000 eller senare av Office Professional Plus 2013 (MSI) eller Office Standard 2013 (MSI).
- Version 16.0.9318.1000 eller senare av Office 2016 för Mac. 
- Version 2.75.0 eller senare av Outlook Mobile för iOS. 
- Version 2.2.145 eller senare av Outlook Mobile för Android. 



### <a name="exchange-online-requirements"></a>Krav för Exchange Online 
Microsoft Exchange lagrar tilläggsmanifesten i organisationens klientorganisation. Administratören som distribuerar tillägg och användarna som tar emot tilläggen måste använda en version av Exchange Online som har stöd för OAuth-autentisering. 

Fråga organisationens Exchange-administratör om vilken konfiguration som används. OAuth-anslutning per användare kan verifieras med hjälp av [PowerShell-cmdleten Test-OAuthConnectivity.](/powershell/module/exchange/test-oauthconnectivity)   

### <a name="user-and-group-assignments"></a>Användar- och grupptilldelningar
Distributionen av tillägget stöds för närvarande till de flesta grupper som stöds av Azure Active Directory, inklusive Microsoft 365-grupper, distributionslistor och säkerhetsgrupper. Distributionen stöder användare i grupper på översta nivån eller grupper utan överordnade grupper, men inte användare i kapslade grupper eller grupper som har överordnade grupper. 

> [!NOTE]
> Säkerhetsgrupper utan e-postaktivering stöds inte för närvarande. 

I följande exempel tilldelas Sandra, Sheila och gruppen Sales Department till ett tillägg. Eftersom West Coast Sales Department är en kapslad grupp, tilldelas Jens och Erik inte till ett tillägg. 

![Diagram över försäljningsavdelningen](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

### <a name="find-out-if-a-group-contains-nested-groups"></a>Ta reda på om en grupp innehåller kapslade grupper

Det enklaste sättet att upptäcka om en grupp innehåller kapslade grupper är att visa gruppens kontaktkort i Outlook. Om du anger gruppens **** namn i fältet Till i ett e-postmeddelande och sedan väljer gruppens namn när det matchas visas om den innehåller användare eller   kapslade grupper. I exemplet nedan visas inga **användare och** bara två undergrupper på fliken Medlemmar för   Outlook-kontaktkortet för testgruppen. 

![Fliken Medlemmar på Outlook-kontaktkortet](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

Du kan göra motsatt fråga genom att matcha gruppen och ta reda på om den är medlem i en grupp. I exemplet nedan kan du <b></b>se att Sub Group 1 är medlem i Test Group under fliken Medlemskap för   Outlook-kontaktkortet. 

![Fliken Medlemskap på Outlook-kontaktkortet](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

Observera att du kan använda Azure Active Directory Graph API för att köra frågor för att hitta listan med grupper inom en grupp. Mer information finns i [Åtgärder för | Graph API-referens](/previous-versions/azure/ad/graph/api/groups-operations). 

## <a name="recommended-approach-for-deploying-office-add-ins"></a>Rekommenderad metod för distribution av Office-tillägg 
Om du vill distribuera tillägg genom att använda en fasad metod rekommenderar vi följande: 
1. Distribuera tillägget till ett mindre antal personer i företaget och till medlemmar i IT-avdelningen. Du kan aktivera flaggan Är det **här en testdistribution?** Om distributionen lyckas går du vidare till steg 2. 

2. Distribuera tillägget till fler personer inom företaget. Utvärdera resultatet på nytt och fortsätt med fullständig distribution om det lyckas. 

3. Distribuera den till alla användare. Inaktivera flaggan från Är det **här en testdistribution.** 

Beroende målgruppens storlek kan du lägga till eller ta bort utrullningssteg.  

## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Distribuera ett Office-tillägg med hjälp av administrationscentret 

1. I administrationscentret väljer du **Inställningar** och sedan **Integrerade appar**. 

2. Välj **Skaffa appar** högst upp på sidan. AppSource läses in i ett inbäddat format. Sök efter ett tillägg eller hitta det genom att klicka på Produkt i navigeringsfältet till vänster.  Om tillägget har länkats av ISV till en SaaS-app eller andra appar och tillägg, och om SaaS-appen är en betalapp visas en dialogruta där du kan köpa licensen eller Distribuera. Oavsett om du har köpt licensen eller inte kan du fortsätta med distributionen. Välj **Distribuera**.  

3. Sidan Konfiguration **visas** där alla appar finns. Om du inte har behörighet eller rätt åtkomst till att distribuera programmet markeras respektive information. Du kan välja de program som du vill distribuera. Genom att **välja** Nästa visas **sidan** Användare. Om tillägget inte har länkats av ISV kommer du till sidan Användare. 

4. Välj **Alla,** **Specifika användare/grupper** eller **Bara** jag för att ange vilka tillägget   ska distribueras till. Använd sökrutan för att söka efter specifika användare eller grupper. Om du testar tillägget väljer du Är det **här en testdistribution.** 

5. Välj **Nästa**. Alla programfunktioner och -behörigheter visas i ett enda fönster tillsammans med certifieringsinformation om appen har Microsoft 365-certifiering. Om du väljer certifieringslogotypen kan användaren se mer information om certifieringen.  

6. Granska och välj sedan **Slutför distributionen.**  

7. En grön skalstrecksikon visas när tillägget har distribuerats. Följ anvisningarna på sidan för att testa tillägget. 

> [!NOTE]
> Användare kan behöva köra om Office för att visa tilläggsikonen i menyfliksområdet. Det kan ta upp till 24 timmar innan Outlook-tillägg visas i appfliksområde. 

Vi är bra att informera användare och grupper om att det distribuerade tillägget är tillgängligt. Du kan skicka ett e-postmeddelande som beskriver när och hur du använder tillägget. Inkludera eller länka till hjälpinnehåll eller vanliga frågor och svar som kan hjälpa användare om de har problem med tillägget. 

## <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Att tänka på när du tilldelar ett tillägg till användare och grupper 

Globala administratörer och Exchange-administratörer kan tilldela ett tillägg till alla eller till vissa användare och grupper. Varje alternativ har sina konsekvenser: 

- **Alla**   Med det här alternativet tilldelas tillägget till alla användare i organisationen. Använd det här alternativet sparsamt och bara för tillägg som verkligen är till för hela organisationen. 

- **Användare**   Om du tilldelar ett tillägg till en enskild användare och sedan distribuerar tillägget till en ny användare måste du först lägga till den nya användaren. 

- **Grupper**   Om du tilldelar ett tillägg till en grupp tilldelas tillägget automatiskt till användare som läggs till i gruppen. När en användare tas bort från en grupp förlorar användaren åtkomsten till tillägget. I båda fallen krävs inga ytterligare åtgärder från administratören. 

- **Bara jag**   Om du bara tilldelar ett tillägg till dig själv, tilldelas tillägget bara till ditt konto, vilket är perfekt för att testa tillägget. 

Rätt alternativ för din organisation beror på din konfiguration. Vi rekommenderar emellertid att tilldelningar genom att använda grupper. Som administratör kan det vara enklare att hantera tillägg genom att använda grupper och kontrollera medlemskapet i de grupperna i stället för att tilldela enskilda användare varje gång. I vissa situationer kanske du vill begränsa åtkomsten till en liten uppsättning användare genom att tilldela vissa användare genom att tilldela användare manuellt. 

### <a name="more-about-office-add-ins-security"></a>Mer om säkerhet för Office-tillägg 
Office-tillägg kombinerar en XML-manifestfil som innehåller vissa metadata om tillägget, men det viktigaste är att de pekar på ett webbprogram som innehåller all kod och logik. Tillägg kan ha olika funktioner. Tillägg kan till exempel:
- Visa data. 
- Läsa en användares dokument för att tillhandahålla sammanhangsberoende tjänster. 
- Läsa och skriva data till och från en användares dokument för att ge värde till användaren.  

Mer information om olika typer och funktioner i Office-tillägg finns i [Plattformsöversikt](/office/dev/add-ins/overview/office-add-ins)för Office-tillägg, särskilt avsnittet "Beskrivning av ett Office-tillägg". 

För att tillägget ska kunna interagera med användarens dokument måste det deklarera vilken behörighet som behövs i manifestet. En JavaScript API-behörighetsmodell för åtkomst i fem nivåer utgör grunden för sekretess och säkerhet för användare av tillägg för åtgärdsfönster. Majoriteten av tilläggen i Office Store är på nivån ReadWriteDocument med nästan alla tillägg som stöder minst ReadDocument-nivå. Mer information om behörighetsnivåer finns i [Begära behörigheter för API-användning i innehåll och tillägg för åtgärdsfönster.](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins) 

När du uppdaterar ett manifest är det vanligtvis ändringar av ikon och text för ett tillägg. Ibland kan tilläggskommandon ändras. Tilläggets behörigheter ändras dock inte. Webbprogrammet där all kod och logik för tillägget körs kan ändras när som helst, vilket är hur webbprogram fungerar. 

Uppdateringar för tillägg sker enligt följande: 
- **Verksamhetstillägg:** I det här fallet, där en administratör uttryckligen har laddat upp ett manifest, kräver tillägget att administratören laddar upp ett nytt manifest för att ge stöd för metadataändringar. Nästa gång Office-programmet startar uppdateras tillägget. Webbprogrammet kan ändras när som helst. 

- **Office Store-tillägg:** Om ett tillägg uppdateras i Office Store nästa gång det relevanta Office-programmet startar, uppdateras tillägget när en administratör väljer ett tillägg från Office Store. Webbprogrammet kan ändras när som helst. 

> [!NOTE]
> För Word använder Excel och PowerPoint en [](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)SharePoint-programkatalog för att distribuera tillägg till användare i en lokal miljö utan anslutning till   Microsoft 365 och/eller support för SharePoint-tillägg som krävs. Du Outlook till Exchange på Kontrollpanelen för att distribuera i en lokal miljö utan anslutning till Microsoft 365.  

## <a name="add-in-states"></a>Tilläggsstater
Ett tillägg kan vara antingen i läget **På**   eller **Av.**   

| Region | Hur tillståndet uppstår | Påverkan |
|:-----|:-----|:-----|
|**Aktiv**  <br/> |Administratören har laddat upp tillägget och tilldelat det till användare eller grupper.  <br/> |Användare och grupper som tilldelats tillägget kan se det i relevanta klienter.  <br/> |
|**Inaktiverad**  <br/> |Administratören har inaktiverat tillägget.  <br/> |Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.  <br/> Om tilläggstillståndet ändras till Aktivt får användare och grupper åtkomst till det igen.  <br/> |
|**Borttagen**  <br/> |Administratören har tagit bort tillägget.  <br/> |Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.  <br/> |
 
Överväg att ta bort tillägg som ingen använder längre. Det kan vara bra att stänga av ett tillägg om ett tillägg bara används under vissa tider på året. 

## <a name="manage-an-office-add-in-using-the-admin-center"></a>Hantera Office-tillägg med hjälp av administrationscentret

Efter distributionen kan administratörer också hantera användaråtkomst till tillägg. 

1. I administrationscentret väljer du **Inställningar** och sedan **Integrerade appar**. 
2. På sidan Integrerade appar visas en lista över appar, antingen enskilda tillägg eller tillägg som har länkats till andra appar. 
3. Välj en app med **Status**   för Fler appar **som** du kan använda för att   öppna **fönstret**   Hantera. Status för fler **tillgängliga appar gör** att du vet att det finns fler integreringar från   ISV-enheter som ännu inte har distribuerats. 
4. Välj **Distribuera**   på fliken **Översikt.** För vissa program måste du lägga till användare innan du kan välja Distribuera. 
5. Välj **Användare**, välj **Är det här en testdistribution** och välj sedan antingen **Hela** organisationen , **Specifika användare/grupper**   eller Bara **jag**. Du kan också välja **Testa distribution** om du föredrar att vänta med att distribuera programmet till   hela organisationen. Vissa användare eller grupper kan Microsoft 365 en grupp, en säkerhetsgrupp eller en distributionsgrupp. 
6. Välj  **Uppdatera**   och välj sedan **Klar**. Nu kan du välja **Distribuera** på **fliken** Översikt. 
7. Granska programinformationen och välj sedan **Distribuera**.
8. Välj **Klar** på sidan Distribution slutförd och granska informationen om testet eller   fullständig distribution på **fliken**    Översikt. 
9. Om programmet har statusen  **Uppdatering väntar kan** du klicka på programmet för att öppna **fönstret** Hantera och uppdatera programmet. 
10. Om du bara vill uppdatera användare **väljer du fliken** Användare och gör rätt ändring. Välj **Uppdatera** när du har gjort ändringarna.  

## <a name="delete-an-add-in"></a>Ta bort ett tillägg

Du kan också ta bort ett tillägg som har distribuerats.

1. I administrationscentret väljer du **Inställningar** och sedan **Integrerade appar** .
2. Markera valfri rad för att visa hanteringsfönstret. 
3. Välj **fliken** Konfiguration. 
4. Markera det tillägg du vill ta bort och välj sedan Ta **bort**.  

> [!NOTE]
>  Om tillägget har distribuerats av en annan administratör inaktiveras knappen Ta bort. Endast den administratör som har distribuerat appen eller en global administratör kan ta bort tillägget.

## <a name="scenarios-where-exchange-admin-cannot-deploy-an-add-in"></a>Scenarier där Exchange administratör inte kan distribuera ett tillägg 

Det finns två fall där Exchange administratör inte kan distribuera ett tillägg:
- Om ett tillägg behöver behörighet till MS Graph API:er och behöver godkännande från en global administratör.
- Om ett tillägg är länkat till två eller flera tillägg och webbapps och minst ett av dessa tillägg distribueras av en annan administratör (exchange/global) och användartilldelningen inte är enhetlig. Vi tillåter endast distribution av tillägg när användartilldelningen är samma för alla redan distribuerade program.  


## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

### <a name="which-administrator-role-do-i-need-to-access-integrated-apps"></a>Vilken administratörsroll behöver jag för att komma åt integrerade appar?

Endast globala administratörer kan komma åt integrerade appar. Integrerade appar visas inte i det vänstra navigeringsfältet för andra administratörer.

### <a name="why-do-i-see-add-in-in-the-left-nav-under-setting-but-not-integrated-apps"></a>Varför visas Tillägg i det vänstra navigeringsfältet under Inställning men inte Integrerade appar?

Det kan finnas flera anledningar:

- Den inloggade administratören är Exchange administratör.
- Kunden använder molntjänster i en suverän del och integrerade appar finns ännu tillgängliga för molnkunder i en suverän del.

### <a name="what-apps-can-i-deploy-from-integrated-apps"></a>Vilka appar kan jag distribuera från integrerade appar?

Integrerade appar tillåter distribution av webbappar, Teams-appar, Excel-, PowerPoint-, Word-, Outlook-tillägg och SPFx program. För tillägg stöder integrerade appar distribution till e-Exchange onlinepostlådor och inte lokala Exchange postlådor.

### <a name="can-administrators-delete-or-remove-apps"></a>Kan administratörer ta bort eller ta bort appar?

Ja. Globala administratörer kan ta bort appar.

- Välj en app i listvyn. På fliken **Konfiguration** väljer du vilka appar som ska tas bort.  

### <a name="is-integrated-apps-available-in-sovereign-cloud"></a>Finns integrerade appar i en suverän molntjänst?

Nej. Integrerade appar är inte tillgängliga för molnkunder med en suverän tillgång.

### <a name="is-integrated-apps-available-in-government-clouds"></a>Finns integrerade appar i myndighetsmoln?

Nej. Integrerade appar är inte tillgängliga för kunder i myndighetsmoln.
