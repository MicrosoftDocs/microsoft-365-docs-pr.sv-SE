---
title: Microsoft 365-informerad nätverksdirigering
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
description: Microsoft 365-informerad nätverksdirigering
ms.openlocfilehash: 5275f8ea55afaf621555b440e7fae4a6d11cad91
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717586"
---
# <a name="microsoft-365-informed-network-routing-preview"></a>Microsoft 365-informerad nätverksdirigering (förhandsversion)

Informerad nätverksdirigering är en funktion som integrerar olika Microsoft 365-program med SD-WAN-lösningar (programvara som definierats av tredje part) för att optimera och förbättra nätverksanslutningen till Microsoft-tjänstens slutpunkter. Optimerad SD-WAN-anslutning kan resultera i förbättrade användarupplevelser och prestanda.

>[!IMPORTANT]
>Microsoft 365-informerad nätverksdirigering är för närvarande i förhandsgranskningsstatus. Mer information om den här förhandsversionen, inklusive vägledning för att få hjälp, finns i Den offentliga förhandsversionen av [dirigering i Microsoft 365.](https://go.microsoft.com/fwlink/?linkid=2151565)

## <a name="overview"></a>Översikt

Informerad nätverksdirigering ger en dubbelriktad datadelningskanal mellan Microsoft och din SD-WAN-lösning. För varje kontor och internetkrets som du konfigurerar delar Microsoft regelbundet feedback med SD-WAN-lösningen om kvaliteten på valda Microsoft 365-programupplevelser för nätverkstrafik kopplad till varje specifik Internetkrets. Med den här feedbacken kan SD-WAN-lösningen sedan vidta smarta återställningsåtgärder genom att dirigera Microsoft 365-programtrafik via alternativa tillgängliga länkar. 

Tjänstekvalitetsförsämring i sökvägen till en viss Internetkrets, till exempel ökad fördröjning eller hög paketförlust, är svåra att upptäcka kontinuerligt. Dessa försämringar kan skada användarupplevelsen för program som Exchange Online, SharePoint, OneDrive och Microsoft Teams. Vanliga symptom är långsam sökning av Exchange-innehåll, stora överföringstider vid interaktion med SharePoint- eller OneDrive-dokumentbibliotek eller dålig samtals- eller möteskvalitet i Microsoft Teams.

Feedback- och återställningsmekanismen i nätverksinbyggda routning söker dynamiskt efter sådana problem i nära realtid och meddelar den distribuerade SD-WAN-lösningen att vidta automatiska återställningsåtgärder.

Datadelningskanalen används också för att regelbundet ta emotoptisk data på nätverksnivå från SD-WAN-lösningen, inklusive konfigurationsinformation och användningsstatistik som associeras med enheten och anslutna kretsar. Ingen personlig information samlas in eller lagras. All insamlad information aggregeras till kontorsplatser och anslutna Internetkretsar. Den här informationen kan hjälpa Microsoft på ett effektivare sätt att lösa rapporterade problem med din användning av Microsoft 365-tjänster och -program.

>[!NOTE]
>Microsoft 365-informerad nätverksdirigering stöder klientorganisation i kommersiella WW-moln men inte molnen GCC Måttlig, GCC High, DoD, Tyskland eller Kina.

## <a name="requirements"></a>Krav

### <a name="integrated-sd-wan-solutions"></a>Integrerade SD-WAN-lösningar

Microsoft samarbetar med olika partner för att möjliggöra integrering med dirigering av Microsoft 365-underbyggda nätverk. För närvarande finns följande lösningar:

| Device Maker | Lösningsnamn | Lägsta version |
| --- | --- | --- |
| Cisco | [IOS XE SD-WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20.4/17.4 |

### <a name="network-topology"></a>Nätverkstopologi

Informerad nätverksdirigering identifierar för närvarande trafik som är kopplad till en specifik kontorsplats och internetkrets baserat på den offentliga IP-adress som används för att skicka nätverkstrafik till Microsoft. 

Om det inte finns minst en nätverkskrets som ger direkt internetanslutning på en filialplats, kan det hända att nätverksinbyggda routning inte ger betydande värde.

### <a name="application-usage"></a>Programanvändning

Programupplevelsesdata (som återspeglas i nätverkskvalitetsmått) samlas in genom användning av specifika Microsoft-klientprogram. Exchange-mått återspeglar användningen av Outlook-klienten samt viss Outlook Web App-användning. Måtten för SharePoint och OneDrive återspeglar användningen av de klientspecifika SharePoint-slutpunkterna, oavsett klientprogram. Teams-mått återspeglar användningen av Teams skrivbordsklient. Annan programtrafik beaktas inte vid utvärdering av hälsotillståndet för en nätverkskrets.

## <a name="enabling-informed-network-routing"></a>Aktivera informerad nätverksdirigering

Aktivering av informerad nätverksdirigering kräver flera steg, av vilka en del måste utföras i konfigurationsgränssnittet för SD-WAN-lösningen. Kontakta SD-WAN-lösningsleverantören för anvisningar om hur du initierar processen med att aktivera nätverksinformad routning i SD-WAN-lösningen innan du fortsätter med konfigurationen i administrationscentret för Microsoft 365.

När du är redo att aktivera informerad nätverksdirigering i administrationscentret för Microsoft 365 bör du kontrollera att du har de globala administratörsbehörigheter som krävs.

>[!IMPORTANT]
>För att ge nödvändiga behörigheter på innehavarnivå för programbehörigheter för den valda SD-WAN-lösningen för att få åtkomst till den informerade kanalen för nätverksdirigeringsdatadelning måste du utföra följande steg som global administratör.


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Steg 1: Öppna konfigurationsalternativ för SD-WAN-lösningar

I [administrationscentret för Microsoft 365](https://admin.microsoft.com/)väljer du **> nätverksanslutning** i det vänstra navigeringsfönstret.

Det här avsnittet i administrationscentret innehåller aggregerade mätvärden för nätverksanslutning för din organisation och vägledning för hur du kan förbättra anslutningen. Se [Nätverksanslutningen i administrationscentret för Microsoft 365 (förhandsversion)](office-365-network-mac-perf-overview.md) för ytterligare information om de här funktionerna som är tillgängliga i administrationscentret.

Välj **Inställningar > SD-WAN-lösning för att** öppna det informerade konfigurationsfönstret för nätverksdirigering. De andra alternativen som visas under **Inställningar** gäller för den allmänna vägledningen om nätverksanslutning i administrationscentret och krävs inte för att aktivera informerad nätverksdirigering.

Välj Lägg till din **SD-WAN-lösning (förhandsversion) i konfigurationsfönstret.**

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>Steg 2: Välj din SD-WAN-lösning och datalagringsplats

I listrutorna väljer du SD-WAN-lösningen som du har distribuerat och den plats där du vill att data som är kopplade till nätverksinformerad routning ska lagras. Mer information [finns i](#data-storage) avsnittet för datalagring.

Välj **Nästa**.

### <a name="step-3-accept-terms-for-sharing-of-data"></a>Steg 3: Acceptera villkoren för delning av data

Läs noga igenom och bekräfta angivna termer som är associerade med delning av data mellan Microsoft och din valda SD-WAN-lösning, och markera sedan kryssrutan.

Välj **Nästa**.

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>Steg 4: Tilldela behörigheter till SD-WAN-lösningen

Det här steget initierar en begäran om att bevilja behörigheter med Azure Active Directory (Azure AD). Du uppmanas att bevilja behörigheter på klientnivå som ger den valda SD-WAN-lösningen åtkomst till den informerade lagringen av nätverksdirigeringsdata och den hälsoinformation som är kopplad till klientorganisationen. Den här åtgärden kräver behörighet som global administratörsroll.

Välj länken **Ge behörighet till den här appen** och följ Azure AD-begärandena.

Välj Nästa när du har slutfört **behörighetsbehörigheten.**

### <a name="step-5-confirm-your-configuration-settings"></a>Steg 5: Bekräfta konfigurationsinställningarna

Det sista steget för att aktivera nätverksinformerad routning för klientorganisationen är en bekräftelsesida som visar de inställningar du har angett. 

Informerad nätverksdirigering är nu aktiverad för innehavaren.

Välj **Klar** och stäng sedan konfigurationsfönstret för SD-WAN-lösningen.

## <a name="configuring-network-informed-routing"></a>Konfigurera nätverksinformerad routning

Du utför mycket av konfigurationen för informerad nätverksdirigering i SD-WAN-lösningen, till exempel konfigurera hur trafiken ska dirigeras under normala förhållanden och de alternativa sökvägar som ska användas om problem upptäcks. Kontakta SD-WAN-lösningsleverantören för mer information om de här konfigurationsstegen.

Varje kontor måste konfigureras i administrationscentret för Microsoft 365 så att informerad nätverksdirigering kan identifiera trafik som är kopplad till nätverkskretsarna som tillhandahåller anslutningar till dessa platser.

Office-platser kan upptäckas automatiskt som en del av Microsofts löpande samling av nätverks telemetri. Därför kan vissa platser vara förifyllda i administrationscentret för innehavaren. 

Om de här platserna är korrekta behöver du bara aktivera den informerade nätverksdirigeringsfunktionen för varje önskad plats och konfigurera Internetkretsarna och deras offentliga IP-adresser. 

Om de automatiskt identifierade platserna inte är korrekta, eller om det inte finns några förifyllda platser i klientorganisationen, måste du lägga till eller redigera platser manuellt för att återspegla en korrekt topologi för organisationen.

### <a name="updating-locations"></a>Uppdatera platser

Platser för klientorganisationen finns under **fliken** Platser. Platser kan redigeras direkt i listan eller uppdateras med hjälp av en CSV-fil.

Se till att varje kontor där du vill aktivera informerad nätverksdirigering finns i den här listan.

>[!NOTE]
>Kolumnerna i listan **Platser för** prov som samlas in och annan utvärderingsrelaterad information är inte relaterade till funktionen för informerad nätverksdirigering.

### <a name="enabling-a-location-for-informed-network-routing"></a>Aktivera en plats för informerad nätverksdirigering

1. I listan **Platser väljer** du Redigera **i snabbåtgärder-menyn** för att öppna fönstret för platskonfiguration.

2. Välj **Använd Microsoft 365-informerad nätverksdirigering på den här platsen.**

3. Lägg till alla nätverkskretsar som tillhandahåller Internetanslutning till den här kontorsplatsen i **IP-adressintervallen för utgående adresser i det här avsnittet för kontorsplats.** Se till att varje krets är kopplad till de unika offentliga IP-adressundernäten som representerar din nätverkstrafik.

4. Välj **Spara** för att spara ändringarna.

## <a name="disabling-network-informed-routing"></a>Inaktivera nätverksinformerad routning

Funktionen för informed nätverksroutning kan inaktiveras för hela klientorganisationen genom att återställa dina SD-WAN-lösningsinställningar. Även om detta stoppar all databearbetning inom Microsoft 365 bör du också inaktivera nätverksinformerad routning i administrationscentret.

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Steg 1: Öppna konfigurationsalternativ för SD-WAN-lösningar

I [administrationscentret för Microsoft 365](https://admin.microsoft.com/) väljer du **> nätverksanslutning** i det vänstra navigeringsfönstret.

Välj **Inställningar > SD-WAN-lösning för att** öppna det informerade konfigurationsfönstret för nätverksdirigering.

Konfigurationsfönstret visar en sammanfattning av din för närvarande konfigurerade SD-WAN-lösning.

### <a name="step-2-reset-your-configuration"></a>Steg 2: Återställ konfigurationen

Välj Återställ dina **SD-WAN-lösningsinställningar i konfigurationsfönstret.**

Dina inställningar har nu återställts och informerad nätverksdirigering har inaktiverats. Du kan återaktivera den när som helst genom att följa stegen i [Aktivera informerad nätverksdirigering.](#enabling-informed-network-routing)

## <a name="data-storage"></a>Datalagring

Data som utväxlar mellan Microsoft och SD-WAN-lösningsleverantören lagras på den datalagringsplats som valdes vid den första funktionen för nätverksinitierad routning. Alternativen för datalagringsplats representerar geografiska områden som innehåller Microsoft Azure-regioner där data lagras.

>[!NOTE]
>Under förhandsgranskningsfasen är Nordamerika den enda tillgängliga **datalagringsplatsen.** Ytterligare datalagringsplatser blir tillgängliga innan den allmänt tillgängliga dirigeringen blir allmänt tillgänglig.

Data lagras på den här platsen i upp till 30 dagar. När den är inaktiverad tas alla återstående data bort inom det här 30-dagars kvarhållningsfönstret.

## <a name="related-topics"></a>Relaterade ämnen

[Nätverksanslutning i administrationscentret för Microsoft 365 (förhandsversion)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Network Connectivity Location Services (förhandsversion)](office-365-network-mac-location-services.md)
