---
title: Nätverksplanering och prestandajustering för Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/19/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_Enterprise
f1.keywords:
- CSH
search.appverid:
- MET150
ms.assetid: e5f1228c-da3c-4654-bf16-d163daee8848
ms.custom:
- seo-marvel-apr2020
- Adm_O365
description: Den här artikeln hjälper dig att planera nätverkets bandbreddskrav för Microsoft 365 samt finjustera och felsöka prestanda.
ms.openlocfilehash: bf05e4128f8ba5ddecce76cb00dc945f43c9c59a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923606"
---
# <a name="network-planning-and-performance-tuning-for-microsoft-365"></a>Nätverksplanering och prestandajustering för Microsoft 365
Innan du distribuerar för första gången eller migrerar till Microsoft 365 kan du använda informationen i följande avsnitt för att uppskatta vilken bandbredd du behöver och sedan testa och verifiera att du har tillräckligt med bandbredd för att distribuera eller migrera till Microsoft 365. En översikt finns i: [Nätverks- och migreringsplanering för Microsoft 365](network-and-migration-planning.md).
  
|||||
|:-----|:-----|:-----|:-----|
|**Nätverksplanering** <br/> ![Nätverk](../media/5e9dcd06-601b-4b28-88dc-f524e7548794.png)           <br/> |Vill du ha snabba anslutningar och sidor som läses in snabbt?  <br/> Läs [Få bästa möjliga anslutning och prestanda i Microsoft 365](https://aka.ms/o365perfprinciples).<br/>Läs [Microsoft 365 översikt över nätverksanslutning för](microsoft-365-networking-overview.md) att förstå begrepp.<br/> |**Mäta nätverket** <br/> ![Kalkylatorn](../media/d690a132-4884-40eb-a918-526bb3dff3cc.png)           <br/> |Läs [Microsoft 365 prestandajustering med baslinjer och prestandahistorik och](performance-tuning-using-baselines-and-history.md) Plan för [prestandafelsökning för Microsoft 365](performance-troubleshooting-plan.md).  <br/> Använd de här verktygen för [att utvärdera ditt befintliga nätverk.](network-and-migration-planning.md#calculators)  <br/> |
|**Metodtips** <br/> ![Best practices](../media/2a659a5c-1007-47d3-a6c6-a19e018ab29b.png)           <br/> |[Rekommendationer för nätverksplanering och förbättring av migreringsprestanda för Microsoft 365.](network-and-migration-planning.md#BestPractices) Vill du komma igång och hjälpa användarna direkt? Läs [Rekommendationer för att Office 365 i ett långsamt nätverk.](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)  <br/> [Microsoft 365 med nätverksanslutningsprinciper](./microsoft-365-network-connectivity-principles.md) hjälper dig att förstå de senaste vägsvägledningen så att du kan optimera Microsoft 365 och nätverksanslutningen på ett säkert sätt.  <br/> |**Referens** <br/> ![Bok eller journal](../media/56dff3c1-f605-48d8-811f-7d13ce639ecd.png)           <br/> |Vill du veta mer, som en lista med IP-adresser och portar? Se [referensen för nätverksplanering för Microsoft 365](network-and-migration-planning.md#NetReference).  <br/> |
|![Se postern Microsoft Cloud Networking för Enterprise Architects](../media/3094be9f-2407-4fa5-896d-aa66ef7b9bb9.png)           <br/> |Instruktioner för hur du optimerar nätverket för Microsoft 365 och andra molnplattformar och -tjänster från Microsoft finns på postern [Microsoft Cloud Networking for Enterprise Architects.](../solutions/cloud-architecture-models.md)  <br/> |
   
## <a name="performance-tuning-and-troubleshooting-resources-for-microsoft-365"></a>Resurser för prestandajustering och felsökning för Microsoft 365
<a name="apptuning"> </a>

När du Microsoft 365 distribuerat kan du optimera prestanda med hjälp av avsnitten i det här avsnittet. Om du upplever försämrad prestanda du kan också använda dessa avsnitt för att felsöka problem.
  
 **[Justera Office 365:](tune-microsoft-365-performance.md)** Mer information om hur du använder översättning av nätverksadresser med Office 365 finns [NAT-stöd med Office 365.](nat-support-with-microsoft-365.md) Ta också en titt på de [10 bästa tipsen för att optimera och felsöka Office 365 nätverksanslutningar.](/archive/blogs/onthewire/top-10-tips-for-optimising-troubleshooting-your-office-365-network-connectivity) 
  
 **[Justera Exchange Online:](tune-exchange-online-performance.md)** Använd de här artiklarna till att finjustera Exchange Online prestanda. 
  
 **[Justera Skype för företag onlineprestanda:](tune-skype-for-business-online-performance.md)** Använd följande artiklar för att finjustera prestandan Skype för företag online. 
  
 **[Justera SharePoint onlineprestanda:](tune-sharepoint-online-performance.md)** Använd följande artiklar för att finjustera prestandan SharePoint online. 
  
 **[Justera Project Online prestanda:](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c)** Använd den här artikeln för att finjustera Project Online prestanda.