---
title: Justera villkorsstyrd åtkomst
description: Så här utesluter du vissa Microsoft-konton
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8844c50f5faba609b3f5f53adc5ab45ba1dbaa74
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529689"
---
# <a name="adjust-conditional-access"></a>Justera villkorsstyrd åtkomst

Om du använder [principer för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) i organisationen måste du ange att de ska utesluta vissa konton så att Microsoft Managed Desktop kan fungera korrekt.

Gör så här:

1. Se avsnittet "Återställ steg" i [Så här planerar du distributionen för villkorlig åtkomst i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).
2. Följ stegen där för att utesluta gruppen *Moderna arbetsplatstjänstkonton* för alla principer.


Om du har några problem med villkorlig åtkomst kontaktar du [administratörssupporten](../working-with-managed-desktop/admin-support.md).

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Steg för att komma igång med Microsoft Managed Desktop

1. [Lägga till och verifiera administratörskontakter i administratörsportalen](add-admin-contacts.md)
2. Justera villkorlig åtkomst (det här avsnittet)
3. [Koppla licenser](assign-licenses.md)
4. [Distribuera Intune-företagsportalen](company-portal.md)
5. [Aktivera Enterprise State Roaming](enterprise-state-roaming.md)
6. [Konfigurera enheter](set-up-devices.md)
7. [Gör användarna redo att använda enheter](get-started-devices.md)
8. [Distribuera appar](deploy-apps.md)
