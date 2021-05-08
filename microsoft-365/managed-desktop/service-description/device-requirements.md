---
title: Enhetskrav
description: Sammanfattning av minimikraven för maskinvara och programvara för enheter som ska fungera Microsoft Hanterat skrivbord
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: fcd7f192ba0846e3bf3051cde927095088f32d26
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245798"
---
# <a name="device-requirements"></a>Enhetskrav

Microsoft Hanterat skrivbord regelbundet utvärderas enhetskrav som ska ingå i tjänsten. I den här artikeln beskrivs de maskin- och programvarukrav en enhet måste uppfylla för att kunna arbeta med Microsoft Hanterat skrivbord. Du kan granska en lista över specifika enheter som redan är godkända för användning med tjänsten baserat på dessa krav. Filter för Microsoft Hanterat skrivbord på webbplatsen [handla Windows 10 Pro företagsenheter](https://www.microsoft.com/windowsforbusiness/view-all-devices)

> [!NOTE]
> Dessa krav kan ändras när som helst, men vi kommer att tillhandahålla 30 dagars förvarning om alla maskinvarukrav ändras. De senast ändrade kraven markeras med **\*** . 

## <a name="check-hardware-requirements"></a>Kontrollera maskinvarukraven

Förutom att granska enhetsspecifikter kan du också använda den nedladdningsbara beredskapskontrollen [för](../get-ready/readiness-assessment-downloadable.md) att verifiera att en viss enhet uppfyller de nödvändiga kraven. Det här verktyget kontrollerar även nätverksinställningar och slutpunkter som även krävs för att tjänsten ska fungera.

## <a name="minimum-requirements"></a>Minimikrav

För att registreras i Microsoft Hanterat skrivbord måste en enhet uppfylla eller överskrida alla dessa krav.

### <a name="manufacturer"></a>Tillverkare

Enheten måste ha gjorts av någon av dessa tillverkare:

- Dell
- HP
- Lenovo
- Microsoft


### <a name="installed-software"></a>Installerad programvara

Enheten måste ha den här programvaran förinstallerad:

- Windows 10 Enterprise, Pro eller Pro Arbetsstation
- 64-bitarsversionen av Microsoft 365-appar för företag 
- Alla tillämpliga drivrutiner


### <a name="physical-features"></a>Fysiska funktioner

Enheter måste ha följande funktioner:

- Aktiverad för säker UEFI-uppstart 
- Trusted Platform Module 2.0 
- Klarar virtualiseringsbaserad säkerhet 
- [Hypervisorskyddad kodintegritet](/windows-hardware/drivers/bringup/device-guard-and-credential-guard) som stöds av TIDE

Mer information om dessa funktioner och de tekniker som är relaterade till dem som tjänsten använder finns [i Microsoft Hanterat skrivbord teknik.](../intro/technologies.md)

> [!NOTE]
> ARM-processorer stöds inte.

Enheter bör uppfylla eller överskrida följande begränsningar för lagring och minne:

- Startenheten måste vara av någon annan typ än en hårddisk. SSD-, NVMe- och eMMC-enheter är till exempel alla giltiga alternativ.
- Startenheten måste ha en kapacitet på minst 128 GB.
- Internt enhetsminne (RAM) måste vara lika med eller överstiger 8 GB.

Om enheten gjordes efter den 1 juli 2020 bör den också ha en IR-kamera, fingeravtrycksläsare eller båda, för att stödja [Windows Hello.](/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)

## <a name="recommended-features"></a>Rekommenderade funktioner

Användarna får en mycket bättre upplevelse om du väljer enheter som har följande funktioner:

- En Intel vPro-processor eller en AMD Ryzen-processor Pro Intel
- Startenhet av SSD-typ med en kapacitet på minst 256 GB
- Internt enhetsminne (RAM) på minst 16 GB
- Stöd för modern vänteläge
- Enheten är av skyddad datortyp
- Stöder Kernel DMA Protection
