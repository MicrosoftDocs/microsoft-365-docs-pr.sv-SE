---
title: Kontrollera tjänstens hälsa för Microsoft 365
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
description: Visa hälsostatus för Microsoft 365-tjänster innan du ringer supporten för att se om det finns ett aktivt tjänsteavbrott.
ms.openlocfilehash: 30b677a80e5a08d75534a91aa04d735443660f18
ms.sourcegitcommit: 3d2261af22bebbbf7efa8a0d3135225a15bd6ba8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51215486"
---
# <a name="how-to-check-microsoft-365-service-health"></a>Kontrollera tjänstens hälsa för Microsoft 365

[![Etikett som gör att du kan se att administrationscentret ändras och mer information finns på aka.ms/aboutM365preview.](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)

Du kan visa hälsotillståndet för dina Microsoft-tjänster, inklusive Office på webben, Yammer, Microsoft  Dynamics CRM och molntjänster för hantering av mobila enheter, på sidan Tjänstens hälsa i administrationscentret för [Microsoft 365.](https://go.microsoft.com/fwlink/p/?linkid=2024339) Om du har problem med en molnbaserad tjänst kan du kontrollera tjänstens hälsa för att ta reda på om det är ett känt problem där en lösning är på gång innan du ringer supporten eller ägnar tid åt felsökning.

Om du inte kan logga in i administrationscentret kan du använda [tjänststatussidan](https://status.office365.com) till att kontrollera om det finns kända problem som hindrar dig att logga in i klientorganisationen.  Registrera dig även för att följa oss på [@MSFT365status](https://twitter.com/MSFT365Status) Twitter för att se information om vissa händelser.

  
### <a name="how-to-check-service-health"></a>Kontrollera tjänstens hälsa

1. Gå till administrationscentret för Microsoft 365 på [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) och logga in med ett administratörskonto.

    > [!NOTE]
    > Personer som har tilldelats rollen som global administratör eller tjänstadministratör kan visa tjänstens hälsa. För att tillåta Exchange-, SharePoint- och Skype för företag-administratörer att visa tjänstens hälsa, måste de också tilldelas tjänstadministratörsrollen. Mer information om roller som kan visa tjänstens hälsa finns i [Om administratörsroller.](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles)
  
2. Om du inte använder det nya  administrationscentret går  du till startsidan och väljer växlingsknappen Prova det nya administrationscentret i det övre högra hörnet.

3. Om du vill visa tjänstens hälsa går du till Tjänstens hälsa i administrationscentret eller väljer kortet  >   **Tjänstens hälsa** på **instrumentpanelen Start**. Instrumentpanelskortet anger om det finns ett aktivt problem med tjänsten och länkar till sidan med detaljerad **information om tjänstens** hälsa.
  
4. På sidan **Tjänstens** hälsa visas hälsotillståndet för varje molntjänst i ett tabellformat.

   ![View of current issues in service health](../media/service-health-all-services.png)

På **fliken Alla** tjänster (standardvyn) visas alla tjänster och deras aktuella hälsotillstånd. En ikon och kolumnen **Status** anger status för varje tjänst. 

Om du vill filtrera vyn efter tjänster där det för närvarande finns incidenter väljer du **fliken** Incidenter högst upp på sidan. Om du **väljer fliken Rådgivning** visas endast de tjänster där det för närvarande finns en rådgivning publicerad. 

På **fliken** Historik visas historik över incidenter och rekommendationer som har lösts.

Om du har ett problem med en Microsoft 365-tjänst och  du inte ser den på sidan Tjänstens hälsa kan du berätta det genom att välja Rapportera ett problem **och** fylla i det korta formuläret. Vi tittar på relaterade data och rapporter från andra organisationer för att se hur omfattande problemet är och om det kommer till vår tjänst. Om den har det lägger vi till den som  en ny händelse eller rådgivning på sidan Tjänstens hälsa, där du kan spåra dess lösning. Om du inte ser den i listan inom ungefär 30 minuter kan du kontakta support för att lösa problemet.

Om du vill anpassa vyn för vilka tjänster som visas på instrumentpanelen väljer du Anpassad vy för inställningar och avmarkerar kryssrutorna för de tjänster som du vill filtrera bort från hälsoinstrumentpanelen.  >   Kontrollera att kryssrutan är markerad för varje tjänst som du vill övervaka.    

Om du vill registrera dig för e-postmeddelanden om nya incidenter som påverkar din klientorganisation och statusändringar för en aktiv incident väljer du Inställningar E-post , klickar på Skicka e-postaviseringar på tjänsten  >   **hedn** och anger sedan:

- Upp till två e-postadresser.
- Om du vill få aviseringar om incidenter eller rådgivning
- De tjänster som du vill få aviseringar om

> [!NOTE]
> Varje administratör kan ha sina inställningar inställda och ovanstående begränsning på två e-postadresser är per administratörskonto.

> [!TIP]
> Du kan också använda [Microsoft 365 Admin-appen](https://go.microsoft.com/fwlink/p/?linkid=627216) på din mobila enhet för att visa tjänstens hälsa, vilket är ett bra sätt att hålla dig aktuell med push-meddelanden. 
  
### <a name="view-details-of-posted-service-health"></a>Visa information om publicerad tjänsthälsa

Om du **väljer tjänststatus** i vyn Alla tjänster öppnas en sammanfattning av rådgivningar och incidenter.
  
[![En skärmbild som visar tjänstrådgivningen ](../media/service-health-advisory.png)](../media/service-health-advisory.png#lightbox)

Sammanfattningen av rådgivningen eller incidenten innehåller följande information:

- **Rubrik** – en sammanfattning av problemet.
- **Tjänst** – Namnet på den aktuella tjänsten.
- **ID** – En numerisk identifierare för problemet.
- **Status** – Hur det här problemet påverkar tjänsten.
- **Starttid** – tidpunkten då problemet började.
- **Senast uppdaterad** – den senaste gången som meddelandet om tjänstens hälsa uppdaterades. Vi publicerar ofta meddelanden för att meddela dig om förloppet för att använda en lösning.

Välj rubriken för problemet om du vill visa informationssidan som [](#history) visar mer information om problemet, inklusive historik över alla meddelanden som publicerats medan vi arbetar med en lösning.

![En skärmbild som visar information om problemet](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a>Översätta information om tjänstens hälsa

Eftersom förklaringar om tjänstens hälsa publiceras i realtid översätts de inte automatiskt till ditt språk, och information om en tjänsthändelse finns endast på engelska. Följ de här stegen om du vill översätta en förklaring:
  
1. Gå till [Translator](https://www.bing.com/translator/).

2. På sidan **Tjänstens hälsa** väljer du en händelse eller rådgivning. Kopiera texten om problemet under **Visa information**.

3. Klistra in texten i Translator och välj **Översätt**.

### <a name="definitions"></a>Definitioner

Oftast visas tjänsterna som felfria utan ytterligare information. Om ett problem inträffar i tjänsten identifieras problemet som rådgivning eller incident och aktuell status visas.
  
> [!TIP]
> Planerade underhållshändelser visas inte i tjänstens hälsa. Du kan spåra planerade underhållshändelser genom att hålla dig uppdaterad i **Meddelandecenter**. Filtrera på meddelanden som kategoriserats som Planera för ändring för att ta reda på när ändringen ska ske, dess påverkan och vilka förberedelser som bör vidtas. Mer information finns i Meddelandecenter i [Microsoft 365.](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093)
  
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

### <a name="history"></a>Historik

I Tjänstens hälsa kan du se den aktuella hälsostatusen och visa historik för rådgivningar och incidenter för tjänsten som har påverkat din klientorganisation under de senaste 30 dagarna. Om du vill visa tidigare hälsoläge för alla tjänster väljer **du Visa historik** på sidan med information om problemet.
  
![Show link to health history](../media/service-health-view-history.png)
  
En lista över alla meddelanden om tjänstens hälsa som publicerats inom den valda tidsramen visas enligt nedan:
  
![View service health history](../media/service-health-history.png)
  
Expandera valfri rad för att visa mer information om problemet.
  
Mer information om vår utfästelse om drifttid finns [i Transparent drift från Microsoft 365.](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

## <a name="related-topics"></a>Relaterade ämnen

[Aktivitetsrapporter i administrationscentret för Microsoft 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 
 [Inställningar för Meddelandecenter](../admin/manage/message-center.md?preserve-view=true&view=o365-worldwide#preferences)<br/>
[Så här kontrollerar du utgivningshälsan för Windows i administrationscentret](https://docs.microsoft.com/windows/deployment/update/check-release-health)
