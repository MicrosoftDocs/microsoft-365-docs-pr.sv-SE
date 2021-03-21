---
title: Prestandaoptimering av globala klientorganisationen för Kina-användare av Microsoft 365
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
search.appverid: MET150
f1.keywords:
- NOCSH
description: Den här artikeln innehåller vägledning för hur du optimerar nätverksprestanda för Kina-användare av globala Microsoft 365-klientorganisationar.
ms.openlocfilehash: 2ba0509425b60aec35d29b23b84e3b6346d2f5cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923200"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Prestandaoptimering av globala klientorganisationen för Kina-användare av Microsoft 365

>[!IMPORTANT]
>Den här vägledningen är specifik för användningsscenarier där **Microsoft 365-företagsanvändare** i Kina ansluter till en **global Microsoft 365-klientorganisation.** Den här **vägledningen gäller** inte för klientorganisationen i Office 365 som drivs av 21Vianet.

För företag med globala Microsoft 365-klientprogram och företagsnärvaro i Kina kan Microsoft 365-klientprestandan för kinabaserade användare vara komplicerad av faktorer som är unika för China Telcos Internetarkitektur.

Kinas internetleverantörer har reglerat anslutningar till det globala offentliga Internet som går genom perimeterenheter som ofta blir överbelastade i olika gränsnätverk. Den här överbelastningen skapar paketförlust och svarstid för all Internettrafik som går till och från Kina.

![Microsoft 365-trafik – inte optimerad](../media/O365-networking/China-O365-unoptimized.png)

Paketförluster och -svarstider innebär skadliga prestanda för nätverkstjänster, särskilt tjänster som kräver stora datautbyten (t.ex. stora filöverföringar) eller kräver nära realtidsprestanda (ljud- och videoprogram).

Syftet med det här avsnittet är att tillhandahålla metodtips för att minska påverkan på korsnätverksstockningar i Kina på Microsoft 365-tjänster. Det här avsnittet tar inte upp andra vanliga prestandaproblem på sista biten, till exempel problem med hög paketfördröjning på grund av komplex routning inom Kina-operatörer.

## <a name="corporate-network-best-practices"></a>Metodtips för företagsnätverk

Många företag med globala Microsoft 365-klientorganisationar och användare i Kina har implementerat privata nätverk som har företagsnätverkstrafik mellan kontor i Kina och kontorsplatser runt om i världen. Dessa företag kan utnyttja den här nätverksinfrastrukturen för att undvika nätverksstockningar över gränserna och optimera Microsoft 365-tjänstprestandan i Kina.

>[!IMPORTANT]
>Som med alla privata WAN-implementeringar bör du alltid följa kraven i lagstiftningen för ditt land och/eller din region för att säkerställa att nätverkskonfigurationen är i regel.

Som ett första steg är det centralt att du följer våra riktvärdesnätverksvägledning i Nätverksplanering och [prestandajustering för Microsoft 365.](./network-planning-and-performance.md) Det primära målet bör vara att undvika att få tillgång till globala Microsoft 365-tjänster från Internet i Kina, om möjligt.

- Använd ditt befintliga privata nätverk för att överföra Microsoft 365-nätverkstrafik mellan Kinas office-nätverk och platser för trådlös anslutning till det offentliga Internet utanför Kina. Nästan alla platser utanför Kina ger en tydlig fördel. Nätverksadministratörer kan optimera ytterligare genom att gå ut i områden med låg fördröjning som är sammankopplade med [Microsofts globala nätverk.](/azure/networking/microsoft-global-network) Hongkong, Japan och Sydkorea är exempel.
- Konfigurera användarenheter för åtkomst till företagsnätverket via en VPN-anslutning så att Microsoft 365-trafik kan ta dig via företagsnätverkets privata länk. Se till att VPN-klienter antingen inte är konfigurerade för delade tunnlar eller att användarenheter är konfigurerade för att ignorera delade tunnlar för Microsoft 365-trafik.
- Konfigurera nätverket för att dirigera all Microsoft 365-trafik via din privata länk. Om du måste minimera mängden trafik via din privata länk kan du välja att endast  dirigera  slutpunkter i kategorin Optimera och tillåta förfrågningar om att tillåta och standardslutpunkter för att skicka internet.  Det förbättrar prestanda och minimerar bandbreddsanvändningen genom att begränsa optimerad trafik till viktiga tjänster som är mest känsliga för hög fördröjning och paketförlust.
- Om möjligt bör du använda UDP i stället för TCP för direktuppspelad mediatrafik, till exempel för Teams. UDP erbjuder bättre prestanda för direktuppspelning av media än TCP.

Mer information om hur du selektivt dirigerar Microsoft 365-trafik finns i [Hantera Office 365-slutpunkter](managing-office-365-endpoints.md). En lista över alla URL:er och IP-adresser för Office 365 finns i URL-adresser och IP-adressintervall för [Office 365.](urls-and-ip-address-ranges.md)

![Microsoft 365-trafik – optimerad](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Metodtips för användare

Användare i Kina som ansluter till globala Microsoft 365-klientorganisationsplatser från fjärranslutna platser som hem, caféer, hotell och filialkontor utan anslutning till företagsnätverk kan uppleva dålig nätverksprestanda eftersom trafiken mellan deras enheter och Microsoft 365 måste ta med Kinas överbelastade korsgränsade nätverkskretsar.

Om det inte går att använda privata nätverk över kantlinjer och/eller VPN-åtkomst till företagsnätverket kan prestandaproblem per användare fortfarande minimeras om dina kinabaserade användare utbildas så att de kan följa de här metodtipsen.

- Använd avancerade Office-klienter som har stöd för cachelagring (t.ex. Outlook, Teams, OneDrive osv.) och undvik webbaserade klienter. Cachelagring av Office-klient och offlineåtkomstfunktioner kan avsevärt minska effekterna av nätverksstockningar och svarstider.
- Om Microsoft 365-klientorganisationen har  konfigurerats med ljudkonferensfunktionen kan Teams-användare ansluta till möten via PSTN (public switched telephone network). Mer information finns i [Ljudkonferens i Office 365.](/microsoftteams/audio-conferencing-in-office-365)
- Om användare har problem med nätverksprestanda bör de rapportera till IT-avdelningen för felsökning och eskalera till Microsoft-support om problem med Microsoft 365-tjänster är misstänkt. Alla problem orsakas inte av nätverksprestanda över kantlinjer.

Microsoft arbetar kontinuerligt med att förbättra användarupplevelsen och prestandan för klienter i hela intervallet av nätverksarkitekturer och egenskaper. Besök [Office 365 Tech Community om](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) du vill starta eller delta i en konversation, hitta resurser och skicka förslag och förfrågningar om funktioner.

## <a name="related-topics"></a>Relaterade ämnen

[Nätverksplanering och prestandajustering för Microsoft 365](./network-planning-and-performance.md)

[Microsoft 365 principer för nätverksanslutningar](microsoft-365-network-connectivity-principles.md)

[Hantera Office 365-slutpunkter](managing-office-365-endpoints.md)

[URL-adresser och IP-adressintervall för Office 365](urls-and-ip-address-ranges.md)

[Microsofts globala nätverk](/azure/networking/microsoft-global-network)