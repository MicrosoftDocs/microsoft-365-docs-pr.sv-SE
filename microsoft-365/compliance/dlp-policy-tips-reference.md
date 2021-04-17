---
title: Referens för principtips för dataförlustskydd
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: Lär dig hur du lägger till ett principtips i en DLP-princip (Data Loss Prevention) om att de arbetar med innehåll som står i konflikt med en DLP-princip.
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 693f511b6303fb07d393c62efb4a61631b844474
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876824"
---
# <a name="data-loss-prevention-policy-tips-reference"></a><span data-ttu-id="23c40-103">Referens för principtips för dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="23c40-103">Data Loss Prevention policy tips reference</span></span>

<span data-ttu-id="23c40-104">DLP-principtips i Outlook Web Access stöds för alla villkor, undantag och åtgärder som är tillämpliga för Exchange-arbetsbelastning i en DLP-princip, förutom följande:</span><span class="sxs-lookup"><span data-stu-id="23c40-104">DLP policy tips in Outlook Web Access is supported for all the conditions, exceptions and actions that are applicable on Exchange workload in a DLP policy except the following:</span></span>

<span data-ttu-id="23c40-105">**Villkor:**</span><span class="sxs-lookup"><span data-stu-id="23c40-105">**Conditions:**</span></span>

- <span data-ttu-id="23c40-106">Sender Is</span><span class="sxs-lookup"><span data-stu-id="23c40-106">Sender Is</span></span>
- <span data-ttu-id="23c40-107">Sender Domain Is</span><span class="sxs-lookup"><span data-stu-id="23c40-107">Sender Domain Is</span></span>
- <span data-ttu-id="23c40-108">Mottagaren är medlem i</span><span class="sxs-lookup"><span data-stu-id="23c40-108">Recipient is a member of</span></span>
- <span data-ttu-id="23c40-109">Sidhuvudet innehåller ord eller fraser</span><span class="sxs-lookup"><span data-stu-id="23c40-109">Header contains words or phrases</span></span>
- <span data-ttu-id="23c40-110">Sidhuvud matchar mönster</span><span class="sxs-lookup"><span data-stu-id="23c40-110">Header matches patterns</span></span>
- <span data-ttu-id="23c40-111">Dokumentstorlek är lika med eller större än</span><span class="sxs-lookup"><span data-stu-id="23c40-111">Document size equals or is greater than</span></span>
- <span data-ttu-id="23c40-112">Meddelandetypen är</span><span class="sxs-lookup"><span data-stu-id="23c40-112">Message type is</span></span>
- <span data-ttu-id="23c40-113">Meddelandets prioritet är</span><span class="sxs-lookup"><span data-stu-id="23c40-113">Message importance is</span></span>
- <span data-ttu-id="23c40-114">Innehållsteckenuppsättning innehåller ord</span><span class="sxs-lookup"><span data-stu-id="23c40-114">Content character set contains words</span></span>
- <span data-ttu-id="23c40-115">Ämne eller brödtext innehåller ord eller fraser</span><span class="sxs-lookup"><span data-stu-id="23c40-115">Subject or body contains words or phrases</span></span>
- <span data-ttu-id="23c40-116">Mönster för ämne eller brödtext</span><span class="sxs-lookup"><span data-stu-id="23c40-116">Subject or body matches patterns</span></span>
- <span data-ttu-id="23c40-117">Innehållsteckenuppsättning innehåller ord</span><span class="sxs-lookup"><span data-stu-id="23c40-117">Content character set contains words</span></span>
- <span data-ttu-id="23c40-118">Innehåll tas emot från</span><span class="sxs-lookup"><span data-stu-id="23c40-118">Content is received from</span></span>
- <span data-ttu-id="23c40-119">Har avsändaren åsidosättt principtipset</span><span class="sxs-lookup"><span data-stu-id="23c40-119">Has sender overridden the policy tip</span></span>
- <span data-ttu-id="23c40-120">Meddelandestorlek är lika med eller större än</span><span class="sxs-lookup"><span data-stu-id="23c40-120">Message size equals or is greater than</span></span>
- <span data-ttu-id="23c40-121">Sender AD-attributet innehåller ord eller fraser</span><span class="sxs-lookup"><span data-stu-id="23c40-121">Sender AD attribute contains words or phrases</span></span>
- <span data-ttu-id="23c40-122">Ad-sender-attributet matchar mönster</span><span class="sxs-lookup"><span data-stu-id="23c40-122">Sender AD attribute matches patterns</span></span>
- <span data-ttu-id="23c40-123">Dokumentinnehållet innehåller ord eller fraser</span><span class="sxs-lookup"><span data-stu-id="23c40-123">Document content contains words or phrases</span></span>
- <span data-ttu-id="23c40-124">Dokumentinnehåll matchar mönster</span><span class="sxs-lookup"><span data-stu-id="23c40-124">Document content matches patterns</span></span>

<span data-ttu-id="23c40-125">**Åtgärder:**</span><span class="sxs-lookup"><span data-stu-id="23c40-125">**Actions:**</span></span>

- <span data-ttu-id="23c40-126">Vidarebefordra meddelandet för godkännande till avsändarens chef</span><span class="sxs-lookup"><span data-stu-id="23c40-126">Forward the message for approval to sender’s manager</span></span>
- <span data-ttu-id="23c40-127">Vidarebefordra meddelandet för godkännande till vissa godkännare</span><span class="sxs-lookup"><span data-stu-id="23c40-127">Forward the message for approval to specific approvers</span></span>
- <span data-ttu-id="23c40-128">Omdirigera meddelandet till specifika användare</span><span class="sxs-lookup"><span data-stu-id="23c40-128">Redirect the message to specific users</span></span>
- <span data-ttu-id="23c40-129">Lägga till mottagare i Rutan Till</span><span class="sxs-lookup"><span data-stu-id="23c40-129">Add recipients to the To Box</span></span>
- <span data-ttu-id="23c40-130">Lägga till mottagare i rutan Kopia</span><span class="sxs-lookup"><span data-stu-id="23c40-130">Add recipients to the Cc Box</span></span>
- <span data-ttu-id="23c40-131">Lägga till mottagare i rutan Hemlig kopia</span><span class="sxs-lookup"><span data-stu-id="23c40-131">Add recipients to the Bcc Box</span></span>
- <span data-ttu-id="23c40-132">Lägga till avsändarens chef som mottagare</span><span class="sxs-lookup"><span data-stu-id="23c40-132">Add the sender’s manager as recipient</span></span>
- <span data-ttu-id="23c40-133">Lägga till HTML-ansvarsfriskrivning</span><span class="sxs-lookup"><span data-stu-id="23c40-133">Add HTML disclaimer</span></span>
- <span data-ttu-id="23c40-134">Förbereda ämnet för e-post</span><span class="sxs-lookup"><span data-stu-id="23c40-134">Prepend email subject</span></span>
- <span data-ttu-id="23c40-135">Ta bort meddelandekryptering och rättighetsskydd i O365</span><span class="sxs-lookup"><span data-stu-id="23c40-135">Remove O365 Message Encryption and rights protection</span></span>
- <span data-ttu-id="23c40-136">Ta bort</span><span class="sxs-lookup"><span data-stu-id="23c40-136">Remove</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a><span data-ttu-id="23c40-137">Outlook 2013 och senare har stöd för att visa principtips för bara vissa villkor och undantag</span><span class="sxs-lookup"><span data-stu-id="23c40-137">Outlook 2013 and later supports showing policy tips for only some conditions and exceptions</span></span>

<span data-ttu-id="23c40-138">För närvarande har Outlook 2013 och senare stöd för att visa principtips för principer som inte innehåller några villkor eller undantag utöver nedan nämnda villkor och motsvarande undantag:</span><span class="sxs-lookup"><span data-stu-id="23c40-138">Currently, Outlook 2013 and later supports showing policy tips for policies which do not contain any condition or exception apart from the below mentioned conditions and corresponding exceptions :</span></span>

- <span data-ttu-id="23c40-139">Innehållet innehåller (fungerar endast för typer av känslig information.</span><span class="sxs-lookup"><span data-stu-id="23c40-139">Content contains (works only for Sensitive information types.</span></span> <span data-ttu-id="23c40-140">Känslighetsetiketter stöds inte)</span><span class="sxs-lookup"><span data-stu-id="23c40-140">Sensitivity labels are not supported)</span></span>
- <span data-ttu-id="23c40-141">Innehåll delas</span><span class="sxs-lookup"><span data-stu-id="23c40-141">Content is shared</span></span>

<span data-ttu-id="23c40-142">Observera att alla villkor fungerar för e-postmeddelanden som redigeras i Outlook-klientappen, där de matchar innehåll och tillämpar skyddsåtgärder för innehåll.</span><span class="sxs-lookup"><span data-stu-id="23c40-142">Note that all the conditions work for emails authored in Outlook client app, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="23c40-143">Men det är ännu inte möjligt att visa principtips för användare för andra villkor än de som nämns ovan.</span><span class="sxs-lookup"><span data-stu-id="23c40-143">However, showing policy tips to users is not yet supported for any conditions that are used apart from the ones mentioned above.</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="23c40-144">Outlook 2013 och senare har stöd för att visa principtips för endast vissa typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="23c40-144">Outlook 2013 and later supports showing policy tips for only some sensitive information types</span></span>

<span data-ttu-id="23c40-145">Listan med för in visna typer av känslig information som identifieras för visning av DLP-principtips i Outlook på skrivbordet (2013 och senare) är följande:</span><span class="sxs-lookup"><span data-stu-id="23c40-145">The list of out-of-the-box sensitive information types that will be detected for showing DLP policy tips in Outlook on Desktop (2013 and later) are the following :</span></span>

- <span data-ttu-id="23c40-146">ABA-routningsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-146">ABA Routing Number</span></span>
- <span data-ttu-id="23c40-147">Argentina National Identity (DNI) Number</span><span class="sxs-lookup"><span data-stu-id="23c40-147">Argentina National Identity (DNI) Number</span></span>
- <span data-ttu-id="23c40-148">Bank Account Number för Australien</span><span class="sxs-lookup"><span data-stu-id="23c40-148">Australia Bank Account Number</span></span>
- <span data-ttu-id="23c40-149">Australiens medicinska kontonummer</span><span class="sxs-lookup"><span data-stu-id="23c40-149">Australia Medical Account Number</span></span>
- <span data-ttu-id="23c40-150">Australia Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-150">Australia Passport Number</span></span>
- <span data-ttu-id="23c40-151">Australiens skattenummer</span><span class="sxs-lookup"><span data-stu-id="23c40-151">Australia Tax File Number</span></span>
- <span data-ttu-id="23c40-152">Autentiseringsnyckel för Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="23c40-152">Azure DocumentDB Auth Key</span></span>  
- <span data-ttu-id="23c40-153">Azure IAAS-databasanslutningssträng och Azure SQL-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="23c40-153">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>  
- <span data-ttu-id="23c40-154">Azure IoT-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="23c40-154">Azure IoT Connection String</span></span>  
- <span data-ttu-id="23c40-155">Lösenord för Inställning av Azure-publicering</span><span class="sxs-lookup"><span data-stu-id="23c40-155">Azure Publish Setting Password</span></span>  
- <span data-ttu-id="23c40-156">Azure Redis Cache-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="23c40-156">Azure Redis Cache Connection String</span></span>  
- <span data-ttu-id="23c40-157">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="23c40-157">Azure SAS</span></span>  
- <span data-ttu-id="23c40-158">Azure Service Bus Connection String</span><span class="sxs-lookup"><span data-stu-id="23c40-158">Azure Service Bus Connection String</span></span>  
- <span data-ttu-id="23c40-159">Azure Storage Account Key</span><span class="sxs-lookup"><span data-stu-id="23c40-159">Azure Storage Account Key</span></span>  
- <span data-ttu-id="23c40-160">Azure Storage Account Key (generic)</span><span class="sxs-lookup"><span data-stu-id="23c40-160">Azure Storage Account Key (Generic)</span></span>  
- <span data-ttu-id="23c40-161">Belgiens nationalnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-161">Belgium National Number</span></span>
- <span data-ttu-id="23c40-162">Brasilien CPF-nummer</span><span class="sxs-lookup"><span data-stu-id="23c40-162">Brazil CPF Number</span></span>
- <span data-ttu-id="23c40-163">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="23c40-163">Brazil Legal Entity Number (CNPJ)</span></span>
- <span data-ttu-id="23c40-164">Brazil National ID Card (RG)</span><span class="sxs-lookup"><span data-stu-id="23c40-164">Brazil National ID Card (RG)</span></span>
- <span data-ttu-id="23c40-165">Bank Account Number för Kanada</span><span class="sxs-lookup"><span data-stu-id="23c40-165">Canada Bank Account Number</span></span>
- <span data-ttu-id="23c40-166">Kanadas driver's License Number</span><span class="sxs-lookup"><span data-stu-id="23c40-166">Canada Driver's License Number</span></span>
- <span data-ttu-id="23c40-167">Canada Health Service Number</span><span class="sxs-lookup"><span data-stu-id="23c40-167">Canada Health Service Number</span></span>
- <span data-ttu-id="23c40-168">Canada Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-168">Canada Passport Number</span></span>
- <span data-ttu-id="23c40-169">Canada Personal Health Identification Number (PHIN)</span><span class="sxs-lookup"><span data-stu-id="23c40-169">Canada Personal Health Identification Number (PHIN)</span></span>
- <span data-ttu-id="23c40-170">Canada Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="23c40-170">Canada Social Insurance Number</span></span>
- <span data-ttu-id="23c40-171">Chile Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="23c40-171">Chile Identity Card Number</span></span>
- <span data-ttu-id="23c40-172">China Resident Identity Card (Folkrepubliken Kina) Nummer</span><span class="sxs-lookup"><span data-stu-id="23c40-172">China Resident Identity Card (PRC) Number</span></span>
- <span data-ttu-id="23c40-173">Kreditkortsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-173">Credit Card Number</span></span>
- <span data-ttu-id="23c40-174">Kroatiens identitetskortsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-174">Croatia Identity Card Number</span></span>  
- <span data-ttu-id="23c40-175">Kroatiens OIB-nummer (Personal Identification)</span><span class="sxs-lookup"><span data-stu-id="23c40-175">Croatia Personal Identification (OIB) Number</span></span>  
- <span data-ttu-id="23c40-176">Tjeckiska Personliga identitetsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-176">Czech Personal Identity Number</span></span>  
- <span data-ttu-id="23c40-177">Danmarks personliga id-nummer</span><span class="sxs-lookup"><span data-stu-id="23c40-177">Denmark Personal Identification Number</span></span>
- <span data-ttu-id="23c40-178">Tvingande Enforcement Agency (DEA) Number</span><span class="sxs-lookup"><span data-stu-id="23c40-178">Drug Enforcement Agency (DEA) Number</span></span>
- <span data-ttu-id="23c40-179">Betalkortsnummer (EU)</span><span class="sxs-lookup"><span data-stu-id="23c40-179">EU Debit Card Number</span></span>
- <span data-ttu-id="23c40-180">EU:s körkortsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-180">EU Driver's License Number</span></span>  
- <span data-ttu-id="23c40-181">EU National Identification Number</span><span class="sxs-lookup"><span data-stu-id="23c40-181">EU National Identification Number</span></span>  
- <span data-ttu-id="23c40-182">EU Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-182">EU Passport Number</span></span>  
- <span data-ttu-id="23c40-183">SOCIAL SECURITY Number (SSN) eller motsvarande ID</span><span class="sxs-lookup"><span data-stu-id="23c40-183">EU Social Security Number (SSN) or Equivalent ID</span></span>  
- <span data-ttu-id="23c40-184">EU:s skatteidentifieringsnummer (TIN)</span><span class="sxs-lookup"><span data-stu-id="23c40-184">EU Tax Identification Number (TIN)</span></span>  
- <span data-ttu-id="23c40-185">Finlands national-ID</span><span class="sxs-lookup"><span data-stu-id="23c40-185">Finland National ID</span></span>
- <span data-ttu-id="23c40-186">Finland Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-186">Finland Passport Number</span></span>
- <span data-ttu-id="23c40-187">Frankrikes licensnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-187">France Driver's License Number</span></span>
- <span data-ttu-id="23c40-188">France National ID Card (CNI)</span><span class="sxs-lookup"><span data-stu-id="23c40-188">France National ID Card (CNI)</span></span>
- <span data-ttu-id="23c40-189">France Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-189">France Passport Number</span></span>
- <span data-ttu-id="23c40-190">France Social Security Number (INSEE)</span><span class="sxs-lookup"><span data-stu-id="23c40-190">France Social Security Number (INSEE)</span></span>
- <span data-ttu-id="23c40-191">Tyskt körkortsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-191">German Driver's License Number</span></span>
- <span data-ttu-id="23c40-192">Tyska Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-192">German Passport Number</span></span>
- <span data-ttu-id="23c40-193">Id Card Number för Tyskland</span><span class="sxs-lookup"><span data-stu-id="23c40-193">Germany Identity Card Number</span></span>
- <span data-ttu-id="23c40-194">Greklands national-ID-kort</span><span class="sxs-lookup"><span data-stu-id="23c40-194">Greece National ID Card</span></span>  
- <span data-ttu-id="23c40-195">Hong Kong Identity Card (HKID)-nummer</span><span class="sxs-lookup"><span data-stu-id="23c40-195">Hong Kong Identity Card (HKID) Number</span></span>
- <span data-ttu-id="23c40-196">Indiens permanenta kontonummer (PAN)</span><span class="sxs-lookup"><span data-stu-id="23c40-196">India Permanent Account Number (PAN)</span></span>
- <span data-ttu-id="23c40-197">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="23c40-197">India Unique Identification (Aadhaar) Number</span></span>
- <span data-ttu-id="23c40-198">Indonesia Identity Card-nummer (KTP)</span><span class="sxs-lookup"><span data-stu-id="23c40-198">Indonesia Identity Card (KTP) Number</span></span>
- <span data-ttu-id="23c40-199">International Banking Account Number (IBAN)</span><span class="sxs-lookup"><span data-stu-id="23c40-199">International Banking Account Number (IBAN)</span></span>
- <span data-ttu-id="23c40-200">Internationell klassificering av avnärende (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="23c40-200">International Classification of Diseases (ICD-10-CM)</span></span>  
- <span data-ttu-id="23c40-201">Internationell klassificering av tidsklassificering (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="23c40-201">International Classification of Diseases (ICD-9-CM)</span></span>  
- <span data-ttu-id="23c40-202">IP-adress</span><span class="sxs-lookup"><span data-stu-id="23c40-202">IP Address</span></span>
- <span data-ttu-id="23c40-203">Ireland Personal Public Service -nummer (PPS)</span><span class="sxs-lookup"><span data-stu-id="23c40-203">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="23c40-204">Israels bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="23c40-204">Israel Bank Account Number</span></span>
- <span data-ttu-id="23c40-205">Israels national-ID</span><span class="sxs-lookup"><span data-stu-id="23c40-205">Israel National ID</span></span>
- <span data-ttu-id="23c40-206">Italiens licensnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-206">Italy Driver's License Number</span></span>
- <span data-ttu-id="23c40-207">Japan Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="23c40-207">Japan Bank Account Number</span></span>
- <span data-ttu-id="23c40-208">Japan Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="23c40-208">Japan Driver's License Number</span></span>
- <span data-ttu-id="23c40-209">Japan Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-209">Japan Passport Number</span></span>
- <span data-ttu-id="23c40-210">Invånarregistreringsnummer för Japan</span><span class="sxs-lookup"><span data-stu-id="23c40-210">Japan Resident Registration Number</span></span>
- <span data-ttu-id="23c40-211">Japan Social Insurance Number (SIN)</span><span class="sxs-lookup"><span data-stu-id="23c40-211">Japan Social Insurance Number (SIN)</span></span>
- <span data-ttu-id="23c40-212">Japanska Residence Card Number</span><span class="sxs-lookup"><span data-stu-id="23c40-212">Japanese Residence Card Number</span></span>
- <span data-ttu-id="23c40-213">Malaysia Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="23c40-213">Malaysia Identity Card Number</span></span>
- <span data-ttu-id="23c40-214">Nederländska medborgares servicenummer (BSN)</span><span class="sxs-lookup"><span data-stu-id="23c40-214">Netherlands Citizen's Service (BSN) Number</span></span>  
- <span data-ttu-id="23c40-215">New Zealand Ministry of Health Number</span><span class="sxs-lookup"><span data-stu-id="23c40-215">New Zealand Ministry of Health Number</span></span>
- <span data-ttu-id="23c40-216">Norges identitetsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-216">Norway Identity Number</span></span>  
- <span data-ttu-id="23c40-217">Philippines Unified Multi-Purpose ID Number</span><span class="sxs-lookup"><span data-stu-id="23c40-217">Philippines Unified Multi-Purpose ID Number</span></span>
- <span data-ttu-id="23c40-218">Polens identitetskort</span><span class="sxs-lookup"><span data-stu-id="23c40-218">Poland Identity Card</span></span>
- <span data-ttu-id="23c40-219">Polens National ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="23c40-219">Poland National ID (PESEL)</span></span>
- <span data-ttu-id="23c40-220">Polen-pass</span><span class="sxs-lookup"><span data-stu-id="23c40-220">Poland Passport</span></span>
- <span data-ttu-id="23c40-221">Portugal, kreditkortsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-221">Portugal Citizen Card Number</span></span>
- <span data-ttu-id="23c40-222">Saudiarabiens national-ID</span><span class="sxs-lookup"><span data-stu-id="23c40-222">Saudi Arabia National ID</span></span>
- <span data-ttu-id="23c40-223">Singapore National Registration Identity Card (NRIC) Number</span><span class="sxs-lookup"><span data-stu-id="23c40-223">Singapore National Registration Identity Card (NRIC) Number</span></span>
- <span data-ttu-id="23c40-224">South Africa Identification Number</span><span class="sxs-lookup"><span data-stu-id="23c40-224">South Africa Identification Number</span></span>  
- <span data-ttu-id="23c40-225">Sydkoreas invånarregistreringsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-225">South Korea Resident Registration Number</span></span>
- <span data-ttu-id="23c40-226">Spain Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="23c40-226">Spain Social Security Number (SSN)</span></span>
- <span data-ttu-id="23c40-227">SQL Server-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="23c40-227">SQL Server Connection String</span></span>  
- <span data-ttu-id="23c40-228">National ID för Sverige</span><span class="sxs-lookup"><span data-stu-id="23c40-228">Sweden National ID</span></span>
- <span data-ttu-id="23c40-229">Sverige Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-229">Sweden Passport Number</span></span>
- <span data-ttu-id="23c40-230">SWIFT-kod</span><span class="sxs-lookup"><span data-stu-id="23c40-230">SWIFT Code</span></span>
- <span data-ttu-id="23c40-231">Taiwan National ID</span><span class="sxs-lookup"><span data-stu-id="23c40-231">Taiwan National ID</span></span>
- <span data-ttu-id="23c40-232">Taiwan Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-232">Taiwan Passport Number</span></span>
- <span data-ttu-id="23c40-233">Taiwan Resident Certificate (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="23c40-233">Taiwan Resident Certificate (ARC/TARC)</span></span>
- <span data-ttu-id="23c40-234">Identifieringskod för thailändska</span><span class="sxs-lookup"><span data-stu-id="23c40-234">Thai Population Identification Code</span></span>
- <span data-ttu-id="23c40-235">Turkiska National Identification Number</span><span class="sxs-lookup"><span data-stu-id="23c40-235">Turkish National Identification number</span></span>
- <span data-ttu-id="23c40-236">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="23c40-236">U.K.</span></span> <span data-ttu-id="23c40-237">Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="23c40-237">Driver's License Number</span></span>
- <span data-ttu-id="23c40-238">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="23c40-238">U.K.</span></span> <span data-ttu-id="23c40-239">E-nummer för att samla in</span><span class="sxs-lookup"><span data-stu-id="23c40-239">Electoral Roll Number</span></span>
- <span data-ttu-id="23c40-240">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="23c40-240">U.K.</span></span> <span data-ttu-id="23c40-241">National Health Service Number</span><span class="sxs-lookup"><span data-stu-id="23c40-241">National Health Service Number</span></span>
- <span data-ttu-id="23c40-242">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="23c40-242">U.K.</span></span> <span data-ttu-id="23c40-243">National Insurance Number (NINO)</span><span class="sxs-lookup"><span data-stu-id="23c40-243">National Insurance Number (NINO)</span></span>
- <span data-ttu-id="23c40-244">U.S. / Storbritannien</span><span class="sxs-lookup"><span data-stu-id="23c40-244">U.S. / U.K.</span></span> <span data-ttu-id="23c40-245">Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-245">Passport Number</span></span>
- <span data-ttu-id="23c40-246">U.S. Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="23c40-246">U.S. Bank Account Number</span></span>
- <span data-ttu-id="23c40-247">U.S. Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="23c40-247">U.S. Driver's License Number</span></span>
- <span data-ttu-id="23c40-248">U.S. Individual Taxpayer Identification Number (ITIN)</span><span class="sxs-lookup"><span data-stu-id="23c40-248">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="23c40-249">U.S. Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="23c40-249">U.S. Social Security Number (SSN)</span></span>

<span data-ttu-id="23c40-250">Observera att anpassade typer av känslig information även stöds för DLP-principtips, utöver de för in visna typerna av känslig information.</span><span class="sxs-lookup"><span data-stu-id="23c40-250">Please note that custom sensitive information types are also supported for DLP policy tips in addition to the above out-of-the-box sensitive information types.</span></span>

## <a name="data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="23c40-251">Skydd mot dataförlust i Slutpunkten stöder principtips för endast vissa typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="23c40-251">Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types</span></span>

<span data-ttu-id="23c40-252">Listan över inringningstyper för känslig information som identifieras i dokument som lagras på slutpunktsenheter är följande:</span><span class="sxs-lookup"><span data-stu-id="23c40-252">The list of out-of-the-box sensitive information types that will be detected in documents residing on endpoint devices are the following :</span></span>

- <span data-ttu-id="23c40-253">ABA-routningsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-253">ABA Routing Number</span></span> 
- <span data-ttu-id="23c40-254">Argentina National Identity (DNI) Number</span><span class="sxs-lookup"><span data-stu-id="23c40-254">Argentina National Identity (DNI) Number</span></span> 
- <span data-ttu-id="23c40-255">Bank Account Number för Australien</span><span class="sxs-lookup"><span data-stu-id="23c40-255">Australia Bank Account Number</span></span> 
- <span data-ttu-id="23c40-256">Australiens medicinska kontonummer</span><span class="sxs-lookup"><span data-stu-id="23c40-256">Australia Medical Account Number</span></span> 
- <span data-ttu-id="23c40-257">Australia Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-257">Australia Passport Number</span></span> 
- <span data-ttu-id="23c40-258">Australiens skattenummer</span><span class="sxs-lookup"><span data-stu-id="23c40-258">Australia Tax File Number</span></span> 
- <span data-ttu-id="23c40-259">Australiensiska företagsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-259">Australian Business Number</span></span> 
- <span data-ttu-id="23c40-260">Australiensiska företags nummer</span><span class="sxs-lookup"><span data-stu-id="23c40-260">Australian Company Number</span></span> 
- <span data-ttu-id="23c40-261">Österrikes registreringsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-261">Austria Driver's License Number</span></span> 
- <span data-ttu-id="23c40-262">Österrike-identitetskort</span><span class="sxs-lookup"><span data-stu-id="23c40-262">Austria Identity Card</span></span> 
- <span data-ttu-id="23c40-263">Österrike Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-263">Austria Passport Number</span></span> 
- <span data-ttu-id="23c40-264">Österrike, social security number</span><span class="sxs-lookup"><span data-stu-id="23c40-264">Austria Social Security Number</span></span> 
- <span data-ttu-id="23c40-265">Österrike skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-265">Austria Tax Identification Number</span></span> 
- <span data-ttu-id="23c40-266">Österrike , momsregistreringsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-266">Austria Value Added Tax (VAT) Number</span></span> 
- <span data-ttu-id="23c40-267">Autentiseringsnyckel för Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="23c40-267">Azure DocumentDB Auth Key</span></span> 
- <span data-ttu-id="23c40-268">Azure IAAS-databasanslutningssträng och Azure SQL-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="23c40-268">Azure IAAS Database Connection String and Azure SQL Connection String</span></span> 
- <span data-ttu-id="23c40-269">Azure IoT-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="23c40-269">Azure IoT Connection String</span></span> 
- <span data-ttu-id="23c40-270">Lösenord för Inställning av Azure-publicering</span><span class="sxs-lookup"><span data-stu-id="23c40-270">Azure Publish Setting Password</span></span> 
- <span data-ttu-id="23c40-271">Azure Redis Cache-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="23c40-271">Azure Redis Cache Connection String</span></span> 
- <span data-ttu-id="23c40-272">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="23c40-272">Azure SAS</span></span> 
- <span data-ttu-id="23c40-273">Azure Service Bus Connection String</span><span class="sxs-lookup"><span data-stu-id="23c40-273">Azure Service Bus Connection String</span></span> 
- <span data-ttu-id="23c40-274">Azure Storage Account Key</span><span class="sxs-lookup"><span data-stu-id="23c40-274">Azure Storage Account Key</span></span> 
- <span data-ttu-id="23c40-275">Azure Storage Account Key (generic)</span><span class="sxs-lookup"><span data-stu-id="23c40-275">Azure Storage Account Key (Generic)</span></span> 
- <span data-ttu-id="23c40-276">Belgien Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="23c40-276">Belgium Driver's License Number</span></span> 
- <span data-ttu-id="23c40-277">Belgiens nationalnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-277">Belgium National Number</span></span> 
- <span data-ttu-id="23c40-278">Belgien Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-278">Belgium Passport Number</span></span> 
- <span data-ttu-id="23c40-279">Belgium Value Added Tax Number</span><span class="sxs-lookup"><span data-stu-id="23c40-279">Belgium Value Added Tax Number</span></span> 
- <span data-ttu-id="23c40-280">Brasilien CPF-nummer</span><span class="sxs-lookup"><span data-stu-id="23c40-280">Brazil CPF Number</span></span> 
- <span data-ttu-id="23c40-281">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="23c40-281">Brazil Legal Entity Number (CNPJ)</span></span> 
- <span data-ttu-id="23c40-282">Brazil National ID Card (RG)</span><span class="sxs-lookup"><span data-stu-id="23c40-282">Brazil National ID Card (RG)</span></span> 
- <span data-ttu-id="23c40-283">Bulgariens registreringsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-283">Bulgaria Driver's License Number</span></span> 
- <span data-ttu-id="23c40-284">Bulgarien Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-284">Bulgaria Passport Number</span></span> 
- <span data-ttu-id="23c40-285">Bulgariens enhetliga civilnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-285">Bulgaria Uniform Civil Number</span></span> 
- <span data-ttu-id="23c40-286">Bank Account Number för Kanada</span><span class="sxs-lookup"><span data-stu-id="23c40-286">Canada Bank Account Number</span></span> 
- <span data-ttu-id="23c40-287">Kanadas driver's License Number</span><span class="sxs-lookup"><span data-stu-id="23c40-287">Canada Driver's License Number</span></span> 
- <span data-ttu-id="23c40-288">Canada Health Service Number</span><span class="sxs-lookup"><span data-stu-id="23c40-288">Canada Health Service Number</span></span> 
- <span data-ttu-id="23c40-289">Canada Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-289">Canada Passport Number</span></span> 
- <span data-ttu-id="23c40-290">Canada Personal Health Identification Number (PHIN)</span><span class="sxs-lookup"><span data-stu-id="23c40-290">Canada Personal Health Identification Number (PHIN)</span></span> 
- <span data-ttu-id="23c40-291">Canada Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="23c40-291">Canada Social Insurance Number</span></span> 
- <span data-ttu-id="23c40-292">Chile Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="23c40-292">Chile Identity Card Number</span></span> 
- <span data-ttu-id="23c40-293">China Resident Identity Card (Folkrepubliken Kina) Nummer</span><span class="sxs-lookup"><span data-stu-id="23c40-293">China Resident Identity Card (PRC) Number</span></span> 
- <span data-ttu-id="23c40-294">Kreditkortsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-294">Credit Card Number</span></span> 
- <span data-ttu-id="23c40-295">Kroatiens licensnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-295">Croatia Driver's License Number</span></span> 
- <span data-ttu-id="23c40-296">Kroatiens identitetskortsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-296">Croatia Identity Card Number</span></span> 
- <span data-ttu-id="23c40-297">Kroatiens National ID-kortnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-297">Croatia National ID Card Number</span></span> 
- <span data-ttu-id="23c40-298">Kroatien Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-298">Croatia Passport Number</span></span> 
- <span data-ttu-id="23c40-299">Kroatiens OIB-nummer (Personal Identification)</span><span class="sxs-lookup"><span data-stu-id="23c40-299">Croatia Personal Identification (OIB) Number</span></span> 
- <span data-ttu-id="23c40-300">CSCAN-AZURE0060 Signatur för delat åtkomstkonto för Azure-lagring</span><span class="sxs-lookup"><span data-stu-id="23c40-300">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span></span> 
- <span data-ttu-id="23c40-301">CSCAN-GENERAL0140 allmän symmetrisk nyckel</span><span class="sxs-lookup"><span data-stu-id="23c40-301">CSCAN-GENERAL0140 General Symmetric Key</span></span> 
- <span data-ttu-id="23c40-302">Cyperns drivrutinslicensnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-302">Cyprus Driver's License Number</span></span> 
- <span data-ttu-id="23c40-303">Cypern-identitetskort</span><span class="sxs-lookup"><span data-stu-id="23c40-303">Cyprus Identity Card</span></span> 
- <span data-ttu-id="23c40-304">Cypern Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-304">Cyprus Passport Number</span></span> 
- <span data-ttu-id="23c40-305">Cyperns skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-305">Cyprus Tax Identification Number</span></span> 
- <span data-ttu-id="23c40-306">Tjeckiska driver's License Number</span><span class="sxs-lookup"><span data-stu-id="23c40-306">Czech Driver's License Number</span></span> 
- <span data-ttu-id="23c40-307">Tjeckiska Personliga identitetsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-307">Czech Personal Identity Number</span></span> 
- <span data-ttu-id="23c40-308">Tjeckien Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-308">Czech Republic Passport Number</span></span> 
- <span data-ttu-id="23c40-309">Danmarks körkortsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-309">Denmark Driver's License Number</span></span> 
- <span data-ttu-id="23c40-310">Danmark Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-310">Denmark Passport Number</span></span> 
- <span data-ttu-id="23c40-311">Danmarks personliga id-nummer</span><span class="sxs-lookup"><span data-stu-id="23c40-311">Denmark Personal Identification Number</span></span> 
- <span data-ttu-id="23c40-312">Tvingande Enforcement Agency (DEA) Number</span><span class="sxs-lookup"><span data-stu-id="23c40-312">Drug Enforcement Agency (DEA) Number</span></span> 
- <span data-ttu-id="23c40-313">Estlands licensnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-313">Estonia Driver's License Number</span></span> 
- <span data-ttu-id="23c40-314">Estland Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-314">Estonia Passport Number</span></span> 
- <span data-ttu-id="23c40-315">Estland – personidentifieringskod</span><span class="sxs-lookup"><span data-stu-id="23c40-315">Estonia Personal Identification Code</span></span> 
- <span data-ttu-id="23c40-316">Betalkortsnummer (EU)</span><span class="sxs-lookup"><span data-stu-id="23c40-316">EU Debit Card Number</span></span> 
- <span data-ttu-id="23c40-317">EU:s körkortsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-317">EU Driver's License Number</span></span> 
- <span data-ttu-id="23c40-318">EU National Identification Number</span><span class="sxs-lookup"><span data-stu-id="23c40-318">EU National Identification Number</span></span> 
- <span data-ttu-id="23c40-319">EU Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-319">EU Passport Number</span></span> 
- <span data-ttu-id="23c40-320">SOCIAL SECURITY Number (SSN) eller motsvarande ID</span><span class="sxs-lookup"><span data-stu-id="23c40-320">EU Social Security Number (SSN) or Equivalent ID</span></span> 
- <span data-ttu-id="23c40-321">EU:s skatteidentifieringsnummer (TIN)</span><span class="sxs-lookup"><span data-stu-id="23c40-321">EU Tax Identification Number (TIN)</span></span> 
- <span data-ttu-id="23c40-322">Finland Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="23c40-322">Finland Driver's License Number</span></span> 
- <span data-ttu-id="23c40-323">Finland European Health Insurance Number</span><span class="sxs-lookup"><span data-stu-id="23c40-323">Finland European Health Insurance Number</span></span> 
- <span data-ttu-id="23c40-324">Finlands national-ID</span><span class="sxs-lookup"><span data-stu-id="23c40-324">Finland National ID</span></span> 
- <span data-ttu-id="23c40-325">Finland Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-325">Finland Passport Number</span></span> 
- <span data-ttu-id="23c40-326">Frankrikes licensnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-326">France Driver's License Number</span></span> 
- <span data-ttu-id="23c40-327">France Health Insurance Number</span><span class="sxs-lookup"><span data-stu-id="23c40-327">France Health Insurance Number</span></span> 
- <span data-ttu-id="23c40-328">France National ID Card (CNI)</span><span class="sxs-lookup"><span data-stu-id="23c40-328">France National ID Card (CNI)</span></span> 
- <span data-ttu-id="23c40-329">France Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-329">France Passport Number</span></span> 
- <span data-ttu-id="23c40-330">France Social Security Number (INSEE)</span><span class="sxs-lookup"><span data-stu-id="23c40-330">France Social Security Number (INSEE)</span></span> 
- <span data-ttu-id="23c40-331">France Tax Identification Number (numéro SPI.)</span><span class="sxs-lookup"><span data-stu-id="23c40-331">France Tax Identification Number (numéro SPI.)</span></span> 
- <span data-ttu-id="23c40-332">France Value Added Tax Number</span><span class="sxs-lookup"><span data-stu-id="23c40-332">France Value Added Tax Number</span></span> 
- <span data-ttu-id="23c40-333">Tyskt körkortsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-333">German Driver's License Number</span></span> 
- <span data-ttu-id="23c40-334">Tyska Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-334">German Passport Number</span></span> 
- <span data-ttu-id="23c40-335">Id Card Number för Tyskland</span><span class="sxs-lookup"><span data-stu-id="23c40-335">Germany Identity Card Number</span></span> 
- <span data-ttu-id="23c40-336">Tysklands skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-336">Germany Tax Identification Number</span></span> 
- <span data-ttu-id="23c40-337">Värdeskattenummer för Tyskland</span><span class="sxs-lookup"><span data-stu-id="23c40-337">Germany Value Added Tax Number</span></span> 
- <span data-ttu-id="23c40-338">Greklands körkortsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-338">Greece Driver's License Number</span></span> 
- <span data-ttu-id="23c40-339">Greklands national-ID-kort</span><span class="sxs-lookup"><span data-stu-id="23c40-339">Greece National ID Card</span></span> 
- <span data-ttu-id="23c40-340">Greklands passnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-340">Greece Passport Number</span></span> 
- <span data-ttu-id="23c40-341">Greklands social securitynummer (AMKA)</span><span class="sxs-lookup"><span data-stu-id="23c40-341">Greece Social Security Number (AMKA)</span></span> 
- <span data-ttu-id="23c40-342">Grekiska skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-342">Greek Tax identification Number</span></span> 
- <span data-ttu-id="23c40-343">Hong Kong Identity Card (HKID)-nummer</span><span class="sxs-lookup"><span data-stu-id="23c40-343">Hong Kong Identity Card (HKID) Number</span></span> 
- <span data-ttu-id="23c40-344">Ungerska social security number (TAD)</span><span class="sxs-lookup"><span data-stu-id="23c40-344">Hungarian Social Security Number (TAJ)</span></span> 
- <span data-ttu-id="23c40-345">Ungerska nummer med moms</span><span class="sxs-lookup"><span data-stu-id="23c40-345">Hungarian Value Added Tax Number</span></span> 
- <span data-ttu-id="23c40-346">Ungerns registreringsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-346">Hungary Driver's License Number</span></span> 
- <span data-ttu-id="23c40-347">Ungern Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-347">Hungary Passport Number</span></span> 
- <span data-ttu-id="23c40-348">Ungerns personliga id-nummer</span><span class="sxs-lookup"><span data-stu-id="23c40-348">Hungary Personal Identification Number</span></span> 
- <span data-ttu-id="23c40-349">Ungerns skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-349">Hungary Tax identification Number</span></span> 
- <span data-ttu-id="23c40-350">Indiens permanenta kontonummer (PAN)</span><span class="sxs-lookup"><span data-stu-id="23c40-350">India Permanent Account Number (PAN)</span></span> 
- <span data-ttu-id="23c40-351">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="23c40-351">India Unique Identification (Aadhaar) Number</span></span> 
- <span data-ttu-id="23c40-352">Indonesia Identity Card-nummer (KTP)</span><span class="sxs-lookup"><span data-stu-id="23c40-352">Indonesia Identity Card (KTP) Number</span></span> 
- <span data-ttu-id="23c40-353">International Banking Account Number (IBAN)</span><span class="sxs-lookup"><span data-stu-id="23c40-353">International Banking Account Number (IBAN)</span></span> 
- <span data-ttu-id="23c40-354">Internationell klassificering av avnärende (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="23c40-354">International Classification of Diseases (ICD-10-CM)</span></span> 
- <span data-ttu-id="23c40-355">Internationell klassificering av tidsklassificering (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="23c40-355">International Classification of Diseases (ICD-9-CM)</span></span> 
- <span data-ttu-id="23c40-356">IP-adress</span><span class="sxs-lookup"><span data-stu-id="23c40-356">IP Address</span></span> 
- <span data-ttu-id="23c40-357">Ireland Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="23c40-357">Ireland Driver's License Number</span></span> 
- <span data-ttu-id="23c40-358">Ireland Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-358">Ireland Passport Number</span></span> 
- <span data-ttu-id="23c40-359">Ireland Personal Public Service -nummer (PPS)</span><span class="sxs-lookup"><span data-stu-id="23c40-359">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="23c40-360">Israels bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="23c40-360">Israel Bank Account Number</span></span> 
- <span data-ttu-id="23c40-361">Israels national-ID</span><span class="sxs-lookup"><span data-stu-id="23c40-361">Israel National ID</span></span> 
- <span data-ttu-id="23c40-362">Italiens licensnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-362">Italy Driver's License Number</span></span> 
- <span data-ttu-id="23c40-363">Italiens räkenskapskod</span><span class="sxs-lookup"><span data-stu-id="23c40-363">Italy Fiscal Code</span></span> 
- <span data-ttu-id="23c40-364">Italy Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-364">Italy Passport Number</span></span> 
- <span data-ttu-id="23c40-365">Italy Value Added Tax Number</span><span class="sxs-lookup"><span data-stu-id="23c40-365">Italy Value Added Tax Number</span></span> 
- <span data-ttu-id="23c40-366">Japan Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="23c40-366">Japan Bank Account Number</span></span> 
- <span data-ttu-id="23c40-367">Japan Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="23c40-367">Japan Driver's License Number</span></span> 
- <span data-ttu-id="23c40-368">Japan Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-368">Japan Passport Number</span></span> 
- <span data-ttu-id="23c40-369">Invånarregistreringsnummer för Japan</span><span class="sxs-lookup"><span data-stu-id="23c40-369">Japan Resident Registration Number</span></span> 
- <span data-ttu-id="23c40-370">Japan Social Insurance Number (SIN)</span><span class="sxs-lookup"><span data-stu-id="23c40-370">Japan Social Insurance Number (SIN)</span></span> 
- <span data-ttu-id="23c40-371">Japanska My Number Corporate</span><span class="sxs-lookup"><span data-stu-id="23c40-371">Japanese My Number Corporate</span></span> 
- <span data-ttu-id="23c40-372">Japanska, Mitt nummer Personligt</span><span class="sxs-lookup"><span data-stu-id="23c40-372">Japanese My Number Personal</span></span> 
- <span data-ttu-id="23c40-373">Japanska Residence Card Number</span><span class="sxs-lookup"><span data-stu-id="23c40-373">Japanese Residence Card Number</span></span> 
- <span data-ttu-id="23c40-374">Lettlands drivrutinslicensnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-374">Latvia Driver's License Number</span></span> 
- <span data-ttu-id="23c40-375">Lettlands passport number</span><span class="sxs-lookup"><span data-stu-id="23c40-375">Latvia Passport Number</span></span> 
- <span data-ttu-id="23c40-376">Personlig kod för Lettland</span><span class="sxs-lookup"><span data-stu-id="23c40-376">Latvia Personal Code</span></span> 
- <span data-ttu-id="23c40-377">Litauens licensnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-377">Lithuania Driver's License Number</span></span> 
- <span data-ttu-id="23c40-378">Litauen Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-378">Lithuania Passport Number</span></span> 
- <span data-ttu-id="23c40-379">Litauen – personlig kod</span><span class="sxs-lookup"><span data-stu-id="23c40-379">Lithuania Personal Code</span></span> 
- <span data-ttu-id="23c40-380">Luxemburg-drivrutinens licensnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-380">Luxemburg Driver's License Number</span></span> 
- <span data-ttu-id="23c40-381">Luxemburg National Identification Number (naturliga personer)</span><span class="sxs-lookup"><span data-stu-id="23c40-381">Luxemburg National Identification Number (Natural persons)</span></span> 
- <span data-ttu-id="23c40-382">Luxemburg National Identification Number (icke-naturliga personer)</span><span class="sxs-lookup"><span data-stu-id="23c40-382">Luxemburg National Identification Number (Non-natural persons)</span></span> 
- <span data-ttu-id="23c40-383">Luxemburg Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-383">Luxemburg Passport Number</span></span> 
- <span data-ttu-id="23c40-384">Malaysia Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="23c40-384">Malaysia Identity Card Number</span></span> 
- <span data-ttu-id="23c40-385">Malta Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="23c40-385">Malta Driver's License Number</span></span> 
- <span data-ttu-id="23c40-386">Malta-identitetskortsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-386">Malta Identity Card Number</span></span> 
- <span data-ttu-id="23c40-387">Malta Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-387">Malta Passport Number</span></span> 
- <span data-ttu-id="23c40-388">Maltas skattenummer</span><span class="sxs-lookup"><span data-stu-id="23c40-388">Malta Tax ID Number</span></span> 
- <span data-ttu-id="23c40-389">Nederländska medborgares servicenummer (BSN)</span><span class="sxs-lookup"><span data-stu-id="23c40-389">Netherlands Citizen's Service (BSN) Number</span></span> 
- <span data-ttu-id="23c40-390">Nederländska driver's License Number</span><span class="sxs-lookup"><span data-stu-id="23c40-390">Netherlands Driver's License Number</span></span> 
- <span data-ttu-id="23c40-391">Nederländerna Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-391">Netherlands Passport Number</span></span> 
- <span data-ttu-id="23c40-392">Nederländska skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-392">Netherlands Tax Identification Number</span></span> 
- <span data-ttu-id="23c40-393">Nederländska värdeskattenummer</span><span class="sxs-lookup"><span data-stu-id="23c40-393">Netherlands Value Added Tax Number</span></span> 
- <span data-ttu-id="23c40-394">Bankkontonummer för Nya Zeeland</span><span class="sxs-lookup"><span data-stu-id="23c40-394">New Zealand bank account number</span></span> 
- <span data-ttu-id="23c40-395">New Zealand Driver License Number</span><span class="sxs-lookup"><span data-stu-id="23c40-395">New Zealand Driver License Number</span></span> 
- <span data-ttu-id="23c40-396">New Zealand Inland Revenue number</span><span class="sxs-lookup"><span data-stu-id="23c40-396">New Zealand Inland Revenue number</span></span> 
- <span data-ttu-id="23c40-397">New Zealand Ministry of Health Number</span><span class="sxs-lookup"><span data-stu-id="23c40-397">New Zealand Ministry of Health Number</span></span> 
- <span data-ttu-id="23c40-398">New Zealand Social Enl. Nummer</span><span class="sxs-lookup"><span data-stu-id="23c40-398">New Zealand Social Welfare Number</span></span> 
- <span data-ttu-id="23c40-399">Norges identitetsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-399">Norway Identity Number</span></span> 
- <span data-ttu-id="23c40-400">Philippines Unified Multi-Purpose ID Number</span><span class="sxs-lookup"><span data-stu-id="23c40-400">Philippines Unified Multi-Purpose ID Number</span></span> 
- <span data-ttu-id="23c40-401">Polens licensnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-401">Poland Driver's License Number</span></span> 
- <span data-ttu-id="23c40-402">Polens identitetskort</span><span class="sxs-lookup"><span data-stu-id="23c40-402">Poland Identity Card</span></span> 
- <span data-ttu-id="23c40-403">Polens National ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="23c40-403">Poland National ID (PESEL)</span></span> 
- <span data-ttu-id="23c40-404">Polen-pass</span><span class="sxs-lookup"><span data-stu-id="23c40-404">Poland Passport</span></span> 
- <span data-ttu-id="23c40-405">Polens skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-405">Poland Tax Identification Number</span></span> 
- <span data-ttu-id="23c40-406">Polska REGON-nummer</span><span class="sxs-lookup"><span data-stu-id="23c40-406">Polish REGON Number</span></span> 
- <span data-ttu-id="23c40-407">Portugal, kreditkortsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-407">Portugal Citizen Card Number</span></span> 
- <span data-ttu-id="23c40-408">Portugal Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="23c40-408">Portugal Driver's License Number</span></span> 
- <span data-ttu-id="23c40-409">Portugal Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-409">Portugal Passport Number</span></span> 
- <span data-ttu-id="23c40-410">Portugals skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-410">Portugal Tax Identification Number</span></span> 
- <span data-ttu-id="23c40-411">Rumäniens registreringsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-411">Romania Driver's License Number</span></span> 
- <span data-ttu-id="23c40-412">Rumänien Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-412">Romania Passport Number</span></span> 
- <span data-ttu-id="23c40-413">Rumäniens personliga numeriska kod (CNP)</span><span class="sxs-lookup"><span data-stu-id="23c40-413">Romania Personal Numerical Code (CNP)</span></span> 
- <span data-ttu-id="23c40-414">Ryska passnummer (inrikes)</span><span class="sxs-lookup"><span data-stu-id="23c40-414">Russian Passport Number (Domestic)</span></span> 
- <span data-ttu-id="23c40-415">Ryska Passport Number (internationellt)</span><span class="sxs-lookup"><span data-stu-id="23c40-415">Russian Passport Number (International)</span></span> 
- <span data-ttu-id="23c40-416">Saudiarabiens national-ID</span><span class="sxs-lookup"><span data-stu-id="23c40-416">Saudi Arabia National ID</span></span> 
- <span data-ttu-id="23c40-417">Singapore National Registration Identity Card (NRIC) Number</span><span class="sxs-lookup"><span data-stu-id="23c40-417">Singapore National Registration Identity Card (NRIC) Number</span></span> 
- <span data-ttu-id="23c40-418">Slovakiens licensnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-418">Slovakia Driver's License Number</span></span> 
- <span data-ttu-id="23c40-419">Slovakien Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-419">Slovakia Passport Number</span></span> 
- <span data-ttu-id="23c40-420">Slovakiens personliga nummer</span><span class="sxs-lookup"><span data-stu-id="23c40-420">Slovakia Personal Number</span></span> 
- <span data-ttu-id="23c40-421">Sloveniens körkortsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-421">Slovenia Driver's License Number</span></span> 
- <span data-ttu-id="23c40-422">Slovenien Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-422">Slovenia Passport Number</span></span> 
- <span data-ttu-id="23c40-423">Sloveniens skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-423">Slovenia Tax Identification Number</span></span> 
- <span data-ttu-id="23c40-424">Slovenska unik master number</span><span class="sxs-lookup"><span data-stu-id="23c40-424">Slovenia Unique Master Citizen Number</span></span> 
- <span data-ttu-id="23c40-425">South Africa Identification Number</span><span class="sxs-lookup"><span data-stu-id="23c40-425">South Africa Identification Number</span></span> 
- <span data-ttu-id="23c40-426">Sydkoreas invånarregistreringsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-426">South Korea Resident Registration Number</span></span> 
- <span data-ttu-id="23c40-427">Spanien DNI</span><span class="sxs-lookup"><span data-stu-id="23c40-427">Spain DNI</span></span> 
- <span data-ttu-id="23c40-428">Spaniens licensnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-428">Spain Driver's License Number</span></span> 
- <span data-ttu-id="23c40-429">Spain Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-429">Spain Passport Number</span></span> 
- <span data-ttu-id="23c40-430">Spain Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="23c40-430">Spain Social Security Number (SSN)</span></span> 
- <span data-ttu-id="23c40-431">Spaniens skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-431">Spain Tax Identification Number</span></span> 
- <span data-ttu-id="23c40-432">SQL Server-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="23c40-432">SQL Server Connection String</span></span> 
- <span data-ttu-id="23c40-433">Sverige driver's License Number</span><span class="sxs-lookup"><span data-stu-id="23c40-433">Sweden Driver's License Number</span></span> 
- <span data-ttu-id="23c40-434">National ID för Sverige</span><span class="sxs-lookup"><span data-stu-id="23c40-434">Sweden National ID</span></span> 
- <span data-ttu-id="23c40-435">Sverige Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-435">Sweden Passport Number</span></span> 
- <span data-ttu-id="23c40-436">Skatteidentifieringsnummer i Sverige</span><span class="sxs-lookup"><span data-stu-id="23c40-436">Sweden Tax Identification Number</span></span> 
- <span data-ttu-id="23c40-437">SWIFT-kod</span><span class="sxs-lookup"><span data-stu-id="23c40-437">SWIFT Code</span></span> 
- <span data-ttu-id="23c40-438">Swiss Social Security Number AHV</span><span class="sxs-lookup"><span data-stu-id="23c40-438">Swiss Social Security Number AHV</span></span> 
- <span data-ttu-id="23c40-439">Taiwan National ID</span><span class="sxs-lookup"><span data-stu-id="23c40-439">Taiwan National ID</span></span> 
- <span data-ttu-id="23c40-440">Taiwan Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-440">Taiwan Passport Number</span></span> 
- <span data-ttu-id="23c40-441">Taiwan Resident Certificate (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="23c40-441">Taiwan Resident Certificate (ARC/TARC)</span></span> 
- <span data-ttu-id="23c40-442">Identifieringskod för thailändska</span><span class="sxs-lookup"><span data-stu-id="23c40-442">Thai Population Identification Code</span></span> 
- <span data-ttu-id="23c40-443">Turkiska National Identification Number</span><span class="sxs-lookup"><span data-stu-id="23c40-443">Turkish National Identification number</span></span> 
- <span data-ttu-id="23c40-444">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="23c40-444">U.K.</span></span> <span data-ttu-id="23c40-445">Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="23c40-445">Driver's License Number</span></span> 
- <span data-ttu-id="23c40-446">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="23c40-446">U.K.</span></span> <span data-ttu-id="23c40-447">E-nummer för att samla in</span><span class="sxs-lookup"><span data-stu-id="23c40-447">Electoral Roll Number</span></span> 
- <span data-ttu-id="23c40-448">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="23c40-448">U.K.</span></span> <span data-ttu-id="23c40-449">National Health Service Number</span><span class="sxs-lookup"><span data-stu-id="23c40-449">National Health Service Number</span></span> 
- <span data-ttu-id="23c40-450">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="23c40-450">U.K.</span></span> <span data-ttu-id="23c40-451">National Insurance Number (NINO)</span><span class="sxs-lookup"><span data-stu-id="23c40-451">National Insurance Number (NINO)</span></span> 
- <span data-ttu-id="23c40-452">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="23c40-452">U.K.</span></span> <span data-ttu-id="23c40-453">Unique Taxpayer-referensnummer</span><span class="sxs-lookup"><span data-stu-id="23c40-453">Unique Taxpayer Reference Number</span></span> 
- <span data-ttu-id="23c40-454">U.S. / Storbritannien</span><span class="sxs-lookup"><span data-stu-id="23c40-454">U.S. / U.K.</span></span> <span data-ttu-id="23c40-455">Passport Number</span><span class="sxs-lookup"><span data-stu-id="23c40-455">Passport Number</span></span> 
- <span data-ttu-id="23c40-456">U.S. Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="23c40-456">U.S. Bank Account Number</span></span> 
- <span data-ttu-id="23c40-457">U.S. Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="23c40-457">U.S. Driver's License Number</span></span> 
- <span data-ttu-id="23c40-458">U.S. Individual Taxpayer Identification Number (ITIN)</span><span class="sxs-lookup"><span data-stu-id="23c40-458">U.S. Individual Taxpayer Identification Number (ITIN)</span></span> 
- <span data-ttu-id="23c40-459">U.S. Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="23c40-459">U.S. Social Security Number (SSN)</span></span> 
- <span data-ttu-id="23c40-460">Ukraina Passport Number (inrikes)</span><span class="sxs-lookup"><span data-stu-id="23c40-460">Ukraine Passport Number (Domestic)</span></span> 
- <span data-ttu-id="23c40-461">Ukraina Passport Number (internationellt)</span><span class="sxs-lookup"><span data-stu-id="23c40-461">Ukraine Passport Number (International)</span></span> 
 
<span data-ttu-id="23c40-462">Observera att anpassade typer av känslig information också identifieras, utöver de för insmådde typerna av känslig information</span><span class="sxs-lookup"><span data-stu-id="23c40-462">Please note that custom sensitive information types will also be detected in addition to the above out-of-the-box sensitive information types</span></span>

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a><span data-ttu-id="23c40-463">Tips om stödmatris för DLP-principen i Microsoft-appar</span><span class="sxs-lookup"><span data-stu-id="23c40-463">Support Matrix for DLP policy tips across Microsoft apps</span></span>

|<span data-ttu-id="23c40-464">**App och plattform**</span><span class="sxs-lookup"><span data-stu-id="23c40-464">**App and platform**</span></span>|<span data-ttu-id="23c40-465">**Stöd för DLP-principtips**</span><span class="sxs-lookup"><span data-stu-id="23c40-465">**DLP policy tip support**</span></span>|<span data-ttu-id="23c40-466">**Typer av känslig information som stöds**</span><span class="sxs-lookup"><span data-stu-id="23c40-466">**Sensitive information types supported**</span></span>|<span data-ttu-id="23c40-467">**Predikat och åtgärder som stöds**</span><span class="sxs-lookup"><span data-stu-id="23c40-467">**Predicates and actions supported**</span></span>|<span data-ttu-id="23c40-468">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="23c40-468">**Comments**</span></span>|
|:--|:--|:--|:--|:--|
|<span data-ttu-id="23c40-469">**Outlook Web Access**</span><span class="sxs-lookup"><span data-stu-id="23c40-469">**Outlook Web Access**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="23c40-470">Alla</span><span class="sxs-lookup"><span data-stu-id="23c40-470">All</span></span>|<span data-ttu-id="23c40-471">Delmängd</span><span class="sxs-lookup"><span data-stu-id="23c40-471">Subset</span></span>|<span data-ttu-id="23c40-472">Se [referens för policytips för skydd mot dataförlust](#data-loss-prevention-policy-tips-reference)</span><span class="sxs-lookup"><span data-stu-id="23c40-472">See [Data Loss Prevention policy tips reference](#data-loss-prevention-policy-tips-reference)</span></span>|
|<span data-ttu-id="23c40-473">**Outlook Win32 (Outlook 2013 och vidare)**</span><span class="sxs-lookup"><span data-stu-id="23c40-473">**Outlook Win32 (Outlook 2013 and beyond)**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="23c40-474">Delmängd</span><span class="sxs-lookup"><span data-stu-id="23c40-474">Subset</span></span>|<span data-ttu-id="23c40-475">Delmängd</span><span class="sxs-lookup"><span data-stu-id="23c40-475">Subset</span></span>|<span data-ttu-id="23c40-476">Se [Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) och senare med stöd för att visa principtips för bara vissa villkor och undantag, [och Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types) och senare stöder visning av principtips för endast vissa typer av känslig information för information om stöd för typer av känslig information och de DLP-villkor och åtgärder som stöds för att visa DLP-principtips i Outlook Win32.</span><span class="sxs-lookup"><span data-stu-id="23c40-476">See [Outlook 2013 and later supports showing policy tips for only some conditions and exceptions](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) and [Outlook 2013 and later supports showing policy tips for only some sensitive information types](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types) for details on support for sensitive information types and DLP conditions and actions supported for showing DLP policy tips on Outlook Win32.</span></span>|
|<span data-ttu-id="23c40-477">**Outlook Mobile (iOS, Android)/Outlook Mac**</span><span class="sxs-lookup"><span data-stu-id="23c40-477">**Outlook Mobile (iOS, Android)/Outlook Mac**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="23c40-478">Inga</span><span class="sxs-lookup"><span data-stu-id="23c40-478">None</span></span>|<span data-ttu-id="23c40-479">Inga</span><span class="sxs-lookup"><span data-stu-id="23c40-479">None</span></span>|<span data-ttu-id="23c40-480">Tips för DLP-policyer stöds inte i Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="23c40-480">DLP policy tips are not supported on Outlook mobile</span></span>|
|<span data-ttu-id="23c40-481">**Sharepoint Online/One Drive för företag-webbklient**</span><span class="sxs-lookup"><span data-stu-id="23c40-481">**Sharepoint Online/One Drive for Business Web client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="23c40-482">Alla</span><span class="sxs-lookup"><span data-stu-id="23c40-482">All</span></span>|<span data-ttu-id="23c40-483">Alla SPO/ODB-predikat och åtgärder i DLP</span><span class="sxs-lookup"><span data-stu-id="23c40-483">All SPO/ODB predicates and actions in DLP</span></span>||
|<span data-ttu-id="23c40-484">**Sharepoint Win32/ One Drive för företag Win32-klient**</span><span class="sxs-lookup"><span data-stu-id="23c40-484">**Sharepoint Win32/ One Drive for Business Win32 client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="23c40-485">Inga</span><span class="sxs-lookup"><span data-stu-id="23c40-485">None</span></span>|<span data-ttu-id="23c40-486">Inga</span><span class="sxs-lookup"><span data-stu-id="23c40-486">None</span></span>|<span data-ttu-id="23c40-487">Tips för DLP-princip stöds inte i Sharepoint- eller OneDrive-klientprogram</span><span class="sxs-lookup"><span data-stu-id="23c40-487">DLP policy tips are not supported on Sharepoint or OneDrive desktop client apps</span></span>|
|<span data-ttu-id="23c40-488">**Word, Excel, Powerpoint Web Client**</span><span class="sxs-lookup"><span data-stu-id="23c40-488">**Word, Excel, Powerpoint Web Client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="23c40-489">Alla</span><span class="sxs-lookup"><span data-stu-id="23c40-489">All</span></span>|<span data-ttu-id="23c40-490">Alla SPO/ODB-predikat och åtgärder i DLP</span><span class="sxs-lookup"><span data-stu-id="23c40-490">All SPO/ODB predicates and actions in DLP</span></span>|<span data-ttu-id="23c40-491">Tips för DLP-princip stöds om dokumentet ligger på SPO- eller ODB-webbappen och DLP-principen redan har stämplats.</span><span class="sxs-lookup"><span data-stu-id="23c40-491">DLP policy tip is supported if the document is hosted on SPO or ODB web app and the DLP policy is already stamped.</span></span>|
|<span data-ttu-id="23c40-492">**Word, Excel och Powerpoint Mobile-klient**</span><span class="sxs-lookup"><span data-stu-id="23c40-492">**Word, Excel, Powerpoint Mobile Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="23c40-493">Inga</span><span class="sxs-lookup"><span data-stu-id="23c40-493">None</span></span>|<span data-ttu-id="23c40-494">Inga</span><span class="sxs-lookup"><span data-stu-id="23c40-494">None</span></span>|<span data-ttu-id="23c40-495">Tips för DLP-princip stöds inte i mobilappar för Office.</span><span class="sxs-lookup"><span data-stu-id="23c40-495">DLP policy tips are not supported in mobile apps for Office.</span></span>|
|<span data-ttu-id="23c40-496">**Teams Webb/ Teams skrivbords- / Teams Mobile/ Teams Mac**</span><span class="sxs-lookup"><span data-stu-id="23c40-496">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="23c40-497">Alla</span><span class="sxs-lookup"><span data-stu-id="23c40-497">All</span></span>|<span data-ttu-id="23c40-498">Alla Teams-predikat i DLP-princip</span><span class="sxs-lookup"><span data-stu-id="23c40-498">All Teams predicates in DLP policy</span></span>|<span data-ttu-id="23c40-499">Principtips visas när ett meddelande flaggas som "Det här meddelandet har flaggats.</span><span class="sxs-lookup"><span data-stu-id="23c40-499">Policy tips will show when a message is flagged as “This message has been flagged.</span></span> <span data-ttu-id="23c40-500">Vad kan jag göra?"</span><span class="sxs-lookup"><span data-stu-id="23c40-500">What can I do?”</span></span> <span data-ttu-id="23c40-501">När användaren klickar på länken kan han eller hon granska de typer av känslig information som upptäckts och åsidosätta eller rapportera ett problem om administratören tillåtit det. Observera att inga principtips visas för filer.</span><span class="sxs-lookup"><span data-stu-id="23c40-501">When clicking the link, the user can review the sensitive info types detected and override or report an issue if allowed by the admin. Note that no policy tips are shown for files.</span></span> <span data-ttu-id="23c40-502">När mottagaren försöker komma åt dokumentet kan de få åtkomst nekad om det inte är tillåtet.</span><span class="sxs-lookup"><span data-stu-id="23c40-502">When the recipient tries to access the document, they might get access denied if not allowed.</span></span>|
|<span data-ttu-id="23c40-503">**Win32-slutpunktsenheter**</span><span class="sxs-lookup"><span data-stu-id="23c40-503">**Win32 Endpoint Devices**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="23c40-504">Delmängd</span><span class="sxs-lookup"><span data-stu-id="23c40-504">Subset</span></span>|<span data-ttu-id="23c40-505">Alla endpoint DLP-predikat och åtgärder i DLP-princip</span><span class="sxs-lookup"><span data-stu-id="23c40-505">All Endpoint DLP predicates and actions in DLP policy</span></span>|<span data-ttu-id="23c40-506">Se [Skydd mot dataförlust i Slutpunkt som stöder principtips för endast vissa typer av känslig information](#data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types)</span><span class="sxs-lookup"><span data-stu-id="23c40-506">See [Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types](#data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types)</span></span>|
|<span data-ttu-id="23c40-507">**Mac-enheter**</span><span class="sxs-lookup"><span data-stu-id="23c40-507">**Mac devices**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="23c40-508">Inga</span><span class="sxs-lookup"><span data-stu-id="23c40-508">None</span></span>|<span data-ttu-id="23c40-509">Inga</span><span class="sxs-lookup"><span data-stu-id="23c40-509">None</span></span>|<span data-ttu-id="23c40-510">Dataförlustskydd kan inte användas på Mac-enheter idag</span><span class="sxs-lookup"><span data-stu-id="23c40-510">Data loss prevention are not enforceable on Mac devices today</span></span>|
|<span data-ttu-id="23c40-511">**Molnbaserade appar från tredje part**</span><span class="sxs-lookup"><span data-stu-id="23c40-511">**3rd party cloud apps**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="23c40-512">Inga</span><span class="sxs-lookup"><span data-stu-id="23c40-512">None</span></span>|<span data-ttu-id="23c40-513">Inga</span><span class="sxs-lookup"><span data-stu-id="23c40-513">None</span></span>|<span data-ttu-id="23c40-514">Dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="23c40-514">Data Loss Prevention</span></span>|
|<span data-ttu-id="23c40-515">**On-prem**</span><span class="sxs-lookup"><span data-stu-id="23c40-515">**On-prem**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="23c40-516">Inga</span><span class="sxs-lookup"><span data-stu-id="23c40-516">None</span></span>|<span data-ttu-id="23c40-517">Inga</span><span class="sxs-lookup"><span data-stu-id="23c40-517">None</span></span>||
|<span data-ttu-id="23c40-518">**Word, Excel, Powerpoint Win32-klient**</span><span class="sxs-lookup"><span data-stu-id="23c40-518">**Word, Excel, Powerpoint Win32 Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="23c40-519">Delmängd</span><span class="sxs-lookup"><span data-stu-id="23c40-519">Subset</span></span>|<span data-ttu-id="23c40-520">Delmängd</span><span class="sxs-lookup"><span data-stu-id="23c40-520">Subset</span></span>|<span data-ttu-id="23c40-521">Principtips för WXP-klientprogram fungerar för dokument som lagras på Sharepoint Online- eller One Drive för företag-webbplatser för alla DLP-principer som har exakt nedanstående eller en delmängd villkor eller åtgärder i DLP-principen:</span><span class="sxs-lookup"><span data-stu-id="23c40-521">Policy tips for WXP client apps will work for documents stored on Sharepoint Online or One Drive for Business Sites for all DLP policies which have exactly the below or a subset of conditions or actions in the DLP policy:</span></span></br> <ul><li><span data-ttu-id="23c40-522">Innehållet innehåller typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="23c40-522">Content contains sensitive information types</span></span></li><li><span data-ttu-id="23c40-523">Åtkomstomfattning (innehåll delas internt/externt)</span><span class="sxs-lookup"><span data-stu-id="23c40-523">Access Scope (Content is shared internally/externally)</span></span></li><li><span data-ttu-id="23c40-524">Meddela användare (principtips/användarmeddelanden)</span><span class="sxs-lookup"><span data-stu-id="23c40-524">Notify User (policy tips/user notifications)</span></span></li><li><span data-ttu-id="23c40-525">Blockera alla</span><span class="sxs-lookup"><span data-stu-id="23c40-525">Block everyone</span></span></li><li><span data-ttu-id="23c40-526">Incidentrapporter</span><span class="sxs-lookup"><span data-stu-id="23c40-526">Incident reports</span></span></li></ul></br> <span data-ttu-id="23c40-527">Om det finns andra villkor eller åtgärder visas inte DLP-principtipset för den principen i skrivbordsapparna för Word, Excel eller PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="23c40-527">If any other condition or action is present, the DLP policy tip for that policy will not appear in the desktop apps of Word, Excel or PowerPoint.</span></span>|
||||||