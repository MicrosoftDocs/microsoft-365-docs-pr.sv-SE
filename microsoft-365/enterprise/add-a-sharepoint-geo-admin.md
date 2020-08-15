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
description: Behöver du konfigurera separata administratörer för varje Geo-plats? Lär dig hur du lägger till eller tar bort en geo-administratör i Microsoft 365 multi-geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9a3d916bfec2c53850f923fb5322298e9ff440ca
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694895"
---
# <a name="add-or-remove-a-geo-administrator-in-microsoft-365-multi-geo"></a>Lägga till eller ta bort en geo-administratör i Microsoft 365 multi-geo

Du kan konfigurera separata administratörer för varje Geo-plats som du har i klient organisationen. Dessa administratörer kommer att ha åtkomst till SharePoint Online-och OneDrive-inställningarna som är specifika för deras Geo-plats.

Vissa tjänster-till exempel term lagrings platsen-administreras från central plats och replikeras till satellit platser. Geo-administratören för den centrala platsen har till gång till dessa, medan geo-administratörer för satellit platser inte gör det.

Globala administratörer och SharePoint Online-administratörer fortsätter att ha åtkomst till inställningar på Central platsen och alla satellit platser.

## <a name="configuring-geo-administrators"></a>Konfigurera geo-administratörer

Konfigurering av Geo administratörer kräver PowerShell-modulen för SharePoint Online.

Använd [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/Connect-SPOService) för att ansluta till administrations centret för den Geo-plats där du vill lägga till geo-administratören. (Till exempel Connect-SPOService  https://ContosoEUR-admin.sharepoint.com.)

Om du vill visa befintliga geo-administratörer på en plats kör du `Get-SPOGeoAdministrator`

### <a name="adding-a-user-as-a-geo-admin"></a>Lägga till en användare som geo-administratör

Om du vill lägga till en användare som geo-administratör kör du `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`

Om du vill ta bort en användare som geo-administratör på en plats kör du  `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`

### <a name="adding-a-group-as-a-geo-admin"></a>Lägga till en grupp som geo-administratör

Du kan lägga till en säkerhets grupp eller en e-postaktiverad säkerhets grupp som geo-administratör. (Distributions grupper och Microsoft 365-grupper stöds inte.)

Om du vill lägga till en grupp som geo-administratör kör du `Add-SPOGeoAdministrator -GroupAlias <alias>`

Om du vill ta bort en grupp som geo-administratör kör du `Remove-SPOGeoAdministrator -GroupAlias <alias>`

Observera att inte alla säkerhets grupper har ett gruppalias. Om du vill lägga till en säkerhets grupp som inte har ett alias kör du [Get-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/get-msolgroup) för att hämta en lista med grupper, letar reda på säkerhets gruppens ObjectID och kör:

`Add-SPOGeoAdministrator -ObjectID <ObjectID>`

Om du vill ta bort en grupp med hjälp av ObjectID kör du `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`

## <a name="related-topics"></a>Relaterade ämnen

[Add-SPOGeoAdministrator](https://docs.microsoft.com/powershell/module/sharepoint-online/add-spogeoadministrator)

[Get-SPOGeoAdministrator](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spogeoadministrator)

[Remove-SPOGeoAdministrator](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spogeoadministrator)

[Ange ett alias (smek namn) för en säkerhets grupp](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup)