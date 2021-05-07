---
title: Filtyper som stöds i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: En lista över filtyper som stöds i Microsoft 365 Advanced eDiscovery, inklusive filtyper som stöds av OCR-funktionen i Advanced eDiscovery.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 719a0474d45825114cf4ea3fbd19082bb8df7622
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2021
ms.locfileid: "52162644"
---
# <a name="supported-file-types-in-advanced-ediscovery"></a>Filtyper som stöds i Advanced eDiscovery

Advanced eDiscovery har stöd för många filtyper på många olika nivåer. Supportfiltyperna beskrivs i följande tabeller i den här artikeln. Den här listan är inte färdig och vi kommer att lägga till nya filtyper när vi fortsätter med verifieringstestningen. Dessa tabeller anger om en filtyp stöds för text extrahering (och optisk teckenläsning eller OCR-texttextrahering för bildfiler), som kan visas i det ursprungliga visningsprogrammet och även i visningsprogrammet anteckningar i Advanced eDiscovery.

## <a name="archive--container"></a>Arkivera/behållare

| Mime-typ | Filidentifiering | Metadata-extrahering | Behållare för extrahering | Möjliga tillägg |
|:---- |:---- |:---- |:---- |:---- |
|application/x-7z-compressed | Ja | Ja | Ja | .7z |
|application/x-rar-compressed | Ja | Ja | Ja | .rar |
|application/x-tar | Ja | Ja | Ja | .tar |
|application/zip | Ja | Ja | Ja | .zip |
||||||||

## <a name="audio--video"></a>Ljud/video

| Mime-typ | Filidentifiering | Metadata-extrahering | Texttextrahering | Inbyggt visningsprogram | Kommentera visningsprogram | Möjliga tillägg |
|:------| :------| :------| :------| :------| :------| :------|
| application/mp4 | Ja | Ja | Nej | Ja | Nej | .f4v; .m4a; .m4v; .mp4; .mp4v; .mpeg; .mpeg4 |
|audio/mpeg | Ja | Ja | Nej | Ja | Nej | .mpeg |
|video/3gpp | Ja | Ja | Nej | Ja | Nej | .3gp |
|video/3gpp2 | Ja | Ja | Nej | Ja | Nej | .3g2; .3gp2 |
|video/quicktime | Ja | Ja | Nej | Ja | Nej | .moov; .mov; .qt |
|video/x-m4v | Ja | Ja | Nej | Ja | Nej | .m4v |
||||||||

## <a name="database"></a>Databas

| Mime-typ | Filidentifiering | Metadata-extrahering | Texttextrahering | Inbyggt visningsprogram | Kommentera visningsprogram | Möjliga tillägg |
|:------| :------| :------| :------| :------| :------| :------|
|application/x-msaccess | Ja | Ja | Ja | Nej | Nej | MDB |
||||||||

## <a name="email"></a>E-post

|Mime-typ |Filidentifiering |Metadata-extrahering |Texttextrahering |Inbyggt visningsprogram |Kommentera visningsprogram | Möjliga tillägg |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-outlook | Ja | Ja | Ja | Ja | Ja | MSG |
|meddelande/rfc822 | Ja | Ja | Ja | Ja | Ja | EML |
|text/visitkort-kontakt | Ja | Ja | Ja | Ja | Ja | VCF |
||||||||

## <a name="email-container"></a>E-postbehållare

| Mime-typ | Filidentifiering | Metadata-extrahering | Behållare för extrahering | Möjliga tillägg |
|:------| :------| :------| :------| :------|
|application/mbox | Ja | Ja | Ja | MBOX |
|application/vnd.ms-outlook-pst | Ja | Ja | Ja | PST |
||||||||

## <a name="html"></a>HTML

| Mime-typ | Filidentifiering | Metadata-extrahering | Texttextrahering | Inbyggt visningsprogram | Kommentera visningsprogram | Möjliga tillägg |
|:------| :------| :------| :------| :------| :------| :------|
|program/xhtml+xml | Ja | Ja | Ja | Ja | Ja | .xhtml |
|program/xml | Ja | Ja | Ja | Ja | Ja | .xml |
|text/html | Ja | Ja | Ja | Ja | Ja | .htm; .html; .shtml |
||||||||

## <a name="image"></a>Bild

|Mime-typ |Filidentifiering |Metadata-extrahering |OCR-text-extrahering |Inbyggt visningsprogram |Kommentera visningsprogram |Möjliga tillägg |
|:------| :------| :------| :------| :------| :------| :------|
|bild/bmp | Ja | Ja | Ja | Ja | Ja | .bmp |
|bild/emf | Ja | Ja | Ja | Ja | Ja | EMF |
|bild/gif | Ja | Ja | Ja | Ja | Ja | .gif |
|bild/jpeg | Ja | Ja | Ja | Ja | Ja | JPEG; .jpg |
|bild/png | Ja | Ja | Ja | Ja | Ja | .png |
|image/svg+xml | Ja | Ja | Ja | Ja | Nej | SVG |
|bild/tiff | Ja | Ja | Ja | Ja | Ja | .tif |
|image/vnd.dwg | Ja | Ja | Ja | Ja | Ja | DWG; DXF |
|image/wmf | Ja | Ja | Ja | Ja | Ja | .wmf |
||||||||

## <a name="microsoft-excel"></a>Microsoft Excel

| Mime-typ | Filidentifiering | Metadata-extrahering | Texttextrahering | Inbyggt visningsprogram | Kommentera visningsprogram | Möjliga tillägg |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-excel | Ja | Ja | Ja | Ja | Ja | .dat; .xls |
|application/vnd.ms-excel.sheet.binary.macroenabled.12 | Ja | Ja | Ja | Ja | Nej | XLSB |
|application/vnd.ms-excel.sheet.macroenabled.12 | Ja | Ja | Ja | Ja | Ja | XLSM |
|application/vnd.ms-excel.template.macroenabled.12 | Ja | Ja | Ja | Nej | Nej | XLTM |
|application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | Ja | Ja | Ja | Ja | Ja | .xlsx |
|application/vnd.openxmlformats-officedocument.spreadsheetml.template | Ja | Ja | Ja | Ja | Ja | XLTX |
||||||||

## <a name="microsoft-onenote"></a>Microsoft OneNote

| Mime-typ | Filidentifiering | Metadata-extrahering | Texttextrahering | Inbyggt visningsprogram | Kommentera visningsprogram | Möjliga tillägg |
|:------| :------| :------| :------| :------| :------| :------|
|program/onenote | Ja | Ja | Ja | Nej | Nej | .one |
||||||||

## <a name="microsoft-powerpoint"></a>Microsoft PowerPoint

| Mime-typ | Filidentifiering | Metadata-extrahering | Texttextrahering | Inbyggt visningsprogram | Kommentera visningsprogram | Möjliga tillägg |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-powerpoint | Ja | Ja | Ja | Ja | Ja | .pot; .pps; .ppt |
|application/vnd.openxmlformats-officedocument.presentationml.presentation | Ja | Ja | Ja | Ja | Ja | .pptx |
|application/vnd.openxmlformats-officedocument.presentationml.slideshow | Ja | Ja | Ja | Ja | Ja | PPSX |
|application/vnd.openxmlformats-officedocument.presentationml.template | Ja | Ja | Ja | Ja | Ja | POTX |
||||||||

## <a name="microsoft-project"></a>Microsoft Project

| Mime-typ | Filidentifiering | Metadata-extrahering | Texttextrahering | Inbyggt visningsprogram | Kommentera visningsprogram | Möjliga tillägg |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-project | Ja | Ja | Ja | Nej | Ja | .mpp |
||||||||

## <a name="microsoft-publisher"></a>Microsoft Publisher

|Mime-typ | Filidentifiering | Metadata-extrahering | Texttextrahering | Inbyggt visningsprogram | Kommentera visningsprogram | Möjliga tillägg |
|:------| :------| :------| :------| :------| :------| :------|
|application/x-mspublisher | Ja | Ja | Ja | Ja | Ja | .pub |
||||||||

## <a name="microsoft-visio"></a>Microsoft Visio

| Mime-typ | Filidentifiering | Metadata-extrahering | Texttextrahering | Inbyggt visningsprogram | Kommentera visningsprogram | Möjliga tillägg |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-visio.drawing | Ja | Ja | Ja | Ja | Nej |  |
|application/vnd.visio | Ja | Ja | Ja | Ja | Ja | .vsd |
||||||||

## <a name="microsoft-word"></a>Microsoft Word

| Mime-typ | Filidentifiering | Metadata-extrahering | Texttextrahering | Inbyggt visningsprogram | Kommentera visningsprogram | Möjliga tillägg |
|:------| :------| :------| :------| :------| :------| :------|
|program/msword | Ja | Ja | Ja | Ja | Ja | .dat; .doc |
| application/rtf | Ja | Ja | Ja | Ja | Ja | .doc; .rtf |
|program/vnd.ms-word.document.macroenabled.12 | Ja | Ja | Ja | Ja | Ja | DOCM |
|application/vnd.ms-word.template.macroenabled.12 | Ja | Ja | Ja | Ja | Ja | DOTM |
|program/vnd.openxmlformats-officedocument.wordprocessingml.document | Ja | Ja | Ja | Ja | Ja | .docx |
|application/vnd.openxmlformats-officedocument.wordprocessingml.template | Ja | Ja | Ja | Ja | Ja | DOTX |
||||||||

## <a name="microsoft-works"></a>Microsoft Works

| Mime-typ | Filidentifiering | Metadata-extrahering | Texttextrahering | Inbyggt visningsprogram | Kommentera visningsprogram | Möjliga tillägg |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-works-ss | Ja | Ja | Nej | Nej | Nej | .wps |
|application/vnd.ms-works-wp | Ja | Ja | Nej | Nej | Nej | .wps |
||||||||

## <a name="open-document-format"></a>Öppna dokumentformat

| Mime-typ | Filidentifiering | Metadata-extrahering | Texttextrahering | Inbyggt visningsprogram | Kommentera visningsprogram | Möjliga tillägg |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.oas.opendocument.text | Ja | Ja | Ja | Ja | Ja | ODT |
||||||||

## <a name="other"></a>Annat

| Mime-typ | Filidentifiering | Metadata-extrahering | Texttextrahering | Inbyggt visningsprogram | Kommentera visningsprogram | Möjliga tillägg |
|:------| :------| :------| :------| :------| :------| :------|
|application/json | Ja | Ja | Ja | Ja | Ja | Ej a |
|application/vnd.ms-graph | Ja | Ja | Nej | Nej | Nej |  |
|application/winhlp | Ja | Ja | Nej | Nej | Nej | HLP |
|application/x-tnef | Ja | Ja | Nej | Nej | Nej |  |
||||||||

## <a name="plain-text"></a>Oformaterad text

| Mime-typ | Filidentifiering | Metadata-extrahering | Texttextrahering | Inbyggt visningsprogram | Kommentera visningsprogram | Möjliga tillägg |
|:------| :------| :------| :------| :------| :------| :------|
|text/csv | Ja | Ja | Ja | Ja | Ja | .csv |
|text/oformaterad | Ja | Ja | Ja | Ja | Ja | .con; .css; .csv; .dat; .pl; .txt |
||||||||

## <a name="portable-document-format"></a>Portable Document Format

| Mime-typ | Filidentifiering | Metadata-extrahering | Texttextrahering | Inbyggt visningsprogram | Kommentera visningsprogram | Möjliga tillägg |
|:------| :------| :------| :------| :------| :------| :------|
|program/pdf | Ja | Ja | Ja | Ja | Ja | .pdf |
||||||||

## <a name="word-perfect"></a>Perfekt Word

| Mime-typ | Filidentifiering | Metadata-extrahering | Texttextrahering | Inbyggt visningsprogram | Kommentera visningsprogram | Möjliga tillägg |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.wordperfect; version=5.0 | Ja | Ja | Ja | Nej | Nej | .wpd |
|application/vnd.wordperfect; version=5.1 | Ja | Ja | Ja | Nej | Nej | .wpd |
|application/vnd.wordperfect; version=6.x | Ja | Ja | Ja | Nej | Nej | .wpd |
||||||||

## <a name="word-pro"></a>Word-Pro

| Mime-typ | Filidentifiering | Metadata-extrahering | Texttextrahering | Inbyggt visningsprogram | Kommentera visningsprogram | Möjliga tillägg |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.lotus-wordpro | Ja | Ja | Nej | Nej | Nej | LWP |
||||||||
