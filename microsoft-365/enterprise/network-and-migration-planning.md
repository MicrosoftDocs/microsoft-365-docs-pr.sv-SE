---
title: Nätverks- och migreringsplanering för Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: Den här artikeln innehåller länkar till information om nätverksplanering, tester och migrering till Office 365.
ms.openlocfilehash: 99bcc1bd0447b192860fc0bcc67fc18d87c2d5fc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923594"
---
# <a name="network-and-migration-planning-for-office-365"></a>Nätverks- och migreringsplanering för Office 365

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Den här artikeln innehåller länkar till information om nätverksplanering och -testning samt migrering till Office 365.
  
Innan du distribuerar för första gången eller migrerar till Office 365 kan du använda informationen i följande avsnitt för att uppskatta vilken bandbredd du behöver och sedan testa och verifiera att du har tillräckligt med bandbredd för att distribuera eller migrera till Office 365.

Den här artikeln är en [del av Nätverksplanering och prestandajustering för Office 365](./network-planning-and-performance.md).

Instruktioner för hur du optimerar nätverket för Microsoft 365 och andra molnplattformar och -tjänster från Microsoft finns på postern [Microsoft Cloud Networking for Enterprise Architects.](../solutions/cloud-architecture-models.md)
   
## <a name="estimate-network-bandwidth-requirements"></a>Beräkna bandbreddskrav för nätverket
<a name="EstimateBandwidthRequirements"> </a>

Användning Office 365 kan öka utnyttjandet av din organisations internetkrets. Det är viktigt att fastställa om den mängd bandbredd som är tillgänglig för närvarande är tillräcklig för att hantera den uppskattade ökningen när Office 365 är helt distribuerad med minst 20 % ytterligare kapacitet för dagarna med mest trafik.
  
Gör så här för att uppskatta bandbredden:
  
1. Utvärdera antalet klienter som kommer att använda varje Internet-utgång. Låt vårt nätverk med flera terabit hantera så mycket av anslutningen som möjligt. 
    
2. Avgör vilka Office 365 tjänster och funktioner som kan användas av klienter. Det kommer antagligen att finns grupper med personer med olika tjänster eller användningsprofiler.
    
3. Mät nätverksanvändningen för en testgrupp med klienter. Se till att testklienterna är representativa för olika användarprofiler i organisationen och för olika geografiska platser. Du kan korskolla resultaten med våra gamla kalkylatorer för [Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744) [](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365) och [Microsoft Teams](/microsoftteams/prepare-network) fallstudien vi utförde på vårt eget nätverk. 
    
4. Använd måtten från pilotgruppen till att extrapolera hela organisationens behov och testa om för att verifiera uppskattningarna innan du gör några ändringar i nätverket.
    
## <a name="test-your-existing-network"></a>Testa ditt befintliga nätverk
<a name="calculators"> </a>

 **Nätverksverktyg.** Testa och validera Internetbandbredden och fastställ begränsningar för hämtning, överföring och svarstid. Med de här verktygen kan du fastställa nätverksfunktioner för migrering och efter fullständig distribution. 
    
- [Microsoft Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=517243): Testar anslutningen i din Exchange Online miljö.
    
- Använd [Microsoft-webbplatsen Support- och återställningsassistenten för Office 365](https://diagnostics.office.com/#/Download?env=SOC) att Outlook och Office 365 problem. 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a>Rekommendationer för nätverksplanering och förbättring av migreringsprestanda för Office 365
<a name="BestPractices"> </a>

Fördjupa dig lite djupare i de här metodtipsen för mer information om hur du Office 365 upplevelsen.
  
1. Vill du komma igång och hjälpa användarna direkt? I [Metodtips](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) för att använda Office 365 i ett långsamt nätverk finns tips om hur du använder Office 365, till exempel SharePoint Online, Exchange Online och Lync Online, när nätverket inte är aktivt. I den här artikeln finns länkar till innehåll på TechNet och Support.office.com som optimerar din upplevelse av Office 365. Här finns information om enkla sätt att anpassa webbsidor och hur du ställer in inställningarna för Internet Explorer för bästa Office 365 upplevelse. 
    
2. Läs [Office 365 principer för nätverksanslutning](./microsoft-365-network-connectivity-principles.md) för att förstå anslutningsprinciperna för säker hantering av Office 365 och få bästa möjliga prestanda. Den här artikeln hjälper dig att förstå de senaste vägsvägledningen för att på ett säkert sätt Office 365 nätverksanslutningar. 
    
3. Förbättra e-postmigreringsprestandan med noggrann schemahantering Windows uppdateringar. Du kan gruppindelar uppdatera klientdatorerna och säkerställa att alla klientdatorer är uppdaterade innan du migrerar till Office 365 och reglera användningen av nätverksbandbredden. Mer information finns i [Uppdatera och konfigurera skrivbord manuellt för Office 365 för de senaste uppdateringarna.](https://support.microsoft.com/gp/office-2013-365-update)
    
4. Office 365 nätverkstrafik presterar bäst när den hanteras som en betrodd Internettjänst och tillåts kringgå mycket av den traditionella filtrering och genomsökning som en del organisationer placerar på nätverkstrafik till icke betrodda Internettjänster. Det omfattar vanligtvis borttagning av utgående bearbetning som proxyanvändares autentisering och paketinspektion, samt att säkerställa lokal utgående trafik till Internet med rätt NAT (Network Address Translation) och tillräcklig bandbreddskapacitet för att hantera ökade nätverksbegäranden. Mer information [om hur du Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)ditt nätverk för att hantera Office 365 som en betrodd Internettjänst i nätverket finns i Hantera Office 365 ändpunkter.
    
1. Hantera [Office 365 slutpunkter](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a). Den extra trafiken som Office 365 leder till en ökning av utgående proxyanslutningar samt en ökning av säker trafik via TLS/SSL.
    
2. Om dina utgående proxyserverier kräver autentisering av användare kan anslutningen gå långsammare eller också kan funktionaliteten gå förlorad. Det kan minska problemet genom att hoppa Office 365 autentiseringskravet för domänerna.
    
3. Om du har ett stort antal delade kalendrar och postlådor kan du eventuellt se en ökning av antalet anslutningar från Outlook till Exchange. Till exempel kan Outlook klient öppna upp till två extra anslutningar för varje delad kalender som används. I det här fallet ska du kontrollera att den utgående proxyn kan hantera anslutningarna, eller kringgå proxyn för anslutningar till Office 365 för Outlook.
    
4. Fastställ det maximala antalet enheter som stöds för en offentlig IP-adress och hur du lastbalanser över flera IP-adresser. Mer information finns [NAT-stöd med Office 365.](nat-support-with-microsoft-365.md)
    
5. Om du kontrollerar utgående anslutningar från datorer i nätverket kan du förbättra anslutningen och prestanda genom att hoppa över filtreringen till Office 365-domänerna. Om du kringgår utgående kontroll tas också ofta behovet av en enda Internet-utgång bort och lokal Internet-utgående trafik för Office 365 nätverksbegäranden på väg.
    
6. För vissa kunder kan interna nätverksinställningar påverka prestanda. Inställningar t.ex. maximal storlek på överföringsenheten (MTU), automatiska nätverksförhandlingar, automatisk identifiering och underoptimerade rutter till Internet är vanliga frågor.
    
## <a name="network-planning-reference-for-office-365"></a>Referens för nätverksplanering för Office 365
<a name="NetReference"> </a>

Följande avsnitt innehåller detaljerad Office 365 information om nätverksreferensen.
  
- [Hantera Office 365-slutpunkter](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [Nätverk för innehållsleverans](content-delivery-networks.md)
    
- [Externa DNS-poster för Office 365](external-domain-name-system-records.md)
    
- [IPv6-stöd i Office 365-tjänster](ipv6-support.md)
    
- [Office 365 principer för nätverksanslutningar](./microsoft-365-network-connectivity-principles.md)
    
- [Office 365 vanliga frågor och svar om videonätverk](office-365-video-networking-faq.md)
    
- [Planera för nätverksenheter som ansluter till Office 365 tjänster](plan-for-network-devices.md)
    
- [Installationsguider för Office 365 tjänster](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a>Se även

[Microsoft 365 Enterprise översikt](microsoft-365-overview.md)