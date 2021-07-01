---
title: Konfigurera Microsoft Defender för slutpunkt för iOS-funktioner
description: Här beskrivs hur du distribuerar Microsoft Defender för Slutpunkt i iOS-funktioner
keywords: microsoft, defender, Microsoft Defender för Slutpunkt, ios, konfigurera, funktioner, ios
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
ms.openlocfilehash: 749e03cb9d14476245baea82c21d322d4d726aad
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230013"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a>Konfigurera Microsoft Defender för slutpunkt för iOS-funktioner

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> Defender för Endpoint i iOS skulle använda ett VPN för att tillhandahålla webskyddsfunktionen. Det här är inte en vanlig VPN och är en lokal/självslingande VPN som inte tar trafik utanför enheten.

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a>Villkorsstyrd åtkomst med Defender för slutpunkt i iOS  
Microsoft Defender för slutpunkt på iOS tillsammans med Microsoft Intune och Azure Active Directory aktiverar tvingande enhetsefterlevnad och villkorsstyrd åtkomstprincip baserat på enhetens riskresultat. Defender för Endpoint är en MTD-lösning (Mobile Threat Defense) som du kan distribuera för att utnyttja den här funktionen via Intune.

Mer information om hur du konfigurera villkorsstyrd åtkomst med Defender för slutpunkt i iOS finns [i Defender för Endpoint och Intune.](/mem/intune/protect/advanced-threat-protection)

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a>Identifiering av identifiering av Microsoft Defender för Endpoint
I Microsoft Defender för Endpoint går det att identifiera ohanterade och hanterade enheter som är jailbroken. Om en enhet identifieras som jailbroken kommer en varning med hög risk att rapporteras till Säkerhetscenter, och om villkorsstyrd åtkomst konfigureras baserat på enhetsriskresultat blockeras enheten från att komma åt företagsdata.

## <a name="web-protection-and-vpn"></a>Web Protection och VPN

Som standard inkluderar och aktiverar Defender för Slutpunkt i iOS webbskyddsfunktionen. [Webbskydd](web-protection-overview.md) hjälper till att skydda enheter mot webbhot och skyddar användare mot nätfiskeattacker. Defender för Endpoint på iOS använder en VPN för att tillhandahålla detta skydd. Observera att det här är en lokal VPN och till skillnad från traditionell VPN skickas inte nätverkstrafik utanför enheten.

När den är aktiverad som standard kan det finnas fall där du måste inaktivera VPN. Du kanske till exempel vill köra vissa appar som inte fungerar när en VPN konfigureras. I sådana fall kan du välja att inaktivera VPN från appen på enheten genom att följa stegen nedan:

1. På din iOS-enhet öppnar du **Inställningar,** klickar eller trycker på **Allmänt** och sedan **VPN.**
1. Klicka eller tryck på i-knappen för Microsoft Defender för Slutpunkt.
1. Inaktivera ANSLUT **för att** inaktivera VPN.

    > [!div class="mx-imgBorder"]
    > ![VPN-konfiguration ansluter på begäran](images/ios-vpn-config.png)

> [!NOTE]
> Web Protection är inte tillgängligt när VPN inaktiveras. Om du vill återaktivera Web Protection öppnar du appen Microsoft Defender för Endpoint på enheten och klickar eller trycker på **Starta VPN.**

## <a name="co-existence-of-multiple-vpn-profiles"></a>Det finns flera VPN-profiler

Apple iOS stöder inte flera vpn som gäller hela enheten för att vara aktiva samtidigt. Även om flera VPN-profiler kan finnas på enheten kan bara ett VPN vara aktivt i taget.

## <a name="configure-microsoft-defender-for-endpoint-risk-signal-in-app-protection-policy-mam"></a>Konfigurera Microsoft Defender för Slutpunktsrisk signal i programskyddsprincip (MAM)

Microsoft Defender för Endpoint kan konfigureras för att skicka hotsignaler som ska användas i appskyddsprinciper (APP, som även kallas MAM) på iOS/iPadOS. Med den här funktionen kan du även använda Microsoft Defender för Endpoint för att skydda åtkomsten till företagsdata från oregistrerade enheter.

Steg för att konfigurera principer för programskydd med Microsoft Defender för Slutpunkt är enligt nedan:

1. Konfigurera anslutningen från din klientorganisation Microsoft Endpoint Manager Microsoft Defender för Endpoint. I [Administrationscenter](https://go.microsoft.com/fwlink/?linkid=2109431)för Microsoft Endpoint Manager går du till Kopplingar för klientorganisationsadministration och tokens Microsoft Defender för slutpunkt (under flera plattformar) eller  >  **Slutpunktssäkerhet** Microsoft Defender för Slutpunkt (under Installation) och aktiverar  >     >   växlingsknapparna under Programskyddsprincip Inställningar för **iOS.**
1. Välj Spara. Anslutningsstatus **visas nu** som **Aktiverad.**
1. Skapa programskyddsprincip: När konfigurationen av Microsoft Defender för Endpoint-kopplingen är klar går du till  >  **Programskyddsprinciper** (under Princip) för att skapa en ny princip eller uppdatera en befintlig.
1. Välj den plattform, **appar, dataskydd, åtkomstkravinställningar** som din organisation kräver för principen.
1. Under **Villkor för**  >  **villkorsstyrd** start av enhet hittar du inställningen **Max hotnivå för tillåtna enheter.** Det här måste konfigureras för antingen Låg, Medel, Hög eller Skyddad. De tillgängliga åtgärderna blir Blockera åtkomst **eller** **Rensa data.** Det kan visas en informationsdialogruta för att kontrollera att du har angett kopplingen innan den här inställningen används. Om kopplingen redan är konfigurerad kan du ignorera den här dialogrutan.
1. Slutför med Uppgifter och spara principen.

Mer information om MAM- eller appskyddsprincip finns i [principinställningar för iOS-programskydd.](/mem/intune/apps/app-protection-policy-settings-ios)

### <a name="deploying-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a>Distribuera Microsoft Defender för slutpunkt för MAM eller på oregistrerade enheter

Microsoft Defender för slutpunkt i iOS aktiverar Scenariot för programskyddsprincip och är tillgängligt i Apple App Store.

Slutanvändarna bör installera den senaste versionen av programmet direkt från Apple App Store.

## <a name="configure-compliance-policy-against-jailbroken-devices"></a>Konfigurera efterlevnadsprincip mot jailbroken enheter

För att skydda företagsdata från att kommas åt på jailbroken iOS-enheter rekommenderar vi att du konfigurerar följande efterlevnadsprincip på Intune.

> [!NOTE]
> Identifiering av identifiering av objekt är en funktion som tillhandahålls av Microsoft Defender för Endpoint i iOS. Vi rekommenderar dock att du inställningar den här principen som ytterligare skydd mot scenarier.

Följ stegen nedan för att skapa en efterlevnadsprincip mot jailbroken enheter.

1. I [Microsoft Endpoint Manager administrationscenter går](https://go.microsoft.com/fwlink/?linkid=2109431)du till Principer för efterlevnad av **enheter**  ->  **Skapa**  ->  **princip.** Välj "iOS/iPadOS" som plattform och klicka på **Skapa**.

    > [!div class="mx-imgBorder"]
    > ![Skapa princip](images/ios-jb-policy.png)

2. Ange ett namn på principen, till exempel "Efterlevnadsprincip för Företag".
3. På sidan inställningar för efterlevnad klickar du för att expandera **avsnittet Enhetshälsa** och klickar på **Spärra för** **Jailbroken-enheter.**

    > [!div class="mx-imgBorder"]
    > ![Princip Inställningar](images/ios-jb-settings.png)

4. I avsnittet **Åtgärd för icke-efterlevnad** väljer du åtgärderna enligt dina krav och väljer **Nästa.**

    > [!div class="mx-imgBorder"]
    > ![Principåtgärder](images/ios-jb-actions.png)

5. I avsnittet **Tilldelningar** väljer du de användargrupper som du vill inkludera för den här principen och väljer sedan **Nästa.**
6. I avsnittet **Granska+Skapa** kontrollerar du att all information som angetts är korrekt och väljer sedan **Skapa**.

## <a name="configure-custom-indicators"></a>Konfigurera anpassade indikatorer

Med Defender för Slutpunkt i iOS kan administratörer även konfigurera anpassade indikatorer på iOS-enheter. Mer information om hur du konfigurerar anpassade indikatorer finns [i Hantera indikatorer.](/microsoft-365/security/defender-endpoint/manage-indicators)

> [!NOTE]
> Defender för Slutpunkt i iOS har stöd för att endast skapa anpassade indikatorer för IP-adresser och URL:er/domäner.

## <a name="report-unsafe-site"></a>Rapportera osäker webbplats

Nätfiskewebbplatser utger sig för att vara betrodda webbplatser i syfte att skaffa personlig eller ekonomisk information. Gå till [sidan Ge feedback om nätverksskydd](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) om du vill rapportera en webbplats som kan vara en nätfiskewebbplats.

