---
title: Hot jaga i Threat Explorer för Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Använd Threat Explorer eller identifieringar i realtid i Microsoft 365 Defender-portalen för att undersöka och reagera på hot effektivt.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71052cc5a3874da250772bfa628417824ba51c63
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930139"
---
# <a name="threat-hunting-in-threat-explorer-for-microsoft-defender-for-office-365"></a>Hot jaga i Threat Explorer för Microsoft Defender för Office 365

I den här artikeln:

- [Genomgång av Threat Explorer](#threat-explorer-walk-through)
- [Undersökning av e-post](#email-investigation)
- [E-postreparation](#email-remediation)
- [Förbättringar för att hitta hot](#improvements-to-threat-hunting-experience)

> [!NOTE]
> Det här är en del av en **3-artikelserie** om grunderna för identifiering av  **hotutforskaren (Explorer),** e-postsäkerhet och Utforskaren och **realtidsidentifiering** (till exempel skillnader mellan verktygen och behörigheter som krävs för att hantera dem). De andra två artiklarna i den här serien [är E-postsäkerhet](email-security-in-microsoft-defender.md) med Threat Explorer och Threat Explorer samt grundläggande funktioner för [identifiering i realtid.](real-time-detections.md)


**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Om din organisation har [Microsoft Defender för Office 365](defender-for-office-365.md) [](#required-licenses-and-permissions)och du har behörighet kan du använda **Utforskaren** eller **Realtidsidentifiering** för att identifiera och åtgärda hot. 

Gå till **Microsoft 365 E& samarbete** i **Defender-& och** välj sedan **Utforskaren**.

<br>

****

|Med Microsoft Defender för Office 365 abonnemang 2 visas:|Med Microsoft Defender för Office 365 abonnemang 1 visas:|
|---|---|
|![Hotutforskaren](../../media/path-to-explorer.png)|![Identifiering i realtid](../../media/threatmgmt-realtimedetections.png)|
|

Med dessa verktyg kan du:

- Se skadlig programvara som upptäckts Microsoft 365 säkerhetsfunktioner
- Visa nätfiske-URL och klicka på bedömningsdata
- Starta en automatiserad undersökning och svarsprocess från en vy i Utforskaren
- Undersöka skadlig e-post med mera

Mer information finns i [E-postsäkerhet med Hotutforskaren.](email-security-in-microsoft-defender.md) 

## <a name="threat-explorer-walk-through"></a>Genomgång av Threat Explorer

I Microsoft Defender för Office 365 finns det två abonnemang – abonnemang 1 och abonnemang 2. Manuellt använda sökverktyg för hot finns i båda abonnemangen, under olika namn och med olika funktioner.

Defender för Office 365 abonnemang 1 använder identifieringar i *realtid,* vilket är en del av sökverktyget i Threat *Explorer* (kallas även *Utforskaren)* i abonnemang 2. I den här serien med artiklar har de flesta av exemplen skapats med hjälp av hela Hotutforskaren. Administratörer bör testa stegen i realtidsidentifiering för att se var de är tillämpliga.

Om du vill öppna verktyget Utforskaren går du till **Microsoft 365 Defender-portalen**  >  **för & för samarbete i**  >  **Utforskaren.** Som standard kommer du till  sidan Skadlig programvara, men använder listrutan **Visa** för att bekanta dig med alternativen. Om du letar efter Phish eller är redo för en hotkampanj väljer du de här vyerna.

> [!div class="mx-imgBorder"]
> ![Listrutan Visa i Utforskaren med hot](../../media/view-drop-down.png)

När en säkerhetsoperationer (Sec Ops) väljer ut de data som de vill se, om omfattningen är smal vy som  användare Som skickar , eller en bredare vy, som All e-post, kan de använda knappen Avsändare för att filtrera ytterligare. Kom ihåg att välja Uppdatera för att slutföra filtreringsåtgärderna.

> [!div class="mx-imgBorder"]
> ![Knappen Avsändare i Utforskaren med hot](../../media/sender-drop-down.png)

Du kan tänka på att förfina fokus i Utforskaren eller Identifiering i realtid i lager. Det första är **Visa**. Det andra kan ses som ett *filtrerat fokus.* Du kan till exempel gå tillbaka till de steg du gick genom att registrera ett hot genom att registrera dina beslut så här: För att hitta problemet i Utforskaren valde jag vyn Skadlig programvara med filtret Mottagare i **fokus**. Det gör det enklare att ta om stegen.

> [!TIP]
> Om Sek Ops använder **taggar** för att markera konton som de överväger högvärdiga mål, kan de göra val som Phish View med ett *taggfilterfokus (ta* med ett datumintervall om det används). Då visas deras nätfiskeförsök mot användarens högvärdesmålen under en tidsperiod (t.ex. datum när vissa nätfiskeattacker pågår mycket inom branschen). 

Du kan förbättra datumintervallen med hjälp av kontrollerna för datumintervall. Här kan du se Utforskaren i **vyn Skadlig** programvara med filtret **Identifieringsteknik** i fokus. Men det är filterknappen **Avancerat som** gör att Sek Ops grupper kan gräva djupare. 

> [!div class="mx-imgBorder"]
> ![Avancerat filter i Hotutforskaren](../../media/advanced-filter.png)

Om du **klickar på filtret** Avancerat visas en panel som låter Sek Ops skapa frågor själva, så att de kan inkludera eller exkludera den information de behöver se. Både diagrammet och tabellen på sidan Utforskaren speglar deras resultat. 

> [!div class="mx-imgBorder"]
> ![Resultat från en fråga](../../media/threat-explorer-chart-table.png)

Använd knappen **Kolumnalternativ** för att få den typ av information om tabellen som skulle vara mest användbar: 

> [!div class="mx-imgBorder"]
> ![Knappen Kolumnalternativ markerad](../../media/threat-explorer-column-options.png)

> [!div class="mx-imgBorder"]
> ![Tillgängliga alternativ i Kolumner](../../media/column-options.png)

Testa bildskärmsalternativen med samma mien. Olika målgrupper kommer att reagera bra på olika presentationer med samma data. För vissa användare kan kartan för e-postsprung visa att  ett hot är svårt eller **ödslar** snabbare än visningsalternativet Kampanj bredvid det. Sek Ops kan använda dessa bildskärmar för att bäst understryka behovet av säkerhet och skydd, eller för senare jämförelse, för att visa hur effektivt deras åtgärder är. 

> [!div class="mx-imgBorder"]
> ![Karta över e-post origins](../../media/threat-explorer-email-origin-map.png)

> [!div class="mx-imgBorder"]
> ![Visningsalternativ för kampanj](../../media/threat-explorer-campaign-display.png)

### <a name="email-investigation"></a>Undersökning av e-post

När du ser ett misstänkt e-postmeddelande klickar du på namnet för att expandera den utfällade menyn till höger. Här är banderollen som låter Sek Ops se sidan med [e-post entitet](mdo-email-entity-page.md) tillgänglig.

Sidan för e-post entitet samlas ihop med innehåll som finns under **Information**, **Bifogade filer** **,** Enheter , men innehåller mer ordnade data. Det kan till exempel vara DMARC-resultat, oformaterad textvisning av e-postrubriken med ett kopieringsalternativ, bedömningsinformation om bifogade filer som har lösts och filer som detonationer har släppt (kan inkludera IP-adresser som kontaktades och skärmbilder på sidor eller filer). Webbadresser och deras bedömnings inrapporter visas också med liknande information. 

När du kommer till det här steget är sidan för e-post entitet kritisk till det sista steget *– åtgärd*. 

> [!div class="mx-imgBorder"]
> ![Sidan e-post entitet](../../media/threat-explorer-email-entity-page.png)

> [!TIP]
> Om du vill veta mer om sidan  med en omfattande e-post entitet (som visas nedan på fliken Analys), inklusive resultatet av detonerade bifogade filer, resultat för inkluderade webbadresser och säker förhandsgranskning av e-post, klickar du [här](mdo-email-entity-page.md).

> [!div class="mx-imgBorder"]
> ![Fliken Analys på sidan e-post entitet](../../media/threat-explorer-analysis-tab.png)

### <a name="email-remediation"></a>E-postreparation

När en sec Ops-person anser att ett e-postmeddelande är ett hot är nästa steg i Utforskaren eller identifiering i realtid att hantera hotet och åtgärda det. Det kan du göra genom att gå tillbaka till Hotutforskaren, markera kryssrutan för problemmeddelandet och använda **knappen** Åtgärder.

> [!div class="mx-imgBorder"]
> ![Knappen Åtgärder i Utforskaren med hot](../../media/threat-explorer-email-actions-button.png)

Här kan analytikern vidta åtgärder som att rapportera e-post som skräppost, nätfiske eller skadlig kod, kontakta mottagare eller ytterligare undersökningar som kan omfatta utlösa spelböcker för automatisk undersökning och svar (eller AIR) (om du har abonnemang 2). Eller så kan e-posten rapporteras som ren.

> [!div class="mx-imgBorder"]
> ![Listrutan Åtgärder](../../media/threat-explorer-email-actions-drop-down.png)

## <a name="improvements-to-threat-hunting-experience"></a>Förbättringar för att hitta hot

### <a name="alert-id"></a>Aviserings-ID

När du navigerar från en avisering till **Hotutforskaren filtreras** vyn med **aviserings-ID**. Det här gäller även vid identifiering i realtid. Meddelanden som är relevanta för den specifika aviseringen och en summa för e-post (antal) visas. Du kan se om ett meddelande var en del av en avisering och även navigera från det meddelandet till den relaterade aviseringen.

Slutligen inkluderas aviserings-ID i URL:en, till exempel: `https://https://security.microsoft.com/viewalerts`

> [!div class="mx-imgBorder"]
> ![Filtrera efter aviserings-ID](../../media/AlertID-Filter.png)

> [!div class="mx-imgBorder"]
> ![Aviserings-ID i den utfällade informationen](../../media/AlertID-DetailsFlyout.png)

### <a name="extending-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants"></a>Utöka databevarandet i Utforskaren (och realtidsidentifiering) och sökbegränsningen för utvärderingsklienter 

Som en del av den här ändringen kan analytiker söka efter och filtrera e-postdata i 30 dagar (ökad från sju dagar) i Threat Explorer och realtidsidentifiering för både Defender för Office P1- och P2-utvärderingsklienter. Detta påverkar inte några produktionsklienter för både P1- och P2 E5-kunder, där standardinställningen för bevarande redan är 30 dagar.

### <a name="updated-export-limit"></a>Uppdaterad exportgräns 

Antalet e-postposter som kan exporteras från Threat Explorer är nu 200 000 (var 9990). Uppsättningen kolumner som kan exporteras ändras inte. 

### <a name="tags-in-threat-explorer"></a>Taggar i Hotutforskaren

> [!NOTE]
> Funktionen med användartaggar är en förhandsversion och kanske inte tillgänglig för alla. Förhandsgranskningar kan också komma att ändras. Mer information om versionsschemat finns i översikten över Microsoft 365 version.

Användartaggar identifierar specifika användargrupper i Microsoft Defender för Office 365. Mer information om taggar, inklusive licensiering och konfiguration, finns i [Användartaggar.](user-tags.md)

I Hotutforskaren kan du se information om användartaggar i följande funktioner.

#### <a name="email-grid-view"></a>Rutnätsvyn för e-post

När analytiker tittar på **kolumnen Taggar** i e-postrutnätet ser de alla taggar som har tillämpats på avsändares eller mottagares postlådor. Som standard visas systemtaggar *som prioritetskonton* först.

> [!div class="mx-imgBorder"]
> ![Filtertaggar i rutnätsvyn för e-post](../../media/tags-grid.png)

#### <a name="filtering"></a>Filtrera

Taggar kan användas som filter. Jaga endast bland prioritetskonton eller använd specifika användartaggsscenarier på det här sättet. Du kan också utesluta resultat som har vissa taggar. Kombinera taggar med andra filter och datumintervall för att begränsa undersökningens omfattning. 

[![Filtertaggar](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)

> [!div class="mx-imgBorder"]
> ![Inte filtertaggar](../../media/tags-filter-not.png)

#### <a name="email-detail-flyout"></a>Utfällblad för e-postinformation

Om du vill visa de enskilda taggarna för avsändare och mottagare väljer du ett e-postmeddelande för att öppna den utfällade meddelandeinformationen. På fliken **Sammanfattning** visas taggarna för avsändare och mottagare separat. Informationen om enskilda taggar för avsändare och mottagare kan exporteras som CSV-data. 

> [!div class="mx-imgBorder"]
> ![Taggar för e-postinformation](../../media/tags-flyout.png)

Information om taggar visas också i den utfällade URL-klickningen. Du kan visa den i vyn Phish eller All e-> **url-adresser** **eller fliken URL-klickningar.** Välj en enskild utfällsida för URL om du vill se mer information om klickningar för URL-adressen, inklusive eventuella taggar som är kopplade till den klickningen.

### <a name="updated-timeline-view"></a>Uppdaterad tidslinjevy

> [!div class="mx-imgBorder"]
> ![URL-taggar](../../media/tags-urls.png)
>
Lär dig mer genom att titta på [den här videon](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).

## <a name="extended-capabilities"></a>Utökade funktioner

### <a name="top-targeted-users"></a>Mest riktade användare

Populära programfamiljer för skadlig **programvara visar de mest riktade användarna** i avsnittet Om skadlig programvara. De mest riktade användarna kommer även att utökas genom vyerna Phish och All e-post. Analytiker kommer att kunna se de fem viktigaste användarna, tillsammans med antalet försök för varje användare i varje vy. 

Säkerhetsåtgärder användarna kan exportera listan med riktade användare, upp till en gräns på 3 000, tillsammans med antalet försök som gjorts, för offlineanalys för varje e-postvy. Om du väljer antalet försök (till exempel 13 försök i bilden nedan) öppnas en filtrerad vy i Hotutforskaren, så att du kan se mer information om e-postmeddelanden och hot för den användaren.  

> [!div class="mx-imgBorder"]
> ![Mest riktade användare](../../media/Top_Targeted_Users.png)

### <a name="exchange-transport-rules"></a>Exchange för transport

Säkerhetsgruppen kommer att kunna se alla transportregler (Exchange eller E-postflödesregler) som tillämpas på ett meddelande i rutnätsvyn för e-post. Välj **Kolumnalternativ** i rutnätet och välj **sedan Exchange för Transportregel** bland kolumnalternativen. Alternativet Exchange För transportregler visas också på den utfällbara **informationen** i e-postmeddelandet. 

Namn och GUID för transportregler som tillämpas på meddelandet visas. Analytiker kan söka efter meddelanden med hjälp av namnet på transportregeln. Det här är en CONTAINS-sökning, vilket innebär att det även går att göra partiella sökningar. 

> [!IMPORTANT]
> Exchange med transportregelsökning och namntillgänglighet beror på vilken roll du har tilldelats. Du måste ha någon av följande roller eller behörigheter för att visa transportregelnamn och sökning. Men även utan rollerna eller behörigheterna nedan kan en analytiker se transportregeletiketten och GUID-informationen i e-postinformationen. Andra funktioner för postvisning i e-postrutnät, utfällningar av e-post, filter och export påverkas inte.
>
> - Exchange Online Endast – skydd mot dataförlust: alla
> - Exchange Online Endast – O365SupportViewConfig: Alla
> - Microsoft Azure Active Directory eller Exchange Online – säkerhetsadministratör: Alla
> - Azure Active Directory eller Exchange Online – Säkerhetsläsare: Alla
> - Exchange Online Endast – Transportregler: Alla
> - Exchange Online Endast – View-Only konfiguration: Alla
>
> I e-postrutnätet, den utfällliga listan Information och Exporterad CSV visas ETR-trafikerna med ett Namn/GUID enligt nedan.
>
> > [!div class="mx-imgBorder"]
> > ![Exchange Transportregler](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a>Inkommande kopplingar

Kopplingar är en samling instruktioner som anpassar hur din e-post flödar till och från din Microsoft 365 eller Office 365 organisation. De gör att du kan tillämpa alla säkerhetsbegränsningar eller kontroller. I Hotutforskaren kan du visa kopplingar som är relaterade till ett e-postmeddelande och söka efter e-postmeddelanden med hjälp av kopplingsnamn. 

Sökningen efter kopplingar är en CONTAINS-fråga, vilket innebär att partiella nyckelordssökningar kan fungera: 

> [!div class="mx-imgBorder"]
> ![Kopplingsinformation](../../media/Connector_Details.png)

## <a name="required-licenses-and-permissions"></a>Obligatoriska licenser och behörigheter

Du måste ha [Microsoft Defender Office 365](defender-for-office-365.md) kunna använda Utforskaren eller identifiering i realtid.

- Utforskaren ingår i Defender för Office 365 abonnemang 2.
- Rapporten Identifieringar i realtid ingår i Defender för Office 365 abonnemang 1.
- Planera att tilldela licenser till alla användare som ska skyddas av Defender för Office 365. I Utforskaren och identifiering i realtid visas identifieringsdata för licensierade användare.

Om du vill visa och använda Utforskaren eller Identifieringar i realtid måste du ha följande:

- På Microsoft 365 Defender-portalen:

  - Organisationshantering
  - Säkerhetsadministratör (det här kan tilldelas Azure Active Directory administrationscentret ( <https://aad.portal.azure.com> )
  - Säkerhetsläsare

- För Exchange Online:

  - Organisationshantering
  - View-Only organisationshantering
  - View-Only mottagare
  - Efterlevnadshantering

Mer information om roller och behörigheter finns i följande resurser:

- [Behörigheter på Microsoft 365 Defender-portalen](permissions-in-the-security-and-compliance-center.md)
- [Funktionsbehörigheter i Exchange Online](/exchange/permissions-exo/feature-permissions)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a>Mer information

- [Hitta och undersöka skadlig e-post som har levererats](investigate-malicious-email-that-was-delivered.md) 
- [Visa skadliga filer som upptäckts SharePoint Online, OneDrive och Microsoft Teams](mdo-for-spo-odb-and-teams.md) 
- [Få en översikt över vyerna i Hotutforskaren (och identifieringar i realtid)](threat-explorer-views.md) 
- [Statusrapport för hotskydd](view-email-security-reports.md#threat-protection-status-report) 
- [Automatisk undersökning och svar i Microsoft Threat Protection](automated-investigation-response-office.md) 
- [Undersöka e-postmeddelanden med sidan E-post entitet](mdo-email-entity-page.md)