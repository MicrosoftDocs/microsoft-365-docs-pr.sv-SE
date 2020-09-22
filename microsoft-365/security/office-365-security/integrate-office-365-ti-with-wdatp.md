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
description: Integrera Office 365 Avancerat skydd med Microsoft Defender Avancerat skydd för att visa mer detaljerad information om Threat Management.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0906b8b44922084a65999dd9ab10a09c827605c2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201977"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>Integrera Office 365 Avancerat skydd med Microsoft Defender Avancerat skydd

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Office 365 Avancerat skydd](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) kan konfigureras så att det fungerar med [Microsoft Defender Avancerat skydd](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).

Integrering av Office 365 ATP med Microsoft Defender ATP kan hjälpa din säkerhets åtgärds grupp övervakning och vidta åtgärder snabbt om användarnas enheter löper risk. När integrationen är aktive rad kan till exempel din säkerhets åtgärds grupp se vilka enheter som eventuellt påverkas av ett identifierat e-postmeddelande, samt hur många aviseringar om dessa enheter har i Microsoft Defender ATP. 

Följande bild visar vad fliken **enheter** ser ut som har Microsoft Defender ATP-integrering aktive rad:
  
![När Microsoft Defender ATP är aktiverat kan du se en lista med enheter med aviseringar.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
I det här exemplet kan du se att mottagarna av det identifierade e-postmeddelandet har fyra enheter och en har en avisering. Om du klickar på länken för en enhet öppnas den i Microsoft Defender säkerhets Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

> [!TIP]
> **[Läs mer om Microsoft Defender säkerhets Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (kallas även Microsoft Defender ATP-portalen.)
  
## <a name="requirements"></a>Krav

- Din organisation måste ha Office 365 ATP-abonnemang 2 (eller Office 365 E5) och Microsoft Defender ATP.
    
- Du måste vara global administratör eller ha en säkerhets administratörs roll (till exempel säkerhets administratör) som är tilldelad i [ &amp; Säkerhetscenter](https://protection.office.com). (Se [behörigheter i säkerhets &amp; kontroll Center](permissions-in-the-security-and-compliance-center.md))
    
- Du måste ha till gång till både [Explorer (eller real tids identifieringar)](threat-explorer.md) i säkerhets & efterlevnaden för säkerhet och Microsoft Defender säkerhets Center.
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>Integrera Office 365 ATP med Microsoft Defender ATP

Integrering av Office 365 ATP med Microsoft Defender ATP konfigureras med hjälp av både säkerhets & och Microsoft Defender säkerhets Center.
  
1. Som global administratör eller säkerhets administratör går du till [https://protection.office.com](https://protection.office.com) och loggar in. (Du kommer till Office 365 Security & Compliance Center.)
    
2. Välj **Threat Management**  >  **Explorer**i navigerings fönstret.<br>![Utforskaren i Threat Management-menyn](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. I det övre högra hörnet av skärmen väljer du **WDATP inställningar**.
    
4. I dialog rutan Microsoft Defender ATP-anslutning aktiverar **du Anslut till Windows ATP**.<br>![Microsoft Defender ATP-anslutning](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Gå till Microsoft Defender säkerhets Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

6. I navigerings fältet väljer du **Inställningar**. Under **Allmänt**väljer du **avancerade funktioner**.

7. Rulla ned till **Office 365 Threat Intelligence-anslutning**och slå på anslutningen.<br/>![Anslutning till Office 365 Threat Intelligence](../../media/mdatp-oatptoggle.png)<br>

## <a name="related-articles"></a>Relaterade artiklar

[Hot-och svars funktioner i Office 365](office-365-ti.md)
  
[Office 365 Avancerat skydd](office-365-atp.md)
  
[Microsoft Defender Avancerat skydd](https://docs.microsoft.com/windows/security/threat-protection)
