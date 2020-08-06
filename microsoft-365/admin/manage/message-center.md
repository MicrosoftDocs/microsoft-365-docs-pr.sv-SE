---
title: Meddelandecenter
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 38fb3333-bfcc-4340-a37b-deda509c2093
description: Få en översikt över Microsoft 365 meddelande Center och dess roll i ändrings hantering.
ms.openlocfilehash: cec60a7ae5df1af01625f8feef84ff258d798659
ms.sourcegitcommit: 48f3c002678906189bfba079bbf055d67d08a60f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2020
ms.locfileid: "46564031"
---
# <a name="message-center"></a>Meddelandecenter


För att hålla reda på kommande ändringar, inklusive nya och ändrade funktioner, planerade underhåll och andra viktiga meddelanden, går du till <a href="https://go.microsoft.com/fwlink/p/?linkid=2070717" target="_blank">meddelande Center</a>. 
  
Så här öppnar du meddelande Center:

::: moniker range="o365-worldwide"

- I administrations centret går du till Center för **hälso** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2070717" target="_blank">meddelanden</a>.

::: moniker-end

::: moniker range="o365-germany"

- I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrations centret</a>går du till Center för **hälso** > **meddelanden**.

::: moniker-end

::: moniker range="o365-21vianet"
 
- I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrations centret</a>går du till Center för **hälso** > **meddelanden**.

::: moniker-end

Du kan också använda [Microsoft 365 admin-appen](https://go.microsoft.com/fwlink/p/?linkid=627216) på din mobila enhet för att Visa meddelande Center, som är ett bra sätt att fortsätta med push-meddelanden. 
  
  
### <a name="frequently-asked-questions"></a>Vanliga frågor och svar

|**Fråga**|**Svar**|
|:-----|:-----|
|Vem kan visa inlägg i Meddelandecenter?  <br/> |De flesta användare som har tilldelats en administratörs roll i Microsoft 365 kan visa meddelande Center inlägg. [Här är en lista](#admin-roles-that-dont-have-access-to-the-message-center) över administrativa roller som inte har till gång till meddelande Center. Du kan också tilldela rollen som meddelande Center läsare för användare som ska kunna läsa och dela meddelande Center inlägg utan andra administratörs behörigheter.<br/>|
|Är det enda sättet som Microsoft kommunicerar ändringar om Microsoft 365?  <br/> |Nej, men meddelande Center är det vanligaste sättet för vi att kommunicera enskilda ändringar i Microsoft 365. Se [Håll koll på Microsoft 365-ändringar](stay-on-top-of-updates.md) för information om ytterligare resurser.  <br/> |
|Hur kan jag se inlägg på mitt språk?  <br/> |Meddelande Center inlägg skrivs på endast på engelska, men du kan styra om inlägg ska visas på engelska eller automatiskt avbildas till önskat språk. Du kan också välja att översätta inlägg till alla språk som vi har stöd för. Mer information finns i [översättningar för meddelanden i meddelande Center](language-translation-for-message-center-posts.md) .  <br/> |
|Kan jag förhandsgranska ändringar eller funktioner innan de distribueras i organisationen?  <br/> |Vissa ändringar och nya funktioner kan förhandsgranskas av vanligt i mål utgivnings programmet. Om du vill välja i administrations Center går du till **Inställningar**organisation för hantering av  >  **profil**  >  **Inställningar**. (I administrations centret kan du behöva välja **Visa alla** längst ned i det vänstra navigerings fönstret för att se **Inställningar**.) Du kan välja riktad version för hela organisationen eller bara för utvalda användare. Se [alternativ för standard eller riktade till Microsoft 365](release-options-in-office-365.md) för mer information om programmet.  <br/> |
|Kan jag ta reda på det exakta datumet då en ändring blir tillgänglig för min organisation?  <br/> |Tyvärr kan vi inte berätta för dig vilket datum en ändring ska göras i din organisation. I vårt inlägg i meddelande Center kommer vi att ge så mycket information som möjligt för utgivnings perioden, baserat på vår konfidensnivå. Vi arbetar med förbättringar för bättre åtkomst till den detalj nivån.  <br/> |
|Är de här meddelandena specifika för min organisation?  <br/> |Vi gör vårt bästa för att se till att du bara ser meddelanden i meddelande Center som påverkar din organisation. Microsoft 365-översikten innehåller alla funktioner som vi för närvarande arbetar med, men inte alla dessa funktioner gäller för varje organisation. <br/> |
|Kan jag få e-post i meddelande Center i stället?  <br/> |Ja! Du kan välja att få en veckovis sammanfattad e-post till dig och upp till två andra e-postadresser. E-postmeddelandet per vecka är aktiverat som standard. Om du inte får dina vecko sammandrag markerar du mappen spam. I avsnittet [Inställningar](#preferences) i den här artikeln finns mer information om hur du ställer in en vecko sammandrag.  <br/> |
|Hur slutar jag att ta emot meddelande Center sammandrag?  <br/> |Gå till meddelande Center i administrations centret och välj **Redigera inställningar**. Inaktivera alternativet för att **skicka en e-postsammandrag av mina meddelanden**. Om du inte längre vill få e-post om viktiga uppdateringar kan du stänga av **skicka mig e-post för viktiga uppdateringar**.  <br/> |
|Hur kan jag se till att data integritets aviseringar tas emot av de rätta kontakterna i min organisation? <br/> |Som global administratör får du data integritets meddelanden för din organisation. Dessutom kan du tilldela rollen som sekretess läsare för meddelande Center till personer som ska kunna se data integritets meddelanden. Andra administratörs roller med åtkomst till meddelande Center kan inte visa data integritets meddelanden.   <br/><br/>Mer information finns i [Inställningar](#preferences) i den här artikeln.<br/> |

### <a name="messages"></a>Meddelanden

I meddelande centret presenteras alla aktiva meddelanden i ett tabell format. Som standard visas det senaste meddelandet högst upp i listan. Du kan välja en flik för att visa **alla aktiva meddelanden**, meddelanden med **hög prioritet** , **olästa meddelanden**och **meddelanden som stängts**. Och du kan använda den nedrullningsbara menyn **filtrera** för att visa alla meddelanden i en viss meddelande kategori.

Här är en snabb översikt över informationen som du ser i varje kolumn. Välj någon av kolumn rubrikerna för att ändra sorterings ordningen.
  
|**Kolumn**|**Beskrivning**|
|:-----|:-----|
|Bockmarkering  <br/> |Om du markerar kryss rutan kolumn rubrik raden markeras alla meddelanden som för tillfället visas. Om du markerar kryss rutan bredvid ett eller flera meddelanden kan du ta en titt på dessa meddelanden.  <br/> |
|Program ikon <br/> |Ikoner indikerar det program som meddelandet gäller.<br/> |
|Meddelanderubrik  <br/> |Meddelande rubriker är kortfattade beskrivningar av kommande ändringar. Om den fullständiga rubriken inte visas placerar du markören över den och hela titeln visas i en popup-ruta.  <br/> |
|Fler alternativ <br/> |Med fler alternativ kan du stänga ett meddelande, markera det som läst eller oläst, eller dela det med en annan administratör. Om du vill återställa ett avstängt meddelande väljer du fliken **avstängda meddelanden** , markerar kryss rutan bredvid meddelandet och väljer **Återställ**. <br/> |
|Större uppdatering <br/> |Ett utrops tecken i den här kolumnen indikerar en större uppdatering. <br/> |
|Åtgärd senast  <br/> |Vi anger datum här endast om vi gör en ändring som kräver att du vidtar en åtgärd före ett visst datum. Eftersom vi sällan använder kolumnen **åtgärd efter** , bör du betala extra uppmärksam på den om du ser något här.  <br/> |
|Kategori  <br/> | Meddelanden identifieras av någon av följande kategorier: <br/><br/> **Förhindra eller åtgärda problem**: informerar dig om kända problem som påverkar din organisation och kan kräva att du vidtar åtgärder för att undvika avbrott i tjänsten. Meddelanden i Förhindra eller åtgärda problem skiljer från meddelanden om tjänstens tillstånd eftersom de förra uppmanar dig att ha framförhållning för att undvika problem. <br/> <br/> **Abonnemang för ändring**: du får information om ändringar i Microsoft 365 som kan kräva att du ska undvika avbrott i tjänsten. Vi meddelar till exempel att du har ändringar i system kraven eller vilka funktioner som tas bort. Vi försöker ge minst 30 dagars varsel om eventuella ändringar som kräver en administratör för att kunna fortsätta använda tjänsten. <br/> <br/> **Håll dig informerad**: visar om nya eller uppdaterade funktioner som vi aktiverar i din organisation. Funktionerna annonseras vanligt vis först i [Microsoft 365-översikten](https://go.microsoft.com/fwlink/?linkid=2070821). <br/><br/>Kan även informera dig om planerat underhåll i enlighet med vårt service nivå avtal. Planerat underhåll kan leda till att du eller användarna inte kan komma åt Microsoft 365, en specifik funktion eller en tjänst som e-post eller OneDrive för företag.  <br/> |
|Senast uppdaterad  <br/> |Datum då meddelandet publicerades eller uppdaterades senast.  <br/> |
|Meddelande-ID  <br/> |Microsoft håller reda på inläggen i Meddelandecenter med hjälp av meddelande-ID:n. Du kan referera till det här ID: t om du vill ge feedback eller om du ringer till ett visst meddelande.  <br/> |

Mer information om vad du kan göra med meddelanden finns i [Hantera meddelanden i Meddelandecenter](manage-messages.md).
  
### <a name="major-updates"></a>Viktiga uppdateringar

Du kan granska viktiga uppdateringar genom att välja fliken **hög prioritet** högst upp i meddelande Center.

Huvud uppdateringar skickas till minst 30 dagar i förväg när en åtgärd krävs och kan innehålla:
  
- Ändringar av daglig produktivitet, till exempel Inkorgen, möten, ombud, delning och åtkomst

- Ändringar av teman, webb delar och andra komponenter som kan påverka anpassade funktioner

- Ökar eller minskar till den synliga kapaciteten som lagring, antalet regler, objekt eller varaktigheter

- Ändringar av produkt märkning som kan:

  - Orsaka förvirring för slutanvändare,

  - Leder till ändringar i hjälp Skriv bords processer och referensmaterial, eller

  - Ändra en URL

- En ny tjänst eller ett nytt program

- Ändringar som kräver en administratörs åtgärd (exklusivt förhindrande eller åtgärdade problem)

- Ändringar där data lagras
  
### <a name="preferences"></a>Önskemål

Om administrationen distribueras i hela organisationen kanske du inte vill ha några inlägg om alla Microsoft 365-tjänster. Varje administratör kan:

- Ange inställningar som styr vilka meddelanden som visas i meddelande Center.
- Filtrera meddelanden
- Ange e-postinställningar för att få en veckovis sammandrag av alla meddelanden, e-postmeddelanden för endast viktiga uppdateringar och e-postmeddelanden för data integritets meddelanden.  

::: moniker range="o365-worldwide"

1. Välj **Redigera inställningar** högst upp i meddelande Center.

2. Kontrol lera att kryss rutan är markerad för varje tjänst som du vill övervaka. Avmarkera kryss rutorna för de tjänster som du vill filtrera bort från din meddelande Center.

3. Digest-meddelanden är aktiverade som standard och skickas till din primära e-postadress. Om du inte vill ta emot vecko sammandrag avmarkerar du kryss rutan **skicka en veckovis e-postsammandrag av mina meddelanden** . <br/><br/>E-postavisering för viktiga uppdateringar är en separat kontroll. Om du vill få e-postaviseringar om viktiga uppdateringar kontrollerar du att **skicka mig e-post för huvud uppdateringar** är markerat. Avmarkera kryss rutan om du vill sluta få e-post om viktiga uppdateringar. <br><br/>Markera kryss rutan bredvid **skicka mig e-post för data integritets meddelanden** för att få separata e-postaviseringar om data integritets meddelanden (data integritets meddelanden ingår inte i vecko sammandrag). <br><br/>Du kan markera eller avmarkera din primära e-postadress, men det går inte att ändra den. Om du vill ange andra e-postadresser som e-postmeddelandet för data integritets meddelanden skickas till markerar du kryss rutan **andra e-postadresser** och anger de andra e-postadresser dit du vill att e-postadressen ska skickas. Ange e-postadressen för en Microsoft 365-grupp eller en distributions lista om fler än två personer skulle få data integritets-e-post.

4. Välj **Spara** om du vill behålla dina ändringar.
  
::: moniker-end 

::: moniker range="o365-germany"

1. Välj **Redigera inställningar för meddelande Center** överst i meddelande Center.

2. Se till att knappen är inställd på **På** för varje tjänst du vill övervaka. Använd växlings knappen för att ändra inställningen till **av** för de tjänster som du vill filtrera bort från din meddelande Center.

3. Digest-meddelanden är aktiverade som standard och skickas till din primära e-postadress. Om du inte vill ta emot vecko sammandrag ändrar du inställningen **skicka en veckovis sammandrag av mina meddelanden** till **av**. <br/><br/>E-postavisering för viktiga uppdateringar är en separat kontroll. Om du vill få e-postaviseringar om viktiga uppdateringar kontrollerar du att **skicka mig e-post för huvud uppdateringar** är **aktiverat**. Ändra inställningen till **av** för att sluta få e-post om viktiga uppdateringar. <br/><br/>För att få e-postaviseringar om data integritets meddelanden kontrollerar du att **skicka mig e-post för data integritets meddelanden** är **aktiverat**. Om du vill sluta få dessa meddelanden ändrar du inställningen till **av**. (Data integritets meddelanden är inte inkluderade i vecko sammandrag.)<br/><br/>Du kan markera eller avmarkera din primära e-postadress, men det går inte att ändra den. **Om**du vill ange andra e-postadresser som Sammanfattning av e-postmeddelandet skickas till kontrollerar du att **skicka en veckovis sammandrag av mina meddelanden** . Ange e-postadressen för en Microsoft 365-grupp eller en distributions lista om fler än två personer ska få den sammanfattande e-posten.

4. Välj **Spara** om du vill behålla dina ändringar.<br/>

::: moniker-end

::: moniker range="o365-21vianet"

1. Välj **Redigera inställningar för meddelande Center** överst i meddelande Center.

2. Se till att knappen är inställd på **På** för varje tjänst du vill övervaka. Använd växlings knappen för att ändra inställningen till **av** för de tjänster som du vill filtrera bort från din meddelande Center.

3. Digest-meddelanden är aktiverade som standard och skickas till din primära e-postadress. Om du inte vill ta emot vecko sammandrag ändrar du inställningen **skicka en veckovis sammandrag av mina meddelanden** till **av**. <br/><br/>E-postavisering för viktiga uppdateringar är en separat kontroll. Om du vill få e-postaviseringar om viktiga uppdateringar kontrollerar du att **skicka mig e-post för huvud uppdateringar** är **aktiverat**. Ändra inställningen till **av** för att sluta få e-post om viktiga uppdateringar. <br/><br/>För att få e-postaviseringar om data integritets meddelanden kontrollerar du att **skicka mig e-post för data integritets meddelanden** är **aktiverat**. Om du vill sluta få dessa meddelanden ändrar du inställningen till **av**. (Data integritets meddelanden är inte inkluderade i vecko sammandrag.)<br/><br/>Du kan markera eller avmarkera din primära e-postadress, men det går inte att ändra den. **Om**du vill ange andra e-postadresser som Sammanfattning av e-postmeddelandet skickas till kontrollerar du att **skicka en veckovis sammandrag av mina meddelanden** . Ange e-postadressen för en Microsoft 365-grupp eller en distributions lista om fler än två personer ska få den sammanfattande e-posten.

4. Välj **Spara** om du vill behålla dina ändringar.<br/>

::: moniker-end

#### <a name="display-messages-in-your-preferred-language"></a>Visa meddelanden på önskat språk
  
Vi använder maskin översättning för att automatiskt visa meddelanden på ditt språk. Om du vill ha mer information om hur du ställer in språk kan du läsa [språk översättning för meddelanden i meddelande Center](language-translation-for-message-center-posts.md) .
  
> [!NOTE]
> Vecko sammandrag och eventuella inlägg som är e-post skickas på engelska. Mottagarna kan använda [Translator för Outlook](https://support.microsoft.com/office/3d7e12ed-99d6-406e-a453-b9db0d9653fa) för att läsa meddelandet på deras prioriterade språk. 
  
### <a name="admin-roles-that-dont-have-access-to-the-message-center"></a>Administratörs roller som inte har åtkomst till meddelande Center

- Efterlevnadsadministratör
- Administratör för villkorsstyrd åtkomst
- Åtkomst granskare för kund lås
- Enhets administratörer
- Katalog läsare
- Katalog-synkronisering
- Katalogredigerare
- Intune tjänst administratör
- Administratör för privilegierade roller
- Rapportläsare

## <a name="unsubscribe-from-message-center-emails"></a>Avabonnera från e-post i meddelande Center

1. Digest-meddelanden är aktiverade som standard och skickas till din primära e-postadress. Om du inte vill ta emot vecko sammandrag ändrar du inställningen **skicka en veckovis sammandrag av mina meddelanden** till **av**. <br/><br/>E-postavisering för viktiga uppdateringar är en separat kontroll. Om du inte vill få e-postaviseringar om viktiga uppdateringar kontrollerar du att **skicka e-post för huvud uppdateringar** är **inaktiverat**.  <br/><br/>För att sluta få meddelanden om data integritets meddelanden bör du kontrol lera att **skicka mig-e-postmeddelanden för data integritets meddelanden** är **inaktiverade**.  (Data integritets meddelanden är inte inkluderade i vecko sammandrag.)<br/><br/>

2. Välj **Spara** om du vill behålla dina ändringar.<br/>