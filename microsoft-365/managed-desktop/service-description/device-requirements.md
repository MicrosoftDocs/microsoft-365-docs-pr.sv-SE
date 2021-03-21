---
title: Enhetskrav
description: Sammanfattning av de lägsta maskin- och programvarukraven för att enheter ska fungera med Microsoft Managed Desktop
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 18422f74d87bbadf014de24849235ce5c25bd614
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920474"
---
# <a name="device-requirements"></a>Enhetskrav

Microsoft Managed Desktop utvärderar regelbundet enhetskrav för att ingå i tjänsten. I den här artikeln beskrivs de maskin- och programvarukrav en enhet måste uppfylla för att kunna arbeta med Microsoft Managed Desktop. Du kan granska en lista över specifika [enheter som redan är godkända](device-list.md) för användning med tjänsten baserat på dessa krav.

> [!NOTE]
> Dessa krav kan ändras när som helst, men vi kommer att tillhandahålla 30 dagars förvarning om alla maskinvarukrav ändras. De senast ändrade kraven markeras med **\*** . 

## <a name="check-hardware-requirements"></a>Kontrollera maskinvarukraven

Förutom att granska enhetsspecifikter kan du också använda den nedladdningsbara beredskapskontrollen [för](../get-ready/readiness-assessment-downloadable.md) att verifiera att en viss enhet uppfyller de nödvändiga kraven. Det här verktyget kontrollerar även nätverksinställningar och slutpunkter som även krävs för att tjänsten ska fungera.

## <a name="minimum-requirements"></a>Minimikrav

För att registreras i Microsoft Managed Desktop måste en enhet uppfylla eller överskrida alla dessa krav.

### <a name="manufacturer"></a>Tillverkare

Enheten måste ha gjorts av någon av dessa tillverkare:

- Dell
- HP
- Lenovo
- Microsoft


### <a name="installed-software"></a>Installerad programvara

Enheten måste ha den här programvaran förinstallerad:

- Windows 10 Enterprise, Pro eller Pro Arbetsstation
- 64-bitarsversionen av Microsoft Office Klicka-och-kör 
- Alla tillämpliga drivrutiner


### <a name="physical-features"></a>Fysiska funktioner

Enheter måste ha följande funktioner:

- Aktiverad för säker UEFI-uppstart 
- Trusted Platform Module 2.0 
- Klarar virtualiseringsbaserad säkerhet 
- Stöder Hypervisor-skyddad kodintegritet 

Mer information om dessa funktioner och tekniker som är relaterade till dem som används i tjänsten finns i [Microsoft Managed Desktop-tekniker.](../intro/technologies.md)

> [!NOTE]
> ARM-processorer stöds inte.

Enheter bör uppfylla eller överskrida följande begränsningar för lagring och minne:

- Startenheten måste vara av någon annan typ än en hårddisk. SSD-, NVMe- och eMMC-enheter är till exempel alla giltiga alternativ.
- Startenheten måste ha en kapacitet på minst 128 GB.
- Internt enhetsminne (RAM) måste vara lika med eller överstiger 8 GB.

Om enheten gjordes efter 1 juli 2020 bör den också ha en IR-kamera, fingeravtrycksläsare eller båda, för att stödja [Windows Hello.](/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)

## <a name="recommended-requirements"></a>Rekommenderade krav

Även om de inte är absolut krav, kommer dina användare att ha en mycket bättre upplevelse om du väljer enheter som har dessa funktioner:

- Antingen en Intel vPro-processor eller en AMD Ryzen Pro-processor
- Startenhet av SSD-typ med en kapacitet på minst 256 GB
- Stöd för modern vänteläge
- Enheten är av skyddad datortyp
- Stöder Kernel DMA Protection