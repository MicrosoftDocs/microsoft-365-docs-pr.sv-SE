---
title: Gå till API för Microsoft 365 Defender
description: 'Lär dig hur du kommer åt Microsoft 365 Defender API: er'
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
ms.openlocfilehash: bf7a6a70cefda7bfac83d42f8e8dd6355c479914
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845026"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Gå till API för Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

>[!IMPORTANT] 
>Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.


 Microsoft 365 Defender visar mycket av dess data och åtgärder via en uppsättning API: er. Dessa API: er gör det möjligt för dig att automatisera arbets flöden och förnyande baserat på Microsoft 365 Defender-funktioner. För API-åtkomst krävs autentisering med OAuth 2.0. Mer information finns i [verifierings kod flödet för OAuth-2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).


I allmänhet måste du utföra följande steg för att använda API:
- Skapa ett AAD-program
- Skaffa en åtkomsttoken med det här programmet
- Använda token för att få åtkomst till Microsoft 365 Defender API


Du kan komma åt Microsoft 365 Defender API med **program kontext** eller **användar kontext**.

- **Program kontext: (rekommenderas)** <br>
    Används av appar som körs utan en inloggad användare. appar som körs som bakgrunds tjänster eller bakgrunds program.

    Steg som måste vidtas för att få åtkomst till Microsoft 365 Defender API med program kontext:

  1. Skapa ett AAD-webbprogram.
  2. Ge den önskade behörigheten till applicationFor exempel, **incident. Read. all** , **AdvancedHunting. Read. all**. 
  3. Skapa en för detta program.
  4. Hämta token med hjälp av programmet med dess nyckel.
  5. Använda token för att få åtkomst till Microsoft 365 Defender API

     Mer information finns i [få åtkomst med program kontext](api-create-app-web.md).


- **Användar kontext:** <br>
    Används för att utföra åtgärder i API: et åt en användare.

    Steg som måste vidtas för att få åtkomst till Microsoft 365 Defender API med program kontext:
  1. Skapa AAD-program.
  2. Ge programmet rätt behörighet. Till exempel: **incident. Read** , **AdvancedHunting. Read**.
  3. Hämta token med hjälp av programmet med användarautentiseringsuppgifter.
  4. Använda token för att få åtkomst till Microsoft 365 Defender API

     Mer information finns i [få åtkomst med användar kontext](api-create-app-user-context.md).


## <a name="related-topics"></a>Relaterade ämnen
- [Microsoft 365 Defender API: er](api-supported.md)
- [Åtkomst till Microsoft 365 Defender med program kontext](api-create-app-web.md)
- [Åtkomst till Microsoft 365 Defender med användar kontext](api-create-app-user-context.md)
