---
title: Undersöka skadlig e-post som levererats i Office 365, hitta och undersöka skadlig e-post
keywords: TIMailData-Inline, Security Incident, incident, ATP PowerShell, email malware, compromised users, email phish, email malware, read email headers, read headers, open email headers,special actions
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/16/2020
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: Lär dig hur du använder funktioner för hotundersökning och -svar för att hitta och undersöka skadlig e-post.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b36e16f5351ab30ac8150fbc3e87feb9ca4a6453
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286639"
---
# <a name="investigate-malicious-email-that-was-delivered-in-office-365"></a>Undersöka skadlig e-post som levererats i Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**

- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[Med Microsoft Defender för Office 365](office-365-atp.md) kan du undersöka aktiviteter som riskerar för personer i organisationen och vidta åtgärder för att skydda din organisation. Om du till exempel ingår i organisationens säkerhetsteam kan du söka efter och undersöka misstänkta e-postmeddelanden som levererades. Det kan du göra med [hjälp av Hotutforskaren (eller identifieringar i realtid).](threat-explorer.md)

> [!NOTE]
> Gå till åtgärdsartikeln [här.](remediate-malicious-email-delivered-office-365.md)

## <a name="before-you-begin"></a>Innan du börjar

Kontrollera att följande krav uppfylls:

- Din organisation har [Microsoft Defender för Office 365](office-365-atp.md) och licenser [tilldelas till användare.](../../admin/manage/assign-licenses-to-users.md)

- [granskningsloggning](../../compliance/turn-audit-log-search-on-or-off.md) är aktiverat för organisationen.

- Organisationen har definierat principer för skydd mot skräppost, skadlig programvara, nätfiske och så vidare. Se [Skydda mot hot i Office 365.](protect-against-threats.md)

- Du är global administratör eller har antingen säkerhetsadministratören eller rollen Sök och rensning tilldelad i Säkerhets- & Efterlevnadscenter. Se [behörigheter i Säkerhets- & Efterlevnadscenter.](permissions-in-the-security-and-compliance-center.md) För vissa åtgärder måste du också ha en ny roll för förhandsgranskning tilldelad.

### <a name="preview-role-permissions"></a>Förhandsgranskningsrollbehörigheter

Om du vill utföra vissa åtgärder, till exempel visa meddelanderubriker eller  ladda ned innehåll i e-postmeddelanden, måste du ha en ny roll som kallas Förhandsgranskning tillagd i en annan lämplig rollgrupp. I följande tabell förtydligas de roller och behörigheter som krävs.

****

|Aktivitet|Rollgrupp|Krävs en förhandsgranskningsroll?|
|---|---|---|
|Använda Hotutforskaren (och identifieringar i realtid) för att analysera hot |Global administratör <p> Säkerhetsadministratör <p> Säkerhetsläsare|Nej|
|Använd HotUtforskaren (och identifieringar i realtid) för att visa rubriker för e-postmeddelanden samt förhandsgranska och ladda ned e-postmeddelanden i karantän|Global administratör <p> Säkerhetsadministratör <p> Säkerhetsläsare|Nej|
|Använda Hotutforskaren för att visa rubriker, förhandsgranska e-post (endast på sidan för e-post entitet) och ladda ned e-postmeddelanden som levereras till postlådor|Global administratör <p> Säkerhetsadministratör <p> Säkerhetsläsare <p> Förhandsgranska|Ja|
|

> [!NOTE]
> *Förhandsgranskning* är en roll och inte en rollgrupp. Förhandsversionsrollen måste läggas till i en befintlig rollgrupp för Office 365 (at [https://protection.office.com](https://protection.office.com) ). Gå till **Behörigheter** och redigera sedan en befintlig rollgrupp eller lägg till en ny rollgrupp med tilldelad **förhandsversionsroll.**
> Rollen Global administratör tilldelas administratörscentret för Microsoft 365 ( ), och rollerna Säkerhetsadministratör och Säkerhetsläsare tilldelas i Säkerhets- <https://admin.microsoft.com> & Efterlevnadscenter <https://protection.office.com> (). Mer information om roller och behörigheter finns i [Behörigheter i Säkerhets- & Efterlevnadscenter.](permissions-in-the-security-and-compliance-center.md)

Vi förstår att förhandsgranskning och nedladdning av e-post är känsliga aktiviteter och därför är granskning aktiverad för dessa. När en administratör utför de här aktiviteterna i e-postmeddelanden genereras granskningsloggar för samma och visas i Säkerhets- och efterlevnadscenter & för Office 365 ( [https://protection.office.com](https://protection.office.com) ). Gå till **Sök**  >  **granskningsloggsökning** och filtrera på administratörsnamnet i avsnittet Sök. De filtrerade resultaten visar aktiviteten **AdminMailAccess.** Markera en rad för att visa information i avsnittet **Mer information** om förhandsgranskad eller hämtad e-post.

## <a name="find-suspicious-email-that-was-delivered"></a>Hitta misstänkta e-postmeddelanden som har levererats

Threat Explorer är en kraftfull rapport som kan ha flera syften, till exempel att söka efter och ta bort meddelanden, identifiera IP-adressen för en skadlig e-postavsändare eller starta en incident för ytterligare undersökning. Följande procedur fokuserar på att använda Utforskaren för att hitta och ta bort skadlig e-post från mottagarens postlådor.

> [!NOTE]
> Standardsökningar i Utforskaren inkluderar för närvarande inte zapped objekt.  Det här gäller för alla vyer, till exempel skadlig programvara eller phish-vyer. Om du vill inkludera Zapped-objekt måste du lägga till **en leveransåtgärd som** är inställd på att **inkludera Borttaget av ZAP.** Om du inkluderar alla alternativ visas alla leveransåtgärdsresultat, inklusive Zapped items.

1. **Navigera till Hotutforskaren:** Gå <https://protection.office.com> till och logga in med ditt arbets- eller skolkonto för Office 365. Då kommer du till Säkerhets- & Efterlevnadscenter.

2. Välj Hot management Explorer i det vänstra **navigeringsfältet.** \> 

    ![Utforskaren med fälten Leveransåtgärd och Leveransplats.](../../media/ThreatExFields.PNG)

    Du kanske ser den nya **kolumnen Specialåtgärder.** Den här funktionen är avsedd att berätta för administratörer resultatet av att bearbeta ett e-postmeddelande. Kolumnen **Specialåtgärder** kan nås på samma plats som **leveransåtgärd och** **leveransplats.** Särskilda åtgärder kan uppdateras i slutet av hotutforskarens e-posttidslinje, vilket är en ny funktion som är avsedd att ge administratörer en bättre upplevelsen.

3. **Vyer i Hotutforskaren:** Välj **All e-post** på **Visa-menyn.**

    ![Menyn För visning av hotutforskaren och e-post – skadlig programvara, nätt innehåll och alla e-postalternativ, även innehåll – skadlig programvara.](../../media/tp-InvestigateMalEmail-viewmenu.png)

    Vyn *skadlig* programvara är för närvarande standard och fångar e-postmeddelanden där ett skadlig kodshot identifieras. *Phish-vyn* fungerar på samma sätt för Phish.

    I vyn *All e-post* visas dock alla meddelanden som tas emot av organisationen, oavsett om hot har upptäckts eller inte. Som du kan föreställa dig är det mycket data, vilket är anledningen till att den här vyn visar en platshållare som begär att ett filter ska användas. (Den här vyn är endast tillgänglig för Defender för Office 365 P2-kunder.)

    *Vyn För* inskickade uppgifter visar alla e-postmeddelanden som skickats av administratören eller användaren och som har rapporterats till Microsoft.

4. **Sökning och filter i Hotutforskaren:** Filter visas högst upp på sidan i sökfältet för att hjälpa administratörer i sina undersökningar. Observera att flera filter kan användas samtidigt och att flera kommaavgränsade värden läggs till i ett filter för att begränsa sökningen. Kom ihåg:

    - Filter matchar exakt på de flesta filtervillkor.
    - Ämnesfilter använder en CONTAINS-fråga.
    - URL-filter fungerar med eller utan protokoll (t.ex. https).
    - URL-domän, URL-sökväg samt URL-domän och sökvägsfilter kräver inte ett protokoll för att filtrera.
    - Du måste klicka på uppdateringsikonen varje gång du ändrar filtervärdena för att få relevanta resultat.

5. **Avancerade filter:** Med dessa filter kan du skapa komplexa frågor och filtrera datauppsättningen. Om du *klickar på Avancerade* filter öppnas en utfällsmöjligheter med alternativ.

   Avancerad filtrering är ett bra tillägg till sökfunktionerna. Ett booleskt **NOT-filter** har  införts i domänen *Mottagare,* Avsändare och *Avsändare* för att tillåta administratörer att undersöka genom att utesluta värden. Det här alternativet visas under *urvalsparametern Innehåller ingen av*. **INTE** låta administratörer utesluta aviseringspostlådor, standardsvarspostlådor från undersökningarna och är användbara i fall där administratörer söker efter ett visst ämne (ämne ="Uppmärksamhet") där mottagaren kan anges till ingen standardpostlåda *\@ contoso.com.* Det här är en exakt värdesökning.

   ![Mottagarna – filtret "Innehåller inget av" Avancerat.](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   *Om du filtrerar* efter timmar kan organisationens säkerhetsteam snabbt öka detalj detalj detaljringen. Den kortaste tillåtna varaktigheten är 30 minuter. Om du kan begränsa den misstänkta åtgärden efter tidsperiod (t.ex. för 3 timmar sedan), begränsar det här sammanhanget och gör det enkelt att hitta problemet.

   ![Alternativet filtrera efter timmar för att begränsa mängden datasäkerhetsgrupper måste bearbetas och vars kortaste varaktighet är 30 minuter.](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. **Fält i** Hotutforskaren: Hotutforskaren visar mycket mer säkerhetsrelaterad e-postinformation, till exempel leveransåtgärd, leveransplats,  *specialåtgärd,*  *riktning,* åsidosättningar och *URL-hot.* Det gör också att organisationens säkerhetsteam kan undersöka saken med högre säkerhet.

    *Leveransåtgärd* är den åtgärd som vidtas för ett e-postmeddelande på grund av befintliga principer eller identifieringar. Här är de åtgärder som kan vidtas i ett e-postmeddelande:

    - **Levererad** – e-post levererades till en användares inkorg eller mapp och användaren kan komma åt den direkt.
    - **Skräppost** (levererad till skräppost) – e-post skickades till antingen användarens skräppostmapp eller borttagna mapp och användaren har tillgång till e-postmeddelanden i mappen Skräppost eller Borttaget.
    - **Blockerad** – alla e-postmeddelanden som har satts i karantän, som har misslyckats eller släppts. (Användaren är helt otillgänglig.)
    - **Ersatt** – alla e-postmeddelanden där skadliga bifogade filer ersätts med TXT-filer som säger att den bifogade filen var skadlig

    **Leveransplats:** Filtret Leveransplats är tillgängligt för att hjälpa administratörer att förstå var misstänkt skadlig e-post upphört och vilka åtgärder som har vidtas på den. Resulterande data kan exporteras till kalkylblad. Möjliga leveransplatser är:

    - **Inkorgen eller mappen** – E-postmeddelandet ligger i Inkorgen eller i en särskild mapp, enligt dina e-postregler.
    - **Lokal eller extern** – Postlådan finns inte i molnet men är lokal.
    - **Skräppostmapp** – e-postmeddelandet finns i användarens skräppostmapp.
    - **Mappen Borttaget** – e-postmeddelandet finns i en användares mapp Borttaget.
    - **Karantän** – e-postmeddelandet i karantän, och inte i en användares postlåda.
    - **Misslyckades** – E-postmeddelandet kunde inte nå postlådan.
    - **Släppt –** e-postmeddelandet förlorades någonstans i e-postflödet.

    **Riktning: Med det** här alternativet kan teamet för säkerhetsåtgärder filtrera efter i vilken riktning ett e-postmeddelande kommer från eller går. Directionality values are *Inbound,* *Outbound,* and *Intra-org* (corresponding to mail coming into your org from outside, being sent out of your org, or being sent internally to your org, respectively). Den här informationen kan hjälpa säkerhetsåtgärder för grupper att upptäcka förfalskning och personifiering, eftersom det finns en felmatchning mellan riktningsvärdet (t.ex. *Inkommande*), och domänen för avsändaren (som *verkar* vara en intern domän) blir tydlig! The Directionality value is separate, and can differ from, the Message Trace. Resultaten kan exporteras till kalkylblad.

    **Åsidosätter:** Det här filtret tar information som visas på e-postmeddelandets informationsflik och använder den för att exponera organisationens eller användarnas principer för att tillåta och blockera *e-postmeddelanden.* Det viktigaste med filtret är att det hjälper organisationens säkerhetsteam att se hur många misstänkta e-postmeddelanden som har levererats på grund av konfiguration. Det ger dem möjlighet att ändra tillåt och spärrar efter behov. Den här resultatuppsättningen för det här filtret kan exporteras till kalkylblad.

    ****

    |Åsidosättningar i Threat Explorer|Vad de betyder|
    |---|---|
    |Tillåts enligt org.policy|E-post släpptes in i postlådan enligt organisationens policy.|
    |Blockeras av organisationspolicy|E-post blockerades från att levereras till postlådan enligt organisationens policy.|
    |Filnamnstillägg som blockeras av organisationsprincipen|Filen blockerades från leverans till postlådan enligt organisationens policy.|
    |Tillåts av användarprincip|E-post släpptes in i postlådan enligt användarprincipen.|
    |Blockeras av användarprincip|E-post blockerades från att levereras till postlådan enligt användarprincipen.|
    |

    **URL-hot:** Fältet för URL-hot har inkluderats på *informationsfliken* i ett e-postmeddelande för att ange hot som presenteras av en URL. Hot som presenteras av en URL kan vara *skadlig* kod,  *phish* eller *skräppost,* och en URL utan hot säger *Inga* i avsnittet om hot.

7. **Vyn för e-posttidslinje:** Ditt säkerhetsteam kan behöva fördjupa sig i e-postinformationen för att undersöka ytterligare. På tidslinjen för e-post kan administratörer visa åtgärder som vidtas i ett e-postmeddelande från leverans till efterleverans. Om du vill visa en tidslinje för e-post klickar du på ämnet för ett e-postmeddelande och klickar sedan på E-posttidslinje. (Den visas bland andra rubriker i panelen, till exempel Sammanfattning eller Detaljer.) De här resultaten kan exporteras till kalkylblad.

    Tidslinjen för e-post öppnas i en tabell som visar alla leverans- och efterleveranshändelser för e-postmeddelandet. Om det inte finns några ytterligare åtgärder för e-postmeddelandet bör du se en enda händelse för den ursprungliga leveransen som visar resultatet, till exempel *Blockerad,* med en bedömning *som Phish.* Administratörer kan exportera hela tidslinjen för e-post, inklusive all information på fliken och e-postmeddelandet (t.ex. ämne, avsändare, mottagare, nätverk och meddelande-ID). Tidslinjen för e-post klipper ut slumpmässigt eftersom det är mindre tid att kontrollera olika platser för att försöka förstå händelser som har hänt sedan e-postmeddelandet kom. När flera händelser inträffar samtidigt, eller i närheten, i ett e-postmeddelande visas dessa händelser i en tidslinjevy.

8. **Förhandsversion/nedladdning:** Med Threat Explorer får teamet i säkerhetsåtgärder den information de behöver för att undersöka misstänkt e-post. Ditt säkerhetsteam kan antingen:

    - [Kontrollera leveransåtgärd och plats.](#check-the-delivery-action-and-location)

    - [Visa tidslinjen för e-postmeddelandet.](#view-the-timeline-of-your-email)

### <a name="check-the-delivery-action-and-location"></a>Kontrollera leveransåtgärd och plats

I [Threat Explorer (och identifieringar i realtid)](threat-explorer.md)har du nu kolumnerna Leveransåtgärd och **Leveransplats** i stället för den tidigare **kolumnen Leveransstatus.**  Det ger en mer fullständig bild av var e-postmeddelandena hamnar. En del av syftet med den här ändringen är att göra undersökningar enklare för säkerhetsteam, men nettoresultatet är att snabbt kunna se platsen för problemmeddelanden.

Leveransstatus delas nu upp i två kolumner:

- **Leveransåtgärd** – Vilken status har det här e-postmeddelandet?

- **Leveransplats** – Var har e-postmeddelandet dirigerats som ett resultat?

Leveransåtgärd är den åtgärd som vidtas för ett e-postmeddelande på grund av befintliga principer eller identifieringar. Här är de åtgärder som kan vidtas i ett e-postmeddelande:

- **Levererad** – e-post levererades till en användares inkorg eller mapp och användaren kan komma åt den direkt.

- **Skräppost** – e-post skickades till antingen användarens skräppostmapp eller borttaget och användaren har tillgång till e-postmeddelanden i mappen Skräppost eller Borttaget.

- **Blockerad** – alla e-postmeddelanden som har satts i karantän, som har misslyckats eller släppts. (Användaren är helt otillgänglig.)

- **Ersatt** – alla e-postmeddelanden där skadliga bifogade filer ersätts med TXT-filer som säger att den bifogade filen var skadlig.

Leveransplats visar resultatet av principer och identifieringar som körs efter leverans. Det är länkat till en leveransåtgärd. Det här fältet har lagts till för att ge insyn i åtgärder som vidtas när ett problem har hittats. Här är möjliga värden för leveransplats:

- **Inkorgen eller mappen** – E-postmeddelandet ligger i Inkorgen eller i en mapp (enligt dina e-postregler).

- **Lokal eller extern** – Postlådan finns inte i molnet men är lokal.

- **Skräppostmapp** – E-postmeddelandet finns i användarens skräppostmapp.

- **Mappen Borttaget** – e-postmeddelandet finns i en användares mapp Borttaget.

- **Karantän** – e-postmeddelandet i karantän, och inte i en användares postlåda.

- **Misslyckades** – E-postmeddelandet kunde inte nå postlådan.

- **Släppt –** e-postmeddelandet försvinner någonstans i e-postflödet.

### <a name="view-the-timeline-of-your-email"></a>Visa tidslinjen för din e-post

**E-posttidslinje** är ett fält i HotUtforskaren som gör det enklare för ditt team med säkerhetsåtgärder att hitta den. När flera händelser inträffar samtidigt eller nära varandra i ett e-postmeddelande visas de i en tidslinjevy. Vissa händelser som inträffar efter leverans till e-post visas i kolumnen **Specialåtgärder.** Om du kombinerar information från tidslinjen i ett e-postmeddelande med särskilda åtgärder som har gjorts efter leveransen får administratörer insikt i principer och hothantering (till exempel vart e-postmeddelandet skickades och, i vissa fall, vad den slutliga bedömningen var).

> [!IMPORTANT]
> Gå till ett åtgärdsavsnitt [här.](remediate-malicious-email-delivered-office-365.md)

## <a name="related-topics"></a>Relaterade ämnen

[Åtgärda skadlig e-post som levereras i Office 365](remediate-malicious-email-delivered-office-365.md)

[Microsoft Defender för Office 365](office-365-ti.md)

[Skydda mot hot i Office 365](protect-against-threats.md)

[Visa rapporter för Defender för Office 365](view-reports-for-atp.md)
