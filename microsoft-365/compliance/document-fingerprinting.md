---
title: Fingeravtrycksfunktioner för dokument
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: ITPro
ms.topic: article
search.appverid: MET150
ms.service: exchange-online
ms.collection: M365-security-compliance
localization_priority: Normal
description: Informationsarbetare i organisationen hanterar många typer av känslig information under en vanlig dag. Med fingeravtrycksuttryck blir det enklare för dig att skydda den här informationen genom att identifiera standardformulär som används i hela organisationen. I det här avsnittet beskrivs begreppen bakom fingeravtrycksavtryck i dokument och hur du skapar ett med hjälp av PowerShell.
ms.openlocfilehash: 392b42e779de249dddc0acb4c7c757a009f9f743
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2021
ms.locfileid: "52162850"
---
# <a name="document-fingerprinting"></a>Fingeravtrycksfunktioner för dokument

Informationsarbetare i organisationen hanterar många typer av känslig information under en vanlig dag. I Säkerhetsefterlevnadscenter gör dokumentavtryckning det enklare för dig att skydda den här informationen genom att identifiera &amp; standardformulär som används i organisationen. I det här avsnittet beskrivs begreppen bakom fingeravtrycksavtryck i dokument och hur du skapar ett med hjälp av PowerShell.
  
## <a name="basic-scenario-for-document-fingerprinting"></a>Grundläggande scenario för fingeravtryck i dokument

Dokument fingeravtryck är en funktion för skydd mot dataförlust (DLP) som konverterar ett standardformulär till en typ av känslig information som du kan använda i reglerna för DLP-principer. Du kan till exempel skapa ett dokuments fingeravtryck baserat på en tom patentmall och sedan skapa en DLP-princip som identifierar och blockerar alla utgående patentmallar med känsligt innehåll ifyllt innehåll. Om du vill kan du konfigurera [principtips](use-notifications-and-policy-tips.md) för att meddela avsändarna att de kan skicka känslig information, och avsändaren bör kontrollera att mottagarna är behöriga att ta emot patenten. Den här processen fungerar med alla textbaserade formulär som används i organisationen. Ytterligare exempel på formulär som du kan ladda upp är:
  
- Myndighetsformulär
- HIPAA-efterlevnadsformulär (Health Insurance Portability and Accountability Act)  
- Personalinformationsformulär för Personalavdelningen
- Anpassade formulär som skapats specifikt för din organisation

Under idealiska omständigheter har organisationen redan en fastställda affärsmetod att använda vissa formulär för att överföra känslig information. När du överfört ett tomt formulär som ska konverteras till ett dokuments fingeravtryck och angett en motsvarande princip identifierar DLP alla dokument i utgående e-postmeddelanden som matchar fingeravtrycket.

## <a name="how-document-fingerprinting-works"></a>Så här fungerar fingeravtrycksavtryck i dokument

Du har antagligen redan gissat att dokument inte har faktiska fingeravtryck, men namnet hjälper till att förklara funktionen. Dokument har unika ordmönster, på samma sätt som en persons fingeravtryck har unika mönster. När du överför en fil identifierar DLP det unika ordmönstret i dokumentet, skapar ett dokuments fingeravtryck baserat på det mönstret och använder det dokument fingeravtrycket för att identifiera utgående dokument som innehåller samma mönster. Därför skapas den effektivaste typen av dokument fingeravtryck när du laddar upp ett formulär eller en mall. Alla som fyller i ett formulär använder samma ursprungliga uppsättning ord och lägger sedan till sina egna ord i dokumentet. Så länge det utgående dokumentet inte är lösenordsskyddat och innehåller all text från det ursprungliga formuläret kan DLP avgöra om dokumentet matchar dokumentets fingeravtryck.

> [!IMPORTANT]
> För tillfället kan DLP använda fingeravtryck för dokument som identifieringsmetod endast Exchange online.

Följande exempel visar vad som händer om du skapar ett dokuments fingeravtryck baserat på en patentmall, men du kan använda vilket formulär som helst som grund för att skapa fingeravtryck.
  
### <a name="example-of-a-patent-document-matching-a-document-fingerprint-of-a-patent-template"></a>Exempel på ett patentdokument som matchar ett dokuments fingeravtryck på en patentmall

![Diagram över fingeravtryck i dokument.](../media/Document-Fingerprinting-diagram.png)
  
Patentmallen innehåller de tomma fälten "Patenttitel", "Avdelningen" och "Beskrivning" samt beskrivningar för vart och ett av dessa fält – det är ordets mönster. När du laddar upp den ursprungliga patentmallen finns den i en av de filtyper som stöds och som oformaterad text. DLP konverterar det här ordmönstret till ett dokument fingeravtryck, som är en liten Unicode XML-fil som innehåller ett unikt hash-värde som representerar den ursprungliga texten, och fingeravtrycket sparas som en dataklassificering i Active Directory. (Som en säkerhetsåtgärd lagras inte själva det ursprungliga dokumentet i tjänsten. Det är bara hashvärdet som lagras och det ursprungliga dokumentet kan inte återskapas från hash-värdet.) Patent fingeravtrycket blir då en typ av känslig information som du kan associera med en DLP-princip. När du kopplar fingeravtrycket till en DLP-princip identifierar DLP alla utgående e-postmeddelanden som innehåller dokument som matchar det patenterade fingeravtrycket och hanterar dem enligt organisationens princip. 

Du kanske till exempel vill skapa en DLP-princip som förhindrar att vanliga anställda skickar utgående meddelanden med patent. DLP använder det patenterade fingeravtrycket för att identifiera patent och blockera dessa e-postmeddelanden. Du kanske också vill att den juridiska avdelningen ska kunna skicka patent till andra organisationer eftersom den har ett företag som behöver göra det. Du kan tillåta att vissa avdelningar skickar känslig information genom att skapa undantag för dessa avdelningar i DLP-principen, eller så kan du låta dem åsidosätta ett principtips med en justering för företaget.
  
### <a name="supported-file-types"></a>Filtyper som stöds

Document Fingerprinting har stöd för samma filtyper som stöds i e-postflödesregler (kallas även transportregler). En lista över filtyper som stöds finns i Filtyper [som stöds för innehållskontroll av e-postflödesregel.](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection) En anmärkning om filtyper: varken e-postflödesregler eller dokumentavtryckning stöder .dotx-filtypen, vilket kan vara förvirrande eftersom det är en mallfil i Word. När du ser ordet "mall" i denna och andra avsnitt om fingeravtrycksavtryck, syftar den på ett dokument som du har upprättat som standardformulär, inte som filtyp för mall.
  
#### <a name="limitations-of-document-fingerprinting"></a>Begränsningar av fingeravtryck i dokument

Fingeravtryck i dokument identifierar inte känslig information i följande fall:
  
- Lösenordsskyddade filer
- Filer som endast innehåller bilder
- Dokument som inte innehåller all text från det ursprungliga formuläret som användes för att skapa dokumentets fingeravtryck
- Filer som är större än 10 MB

## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>Använda PowerShell för att skapa ett klassificeringsregelpaket baserat på fingeravtryck från dokument

Observera att du för närvarande bara kan skapa ett fingeravtryck genom att använda PowerShell i &amp; Säkerhetsefterlevnadscenter. Information om hur du [ansluter Anslut till Säkerhets- & Compliance Center PowerShell.](/powershell/exchange/connect-to-scc-powershell)

DLP använder paket med klassificeringsregel för att identifiera känsligt innehåll. Om du vill skapa ett klassificeringsregelpaket baserat på ett dokuments fingeravtryck använder du **cmdletsna New-Dlp Fingerprint** och **New-DlpSensitiveInformationType.** Eftersom resultaten för **New-Dlp Fingerprint** inte lagras utanför dataklassificeringsregeln kör du alltid **New-Dlp Fingerprint** och **New-DlpSensitiveInformationType** eller **Set-DlpSensitiveInformationType** i samma PowerShell-session. Följande exempel skapar ett nytt dokuments fingeravtryck baserat på filen C:\My Documents\Contoso Employee Template.docx. Du lagrar det nya fingeravtrycket som en variabel så att du kan använda den med cmdleten **New-DlpSensitiveInformationType** i samma PowerShell-session.
  
```powershell
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

Nu skapar vi en ny dataklassificeringsregel med namnet "Contoso-anställd konfidentiellt" som använder dokumentets fingeravtryck från filen C:\My Documents\Contoso Customer Information Form.docx.
  
```powershell
$Customer_Form = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

Du kan nu använda cmdleten **Get-DlpSensitiveInformationType** till att hitta alla paket med DLP-dataklassificeringsregel, och i det här exemplet är "Contoso Customer Confidential" en del av listan med dataklassificeringsregelpaket. 
  
Lägg till sist till dataklassificeringsregelpaketet Contoso-konfidentiellt till en DLP-princip i &amp; Säkerhetsefterlevnadscenter. I det här exemplet läggs en regel till i en befintlig DLP-princip med namnet "ConfidentialPolicy".

```powershell
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

Du kan också använda dataklassificeringsregelpaketet i e-postflödesregler i Exchange Online, som du ser i följande exempel. För att kunna köra det här kommandot måste du först [Anslut och Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell) Observera också att det tar tid för regelpaketet att synkronisera från &amp; Säkerhetsefterlevnadscenter till Exchange administrationscentret.
  
```powershell
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}
```

DLP identifierar nu dokument som matchar Contoso Customer Form.docx-dokuments fingeravtryck.
  
Information om syntax och parametrar finns i:

- [New-Dlp Fingerprint](/powershell/module/exchange/New-DlpFingerprint)
- [New-DlpSensitiveInformationType](/powershell/module/exchange/New-DlpSensitiveInformationType)
- [Remove-DlpSensitiveInformationType](/powershell/module/exchange/Remove-DlpSensitiveInformationType)
- [Set-DlpSensitiveInformationType](/powershell/module/exchange/Set-DlpSensitiveInformationType)
- [Get-DlpSensitiveInformationType](/powershell/module/exchange/Get-DlpSensitiveInformationType)
