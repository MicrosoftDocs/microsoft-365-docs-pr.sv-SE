---
title: 'Steg 3: undvika nätverkshairpins'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/20/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå och ta bort hairpins för bättre prestanda.
ms.openlocfilehash: 1d5e10bdd8b79f5c7ccd646ac08f83bb2c48b6ee
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583431"
---
# <a name="step-3-avoid-network-hairpins"></a>Steg 3: undvika nätverkshairpins

*Det här steget är obligatoriskt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*

![Fas 1 – nätverk](../media/deploy-foundation-infrastructure/networking_icon-small.png)

En [nätverkshairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) uppstår när trafik som är kopplad till ett mål först dirigeras till en annan mellanliggande plats, t. ex. en lokal säkerhetsstack, molnåtkomstkoordinator eller en molnbaserad webbgateway. Här är ett exempel.

![Exempel på en nätverkshairpin](../media/networking-avoid-network-hairpins/network-hairpin-example.png)

En nätverkshairpin kan också orsakas av dålig routning på Internet på grund av nätverksleverantörer. 

En hairpin lägger till en svarstid och kan eventuellt dirigera om trafik till en geografiskt avlägsen plats.

För att optimera prestanda för trafik till molnbaserade Microsoft 365-tjänster kontrollerar du om Internet-leverantören av den lokala Internet-anslutningen har någon direkt peeringrelation med Microsofts globala nätverk i närheten av platsen. De här anslutningarna har inte hairpins.

Om du använder molnbaserade nätverks- eller säkerhetstjänster för din Microsoft 365-trafik ska du se till att hairpinningeffekten utvärderas och att dess påverkan på prestanda förstås. Undersök följande:

- Antal och platser för dina tjänstleverantörer som trafiken vidarebefordras i i förhållande till dina olika kontor och Microsofts globala nätverkspeeringpunkter 
- Kvaliteten på tjänstleverantörens nätverkspeeringrelation med din Internet-leverantör och Microsoft 
- Prestandaeffekten av backhaul i infrastrukturen för tjänstleverantören

När det är möjligt konfigurerar du dina gränsroutrar så att de skickar betrodd Microsoft 365-trafik direkt, i stället för via proxy eller tunnel via en moln- eller molnbaserad nätverkssäkerhetsleverantör från tredje part som behandlar din Internet-trafik. 

![Exempel på att förbikoppla en nätverkshairpin](../media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

Om du vill testa hur nära du befinner dig i en ingångspunkt för Microsoft globalt nätverk och hur nära din plats som organisationens nätverk ansluter till din Internetleverantör använder du [Office 365 Network Onboarding Tool](https://connectivity.office.com/).

Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](networking-exit-criteria.md#crit-networking-step3) för detta steg.

## <a name="next-step"></a>Nästa steg

|||
|:-------|:-----|
|![Steg 4](../media/stepnumbers/Step4.png)|[Konfigurera förbikoppling av trafik](networking-configure-proxies-firewalls.md)|
