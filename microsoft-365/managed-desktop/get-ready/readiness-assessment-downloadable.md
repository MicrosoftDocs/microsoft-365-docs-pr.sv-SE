---
title: Nedladdningsbar kontroll för beredskapsbedömning
description: Kontrollerar enhets- och nätverksinställningar, inklusive obligatoriska slutpunkter
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: eec6bdff2e494e0f55b06cb581c5775d3ffeb9e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581040"
---
# <a name="downloadable-readiness-assessment-checker"></a>Nedladdningsbar kontroll för beredskapsbedömning

För att fungera bra med Microsoft Managed Desktop måste enheter uppfylla vissa krav för maskinvara och inställningar. Varje enhet måste också kunna nå viktiga slutpunkter. Ladda ned och kör det här verktyget för att hämta en HTML-rapport, visa resultat och sedan vidta åtgärder. Du måste ladda ned verktyget och stödfilerna och sedan köra det manuellt på varje enhet som du vill registrera i Microsoft Managed Desktop.

För varje kontroll rapporterar verktyget ett av tre möjliga resultat:


|Resultat  |Betydelse  |
|---------|---------|
|Klar     | Ingen åtgärd krävs innan du slutför registreringen.        |
|Rådgivning    | Följ stegen i verktyget för att få den bästa upplevelsen med registrering och för användare. Du *kan* slutföra registreringen, men du måste åtgärda de här problemen innan du distribuerar din första enhet.        |
|Inte klar | *Registrering kommer att* misslyckas om du inte åtgärdar dessa problem. Följ stegen i verktyget för att lösa dem.        |

## <a name="obtain-the-checker"></a>Skaffa kontrollen

Ladda ned ZIP-filen från https://aka.ms/mmddratoolv0 .

> [!NOTE]
> Den användare som kör verktyget måste ha lokal administratörsbehörighet på den enhet där den körs.

 Kör sedan verktyget så här:

1. Kopiera den nedladdade ZIP-filen till varje enhet som du vill kontrollera.
2. Extrahera alla filer i den komprimerade nedladdningen.
3. Kör **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.
4. När uppmaningen Om användaråtkomstkontroll visas väljer du **Ja.** Verktyget körs och en rapport öppnas i standardwebbläsaren.

Du kan också ladda ned och extrahera ZIP-arkivet till en delad plats, **kommaMicrosoft.MMD.DeviceReadinessAssessmentTool.exe** från varje enhet och sedan köra det lokalt.


## <a name="checks"></a>Kontroller

Det nedladdningsbara verktyget kontrollerar dessa enhets- och nätverksrelaterade objekt:

### <a name="hardware"></a>Maskinvara

Enheter måste uppfylla vissa maskinvarukrav för att fungera med Microsoft Managed Desktop. För närvarande [tillåts endast vissa](../service-description/device-list.md) godkända enheter att registrera. 

Om någon av kontrollerna misslyckas på enheten är den inte kompatibel med Microsoft Managed Desktop.

### <a name="network-endpoints"></a>Nätverksslutpunkter

Enheter kan nå flera viktiga [slutpunkter för att](network.md) arbeta med Microsoft Hanterat skrivbord.

Om verktyget rapporterar ett resultat **som inte är** redo kan du se den detaljerade rapporten för att ta reda på vilka slutpunkter som inte kunde nås. Justera sedan brandväggen eller andra nätverksinställningar för att säkerställa att dessa slutpunkter kan nås.

### <a name="other-settings"></a>Andra inställningar

#### <a name="enterprise-wi-fi-profiles"></a>Enterprise Wi-fi-profiler

Ett **rådgivningsresultat** innebär att du använder vissa wi-fi-profiler som behöver certifikat och profiler för att fungera korrekt. Mer information finns i [Distribuera certifikat och Wi-Fi/VPN-profil.](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)

#### <a name="lan-profiles"></a>LAN-profiler

Ett **rådgivningsresultat** innebär att du har certifikat och profiler för att fungera korrekt. Mer information finns i Förbereda [certifikat och nätverksprofiler för Microsoft Managed Desktop.](certs-wifi-lan.md)

#### <a name="vpn-profiles"></a>VPN-profiler

Ett **rådgivningsresultat** innebär att du använder ett virtuellt privat nätverk (VPN). Skapa en VPN-profil som distribuerar certifikat integrerade med Microsoft Intune. Mer information finns i Förbereda [certifikat och nätverksprofiler för Microsoft Managed Desktop.](certs-wifi-lan.md)

#### <a name="mapped-drives"></a>Mappade enheter

Ett **Rådgivning-resultat** innebär att du har vissa mappade enheter, och det rekommenderas inte. Mer information finns i Förbereda [mappade enheter för Microsoft Managed Desktop.](mapped-drives.md)

#### <a name="print-queues"></a>Utskriftsköer

Ett **Rådgivningsresultat** innebär att du har några utestående utskriftsköer, vilket inte rekommenderas. En lösning är att använda molnbaserad utskrift. Mer information finns i Förbereda [utskriftsresurser för Microsoft Managed Desktop.](printing.md)

#### <a name="proxies"></a>Proxy

Ett **rådgivningsresultat** innebär att du har en proxyserver som används. Mer information finns i [Nätverkskonfiguration för Microsoft Managed Desktop.](network.md)

