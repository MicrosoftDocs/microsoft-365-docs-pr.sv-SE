---
title: Förbereda skrivarresurser för Microsoft Hanterat skrivbord
description: Viktiga steg för att se till att utskriften fungerar smidigt
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 3decc7d67decc5557e7921e68108e2ddb447f0fd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924558"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Förbereda skrivarresurser för Microsoft Hanterat skrivbord

När du gör dig redo att registrera dig i Microsoft Managed Desktop bör du utvärdera dina utskriftskrav och bestämma rätt metod för din miljö. Det finns tre alternativ:
 
- Distribuera Microsoft Universal Print-lösningen för att göra det enkelt för Microsoft Managed Desktop-enheter att identifiera skrivare. Mer information finns i Vad [är Universell utskrift.](/universal-print/fundamentals/universal-print-whatis)
- Distribuera skrivare direkt med hjälp av ett anpassat PowerShell-skript. Följ anvisningarna i [avsnittet Konfigurera lokala](#set-up-local-printers) skrivare.
- Använd en lösning som inte är en Microsoft-lösning för molnutskrift som är kompatibel med Windows 10-enheter som är anslutna till en Azure Active Directory-domän. Lösningen måste uppfylla programvarukraven för Microsoft Managed Desktop. Mer information finns i [Appkrav för Microsoft Managed Desktop.](../service-description/mmd-app-requirements.md)
 
Om skrivardrivrutinerna inte är tillgängliga från Microsoft Update eller Microsoft Store måste du i samtliga fall skaffa dem själv och paketera dem för distribution till dina Microsoft Managed Desktop-enheter med Microsoft Intune. Mer information finns i [Fristående Intune – Win32-apphantering](/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Konfigurera lokala skrivare

Om du har bestämt dig för att distribuera skrivare med hjälp av ett anpassat PowerShell-skript och har förberett utskriftsresurserna följer du de här stegen för att distribuera delade skrivare:

1.  Gå till Microsoft Managed Desktop-portalen.
2.  Skicka en begäran med etiketten *Skrivardistribution* i **avsnittet Support > supportförfrågningar** i administrationsportalen med följande information:
    - Alla UNC-sökvägar till delade skrivarplatser som måste distribueras för Microsoft Managed Desktop-enheter
    - Användargrupper som kräver åtkomst till dessa delade skrivare
3.  I administrationsportalen meddelas du när begäran har slutförts. Först distribuerar vi bara konfigurationen till enheter i testdistributionsgruppen.
4.  Du måste testa och bekräfta om konfigurationen fungerar som förväntat. Svara genom att använda **fliken** Diskussion i supportbegäran och meddela oss när du har slutfört testningen.
5.  Sedan distribuerar vi konfigurationen till andra distributionsgrupper.