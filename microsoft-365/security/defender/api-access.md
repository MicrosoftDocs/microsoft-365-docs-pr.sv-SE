---
title: Åtkomst till Microsoft 365 Defender-API:er
description: Lär dig hur du får tillgång till Microsoft 365 Defender-API:er
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
ms.openlocfilehash: 1fbba132e664f4773496eac7123a0a408db5b3bd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072761"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Åtkomst till Microsoft 365 Defender-API:er

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

Microsoft 365 Defender visar mycket av sina data och åtgärder via en uppsättning programmässiga API:er. De här API:erna hjälper dig att automatisera arbetsflöden och utnyttja funktionerna i Microsoft 365 Defender till fullo.

I allmänhet måste du vidta följande steg för att använda API:er:

- Skapa ett Azure Active Directory-program
- Hämta en åtkomsttoken med det här programmet
- Använda token för att få åtkomst till Microsoft 365 Defender API

> [!NOTE]
> API-åtkomst kräver OAuth2.0-autentisering. Mer information finns i [OAuth 2.0 Auktoriseringskodflöde](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

När du har utfört de här stegen är du redo att använda Microsoft 365 Defender API i ett visst sammanhang.

## <a name="application-context-recommended"></a>Programkontext (rekommenderas)

Använd det här sammanhanget för appar som körs utan att en inloggad användare finns, till exempel bakgrundstjänster eller bakgrundsljud.

1. Skapa ett Azure Active Directory-webbprogram.
2. Tilldela önskad behörighet till programmet.
3. Skapa en nyckel för programmet.
4. Hämta en säkerhetstoken med hjälp av programmet och dess nyckel.
5. Använd tokenet för att få åtkomst till Microsoft 365 Defender API.

Mer information finns i Skapa **[en app för att komma åt Microsoft 365 Defender utan användare.](api-create-app-web.md)**

## <a name="user-context"></a>Användarkontext

Använd det här sammanhanget för att utföra åtgärder för en enskild användare.

1. Skapa ett Inbyggt Azure Active Directory-program.
2. Tilldela önskad behörighet till programmet.
3. Hämta en säkerhetstoken med användaruppgifterna för programmet.
4. Använd tokenet för att få åtkomst till Microsoft 365 Defender API.

Mer information finns i Skapa **[en app för att få åtkomst till Microsoft 365 Defender-API:er för en användares räkning.](api-create-app-user-context.md)**

## <a name="partner-context"></a>Partnerkontext

Använd det här sammanhanget när du behöver tillhandahålla ett program för många användare [i flera klientorganisationar.](/azure/active-directory/develop/single-and-multi-tenant-apps)

1. Skapa ett Azure Active Directory-program för flera innehavare.
2. Tilldela önskad behörighet till programmet.
3. Få [administratörsmedgivande](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) för appen från varje klientorganisation.
4. Hämta en säkerhetstoken med användarautentiseringsuppgifter baserat på en kunds klientorganisations-ID.
5. Använd tokenet för att få åtkomst till Microsoft 365 Defender API.

Mer information finns i Skapa **[en app med partneråtkomst till Microsoft 365 Defender-API:er.](api-partner-access.md)**

## <a name="related-articles"></a>Relaterade artiklar

- [Översikt över Microsoft 365 Defender-API:er](api-overview.md)
- [OAuth 2.0-auktorisering för användar logga in och API-åtkomst](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Hantera hemligheter i dina serverappar med Azure-tangentvalvet](/learn/modules/manage-secrets-with-azure-key-vault/)
- [Skapa programmet Hello world som har åtkomst till Microsoft 365-API:er](api-hello-world.md)