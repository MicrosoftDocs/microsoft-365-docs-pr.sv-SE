---
title: Microsofts appkrav för hanterade skrivbord
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5889a4e80f44349b4f149ee4f2a631f12b32251e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637858"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Microsofts appkrav för hanterade skrivbord

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
För att garantera prestanda, tillförlitlighet och servicebarhet för Microsoft Managed Desktop-enheter får en kunds affärsappar inte allvarligt påverka slutanvändarens upplevelse eller ändra säkerhetsinställningen. Därför måste affärsprogram som du vill distribuera till Microsoft Managed Desktop-enheter uppfylla kraven i det här avsnittet.

## <a name="application-condition"></a>Villkor för program

Det är viktigt att program inte påverkar Microsoft Managed Desktop-miljön negativt. Följande är de krav som ett program måste uppfylla för att ett program ska kunna distribueras. För ett visst program eller en viss drivrutin kan Microsoft avstå från alla krav som anges häri. Microsoft kan besluta att ta bort alla program eller drivrutiner som påverkar prestanda och tillförlitlighet för Microsoft Hanterade stationära enheter negativt.

## <a name="centrally-managed-apps"></a>Centralt hanterade appar

Alla program och drivrutiner som är installerade på Microsoft Managed Devices måste distribueras via Microsoft Intune, Microsoft Store eller Microsoft Store för företag. Om det är tillgängligt kommer drivrutiner också att distribueras via Windows Update-tjänsten. 

## <a name="prohibited-app-classes"></a>Förbjudna appklasser

Vissa programtyper är inte tillåtna på Microsoft Managed Desktop-enheter:
- Antivirusprogram för tredje part, säkerhet eller granskning
- Versioner av Microsoft Office före Microsoft 365 Apps för företag
- Program som installerar eller buntar annan programvara från tredje part

## <a name="restricted-app-behaviors"></a>Begränsade appbeteenden

Vissa appbeteenden kan påverka användarupplevelsen negativt eller utgöra en säkerhetsrisk för Microsoft Managed Desktop-enheter. Appar med följande beteenden tillåts inte att köras i Microsoft Managed Desktop-miljön utan en specifik från Microsoft.

Användarupplevelse:
- Installera bakgrundstjänster
- Lägga till sig själv i startsökvägen för Windows
- Program som är beroende av drivrutiner
- Webbläsare från tredje part

Säkerhet:
- Höj slutanvändarens privilegier
- Agera som appbutik eller har en inbyggd tilläggshanterare
- Ha kända säkerhetsproblem
- Kryptera eller begränsa åtkomsten till slutanvändardata
- Är osignerad eller signerad med ett certifikat som inte summeras till en betrodd rot


## <a name="driver-deployment"></a>Drivrutinsdistribution

Microsoft Managed Desktop stöder endast drivrutiner som är tillgängliga via Windows Update eller installerad inkorg med Microsoft Managed Device. 

Om ett program kräver att en viss drivrutin körs betraktas det som ett begränsat program och kräver ett undantag innan det distribueras till Microsoft Managed Desktop. 

