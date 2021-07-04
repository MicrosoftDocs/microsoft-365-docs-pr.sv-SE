---
title: Hur innehåll identifieras för rekommendationer om datastyrning
f1.keywords:
- NOCSH
ms.author: brendonb
author: cabailey
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365 Säkerhetscenter och Microsoft 365 Efterlevnadscenter ger rekommendationer för datastyrning baserat på din organisations aktuella konfiguration och låter dig konfigurera med några klick. Vissa av de här rekommendationerna identifierar specifikt innehåll i din organisation och ger sedan rekommenderade steg för att hantera innehållet. En rekommendation kanske, till exempel, identifierar objekt som innehåller verksamhetskritiskt innehåll (t.ex. rätt till förtrolig kommunikation mellan advokat och klient eller information om sekretessavtal) och sedan låter dig automatiskt lägga till en etikett för de objekten för att säkerställa att de klassificeras och behålls efter behov. Det här avsnittet innehåller rekommendationer om datastyrning som du kan se och beskriver vilket innehåll som upptäcks för att utlösa det.
ms.openlocfilehash: 42956e72bf377a02adde3e4253bd9221bb84ff3e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288533"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a>Hur innehåll identifieras för rekommendationer om datastyrning

Microsoft 365 Säkerhetscenter och Microsoft 365 Efterlevnadscenter ger rekommendationer för datastyrning baserat på din organisations aktuella konfiguration och låter dig konfigurera med några klick. Vissa av de här rekommendationerna identifierar specifikt innehåll i din organisation och ger sedan rekommenderade steg för att hantera innehållet. En rekommendation kanske, till exempel, identifierar objekt som innehåller verksamhetskritiskt innehåll (t.ex. rätt till förtrolig kommunikation mellan advokat och klient eller information om sekretessavtal) och sedan låter dig automatiskt lägga till en etikett för de objekten för att säkerställa att de klassificeras och behålls efter behov.

Det här avsnittet innehåller rekommendationer om datastyrning som du kan se och beskriver vilket innehåll som upptäcks för att utlösa det.

## <a name="clean-up-voicemail"></a>Rensa röstmeddelanden

Den här rekommendationen visas när e-postmeddelanden identifieras som meddelandetypen ‘Röstmeddelanden’ upptäcks i användarnas postlådor. Läs mer om [meddelandeegenskaper i Exchange](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators#searchable-properties-in-exchange).

## <a name="label-attorney-client-privilege-content"></a>Etikett för innehåll i förtrolig kommunikation mellan advokat och klient

Den här rekommendationen visas när något av följande kriterier uppfylls.

- Valfri kombination av dessa nyckelord identifieras i brödtexten i ett e-postmeddelande:
  - AKP
  - Rätt till förtrolig kommunikation mellan advokat och klient
  - Rätt till förtrolig kommunikation mellan advokat – klient
  - Advokat klient privilegium

- Alla kombinationer av dessa nyckelord kan identifieras i SharePoint- eller OneDrive-filer:
  - AKP
  - Rätt till förtrolig kommunikation mellan advokat och klient*
  - Advokat klient privilegium

## <a name="retain-audio-files"></a>Behålla ljudfiler

Den här rekommendationen visas när någon av följande filtyper identifieras i SharePoint eller OneDrive.

- .MP3
- .WMA
- .WAV
- .RA
- .RAM
- .RM
- .MID
- .OGG
- .AIFF
- .PCM
- .AAC
- .FLAC
- .ALAC

## <a name="retain-cad-files"></a>Behålla CAD-filer

Den här rekommendationen visas när någon av följande filtyper identifieras i SharePoint eller OneDrive.

- .3DXML
- .ACIS
- .ARC
- .ASM
- .CAT*
- .CGR
- .DW*
- .DX*
- .EDRW
- .IAM
- .IGES
- .IGS
- .IPT
- .JT
- .MF1
- .NEU
- .PAR
- .PKG
- .PRC
- .PRT
- .PSM
- .PWD
- .SLD*
- .STEP
- .STL
- .STP
- .U3D
- .UNV
- .VRML
- .WRL
- .X_*
- .XAS
- .XMT*
- .XPR

## <a name="retain-image-files"></a>Behålla bildfiler

Den här rekommendationen visas när någon av följande filtyper identifieras i SharePoint eller OneDrive.

- .JPEG
- .GIF
- .TIF*
- .BMP
- .PNG
- .RAW
- .PSD
- .PSP
- .JPG
- .EXIF
- .PPM
- .PGM
- .PBM
- .PNM
- .WEBP

## <a name="retain-nda-content"></a>Behålla material med sekretessavtal innehåll

Den här rekommendationen visas när något av följande kriterier uppfylls.

- Valfri kombination av dessa nyckelord identifieras i brödtexten i ett e-postmeddelande:
  - Sekretessavtal
  - "Sekretess-avtal"
  - "Sekretess avtal"

- Alla kombinationer av dessa nyckelord identifieras i .PDF eller .DOC-filer i SharePoint eller OneDrive:
  - Sekretessavtal
  - Sekretess-avtal

## <a name="retain-software-development-files"></a>Behålla programutvecklingsfiler

Den här rekommendationen visas när någon av följande filtyper identifieras i SharePoint eller OneDrive.

- .ASAX
- .ASM
- .ASP*
- .BAT
- .CONFIG
- .CS
- .CSS
- .DISCO
- .HTM*
- .INC
- .JAD
- .JAVA
- .JS*
- .LIB
- .O
- .PHP
- .RC
- .RESX
- .RPT
- .RSS
- .SCPT
- .SRC
- .VB*
- .WSF
- .XCODEPROJ
- .XML
- .XSD
- .XSL*

## <a name="retain-video-files"></a>Behålla videofiler

Den här rekommendationen visas när någon av följande filtyper identifieras i SharePoint eller OneDrive.

- .AVCHD
- .AVI
- .FLV
- .MOV
- .MP2V
- .MP4
- .MP4V
- .MPE
- .MPEG
- .MPEG1
- .MPEG2
- .MPEG4
- .MPG
- .MPG2
- .MPG4
- .WMV
- .XMV
