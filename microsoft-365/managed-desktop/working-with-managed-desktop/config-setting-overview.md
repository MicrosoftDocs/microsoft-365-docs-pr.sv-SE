---
title: Konfigurerbara inställningar för Microsoft Hanterat skrivbord
description: Information om konfigurerbara inställningar med Microsoft Hanterat skrivbord
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation, inställningar, konfigurerbara inställningar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bf8672ee6c3332ea6f8522f5086d72e58d1b9048
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371496"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>Konfigurerbara inställningar – Microsoft Hanterat skrivbord

Microsoft Hanterat skrivbord distribuerar inställningar och principer som tillämpas på alla enheter som hanteras av Microsoft Hanterat skrivbord. Mer information finns i [Enhetskonfiguration](../service-description/device-policies.md).

Konfigurerbara inställningar i Microsoft Hanterat skrivbord ger IT-administratörer ett sätt att anpassa och distribuera inställningar som är unika för organisationens och verksamhetens behov. De här inställningarna är utöver inställningar för enhetskonfiguration och principer som hanteras av Microsoft Hanterat skrivbord.  

Konfigurerbara inställningsändringar görs i molnet och tillämpas på Microsoft Hanterat skrivbord enheter i definierade distributionsgrupper. Den här processen liknar hur Microsoft Hanterat skrivbord ändrar inställningar för enhetskonfiguration och principer som definieras och hanteras av tjänsten. Genom att använda samma process som Microsoft Hanterat skrivbord för att distribuera ändringar fortsätter du att flytta organisationen framåt med moderna IT-hanteringsmetoder.

## <a name="when-to-use-configurable-settings"></a>När bör du använda konfigurerbara inställningar?

Det finns några gånger då konfigurerbara inställningar kan användas. 

**Onboarding-process** – Microsoft Hanterat skrivbord rekommenderar att du anpassar konfigurerbara inställningar när du går in på Microsoft Hanterat skrivbord-tjänsten eller när du använder ett stort antal enheter (20 eller fler). Inställningar av kategorier konfigureras i Microsoft Hanterat skrivbord administrationsportalen. När du har gått igång och har åtkomst till administratörsportalen kan du bestämma vilka kategorier du vill anpassa för din organisation, göra ändringarna, fasa in en distribution och sedan distribuera dina ändringar.

**Underhålla inställningar** – granska inställningarna regelbundet och gör nödvändiga uppdateringar. Du kan behöva göra ändringar för att stödja en ändring i ditt företag.   

## <a name="setting-categories"></a>Ange kategorier

Det här är de konfigurerbara inställningskategorier som du kan anpassa:
- [Skrivbordsbakgrund –](config-setting-ref.md#desktop-background-picture) Anpassa skrivbordsbakgrundsbilden för Microsoft Hanterat skrivbord enheter. 
- [Startsidor för webbläsare](config-setting-ref.md#browser-start-pages) – Lägga till startsidor som ska användas med Microsoft Edge. Se webbläsarens startsida
- [Webbplatslista för företagsläge](config-setting-ref.md#enterprise-mode-site-list-location) – Lägg till webbplatser och deras kompatibilitetsläge. Webbplatserna i listan börjar i Internet Explorer. 
- [Betrodda](config-setting-ref.md#trusted-sites) platser – Lägg till betrodda platser och ange säkerhetszoner för varje webbplats. 
- [Undantag för proxywebbplatser](config-setting-ref.md#proxy) – konfigurera proxyserverns adressnummer och portnummer och lägg till undantag för proxywebbplatsen.

Varje inställningskategori kan anpassas och distribueras på egen hand. Du kan distribuera ändringar till flera inställningskategorier samtidigt, men du kan bara distribuera en ändring i taget till en inställningskategori.

Till exempel:
- Du kan distribuera ändringar till skrivbordsbakgrundsbilden och betrodda webbplatser, var och en som sin egen distribution, samtidigt. 
- Du kan inte distribuera två distributioner till webbläsarens startsidor samtidigt. Den senaste distributionen stoppar tidigare distributioner som fortfarande pågår.

## <a name="configurable-setting-process"></a>Konfigurerbar inställningsprocess

Microsoft Hanterat skrivbord rekommenderar att du följer en process som liknar följande när du använder konfigurerbara inställningar för organisationen:

**Steg 1 – Abonnemang** – Läs mer om konfigurerbara inställningar och bestäm vilka kategorier du vill konfigurera för organisationen. Skapa en tidslinje för när du vill distribuera ändringar till varje grupp. Planera kommunikationen till de användare som uppfyller dina interna processer för ändringshantering. Om du till exempel lägger till startsidor för webbläsare kan du meddela användarna att de kommer att ha en ny uppsättning startsidor i webbläsaren efter distributionen.  

**Steg 2 - Konfigurera och fasa distribution** - Göra ändringar i konfigurerbara inställningar Microsoft Hanterat skrivbord administrationsportalen. Fasa in ändringarna så att de är redo att distribueras. Kom ihåg att berätta för användarna om ändringarna och hur ändringarna påverkar deras enhetsupplevelse.   

Du konfigurerar och fasändringar i Microsoft Hanterat skrivbord administrationsportalen. Mer information finns i [Anpassa konfigurerbara inställningar.](config-setting-ref.md) 

**Steg 3 - Kommunicera ändringar** Informera användarna om kommande ändringar. För varje distribution slutför du kommunikationen som ingår i dina ändringshanteringsprocesser. Du bör tydligt informera om alla ändringar som påverkar hur en användare fungerar eller vad de ser på sina enheter.

**Steg 4 – Distribuera ändringar** – Distribuera dina ändringar med början i testgruppen. Med testgruppen kan du verifiera och felsöka problem i en grupp med färre enheter innan du distribuerar ändringar till större grupper av enheter. Om du får problem kan du återställa ändringen, uppdatera inställningen och fasa in en ny distribution. Microsoft Hanterat skrivbord rekommenderar att du följer den strukturerade metoden och distribuerar till grupper i följande ordning: Testa, först, snabbt och sedan bred.   

Alla konfigurerbara inställningar hanteras via Microsoft Hanterat skrivbord administrationsportalen. Mer information finns i [Distribuera ändringar.](config-setting-deploy.md) 

**Steg 5 – Spåra ändringar** – Spåra förloppet för dina ändringar i Distributionsstatus. För varje inställning kan du:
- **Spåra förloppet** – Spåra status när du har distribuerat ändringen. Statusen ändras till **Pågår och** sedan antingen **Slutförd** eller **Misslyckades.** Om en distribution misslyckas öppnas automatiskt en supportbegäran Microsoft Hanterat skrivbord för att undersöka problemet.  
- **Se version distribuerad** – Varje distribuerad ändring har ett versionsnummer.
- **Återställ ändringar** – Om du återställer en ändring stoppas den aktuella distributionen och alla grupper återställs till de senaste ändringarna som har distribuerats till alla grupper. Du rullar tillbaka till det senast kända värdet.
- **Verifiera ändringar** – kontrollera att ändringarna har tillämpats som förväntat när distributionen är klar.  

Om en distribution har misslyckats, eller om du inte kan återställa en ändring, [öppnar du en supportbegäran](admin-support.md) Microsoft Hanterat skrivbord Åtgärder. 

Mer information finns i [Distribuera och spåra konfigurerbara inställningar.](config-setting-deploy.md)

## <a name="additional-resources"></a>Ytterligare resurser
- [Referens för inställningar som kan konfigureras](config-setting-ref.md) 
- [Distribuera inställningar som kan konfigureras](config-setting-deploy.md) 
