---
title: Undersök skadlig e-post som har levererats i Office 365, hitta och undersöka skadlig e-post
keywords: TIMailData-inline, säkerhets tillbud, incident, ATP PowerShell, skadlig program vara, obehörig användare, e-Phish, e-postskadlig kod, läsa rubriker, öppna e-postrubriker, särskilda åtgärder
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 07/09/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: Lär dig hur du använder hot-och svars funktioner för att hitta och undersöka skadlig e-post.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5026b69f356fad11a664900a3e316d9c1c976905
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845960"
---
# <a name="investigate-malicious-email-that-was-delivered-in-office-365"></a>Undersök skadlig e-post som har levererats i Office 365

Med [Office 365 Avancerat skydd](office-365-atp.md) kan du undersöka aktiviteter som ger folk i din organisation till risk och att vidta åtgärder för att skydda din organisation. Om du till exempel är en del av din organisations säkerhets team kan du hitta och undersöka misstänkta e-postmeddelanden som har levererats. Du kan göra det med hjälp av [Threat Explorer (eller identifieringar i real tid)](threat-explorer.md).

> [!NOTE]
> Hoppa till reparations artikeln [här](https://docs.microsoft.com/microsoft-365/security/mtp/article-submission/remediate-malicious-email-delivered-office-365?view=o365-21vianet&branch=pr-en-us-4258).

## <a name="before-you-begin"></a>Innan du börjar

Kontrol lera följande krav:

- Din organisation har [Office 365 Avancerat skydd](office-365-atp.md) och [licenser är tilldelade till användare](../../admin/manage/assign-licenses-to-users.md).

- [gransknings loggning](../../compliance/turn-audit-log-search-on-or-off.md) är aktiverat för din organisation.

- Din organisation har principer som har definierats för att förhindra skräp post, mot skadlig program vara och så vidare. Se [skydda mot hot i Office 365](protect-against-threats.md).

- Du är global administratör, eller så har du antingen säkerhets administratören eller Sök-och säkerhets rollen för säkerhets &amp; kontroll. Se [behörigheter i säkerhetsrelaterade &amp; Center](permissions-in-the-security-and-compliance-center.md). För vissa åtgärder måste du också ha en ny för hands versions förhands granskning.

### <a name="preview-role-permissions"></a>Förhandsgranska roll behörigheter

Om du vill utföra vissa åtgärder, till exempel Visa meddelande rubriker eller hämta e-postinnehåll, måste du ha en ny roll som heter för *förhands granskning* tillagd i en annan lämplig roll grupp. Följande tabell förklarar de roller och behörigheter som krävs.

****

|Aktivitet|Roll grupp|Vill du för hands Visa den?|
|---|---|---|
|Använd Threat Explorer (och real tids identifieringar) för att analysera hot |Global administratör <br> Säkerhets administratör <br> Säkerhets läsare|Nej|
|Använd Threat Explorer (och real tids identifieringar) för att visa rubriker för e-postmeddelanden samt för hands Visa och ladda ned e-postmeddelanden i karantän|Global administratör <br> Säkerhets administratör <br>Säkerhets läsare|Nej|
|Använda Threat Explorer för att visa rubriker och hämta e-postmeddelanden som skickas till post lådor|Global administratör <br>Säkerhets administratör <br> Säkerhets läsare <br> Automatisk|Ja|
|

> [!NOTE]
> För *hands versionen* är en roll och inte en roll grupp; förhands gransknings rollen måste läggas till i en befintlig roll grupp för Office 365. Rollen global administratör har tilldelats administratörs Center för Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ) och rollerna säkerhets administratör och säkerhets läsare tilldelas i säkerhets & Compliance Center ( [https://protection.office.com](https://protection.office.com) ). Mer information om roller och behörigheter finns i [behörigheter i säkerhets & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>Hitta och ta bort misstänkta e-postmeddelanden som har levererats

Threat Explorer är en kraftfull rapport som kan hantera flera ändamål, till exempel att söka efter och ta bort meddelanden, identifiera IP-adressen för en oönskad e-avsändare eller påbörja en olycka för ytterligare undersökning. Följande procedur fokuserar på att använda Utforskaren för att hitta och ta bort skadlig e-post från mottagares post lådor.

> [!NOTE]
> Standard sökningar i Utforskaren inkluderar för närvarande inte zapped-objekt.  Detta gäller för alla vyer, till exempel skadliga program och Phish. Om du vill inkludera Zappeda objekt måste du lägga till en "leverans åtgärd" för att ta med "borttagen av ZAP". Om du inkluderar alla alternativ visas alla leverans resultat, inklusive zapped-objekt.

1. **Navigera till Threat Explorer**: gå till [https://protection.office.com](https://protection.office.com) och logga in med ditt arbets-eller skol konto för Office 365. Då kommer du till säkerhets &amp; kontroll Center.

2. Välj **Threat Management** Explorer i navigerings fältet till vänster \> **Explorer**.

    ![Explorer med fälten leverans åtgärd och leverans plats.](../../media/ThreatExFields.PNG)

    Du kan märka den nya kolumnen **särskilda åtgärder** . Denna funktion syftar till att berätta för administratörer resultatet av att bearbeta ett e-postmeddelande. Kolumnen **särskilda åtgärder** kan nås på samma plats som **leverans åtgärden** och **leverans platsen**. Särskilda åtgärder kan uppdateras efter att hot Explorers e-posttids linje är en ny funktion som syftar till att förbättra jakt upplevelsen för administratörer.

3. **Vyer i Threat Explorer**: Välj **all e-post**i menyn **Visa** .

    ![Threat Explorer Visa-menyn och e-postskadlig kod, Phish, inlämning och alla e-postalternativ, även skadlig program vara.](../../media/tp-InvestigateMalEmail-viewmenu.png)

    Vyn för *skadliga program* är för närvarande standard och fångar in e-postmeddelanden där ett hot mot skadlig kod upptäcks. *Phish* -vyn fungerar på samma sätt för Phish.

    *Alla e-* postvyer visar alla e-postmeddelanden som tagits emot av organisationen, oavsett om det upptäckts eller inte. Det här är många data, vilket är orsaken till att ett filter används för den här vyn. (Den här vyn är bara tillgänglig för ATP-kunder.)

    I vyn *inlämning* visas alla e-postmeddelanden som skickas av administratören eller användaren som har rapporter ATS till Microsoft.

4. **Sök och filtrera i Threat Explorer**: filter visas högst upp på sidan i Sök fältet för att hjälpa administratörer i deras utredningar. Observera att det går att använda flera filter samtidigt och flera kommaavgränsade värden som läggs till i ett filter för att begränsa sökningen. Tid

    - Filter gör exakt matchning på de flesta filter villkor.
    - Ämnes filter använder en innehåller-fråga.
    - URL-filter fungerar med eller utan protokoll (ex. https).
    - URL-domän, URL-sökväg och URL-domän och Sök vägs filter kräver inte protokollet för att filtrera.
    - Du måste klicka på ikonen Uppdatera varje gång du ändrar filter värden för att få relevanta resultat.

5. **Avancerade filter**: med de här filtren kan du skapa komplexa frågor och filtrera data uppsättningen. Om du klickar på *Avancerade filter* öppnas en utfällbar med alternativ.

   Avancerad filtrering är ett fantastiskt tillägg för Sök funktioner. Ett booleskt **icke** -filter har introducerats på *mottagare*, *avsändare* och *avsändare-domän* för att tillåta att administratörer undersöker genom att exkludera värden. Det här alternativet visas under markerings parameter *som inte innehåller något av*. Om du **inte** vill att administratörer ska utesluta aviserings post lådor, standard brev lådor från deras undersökningar och är användbart i de fall då administratörer söker efter ett specifikt ämne (ämne = "Attention") där mottagaren kan ställas in på *ingen av defaultMail \@ contoso.com*. Det här är en exakt Sök funktion.

   ![Mottagarna-' contains inget av ' Avancerat filter.](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   Om du *filtrerar efter timmar* blir det lättare för din organisations säkerhets grupp att öka detalj nivån. Den kortast tillåtna tids åtgången är 30 minuter. Om du kan begränsa den misstänkta åtgärden till tid bild ruta (t. ex. det hände 3 timmar sedan) så begränsas kontexten och hjälp till att hitta problemet.

   ![Alternativet filtrera efter timmar för att begränsa mängden data säkerhets team som måste behandlas och vars kortast varaktighet är 30 minuter.](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. **Fält i Threat Explorer**: Threat Explorer visar mycket mer säkerhetsrelaterad e-postinformation som *leverans åtgärd*, *leverans plats*, *särskild åtgärd, befattning* *,* *åsidosättningar*och URL- *hot*. Det gör det också möjligt för din organisations säkerhets grupp att undersöka det med högre säkerhet.

    *Leverans åtgärden* är den åtgärd som utförs via e-post på grund av befintliga principer eller identifieringar. Här är de möjliga åtgärder som ett e-postmeddelande kan ta:

    - **Levererat** – e-post levererades till Inkorgen eller mappen för en användare och användaren kan komma åt den direkt.
    - **Skräp post** – e-postmeddelandet skickades till antingen användarens skräppostmappen eller mappen Borttaget, och användaren har till gång till e-postmeddelanden i sina skräppostmappen.
    - **Blockerad** – alla e-postmeddelanden som har satts i karantän, som misslyckats eller släppts. (Det här är inte tillgängligt för användaren.)
    - **Ersatt** – ett e-postmeddelande där skadligt bifogade filer ersätts med txt-filer som gör att den bifogade filen har skadligt

    **Leverans plats**: filtret för leverans plats är tillgängligt för att administratörer ska förstå var misstänkt skadlig e-post har avslut ATS och vilka åtgärder som vidtogs. Resultatet kan exporteras till kalkyl bladet. Möjliga leverans ställen är:

    - **Inkorg eller mapp** – e-postmeddelandet finns i Inkorgen eller i en specifik mapp enligt dina e-postregler.
    - **On-lokala eller external** – post lådan finns inte i molnet, men den är lokal.
    - **Skräppostmappen** – e-postmeddelandet finns i en användares mapp för skräp post.
    - **Mappen Borttaget** – e-postmeddelandet finns i mappen Borttaget.
    - **Karantän** – e-postmeddelandet i karantän och inte i en användares post låda.
    - **Misslyckades** -det gick inte att nå post lådan.
    - **Släppt** – e-postmeddelandet har kopplats ned någonstans i e-postflödet.

    **Riktad**: med det här alternativet kan säkerhets åtgärds gruppen filtrera efter "riktningen" ett e-postmeddelande kommer från eller går. Riktnings värden är *inkommande*, *utgående*och *inom organisation* (motsvarande e-post som kommer till ditt organisations samtal från en annan plats, som skickas från din organisation eller skickas internt till din organisation. Den här informationen kan hjälpa dig att skydda säkerhets åtgärder för att upptäcka förfalskningar och användning, eftersom en avvikelse mellan värdet (ex. *Inkommande*) och avsändarens domän (som *verkar* vara en intern domän), är det tydligt! Värdet för riktning är avgränsat och kan skilja sig från meddelande spårningen. Resultat kan exporteras till kalkyl bladet.

    **Åsidosättningar**: det här filtret tar information som visas på e-postmeddelandets informations flik och använder det för att visa var organisations-och användar principer har *åsidosatts*. Det viktigaste med filtret är att det hjälper organisationens säkerhets team att se hur många misstänkta e-postmeddelanden som levererats på grund av konfiguration. Då får de möjlighet att ändra Tillåt och blockera efter behov. Det här filtret kan exporteras till kalkyl bladet.

    ****

    |Åsidosättning av Threat Explorer|Vad de betyder|
    |---|---|
    |Tillåts av organisations princip|E-post har skickats till post lådan enligt organisationens policy.|
    |Blockerat av organisations princip|E-post har blockerats från leverans till post lådan enligt organisationens policy.|
    |Fil tillägget blockerat av en organisations princip|Filen blockerades från leverans till post lådan enligt organisationens policy.|
    |Tillåts av en användar princip|E-post har skickats till post lådan enligt användar policyn.|
    |Blockerad av en användar princip|E-post har blockerats från leverans till post lådan enligt användar policyn.|
    |

    **URL-hot**: fältet URL-hot har inkluderats på fliken *information* i ett e-postmeddelande för att visa att en URL-adress visas för hotet. Hot som presenteras av en URL kan inkludera *skadlig kod*, *Phish*eller *skräp post*, och en URL utan *hotet* säger *ingen* i avsnittet hot.

7. **Vyn tids linje för e-post**: dina säkerhets åtgärder kan behöva djupgående för att visa e-postuppgifter. Med e-posttids linjen kan administratörer se åtgärder på ett e-postmeddelande från leveransen till efter leverans. Om du vill visa en e-posttidslinje klickar du på ämnet för e-postmeddelandet och sedan på e-postschema. (Det visas i andra rubriker på panelen som Sammanfattning eller Detaljer.) De här resultaten kan exporteras till kalkyl bladet.

    E-posttids linjen öppnas i en tabell som visar alla leverans-och efter leverans händelser för e-postmeddelandet. Om det inte finns några fler åtgärder i e-postmeddelandet bör du se en händelse för den ursprungliga leveransen som ger ett resultat, till exempel *blockerat*, med en Verdict som *Phish*. Administratörer kan exportera hela e-postschemat, inklusive all information om fliken och e-post (till exempel ämne, avsändare, mottagare, nätverk och meddelande-ID). E-postlinjen klipps av ned på slump slag eftersom det är mindre tid att kontrol lera olika platser för att försöka förstå händelser som har hänt sedan e-postmeddelandet kom. När flera händelser inträffar till, eller nära, samtidigt i ett e-postmeddelande, visas händelserna i vyn tids linje.

8. För **hands version/nedladdning**: Threat Explorer ger din säkerhets policy den information de behöver för att undersöka misstänkt e-post. Din säkerhets åtgärd kan antingen:

    - [Kontrol lera leverans åtgärden och plats](#check-the-delivery-action-and-location).

    - [Visa tids linjen för din e-post](#view-the-timeline-of-your-email).

### <a name="check-the-delivery-action-and-location"></a>Kontrol lera leverans åtgärd och plats

I [Threat Explorer (och real tids identifieringar)](threat-explorer.md)har du nu **leverans** -och **leverans plats** kolumner i stället för kolumnen förra **leverans status** . Detta ger en mer fullständig bild av var e-postmeddelandena hamnar. Delar av syftet med ändringen är att göra det enklare att underkänna sig på säkerhets åtgärder, men netto resultatet är att få reda på var det finns problem med e-postmeddelanden.

Leverans status är nu uppdelad i två kolumner:

- **Leverans åtgärd** – vilken är statusen för det här meddelandet?

- **Leverans plats** – var hette detta e-postmeddelande som ett resultat?

Leverans åtgärden är den åtgärd som utförs via e-post på grund av befintliga principer eller identifieringar. Här är de möjliga åtgärder som ett e-postmeddelande kan ta:

- **Levererat** – e-post levererades till Inkorgen eller mappen för en användare och användaren kan komma åt den direkt.

- **Skräp post** – e-postmeddelandet skickades antingen till användarens skräppostmappen eller mappen Borttaget, och användaren har till gång till e-postmeddelanden i mappen skräp post.

- **Blockerad** – alla e-postmeddelanden som har satts i karantän, som misslyckats eller släppts. (Det här är inte tillgängligt för användaren.)

- **Ersatt** – ett e-postmeddelande där skadligt bifogade filer ersätts med txt-filer som gör att den bifogade filen har skadligt.

Leverans platsen visar resultaten av principer och upptäckter med efter-leverans. Den är länkad till en leverans åtgärd. Det här fältet lades till för att ge insyn i den åtgärd som utförs när ett problem har uppstått. Här är möjliga värden för leverans plats:

- **Inkorg eller mapp** – e-postmeddelandet finns i Inkorgen eller i en mapp (enligt dina e-postregler).

- **On-lokala eller external** – post lådan finns inte i molnet, men den är lokal.

- **Skräppostmappen** – e-postadressen finns i en användares skräppost-mapp.

- **Mappen Borttaget** – e-postmeddelandet finns i mappen Borttaget.

- **Karantän** – e-postmeddelandet i karantän och inte i en användares post låda.

- **Misslyckades** -det gick inte att nå post lådan.

- **Släppt** – e-postmeddelandet tappas bort någonstans i e-postflödet.

### <a name="view-the-timeline-of-your-email"></a>Visa tids linjen för din e-post

**E-Posttids linje** är ett fält i Threat Explorer som gör det lättare för dina säkerhets åtgärder. När flera händelser inträffar samtidigt eller nära varandra i ett e-postmeddelande visas händelserna i vyn tids linje. Vissa händelser som inträffar efter leveransen i e-postmeddelandet sparas i kolumnen **särskilda åtgärder** . Om du kombinerar information från tids linjen för ett e-postmeddelande med eventuella särskilda åtgärder som vidtogs efter publiceringen blir administratörer inblick i policy-och Threat-hanteringen (till exempel var e-postadressen cirkulerades och i vissa fall vad den slutliga utvärderingen var).

> [!IMPORTANT]
> Hoppa till ett reparations ämne [här](https://docs.microsoft.com/microsoft-365/security/mtp/article-submission/remediate-malicious-email-delivered-office-365?view=o365-worldwide).

## <a name="related-topics"></a>Relaterade ämnen

[Åtgärda skadlig e-post som skickas i Office 365](https://docs.microsoft.com/microsoft-365/security/mtp/article-submission/remediate-malicious-email-delivered-office-365?view=o365-worldwide)

[Office 365 Avancerat skydd](office-365-ti.md)

[Skydda mot hot i Office 365](protect-against-threats.md)

[Visa rapporter för Office 365 Avancerat skydd](view-reports-for-atp.md)
