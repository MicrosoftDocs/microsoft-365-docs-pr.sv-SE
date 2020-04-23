---
title: 'Steg 5: Konfigurera dataförlustskydd'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå och distribuera dataförlustskydd i Microsoft 365.
ms.openlocfilehash: e3d18bf54ecdfe11f8233163e7f200a70606d81d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636982"
---
# <a name="step-5-configure-data-loss-prevention"></a>Steg 5: Konfigurera dataförlustskydd

*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*

![Fas 6: Informationsskydd](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Med principer för dataförlustskydd (DLP) i Säkerhets- och efterlevnadscenter kan du identifiera, övervaka och automatiskt skydda känslig information i Microsoft 365. Med DLP-principer kan du göra följande:

- Identifiera känslig information på många platser, till exempel Exchange Online, SharePoint Online, OneDrive för företag och Microsoft Teams.
- Förhindra oavsiktlig delning av känslig information genom att blockera åtkomst till ett dokument eller blockera e-postmeddelandet som innehåller det.
- Övervaka och skydda känslig information i skrivbordsversionerna av Excel, PowerPoint och Word.
- Hjälpa användare att upprätthålla efterlevnaden utan att avbryta arbetsflödet med e-postmeddelanden och policytips. 
- Visa DLP-rapporter som visar innehåll som överensstämmer med din organisations DLP-principer.

En DLP-princip anger:

- **Var:** Platser som Exchange Online, SharePoint Online, OneDrive för företag-webbplatser och Microsoft Teams-chattar och kanaler.
- **När:** Villkor som innehållet måste matcha i en specifik policyregel.
- **Hur:** Åtgärder i matchningspolicyregeln som automatiskt ska utföras för matchningsvillkoren.

Med andra ord:

- För ett dokument på den här platsen (var), om innehållet överensstämmer med villkoren för en regel (när), ska åtgärderna som anges i regeln automatiskt utföras (hur).

Om du vill fastställa vilken uppsättning DLP-principer du behöver måste du analysera dina dokument och de datatyper i dem som måste skyddas från dataförlust. Om du till exempel arbetar i en finansorganisation i USA kan du skapa en DLP-princip som hindrar att dokument med socialförsäkringsnummer delas utanför organisationen eller skickas via e-post till platser utanför organisationen.

Därefter konfigurerar och testar du principerna med testplatser för att säkerställa korrekt DLP-beteende och minimera falska positiva identifieringar.

Slutligen kan du distribuera det i din organisation genom att informera medarbetarna om de nya principerna och deras önskade beteende och bredda omfånget för platserna.

Mer information finns i [Kom igång med DLP-principrekommendationer](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).

Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](infoprotect-exit-criteria.md#crit-infoprotect-step5) som motsvarar det här steget.

## <a name="next-step"></a>Nästa steg

|||
|:-------|:-----|
|![Steg 6](../media/stepnumbers/Step6.png)|[Konfigurera e-postkryptering](infoprotect-email-encryption.md)|


