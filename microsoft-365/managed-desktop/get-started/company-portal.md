---
title: Installera Intune-företagsportal på enheter
description: Information om hur du installerar en företagsportalapp på Microsoft Managed Desktop-enheter
keywords: Microsoft Managed Desktop, Microsoft 365, företagsportal
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f4c5d20529a210207e225d4a2b46d5935ae112c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925780"
---
# <a name="install-intune-company-portal-on-devices"></a>Installera Intune-företagsportal på enheter

Microsoft Managed Desktop kräver att IT-administratörer installerar Intune-företagsportal för sina användare med Microsoft Managed Desktop-enheter. Här är några fördelar för din organisation:
- Användarna har ett ställe där de kan bläddra bland och installera tillgängliga program. 
- IT-administratörer kan ordna program efter kategorier för sina användare.  
- För vissa program (till exempel Microsoft Project och Microsoft Visio) krävs en företagsportal för distribution med Microsoft Managed Desktop.
- IT-administratörer kan anpassa företagsportalen för organisationen. Det inkluderar brand imaging, lägga till i lokala supportkontakter och mycket mer. Mer information finns i Konfigurera [appen Microsoft Intune-företagsportal.](/intune/company-portal-app)   

I det här avsnittet finns information om hur du distribuerar Intune-företagsportalen till användare av Microsoft Managed Desktop. Den övergripande processen ser ut så här:
1. Köp företagsportalen från Microsoft Store för företag och synkronisera med Intune
2. Tilldela företagsportalen till användarna
3. Informera användarna om ändringar

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Steg 1 – Köp företagsportal från Microsoft Store för företag och synkronisera med Intune
Mer information om hur du köper appar och synkroniserar med Intune finns i Microsoft Store för [företag-appar](deploy-apps.md#msfb-apps) i Distribuera appar till *Microsoft Hanterade skrivbordsenheter.*

I det här avsnittet finns information om hur du: 
- Köp företagsportal från Microsoft Store för företag 
- Tvinga synkronisering mellan Intune och Microsoft Store för företag
- Verifiera aktiv synkronisering mellan Intune och Microsoft Store för företag 

## <a name="step-2---assign-company-portal-to-your-users"></a>Steg 2 - Tilldela företagsportalen till användarna
Efter registreringen i Microsoft Managed Desktop kommer Microsoft Managed Desktop Operations automatiskt att distribuera företagsportalen till klientorganisationen och installera appen på Microsoft Managed Desktop-enheter i organisationen.

## <a name="step-3---communicate-change-to-your-users"></a>Steg 3 - Meddela användarna om ändring
Som IT-administratör för din organisation är det viktigt att berätta för användarna hur företagsportalen i organisationen ska användas. Microsoft Managed Desktop rekommenderar:
- Steg för att installera program från företagsportalen. Mer information finns i [Installera och dela appar på din enhet.](/intune-user-help/install-apps-cpapp-windows)
- Så här skickar du förfrågningar till IT-administratörer för program som inte är tillgängliga för närvarande. Mer information finns i Begära [en app för arbete eller skola.](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Steg för att komma igång med Microsoft Managed Desktop

1. [Lägga till och verifiera administratörskontakter i administratörsportalen](add-admin-contacts.md)
2. [Justera villkorsstyrd åtkomst](conditional-access.md)
3. [Koppla licenser](assign-licenses.md)
4. Distribuera Intune-företagsportal (det här avsnittet)
5. [Aktivera Enterprise State Roaming](enterprise-state-roaming.md)
6. [Konfigurera enheter](set-up-devices.md)
7. [Gör användarna redo att använda enheter](get-started-devices.md)
8. [Distribuera appar](deploy-apps.md)