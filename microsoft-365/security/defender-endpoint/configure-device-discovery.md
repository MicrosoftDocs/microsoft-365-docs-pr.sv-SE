---
title: Konfigurera enhetsidentifiering
description: Lär dig hur du konfigurerar enhetsidentifiering i Microsoft 365 Defender med grundläggande identifiering eller standardidentifiering
keywords: grundläggande, standard, konfigurera identifiering av slutpunkt, enhetsidentifiering
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
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: e1efeff77657e04223b21d639a0a09287f3707cc
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177591"
---
# <a name="configure-device-discovery"></a>Konfigurera enhetsidentifiering

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


[!include[Prerelease information](../../includes/prerelease.md)]

Identifiering kan konfigureras att ske i standard- eller standardläge. Använd standardalternativet för att aktivt hitta enheter i nätverket, vilket bättre garanterar att slutpunkter upptäcks och ger bättre enhetsklassificering. 

Du kan anpassa listan med enheter som används för standardidentifiering. Du kan antingen aktivera standardidentifiering för alla enheter som har stöd för den här funktionen (för närvarande endast Windows 10-enheter) eller välja en delmängd eller delmängder av dina enheter genom att ange deras enhetstaggar. 


> [!IMPORTANT]
> För förhandsgranskning måste du först aktivera förhandsgranskningsfunktionerna i Microsoft Defender Säkerhetscenter.
> Du kan sedan komma åt konfigurationen för enhetsidentifiering Microsoft 365 säkerhetscenter. Listan över ohanterade enheter och säkerhetsrekommendationer blir tillgänglig i både säkerhetscentret i Microsoft Defender Säkerhetscenter och Microsoft 365, medan panelerna på instrumentpanelen bara är tillgängliga i Microsoft 365 säkerhetscenter.


Gör följande i Microsoft 365 säkerhetscenter:

1.  Gå till Inställningar > **enhetsidentifiering**.
2.  Välj det identifieringsläge du vill använda på dina onboarded-enheter. 
3.  Om du har valt att använda standardidentifiering väljer du vilka enheter som ska användas för aktiv sannolikhet: alla enheter eller en delmängd genom att ange deras enhetstaggar.
4. Klicka på **Spara**.


## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a>Undanta enheter från aktivt sök efter standardidentifiering
Om det finns enheter i nätverket som inte ska sökas igenom aktivt (till exempel enheter som används som Honey honeytek för ett annat säkerhetsverktyg) kan du också definiera en lista med undantag så att de inte genomsöks. Observera att enheter fortfarande kan upptäckas med hjälp av Grundläggande identifieringsläge. Dessa enheter kommer att upptäckas passivt men kommer inte att sökas aktivt. 

## <a name="select-networks-to-monitor"></a>Välja nätverk att övervaka
 Microsoft Defender för Endpoint analyserar ett nätverk och fastställer om det är ett företagsnätverk som måste övervakas eller ett icke-företagsnätverk som kan ignoreras. Företagsnätverk övervakas vanligtvis. Du kan dock åsidosätta det här beslutet genom att välja att övervaka icke-företagsnätverk där enheter med registrering finns. 

Du kan konfigurera var enhetsidentifiering kan utföras genom att ange vilka nätverk som ska övervakas. När ett nätverk övervakas kan enhetsidentifieringen utföras på det. 

En lista över nätverk där enhetsidentifiering kan utföras visas på sidan **Övervakade** nätverk. 


>[!NOTE]
> Endast de 50 främsta nätverken (enligt antalet associerade enheter) kommer att vara tillgängliga i nätverkslistan. 


Listan över övervakade nätverk sorteras baserat på det totala antalet enheter som har setts på nätverket under de senaste 7 dagarna.


Du kan använda ett filter för att visa följande nätverksidentifierings tillstånd:

- **Övervakade nätverk** – nätverk där enhetsidentifieringen utförs.
- **Ignorerade nätverk** – Det här nätverket ignoreras och enhetsidentifieringen utförs inte på det.
- **Alla** – Både övervakade och ignorerade nätverk visas. 


### <a name="configure-the-network-monitor-state"></a>Konfigurera nätverksövervakningstillståndet
Du styr var enhetsidentifiering sker. Övervakade nätverk är den plats där enhetsidentifiering utförs och vanligtvis är företagsnätverk. Du kan också välja att ignorera nätverk eller välja den första identifieringsklassificeringsklassificeringen när du har modifierat ett tillstånd. 

När du väljer den första identifieringsklassificeringen innebär det att standardsystemets nätverksövervakningstillstånd tillämpas. Om du väljer standardsystemövervakningstillståndet övervakas nätverk som har identifierats som företagsbaserade och sådana som identifieras som icke-företagsbaserade ignoreras automatiskt.
 
1. Välj **Inställningar > enhetsidentifiering**.
2. Välj **Övervakade nätverk**. 
3. Visa listan över nätverk. 
4. Välj de tre punkterna bredvid nätverksnamnet. 
5. Välj om du vill övervaka, ignorera eller använda den första identifieringsklassificeringsklassificeringen. 
    
    > [!WARNING]
    >- Om du väljer att övervaka ett nätverk som inte identifierats av Microsoft Defender för Endpoint som ett företagsnätverk kan det orsaka enhetsidentifiering utanför företagsnätverket och kan därför identifiera hemenheter eller andra enheter som inte är företagsbaserade. 
    > - Om du väljer att ignorera ett nätverk avbryts övervakning och identifiering av enheter i nätverket. Enheter som redan identifierats tas inte bort från inventeringen, men uppdateras inte längre, och informationen behålls tills Defender för Slutpunktens datalagringsperiod upphör att gälla.
    > - Innan du väljer att övervaka nätverk utanför företaget måste du ha behörighet att göra det. <br>


6. Bekräfta att du vill göra ändringen. 


## <a name="explore-devices-in-the-network"></a>Utforska enheter i nätverket

Du kan använda följande avancerade fråga för sökning för att få mer kontext för varje nätverksnamn som beskrivs i listan över nätverk. I frågan visas alla onboarded-enheter som var anslutna till ett visst nätverk under de senaste 7 dagarna.



```kusto
DeviceNetworkInfo
| where Timestamp > ago(7d)
| summarize arg_max(Timestamp, *) by DeviceId
| where ConnectedNetworks  != ""
| extend ConnectedNetworksExp = parse_json(ConnectedNetworks)
| mv-expand bagexpansion = array ConnectedNetworks=ConnectedNetworksExp
| extend NetworkName = tostring(ConnectedNetworks ["Name"]), Description = tostring(ConnectedNetworks ["Description"]), NetworkCategory = tostring(ConnectedNetworks ["Category"])
| where NetworkName == "<your network name here>"


```

## <a name="see-also"></a>Se även
- [Översikt över enhetsidentifiering](device-discovery.md)
- [Vanliga frågor och svar om enhetsupptäckt](device-discovery-faq.md)