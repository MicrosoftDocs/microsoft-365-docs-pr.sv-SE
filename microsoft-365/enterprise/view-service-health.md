---
title: Så här kontrollerar du Microsoft 365 tjänstens hälsa
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_ServiceHealthModern
- O365M_ServiceHealthModern
- O365E_ViewStatusServices
- O365E_ServiceHealthModern
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
- IWA160
ms.assetid: 932ad3ad-533c-418a-b938-6e44e8bc33b0
description: Visa hälsostatus för Microsoft 365 innan du ringer supporten för att se om det finns ett aktivt tjänsteavbrott.
ms.openlocfilehash: 95ab260b4950d261eed1288b8fdf1f59883ff15f
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300411"
---
# <a name="how-to-check-microsoft-365-service-health"></a>Så här kontrollerar du Microsoft 365 tjänstens hälsa

[![Etikett som gör att du kan se att administrationscentret ändras och mer information finns på aka.ms/aboutM365preview.](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)

Du kan se din Microsoft-tjänster, inklusive Office på webben, Yammer, Microsoft Dynamics CRM och molntjänster för hantering av mobila enheter,  på sidan Tjänstens hälsa [i Administrationscenter för Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339). Om du har problem med en molnbaserad tjänst kan du kontrollera tjänstens hälsa för att ta reda på om det är ett känt problem där en lösning är på gång innan du ringer supporten eller ägnar tid åt felsökning.

Om du inte kan logga in i administrationscentret kan du använda [tjänststatussidan](https://status.office365.com) till att kontrollera om det finns kända problem som hindrar dig att logga in i klientorganisationen.  Registrera dig även för att följa oss på [@MSFT365status](https://twitter.com/MSFT365Status) Twitter för att se information om vissa händelser.

## <a name="how-to-check-service-health"></a>Kontrollera tjänstens hälsa

1. Gå till Administrationscenter för Microsoft 365 och [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) logga in med ett administratörskonto.

    > [!NOTE]
    > Personer som har tilldelats rollen som global administratör eller tjänstsupportadministratör kan visa tjänstens hälsa. För att tillåta Exchange-, SharePoint- och Skype för företag-administratörer att visa tjänstens hälsa, måste de också tilldelas tjänstadministratörsrollen. Mer information om roller som kan visa tjänstens hälsa finns i [Om administratörsroller.](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles)

2. Om du vill visa tjänstens hälsa går du till Tjänstens hälsa i administrationscentret eller väljer kortet  >   **Tjänstens hälsa** på **instrumentpanelen Start**. Instrumentpanelskortet anger om det finns ett aktivt problem med tjänsten och länkar till sidan med detaljerad **information om tjänstens** hälsa.

3. På sidan **Tjänstens** hälsa visas hälsotillståndet för varje molntjänst i ett tabellformat.

   ![View of current issues in service health](../media/service-health-all-services.png)

På **fliken Alla** tjänster (standardvyn) visas alla tjänster, deras aktuella hälsotillstånd och alla aktiva incidenter eller rådgivningar. En ikon och status i **kolumnen Hälsa** anger status för varje tjänst.

Om det finns en aktiv incident eller rådgivning för en tjänst visas de direkt under tjänstnamnet i en kapslad tabell. Du kan dölja den kapslade tabellen om du vill dölja incidenterna eller råden i den här vyn genom att klicka på sparrikonen till vänster om tjänstnamnet.   

Om du vill filtrera vyn för att bara visa alla aktiva incidenter väljer du **fliken** Incidenter högst upp på sidan. Om du **väljer fliken Rådgivning** visas bara alla aktiva rådgivningar som publicerats.

På **fliken** Historik visas alla incidenter och råd som har lösts de senaste sju eller 30 dagarna.

Om du har problem med en Microsoft 365-tjänst och du inte ser  den på sidan Tjänstens hälsa kan du berätta det genom att välja Rapportera ett problem och fylla i det korta formuläret. Vi tittar på relaterade data och rapporter från andra organisationer för att se hur omfattande problemet är och om det kommer till vår tjänst. Om den har det lägger vi till den som  en ny händelse eller rådgivning på sidan Tjänstens hälsa, där du kan spåra dess lösning. Sidan **Rapporterade problem** visar alla problem som din innehavare har rapporterat från det här formuläret och status.

Om du vill anpassa vyn för vilka tjänster som visas på instrumentpanelen väljer du Inställningar anpassad vy och avmarkerar kryssrutorna för de tjänster som du vill filtrera bort från hälsoinstrumentpanelen.  >   Kontrollera att kryssrutan är markerad för varje tjänst som du vill övervaka.

Om du vill registrera dig för e-postmeddelanden om nya incidenter som påverkar din klientorganisation och statusändringar för en aktiv incident väljer du Inställningar E-post , klickar på Skicka e-postaviseringar på tjänsten  >   **hedn** och anger sedan:

- Upp till två e-postadresser.
- Om du vill få aviseringar om incidenter eller rådgivning
- De tjänster som du vill få aviseringar om

Du kan även prenumerera på e-postaviseringar för enskilda händelser i stället för varje händelse för en tjänst. Det gör du genom att välja det aktiva problemet du vill få e-postaviseringsuppdateringar för, välja Hantera aviseringar för det **här** problemet och sedan ange: 
- Upp till två e-postadresser.

> [!NOTE]
> Varje administratör kan ha sina inställningar inställda och ovanstående begränsning på två e-postadresser är per administratörskonto.

> [!TIP]
> Du kan också använda [Microsoft 365 Admin-appen](https://go.microsoft.com/fwlink/p/?linkid=627216) på din mobila enhet för att visa Tjänstens hälsa, vilket är ett bra sätt att hålla dig aktuell med push-meddelanden.

### <a name="view-details-of-posted-service-health"></a>Visa information om publicerad tjänsthälsa

I vyn **Alla tjänster** väljer du rubriken för problemet så visas informationssidan som visar mer information om problemet, inklusive en feed av alla meddelanden som publiceras när vi arbetar med en lösning. 

[![En skärmbild som visar tjänstrådgivningen ](../media/service-health-advisory.png)](../media/service-health-advisory.png#lightbox)

Sammanfattningen av rådgivningen eller incidenten innehåller följande information:

- **Rubrik** – en sammanfattning av problemet.
- **ID** – En numerisk identifierare för problemet.
- **Tjänst** – Namnet på den aktuella tjänsten.
- **Senast uppdaterad** – den senaste gången som meddelandet om tjänstens hälsa uppdaterades.
- **Beräknad starttid** – den uppskattade tiden då problemet började.
- **Status** – Hur det här problemet påverkar tjänsten.
- **Användareffekter** – en kort beskrivning av hur problemet påverkar slutanvändaren.
- **Alla uppdateringar** – Vi publicerar ofta meddelanden om vilka framsteg som görs för att använda en lösning.

![En skärmbild som visar information om problemet](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a>Översätta information om tjänstens hälsa

Vi använder maskinöversättning för att automatiskt visa meddelanden på det valda språket. Läs [Översättningar för inlägg i Meddelandecenter](/microsoft-365/admin/manage/language-translation-for-message-center-posts) om du vill ha mer information om hur du anger språk.

### <a name="definitions"></a>Definitioner

Oftast visas tjänsterna som felfria utan ytterligare information. Om ett problem inträffar i tjänsten identifieras problemet som rådgivning eller incident och aktuell status visas.

> [!TIP]
> Planerade underhållshändelser visas inte i tjänstens hälsa. Du kan spåra planerade underhållshändelser genom att hålla dig uppdaterad i **Meddelandecenter**. Filtrera på meddelanden som kategoriserats som Planera för ändring för att ta reda på när ändringen ska ske, dess påverkan och vilka förberedelser som bör vidtas. Mer [information finns i Meddelandecenter Microsoft 365](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) meddelandecenter.

### <a name="incidents-and-advisories"></a>Incidenter och rådgivning

| Ikon | Beskrivning |
|:-----|:-----|
|![Information icon for advisory](../media/a7f5fd21-c760-4948-9bc1-50f7c8070e28.png)|Om ikonen för rådgivning visas för en tjänst betyder det att vi är medvetna om att ett problem påverkar vissa användare, men att tjänsten fortfarande är tillgänglig. Rådgivning innebär att det ofta finns en lösning på problemet, och problemet kan vara tillfälligt eller är begränsat i omfattning och påverkan på användare.  <br/> |
|![Exclamation point icon for incident](../media/a636db57-6083-44dc-bbd5-556850804f17.png)|Om en aktiv incident visas för tjänsten är det ett kritiskt problem, vilket innebär att tjänsten eller en viktig funktion i tjänsten inte är tillgänglig. Användare kanske inte kan skicka och ta emot e-post eller inte kan logga in. Händelser har betydande påverkan på användarna. Om en händelse pågår tillhandahåller vi uppdateringar om undersökningen, åtgärder och bekräftar lösningen på hälsoinstrumentpanelen.  <br/> |

### <a name="status-definitions"></a>Statusdefinitioner

| Status | Definition |
|:-----|:-----|
|**Undersöker** | Vi är medvetna om ett potentiellt problem och samlar mer information om vad som händer och dess påverkan. |
|**Tjänsteförsämring** | Vi har bekräftat att det finns ett problem som kan påverka användningen av en tjänst eller funktion. Den här statusen kan visas om till exempel en tjänst fungerar långsammare än vanligt, det sker oregelbundna avbrott eller om en funktion inte fungerar. |
|**Tjänsteavbrott** | Denna status visas om vi anser att ett problem påverkar möjligheten för användarna att använda tjänsten. I det här fallet är problemet betydande och kan upprepas konsekvent. |
|**Återställer tjänsten** | Orsaken till problemet har hittats, vi vet vilka korrigerande åtgärder som ska göras och arbetar med att få tillbaka tjänsten i ett felfritt tillstånd. |
|**Utökad återställning** | Denna status anger att korrigerande åtgärder pågår för att återställa tjänsten för de flesta användare, men att det tar ett tag att nå alla berörda system. Du kan också få den här statusen om vi har gjort en tillfällig lösning för att minska påverkan medan vi jobbar på en permanent korrigering. |
|**Undersökning uppskjuten** | Du ser den här statusen om vår detaljerade undersökning av ett potentiellt problem gör att vi måste begära ytterligare information från kunder för att kunna utvidga undersökningen. Om du behöver vidta några åtgärder meddelar vi dig vilka data eller loggar vi behöver. |
|**Tjänsten har återställts** | Vi har bekräftat att korrigerande åtgärder har löst problemet och att tjänsten har återställts till ett felfritt läge. Om du vill ta reda på vad som var fel kan du visa information om problemet. |
|**Falskt positivt resultat** | Efter en detaljerad undersökning har vi bekräftat att tjänsten är felfri och fungerar som tänkt. Ingen påverkan på tjänsten har observerats eller orsaken till incidenten som uppstod utanför tjänsten. |
|**Efterrapport av incident har publicerats** | Vi har publicerat en efterhändelserapport för ett specifikt problem som innehåller orsaksinformation och nästa steg för att säkerställa att ett liknande problem inte upprepas. |

### <a name="message-post-types"></a>Posttyper för meddelanden

| Typ | Definition |
|:-----|:-----|
|**Snabbuppdatering** | Korta och ofta inkrementella uppdateringar för incidenter med brett påverkan som är tillgängliga för alla kunder. |
|**Ytterligare information** | De här ytterligare inläggen ger bättre teknisk information och lösningsinformation så att du bättre kan se hur incidenter hanteras. Detta är tillgängligt för klienter som uppfyller samma krav som beskrivs för [Exchange Online,](/microsoft-365/enterprise/microsoft-365-exchange-monitoring?view=o365-worldwide#requirements) |

### <a name="history"></a>Historik

I Tjänstens hälsa kan du se den aktuella hälsostatusen och visa historik för rådgivningar och incidenter för tjänsten som har påverkat din klientorganisation under de senaste 30 dagarna. Om du vill visa tidigare hälsoläge för alla tjänster väljer du **Historikvy.**

Mer information om vår utfästelse om drifttid finns [i Transparent drift från Microsoft 365.](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

## <a name="related-topics"></a>Relaterade ämnen

[Aktivitetsrapporter i administrationscentret för Microsoft 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

[Inställningar för Meddelandecenter](../admin/manage/message-center.md?preserve-view=true&view=o365-worldwide#preferences)

[Så här kontrollerar du Windows publiceringshälsa i administrationscentret](/windows/deployment/update/check-release-health)
