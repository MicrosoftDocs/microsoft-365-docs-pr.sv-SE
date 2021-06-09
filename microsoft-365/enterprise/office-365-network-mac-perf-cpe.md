---
title: Microsoft 365 informerad nätverksdirigering
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/10/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 informerad nätverksdirigering
ms.openlocfilehash: 5275f8ea55afaf621555b440e7fae4a6d11cad91
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717586"
---
# <a name="microsoft-365-informed-network-routing-preview"></a>Microsoft 365 informerad nätverksdirigering (förhandsversion)

Informerad nätverksroutning är en funktion som integrerar olika Microsoft 365-program med SD-WAN-lösningar (tredjepartsprogram) för att optimera och förbättra nätverksanslutningen till Microsofts tjänsteslutpunkter. Optimerad SD-WAN-anslutning kan resultera i förbättrade användarupplevelser och prestanda.

>[!IMPORTANT]
>Microsoft 365 informerad nätverksdirigering är för närvarande i förhandsgranskningsstatus. Mer information om den här förhandsversionen, inklusive vägledning för mottagande av hjälp, finns i Microsoft 365 information om offentlig förhandsversion [för nätverksdirigering.](https://go.microsoft.com/fwlink/?linkid=2151565)

## <a name="overview"></a>Översikt

Välinformerad nätverksroutning är en dubbelriktad datadelningskanal mellan Microsoft och SD-WAN-lösningen. För varje kontor och internetkrets som du konfigurerar delar Microsoft med jämna mellanrum feedback med SD-WAN-lösningen om kvaliteten på valda Microsoft 365-programupplevelser för nätverkstrafik som associeras med varje specifik Internetkrets. Med den här feedbacken kan SD-WAN-lösningen sedan vidta smarta återställningsåtgärder genom att Microsoft 365 programtrafik via alternativa tillgängliga länkar. 

Kvaliteten på tjänsteförsämring i sökvägen till en viss internetkrets, till exempel ökad fördröjning eller hög paketförlust är svåra att upptäcka kontinuerligt. Dessa försämringar kan vara skadliga för användare i program som Exchange Online, SharePoint, OneDrive och Microsoft Teams. Vanliga symptom är långsam sökning av Exchange innehåll, stora överföringstider vid interaktion med SharePoint eller OneDrive-dokumentbibliotek eller dålig samtals- eller möteskvalitet i Microsoft Teams.

Feedback- och återställningsmekanismen inom nätverksinformningen söker efter dynamisk identifiering av sådana problem i nära realtid och meddelar den distribuerade SD-WAN-lösningen för att vidta automatiska återställningsåtgärder.

Datadelningskanalen används också för att regelbundet ta emotoptisk data på nätverksnivå från SD-WAN-lösningen, inklusive konfigurationsinformation och användningsstatistik som associeras med enheten och anslutna kretsar. Ingen personlig information samlas in eller lagras. All insamlad information aggregeras till kontorsplatser och anslutna internetkretsar. Den här informationen kan hjälpa Microsoft mer effektivt och effektivt att lösa rapporterade problem med din användning Microsoft 365 tjänster och program.

>[!NOTE]
>Microsoft 365 välinformerad nätverksdirigering har stöd för klientorganisation i kommersiella WW-moln men inte GCC Måttliga, GCC Hög, DoD, Tyskland eller Kina.

## <a name="requirements"></a>Krav

### <a name="integrated-sd-wan-solutions"></a>Integrerade SD-WAN-lösningar

Microsoft samarbetar med olika partner för att möjliggöra integrering med Microsoft 365 välinformerad nätverksdirigering. Exempel på lösningar som redan är aktiverade:

| Enhetshanteraren | Lösningsnamn | Lägsta version |
| --- | --- | --- |
| Cisco | [IOS XE SD-WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20.4/17.4 |

### <a name="network-topology"></a>Nätverkstopologi

Med välinformerad nätverksdirigering identifieras för närvarande trafik som associeras med en specifik kontorsplats och internetkrets baserat på den offentliga IP-adress som används för att skicka nätverkstrafik till Microsoft. 

Om det inte finns minst en nätverkskrets som ger direkt internetåtkomst på en filialplats, kan det hända att nätverksinbyggda routning inte ger något betydande värde.

### <a name="application-usage"></a>Programanvändning

Programupplevelsesdata (som återspeglas i nätverkskvalitetsmått) samlas in via användning av specifika Microsoft-klientprogram. Exchange mätvärdena återspeglar användningen Outlook klient samt en del Outlook Web App användning. SharePoint och OneDrive återspeglar användningen av klientorganisationens specifika SharePoint, oavsett klientprogram. Teams måtten återspeglar användningen av Teams-klienten på datorn. Annan programtrafik beaktas inte vid utvärdering av en nätverkskretss hälsa.

## <a name="enabling-informed-network-routing"></a>Aktivera informerad nätverksroutning

För aktivering av välinformerad nätverksroutning krävs flera steg, varav en del måste utföras i konfigurationsgränssnittet för SD-WAN-lösningen. Kontakta leverantören av SD-WAN-lösningar för att få vägledning om hur du ska initiera processen med att aktivera nätverksinformad routning i SD-WAN-lösningen innan du fortsätter med konfigurationen Microsoft 365 administrationscentret.

När du är redo att aktivera informerad nätverksdirigering i Microsoft 365-administrationscentret bör du kontrollera att du har nödvändiga globala administratörsbehörigheter.

>[!IMPORTANT]
>För att ge nödvändiga behörigheter på klientnivåprogram tillstånd för den valda SD-WAN-lösningen för att få åtkomst till den informerade kanalen för delning av nätverksroutningsdata måste du utföra följande steg som global administratör.


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Steg 1: Öppna konfigurationsalternativ för SD-WAN-lösningar

I Microsoft 365 [väljer du](https://admin.microsoft.com/)Hälsa **> Nätverksanslutningen i** det vänstra navigeringsfönstret.

Det här avsnittet i administrationscentret innehåller aggregerade mått för nätverksanslutning för din organisation och anvisningar om hur du kan förbättra anslutningen. Mer information [om de här funktionerna Microsoft 365 administrationscentret (förhandsversion)](office-365-network-mac-perf-overview.md) finns i Nätverksanslutningar i administrationscentret.

Välj **Inställningar > SD-WAN-lösning för** att öppna det informerade konfigurationsfönstret för nätverksroutning. De andra alternativen som visas under **Inställningar** gäller den allmänna vägledningen om nätverksanslutning i administrationscentret och krävs inte för att aktivera informerad nätverksdirigering.

Välj Lägg till din **SD-WAN-lösning (förhandsversion) i konfigurationsfönstret.**

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>Steg 2: Välj SD-WAN-lösning och datalagringsplats

I listrutorna väljer du den SD-WAN-lösning som du har distribuerat och den plats där du vill att data som associeras med nätverksinformad routning ska lagras. Mer information [finns i](#data-storage) avsnittet för datalagring.

Välj **Nästa**.

### <a name="step-3-accept-terms-for-sharing-of-data"></a>Steg 3: Acceptera villkor för delning av data

Läs noga och bekräfta de angivna villkoren för delning av data mellan Microsoft och din valda SD-WAN-lösning, och markera sedan kryssrutan.

Välj **Nästa**.

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>Steg 4: Tilldela behörigheter till SD-WAN-lösningen

Det här steget initierar en behörighetsbegäran med Azure Active Directory (Azure AD). Du uppmanas att bevilja behörigheter på klientnivå som tillåter att din valda SD-WAN-lösning får åtkomst till den informerade lagringen av nätverksroutningsdata och den hälsoinformation som är kopplad till din klientorganisation. Den här åtgärden kräver behörighet som global administratörsroll.

Välj länken **Ge behörighet till det här programmet** och följ Azure AD-begärandena.

När du har slutfört behörigheterna väljer du **Nästa.**

### <a name="step-5-confirm-your-configuration-settings"></a>Steg 5: Bekräfta konfigurationsinställningarna

Det sista steget för att aktivera nätverksinformerad routning för klientorganisationen är en bekräftelsesida där de inställningar du har angett visas. 

Informerad nätverksroutning är nu aktiverad för innehavaren.

Välj **Klar** och stäng sedan konfigurationsfönstret för SD-WAN-lösningen.

## <a name="configuring-network-informed-routing"></a>Konfigurera nätverksinformning

Du utför mycket av konfigurationen för välinformerad nätverksroutning i SD-WAN-lösningen, t.ex. genom att konfigurera hur trafiken ska dirigeras under normala förhållanden och de alternativa sökvägar som ska användas om problem upptäcks. Kontakta SD-WAN-lösningsleverantören för mer information om de här konfigurationsstegen.

Varje kontor måste konfigureras i administrationscentret för Microsoft 365 så att informerad nätverksdirigering kan identifiera trafik som är kopplad till de nätverkskretsar som tillhandahåller anslutningar till dessa platser.

Office platser kan upptäckas automatiskt som en del av Microsofts kontinuerliga samling av nätverks telemetri. Därför kan vissa platser vara förifyllda i administrationscentret för klientorganisationen. 

Om de här platserna är korrekta behöver du bara aktivera den informerade nätverksdirigeringsfunktionen för varje önskad plats och konfigurera Internetkretsarna och deras offentliga IP-adresser. 

Om de automatiskt identifierade platserna inte är korrekta, eller om det inte finns några förifyllda platser i klientorganisationen, måste du lägga till eller redigera platser manuellt för att återspegla en korrekt topologi för organisationen.

### <a name="updating-locations"></a>Uppdatera platser

Platser för klientorganisationen finns under **fliken** Platser. Platser kan redigeras direkt i listan eller uppdateras med hjälp av en CSV-fil.

Se till att varje kontorsplats där du vill aktivera informerad nätverksroutning finns i den här listan.

>[!NOTE]
>Kolumnerna i listan **Platser för** stickprov som samlas in och annan utvärderingsrelaterad information är inte relaterade till den underbyggda nätverksdirigeringsfunktionen.

### <a name="enabling-a-location-for-informed-network-routing"></a>Aktivera en plats för välinformerad nätverksdirigering

1. I listan **Platser väljer** du Redigera **i snabbåtgärder-menyn** för att öppna fönstret för platskonfiguration.

2. Välj **Använd Microsoft 365 informerad nätverksdirigering på den här platsen.**

3. Lägg till alla nätverkskretsar som tillhandahåller Internetanslutning till den här kontorsplatsen **i IP Egress adressintervallen för den här kontorsplatsen.** Se till att varje krets är kopplad till unika offentliga IP-adressundernät som representerar din nätverkstrafik.

4. Välj **Spara** för att spara ändringarna.

## <a name="disabling-network-informed-routing"></a>Inaktivera nätverksinformerad routning

Funktionen för välinformerad nätverksroutning kan inaktiveras för hela klientorganisationen genom att återställa inställningarna för SD-WAN-lösningen. Även om detta stoppar all bearbetning av data inom Microsoft 365 bör du också inaktivera nätverksinbyggda routning i administrationscentret.

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Steg 1: Öppna konfigurationsalternativ för SD-WAN-lösningar

I Microsoft 365 [väljer du](https://admin.microsoft.com/) **Hälsa > Nätverksanslutningen i** det vänstra navigeringsfönstret.

Välj **Inställningar > SD-WAN-lösning för** att öppna det informerade konfigurationsfönstret för nätverksroutning.

Konfigurationsfönstret visar en sammanfattning av den konfigurerade SD-WAN-lösningen.

### <a name="step-2-reset-your-configuration"></a>Steg 2: Återställ konfigurationen

Välj Återställ dina **SD-WAN-lösningsinställningar i konfigurationsfönstret.**

Inställningarna har nu återställts och informerad nätverksdirigering har inaktiverats. Du kan återaktivera den när som helst genom att följa stegen i [Aktivera informerad nätverksdirigering.](#enabling-informed-network-routing)

## <a name="data-storage"></a>Datalagring

Data som utbyts mellan Microsoft och SD-WAN-lösningsleverantören lagras på den datalagringsplats som valts vid den första funktionen för nätverksinitierad routning. Alternativen för datalagringsplats representerar geografiska områden Microsoft Azure regioner där data lagras.

>[!NOTE]
>Under förhandsgranskningsfasen är Nordamerika den enda tillgängliga **lagringsplatsen för data.** Ytterligare datalagringsplatser blir tillgängliga innan en välinformerad nätverksroutning blir allmänt tillgänglig.

Data lagras på den här platsen i upp till 30 dagar. När den inaktiveras tas alla återstående data bort inom det här 30-dagars kvarhållningsfönstret.

## <a name="related-topics"></a>Relaterade ämnen

[Nätverksanslutningen i administrationscentret Microsoft 365 (förhandsversion)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Nätverksplatstjänster (förhandsversion)](office-365-network-mac-location-services.md)
