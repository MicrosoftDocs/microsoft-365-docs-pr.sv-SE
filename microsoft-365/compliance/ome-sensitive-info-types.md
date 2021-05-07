---
title: Skapa en princip för känslig information med Meddelandekryptering i Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: Lär dig hur du skapar en princip för känslig information för organisationen med hjälp av Meddelandekryptering i Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ad570f64122aecd245b912b1b6545a5950e838cc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162243"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a>Skapa en princip för känslig informationstyp för organisationen med meddelandekryptering

Du kan antingen Exchange e-postflödesregler eller skydd mot dataförlust (DLP) för att skapa en princip för känslig information med Meddelandekryptering i Office 365. Om du vill Exchange en e-postflödesregel kan du använda e Exchange administrationscentret (EAC) eller PowerShell.

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>Skapa principen med hjälp av e-postflödesregler i EAC

Logga in på Exchange (EAC) och gå till **E-postflödesregler.**  >   På sidan Regler skapar du en regel som gäller för Meddelandekryptering i Office 365. Du kan skapa en regel utifrån villkor som exempelvis förekomsten av vissa nyckelord eller typer av känslig information i meddelandet eller den bifogade filen.

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>Skapa principen med hjälp av e-postflödesregler i PowerShell

Använd ett arbets- eller skolkonto med global administratörsbehörighet i din organisation, starta Windows PowerShell en session och anslut till Exchange Online. Instruktioner finns i [Anslut för Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell) Använd Set-IRMConfiguration och New-TransportRule för att skapa principen.

## <a name="example-mail-flow-rule-created-with-powershell"></a>Exempel på e-postflödesregel som skapats med PowerShell

Kör följande kommandon i PowerShell för att skapa en e-postflödesregel för Exchange som automatiskt krypterar e-postmeddelanden som skickas utanför organisationen med alternativet som endast krypteras om e-postmeddelandena eller deras bifogade filer innehåller följande typer av känslig information:

- ABA-routningsnummer
- Kreditkortsnummer
- Dea-nummer
- U.S. / Storbritannien passnummer
- U.S. bank account number
- U.S. Individual Taxpayer Identification Number (ITIN)
- U.S. Social Security Number (SSN)

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

Mer information finns i [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) [och New-TransportRule.](/powershell/module/exchange/new-transportrule)

## <a name="how-recipients-access-attachments"></a>Hur mottagare kommer åt bifogade filer

När Microsoft krypterar ett meddelande har mottagarna obegränsad åtkomst till bifogade filer när de öppnar och öppnar krypterad e-post.

## <a name="to-prepare-for-this-change"></a>Så här förbereder du ändringen

Du kanske vill uppdatera alla tillämpliga dokumentation och utbildningsmaterial för att förbereda användarna i din organisation för ändringen. Dela de Meddelandekryptering i Office 365 resurserna med användarna efter behov:

- [Skicka, visa och svara på krypterade meddelanden i Outlook för pc](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [Microsoft 365 Essentials-video: Office meddelandekryptering](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>Visa dessa ändringar i granskningsloggen

Microsoft 365 granskar den här aktiviteten och gör den tillgänglig för administratörer. Åtgärden är "New-TransportRule" och ett avsnitt av en exempelgranskningspost från Granskningsloggsökning i Säkerhets- & kompatibilitetscenter visas nedan:

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>Inaktivera eller anpassa principen för känsliga informationstyper

När du har skapat Exchange-e-postflödesregeln [](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) kan du inaktivera eller redigera regeln genom att gå till E-postflödesregler i administrationscentret för Exchange (EAC) och inaktivera regeln " Kryptera känsliga utgående e-postmeddelanden (regel för inkommande  >   *e-post)*".