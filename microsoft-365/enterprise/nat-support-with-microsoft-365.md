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
description: I den här artikeln finns information om hur man uppskattar antalet klienter som du kan använda per IP-adress i din organisation via NAT.
ms.openlocfilehash: f48874853c3acb80927933761862b14379b6d4bd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694314"
---
# <a name="nat-support-with-office-365"></a>Stöd för NAT med Office 365

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Tidigare föreslog vägledning att det högsta antalet Exchange-klienter du bör använda per IP-adress för att ansluta till Office 365 skulle ha 2 000-klienter per nätverks port.
  
## <a name="why-use-nat"></a>Varför ska jag använda NAT?

Genom att använda NAT kan tusentals personer i ett företags nätverk "dela" några få offentligt routade IP-adresser.
  
I de flesta företags nätverk används privata IP-adressutrymmet (RFC1918). Det privata adress utrymmet tilldelas av Internet Assigned Numbers Authority (IANA) och är endast avsett för nätverk som inte dirigerar direkt till och från det globala Internet.
  
För att ge Internet åtkomst till enheter i ett privat IP-adressutrymme använder organisationer Gateway-teknologin, till exempel brand väggar och proxyservrar som tillhandahåller NAT-eller port Address Translation-tjänster (PAT). Dessa gateways gör att trafik från interna enheter till Internet (inklusive Office 365) kommer från en eller flera offentligt routade IP-adresser. Varje utgående anslutning från en intern enhet översätts till en annan TCP-port på den offentliga IP-adressen. 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a>Varför måste du ha så många anslutningar att de är öppna för Office 365 samtidigt?

Outlook kan öppna åtta eller fler anslutningar (när det finns tillägg, delade kalendrar, post lådor och andra funktioner). Eftersom det finns högst 64 000 portar tillgängliga på en Windows-baserad NAT-enhet kan det högsta antalet 8 000-användare bakom en IP-adress innan portarna uttömts. Observera att om kunder använder datorer som inte är Windows OS-baserade kan de totala tillgängliga portarna vara beroende av vilken NAT-enhet eller program vara som används. I det här scenariot kan det högsta antalet portar vara mindre än 64 000. Tillgängligheten för portar påverkas också av andra faktorer som Windows begränsar 4 000-portar för eget bruk, vilket minskar det totala antalet tillgängliga portar för 60 000. Det kan finnas andra program, till exempel Internet Explorer, som kan ansluta samtidigt och kräva ytterligare portar.
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a>Beräkna högsta enheter som stöds bakom en enda offentlig IP-adress med Office 365

För att fastställa det högsta antalet enheter bakom en enda offentlig IP-adress bör du övervaka nätverks trafik för att fastställa högsta port förbrukning per klient. Dessutom bör en topp faktor användas för port användning (minst 4). 
  
 **Använd följande formel för att beräkna antalet enheter som stöds per IP-adress:**
  
Högsta enheter som stöds bakom en enda offentlig IP-adress = (64 000-begränsade portar)/(högsta port förbrukning + högsta faktor)
  
 **Om till exempel följande var sant:**
  
- **Begränsade portar:** 4 000 för operativ systemet

- **Högsta port förbrukning:** 6 per enhet

- **Högsta faktor:** 4

Sedan kan de högsta enheter som stöds bakom en enda offentlig IP-adress = (64 000-4000)/(6 + 4) = 6 000
  
Med utgivningen av Office 365-värd paketet, som ingår i uppdateringarna från september 2011 för Microsoft Office Outlook 2007 eller november 2011 för Microsoft Outlook 2010 eller senare uppdatering, kan antalet anslutningar från Outlook (både Office Outlook 2007 med Service Pack 2 och Outlook 2010) till Exchange vara så lite som 2. Du måste vara en faktor i de olika operativ systemen, användar funktioner och så vidare för att fastställa det lägsta och högsta antal portar som nätverket kräver vid hög belastning.
  
Om du vill ha stöd för fler enheter bakom en enda offentlig IP-adress följer du stegen som beskrivs för att utvärdera det maximala antalet enheter som stöds:
  
Övervaka nätverks trafik för att fastställa högsta port förbrukning per klient. Du bör samla in dessa data:
  
- Från flera platser
    
- Från flera enheter
    
- Flera gånger
    
Använd den föregående formeln för att beräkna maximalt antal användare per IP-adress som kan användas i miljön.
  
Det finns olika metoder för att distribuera klient belastning mellan ytterligare offentliga IP-adresser. Vilka strategier som är tillgängliga beror på funktionerna i Corporate Gateway-lösningen. Den enklaste lösningen är att segmentera ditt användar adress utrymme och statiskt "tilldela" ett antal IP-adresser till varje gateway. Ett annat alternativ till att många gateway-enheter kan använda en adresspool för IP-adresser. Fördelen med adresspoolen är att det är mycket mer dynamiskt och mindre troligt att det krävs justering när användar basen växer.
  
## <a name="see-also"></a>Se även

[Hantera slut punkter för Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Vanliga frågor om Office 365-slut punkter](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
