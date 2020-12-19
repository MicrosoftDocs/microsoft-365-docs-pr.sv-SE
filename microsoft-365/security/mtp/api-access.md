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
ms.openlocfilehash: 5e01aaf2ee9255fd909b26278346fd4ccf54729a
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719244"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Gå till API för Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.

Microsoft 365 Defender visar mycket av dess data och åtgärder via en uppsättning API: er. Dessa API: er hjälper dig att automatisera arbets flöden och utnyttja Microsofts 365 Defender-funktioner fullt ut.

I allmänhet måste du utföra följande steg för att använda API:

- Skapa ett Azure Active Directory-program
- Skaffa en åtkomsttoken med det här programmet
- Använda token för att komma åt Microsoft 365 Defender API

> [!NOTE]
> För API-åtkomst krävs autentisering med OAuth 2.0. Mer information finns i [verifierings kod flödet för OAuth-2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

När du har utfört de här stegen kan du komma åt Microsoft 365 Defender API med en viss kontext.

## <a name="application-context-recommended"></a>Program kontext (rekommenderas)

Använd den här kontexten för appar som körs utan en inloggad användare, till exempel bakgrunds tjänster och bakgrunds program.

1. Skapa ett Azure Active Directory-webbprogram.
2. Tilldela önskade behörigheter till programmet.
3. Skapa en-tangenten för programmet.
4. Skaffa ett säkerhetstoken med programmet och dess nyckel.
5. Använd token för att få åtkomst till Microsoft 365 Defender API.

Mer information finns i **[skapa en app för att komma åt Microsoft 365 Defender utan en användare](api-create-app-web.md)**.

## <a name="user-context"></a>Användar kontext

Använd den här kontexten för att utföra åtgärder åt en enskild användare.

1. Skapa ett internt Azure Active Directory-program.
2. Ge programmet rätt behörighet.
3. Skaffa en säkerhetstoken med hjälp av användarens autentiseringsuppgifter för programmet.
4. Använd token för att få åtkomst till Microsoft 365 Defender API.

Mer information finns i **[skapa en app för att få åtkomst till Microsoft 365 Defender API: er för en användares räkning](api-create-app-user-context.md)**.

## <a name="partner-context"></a>Partner kontext

Använd den här kontexten om du behöver tillhandahålla en app för många användare i [flera klient organisationer](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).

1. Skapa ett Azure Active Directory-program med flera innehavare.
2. Ge programmet rätt behörighet.
3. Få ett [administrativt medgivande](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) för appen från varje innehavare.
4. Skaffa en säkerhetstoken med hjälp av användarautentiseringsuppgifter baserat på kundens klient organisations-ID.
5. Använd token för att få åtkomst till Microsoft 365 Defender API.

Mer information finns i **[skapa en app med partner åtkomst till Microsoft 365 Defender API: er](api-partner-access.md)**.

## <a name="related-articles"></a>Relaterade artiklar

- [Översikt över Microsoft 365 Defender API](api-overview.md)
- [OAuth 2,0-auktorisering för användare inloggning och API-åtkomst](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Hantera hemligheter i dina serverprogram med Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [Skapa ett ' Hej världen '-program som använder API för Microsoft 365.](api-hello-world.md)
