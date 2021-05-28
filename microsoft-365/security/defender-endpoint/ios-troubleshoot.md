---
title: Felsöka problem och hitta svar på vanliga frågor och svar som rör Microsoft Defender för Slutpunkt i iOS
description: Felsökning och vanliga frågor och svar – Microsoft Defender för slutpunkt i iOS
keywords: microsoft, defender, Microsoft Defender för Slutpunkt, ios, felsökning, vanliga frågor och svar, så gör du, så här gör du
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
ms.openlocfilehash: 2f9d56b7e72befb8acddf6d9f810a7ba5cec1083
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694371"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a>Felsöka problem och hitta svar på vanliga frågor och svar i Microsoft Defender för Endpoint i iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Det här avsnittet innehåller felsökningsinformation som hjälper dig att lösa problem som kan uppstå när du använder Microsoft Defender för Endpoint i iOS.



> [!NOTE]
> Defender för Endpoint i iOS skulle använda ett VPN för att tillhandahålla webskyddsfunktionen. Det här är inte en vanlig VPN och är en lokal/självslingande VPN som inte tar trafik utanför enheten.

## <a name="apps-dont-work-when-vpn-is-turned-on"></a>Appar fungerar inte när VPN är aktiverat
Det finns vissa appar som slutar fungera när ett aktivt VPN upptäcks. Du kan inaktivera VPN under tiden du använder sådana appar. 

Som standard inkluderar och aktiverar Defender för Slutpunkt i iOS webbskyddsfunktionen. [Webbskydd](web-protection-overview.md) hjälper till att skydda enheter mot webbhot och skyddar användare mot nätfiskeattacker. Defender för Endpoint på iOS använder en VPN för att tillhandahålla detta skydd. Observera att det här är en lokal VPN och till skillnad från traditionell VPN skickas inte nätverkstrafik utanför enheten.

När den är aktiverad som standard kan det finnas fall där du måste inaktivera VPN. Du kanske till exempel vill köra vissa appar som inte fungerar när en VPN konfigureras. I sådana fall kan du välja att inaktivera VPN från appen på enheten genom att följa stegen nedan:

1. På din iOS-enhet öppnar du **Inställningar,** klickar eller trycker på **Allmänt** och sedan **VPN.**
1. Klicka eller tryck på i-knappen för Microsoft Defender för Slutpunkt.
1. Inaktivera ANSLUT **för att** inaktivera VPN.

    > [!div class="mx-imgBorder"]
    > ![VPN-konfiguration ansluter på begäran](images/ios-vpn-config.png)

> [!NOTE]
> Web Protection är inte tillgängligt när VPN inaktiveras. Om du vill återaktivera Web Protection öppnar du appen Microsoft Defender för Endpoint på enheten och klickar eller trycker på **Starta VPN.**

## <a name="issues-with-multiple-vpn-profiles"></a>Problem med flera VPN-profiler

Apple iOS stöder inte flera **vpn som gäller hela enheten** för att vara aktiva samtidigt. Även om flera VPN-profiler kan finnas på enheten kan bara ett VPN vara aktivt i taget.

Microsoft Defender för endpoint VPN kan finnas tillsammans med andra VPN som är konfigurerade *som per app* eller *"Personligt".*

## <a name="battery-consumption"></a>Batteriförbrukning

I Inställningar visar iOS endast batterianvändningen av appar som är synliga för användaren under en viss tid. Batterianvändningen från appar som visas på skärmen gäller bara under den tiden och beräknas av iOS baserat på en mängd faktorer, till exempel CPU och nätverksanvändning. Microsoft Defender för Endpoint använder en lokal/loop-back VPN i bakgrunden för att kontrollera webbtrafiken efter skadliga webbplatser eller anslutningar. Nätverkspaket från alla appar går igenom den här kontrollen och det gör att batterianvändningen av Microsoft Defender för Endpoint beräknas felaktigt. Den faktiska batteriförbrukningen i Microsoft Defender för Endpoint är mycket mindre än vad som visas på sidan Inställningar batteri på enheten.

Batterianvändning per dag av Microsoft Defender för Slutpunkt som körs i bakgrunden är cirka **8,81**% av det totala batteriet som använts den dagen. Det här måttet rapporteras av Apple baserat på faktisk användning av Microsoft Defender för Endpoint på slutanvändareenheter och på grund av orsaker som nämns ovan kan även redovisas för andra appar som har nätverksaktivitet.

Vpn som används är också en lokal VPN och till skillnad från en traditionell VPN skickas inte nätverkstrafik utanför enheten.

## <a name="data-usage"></a>Dataanvändning

Microsoft Defender för Endpoint använder ett vpn som ger lokal/loopback för att kontrollera webbtrafik efter skadliga webbplatser eller anslutningar. På grund av den här orsaken kan Microsoft Defender för Slutpunktsdataanvändning redovisas felaktigt. Den faktiska dataanvändningen av Microsoft Defender för Endpoint är inte signifikant och mindre än vad som visas på Inställningar på enheten.

## <a name="report-unsafe-site"></a>Rapportera osäker webbplats

Nätfiskewebbplatser utger sig för att vara betrodda webbplatser i syfte att skaffa personlig eller ekonomisk information. Gå till [sidan Ge feedback om nätverksskydd](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) om du vill rapportera en webbplats som kan vara en nätfiskewebbplats.

## <a name="malicious-site-detected"></a>Skadlig webbplats har upptäckts

Microsoft Defender för slutpunkt skyddar dig mot nätfiske eller andra webbaserade attacker. Om en skadlig webbplats upptäcks blockeras anslutningen och en avisering skickas till organisationens säkerhetscenterportal. Aviseringen omfattar domännamnet för anslutningen, fjärr-IP-adressen och enhetsinformationen.

Dessutom visas ett meddelande på iOS-enheten. När användaren trycker på meddelandet öppnas följande skärm för att granska informationen.

> [!div class="mx-imgBorder"]
> ![Bild på webbplatsen som rapporterats som osäker](images/ios-phish-alert.png)

## <a name="data-and-privacy"></a>Data och sekretess

Mer information om data som samlas in och sekretess finns i [Sekretessinformation – Microsoft Defender för Endpoint på iOS.](ios-privacy.md)

