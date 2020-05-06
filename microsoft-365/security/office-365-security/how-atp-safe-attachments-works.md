---
title: Så fungerar ATP – säkra bifogade filer
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du skyddar organisationen från skadliga filer med ATP-säkra bilagor för Office 365.
ms.openlocfilehash: a0d5923ccac525b23aa2ef6b45936524f0a7b483
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036662"
---
# <a name="how-atp-safe-attachments-works"></a>Så fungerar ATP – säkra bifogade filer

## <a name="how-it-works"></a>Så här fungerar det

Funktionen Betrodda atp-bilagor kontrollerar e-postbilagor för personer i organisationen. När en ATP-princip för säkra bilagor finns på plats och någon som omfattas av den principen visar sin e-post i Office 365 kontrolleras deras e-postbilagor och lämpliga åtgärder vidtas, baserat på dina ATP-principer för säkra bilagor. Beroende på hur dina principer definieras kan användarna fortsätta arbeta utan att någonsin veta att de har skickats skadliga filer.
  
Här är två exempel på ATP Säkra bilagor på jobbet.
  
- **Exempel 1: Bifogad e-post** Anta att Lee får ett e-postmeddelande som har en bifogad fil. Det är inte självklart att Lee om denna bilaga är säker eller faktiskt innehåller skadlig kod för att stjäla Lees användaruppgifter. I Lees organisation definierade en säkerhetsadministratör en ATP Safe Attachments-princip för några dagar sedan. Med funktionen BETRODDa ATP-bilagor öppnas och testas e-postbilagan i en virtuell miljö innan Lee tar emot den. Om den bifogade filen bedöms vara skadlig tas den bort automatiskt. Om bilagan är säker öppnas den som förväntat när Lee klickar på den.

- **Exempel 2: Fil i SharePoint Online** Anta att Jean tog emot en fil och laddade upp den till ett bibliotek i SharePoint Online. Jean delar länken till filen med resten av teamet, utan att veta att filen faktiskt är skadlig. Lyckligtvis identifierar [ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) den skadliga filen och blockerar den. Några dagar senare öppnar Chris dokumentet. Även om Chris kan se att filen finns där, kan Chris inte öppna eller dela den, vilket skyddar Chris dator och andra från den skadliga filen.

ATP Principer för säkra bilagor kan tillämpas på specifika personer eller grupper i organisationen eller på hela domänen. Dessutom kan ATP-principer för säkra bifogade filer konfigureras för att använda platshållarbilagor medan faktiska bilagor genomsöks. Mer information finns i **[Konfigurera principer för betrodda bifogade filer i Office 365.](set-up-atp-safe-attachments-policies.md)**

> [!NOTE]
> ATP-skanning av säkra bilagor sker i samma region där dina data finns. Mer information om datacentergeografi finns i [Var finns dina data?](https://products.office.com/where-is-your-data-located?geo=All) 

