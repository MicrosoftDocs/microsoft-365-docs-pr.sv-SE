---
title: Förbereda skrivarresurser för Microsoft Hanterat skrivbord
description: Viktiga steg för att se till att utskriften fungerar smidigt
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: b6e809505fed8b1f84eb502dc08751ad1f0b587c
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841405"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Förbereda skrivarresurser för Microsoft Hanterat skrivbord

När du är redo att registrera dig på Microsoft Managed Desktop bör du bedöma utskrifts kraven och bestämma rätt metod för din miljö. Du har tre alternativ:
 
- Distribuera Microsofts universella utskrifts lösning för att göra det lättare för Microsoft-hanterade Station ära enheter att upptäcka skrivare. Mer information finns i [Vad är universell utskrift](https://docs.microsoft.com/universal-print/fundamentals/universal-print-whatis).
- Distribuera skrivare direkt med ett anpassat PowerShell-skript. Följ stegen i avsnittet [Konfigurera lokala skrivare](#set-up-local-printers) .
- Använd en lösning som inte kommer från Microsoft och som är kompatibel med Windows 10-enheter som är anslutna till en Azure Active Directory-domän. Lösningen måste uppfylla program varu kraven för Microsoft Managed Desktop. Mer information finns i [Microsofts hanterade program krav](../service-description/mmd-app-requirements.md).
 
Om skrivar driv rutinerna inte är tillgängliga från Microsoft Update eller Microsoft Store måste du i alla fall skaffa dem själv och få dem att paketera för distribution till Microsoft Managed Station ära datorer med Microsoft Intune. Mer information finns i den [fristående-Win32-program hanteringen i Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Konfigurera lokala skrivare

Om du har bestämt dig för att distribuera skrivare med ett anpassat PowerShell-skript och har för berett utskrifts resurserna följer du de här stegen för att distribuera delade skrivare:

1.  Gå till Microsofts hanterade Skriv bords Portal.
2.  Skicka en begäran med etiketten *skrivar distribution* i avsnittet **support > supportfrågor** på administrations portalen och uppge följande uppgifter:
    - Alla UNC-sökvägar till delade skrivar platser som måste distribueras för Microsoft-hanterade Station ära enheter
    - Användar grupper som kräver åtkomst till dessa delade skrivare
3.  Med administrations portalen meddelar vi dig när begäran har slutförts. Från början distribueras bara konfigurationen till enheter i test distributions gruppen.
4.  Du måste testa och bekräfta om konfigurationen fungerar som förväntat. Svara genom att använda fliken **diskussion** i supportavdelningen för att berätta när du har testat.
5.  Vi distribuerar sedan konfigurationen till de andra distributions grupperna.
