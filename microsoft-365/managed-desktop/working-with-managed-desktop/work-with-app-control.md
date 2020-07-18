---
title: Arbeta med appkontroll
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 74cd1ec93058ed733e7d79da2d6932f04acfa5da
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170742"
---
# <a name="work-with-app-control"></a>Arbeta med appkontroll

När appkontrollen har distribuerats i din miljö har både du och Microsoft Managed Desktop Operations kontinuerligt ansvar. Du kanske till exempel vill lägga till en ny app i miljön eller lägga till (eller ta bort) en betrodd undertecknare. För att förbättra säkerheten bör alla appar vara kodsignerade innan du släpper dem till slutanvändare. En apps utgivarinformation innehåller information om undertecknaren.


## <a name="add-a-new-app"></a>Lägga till en ny app

Så här lägger du till en ny app:

1. Lägg till appen [i Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).
2. Distribuera appen till valfri enhet i testringen. 
3. Testa din app enligt dina vanliga affärsprocesser. 
4. Kontrollera Loggboken under **Program- och tjänstloggar\Microsoft\Windows\AppLocker**och leta efter eventuella **8003-** eller **8006-händelser.** Dessa händelser indikerar att appen skulle blockeras. Mer information om alla App Locker-händelser och deras betydelser finns i [Använda Loggboken med AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).
5. Om du hittar någon av dessa händelser öppnar du en undertecknarbegäran med Microsoft Managed Desktop Operations.

## <a name="add-or-remove-a-trusted-signer"></a>Lägga till (eller ta bort) en betrodd undertecknare

När du öppnar en undertecknarbegäran måste du ange viktig information om utgivaren först. Följ sedan dessa steg:

1. [Samla in information om utgivare](#gather-publisher-details).
2. Öppna en biljett med Microsoft Managed Desktop Operations för att begära undertecknarregeln och inkludera följande information:  
    - Programnamn 
    - Programversion 
    - Beskrivning 
    - Ändra typ ("lägg till" eller "ta bort")  
    - Information om utgivare (till exempel : "O= <publisher name> ,L= <location> ,S=State,C=Country") 

> [!NOTE]
> Om du vill ta bort förtroendet för en app följer du samma steg, men anger **Ändra typ** för att *ta bort*.

Åtgärder distribuerar progressivt principer till distributionsgrupper enligt det här schemat:


|Distributionsgrupp  |Typ av princip  |Timing  |
|---------|---------|---------|
|Test     |  Revision       |  Dag 0       |
|Första     | Verkställas        | Dag 1        |
|Snabb     | Verkställas        |  Dag 3       |
|Bred     | Verkställas        |  Dag 7       |


Du kan pausa eller återställa distributionen när som helst under distributionen. Det gör du genom att öppna en annan tjänstbegäran med åtgärder.

> [!NOTE]
> Om du pausar frisättningen av en undertecknarregel måste den regeln antingen återställas eller slutföras innan en annan distribution kan starta.

## <a name="gather-publisher-details"></a>Samla in information om utgivare

Så här kommer du åt utgivardata för en app:

1. Hitta en Microsoft-hanterad skrivbordsenhet i testringen som har en princip för granskningsläge tillämpad. 
2. Försök att installera appen på enheten.
3. Öppna Loggboken på den enheten. 
4. I Loggboken navigerar du till **program- och tjänstloggar\Microsoft\Windows**och väljer sedan **AppLocker**. 
5. Hitta en händelse på **8003** eller **8006** och kopiera sedan information från evenemanget: 
    - Programnamn 
    - Programversion 
    - Beskrivning 
    - Information om utgivare (till exempel: "O= <publisher name> , L= <location> , S=State, C=Country") 