---
title: Hantera hur användare kommer åt Office-dokument på mobila enheter
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Läs mer om skyddsprinciper som gör att du kan hantera hur användare får åtkomst till Office-program och arbetsfiler från mobila enheter.
ms.openlocfilehash: a48aa241c9e70cf087da3f1701e859dae7238024
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578396"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a>Hantera hur användare kommer åt Office-dokument på mobila enheter

Den här artikeln gäller Microsoft 365 Business Premium.

Principinställningar som styr hur användare får åtkomst till Office-filer från sina mobila enheter är **Av** som standard. Vi rekommenderar att du godkänner standardvärdena vid installationen för att skapa programprinciper för alla användare i Android, iOS och Windows 10. Du kan skapa fler principer när installationen har slutförts. 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Inställningar som styr hur användare kommer åt Office-filer på mobila enheter

Följande inställningar är tillgängliga för att bestämma hur användare kan komma åt Office arbetsfiler:
  
|||
|:-----|:-----|
|Inställning  <br/> |Beskrivning  <br/> |
|Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program  <br/> |Om den här inställningen **är På** måste användare utöver användarnamn och lösenord, tillhandahålla annan autentisering innan de kan använda Office-apparna på sina mobila enheter.  <br/> |
|Återställ PIN-kod när inloggningen misslyckas så här många gånger  <br/> |Om du vill förhindra att obehöriga användare slumpmässigt gissar en PIN-kod. PIN-koden återställs efter det antal felaktiga försök som du anger.  <br/> |
|Kräv att användare loggar in igen efter att Office-appar har varit inaktiva  <br/> |Den här inställningen bestämmer hur länge en användare kan vara inaktiv innan de uppmanas att logga in igen.  <br/> |
|Neka åtkomst till arbetsfiler på jailbroken eller rotade enheter  <br/> |Smarta användarna kanske har en jailbroken eller rotad enhet. Det innebär att användaren kan ändra operativsystemet, vilket kan göra enheten mer känslig för skadlig programvara. De här enheterna är blockerade när den här inställningen är **På**.  <br/> |
|Tillåt inte användare att kopiera innehåll från Office-program till personliga program  <br/> |När inställningen är **På** kan användaren inte kopiera information i en arbetsfil till en personlig fil. Om inställningen är **Av** kan användaren kopiera information från en arbetsfil till ett privat program eller personligt konto.  <br/> |
   

