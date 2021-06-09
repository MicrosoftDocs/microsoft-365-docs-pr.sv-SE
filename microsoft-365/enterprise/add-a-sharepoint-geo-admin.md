---
title: Lägga till eller ta bort en geo-administratör
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: Behöver du konfigurera separata administratörer för varje geoplats? Lär dig hur du lägger till eller tar bort en geoadministratör i Microsoft 365 Multi-Geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 32fe5e934e6a3d6f18c802c3c427974e67c1b454
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905614"
---
# <a name="add-or-remove-a-geo-administrator-in-microsoft-365-multi-geo"></a>Lägga till eller ta bort en geoadministratör Microsoft 365 i Multi-Geo

Du kan konfigurera separata administratörer för varje geoplats som du har i klientorganisationen. De här administratörerna har tillgång till de SharePoint Online OneDrive de inställningar som är specifika för deras geografiska position.

Vissa tjänster, till exempel termlager, administreras från den centrala platsen och replikeras till satellitplatser. Geoadministratören för den centrala platsen har åtkomst till dessa, men geoadministratörer för satellitplatser har det inte.

Globala administratörer och SharePoint Online-administratörer fortsätter att ha åtkomst till inställningar på den centrala platsen och alla satellitplatser.

## <a name="configuring-geo-administrators"></a>Konfigurera geoadministratörer

Om du vill konfigurera geoadministratörer SharePoint PowerShell-modulen Online.

Använd [Anslut-SPOService för](/powershell/module/sharepoint-online/Connect-SPOService) att ansluta till administrationscentret för den geoplats där du vill lägga till geoadministratören. (Till exempel Connect-SPOServicehttps://ContosoEUR-admin.sharepoint.com.)

Om du vill visa befintliga geoadministratörer för en plats kör du `Get-SPOGeoAdministrator`

### <a name="adding-a-user-as-a-geo-admin"></a>Lägga till en användare som geoadministratör

Om du vill lägga till en användare som geoadministratör kör du `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`

Om du vill ta bort en användare som geoadministratör för en plats kör du  `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`

### <a name="adding-a-group-as-a-geo-admin"></a>Lägga till en grupp som geoadministratör

Du kan lägga till en säkerhetsgrupp eller en e-postaktiverad säkerhetsgrupp som geoadministratör. (Distributionsgrupper och Microsoft 365-grupper stöds inte.)

Om du vill lägga till en grupp som geoadministratör kör du `Add-SPOGeoAdministrator -GroupAlias <alias>`

Om du vill ta bort en grupp som geoadministratör kör du `Remove-SPOGeoAdministrator -GroupAlias <alias>`

Observera att inte alla säkerhetsgrupper har ett gruppalias. Om du vill lägga till en säkerhetsgrupp som inte har ett alias kör du [Get-MsolGroup](/powershell/module/msonline/get-msolgroup) för att hämta en lista med grupper, letar reda på säkerhetsgruppens ObjectID och kör sedan:

`Add-SPOGeoAdministrator -ObjectID <ObjectID>`

Om du vill ta bort en grupp med hjälp av Objekt-ID:t kör du `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`

## <a name="related-topics"></a>Relaterade ämnen

[Add-SPOGeoAdministrator](/powershell/module/sharepoint-online/add-spogeoadministrator)

[Get-SPOGeoAdministrator](/powershell/module/sharepoint-online/get-spogeoadministrator)

[Remove-SPOGeoAdministrator](/powershell/module/sharepoint-online/remove-spogeoadministrator)

[Ange ett alias (MailNickName) för en säkerhetsgrupp](/powershell/module/azuread/set-azureadgroup)