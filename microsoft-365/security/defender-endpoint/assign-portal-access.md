---
title: Tilldela användaråtkomst till Microsoft Defender Säkerhetscenter
description: Tilldela läs- och skrivskyddad åtkomst till Microsoft Defender för Endpoint-portalen.
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
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: 71215c4988351644cfa4d79503c097c932caf9d6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164783"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a>Tilldela användaråtkomst till Microsoft Defender Säkerhetscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- Azure Active Directory
- Office 365
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender för Endpoint har stöd för två sätt att hantera behörigheter:

- **Grundläggande behörighetshantering:** Ange behörighet till antingen fullständig åtkomst eller skrivskydd.
- **Rollbaserad åtkomstkontroll (RBAC):** Ange detaljerade behörigheter genom att definiera roller, tilldela Azure AD-användargrupper till rollerna och ge användargrupper åtkomst till enhetsgrupper. Mer information om RBAC finns i Hantera [portalåtkomst med rollbaserad åtkomstkontroll.](rbac.md)

> [!NOTE]
> Om du redan har tilldelat grundläggande behörigheter kan du när som helst byta till RBAC. Tänk på följande innan du byter:
> 
> - Användare med fullständig åtkomst (användare som har tilldelats rollen Global administratör eller Säkerhetsadministratör i Azure AD) tilldelas automatiskt standardrollen Defender för slutpunktsadministratör, som också har fullständig åtkomst. Ytterligare Azure AD-användargrupper kan tilldelas rollen Defender för slutpunktsadministratör när du har växlat till RBAC.  Endast användare som tilldelats rollen Defender för slutpunktsadministratör kan hantera behörigheter med RBAC. 
> - Användare som har skrivskyddade åtkomst (säkerhetsläsare) förlorar åtkomsten till portalen tills de har tilldelats en roll. Observera att endast Azure AD-användargrupper kan tilldelas en roll under RBAC.
> - När du har bytt till RBAC kan du inte växla tillbaka till att använda grundläggande behörighetshantering.

## <a name="related-topics"></a>Relaterade ämnen

- [Använda grundläggande behörigheter för åtkomst till portalen](basic-permissions.md)
- [Hantera portalåtkomst med RBAC](rbac.md)
