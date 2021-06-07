---
title: Contosos COVID-19-svar och stöd för hybridarbete
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå hur Contoso Corporation besvarade COVID-19-installationen ochkompilerade deras programvaruinstallations- och uppdateringsinfrastruktur för hybridarbete.
ms.openlocfilehash: 2d28b0513221f6c14526baba69bf0f5986154805
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788385"
---
# <a name="contosos-covid-19-response-and-support-for-hybrid-work"></a>Contosos COVID-19-svar och stöd för hybridarbete

Contoso hade alltid stöd för fjärranslutna medarbetare som hade åtkomst till lokala resurser via en central VPN-server i huvudkontoret i Paris. Contoso hade utfärdat alla fjärranslutna medarbetare till en hanterad bärbar dator. Lokala medarbetare hade en blandning av stationära och bärbara datorer.

## <a name="contosos-response-to-covid-19"></a>Contosos svar till COVID-19

Med hjälp av COVID-19-personalen var plötsligt alla utom viktiga medarbetare fjärranslutna medarbetare. Contoso har svarat genom att skifta arbetsstyrkan för att arbeta hemifrån och utföra sina primära aktiviteter via fjärråtkomst till lokala resurser och online med hjälp Microsoft 365 molntjänster.

Contoso hade fjärråtkomst till VPN-servrar i Paris huvudkontorskontor för att stödja 25 % av dess redan fjärranslutna arbetsstyrka, men flyttade snabbt för att öka dess fjärranslutna åtkomstkapacitet till 90 % av arbetsstyrkan. Contoso distribuerade VPN-servrar för fjärråtkomst i varje satellitkontor så att fjärranslutna medarbetare skulle använda en regional stängningspunkt för åtkomst till Contoso-intranätet.

Contoso uppdaterade även konfigurationen av VPN-klienter som är installerade på bärbara datorer, surfplattor och smartphones för delade tunnlar så att trafiken för Optimera-uppsättningen av Office 365-slutpunkter kringgår VPN-anslutningen och skickas direkt via Internet. Mer information finns i Optimera [Office 365 anslutningar för fjärranvändare med VPN-delade tunnlar.](../enterprise/microsoft-365-vpn-split-tunnel.md)

Här är den resulterande konfigurationen med VPN-enheter som installeras i paris huvudkontor och var och en av satellitkontoren. 

![Contosos VPN-infrastruktur](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

En fjärransluten anställd med den installerade VPN-klienten använder DNS för att hitta det regionala närmaste kontoret och ansluter till VPN-enheten som är installerad där. Med delade tunnlar skickas trafik till Microsoft 365 och optimerar slutpunkter direkt till den region Microsoft 365 nätverksplatsen. All annan trafik skickas via VPN-anslutningen till VPN-enheten.

## <a name="contosos-support-for-hybrid-work"></a>Contosos stöd för hybridarbete

Efter att de initiala ändringarna gjorts för att stödja fjärranslutna medarbetare under regionala lockdowns gjorde Contoso infrastrukturändringar för att stödja hybridarbete där en anställd kan vara:

- Alltid fjärrstyrd.
- Alltid på plats.
- En kombination av olika platser och fjärranslutna platser.

Microsoft 365 funktioner för identitet, säkerhet och efterlevnad är utformade för Zero Trust och att fungera oavsett var användaren och deras enhet finns. Mer information finns i [Noll förtroende](https://www.microsoft.com/security/business/zero-trust).

Hantering av nya installationer och uppdateringar av programvara beror emellertid på enhetens plats, eftersom programvaran som ska installeras kan komma från en lokal eller en Internetkälla. Contoso IT-arkitekter utformade sin nya installation och uppdaterar infrastruktur baserat på enhetens plats, istället för medarbetaren.

De har angett två typer av enheter: dedikerad lokal roaming och roaming.

### <a name="dedicated-on-premises"></a>Dedikerad lokalt

En dedikerad lokal enhet är en stationär eller serverdator som aldrig lämnar Contoso-intranätet och inte har en VPN-klient installerad. De här lokala enheterna fortsätter att använda Microsoft Endpoint Configuration Manager och dess distributionspunkter för installationer och uppdateringar av Windows 10, Microsoft 365-appar för företag och Edge.

### <a name="roaming"></a>Roaming

En roamingenhet kan lämna Contosos intranät och omfattar bärbara datorer som har utfärdats till många kontorsanställda och alla fjärranslutna medarbetare och andra organisationer ägda enheter, till exempel smartphones och surfplattor med Contoso VPN-klienten installerad. 

Eftersom dessa enheter kan vara anslutna till Internet när som helst använder de Intune eller andra molnbaserade tjänster för installationer och uppdateringar av Windows 10, Microsoft 365-appar för företag och Edge. De använder inte de befintliga distributionspunkterna i Konfigurationshanteraren lokalt.

Det innebär att vissa installationer och uppdateringar för roaming-enheter görs via Internet medan de är lokala och anslutna till intranätet. Men Contoso IT-arkitekter valde att det är viktigare att göra konfigurationen enklare än optimering av bandbredden på internet på intranätet, särskilt när de flesta fjärranslutna medarbetare sällan är anslutna till intranätet.

Här är den resulterande infrastrukturen.

![Infrastruktur för installationer och uppdateringar av Contosos](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

Installations- och uppdateringsbeteendet bestäms genom att datorkonton för enheter blir medlemmar i någon av följande grupper:

- OnPremDevices

  Konfigurationshanterarens klient på enheten använder distributionspunkter för installationer och uppdateringar.

- RoamingDevices

  Intune och andra inställningar på enheten anger hur nätverket Microsoft 365 för installationer och uppdateringar.

## <a name="new-onboarding-process"></a>Ny registreringsprocess

För en ny dedikerad lokal enhet som utfärdats till en ny anställd eller för en ny server i ett datacenter laddar Configuration Manager-klienten, baserat på enhetens medlemskap i gruppen Lokala enheter, ned och installerar de senaste uppdateringarna för Windows 10, Microsoft 365-appar för företag och Edge från lokala konfigurationshanterarens distributionspunkter. När det är klart är den dedikerade lokala enheten klar för användning och använder distributionspunkterna för pågående uppdateringar.

När en anställd loggar in på en ny fjärransluten enhet, baserat på medlemskap i gruppen RoamingDevices, kontaktar du intune-molntjänsten och andra tjänster och laddar ned och installerar de senaste uppdateringarna för Windows 10, Microsoft 365-appar för företag och Edge. När det är klart är fjärrenheten redo att användas och använder den installerade VPN-klienten för åtkomst till lokala resurser och Microsoft 365 för pågående uppdateringar.

## <a name="next-step"></a>Nästa steg

[Konfigurera infrastrukturen för hybridarbete](empower-people-to-work-remotely.md) i organisationen.
