---
title: Contosos COVID – 19 svar och support för fjärrsamtal-och-på-plats-arbete
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå hur Contoso Corporation svarade på COVID-19 Pandemic och har utvecklat sina program varu installationer och uppdatera infrastrukturen för fjärrsamtal.
ms.openlocfilehash: 8e25b399d7acd2cb3486283623d29315eac9491e
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371775"
---
# <a name="contosos-covid-19-response-and-support-for-remote-and-onsite-work"></a>Contosos COVID – 19 svar och support för fjärrsamtal-och-på-plats-arbete

Contoso hade alltid stöd för sina fjärranställda, vilka kom åt lokala resurser via en central VPN-server i Paris huvud gruppen. Contoso hade utfärdat alla fjärranslutna kollegor till en hanterad bärbar dator. Lokala arbetare hade en blandning av Station ära och bärbara datorer.

## <a name="contosos-response-to-covid-19"></a>Contosos svar till COVID-19

Med COVID-19-pandemics fast alla som är avgörande för arbets tagarna. Contoso svarade genom att ändra dess arbets styrka för att arbeta hemifrån och genomföra dess primära aktiviteter via fjärråtkomst till lokala resurser och online med Microsoft 365-molntjänster.

Contoso hade VPN-servrar för fjärråtkomst på Paris huvud kontoret för att stödja 25% av dess redan fjärranställda, men snabbt flyttad för att skala upp den för att kunna hantera 90% av dess arbets styrka. Contoso distribuerade VPN-servrar för fjärråtkomst på varje satellit kontor så att fjärranslutna användare kan använda en regionalt avstängnings punkt för åtkomst till Contosos intranät.

Contoso har också uppdaterat konfigurationen för VPN-klienter som är installerade på bärbara datorer, surfplattor och fasta telefoner för delade tunnlar så att trafik för optimering av Office 365-slutpunkter kringgår VPN-anslutningen och har skickats direkt via Internet. Mer information finns i [optimera Office 365-anslutningar för fjärran vändare via VPN-delning](../enterprise/microsoft-365-vpn-split-tunnel.md).

Här är den resulterande konfigurationen med VPN-enheter som är installerade i Paris huvud gruppen och vart och ett av satellit kontoren. 

![Contosos VPN-infrastruktur](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

En fjärran sluten anställd med den installerade VPN-klienten använder DNS för att hitta det regionala närmaste kontoret och ansluter till den VPN-enhet som är installerad där. Med delade tunnlar kan trafik till Microsoft 365 optimera slut punkter direkt till den regionala närmast Microsoft 365-nätverks platsen. All annan trafik skickas via VPN-anslutningen till VPN-enheten.

## <a name="contosos-support-for-remote-and-onsite-work"></a>Contosos support för fjärrsamtal på kontoret

Efter det att de ursprungliga ändringarna har gjorts till stöd som var och en av de flesta fjärranställdaer under regionala låsningar, har contoso gjorda infrastruktur ändringar som stöd för fjärranslutna och på-på-på-plats

- Alltid fjärr.
- Alltid lokal.
- En kombination av fjär och lokal.

Microsoft 365-funktioner för identitet, säkerhet och efterlevnad är avsedda för noll och fungerar oberoende av användarens och enhetens plats. Mer information finns i avsnittet [noll](https://www.microsoft.com/security/business/zero-trust).

Men hanteringen av nya installationer och uppdateringar av program vara beror på enhetens plats eftersom program varan som installeras kan komma från en lokal eller Internet källa. Contoso IT Architects utformade sina nya installationer och uppdaterar infrastrukturen baserat på enhetens plats i stället för i arbetaren.

De har utsett två typer av enheter: dedikerade lokala och roaming.

### <a name="dedicated-on-premises"></a>Dedikerad lokal

En dedikerad lokal enhet är en stationär eller serverdator som aldrig lämnar Contosos intranät och inte har någon VPN-klient installerad. Dessa lokala enheter fortsätter att använda Microsoft Endpoint Configuration Manager och dess distributions platser för installationer och uppdateringar av Windows 10, Microsoft 365-appar för företag och Edge browser.

### <a name="roaming"></a>Roaming

En central enhet kan lämna Contosos intranät och inkluderar bärbara datorer som utfärdas till många kontors kollegor och alla andra organisations ägda enheter, till exempel telefoner och surfplattor med contoso VPN-klient installerad. 

Eftersom dessa enheter kan anslutas till Internet samtidigt använder de Intune eller andra molnbaserade tjänster för installation och uppdateringar av Windows 10, Microsoft 365-appar för företag och Edge. De använder inte befintliga lokala Configuration Manager-distributionslistor.

Det innebär att vissa installationer och uppdateringar för centrala enheter utförs via Internet medan de är lokala och anslutna till intranätet. Men contoso IT Architects bestämde att det är enkelt att konfigurera, än att kunna optimera bandbredden på intranätet till Internet, särskilt när de flesta fjärranställda inte är anslutna till intranätet.

Här är den resulterande infrastrukturen.

![Organisationens installationer och uppdateringar](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

Installations-och uppdaterings beteende fastställs genom att göra dator konton för enheter till medlemmar i en av dessa grupper:

- OnPremDevices

  Configuration Manager-klienten på enheten använder distributions platser för installationer och uppdateringar.

- RoamingDevices

  Intune och andra inställningar på enheten anger hur Microsoft 365-nätverket används för installationer och uppdateringar.

## <a name="new-onboarding-process"></a>Ny registrerings process

För att en ny dedikerad lokal enhet ska utfärdas till en ny anställd eller för en ny server i ett Data Center, när en användare loggar in, kan Configuration Manager-klienten baserat på enhetens medlemskap i OnPremDevices-gruppen Ladda ned och installera de senaste uppdateringarna för Windows 10, Microsoft 365-appar för företag och Edge från lokala Configuration Manager-distributionslistor. När det är klart är den dedikerade lokala enheten klar för användning och använder dessa distributions platser för pågående uppdateringar.

För en ny fjär renhet som utfärdas till en ny anställd, när en arbets tagare loggar in, beror på dess medlemskap i gruppen RoamingDevices, kontaktar Intune-molnet och andra tjänster och laddar ned och installerar de senaste uppdateringarna för Windows 10, Microsoft 365-appar för företag och Edge. När det är klart är fjär renheten klar för användning och använder den installerade VPN-klienten för åtkomst till lokala resurser och Microsoft 365-nätverket för pågående uppdateringar.

## <a name="next-step"></a>Nästa steg

Ge [fjärranställda](empower-people-to-work-remotely.md) i organisationen.
