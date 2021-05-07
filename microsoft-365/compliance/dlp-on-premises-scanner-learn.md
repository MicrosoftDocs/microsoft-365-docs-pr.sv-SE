---
title: Mer information om Microsoft 365 lokal skanner för dataförlustskydd (förhandsversion)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
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
description: I Microsoft 365 lokala skanner för dataförlustskydd utökas övervakning av filaktiviteter och skyddsåtgärder för dessa filer till lokala filresurser samt SharePoint-mappar och dokumentbibliotek. Filer genomsöks och skyddas av en Azure Information Protection-skanner (AIP)
ms.openlocfilehash: f0a34a13630e42c5dd29734ad708b3c11bb1d587
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52163002"
---
# <a name="learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a>Mer information om Microsoft 365 lokal skanner för dataförlustskydd (förhandsversion)

Microsofts lokala skanner för dataförlustskydd är en del av DLP-funktioner (Data Loss Prevention) i Microsoft 365 som du kan använda för att identifiera och skydda känsliga objekt i Microsoft 365-tjänster. Mer information om alla Microsofts DLP-erbjudanden finns i [Läs mer om skydd mot dataförlust](dlp-learn-about-dlp.md).

**DLP lokala skanner** crawlar lokala vilande data i filresurser och SharePoint-dokumentbibliotek och -mappar för känsliga objekt som, om de läckts, kan utgöra en risk för organisationen eller utgöra en risk för brott mot efterlevnadsprincipen. På så sätt får du den synlighet och kontroll som du behöver för att säkerställa att känsliga objekt används och skyddas på rätt sätt och för att förhindra riskfaktorer som kan avslöja dem. Den lokala DLP-skannern identifierar känslig information med hjälp av någon sorts [inbyggda](sensitive-information-type-entity-definitions.md) eller [anpassad känslig information](create-a-custom-sensitive-information-type.md), [känslighetsetiketter](sensitivity-labels.md) eller filegenskaper. Informationen om vad användare gör med känsliga objekt blir synlig i [aktivitetsutforskaren](data-classification-activity-explorer.md) och du kan tillämpa skyddsåtgärder för dessa objekt via [DLP-principer](create-test-tune-dlp-policy.md).

## <a name="the-dlp-on-premises-scanner-relies-on-azure-information-protection-scanner"></a>Den lokala DLP-skannern använder Azure Information Protection-skanner

Den lokala DLP-skannern använder en fullständig implementering av AIP-skannern (Azure Information Protection) för att övervaka, märka och skydda känsliga objekt. Om du inte är bekant med AIP-skannern rekommenderar vi att du bekantar dig med den. Mer information finns i följande artiklar:

- [Vad är Azure Information Protection](/azure/information-protection/what-is-information-protection)
- [Vad är AIP:s enhetliga etikettsskanner (Azure Information Protection)?](/azure/information-protection/deploy-aip-scanner)
- [Krav för installation och distribution av den enhetliga etikettsskannern för Azure Information Protection](/azure/information-protection/deploy-aip-scanner-prereqs)
- [Självstudiekurs: Installera AIP:s enhetliga etikettsskanner (Azure Information Protection)](/azure/information-protection/tutorial-install-scanner)
- [Konfigurera och installera AIP:s enhetliga etikettsskanner (Azure Information Protection)](/azure/information-protection/deploy-aip-scanner-configure-install)
- [Enhetlig etikettsklient för Azure Information Protection – versionshistorik och supportprincip](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)

## <a name="dlp-on-premises-scanner-actions"></a>DLP-åtgärder för lokal skanner

Den lokala DLP-skannern identifierar filer med en av följande fyra metoder:

- Typer av känslig information
- Känslighetsetiketter
- Filtillägg
- Anpassade dokumentegenskaper endast för Office-filer 

När en identifierad fil kan utgöra en potentiell risk om den läckts eller om en efterlevnadsprincip bryter mot reglerna kan den lokala DLP-skannern vidta någon av dessa fyra åtgärder.

|Åtgärd |Beskrivning  |
|---------|---------|
|**Blockera dessa personer från att komma åt filer som lagrats i en lokal skanner – Alla** | När den här åtgärden tillämpas blockeras åtkomsten till alla konton utom innehållsägaren, det sista kontot som ändrade objektet och administratören. Det gör du genom att ta bort alla konton från NTFS/SharePoint-behörigheter på filnivå utom filägaren, databasägaren (anges i inställningen för [Ställ in databasägaren](/azure/information-protection/deploy-aip-scanner-configure-install#use-a-data-loss-prevention-dlp-policy-public-preview) i innehållssökningsjobbet), den sista modifieraren (endast i SharePoint) och administratör. Sökningskontot tilldelas också FC-behörigheter för filen.|
|**Blockera dessa personer från att komma åt filer som lagrats i en lokal skanner – blockera org-wide (offentlig) åtkomst**    |När den här åtgärden tillämpas tas **_Alla_*_, _*_NT AUTHORITY\autentiserade användare_*_, och _*_Domänanvändare_** SID:er från filåtkomstkontrolllistan (ACL). Endast användare och grupper som uttryckligen har beviljats behörighet till filen eller den överordnade mappen kommer att kunna komma åt filen.|
|**Ange behörigheter för filen**|När den här åtgärden tillämpas tvingas filen att ärva behörigheterna för den överordnade mappen. Som standard tillämpas den här åtgärden bara om behörigheterna i den överordnade mappen är mer restriktiva än de behörigheter som redan finns i filen. Om till exempel ACL för filen är inställd på att endast tillåta **_specifika användare_*_ och den överordnade mappen konfigureras att tillåta _*_Domain Users_*_ grupp ärvs inte behörigheterna för den överordnade mappen av filen. Du kan åsidosätta det här beteendet genom att välja alternativet _* Ärva även om överordnade behörigheter är mindre restriktiva**.|
|**Ta bort filen från olämplig plats**|När den här åtgärden tillämpas ersätts den ursprungliga filen med en stub-fil med txt-filnamnstillägg och en kopia av den ursprungliga filen placeras i en karantänmapp. 

## <a name="whats-different-in-the-on-premises-scanner"></a>Vad är annorlunda i den lokala skannern

Det finns några extra begrepp du behöver känna till innan du tar dig in i den lokala skannern.

### <a name="aip-repositories-and-content-scan-jobs"></a>AIP-databaser och innehållssökningsjobb

Du måste skapa en AIP-innehållssökningsjobb och identifiera de databaser som är värd för de filer som ska utvärderas av DLP-motorn. Se till att du aktiverar DLP-regler i det skapade genomsökningsjobbet för AIP-innehåll.

### <a name="policy-tips"></a>Principtips

[Principtips](use-notifications-and-policy-tips.md) är inte tillgängliga i en lokal skanner.


### <a name="viewing-dlp-on-premises-scanner-events"></a>Visar åtgärder för lokal DLP-skanner

Data om den lokala DLP-skannern visas i [aktivitetsutforskaren](data-classification-activity-explorer.md) i M365 Efterlevnadscentret. 

## <a name="next-steps"></a>Nästa steg

Nu när du har lärt dig mer om lokal DLP-skanner är nästa steg:

1. [Komma igång med lokal DLP-skanner (förhandsversion)](dlp-on-premises-scanner-get-started.md)
2. [Använda den lokala DLP-skannern](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a>Se även

- [Komma igång med den lokala skannern för dataförlustskydd från Microsoft](dlp-on-premises-scanner-get-started.md)
- [Använda den lokala skannern för dataförlustskydd från Microsoft](dlp-on-premises-scanner-use.md)
- [Mer information om skydd mot dataförlust](dlp-learn-about-dlp.md)
- [Skapa, testa och justera en DLP-princip](create-test-tune-dlp-policy.md)
- [Kom igång med aktivitetsutforskaren](data-classification-activity-explorer.md)