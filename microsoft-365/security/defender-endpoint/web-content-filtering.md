---
title: Filtrering av webbinnehåll
description: Använd webbinnehållsfiltrering i Microsoft Defender för Endpoint för att spåra och reglera åtkomsten till webbplatser baserat på deras innehållskategorier.
keywords: webbskydd, skydd mot webbhot, surfning, övervakning, rapporter, kort, domänlista, säkerhet, nätfiske, skadlig kod, sårbarhet, webbplatser, nätverksskydd, Edge, Internet Explorer, Chrome, Firefox, webbläsare
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c7b39b600af2fed130a0b78a590740a8bc063f50
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861701"
---
# <a name="web-content-filtering"></a>Filtrering av webbinnehåll

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> **Webbinnehållsfiltrering är för närvarande i offentlig förhandsversion**<br>
> Den här förhandsversionen tillhandahålls utan ett servicenivåavtal och rekommenderas inte för produktionsarbetsbelastningar. Vissa funktioner kanske inte stöds eller kan ha begränsade funktioner.
> Mer information finns i [Förhandsversionsfunktioner för Microsoft Defender för slutpunkt.](preview.md)

> [!TIP]
> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Webbinnehållsfiltrering är [en del av webbskyddsfunktionerna](web-protection-overview.md) i Microsoft Defender för Endpoint. Det gör att din organisation kan spåra och reglera åtkomsten till webbplatser baserat på deras innehållskategorier. Många av dessa webbplatser, även om de inte är skadliga, kan vara problematiska på grund av regelefterlevnad, bandbreddsanvändning eller andra problem.

Konfigurera principer i din enhetsgrupper för att blockera vissa kategorier. När en kategori blockeras förhindrar du att användare i angivna enhetsgrupper kommer åt URL-adresser som är kopplade till kategorin. URL-adresser granskas automatiskt för alla kategorier som inte blockeras. Användarna kan komma åt URL-adresser utan störningar och du samlar in åtkomststatistik för att skapa ett mer anpassat principbeslut. Användarna ser ett blockeringsmeddelande om ett element på sidan de visar är att ringa samtal till en blockerad resurs.

Webbinnehållsfiltrering är tillgängligt i de större webbläsarna, med block som utförs av Windows Defender SmartScreen (Microsoft Edge) och Nätverksskydd (Chrome, Firefox, Och Opera). Mer information om webbläsarstöd finns i avsnittet krav.

Sammanfattning av fördelarna:

- Användare hindras från att komma åt webbplatser i blockerade kategorier, oavsett om de surfar lokalt eller inte
- Ditt säkerhetsteam kan enkelt distribuera principer till grupper av användare med hjälp av enhetsgrupper som definierats i Microsoft Defender för [slutpunktsrollbaserade inställningar för åtkomstkontroll](/microsoft-365/security/defender-endpoint/rbac)
- Säkerhetsteamet kan komma åt webbrapporter på samma centrala plats, med synlighet över faktiska block och webbanvändning

## <a name="user-experience"></a>Användarupplevelse

Blockeringen för webbläsare som stöds av tredje part tillhandahålls av Network Protection, som ger ett popup-meddelande på systemnivå om en blockerad anslutning för användaren. Om du vill ha en mer användarvänlig upplevelse i webbläsaren kan du använda Microsoft Edge.

## <a name="prerequisites"></a>Förutsättningar

Innan du provar den här funktionen bör du kontrollera att du uppfyller följande krav:

- Windows 10 Enterprise E5 Microsoft 365 E5, Microsoft 365 E5 Security, Microsoft 365 E3 + Microsoft 365 E5 Security eller Microsoft Defender för slutpunkten som är fristående licens. 
- Åtkomst till Microsoft Defender Säkerhetscenter portal ( https://securitycenter.windows.com) .
- Enheter som kör Windows 10 Anniversary Update (version 1607) eller senare med den senaste Mo FUNKTIONEN-uppdateringen.
- Windows Defender SmartScreen och nätverksskydd aktiverade.


## <a name="data-handling"></a>Datahantering

Data lagras i den region som valdes som en del av dina inställningar för [Microsoft Defender för Slutpunktsdatahantering.](data-storage-privacy.md) Dina data lämnar inte datacentret i den regionen. Dessutom kommer dina data inte att delas med någon tredje part, inklusive våra dataleverantörer.

## <a name="turn-on-web-content-filtering"></a>Aktivera webbinnehållsfiltrering

I den vänstra navigeringsmenyn väljer du **Inställningar**  >    >  **Avancerade funktioner.** Bläddra nedåt tills du ser posten för **webbinnehållsfiltrering**. Ändra växlingsknappen till **På** **och Spara inställningar.**

### <a name="configure-web-content-filtering-policies"></a>Konfigurera principer för filtrering av webbinnehåll

Principer för filtrering av webbinnehåll anger vilka webbplatskategorier som blockeras i vilka enhetsgrupper. Gå till Regelfiltrering av **webbinnehåll Inställningar** för att  >    >  **hantera principerna.**

Använd filtret för att hitta principer som innehåller vissa blockerade kategorier eller som tillämpas på specifika enhetsgrupper.

### <a name="create-a-policy"></a>Skapa en princip

Så här lägger du till en ny princip:

1. Välj **Lägg till princip** på sidan för **webbinnehållsfiltrering** i **Inställningar**.

2. Ange ett namn.

3. Markera de kategorier som ska blockeras. Använd expanderikonen för att helt expandera varje överordnad kategori och välja specifika kategorier för webbinnehåll.

4. Ange principens omfattning. Välj enhetsgrupper för att ange var principen ska tillämpas. Det är bara enheter i de valda enhetsgrupperna som hindras från att komma åt webbplatser i de valda kategorierna.

5. Granska sammanfattningen och spara principen. Det kan ta upp till 2 timmar innan principuppdateringen tillämpas på dina valda enheter.

> [!NOTE]
> - Du kan distribuera en princip utan att välja en kategori i en enhetsgrupp. Den här åtgärden skapar en princip för granskning bara för att hjälpa dig att förstå användarbeteendet innan du skapar en blockeringsprincip.
> - Om du tar bort en princip eller ändrar enhetsgrupper samtidigt kan det orsaka en fördröjning i principdistributionen.
> - Att blockera kategorin "Okategoriserad" kan leda till oväntade och oönskade resultat.  

### <a name="allow-specific-websites"></a>Tillåt specifika webbplatser

Du kan åsidosätta kategorin blockerad i webbinnehållsfiltrering om du vill tillåta en enda webbplats genom att skapa en egen indikatorprincip. Principen för anpassad indikator ersätter webbinnehållsfiltreringsprincipen när den tillämpas på enhetsgruppen i fråga.

1. Du kan skapa en anpassad indikator i Microsoft Defender Säkerhetscenter genom att gå **Inställningar**  >    >  **URL/Domain**  >  **Add Item**.

2. Ange domänen för webbplatsen.

3. Ställ in principåtgärden på **Tillåt**.  

### <a name="reporting-inaccuracies"></a>Rapportering av felaktigheter

Om du träffar på en domän som felaktigt har kategoriserats kan du rapportera felaktigheter direkt till oss från rapportsidan Webbinnehållsfiltrering. Den här funktionen är endast tillgänglig i det Microsoft 365 säkerhetscentret (security.microsoft.com).

Om du vill rapportera en säkerhet går du till Reports  >  **Web Protection Web Content** Filtering  >  **Details**  >  **Domains**. På fliken Domäner i webbinnehållsfiltreringsrapporterna visas en ellips bredvid var och en av domänerna. Hovra över de här ellipsen **och välj Rapportinaccuracy**.

En panel öppnas där du kan välja prioritet och lägga till ytterligare information, till exempel den föreslagna kategorin för omkategorisering. När du har slutfört formuläret väljer du **Skicka**. Vår grupp kommer att granska begäran inom en arbetsdag. Skapa en anpassad indikator för tillåt för omedelbar [blockering.](indicator-ip-domain.md)

## <a name="web-content-filtering-cards-and-details"></a>Filtreringskort och information för webbinnehåll

Välj **Rapporter**  >  **Webbskydd om** du vill visa kort med information om webbinnehållsfiltrering och skydd mot webbhot. På följande kort får du sammanfattningsinformation om filtrering av webbinnehåll.

### <a name="web-activity-by-category"></a>Webbaktivitet efter kategori

Det här kortet visar de överordnade webbinnehållskategorierna med den största ökningen eller minskning av antalet åtkomstförsök. Förstå förändrat webbaktivitetsmönster i organisationen från de senaste 30 dagarna, 3 månaderna eller 6 månaderna. Välj ett kategorinamn om du vill visa mer information.

Under de första 30 dagarna av den här funktionen kanske organisationen inte har tillräckligt med data för att visa den här informationen.

![Bild av webbaktivitet efter kategorikort](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a>Sammanfattningskort för webbinnehållsfiltrering

På det här kortet visas fördelningen av blockerade åtkomstförsök mellan de olika överordnade webbinnehållskategorierna. Välj en av de färgade staplarna om du vill visa mer information om en viss överordnad webbkategori.

![Bild på sammanfattningskort för filtrering av webbinnehåll](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a>Sammanfattningskort för webbaktivitet

På det här kortet visas det totala antalet begäranden om webbinnehåll i alla URL:er.

![Bild på sammanfattningskort för webbaktivitet](images/web-activity-summary.png)

### <a name="view-card-details"></a>Visa kortinformation

Du kommer åt **rapportinformationen för varje** kort genom att välja en tabellrad eller en färgad stapel i diagrammet på kortet. Rapportinformationssidan för varje kort innehåller omfattande statistiska data om kategorier av webbinnehåll, webbplatsdomäner och enhetsgrupper.

![Bild på information om webbskyddsrapporten](images/web-protection-report-details.png)

- **Webbkategorier:** Visar de webbinnehållskategorier som har haft åtkomstförsök i organisationen. Välj en specifik kategori för att öppna en utfällbladstext för sammanfattningen.

- **Domäner**: Visar de webbdomäner som har använts eller blockerats i organisationen. Välj en viss domän om du vill visa detaljerad information om den domänen.

- **Enhetsgrupper:** Visar alla enhetsgrupper som har skapat webbaktivitet i organisationen

Använd tidsintervallsfiltret längst upp till vänster på sidan för att välja en tidsperiod. Du kan också filtrera informationen eller anpassa kolumnerna. Markera en rad för att öppna ett utfällt fönster med ännu mer information om det markerade objektet.

## <a name="errors-and-issues"></a>Fel och problem

### <a name="limitations-and-known-issues-in-this-preview"></a>Begränsningar och kända problem i den här förhandsversionen

- Endast Microsoft Edge om enhetens OS-konfiguration är Server **(cmd**  >  **Systeminfo**  >  **OS Configuration).** Nätverksskydd stöds endast i inspektera-läge på serverenheter, som ansvarar för att skydda trafiken mellan webbläsare som stöds.

- Enheter som inte tilldelats visas med felaktiga data i rapporten. I **rapportens**  >  **detaljenhetsgrupper** visas eventuellt en rad med ett tomt enhetsgruppsfält. Den här gruppen innehåller dina otilldelade enheter innan de läggs till i den angivna gruppen. Rapporten för den här raden kanske inte innehåller rätt antal enheter eller antal åtkomstvärden.

- Rapporterna för webbinnehållsfiltrering är för närvarande begränsade till att visa de 5 000 högsta posterna. Till exempel visar rapporten Domäner endast det högsta antalet 5 000 domäner för en viss filterfråga, om tillämpligt. 



- [Översikt över webbskydd](web-protection-overview.md)
- [Skydd mot webbhot](web-threat-protection.md)
- [Övervaka webbsäkerhet](web-protection-monitoring.md)
- [Svara på webbhot](web-protection-response.md)
- [Krav för nätverksskydd](web-content-filtering.md)

