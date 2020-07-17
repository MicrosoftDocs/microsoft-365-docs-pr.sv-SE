---
title: 'Steg 2: Konfigurera klassificering för din miljö'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå och konfigurera flera olika sätt att klassificera data i din organisation.
ms.openlocfilehash: 57d4c692630826f371ea825d86fc64b959b71df2
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005816"
---
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="a2774-103">Steg 2: Konfigurera klassificering för din miljö</span><span class="sxs-lookup"><span data-stu-id="a2774-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="a2774-104">*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="a2774-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fas 6: Informationsskydd](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="a2774-106">I det här steget arbetar du med dina team för lag- och regelefterlevnad för att definiera ett klassificeringsschema för organisationens data.</span><span class="sxs-lookup"><span data-stu-id="a2774-106">In this step, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-365-classification-types"></a><span data-ttu-id="a2774-107">Klassificeringstyper för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a2774-107">Microsoft 365 classification types</span></span>

<span data-ttu-id="a2774-108">I Microsoft 365 finns fyra typer av klassificering:</span><span class="sxs-lookup"><span data-stu-id="a2774-108">Microsoft 365 includes four types of classification:</span></span>

- <span data-ttu-id="a2774-109">Typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="a2774-109">Sensitive information types</span></span>
- <span data-ttu-id="a2774-110">Kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="a2774-110">Retention labels</span></span>
- <span data-ttu-id="a2774-111">Markera som känsligt</span><span class="sxs-lookup"><span data-stu-id="a2774-111">Sensitivity labels</span></span>
- <span data-ttu-id="a2774-112">Azure Information Protection-etiketter och -skydd</span><span class="sxs-lookup"><span data-stu-id="a2774-112">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="a2774-113">Typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="a2774-113">Sensitive information types</span></span>

<span data-ttu-id="a2774-114">Känsliga informationstyper för Microsoft 365 definierar hur automatiserade processer, t. ex. sökning, ska identifiera vissa typer av information.</span><span class="sxs-lookup"><span data-stu-id="a2774-114">Sensitive information types for Microsoft 365 define how automated processes such as search recognize specific information types.</span></span> <span data-ttu-id="a2774-115">Här ingår känslig information för medarbetare eller kunder, t. ex. nummer till sjukvården och kreditkortsnummer.</span><span class="sxs-lookup"><span data-stu-id="a2774-115">These include sensitive employee or customer data such as health service numbers and credit card numbers.</span></span> <span data-ttu-id="a2774-116">Du kan använda känsliga informationstyper för att hitta känsliga data och tillämpa regler och principer för DLP (dataförlustskydd) för att skydda dessa data.</span><span class="sxs-lookup"><span data-stu-id="a2774-116">You use sensitive information types to find sensitive data and apply data loss prevention (DLP) rules and policies to protect this data.</span></span> <span data-ttu-id="a2774-117">Mer information finns i avsnittet om [vad en DLP-princip innehåller](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span><span class="sxs-lookup"><span data-stu-id="a2774-117">For more information, see [what a DLP policy contains](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span></span> 

<span data-ttu-id="a2774-118">Olika typer av känsliga uppgifter är särskilt användbara för att uppfylla kraven på efterlevnad och föreskrifter, t. ex. för den allmänna dataskyddsförordningen (GDPR).</span><span class="sxs-lookup"><span data-stu-id="a2774-118">Sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="a2774-119">Kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="a2774-119">Retention labels</span></span>

<span data-ttu-id="a2774-120">En del av att definiera en datastyrningsstrategi är att ange hur länge vissa typer av dokument eller dokument med specifikt innehåll ska behållas i enlighet med organisationens principer och regionala bestämmelser.</span><span class="sxs-lookup"><span data-stu-id="a2774-120">Part of defining a data governance strategy is deciding how long specific types of documents or documents with specific contents should be retained in compliance with organization policies and regional regulations.</span></span> <span data-ttu-id="a2774-121">Exempelvis ska vissa typer av dokument bevaras under en viss tidsperiod och sedan tas bort, och andra måste behållas för alltid.</span><span class="sxs-lookup"><span data-stu-id="a2774-121">For example, some types of documents should be retained for a set amount of time and then deleted and others must be retained indefinitely.</span></span>

<span data-ttu-id="a2774-122">För dokument som lagrats i Microsoft 365 definierar och tillämpar du kvarhållandet av etiketter för dokument och data som lagras i Exchange-e-post, SharePoint Online, OneDrive för företag och Teams-chattar och kanalmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="a2774-122">For documents stored in Microsoft 365, you define and apply retention labels to documents and data stored in Exchange email, SharePoint Online, OneDrive for Business, and Teams chat and channel messages.</span></span> 

<span data-ttu-id="a2774-123">Om du använder kvarhållningsetiketter ska du konfigurera en etikett för varje filkategori som behöver ha en tillämpad kvarhållningsprincip.</span><span class="sxs-lookup"><span data-stu-id="a2774-123">If you use retention labels, you should configure a label for each category of file that needs to have a retention policy applied.</span></span> <span data-ttu-id="a2774-124">I kvarhållningsetiketter kan du ange:</span><span class="sxs-lookup"><span data-stu-id="a2774-124">Within the retention label, you can specify:</span></span>

- <span data-ttu-id="a2774-125">En uppsättning beskrivningar för filerna (t. ex. efter företagsavdelning, filkategori eller förordning).</span><span class="sxs-lookup"><span data-stu-id="a2774-125">A set of descriptors for the files (for example, by business department, file category, or regulation).</span></span>
- <span data-ttu-id="a2774-126">Inställningarna för kvarhållande för de filer som har kvarhållningsetiketten bifogad, t. ex. kvarhållningstider och beteenden efter att kvarhållningstiden har uppnåtts.</span><span class="sxs-lookup"><span data-stu-id="a2774-126">The retention settings for the files that have the retention label attached, such as retain times and behaviors after the retain time has been reached.</span></span>

<span data-ttu-id="a2774-127">Du kan också använda en kvarhållningsetikett för filer automatiskt genom att konfigurera en SharePoint Online-webbplats för att lägga till en standardkvarhållningsetikett på alla nya dokument på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="a2774-127">You can also apply a retention label to files automatically by configuring a SharePoint Online site to apply a default retention label to all new documents in the site.</span></span> 

<span data-ttu-id="a2774-128">Mer information finns i [översikten över kvarhållningsetiketter](https://docs.microsoft.com/office365/securitycompliance/labels).</span><span class="sxs-lookup"><span data-stu-id="a2774-128">For more information, see the [overview of retention labels](https://docs.microsoft.com/office365/securitycompliance/labels).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="a2774-129">Markera som känsligt</span><span class="sxs-lookup"><span data-stu-id="a2774-129">Sensitivity labels</span></span>

<span data-ttu-id="a2774-130">En del av skyddet och implementeringen av säkerheten för vissa typer av dokument eller dokument med ett särskilt innehåll markeras med en etikett så att den ytterligare säkerheten kan användas.</span><span class="sxs-lookup"><span data-stu-id="a2774-130">Part of protecting and implementing security for specific types of documents or documents with specific contents is marking them with a label so that the additional security can be applied.</span></span> <span data-ttu-id="a2774-131">Med känslighetsetiketter i Microsoft 365 kan du göra följande:</span><span class="sxs-lookup"><span data-stu-id="a2774-131">With sensitivity labels in Microsoft 365, you can:</span></span>

- <span data-ttu-id="a2774-132">Använda skyddsinställningar som kryptering, behörigheter eller lägga till en vattenstämpel.</span><span class="sxs-lookup"><span data-stu-id="a2774-132">Enforce protection settings such as encryption, permissions, or adding a watermark.</span></span>
- <span data-ttu-id="a2774-133">Använd WIP-slutpunktsskydd (Windows Endpoint Protection) för att förhindra att innehåll kopieras till ett program från tredje part, t. ex. Twitter och Gmail, eller kopieras till flyttbara lagringsmedier, t. ex. en USB-enhet.</span><span class="sxs-lookup"><span data-stu-id="a2774-133">Use Windows Information Protection (WIP) endpoint protection to prevent that content from being copied to a third-party app, such as Twitter or Gmail, or being copied to removable storage, such as a USB drive.</span></span>
- <span data-ttu-id="a2774-134">Använd Microsoft Cloud App Security (CAS) för att skydda innehåll i program och tjänster från tredje part.</span><span class="sxs-lookup"><span data-stu-id="a2774-134">Use Microsoft Cloud App Security (CAS) to protect content in third-party apps and services.</span></span> 
- <span data-ttu-id="a2774-135">Klassificera innehåll utan att använda skyddsinställningar.</span><span class="sxs-lookup"><span data-stu-id="a2774-135">Classify content without using any protection settings.</span></span>

<span data-ttu-id="a2774-136">Om du använder känslighetsetiketter måste du konfigurera en etikett för varje säkerhets-och informationsskyddsnivå.</span><span class="sxs-lookup"><span data-stu-id="a2774-136">If you use sensitivity labels, you should configure a label for each security and information protection level.</span></span> <span data-ttu-id="a2774-137">Skapa exempelvis tre känslighetsetiketter för:</span><span class="sxs-lookup"><span data-stu-id="a2774-137">For example, create three sensitivity labels for:</span></span>

- <span data-ttu-id="a2774-138">Grundläggande</span><span class="sxs-lookup"><span data-stu-id="a2774-138">Baseline</span></span>
- <span data-ttu-id="a2774-139">Känslig</span><span class="sxs-lookup"><span data-stu-id="a2774-139">Sensitive</span></span>
- <span data-ttu-id="a2774-140">Strikt reglerad</span><span class="sxs-lookup"><span data-stu-id="a2774-140">Highly regulated</span></span>

<span data-ttu-id="a2774-141">Om du lagrar filer med strikt reglerade data i en SharePoint Online-webbplats och vill att filerna ska ha samma behörighet som webbplatsen om filerna lämnar webbplatsen måste du skapa en extra känslighetsetikett vars behörigheter är desamma som webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="a2774-141">If you store files with highly regulated data in a SharePoint Online site and want those files to have the same permissions as the site if the files leave the site, you need to create an additional sensitivity label whose permissions are the same as the site.</span></span>

<span data-ttu-id="a2774-142">Mer information finns i den här [översikten över känslighetsetiketter](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="a2774-142">For more information, see this [overview of sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="a2774-143">Azure Information Protection-etiketter och -skydd</span><span class="sxs-lookup"><span data-stu-id="a2774-143">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="a2774-144">Du kan använda Azure information Protection-etiketter för att klassificera och eventuellt skydda organisationens dokument och e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="a2774-144">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails.</span></span> <span data-ttu-id="a2774-145">Etiketterna kan användas för dokument som är lagrade utanför Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a2774-145">These labels can apply to documents that are stored outside of Microsoft 365.</span></span> <span data-ttu-id="a2774-146">De här etiketterna kan användas automatiskt av administratörer som definierar regler och villkor, manuellt av användare, eller en kombination där användarna får rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="a2774-146">These labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="a2774-147">Om du vill planera och distribuera Azure Information Protection-etiketter och -skydd gör du så här:</span><span class="sxs-lookup"><span data-stu-id="a2774-147">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="a2774-148">Granska [kraven för Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span><span class="sxs-lookup"><span data-stu-id="a2774-148">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="a2774-149">Följ [distributionsöversikten för klassificering, märkning och skydd](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span><span class="sxs-lookup"><span data-stu-id="a2774-149">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="a2774-150">Mer information finns i [biblioteket med dokumentation för Azure Information Protection](https://docs.microsoft.com/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="a2774-150">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

<span data-ttu-id="a2774-151">Befintliga etiketter för Azure Information Protection fungerar smidigt med känslighetsetiketter.</span><span class="sxs-lookup"><span data-stu-id="a2774-151">Existing Azure Information Protection labels work seamlessly with sensitivity labels.</span></span> <span data-ttu-id="a2774-152">Du kan till exempel behålla dina befintliga etiketter för Azure Information Protection och de etiketter som används i dokument och e-post.</span><span class="sxs-lookup"><span data-stu-id="a2774-152">For example, you can keep your existing Azure Information Protection labels and the labels that are applied to documents and email.</span></span>

<span data-ttu-id="a2774-153">Om du har både känslighets- och Azure Information Protection-etiketter ska du [migrera Azure Information Protection-etiketterna till känslighetsetiketter](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#sensitivity-labels-and-azure-information-protection).</span><span class="sxs-lookup"><span data-stu-id="a2774-153">If you have both sensitivity and Azure Information Protection labels, you should [migrate your Azure Information Protection labels to sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#sensitivity-labels-and-azure-information-protection).</span></span>

## <a name="example-classification-for-gdpr"></a><span data-ttu-id="a2774-154">Exempel: klassificering för GDPR</span><span class="sxs-lookup"><span data-stu-id="a2774-154">Example: Classification for GDPR</span></span>

<span data-ttu-id="a2774-155">Ett exempel på ett klassificeringsschema som innehåller personliga data för GDPR finns i [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data) (Skapa ett klassificeringsschema för personliga data).</span><span class="sxs-lookup"><span data-stu-id="a2774-155">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

## <a name="take-it-for-a-test-drive"></a><span data-ttu-id="a2774-156">Kör en provomgång</span><span class="sxs-lookup"><span data-stu-id="a2774-156">Take it for a test drive</span></span>

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="a2774-158">Testlabbguide: dataklassificering</span><span class="sxs-lookup"><span data-stu-id="a2774-158">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="a2774-159">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](infoprotect-exit-criteria.md#crit-infoprotect-step2) som motsvarar det här steget.</span><span class="sxs-lookup"><span data-stu-id="a2774-159">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step2) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="a2774-160">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="a2774-160">Next step</span></span>

|||
|:-------|:-----|
|![Steg 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="a2774-162">Konfigurera ökad säkerhet för Office 365</span><span class="sxs-lookup"><span data-stu-id="a2774-162">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

