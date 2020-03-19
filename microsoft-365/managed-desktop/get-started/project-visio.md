---
title: Installera Microsoft Project eller Microsoft Visio på Microsoft Managed Desktop-enheter
description: Information om hur du installerar Microsoft Project eller Microsoft Visio på Microsoft Managed Desktop-enheter
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 30374e603350ecf9d5e5542263f004a22ccb0a67
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/14/2019
ms.locfileid: "42805638"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Installera Microsoft Project eller Microsoft Visio på Microsoft Managed Desktop-enheter

Microsoft Project och Microsoft Visio kräver att specifika steg installeras på Microsoft Managed Desktop-enheter. I det här avsnittet dokumenteras förutsättningarna och installationsprocessen för dessa program.

## <a name="prerequisites"></a>Förutsättningar

Administratörer bör kontrollera att de uppfyller dessa förutsättningar:
- **Licenskvantiteter** – Rätt mängd Licenser för Microsoft Project och Microsoft Visio måste vara tillgängligt för användarna. Microsoft Managed Desktop stöder för närvarande bara 64-bitarsversioner av dessa program. 
- **Licensnamn** - Lämpliga licensnamn för dessa program är:
    - **Microsoft Project** - Project Online Professional eller Project Online Premium
    - **Microsoft Visio** - Visio Online Plan 2
- **Företagsportalen** – Företagsportalen måste vara tillgänglig i din klientorganisation för att användarna ska kunna installera dessa program. Om företagsportalen inte distribueras i din klient finns i [Företagsportalen](company-portal.md).

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Distribuera Project och Visio för Microsoft Managed Desktop-enheter
När du har skickat in supportbegäran skapar Microsoft Managed Desktop tre Azure AD-grupper och tre programdistributioner via Microsoft Intune för att distribuera apparna till din klientorganisation.  

**Så här distribuerar du Project och Visio**
1. **Lämna in en supportbegäran** IT-administratörer måste lämna in en supportbegäran för att göra dessa program tillgängliga för sina användare. Information om hur du kontaktar Microsoft Managed Desktop finns i [Administratörssupport för Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).
2. **Tilldela användare till nya Azure AD-grupper** Microsoft Managed Desktop skapar 3 Azure AD-grupper i din klientorganisation och 3 motsvarande programdistributioner. IT-administratörer måste tilldela användarna till lämpliga grupper.

>[!NOTE]
>Tilldela användare till endast en av dessa Azure AD-grupper. 

Azure AD-gruppnamn | Vilka användare att tilldela?   
 --- | ---
Modern arbetsplats-Office-Project_Install | Användare som bara behöver Project
Modern Visio_Install på arbetsplatsen | Användare som bara behöver Visio
Modern arbetsplats-Office-Visio_Project_Install | Användare som behöver både Project och Visio

När dessa grupper har tilldelats kommer programmen att vara tillgängliga i företagsportalen. Det kan ta några minuter att synkronisera, men sedan kan användarna installera apparna från Företagsportalen. 

## <a name="communicate-changes"></a>Kommunicera ändringar
Det är viktigt att IT-administratörer meddelar användarna hur de installerar Project och Visio. Detta inkluderar: 
- Meddela användare när dessa program är tillgängliga för dem. 
- Instruktioner om hur du installerar dessa program från företagsportalen.

>[!NOTE]
>Användare måste stänga alla Office-program innan de installerar Microsoft Project eller Microsoft Visio från Företagsportalen. 
