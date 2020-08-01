---
title: Installera Intune Company Portal på enheter
description: Information om hur du installerar företagsportalapp på Microsoft Managed Desktop-enheter
keywords: Microsoft Managed Desktop, Microsoft 365, Företagsportal
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 371656168f32db86ff32f187736d59dbd5dbe749
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529701"
---
# <a name="install-intune-company-portal-on-on-devices"></a>Installera Intune-företagsportal på enheter

Microsoft Managed Desktop kräver att IT-administratörer installerar Intune Company Portal för sina användare med Microsoft Managed Desktop-enheter. Här är några fördelar för din organisation:
- Användarna har ett ställe att bläddra och installera tillgängliga program. 
- IT-administratörer kan ordna program efter kategorier för sina användare.  
- Vissa program (som Microsoft Project och Microsoft Visio) kräver att Company Portal distribueras med Microsoft Managed Desktop.
- IT-administratörer kan anpassa Företagsportalen för sin organisation. Detta inkluderar varumärkesavbildning, lägger till lokala supportkontakter med mera. Mer information finns i [Så här konfigurerar du microsoft Intune Company Portal-appen](https://docs.microsoft.com/intune/company-portal-app).   

I det här avsnittet dokumenteras processen för att distribuera Intune Company Portal till dina Microsoft Managed Desktop-användare. Den övergripande processen ser ut så här:
1. Köpa företagsportal från Microsoft Store för företag och synkronisera med Intune
2. Tilldela företagsportal till dina användare
3. Kommunicera ändring till användarna

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Steg 1 – Köp företagsportal från Microsoft Store för företag och synkronisera med Intune
Information om hur du köper apparna och synkroniserar med Intune finns i [Microsoft Store för företag-appar](deploy-apps.md#msfb-apps) i *Distribuera appar till Microsoft Hanterade stationära enheter*.

Det här avsnittet innehåller information om hur du: 
- Köpa företagsportal från Microsoft Store för företag 
- Tvinga synkronisering mellan Intune och Microsoft Store för företag
- Verifiera aktiv synkronisering mellan Intune och Microsoft Store för företag 

## <a name="step-2---assign-company-portal-to-your-users"></a>Steg 2 - Tilldela företagsportal till användarna
Skicka en supportbegäran till Microsoft Managed Desktop Operations via Microsoft Managed Desktop Admin portal. I supportbegäran begär du att företagsportalen ska tilldelas användarna. Microsoft Managed Desktop distribuerar Företagsportalen till din klientorganisation och installerar appen på Microsoft Managed Desktop-enheter i organisationen.

Mer information om hur du skickar supportbegäranden med Microsoft Managed Desktop finns i [Administratörsstöd för Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).

## <a name="step-3---communicate-change-to-your-users"></a>Steg 3 - Kommunicera ändring till användarna
Som IT-administratör för din organisation är det viktigt att låta användarna veta hur de använder Företagsportalen i organisationen. Microsoft Managed Desktop rekommenderar:
- Steg för att installera program från företagsportalen. Mer information finns i [Installera och dela appar på enheten](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).
- Så här skickar du begäranden till IT-administratörer för program som för närvarande inte är tillgängliga. Mer information finns i [Begär en app för arbete eller skola](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Steg för att komma igång med Microsoft Managed Desktop

1. [Lägga till och verifiera administratörskontakter i administratörsportalen](add-admin-contacts.md)
2. [Justera villkorsstyrd åtkomst](conditional-access.md)
3. [Koppla licenser](assign-licenses.md)
4. Distribuera Intune Company Portal (det här avsnittet)
5. [Aktivera Enterprise State Roaming](enterprise-state-roaming.md)
6. [Konfigurera enheter](set-up-devices.md)
7. [Gör användarna redo att använda enheter](get-started-devices.md)
8. [Distribuera appar](deploy-apps.md)
