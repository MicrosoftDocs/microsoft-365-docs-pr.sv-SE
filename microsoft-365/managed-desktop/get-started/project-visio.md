---
title: Installera Microsoft Project eller Microsoft Visio på Microsoft Hanterat skrivbord enheter
description: Information om hur du installerar Microsoft Project eller Microsoft Visio på Microsoft Hanterat skrivbord enheter
keywords: Microsoft Hanterat skrivbord, Microsoft 365, Microsoft Project, Microsoft Visio
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
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Installera Microsoft Project eller Microsoft Visio på Microsoft Hanterat skrivbord enheter

Microsoft Project och Microsoft Visio specifika steg för installation på alla Microsoft Hanterat skrivbord enheter. I det här avsnittet finns information om förutsättningarna och installationen för dessa program.

## <a name="prerequisites"></a>Förutsättningar

Administratörer bör kontrollera att de uppfyller följande krav:
- **Antal licenser** – Rätt mängd licenser Microsoft Project Och Microsoft Visio vara tillgängliga för användarna. Microsoft Hanterat skrivbord för närvarande endast 64-bitarsversioner av dessa program. 
- **Licensnamn** – Rätt licensnamn för dessa program är:
    - **Microsoft Project** – Project Online Professional eller Project Online Premium
    - **Microsoft Visio** – Visio Online, abonnemang 2
- **Företagsportal** – Företagsportal måste vara tillgänglig i klientorganisationen för att användarna ska kunna installera programmen. Om Företagsportal inte har distribuerats i klientorganisationen kan du gå till [Företagsportal](company-portal.md).

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Distribuera Project och Visio för Microsoft Hanterat skrivbord enheter
Microsoft Hanterat skrivbord lägger till Microsoft Project och Microsoft Visio som två Win32-program i Microsoft Intune. Vi kommer också att skapa två grupper Azure Active Directory som tilldelas till motsvarande program med avsikten "Tillgänglig". 

**Distribuera Project och Visio** Lägg till användaren i lämplig grupp så blir programmet tillgängligt i Företagsportal. Det kan ta några minuter att synkronisera, men sedan kan användarna installera apparna från Företagsportal. 

Azure AD-gruppnamn | Vilka användare ska tilldelas?   
 --- | ---
Modern workplace-Office-Project_Install | Användare som behöver Project
Modern workplace-Office-Visio_Install | Användare som behöver Visio

## <a name="communicate-changes"></a>Informera om ändringar
It's important for IT administrators to let their users know how to install Project and Visio. Detta omfattar följande: 
- Meddela användare när dessa program är tillgängliga för dem. 
- Anvisningar om hur du installerar programmen från Företagsportal.
