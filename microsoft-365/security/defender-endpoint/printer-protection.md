---
title: Microsoft Defender för Endpoint Device Control Printer Protection
description: Microsoft Defender för Endpoint Device Control Printer Protection blockerar personer från att skriva ut via icke-företagsskrivare eller icke-godkänd USB-skrivare.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: v-lsaldanha
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 0f089efedef1e4fb6b146692da3f1a630f2bacac
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289697"
---
# <a name="device-control-printer-protection"></a>Enhetskontroll för skrivarskydd

Microsoft Defender för Endpoint Device Control Printer Protection blockerar personer från att skriva ut via icke-företagsskrivare eller icke-godkänd USB-skrivare.

## <a name="licensing"></a>Licensiering

Innan du börjar med skrivarskyddet bör du bekräfta din [prenumeration Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1). För att komma åt och använda skrivarskydd måste du ha följande:

- Microsoft 365 E3 för funktionalitet/principdistribution
- Microsoft 365 E5 för rapportering

## <a name="permission"></a>Behörighet

För principdistribution i Intune måste kontot ha behörighet att skapa, redigera, uppdatera eller ta bort enhetskonfigurationsprofiler för att distribuera principen via OMA-URI. Du kan skapa anpassade roller eller använda någon av de inbyggda rollerna med följande behörigheter:

- Rollen Princip och profilhanterare.
- Eller en anpassad roll med behörigheten Skapa/redigera/uppdatera/Läsa/Ta bort/Visa rapporter aktiverad för enhetskonfigurationsprofiler
- Eller global administratör

För att kunna se enhetkonfigurationsrapporter måste kontot ha behörighet att visa rapporter. Du kan skapa anpassade roller eller använda de inbyggda rollerna med följande behörigheter:

- Global säkerhetsadministratör
- Säkerhetsadministratör
- Säkerhetsläsare

## <a name="prepare-your-endpoints"></a>Förbered dina slutpunkter

Kontrollera att de Windows 10 som du planerar att distribuera skrivarskydd för att uppfylla dessa krav.

1. Gå med i Insider Program.

1. Följande Windows-uppdateringar installeras.
    - För Windows 1809: installera Windows [KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)
    - För Windows 1909: installera Windows [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)
    - För Windows 2004 eller senare

1. Om du planerar att distribuera principen via Grupprincip måste enheten vara ansluten till MDATP. Om du planerar att distribuera principen via MEM måste enheten vara intune ansluten.

## <a name="deploy-device-control-printer-protection-policy"></a>Princip för skrivarskydd för enhetskontroll

Du kan distribuera principen via Grupprincip eller Intune.

<br>

****

|Title|Beskrivning|Stöd för CSP | GPO-support | Användarbaserad support | Maskinbaserad support |
|---|---|:---:|:---:|:---:|:---:|
|**Aktivera enhetskontrollens utskriftsbegränsningar**|Blockera personer från att skriva ut via skrivare som inte finns i företaget|Ja|Ja|Ja|Ja|
|**Lista över godkända USB-anslutna utskriftsenheter**\*|Tillåt specifik USB-skrivare|Ja|Ja|Ja|Ja|
|

\*Den här principen måste användas tillsammans med **Aktivera begränsningar för utskriftskontroll på enheten.**

## <a name="deploy-policy-via-intune"></a>Distribuera princip via Intune

För Intune stöder för närvarande Device Control Printer Protection ENDAST OMA-URI.

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-intune"></a>Scenario 1: Blockera personer från att skriva ut via en skrivare som inte är en företagsskrivare med Intune

- Tillämpa principen på datorn:

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl`

- Tillämpa princip över användare:

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser`

CSP-supportsträngen `<enabled/>` med:

:::image type="content" source="../../media/customeditrow.png" alt-text="anpassad redigeringsrad":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-intune"></a>Scenario 2: Tillåta specifika godkända USB-skrivare med Intune

- Tillämpa principen på datorn:

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices`

- Tillämpa princip över användare:

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser`

CSP-supportsträngen med godkända USB-skrivare via egenskapen ApprovedUsbPrintDevices, till `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">` exempel:

:::image type="content" source="../../media/editrow.png" alt-text="redigera rad":::

## <a name="deploy-policy-via-group-policy"></a>Distribuera princip via grupprincip

Om enheten inte är Intune ansluten kan du även distribuera principen via Grupprincip.

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-group-policy"></a>Scenario 1: Blockera personer från att skriva ut via en skrivare som inte finns i företaget med grupprinciper

- Tillämpa principen på datorn:

  Skrivare med \> administrativa mallar för \> datorkonfiguration: Aktivera begränsningar för utskrift i enhetskontrollen

- Tillämpa princip över användare:

  Skrivare på \> Kontrollpanelen för \> användarkonfigurationsmallar: \> Aktivera begränsningar för utskrift i enhetskontroller

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="aktivera begränsningar för utskrift av enheter":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-group-policy"></a>Scenario 2: Tillåta specifika godkända USB-skrivare med grupprincip

- Tillämpa principen på datorn:

  Skrivare för \> administrativa \> datorkonfigurationer: Lista över godkända USB-anslutna utskriftsenheter

- Tillämpa princip över användare:

  Administrativa mallar \> för användarkonfiguration \> – Skrivare \> på Kontrollpanelen: Lista över godkända USB-anslutna utskriftsenheter

:::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="lista över godkända USB-anslutna utskriftsenheter":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a>Visa data om skrivarskydd för enhetskontroll i Microsoft Defender för Endpoint-portalen

På [Microsoft 365 säkerhetscenter visas](https://security.microsoft.com) utskrift som blockerats av principen för skrivarskydd för enhetskontroll ovan.

```sql
DeviceEvents

|where ActionType == 'PrintJobBlocked'

| extend parsed=parse_json(AdditionalFields)

| extend PrintedFile=tostring(parsed.JobOrDocumentName)

| extend PrintPortName=tostring(parsed.PortName)

| extend PrinterName=tostring(parsed.PrinterName)

| extend Policy=tostring(parsed.RestrictionReason) 

| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName,Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields

| order by Timestamp desc
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="avancerad sökning":::
