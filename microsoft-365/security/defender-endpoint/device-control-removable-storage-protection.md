---
title: Flyttbara enheter i Microsoft Defender för Endpoint Device Control Storage Protection
description: Förstå "funktioner som förhindrar användare eller dator eller både och från att använda obehöriga flyttbara lagringsmedia
keywords: flyttbart lagringsmedia
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c9b97c2157ba8090628af23b2ab54cf38f04d8c6
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538393"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Flyttbara enheter i Microsoft Defender för Endpoint Device Control Storage Protection

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender för Endpoint Device Control flyttbart Storage skydd förhindrar användare eller dator eller båda från att använda obehöriga flyttbara lagringsmedia.

## <a name="protection-policies"></a>Skyddsprinciper

### <a name="device-installation"></a>Enhetsinstallation

**Funktioner –** Förhindra installation med eller utan undantag baserat på olika enhetsegenskaper.

**Beskrivning**
- Används på maskinnivå: samma princip gäller för alla inloggade användare.
- Stöd för MEM och GPO.
- ' Device[Properties '](#device-properties)as listed.
- Mer information om hur Windows finns i Styra USB-enheter och andra [flyttbara medium med hjälp av Microsoft Defender för slutpunkt.](control-usb-devices-using-intune.md)

**Plattform som stöds** – Windows 10

**Beskrivning**
- Används på maskinnivå: samma princip gäller för alla inloggade användare
- Specifik information för macOS finns i [Enhetskontroll för macOS.](mac-device-control-overview.md)
 
**Plattform som** stöds – macOS Catalina 10.15.4+ (med systemtillägg aktiverade)

### <a name="removable-storage-access-control"></a>Åtkomstkontroll för flyttbara lagringsmedia

**Kapaciteter**
- *Granskning* Läsa eller skriva eller köra åtkomst till flyttbart lagringsutrymme baserat på olika enhetsegenskaper, med eller utan undantag.
- *Förhindra* Läsa eller skriva eller köra åtkomst med eller utan undantag – Tillåt specifik enhet baserat på olika enhetsegenskaper.

**Beskrivning**
- Används på antingen datorn eller användaren eller både och – tillåt endast vissa personer som utför läs-/skriv-/kör åtkomst till specifik flyttbar lagring på en viss dator.
- Stöd för MEM OMA-URI och GPO.
- ' Device[Properties '](#device-properties)as listed.
- Information om funktionen Windows finns i [Ta bort åtkomstkontroll för flyttbara lagringsmedia.](device-control-removable-storage-access-control.md)

**Plattform som stöds** – Windows 10

**Beskrivning**
- Används på maskinnivå: samma princip gäller för alla inloggade användare.
- Specifik information för macOS finns i [Enhetskontroll för macOS.](mac-device-control-overview.md)
 
**Plattform som** stöds – macOS Catalina 10.15.4+ (med systemtillägg aktiverade)

### <a name="windows-portable-device-access-control"></a>Windows Åtkomstkontroll för bärbar enhet

**Funktioner –** Neka läs- eller skrivåtkomst till valfri [bärbar Windows,](/windows-hardware/drivers/portable/)till exempel: surfplatta, iPhone.

**Beskrivning**
- Används på antingen datorn eller användaren eller båda.
- Stöd för MEM OMA-URI och GPO.

**Plattform som stöds** – Windows 10

### <a name="endpoint-dlp-removable-storage"></a>Slutpunkt DLP, flyttbar lagring

**Funktioner –** Granska eller Varna eller Förhindra en användare från att kopiera ett objekt eller information till ett flyttbart medium eller EN USB-enhet.

**Beskrivning** – Mer information om Windows finns i Läs [mer Microsoft 365 skydd mot dataförlust i Slutpunkt](../../compliance/endpoint-dlp-learn-about.md).

**Plattform som stöds** – Windows 10

### <a name="bitlocker"></a>BitLocker 

**Kapaciteter**
- Blockera data som ska skrivas till flyttbara enheter som inte BitLocker skyddade.
- Blockera åtkomst till flyttbara enheter såvida de inte krypterats på en dator som ägs av din organisation
 
**Beskrivning** – Mer information om hur du Windows finns i [BitLocker – Flyttbar enhet Inställningar](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).

**Plattform som stöds** – Windows 10

## <a name="device-properties"></a>Enhetsegenskaper

Med Microsoft Defender för Endpoint Device Control flyttbart Storage Protection kan du begränsa åtkomsten till det flyttbara lagringsutrymmet baserat på de egenskaper som beskrivs i tabellen nedan:


|Egenskapsnamn  |Tillämpliga principer  |Gäller för operativsystem  |Beskrivning  |
|---------|---------|---------|---------|
|Enhetsklass    |     [Styra USB-enheter och andra flyttbara medium med Hjälp av Microsoft Defender för Endpoint](control-usb-devices-using-intune.md)     |   Windows      |  Mer information om enhets-ID-format finns i [enhetskonfigurationsklassen](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors). **Obs!** Enhetsinstallation kan tillämpas på alla enheter, inte bara på flyttbart lagringsutrymme.       |
|Primärt ID   |     Åtkomstkontroll för flyttbara lagringsmedia    |   Windows      |      Det primära ID:t omfattar flyttbart lagringsutrymme och CD/DVD.   |
|Enhets-ID     |  [Styra USB-enheter och andra flyttbara medium med Hjälp av Microsoft Defender för Slutpunkt](control-usb-devices-using-intune.md); Åtkomstkontroll för flyttbara lagringsmedia       |      Windows   |    Mer information om enhets-ID-format finns [i Standard-USB-identifierare,](/windows-hardware/drivers/install/standard-usb-identifiers)till exempel USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07      |
|Maskinvaru-ID     |     [Styra USB-enheter och andra flyttbara medium med Hjälp av Microsoft Defender för Slutpunkt](control-usb-devices-using-intune.md); Åtkomstkontroll för flyttbara lagringsmedia    |     Windows    |    En sträng som identifieras av enheten i systemet, till exempel USBSTOR\DiskGeneric_Flash_Disk______8.07; **Obs!** Maskinvaru-ID är inte unikt. olika enheter kan ha samma värde.|
|Instans-ID    | Enhetsinstallation; Åtkomstkontroll för flyttbara lagringsmedia     |     Windows    |   En sträng identifierar unikt enheten i systemet, till exempel USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0      |
|Eget namn     |     Åtkomstkontroll för flyttbara lagringsmedia    |   Windows      |    En sträng ansluten till enheten, till exempel allmän FLASH USB-enhet     |
|Leverantörs-ID/produkt-ID     |  Åtkomstkontroll för flyttbara lagringsmedia       |   Windows Mac      |     Leverantörs-ID är den fyrsiffriga leverantörskod som USB-kommittéen tilldelar leverantören. Produkt-ID är den fyrsiffriga produktkod som leverantören tilldelar till enheten. Stöd för jokertecken.    |
|Serienummer     |     Åtkomstkontroll för flyttbara lagringsmedia    |      Windows Mac   |     Exempel: <SerialNumberId>002324B534BCB431B000058A</SerialNumberId>    |

## <a name="related-topic"></a>Relaterat ämne

- [Microsoft Defender för endpoint-enhetskontroll, flyttbar Storage access-kontroll](device-control-removable-storage-access-control.md)

