---
title: Hantera hur användare kommer åt Office-dokument på mobila enheter
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4OfficeMobile
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Lär dig mer om skyddsprinciper som gör att du kan hantera hur användare får åtkomst till Office-appar och arbetar filer från mobila enheter.
ms.openlocfilehash: f613e518c3607010cae55443456be9d3ddc3d689
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403087"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a>Hantera hur användare kommer åt Office-dokument på mobila enheter

 Principinställningar som styr hur användare får åtkomst till Office-filer från sina mobila enheter är **Av** som standard. Vi rekommenderar att du accepterar standardvärdena under installationen för att skapa programprinciper för Android, iOS och Windows 10 som gäller för alla användare. Du kan skapa fler principer när installationen har slutförts. 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Inställningar som styr hur användare kommer åt Office-filer på mobila enheter

Följande inställningar är tillgängliga för att bestämma hur användare kan komma åt Office arbetsfiler:
  
|||
|:-----|:-----|
|Inställning  <br/> |Beskrivning  <br/> |
|Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program  <br/> |Om den här inställningen är **På**måste användarna ange en annan form av autentisering, utöver sitt användarnamn och lösenord, innan de kan använda Office-appar på sin mobila enhet.  <br/> |
|Återställ PIN-kod när inloggningen misslyckas så här många gånger  <br/> |Om du vill förhindra att obehöriga användare slumpmässigt gissar en PIN-kod. PIN-koden återställs efter det antal felaktiga försök som du anger.  <br/> |
|Kräv att användare loggar in igen efter att Office-appar har varit inaktiva  <br/> |Den här inställningen avgör hur länge en användare kan vara inaktiv innan han eller hon uppmanas att logga in igen.  <br/> |
|Neka åtkomst till arbetsfiler på jailbroken eller rotade enheter  <br/> |Smarta användarna kanske har en jailbroken eller rotad enhet. Detta innebär att användaren kan ändra operativsystemet, vilket kan göra enheten mer mottaglig för skadlig kod. De här enheterna är blockerade när den här inställningen är **På**.  <br/> |
|Tillåt inte att användare kopierar innehåll från Office-appar till personliga appar  <br/> |När inställningen är **På**kan användaren inte kopiera information i en arbetsfil till en personlig fil. Om inställningen är **Av**kan användaren kopiera information från en arbetsfil till en personlig app eller ett personligt konto.  <br/> |
   

