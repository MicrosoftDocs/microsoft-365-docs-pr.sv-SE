---
title: Kryptering med dubbla nycklar (DKE)
description: Med DKE kan du skydda mycket känsliga data samtidigt som du behåller full kontroll över din nyckel.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 01/29/2021
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 746f1345b47694f4a4122edc5d89cc924441ea81
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/29/2021
ms.locfileid: "52162551"
---
# <a name="double-key-encryption-for-microsoft-365"></a><span data-ttu-id="2d575-103">Dubbelnyckelkryptering för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2d575-103">Double Key Encryption for Microsoft 365</span></span>

> <span data-ttu-id="2d575-104">*Gäller för: Dubbelnyckelkryptering för Microsoft 365, [Microsoft 365 efterlevnad](https://www.microsoft.com/microsoft-365/business/compliance-management), Azure [Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="2d575-104">*Applies to: Double Key Encryption for Microsoft 365, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="2d575-105">*Instruktioner för: [Azure Information Protection unified labeling client for Windows](/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="2d575-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="2d575-106">*Tjänstbeskrivning för: [Microsoft 365 regelefterlevnad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="2d575-106">*Service description for: [Microsoft 365 Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="2d575-107">DKE (Double Key Encryption) använder två nycklar tillsammans för att komma åt skyddat innehåll.</span><span class="sxs-lookup"><span data-stu-id="2d575-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="2d575-108">Microsoft lagrar en nyckel Microsoft Azure och du håller den andra nyckeln.</span><span class="sxs-lookup"><span data-stu-id="2d575-108">Microsoft stores one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="2d575-109">Du har full kontroll över en av dina nycklar med hjälp av tjänsten dubbelnyckelkryptering.</span><span class="sxs-lookup"><span data-stu-id="2d575-109">You maintain full control of one of your keys using the Double Key Encryption service.</span></span> <span data-ttu-id="2d575-110">Du tillämpar skydd med hjälp av Azure Information Protection-unified labeling-klienten för ditt känsliga innehåll.</span><span class="sxs-lookup"><span data-stu-id="2d575-110">You apply protection using The Azure Information Protection unified labeling client to your highly sensitive content.</span></span>

<span data-ttu-id="2d575-111">Dubbelnyckelkryptering har stöd för både molndistribution och lokal distribution.</span><span class="sxs-lookup"><span data-stu-id="2d575-111">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="2d575-112">De här distributionerna hjälper till att säkerställa att krypterade data förblir ogenomskinliga oavsett var du lagrar skyddade data.</span><span class="sxs-lookup"><span data-stu-id="2d575-112">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="2d575-113">Mer information om den molnbaserade klientorganisationens standardrotnycklar finns i Planera och [implementera Azure Information Protection-klientnyckeln.](/azure/information-protection/plan-implement-tenant-key)</span><span class="sxs-lookup"><span data-stu-id="2d575-113">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](/azure/information-protection/plan-implement-tenant-key).</span></span>

## <a name="when-your-organization-should-adopt-dke"></a><span data-ttu-id="2d575-114">När din organisation ska använda DKE</span><span class="sxs-lookup"><span data-stu-id="2d575-114">When your organization should adopt DKE</span></span>

<span data-ttu-id="2d575-115">Dubbelnyckelkryptering är avsedd för de känsligaste data som omfattas av de strikta skyddskraven.</span><span class="sxs-lookup"><span data-stu-id="2d575-115">Double Key Encryption is intended for your most sensitive data that is subject to the strictest protection requirements.</span></span> <span data-ttu-id="2d575-116">DKE är inte avsett för alla data.</span><span class="sxs-lookup"><span data-stu-id="2d575-116">DKE is not intended for all data.</span></span> <span data-ttu-id="2d575-117">I allmänhet använder du Dubbelnyckelkryptering för att endast skydda en liten del av dina övergripande data.</span><span class="sxs-lookup"><span data-stu-id="2d575-117">In general, you'll be using Double Key Encryption to protect only a small part of your overall data.</span></span> <span data-ttu-id="2d575-118">Du bör vara noggrann med att identifiera rätt data som ska täckas med den här lösningen innan du distribuerar.</span><span class="sxs-lookup"><span data-stu-id="2d575-118">You should do due diligence in identifying the right data to cover with this solution before you deploy.</span></span> <span data-ttu-id="2d575-119">I vissa fall kan du behöva begränsa omfattningen och använda andra lösningar för de flesta data, till exempel Microsoft Information Protection med Microsoft-hanterade nycklar eller BYOK.</span><span class="sxs-lookup"><span data-stu-id="2d575-119">In some cases, you might need to narrow your scope and make use of other solutions for most your data such as Microsoft Information Protection with Microsoft-managed keys or BYOK.</span></span> <span data-ttu-id="2d575-120">Dessa lösningar är tillräckliga för dokument som inte omfattas av förbättrade skydd och föreskrifter.</span><span class="sxs-lookup"><span data-stu-id="2d575-120">These solutions are sufficient for documents that aren't subject to enhanced protections and regulatory requirements.</span></span> <span data-ttu-id="2d575-121">De här lösningarna ger dig också möjlighet att använda de Office 365 tjänsterna. tjänster som du inte kan använda med DKE-krypterat innehåll.</span><span class="sxs-lookup"><span data-stu-id="2d575-121">Also, these solutions enable you to use the most powerful Office 365 services; services that you can't use with DKE encrypted content.</span></span> <span data-ttu-id="2d575-122">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2d575-122">For example:</span></span>

- <span data-ttu-id="2d575-123">Transportregler som skydd mot skadlig programvara och skräppost som kräver insyn i den bifogade filen</span><span class="sxs-lookup"><span data-stu-id="2d575-123">Transport rules including anti-malware and spam that require visibility into the attachment</span></span>
- <span data-ttu-id="2d575-124">Microsoft Delve</span><span class="sxs-lookup"><span data-stu-id="2d575-124">Microsoft Delve</span></span>
- <span data-ttu-id="2d575-125">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2d575-125">eDiscovery</span></span>
- <span data-ttu-id="2d575-126">Innehållssökning och indexering</span><span class="sxs-lookup"><span data-stu-id="2d575-126">Content search and indexing</span></span>
- <span data-ttu-id="2d575-127">Office Webbappar inklusive samtidiga funktioner</span><span class="sxs-lookup"><span data-stu-id="2d575-127">Office Web Apps including coauthoring functionality</span></span>

<span data-ttu-id="2d575-128">Externa program eller tjänster som inte är integrerade med DKE via MIP SDK kan inte utföra åtgärder på krypterade data.</span><span class="sxs-lookup"><span data-stu-id="2d575-128">Any external applications or services that are not integrated with DKE through the MIP SDK will be unable to perform actions on the encrypted data.</span></span>

<span data-ttu-id="2d575-129">Microsoft Information Protection SDK 1.7+ har stöd för Dubbel nyckelkryptering. program som integrerar med vårt SDK kommer att kunna använda dessa data med tillräcklig behörighet och integrering.</span><span class="sxs-lookup"><span data-stu-id="2d575-129">The Microsoft Information Protection SDK 1.7+ supports Double Key Encryption; applications that integrate with our SDK will be able to reason over this data with sufficient permissions and integrations in place.</span></span>

<span data-ttu-id="2d575-130">Vi rekommenderar att organisationer använder Microsofts informationsskyddsfunktioner (klassificering och märkning) för att skydda de flesta känsliga data och bara använda DKE för verksamhetskritiska data.</span><span class="sxs-lookup"><span data-stu-id="2d575-130">We recommend organizations use Microsoft Information protection capabilities (classification and labeling) to protect most of their sensitive data and only use DKE for their mission-critical data.</span></span> <span data-ttu-id="2d575-131">Dubbel nyckelkryptering är relevant för känsliga data i branscher som är reglerade, till exempel finansiella tjänster och sjukvård.</span><span class="sxs-lookup"><span data-stu-id="2d575-131">Double Key Encryption is relevant for sensitive data in highly regulated industries such as Financial services and Healthcare.</span></span>

<span data-ttu-id="2d575-132">Om din organisation har något av följande krav kan du använda DKE för att skydda ditt innehåll:</span><span class="sxs-lookup"><span data-stu-id="2d575-132">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="2d575-133">Du vill vara säker på *att det* bara är du som kan dekryptera skyddat innehåll under alla omständigheter.</span><span class="sxs-lookup"><span data-stu-id="2d575-133">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="2d575-134">Du vill inte att Microsoft ska ha tillgång till skyddade data på egen hand.</span><span class="sxs-lookup"><span data-stu-id="2d575-134">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="2d575-135">Du har regler som måste innehålla nycklar inom en geografisk gräns.</span><span class="sxs-lookup"><span data-stu-id="2d575-135">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="2d575-136">Alla nycklar som du håller för datakryptering och dekryptering behålls i datacentret.</span><span class="sxs-lookup"><span data-stu-id="2d575-136">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="2d575-137">System- och licenskrav för DKE</span><span class="sxs-lookup"><span data-stu-id="2d575-137">System and licensing requirements for DKE</span></span>

<span data-ttu-id="2d575-138">**Dubbel nyckelkryptering för Microsoft 365** levereras med Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="2d575-138">**Double Key Encryption for Microsoft 365** comes with Microsoft 365 E5.</span></span> <span data-ttu-id="2d575-139">Om du inte har en licens Microsoft 365 E5 kan du registrera dig för en [utvärderingsversion.](https://aka.ms/M365E5ComplianceTrial)</span><span class="sxs-lookup"><span data-stu-id="2d575-139">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="2d575-140">Mer information om licenserna finns i vägledningen [Microsoft 365 om licensiering för säkerhet och & efterlevnad.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)</span><span class="sxs-lookup"><span data-stu-id="2d575-140">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="2d575-141">**Azure Information Protection.**</span><span class="sxs-lookup"><span data-stu-id="2d575-141">**Azure Information Protection**.</span></span> <span data-ttu-id="2d575-142">DKE fungerar med känslighetsetiketter och kräver Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="2d575-142">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

<span data-ttu-id="2d575-143">DKE-känslighetsetiketter görs tillgängliga för slutanvändare via det känslighets-menyfliksområdet Office skrivbordsappar.</span><span class="sxs-lookup"><span data-stu-id="2d575-143">DKE sensitivity labels are made available to end users through the sensitivity ribbon in Office Desktop Apps.</span></span> <span data-ttu-id="2d575-144">Installera de här förutsättningarna på varje klientdator där du vill skydda och använda skyddade dokument.</span><span class="sxs-lookup"><span data-stu-id="2d575-144">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="2d575-145">**Microsoft Office Program för företag** version 2009 eller senare (skrivbordsversioner av Word, PowerPoint och Excel) på Windows.</span><span class="sxs-lookup"><span data-stu-id="2d575-145">**Microsoft Office Apps for enterprise** version 2009 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

<span data-ttu-id="2d575-146">**Azure Information Protection Unified Labeling Client** version 2.7.93.0 eller senare.</span><span class="sxs-lookup"><span data-stu-id="2d575-146">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="2d575-147">Ladda ned och installera unified Labeling-klienten från [Microsoft Download Center.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="2d575-147">Download and install the Unified Labeling client from the [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="2d575-148">Miljöer som stöds för lagring och visning av DKE-skyddat innehåll</span><span class="sxs-lookup"><span data-stu-id="2d575-148">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="2d575-149">**Program som stöds.**</span><span class="sxs-lookup"><span data-stu-id="2d575-149">**Supported applications**.</span></span> <span data-ttu-id="2d575-150">[Microsoft 365-appar för företag](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) klienter på Windows, till exempel Word, Excel och PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="2d575-150">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="2d575-151">**Stöd för onlineinnehåll.**</span><span class="sxs-lookup"><span data-stu-id="2d575-151">**Online content support**.</span></span> <span data-ttu-id="2d575-152">Du kan lagra dokument och filer som skyddas med Dubbel nyckelkryptering online i både Microsoft SharePoint och OneDrive för företag.</span><span class="sxs-lookup"><span data-stu-id="2d575-152">You can store documents and files protected with Double Key Encryption online in both Microsoft SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="2d575-153">Du måste märka och skydda dokument och filer med DKE av program som stöds innan du laddar upp till dessa platser.</span><span class="sxs-lookup"><span data-stu-id="2d575-153">You must label and protect documents and files with DKE by supported applications before you upload to these locations.</span></span> <span data-ttu-id="2d575-154">Du kan dela krypterat innehåll via e-post, men du kan inte visa krypterade dokument och filer online.</span><span class="sxs-lookup"><span data-stu-id="2d575-154">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="2d575-155">I stället måste du visa skyddat innehåll med de skrivbordsprogram och klienter som stöds på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="2d575-155">Instead, you must view protected content using the supported desktop applications and clients on your local computer.</span></span>

## <a name="overview-of-deploying-dke"></a><span data-ttu-id="2d575-156">Översikt över distribution av DKE</span><span class="sxs-lookup"><span data-stu-id="2d575-156">Overview of deploying DKE</span></span>

<span data-ttu-id="2d575-157">Du följer de här allmänna anvisningarna för att konfigurera DKE.</span><span class="sxs-lookup"><span data-stu-id="2d575-157">You'll follow these general steps to set up DKE.</span></span> <span data-ttu-id="2d575-158">När du har utfört de här stegen kan slutanvändarna skydda känslig information med Dubbelnyckelkryptering.</span><span class="sxs-lookup"><span data-stu-id="2d575-158">Once you've completed these steps, your end users will can protect your highly sensitive data with Double Key Encryption.</span></span>

1. <span data-ttu-id="2d575-159">Distribuera DKE-tjänsten enligt beskrivningen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="2d575-159">Deploy the DKE service as described in this article.</span></span>

2. <span data-ttu-id="2d575-160">Skapa en etikett med Dubbelnyckelkryptering.</span><span class="sxs-lookup"><span data-stu-id="2d575-160">Create a label with Double Key Encryption.</span></span> <span data-ttu-id="2d575-161">Gå till Informationsskydd under [kompatibilitetscentret Microsoft 365 och](https://compliance.microsoft.com) skapa en ny etikett med Dubbelnyckelkryptering.</span><span class="sxs-lookup"><span data-stu-id="2d575-161">Navigate to Information protection under the [Microsoft 365 compliance center](https://compliance.microsoft.com) and create a new label with Double Key Encryption.</span></span> <span data-ttu-id="2d575-162">Läs [Begränsa åtkomst till innehåll genom att använda känslighetsetiketter för att tillämpa kryptering.](./encryption-sensitivity-labels.md)</span><span class="sxs-lookup"><span data-stu-id="2d575-162">See [Restrict access to content by using sensitivity labels to apply encryption](./encryption-sensitivity-labels.md).</span></span>

3. <span data-ttu-id="2d575-163">Använd etiketter för dubbelnyckelkryptering.</span><span class="sxs-lookup"><span data-stu-id="2d575-163">Use Double Key Encryption labels.</span></span> <span data-ttu-id="2d575-164">Skydda data genom att välja etiketten Dubbelnyckelkrypterad i menyfliksområdet Känslighet i Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="2d575-164">Protect data by selecting the Double Key Encrypted label from the Sensitivity ribbon in Microsoft Office.</span></span>

<span data-ttu-id="2d575-165">Det finns flera sätt att utföra några av stegen för att distribuera dubbelnyckelkryptering.</span><span class="sxs-lookup"><span data-stu-id="2d575-165">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="2d575-166">Den här artikeln innehåller detaljerade anvisningar så att mindre erfarna administratörer kan distribuera tjänsten.</span><span class="sxs-lookup"><span data-stu-id="2d575-166">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="2d575-167">Om du känner dig bekväm med det kan du välja att använda dina egna metoder.</span><span class="sxs-lookup"><span data-stu-id="2d575-167">If you're comfortable doing so, you can choose to use your own methods.</span></span>

## <a name="deploy-dke"></a><span data-ttu-id="2d575-168">Distribuera DKE</span><span class="sxs-lookup"><span data-stu-id="2d575-168">Deploy DKE</span></span>

<span data-ttu-id="2d575-169">I den här artikeln och videon om distribution används Azure som distributionsdestination för DKE-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="2d575-169">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="2d575-170">Om du distribuerar till en annan plats måste du ange egna värden.</span><span class="sxs-lookup"><span data-stu-id="2d575-170">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="2d575-171">Titta på [videon om distribution med dubbel nyckelkryptering](https://youtu.be/vDWfHN_kygg) om du vill se en steg-för-steg-översikt över begreppen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="2d575-171">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see a step-by-step overview of the concepts in this article.</span></span> <span data-ttu-id="2d575-172">Videon tar ca 18 minuter att slutföra.</span><span class="sxs-lookup"><span data-stu-id="2d575-172">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="2d575-173">Du följer de här allmänna anvisningarna för att konfigurera Dubbelnyckelkryptering för din organisation.</span><span class="sxs-lookup"><span data-stu-id="2d575-173">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="2d575-174">Installera programvaruförutsättningarna för DKE-tjänsten</span><span class="sxs-lookup"><span data-stu-id="2d575-174">Install software prerequisites for the DKE service</span></span>](#install-software-prerequisites-for-the-dke-service)
1. [<span data-ttu-id="2d575-175">Klona dubbelnyckelkrypteringsplatsen GitHub krypteringsplatsen</span><span class="sxs-lookup"><span data-stu-id="2d575-175">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="2d575-176">Ändra programinställningar</span><span class="sxs-lookup"><span data-stu-id="2d575-176">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="2d575-177">Generera testnycklar</span><span class="sxs-lookup"><span data-stu-id="2d575-177">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="2d575-178">Skapa projektet</span><span class="sxs-lookup"><span data-stu-id="2d575-178">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="2d575-179">Distribuera DKE-tjänsten och publicera nyckelarkivet</span><span class="sxs-lookup"><span data-stu-id="2d575-179">Deploy the DKE service and publish the key store</span></span>](#deploy-the-dke-service-and-publish-the-key-store)
1. [<span data-ttu-id="2d575-180">Validera din distribution</span><span class="sxs-lookup"><span data-stu-id="2d575-180">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="2d575-181">Registrera din nyckelbutik</span><span class="sxs-lookup"><span data-stu-id="2d575-181">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="2d575-182">Skapa känslighetsetiketter med DKE</span><span class="sxs-lookup"><span data-stu-id="2d575-182">Create sensitivity labels using DKE</span></span>](#create-sensitivity-labels-using-dke)
1. [<span data-ttu-id="2d575-183">Aktivera DKE i klienten</span><span class="sxs-lookup"><span data-stu-id="2d575-183">Enable DKE in your client</span></span>](#enable-dke-in-your-client)
1. [<span data-ttu-id="2d575-184">Migrera skyddade filer från HYOK-etiketter till DKE-etiketter</span><span class="sxs-lookup"><span data-stu-id="2d575-184">Migrate protected files from HYOK labels to DKE labels</span></span>](#migrate-protected-files-from-hyok-labels-to-dke-labels)

<span data-ttu-id="2d575-185">När du är klar kan du kryptera dokument och filer med DKE.</span><span class="sxs-lookup"><span data-stu-id="2d575-185">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="2d575-186">Mer information finns i [Använda känslighetsetiketter för dina filer och e-post i Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span><span class="sxs-lookup"><span data-stu-id="2d575-186">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites-for-the-dke-service"></a><span data-ttu-id="2d575-187">Installera programvaruförutsättningarna för DKE-tjänsten</span><span class="sxs-lookup"><span data-stu-id="2d575-187">Install software prerequisites for the DKE service</span></span>

<span data-ttu-id="2d575-188">Installera de här förutsättningarna på den dator där du vill installera DKE-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="2d575-188">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="2d575-189">**.NET Core 3.1 SDK.**</span><span class="sxs-lookup"><span data-stu-id="2d575-189">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="2d575-190">Ladda ned och installera SDK från [Ladda ned .NET Core 3.1.](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="2d575-190">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="2d575-191">**Visual Studio kod**.</span><span class="sxs-lookup"><span data-stu-id="2d575-191">**Visual Studio Code**.</span></span> <span data-ttu-id="2d575-192">Ladda Visual Studio kod från [https://code.visualstudio.com/](https://code.visualstudio.com) .</span><span class="sxs-lookup"><span data-stu-id="2d575-192">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="2d575-193">När du är installerad kör Visual Studio kod och väljer **Visa** \> **tillägg.**</span><span class="sxs-lookup"><span data-stu-id="2d575-193">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="2d575-194">Installera de här tilläggen.</span><span class="sxs-lookup"><span data-stu-id="2d575-194">Install these extensions.</span></span>

- <span data-ttu-id="2d575-195">C# för Visual Studio kod</span><span class="sxs-lookup"><span data-stu-id="2d575-195">C# for Visual Studio Code</span></span>

- <span data-ttu-id="2d575-196">NuGet Package Manager</span><span class="sxs-lookup"><span data-stu-id="2d575-196">NuGet Package Manager</span></span>

<span data-ttu-id="2d575-197">**Git-resurser**.</span><span class="sxs-lookup"><span data-stu-id="2d575-197">**Git resources**.</span></span> <span data-ttu-id="2d575-198">Ladda ned och installera något av följande.</span><span class="sxs-lookup"><span data-stu-id="2d575-198">Download and install one of the following.</span></span>

- [<span data-ttu-id="2d575-199">Git</span><span class="sxs-lookup"><span data-stu-id="2d575-199">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="2d575-200">GitHub Skrivbord</span><span class="sxs-lookup"><span data-stu-id="2d575-200">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="2d575-201">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="2d575-201">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="2d575-202">**OpenSSL** Du måste ha [OpenSSL installerat](https://slproweb.com/products/Win32OpenSSL.html) för att [generera testnycklar när](#generate-test-keys) du har distribuerat DKE.</span><span class="sxs-lookup"><span data-stu-id="2d575-202">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="2d575-203">Kontrollera att du använder den på rätt sätt från sökvägen med miljövariabler.</span><span class="sxs-lookup"><span data-stu-id="2d575-203">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="2d575-204">Mer information finns i "Lägga till installationskatalogen i [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) PATH".</span><span class="sxs-lookup"><span data-stu-id="2d575-204">For example, see "Add the installation directory to PATH" at [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) for details.</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="2d575-205">Klona DKE-GitHub lagringsplatsen</span><span class="sxs-lookup"><span data-stu-id="2d575-205">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="2d575-206">Microsoft tillhandahåller DKE-källfilerna på en GitHub lagringsplats.</span><span class="sxs-lookup"><span data-stu-id="2d575-206">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="2d575-207">Du klonar lagringsplatsen för att skapa projektet lokalt för din organisations användning.</span><span class="sxs-lookup"><span data-stu-id="2d575-207">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="2d575-208">Lagringsplatsen för GitHub finns vid [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="2d575-208">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="2d575-209">Följande anvisningar är avsedda för oerfarna git eller Visual Studio kodanvändare:</span><span class="sxs-lookup"><span data-stu-id="2d575-209">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="2d575-210">Öppna webbläsaren och gå till: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="2d575-210">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

2. <span data-ttu-id="2d575-211">Välj Kod till höger på **skärmen.**</span><span class="sxs-lookup"><span data-stu-id="2d575-211">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="2d575-212">Din version av användargränssnittet kan visa knappen **Klona eller ladda** ned.</span><span class="sxs-lookup"><span data-stu-id="2d575-212">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="2d575-213">I den nedrullningsbara listrutan som visas väljer du ikonen Kopiera för att kopiera URL-adressen till Urklipp.</span><span class="sxs-lookup"><span data-stu-id="2d575-213">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="2d575-214">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2d575-214">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2d575-215">![Klona tjänsten dubbelnyckelkryptering från GitHub](../media/dke-clone.png)</span><span class="sxs-lookup"><span data-stu-id="2d575-215">![Clone the Double Key Encryption service repository from GitHub](../media/dke-clone.png)</span></span>

3. <span data-ttu-id="2d575-216">I Visual Studio väljer du  Visa \> **kommandopalett och** **sedan Git: Klona**.</span><span class="sxs-lookup"><span data-stu-id="2d575-216">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="2d575-217">Om du vill gå till alternativet i listan börjar du skriva för att `git: clone` filtrera posterna och väljer det i listrutan.</span><span class="sxs-lookup"><span data-stu-id="2d575-217">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="2d575-218">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2d575-218">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2d575-219">![Visual Studio Kod GIT:alternativet Klona](../media/dke-vscode-clone.png)</span><span class="sxs-lookup"><span data-stu-id="2d575-219">![Visual Studio Code GIT:Clone option](../media/dke-vscode-clone.png)</span></span>

4. <span data-ttu-id="2d575-220">I textrutan klistrar du in webbadressen du kopierade från Git och väljer **Klona från GitHub**.</span><span class="sxs-lookup"><span data-stu-id="2d575-220">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="2d575-221">I dialogrutan **Välj mapp** som visas bläddrar du till och väljer en plats där du vill lagra lagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="2d575-221">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="2d575-222">Välj Öppna när du **uppmanas att göra det.**</span><span class="sxs-lookup"><span data-stu-id="2d575-222">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="2d575-223">Lagringsplatsen öppnas Visual Studio kod och visar den aktuella Git-grenen längst ned till vänster.</span><span class="sxs-lookup"><span data-stu-id="2d575-223">The repository opens in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="2d575-224">Grenen ska till exempel vara **huvud.**</span><span class="sxs-lookup"><span data-stu-id="2d575-224">For example,  The branch should be **main**.</span></span> <span data-ttu-id="2d575-225">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2d575-225">For example:</span></span>

   ![Skärmbild av DKE-lagringsplatsen Visual Studio kod som visar huvudgrenen](../media/dke-vscode-main-branch.jpg)

6. <span data-ttu-id="2d575-227">Om du inte är i huvudgrenen måste du välja den.</span><span class="sxs-lookup"><span data-stu-id="2d575-227">If you're not on the main branch, you'll need to select it.</span></span> <span data-ttu-id="2d575-228">I Visual Studio väljer du grenen och väljer **huvud i** listan med filialer som visas.</span><span class="sxs-lookup"><span data-stu-id="2d575-228">In Visual Studio Code, select the branch and choose **main** from the list of branches that displays.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="2d575-229">Genom att välja huvudgren ser du till att du har rätt filer för att skapa projektet.</span><span class="sxs-lookup"><span data-stu-id="2d575-229">Selecting the main branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="2d575-230">Om du inte väljer rätt gren kommer distributionen att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="2d575-230">If you don't choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="2d575-231">Du har nu din DKE-källdatabas konfigurerad lokalt.</span><span class="sxs-lookup"><span data-stu-id="2d575-231">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="2d575-232">Ändra sedan [programinställningarna](#modify-application-settings) för din organisation.</span><span class="sxs-lookup"><span data-stu-id="2d575-232">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="2d575-233">Ändra programinställningar</span><span class="sxs-lookup"><span data-stu-id="2d575-233">Modify application settings</span></span>

<span data-ttu-id="2d575-234">Du måste ändra följande typer av programinställningar för att distribuera DKE-tjänsten:</span><span class="sxs-lookup"><span data-stu-id="2d575-234">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="2d575-235">Inställningar för tangentåtkomst</span><span class="sxs-lookup"><span data-stu-id="2d575-235">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="2d575-236">Inställningar för klientorganisation och nyckel</span><span class="sxs-lookup"><span data-stu-id="2d575-236">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="2d575-237">Du ändrar programinställningarna i det appsettings.jsfilen.</span><span class="sxs-lookup"><span data-stu-id="2d575-237">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="2d575-238">Den här filen finns på den DoubleKeyEncryptionService-lagringsplatsen som du klonade lokalt under DoubleKeyEncryptionService\src\customer-key-store.</span><span class="sxs-lookup"><span data-stu-id="2d575-238">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="2d575-239">I Visual Studio kan du till exempel bläddra till filen som på bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="2d575-239">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![Hitta filen appsettings.jsför DKE.](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="2d575-241">Inställningar för tangentåtkomst</span><span class="sxs-lookup"><span data-stu-id="2d575-241">Key access settings</span></span>

<span data-ttu-id="2d575-242">Välj om du vill använda e-post eller rollauktorisering.</span><span class="sxs-lookup"><span data-stu-id="2d575-242">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="2d575-243">DKE stöder endast en av dessa autentiseringsmetoder i taget.</span><span class="sxs-lookup"><span data-stu-id="2d575-243">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="2d575-244">**E-postauktorisering**.</span><span class="sxs-lookup"><span data-stu-id="2d575-244">**Email authorization**.</span></span> <span data-ttu-id="2d575-245">Gör att din organisation kan auktorisera åtkomst till nycklar endast baserat på e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="2d575-245">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="2d575-246">**Rollauktorisering**.</span><span class="sxs-lookup"><span data-stu-id="2d575-246">**Role authorization**.</span></span> <span data-ttu-id="2d575-247">Ger organisationen behörighet att auktorisera åtkomst till nycklar baserat på Active Directory-grupper och kräver att webbtjänsten kan köra frågor för LDAP.</span><span class="sxs-lookup"><span data-stu-id="2d575-247">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="2d575-248">**Så här anger du tangentåtkomstinställningar för DKE med e-postauktorisering**</span><span class="sxs-lookup"><span data-stu-id="2d575-248">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="2d575-249">Öppna **filenappsettings.js** filen och leta reda på `AuthorizedEmailAddress` inställningen.</span><span class="sxs-lookup"><span data-stu-id="2d575-249">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="2d575-250">Lägg till den e-postadress eller de adresser som du vill auktorisera.</span><span class="sxs-lookup"><span data-stu-id="2d575-250">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="2d575-251">Avgränsa flera e-postadresser med dubbla citattecken och kommatecken.</span><span class="sxs-lookup"><span data-stu-id="2d575-251">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="2d575-252">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2d575-252">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="2d575-253">Leta reda `LDAPPath` på inställningen och ta bort texten mellan `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` citattecken.</span><span class="sxs-lookup"><span data-stu-id="2d575-253">Locate the `LDAPPath` setting and remove the text `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` between the double quotes.</span></span> <span data-ttu-id="2d575-254">Låt de dubbla citattförfrågningarna vara kvar.</span><span class="sxs-lookup"><span data-stu-id="2d575-254">Leave the double quotes in place.</span></span> <span data-ttu-id="2d575-255">När du är klar bör inställningen se ut så här.</span><span class="sxs-lookup"><span data-stu-id="2d575-255">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="2d575-256">Leta reda `AuthorizedRoles` på inställningen och ta bort hela raden.</span><span class="sxs-lookup"><span data-stu-id="2d575-256">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="2d575-257">Den här bilden visar filen **appsettings.jskorrekt formaterad** för e-postauktorisering.</span><span class="sxs-lookup"><span data-stu-id="2d575-257">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![Filen appsettings.jssom visar e-postauktoriseringsmetod](../media/dke-email-accesssetting.png)

<span data-ttu-id="2d575-259">**Så här anger du nyckelåtkomstinställningar för DKE med rollauktorisering**</span><span class="sxs-lookup"><span data-stu-id="2d575-259">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="2d575-260">Öppna **filenappsettings.js** filen och leta reda på `AuthorizedRoles` inställningen.</span><span class="sxs-lookup"><span data-stu-id="2d575-260">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="2d575-261">Lägg till de Active Directory-gruppnamn som du vill auktorisera.</span><span class="sxs-lookup"><span data-stu-id="2d575-261">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="2d575-262">Avgränsa flera gruppnamn med dubbla citattecken och kommatecken.</span><span class="sxs-lookup"><span data-stu-id="2d575-262">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="2d575-263">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2d575-263">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="2d575-264">Leta reda `LDAPPath` på inställningen och lägg till Active Directory-domänen.</span><span class="sxs-lookup"><span data-stu-id="2d575-264">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="2d575-265">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2d575-265">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="2d575-266">Leta reda `AuthorizedEmailAddress` på inställningen och ta bort hela raden.</span><span class="sxs-lookup"><span data-stu-id="2d575-266">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="2d575-267">I den här bilden **appsettings.jsfilen** är korrekt formaterad för rollauktorisering.</span><span class="sxs-lookup"><span data-stu-id="2d575-267">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![appsettings.jsfil som visar rollauktoriseringsmetod](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="2d575-269">Inställningar för klientorganisation och nyckel</span><span class="sxs-lookup"><span data-stu-id="2d575-269">Tenant and key settings</span></span>

<span data-ttu-id="2d575-270">Klientorganisation och nyckelinställningar för DKE finns i **filenappsettings.jsfilen.**</span><span class="sxs-lookup"><span data-stu-id="2d575-270">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="2d575-271">**Så här konfigurerar du klientorganisations- och nyckelinställningar för DKE**</span><span class="sxs-lookup"><span data-stu-id="2d575-271">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="2d575-272">Öppna **filenappsettings.jsfilen.**</span><span class="sxs-lookup"><span data-stu-id="2d575-272">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="2d575-273">Leta reda på `ValidIssuers` inställningen och ersätt med ditt `<tenantid>` klientorganisations-ID.</span><span class="sxs-lookup"><span data-stu-id="2d575-273">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="2d575-274">Du kan hitta ditt klient-ID genom att gå till Azure-portalen och visa [klientorganisationens egenskaper.](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)</span><span class="sxs-lookup"><span data-stu-id="2d575-274">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="2d575-275">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2d575-275">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```
> [!NOTE]
> <span data-ttu-id="2d575-276">Om du vill aktivera extern B2B-åtkomst till nyckelarkivet måste du också inkludera dessa externa innehavare som en del av listan över giltiga utfärdare.</span><span class="sxs-lookup"><span data-stu-id="2d575-276">If you want to enable external B2B access to your key store, you will also need to include these external tenants as part of the valid issuers' list.</span></span>

<span data-ttu-id="2d575-277">Leta reda på `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="2d575-277">Locate the `JwtAudience`.</span></span> <span data-ttu-id="2d575-278">Ersätt `<yourhostname>` med värdnamnet för den dator där DKE-tjänsten körs.</span><span class="sxs-lookup"><span data-stu-id="2d575-278">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="2d575-279">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2d575-279">For example:</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="2d575-280">Värdet för måste `JwtAudience` matcha värdens namn *exakt.*</span><span class="sxs-lookup"><span data-stu-id="2d575-280">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="2d575-281">Du kan använda **localhost:5001** när du felsöker.</span><span class="sxs-lookup"><span data-stu-id="2d575-281">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="2d575-282">Men när du är klar med felsökningen måste du uppdatera det här värdet till serverns värdnamn.</span><span class="sxs-lookup"><span data-stu-id="2d575-282">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="2d575-283">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="2d575-283">`TestKeys:Name`.</span></span> <span data-ttu-id="2d575-284">Ange ett namn på nyckeln.</span><span class="sxs-lookup"><span data-stu-id="2d575-284">Enter a name for your key.</span></span> <span data-ttu-id="2d575-285">Till exempel: `TestKey1`</span><span class="sxs-lookup"><span data-stu-id="2d575-285">For example: `TestKey1`</span></span>
- <span data-ttu-id="2d575-286">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="2d575-286">`TestKeys:Id`.</span></span> <span data-ttu-id="2d575-287">Skapa ett GUID och ange det som `TestKeys:ID` värde.</span><span class="sxs-lookup"><span data-stu-id="2d575-287">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="2d575-288">Till exempel `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span><span class="sxs-lookup"><span data-stu-id="2d575-288">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="2d575-289">Du kan använda en webbplats som [Online GUID Generator för](https://guidgenerator.com/) att slumpmässigt generera en GUID.</span><span class="sxs-lookup"><span data-stu-id="2d575-289">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="2d575-290">Den här bilden visar rätt format för inställningar för klientorganisation och nycklar **appsettings.jspå**.</span><span class="sxs-lookup"><span data-stu-id="2d575-290">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="2d575-291">`LDAPPath` har konfigurerats för rollauktorisering.</span><span class="sxs-lookup"><span data-stu-id="2d575-291">`LDAPPath` is configured for role authorization.</span></span>

![Visar rätt inställningar för klientorganisation och nyckel för DKE i filen appsettings.jspå filen.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="2d575-293">Generera testnycklar</span><span class="sxs-lookup"><span data-stu-id="2d575-293">Generate test keys</span></span>

<span data-ttu-id="2d575-294">När du har definierat dina programinställningar är du redo att skapa offentliga och privata testnycklar.</span><span class="sxs-lookup"><span data-stu-id="2d575-294">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="2d575-295">Så här skapar du nycklar:</span><span class="sxs-lookup"><span data-stu-id="2d575-295">To generate keys:</span></span>

1. <span data-ttu-id="2d575-296">I Windows På Start-menyn kör du Kommandotolken i OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="2d575-296">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

2. <span data-ttu-id="2d575-297">Byt till den mapp där du vill spara testnycklarna.</span><span class="sxs-lookup"><span data-stu-id="2d575-297">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="2d575-298">Filer som du skapar genom att utföra stegen i uppgiften lagras i samma mapp.</span><span class="sxs-lookup"><span data-stu-id="2d575-298">The files you create by completing the steps in this task are stored in the same folder.</span></span>

3. <span data-ttu-id="2d575-299">Generera den nya testnyckeln.</span><span class="sxs-lookup"><span data-stu-id="2d575-299">Generate the new test key.</span></span>

   ```console
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. <span data-ttu-id="2d575-300">Generera den privata nyckeln.</span><span class="sxs-lookup"><span data-stu-id="2d575-300">Generate the private key.</span></span>

   ```console
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. <span data-ttu-id="2d575-301">Generera den offentliga nyckeln.</span><span class="sxs-lookup"><span data-stu-id="2d575-301">Generate the public key.</span></span>

   ```console
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. <span data-ttu-id="2d575-302">I en textredigerare öppnar **du pubkeyonly.pem**.</span><span class="sxs-lookup"><span data-stu-id="2d575-302">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="2d575-303">Kopiera allt innehåll i filen **pubkeyonly.pem,** förutom den första och den sista raderna, till avsnittet i `PublicPem` filenappsettings.js **på.**</span><span class="sxs-lookup"><span data-stu-id="2d575-303">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

7. <span data-ttu-id="2d575-304">Öppna **privkeynopass.pem** i en textredigerare.</span><span class="sxs-lookup"><span data-stu-id="2d575-304">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="2d575-305">Kopiera allt innehåll i **filen privkeynopass.pem,** förutom den första och sista raderna, till den delen av `PrivatePem` filenappsettings.js **filen.**</span><span class="sxs-lookup"><span data-stu-id="2d575-305">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

8. <span data-ttu-id="2d575-306">Ta bort alla tomma utrymmen och nya rader i både `PublicPem` avsnitt `PrivatePem` och.</span><span class="sxs-lookup"><span data-stu-id="2d575-306">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2d575-307">När du kopierar det här innehållet ska du inte ta bort några PEM-data.</span><span class="sxs-lookup"><span data-stu-id="2d575-307">When you copy this content, do not delete any of the PEM data.</span></span>

9. <span data-ttu-id="2d575-308">Bläddra Visual Studio.cs-filen i **Kod.**</span><span class="sxs-lookup"><span data-stu-id="2d575-308">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="2d575-309">Den här filen finns på den DoubleKeyEncryptionService-lagringsplatsen som du klonade lokalt under DoubleKeyEncryptionService\src\customer-key-store\.</span><span class="sxs-lookup"><span data-stu-id="2d575-309">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

10. <span data-ttu-id="2d575-310">Leta upp följande rader:</span><span class="sxs-lookup"><span data-stu-id="2d575-310">Locate the following lines:</span></span>

    ```csharp
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
    ```

11. <span data-ttu-id="2d575-311">Ersätt dessa rader med följande text:</span><span class="sxs-lookup"><span data-stu-id="2d575-311">Replace these lines with the following text:</span></span>

    ```csharp
    services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
    ```

    <span data-ttu-id="2d575-312">Resultatet bör se ut ungefär så här.</span><span class="sxs-lookup"><span data-stu-id="2d575-312">The end results should look similar to the following.</span></span>

    ![startup.cs-fil för offentlig förhandsgranskning](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="2d575-314">Nu är du redo att [skapa ditt DKE-projekt](#build-the-project).</span><span class="sxs-lookup"><span data-stu-id="2d575-314">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="2d575-315">Skapa projektet</span><span class="sxs-lookup"><span data-stu-id="2d575-315">Build the project</span></span>

<span data-ttu-id="2d575-316">Använd följande anvisningar för att skapa DKE-projektet lokalt:</span><span class="sxs-lookup"><span data-stu-id="2d575-316">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="2d575-317">I Visual Studio kod i DKE-tjänstens lagringsplats väljer du **Visa kommandopalett** och skriver sedan version när du \>  uppmanas att göra  det.</span><span class="sxs-lookup"><span data-stu-id="2d575-317">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

2. <span data-ttu-id="2d575-318">I listan väljer du **Uppgifter: Kör build-uppgift**.</span><span class="sxs-lookup"><span data-stu-id="2d575-318">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="2d575-319">Om inga build-uppgifter hittas väljer du **Konfigurera build-uppgift** och skapar en för .NET-kärnuppgifterna på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="2d575-319">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![Konfigurera uppgiften för saknad version för .NET](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="2d575-321">Välj **Skapa tasks.jsfrån mall**.</span><span class="sxs-lookup"><span data-stu-id="2d575-321">Choose **Create tasks.json from template**.</span></span>

      ![Skapa tasks.jsfrån en mall för DKE](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="2d575-323">Välj .NET Core i listan **över malltyper.**</span><span class="sxs-lookup"><span data-stu-id="2d575-323">From the list of template types, select **.NET Core**.</span></span>

      ![Välj rätt mall för DKE](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="2d575-325">Leta reda på sökvägen till filen **customerkeystore.csproj** i build-avsnittet.</span><span class="sxs-lookup"><span data-stu-id="2d575-325">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="2d575-326">Om den inte visas lägger du till följande rad:</span><span class="sxs-lookup"><span data-stu-id="2d575-326">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. <span data-ttu-id="2d575-327">Kör versionen igen.</span><span class="sxs-lookup"><span data-stu-id="2d575-327">Run the build again.</span></span>

3. <span data-ttu-id="2d575-328">Kontrollera att det inte finns några röda fel i utdatafönstret.</span><span class="sxs-lookup"><span data-stu-id="2d575-328">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="2d575-329">Om det finns röda fel kontrollerar du konsolens utdata.</span><span class="sxs-lookup"><span data-stu-id="2d575-329">If there are red errors, check the console output.</span></span> <span data-ttu-id="2d575-330">Kontrollera att du har slutfört alla tidigare steg korrekt och att rätt versionsversioner finns.</span><span class="sxs-lookup"><span data-stu-id="2d575-330">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

4. <span data-ttu-id="2d575-331">Välj **Kör** \> **Starta felsökning för** att felsöka processen.</span><span class="sxs-lookup"><span data-stu-id="2d575-331">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="2d575-332">Om du uppmanas att välja en miljö väljer du **.NET core**.</span><span class="sxs-lookup"><span data-stu-id="2d575-332">If you're prompted to select an environment, select **.NET core**.</span></span>

   <span data-ttu-id="2d575-333">.NET core debugger startar vanligtvis på `https://localhost:5001` .</span><span class="sxs-lookup"><span data-stu-id="2d575-333">The .NET core debugger typically launches to `https://localhost:5001`.</span></span> <span data-ttu-id="2d575-334">Du visar testtangenten genom att gå till `https://localhost:5001` och lägga till ett snedstreck (/) och namnet på tangenten.</span><span class="sxs-lookup"><span data-stu-id="2d575-334">To view your test key, go to `https://localhost:5001` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="2d575-335">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2d575-335">For example:</span></span>

   ```https
   https://localhost:5001/TestKey1
   ```

   <span data-ttu-id="2d575-336">Nyckeln ska visas i JSON-format.</span><span class="sxs-lookup"><span data-stu-id="2d575-336">The key should display in JSON format.</span></span>

<span data-ttu-id="2d575-337">Konfigurationen är nu klar.</span><span class="sxs-lookup"><span data-stu-id="2d575-337">Your setup is now complete.</span></span> <span data-ttu-id="2d575-338">Innan du publicerar nyckelstore ska du, i appsettings.jspå, se till att värdet för värdnamn matchar programtjänstens värdnamn exakt.</span><span class="sxs-lookup"><span data-stu-id="2d575-338">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="2d575-339">Du kan ha ändrat det till localhost för att felsöka versionen.</span><span class="sxs-lookup"><span data-stu-id="2d575-339">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a><span data-ttu-id="2d575-340">Distribuera DKE-tjänsten och publicera nyckelarkivet</span><span class="sxs-lookup"><span data-stu-id="2d575-340">Deploy the DKE service and publish the key store</span></span>

<span data-ttu-id="2d575-341">För produktionsdistributioner distribuerar du tjänsten i ett tredjepartsmoln [eller publicerar på ett lokalt system.](/aspnet/core/tutorials/publish-to-iis?preserve-view=true&tabs=netcore-cli&view=aspnetcore-3.1)</span><span class="sxs-lookup"><span data-stu-id="2d575-341">For production deployments, deploy the service either in a third-party cloud or [publish to an on-premises system](/aspnet/core/tutorials/publish-to-iis?preserve-view=true&tabs=netcore-cli&view=aspnetcore-3.1).</span></span>

<span data-ttu-id="2d575-342">Du kanske föredrar andra metoder för att distribuera dina nycklar.</span><span class="sxs-lookup"><span data-stu-id="2d575-342">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="2d575-343">Välj den metod som passar din organisation bäst.</span><span class="sxs-lookup"><span data-stu-id="2d575-343">Select the method that works best for your organization.</span></span>

<span data-ttu-id="2d575-344">För pilotdistributioner kan du distribuera i Azure och komma igång direkt.</span><span class="sxs-lookup"><span data-stu-id="2d575-344">For pilot deployments, you can deploy in Azure and get started right away.</span></span>

<span data-ttu-id="2d575-345">**Så här skapar du en Azure Web App-instans som värd för DKE-distributionen**</span><span class="sxs-lookup"><span data-stu-id="2d575-345">**To create an Azure Web App instance to host your DKE deployment**</span></span>

<span data-ttu-id="2d575-346">När du ska publicera nyckellagringsnyckeln skapar du en Azure App Service-instans som värd för DKE-distributionen.</span><span class="sxs-lookup"><span data-stu-id="2d575-346">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="2d575-347">Därefter ska du publicera de nycklar du skapat i Azure.</span><span class="sxs-lookup"><span data-stu-id="2d575-347">Next, you'll publish your generated keys to Azure.</span></span>

1. <span data-ttu-id="2d575-348">Logga in på e-postportalen [i Microsoft Azure](https://ms.portal.azure.com)och gå till **Lägg till**  >  **Apptjänster.**</span><span class="sxs-lookup"><span data-stu-id="2d575-348">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

2. <span data-ttu-id="2d575-349">Välj prenumerations- och resursgrupp och definiera instansinformation.</span><span class="sxs-lookup"><span data-stu-id="2d575-349">Select your subscription and resource group and define your instance details.</span></span>

   - <span data-ttu-id="2d575-350">Ange värdnamnet för den dator där du vill installera DKE-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="2d575-350">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="2d575-351">Kontrollera att det är samma namn som det som definierats för inställningen JwtAudience [**i detappsettings.jsfilen.**](#tenant-and-key-settings)</span><span class="sxs-lookup"><span data-stu-id="2d575-351">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="2d575-352">Värdet du anger för namnet är också WebAppInstanceName.</span><span class="sxs-lookup"><span data-stu-id="2d575-352">The value you provide for the name is also the WebAppInstanceName.</span></span>

   - <span data-ttu-id="2d575-353">För **Publicera** väljer du **kod** och för **Runtime-stack** väljer du **.NET Core 3.1.**</span><span class="sxs-lookup"><span data-stu-id="2d575-353">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

   <span data-ttu-id="2d575-354">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2d575-354">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2d575-355">![Lägg till din programtjänst](../media/dke-azure-add-app-service.png)</span><span class="sxs-lookup"><span data-stu-id="2d575-355">![Add your App Service](../media/dke-azure-add-app-service.png)</span></span>

3. <span data-ttu-id="2d575-356">Längst ned på sidan väljer du Granska **+ skapa och** sedan Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="2d575-356">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

4. <span data-ttu-id="2d575-357">Gör något av följande för att publicera de nycklar du skapat:</span><span class="sxs-lookup"><span data-stu-id="2d575-357">Do one of the following to publish your generated keys:</span></span>

   - [<span data-ttu-id="2d575-358">Publicera via ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="2d575-358">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
   - [<span data-ttu-id="2d575-359">Publicera via FTP</span><span class="sxs-lookup"><span data-stu-id="2d575-359">Publish via FTP</span></span>](#publish-via-ftp)
   - [<span data-ttu-id="2d575-360">Publicera via Visual Studio 2019 eller senare</span><span class="sxs-lookup"><span data-stu-id="2d575-360">Publish via Visual Studio 2019 or later</span></span>](/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="2d575-361">Publicera via ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="2d575-361">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="2d575-362">Gå till `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span><span class="sxs-lookup"><span data-stu-id="2d575-362">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

   <span data-ttu-id="2d575-363">Till exempel: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="2d575-363">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

2. <span data-ttu-id="2d575-364">Gå till mappen **customer-key-store\src\customer-key-store** i codebase för nyckellagret och kontrollera att mappen innehåller filen **customerkeystore.csproj.**</span><span class="sxs-lookup"><span data-stu-id="2d575-364">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

3. <span data-ttu-id="2d575-365">Kör: **dotnet publicera**</span><span class="sxs-lookup"><span data-stu-id="2d575-365">Run: **dotnet publish**</span></span>

   <span data-ttu-id="2d575-366">I utdatafönstret visas katalogen där publiceringen distribuerades.</span><span class="sxs-lookup"><span data-stu-id="2d575-366">The output window displays the directory where the publish was deployed.</span></span>

   <span data-ttu-id="2d575-367">Till exempel: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="2d575-367">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

4. <span data-ttu-id="2d575-368">Skicka alla filer i publiceringskatalogen till en .zip filen.</span><span class="sxs-lookup"><span data-stu-id="2d575-368">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="2d575-369">När du .zip filen ser du till att alla filer i katalogen är på rotnivån i .zip filen.</span><span class="sxs-lookup"><span data-stu-id="2d575-369">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

5. <span data-ttu-id="2d575-370">Dra och släpp .zip filen du skapade på ZipDeployUI-webbplatsen som du öppnade ovan.</span><span class="sxs-lookup"><span data-stu-id="2d575-370">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="2d575-371">Till exempel: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="2d575-371">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="2d575-372">DKE distribueras och du kan bläddra till testnycklarna som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="2d575-372">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="2d575-373">Fortsätt att [validera distributionen](#validate-your-deployment) nedan.</span><span class="sxs-lookup"><span data-stu-id="2d575-373">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="2d575-374">Publicera via FTP</span><span class="sxs-lookup"><span data-stu-id="2d575-374">Publish via FTP</span></span>

1. <span data-ttu-id="2d575-375">Anslut till apptjänsten som du skapade [ovan.](#deploy-the-dke-service-and-publish-the-key-store)</span><span class="sxs-lookup"><span data-stu-id="2d575-375">Connect to the App Service you created [above](#deploy-the-dke-service-and-publish-the-key-store).</span></span>

   <span data-ttu-id="2d575-376">I webbläsaren går du till: **Azure Portal App Service**  >  **Deployment** Center ,  >  **FTP-instrumentpanel** för  >  **manuell**  >    >  **distribution.**</span><span class="sxs-lookup"><span data-stu-id="2d575-376">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

2. <span data-ttu-id="2d575-377">Kopiera anslutningssträngarna som visas till en lokal fil.</span><span class="sxs-lookup"><span data-stu-id="2d575-377">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="2d575-378">Du använder strängarna för att ansluta till Webbtjänsten och ladda upp filer via FTP.</span><span class="sxs-lookup"><span data-stu-id="2d575-378">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

   <span data-ttu-id="2d575-379">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2d575-379">For example:</span></span>

   ![Kopiera anslutningssträngar från FTP-instrumentpanelen](../media/dke-ftp-dashboard.png)

3. <span data-ttu-id="2d575-381">Gå till katalogen **customer-key-store\src\customer-key-store** i codebase för nyckellagring.</span><span class="sxs-lookup"><span data-stu-id="2d575-381">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

4. <span data-ttu-id="2d575-382">Kontrollera att den här katalogen innehåller **filen customerkeystore.csproj.**</span><span class="sxs-lookup"><span data-stu-id="2d575-382">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

5. <span data-ttu-id="2d575-383">Kör: **dotnet publicera**</span><span class="sxs-lookup"><span data-stu-id="2d575-383">Run: **dotnet publish**</span></span>

   <span data-ttu-id="2d575-384">Utdata innehåller katalogen där publiceringen distribuerades.</span><span class="sxs-lookup"><span data-stu-id="2d575-384">The output contains the directory where the publish was deployed.</span></span>

   <span data-ttu-id="2d575-385">Till exempel: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="2d575-385">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

6. <span data-ttu-id="2d575-386">Skicka alla filer i publiceringskatalogen till en ZIP-fil.</span><span class="sxs-lookup"><span data-stu-id="2d575-386">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="2d575-387">När du .zip filen ser du till att alla filer i katalogen är på rotnivån i .zip filen.</span><span class="sxs-lookup"><span data-stu-id="2d575-387">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

7. <span data-ttu-id="2d575-388">Från FTP-klienten använder du anslutningsinformationen som du kopierade för att ansluta till apptjänsten.</span><span class="sxs-lookup"><span data-stu-id="2d575-388">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="2d575-389">Upload till .zip skapade i föregående steg i rotkatalogen för webbprogrammet.</span><span class="sxs-lookup"><span data-stu-id="2d575-389">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="2d575-390">DKE distribueras och du kan bläddra till de testnycklar som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="2d575-390">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="2d575-391">Validera [sedan distributionen.](#validate-your-deployment)</span><span class="sxs-lookup"><span data-stu-id="2d575-391">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="2d575-392">Validera din distribution</span><span class="sxs-lookup"><span data-stu-id="2d575-392">Validate your deployment</span></span>

<span data-ttu-id="2d575-393">När du har distribuerat DKE med någon av metoderna som beskrivs ovan verifierar du inställningarna för distributionen och nyckelarkivet.</span><span class="sxs-lookup"><span data-stu-id="2d575-393">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="2d575-394">Kör:</span><span class="sxs-lookup"><span data-stu-id="2d575-394">Run:</span></span>

```powershell
src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey
```

<span data-ttu-id="2d575-395">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2d575-395">For example:</span></span>

```powershell
key_store_tester.ps1 https://mydkeservice.com/mykey
```

<span data-ttu-id="2d575-396">Se till att inga fel visas i utdata.</span><span class="sxs-lookup"><span data-stu-id="2d575-396">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="2d575-397">Registrera nyckelbutiken [när du är klar.](#register-your-key-store)</span><span class="sxs-lookup"><span data-stu-id="2d575-397">When you're ready, [register your key store](#register-your-key-store).</span></span>

<span data-ttu-id="2d575-398">Nyckelnamnet är det ärendekänsliga.</span><span class="sxs-lookup"><span data-stu-id="2d575-398">The key name is case sensitive.</span></span> <span data-ttu-id="2d575-399">Ange nyckelns namn som det visas i det appsettings.jsfilen.</span><span class="sxs-lookup"><span data-stu-id="2d575-399">Enter the key name as it appears in the appsettings.json file.</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="2d575-400">Registrera din nyckelbutik</span><span class="sxs-lookup"><span data-stu-id="2d575-400">Register your key store</span></span>

<span data-ttu-id="2d575-401">Med följande steg kan du registrera din DKE-tjänst.</span><span class="sxs-lookup"><span data-stu-id="2d575-401">The following steps enable you to register your DKE service.</span></span> <span data-ttu-id="2d575-402">Att registrera din DKE-tjänst är det sista steget i distributionen av DKE innan du kan börja skapa etiketter.</span><span class="sxs-lookup"><span data-stu-id="2d575-402">Registering your DKE service is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="2d575-403">Så här registrerar du DKE-tjänsten:</span><span class="sxs-lookup"><span data-stu-id="2d575-403">To register the DKE service:</span></span>

1. <span data-ttu-id="2d575-404">I webbläsaren öppnar du [webbportalen Microsoft Azure](https://ms.portal.azure.com/)och går till **Registreringar för Alla** \> **tjänster-identitetsapp.** \> </span><span class="sxs-lookup"><span data-stu-id="2d575-404">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="2d575-405">Välj **Ny registrering** och ange ett beskrivande namn.</span><span class="sxs-lookup"><span data-stu-id="2d575-405">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="2d575-406">Välj en kontotyp bland alternativen som visas.</span><span class="sxs-lookup"><span data-stu-id="2d575-406">Select an account type from the options displayed.</span></span>

   <span data-ttu-id="2d575-407">Om du använder Microsoft Azure domän som inte är en egen domän, till exempel **onmicrosoft.com,** väljer du Konton endast i den här organisationskatalogen **(Endast Microsoft – enskild klient).**</span><span class="sxs-lookup"><span data-stu-id="2d575-407">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

   <span data-ttu-id="2d575-408">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2d575-408">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2d575-409">![Registrering för ny app](../media/dke-app-registration.png)</span><span class="sxs-lookup"><span data-stu-id="2d575-409">![New App Registration](../media/dke-app-registration.png)</span></span>

4. <span data-ttu-id="2d575-410">Längst ned på sidan väljer du Registrera **för att** skapa den nya appregistreringen.</span><span class="sxs-lookup"><span data-stu-id="2d575-410">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="2d575-411">I den nya appregistreringen, i den vänstra rutan, under **Hantera** väljer du **Autentisering**.</span><span class="sxs-lookup"><span data-stu-id="2d575-411">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="2d575-412">Välj **Lägg till en plattform.**</span><span class="sxs-lookup"><span data-stu-id="2d575-412">Select **Add a platform**.</span></span>

7. <span data-ttu-id="2d575-413">Välj **Webb på** popup-menyn Konfigurera **plattformar.**</span><span class="sxs-lookup"><span data-stu-id="2d575-413">On the **Configure platforms** popup, select **Web**.</span></span>

8. <span data-ttu-id="2d575-414">Under **Omdirigera URI:er** anger du URI:en för krypteringstjänsten med dubbelnyckeln.</span><span class="sxs-lookup"><span data-stu-id="2d575-414">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="2d575-415">Ange apptjänst-URL:en, inklusive både värdnamn och domän.</span><span class="sxs-lookup"><span data-stu-id="2d575-415">Enter the App Service URL, including both the hostname and domain.</span></span>

   <span data-ttu-id="2d575-416">Till exempel: https://mydkeservicetest.com</span><span class="sxs-lookup"><span data-stu-id="2d575-416">For example: https://mydkeservicetest.com</span></span>

   - <span data-ttu-id="2d575-417">URL-adressen du anger måste matcha värdnamnet där DKE-tjänsten är distribuerad.</span><span class="sxs-lookup"><span data-stu-id="2d575-417">The URL you enter must match the hostname where your DKE service is deployed.</span></span>
   - <span data-ttu-id="2d575-418">Om du testar lokalt med Visual Studio du **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="2d575-418">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
   - <span data-ttu-id="2d575-419">I samtliga fall måste schemat vara **https.**</span><span class="sxs-lookup"><span data-stu-id="2d575-419">In all cases, the scheme must be **https**.</span></span>

   <span data-ttu-id="2d575-420">Se till att värdnamnet exakt matchar din App Service-värdnamn.</span><span class="sxs-lookup"><span data-stu-id="2d575-420">Ensure the hostname exactly matches your App Service hostname.</span></span> <span data-ttu-id="2d575-421">Du kanske har ändrat den till `localhost` att felsöka versionen.</span><span class="sxs-lookup"><span data-stu-id="2d575-421">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="2d575-422">I **appsettings.jspå** är det här värdet det värdnamn som du anger för `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="2d575-422">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

9. <span data-ttu-id="2d575-423">Markera **kryssrutan** **ID-token under** Implicit grant.</span><span class="sxs-lookup"><span data-stu-id="2d575-423">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

10. <span data-ttu-id="2d575-424">Välj **Spara** för att spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="2d575-424">Select **Save** to save your changes.</span></span>

11. <span data-ttu-id="2d575-425">Välj Visa ett **API** i det vänstra fönstret och välj sedan Ange bredvid Program-ID-URI. </span><span class="sxs-lookup"><span data-stu-id="2d575-425">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

12. <span data-ttu-id="2d575-426">Välj Lägg till en omfattning i området Omfattningar **som definieras** av detta API på sidan Visa **ett** **API.**</span><span class="sxs-lookup"><span data-stu-id="2d575-426">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="2d575-427">I den nya omfattningen:</span><span class="sxs-lookup"><span data-stu-id="2d575-427">In the new scope:</span></span>

    1. <span data-ttu-id="2d575-428">Definiera omfattningsnamnet som **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="2d575-428">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="2d575-429">Välj de administratörer och användare som kan ge sitt medgivande.</span><span class="sxs-lookup"><span data-stu-id="2d575-429">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="2d575-430">Definiera eventuella återstående värden som krävs.</span><span class="sxs-lookup"><span data-stu-id="2d575-430">Define any remaining values required.</span></span>

    4. <span data-ttu-id="2d575-431">Välj **Lägg till omfattning**.</span><span class="sxs-lookup"><span data-stu-id="2d575-431">Select **Add scope**.</span></span>

    5. <span data-ttu-id="2d575-432">Spara **ändringarna** genom att välja Spara högst upp.</span><span class="sxs-lookup"><span data-stu-id="2d575-432">Select **Save** at the top to save your changes.</span></span>

13. <span data-ttu-id="2d575-433">Fortfarande på sidan **Visa ett API** går du till området Auktoriserade **klientprogram** och väljer Lägg **till ett klientprogram.**</span><span class="sxs-lookup"><span data-stu-id="2d575-433">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="2d575-434">I det nya klientprogrammet:</span><span class="sxs-lookup"><span data-stu-id="2d575-434">In the new client application:</span></span>

    1. <span data-ttu-id="2d575-435">Definiera klient-ID som `d3590ed6-52b3-4102-aeff-aad2292ab01c` .</span><span class="sxs-lookup"><span data-stu-id="2d575-435">Define the Client ID as `d3590ed6-52b3-4102-aeff-aad2292ab01c`.</span></span> <span data-ttu-id="2d575-436">Det här värdet är Microsoft Office klient-ID och gör att Office hämta en åtkomsttoken för nyckelarkivet.</span><span class="sxs-lookup"><span data-stu-id="2d575-436">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="2d575-437">Under **Auktoriserade omfattningar** väljer du **user_impersonation** omfattning.</span><span class="sxs-lookup"><span data-stu-id="2d575-437">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="2d575-438">Välj **Lägg till program**.</span><span class="sxs-lookup"><span data-stu-id="2d575-438">Select **Add application**.</span></span>

    4. <span data-ttu-id="2d575-439">Spara **ändringarna** genom att välja Spara högst upp.</span><span class="sxs-lookup"><span data-stu-id="2d575-439">Select **Save** at the top to save your changes.</span></span>

    5. <span data-ttu-id="2d575-440">Upprepa dessa steg, men nu definierar du klient-ID som `c00e9d32-3c8d-4a7d-832b-029040e7db99` .</span><span class="sxs-lookup"><span data-stu-id="2d575-440">Repeat these steps, but this time, define the client ID as `c00e9d32-3c8d-4a7d-832b-029040e7db99`.</span></span> <span data-ttu-id="2d575-441">Det här värdet är det enhetliga klient-ID:t för Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="2d575-441">This value is the Azure Information Protection unified labeling client ID.</span></span> 

<span data-ttu-id="2d575-442">Din DKE-tjänst är nu registrerad.</span><span class="sxs-lookup"><span data-stu-id="2d575-442">Your DKE service is now registered.</span></span> <span data-ttu-id="2d575-443">Fortsätt genom [att skapa etiketter med DKE](#create-sensitivity-labels-using-dke).</span><span class="sxs-lookup"><span data-stu-id="2d575-443">Continue by [creating labels using DKE](#create-sensitivity-labels-using-dke).</span></span>

## <a name="create-sensitivity-labels-using-dke"></a><span data-ttu-id="2d575-444">Skapa känslighetsetiketter med DKE</span><span class="sxs-lookup"><span data-stu-id="2d575-444">Create sensitivity labels using DKE</span></span>

<span data-ttu-id="2d575-445">I Microsoft 365 säkerhets- och efterlevnadscenter skapar du en ny känslighetsetikett och tillämpar kryptering som du annars skulle göra.</span><span class="sxs-lookup"><span data-stu-id="2d575-445">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="2d575-446">Välj **Använd dubbelnyckelkryptering** och ange slutpunkts-URL:en för din nyckel.</span><span class="sxs-lookup"><span data-stu-id="2d575-446">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="2d575-447">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="2d575-447">For example:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2d575-448">![Välj Använd dubbelnyckelkryptering i Microsoft 365 kompatibilitetscenter](../media/dke-use-dke.png)</span><span class="sxs-lookup"><span data-stu-id="2d575-448">![Select Use Double Key Encryption in the Microsoft 365 compliance center](../media/dke-use-dke.png)</span></span>

<span data-ttu-id="2d575-449">De DKE-etiketter du lägger till visas i de senaste versionerna av Microsoft 365-appar för företag.</span><span class="sxs-lookup"><span data-stu-id="2d575-449">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="2d575-450">Det kan ta upp till 24 timmar för klienterna att uppdatera med de nya etiketterna.</span><span class="sxs-lookup"><span data-stu-id="2d575-450">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="2d575-451">Aktivera DKE i klienten</span><span class="sxs-lookup"><span data-stu-id="2d575-451">Enable DKE in your client</span></span>

<span data-ttu-id="2d575-452">Om du är en Office Insider är DKE aktiverat för dig.</span><span class="sxs-lookup"><span data-stu-id="2d575-452">If you're an Office Insider, DKE is enabled for you.</span></span> <span data-ttu-id="2d575-453">Annars aktiverar du DKE för klienten genom att lägga till följande registernycklar:</span><span class="sxs-lookup"><span data-stu-id="2d575-453">Otherwise, enable DKE for your client by adding the following registry keys:</span></span>

```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001

   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a><span data-ttu-id="2d575-454">Migrera skyddade filer från HYOK-etiketter till DKE-etiketter</span><span class="sxs-lookup"><span data-stu-id="2d575-454">Migrate protected files from HYOK labels to DKE labels</span></span>

<span data-ttu-id="2d575-455">När du är klar med att konfigurera DKE kan du migrera innehåll som du har skyddat med hjälp av HYOK-etiketter till DKE-etiketter.</span><span class="sxs-lookup"><span data-stu-id="2d575-455">If you want, once you're finished setting up DKE, you can migrate content that you've protected using HYOK labels to DKE labels.</span></span> <span data-ttu-id="2d575-456">Om du vill migrera använder du AIP-skannern.</span><span class="sxs-lookup"><span data-stu-id="2d575-456">To migrate, you'll use the AIP scanner.</span></span> <span data-ttu-id="2d575-457">Om du vill komma igång med att använda [skannern går du till Vad är Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner).</span><span class="sxs-lookup"><span data-stu-id="2d575-457">To get started using the scanner, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner).</span></span>

<span data-ttu-id="2d575-458">Om du inte migrerar innehåll påverkas inte ditt HYOK-skyddade innehåll.</span><span class="sxs-lookup"><span data-stu-id="2d575-458">If you don't migrate content, your HYOK protected content will remain unaffected.</span></span>
