---
title: Hantera ExpressRoute för Office 365
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
description: Lär dig hur du hanterar ExpressRoute för Office 365, inklusive vanliga områden för att konfigurera liknande prefix filtrering, säkerhet och efterlevnad.
ms.openlocfilehash: 5b55150b91b68954cb7b701afb7cf46ab9b951dd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694921"
---
# <a name="managing-expressroute-for-office-365-connectivity"></a>Hantera ExpressRoute för Office 365

ExpressRoute för Office 365 erbjuder en alternativ cirkulations väg för många Office 365-tjänster utan att behöva all trafik för att komma ut på Internet. Även om Internet anslutningen till Office 365 fortfarande behövs kan de specifika vägar som Microsoft annonserar via BGP till nätverket göra den direkt ExpressRoute-kretsen förvald såvida det inte finns andra konfigurationer i ditt nätverk. De tre vanligaste områdena du kanske vill konfigurera för att hantera denna operationsföljd inkluderar prefix, säkerhet och efterlevnad.
  
> [!NOTE]
> Microsoft har ändrat hur Microsoft peering routing-domänen granskas för Azure ExpressRoute. Från och med den 31 juli 2017 kan alla Azure ExpressRoute-kunder aktivera Microsoft peering direkt från den administrativa administrations konsolen för Azure eller via PowerShell. När du har aktiverat Microsoft peering kan en kund skapa väg filter för att ta emot BGP-vägfilter för Dynamics 365-program för kund engagemang (kallades tidigare CRM Online). Kunder som behöver Azure ExpressRoute för Office 365 måste få en recension från Microsoft innan de kan skapa väg filter för Office 365. Kontakta ditt Microsoft-konto för att få veta mer om hur du kan begära en recension för att aktivera Office 365 ExpressRoute. Icke-auktoriserade abonnemang vid försök att skapa väg filter för Office 365 får ett [fel meddelande](https://support.microsoft.com/kb/3181709)
  
## <a name="prefix-filtering"></a>Prefixlängd

Microsoft rekommenderar att kunderna accepterar alla BGP-vägar som annonseras från Microsoft, men vägarna tillhandahålls av en grundlig gransknings-och verifierings process som tar bort alla fördelar för att lägga till granskning. ExpressRoute erbjuder de rekommenderade kontrollerna som till exempel ägande, integritet och skala – med ingen filtrering av inkommande vägar på kund sidan.
  
Om du behöver mer verifiering av vägens ägarskap över ExpressRoute Public peering kan du kontrol lera de annonserade vägarna mot listan över alla IPv4-och IPv6-IP-prefix som representerar [Microsofts offentliga IP-adressintervall](https://www.microsoft.com/download/details.aspx?id=53602). Dessa områden täcker hela adress utrymmet och ändrar sig sällan, vilket ger en tillförlitlig uppsättning områden att filtrera sig mot, vilket ger ytterligare skydd för kunder som är bekymrade över icke-Microsofts ägda vägar som läcker fram i sin miljö. I händelse av att det finns en ändring kommer den att göras den 1 i månaden och versions numret i **informations** avsnittet på sidan ändras varje gång filen uppdateras.
  
Det finns ett antal skäl för att undvika användning av [Office 365 URL-adresser och IP-adressintervall](https://aka.ms/o365endpoints) för att skapa prefix filter listor. Bland annat:
  
- Office 365 IP-prefix genomgår många ändringar oftare.

- Office 365 URL-adresser och IP-adressintervall är avsedda för att hantera listor över brand väggar och proxyservrar, inte routning.

- URL-adresser och IP-adressintervall för Office 365 omfattar inte andra Microsoft-tjänster som kan finnas i omfattning för dina ExpressRoute-anslutningar.

|**Alternativ**|**Komplexitet**|**Ändra kontroll**|
|:-----|:-----|:-----|
|Acceptera alla Microsoft-vägar  <br/> |**Lågt:** Kunden använder Microsoft-kontroller för att säkerställa att alla vägar ägs korrekt.  <br/> |Inga  <br/> |
|Filtrera Microsoft-ägda supernäten  <br/> |**Mellan:** Kund implementerar sammanfattade prefix filter listor för att endast tillåta Microsoft-ägda vägar.  <br/> |Kunderna måste se till att de invanliga uppdateringarna återspeglas i väg filter.  <br/> |
|Filtrera Office 365 IP-adressintervall  <br/> [!CAUTION] Rekommenderas inte |**Hög:** Kund filtrerar vägar baserat på definierade IP-prefix för Office 365.  <br/> |Kunderna måste implementera en robust ändrings hanterings process för månads uppdateringar.  <br/> [!CAUTION] Denna lösning kräver viktiga pågående ändringar. Ändringar som inte implementerats i tid innebär troligen ett tjänst avbrott.   |

Anslutning till Office 365 med Azure ExpressRoute baseras på BGP-annonser med specifika IP-undernät som representerar nätverk där slut punkter för Office 365 distribueras. På grund av den globala karaktären hos Office 365 och antalet tjänster som utgör Office 365 har kunderna ofta behov att hantera de annonser de accepterar i sitt nätverk. Om du är bekymrad med antalet prefix som annonseras i din miljö kan du använda [BGP community](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099) -funktionen för att filtrera annonserna till en viss uppsättning Office 365-tjänster. Den här funktionen är nu i förhands granskning.
  
Oavsett hur du hanterar BGP-vägfilter som kommer från Microsoft, får du ingen särskild exponering för Office 365-tjänster när du jämförs med att ansluta till Office 365 via en Internet-krets ensam. Microsoft upprätthåller samma regler för säkerhet, efterlevnad och prestanda oavsett vilken typ av krets en kund använder för att ansluta till Office 365.
  
### <a name="security"></a>Säkerhet

Microsoft rekommenderar att du upprätthåller dina egna nätverks-och säkerhets gräns kontroller för anslutningar som skickas till och från ExpressRoute offentlig och Microsoft peering, vilket inkluderar anslutningar till och från Office 365-tjänster. Säkerhets kontroller bör användas för nätverks förfrågningar som skickas från nätverket till Microsoft-nätverket samt inkommande från Microsofts nätverk till nätverket.
  
#### <a name="outbound-from-customer-to-microsoft"></a>Utgående från kund till Microsoft
  
När datorer ansluts till Office 365 ansluter de till samma uppsättning slut punkter oavsett om anslutningen görs via en Internet-eller en ExpressRoute-krets. Oavsett vilken krets som används rekommenderar Microsoft att du hanterar Office 365-tjänster som tillförlitligare än allmänna Internet destinationer. Dina utgående säkerhets kontroller bör fokusera på portar och protokoll för att minska exponeringen och minimera löpande underhåll. Den portinformation som krävs finns i referens artikeln för [Office 365-slut punkter](https://aka.ms/o365endpoints) .
  
För att lägga till kontroller kan du använda FQDN-nivå filtrering i din proxyserver för att begränsa eller inspektera vissa eller alla nätverks begär Anden som är avsedda för Internet eller Office 365. Att underhålla listan med FQDN-funktioner när funktionerna släpps och att Office 365-tjänsterna utvecklas kräver mer robust ändrings hantering och spårning av ändringar i de publicerade [Office 365-slutpunkterna](https://aka.ms/o365endpoints).
  
> [!CAUTION]
> Microsoft rekommenderar att du inte enbart förlitar dig på IP-prefix för att hantera utgående säkerhet till Office 365.

|**Alternativ**|**Komplexitet**|**Ändra kontroll**|
|:-----|:-----|:-----|
|Inga begränsningar  <br/> |**Lågt:** Kunden tillåter obegränsad utgående åtkomst till Microsoft.  <br/> |Inga  <br/> |
|Port begränsningar  <br/> |**Lågt:** Kunden begränsar utgående åtkomst till Microsoft av de förväntade portarna.  <br/> |Sällan.  <br/> |
|Begränsningar för FQDN  <br/> |**Hög:** Kunden begränsar utgående åtkomst till Office 365 baserat på publicerade FQDN: er.  <br/> |Månads ändringar.  <br/> |

#### <a name="inbound-from-microsoft-to-customer"></a>Inkommande från Microsoft till kund
  
Det finns flera valfria scenarier som kräver att Microsoft initierar anslutningar till ditt nätverk.
  
- ADFS vid lösen ords verifiering för inloggning.

- [Hybrid distributioner av Exchange Server](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx).

- E-post från en Exchange Online-klient till en lokal värd.

- SharePoint Online mail skicka från SharePoint Online till en lokal värd.

- [SharePoint-federerad hybrid sökning](https://technet.microsoft.com/library/dn197174.aspx).

- [SharePoint hybrid BCS](https://technet.microsoft.com/library/dn197239.aspx ).

- [Skype för företag – hybrid](https://technet.microsoft.com/library/jj205403.aspx) -och/eller [Skype för företag-Federation](https://technet.microsoft.com/library/skype-for-business-online-federation-and-public-im-conectivity.aspx).

- [Moln kopplingen Skype för företag](https://technet.microsoft.com/library/mt605227.aspx ).

Microsoft rekommenderar att du godkänner dessa anslutningar över Internet kretsen i stället för ExpressRoute-kretsen för att minska komplexiteten. Om dina krav på efterlevnad eller prestanda avgör att dessa inkommande anslutningar måste accepteras via en ExpressRoute-krets rekommenderas en brand vägg eller omvänd proxyserver för att acceptera accepterade anslutningar. Du kan använda [Office 365-slutpunkterna](https://aka.ms/o365endpoints) för att ta reda på slut-FQDN och IP-prefix.
  
### <a name="compliance"></a>Efterlevnad

Den Dirigerings Sök väg som du använder för de efterföljande kontrollerna förlitar sig inte. Oavsett om du ansluter till Office 365-tjänster via en ExpressRoute eller Internet-krets ändras inte våra kontroll kontroller. Du bör granska de olika nivåerna för kompatibilitet och säkerhets certifiering för Office 365 för att ta reda på det bästa valet för att tillgodose organisationens behov.
  
Här är en kort länk som du kan använda för att komma tillbaka: [https://aka.ms/manageexpressroute365](https://aka.ms/manageexpressroute365)
  
## <a name="related-topics"></a>Relaterade ämnen

[Nätverk för innehålls leverans](content-delivery-networks.md)
  
[URL-adresser och IP-adressintervall för Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Hantera slut punkter för Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Azure ExpressRoute för Office 365-utbildning](https://channel9.msdn.com/series/aer)
