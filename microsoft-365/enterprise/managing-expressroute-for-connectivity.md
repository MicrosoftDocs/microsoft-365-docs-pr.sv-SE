---
title: Hantera ExpressRoute för Office 365-anslutningar
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/13/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: e4468915-15e1-4530-9361-cd18ce82e231
description: Lär dig hur du hanterar ExpressRoute för Office 365, inklusive vanliga områden för att konfigurera som prefixfiltrering, säkerhet och efterlevnad.
ms.openlocfilehash: e8de0763df7d592bc41802b1ead48df06891e6dc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916674"
---
# <a name="managing-expressroute-for-office-365-connectivity"></a>Hantera ExpressRoute för Office 365-anslutningar

ExpressRoute för Office 365 erbjuder en alternativ routningssökväg för att nå många Office 365-tjänster utan att all trafik måste gå till Internet. Även om Internetanslutningen till Office 365 fortfarande behövs gör de specifika vägar som Microsoft annonserar via BGP till ditt nätverk att den direkta ExpressRoute-kretsen prioriteras såvida det inte finns andra konfigurationer i nätverket. De tre vanligaste områdena du kanske vill konfigurera för att hantera den här dirigeringen inkluderar prefixfiltrering, säkerhet och efterlevnad.
  
> [!NOTE]
> Microsoft har ändrat hur routningsdomänen för Microsoft-peering granskas för Azure ExpressRoute. Från och med den 31 juli 2017 kan alla Azure ExpressRoute-kunder aktivera Microsoft-peering direkt via Azure-administratörskonsolen eller via PowerShell. När microsoft-peering har installerats kan alla kunder skapa routefilter för att ta emot BGP-routeannonsering för Dynamics 365 Customer Engagement-appar (tidigare kallat CRM Online). Kunder som behöver Azure ExpressRoute för Office 365 måste granskas av Microsoft innan de kan skapa routefilter för Office 365. Kontakta ditt Microsoft-kontoteam om du vill veta mer om hur du begär en granskning för att aktivera Office 365 ExpressRoute. Obehöriga prenumerationer som försöker skapa routefilter för Office 365 får [ett felmeddelande](https://support.microsoft.com/kb/3181709)
  
## <a name="prefix-filtering"></a>Prefixfiltrering

Microsoft rekommenderar att kunderna accepterar alla BGP-vägar som de annonseras från Microsoft. De vägar som tillhandahålls genomgår en mycket noggrann gransknings- och valideringsprocess som innebär att extra granskning inte ger några fördelar. ExpressRoute erbjuder inbyggt de rekommenderade kontrollerna, till exempel IP-prefixägarskap, integritet och skala – utan filtrering av inkommande route på kundsidan.
  
Om du kräver ytterligare validering av vägägarskapet i ExpressRoutes offentliga peering kan du kontrollera de annonserade rutter mot listan över alla IPv4- och IPv6-IP-prefix som representerar Microsofts offentliga [IP-intervall.](https://www.microsoft.com/download/details.aspx?id=53602) Intervallen omfattar hela Microsofts adressutrymme och ändras så sällan som möjligt, vilket ger en tillförlitlig uppsättning intervaller att filtrera mot som även ger ytterligare skydd till kunder som är oroliga att vägar som inte tillhör Microsoft ska läcka in i deras miljö. Om det sker en ändring görs den den 1:a i månaden och  versionsnumret i informationsavsnittet på sidan ändras varje gång filen uppdateras.
  
Det finns ett antal olika skäl till att undvika att använda URL:er och IP-adressintervall för [Office 365 för](./urls-and-ip-address-ranges.md) att generera prefixfilterlistor. Till exempel:
  
- IP-prefixen i Office 365 genomgår regelbundet många ändringar.

- URL:er och IP-adressintervall för Office 365 är utformade för att hantera listor över tillåtna brandväggar och proxyinfrastruktur, inte routning.

- URL:er och IP-adressintervall för Office 365 omfattar inte andra Microsoft-tjänster som kanske omfattas av dina ExpressRoute-anslutningar.

|**Alternativ**|**Komplexitet**|**Ändra kontroll**|
|:-----|:-----|:-----|
|Acceptera alla Microsoft-vägar  <br/> |**Låg:** Kunden använder sig av Microsoft-kontroller för att säkerställa att alla vägar har rätt ägare.  <br/> |Inga  <br/> |
|Filtrera supernät som ägs av Microsoft  <br/> |**Medel:** Kunden implementerar sammanfattningar av prefixfilterlistor så att endast vägar som ägs av Microsoft tillåts.  <br/> |Kunderna måste säkerställa att de oregelade uppdateringarna återspeglas i filtren.  <br/> |
|Filtrera IP-intervall för Office 365  <br/> [!CAUTION] Not-Recommended |**Hög:** Kunden filtrerar vägar baserat på definierade IP-prefix för Office 365.  <br/> |Kunderna måste implementera en robust ändringshanteringsprocess för månadsuppdateringarna.  <br/> [!CAUTION] Den här lösningen kräver betydande gång på gång-ändringar. Ändringar som inte implementeras i tid kommer troligtvis att resultera i driftavbrott för tjänsten.   |

Anslutning till Office 365 med hjälp av Azure ExpressRoute baseras på BGP-annonsering av specifika IP-undernät som representerar nätverk där Office 365-slutpunkter distribueras. På grund av den globala naturen hos Office 365 och antalet tjänster som utgör Office 365 behöver kunder ofta hantera de annonseringar som de accepterar på sitt nätverk. Om du bekymrar dig över antalet prefix som annonseras i miljön kan du med [BGP-communityfunktionen](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099) filtrera annonserna till en viss uppsättning Office 365-tjänster. Den här funktionen är nu i förhandsgranskningsläge.
  
Oavsett hur du hanterar BGP-routeannonseringarna från Microsoft får du inte någon särskild exponering för Office 365-tjänster jämfört med vid anslutning till Office 365 över enbart en internetkrets. Microsoft håller samma säkerhets-, efterlevnads- och prestandanivåer oavsett vilken typ av krets en kund använder sig av för att ansluta till Office 365.
  
### <a name="security"></a>Säkerhet

Microsoft rekommenderar att du har egna nätverks- och säkerhets perimeterkontroller för anslutningar till och från ExpressRoute offentligt och Microsoft-peering, vilket omfattar anslutningar till och från Office 365-tjänster. Säkerhetskontroller bör finnas för nätverksbegäranden som färdas ut från ditt nätverk till Microsofts nätverk samt inkommande från Microsofts nätverk till ditt nätverk.
  
#### <a name="outbound-from-customer-to-microsoft"></a>Utgående från kund till Microsoft
  
När datorer ansluter till Office 365 ansluter de till samma uppsättning slutpunkter oavsett om anslutningen görs via en Internetkrets eller en ExpressRoute-krets. Oavsett vilken krets som används rekommenderar Microsoft att du behandlar Office 365-tjänster som mer tillförlitliga än allmänna Internetdestinationer. Dina säkerhetskontroller för utgående trafik bör fokusera på portar och protokoll för att minska exponering och minimera det fortlöpande underhållet. Den portinformation som krävs finns i [referensartikeln om Office 365-slutpunkter.](./urls-and-ip-address-ranges.md)
  
För ytterligare kontroller kan du använda filtrering på FQDN-nivån i proxyinfrastrukturen för att begränsa eller kontrollera vissa eller alla nätverksbegäranden till Internet eller Office 365. Underhållet av listan över FQDN allt eftersom funktioner släpps och Office 365-erbjudandena utvecklas kräver stabilare ändringshantering och spårning av ändringar i de publicerade [Office 365-slutpunkterna.](./urls-and-ip-address-ranges.md)
  
> [!CAUTION]
> Microsoft rekommenderar att du inte enbart använder IP-prefix för att hantera säkerhet för utgående trafik i Office 365.

|**Alternativ**|**Komplexitet**|**Ändra kontroll**|
|:-----|:-----|:-----|
|Inga begränsningar  <br/> |**Låg:** Kunden ger obegränsad utgående åtkomst till Microsoft.  <br/> |Inga  <br/> |
|Portbegränsningar  <br/> |**Låg:** Kunden begränsar utgående åtkomst till Microsoft genom de förväntade portarna.  <br/> |Sällan förekommande.  <br/> |
|FQDN-begränsningar  <br/> |**Hög:** Kunden begränsar utgående åtkomst till Office 365 baserat på de publicerade FQDN.  <br/> |Månadsvisa ändringar.  <br/> |

#### <a name="inbound-from-microsoft-to-customer"></a>Inkommande från Microsoft till kund
  
Det finns flera valfria scenarier som kräver att Microsoft initierar anslutningar till ditt nätverk.
  
- ADFS under verifiering av lösenord för inloggning.

- [Exchange Server-hybriddistributioner.](/exchange/exchange-hybrid)

- E-post från en Exchange Online-klientorganisation till en lokal värd.

- E-post som skickas från SharePoint Online till en lokal värd.

- [Federerad SharePoint-hybridsökning](/SharePoint/hybrid/display-hybrid-federated-search-results-in-sharepoint-online).

- [SharePoint hybrid BCS](/SharePoint/hybrid/deploy-a-business-connectivity-services-hybrid-solution).

- [Skype för företag-hybrid](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) och/eller [Skype för företag-federation.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)

- [Skype för företag Cloud Connector](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition).

Microsoft rekommenderar att du godkänner dessa anslutningar via din internetkrets i stället för din ExpressRoute-krets för att minska komplexiteten. Om dina efterlevnads- eller prestandabehov dikterar dessa inkommande anslutningar måste accepteras via en ExpressRoute-krets rekommenderas användning av en brandvägg eller omvänd proxyserver för att begränsa de godkända anslutningarna. Du kan använda [Office 365-slutpunkterna för](./urls-and-ip-address-ranges.md) att ta reda på rätt FQDN och IP-prefix.
  
### <a name="compliance"></a>Efterlevnad

Vi förlitar oss inte på den routningssökväg du använder för våra efterlevnadskontroller. Oavsett om du ansluter till Office 365-tjänster via en ExpressRoute- eller internetkrets ändras inte våra efterlevnadskontroller. Du bör granska de olika efterlevnads- och säkerhetscertifieringsnivåerna för Office 365 för att ta reda på det bästa valet för att uppfylla organisationens behov.
  
Här är en kort länk som du kan använda för att komma tillbaka: [https://aka.ms/manageexpressroute365]()
  
## <a name="related-topics"></a>Relaterade ämnen

[Nätverk för innehållsleverans](content-delivery-networks.md)
  
[URL-adresser och IP-adressintervall för Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Hantera Office 365-slutpunkter](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Utbildning för Azure ExpressRoute för Office 365](https://channel9.msdn.com/series/aer)