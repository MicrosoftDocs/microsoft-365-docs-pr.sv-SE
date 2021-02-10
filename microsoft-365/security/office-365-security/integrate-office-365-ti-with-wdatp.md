---
title: Använda Microsoft Defender för Office 365 tillsammans med Microsoft Defender för Slutpunkt
f1.keywords:
- NOCSH
keywords: integrate, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Använd Microsoft Defender för Office 365 tillsammans med Microsoft Defender för Slutpunkt för att få mer detaljerad information om hot mot dina enheter och e-postinnehåll.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 035834e1e4855c0e47defed06043a5fdbd0e63bd
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166093"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Använda Microsoft Defender för Office 365 tillsammans med Microsoft Defender för Slutpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender för Office 365](office-365-atp.md) kan konfigureras för att fungera med [Microsoft Defender för Slutpunkt.](https://docs.microsoft.com/windows/security/threat-protection)

Genom att integrera Microsoft Defender för Office 365 med Microsoft Defender för Endpoint kan ditt säkerhetsåtgärdsteam övervaka och vidta åtgärder snabbt om användarnas enheter är på risk. När integreringen har aktiverats kan ditt säkerhetsteam till exempel se vilka enheter som eventuellt påverkas av ett upptäckt e-postmeddelande, samt hur många aviseringarna som genererats för dessa enheter i Microsoft Defender för Endpoint.

I följande bild visas hur fliken **Enheter ser** ut när du har Aktiverat Microsoft Defender för slutpunktsintegrering:

![När Microsoft Defender för slutpunkt är aktiverat kan du se en lista med enheter med aviseringar.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

I det här exemplet kan du se att mottagarna av det identifierade e-postmeddelandet har fyra enheter och en har en avisering. När du klickar på länken för en enhet öppnas sidan i Microsoft Defender Säkerhetscenter <https://securitycenter.windows.com> ().

> [!TIP]
> **[Läs mer om Microsoft Defender Säkerhetscenter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (kallas även Microsoft Defender för Endpoint-portalen).)

## <a name="requirements"></a>Krav

- Din organisation måste ha Microsoft Defender för Office 365 (eller Office 365 E5) och Microsoft Defender för Slutpunkt.

- Du måste vara global administratör eller ha en säkerhetsadministratörsroll (till exempel säkerhetsadministratör) som tilldelats [i säkerhets- & Efterlevnadscenter.](https://protection.office.com) (Se [behörigheter i Säkerhets- & Efterlevnadscenter)](permissions-in-the-security-and-compliance-center.md)

- Du måste ha åtkomst till både [Utforskaren (eller](threat-explorer.md) identifieringar i realtid) i Säkerhets- & och Microsoft Defender Säkerhetscenter.

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Integrera Microsoft Defender för Office 365 med Microsoft Defender för Slutpunkt

Integrering av Microsoft Defender för Office 365 med Microsoft Defender för Slutpunkt konfigureras med hjälp av både Säkerhets- & Efterlevnadscenter OCH Microsoft Defender Säkerhetscenter.

1. Som global administratör eller säkerhetsadministratör går du till <https://protection.office.com> och loggar in. (Då kommer du till Säkerhets- och & Office 365.)

2. Välj Hothanteringsutforskaren **i** \> **navigeringsfönstret.**

   ![Utforskaren på menyn Hothantering](../../media/ThreatMgmt-Explorer-nav.png)

3. I skärmens övre högra hörn väljer du **Defender för Slutpunktsinställningar (MDE-inställningar).**

4. I dialogrutan Anslutning till Microsoft Defender för slutpunkt aktiverar du **Anslut till Microsoft Defender för Slutpunkt.**

   ![Anslutning till Microsoft Defender för slutpunkt](../../media/Explorer-WDATPConnection-dialog.png)

5. Gå till Microsoft Defender Säkerhetscenter <https://securitycenter.windows.com> ().

6. Välj Inställningar i **navigeringsfältet.** Välj sedan **Avancerade** funktioner under **Allmänt.**

7. Rulla ned till **Office 365 Threat Intelligence-anslutningen** och aktivera anslutningen.

   ![Office 365 Threat Intelligence-anslutning](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>Relaterade artiklar

[Funktioner för undersökning av hot och svar i Office 365](office-365-ti.md)

[Microsoft Defender för Office 365](office-365-atp.md)

[Microsoft Defender för Endpoint](https://docs.microsoft.com/windows/security/threat-protection)
