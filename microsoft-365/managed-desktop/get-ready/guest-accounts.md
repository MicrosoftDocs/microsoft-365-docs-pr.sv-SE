---
title: Förutsättningar för gäst konton
description: Konfigurations rikt linjer för gäst konton och hur du justerar dem
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8953e9f451daa02671a1e1544f2dfe6649ab1b3
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073246"
---
# <a name="prerequisites-for-guest-accounts"></a>Förutsättningar för gäst konton

Microsoft Managed Desktop kräver följande inställningar i din Azure AD-organisation för gäst konto åtkomst. Du kan justera dessa inställningar på [Azure-portalen](https://portal.azure.com) under **externa identiteter/externa samarbete** :

-   **Administratörer och användare i rollen inbjudna för gäst kan bjuda** in till **Ja**
-   För **samarbets begränsningar** väljer du något av följande alternativ:
    -   Om du väljer **Tillåt att inbjudningar skickas till valfri domän (inklusive den mest omfattande)** behöver ingen annan konfiguration göras.
    -   Om du väljer **Neka för angivna domäner** kontrollerar du att Microsoft.com inte finns med i listan i mål domänerna.
    -   Om du väljer **Tillåt endast inbjudningar till angivna domäner (mest restriktiv)** kontrollerar du att Microsoft.com *finns* med i listan i mål domänerna.

Om du ställer in begränsningar som interagerar med de här inställningarna ska du se till att exkludera Azure Active Directory **moderna arbets plats tjänst konton**. Om du till exempel har en policy för villkorsstyrd åtkomst som hindrar gäst konton från att komma åt Intune-portalen utesluter du gruppen **moderna arbets plats tjänst konton** från den här principen.

