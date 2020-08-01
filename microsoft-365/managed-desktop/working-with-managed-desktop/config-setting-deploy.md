---
title: Distribuera konfigurerbara inställningar i Microsoft Managed Desktop
description: Distribuera och spåra konfigurerbara inställningsändringar i Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation, distribution, mellanlagd distribution, konfigurerbara inställningar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b731422e6d981b12ea576ed26b841e7c679266ae
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530265"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Distribuera och spåra konfigurerbara inställningar – Microsoft Managed Desktop

När du har gjort ändringar i inställningskategorierna och arrangera en distribution kan du på sidan Distributionsstatus börja distribuera dina inställningar till grupper. På den här sidan visas en sammanfattning av varje konfigurerbar inställning. Genom att öppna en inställningskategori kan du distribuera inställningar till grupper och spåra förloppet för dessa distributioner.

## <a name="deployment-statuses"></a>Distributionsstatus 

Det här är de statusar som visas för varje distribution.

Status  | Förklaring 
--- | --- 
Distribuera | Ändringen väntar på att distribueras till den här gruppen.
Pågår | Ändringen tillämpas på aktiva enheter i den här gruppen. 
Komplett | Ändringen slutfördes på alla aktiva enheter i den här gruppen. 
Misslyckades | Ändringen misslyckades på en 10 procent av aktiva enheter i gruppen, så distributionen stoppades.<br><br> En supportbegäran öppnas automatiskt med Microsoft Managed Desktop-åtgärder för att felsöka distributionen. 
Återgick | Ändringen återställdes till den senaste ändringen som har distribuerats till alla distributionsgrupper.

## <a name="deploy-changes"></a>Distribuera ändringar

Vi visar skrivbordsbakgrundsbild i de här instruktionerna. När du har iscensatt en distribution distribuerar du ändringar från statussidan för distribution. 

**Så här distribuerar du ändringar**

1. Logga in på [Microsofts administratörsportal för hanterade skrivbord](https://aka.ms/mwaasportal)
2. Under **Inställningar**väljer du **Konfigurera .**
3. I **distributionsstatusarbetsytan** väljer du den inställning som du vill distribuera och väljer sedan den stegvisa distributionen som ska distribueras.
4. Välj **Distribuera om** du vill distribuera ändringen till en av distributionsgrupperna.

> [!NOTE] 
> Den orangea varningsikonen anger att det finns en tidigare grupp tillgänglig för distribution eftersom det rekommenderas att distribueras i ordning. 

![Arbetsyta för distributionsstatus. Fönstret Betrodda platser till höger. I avsnittet Distributionsgrupper finns tre kolumner: distributionsgrupper, enheter och status. I statuskolumnen markeras "deploy".](../../media/1deployedit.png)
Vi rekommenderar distribution till distributionsgrupper i den här ordningen: Testa, Först, Snabbt och sedan Brett. 

När ändringarna är slutförd i varje grupp ändras statusen till **Slutför**.

![Arbetsyta för distributionsstatus med kolumner för datumupptror, version, test, först, snabbt och brett. Proxy-raden expanderas och visar en daterad inställning som flaggats som "fullständig" i var och en av de fyra distributionsgrupperna.](../../media/2completeedit.png)

## <a name="revert-deployment"></a>Återställa distributionen

När du har distribuerat en ändring kan du återgå från **distributionsstatus**. När du återställer en ändring som **pågår** eller **Slutför**stoppas den aktuella distributionen. Inställningen återgår till den senaste versionen som distribuerades till alla grupper. 

Vi visar stegen för att återställa en ändring med bakgrundsbilden Skrivbord som ett exempel. 

**Så här återställer du en ändring**
1. Logga in på [Microsofts administratörsportal för hanterade skrivbord](https://aka.ms/mwaasportal)
2. Under **Inställningar**väljer du **Konfigurera .**
3. I **distributionsstatusarbetsytan** väljer du den inställning som du vill återställa och väljer sedan den stegvisa distributionen för att återgå.
4. Välj Återställ **distributionen**under **Behöver du återställa den här ändringen?**

![Arbetsyta för distributionsstatus. Startsidorna i webbläsaren väljs och öppnar en ruta till höger med data om den inskickade ändringen och dess status. Längst ned finns området "Måste återställa den här ändringen" där du kan välja "Återställ distributionen".](../../media/3revert.png) 

## <a name="additional-resources"></a>Ytterligare resurser
- [Översikt över konfigurerbara inställningar](config-setting-overview.md)
- [Referens för inställningar som kan konfigureras](config-setting-ref.md) 
