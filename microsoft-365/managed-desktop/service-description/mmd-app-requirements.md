---
title: Appkrav för Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 01c580cd671a84ef68c18b114e133f046a3e5b3b
ms.sourcegitcommit: 7930fb8327bbd3594fde52f2dbf91e0f5d92f684
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "42811812"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Appkrav för Microsoft Managed Desktop

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
För att garantera prestanda, tillförlitlighet och serviceför tjänster får en kunds bransch inte allvarligt påverka slutanvändarens upplevelse eller ändra säkerhetsinriktningen. Därför måste affärsprogram som du vill distribuera till Microsoft Managed Desktop-enheter uppfylla kraven i det här avsnittet.

## <a name="application-condition"></a>Ansökan villkor

Det är viktigt att program inte påverkar Microsoft Managed Desktop negativt. Följande är de krav som ett program måste uppfylla för att ett program ska distribueras. För ett visst program eller en viss drivrutin får Microsoft avstå från alla krav som anges häri. Microsoft kan besluta att ta bort alla program eller drivrutiner som påverkar prestanda och tillförlitlighet på Microsoft Managed Desktop-enheter negativt.

## <a name="centrally-managed-apps"></a>Centralt hanterade appar

Alla program och drivrutiner som är installerade på Microsoft Managed Devices måste distribueras via Microsoft Intune, Microsoft Store eller Microsoft Store for Business. Om det är tillgängligt distribueras även drivrutiner via Windows Update-tjänsten. 

## <a name="prohibited-app-classes"></a>Förbjudna appklasser

Vissa programtyper är inte tillåtna på Microsoft Managed Desktop-enheter:
- Tredjepartsantivirusprogram, säkerhets- eller granskningsprogram för tredje part
- Versioner av Microsoft Office före Office 365 ProPlus
- Program som installerar eller paketerar annan programvara från tredje part

## <a name="restricted-app-behaviors"></a>Begränsade appbeteenden

Vissa appbeteenden kan påverka användarupplevelsen negativt eller utgöra en säkerhetsrisk för Microsoft Managed Desktop-enheter. Appar med följande beteenden får inte köras i Microsoft Managed Desktop-miljön utan en specifik från Microsoft.

Användarupplevelse:
- Installera bakgrundstjänster
- Lägga till sig själv i startsökvägen för Windows
- Program som är beroende av drivrutiner
- Webbläsare i tredje part

Säkerhet:
- Höj slutanvändarens privilegier
- Fungera som en appbutik eller ha en inbyggd förlängningshanterare
- Ha kända säkerhetsproblem
- Kryptera eller begränsa åtkomsten till slutanvändardata
- Är osignerad eller signerad med ett certifikat som inte summeras till en betrodd rot


## <a name="driver-deployment"></a>Drivrutinsdistribution

Microsoft Managed Desktop stöder endast drivrutiner som är tillgängliga via Windows Update eller installeras inkorg med Microsoft Managed Device. 

Om ett program kräver att en viss drivrutin/ett eller de körs betraktas det som ett begränsat program och kräver ett undantag innan det distribueras till Microsoft Managed Desktop. 

