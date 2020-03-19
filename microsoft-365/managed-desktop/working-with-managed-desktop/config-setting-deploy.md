---
title: Distribuera konfigurerbara inställningar på Microsoft Managed Desktop
description: Distribuera och spåra konfigurerbara inställningar i Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation, distribuera, iscensatt distribution, konfigurerbara inställningar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: e6946c138cb6fde15e35374b447038d5c302187e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806450"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Distribuera och spåra konfigurerbara inställningar – Microsoft Managed Desktop

När du har gjort ändringar i inställningskategorierna och arrangerat en distribution kan du med sidan Distributionsstatus börja distribuera inställningarna till grupper. På den här sidan visas en sammanfattning av varje konfigurerbar inställning. Genom att öppna en inställningskategori kan du distribuera inställningar till grupper och spåra förloppet för dessa distributioner.

## <a name="deployment-statuses"></a>Distributionsstatus 

Det här är statusarna som visas för varje distribution.

Status  | Förklaring 
--- | --- 
Distribuera | Ändringen väntar på att distribueras till den här gruppen.
Pågående | Ändringen tillämpas på aktiva enheter i den här gruppen. 
Komplett | Ändringen slutfördes på alla aktiva enheter i den här gruppen. 
Misslyckades | Ändringen misslyckades på 10 procent av aktiva enheter i gruppen, så distributionen stoppades.<br><br> En supportbegäran öppnas automatiskt med Microsoft Managed Desktop-åtgärder för att felsöka distributionen. 
Återgick | Ändringen återgick till den senaste ändringen som har distribuerats till alla distributionsgrupper.

## <a name="deploy-changes"></a>Distribuera ändringar

Vi visar skrivbordsbakgrundsbild i dessa instruktioner. När du har genomfört en distribution distribuerar du ändringar från sidan Distributionsstatus. 

**Så här distribuerar du ändringar**

1. Logga in på [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)
2. Under **Inställningar**väljer du **Konfigurerbar**.
3. I **arbetsytan distributionsstatus** väljer du den inställning som du vill distribuera och väljer sedan den stegvisa distributionsom ska distribueras.
4. Välj **Distribuera** om du vill distribuera ändringen till en av distributionsgrupperna.

> [!NOTE] 
> Ikonen för orange varning anger att det finns en tidigare grupp tillgänglig för distribution eftersom det rekommenderas att distribueras i ordning. 

![Arbetsyta för distributionsstatus. Fönstret Betrodda platser till höger. I avsnittet Distributionsgrupper finns tre kolumner: distributionsgrupper, enheter och status. I statuskolumnen markeras "distribution".](../../media/1deployedit.png)
Vi rekommenderar att du distribuerar till distributionsgrupper i den här ordningen: Testa, Först, Snabb och sedan Bred. 

När ändringarna är slutförda i varje grupp ändras statusen till **Slutförd**.

![Arbetsyta för distributionsstatus med kolumner för datumuppdaterade, version, test, först, snabb och bred. Raden Proxy expanderas och visar en daterad inställning som flaggas som "fullständig" i var och en av de fyra distributionsgrupperna.](../../media/2completeedit.png)

## <a name="revert-deployment"></a>Återställ distributionen

När du har distribuerat en ändring kan du återgå från **distributionsstatus**. När du återställer en ändring som **pågår** eller **är slutförd**stoppas den aktuella distributionen. Inställningen återgår till den senaste versionen som distribuerades till alla grupper. 

Vi visar stegen för att återställa en ändring med bakgrundsbilden Skrivbord som exempel. 

**Så här återställer du en ändring**
1. Logga in på [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)
2. Under **Inställningar**väljer du **Konfigurerbar**.
3. I **arbetsytan distributionsstatus** väljer du den inställning du vill återställa och väljer sedan den stegvisa distributionen som ska återställas.
4. Under **Behöver du återställa den här ändringen?** väljer du Återställ **distribution**.

![Arbetsyta för distributionsstatus. Startsidorna för webbläsaren är markerat och öppnar en ruta till höger med data om den inskickade ändringen och dess status. Längst ner finns området "need to revert this change" där du kan välja "Återställ distribution".](../../media/3revert.png) 

## <a name="additional-resources"></a>Ytterligare resurser
- [Översikt över konfigurerbara inställningar](config-setting-overview.md)
- [Referens för konfigurerbara inställningar](config-setting-ref.md) 
