---
title: Installera Intune Company Portal på enheter
description: Information om hur du installerar företagsportalapp på Microsoft Managed Desktop-enheter
keywords: Microsoft Managed Desktop, Microsoft 365, Företagsportal
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4e83983ae7b8b936b639382f025f1f88eeca0762
ms.sourcegitcommit: 0ceb79a633f7004e82b80e69b6f7a7329ccec7ff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2019
ms.locfileid: "42808602"
---
# <a name="install-intune-company-portal-on-on-devices"></a>Installera Intune Company Portal på enheter

Microsoft Managed Desktop kräver att IT-administratörer installerar Intune Company Portal för sina användare med Microsoft Managed Desktop-enheter. Här är några fördelar för din organisation:
- Användare har en plats att bläddra bland och installera tillgängliga program. 
- IT-administratörer kan ordna program efter kategorier för sina användare.  
- Vissa program (som Microsoft Project och Microsoft Visio) kräver att Företagsportaldistribueras med Microsoft Managed Desktop.
- IT-administratörer kan anpassa företagsportalen för sin organisation. Detta inkluderar varumärkesavbildning, lägga till i lokala supportkontakter med mera. Mer information finns i [Konfigurera appen Microsoft Intune Company Portal](https://docs.microsoft.com/intune/company-portal-app).   

I det här avsnittet dokumenteras processen för distribution av Intune Company Portal till dina Microsoft Managed Desktop-användare. Den övergripande processen ser ut så här:
1. Köp företagsportal från Microsoft Store för företag och synkronisera med Intune
2. Tilldela företagsportal till användarna
3. Kommunicera ändringar till användarna

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Steg 1 - Köp företagsportal från Microsoft Store för företag och synkronisera med Intune
Information om hur du köper apparna och synkroniserar med Intune finns i [Microsoft Store för företag-appar](deploy-apps.md#msfb-apps) i *Distribuera appar till Microsoft Managed Desktop-enheter*.

Det här avsnittet innehåller information om hur du: 
- Köpa företagsportal från Microsoft Store för företag 
- Tvinga synkronisering mellan Intune och Microsoft Store för företag
- Verifiera aktiv synkronisering mellan Intune och Microsoft Store för företag 

## <a name="step-2---assign-company-portal-to-your-users"></a>Steg 2 - Tilldela företagsportal till dina användare
Skicka en supportbegäran till Microsoft Managed Desktop Operations via Microsoft Managed Desktop Admin portal. I supportbegäran begär att företagsportalen ska tilldelas dina användare. Microsoft Managed Desktop distribuerar Företagsportal en till din klientorganisation och installerar appen på Microsoft Managed Desktop-enheter i organisationen.

Mer information om hur du skickar supportförfrågningar med Microsoft Managed Desktop finns i [Administratörssupport för Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).

## <a name="step-3---communicate-change-to-your-users"></a>Steg 3 - Kommunicera ändring till användarna
Som IT-administratör för din organisation är det viktigt att låta användarna veta hur de använder Företagsportalen i organisationen. Microsoft Managed Desktop rekommenderar:
- Åtgärder för att installera program från företagsportalen. Mer information finns i [Installera och dela appar på enheten](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).
- Så här skickar du förfrågningar till IT-administratörer för program som för närvarande inte är tillgängliga. Mer information finns i [Begär en app för arbete eller skola](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Steg för att komma igång med Microsoft Managed Desktop

1. [Lägga till och verifiera administratörskontakter i administratörsportalen](add-admin-contacts.md)
2. [Justera villkorlig åtkomst](conditional-access.md)
3. [Tilldela licenser](assign-licenses.md)
4. Distribuera Intune Company Portal (det här avsnittet)
5. [Aktivera roaming mellan företagstillstånd](enterprise-state-roaming.md)
6. [Konfigurera enheter](set-up-devices.md)
7. [Gör användarna redo att använda enheter](get-started-devices.md)
8. [Distribuera appar](deploy-apps.md)
