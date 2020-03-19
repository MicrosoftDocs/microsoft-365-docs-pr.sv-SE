---
title: Integrera Office 365 Avancerat hotskydd med Microsoft Defender Avancerat hotskydd
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/22/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Integrera Office 365 Advanced Threat Protection med Microsoft Defender Advanced Threat Protection för att se mer detaljerad information om hothantering.
ms.openlocfilehash: 8096a950e66ed94d6e056f40b737d89d48cb811e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805444"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>Integrera Office 365 Avancerat hotskydd med Microsoft Defender Avancerat hotskydd

Om du ingår i organisationens säkerhetsteam kan du integrera [Office 365 Advanced Threat Protection](office-365-atp.md) och relaterade utrednings- och svarsfunktioner med Microsoft Defender Advanced Threat [Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection). Detta kan hjälpa dig att snabbt förstå om användarnas datorer är i riskzonen när du undersöker hot i Office 365. När integreringen har aktiverats kan du till exempel se en lista över datorer som används av mottagarna av ett upptäckt e-postmeddelande, samt hur många senaste aviseringar dessa datorer har i Microsoft Defender Advanced Threat Protection.
  
Följande bild visar fliken **Enheter** som visas när microsoft Defender ATP-integrering är aktiverad:
  
![När Microsoft Defender ATP är aktiverat kan du se en lista över datorer med aviseringar.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
I det här exemplet kan du se att mottagarna av e-postmeddelandet har fyra enheter och en har en avisering. Om du klickar på länken för en enhet öppnas sidan i Microsoft Defender Security Center.
  
## <a name="requirements"></a>Krav

- Din organisation måste ha Office 365 ATP Plan 2 (eller Office 365 E5) och Microsoft Defender ATP.
    
- Du måste vara en Global Office 365-administratör eller ha en säkerhetsadministratörsroll (till exempel säkerhetsadministratör) som är tilldelad i [Security &amp; Compliance Center](https://protection.office.com). (Se [Behörigheter i &amp; Säkerhetsefterlevnadscenter för Office 365](permissions-in-the-security-and-compliance-center.md))
    
- Du måste ha tillgång till både [Explorer (eller realtidsidentifieringar)](threat-explorer.md) i Security & Compliance Center och Microsoft Defender Security Center.
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>Så här integrerar du Office 365 ATP med Microsoft Defender ATP

Integrering av Office 365 ATP med Microsoft Defender ATP konfigureras med både Security & Compliance Center och Microsoft Defender Security Center.
  
1. Som en global Office 365-administratör eller [https://protection.office.com](https://protection.office.com) en säkerhetsadministratör går du till och loggar in med ditt arbets- eller skolkonto för Office 365.
    
2. Välj **Explorer** **för hothantering** \> .<br>![Explorer i menyn Hothantering](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. Välj **WDATP-inställningar**i det övre högra hörnet av skärmen .
    
4. Aktivera Anslut till Windows ATP i dialogrutan Windows Defender ATP-anslutning.<br>![Microsoft Defender ATP-anslutning](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Aktivera anslutningen i Microsoft Defender Security Center.

  
## <a name="related-topics"></a>Relaterade ämnen

[Office 365 Hotutredning och svar](office-365-ti.md)
  
[Office 365 Avancerat hotskydd](office-365-atp.md)
  

