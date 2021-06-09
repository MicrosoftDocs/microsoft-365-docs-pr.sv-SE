---
title: Stöd för NAT med Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2017
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: 170e96ea-d65d-4e51-acac-1de56abe39b9
description: I den här artikeln finns information om hur du kan ange ungefärligt antal klienter som du kan använda per IP-adress i organisationen med NAT.
ms.openlocfilehash: f48874853c3acb80927933761862b14379b6d4bd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694314"
---
# <a name="nat-support-with-office-365"></a>Stöd för NAT med Office 365

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Tidigare rekommenderades att det maximala antalet Exchange-klienter per IP-adress vid anslutning till Office 365 var cirka 2 000 klienter per nätverksport.
  
## <a name="why-use-nat"></a>Varför ska jag använda NAT?

Med hjälp av NAT kan tusentals personer i ett företagsnätverk "dela" några få offentligt dirigerbara IP-adresser.
  
De flesta företagsnätverk använder privata IP-adressutrymmen (RFC1918). Det privata adressutrymmet tilldelas av IANA (Internet Assigned Numbers Authority) och det är endast avsett för nätverk som inte dirigeras direkt till och från det globala Internet.
  
Organisationer tillhandahåller åtkomst för enheter i ett privat IP-adressutrymme med hjälp av gatewaytekniker som brandväggar och proxyenheter som tillhandahåller NAT- (Network Address Translation) eller PAT-tjänster (Port Address Translation). Dessa gateways gör att trafik från interna enheter till Internet (inklusive Office 365) ser ut att komma från en eller flera offentligt dirigerbara IP-adresser. Varje utgående anslutning från en intern enhet omvandlas till en annan TCP-port på den offentliga IP-adressen. 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a>Varför måste så många anslutningar vara öppna för Office 365 samtidigt?

Outlook kan öppna åtta eller fler anslutningar (i situationer där det finns tillägg, delade kalendrar, postlådor osv.). Eftersom det finns maximalt 64 000 portar tillgängliga på en Windows-baserad NAT-enhet kan det finnas högst 8 000 användare bakom en IP-adress innan portarna tar slut. Observera att om kunder använder icke-Windows os-baserade enheter för NAT är det totala antalet tillgängliga portar beroende av vilken NAT-enhet eller -programvara som används. I det här scenariot kan det maximala antalet portar vara mindre än 64 000. Portars tillgänglighet påverkas också av andra faktorer, till exempel Windows som begränsar 4 000 portar för eget bruk, vilket minskar det totala antalet tillgängliga portar till 60 000. Det kan finnas andra program, till exempel Internet Explorer, som kan ansluta samtidigt och kräva ytterligare portar.
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a>Beräkna det maximala antalet enheter som stöds bakom en offentlig IP-adress med Office 365

Om du vill beräkna det maximala antalet enheter som kan finnas bakom en offentlig IP-adress bör du övervaka nätverkstrafiken och fastställa den högsta portanvändningen per klient. En högtrafikfaktor bör även användas för portanvändningen (lägst 4). 
  
 **Använd följande formel för att beräkna antalet enheter som stöds per IP-adress:**
  
Det högsta antalet enheter bakom en offentlig IP-adress = (64 000 - begränsade portar)/(Högsta portanvändning + högtrafikfaktor)
  
 **Om följande till exempel är sant:**
  
- **Begränsade portar:** 4 000 för operativsystemet

- **Högsta portanvändning:** 6 per enhet

- **Toppfaktor:** 4

Det maximala antalet enheter som stöds bakom en offentlig IP-adress är då = (64 000 - 4 000)/(6 + 4) = 6 000
  
I och med lanseringen av Office 365-värdpaketet, som ingår i uppdateringarna från september 2011 för Microsoft Office Outlook 2007 eller november 2011 för Microsoft Outlook 2010, eller en senare uppdatering, kan antalet anslutningar från Outlook (både Office Outlook 2007 med Service Pack 2 och Outlook 2010) till Exchange vara så få som 2. Du måste faktor för olika operativsystem, användarbeteenden och så vidare för att fastställa det lägsta och högsta antalet portar som ditt nätverk kräver högst.
  
Om du vill stödja fler enheter bakom en offentlig IP-adress följer du stegen som beskrivs för att bedöma det maximala antal enheter som stöds:
  
Övervaka nätverkstrafiken och fastställ den högsta portanvändningen per klient. Samla in dessa data:
  
- Från flera platser
    
- Från flera enheter
    
- Vid flera tidpunkter
    
Använd formeln ovan för att beräkna det maximala antalet användare per IP-adress som stöds i miljön.
  
Det finns olika metoder för att distribuera klientbelastningen på ytterligare offentliga IP-adresser. Vilka strategier som är tillgängliga beror på funktionerna i företagets gatewaylösning. Den enklaste lösningen är att segmentera användaradressutrymmet och statiskt "tilldela" varje gateway ett antal IP-adresser. Ett annat alternativ som många gatewayenheter erbjuder är möjligheten att använda en IP-adresspool. Fördelen med adresspoolen är att den är mycket mer dynamisk och med mindre sannolikhet kommer det att krävas justeringar när användarbasen växer.
  
## <a name="see-also"></a>Se även

[Hantera Office 365-slutpunkter](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Office 365-slutpunkter – vanliga frågor och svar](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
