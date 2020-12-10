---
title: Använda Microsoft Defender för Office 365 tillsammans med Microsoft Defender för slut punkten
f1.keywords:
- NOCSH
keywords: integrering, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Använd Microsoft Defender för Office 365 tillsammans med Microsoft Defender för slut punkt för att få mer detaljerad information om hot mot dina enheter och e-postinnehåll.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8cc78e7d674facb371ea98125b6857502031d26e
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616518"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Använda Microsoft Defender för Office 365 tillsammans med Microsoft Defender för slut punkten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender för Office 365](office-365-atp.md) kan konfigureras så att det fungerar med [Microsoft Defender för slut punkten](https://docs.microsoft.com/windows/security/threat-protection).

Att integrera Microsoft Defender för Office 365 med Microsoft Defender för slut punkten kan hjälpa din säkerhets åtgärds grupp övervakning och vidta åtgärder snabbt om användarnas enheter löper risk. När integrationen är aktive rad kan till exempel din säkerhets åtgärds grupp se vilka enheter som eventuellt påverkas av ett identifierat e-postmeddelande, samt hur många senaste aviseringar som genererades för dessa enheter i Microsoft Defender för slut punkter.

I följande bild visas hur fliken **enheter** ser ut som har Microsoft Defender för slut punkts integrering aktiverat:

![När Microsoft Defender för slut punkt är aktiverat kan du se en lista med enheter med aviseringar.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

I det här exemplet kan du se att mottagarna av det identifierade e-postmeddelandet har fyra enheter och en har en avisering. Om du klickar på länken för en enhet öppnas den i Microsoft Defender säkerhets Center ( <https://securitycenter.windows.com> ).

> [!TIP]
> **[Läs mer om Microsoft Defender säkerhets Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (kallas även Microsoft Defender för slut punkts Portal).

## <a name="requirements"></a>Krav

- Din organisation måste ha Microsoft Defender för Office 365 (eller Office 365 E5) och Microsoft Defender för slut punkt.

- Du måste vara global administratör eller ha en säkerhets administratörs roll (till exempel säkerhets administratör) som tilldelats i [säkerhets & Compliance Center](https://protection.office.com). (Se [behörigheter i säkerhets & kompatibilitetskontrollen](permissions-in-the-security-and-compliance-center.md))

- Du måste ha till gång till både [Explorer (eller real tids identifieringar)](threat-explorer.md) i säkerhets & efterlevnaden för säkerhet och Microsoft Defender säkerhets Center.

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Integrera Microsoft Defender för Office 365 med Microsoft Defender för slut punkt

Att integrera Microsoft Defender för Office 365 med Microsoft Defender för slut punkten är inställt på både säkerhets & och Microsoft Defender säkerhets Center.

1. Som global administratör eller säkerhets administratör går du till <https://protection.office.com> och loggar in. (Du kommer till Office 365 Security & Compliance Center.)

2. Välj **Threat Management** \> **Explorer** i navigerings fönstret.

   ![Utforskaren i Threat Management-menyn](../../media/ThreatMgmt-Explorer-nav.png)

3. I det övre högra hörnet på skärmen väljer du **Defender för slut punkts inställningar**.

4. I dialog rutan Microsoft Defender för slut punkts anslutning aktiverar **du Anslut till Microsoft Defender för slut punkt**.

   ![Microsoft Defender för slut punkts anslutning](../../media/Explorer-WDATPConnection-dialog.png)

5. Gå till Microsoft Defender säkerhets Center ( <https://securitycenter.windows.com> ).

6. I navigerings fältet väljer du **Inställningar**. Under **Allmänt** väljer du **avancerade funktioner**.

7. Rulla ned till **Office 365 Threat Intelligence-anslutning** och slå på anslutningen.

   ![Anslutning till Office 365 Threat Intelligence](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>Relaterade artiklar

[Hot-och svars funktioner i Office 365](office-365-ti.md)

[Microsoft Defender för Office 365](office-365-atp.md)

[Microsoft Defender för slut punkt](https://docs.microsoft.com/windows/security/threat-protection)
