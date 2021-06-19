---
title: Få åtkomst Microsoft 365 Defender API:er
description: Lär dig hur du får åtkomst Microsoft 365 Defender API:er
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 03fd82cd5dc24653b6d67fa47cc225d355bfac45
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028805"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Få åtkomst Microsoft 365 Defender API:er

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

Microsoft 365 Defender mycket av informationen och åtgärderna via ett antal programmässiga API:er. De här API:erna hjälper dig att automatisera arbetsflöden och Microsoft 365 Defender av funktionerna.

I allmänhet måste du vidta följande steg för att använda API:er:

- Skapa ett Azure Active Directory program
- Hämta en åtkomsttoken med det här programmet
- Använda tokenet för att komma åt Microsoft 365 Defender API

> [!NOTE]
> API-åtkomst kräver OAuth2.0-autentisering. Mer information finns i [OAuth 2.0 auktoriseringskod för Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

När du har utfört de här stegen är du redo att använda API:t Microsoft 365 Defender ett visst sammanhang.

## <a name="application-context-recommended"></a>Programkontext (rekommenderas)

Använd det här sammanhanget för appar som körs utan att en inloggad användare finns, till exempel bakgrundstjänster eller bakgrundsljud.

1. Skapa ett Azure Active Directory webbprogram.
2. Tilldela önskad behörighet till programmet.
3. Skapa en nyckel för programmet.
4. Hämta en säkerhetstoken med hjälp av programmet och dess nyckel.
5. Använd tokenet för att komma Microsoft 365 Defender API.

Mer information finns i Skapa **[ett program för att komma Microsoft 365 Defender utan en användare.](api-create-app-web.md)**

## <a name="user-context"></a>Användarkontext

Använd det här sammanhanget för att utföra åtgärder för en enskild användare.

1. Skapa ett Azure Active Directory inbyggt program.
2. Tilldela önskad behörighet till programmet.
3. Hämta en säkerhetstoken med användaruppgifterna för programmet.
4. Använd tokenet för att komma Microsoft 365 Defender API.

Mer information finns i Skapa **[ett program för att komma Microsoft 365 Defender API:er åt en användare.](api-create-app-user-context.md)**

## <a name="partner-context"></a>Partnerkontext

Använd det här sammanhanget när du behöver tillhandahålla ett program för många användare [i flera klientorganisationar.](/azure/active-directory/develop/single-and-multi-tenant-apps)

1. Skapa ett Azure Active Directory för flera innehavare.
2. Tilldela önskad behörighet till programmet.
3. Få [administratörsmedgivande](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) för appen från varje klientorganisation.
4. Hämta en säkerhetstoken med användarautentiseringsuppgifter baserat på en kunds klientorganisations-ID.
5. Använd tokenet för att komma Microsoft 365 Defender API.

Mer information finns i Skapa **[ett program med partneråtkomst till Microsoft 365 Defender API:er.](api-partner-access.md)**

## <a name="related-articles"></a>Relaterade artiklar

- [Microsoft 365 Defender API:er – översikt](api-overview.md)
- [OAuth 2.0-auktorisering för användar logga in och API-åtkomst](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Hantera hemligheter i dina serverappar med Azure-tangentvalvet](/learn/modules/manage-secrets-with-azure-key-vault/)
- [Skapa programmet Hej världen som har åtkomst till de Microsoft 365 API:er](api-hello-world.md)