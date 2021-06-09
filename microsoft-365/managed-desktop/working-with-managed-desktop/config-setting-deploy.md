---
title: Distribuera konfigurerbara inställningar i Microsoft Hanterat skrivbord
description: Distribuera och spåra konfigurerbara inställningsändringar i Microsoft Hanterat skrivbord.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation, distribuera, fasad distribution, konfigurerbara inställningar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a24d0dc64e2262a8b208119c45a4a6bade701c10
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104540"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Distribuera och spåra konfigurerbara inställningar – Microsoft Hanterat skrivbord

När du har gjort ändringar i inställningskategorierna och fasa in en distribution kan du på sidan Distributionsstatus börja distribuera inställningarna till grupper. På den här sidan visas en sammanfattning av varje konfigurerbar inställning. Genom att öppna en inställningskategori kan du distribuera inställningar till grupper och spåra förloppet för distributionerna.

## <a name="deployment-statuses"></a>Distributionsstatus 

Det här är de statusar som visas för varje distribution.

Status  | Förklaring 
--- | --- 
Distribuera | Ändringen väntar på att distribueras till den här gruppen.
Pågående | Ändringen tillämpas på aktiva enheter i den här gruppen. 
Slutfört | Ändringen slutfördes på alla aktiva enheter i den här gruppen. 
Misslyckades | Ändringen misslyckades på 10 procent av alla aktiva enheter i gruppen, så distributionen stoppades.<br><br> En supportbegäran öppnas automatiskt med Microsoft Hanterat skrivbord för att felsöka distributionen. 
Återställd | Ändringen återställdes till den senaste ändringen som distribuerades till alla distributionsgrupper.

## <a name="deploy-changes"></a>Distribuera ändringar

Vi kommer att visa bakgrundsbilden för skrivbordet i de här instruktionerna. När du har gjort en distribution distribuerar du ändringar från sidan Distributionsstatus. 

**Distribuera ändringar**

1. Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till **menyn** Enheter
2. Titta efter avsnittet Microsoft Hanterat skrivbord, välj **Inställningar**.
3. Välj **den inställning** du vill distribuera i arbetsytan Distributionsstatus och välj sedan den distribution som ska distribueras.
4. Välj **Distribuera** för att distribuera ändringen till någon av distributionsgrupperna.

> [!NOTE] 
> Den orange varningsikonen visar att det finns en tidigare grupp tillgänglig för distribution eftersom vi rekommenderar att distribuera den i ordning. 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

Vi rekommenderar att du distribuerar till distributionsgrupper i följande ordning: Testa först, snabbt och sedan bred. 

När ändringarna är slutförda i varje grupp ändras statusen till **Slutförd.**

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a>Återställ distribution

När du har distribuerat en ändring kan du återgå till **Distributionsstatus.** När du återställer en ändring som **pågår eller** **Slutförd upphör** den aktuella distributionen. Inställningen återgår till den senaste versionen som distribuerades till alla grupper. 

Vi kommer att visa stegen för att återställa en ändring med hjälp av skrivbordsbakgrundsbilden som exempel. 

**Om du vill återställa en ändring**
1. Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till **menyn** Enheter
2. Titta efter avsnittet Microsoft Hanterat skrivbord, välj **Inställningar**.
3. Välj **den inställning** du vill återställa i arbetsytan Distributionsstatus och välj sedan den stegade distributionen för att återställa.
4. Under **Behöver du återställa den här ändringen?** väljer du Återställ **distribution.**

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a>Ytterligare resurser
- [Översikt över konfigurerbara inställningar](config-setting-overview.md)
- [Referens för inställningar som kan konfigureras](config-setting-ref.md) 
