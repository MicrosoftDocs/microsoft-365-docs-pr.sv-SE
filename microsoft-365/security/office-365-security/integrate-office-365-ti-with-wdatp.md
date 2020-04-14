---
title: Integrera avancerat hotskydd för Office 365 med avancerat hotskydd för Microsoft Defender
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 04/13/2020
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
description: Integrera office 365 avancerat skydd mot hot med Microsoft Defender Advanced Threat Protection för att se mer detaljerad information om hothantering.
ms.openlocfilehash: a2634a70bdbdd21efe2c59721e5532500eb4e4cc
ms.sourcegitcommit: 4c6af6530b4997055b8e60bf532e75cbc72fb6c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2020
ms.locfileid: "43284233"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>Integrera avancerat hotskydd för Office 365 med avancerat hotskydd för Microsoft Defender

Om du ingår i organisationens säkerhetsteam kan du integrera [Office 365 Advanced Threat Protection](office-365-atp.md) och relaterade undersöknings- och svarsfunktioner med Microsoft Defender Advanced Threat [Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection). Detta kan hjälpa dig att snabbt förstå om användarnas datorer är i riskzonen när du undersöker hot i Office 365. När integreringen har aktiverats kan du till exempel se en lista över datorer som används av mottagarna av ett upptäckt e-postmeddelande, samt hur många aviseringar dessa datorer har i Microsoft Defender Advanced Threat Protection.
  
Följande bild visar fliken **Enheter** som visas när Microsoft Defender ATP-integrering är aktiverat:
  
![När Microsoft Defender ATP är aktiverat kan du se en lista över enheter med aviseringar.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
I det här exemplet kan du se att mottagarna av e-postmeddelandet har fyra enheter och en har en avisering. Om du klickar på länken för en enhet öppnas sidan i Microsoft Defender Security Center.
  
## <a name="requirements"></a>Krav

- Din organisation måste ha Office 365 ATP-abonnemang 2 (eller Office 365 E5) och Microsoft Defender ATP.
    
- Du måste vara en Global Office 365-administratör eller ha en säkerhetsadministratörsroll (till exempel säkerhetsadministratör) tilldelad i [Säkerhetsefterlevnadscenter &amp; ](https://protection.office.com). (Se [behörigheter i &amp; Säkerhetsefterlevnadscenter för Office 365)](permissions-in-the-security-and-compliance-center.md)
    
- Du måste ha tillgång till både [Explorer (eller realtidsidentifieringar)](threat-explorer.md) i Security & Compliance Center och Microsoft Defender Security Center.
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>Så här integrerar du Office 365 ATP med Microsoft Defender ATP

Integrering av Office 365 ATP med Microsoft Defender ATP konfigureras med både Office 365 Security & Compliance Center och Microsoft Defender Security Center.
  
1. Som en global Office 365-administratör eller [https://protection.office.com](https://protection.office.com) säkerhetsadministratör går du till och loggar in.
    
2. Välj **Explorer för hothantering** \> **.**<br>![Explorer på menyn Hothantering](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. I det övre högra hörnet av skärmen väljer du **WDATP-inställningar**.
    
4. Aktivera **Anslut till Windows ATP**i dialogrutan Microsoft Defender ATP-anslutning.<br>![Microsoft Defender ATP-anslutning](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Aktivera anslutningen i Microsoft Defender[https://securitycenter.windows.com](https://securitycenter.windows.com)Security Center ( ).

## <a name="related-topics"></a>Relaterade ämnen

[Hotutredning och hotsvarsfunktioner i Office 365](office-365-ti.md)
  
[Office 365 Avancerat skydd](office-365-atp.md)
  

