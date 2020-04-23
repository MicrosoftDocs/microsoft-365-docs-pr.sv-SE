---
title: 'Fas 1: nätverksinfrastruktur för Microsoft 365 Enterprise'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Steg för att distribuera nätverksinfrastrukturen för Microsoft 365 Enterprise.
ms.openlocfilehash: 341e5530b159d4ba78b94001d92427e36224ab04
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631483"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a>Fas 1: nätverksinfrastruktur för Microsoft 365 Enterprise

![Fas 1: Nätverk](../media/deploy-foundation-infrastructure/networking_icon.png)

Microsoft 365 Enterprise innehåller Office 365, Microsoft Intune och många identitets- och säkerhetstjänster i Microsoft Azure. Alla dessa molnbaserade tjänster kräver säkerhet, prestanda och tillförlitlighet för anslutningar från klientenheter via Internet eller dedikerade kretsar. Om du vill ha de här tjänsterna och göra dem tillgängliga för kunder över hela världen har Microsoft utformat en nätverksinfrastruktur som betonar prestanda och integrering. 

I det här steget ska du gå igenom de viktigaste aspekterna när du skapar en omfattande anslutning till molntjänsterna för Microsoft 365 Enterprise. En översikt finns i [Nätverksprinciper för Microsoft 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

>[!Note]
>Om du redan har distribuerat en nätverksinfrastruktur går du till [avslutsvillkoren](networking-exit-criteria.md) i den här fasen för att kontrollera att det uppfyller kraven och valfria villkor för Microsoft 365 Enterprise.

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a>Planera och distribuera din nätverksinfrastruktur för Microsoft 365 Enterprise 

Använd följande steg för att bygga ut nätverksinfrastrukturen för krav och funktioner i Microsoft 365 Enterprise.

|||
|:-------|:-----|
|![Steg 1](../media/stepnumbers/Step1.png)|[Förbereda nätverket för Microsoft 365](networking-provide-bandwidth-cloud-services.md)|
|![Steg 2](../media/stepnumbers/Step2.png)|[Konfigurera lokala internetanslutningar för Office](networking-dns-resolution-same-location.md)|
|![Steg 3](../media/stepnumbers/Step3.png)|[Undvika nätverkshairpins](networking-avoid-network-hairpins.md)|
|![Steg 4](../media/stepnumbers/Step4.png)|[Konfigurera förbikoppling av trafik](networking-configure-proxies-firewalls.md)|
|![Steg 5](../media/stepnumbers/Step5.png)|[Optimera prestanda för klienten och tjänsten](networking-optimize-tcp-performance.md)|


När du har utfört de här stegen går du till [avslutsvillkoret](networking-exit-criteria.md) i den här fasen för att säkerställa att du uppfyller kraven och valfria villkor för Microsoft 365 Enterprise.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Hur Microsoft gör Microsoft 365 Enterprise

Granska Microsoft och lär dig hur företaget [optimerade Microsoft-nätverket för molntjänster](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR4).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Hur Contoso skapade Microsoft 365 Enterprise

Se hur Contoso Corporation, ett fiktivt men representativt multinationellt företag, [optimerade sina nätverksenheter och Internet-anslutningar](contoso-networking.md) för Microsoft 365-molntjänster.

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Nästa steg

|||
|:-------|:-----|
|![Steg 1](../media/stepnumbers/Step1.png)|[Förbereda nätverket för Microsoft 365](networking-provide-bandwidth-cloud-services.md)|

