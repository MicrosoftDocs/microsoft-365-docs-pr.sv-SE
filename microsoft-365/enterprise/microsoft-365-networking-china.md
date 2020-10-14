---
title: Microsoft 365 global prestanda optimering för användare av Kina
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
- m365initiative-coredeploy
search.appverid: MET150
f1.keywords:
- NOCSH
description: I den här artikeln finns vägledning för hur du optimerar nätverks prestanda för användare av globala Microsoft 365-klient organisationer.
ms.openlocfilehash: 9b397e60b4a3b80563ed31731a6f7aa8e0bdab7f
ms.sourcegitcommit: d76a4c07f0be2938372bdfae50e0e4d523bd8e9f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456369"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Microsoft 365 global prestanda optimering för användare av Kina

>[!IMPORTANT]
>Den här vägledningen är specifik för användnings scenarier där **företags microsoft 365-användare finns i Kina** ansluta till en **Global klient organisation för Microsoft 365**. Denna vägledning gäller **inte** för klient organisationer i Office 365 som drivs av 21Vianet.

För företag med globala Microsoft 365-innehavare och en företags närvaro i Kina kan Microsoft 365-klientens prestanda för Kina-baserade användare vara komplicerade genom faktorer som är unika för Telco Internet Architecture.

Kina har reglerat offshore-anslutningar till det globala offentliga Internet som går genom perimeter-enheter som lätt kan utnyttjas för att överbelasta gränsöverskridande nätverk. Denna överbelastning skapar paket förlust och svars tid för all Internet trafik som kommer in i och ut ur Kina.

![Microsoft 365-trafik – inte optimerad](../media/O365-networking/China-O365-unoptimized.png)

Paket förlust och svars tid är till skada för nätverks tjänster, särskilt tjänster som kräver stora data utbyten (till exempel stora fil överföringar) eller kräver nära real tids prestanda (ljud-och video program).

Målet med detta ämne är att tillhandahålla de bästa metoderna för att minska belastningen på den gränsöverskridande nätverks påverkan i Microsoft 365-tjänster. I det här avsnittet beskrivs inte andra vanliga problem med senaste mil kostnad, till exempel problem med hög paket fördröjning på grund av komplex routning i Kina.

## <a name="corporate-network-best-practices"></a>Metod tips för företags nätverk

Många företag med globala Microsoft 365-innehavare och användare i Kina har implementerat privata nätverk som bär nätverks trafik mellan Kina och platser över hela världen. Dessa företag kan utnyttja den här nätverks infrastrukturen för att undvika överbelastning av överkanten och optimera deras Microsoft 365-tjänstens prestanda i Kina.

>[!IMPORTANT]
>Precis som med alla privata WAN-implementeringar bör du alltid kontrol lera föreskrifter för ditt land och/eller din region för att se till att din nätverks konfiguration efterlevs.

Det första steget är att du följer våra rikt linjer för benchmark-nätverk vid [nätverks planering och prestanda justering för Microsoft 365](https://aka.ms/tune). Det primära målet bör vara att undvika åtkomst till globala Microsoft 365-tjänster från Internet i Kina om det är möjligt.

- Du kan använda ditt befintliga privata nätverk för att hantera Microsoft 365-nätverks trafik mellan de olika platserna för Office på kontoret och offshore-platser som utgångs på Internet utanför Kina. Nästan alla platser utanför Kina ger en klar förstorad fördel. Nätverks administratörer kan optimera ytterligare genom att komma in i områden med sammanlänkad sammanlänkning med [Microsofts globala nätverk](https://docs.microsoft.com/azure/networking/microsoft-global-network). Hongkong, Japan och Sydkorea är exempel.
- Konfigurera användar enheter för att få åtkomst till företags nätverket via en VPN-anslutning så att Microsoft 365-trafik tillåts att överföra företagets nätverks anslutning. Se till att VPN-klienter inte har kon figurer ATS för att använda delade tunnlar eller att användar enheter har kon figurer ATS för att ignorera delad tunnel för Microsoft 365-trafik.
- Konfigurera ditt nätverk för att dirigera all Microsoft 365-trafik via din privata länk från offshore. Om du måste minimera volymen för trafik på din privata länk kan du välja att bara dirigera slut punkter i **optimerings** kategorin och **tillåta att begär Anden och** **standard** slut punkter överförs till Internet. Detta förbättrar prestanda och minimerar bandbredden genom att begränsa optimerad trafik till kritiska tjänster som är mest känslig för hög fördröjning och paket förlust.
- Använd om möjligt UDP i stället för TCP för direkt uppspelning, till exempel för team. UDP erbjuder bättre funktioner för direkt uppspelning av mediet jämfört med TCP.

Information om hur du kan dra Microsoft 365-trafik selektivt finns i [Hantera slut punkter för Office 365](managing-office-365-endpoints.md). En lista över alla URL: er och IP-adresser för Office 365 finns i [URL: er och IP-adressintervall för office 365](urls-and-ip-address-ranges.md).

![Microsoft 365-trafik – optimerad](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Metod tips för användare

Användare i Kina som ansluter till globala Microsoft 365-klient organisationer från fjärrplatser, till exempel hem, caféer, hotell och filial kontor utan anslutning till företags nätverk, kan uppleva dålig nätverks prestanda eftersom trafik mellan deras enheter och Microsoft 365 måste ha transit över gränserna för gränsöverskridande nätverk.

Om det inte finns något alternativ för privata nätverk och/eller VPN-anslutning till företags nätverket kan du fortfarande begränsa varje användares prestanda problem genom att följa de här bästa metoderna.

- Använd många Office-klienter som stöder cachelagring (till exempel Outlook, teams, OneDrive etc.) och Undvik webbaserade klienter. Funktionerna för cachelagring av Office-klient och offline-åtkomst kan minska risken för nätverks belastning och svars tid avsevärt.
- Om din Microsoft 365-klient organisation har kon figurer ATS med funktionen _ljud konferens_ kan team användarna ansluta till möten via det offentliga telefonnätet. Mer information finns i [ljud konferenser i Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).
- Om det uppstår problem med nätverks prestanda bör de rapportera till IT-avdelningen för fel sökning och eskalera till Microsoft support om problem med Microsoft 365-tjänsterna är misstänkta. Det är inte alla problem som orsakas av gränsöverskridande nätverks prestanda.

Microsoft arbetar kontinuerligt med att förbättra Microsoft 365-användar upplevelsen och prestandan hos klienter i det största möjliga intervallet olika nätverks arkitekturer och-egenskaper. Besök [Office 365-Tech-communityn](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) för att starta eller ansluta till en konversation, hitta resurser och skicka in önskemål om funktioner och förslag.

## <a name="related-topics"></a>Relaterade ämnen

[Nätverksplanering och prestandajustering för Microsoft 365](https://aka.ms/tune)

[Microsoft 365 principer för nätverksanslutningar](microsoft-365-network-connectivity-principles.md)

[Hantera Office 365-slutpunkter](managing-office-365-endpoints.md)

[URL-adresser och IP-adressintervall för Office 365](urls-and-ip-address-ranges.md)

[Microsoft globalt nätverk](https://docs.microsoft.com/azure/networking/microsoft-global-network)
