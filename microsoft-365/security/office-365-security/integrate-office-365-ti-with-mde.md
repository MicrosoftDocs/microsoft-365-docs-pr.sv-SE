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
ms.openlocfilehash: fed3a04a7a699b4689cd9d6d9d335a8ba51d2fd8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083386"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Använda Microsoft Defender för Office 365 tillsammans med Microsoft Defender för Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender för Office 365](defender-for-office-365.md) kan konfigureras för att fungera med [Microsoft Defender för slutpunkt.](/windows/security/threat-protection)

Genom att integrera Microsoft Defender för Office 365 med Microsoft Defender för Endpoint kan du hjälpa dina säkerhetsåtgärder att övervaka teamet och vidta åtgärder snabbt om användarnas enheter är på risk. När integration har aktiverats kan teamet för säkerhetsåtgärder till exempel se de enheter som eventuellt påverkas av ett upptäckt e-postmeddelande, samt hur många aviseringar som nyligen har genererats för dessa enheter i Microsoft Defender för Slutpunkt.

I följande bild visas hur fliken **Enheter ser** ut när du har aktiverat Microsoft Defender för slutpunktsintegrering:

![När Microsoft Defender för slutpunkt är aktiverat visas en lista över enheter med aviseringar.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

I det här exemplet kan du se att mottagarna av det identifierade e-postmeddelandet har fyra enheter och en har en avisering. När du klickar på länken för en enhet öppnas sidan i [Microsoft 365 Defender (tidigare](../defender-endpoint/microsoft-defender-security-center.md) Microsoft Defender säkerhetscenter).

> [!TIP]
> Den Microsoft 365 Defender portalen ersätter Microsoft Defender Säkerhetscenter. Se [Microsoft Defender för Slutpunkt i Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).

## <a name="requirements"></a>Krav

- Din organisation måste ha Microsoft Defender för Office 365 (eller Office 365 E5) och Microsoft Defender för Slutpunkt.

- Du måste vara global administratör eller ha en säkerhetsadministratörsroll (till exempel säkerhetsadministratör) som tilldelats Microsoft 365. Mer information finns under [Behörigheter på Microsoft 365 Defender-portalen](permissions-microsoft-365-security-center.md).

- Du måste ha tillgång [till Utforskaren (eller identifieringar i realtid).](threat-explorer.md)

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Integrera Microsoft Defender för Office 365 med Microsoft Defender för Slutpunkt

Integrering av Microsoft Defender för Office 365 med Microsoft Defender för slutpunkt konfigureras i både Defender för Slutpunkt och Defender för Office 365.

1. Som global administratör eller säkerhetsadministratör öppnar du Microsoft 365 Defender portalen () och går till Skicka <https://security.microsoft.com> **e-& för samarbete** \> **i Utforskaren.** Om du vill gå direkt till **sidan i Utforskaren** använder du <https://security.microsoft.com/threatexplorer> .

2. På sidan **Utforskaren** går du till det övre högra hörnet på skärmen och klickar på **MDE Inställningar**.

3. I den **utfällna** menyn för Microsoft Defender för slutpunktsanslutning som visas aktiverar du **Anslut Microsoft Defender** för slutpunkt (växlingsknapp på) och klickar sedan på ![ ](../../media/scc-toggle-on.png) ![ Stäng-ikonen ](../../media/m365-cc-sc-close-icon.png) **Stäng.**

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="MDE-anslutning":::

4. I navigeringsfönstret väljer du **Inställningar**. På **Inställningar** väljer du **Slutpunkter**

5. På sidan **Slutpunkter** som öppnas väljer du **Avancerade funktioner.**

6. Rulla ned till **Office 365 Threat Intelligence-anslutning** och aktivera den ![ (växlingsknapp ](../../media/scc-toggle-on.png) på ).

   När du är klar klickar du på **Spara inställningar.**

## <a name="related-articles"></a>Relaterade artiklar

[Funktioner för undersökning av hot och svar i Office 365](office-365-ti.md)

[Microsoft Defender för Office 365](defender-for-office-365.md)

[Microsoft Defender för Endpoint](/windows/security/threat-protection)
