---
title: Justera villkorlig åtkomst
description: Så här utesluter du vissa Microsoft-konton
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1bc5d937616cba60c5af43fe22a7c4dccf89a55e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806478"
---
# <a name="adjust-conditional-access"></a>Justera villkorlig åtkomst

Om du använder [principer för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) i organisationen måste du ange att de ska utesluta vissa konton så att Microsoft Managed Desktop kan fungera korrekt.

Gör så här:

1. Se avsnittet "Återställ steg" i [Så här planerar du distributionen för villkorlig åtkomst i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).
2. Följ stegen där för att utesluta gruppen *Moderna arbetsplatstjänstkonton* för alla principer.


Om du har några problem med villkorlig åtkomst kontaktar du [administratörssupporten](../working-with-managed-desktop/admin-support.md).

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Steg för att komma igång med Microsoft Managed Desktop

1. [Lägga till och verifiera administratörskontakter i administratörsportalen](add-admin-contacts.md)
2. Justera villkorlig åtkomst (det här avsnittet)
3. [Tilldela licenser](assign-licenses.md)
4. [Distribuera Intune-företagsportal](company-portal.md)
5. [Aktivera roaming i företagstillstånd](enterprise-state-roaming.md)
6. [Konfigurera enheter](set-up-devices.md)
7. [Gör användarna redo att använda enheter](get-started-devices.md)
8. [Distribuera appar](deploy-apps.md)
