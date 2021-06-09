---
title: Definiera dina serviceerbjudanden i Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 4a1c391e-524f-48e0-bef8-185df3a9634b
description: Instruktioner för hur du anger tjänsterbjudanden, inklusive tjänstnamn, beskrivning, plats, varaktighet och priser. Du kan även tagga de medarbetare som är kvalificerade för att tillhandahålla tjänsten.
ms.openlocfilehash: 095188546c01149a793a478a3cbd5ac9fbeb5524
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962543"
---
# <a name="define-your-service-offerings-in-bookings"></a>Definiera dina serviceerbjudanden i Bookings

När du definierar dina tjänsteerbjudanden i Microsoft Bookings anger du ett tjänstnamn, en beskrivning, plats (välj om du vill träffas personligen eller ha ett onlinemöte), varaktighet, standardpåminnelser till kunder och personal, interna anteckningar om tjänsten och priser. Du kan även tagga de medarbetare som är kvalificerade för att tillhandahålla tjänsten. När kunder kommer till företagets webbplats för att boka en avtalad tid kan de se exakt vilka typer av avtalade tider som är tillgängliga, välja vilken person som ska tillhandahålla tjänsten och hur mycket deras tjänst kommer att kosta.

Du kan också lägga till anpassad information och WEBBADRESSer i e-postbekräftelsen och påminnelser som du skickar när någon bokar en tjänst via din bokningssida.

## <a name="create-the-service-details"></a>Skapa tjänstinformationen

1. Gå till sidan [Hantera tjänster och](https://outlook.office.com/bookings/services) välj Lägg till en **tjänst.**

2. **Tjänstnamn**: ange namnet på tjänsten. Det här är det namn som visas i listrutan på sidan Kalender. Det här namnet visas också när någon lägger till en avtalad tid manuellt på sidan Kalender, och det visas som en panel på självbetjäningssidan.

3. **Beskrivning**: Den beskrivning du anger är vad som visas när en användare klickar på informationsikonen på självbetjäningssidan.

4. **Standardplats:** Den här platsen visas vid bekräftelse- och påminnelsemeddelanden till både personal och kunder, och den visas i kalenderhändelsen som skapats för bokning.

5. **Lägg till onlinemöte:** Med den här inställningen aktiveras eller inaktiveras onlinemöten för varje avtalad tid, antingen via Teams eller Skype, beroende på vilken du konfigurerar som standardklient för den anställde.

    - Aktiverad:

        - En länk till ett Teams- eller Skype-möte, som är unikt för bokningsmötet, läggs till i kalenderhändelsen i både personalens och kundens kalendrar, tillsammans med uppringningsinformation.
        - Länken för att ansluta till mötet läggs till i alla bekräftelse- och påminnelsemeddelanden som visas i följande exempel:

        :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="Exempel på länk för att ansluta Teams mötet i Bookings":::

        > [!NOTE]
        > Teams möten kan du delta via Teams-mobilappen, Teams-skrivbordsappen, i en webbläsare eller via telefonens uppringning. Vi rekommenderar att du Teams att använda som standardtjänst för onlinemöte för din klientorganisation, för bästa upplevelse av virtuella bokningsbokningar.

    - Inaktiverad:
        - Avtalade tider innehåller inte något mötesalternativ och alla mötesrelaterade fält som visas när Lägg till **onlinemöte** har aktiverats visas inte.

6. **Standardvaraktighet:** Det här är hur länge alla möten bokas för. Tiden blockeras från början av starttiden, som väljs vid bokning. Den fullständiga tiden blockeras i personalens kalendrar.

7. **Tidsbuffert** som kunden inte kan boka : Om du aktiverar den här inställningen kan du lägga till extra tid i personalens kalender varje gång en avtalad tid bokas.

    Tiden blockeras i personalens kalender och påverkar ledig/upptagen-information. Det innebär att om en avtalad tid slutar kl. 15:00 och 10 minuters tidsbuffert har lagts till i slutet av mötet visas personalens kalender som upptagen och icke-bokbar fram till 15:10. Det kan vara användbart om din personal behöver tid innan ett möte för att förbereda sig, till exempel en läkarjournal eller en ekonomisk rådgivare som förbereder relevant kontoinformation. Det kan också vara praktiskt efter ett möte, till exempel när någon behöver tid för att resa till en annan plats.

8. **Låt kunden hantera sin bokning**: Den här inställningen anger om kunden kan ändra eller avbryta sin bokning, förutsatt att den har bokats via fliken Kalender i webbappen Bookings.

    - Aktiverad:

        Knappen **Hantera bokning** visas i e-postmeddelandet med kundbekräftelsen. När kunden väljer den här knappen visas tre alternativ:
        - **Schemata om** Om du väljer det här alternativet kommer användaren till en tjänstspecifik Self-Service-sida, där han eller hon kan välja en ny tid och/eller ett nytt datum för samma tjänst och samma anställd från den ursprungliga bokningen. Observera att även om den ursprungliga anställde är kopplad till den omplanerade bokningen som standard har användaren möjlighet att ändra den anställde också.
        - **Avbryt bokning** Då ställs bokningsbokningen in och den tas bort från personalens kalender.
        - **Ny bokning** Med det här alternativet kommer användaren Self-Service sidan med alla tjänster och personal som visas för att schemalägga en ny bokning.

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="Knappen Hantera bokningar i Bookings":::

        Vi rekommenderar att du lämnar den här inställningen aktiverad om du är bekväm med att kunder har åtkomst Self-Service sidan.

    - Inaktiverad:

        Användaren kan inte omboka eller avbryta sin bokning när de bokar via fliken Kalender i webbappen Bookings. När du gör en bokning Self-Service sidan har kunderna  dock fortfarande knappen Hantera bokning och alla alternativ, även om den här inställningen är inaktiverad.

        Vi rekommenderar att du inaktiverar den här inställningen om du vill begränsa åtkomsten till Self-Service sidan. Vi föreslår dessutom att du lägger till text i din bekräftelse och påminnelse via e-post som talar om för dina kunder hur de gör ändringar i bokning på andra sätt, till exempel genom att ringa till kontoret eller skicka e-post till supporten.

9. **Maximalt antal deltagare per händelse** Med den här inställningen kan du skapa tjänster som kräver att flera personer kan boka samma avtalade tid och samma personal (till exempel en träningsklass). Tidsluckan för den valda tjänsten, personalen och tiden är tillgänglig för bok tills det maximala antalet deltagare, som anges av dig, har nåtts. Aktuell möteskapacitet och -deltagare kan visas på fliken Kalender i webbappen Bookings.

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Exempel på hur du anger maximalt antal deltagare i Bookings":::

10. **Standardpris**  Det här är det pris som visas på Self-Service sidan. Om **Pris inte angetts** visas inget pris eller någon referens till kostnad eller priser.

11. **Anteckningar** Det här fältet visas i bokningshändelsen för bokad personal samt i händelsen som visas på fliken Kalender i webbappen Bookings.

12. **Anpassade fält** Det här avsnittet tillåter att frågor läggs till eller tas bort om kunden behöver svara på frågor för att kunna boka.

    - Kundens e-postadress, telefonnummer, adress och anteckningar är icke-flyttbara fält, men du kan göra dem valfria genom att avmarkera **Krävs** bredvid varje fält.

    - Du kan lägga till flervals- eller textsvarsfråga genom att välja **Lägg till en fråga**.

        Anpassade fält kan vara användbara när du samlar in information som behövs varje gång den avtalade tiden bokas. Exempel är försäkringsbolag innan ett besök, lånetyp för lånssamråd, större studieråd för akademisk rådgivning eller sökande-ID för kandidatintervjuer.

13. **Påminnelser och bekräftelser** Båda e-postmeddelandena skickas till kunder, anställda eller både och, vid en angiven tidsperiod före den avtalade tiden. Du kan skapa flera meddelanden för varje avtalad tid, enligt vad du föredrar.

    - Standardbekräftelsen och påminnelsen innehåller grundläggande information om den avtalade tiden, till exempel kund-/klientnamn, anställds namn, tjänsten eller den avtalade tiden bokad och tiden för den avtalade tiden. För onlinemöten inkluderas även en länk att ansluta till. Du kan också hantera bokningsinställningen om den här inställningen är aktiverad (enligt beskrivningen ovan i steg 8).

        :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="Ett bekräftelsemeddelande från Bookings":::

    - Alternativt kan du ta med eventuell ytterligare text som du vill ha här, till exempel information om ny nyplanering eller vad kunder ska ta med för den avtalade tiden. Följande är ett exempel på anpassad text som lagts till i det ursprungliga bekräftelsemeddelandet, som visas i **fältet Ytterligare information för e-postbekräftelse:**

        :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Ytterligare information i ett bookings-e-postmeddelande":::

14. **Aktivera SMS-aviseringar för kunden** Om du väljer SMS meddelanden skickas till kunden, men endast om denna anmäler sig.

    - Rutan för avanmälning på manuell bokning Self-Service sidan:

        :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="Rutan för avanmälning i Bookings":::

    - Sms-aviseringar ser ut som följande (observera att SMS är för närvarande endast tillgängliga i Nordamerika):

        :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="Ett sms från Bookings":::

15. **Publiceringsalternativ** Välj om du vill att den här tjänsten ska visas som bokbar på Self-Service-sidan eller om du vill att tjänsten endast ska kunna bokas på fliken Kalender i webbappen Bookings.

16. **Schemaläggningsprincip** Den här inställningen bestämmer hur tider för avtalade tider visas och tidsperiod då bokningar kan göras eller avbrytas.

17. **E-postaviseringar** Anger när e-postmeddelanden skickas till organisationens personal och till kunder eller klienter.

18. **Personal** Om du markerar den här kryssrutan kan kunder eller klienter välja en viss anställd för sin avtalade tid.

    - Aktiverad:

        Kunder kan välja från all personal som tilldelats den avtalade tiden vid bokning Self-Service sidan. Om du väljer alternativet Alla **så** väljs en tillgänglig anställd slumpmässigt för att tilldela till den avtalade tiden.

    - Inaktiverad:

        Kunder som bokar via Self-Service kan välja en tjänst och en tid och ett datum. Den tillgängliga personalen bokas slumpmässigt. Observera att viss personal fortfarande kan väljas vid bokning via fliken Kalender i webbappen Bookings.

19. **Tillgänglighet** Följande alternativ avgör när tjänsten kan bokas:

    - **Kan bokas när personalen är gratis** Tjänsten behåller tillgängligheten baserat på när personalen är ledig inom arbetstid, utan extra tidsbegränsningar.

    - **Anpassade timmar (återkommande varje vecka)** Tjänsten har ett lager med tillgänglighet som kan begränsas ytterligare (förutom att begränsa efter arbetstid eller med personaltimmar). Använd det här alternativet när tjänsten endast kan tillhandahållas eller utföras vid en viss tidpunkt.

    - **Ange annan tillgänglighet för ett datumintervall** Den här inställningen påverkar tillgänglighet vid en viss tidpunkt i stället för en återkommande bas. Den kan till exempel användas när en dator som behövs för tjänsten tillfälligt blir servicen och otillgänglig, eller när en organisation är stängd för en helgdag.

20. **Tilldela personal** Välj den personal (förutsatt att du har lagt till anställda på fliken Personal) som kan bokas för den specifika tjänsten. Om du väljer ingen enskild personal tilldelas all personal till tjänsten.