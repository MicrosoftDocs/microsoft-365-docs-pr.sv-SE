---
title: Installera Microsoft Project eller Microsoft Visio på Microsoft Managed Station ära enheter
description: Information om hur du installerar Microsoft Project eller Microsoft Visio på Microsoft Managed Station ära enheter
keywords: Microsoft-hanterat skriv bord, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c04bcdf846bafaa7838ef5932c8de595f5035992
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950538"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Installera Microsoft Project eller Microsoft Visio på Microsoft Managed Station ära enheter

Microsoft Project och Microsoft Visio kräver att specifika steg installeras på Microsoft Managed Station ära datorer. I det här avsnittet beskrivs förutsättningar och installations processen för dessa program.

## <a name="prerequisites"></a>Förutsättningar

Administratörer bör kontrol lera att de uppfyller följande krav:
- **Licens mängder** -det korrekta beloppet för Microsoft Project-och Microsoft Visio-licenser måste vara tillgängliga för användarna. Microsoft Managed Desktop stöder för närvarande endast 64-bitars versioner av dessa program. 
- **Licens namn** -lämpliga licens namn för dessa program är:
    - **Microsoft Project** – Project Online Professional eller Project Online Premium
    - **Microsoft Visio** – Visio Online abonnemang 2
- **Företags Portal** -företags portalen måste vara tillgänglig i klient organisationen för att användarna ska kunna installera dessa program. Om företags portalen inte distribueras i din klient organisation, se [företags Portal](company-portal.md).

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Distribuera Project och Visio för Microsoft hanterade Station ära enheter
Microsoft Managed Desktop lägger till Microsoft Project och Microsoft Visio som två Win32-program i Microsoft Intune. Dessutom skapas två grupper i Azure Active Directory som tilldelas motsvarande program med avsikten "tillgänglig". 

**Distribuera Project och Visio** Lägga till användaren i en lämplig grupp så blir programmet tillgänglig i företags portalen. Det kan ta några minuter att synkronisera, men sedan kan användarna installera programmen från företags portalen. 

Azure AD-gruppnamn | Vilka användare ska tilldelas?   
 --- | ---
Modern arbets plats – Office-Project_Install | Användare som behöver projekt
Modern arbets plats – Office-Visio_Install | Användare som behöver Visio

## <a name="communicate-changes"></a>Kommunicera ändringar
Det är viktigt för IT-administratörer att låta användarna veta hur de kan installera Project och Visio. Detta inkluderar: 
- Meddela användarna när de är tillgängliga för dem. 
- Anvisningar för hur du installerar dessa program från företags portalen.
