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
ms.openlocfilehash: ec5cfa78852d65db808c4e853f90f5639df25d6f
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300270"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a>Flyttbara enheter i Microsoft Defender för Endpoint Device Control Storage Protection

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Microsoft Defender för Endpoint Device Control flyttbart Storage skydd förhindrar användare eller dator eller båda från att använda obehöriga flyttbara lagringsmedia.

**Microsoft Defender för slutpunktens flyttbara Storage skydd**


|Princip  |Funktion |Beskrivning  |
|---------|---------|---------|
|Enhetsinstallation    |  Förhindra installation med eller utan undantag – Tillåt specifika enheter baserat på olika egenskaper. Mer information finns i avsnittet [Enhetsegenskaper](#device-properties) nedan.        |    Fungerar på datorn: Olika användare som loggar in på samma dator begränsas av samma princip. Mer information finns i Styra [USB-enheter och andra flyttbara media med hjälp av Microsoft Defender för Slutpunkt.](control-usb-devices-using-intune.md)     |
|Åtkomstkontroll för flyttbara lagringsmedia      | (1) Granska läs- eller skriv- eller kör åtkomst till flyttbart lagringsutrymme baserat på olika enhetsegenskaper, med eller utan undantag. Mer information finns i avsnittet [Enhetsegenskaper](#device-properties) nedan. (2) Förhindra läsning eller skrivning eller kör åtkomst med eller utan undantag – Tillåt specifika enheter baserat på olika enhetsegenskaper; Mer information om enhetsegenskaper finns i avsnittet [Enhetsegenskaper](#device-properties) nedan.     |     Fungerar på antingen datorn eller användaren eller både och: Tillåt endast vissa personer som utför läs-/skriv-/kör åtkomst till specifik flyttbar lagring på en viss dator. för funktion i Windows finns i [Åtkomstkontroll för flyttbara lagringsmedia](device-control-removable-storage-access-control.md); för funktion i Mac, se [Enhetskontroll för macOS.](mac-device-control-overview.md)     |
|Slutpunkt DLP, flyttbar lagring      |    Granska eller varna eller förhindra en användare från att kopiera ett objekt eller information till ett flyttbart medium eller en USB-enhet.     |  Mer information finns i [Microsoft Endpoint DLP](/compliance/endpoint-dlp-learn-about.md).       |
|BitLocker    |     Blockera data som ska skrivas till flyttbara enheter som inte är BitLocker skyddade: Blockera åtkomst till flyttbara enheter såvida de inte krypterats på en dator som ägs av din organisation.    |   Mer information finns i BitLocker – [Flyttbar enhet Inställningar](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings#bitlocker---removable-drive-settings.md).      |

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
