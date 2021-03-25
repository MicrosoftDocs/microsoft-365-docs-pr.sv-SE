---
title: Använda grundläggande behörigheter för att komma åt Microsoft Defender Säkerhetscenter
description: Lär dig hur du använder grundläggande behörigheter för att komma åt Microsoft Defender för Endpoint-portalen.
keywords: tilldela användarroller, tilldela läs- och skrivåtkomst, tilldela skrivskyddsåtkomst, användare, användarroller, roller
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: cb5762d2a9e4b62432aba6dacd1033ddc3c7daf2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163677"
---
# <a name="use-basic-permissions-to-access-the-portal"></a>Använda grundläggande behörigheter för åtkomst till portalen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- Azure Active Directory
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

Använd grundläggande behörighetshantering i anvisningarna nedan.

Du kan använda någon av följande lösningar:
- Azure PowerShell
- Azure Portal

Om du vill ha detaljerad kontroll över behörigheter [växlar du till rollbaserad åtkomstkontroll.](rbac.md)

## <a name="assign-user-access-using-azure-powershell"></a>Tilldela användaråtkomst med hjälp av Azure PowerShell
Du kan tilldela användare med någon av följande behörighetsnivåer:
- Fullständig åtkomst (läsa och skriva)
- Skrivskyddade åtkomst

### <a name="before-you-begin"></a>Innan du börjar

- Installera Azure PowerShell. Mer information finns i Installera [och konfigurera Azure PowerShell.](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)<br>

    > [!NOTE]
    > Du måste köra PowerShell-cmdletarna i en upphöjd kommandorad.

- Anslut till Azure Active Directory. Mer information finns i [Connect-MsolService.](https://docs.microsoft.com/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true)

**Fullständig åtkomst** <br>
Användare med fullständig åtkomst kan logga in, visa all systeminformation och lösa aviseringar, skicka filer för djupanalys och ladda ned onboarding-paketet.
Om du vill tilldela fullständiga åtkomstbehörigheter måste du lägga till användarna i de inbyggda rollerna "säkerhetsadministratör" eller "global administratör".

**Skrivskyddade åtkomst** <br>
Användare med skrivskydd kan logga in, visa alla aviseringar och relaterad information.
De kommer inte att kunna ändra aviseringstillstånd, skicka filer för djupanalys eller utföra åtgärder som ändrar tillstånd.
Om du vill tilldela skrivskyddad åtkomstbehörighet måste användarna läggs till i den inbyggda rollen "Säkerhetsläsare" i Azure AD.

Använd följande steg för att tilldela säkerhetsroller:

- För **läs- och skrivbehörighet** tilldelar du användare till säkerhetsadministratörsrollen med hjälp av följande kommando:

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- För **skrivskyddad** åtkomst tilldelar du användare till rollen för säkerhetsläsare med hjälp av följande kommando:

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

Mer information finns i Lägga [till eller ta bort gruppmedlemmar med Hjälp av Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

## <a name="assign-user-access-using-the-azure-portal"></a>Tilldela användaråtkomst via Azure Portal

Mer information finns i Tilldela [användare med Azure Active Directory administratörsroller och icke-administratörsroller.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

## <a name="related-topic"></a>Relaterade ämnen

- [Hantera portalåtkomst med RBAC](rbac.md)
