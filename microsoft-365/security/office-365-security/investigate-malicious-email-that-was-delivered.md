---
title: Undersöka skadlig e-post som levererats i Microsoft 365, Hitta och undersöka skadlig e-post
keywords: TIMailData-Inline, Säkerhetshändelse, incident, Microsoft Defender för Endpoint PowerShell, skadlig e-post, komprometterade användare, e-post phish, skadlig programvara för e-post, läsa e-postrubriker, öppna e-posthuvuden, specialåtgärder
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
description: Lär dig hur du använder funktioner för undersökning av hot och svar för att hitta och undersöka skadlig e-post.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e49963d1ffaeb7bce20f21f82f37fd3675b9cdd3
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083362"
---
# <a name="investigate-malicious-email-that-was-delivered-in-microsoft-365"></a>Undersök skadlig e-post som levererats i Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för:**

- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Med Microsoft Defender Office 365](defender-for-office-365.md) företag kan du undersöka aktiviteter som riskerar att riskera personer i organisationen och vidta åtgärder för att skydda organisationen. Om du till exempel ingår i organisationens säkerhetsteam kan du hitta och undersöka misstänkta e-postmeddelanden som levererades. Det kan du göra med [hjälp av Threat Explorer (eller identifiering i realtid).](threat-explorer.md)

> [!NOTE]
> Gå till åtgärdsartikeln [här](remediate-malicious-email-delivered-office-365.md).

## <a name="before-you-begin"></a>Innan du börjar

Kontrollera att följande krav uppfylls:

- Din organisation har [Microsoft Defender för Office 365](defender-for-office-365.md) och licenser [tilldelas till användare](../../admin/manage/assign-licenses-to-users.md).

- [Granskningsloggning](../../compliance/turn-audit-log-search-on-or-off.md) är aktiverad för organisationen.

- Organisationen har definierat principer för skydd mot skräppost, skadlig programvara, nätfiske och så vidare. Se [Skydda mot hot i Office 365](protect-against-threats.md).

- Du är global administratör eller har antingen säkerhetsadministratören eller rollen Sök och rensning tilldelad i Microsoft 365 Defender portalen. Mer information finns under [Behörigheter på Microsoft 365 Defender-portalen](permissions-microsoft-365-security-center.md). För vissa åtgärder måste du också ha rollen Förhandsgranska tilldelad.

### <a name="preview-role-permissions"></a>Förhandsgranska rollbehörigheter

För att utföra vissa åtgärder, till exempel visa meddelanderubriker eller  ladda ned innehåll i e-postmeddelanden, måste du ha rollen Förhandsgranska tillagd i en annan lämplig rollgrupp. I följande tabell förtydligas de roller och behörigheter som krävs.

<br>

****

|Aktivitet|Rollgrupp|Krävs en förhandsgranskningsroll?|
|---|---|---|
|Använd Threat Explorer (och realtidsidentifiering) för att analysera hot |Global administratör <p> Säkerhetsadministratör <p> Säkerhetsläsare|Nej|
|Använd Hotutforskaren (och identifieringar i realtid) för att visa rubriker för e-postmeddelanden samt förhandsgranska och ladda ned e-postmeddelanden i karantän|Global administratör <p> Säkerhetsadministratör <p> Säkerhetsläsare|Nej|
|Använda Hotutforskaren för att visa rubriker, förhandsgranska e-post (endast i sidan för e-post entitet) och ladda ned e-postmeddelanden som levereras till postlådor|Global administratör <p> Säkerhetsadministratör <p> Säkerhetsläsare <p> Förhandsgranska|Ja|
|

> [!NOTE]
> *Förhandsgranskning* är en roll, inte en rollgrupp. Förhandsversionsrollen måste läggas till i en befintlig rollgrupp i Microsoft 365 Defender portalen ( <https://security.microsoft.com> ). Gå till **Behörigheter** och redigera sedan en befintlig rollgrupp eller lägg till en ny rollgrupp med rollen **Förhandsgranskning** tilldelad.
>
> Rollen Global administratör tilldelas rollerna Administrationscenter för Microsoft 365 ( ) och roller som säkerhetsadministratör och säkerhetsläsare <https://admin.microsoft.com> tilldelas i Microsoft 365 Defender ( <https://security.microsoft.com> ). Mer information om roller och behörigheter finns i [Behörigheter i Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).

Vi förstår att förhandsgranskning och nedladdning av e-postmeddelanden är känsliga aktiviteter och därför är granskning aktiverad för dessa. När en administratör utför de här aktiviteterna i e-postmeddelanden genereras granskningsloggar för samma och visas i Microsoft 365 Defender portalen ( <https://security.microsoft.com> ). Gå till **fliken** \> **Granskningssökning** och filtrera på administratörsnamnet i **rutan** Användare. De filtrerade resultaten visar aktivitet **AdminMailAccess.** Markera en rad för att visa information i avsnittet **Mer information om** förhandsgranskad eller nedladdad e-post.

## <a name="find-suspicious-email-that-was-delivered"></a>Hitta misstänkt e-postmeddelande som har levererats

Hotutforskaren är en kraftfull rapport som kan ha flera syften, till exempel att hitta och ta bort meddelanden, identifiera IP-adressen för en skadlig e-postavsändare eller starta en incident för vidare undersökning. Följande procedur fokuserar på att använda Utforskaren för att hitta och ta bort skadlig e-post från mottagarens postlådor.

> [!NOTE]
> Standardsökningar i Utforskaren inkluderar för närvarande inte levererade objekt som har tagits bort från den molnbaserade postlådan med ett automatiskt skydd på nolltimmars timmar (ZAP). Den här begränsningen gäller för **alla \>** vyer (till exempel vyerna E-postprogram för skadlig programvara **eller \> E-post).** Om du vill inkludera objekt som tagits bort med ZAP måste du lägga till en **leveransåtgärd** som är inställd på att inkludera **Borttaget av ZAP.** Om du tar med alla alternativ visas alla leveransåtgärdsresultat, inklusive objekt som tagits bort av ZAP.

1. Öppna Microsoft 365 Defender och <https://security.microsoft.com> logga in med ditt arbets- eller skolkonto för Office 365.

2. Gå till **Threat Explorer genom** att välja **E& för samarbete** \> **i** det vänstra navigeringsfältet. Om du vill gå **direkt till Threat Explorer** använder du <https://security.microsoft.com/threatexplorer> .

   På sidan **Utforskaren** visar **kolumnen Ytterligare åtgärder** resultatet av bearbetningen av ett e-postmeddelande. Kolumnen **Ytterligare åtgärder** kan nås på samma plats som leveransåtgärd **och** **leveransplats.** Särskilda åtgärder kan uppdateras i slutet av e-posttidslinjen i Threat Explorer, vilket är en ny funktion som är avsedd att göra upplevelsen bättre för administratörer.

3. I menyn **Visa** väljer du **Skicka** all \> **e-post** med e-post i listrutan.

    ![Visa-menyn för Hotutforskaren och E-post – skadlig programvara, nättröjning, inskickade meddelanden och alla e-postalternativ, även innehåll – skadlig programvara.](../../media/tp-InvestigateMalEmail-viewmenu.png)

    Vyn *skadlig* programvara är för närvarande standard och fångar e-postmeddelanden där ett hot mot skadlig programvara identifieras. *Phish-vyn* fungerar på samma sätt för Phish.

    Vyn All *e-post* visar dock alla e-postmeddelanden som tas emot av organisationen, oavsett om hot har upptäckts eller inte. Som du kan föreställa dig är det mycket data, och därför visas en platshållare som frågar om ett filter ska användas i den här vyn. (Den här vyn är bara tillgänglig för Defender Office 365 P2-kunder.)

    *Vyn Inlämnade* uppgifter visar alla e-postmeddelanden som skickats in av administratören eller användaren och som har rapporterats till Microsoft.

4. **Sökning och filter i Hotutforskaren:** Filter visas högst upp på sidan i sökfältet för att hjälpa administratörer i sina undersökningar. Observera att flera filter kan användas samtidigt och att flera kommaavgränsade värden läggs till i ett filter för att begränsa sökningen. Kom ihåg:

    - Filter matchar exakt de flesta filtervillkoren.
    - Ämnesfilter använder en CONTAINS-fråga.
    - URL-filter fungerar med eller utan protokoll (t.ex. https).
    - Filter för URL-domäner, URL-sökvägar, URL-domäner och sökvägar kräver inte något protokoll för att filtrera.
    - Du måste klicka på ikonen Uppdatera varje gång du ändrar filtervärdena för att få relevanta resultat.

5. **Avancerade filter:** Med dessa filter kan du skapa komplexa frågor och filtrera datauppsättningen. Om du *klickar på Avancerade* filter öppnas en utfäll plats med alternativ.

   Avancerad filtrering är ett bra tillägg till sökfunktionerna. Ett booleskt NOT för **domänfiltren** **Recipient , Sender** **och Sender gör** att administratörer kan undersöka detta genom att utesluta värden. Det här alternativet är **lika med inget val.** Med det här alternativet kan administratörer utesluta oönskade postlådor från undersökningar (till exempel aviseringspostlådor och standardsvarspostlådor) och är användbart för fall där administratörer söker efter ett specifikt ämne (till exempel Attention) där mottagaren kan ställas in på Är lika med inget *av: defaultMail@contoso.com.* Det här är en exakt värdesökning.

   ![Mottagarna – "Innehåller inget av" avancerat filter.](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   Om du lägger till ett tidsfilter till startdatum och slutdatum kan säkerhetsteamet snabbt öka detalj granska nedåt. Den kortaste tillåtna varaktigheten är 30 minuter. Om du kan begränsa den misstänkta åtgärden efter tidsperiod (t.ex. för 3 timmar sedan) begränsar det här sammanhanget och gör det enkelt att hitta problemet.

   ![Alternativet filtrera efter timmar för att begränsa mängden datasäkerhetsgrupper måste bearbetas, och vars kortaste varaktighet är 30 minuter.](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. **Fält i Hotutforskaren:** I Hotutforskaren visas mycket mer säkerhetsrelaterad e-postinformation, till exempel *Leveransåtgärd,* Leveransplats,  *Specialåtgärd,* Riktning, *Åsidosättningar* och *URL-hot.* Det gör också att organisationens säkerhetsteam kan undersöka med högre säkerhet.

    *Leveransåtgärd* är den åtgärd som vidtas på ett e-postmeddelande på grund av befintliga principer eller identifieringar. Här är de möjliga åtgärder som kan vidtas i ett e-postmeddelande:

    - **Levererad** – e-post levererades till en användares inkorg eller mapp och användaren kan komma åt den direkt.
    - **Skräppost** (Levererad till skräppost)– e-postmeddelande skickades till antingen användarens skräppostmapp eller en borttaget borttaget-mapp, och användaren har åtkomst till e-postmeddelanden i mappen Skräppost eller Borttaget.
    - **Blockerad** – alla e-postmeddelanden som har satts i karantän, som misslyckades eller släppts. (Detta är helt otillgängligt för användaren.)
    - **Ersatt** – alla e-postmeddelanden där skadliga bifogade filer ersätts .txt filer som uppger att den bifogade filen var skadlig

    **Leveransplats:** Filtret Leveransplats är tillgängligt för att hjälpa administratörer att förstå var misstänkt skadlig e-post avslutades och vilka åtgärder som har vidtagits för den. Resulterande data kan exporteras till kalkylblad. Möjliga leveransplatser är:

    - **Inkorgen eller mappen** – E-postmeddelandet ligger i Inkorgen eller i en särskild mapp, enligt dina e-postregler.
    - **Lokal eller extern** – Postlådan finns inte i molnet men är lokal.
    - **Skräppostmapp** – E-postmeddelandet finns i en användares skräppostmapp.
    - **Mappen Borttaget** – e-postmeddelandet finns i en användares Borttaget-mapp.
    - **Karantän** – E-postmeddelandet i karantän, och inte i en användares postlåda.
    - **Misslyckades** – E-postmeddelandet kunde inte nå postlådan.
    - **Nedslöt** – e-postmeddelandet försvann någonstans i e-postflödet.

    **Riktning: Det här** alternativet gör att teamet för säkerhetsåtgärder kan filtrera efter "riktning" som ett e-postmeddelande kommer från eller går. Directionality values are *Inbound*, *Outbound*, and *Intra-org* (corresponding to mail coming into your org from outside, being sent out of your org, or being sent internally to your org, respectively). Den här informationen kan hjälpa säkerhetsåtgärder grupper att upptäcka förfalskning och personifiering, eftersom det finns en felmatchning mellan directionality-värdet (t.ex. *Inkommande*) och domänen för avsändaren (som *verkar* vara en intern domän) blir tydligt! Värdet för Riktning är separat och kan skilja sig från meddelandespårningen. Resultaten kan exporteras till kalkylblad.

    **Åsidosätter:** Det här filtret tar information som visas på fliken för e-postinformation och använder den för att visa var organisations- eller användarprinciper för att tillåta och blockera e-postmeddelanden har *åsidosättts.* Det viktigaste med filtret är att det hjälper organisationens säkerhetsgrupp att se hur många misstänkta e-postmeddelanden som har levererats på grund av konfigurationen. Då kan de ändra tillåt och spärrar efter behov. Den här resultatuppsättningen för det här filtret kan exporteras till kalkylblad.

    <br>

    ****

    |Åsidosättningar i Threat Explorer|Vad de betyder|
    |---|---|
    |Tillåts av org.policy|E-post tillåts till postlådan enligt organisationspolicyn.|
    |Princip för Blockerade av organisation|E-post blockerades från leverans till postlådan enligt organisationspolicyn.|
    |Filnamnstillägg som blockeras av org-policyn|Filen blockerades från leverans till postlådan enligt organisationspolicyn.|
    |Tillåts av användarprincip|E-post tillåts i postlådan enligt användarprincipen.|
    |Blockeras av användarprincip|E-post blockerades från leverans till postlådan enligt användarprincipen.|
    |

    **URL-hot:** Fältet för URL-hot har inkluderats på *informationsfliken* i ett e-postmeddelande för att ange hot som presenteras av en URL. Hot som presenteras av en URL kan vara *skadlig* kod,  *phish* eller *skräppost,* och en URL utan hot säger *Inga* i avsnittet om hot.

7. **Vyn Tidslinje för** e-post: Ditt team för säkerhetsåtgärder kan behöva fördjupa sig i e-postinformation för att undersöka ytterligare. På tidslinjen för e-post kan administratörer visa åtgärder som vidtas på ett e-postmeddelande från leverans till efterleverans. Om du vill visa en tidslinje för e-post klickar du på ämnet för ett e-postmeddelande och klickar sedan på Skicka tidslinjen med e-post. (Den visas bland andra rubriker på panelen, till exempel Sammanfattning eller Detaljer.) Dessa resultat kan exporteras till kalkylblad.

    Tidslinjen för e-post öppnas i en tabell som visar alla leverans- och efterleveranshändelser för e-postmeddelandet. Om det inte finns några ytterligare åtgärder för e-postmeddelandet bör du se en enda händelse för den ursprungliga leveransen som visar resultatet, till exempel *Blockerad*, med en bedömning *som Phish*. Administratörer kan exportera hela e-posttidslinjen, inklusive all information på fliken och e-post (t.ex. Ämne, Avsändare, Mottagare, Nätverk och Meddelande-ID). E-posttidslinjen klipper ut slumpvis eftersom det inte läggs tid på att kontrollera olika platser för att försöka förstå händelser som har hänt sedan e-postmeddelandet kom. När flera händelser inträffar samtidigt som i ett e-postmeddelande visas de i en tidslinjevy.

8. **Förhandsgranskning/nedladdning:** Med Hotutforskaren får ditt säkerhetsteam den information de behöver för att undersöka misstänkt e-post. Ditt team för säkerhetsåtgärder kan antingen:

    - [Kontrollera leveransåtgärden och platsen](#check-the-delivery-action-and-location).

    - [Visa tidslinjen för din e-post](#view-the-timeline-of-your-email).

### <a name="check-the-delivery-action-and-location"></a>Kontrollera leveransåtgärden och platsen

I [Threat Explorer (och i realtidsidentifiering)](threat-explorer.md)har  du nu kolumnerna Leveransåtgärd och Leveransplats istället för den tidigare **kolumnen Leveransstatus.**  Det ger en mer fullständig bild av var e-postmeddelandena kommer till. En del av den här ändringen är att förenkla undersökningar för säkerhetsteam, men nettoresultatet är att snabbt veta platsen för problemmeddelanden.

Leveransstatus delas nu upp i två kolumner:

- **Leveransåtgärd** – Vilken status har det här e-postmeddelandet?
- **Leveransplats** – Var dirigerades det här e-postmeddelandet till följd av det?

Leveransåtgärd är den åtgärd som vidtas på ett e-postmeddelande på grund av befintliga principer eller identifieringar. Här är de möjliga åtgärder som kan vidtas i ett e-postmeddelande:

- **Levererad** – e-post levererades till en användares inkorg eller mapp och användaren kan komma åt den direkt.
- **Skräppost** – e-post skickades till antingen användarens skräppostmapp eller till en borttaget borttaget-mapp, och användaren har åtkomst till e-postmeddelanden i mappen Skräppost eller Borttaget.
- **Blockerad** – alla e-postmeddelanden som har satts i karantän, som misslyckades eller släppts. (Detta är helt otillgängligt för användaren.)
- **Ersatt** – alla e-postmeddelanden där skadliga bifogade filer ersätts med .txt filer som uppger att den bifogade filen var skadlig.

Leveransplats visar resultatet av principer och identifieringar som körs efter leveransen. Det är länkat till en leveransåtgärd. Det här fältet har lagts till för att ge insyn i åtgärder som vidtas när ett problem har hittats. Här är de möjliga värdena för leveransplatsen:

- **Inkorgen eller mappen** – E-postmeddelandet ligger i inkorgen eller i en mapp (enligt e-postreglerna).
- **Lokal eller extern** – Postlådan finns inte i molnet men är lokal.
- **Skräppostmapp** – E-postmeddelandet finns i användarens skräppostmapp.
- **Mappen Borttaget** – e-postmeddelandet finns i en användares Borttaget-mapp.
- **Karantän** – E-postmeddelandet i karantän, och inte i en användares postlåda.
- **Misslyckades** – E-postmeddelandet kunde inte nå postlådan.
- **Nedslöt** – e-postmeddelandet försvinner någonstans i e-postflödet.

### <a name="view-the-timeline-of-your-email"></a>Visa tidslinjen för din e-post

**Tidslinjen för** e-post är ett fält i Hotutforskaren som gör det lättare för teamet med säkerhetsåtgärder att hitta den. När flera händelser inträffar samtidigt eller nära varandra i ett e-postmeddelande visas de händelserna i en tidslinjevy. Vissa händelser som inträffar efter leverans till e-post fångas i **kolumnen Specialåtgärder.** Om du kombinerar information från tidslinjen i ett e-postmeddelande med eventuella särskilda åtgärder som har gjorts efter leveransen får administratörer insyn i principer och hothantering (till exempel vart e-postmeddelandet skickades och, i vissa fall, vad den slutliga bedömningen var).

> [!IMPORTANT]
> Gå till ett åtgärdsavsnitt [här](remediate-malicious-email-delivered-office-365.md).

## <a name="related-topics"></a>Relaterade ämnen

[Åtgärda skadlig e-post som levereras i Office 365](remediate-malicious-email-delivered-office-365.md)

[Microsoft Defender för Office 365](office-365-ti.md)

[Skydda mot hot i Office 365](protect-against-threats.md)

[Visa rapporter för Defender för Office 365](view-reports-for-mdo.md)
