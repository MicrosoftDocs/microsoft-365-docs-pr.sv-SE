---
title: Förbereda utskriftsresurser för Microsoft Hanterat skrivbord
description: Viktiga steg för att se till att utskriften fungerar smidigt
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 971644aafabda733bf745fae278bdfeeed3282e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574553"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Förbereda utskriftsresurser för Microsoft Hanterat skrivbord

När du gör dig redo att registrera dig Microsoft Hanterat skrivbord bör du utvärdera dina utskriftskrav och bestämma rätt metod för din miljö. Det finns tre alternativ:
 
- Distribuera Microsofts universalutskriftslösning för att göra det enkelt Microsoft Hanterat skrivbord att identifiera skrivare. Mer information finns i Vad [är Universell utskrift.](/universal-print/fundamentals/universal-print-whatis)
- Distribuera skrivare direkt med hjälp av ett anpassat PowerShell-skript. Följ anvisningarna i [avsnittet Konfigurera lokala](#set-up-local-printers) skrivare.
- Använd en lösning som inte är en Microsoft-lösning för molnutskrift som är Windows 10 enheter som är anslutna till en Azure Active Directory domän. Lösningen måste uppfylla programvarukraven för Microsoft Hanterat skrivbord. Mer information finns i Microsoft Hanterat skrivbord [för appar.](../service-description/mmd-app-requirements.md)
 
I samtliga fall om skrivardrivrutinerna inte är tillgängliga från Microsoft Update eller Microsoft Store måste du själv hämta dem och paketera dem för distribution till dina Microsoft Hanterat skrivbord-enheter med Microsoft Intune. Mer information finns i [Fristående Intune – Win32-apphantering](/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Konfigurera lokala skrivare

Om du har bestämt dig för att distribuera skrivare med hjälp av ett anpassat PowerShell-skript och har förberett utskriftsresurserna följer du de här stegen för att distribuera delade skrivare:

1.  Gå till Microsoft Hanterat skrivbord portalen.
2.  Skicka en begäran med etiketten *Skrivardistribution* i **avsnittet Support > supportförfrågningar** i administrationsportalen med följande information:
    - Alla UNC-sökvägar till delade skrivarplatser som måste distribueras för Microsoft Hanterat skrivbord enheter
    - Användargrupper som kräver åtkomst till dessa delade skrivare
3.  I administrationsportalen meddelas du när begäran har slutförts. Först distribuerar vi bara konfigurationen till enheter i testdistributionsgruppen.
4.  Du måste testa och bekräfta om konfigurationen fungerar som förväntat. Svara genom att använda **fliken** Diskussion i supportbegäran och meddela oss när du har slutfört testningen.
5.  Sedan distribuerar vi konfigurationen till andra distributionsgrupper.

## <a name="steps-to-get-ready"></a>Steg för att förbereda dig

1. Granska [Krav för Microsoft Hanterat skrivbord](prerequisites.md).
2. Använda [utvärderingsverktyg för beredskap](readiness-assessment-tool.md).
3. [Förutsättningar för gästkonton](guest-accounts.md)
4. [Nätverkskonfiguration för Microsoft Hanterat skrivbord](network.md)
5. [Förbereda certifikat och nätverksprofiler för Microsoft Hanterat skrivbord](certs-wifi-lan.md)
6. [Förbereda åtkomst till lokala resurser för Microsoft Hanterat skrivbord](authentication.md)
7. [Appar i Microsoft Hanterat skrivbord](apps.md)
8. [Förbereda mappade enheter för Microsoft Hanterat skrivbord](mapped-drives.md)
9. [Förbereda utskriftsresurser för Microsoft Hanterat skrivbord](printing.md) (den här artikeln)
