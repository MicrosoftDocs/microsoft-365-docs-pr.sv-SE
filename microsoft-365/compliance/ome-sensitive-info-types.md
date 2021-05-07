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
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a><span data-ttu-id="06218-103">Skapa en princip för känslig informationstyp för organisationen med meddelandekryptering</span><span class="sxs-lookup"><span data-stu-id="06218-103">Create a sensitive information type policy for your organization using Message Encryption</span></span>

<span data-ttu-id="06218-104">Du kan antingen Exchange e-postflödesregler eller skydd mot dataförlust (DLP) för att skapa en princip för känslig information med Meddelandekryptering i Office 365.</span><span class="sxs-lookup"><span data-stu-id="06218-104">You can use either Exchange mail flow rules or Data Loss Prevention (DLP) to create a sensitive information type policy with Office 365 Message Encryption.</span></span> <span data-ttu-id="06218-105">Om du vill Exchange en e-postflödesregel kan du använda e Exchange administrationscentret (EAC) eller PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06218-105">To create an Exchange mail flow rule, you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="06218-106">Skapa principen med hjälp av e-postflödesregler i EAC</span><span class="sxs-lookup"><span data-stu-id="06218-106">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="06218-107">Logga in på Exchange (EAC) och gå till **E-postflödesregler.**  >  </span><span class="sxs-lookup"><span data-stu-id="06218-107">Sign in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**.</span></span> <span data-ttu-id="06218-108">På sidan Regler skapar du en regel som gäller för Meddelandekryptering i Office 365.</span><span class="sxs-lookup"><span data-stu-id="06218-108">On the Rules page, create a rule that applies Office 365 Message Encryption.</span></span> <span data-ttu-id="06218-109">Du kan skapa en regel utifrån villkor som exempelvis förekomsten av vissa nyckelord eller typer av känslig information i meddelandet eller den bifogade filen.</span><span class="sxs-lookup"><span data-stu-id="06218-109">You can create a rule based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="06218-110">Skapa principen med hjälp av e-postflödesregler i PowerShell</span><span class="sxs-lookup"><span data-stu-id="06218-110">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="06218-111">Använd ett arbets- eller skolkonto med global administratörsbehörighet i din organisation, starta Windows PowerShell en session och anslut till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="06218-111">Use a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="06218-112">Instruktioner finns i [Anslut för Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="06218-112">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="06218-113">Använd Set-IRMConfiguration och New-TransportRule för att skapa principen.</span><span class="sxs-lookup"><span data-stu-id="06218-113">Use the Set-IRMConfiguration and New-TransportRule cmdlets to create the policy.</span></span>

## <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="06218-114">Exempel på e-postflödesregel som skapats med PowerShell</span><span class="sxs-lookup"><span data-stu-id="06218-114">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="06218-115">Kör följande kommandon i PowerShell för att skapa en e-postflödesregel för Exchange som automatiskt krypterar e-postmeddelanden som skickas utanför organisationen med alternativet som endast krypteras om e-postmeddelandena eller deras bifogade filer innehåller följande typer av känslig information:</span><span class="sxs-lookup"><span data-stu-id="06218-115">Run the following commands in PowerShell to create an Exchange mail flow rule that automatically encrypts emails sent outside your organization with the encrypt-only option if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="06218-116">ABA-routningsnummer</span><span class="sxs-lookup"><span data-stu-id="06218-116">ABA routing number</span></span>
- <span data-ttu-id="06218-117">Kreditkortsnummer</span><span class="sxs-lookup"><span data-stu-id="06218-117">Credit card Number</span></span>
- <span data-ttu-id="06218-118">Dea-nummer</span><span class="sxs-lookup"><span data-stu-id="06218-118">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="06218-119">U.S. / Storbritannien</span><span class="sxs-lookup"><span data-stu-id="06218-119">U.S. / U.K.</span></span> <span data-ttu-id="06218-120">passnummer</span><span class="sxs-lookup"><span data-stu-id="06218-120">passport number</span></span>
- <span data-ttu-id="06218-121">U.S. bank account number</span><span class="sxs-lookup"><span data-stu-id="06218-121">U.S. bank account number</span></span>
- <span data-ttu-id="06218-122">U.S. Individual Taxpayer Identification Number (ITIN)</span><span class="sxs-lookup"><span data-stu-id="06218-122">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="06218-123">U.S. Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="06218-123">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

<span data-ttu-id="06218-124">Mer information finns i [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) [och New-TransportRule.](/powershell/module/exchange/new-transportrule)</span><span class="sxs-lookup"><span data-stu-id="06218-124">For more information, see [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) and [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="06218-125">Hur mottagare kommer åt bifogade filer</span><span class="sxs-lookup"><span data-stu-id="06218-125">How recipients access attachments</span></span>

<span data-ttu-id="06218-126">När Microsoft krypterar ett meddelande har mottagarna obegränsad åtkomst till bifogade filer när de öppnar och öppnar krypterad e-post.</span><span class="sxs-lookup"><span data-stu-id="06218-126">After Microsoft encrypts a message, recipients have unrestricted access to attachments when they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="06218-127">Så här förbereder du ändringen</span><span class="sxs-lookup"><span data-stu-id="06218-127">To prepare for this change</span></span>

<span data-ttu-id="06218-128">Du kanske vill uppdatera alla tillämpliga dokumentation och utbildningsmaterial för att förbereda användarna i din organisation för ändringen.</span><span class="sxs-lookup"><span data-stu-id="06218-128">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span> <span data-ttu-id="06218-129">Dela de Meddelandekryptering i Office 365 resurserna med användarna efter behov:</span><span class="sxs-lookup"><span data-stu-id="06218-129">Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="06218-130">Skicka, visa och svara på krypterade meddelanden i Outlook för pc</span><span class="sxs-lookup"><span data-stu-id="06218-130">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="06218-131">Microsoft 365 Essentials-video: Office meddelandekryptering</span><span class="sxs-lookup"><span data-stu-id="06218-131">Microsoft 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="06218-132">Visa dessa ändringar i granskningsloggen</span><span class="sxs-lookup"><span data-stu-id="06218-132">View these changes in the audit log</span></span>

<span data-ttu-id="06218-133">Microsoft 365 granskar den här aktiviteten och gör den tillgänglig för administratörer.</span><span class="sxs-lookup"><span data-stu-id="06218-133">Microsoft 365 audits this activity and makes it available to administrators.</span></span> <span data-ttu-id="06218-134">Åtgärden är "New-TransportRule" och ett avsnitt av en exempelgranskningspost från Granskningsloggsökning i Säkerhets- & kompatibilitetscenter visas nedan:</span><span class="sxs-lookup"><span data-stu-id="06218-134">The operation is 'New-TransportRule' and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="06218-135">Inaktivera eller anpassa principen för känsliga informationstyper</span><span class="sxs-lookup"><span data-stu-id="06218-135">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="06218-136">När du har skapat Exchange-e-postflödesregeln [](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) kan du inaktivera eller redigera regeln genom att gå till E-postflödesregler i administrationscentret för Exchange (EAC) och inaktivera regeln " Kryptera känsliga utgående e-postmeddelanden (regel för inkommande  >   *e-post)*".</span><span class="sxs-lookup"><span data-stu-id="06218-136">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule "*Encrypt outbound sensitive emails (out of box rule)*".</span></span>