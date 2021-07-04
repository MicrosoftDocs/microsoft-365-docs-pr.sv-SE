---
title: Viktig information om Microsoft 365 Efterlevnadscenter för teckenuppsättning med dubbel byte
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
ms.openlocfilehash: b7883495c5b187b98e6b0539eaa075e4f8d3af6e
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256393"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a>Viktig information om stöd för teckenuppsättning med dubbel byte (förhandsversion)

 Microsoft 365 Information Protection har nu stöd för teckenuppsättningsspråk med dubbla byte för:

- Kinesiska (förenklad)
- Kinesiska (traditionell)
- Koreanska
- Japanska

Det här stödet är tillgängligt för känsliga informationstyper och nyckelordsordlistor och kommer att återspeglas i dataförlustskydd (för Exchange Online, SharePoint Online, OneDrive för företag och Teams), kommunikationsefterlevnad, automatisk etikettering i Office-appar och Microsoft Cloud App Security.

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


