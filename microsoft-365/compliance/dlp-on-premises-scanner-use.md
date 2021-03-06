---
title: Använd Microsoft 365 lokal skanner för dataförlustskydd (förhandsversion)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
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
description: Lär dig hur du använder Microsoft 365 lokal skanner för dataförlustskydd för att skanna igenom vilande data och implementera skyddsåtgärder för lokala filresurser och lokala SharePoint-mappar och dokumentbibliotek.
ms.openlocfilehash: b2512c47b82ab3624d892d349611dd3f1e5aed3c
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289181"
---
# <a name="use-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a>Använd Microsoft 365 lokal skanner för dataförlustskydd (förhandsversion)

För att bekanta dig med lokala DLP-funktioner, och hur de visar sig i DLP-principer, har vi skapat scenarier som du kan följa.

> [!IMPORTANT]
> De här lokala DLP-scenarierna är inte officiella procedurer för att skapa och justera DLP-principer. Läs följande avsnitt om du behöver arbeta med DLP-principer i allmänna situationer:
>
> - [Mer information om dataförlustskydd](dlp-learn-about-dlp.md)
> - [Kom igång med DLP-standardprincipen](get-started-with-the-default-dlp-policy.md)
> - [Skapa en DLP-princip från en mall](create-a-dlp-policy-from-a-template.md)
> - [Skapa, testa och justera en DLP-princip](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a>Scenario: Upptäck filer som matchar DLP-regler

Data från lokala DLP-skanner visar sig i flera områden

#### <a name="activity-explorer"></a>Aktivitetsutforskare

 Lokal Microsoft DLP identifierar DLP-regelmatchningar och rapporterar dem till [Aktivitetsutforskaren](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer).

#### <a name="microsoft-365-audit-log"></a>Microsoft 365-granskningslogg

Under den offentliga förhandsversionen är DLP-regelmatchningar tillgängliga i användargränssnittet för granskningsloggen. Läs mer i [Söka i granskningsloggen i efterlevnadscentret](search-the-audit-log-in-security-and-compliance.md)  eller komma åt den med[Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) PowerShell.

#### <a name="aip"></a>AIP

Identifieringsdata är tillgänglig i en lokal rapport i CSV-format som lagras i:

**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.

 Leta efter följande kolumner:

- DLP-läge
- DLP-status
- DLP-kommentar
- Namn på DLP-regel
- DLP-åtgärder
- Ägare
- Aktuella NTFS-behörigheter (SDDL)
- Tillämpade NTFS-behörigheter (SDDL)
- NTFS-behörighetstyp

### <a name="scenario-enforce-dlp-rule"></a>Scenario: Tillämpad DLP-regel

Om du vill tillämpa DLP-regler för de skannade filerna måste tillämpning vara aktiverat för både innehållssökningsjobbet i AIP och på principnivån i DLP.

#### <a name="configure-dlp-to-enforce-policy-actions"></a>Konfigurera DLP för att tillämpa principåtgärder

1. Öppna [sidan Dataförlustskydd](https://compliance.microsoft.com/datalossprevention?viewid=policies) och välj den DLP-princip som är avsedd för de lokala platsdatabaser som du har konfigurerat i AIP.
2. Redigera principen.
3. På sidan **Testa eller aktivera principen** väljer du **Ja, aktivera det direkt**.

## <a name="see-also"></a>Se även

- [Läs mer om DLP-lokal skanner (förhandsversion)](dlp-on-premises-scanner-learn.md)
- [Komma igång med DLP-lokal skanner (förhandsversion)](dlp-on-premises-scanner-get-started.md)
- [Mer information om dataförlustskydd](dlp-learn-about-dlp.md)
- [Skapa, testa och justera en DLP-princip](create-test-tune-dlp-policy.md)
- [Kom igång med aktivitetsutforskaren](data-classification-activity-explorer.md)
