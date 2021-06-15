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
description: Läs mer om skyddsprinciper som gör att du kan hantera hur användare får åtkomst Office appar och arbetsfiler från mobila enheter.
ms.openlocfilehash: 7602b712f2dfc3ba369fd76979baaaa8d5da5c5c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925288"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a>Hantera hur användare kommer åt Office-dokument på mobila enheter

Den här artikeln gäller för Microsoft 365 Business Premium.

Principinställningar som styr hur användare får åtkomst till Office-filer från sina mobila enheter är **Av** som standard. Vi rekommenderar att du godkänner standardvärdena vid installationen för att skapa programprinciper för Android, iOS och Windows 10 som gäller för alla användare. Du kan skapa fler principer när installationen har slutförts. 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Inställningar som styr hur användare kommer åt Office-filer på mobila enheter

Följande inställningar är tillgängliga för att bestämma hur användare kan komma åt Office arbetsfiler:

|Inställning  <br/> |Beskrivning  <br/> |
|:-----|:-----|
|Kräv PIN-kod eller fingeravtryck för åtkomst till Office-program  <br/> |Om den här inställningen **är På** måste användare utöver användarnamn och lösenord, tillhandahålla annan autentisering innan de kan använda Office på sina mobila enheter.  <br/> |
|Återställ PIN-kod när inloggningen misslyckas så här många gånger  <br/> |Om du vill förhindra att obehöriga användare slumpmässigt gissar en PIN-kod. PIN-koden återställs efter det antal felaktiga försök som du anger.  <br/> |
|Kräv att användare loggar in igen efter att Office-appar har varit inaktiva  <br/> |Den här inställningen bestämmer hur länge en användare kan vara inaktiv innan de uppmanas att logga in igen.  <br/> |
|Neka åtkomst till arbetsfiler på jailbroken eller rotade enheter  <br/> |Smarta användarna kanske har en jailbroken eller rotad enhet. Det innebär att användaren kan ändra operativsystemet, vilket kan göra enheten mer känslig för skadlig programvara. De här enheterna är blockerade när den här inställningen är **På**.  <br/> |
|Tillåt inte användare att kopiera innehåll från en Office till personliga appar  <br/> |När inställningen är **På** kan användaren inte kopiera information i en arbetsfil till en personlig fil. Om inställningen är **Av** kan användaren kopiera information från en arbetsfil till ett privat program eller personligt konto.  <br/> |
   

