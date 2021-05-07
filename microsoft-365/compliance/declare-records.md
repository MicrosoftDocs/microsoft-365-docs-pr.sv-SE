---
title: Deklarera poster med hjälp av kvarhållningsetiketter
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Deklarera poster med hjälp av kvarhållningsetiketter.
ms.openlocfilehash: fd88858c8d5cd1870f594050607b784a9dc5b78c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162209"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="55e62-103">Deklarera poster med hjälp av kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="55e62-103">Declare records by using retention labels</span></span>

><span data-ttu-id="55e62-104">*[Licensieringsvägledning för Microsoft 365 för säkerhet och efterlevnad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="55e62-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="55e62-105">Om du vill deklarera dokument och e-postmeddelanden som [poster](records-management.md#records) kan du använda [kvarhållningsetiketter](retention.md#retention-labels) som markerar innehållet som en **post** eller som en **regelbaserad post**.</span><span class="sxs-lookup"><span data-stu-id="55e62-105">To declare documents and emails as [records](records-management.md#records), you use [retention labels](retention.md#retention-labels) that mark the content as a **record** or a **regulatory record**.</span></span>

<span data-ttu-id="55e62-106">Om du är osäker på om du bör använda en post eller en regelbaserad post kan du läsa [Jämför begränsningarna för vilka åtgärder som tillåts och blockeras](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span><span class="sxs-lookup"><span data-stu-id="55e62-106">If you're not sure whether to use a record or a regulatory record, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span> <span data-ttu-id="55e62-107">Om du behöver använda regelbaserade poster måste du först köra ett PowerShell-kommando enligt anvisningarna i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="55e62-107">If you need to use regulatory records, you must first run a PowerShell command, as described in the next section.</span></span>

<span data-ttu-id="55e62-108">Därefter kan du antingen publicera etiketterna i en policy för kvarhållningsetiketter, så att användare och administratörer kan använda dem på innehåll, eller använda automatisk användning av etiketterna på innehåll som du vill deklarera som en post (gäller etiketter som markerar objekt som poster, dock ej som regelbaserade poster).</span><span class="sxs-lookup"><span data-stu-id="55e62-108">You can then either publish those labels in a retention label policy so that users and administrators can apply them to content, or for labels that mark items as records (but not regulatory records), auto-apply those labels to content that you want to declare a record.</span></span>

## <a name="how-to-display-the-option-to-mark-content-as-a-regulatory-record"></a><span data-ttu-id="55e62-109">Så här visar du alternativet för att markera innehåll som en regelbaserad post</span><span class="sxs-lookup"><span data-stu-id="55e62-109">How to display the option to mark content as a regulatory record</span></span>

>[!NOTE] 
> <span data-ttu-id="55e62-110">Följande procedur är en granskningsbar åtgärd som medför att **Aktivering av alternativet för regelbaserade poster för kvarhållningsetiketter** loggas i avsnittet [Kvarhållningspolicy och aktiviteter gällande kvarhållningsetiketter](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities) i granskningsloggen.</span><span class="sxs-lookup"><span data-stu-id="55e62-110">The following procedure is an auditable action, logging **Enabled regulatory record option for retention labels** in the [Retention policy and retention label activities](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities) section of the audit log.</span></span>

<span data-ttu-id="55e62-111">Som standard visas inte alternativet för kvarhållningsetiketter, där innehåll kan markeras som en regelbaserad post, i guiden för kvarhållningsetiketter.</span><span class="sxs-lookup"><span data-stu-id="55e62-111">By default, the retention label option to mark content as a regulatory record isn't displayed in the retention label wizard.</span></span> <span data-ttu-id="55e62-112">Om du vill att det här alternativet ska visas måste du först köra ett PowerShell-kommando:</span><span class="sxs-lookup"><span data-stu-id="55e62-112">To display this option, you must first run a PowerShell command:</span></span>

1. <span data-ttu-id="55e62-113">[Ansluta till Säkerhets- och efterlevnadscenter för Office 365 via PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="55e62-113">[Connect to the Office 365 Security & Compliance Center Powershell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="55e62-114">Kör följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="55e62-114">Run the following cmdlet:</span></span>
    
    ```powershell
    Set-RegulatoryComplianceUI -Enabled $true
    ````
    <span data-ttu-id="55e62-115">Du behöver inte bekräfta åtgärden och inställningen börjar gälla omedelbart.</span><span class="sxs-lookup"><span data-stu-id="55e62-115">There is no prompt to confirm and the setting takes effect immediately.</span></span>

<span data-ttu-id="55e62-116">Om du ångrar dig och inte längre vill att alternativet ska visas i guiden kan du dölja det genom att köra samma cmdlet med värdet **falskt**: `Set-RegulatoryComplianceUI -Enabled $false`</span><span class="sxs-lookup"><span data-stu-id="55e62-116">If you change your mind about seeing this option in the retention label wizard, you can hide it again by running the same cmdlet with the **false** value: `Set-RegulatoryComplianceUI -Enabled $false`</span></span> 

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="55e62-117">Konfigurera kvarhållningsetiketter för att deklarera poster</span><span class="sxs-lookup"><span data-stu-id="55e62-117">Configuring retention labels to declare records</span></span>

<span data-ttu-id="55e62-118">När du skapar eller redigerar kvarhållningsetiketter via lösningen för **hantering av arkivhandlingar** i Microsoft 365 Efterlevnadscenter får du möjlighet att markera objekt som poster.</span><span class="sxs-lookup"><span data-stu-id="55e62-118">When you create or edit a retention label from the **Records Management** solution in the Microsoft 365 compliance center, you have the option to mark items as a record.</span></span> <span data-ttu-id="55e62-119">Om du har kört PowerShell-kommandot enligt anvisningarna i ovanstående avsnitt kan du även markera objekt som regelbaserade poster.</span><span class="sxs-lookup"><span data-stu-id="55e62-119">If you ran the PowerShell command from the previous section, you can alternatively mark items as a regulatory record.</span></span>

<span data-ttu-id="55e62-120">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="55e62-120">For example:</span></span>

![Konfigurera en kvarhållningsetikett för att markera innehåll som en post eller en regelbaserad post](../media/recordversioning6.png)

<span data-ttu-id="55e62-122">Därefter kan du vid behov använda kvarhållningsetiketten på Exchange-meddelanden eller SharePoint- och OneDrive-dokument.</span><span class="sxs-lookup"><span data-stu-id="55e62-122">Using this retention label, you can now apply it to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> 

<span data-ttu-id="55e62-123">Fullständiga instruktioner:</span><span class="sxs-lookup"><span data-stu-id="55e62-123">For full instructions:</span></span>

- [<span data-ttu-id="55e62-124">Skapa kvarhållningsetiketter och använda dem i appar</span><span class="sxs-lookup"><span data-stu-id="55e62-124">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)

- <span data-ttu-id="55e62-125">[Automatisk användning av kvarhållningsetiketter på innehåll](apply-retention-labels-automatically.md) (stöds ej för regelbaserade poster)</span><span class="sxs-lookup"><span data-stu-id="55e62-125">[Apply a retention label to content automatically](apply-retention-labels-automatically.md) (not supported for regulatory records)</span></span>


## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="55e62-126">Använda en konfigurerad kvarhållningsetikett på innehåll</span><span class="sxs-lookup"><span data-stu-id="55e62-126">Applying the configured retention label to content</span></span>

<span data-ttu-id="55e62-127">När kvarhållningsetiketter som markerar objekt som en post eller en regelbaserad post görs tillgängliga för användare som vill använda dem i appar:</span><span class="sxs-lookup"><span data-stu-id="55e62-127">When retention labels that mark items as a record or regulatory record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="55e62-128">I Exchange kan alla användare som har skrivbehörighet till postlådan använda dessa etiketter.</span><span class="sxs-lookup"><span data-stu-id="55e62-128">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="55e62-129">I SharePoint och OneDrive kan alla användare i standardmedlemsgruppen (med behörighetsnivån Delta) använda dessa etiketter.</span><span class="sxs-lookup"><span data-stu-id="55e62-129">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="55e62-130">Exempel på ett dokument som markerats som en post med hjälp av en kvarhållningsetikett:</span><span class="sxs-lookup"><span data-stu-id="55e62-130">Example of a document marked as record by using a retention label:</span></span>

![Informationsfönster för ett dokument som markerats som en post](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="55e62-132">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="55e62-132">Next steps</span></span>

<span data-ttu-id="55e62-133">En lista över fall som stöds via hantering av arkivhandlingar finns här: [Vanliga scenarier för hantering av arkivhandlingar](get-started-with-records-management.md#common-scenarios-for-records-management).</span><span class="sxs-lookup"><span data-stu-id="55e62-133">For a list of scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>