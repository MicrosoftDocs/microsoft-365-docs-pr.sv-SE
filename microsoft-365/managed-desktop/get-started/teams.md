---
title: Microsoft Teams
description: Hur team är installerat på enheter och uppdateras efteråt
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation, appar, branschspecifika appar, LOB-appar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: ea2ef7637a8d360e3b598aec4852425d977ae4ec
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950961"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) är ett [meddelande program](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) för din organisation som också tillhandahåller en arbets yta för samarbete och kommunikation i real tid, möten och fil-och program delning.

## <a name="initial-deployment"></a>Inledande distribution

De flesta maskin varu leverantörer inkluderar inte team som en del av bilderna, så Microsoft Managed Desktop distribuerar Teams till dina enheter med hjälp av Microsoft Intune. Alla hanterade enheter har [Teams. MSI-paketet](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installerat, så att alla användare som loggar in på en enhet kan använda Microsoft Teams. När paketet först slutar installeras startar Teams automatiskt och lägger till en genväg på Skriv bordet.

### <a name="microsoft-intune-changes"></a>Ändringar i Microsoft Intune

Microsoft Managed Desktop lägger till två program i din Azure AD-organisation för Microsoft Teams. De distribueras till antingen 64-bitars-eller 32-bitars klienter enligt vad som är lämpligt för enheten:  

- Modern arbets plats – Teams Machine wide installations program x64  
- Modern arbets plats – Teams Machine wide Installer x32

## <a name="updates"></a>Uppdateringar

Teams följer en separat uppdaterings väg från Microsoft 365-appar för företag och Station ära klient uppdateringar automatiskt. Teams söker efter uppdateringar med några timmars mellanrum, laddar ned dem och väntar sedan på att datorn ska vara inaktiv innan den installeras.  

Teams produkt gruppen tillåter inte att administratörer styr uppdateringar, så Microsoft Managed Desktop använder standard ikonen för [Automatisk uppdatering](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).

### <a name="manually-updating-teams"></a>Uppdatera Teams manuellt

Enskilda användare kan också ladda ner uppdateringar genom att välja **Sök efter uppdateringar**   på den **Profile**   nedrullningsbara menyn profil längst upp till höger i appen. Om det finns en uppdatering hämtas den och installeras tyst när datorn är inaktiv.

## <a name="delivery-optimization-of-updates"></a>Leverans optimering för uppdateringar

Leverans optimering för Teams-uppdateringar är aktiverat som standard och kräver ingen åtgärd från administratörer eller användare. 