---
title: Hantera den gradvisa införandeprocessen för Microsoft Defender-uppdateringar
description: Lär dig mer om den gradvisa uppdateringsprocessen och kontroller
keywords: uppdatering, uppdateringsprocess, kontroller, version
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 435a77432caa9d7335a22993f85cae69eff6cd38
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52862030"
---
#  <a name="manage-the-gradual-rollout-process-for-microsoft-defender-updates"></a>Hantera den gradvisa införandeprocessen för Microsoft Defender-uppdateringar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)


Det är viktigt att se till att klientkomponenter är uppdaterade för att tillhandahålla viktiga skyddsfunktioner och förhindra attacker.

Funktionerna tillhandahålls via flera komponenter: 

- [Slutpunktsidentifiering & svar](overview-endpoint-detection-response.md) 
- [Nästa generations skydd med](microsoft-defender-antivirus-in-windows-10.md#microsoft-defender-antivirus-your-next-generation-protection) [moln levererat skydd](cloud-protection-microsoft-defender-antivirus.md) 
- [Minskning av attackytan](overview-attack-surface-reduction.md)

Uppdateringar släpps varje månad med en stegvis versionsprocess. Den här processen hjälper till att göra det möjligt att upptäcka tidiga fel för att fånga upp påverkan när den sker och åtgärda den snabbt före en större utrullning. 

> [!NOTE]
> Mer information om hur du styr dagliga definitionsuppdateringar finns i [Schemalägga Microsoft Defender Antivirus definitionsuppdateringar – Windows säkerhetsuppdateringar | Microsoft Docs.](manage-protection-update-schedule-microsoft-defender-antivirus.md) Definitionsuppdateringar säkerställer att nästa generations skydd kan försvara sig mot nya hot, även om skydd från molnet inte är tillgängligt för slutpunkten.

## <a name="microsoft-gradual-rollout-model"></a>Microsoft gradvis utrullningsmodell

Följande gradvisa utrullningsmodell följs:

1. Första utgåvan går ut till betakanalprenumeranter.
2. Efter validering, feedback och korrigeringar, inleder vi den gradvisa utrullningsprocessen på ett begränsat sätt och till Förhandsgranska kanal prenumeranter först.
3. Sedan fortsätter vi att släppa uppdateringen till resten av den globala populationen, och skalningen från 10–100 %.

Våra tekniker övervakar och eskalerar kontinuerligt eventuella problem och skapar en korrigering efter behov.

## <a name="how-to-customize-your-internal-deployment-process"></a>Anpassa den interna distributionsprocessen

Om dina datorer får Defender-uppdateringar från Windows Update kan den gradvisa utrullningsprocessen resultera i att vissa av dina datorer får Defender-uppdateringar tidigare än andra. I följande avsnitt beskrivs hur du definierar en strategi som gör att automatiska uppdateringar kan flöda på olika sätt för specifika grupper av enheter med hjälp av konfigurationen av uppdateringskanalen.

> [!NOTE]
> Se till att alltid ha ett urval enheter som prenumererar på förhands- och stegvisa kanaler när du planerar för en egen gradvis utgivning. Det ger din organisation och Microsoft möjlighet att förhindra eller hitta och åtgärda problem som är specifika för din miljö.

För datorer som tar emot uppdateringar via till exempel Windows Server Update Services (WSUS) eller Microsoft Endpoint Configuration Manager (MECM) är fler alternativ tillgängliga för alla Windows-uppdateringar, inklusive alternativ för Microsoft Defender för slutpunkt.

- Läs mer om hur du använder en lösning som WSUS, MECM för att hantera distribution och program av uppdateringar i Hantera Microsoft Defender Antivirus-uppdateringar och tillämpa [baslinjer - Windows säkerhet | Microsoft Docs.](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates)

## <a name="update-channels-for-monthly-updates"></a>Uppdatera kanaler för månatliga uppdateringar

Du kan tilldela en dator till en uppdateringskanal för att ange i vilken takt en dator får månatliga motor- och plattformsuppdateringar.

Mer information om hur du konfigurerar uppdateringar finns i [Skapa en anpassad gradvis utrullningsprocess för Microsoft Defender-uppdateringar.](configure-updates.md)

Följande uppdateringskanaler är tillgängliga:

| Kanalnamn  | Beskrivning  | Program  |
|-|-|-|
| Betakanal – förhandsversion  | Testa uppdateringar före andra  | Enheter som ställs in på den här kanalen blir först med att få nya månatliga uppdateringar. Välj Betakanal för att delta i identifiering och rapportering av problem till Microsoft. Enheter i Windows Insider Program prenumererar på den här kanalen som standard. Endast för användning i testmiljöer.  |
| Aktuell kanal (förhandsversion)  | Få uppdateringar för Aktuell kanal **tidigare** under gradvis utgivning  | Enheter som är inställda på den här kanalen kommer att användas tidigast under den gradvisa versionen. Förslag för miljöer före produktion/validering.  |
| Aktuell kanal (fas)  | Få uppdateringar för Aktuell kanal senare under den gradvisa versionen  | Enheter erbjuds uppdateringar senare under den gradvisa versionen. Rekommenderas att gälla för en liten, representativ del av enhetens population (~10 %).  |
| Aktuell kanal (bred) | Få uppdateringar i slutet av den gradvisa versionen  | Enheter erbjuds endast uppdateringar efter att den stegvisa versionen har slutförts. Rekommenderas att användas på en omfattande uppsättning enheter i produktionspopulationen (~10–100 %).  |
| (standard)  |   | Om du inaktiverar eller inte konfigurerar den här principen finns enheten kvar i aktuell kanal (standard): Håll dig uppdaterad automatiskt under den gradvisa utgivningscykeln. Passar för de flesta enheter.  |

### <a name="update-channels-for-daily-definition-updates"></a>Uppdatera kanaler för dagliga definitionsuppdateringar

Du kan tilldela en dator till en uppdateringskanal för att ange i vilken takt en dator får dagliga definitionsuppdateringar.
  
| Kanalnamn  | Beskrivning  | Program  |
|-|-|-|
| Aktuell kanal (fas)  | Få uppdateringar för Aktuell kanal senare under den gradvisa versionen  | Enheter erbjuds uppdateringar senare under den gradvisa versionen. Rekommenderas att gälla för en liten, representativ del av enhetens population (~10 %).  |
| Aktuell kanal (bred) | Få uppdateringar i slutet av den gradvisa versionen  | Enheter erbjuds uppdateringar efter den gradvisa utgivningscykeln. Bäst för datacenterdatorer som bara får begränsade uppdateringar. Obs! Den här inställningen gäller för alla Defender-uppdateringar.  |
| (standard)  |   | Om du inaktiverar eller inte konfigurerar den här principen finns enheten kvar i aktuell kanal (standard): Håll dig uppdaterad automatiskt under den gradvisa utgivningscykeln. Lämplig för de flesta enheter  |

> [!NOTE]
> Om du vill tvinga fram en uppdatering av den senaste signaturen i stället för att utnyttja den tidsfördröjning du har måste du ta bort den här principen först.

## <a name="update-guidance"></a>Uppdatera vägledning

I de flesta fall är den rekommenderade konfigurationen när du Windows-uppdatering att tillåta slutpunkter att ta emot och använda månatliga Defender-uppdateringar när de anländer. På så sätt får du bästa möjliga balans mellan skydd och eventuella effekter som är associerade med de ändringar de kan införa.

För miljöer där det finns ett behov av en mer kontrollerad gradvis distribution av automatiska Defender-uppdateringar bör du överväga en metod med distributionsgrupper:

1. Delta i Windows Insider-programmet eller tilldela en grupp av enheter till Betakanalen.
2. Utse en pilotgrupp som väljer att använda förhandskanalen, vanligtvis valideringsmiljöer, för att få nya uppdateringar tidigt.
3. Utse en grupp datorer som får uppdateringar senare under den gradvisa utrullningen från den stegvisa kanalen. Vanligtvis är det en representant för ~10 % av populationen.
4. Ange en grupp datorer som får uppdateringarna efter att den gradvisa versionen har slutförts. Det här är vanligtvis viktiga produktionssystem.

För resten av enheter är standardinställningen att få nya uppdateringar när de anländer under den gradvisa utrullningsprocessen från Microsoft och ingen ytterligare konfiguration krävs. 

Genom att använda den här modellen:
- Gör att du kan testa tidiga versioner innan de når en produktionsmiljö 
- Se till att produktionsmiljön fortfarande tar emot regelbundna uppdateringar och säkerställa skydd mot kritiska hot.

## <a name="management-tools"></a>Hanteringsverktyg
Om du vill skapa en egen, stegvis utrullningsprocess för månatliga uppdateringar kan du använda följande verktyg:

- Grupprincip
- Microsoft Endpoint Manager
- PowerShell

Mer information om hur du använder dessa verktyg finns i [Skapa en anpassad gradvis införandeprocess för Microsoft Defender-uppdateringar.](configure-updates.md)
