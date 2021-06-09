---
title: Microsoft Defender för endpoint-enhetskontroll, flyttbar Storage access-kontroll
description: En genomgång om Microsoft Defender för Endpoint
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
ms.openlocfilehash: fba74990d8e4465f957acda83e66e1dc43a317e8
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841192"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Microsoft Defender för endpoint-enhetskontroll, flyttbar Storage access-kontroll

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Med Microsoft Defender för Endpoint Device Control Storage och Access Control kan du göra följande:
- granska, tillåta eller förhindra läsning, skriva eller köra åtkomst till flyttbara lagringsmedia med eller utan undantag

|Behörighet |Behörighet  |
|---------|---------|
|Åtkomst    |  Läsa, skriva, köra       |
|Åtgärdsläge    |    Granska, tillåt, förhindra     |
|Stöd för CSP   |   Ja      |
|GPO-support    |   Ja      |
|Användarbaserad support     |   Ja      |
|Maskinbaserad support    |    Ja     |

## <a name="prepare-your-endpoints"></a>Förbered dina slutpunkter

Distribuera Flyttbart Storage Access Control på Windows 10-enheter med klientversionen mot skadlig programvara **version 4.18.2103.3 eller senare.**
1. **4.18.2104** eller senare: Add SerialNumberId, VID_PID, filepath-baserat GPO-stöd

2. **4.18.2105** eller senare: Lägg till stöd för jokertecken för HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, kombinationen av en specifik användare på en specifik dator, removeable SSD (en SanDisk Extreme SSD)/USB Attached MORD (UAS) stöd

:::image type="content" source="images/powershell.png" alt-text="PowerShell-gränssnittet":::

## <a name="policy-properties"></a>Principegenskaper

Du kan använda följande egenskaper till att skapa en flyttbar lagringsgrupp:

**Egenskapsnamn: Grupp-ID**

1. Beskrivning: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), ett unikt ID, representerar gruppen och kommer att användas i principen.

**Egenskapsnamn: DescriptorIdList**

1. Beskrivning: Lista över de enhetsegenskaper du vill använda för gruppen.
Ange de enhetsegenskaper du vill använda i gruppen.
Mer information om varje **enhetsegenskap finns** i avsnittet Enhetsegenskaper ovan.

1. Alternativ:
    - Primärt ID
        - FlyttbaraMediaDevices
        - CdRomDevices
    - DeviceId
    - HardwareId
    - InstancePathId: InstancePathId är en sträng som unikt identifierar enheten i systemet, till exempel USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0. Numret på slutet (till exempel&**0**) representerar den tillgängliga platsen och kan ändras från enhet till enhet. För bästa resultat bör du använda ett jokertecken i slutet. Exempel: USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611*
    - FriendlyNameId
    - SerialNumberId
    - VID
    - PID
    - VID_PID
        - 0751_55E0: matcha exakt detta VID/PID-par
        - _55E0: matcha media med PID=55E0
        - 0751_: matcha media med VID=0751
        
**Egenskapsnamn: MatchType** 

1. Beskrivning: När det finns flera enhetsegenskaper som används i DescriptorIDList definierar MatchType relationen.

1. Alternativ:
    - MatchAll: Attributen under DescriptorIdList blir **och relationen;** Om administratören till exempel placerar DeviceID och InstancePathID för varje ansluten USB kontrollerar systemet om USB-minnet uppfyller båda värdena.

    - MatchAny: Attributen under DescriptorIdList blir **Eller relationen;** Om administratören till exempel placerar DeviceID och InstancePathID, för varje anslutet USB-minne, kommer systemet att upprätthålla tillämpning så länge USB-minnet har antingen ett identiskt **DeviceID-** eller **InstanceID-värde.**

Här är egenskaperna för principegenskaper för åtkomstkontroll:

**Egenskapsnamn: PolicyRuleId**

1. Beskrivning: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), ett unikt ID, representerar principen och kommer att användas i rapportering och felsökning.

**Egenskapsnamn: IncludedIdList**

1. Beskrivning: De grupper som principen ska tillämpas på. Om flera grupper läggs till tillämpas principen på alla media i alla grupperna.

1. Alternativ: Grupp-ID/GUID måste användas i den här instansen.

I följande exempel visas användningen av GroupID:

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

**Egenskapsnamn: ExcludedIDList**

1. Beskrivning: De grupper som principen inte ska tillämpas på.
1. Alternativ: Grupp-ID/GUID måste användas i den här instansen.

**Egenskapsnamn: Post-ID**

1. Beskrivning: En principregel kan ha flera poster. varje post med ett unikt GUID anger enhetskontroll en begränsning.

**Egenskapsnamn: Typ**

1. Beskrivning: Definierar åtgärden för de flyttbara lagringsgrupperna i IncludedIDList.
    - Tillämpning: Tillåt eller Neka
    - Granskning: GranskningSalla eller GranskaDenied 
1. Alternativ:
    - Tillåt
    - Neka
    - AuditAllowed: Definierar meddelande och händelse när åtkomst är tillåten
    - AuditDenied: Definierar meddelande och händelse när åtkomst nekas. måste arbeta tillsammans med **den nekade** posten.

När det finns konflikttyper för samma media används den första i principen i systemet. Ett exempel på en konflikt är **Tillåt** **och Neka.**

**Egenskapsnamn: Alternativ**

1. Beskrivning: Definierar om meddelandet ska visas eller inte.

   :::image type="content" source="images/device-status.png" alt-text="Skärmen där enhetens status visas":::

1. Alternativ: 0–4. När Tillåt eller Neka är markerat:

   - 0: ingenting
   - 4: Inaktivera **AuditAllowed** **och AuditDenied för** den här posten. Även om **Blockera** inträffar **och AuditDenied-inställningen** har konfigurerats visas inget meddelande i systemet.

   När Type **AuditAllowed** **eller AuditDenied** är markerat:

   - 0: ingenting
   - 1: visa meddelande
   - 2: skicka händelse
   - 3: visa meddelande och skicka händelse

**Egenskapsnamn: AccessMask**

1. Beskrivning: Definierar åtkomsten.

1. Alternativ: 1–7:
    - 1: Läsa
    - 2: Skriva
    - 3: Läsa och skriva
    - 4: Utför
    - 5: Läsa och utföra
    - 6: Skriva och utföra
    - 7: Läsa och skriva och utföra

## <a name="common-removable-storage-access-control-scenarios"></a>Vanliga scenarier för Storage och Access-kontroll

Vi har satt ihop några vanliga scenarier som du kan följa för att bekanta dig med Microsoft Defender för slutpunkten flyttbara Storage Access Control.

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>Scenario 1: Förhindra skrivning och körning av åtkomst till alla men tillåta specifika godkända USBs

1. Skapa grupper
    1. Grupp 1: Alla flyttbara lagringsmedia och CD/DVD. Ett exempel på flyttbart lagringsutrymme och cd/dvd är: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** i exemplet Any [Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.
    
    2. Grupp 2: Godkända usa baserat på enhetsegenskaper. Ett exempel för det här användningsfall är: Instans-ID – Grupp **65fa649a-a111-4912-9294-fb6337a25038** i exemplet Godkända [amerikanska Group.xml-filer.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)

    > [!NOTE]
    > Du måste ersätta `&` med `&amp;` i värdet.

2. Skapa princip
    1. Princip 1: Blockera skrivning och körning av Access men tillåt godkända amerikanskabs. Ett exempel för det här användningsfall är: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** i exemplet [Scenario 1 Blockera skrivning](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) och kör Access men tillåt godkända USBs .xml-fil.
    
    2. Princip 2: Granska skrivning och kör åtkomst till tillåtna USB. Ett exempel för det här användningsfall är: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** i exemplet Scenario 1 Granskningsskrivning och Kör åtkomst till [godkänd USBs.xml-fil.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a>Scenario 2: Granska skrivning och kör åtkomst till alla utom blockera specifika usbs som inte godkänts

1. Skapa grupper
    1. Grupp 1: Alla flyttbara lagringsmedia och CD/DVD. Ett exempel för det här användningsfall är: Grupp **9b28fae8-72f7-4267-a1a5-685f747a7146** i exemplet [Flyttbara Storage- och CD-DVD-Group.xmlfiler.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)
    
    2. Grupp 2: Ej godkända amerikanska sampel baserat på enhetsegenskaper, exempelvis leverantörs-ID/produkt-ID, eget namn – grupp **65fa649a-a111-4912-9294-fb6337a25038** i [exempelfilen Group.xmlusbs som](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) inte godkänts. 

    > [!NOTE]
    > Du måste ersätta `&` med `&amp;` i värdet.

2. Skapa princip
    1. Princip 1: Blockera skrivning och körning av åtkomst till alla utom blockera specifika usBs som inte godkänts. Ett exempel på det här användningsfall är: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** i exempelscenario 2 Granskningsskrivning och Kör åtkomst till alla men blockerar en viss ej USBs.xml [fil.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)
    
    2. Princip 2: Granska skrivning och utför åtkomst till andra. Ett exempel på det här användningsfall är: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** i exemplet [Scenario 2](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Granskningsskrivning och Kör åtkomst till others.xmlfil.

## <a name="deploying-and-managing-policy-via-group-policy"></a>Distribuera och hantera princip via grupprincip

Med funktionen Storage och Access Control kan du tillämpa en princip via grupprincip på antingen en användare eller enhet eller både och.

### <a name="licensing"></a>Licensiering

Innan du kommer igång med Flyttbara Storage Access Control måste du bekräfta din [Microsoft 365-prenumeration.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2) För att komma åt och använda Storage Access Control måste du ha Microsoft 365 E3 eller Microsoft 365 E5.

### <a name="deploying-policy-via-group-policy"></a>Distribuera princip via grupprincip

1. Kombinera alla grupper i `<Groups>` `</Groups>` en XML-fil. 

    Följande bild illustrerar exemplet på [Scenario 1: Förhindra skrivning](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)och kör åtkomst till alla men tillåta specifika godkända amerikanskabs .
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Skärmen som visar konfigurationsinställningar som tillåter specifika godkända usbs på enheter":::
    
2. Kombinera alla regler i `<PolicyRules>` `</PolicyRules>` en XML-fil. 

    Om du vill begränsa en viss användare använder du SID-egenskapen i Posten. Om det inte finns någon SID i principposten kommer posten att tillämpas på alla inloggningsinstans för datorn.
    
    Följande bild visar användningen av SID-egenskapen och ett exempel på [Scenario 1: Förhindra skrivning](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)och kör åtkomst till alla men tillåta specifika godkända USBs.
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="Skärmen som visar en kod som anger användningen av sidegenskapsattributet":::

3. Spara både regel- och grupp-XML-filer i mappen för nätverksresurs och placera sökvägen till mappen för nätverksresurs i grupprincipinställningen: Datorkonfiguration -> Administrativa mallar **-> Windows-komponenter -> Microsoft Defender Antivirus -> Enhetskontroll: Definiera** grupper för enhetskontrollprinciper och Definiera regler för enhetskontrollprinciper.

    - Måldatorn måste kunna komma åt nätverksresursen för att principen ska vara på. När principen har lästs behövs dock inte längre nätverksanslutningen för nätverksresursen, även efter att datorn startats om.

    :::image type="content" source="images/device-control.png" alt-text="Skärmen Enhetskontroll":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a>Distribuera och hantera princip via Intune OMA-URI

Med funktionen flyttbara Storage Access Control kan du tillämpa principen via OMA-URI på antingen användare eller enhet, eller båda.

### <a name="licensing"></a>Licensiering

Innan du kommer igång med Flyttbara Storage Access Control måste du bekräfta din [Microsoft 365-prenumeration.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2) För att komma åt och använda Storage Access Control måste du ha Microsoft 365 E3 eller Microsoft 365 E5.

### <a name="permission"></a>Behörighet

För principdistribution i Intune måste kontot ha behörighet att skapa, redigera, uppdatera eller ta bort profiler för enhetskonfiguration. Du kan skapa anpassade roller eller använda någon av de inbyggda rollerna med dessa behörigheter.

- Rollen Princip- och profilhanterare
- Anpassad roll med behörigheten Skapa/Redigera/Uppdatera/Läsa/Ta bort/Visa rapporter aktiverad för enhetskonfigurationsprofiler
- Global administratör

### <a name="deploying-policy-via-oma-uri"></a>Distribuera princip via OMA-URI

**Microsoft Endpoint Manager administrationscenter ( https://endpoint.microsoft.com/) -> -> Konfigurationsprofiler -> Skapa profil ->-plattform: Windows 10 och senare & Profil: Anpassad**

1. Skapa en OMA-URI-regel för varje grupp:
    - OMA-URI: 

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData

      För flyttbara **lagrings- och CD-/DVD-grupper** i samplet måste länken till exempel vara:

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData

    - Datatyp: Sträng (XML-fil)
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="XML-filen för datatypen STRING":::

2. För varje princip skapar du även en OMA-URI:

    - OMA-URI: 

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData

      För till exempel regeln **Blockera skrivning och körning av Access men** tillåt godkända amerikanskabs i exemplet måste länken vara: 

      ./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.

    - Datatyp: Sträng (XML-fil)

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="Visning av XML-fil för datatypen STRING":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a>Distribuera och hantera princip med hjälp av användargränssnittet i Intune

Den här funktionen (i Microsoft Endpoint Manager admincenter (>-enheter > konfigurationsprofiler > Skapa profil >-plattform: Windows 10 och senare & Profil: Enhetskontroll) är ännu inte https://endpoint.microsoft.com/) tillgänglig. 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>Visa flyttbara enheter med enhetskontroll Storage Access Control-data i Microsoft Defender för Slutpunkt

I Microsoft 365 säkerhetsportalen visas flyttbart lagringsutrymme som blockeras av den flyttbara enhetskontrollen Storage Access Control. För att komma Microsoft 365 säkerhet måste du ha följande prenumeration:

- Microsoft 365 för E5-rapportering

```kusto
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == &quot;RemovableStoragePolicyTriggered&quot; 
| extend parsed=parse_json(AdditionalFields) 
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess)  
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict)  
| extend MediaBusType = tostring(parsed.BusType)  
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId) 
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId) 
| extend MediaName = tostring(parsed.MediaName) 
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy)  
| extend MediaProductId = tostring(parsed.ProductId)  
| extend MediaVendorId = tostring(parsed.VendorId)  
| extend MediaSerialNumber = tostring(parsed.SerialNumber)  
| extend MediaVolume = tostring(parsed.Volume)  
| project Timestamp, DeviceId, DeviceName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber, MediaVolume 
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="Skärmen visar hur det flyttbara lagringsutrymmet blockeras":::
