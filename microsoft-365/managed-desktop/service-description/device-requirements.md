---
title: Enhetskrav
description: Översikt över minimi kraven för maskin vara och program vara för enheter för att fungera med Microsoft Managed Desktop
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 88b1ba657b4823d90a41b28b01362760676410ba
ms.sourcegitcommit: b3bb5bf5efa197ef8b16a33401b0b4f5663d3aa0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/28/2021
ms.locfileid: "50032709"
---
# <a name="device-requirements"></a>Enhetskrav

Microsoft Managed Desktop bedömer regelbundet vilka enheter som ska ingå i tjänsten. I den här artikeln beskrivs maskinvaru-och program varu kraven som en enhet måste uppfylla för att fungera med Microsoft Managed Desktop. Du kan granska en lista med [enheter som redan godkänts](device-list.md) för användning med tjänsten baserat på dessa krav.

> [!NOTE]
> Dessa krav kan ändras när som helst, men vi kommer att erbjuda 90 dagars meddelande om sådana ändringar. De senaste kraven är markerade med **\*** . 

## <a name="check-hardware-requirements"></a>Kontrol lera maskin varu kraven

Förutom att läsa enhets specifikationer kan du även använda nedladdnings [kontrollen](../get-ready/readiness-assessment-downloadable.md) för att kontrol lera att en given enhet uppfyller de nödvändiga kraven. Det här verktyget kontrollerar också nätverks inställningar och slut punkter som också behövs för att tjänsten ska fungera.

## <a name="minimum-requirements"></a>Minimi krav

För att vara registrerade på Microsoft Managed Desktop måste en enhet uppfylla eller överträffa alla dessa krav.

### <a name="manufacturer"></a>Tillverkarnamn

Enheten måste ha gjorts av någon av dessa tillverkare:

- Dell
- KLIENTANSLUTNINGAR
- Lenovos
- Microsoft


### <a name="installed-software"></a>Installerad program vara

Enheten måste ha följande program vara förinstallerat:

- Windows 10 Enterprise, Pro eller Pro Workstation Edition
- {64-bitars versionen av Office Klicka-och-kör {jag kontrollerar namn med Office-arbetskollegor]}
- Alla tillämpliga driv rutiner


### <a name="physical-features"></a>Fysiska funktioner

Enheter måste ha följande funktioner:

- Aktiverat för säker start med UEFI 
- Trusted Platform Module 2,0 
- Möjlighet till virtualiseringsbaserad säkerhet 
- Stöder hypervisor-skyddad kod integritet 

Mer information om de här funktionerna och de tekniker som tjänsten använder finns i [Microsoft Managed Desktop Technologies](../intro/technologies.md).

> [!NOTE]
> ARM-processorer stöds inte.

Enheter bör uppfylla eller överträffa följande begränsningar för lagring och minne:

- Startenheten måste vara annan än hård disk. Till exempel SSD-, NVMe-och eMMC-enheter är giltiga val.
- Startenheten måste ha en kapacitet på minst 128 GB.

Om enheten har gjorts efter den 1 juli 2020 bör den också ha en IR-kamera, finger avtrycks läsare eller både och för att kunna använda [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security).

## <a name="recommended-requirements"></a>Rekommenderade krav

Även om de inte är absoluta krav får användarna en mycket bättre upplevelse om du väljer enheter som har följande funktioner:

- Antingen en Intel vPro-plattforms processor eller en AMD Ryzen Pro-processor
- Startenhet för typen SSD med en kapacitet på minst 256 GB
- Stöd för moderna vänte läge
- Enheten är av typen säker-core-dator
- Stöd för kernel DMA-skydd