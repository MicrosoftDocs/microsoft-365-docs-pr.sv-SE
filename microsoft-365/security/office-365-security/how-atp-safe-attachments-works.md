---
title: Så här fungerar Office 365 ATP-säkra bilagor
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
ms.collection:
- M365-security-compliance
description: Funktionen Säkra bilagor ger tidsklicka verifiering av e-postbilagor. Använd säkra bilagor för att skydda din organisation från skadliga filer som personer skickar eller tar emot via e-post.
ms.openlocfilehash: 951f9f0e50da6ef83135f1ca8f1ad109a8e66988
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42807639"
---
# <a name="how-office-365-atp-safe-attachments-works"></a>Så här fungerar Office 365 ATP-säkra bilagor

## <a name="how-it-works"></a>Så här fungerar det

Funktionen BETRODDA BIFOGADE FILER i ATP kontrollerar e-postbilagor för personer i organisationen. När en ATP Safe Attachments-princip finns på plats och någon som omfattas av den policyn visar sin e-post i Office 365 kontrolleras deras e-postbilagor och lämpliga åtgärder vidtas, baserat på dina principer för betrodda bifogade filer på ATP. Beroende på hur dina principer definieras kan användarna fortsätta arbeta utan att någonsin veta att de skickades skadliga filer.
  
Här är två exempel på ATP Safe Attachments på jobbet.
  
- **Exempel 1: Bifogad e-post** Anta att Lee får ett e-postmeddelande som har en bifogad fil. Det är inte uppenbart för Lee om den bilagan är säker eller faktiskt innehåller skadlig kod för att stjäla Lees användaruppgifter. I Lees organisation definierade en säkerhetsadministratör en ATP Safe Attachments-princip för några dagar sedan. Med funktionen ATP Safe Attachments öppnas och testas e-postbilagan i en virtuell miljö innan Lee tar emot den. Om den bifogade filen bedöms vara skadlig tas den bort automatiskt. Om tillbehöret är säkert, kommer det att öppna som förväntat när Lee klickar på den.

- **Exempel 2: Fil i SharePoint Online** Anta att Jean tog emot en fil och laddade upp den till ett bibliotek i SharePoint Online. Jean delar länken till filen med resten av teamet, utan att veta att filen faktiskt är skadlig. Lyckligtvis upptäcker [ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) den skadliga filen och blockerar den. Några dagar senare öppnar Chris dokumentet. Även om Chris kan se att filen finns där kan Chris inte öppna eller dela den, vilket skyddar Chris dator och andra från den skadliga filen.

Principer för betrodda bifogade filer för ATP kan tillämpas på specifika personer eller grupper i organisationen eller på hela domänen. Dessutom kan ATP Safe Attachments principer konfigureras för att använda platshållarbilagor medan faktiska bilagor genomsöks. Mer information finns i **[Konfigurera principer för betrodda bifogade filer i ATP i Office 365](set-up-atp-safe-attachments-policies.md)**.

> [!NOTE]
> Sökning av betrodda bifogade filer på ATP sker i samma region där dina Office 365-data finns. Mer information om datacentergeografi finns i [Var finns dina data?](https://products.office.com/where-is-your-data-located?geo=All) 

