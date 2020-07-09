---
title: Integrera Office 365 ATP med Microsoft Defender Avancerat skydd
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/08/2020
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bfb87edd24a22033b3771ba0fd3c4f1afbbc988e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086721"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>Integrera avancerat hotskydd för Office 365 med Microsoft Defender avancerat hotskydd

[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) kan konfigureras för att fungera med [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).

Genom att integrera Office 365 ATP med Microsoft Defender ATP kan säkerhetsoperationsteamet övervaka och vidta åtgärder snabbt om användarnas enheter är i riskzonen. När integreringen till exempel är aktiverad kan säkerhetsoperationsteamet se de enheter som kan påverkas av ett upptäckt e-postmeddelande, samt hur många aviseringar dessa enheter har nyligen i Microsoft Defender ATP. 

Följande bild visar hur fliken **Enheter** ser ut om Microsoft Defender ATP-integrering aktiverad:
  
![När Microsoft Defender ATP är aktiverat kan du se en lista över enheter med aviseringar.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
I det här exemplet kan du se att mottagarna av det identifierade e-postmeddelandet har fyra enheter och en har en avisering. Om du klickar på länken för en enhet öppnas sidan i Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

> [!TIP]
> **[Läs mer om Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (kallas även Microsoft Defender ATP-portalen.)
  
## <a name="requirements"></a>Krav

- Din organisation måste ha Office 365 ATP-abonnemang 2 (eller Office 365 E5) och Microsoft Defender ATP.
    
- Du måste vara global administratör eller ha en säkerhetsadministratörsroll (till exempel säkerhetsadministratör) tilldelad i [ &amp; Säkerhetsefterlevnadscenter](https://protection.office.com). (Se [behörigheter i &amp; Säkerhetsefterlevnadscenter](permissions-in-the-security-and-compliance-center.md))
    
- Du måste ha tillgång till både [Explorer (eller realtidsidentifieringar)](threat-explorer.md) i Security & Compliance Center och Microsoft Defender Security Center.
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>Så här integrerar du Office 365 ATP med Microsoft Defender ATP

Integrering av Office 365 ATP med Microsoft Defender ATP konfigureras med både Security & Compliance Center och Microsoft Defender Security Center.
  
1. Som global administratör eller säkerhetsadministratör går du till [https://protection.office.com](https://protection.office.com) och loggar in. (Detta tar dig till Säkerhets- & Compliance Center för Office 365.)
    
2. Välj **Hothanteringsutforskaren**i navigeringsfönstret  >  **Explorer**.<br>![Explorer på menyn Hothantering](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. I det övre högra hörnet av skärmen väljer du **WDATP-inställningar**.
    
4. Aktivera **Anslut till Windows ATP**i dialogrutan Microsoft Defender ATP-anslutning .<br>![Microsoft Defender ATP-anslutning](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Gå till Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

6. Välj **Inställningar**i navigeringsfältet . Välj sedan Avancerade **funktioner**under **Allmänt**.

7. Bläddra ned till **Office 365 Threat Intelligence-anslutning**och aktivera anslutningen.<br/>![Informationsanslutning till Hotinformation i Office 365](../../media/mdatp-oatptoggle.png)<br>

## <a name="related-articles"></a>Relaterade artiklar

[Funktioner för utredning och svar av hot i Office 365](office-365-ti.md)
  
[Office 365 Avancerat skydd](office-365-atp.md)
  
[Microsoft Defender Avancerat skydd.](https://docs.microsoft.com/windows/security/threat-protection)
