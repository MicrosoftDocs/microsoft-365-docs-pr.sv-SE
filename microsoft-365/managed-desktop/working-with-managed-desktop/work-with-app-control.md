---
title: Arbeta med appens kontroll
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 31cc897fe28f557a65cba9c99e5dcecbf7c2b0e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917646"
---
# <a name="work-with-app-control"></a>Arbeta med appens kontroll

När appkontrollen har distribuerats i din miljö har både du och Microsoft Managed Desktop Operations ett pågående ansvar. Du kanske till exempel vill lägga till en ny app i miljön eller lägga till (eller ta bort) en betrodd undertecknare. För att förbättra säkerheten bör alla appar vara kod signerade innan du släpper dem till användarna. Utgivarens information innehåller information om undertecknaren.


## <a name="add-a-new-app"></a>Lägga till ett nytt program

Följ de här anvisningarna om du vill lägga till en ny app:

1. Lägg till appen i [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).
2. Distribuera programmet till valfri enhet i testringen. 
3. Testa programmet enligt dina vanliga affärsprocesser. 
4. Kontrollera Loggboken under **Application and Services Logs\Microsoft\Windows\AppLocker**, letar efter **eventuella 8003-** eller **8006-händelser.** Dessa händelser anger att appen blockeras. Mer information om alla applåsningshändelser och deras innebörd finns i [Använda loggboken med AppLocker.](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)
5. Om du hittar något av dessa händelser öppnar du en begäran om undertecknare med Microsoft Managed Desktop Operations.

## <a name="add-or-remove-a-trusted-signer"></a>Lägga till (eller ta bort) en betrodd undertecknare

När du öppnar en begäran om undertecknaren måste du ange viktig information för utgivaren först. Följ sedan de här anvisningarna:

1. [Samla information om utgivare](#gather-publisher-details).
2. Öppna en biljett med Microsoft Managed Desktop Operations för att begära signeringsregeln och ange följande information:  
    - Programnamn 
    - Programversion 
    - Beskrivning 
    - Ändra typ ("lägg till" eller "ta bort")  
    - Information om Publisher (till exempel: "O= <publisher name> ,L= <location> ,S=State,C=Country") 

> [!NOTE]
> Följ samma steg om du vill ta bort förtroende för en app, men ange ändra **typ för att** ta *bort*.

Åtgärder distribuerar gradvis principer till distributionsgrupper som följer det här schemat:


|Distributions grupp  |Typ av princip  |Tidsinställning  |
|---------|---------|---------|
|Test     |  Granskning       |  Dag 0       |
|Första     | Enforced        | Dag 1        |
|Snabbt     | Enforced        |  Dag 2       |
|Bred     | Enforced        |  Dag 3       |


Du kan pausa eller återställa distributionen när som helst under distributionen. Det gör du genom att öppna en annan tjänstförfrågan med Drift.

> [!NOTE]
> Om du pausar lanseringen av en signeringsregel måste regeln antingen återställas eller slutföras innan en annan utrullning kan starta.

## <a name="gather-publisher-details"></a>Samla information om utgivaren

Gör så här för att få tillgång till publisher-data för ett program:

1. Hitta en Microsoft Managed Desktop-enhet i testringen som har en princip för granskningsläge. 
2. Försök att installera appen på enheten.
3. Öppna Loggboken på enheten. 
4. Gå till Application and **Services Logs\Microsoft\Windows** i Loggboken och välj sedan **AppLocker.** 
5. Hitta en **8003-** eller **8006-händelse** och kopiera sedan information från händelsen: 
    - Programnamn 
    - Programversion 
    - Beskrivning 
    - Information om utgivaren (till exempel: "O= <publisher name> , L= <location> , S=State, C=Country")