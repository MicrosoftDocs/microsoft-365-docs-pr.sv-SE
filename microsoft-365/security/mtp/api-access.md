---
title: 'Komma åt API: erna för skydd mot Microsoft Threat'
description: 'Lär dig hur du kommer åt API: erna för skydd mot Microsoft Threat'
keywords: 'åtkomst, API: er, program kontext, användar kontext, AAD-program, åtkomsttoken'
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 653c359c324852719688a374a6e863df0a1909ba
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650596"
---
# <a name="access-the-microsoft-threat-protection-apis"></a>Komma åt API: erna för skydd mot Microsoft Threat

**Gäller för:**
- Microsoft Hotskydd

>[!IMPORTANT] 
>Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.


 Microsoft Threat Protection visar mycket av dess data och åtgärder genom en uppsättning API: er. Dessa API: er gör det möjligt för dig att automatisera arbets flöden och förnyande baserat på Microsoft Threat Protection-funktioner. För API-åtkomst krävs autentisering med OAuth 2.0. Mer information finns i [verifierings kod flödet för OAuth-2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).


I allmänhet måste du utföra följande steg för att använda API:
- Skapa ett AAD-program
- Skaffa en åtkomsttoken med det här programmet
- Använda token för att få åtkomst till Microsoft Threat Protection API


Du kan få åtkomst till Microsoft Threat Protection API med **program kontext** eller **användar kontext**.

- **Program kontext: (rekommenderas)** <br>
    Används av appar som körs utan en inloggad användare. appar som körs som bakgrunds tjänster eller bakgrunds program.

    Anvisningar som måste vidtas för att få åtkomst till Microsoft Threat Protection API med program kontext:

  1. Skapa ett AAD-webbprogram.
  2. Ge den önskade behörigheten till applicationFor exempel, **incident. Read. all**, **AdvancedHunting. Read. all**. 
  3. Skapa en för detta program.
  4. Hämta token med hjälp av programmet med dess nyckel.
  5. Använda token för att få åtkomst till Microsoft Threat Protection API

     Mer information finns i [få åtkomst med program kontext](api-create-app-web.md).


- **Användar kontext:** <br>
    Används för att utföra åtgärder i API: et åt en användare.

    Steg som måste vidtas för att få åtkomst till Microsoft Threat Protection API med program kontext:
  1. Skapa AAD-program.
  2. Ge programmet rätt behörighet. Till exempel: **incident. Read**, **AdvancedHunting. Read**.
  3. Hämta token med hjälp av programmet med användarautentiseringsuppgifter.
  4. Använda token för att få åtkomst till Microsoft Threat Protection API

     Mer information finns i [få åtkomst med användar kontext](api-create-app-user-context.md).


## <a name="related-topics"></a>Relaterade ämnen
- [API för skydd mot Microsoft Threat](api-supported.md)
- [Åtkomst till Microsoft Threat Protection med program kontext](api-create-app-web.md)
- [Åtkomst till Microsoft Threat Protection med användar kontext](api-create-app-user-context.md)
