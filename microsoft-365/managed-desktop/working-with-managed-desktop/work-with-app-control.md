---
title: Arbeta med appens kontroll
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
ms.openlocfilehash: 0b76a14a30caeb75cfdcb8acc5715fe6710e0625
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289465"
---
# <a name="work-with-app-control"></a>Arbeta med appens kontroll

När app-kontrollen har distribuerats i din miljö har både du och Microsoft hanterade Skriv bords operationer kontinuerlig ansvar. Du kanske till exempel vill lägga till en ny app i miljön eller lägga till (eller ta bort) en betrodd undertecknare. För att förbättra säkerheten bör alla appar vara kodade innan de släpps till användarna. Ett programs publicerings information innehåller information om undertecknaren.


## <a name="add-a-new-app"></a>Lägga till ett nytt program

Följ de här stegen om du vill lägga till ett nytt program:

1. Lägg till programmet i [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).
2. Distribuera appen till valfri enhet i test ringen. 
3. Testa programmet enligt dina vanliga affärs processer. 
4. Kontrol lera logg boken under **program-och Logs\Microsoft\Windows\AppLocker**, och leta efter eventuella **8003** -eller **8006** -händelser. De här händelserna indikerar att programmet blockerades. Mer information om alla program lås händelser och deras betydelser finns i [använda logg boken med AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).
5. Om du hittar några av de här händelserna kan du öppna en undertecknare med Microsoft Managed Station ära datorer.

## <a name="add-or-remove-a-trusted-signer"></a>Lägga till (eller ta bort) en betrodd undertecknare

När du öppnar en undertecknare måste du ange viktig information om utgivaren först. Gör sedan följande:

1. [Samla in information om utgivaren](#gather-publisher-details).
2. Öppna en biljett med Microsoft Managed Station ära datorer för att begära undertecknarens regel och ange följande information:  
    - Program namn 
    - Program version 
    - Beskrivning 
    - Ändra typ ("Lägg till" eller "ta bort")  
    - Information om utgivaren (till exempel: "O = <publisher name> , L = <location> , S = State, C = Country") 

> [!NOTE]
> Om du vill ta bort förtroendet för ett program följer du samma steg, men ange **ändra typ** för att *ta bort*.

Operationer distribuerar automatiskt principer till distributions grupper enligt det här schemat:


|Distributions grupp  |Typ av princip  |Avseende  |
|---------|---------|---------|
|Tävlingar     |  Revisions       |  Dag 0       |
|Skapas     | Tvingande        | Dag 1        |
|Snabbspola     | Tvingande        |  Dag 2       |
|Personer     | Tvingande        |  Dag 3       |


Du kan pausa eller återställa distributionen när som helst under installationen. Det gör du genom att öppna en annan tjänstbegäran med operationer.

> [!NOTE]
> Om du pausar utgivningen av en signerings regel måste den regeln antingen ångras eller slutföras innan en ny installation kan startas.

## <a name="gather-publisher-details"></a>Samla in information om utgivare

Följ de här stegen om du vill få åtkomst till Publisher-data för en app:

1. Hitta en Microsoft-hanterad stationär enhet i test ringen som har en policy för gransknings läge installerad. 
2. Försök att installera appen på enheten.
3. Öppna logg boken på enheten. 
4. I logg boken navigerar du till **program-och Logs\Microsoft\Windows**och väljer sedan **AppLocker**. 
5. Hitta en **8003** -eller **8006** -händelse och kopiera sedan information från händelsen: 
    - Program namn 
    - Program version 
    - Beskrivning 
    - Information om utgivaren (till exempel: "O = <publisher name> , L = <location> , S = State, C = Country") 
