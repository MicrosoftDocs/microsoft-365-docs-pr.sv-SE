---
title: Förbereda utskriftsresurser för Microsoft Managed Desktop
description: Viktiga steg för att se till att utskriften fungerar smidigt
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: a90d104915ecdd31d9ac35a6393fba74a3816ea8
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826455"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Förbereda utskriftsresurser för Microsoft Managed Desktop

När du gör dig redo att registrera dig på Microsoft Managed Desktop bör du utvärdera utskriftskraven och bestämma rätt metod för din miljö. Du har tre alternativ:
 
- Distribuera utskriftslösningen för Microsoft Hybrid Cloud så att det är enkelt för Microsoft Managed Desktop-enheter att identifiera skrivare. Mer information finns i [Distribuera Windows Server Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
- Distribuera skrivare direkt med hjälp av ett anpassat PowerShell-skript. Gör så här i avsnittet [Konfigurera lokala skrivare.](#set-up-local-printers)
- Använd en utskriftslösning från molnet som inte kommer från Microsoft som är kompatibel med Windows 10-enheter som är anslutna till en Azure Active Directory-domän. Lösningen måste uppfylla programvarukraven för Microsoft Managed Desktop. Mer information finns i [krav på Microsoft Managed Desktop-app](../service-description/mmd-app-requirements.md).
 
I samtliga fall, om skrivardrivrutinerna inte är tillgängliga från Microsoft Update eller Microsoft Store, måste du skaffa dem själv och låta dem paketerade för distribution till dina Microsoft Managed Desktop-enheter med Microsoft Intune. Mer information finns [i Intune Standalone - Win32 app management](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Konfigurera lokala skrivare

Om du har bestämt dig för att distribuera skrivare med ett anpassat PowerShell-skript och har förberett utskriftsresurserna gör du så här om du vill att delade skrivare ska distribueras:

1.  Navigera till Microsoft Managed Desktop-portalen.
2.  Skicka en begäran med etiketten *skrivardistribution* i avsnittet **Support > supportbegäranden** i administrationsportalen, med följande information:
    - Alla UNC-sökvägar till delade skrivarplatser som måste distribueras för Microsoft Managed Desktop-enheter
    - Användargrupper som kräver åtkomst till dessa delade skrivare
3.  Med hjälp av adminportalen meddelar vi dig när begäran har slutförts. Inledningsvis distribuerar vi bara konfigurationen till enheter i testdistributionsgruppen.
4.  Du måste testa och bekräfta om konfigurationen fungerar som förväntat. Svara med hjälp av fliken **Diskussion** i supportbegäran för att meddela oss när du har slutfört testningen.
5.  Vi distribuerar sedan konfigurationen till de andra distributionsgrupperna.
