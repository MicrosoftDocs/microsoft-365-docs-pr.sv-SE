---
title: Konfigurerbara inställningar för Microsoft Managed Desktop
description: Information om konfigurerbara inställningar med Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation, inställningar, konfigurerings bara inställningar
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

Inställningar och principer för Microsoft Managed Desktop distribution som tillämpas på alla enheter som hanteras av Microsoft Managed Desktop. Mer information finns i [enhets konfiguration](../service-description/device-policies.md).

Konfigurerbara inställningar på Microsoft Managed Desktop ge IT-administratörer ett sätt att anpassa och distribuera inställningar som är unika för företagets organisation och företag. De här inställningarna gäller utöver konfigurations inställningar för enheter som hanteras av Microsoft Managed Desktop.  

Konfigurerbara inställnings ändringar görs i molnet och tillämpas på dina Microsoft Managed Station ära enheter i definierade distributions grupper. Den här processen liknar hur Microsoft Managed Desktop hanterar ändringar av enhets konfigurations inställningar och principer som definieras och hanteras av tjänsten. Genom att använda samma process som Microsoft Managed Desktop används för att distribuera ändringar, fortsätter du att flytta organisationen framåt med moderna IT-hanterings rutiner.

## <a name="when-to-use-configurable-settings"></a>När bör du använda konfigurerbara inställningar?

Det finns några gånger om du vill använda konfigurerbara inställningar. 

**Registrerings process** – Microsoft Managed Desktop rekommenderar att du anpassar konfigurerings bara inställningar när du är på Microsoft Managed Desktop-tjänsten, eller när du har ett stort antal enheter (20 eller mer). Inställning av kategorier konfigureras på Microsoft Managed Desktop admin-portalen. När du har varit inloggad och har åtkomst till administrations portalen kan du bestämma vilka kategorier du vill anpassa för din organisation genom att göra ändringarna, mellanlagra en distribution och sedan distribuera dina ändringar.

**Underhåll inställningar** – granska dina inställningar regelbundet och gör nödvändiga uppdateringar. Du kan behöva göra ändringar för att stödja en ändring i ditt företag.   

## <a name="setting-categories"></a>Ställa in kategorier

Det här är de konfigurerbara inställnings kategorierna som du kan anpassa:
- [Skriv bords bakgrund](config-setting-ref.md#desktop-background-picture) – anpassa Skriv bords bakgrunden för hanterade enheter med Microsoft. 
- [Webbläsarens start sidor](config-setting-ref.md#browser-start-pages) – Lägg till Start sidor som du kan använda med Microsoft Edge. Se webbläsarens start sida
- [Webbplats lista för företags läge](config-setting-ref.md#enterprise-mode-site-list-location) – Lägg till webbplatser och deras kompatibilitetsläge. Webbplatser i listan startas i Internet Explorer. 
- [Tillförlitliga webbplatser](config-setting-ref.md#trusted-sites) – Lägg till betrodda webbplatser och ange säkerhets zoner för varje webbplats. 
- [Webbplats undantag för proxy](config-setting-ref.md#proxy) – Ställ in ditt adress nummer och port nummer för proxyservern och Lägg till proxy-undantag.

Alla inställnings kategorier kan anpassas och distribueras till sina egna. Du kan distribuera ändringar av flera olika inställnings kategorier samtidigt, men du kan bara distribuera en ändring åt gången till en inställnings kategori.

Till exempel:
- Du kan distribuera ändringar av Skriv bords bild och tillförlitliga platser, var och en med sin egen distribution. 
- Du kan inte distribuera två installationer till webbläsarens start sidor samtidigt. Den senaste distributionen kommer att stoppa tidigare installationer som fortfarande pågår.

## <a name="configurable-setting-process"></a>Konfigurerbar inställnings process

Microsoft Managed Desktop rekommenderar att du följer en process som liknar följande när du använder konfigurerbara inställningar för din organisation:

**Steg 1 – planera** – Läs mer om konfigurerbara inställningar och bestäm vilka inställningar som ska konfigureras för din organisation. Skapa en tids linje som du förväntar dig att distribuera ändringar för varje grupp. Planera kommunikation för dina användare som uppfyller dina interna ändringar för ändrings hantering. Om du till exempel lägger till webb läsar start sidor kan användarna veta att de har en ny uppsättning start sidor i webbläsaren efter distributionen.  

**Steg 2 – Konfigurera och mellanlagra distribution** – gör ändringar i konfigurerbara inställningar på Microsoft Managed Desktop admin-portalen. Mellanlagra ändringarna så att de är redo att distribueras. Kom ihåg att informera användarna om ändringarna och hur de ändrar enhets upplevelsen.   

Du konfigurerar och fas ändringar i portalen för administration av administrativa skriv bord. Mer information finns i [Anpassa konfigurerbara inställningar](config-setting-ref.md). 

**Steg 3 – meddela ändringar** Förmedla information om kommande ändringar för användarna. För varje distribution slutför du kommunikationen som är en del av dina processer för ändrings hantering. Du bör tydligt meddela eventuella ändringar som påverkar hur en användare fungerar, eller vad de kan se på sina enheter.

**Steg 4 – distribuera** ändringar – distribuera dina ändringar från test gruppen. Test gruppen gör att du kan validera och felsöka problem i en grupp med färre enheter, innan du distribuerar ändringar till större grupper av enheter. Om du stöter på problem kan du återställa ändringen, uppdatera inställningen och mellanlagra en ny distribution. Microsoft Managed Desktop rekommenderar att du följer den strukturbaserade metoden och distribuerar till grupper i den här ordningen: testa, första, snabba och sedan breda.   

Alla konfigurerings bara inställningar hanteras via Microsoft Managed Desktop admin-portalen. Mer information finns i [distribuera ändringar](config-setting-deploy.md). 

**Steg 5 – spåra ändringar** – spåra förloppet för dina ändringar av distributions status. För varje inställning kan du:
- **Spåra** status – spåra statusen när du har distribuerat ändringen. Statusen ändras till **pågår** och sedan antingen **komplett** eller **misslyckad**. Om en distribution Miss lyckas öppnas en supportbegäran automatiskt för Microsoft Managed Desktop för att undersöka problemet.  
- **Se distribuerad version** – varje distribuerad ändring har ett versions nummer.
- **Återställer ändringar** -återställning av en ändring stoppar den aktuella distributionen och återställer alla grupper till de senaste ändringarna som distribuerats till alla grupper. Du återställer till det senast kända korrekta inställning svärdet.
- **Validera ändringar** -när distributionen är färdig bekräftar du att ändringarna har gjorts som förväntat.  

Om en distribution misslyckades, eller om du inte kan återgå, [öppnar du en supportbegäran](admin-support.md) med Microsoft Managed Station ära datorer. 

Mer information finns i [distribuera och spåra konfigurerbara inställningar](config-setting-deploy.md).

## <a name="additional-resources"></a>Ytterligare resurser
- [Referens för inställningar som kan konfigureras](config-setting-ref.md) 
- [Distribuera inställningar som kan konfigureras](config-setting-deploy.md) 
