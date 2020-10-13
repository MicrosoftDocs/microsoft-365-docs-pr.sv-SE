---
title: Installera Intune företags Portal på enheter
description: Information om hur du installerar företagsportalsappen på Microsoft Managed Station ära enheter
keywords: Microsoft Managed Desktop, Microsoft 365, företags Portal
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d457c4b96e47485eee041b72a1cf24e96a13bf18
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430193"
---
# <a name="install-intune-company-portal-on-devices"></a>Installera Intune företags Portal på enheter

Microsoft Managed Desktop kräver att IT-administratörer installerar Intune företags Portal för sina användare med Microsoft-hanterade Station ära enheter. Här är några fördelar för organisationen:
- Användare kan bläddra efter och installera tillgängliga program. 
- IT-administratörer kan ordna program efter kategorier för sina användare.  
- Vissa program (till exempel Microsoft Project och Microsoft Visio) kräver att företags portalen distribueras med Microsoft Managed Desktop.
- IT-administratörer kan anpassa företags portalen för sin organisation. Detta inkluderar varumärkes bild, tillägg av lokala support kontakter med mera. Mer information finns i [Konfigurera programmet Microsoft Intune-företagsportalsappen](https://docs.microsoft.com/intune/company-portal-app).   

I det här avsnittet beskrivs hur du distribuerar Intune-företagsportalsappen till dina Microsoft-hanterade Skriv bords användare. Den övergripande processen ser ut så här:
1. Köp företags portal från Microsoft Store för företag och synkroniserar med Intune
2. Tilldela företags Portal till dina användare
3. Kommunicera ändringar för användarna

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Steg 1 – Köp företags portal från Microsoft Store för företag och synkronisera med Intune
Information om hur du köper appar och synkroniserar med Intune finns i [Microsoft Store för företag-appar](deploy-apps.md#msfb-apps) i *distribuera program till Microsoft Managed Station ära datorer*.

Det här avsnittet innehåller information om hur du: 
- Köp företags portal från Microsoft Store för företag 
- Framtvinga synkronisering mellan Intune och Microsoft Store för företag
- Verifiera aktiv synkronisering mellan Intune och Microsoft Store för företag 

## <a name="step-2---assign-company-portal-to-your-users"></a>Steg 2 – tilldela företags Portal till dina användare
Skicka en supportbegäran till Microsoft Managed Station ära datorer via administrations portalen för Microsoft Managed Desktop. I supportbegäran kan du begära att företags portalen är tilldelad till användarna. Microsoft Managed Desktop distribuerar företags portalen till klient organisationen och installerar appen på Microsoft Managed Station ära enheter i din organisation.

Mer information om hur du skickar support ärenden med Microsoft Managed Desktop finns i [Administratörs support för Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).

## <a name="step-3---communicate-change-to-your-users"></a>Steg 3 – meddela användarnas ändringar
Som IT-administratör i organisationen är det viktigt att låta användarna veta hur man använder företags portalen i din organisation. Microsoft Managed Station ära datorer rekommenderar:
- Steg för att installera program från företags portalen. Mer information finns i [Installera och dela appar på din enhet](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).
- Skicka förfrågningar till IT-administratörer för program som för tillfället inte är tillgängliga. Mer information finns i [begära en app för arbete eller skola](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Steg för att komma igång med Microsoft Managed Desktop

1. [Lägga till och verifiera administratörskontakter i administratörsportalen](add-admin-contacts.md)
2. [Justera villkorsstyrd åtkomst](conditional-access.md)
3. [Koppla licenser](assign-licenses.md)
4. Distribuera Intune-företagsportalsappen (det här avsnittet)
5. [Aktivera Enterprise State Roaming](enterprise-state-roaming.md)
6. [Konfigurera enheter](set-up-devices.md)
7. [Gör användarna redo att använda enheter](get-started-devices.md)
8. [Distribuera appar](deploy-apps.md)
