---
title: Microsoft Teams
description: Hur Teams installeras på enheter och uppdateras efteråt
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation, appar, verksamhetsbaserade appar, verksamhetsbaserade appar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: 01a3adc7829bbb94f36649f69ba6ef15dbe6b3c2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920662"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) är en [meddelandeapp](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) för din organisation som även tillhandahåller en arbetsyta för samarbete och kommunikation i realtid, möten samt fil- och appdelning.

## <a name="initial-deployment"></a>Inledande distribution

De flesta maskinvaruleverantörer har ännu inte Teams som en del av sina bilder, så Microsoft Managed Desktop distribuerar Teams till dina enheter med hjälp av Microsoft Intune. Alla hanterade enheter har [Teams .msi-paketet](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installerat, vilket säkerställer att alla användare som loggar in på en enhet har Microsoft Teams redo att använda. När paketet har installerats klart startas Teams automatiskt och en genväg läggs till på skrivbordet.

### <a name="microsoft-intune-changes"></a>Ändringar i Microsoft Intune

Microsoft Managed Desktop lägger till två program i din Azure AD-organisation för Microsoft Teams. De distribueras till antingen 64- eller 32-bitarsklienter efter behov för enheten:  

- Modern arbetsplats – Teams Machine Wide Installer x64  
- Modern arbetsplats – Teams Machine Wide Installer x32

## <a name="updates"></a>Uppdateringar

Teams följer en separat uppdateringssökväg från Microsoft 365-apparna för företag, och själva skrivbordsklienten uppdateras automatiskt. Teams söker efter uppdateringar efter några timmar, laddar ned dem och väntar sedan på att datorn är inaktiv innan uppdateringen installeras utan att du blir tyst.  

Teams-produktgruppen tillåter inte att administratörer styr uppdateringar, så Microsoft Managed Desktop använder [standardkanalen för automatisk uppdatering.](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)

### <a name="manually-updating-teams"></a>Uppdatera Teams manuellt

Enskilda användare kan också ladda ned uppdateringar genom **att välja** Sök efter uppdateringar i den    ****   nedrullningsbara menyn Profil längst upp till höger i programmet. Om det finns en uppdatering kommer den att laddas ned och installeras tyst när datorn är inaktiv.

## <a name="delivery-optimization-of-updates"></a>Leveransoptimering av uppdateringar

Leveransoptimering för Teams-uppdateringar är aktiverat som standard och kräver ingen åtgärd från administratörer eller användare.