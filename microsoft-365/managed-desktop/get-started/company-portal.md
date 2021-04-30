---
title: Installera Intune-företagsportal på enheter
description: Information om hur du installerar en företagsportalapp på Microsoft Hanterat skrivbord enheter
keywords: Microsoft Hanterat skrivbord, Microsoft 365, Företagsportal
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f9f36d6ca14be610ce9374380349264439282a6a
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086691"
---
# <a name="install-intune-company-portal-on-devices"></a>Installera Intune-företagsportal på enheter

Microsoft Hanterat skrivbord att IT-administratörer installerar Intune-företagsportal för sina användare med Microsoft Hanterat skrivbord enheter. Här är några fördelar för din organisation:
- Användarna har ett ställe där de kan bläddra bland och installera tillgängliga program. 
- IT-administratörer kan ordna program efter kategorier för sina användare.  
- Vissa program (till exempel Microsoft Project och Microsoft Visio) Företagsportal behöva distribuera Microsoft Hanterat skrivbord.
- IT-administratörer kan Företagsportal för organisationen. Det inkluderar brand imaging, lägga till i lokala supportkontakter och mycket mer. Mer information finns i [Konfigurera programmet Microsoft Intune Företagsportal](/intune/company-portal-app).   

Det här avsnittet dokumenterar processen för att distribuera Intune-företagsportal till dina Microsoft Hanterat skrivbord användare. Den övergripande processen ser ut så här:
1. Köp Företagsportal från Microsoft Store för företag och synkronisera med Intune
2. Tilldela Företagsportal till användarna
3. Informera användarna om ändringar

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Steg 1 – Köp Företagsportal från Microsoft Store för företag och synkronisera med Intune
Mer information om hur du köper appar och synkroniserar med Intune finns i Microsoft Store för företag [distribuera](deploy-apps.md#msfb-apps) *appar till Microsoft Hanterat skrivbord enheter.*

I det här avsnittet finns information om hur du: 
- Köp Företagsportal från Microsoft Store för företag 
- Tvinga synkronisering mellan Intune och Microsoft Store för företag
- Verifiera aktiv synkronisering mellan Intune och Microsoft Store för företag 

## <a name="step-2---assign-company-portal-to-your-users"></a>Steg 2 - Tilldela Företagsportal till användarna
Efter din registrering i Microsoft Hanterat skrivbord distribuerar vi automatiskt Företagsportal till klientorganisationen och installerar appen på Microsoft Hanterat skrivbord enheter i organisationen.

## <a name="step-3---communicate-change-to-your-users"></a>Steg 3 - Meddela användarna om ändring
Som IT-administratör för organisationen är det viktigt att berätta för användarna hur de använder Företagsportal i organisationen. Microsoft Hanterat skrivbord rekommenderar:
- Steg för att installera program från Företagsportal. Mer information finns i [Installera och dela appar på din enhet.](/intune-user-help/install-apps-cpapp-windows)
- Så här skickar du förfrågningar till IT-administratörer för program som inte är tillgängliga för närvarande. Mer information finns i Begära [en app för arbete eller skola.](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Steg för att komma igång med Microsoft Hanterat skrivbord

1. [Lägga till och verifiera administratörskontakter i administratörsportalen](add-admin-contacts.md)
2. [Justera villkorsstyrd åtkomst](conditional-access.md)
3. [Koppla licenser](assign-licenses.md)
4. Distribuera Intune-företagsportal (det här avsnittet)
5. [Aktivera Enterprise State Roaming](enterprise-state-roaming.md)
6. [Konfigurera enheter](set-up-devices.md)
7. [Gör användarna redo att använda enheter](get-started-devices.md)
8. [Distribuera appar](deploy-apps.md)
