---
title: Enhetskrav
description: Sammanfattning av de lägsta maskinvaru- och programvarukraven för enheter för Microsoft Managed Desktop
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a6b5cbbcb2f48797130b080d9d1dd1e6427d4fb8
ms.sourcegitcommit: fa5659cb66d84dcfeebc03b47bd9d38017d8934d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110057"
---
# <a name="device-requirements"></a>Enhetskrav

Microsoft Managed Desktop utvärderar regelbundet enhetskrav som ska ingå i tjänsten. I den här artikeln beskrivs de maskin- och programvarukrav en enhet måste uppfylla för att kunna arbeta med Microsoft Managed Desktop. Du kan granska en lista över [specifika enheter som redan är godkända](device-list.md) för användning med tjänsten baserat på dessa krav.

> [!NOTE]
> De här kraven kan ändras när som helst, men vi tillhandahåller 30 dagars förvarning om ändringar av maskinvarukrav. De senast ändrade kraven markeras **\*** med. 

## <a name="check-hardware-requirements"></a>Kontrollera maskinvarukraven

Förutom att granska enhetsspecifikter kan du [](../get-ready/readiness-assessment-downloadable.md) också använda den nedladdningsbara beredskapskontrollen för att verifiera att en viss enhet uppfyller de nödvändiga kraven. Det här verktyget kontrollerar även nätverksinställningar och slutpunkter som också behövs för att tjänsten ska fungera.

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
- Modulen Betrodd plattform 2.0 
- Kan använda virtualiseringsbaserad säkerhet 
- Stöder Hypervisor-skyddad kodintegritet 

Mer information om dessa funktioner och tekniker som är relaterade till dem som används i tjänsten finns i Microsofts teknik [för hanterade skrivbord.](../intro/technologies.md)

> [!NOTE]
> ARM processorer stöds inte.

Enheter bör uppfylla eller överskrida följande gränser för lagring och minne:

- Startenheten måste vara av någon annan typ än en hårddisk. SSD-, NVMe- och eMMC-enheter är till exempel giltiga alternativ.
- Startenheten måste ha en kapacitet på minst 128 GB.

Om enheten gjordes efter den 1 juli 2020 bör den också ha en IR-kamera, fingeravtrycksläsare eller båda för att stödja [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)

## <a name="recommended-requirements"></a>Rekommenderade krav

Även om de inte är absoluta krav får användarna mycket bättre upplevelse om du väljer enheter som har dessa funktioner:

- Antingen en Intel vPro-processor eller en AMD Ryzen Pro-processor
- Startenhet av SSD-typ med en kapacitet på minst 256 GB
- Stöd för modern vänteläge
- Enheten är av säker datortyp
- Stöder Kernel DMA-skydd
