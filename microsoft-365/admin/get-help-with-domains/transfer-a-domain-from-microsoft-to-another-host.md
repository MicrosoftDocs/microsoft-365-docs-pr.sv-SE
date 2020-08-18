---
title: Överföra en domän från Microsoft till en annan värd
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'Hitta stegen här för att överföra en domän från Microsoft till en annan registrator. '
ms.openlocfilehash: 7e00f5ae2c36a06803a3f7a8acd825dcab90805c
ms.sourcegitcommit: 6fb2a1c404ea3c3573b0f7803bf17459a9387891
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788993"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Överföra en domän från Microsoft till en annan värd

Du kan inte överföra en Microsoft 365-domän till en annan registrator för 60 dagar efter att du har köpt domänen från Microsoft.

> [!NOTE]
> En _whois_-   fråga visar en Microsoft-köpt domän registrator som vilda Västeuropa Domains LLC. Men endast Microsoft bör kontaktas angående din Microsoft 365-köpta domän.

Följ de här stegen för att få en kod på Microsoft 365 och gå sedan till den andra webbplatsen för domän registratorn för att konfigurera ditt domän namn till den nya registratorn.

## <a name="transfer-a-domain"></a>Överföra en domän

1. Gå till inställningar i administrations centret  **Settings**   >  **Domains**.

2. <på sidan **domäner** väljer du den Microsoft 365-domän som du vill överföra till en annan domän registrator och väljer sedan **kontrol lera hälsa**.

3. Högst upp på sidan väljer du **överför domän**.

4. På sidan **Välj var du vill överföra din domän** väljer du **en annan registrator**och klickar sedan på **Nästa**.

5. På sidan **Lås upp domän överföring** väljer ** _du_ > Lås upp överföring för <domänen**och väljer sedan **Nästa**.

6. Kontrol lera din domän överförings kontakt information och välj sedan **Nästa**.

7. Kopiera auktoriseringsregeln och vänta ungefär 30 minuter för din domän överförings status till **olåst för överföring** på fliken **registrering** innan du fortsätter med nästa steg.

8. Gå till webbplatsen för den domän registrator som du vill hantera ditt domän namn på. Följ anvisningarna för att överföra en domän (Sök efter hjälp på webbplatsen).

Fliken registrerings kod för **registrering** på sidan  **domäner** i Microsoft 365.

9. När överföringen är färdig förnyar du din domän hos den nya domän registratorn.

10. Slutför processen genom att gå tillbaka till sidan **domäner** i administrations centret och sedan välja  **fullständig domän överföring**.

> [!NOTE]
> Microsoft 365-köpta domäner är inte kvalificerat för namnserver ändringar eller överföring av domänen mellan Microsoft 365-organisationer. Om något av följande är obligatoriskt måste domän registreringen flyttas till en annan registrator.
