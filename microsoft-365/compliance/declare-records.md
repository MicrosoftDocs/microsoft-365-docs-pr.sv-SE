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
ms.openlocfilehash: b5114253c99533e890d66248529b4713700b9016
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903906"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="e9abd-103">Deklarera poster med hjälp av kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="e9abd-103">Declare records by using retention labels</span></span>

><span data-ttu-id="e9abd-104">*[Licensieringsvägledning för Microsoft 365 för säkerhet och efterlevnad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="e9abd-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="e9abd-105">Om du vill deklarera dokument och e-postmeddelanden som [poster](records-management.md#records) kan du använda [kvarhållningsetiketter](retention.md#retention-labels) som markerar innehållet som en **post** eller som en **regelbaserad post**.</span><span class="sxs-lookup"><span data-stu-id="e9abd-105">To declare documents and emails as [records](records-management.md#records), you use [retention labels](retention.md#retention-labels) that mark the content as a **record** or a **regulatory record**.</span></span>

<span data-ttu-id="e9abd-106">Om du är osäker på om du bör använda en post eller en regelbaserad post kan du läsa [Jämför begränsningarna för vilka åtgärder som tillåts och blockeras](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span><span class="sxs-lookup"><span data-stu-id="e9abd-106">If you're not sure whether to use a record or a regulatory record, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span> <span data-ttu-id="e9abd-107">Om du behöver använda regelbaserade poster måste du först köra ett PowerShell-kommando enligt anvisningarna i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="e9abd-107">If you need to use regulatory records, you must first run a PowerShell command, as described in the next section.</span></span>

<span data-ttu-id="e9abd-108">Därefter kan du antingen publicera etiketterna i en policy för kvarhållningsetiketter, så att användare och administratörer kan använda dem på innehåll, eller använda automatisk användning av etiketterna på innehåll som du vill deklarera som en post (gäller etiketter som markerar objekt som poster, dock ej som regelbaserade poster).</span><span class="sxs-lookup"><span data-stu-id="e9abd-108">You can then either publish those labels in a retention label policy so that users and administrators can apply them to content, or for labels that mark items as records (but not regulatory records), auto-apply those labels to content that you want to declare a record.</span></span>

## <a name="how-to-display-the-option-to-mark-content-as-a-regulatory-record"></a><span data-ttu-id="e9abd-109">Så här visar du alternativet för att markera innehåll som en regelbaserad post</span><span class="sxs-lookup"><span data-stu-id="e9abd-109">How to display the option to mark content as a regulatory record</span></span>

>[!NOTE] 
> <span data-ttu-id="e9abd-110">Följande procedur är en granskningsbar åtgärd som medför att **Aktivering av alternativet för regelbaserade poster för kvarhållningsetiketter** loggas i avsnittet [Kvarhållningspolicy och aktiviteter gällande kvarhållningsetiketter](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities) i granskningsloggen.</span><span class="sxs-lookup"><span data-stu-id="e9abd-110">The following procedure is an auditable action, logging **Enabled regulatory record option for retention labels** in the [Retention policy and retention label activities](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities) section of the audit log.</span></span>

<span data-ttu-id="e9abd-111">Som standard visas inte alternativet för kvarhållningsetiketter, där innehåll kan markeras som en regelbaserad post, i guiden för kvarhållningsetiketter.</span><span class="sxs-lookup"><span data-stu-id="e9abd-111">By default, the retention label option to mark content as a regulatory record isn't displayed in the retention label wizard.</span></span> <span data-ttu-id="e9abd-112">Om du vill att det här alternativet ska visas måste du först köra ett PowerShell-kommando:</span><span class="sxs-lookup"><span data-stu-id="e9abd-112">To display this option, you must first run a PowerShell command:</span></span>

1. <span data-ttu-id="e9abd-113">[Anslut till Säkerhets- och efterlevnadscenter för Office 365 via PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="e9abd-113">[Connect to the Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="e9abd-114">Kör följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e9abd-114">Run the following cmdlet:</span></span>
    
    ```powershell
    Set-RegulatoryComplianceUI -Enabled $true
    ````
    <span data-ttu-id="e9abd-115">Du behöver inte bekräfta åtgärden och inställningen börjar gälla omedelbart.</span><span class="sxs-lookup"><span data-stu-id="e9abd-115">There is no prompt to confirm and the setting takes effect immediately.</span></span>

<span data-ttu-id="e9abd-116">Om du ångrar dig och inte längre vill att alternativet ska visas i guiden kan du dölja det genom att köra samma cmdlet med värdet **falskt**: `Set-RegulatoryComplianceUI -Enabled $false`</span><span class="sxs-lookup"><span data-stu-id="e9abd-116">If you change your mind about seeing this option in the retention label wizard, you can hide it again by running the same cmdlet with the **false** value: `Set-RegulatoryComplianceUI -Enabled $false`</span></span> 

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="e9abd-117">Konfigurera kvarhållningsetiketter för att deklarera poster</span><span class="sxs-lookup"><span data-stu-id="e9abd-117">Configuring retention labels to declare records</span></span>

<span data-ttu-id="e9abd-118">När du skapar en kvarhållningsetikett via lösningen **Hantering av arkivhandlingar** i Microsoft 365 Efterlevnadscenter får du möjlighet att markera objekt som poster.</span><span class="sxs-lookup"><span data-stu-id="e9abd-118">When you create a retention label from the **Records Management** solution in the Microsoft 365 compliance center, you have the option to mark items as a record.</span></span> <span data-ttu-id="e9abd-119">Om du har kört PowerShell-kommandot enligt anvisningarna i ovanstående avsnitt kan du även markera objekt som regelbaserade poster.</span><span class="sxs-lookup"><span data-stu-id="e9abd-119">If you ran the PowerShell command from the previous section, you can alternatively mark items as a regulatory record.</span></span>

<span data-ttu-id="e9abd-120">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="e9abd-120">For example:</span></span>

![Konfigurera en kvarhållningsetikett för att markera innehåll som en post eller en regelbaserad post](../media/recordversioning6.png)

<span data-ttu-id="e9abd-122">Därefter kan du vid behov använda kvarhållningsetiketten på Exchange-meddelanden eller SharePoint- och OneDrive-dokument.</span><span class="sxs-lookup"><span data-stu-id="e9abd-122">Using this retention label, you can now apply it to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> 

<span data-ttu-id="e9abd-123">Fullständiga instruktioner:</span><span class="sxs-lookup"><span data-stu-id="e9abd-123">For full instructions:</span></span>

- [<span data-ttu-id="e9abd-124">Skapa kvarhållningsetiketter och använda dem i appar</span><span class="sxs-lookup"><span data-stu-id="e9abd-124">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)

- <span data-ttu-id="e9abd-125">[Automatisk användning av kvarhållningsetiketter på innehåll](apply-retention-labels-automatically.md) (stöds ej för regelbaserade poster)</span><span class="sxs-lookup"><span data-stu-id="e9abd-125">[Apply a retention label to content automatically](apply-retention-labels-automatically.md) (not supported for regulatory records)</span></span>


## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="e9abd-126">Använda en konfigurerad kvarhållningsetikett på innehåll</span><span class="sxs-lookup"><span data-stu-id="e9abd-126">Applying the configured retention label to content</span></span>

<span data-ttu-id="e9abd-127">När kvarhållningsetiketter som markerar objekt som en post eller en regelbaserad post görs tillgängliga för användare som vill använda dem i appar:</span><span class="sxs-lookup"><span data-stu-id="e9abd-127">When retention labels that mark items as a record or regulatory record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="e9abd-128">I Exchange kan alla användare som har skrivbehörighet till postlådan använda dessa etiketter.</span><span class="sxs-lookup"><span data-stu-id="e9abd-128">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="e9abd-129">I SharePoint och OneDrive kan alla användare i standardmedlemsgruppen (med behörighetsnivån Delta) använda dessa etiketter.</span><span class="sxs-lookup"><span data-stu-id="e9abd-129">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="e9abd-130">Exempel på ett dokument som markerats som en post med hjälp av en kvarhållningsetikett:</span><span class="sxs-lookup"><span data-stu-id="e9abd-130">Example of a document marked as record by using a retention label:</span></span>

![Informationsfönster för ett dokument som markerats som en post](../media/recordversioning7.png)

## <a name="searching-the-audit-log-for-labeled-items-that-were-declared-records"></a><span data-ttu-id="e9abd-132">Söker i granskningsloggen efter märkta objekt som har deklarerats som arkivhandlingar</span><span class="sxs-lookup"><span data-stu-id="e9abd-132">Searching the audit log for labeled items that were declared records</span></span>

<span data-ttu-id="e9abd-133">Åtgärderna för att märka objekt som arkivhandlingar loggas i granskningsloggen.</span><span class="sxs-lookup"><span data-stu-id="e9abd-133">The actions of labeling to declare items as records are logged in the audit log.</span></span>

<span data-ttu-id="e9abd-134">För SharePoint-objekt:</span><span class="sxs-lookup"><span data-stu-id="e9abd-134">For SharePoint items:</span></span> 
- <span data-ttu-id="e9abd-135">Från **Fil- och sidaktiviteter** välj **Ändrad kvarhållningsetikett för en fil**.</span><span class="sxs-lookup"><span data-stu-id="e9abd-135">From **File and page activities**, select **Changed retention label for a file**.</span></span> <span data-ttu-id="e9abd-136">Den här granskningshändelsen gäller för kvarhållningsetiketter som markerar objekt som arkivhandlingar, regelposter eller som är vanliga kvarhållningsetiketter.</span><span class="sxs-lookup"><span data-stu-id="e9abd-136">This audit event is for retention labels that mark items as records, regulatory records, or that are standard retention labels.</span></span>

<span data-ttu-id="e9abd-137">För Exchange-objekt:</span><span class="sxs-lookup"><span data-stu-id="e9abd-137">For Exchange items:</span></span>
- <span data-ttu-id="e9abd-138">Från **Exchange postlåda aktiviteter** välj **Meddelandet har etiketterats som en arkivhandling**.</span><span class="sxs-lookup"><span data-stu-id="e9abd-138">From **Exchange mailbox activities**, select **Labeled message as a record**.</span></span> <span data-ttu-id="e9abd-139">Den här granskningshändelsen gäller för kvarhållningsetiketter som markerar objekt som arkivhandlingar eller regelposter.</span><span class="sxs-lookup"><span data-stu-id="e9abd-139">This audit event is for retention labels that mark items as records or regulatory records.</span></span>

<span data-ttu-id="e9abd-140">Mer information om hur du söker efter de här händelserna finns [Söka i granskningsloggen i Säkerhets- och efterlevnadscenter](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span><span class="sxs-lookup"><span data-stu-id="e9abd-140">For more information about searching for these events, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="e9abd-141">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="e9abd-141">Next steps</span></span>

<span data-ttu-id="e9abd-142">En lista över fall som stöds via hantering av arkivhandlingar finns här: [Vanliga scenarier för hantering av arkivhandlingar](get-started-with-records-management.md#common-scenarios-for-records-management).</span><span class="sxs-lookup"><span data-stu-id="e9abd-142">For a list of scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>
