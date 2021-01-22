---
title: Nedladdningsbar beredskapsbedömning
description: Kontrollerar enhets- och nätverksinställningar, inklusive obligatoriska slutpunkter
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2080b2fc924320f38d9972c82c0425fa1d8026e7
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49922026"
---
# <a name="downloadable-readiness-assessment-checker"></a>Nedladdningsbar beredskapsbedömning

För att fungera bra med Microsoft Managed Desktop måste enheter uppfylla vissa krav för maskinvara och inställningar. Varje enhet måste också kunna nå viktiga slutpunkter. Ladda ned och kör det här verktyget för att hämta en HTML-rapport, visa resultat och sedan vidta åtgärder. Du måste ladda ned verktyget och stödfilerna och sedan köra det manuellt på varje enhet som du vill registrera i Microsoft Managed Desktop.

För varje kontroll rapporterar verktyget ett av tre möjliga resultat:


|Resultat  |Betydelse  |
|---------|---------|
|Klar     | Ingen åtgärd krävs innan du slutför registreringen.        |
|Rådgivning    | Följ stegen i verktyget för att få den bästa upplevelsen med registrering och för användare. Du *kan* slutföra registreringen, men du måste åtgärda problemen innan du distribuerar din första enhet.        |
|Inte klar | *Registrering misslyckas om* du inte åtgärdar dessa problem. Följ stegen i verktyget för att lösa dem.        |

## <a name="obtain-the-checker"></a>Hämta kontrollen

Hämta ZIP-filen https://aka.ms/mmddratoolv0 från.

> [!NOTE]
> Den användare som kör verktyget måste ha lokala administratörsrättigheter på den enhet där den körs.

 Kör sedan verktyget så här:

1. Kopiera den nedladdade ZIP-filen till varje enhet som du vill kontrollera.
2. Extrahera alla filer i den komprimerade nedladdningen.
3. Kör **Microsoft.MMD.DeviceReadinessAssessmentTool.exe.**
4. Välj Ja när frågan om användaråtkomstkontroll **visas.** Verktyget körs och öppnar en rapport i standardwebbläsaren.

Du kan också ladda ned och extrahera ZIP-arkivet till en delad plats, komma **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** från varje enhet och sedan köra det lokalt.


## <a name="checks"></a>Kontroller

Det nedladdningsbara verktyget kontrollerar dessa enhets- och nätverksrelaterade objekt:

### <a name="hardware"></a>Maskinvara

Enheter måste uppfylla specifika maskinvarukrav för att fungera med Microsoft Managed Desktop. För närvarande [tillåts endast vissa](../service-description/device-list.md) godkända enheter att registrera. 

Om någon av kontrollerna misslyckas på enheten är den inte kompatibel med Microsoft Managed Desktop.

### <a name="network-endpoints"></a>Nätverksslutpunkter

Enheter kan nå flera viktiga [slutpunkter för att arbeta](network.md) med Microsoft Hanterat skrivbord.

Om verktyget rapporterar ett resultat **som inte** är klart kan du i den detaljerade rapporten ta reda på vilka slutpunkter som inte kunde nås. Justera sedan brandväggen eller andra nätverksinställningar för att säkerställa att slutpunkterna kan nås.

### <a name="other-settings"></a>Andra inställningar

#### <a name="enterprise-wi-fi-profiles"></a>Wi-Fi-profiler för Enterprise

Ett **rådgivningsresultat** innebär att du använder vissa Wi-Fi-profiler som behöver certifikat och profiler för att fungera korrekt. Mer information finns i Distribuera [certifikat och profilen Wi-Fi/VPN.](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)

#### <a name="lan-profiles"></a>LAN-profiler

Ett **rådgivningsresultat** innebär att du har LAN som behöver certifikat och profiler för att fungera korrekt. Mer information finns i Förbereda [certifikat och nätverksprofiler för Microsoft Managed Desktop.](certs-wifi-lan.md)

#### <a name="vpn-profiles"></a>VPN-profiler

Ett **rådgivningsresultat** innebär att du använder ett virtuellt privat nätverk (VPN). Skapa en VPN-profil som distribuerar certifikat integrerat med Microsoft Intune. Mer information finns i Förbereda [certifikat och nätverksprofiler för Microsoft Managed Desktop.](certs-wifi-lan.md)

#### <a name="mapped-drives"></a>Mappade enheter

Ett **rådgivningsresultat** innebär att du har vissa mappade enheter, vilket inte rekommenderas. Mer information finns i Förbereda [mappade enheter för Microsoft Managed Desktop.](mapped-drives.md)

#### <a name="print-queues"></a>Skriva ut köer

Ett **rådgivningsresultat** innebär att du har några utestående utskriftsköer, vilket inte rekommenderas. En lösning är att skriva ut i molnet. Mer information finns i Förbereda [utskriftsresurser för Microsoft Managed Desktop.](printing.md)

#### <a name="proxies"></a>Proxy

Ett **rådgivningsresultat** innebär att du har en proxyserver som används. Mer information finns i [Nätverkskonfiguration för Microsoft Managed Desktop.](network.md)

