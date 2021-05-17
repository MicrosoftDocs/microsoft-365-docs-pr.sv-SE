---
title: Kom igång med Microsoft 365 lokal skanner för dataförlustskydd (förhandsversion)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Använd Microsoft 365 lokal skanner för dataförlustskydd
ms.openlocfilehash: 242956a3c6469756481fb823340e715a210562af
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52163003"
---
# <a name="get-started-with-the-data-loss-prevention-on-premises-scanner-preview"></a>Kom igång med lokal skanner för dataförlustskydd (förhandsversion)

Den här artikeln beskriver förutsättningar och konfiguration för Microsoft 365 lokal skanner för dataförlustskydd.

## <a name="before-you-begin"></a>Innan du börjar

### <a name="skusubscriptions-licensing"></a>Licensiering av SKU/prenumerationer

Innan du börjar med den lokala DLP-skannern måste du bekräfta din [Microsoft 365-prenumeration](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) och eventuella tillägg. Om du vill delta i förhandsversionen av administratörskontot som konfigurerar DLP-regler, måste någon av följande licenser tilldelas:

- Microsoft 365 E5
- Microsoft 365 E5 Compliance
- Microsoft 365 E5 – Informationsskydd och styrning 


Fullständig licensinformation finns i: [Vägledning för säkerhet och efterlevnad med licensiering i Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

### <a name="permissions"></a>Behörigheter


Data från den lokala DLP-skannern kan visas i [aktivitetsutforskaren](data-classification-activity-explorer.md). Det finns fyra roller som ger behörighet till aktivitetsutforskaren och det konto som du använder för att komma åt datan måste vara medlem i någon av dem.

- Global administratör
- Efterlevnadsadministratör
- Säkerhetsadministratör
- Administratör för efterlevnadsdata

### <a name="dlp-on-premises-scanner-prerequisites"></a>Förutsättningar för lokal DLP-skanner

- AIP-skannern (Azure Information Protection) implementerar matchning och tillämpning av DLP-principen. Skannern installeras som en del av AIP-klienten. Installationen måste därför uppfylla alla krav för AIP, AIP-klienten och AIP-skannern för enhetliga etiketter.
- Distribuera AIP-klienten och skannern. Mer information finns i [Installera AIP-klienten för enhetliga etiketter](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) och []. Se [Konfigurera och installera Azure Information Protection-skannern för enhetliga etiketter](/azure/information-protection/deploy-aip-scanner-configure-install).
- Minst en etikett och princip måste ha publicerats i klientorganisationen, även om alla identifieringsregler endast baseras på typerna av känslig information.

## <a name="deploy-the-dlp-on-premises-scanner"></a>Distribuera den lokala DLP-skannern

1. Följ metoderna i [Installera AIP-klienten för enhetliga etiketter](/azure/information-protection/rms-client/install-unifiedlabelingclient-app). 
2. Följ metoderna i [Konfigurera och installera Azure Information Protection-skannern för enhetliga etiketter](/azure/information-protection/deploy-aip-scanner-configure-install) för att slutföra skannerinstallationen.
    1. Konfigurationen av nätverksidentifieringsjobb är ett valfritt steg. Du kan hoppa över det och definiera specifika lagringsplatser som ska genomsökas i innehållssökningsjobbet.
    2. Du måste skapa ett innehållssökningsjobb och ange de lagringsplatser som är värd för filerna som ska utvärderas av DLP-motorn.
    3. Aktivera DLP-regler i det skapade innehållssökningsjobbet och ange alternativet **Tillämpa** som **Av**, såvida du inte vill gå direkt till DLP-tillämpningsfasen.
3. Kontrollera att innehållssökningsjobbet har tilldelats till rätt kluster. Om du ännu inte har skapat något innehållssökningsjobb, skapar du ett nytt och tilldelar det till det kluster som innehåller skannernoderna som kör den allmänt tillgängliga förhandsversionen.

4. Anslut till [Azure Information Protection-tillägget i Azure-portalen](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) och lägg till dina lagringsplatser i det innehållssökningsjobb som ska utföra genomsökningen.

5. Kör genomsökningen på något av följande sätt:
    1. ange skannerschemat
    1. använd det manuella alternativet **Genomsök nu** i portalen
    1. eller kör PowerShell-cmdleten **Start-AIPScan**

   > [!IMPORTANT]
   > Kom ihåg att skannern kör en deltagenomsökning av lagringsplatsen som standard och att filer som redan genomsökts i föregående genomsökningscykel hoppas över, om inte filen har ändrats eller om du har initierat en fullständig ny genomsökning. En fullständig ny genomsökning kan initieras med alternativet **Genomsök alla filer på nytt** i användargränssnittet eller genom att köra **Start-AIPScan-Reset**.

6.  Öppna [sidan Dataförlustskydd](https://compliance.microsoft.com/datalossprevention?viewid=policies) i Microsoft 365 Efterlevnadscenter.

7. Välj **Skapa princip** och skapa ett test av DLP-principen. Se [Skapa en DLP-princip från en mall](create-a-dlp-policy-from-a-template.md) om du behöver hjälp med att skapa en princip. Kör den som ett test tills du känner dig bekväm med funktionen. Använd följande parametrar till principen:
    1. Begränsa den lokala DLP-skannerregeln till specifika platser om det behövs. Om du anger **Platser** till **Alla**, kommer alla filer som genomsöks av skannern att omfattas av matchningen och tillämpningen av DLP-regeln.
    1. När du anger platserna kan du antingen använda en undantagslista eller en inkluderingslista. I den allmänt tillgängliga förhandsversionen kan du inte ange båda. Du kan antingen definiera att regeln endast är relevant för sökvägar som matchar ett av mönstren som anges i inkluderingslistan, eller alla filer förutom de filer som matchar mönstret i inkluderingslistan. Inga lokala sökvägar stöds. Här är några exempel på giltiga sökvägar:
      - \\\server\share
      - \\\server\share\folder1\subfolderabc
      - \*\\folder1
      - \*secret\*.docx
      - \*secret\*.\*
      - https:// sp2010.local/sites/HR
      - https://\*/HR 
    3. Här är några exempel på otillåtna värden:
      - \*
      - \*\\a
      - Aaa
      - c:\
      - C:\test

> [!IMPORTANT]
> Undantagslistan har företräde framför inkluderingslistan.

### <a name="viewing-dlp-on-premises-scanner-alerts-in-dlp-alerts-management-dashboard"></a>Visa lokala DLP-skanneraviseringar i instrumentpanelen för hantering av DLP-aviseringar

1. Öppna [sidan Dataförlustskydd](https://compliance.microsoft.com/datalossprevention?viewid=policies) i Microsoft 365 Efterlevnadscenter och välj **Varningar**.

2. Se procedurerna i [Konfigurera och visa aviseringar för dina DLP-principer](dlp-configure-view-alerts-policies.md) om du vill se aviseringarna för dina slutpunkts-DLP-principer.

### <a name="viewing-dlp-on-premises-scanner-in-activity-explorer-and-audit-log"></a>Visa den lokala DLP-skannern i aktivitetsutforskaren och granskningsloggen

> [!NOTE]
> Granskning måste vara aktiverad i den lokala skannern. I Microsoft 365 är granskning aktiverad som standard.

1. Öppna [sidan Dataklassificering](https://compliance.microsoft.com/dataclassification?viewid=overview) för din domän i Microsoft 365 Efterlevnadscenter och välj aktivitetsutforskaren.

2. Se procedurerna i [Kom igång med aktivitetsutforskaren](data-classification-activity-explorer.md) för att komma åt och filtrera alla data för dina lokala skannerplatser.

3. Öppna [Granskningslogg i efterlevnadscentret](https://security.microsoft.com/auditlogsearch). I den allmänt tillgängliga förhandsversionen är DLP-regelmatchningar tillgängliga i granskningsloggens användargränssnitt eller kan nås av [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) i PowerShell 


## <a name="next-steps"></a>Nästa steg
Nu när du har distribuerat en testprincip för lokala DLP-platser och kan se aktivitetsdata i aktivitetsutforskaren, kan du gå vidare till nästa steg där du skapar DLP-principer som skyddar dina känsliga objekt.

- [Använda DLP lokalt (förhandsversion)](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a>Se även

- [Mer information om lokal DLP-skanner (förhandsversion)](dlp-on-premises-scanner-learn.md)
- [Använda lokal DLP-skanner (förhandsversion)](dlp-on-premises-scanner-use.md)
- [Mer information om dataförlustskydd](dlp-learn-about-dlp.md)
- [Skapa, testa och justera en DLP-princip](create-test-tune-dlp-policy.md)
- [Kom igång med aktivitetsutforskaren](data-classification-activity-explorer.md)
- [Microsoft 365-prenumeration](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)