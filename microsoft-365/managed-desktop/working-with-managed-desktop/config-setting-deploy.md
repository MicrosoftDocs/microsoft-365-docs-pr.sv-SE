---
title: Distribuera konfigurerbara inställningar på Microsoft Managed Desktop
description: Distribuera och spåra ändringar som kan konfigureras i Microsoft hanterat skriv bord.
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation, distribution, stegvis distribution, konfigurerbara inställningar
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
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Distribuera och spåra konfigurerbara inställningar – Microsoft Managed Desktop

När du har gjort ändringar i inställnings kategorierna och scen en distribution kan du använda sidan för distributions status för att börja distribuera dina inställningar till grupper. På den här sidan visas en sammanfattning av varje konfigurerbar inställning. Genom att öppna en inställnings kategori kan du distribuera inställningar till grupper och spåra förloppet för dessa distributioner.

## <a name="deployment-statuses"></a>Distributions status 

Dessa status värden visas för varje distribution.

Status  | Förklaring 
--- | --- 
Distribuera | Din ändring väntar på att distribueras till den här gruppen.
Pågår | Ändringen tillämpas på aktiva enheter i den här gruppen. 
Kunna | Ändringen slutförd på alla aktiva enheter i den här gruppen. 
Misslyckades | Ändringen misslyckades på 10 procent av aktiva enheter i gruppen, så distributionen stoppades.<br><br> En supportbegäran öppnas automatiskt med Microsoft hanterade Skriv bords åtgärder för att felsöka distributionen. 
Återställt | Ändringen återfördes till den senaste ändringen som lyckades distribueras till alla distributions grupper.

## <a name="deploy-changes"></a>Distribuera ändringar

Vi kommer att Visa Skriv bords bakgrund i dessa instruktioner. När du har mellanlagrat en distribution distribueras ändringarna från sidan distributions status. 

**Distribuera ändringar**

1. Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till menyn **enheter**
2. Leta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.
3. I arbets ytan **distributions status** väljer du den inställning du vill distribuera och väljer sedan den stegvisa distribution som ska distribueras.
4. Välj **distribuera** för att distribuera ändringen till en av distributions grupperna.

> [!NOTE] 
> Varnings ikonen för Orange visar att en tidigare grupp är tillgänglig för distribution eftersom den är rekommenderad för att bli uppkopplad. 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

Vi rekommenderar att du distribuerar till distributions grupper i den här ordningen: testa, första, snabba och sedan breda. 

När ändringar är slutförda i varje grupp ändras statusen till **slutförd**.

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a>Återställ distribution

När du har distribuerat en ändring kan du återgå från **distributions status**. När du återställer en ändring som **pågår** eller **slutförs**stoppar den aktuella distributionen. Inställningen återställs till den senaste versionen som distribueras till alla grupper. 

Vi visar stegen för att återställa en ändring med hjälp av Skriv bords bakgrunds bilden som ett exempel. 

**Så här återställer du en ändring**
1. Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till menyn **enheter**
2. Leta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.
3. I arbets ytan **distributions status** väljer du den inställning som du vill återställa och väljer sedan den stegvisa distribution som du vill återställa.
4. Under **behöver du återställa den här ändringen?** väljer du **Återställ distribution**.

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a>Ytterligare resurser
- [Inställningar för konfigurerings bara översikt](config-setting-overview.md)
- [Referens för inställningar som kan konfigureras](config-setting-ref.md) 
