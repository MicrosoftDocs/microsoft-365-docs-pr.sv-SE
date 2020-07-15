---
title: Installera Microsoft Project eller Microsoft Visio på Microsoft Managed Desktop-enheter
description: Information om hur du installerar Microsoft Project eller Microsoft Visio på Microsoft Managed Desktop-enheter
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c8690db17c71fd5ce604fd9165fee7e54a41c639
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126833"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Installera Microsoft Project eller Microsoft Visio på Microsoft Managed Desktop-enheter

Microsoft Project och Microsoft Visio kräver att specifika steg installeras på Microsoft Managed Desktop-enheter. Det här avsnittet dokumenterar förutsättningarna och installationsprocessen för dessa program.

## <a name="prerequisites"></a>Förutsättningar

Administratörer bör kontrollera att de uppfyller dessa förutsättningar:
- **Licenskvantiteter** – Rätt mängd Microsoft Project- och Microsoft Visio-licenser måste vara tillgängliga för användarna. Microsoft Managed Desktop stöder för närvarande endast 64-bitarsversioner av dessa program. 
- **Licensnamn** - Lämpliga licensnamn för dessa program är:
    - **Microsoft Project** – Project Online Professional eller Project Online Premium
    - **Microsoft Visio** - Visio Online Plan 2
- **Företagsportal** - Företagsportalen måste vara tillgänglig i din klientorganisation för att användarna ska kunna installera dessa program. Om företagsportalen inte distribueras i din klientorganisation läser du [Företagsportalen](company-portal.md).

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Distribuera Project och Visio för Microsoft Managed Desktop-enheter
Microsoft Managed Desktop lägger till Microsoft Project och Microsoft Visio som två Win32-program i Microsoft Intune. Vi kommer också att skapa två grupper i Azure Active Directory som kommer att tilldelas motsvarande program med avsikten "Tillgänglig". 

**Så här distribuerar du Project och Visio** Lägg till användaren i lämplig grupp så blir programmet tillgängligt i företagsportalen. Det kan ta några minuter att synkronisera, men sedan kan användarna installera apparna från Företagsportalen. 

Namn på Azure AD-grupp | Vilka användare ska tilldela?   
 --- | ---
Moderna arbetsplats-office-Project_Install | Användare som behöver Project
Moderna arbetsplats-office-Visio_Install | Användare som behöver Visio

## <a name="communicate-changes"></a>Kommunicera ändringar
Det är viktigt för IT-administratörer att låta sina användare veta hur de installerar Project och Visio. Detta inkluderar: 
- Meddela användarna när dessa program är tillgängliga för dem. 
- Instruktioner om hur du installerar dessa program från företagsportalen.
