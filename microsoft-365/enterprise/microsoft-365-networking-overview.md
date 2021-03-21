---
title: Översikt för Microsoft 365 nätverksanslutning
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: Här diskuteras varför nätverksoptimering är viktigt för SaaS-tjänster, målet för Microsoft 365-nätverk och hur SaaS kräver olika nätverk från andra arbetsbelastningar.
ms.openlocfilehash: d1a2b79f6e4042b97ec5a31d0ff92175baa1218e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923188"
---
# <a name="microsoft-365-network-connectivity-overview"></a>Översikt över Microsoft 365-nätverksanslutning

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Microsoft 365 är ett SaaS-moln (Software-as-a-Service) som tillhandahåller produktivitets- och samarbetsscenarier genom en diverse uppsättning mikrotjänster och program. Klientkomponenter av Microsoft 365, till exempel Outlook, Word och PowerPoint, körs på användardatorer och ansluter till andra komponenter i Microsoft 365 som körs i Microsoft-datacenter. Den mest signifikanta faktorn som bestämmer kvaliteten på Microsoft 365-slutanvändarens upplevelse är nätverkstillförlitlighet och låg fördröjning mellan Microsoft 365-klienter och Microsoft 365-tjänste front dörrar.

I den här artikeln får du lära dig mer om målen för Microsoft 365-nätverk och varför Microsoft 365-nätverk kräver en annan optimeringsmetod än allmän Internettrafik.

## <a name="microsoft-365-networking-goals"></a>Nätverksmål för Microsoft 365

Det ultimata målet med Microsoft 365-nätverk är att optimera slutanvändarupplevelsen genom att möjliggöra den minst restriktiva åtkomsten mellan klienter och de närmaste Microsoft 365-slutpunkterna. Slutanvändarupplevelsens kvalitet är direkt relaterad till prestanda och svarstiden för programmet som användaren använder. Till exempel förlitar sig Microsoft Teams på låg fördröjning så att användarnas telefonsamtal, konferenser och samarbete på delad skärm blir problemfria, och Outlook förlitar sig på bra nätverksanslutningar för funktioner för snabbsökning som utnyttjar serverindexering och AI-funktioner.

Det primära målet i nätverksdesignen bör vara att minimera svarstiden genom att minska tidsfördröjning för returresor (RTT) från klientdatorer till Microsoft Global Network, Microsofts offentliga stamnät som sammanbinder alla Microsofts datacenter med låg latens, molnbaserade startpunkter för program med hög tillgänglighet över hela världen. Du kan läsa mer om Microsofts globala nätverk i [Hur Microsoft bygger sitt snabba och tillförlitliga globala nätverk](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

Det behöver inte vara svårt att optimera Prestanda i Microsoft 365-nätverk. Du får bästa möjliga prestanda genom att följa några viktiga principer:

- Identifiera Microsoft 365-nätverkstrafik
- Tillåt lokal utgående lokal gren av Microsoft 365-nätverkstrafik till Internet från varje plats där användare ansluter till Microsoft 365
- Tillåta Microsoft 365-trafik att förbikoppla proxyenheter och paketinspektionsenheter

Mer information om nätverksanslutningsprinciper för Microsoft 365 finns i Principer för [Microsoft 365-nätverksanslutning.](microsoft-365-network-connectivity-principles.md)

## <a name="traditional-network-architectures-and-saas"></a>Traditionella nätverksarkitekturer och SaaS

Traditionella principer för nätverksarkitektur för klient-/serverarbetsbelastning är utformade kring antagandet att trafiken mellan klienter och slutpunkter inte sträcker sig utanför företagsnätverkets perimeter. I många företagsnätverk passerar även alla utgående Internetanslutningar företagsnätverket och den utgående platsen från en central plats.

I traditionella nätverksarkitekturer är högre svarstid för allmän Internettrafik en nödvändig kompromiss för att upprätthålla nätverkets perimetersäkerhet och prestandaoptimering för Internettrafik innebär normalt att utrustningen uppgraderas eller skalas ut vid nätverkets utgående punkter. Den här metoden uppfyller dock inte kraven för optimala nätverksprestanda för SaaS-tjänster som Microsoft 365.

## <a name="identifying-microsoft-365-network-traffic"></a>Identifiera Microsoft 365-nätverkstrafik

Vi gör det enklare att identifiera Microsoft 365-nätverkstrafik och göra det enklare att hantera nätverksidentifieringen.

- Nya kategorier av nätverksslutpunkter för att skilja mycket kritisk nätverkstrafik från nätverkstrafik som inte påverkas av Internetfördröjningar. Det finns bara ett litet antal URL:er och stöd för IP-adresser i den mest kritiska "Optimera"-kategorin.
- Webbtjänster för skriptanvändning eller direkt enhetskonfiguration och ändringshantering av Microsoft 365 nätverksidentifiering. Ändringar är tillgängliga från webbtjänsten, i RSS-format eller via e-post med hjälp av en Microsoft Flow-mall.
- [Office 365 Network-partnerprogram](./microsoft-365-networking-partner-program.md) med Microsoft-partner som tillhandahåller enheter eller tjänster som följer principer för Microsoft 365-nätverksanslutning och har enkel konfiguration.

## <a name="securing-microsoft-365-connections"></a>Skydda Microsoft 365-anslutningar

Syftet med den traditionella nätverkssäkerheten är att skärpa företagets nätverksgräns mot intrång och skadlig exploatering. De flesta företagsnätverk tillämpar nätverkssäkerhet för Internettrafik med hjälp av tekniker som proxyservrar, brandväggar, SSL-avbrott och -kontroller, djup paketinspektion och skyddssystem mot dataförlust. Dessa tekniker ger viktig riskreducering för allmänna internetförfrågningar, men kan drastiskt minska prestanda, skalbarhet och kvalitet på slutanvändarens upplevelse när den används på slutpunkter för Microsoft 365.

Microsoft 365 uppfyller organisationens behov av innehållssäkerhet och dataanvändning med inbyggda säkerhets- och styrningsfunktioner särskilt utformade för Microsoft 365-funktioner och -arbetsbelastningar. Mer information om säkerhet och efterlevnad för Microsoft 365 finns i [Office 365-säkerhetsöversikten.](/office365/securitycompliance/security-roadmap) Mer information om Microsofts rekommendationer och supportplacering på avancerade nätverkslösningar som utför avancerad bearbetning på Microsoft 365-trafik finns i Använda nätverksenheter eller lösningar från tredje part i [Office 365-trafik.](https://support.microsoft.com/help/2690045)

## <a name="why-is-microsoft-365-networking-different"></a>Varför är Microsoft 365-nätverk annorlunda?

Microsoft 365 har utformats för optimala prestanda med hjälp av slutpunktssäkerhet och krypterade nätverksanslutningar, vilket minskar behovet av att upprätthålla perimetersäkerhet. Microsoft 365-datacenter finns över hela världen och tjänsten är utformad för att använda olika metoder för att ansluta klienter till bästa tillgängliga tjänsteslutpunkter. Eftersom användardata och bearbetning fördelas mellan många Microsoft-datacenter finns det ingen enda nätverksslutpunkt som klientdatorer kan ansluta till. Data och tjänster i din Microsoft 365-klientorganisation optimeras dynamiskt av Microsofts globala nätverk för att anpassas till de geografiska platser som slutanvändarna kommer åt dem från.

Vissa vanliga prestandaproblem skapas när Microsoft 365-trafik är under kontroll av paket och centraliserad utgående trafik:

- Hög svarstid kan orsaka extremt dålig prestanda för video- och ljudströmmar och långsam respons av datahämtning, sökningar, samarbete i realtid, ledig/upptagen-information i kalendern, innehåll i produkten och andra tjänster
- Att anslutningar som utgående anslutningar från en central plats orsakar förlust av dynamiska routningsfunktioner i det globala Microsoft 365-nätverket och svarstiden och tidsfördröjning för returer läggs till
- Dekryptera SSL-skyddad Microsoft 365-nätverkstrafik och kryptera den igen kan orsaka protokollfel och medför säkerhetsrisk

Om du förkortar nätverkssökvägen till Microsoft 365-startpunkter genom att tillåta att klienttrafiken går ut så nära deras geografiska plats som möjligt kan du förbättra anslutningsprestandan och slutanvändarupplevelsen i Microsoft 365. Den kan också bidra till att minska påverkan på framtida ändringar i nätverksarkitekturen för prestanda och tillförlitlighet i Microsoft 365. Den optimala anslutningsmodellen är att alltid tillhandahålla nätverks egress på användarens plats, oavsett om detta finns i företagsnätverket eller på fjärranslutna platser som hem, hotell, caféer och flygplatser. Allmän Internettrafik och WAN-baserad företagsnätverkstrafik skulle dirigeras separat och inte användas med den lokala direkt utgående modellen. Den här lokala direkt utgångsmodellen visas i diagrammet nedan.

![Lokal utgående nätverksarkitektur](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

Den lokala egress-arkitekturen har följande fördelar för Microsoft 365-nätverkstrafik över den traditionella modellen:
  
- Ger optimal Microsoft 365-prestanda genom att optimera väglängden. Slutanvändaranslutningar dirigeras dynamiskt till närmaste Microsoft 365-startpunkt av  Microsoft Global Networks distribuerade tjänst front door-infrastruktur, och trafiken dirigeras sedan internt till data- och tjänsteslutpunkter via Microsofts extremt låga tillgänglighets fiber med hög latens.
- Minskar belastningen på företagets nätverksinfrastruktur genom att tillåta lokal egress för Microsoft 365-trafik, förbikoppling av proxyenheter och kontrollenheter för trafik.
- Säkrar anslutningar i båda ändarna genom att utnyttja funktionerna för klientslutpunktssäkerhet och molnsäkerhet, så att redundanta nätverkssäkerhetstekniker undviks.

> [!NOTE]
> Infrastrukturen _för den distribuerade_ tjänsten front door är Microsofts globala nätverks mest tillgängliga och skalbara nätverkskant med geografiskt distribuerade platser. Den avslutar slutanvändaranslutningar och dirigerar dem effektivt inom Microsofts globala nätverk. Du kan läsa mer om Microsofts globala nätverk i [Hur Microsoft bygger sitt snabba och tillförlitliga globala nätverk](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

Mer information om hur du förstår och tillämpar Microsoft 365 nätverksanslutningsprinciper finns i Principer för [Microsoft 365-nätverksanslutning.](microsoft-365-network-connectivity-principles.md)

## <a name="conclusion"></a>Sammanfattning

En optimering av Microsoft 365-nätverksprestandan handlar faktiskt om att ta bort onödiga hinder. Genom att behandla Microsoft 365-anslutningar som betrodd trafik kan du förhindra att svarstiden introduceras genom paketinspektion och konkurrens om proxybandbredd. Om du tillåter lokala anslutningar mellan klientdatorer och Office 365-slutpunkter kan trafiken dirigeras dynamiskt genom Microsofts globala nätverk.

## <a name="related-topics"></a>Relaterade ämnen

[Microsoft 365-nätverksanslutningsprinciper](microsoft-365-network-connectivity-principles.md)

[Hantera Office 365-slutpunkter](managing-office-365-endpoints.md)

[URL-adresser och IP-adressintervall för Office 365](urls-and-ip-address-ranges.md)

[Office 365 IP-adress och URL webbtjänst](microsoft-365-ip-web-service.md)

[Utvärdera Microsoft 365 nätverksanslutningar](assessing-network-connectivity.md)

[Nätverksplanering och prestandajustering för Microsoft 365](network-planning-and-performance.md)

[Prestandajustering för Office 365 med baslinjer och prestandahistorik](performance-tuning-using-baselines-and-history.md)

[Plan för prestandafelsökning för Office 365](performance-troubleshooting-plan.md).

[Nätverk för innehållsleverans (CDN)](content-delivery-networks.md)

[Microsoft 365 anslutningstest](https://aka.ms/netonboard)

[Hur Microsoft bygger ett snabbt och tillförlitligt globalt nätverk](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365 Nätverksbloggen](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)