---
title: Viktig information om efterlevnadsstöd för Microsoft 365 för teckenuppsättning med dubbel byte ( förhandsversion)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Viktig information om stöd för teckenuppsättningar med dubbla byte.
ms.openlocfilehash: 1c2244c49a92aa2c00fad06caa8194cf7e32220e
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/22/2020
ms.locfileid: "52161629"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a>Viktig information om stöd för teckenuppsättning med dubbel byte (förhandsversion)

 Microsoft 365 Information Protection har nu stöd för teckenuppsättningsspråk med dubbla byte i förhandsgranskning för:

- Kinesiska (förenklad)
- Kinesiska (traditionell)
- Korean
- Japanese

Det här stödet är tillgängligt för känsliga informationstyper och nyckelordsordlistor och kommer att återspeglas i dataförlustskydd, kommunikationsefterlevnad, Exchange Online, SharePoint Online, OneDrive för företag och Teams-lösningar.

## <a name="known-issues"></a>Kända problem

- När en textfil som bifogats i ett e-postmeddelande är i UTF-8-format utan byteordningsmärke (BOM), identifieras inte e-postmeddelandet av principen för kommunikationsefterlevnad.

- Principer för kommunikationsefterlevnad kan inte identifiera värden om en mening angetts för principvillkoret: "Meddelandet innehåller något av dessa ord". Om den text som anges i principen är skriven som ett ord kan den identifieras; men om den är skriven mitt i en mening identifieras den inte.

- Principer för kommunikationsefterlevnad som anger ordlistor som typinformation identifierar inte Teams privata chattar och kanalchattar.

- Följande villkor stöds inte för kommunikationsefterlevnad i det här skedet (vi planerar att åtgärda problemen i framtiden): 
  - "Meddelandet innehåller något av dessa ord"
  - "Meddelandet innehåller inget av dessa ord"
  - "Bifogad fil innehåller något av dessa ord"
  - "Bifogad fil innehåller något av dessa ord"

I stället rekommenderar vi att du skapar en anpassad typ av känslig information (SIT: Sensitive Information Type) med nyckelordsordlista som identifierar mönster i meddelanden och bilagor, och använder detta anpassade SIT som ett villkor för principen om kommunikation efterlevnad.
