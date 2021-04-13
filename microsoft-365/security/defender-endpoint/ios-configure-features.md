---
title: Konfigurera Microsoft Defender för slutpunkt för iOS-funktioner
description: Här beskrivs hur du distribuerar Microsoft Defender ATP för iOS-funktioner
keywords: microsoft, defender, atp, ios, konfigurera, funktioner, ios
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0e351f6500d5076e724653d0fde1940592dd1ae5
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687491"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a>Konfigurera Microsoft Defender för slutpunkt för iOS-funktioner

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> Defender för Endpoint för iOS skulle använda en VPN för att tillhandahålla webskyddsfunktionen. Det här är inte en vanlig VPN och är en lokal/självslingande VPN som inte tar trafik utanför enheten.

## <a name="conditional-access-with-defender-for-endpoint-for-ios"></a>Villkorsstyrd åtkomst med Defender för Slutpunkt för iOS  
Microsoft Defender för Slutpunkt för iOS tillsammans med Microsoft Intune och Azure Active Directory gör det möjligt att tillämpa enhetsefterlevnad och villkorsstyrd åtkomstprincip baserat på risknivåer för enheter. Defender för Endpoint är en MTD-lösning (Mobile Threat Defense) som du kan distribuera för att utnyttja den här funktionen via Intune.

Mer information om hur du konfigurera villkorsstyrd åtkomst med Defender för slutpunkt för iOS finns [i Defender för Endpoint och Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)

## <a name="web-protection-and-vpn"></a>Web Protection och VPN

Som standard innehåller och aktiverar Defender för Slutpunkt för iOS webbskyddsfunktionen. [Webbskydd](web-protection-overview.md) hjälper till att skydda enheter mot webbhot och skyddar användare mot nätfiskeattacker. Defender för Endpoint för iOS använder en VPN för att tillhandahålla detta skydd. Observera att det här är en lokal VPN och till skillnad från traditionell VPN skickas inte nätverkstrafik utanför enheten.

När den är aktiverad som standard kan det finnas fall där du måste inaktivera VPN. Du kanske till exempel vill köra vissa appar som inte fungerar när en VPN konfigureras. I sådana fall kan du välja att inaktivera VPN från appen på enheten genom att följa stegen nedan:

1. På din iOS-enhet öppnar du **appen Inställningar,** klickar eller trycker på **Allmänt** och sedan **VPN.**
1. Klicka eller tryck på i-knappen för Microsoft Defender ATP.
1. Inaktivera VPN **genom att stänga av** Anslut på begäran.

    > [!div class="mx-imgBorder"]
    > ![VPN-konfiguration ansluter på begäran](images/ios-vpn-config.png)

> [!NOTE]
> Web Protection är inte tillgängligt när VPN inaktiveras. Om du vill återaktivera Web Protection öppnar du appen Microsoft Defender för Endpoint på enheten och klickar eller trycker på **Starta VPN.**

## <a name="co-existence-of-multiple-vpn-profiles"></a>Det finns flera VPN-profiler

Apple iOS stöder inte flera vpn som gäller hela enheten för att vara aktiva samtidigt. Även om flera VPN-profiler kan finnas på enheten kan bara ett VPN vara aktivt i taget.


## <a name="configure-compliance-policy-against-jailbroken-devices"></a>Konfigurera efterlevnadsprincip mot jailbroken enheter

För att skydda företagsdata från att kommas åt på jailbroken iOS-enheter rekommenderar vi att du konfigurerar följande efterlevnadsprincip på Intune.

> [!NOTE]
> För stunden ger Inte Microsoft Defender för Endpoint för iOS skydd mot scenarier. Om den används på en jailbroken enhet kan data som används av programmet i vissa fall som ditt företags-e-post-ID och företagsprofilbild (om tillgängligt) visas lokalt

Följ stegen nedan för att skapa en efterlevnadsprincip mot jailbroken enheter.

1. Gå [till Principer för enhetsefterlevnad](https://go.microsoft.com/fwlink/?linkid=2109431)i **Administrationscenter för** Microsoft Endpoint  ->    ->  Manager. Välj "iOS/iPadOS" som plattform och klicka på **Skapa**.

    > [!div class="mx-imgBorder"]
    > ![Skapa princip](images/ios-jb-policy.png)

2. Ange ett namn på principen, till exempel "Efterlevnadsprincip för Företag".
3. På sidan inställningar för efterlevnad klickar du för att expandera **avsnittet Enhetshälsa** och klickar på **Spärra för** **Jailbroken-enheter.**

    > [!div class="mx-imgBorder"]
    > ![Principinställningar](images/ios-jb-settings.png)

4. I avsnittet *Åtgärd för icke-efterlevnad* väljer du åtgärderna enligt dina krav och väljer **Nästa.**

    > [!div class="mx-imgBorder"]
    > ![Principåtgärder](images/ios-jb-actions.png)

5. I avsnittet *Tilldelningar* väljer du de användargrupper som du vill inkludera för den här principen och väljer sedan **Nästa.**
6. I avsnittet **Granska+Skapa** kontrollerar du att all information som angetts är korrekt och väljer sedan **Skapa**.

## <a name="configure-custom-indicators"></a>Konfigurera anpassade indikatorer

Med Defender för Endpoint för iOS kan administratörer även konfigurera anpassade indikatorer på iOS-enheter. Mer information om hur du konfigurerar anpassade indikatorer finns [i Hantera indikatorer.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)

> [!NOTE]
> Defender för Endpoint för iOS har stöd för att endast skapa anpassade indikatorer för IP-adresser och URL:er/domäner.

## <a name="report-unsafe-site"></a>Rapportera osäker webbplats

Nätfiskewebbplatser utger sig för att vara betrodda webbplatser i syfte att skaffa personlig eller ekonomisk information. Gå till [sidan Ge feedback om nätverksskydd](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) om du vill rapportera en webbplats som kan vara en nätfiskewebbplats.

## <a name="battery-consumption-issues-on-ios-when-microsoft-defender-for-endpoint-is-installed"></a>Problem med batterianvändning i iOS när Microsoft Defender för Slutpunkt är installerat

Batterianvändningen från en app beräknas av Apple baserat på en mängd faktorer, bland annat PROCESSOR- och nätverksanvändning. Microsoft Defender för Endpoint använder en lokal/loop-back VPN i bakgrunden för att kontrollera webbtrafiken efter skadliga webbplatser eller anslutningar. Nätverkspaket från alla appar går igenom den här kontrollen och det gör att batterianvändningen av Microsoft Defender för Endpoint beräknas felaktigt. Det ger användaren ett falskt intryck. Den faktiska batteriförbrukningen i Microsoft Defender för Endpoint är mindre än vad som visas på sidan Batteriinställningar på enheten. Det här baseras på utförda tester som utförts i appen Microsoft Defender för Slutpunkt för att förstå batterianvändningen.

Dessutom är VPN som används en lokal VPN och till skillnad från traditionella VPN så skickas inte nätverkstrafik utanför enheten.
