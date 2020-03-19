---
title: Konfigurerbara inställningar för Microsoft Managed Desktop
description: Information om konfigurerbara inställningar med Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation, inställningar, konfigurerbara inställningar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: d8ebe4519d169db5500c55a3337836ca2d0986c0
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/28/2019
ms.locfileid: "42806792"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>Konfigurerbara inställningar - Microsoft Managed Desktop

Microsoft Managed Desktop distribuerar inställningar och principer som tillämpas på alla enheter som hanteras av Microsoft Managed Desktop. Mer information finns i [Enhetskonfiguration](../service-description/device-policies.md).

Konfigurerbara inställningar i Microsoft Managed Desktop ger IT-administratörer ett sätt att anpassa och distribuera inställningar som är unika för deras organisation och affärsbehov. Dessa inställningar är utöver inställningar och principer för enhetskonfiguration som hanteras av Microsoft Managed Desktop.  

Konfigurerbara inställningsändringar görs i molnet och tillämpas på dina Microsoft Managed Desktop-enheter i definierade distributionsgrupper. Den här processen liknar hur Microsoft Managed Desktop hanterar ändringar av enhetskonfigureringsinställningar och principer som definieras och hanteras av tjänsten. Genom att använda samma process som Microsoft Managed Desktop använder för att distribuera ändringar fortsätter du att flytta organisationen framåt med hjälp av moderna IT-hanteringsmetoder.

## <a name="when-to-use-configurable-settings"></a>När ska konfigurerbara inställningar användas?

Det finns några gånger att använda konfigurerbara inställningar. 

**Introduktionsprocess** – Microsoft Managed Desktop rekommenderar att du anpassar konfigurerbara inställningar när du är ombord på Microsoft Managed Desktop-tjänsten eller när du är ombord på ett stort antal enheter (20 eller fler). Inställningskategorier konfigureras i Microsoft Managed Desktop-administratörsportalen. När du har gått in och har åtkomst till administratörsportalen kan du bestämma vilka inställningskategorier du vill anpassa för din organisation, göra ändringarna, iscensätta en distribution och sedan distribuera ändringarna.

**Underhåll inställningar** - Granska dina inställningar regelbundet och gör nödvändiga uppdateringar. Du kan behöva göra ändringar för att stödja en ändring i ditt företag.   

## <a name="setting-categories"></a>Ange kategorier

Det här är de konfigurerbara inställningskategorierna som du kan anpassa:
- [Bakgrundsbild](config-setting-ref.md#desktop-background-picture) för skrivbordet – Anpassa skrivbordsbakgrundsbilden för Microsoft Hanterade stationära enheter. 
- [Startsidor för webbläsare](config-setting-ref.md#browser-start-pages) – Lägg till startsidor som ska användas med Microsoft Edge. Se Startsida för webbläsare
- [Webbplatslista för företagsläge](config-setting-ref.md#enterprise-mode-site-list-location) – Lägg till webbplatser och deras kompatibilitetsläge. Webbplatser i listan startar i Internet Explorer. 
- [Betrodda platser](config-setting-ref.md#trusted-sites) – Lägg till betrodda platser och ange säkerhetszoner för varje plats. 
- [Proxyplatsundantag](config-setting-ref.md#proxy) – Ställ in adressnummer och portnummer för proxyservern och lägg till proxyplatsundantag.

Varje inställningskategori kan anpassas och distribueras på egen hand. Du kan distribuera ändringar till flera inställningskategorier samtidigt, men du kan bara distribuera en ändring i taget till en inställningskategori.

Till exempel:
- Du kan distribuera ändringar i skrivbordsbakgrundsbild och betrodda platser, var och en som sin egen distribution, samtidigt. 
- Du kan inte distribuera två distributioner till startsidor i webbläsaren samtidigt. Den senaste distributionen stoppar tidigare distributioner som fortfarande pågår.

## <a name="configurable-setting-process"></a>Konfigurerbar inställningsprocess

Microsoft Managed Desktop rekommenderar att du följer en process som liknar följande när du använder konfigurerbara inställningar för din organisation:

**Steg 1 - Planera** - Lär dig mer om konfigurerbara inställningar och bestäm vilka inställningskategorier du vill konfigurera för din organisation. Skapa en tidslinje för när du förväntar dig att distribuera ändringar till varje grupp. Planera kommunikationen till användarna som uppfyller dina interna ändringshanteringsprocesser. Om du till exempel lägger till startsidor i webbläsaren meddelar du användarna att de har en ny uppsättning startsidor i webbläsaren efter distributionen.  

**Steg 2 – Konfigurera och arrangera distribution** – Gör ändringar i konfigurerbara inställningar i Microsoft Managed Desktop-administratörsportalen. Arrangera ändringarna så att de är redo att distribuera. Kom ihåg att informera användarna om ändringarna och hur ändringarna kommer att ändra deras enhetsupplevelse.   

Du konfigurerar och arrangerar ändringar i administrationsportalen för Microsoft Managed Desktop. Mer information finns i [Anpassa konfigurerbara inställningar](config-setting-ref.md). 

**Steg 3 - Kommunicera ändringar** Kommunicera information om kommande ändringar till användarna. Slutför kommunikationen som ingår i dina ändringshanteringsprocesser för varje distribution. Du bör tydligt kommunicera alla ändringar som påverkar hur en användare fungerar, eller vad de kommer att se på sina enheter.

**Steg 4 – Distribuera ändringar** – Distribuera dina ändringar, med början i testgruppen. Med gruppen Test kan du validera och felsöka eventuella problem i en grupp med färre enheter innan du distribuerar ändringar till större grupper av enheter. Om du stöter på problem kan du återställa ändringen, uppdatera inställningen och iscensätta en ny distribution. Microsoft Managed Desktop rekommenderar att du följer den strukturerade metoden och distribuerar till grupper i den här ordningen: Testa, Först, Snabbt och sedan Brett.   

Alla konfigurerbara inställningar hanteras med hjälp av administrationsportalen för Microsoft Managed Desktop. Mer information finns i [Distribuera ändringar](config-setting-deploy.md). 

**Steg 5 – Spåra ändringar** – Spåra förloppet för dina ändringar av distributionsstatus. För varje inställning kan du:
- **Spåra förloppet** – Spåra status när du har distribuerat ändringen. Statusen ändras till **Pågår**och sedan **antingen Slutför**eller **Misslyckades**. Om en distribution misslyckas öppnas en supportbegäran automatiskt för Microsoft Managed Desktop Operations för att undersöka problemet.  
- **Se distribuerad version** – Varje distribuerad ändring har ett versionsnummer.
- **Återställ ändringar** – Om du återställer en ändring stoppas den aktuella distributionen och alla grupper återgår till de senaste ändringarna som har distribuerats till alla grupper. Du rullar tillbaka till det senast kända inställningsvärdet.
- **Validera ändringar** - När distributionen är klar har du validerat ändringarna som förväntat.  

Om en distribution har misslyckats eller om du inte kan återställa en ändring öppnar du [en supportbegäran](admin-support.md) med Microsoft Managed Desktop Operations. 

Mer information finns i [Distribuera och spåra konfigurerbara inställningar](config-setting-deploy.md).

## <a name="additional-resources"></a>Ytterligare resurser
- [Konfigurerbar inställningsreferens](config-setting-ref.md) 
- [Distribuera konfigurerbara inställningar](config-setting-deploy.md) 
