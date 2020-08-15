---
title: Planering för nätverk och migrering för Office 365
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
description: Den här artikeln innehåller länkar till information om nätverks planering, test och migrering till Office 365.
ms.openlocfilehash: 1e6973f93c65012f4ca007332a47cc6b9e67b3b0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694875"
---
# <a name="network-and-migration-planning-for-office-365"></a>Planering för nätverk och migrering för Office 365

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Den här artikeln innehåller länkar till information om nätverks planering och-testning och migrering till Office 365.
  
Innan du distribuerar för första gången eller migrerar till Office 365 kan du använda informationen i dessa ämnen för att uppskatta vilken bandbredd du behöver och sedan testa och kontrol lera att du har tillräckligt med bandbredd för att distribuera eller migrera till Office 365.

Den här artikeln är en del av [nätverks planering och prestanda justering för Office 365](https://aka.ms/tune).

Anvisningar för hur du optimerar ditt nätverk för Microsoft 365 och andra moln och tjänster från Microsoft finns i [Microsoft Cloud Networking for Enterprise Architects](https://aka.ms/cloudarchnetworking) affisch.
   
## <a name="estimate-network-bandwidth-requirements"></a>Uppskatta nätverks bandbredds krav
<a name="EstimateBandwidthRequirements"> </a>

Om du använder Office 365 kan din organisations Internet krets öka. Det är viktigt att ta reda på om det finns tillräckligt med bandbredd för att hantera den uppskattade ökningen när Office 365 är fullt distribuerat samtidigt som du håller minst 20% kapacitet för att hantera busiest.
  
Gör så här för att uppskatta bandbredden:
  
1. Utvärdera antalet klienter som kommer att använda varje Internet-utgång. Låt vårt terabit nätverks handtag så mycket av anslutningen som möjligt. 
    
2. Avgöra vilka Office 365-tjänster och-funktioner som ska vara tillgängliga för klienter. Du kommer troligen att ha grupper med personer med olika tjänster eller användar profiler.
    
3. Mäta nätverks användning för en pilot grupp med klienter. Se till att pilot klienter är representativa för de olika företags profilerna i organisationen samt till olika geografiska platser. Du kan göra en dubbel kontroll av dina resultat mot våra gamla räknare för [Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744) och [Skype för företag](https://go.microsoft.com/fwlink/p/?LinkId=321551) eller den [fallstudie](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365) som vi har utfört på ett eget nätverk. 
    
4. Använd måtten från pilot gruppen för att extrapolera hela organisationens behov och kontrol lera igen för att verifiera uppskattningarna innan du gör några ändringar i nätverket.
    
## <a name="test-your-existing-network"></a>Testa ditt befintliga nätverk
<a name="calculators"> </a>

 **Nätverks verktyg.** Testa och validera din Internet bandbredd för att ta reda på nedladdning, uppladdning och svars tids begränsningar. De här verktygen hjälper dig att avgöra nätverkets funktioner för migrering samt när du är fullständigt distribuerad. 
    
- [Microsoft Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=517243): testar anslutningen i din Exchange Online-miljö.
    
- Använd [Microsoft-assistenten för support och återställning för Office 365](https://diagnostics.office.com/#/Download?env=SOC) för att åtgärda problem med Outlook och Office 365. 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a>Metod tips för nätverks planering och förbättring av migrerings prestanda för Office 365
<a name="BestPractices"> </a>

Se till att få mer information om hur du förbättrar Office 365-upplevelsen.
  
1. Vill du hjälpa användare att komma igång? I [metod tips för hur du använder office 365 i ett långsamt nätverk](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) får du tips om hur du använder Office 365, till exempel SharePoint Online, Exchange Online och Lync Online, när nätverket inte är samarbetsvilligt. Den här artikeln länkar ut till massor av innehåll på TechNet och Support.office.com för att optimera Office 365-upplevelsen och innehåller information om enkla sätt att anpassa dina webb sidor och hur du ställer in dina Internet Explorer-inställningar för den bästa Office 365-upplevelsen. 
    
2. Läs [principer för office 365-nätverks anslutningar](https://aka.ms/o365networkingprinciples) för att förstå anslutnings principerna för säkert hantera Office 365-trafik och få bästa möjliga prestanda. Den här artikeln hjälper dig att förstå de senaste anvisningarna för att optimera Office 365-nätverks anslutningen. 
    
3. Förbättra prestanda för programmigrering genom att noggrant hantera schemat för Windows-uppdateringar. Du kan uppdatera dina klient datorer i grupper och kontrol lera att alla klient datorer uppdateras innan du migrerar till Office 365 för att reglera användningen av nätverks bandbredd. Mer information finns i [manuell uppdatering och konfigurering av skriv bord för Office 365 för de senaste uppdateringarna](https://support.microsoft.com/gp/office-2013-365-update).
    
4. Office 365-nätverks trafik fungerar bäst när den behandlas som en betrodd Internet tjänst och tillåts att kringgå mycket av traditionell filtrering och genomsökning som vissa organisationer placerar på nätverks trafik till icke betrodda Internet tjänster. Detta inkluderar vanligt vis borttagning av utgående bearbetning, såsom proxyautentisering och paket kontroll, samt att det lokala utfallet till Internet med korrekt NAT-adress (Network Address Translation) och tillräcklig bandbredds kapacitet kan hantera de utökade nätverks förfrågningarna. Se [Hantera office 365-slutpunkter](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)för ytterligare vägledning om hur du konfigurerar nätverket för att hantera Office 365 som en tillförlitlig Internet tjänst i nätverket.
    
1. Se till att [Hantera Office 365-slutpunkter](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a). Den ytterligare trafiken till Office 365 ger ökad till gång till utgående proxyanslutningar samt en ökning av den säkra trafiken via TLS/SSL.
    
2. Om dina utgående proxyservrar kräver användarautentisering kan anslutningen bli långsam eller förloras. Att kringgå autentiseringskrav för Office 365-domänerna kan minska denna omkostnad.
    
3. Om du har ett stort antal delade kalendrar och post lådor kan du se en ökning av antalet anslutningar från Outlook till Exchange. Outlook-klienten kan till exempel öppna upp till två ytterligare anslutningar för varje delad kalender som används. I det här fallet kontrollerar du att utgående proxy kan hantera anslutningarna, eller att kringgå proxyn för anslutningar till Office 365 för Outlook.
    
4. Fastställ maximalt antal enheter som stöds för en offentlig IP-adress och hur du ska använda flera IP-adresser. Mer information finns i avsnittet [om stöd för NAT med Office 365](nat-support-with-microsoft-365.md).
    
5. Om du håller på att kontrol lera utgående anslutningar från datorer i nätverket kan du förbättra anslutningen och prestanda genom att kringgå den här filtreringen till Office 365-domänerna. Genom att kringgå utgående inspektioner tar du ofta dessutom bort behovet av en enda avgång på Internet och aktiverar lokal Internet för Office 365 till nätverks begär Anden.
    
6. Vissa kunder hittar interna nätverks inställningar kan påverka prestanda. Inställningar som MTU-storlek (Maximum Transmission Unit), automatisk förhandling eller automatisk avkänning och under optimala vägar till Internet är vanliga platser att titta på.
    
## <a name="network-planning-reference-for-office-365"></a>Referens för nätverks planering för Office 365
<a name="NetReference"> </a>

Dessa ämnen innehåller detaljerad information om Office 365-nätverks referenser.
  
- [Hantera slut punkter för Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [Nätverk för innehålls leverans](content-delivery-networks.md)
    
- [Externa DNS-poster för Office 365](external-domain-name-system-records.md)
    
- [IPv6-stöd i Office 365-tjänster](ipv6-support.md)
    
- [Principer för nätverks anslutning för Office 365](https://aka.ms/o365networkingprinciples)
    
- [Vanliga frågor och svar om Office 365](office-365-video-networking-faq.md)
    
- [Planera för nätverks enheter som ansluter till Office 365-tjänster](plan-for-network-devices.md)
    
- [Installations guider för Office 365-tjänster](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a>Se även

[Översikt över Microsoft 365 Enterprise](microsoft-365-overview.md)
