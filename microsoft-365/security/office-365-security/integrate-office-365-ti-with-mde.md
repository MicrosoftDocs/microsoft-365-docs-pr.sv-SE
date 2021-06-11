---
title: Använda Microsoft Defender för Office 365 tillsammans med Microsoft Defender för Endpoint
f1.keywords:
- NOCSH
keywords: integrera, Microsoft Defender, Microsoft Defender för Slutpunkt
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Använd Microsoft Defender för Office 365 microsoft Defender för slutpunkt om du vill få mer detaljerad information om hot mot dina enheter och e-postinnehåll.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63ae9f8c1136a973e4fccb63ecfbaee2639c3f6f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904086"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Använda Microsoft Defender för Office 365 tillsammans med Microsoft Defender för Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender för Office 365](defender-for-office-365.md) kan konfigureras för att fungera med [Microsoft Defender för slutpunkt.](/windows/security/threat-protection)

Genom att integrera Microsoft Defender för Office 365 med Microsoft Defender för Endpoint kan du hjälpa dina säkerhetsåtgärder att övervaka teamet och vidta åtgärder snabbt om användarnas enheter är på risk. När integration har aktiverats kan teamet för säkerhetsåtgärder till exempel se de enheter som eventuellt påverkas av ett upptäckt e-postmeddelande, samt hur många aviseringar som nyligen har genererats för dessa enheter i Microsoft Defender för Slutpunkt.

I följande bild visas hur fliken **Enheter ser** ut när du har aktiverat Microsoft Defender för slutpunktsintegrering:

![När Microsoft Defender för slutpunkt är aktiverat visas en lista över enheter med aviseringar.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

I det här exemplet kan du se att mottagarna av det identifierade e-postmeddelandet har fyra enheter och en har en avisering. Om du klickar på länken för en enhet öppnas sidan [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (tidigare Microsoft Defender Säkerhetscenter).

> [!TIP]
> Defender Microsoft 365 portalen ersätter den Microsoft Defender Säkerhetscenter. Se [Microsoft Defender för slutpunkt i Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).

## <a name="requirements"></a>Krav

- Din organisation måste ha Microsoft Defender för Office 365 (eller Office 365 E5) och Microsoft Defender för Slutpunkt.

- Du måste vara global administratör eller ha en säkerhetsadministratörsroll (till exempel säkerhetsadministratör) som tilldelats Microsoft 365. (Se [Behörigheter i säkerhets- & Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md))

- Du måste ha tillgång [till Utforskaren (eller identifieringar i realtid).](threat-explorer.md)

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Integrera Microsoft Defender för Office 365 med Microsoft Defender för Slutpunkt

Integrering av Microsoft Defender för Office 365 med Microsoft Defender för slutpunkt konfigureras i både Defender för Slutpunkt och Defender för Office 365.

1. Som global administratör eller säkerhetsadministratör går du till [https://protection.office.com](https://protection.office.com) och loggar in. (Då kommer du till Office 365 Säkerhets- & Efterlevnadscenter.)

2. Välj Hothanteringsutforskaren **i** \> **navigeringsfönstret.**

   ![Utforskaren på menyn Hantering av hot](../../media/ThreatMgmt-Explorer-nav.png)

3. Välj Defender för Endpoint Inställningar **(MDE-Inställningar) i skärmens övre högra Inställningar.**

4. I dialogrutan Microsoft Defender för slutpunktsanslutning aktiverar du Microsoft **Defender Anslut microsoft Defender för slutpunkt.**

   ![Microsoft Defender för Slutpunktsanslutning](../../media/Explorer-WDATPConnection-dialog.png)

5. Gå till Microsoft 365 Defender-portalen ( [https://security.microsoft.com](https://security.microsoft.com) .

6. I navigeringsfältet väljer **du Inställningar**. Välj sedan **Avancerade funktioner** under **Allmänt.**

7. Rulla ned **till Office 365 Threat Intelligence-anslutning** och aktivera anslutningen.

   ![Office 365 för hotinformation](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>Relaterade artiklar

[Funktioner för undersökning av hot och svar i Office 365](office-365-ti.md)

[Microsoft Defender för Office 365](defender-for-office-365.md)

[Microsoft Defender för Endpoint](/windows/security/threat-protection)
