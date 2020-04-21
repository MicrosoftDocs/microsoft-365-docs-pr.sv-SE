---
title: Microsoft 365 användningsanalyser
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
- Adm_TOC
search.appverid:
- MET150
- MOE150
ms.assetid: 77ff780d-ab19-4553-adea-09cb65ad0f1f
description: Få en översikt över hur din organisation använder Microsoft 365-tjänster för att kommunicera och samarbeta.
ms.openlocfilehash: 783b2c599a5f3a31446855450029859e6dfd9f65
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626940"
---
# <a name="microsoft-365-usage-analytics"></a>Microsoft 365 användningsanalyser
---
Microsoft 365-användningsanalys är ännu inte tillgängligt för Microsoft 365 US Government Community.
 
## <a name="overview-of-microsoft-365-usage-analytics"></a>Översikt över Microsoft 365 användningsanalyser

Använd Microsoft 365-användningsanalyser i Power BI för att få insikter om hur din organisation använder de olika tjänsterna inom Microsoft 365 för att kommunicera och samarbeta. Du kan visualisera och analysera Microsoft 365-användningsdata, skapa anpassade rapporter och dela insikterna inom din organisation och få insikter om hur specifika regioner eller avdelningar använder Microsoft 365.
  
Microsoft 365-användningsanalys är en mallapp som ger dig tillgång till en färdig instrumentpanel som ger en produktövergripande vy över de senaste 12 månaderna och innehåller ett antal färdiga rapporter. Varje rapport ger specifika insikter om användningen. Den användarspecifika informationen är tillgänglig för den senaste fullständiga kalendermånaden.
  
Den [datamodell](usage-analytics-data-model.md) som driver mallappen innehåller användarattribut från Active Directory, vilket gör det möjligt att pivotera i vissa rapporter. Följande Active Directory-attribut ingår: plats, avdelning och organisation. 
  
Se [Aktivera Microsoft 365 användningsanalyser](enable-usage-analytics.md) för att börja samla in data. 
  
Microsoft 365-användningsanalys innehåller ett antal rapporter som beskrivs i följande avsnitt. 

Du kan komma åt detaljerade rapporter för varje område genom att välja datatabeller. Du kan visa alla färdiga rapporter genom att välja flikarna längst ned på webbplatsen när du visar rapporterna. Mer detaljerade instruktioner finns [i Navigera och använda rapporterna i Microsoft 365-användningsanalys](navigate-and-utilize-reports.md) och anpassa rapporterna i Microsoft [365-användningsanalys](customize-reports.md).

## <a name="executive-summary"></a>Sammanfattning

Sammanfattningen är en översikt över Microsoft 365 for Business-implementering, användning, mobilitet, kommunikation, samarbete och lagringsrapporter på hög nivå och är avsedd för beslutsfattare för företag. Det ger en bild av hur vissa enskilda tjänster används, baserat på alla användare som har aktiverats och de som är aktiva. Alla värden i månaden som visas i rapporten refererar till den senaste hela månaden. 

Med den här sammanfattningen kan du snabbt förstå användningsmönster i Office och hur och var dina anställda samarbetar.

![Bild av sammanfattningen av Microsoft 365-användningen.](../../media/office365usage-exec-summary.png)

## <a name="overview"></a>Översikt

Översiktsrapporten för Microsoft 365 innehåller följande rapporter. Du kan visa dem genom att välja fliken överst på rapportsidan. Alla värden i månaden som visas i det övre avsnittet i rapporten refererar till den senaste hela månaden.

- **Adoption** &ndash; Erbjuder en sammanfattning av antagandetrenderna. Använd rapporterna i det här avsnittet om du vill veta hur användarna har antagit Microsoft 365 och hur den totala användningen av de enskilda tjänsterna har ändrats månad för månad. Du kan se hur användarna är aktiverade, hur många personer i organisationen som aktivt använder Microsoft 365, hur många som returnerar användare och hur många som använder produkten för första gången.

- **Användning** &ndash; Erbjuder en nedrullningsvy över volymen aktiva användare och nyckelaktiviteterna för varje produkt under de senaste 12 månaderna. Använd rapporterna i det här avsnittet om du vill veta hur personer i organisationen använder Microsoft 365.

- **Kommunikation** &ndash; Du kan snabbt se om personer i organisationen föredrar att hålla kontakten med hjälp av Teams-, Yammer-, e-post- eller Skype-samtal. Du kan observera om det finns förändringar i mönster i användningen av kommunikationsverktyg bland dina anställda. 

- **Samarbete** &ndash; Se hur personer i organisationen använder OneDrive och SharePoint för att lagra dokument och samarbeta med varandra och hur dessa trender utvecklas månad för månad. Du kan också se hur många dokument som delas internt eller externt och hur många SharePoint-webbplatser eller OneDrive-konton som aktivt används, uppdelade efter ägare och andra medarbetare.

- **Lagring** &ndash; Använd den här rapporten för att spåra molnlagring för postlådor, OneDrive och SharePoint-webbplatser.

- **Mobilitetsspår** &ndash; vilka klienter och enheter som personer använder för att ansluta till e-post, Teams, Skype eller Yammer.

## <a name="activation-and-licensing"></a>Aktivering och licensiering

Aktiverings- och licenssidan innehåller rapporter om Microsoft 365-aktivering. det vill exempel på hur många användare som har hämtat och aktiverat Office-appar och hur många licenser som har tilldelats av din organisation. Månadsvärdet mot toppen refererar till den aktuella månaden och måtten återspeglar värden som aggregerats från början av månaden till det aktuella datumet.

- **Aktiveringsspårstjänstplan** &ndash; (till exempel Microsoft 365 ProPlus-, Project- och Visio-aktiveringar) i organisationen. Varje användare med en Office-licens kan installera produkter på upp till fem enheter. Du kan också använda rapporter i det här avsnittet för att se de enheter där personer har installerat Office-appar. Observera att för att aktivera ett abonnemang måste en användare installera appen och logga in med sitt konto.

- **Licensiering** &ndash; Den här rapporten innehåller en översikt över licenstyper, antalet användare som tilldelats varje licenstyp och licenstilldelningsdistributionen för varje månad. Månadsvärdet mot toppen refererar till den aktuella månaden och måtten återspeglar värden som aggregerats från början av månaden till det aktuella datumet.

## <a name="product-usage"></a>Användning av produkter

Den här rapporten innehåller en separat rapport för varje Microsoft 365-tjänst, inklusive Exchange, Microsoft 365-grupper, OneDrive, SharePoint, Skype, Teams och Yammer. Varje rapport innehåller totalt aktiverade kontra totalt antal aktiva användarrapporter, antal entiteter som postlådor, platser, grupper och konton samt aktivitetstyprapporter där så är lämpligt. Alla värden i månaden som visas i det övre avsnittet i rapporten refererar till den senaste hela månaden.

## <a name="user-activity"></a>Användaraktivitet

Användaraktivitetsrapporter är tillgängliga för vissa enskilda tjänster. Dessa rapporter innehåller informationsdata på användarnivå som är kopplade till Active Directory-attribut. I rapporten Avdelningsutförande kan du dessutom segmentera efter Active Directory-attribut så att du kan se aktiva användare i alla enskilda tjänster. Alla mått aggregeras för den senaste hela månaden.

## <a name="faq"></a>Vanliga frågor och svar

### <a name="is-this-template-app-going-to-be-available-through-purchase-or-will-it-be-free"></a>Är denna mall app kommer att vara tillgänglig via köp eller kommer det att vara gratis?

Det är inte gratis, du behöver en Power BI Pro-licens. Mer information finns [i förutsättningarna](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute#prerequisites) för att installera, anpassa och distribuera en mallapp.

Om du vill dela instrumentpanelerna med andra läser du mer på [Dela instrumentpaneler och rapporter](https://docs.microsoft.com/power-bi/service-how-to-collaborate-distribute-dashboards-reports#share-dashboards-and-reports).

### <a name="who-can-connect-to-microsoft-365-usage-analytics"></a>Vem kan ansluta till Microsoft 365 användningsanalyser?

Du måste antingen vara global **administratör**, **Exchange-administratör**, **Skype för företag-administratör,** **SharePoint-administratör,** **Global läsare** eller **Rapportläsare** för att upprätta anslutningen till mallappen. Mer information finns i [Om administratörsroller.](../add-users/about-admin-roles.md)

### <a name="who-can-customize-the-usage-analytics-reports"></a>Vem kan anpassa användningsanalysrapporterna?

Endast den användare som gjorde den första anslutningen till mallappen kan anpassa rapporterna eller skapa nya rapporter i Power BI-webbgränssnittet. Instruktioner [finns i Anpassa rapporterna i Microsoft 365-användningsanalys.](customize-reports.md)

### <a name="can-i-only-customize-the-reports-from-the-power-bi-web-interface"></a>Kan jag bara anpassa rapporterna från Power BI-webbgränssnittet?

Förutom att anpassa rapporterna från Power BI-webbgränssnittet kan användarna också använda Power BI Desktop för att ansluta direkt till Microsoft 365-rapporteringstjänsten för att skapa egna rapporter.

### <a name="how-can-i-get-the-pbit-file-that-this-dashboard-is-associated-with"></a>Hur får jag pbit-filen som är associerad med den här instrumentpanelen?

Du kan komma åt pbit-filen från [Microsoft Download Center](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit).

### <a name="who-can-view-the-dashboards-and-reports"></a>Vem kan visa instrumentpaneler och rapporter?

Om du är ansluten till mallappen kan du dela den med vem som helst med hjälp av [delningsfunktionen](https://go.microsoft.com/fwlink/p/?linkid=845494). Power BI-licensiering kräver att både användardelning och användare som en instrumentpanel delas med har Power BI Pro eller Power BI Premium.

### <a name="can-anyone-share-the-dashboard-or-does-it-have-to-be-the-person-who-connected-to-the-dashboard"></a>Kan vem som helst dela instrumentpanelen eller måste det vara den person som anslöt till instrumentpanelen?

När du delar instrumentpanelen kan du antingen tillåta användare att dela instrumentpanelen igen med andra eller inte. Du kan ställa in det här alternativet vid tidpunkten för delning.

### <a name="is-it-possible-to-work-on-and-customize-the-same-template-app-with-a-group-of-people"></a>Är det möjligt att arbeta med och anpassa samma mallapp med en grupp personer?

Ja. Om du vill att en grupp administratörer ska kunna arbeta tillsammans i samma mallapp kan du använda appens arbetsytas funktioner i Power BI, för mer information, se [Hur ska jag samarbeta och dela instrumentpaneler och rapporter?](https://go.microsoft.com/fwlink/p/?linkid=851070) 

### <a name="for-which-timeframe-is-data-available"></a>Inom vilken tidsram är data tillgängliga?

Majoriteten av rapporterna visar data för de föregående 12 månaderna. Vissa diagram kan dock visa mindre historik eftersom datainsamlingen för olika produkter och rapporter startades vid olika tidpunkter och därför kanske data för hela 12 månader kanske inte är tillgängliga. Alla rapporter kommer så småningom att bygga upp till 12 månaders historia. Rapporter som visar information på användarnivå visar data för föregående hela månad.

### <a name="what-data-is-included-in-the-template-app"></a>Vilka data ingår i mallappen?

Data i mallappen täcker för närvarande samma uppsättning aktivitetsmått som är tillgängliga i [aktivitetsrapporterna](../activity-reports/activity-reports.md). När rapporter läggs till i aktivitetsrapporterna läggs de till i mallappen i en framtida version.

### <a name="how-does-the-data-in-the-template-app-differ-from-the-data-in-the-usage-reports"></a>Hur skiljer sig data i mallappen från data i användningsrapporterna?

Underliggande data som visas i mallappen matchar de data som visas i aktivitetsrapporterna i administrationscentret för Microsoft 365. De viktigaste skillnaderna är att i admin center data är tillgänglig för de senaste 7/30/90/180 dagar medan mallappen presenterar data på månadsbasis i upp till 12 månader.

Dessutom är information på användarnivå i mallappen endast tillgänglig för den senaste hela månaden för användare som tilldelats en produktlicens och utförde en aktivitet.

### <a name="when-should-i-use-the-template-app-and-when-the-usage-reports"></a>När ska jag använda mallappen och när användningsrapporterna?

[Aktivitetsrapporterna](../activity-reports/activity-reports.md) är en bra utgångspunkt för att förstå användning och antagande av Microsoft 365. Mallappen kombinerar Microsoft 365-användningsdata och organisationens Active Directory-information och gör det möjligt för administratörer att analysera datauppsättningen med hjälp av funktionerna för visuell analys i Power BI. Detta gör det möjligt för administratörer att inte bara visualisera och analysera Microsoft 365 användningsdata, men också segmentera den efter Active Directory-egenskaper som avdelningar, plats etc. De kan också skapa anpassade rapporter och dela insikterna inom organisationen. 

### <a name="how-often-is-the-data-refreshed"></a>Hur ofta uppdateras data? 

När du ansluter till mallappen för första gången fylls de automatiskt i med dina data under de föregående 12 månaderna. Därefter uppdateras mallappdata varje vecka. Kunder kan välja att ändra uppdateringsschemat om deras användning av dessa data kräver en annan uppdateringsrytm.

Microsoft 365-tjänsten med serverdelsuppdatering uppdaterar data dagligen och tillhandahåller data som är mellan 5-8 dagar latent från det aktuella datumet.

Kolumnen **Innehållsdatum** i varje datauppsättning representerar färskhetsdatumet för data i mallappen.

### <a name="how-is-an-active-user-defined"></a>Hur definieras en aktiv användare?

Definitionen av aktiv användare är samma som definitionen av [aktiv användare](../activity-reports/active-users.md) i aktivitetsrapporterna.

### <a name="what-sharepoint-site-collections-are-included-in-the-sharepoint-reports"></a>Vilka SharePoint-webbplatssamlingar ingår i SharePoint-rapporterna?

Den aktuella versionen av mallappen innehåller filaktivitet från SharePoint-gruppwebbplatser och SharePoint-gruppwebbplatser.

### <a name="which-groups-are-included-in-the-microsoft-365-groups-usage-report"></a>Vilka grupper ingår i användningsrapporten för Microsoft 365 Grupper?

Den aktuella versionen av mallappen innehåller användning från Outlook-grupper, Yammer-grupper och SharePoint-grupper. Den innehåller inte grupper som är relaterade till Microsoft Teams eller Planner.

### <a name="when-will-an-updated-version-of-the-template-app-become-available"></a>När blir en uppdaterad version av mallappen tillgänglig?

Större ändringar i mallappen kommer att släppas två gånger om året, vilket kan innehålla nya rapporter eller nya data. Mindre ändringar av rapporterna kan komma att publiceras oftare.

### <a name="is-it-possible-to-integrate-the-data-from-the-template-app-into-existing-solutions"></a>Är det möjligt att integrera data från mallappen i befintliga lösningar? 

Data i mallappen kan hämtas via Microsoft 365 API:er (i förhandsversion). När de levereras till produktion slås de samman i [Microsoft Graph-rapporterings-API:erna](https://go.microsoft.com/fwlink/p/?linkid=848843). 

### <a name="are-there-plans-to-expand-the-template-app-to-show-usage-data-from-other-microsoft-products"></a>Finns det planer på att expandera mallappen för att visa användningsdata från andra Microsoft-produkter?

Detta övervägs för framtida förbättringar. Sök efter uppdateringar i [Microsoft 365-översikten.](https://www.microsoft.com/microsoft-365/roadmap)

### <a name="how-can-i-pivot-by-company-information-in-active-directory"></a>Hur kan jag pivotera efter företagsinformation i Active Directory?

Företagsinformation ingår i ett av Active Directory-fälten i mallappen och du kan se den som ett förbyggt filter i **aktivitetsrapporterna för produktanvändare.** Den är tillgänglig som kolumn i tabellen **UserState.**

### <a name="is-it-possible-to-bring-in-additional-fields-from-active-directory"></a>Går det att få in ytterligare fält från Active Directory?

Ytterligare anpassning av dessa data är möjlig genom att ansluta till [Microsoft Graph-rapporterings-API:erna](https://go.microsoft.com/fwlink/p/?linkid=848843) för att hämta ytterligare fält från Azure Active Directory och ansluta till datauppsättningen. 

### <a name="is-it-possible-to-aggregate-the-information-in-the-template-app-across-multiple-subscriptions"></a>Är det möjligt att sammanställa informationen i mallappen över flera prenumerationer?

Just nu är mallappen för en enda prenumeration, eftersom den är associerad med de autentiseringsuppgifter som användes för att först ansluta till den.

### <a name="is-it-possible-to-see-usage-by-plan-ie-e1-e3"></a>Är det möjligt att se användning per plan (dvs. E1, E3)?

I mallappen representeras användningen på produktnivå per produkt. Data om de olika prenumerationer som tilldelas användare tillhandahålls, men det går inte att korrelera användaraktiviteten till den prenumeration som tilldelats användaren.

### <a name="is-it-possible-to-integrate-other-data-sets-into-the-template-app"></a>Är det möjligt att integrera andra datauppsättningar i mallappen?

Du kan använda Power BI Desktop för att ansluta till Microsoft 365 API:er (i förhandsversion) för att få ytterligare datakällor att kombinera med mallappdata.

Mer information finns i [Anpassa dokumentet](customize-reports.md).

### <a name="is-it-possible-to-see-the-top-users-reports-for-a-specific-timeframe"></a>Är det möjligt att se rapporterna "Toppanvändare" för en viss tidsram?

Alla rapporter på användarnivå innehåller aggregerade data för föregående månad.

### <a name="will-the-template-app-be-localized"></a>Kommer mallappen att lokaliseras? 

Detta finns för närvarande inte med i färdplanen.

### <a name="i-have-a-specific-question-about-the-data-im-seeing-for-my-organization-who-can-i-reach-out-to"></a>Jag har en specifik fråga om de data jag ser för min organisation. Vem kan jag nå ut till?

Du kan använda feedbackknappen på översiktssidan för administrationscentrets aktivitet eller öppna ett [supportärende](../contact-support-for-business-products.md) för att få hjälp med mallappen. 

### <a name="how-can-partners-access-the-data"></a>Hur kan en partner komma åt data?

Om en partner har delegerade administratörsrättigheter kan han eller hon ansluta till mallappen för kundens räkning.

### <a name="can-i-hide-identifiable-information-such-as-user-group-and-site-names-in-reports"></a>Kan jag dölja identifierbar information som exempelvis användare, grupp och webbplatsnamn i rapporter?

Ja, se [Göra insamlade data anonyma](enable-usage-analytics.md#make-the-collected-data-anonymous).
