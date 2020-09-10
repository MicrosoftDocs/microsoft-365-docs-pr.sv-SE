---
title: Definiera dina tjänst möjligheter i bokningar
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 4a1c391e-524f-48e0-bef8-185df3a9634b
description: Anvisningar för att ange information om tjänst erbjudanden, inklusive tjänstens namn, beskrivning, plats, längd och prissättning. Du kan också tagga de anställda som är kvalificerade för att tillhandahålla tjänsten.
ms.openlocfilehash: 60b77633b9845b3c269f6773c1fb8a26256fbdc5
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/09/2020
ms.locfileid: "47420244"
---
# <a name="define-your-service-offerings-in-bookings"></a>Definiera dina tjänst möjligheter i bokningar

När du definierar dina tjänst erbjudanden i Microsoft-bokningar kan du ange ett tjänst namn, en beskrivning, en plats (Välj om du vill träffas personligen eller ha ett onlinemöte), varaktighet, standard påminnelser till kunder och personal, interna anteckningar om tjänsten och priser. Du kan också tagga de anställda som är kvalificerade för att tillhandahålla tjänsten. När kunder sedan kommer till företagets webbplats för att boka en avtalad tid kan de se exakt vilka typer av avtalade tider som är tillgängliga, välja den person som ska tillhandahålla tjänsten och hur mycket deras tjänst kommer att kosta.

Du kan också lägga till anpassad information och URL-adresser i e-postbekräftelsen och påminnelser som du skickar när någon bokar en pärm till en tjänst via din boknings sida.

> [!NOTE]
> Bokningar är som standard aktiverade för kunder som har Microsoft 365 Business Standard, Microsoft 365 a3 eller Microsoft 365 A5. Bokningar är också tillgängliga för kunder som har Office 365 Enterprise E3 och Office 365 Enterprise, E5, men det är inaktiverat som standard. Kom igång genom att läsa [få till gång till Microsoft-bokningar](get-access.md). Om du vill aktivera eller inaktivera uppslagning kan du läsa [Aktivera och inaktivera en organisation](turn-bookings-on-or-off.md).

## <a name="create-the-service-details"></a>Skapa tjänst informationen

1. Gå till [sidan Hantera tjänster](https://outlook.office.com/bookings/services) och välj **Lägg till en tjänst**.

2. **Tjänstens namn**: Ange namnet på tjänsten. Det här är det namn som visas i den nedrullningsbara menyn på sidan kalender. Det här namnet visas också när någon manuellt lägger till en avtalad tid på sidan kalender och visas som en panel på sidan själv service.

3. **Beskrivning**: det här är den beskrivning som visas när en användare klickar på informations ikonen på självbetjänings sidan.

4. **Standard plats**: den här platsen är vad som visas i bekräftelse-och e-postmeddelanden för både personal och kunder, och den visas i den kalender händelse som har skapats för bokningen.

5. **Lägga till onlinemöte**: med den här inställningen kan du aktivera eller inaktivera onlinemöten för varje avtalad tid, antingen via Teams eller Skype, beroende på vilken du konfigurerar som standard klient för personal medlemmen.

    - Aktiverat

        - En länk till ett team eller ett Skype-möte, unikt för bokningen, läggs till i kalender händelsen både i personalen och i kundernas kalendrar tillsammans med information om uppringning.
        - Länken till mötet läggs till i alla bekräftelse-och e-postmeddelanden, som visas i följande exempel:

        :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="Exempel på länk till Teams-möte i bokningar":::

        > [!NOTE]
        > Team-möten kan kopplas via Teams-mobilappen, teams-programmet, i en webbläsare eller via telefon uppringningen. Vi rekommenderar starkt att du aktiverar team som standard tjänst för onlinemötet för din klient organisation för att få bästa möjliga bokning av virtuella avtalade tider.

    - Aktiv
        - Avtalade tider kommer inte att innehålla ett mötes alternativ och alla mötesrelaterade fält som visas när **Lägg till onlinemöte** är aktiverat visas inte.

6. **Standard längd**: det här är hur länge alla möten kommer att bokas. Tiden är blockerad från start tiden, som väljs under bokning. Hela den avtalade tiden kommer att blockeras i personalens kalendrar.

7. **Buffertlängd din kund inte kan göra**följande: om du aktiverar den här inställningen kan du lägga till extra tid för personalens kalender varje gång en avtalad tid bokas.

    Tiden blockeras i personalens kalender och påverkar ledig/upptagen-information. Det innebär att om en avtalad tid slutar på 3:00 PM och 10 minuters buffertstorlek har lagts till i slutet av mötet visas personalens kalender som upptagen och icke-bookable förrän 3:10pm. Det kan vara användbart om personalen behöver tid innan ett möte kan förberedas, till exempel en läkare som granskar ett patient diagram eller en finansiell rådgivare som förbereder relevant konto information. Det kan också vara användbart efter ett möte, till exempel när någon behöver tid att resa till en annan plats.

8. **Låt kunden hantera sin bokning**: den här inställningen avgör om eller notthe kunden kan ändra eller annullera sin bokning, förutsatt att den har bokats via fliken Kalender i webb programmet.

    - Aktiverat

        Knappen **Hantera bokning** visas i e-postmeddelandet med bekräftelse på kund. När den här knappen är vald av kunden visas tre alternativ:
        - **Schemalägg om** Om du väljer det här alternativet lägger användaren till en särskild tjänst sida där han eller hon kan välja en ny tid och/eller datum för samma tjänst och personal från den ursprungliga bokningen. Observera att även om den ursprungliga personal medlemmen är kopplad till den ombokade bokningen som standard kan användaren även byta personal medlemmen.
        - **Annullera bokning** Detta annullerar bokningen och tar bort den från personalens kalender.
        - **Ny bokning** Med det här alternativet får användaren till självbetjänings sidan med alla tjänster och personal som visas för att schemalägga en ny bokning.

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="Knappen hantera bokningar i en bokning":::

        Vi rekommenderar bara att du lämnar den här inställningen aktive rad om du är van vid att komma åt sidan för Self-service.

    - Aktiv

        Användaren kommer inte att kunna omboka eller annullera deras bokning när de går igenom fliken Kalender i webb programmet. När du bokar via självbetjänings sidan kommer kunder fortfarande att ha knappen **Hantera bokning** och alla dess alternativ även om den här inställningen är inaktive rad.

        Vi rekommenderar att du inaktiverar den här inställningen om du vill begränsa åtkomsten till självbetjänings sidan. Dessutom föreslår vi att lägga till text i dina bekräftelse-och e-postmeddelanden så att dina kunder kan göra ändringar i sin bokning på annat sätt, till exempel genom att ringa kontoret eller skicka e-post till supportavdelningen.

9. **Maximalt antal deltagare per händelse** Med den här inställningen kan du skapa tjänster som kräver att flera personer kan boka samma avtalade tider och samma personal (till exempel en tränings klass). Tids platsen för den avtalade tiden för den valda tjänsten, personalen och tiden kommer att vara tillgänglig för bok ända tills det maximala antalet deltagare som anges av dig har uppnåtts. Nuvarande kapacitet och deltagare för avtalad tid kan visas på fliken Kalender i webb programmet bokningar.

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Exempel på hur du ställer in maximalt antal deltagare i en bokning":::

10. **Standard pris**  Det är det pris som visas på sidan Self-service. Om **pris inte har ställts in** väljs inga priser eller referenser till kostnad eller prissättning.

11. **Anteckningar** Det här fältet visas i boknings evenemang för boka personal och på den händelse som visas på fliken Kalender i webb programmet.

12. **Anpassade fält** I det här avsnittet kan du lägga till och ta bort frågor om kunden behöver besvara sin order för att kunna boka det.

    - E-post, telefonnummer, adress och anteckningar är inte flyttbara, men du kan göra dem valfria genom **att avmarkera varje** fält.

    - Du kan lägga till flera alternativ eller textsvars frågor genom att välja **Lägg till en fråga**.

        Anpassade fält kan vara användbara när du samlar in information som krävs varje gång den avtalade tiden tas med. Exemplen inkluderar försäkrings leverantör innan ett klinik-besök, låne typ för låne konsultation, huvud analys för utbildning eller sökande-ID för kandidat intervjuer.

13. **Påminnelser och bekräftelser** Båda typerna av e-postmeddelanden skickas ut till kunder, anställda eller båda, under en viss tids period innan den avtalade tiden. Du kan skapa flera meddelanden för varje avtalad tid enligt dina önskemål.

    - Standard-e-postbekräftelsen och påminnelser innehåller grundläggande information om den avtalade tiden, till exempel kund/klient namn, personalens namn, tjänsten eller avtalade tiden, samt tiden för den avtalade tiden. För onlinemöten visas även länken till gå till. Möjligheten att hantera bokningen kan också inkluderas, om den här inställningen är aktive rad (enligt beskrivningen ovan i steg 8).

        :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="En bekräftelse via e-post från bokningar":::

    - Du kan också lägga till ytterligare text som du vill ha med, till exempel information om hur du schemalägger om eller hur kunderna ska skaffa den avtalade tiden. Här följer ett exempel på anpassad text som lagts till i det ursprungliga bekräftelse meddelandet, som visas i fältet **Ytterligare information för bekräftelse av e-post** :

        :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Ytterligare information i en boknings-e-post":::

14. **Aktivera SMS-aviseringar för din kund** Om du väljer det här alternativet skickas SMS-meddelanden till kunden, men bara om de väljer.

    - Rutan för att välja på sidan manuell bokning och self-service:

        :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="Rutan för att välja i en bokning":::

    - SMS-meddelanden ser ut som nedan (Obs! det finns för närvarande inga meddelanden i Nord Amerika):

        :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="Ett SMS från bokningar":::

15. **Publicerings alternativ** Välj om du vill att den här tjänsten ska visas som bookable på självbetjänings sidan, eller om du bara vill göra tjänsten bookable på fliken Kalender i webb programmet.

16. **Schemaläggnings policy** Den här inställningen bestämmer hur tiden för avtalade tider visas och hur lång tid som kan göras eller annulleras.

17. **E-postmeddelanden** Anger när e-postmeddelanden skickas till organisationens personal och till kunder eller klienter.

18. **Personal** Om du markerar den här kryss rutan kan kunder eller klienter välja en specifik anställd för den avtalade tiden.

    - Aktiverat

        Kunderna kan välja bland alla anställda som tilldelats den avtalade tiden när de bokar på självbetjänings sidan. Om du väljer alternativet för **någon** kan du välja en tillgänglig personal medlem med slumpmässig till den avtalade tiden.

    - Aktiv

        Kunder som bokning via Self-Service-sidan kan välja en tjänst och tid och datum. De tillgängliga personalen kommer att bokas slumpmässigt. Observera att specifika personer kan fortfarande väljas när de är på fliken Kalender i webb programmet.

19. **Tillgänglighet** Följande alternativ avgör när servicen kan bokas:

    - **Bookable när personalen är gratis** Tjänsten behåller tillgänglighet baserat på när personalen är gratis inom kontors tid, utan extra tids begränsningar.

    - **Anpassade timmar (återkommande vecka)** Tjänsten har ett extra lager med tillgänglighet som kan begränsas ytterligare (utöver begränsning i arbets tid eller med personal timmar). Använd det här alternativet om din tjänst endast kan tillhandahållas eller genomföras vid en viss tidpunkt.

    - **Ange en annan tillgänglighet för ett datum intervall** Den här inställningen påverkar tillgänglighet vid en viss tidpunkt i stället för återkommande. Detta kan till exempel användas när en dator som behövs för tjänsten tillfälligt betjänas och inte är tillgänglig, eller när en organisation stängs för en semester.

20. **Tilldela personal** Välj personal (förutsatt att du har lagt till personal medlemmar på fliken personal) som kommer att vara bookable för den specifika tjänsten. Om ingen enskild anställd väljs kommer alla anställda som är tilldelade till tjänsten.