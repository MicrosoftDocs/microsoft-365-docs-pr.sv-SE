---
title: Få åtkomst till API:er för Microsoft 365 Defender
description: Lär dig hur du får åtkomst till MICROSOFT 365 Defender-API:er
keywords: access, apis, programkontext, användarkontext, aad-program, åtkomsttoken
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: ea787adfba0afb425da5f6ea0f6609f96e06b378
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932160"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Få åtkomst till API:er för Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Viss information gäller förhandsversioner av produkter som kan komma att ändras väsentligt innan de släpps till kommersiellt bruk. Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

Microsoft 365 Defender visar mycket av sina data och åtgärder via en uppsättning programmatiska API:er. De här API:erna hjälper dig att automatisera arbetsflöden och använda funktionerna i Microsoft 365 Defender till fullo.

I allmänhet måste du göra följande för att använda API:erna:

- Skapa ett Azure Active Directory-program
- Hämta en åtkomsttoken med det här programmet
- Använda token för att få åtkomst till Microsoft 365 Defender API

> [!NOTE]
> API-åtkomst kräver OAuth2.0-autentisering. Mer information finns i [OAuth 2.0 Authorization Code Flow.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

När du har utfört de här stegen är du redo att använda Microsoft 365 Defender API i ett visst sammanhang.

## <a name="application-context-recommended"></a>Programkontext (rekommenderas)

Använd det här sammanhanget för program som körs utan att en inloggad användare finns, till exempel bakgrundstjänster eller daemons.

1. Skapa ett Azure Active Directory-webbprogram.
2. Tilldela önskad behörighet till programmet.
3. Skapa en nyckel för programmet.
4. Hämta en säkerhetstoken med hjälp av programmet och dess nyckel.
5. Använd token för att få åtkomst till Microsoft 365 Defender API.

Mer information finns i Skapa **[en app för att komma åt Microsoft 365 Defender utan en användare.](api-create-app-web.md)**

## <a name="user-context"></a>Användarkontext

Använd det här sammanhanget för att utföra åtgärder åt en enskild användare.

1. Skapa ett Azure Active Directory-program.
2. Tilldela önskad behörighet till programmet.
3. Hämta en säkerhetstoken med hjälp av användarautentiseringsuppgifterna för programmet.
4. Använd token för att få åtkomst till Microsoft 365 Defender API.

Mer information finns i Skapa en app för att få åtkomst till **[Microsoft 365 Defender-API:er åt en användare.](api-create-app-user-context.md)**

## <a name="partner-context"></a>Partnerkontext

Använd det här sammanhanget när du behöver tillhandahålla en app för många användare [i flera klientorganisationar.](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)

1. Skapa ett Azure Active Directory-program för flera innehavare.
2. Tilldela önskad behörighet till programmet.
3. Få [administratörsmedgivande](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) för programmet från varje klientorganisation.
4. Hämta en säkerhetstoken med användarautentiseringsuppgifter baserat på en kunds klientorganisations-ID.
5. Använd token för att få åtkomst till Microsoft 365 Defender API.

Mer information finns i Skapa **[en app med partneråtkomst till Microsoft 365 Defender-API:er.](api-partner-access.md)**

## <a name="related-articles"></a>Relaterade artiklar

- [Översikt över API:er för Microsoft 365 Defender](api-overview.md)
- [OAuth 2.0-auktorisering för användar logga in och API-åtkomst](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Hantera hemligheter i dina serverappar med Azure-nyckelvalv](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [Skapa ett Hello World-program som öppnar Microsoft 365-API:er](api-hello-world.md)
