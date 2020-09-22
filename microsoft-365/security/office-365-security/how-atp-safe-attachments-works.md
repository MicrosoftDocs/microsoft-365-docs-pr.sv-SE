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
description: Lär dig hur du kan skydda din organisation från skadliga filer med hjälp av säkra bifogade filer för Office 365.
ms.openlocfilehash: d13674a5d3e769fc10a1f5fd2fd80a4f07c063de
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201483"
---
# <a name="how-atp-safe-attachments-works"></a>Så fungerar ATP – säkra bifogade filer

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Med funktionen för säker e-poståtkomst för ATP kontrol leras användarna i din organisation. När det finns en princip för att skydda ett ATP-filer på plats och någon som täcks av den policyn visar deras e-post i Office 365, kontrol leras deras e-postbilagor och lämpliga åtgärder vidtas, baserat på dina principer för säker åtkomst Beroende på hur dina principer är definierade kan andra fortsätta att arbeta utan att veta att de har skickat skadliga filer.
  
Här är två exempel på säkra filer för ATP-säkerhet på jobbet.
  
- **Exempel 1: e-postbilaga** Antag att Aaron Lee får ett e-postmeddelande med en bifogad fil. Det är inte uppenbart för Aaron Lee om den bifogade filen är säker eller om den faktiskt innehåller skadlig program vara som är utformad för att stjäla Aaron Lee. I Aaron Lee organisation är en säkerhets administratör som har definierat en policy för säkerhet för ATP-filer för antal dagar sedan. Med funktionen för säker e-postbilagor öppnas och testas den bifogade filen i en virtuell miljö innan Aaron Lee tas emot. Om den bifogade filen bedöms vara skadlig tas den bort automatiskt. Om den bifogade filen är säker öppnas den som förväntat när Aaron Lee klickar på den.

- **Exempel 2: fil i SharePoint Online** Antag att Jean har tagit emot en fil och ladda upp den till ett bibliotek i SharePoint Online. Jean delar länken till filen med resten av gruppen, och vet inte att filen faktiskt är skadlig. Lyckligt vis kommer [ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) att identifiera den skadliga filen och blockera den. Ett par dagar senare kan Chris öppna dokumentet. Men Chris kan se att filen är där kan Chris inte öppna eller dela den, vilket skyddar Chris användare från den skadliga filen.

Säkerhets principer för ATP-säkerhet kan användas för vissa personer eller grupper i din organisation eller till hela domänen. Dessutom kan principer för säkra bifogade filer för ATP konfigureras för användning av bifogade filer för plats hållare när faktiska bilagor skannas. Mer information finns i **[Konfigurera principer för säkrade säkerhets meddelanden för ATP i Office 365](set-up-atp-safe-attachments-policies.md)**.

> [!NOTE]
> ATP Safe Attachments scanning sker i samma region där dina data finns. Mer information om data Center geografi finns i [var finns dina data?](https://products.office.com/where-is-your-data-located?geo=All) 

