---
title: Referensinformation om principtips för dataförlustskydd
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
recommendations: false
description: Lär dig hur du lägger till ett principtips i en DLP-princip (Data Loss Prevention) om att de arbetar med innehåll som står i konflikt med en DLP-princip.
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 0c42569da3fcac40d3121a59f7dc004f25dd3f74
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086765"
---
# <a name="data-loss-prevention-policy-tips-reference"></a><span data-ttu-id="cb8a4-103">Referensinformation om principtips för dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="cb8a4-103">Data Loss Prevention policy tips reference</span></span>

<span data-ttu-id="cb8a4-104">Tips för DLP-Outlook i Web Access stöds för alla villkor, undantag och åtgärder som är tillämpliga för Exchange-arbetsbelastningar i en DLP-princip, förutom följande:</span><span class="sxs-lookup"><span data-stu-id="cb8a4-104">DLP policy tips in Outlook Web Access is supported for all the conditions, exceptions and actions that are applicable on Exchange workload in a DLP policy except the following:</span></span>

<span data-ttu-id="cb8a4-105">**Villkor:**</span><span class="sxs-lookup"><span data-stu-id="cb8a4-105">**Conditions:**</span></span>

- <span data-ttu-id="cb8a4-106">Sender Is</span><span class="sxs-lookup"><span data-stu-id="cb8a4-106">Sender Is</span></span>
- <span data-ttu-id="cb8a4-107">Sender Domain Is</span><span class="sxs-lookup"><span data-stu-id="cb8a4-107">Sender Domain Is</span></span>
- <span data-ttu-id="cb8a4-108">Mottagaren är medlem i</span><span class="sxs-lookup"><span data-stu-id="cb8a4-108">Recipient is a member of</span></span>
- <span data-ttu-id="cb8a4-109">Sidhuvudet innehåller ord eller fraser</span><span class="sxs-lookup"><span data-stu-id="cb8a4-109">Header contains words or phrases</span></span>
- <span data-ttu-id="cb8a4-110">Sidhuvud matchar mönster</span><span class="sxs-lookup"><span data-stu-id="cb8a4-110">Header matches patterns</span></span>
- <span data-ttu-id="cb8a4-111">Dokumentstorlek är lika med eller större än</span><span class="sxs-lookup"><span data-stu-id="cb8a4-111">Document size equals or is greater than</span></span>
- <span data-ttu-id="cb8a4-112">Meddelandetypen är</span><span class="sxs-lookup"><span data-stu-id="cb8a4-112">Message type is</span></span>
- <span data-ttu-id="cb8a4-113">Meddelandets prioritet är</span><span class="sxs-lookup"><span data-stu-id="cb8a4-113">Message importance is</span></span>
- <span data-ttu-id="cb8a4-114">Innehållsteckenuppsättning innehåller ord</span><span class="sxs-lookup"><span data-stu-id="cb8a4-114">Content character set contains words</span></span>
- <span data-ttu-id="cb8a4-115">Ämne eller brödtext innehåller ord eller fraser</span><span class="sxs-lookup"><span data-stu-id="cb8a4-115">Subject or body contains words or phrases</span></span>
- <span data-ttu-id="cb8a4-116">Mönster för ämne eller brödtext</span><span class="sxs-lookup"><span data-stu-id="cb8a4-116">Subject or body matches patterns</span></span>
- <span data-ttu-id="cb8a4-117">Innehållsteckenuppsättning innehåller ord</span><span class="sxs-lookup"><span data-stu-id="cb8a4-117">Content character set contains words</span></span>
- <span data-ttu-id="cb8a4-118">Innehåll tas emot från</span><span class="sxs-lookup"><span data-stu-id="cb8a4-118">Content is received from</span></span>
- <span data-ttu-id="cb8a4-119">Har avsändaren åsidosättt principtipset</span><span class="sxs-lookup"><span data-stu-id="cb8a4-119">Has sender overridden the policy tip</span></span>
- <span data-ttu-id="cb8a4-120">Meddelandestorlek är lika med eller större än</span><span class="sxs-lookup"><span data-stu-id="cb8a4-120">Message size equals or is greater than</span></span>
- <span data-ttu-id="cb8a4-121">Sender AD-attributet innehåller ord eller fraser</span><span class="sxs-lookup"><span data-stu-id="cb8a4-121">Sender AD attribute contains words or phrases</span></span>
- <span data-ttu-id="cb8a4-122">Ad-sender-attributet matchar mönster</span><span class="sxs-lookup"><span data-stu-id="cb8a4-122">Sender AD attribute matches patterns</span></span>
- <span data-ttu-id="cb8a4-123">Dokumentinnehållet innehåller ord eller fraser</span><span class="sxs-lookup"><span data-stu-id="cb8a4-123">Document content contains words or phrases</span></span>
- <span data-ttu-id="cb8a4-124">Dokumentinnehåll matchar mönster</span><span class="sxs-lookup"><span data-stu-id="cb8a4-124">Document content matches patterns</span></span>

<span data-ttu-id="cb8a4-125">**Åtgärder:**</span><span class="sxs-lookup"><span data-stu-id="cb8a4-125">**Actions:**</span></span>

- <span data-ttu-id="cb8a4-126">Vidarebefordra meddelandet för godkännande till avsändarens chef</span><span class="sxs-lookup"><span data-stu-id="cb8a4-126">Forward the message for approval to sender’s manager</span></span>
- <span data-ttu-id="cb8a4-127">Vidarebefordra meddelandet för godkännande till vissa godkännare</span><span class="sxs-lookup"><span data-stu-id="cb8a4-127">Forward the message for approval to specific approvers</span></span>
- <span data-ttu-id="cb8a4-128">Omdirigera meddelandet till specifika användare</span><span class="sxs-lookup"><span data-stu-id="cb8a4-128">Redirect the message to specific users</span></span>
- <span data-ttu-id="cb8a4-129">Lägga till mottagare i Rutan Till</span><span class="sxs-lookup"><span data-stu-id="cb8a4-129">Add recipients to the To Box</span></span>
- <span data-ttu-id="cb8a4-130">Lägga till mottagare i rutan Kopia</span><span class="sxs-lookup"><span data-stu-id="cb8a4-130">Add recipients to the Cc Box</span></span>
- <span data-ttu-id="cb8a4-131">Lägga till mottagare i rutan Hemlig kopia</span><span class="sxs-lookup"><span data-stu-id="cb8a4-131">Add recipients to the Bcc Box</span></span>
- <span data-ttu-id="cb8a4-132">Lägga till avsändarens chef som mottagare</span><span class="sxs-lookup"><span data-stu-id="cb8a4-132">Add the sender’s manager as recipient</span></span>
- <span data-ttu-id="cb8a4-133">Lägga till HTML-ansvarsfriskrivning</span><span class="sxs-lookup"><span data-stu-id="cb8a4-133">Add HTML disclaimer</span></span>
- <span data-ttu-id="cb8a4-134">Förbereda ämnet för e-post</span><span class="sxs-lookup"><span data-stu-id="cb8a4-134">Prepend email subject</span></span>
- <span data-ttu-id="cb8a4-135">Ta bort meddelandekryptering och rättighetsskydd i O365</span><span class="sxs-lookup"><span data-stu-id="cb8a4-135">Remove O365 Message Encryption and rights protection</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a><span data-ttu-id="cb8a4-136">Outlook 2013 och senare har stöd för att visa principtips för bara vissa villkor och undantag</span><span class="sxs-lookup"><span data-stu-id="cb8a4-136">Outlook 2013 and later supports showing policy tips for only some conditions and exceptions</span></span>

<span data-ttu-id="cb8a4-137">I Outlook 2013 och senare stöds för närvarande policytips för principer som inte innehåller några villkor eller undantag från nedanstående villkor och motsvarande undantag:</span><span class="sxs-lookup"><span data-stu-id="cb8a4-137">Currently, Outlook 2013 and later supports showing policy tips for policies which do not contain any condition or exception apart from the below mentioned conditions and corresponding exceptions :</span></span>

- <span data-ttu-id="cb8a4-138">Innehållet innehåller (fungerar endast för typer av känslig information.</span><span class="sxs-lookup"><span data-stu-id="cb8a4-138">Content contains (works only for Sensitive information types.</span></span> <span data-ttu-id="cb8a4-139">Känslighetsetiketter stöds inte)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-139">Sensitivity labels are not supported)</span></span>
- <span data-ttu-id="cb8a4-140">Innehåll delas</span><span class="sxs-lookup"><span data-stu-id="cb8a4-140">Content is shared</span></span>

<span data-ttu-id="cb8a4-141">Observera att alla villkor fungerar för e-postmeddelanden som Outlook i klientappen, där de matchar innehåll och tillämpar skyddsåtgärder på innehåll.</span><span class="sxs-lookup"><span data-stu-id="cb8a4-141">Note that all the conditions work for emails authored in Outlook client app, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="cb8a4-142">Men det går inte att visa principtips för användare för villkor som används utöver de som nämns ovan.</span><span class="sxs-lookup"><span data-stu-id="cb8a4-142">However, showing policy tips to users is not supported for any conditions that are used apart from the ones mentioned above.</span></span>

## <a name="outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="cb8a4-143">Outlook 2013 och senare samt Office-program på skrivbordet som visar principtips för endast vissa typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="cb8a4-143">Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types</span></span>

<span data-ttu-id="cb8a4-144">Följande är en lista över de in alltid använda typer av känslig information som identifieras för visning av DLP-principtips i Outlook på skrivbordet (2013 och senare) och Office-program (Word, Excel, PowerPoint) på skrivbordet:</span><span class="sxs-lookup"><span data-stu-id="cb8a4-144">The list of out-of-the-box sensitive information types that will be detected for showing DLP policy tips in Outlook on Desktop (2013 and later) and Office apps (Word, Excel, PowerPoint) on Desktop are the following :</span></span>

- <span data-ttu-id="cb8a4-145">ABA-routningsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-145">ABA Routing Number</span></span>
- <span data-ttu-id="cb8a4-146">Argentina National Identity (DNI) Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-146">Argentina National Identity (DNI) Number</span></span>
- <span data-ttu-id="cb8a4-147">Bank Account Number för Australien</span><span class="sxs-lookup"><span data-stu-id="cb8a4-147">Australia Bank Account Number</span></span>
- <span data-ttu-id="cb8a4-148">Australiens medicinska kontonummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-148">Australia Medical Account Number</span></span>
- <span data-ttu-id="cb8a4-149">Australia Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-149">Australia Passport Number</span></span>
- <span data-ttu-id="cb8a4-150">Australiens skattenummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-150">Australia Tax File Number</span></span>
- <span data-ttu-id="cb8a4-151">Autentiseringsnyckel för Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="cb8a4-151">Azure DocumentDB Auth Key</span></span>  
- <span data-ttu-id="cb8a4-152">Azure IAAS-databasanslutningssträng och Azure SQL-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="cb8a4-152">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>  
- <span data-ttu-id="cb8a4-153">Azure IoT-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="cb8a4-153">Azure IoT Connection String</span></span>  
- <span data-ttu-id="cb8a4-154">Lösenord för Inställning av Azure-publicering</span><span class="sxs-lookup"><span data-stu-id="cb8a4-154">Azure Publish Setting Password</span></span>  
- <span data-ttu-id="cb8a4-155">Azure Redis Cache-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="cb8a4-155">Azure Redis Cache Connection String</span></span>  
- <span data-ttu-id="cb8a4-156">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="cb8a4-156">Azure SAS</span></span>  
- <span data-ttu-id="cb8a4-157">Azure Service Bus-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="cb8a4-157">Azure Service Bus Connection String</span></span>  
- <span data-ttu-id="cb8a4-158">Azure Storage Kontonyckel</span><span class="sxs-lookup"><span data-stu-id="cb8a4-158">Azure Storage Account Key</span></span>  
- <span data-ttu-id="cb8a4-159">Azure Storage Kontonyckel (allmän)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-159">Azure Storage Account Key (Generic)</span></span>  
- <span data-ttu-id="cb8a4-160">Belgiens nationalnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-160">Belgium National Number</span></span>
- <span data-ttu-id="cb8a4-161">Brasilien CPF-nummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-161">Brazil CPF Number</span></span>
- <span data-ttu-id="cb8a4-162">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-162">Brazil Legal Entity Number (CNPJ)</span></span>
- <span data-ttu-id="cb8a4-163">Brazil National ID Card (RG)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-163">Brazil National ID Card (RG)</span></span>
- <span data-ttu-id="cb8a4-164">Bank Account Number för Kanada</span><span class="sxs-lookup"><span data-stu-id="cb8a4-164">Canada Bank Account Number</span></span>
- <span data-ttu-id="cb8a4-165">Kanadas driver's License Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-165">Canada Driver's License Number</span></span>
- <span data-ttu-id="cb8a4-166">Kanada Hälsotjänst Kanada</span><span class="sxs-lookup"><span data-stu-id="cb8a4-166">Canada Health Service Number</span></span>
- <span data-ttu-id="cb8a4-167">Canada Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-167">Canada Passport Number</span></span>
- <span data-ttu-id="cb8a4-168">Canada Personal Health Identification Number (PHIN)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-168">Canada Personal Health Identification Number (PHIN)</span></span>
- <span data-ttu-id="cb8a4-169">Canada Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-169">Canada Social Insurance Number</span></span>
- <span data-ttu-id="cb8a4-170">Chile Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-170">Chile Identity Card Number</span></span>
- <span data-ttu-id="cb8a4-171">China Resident Identity Card (Folkrepubliken Kina) Nummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-171">China Resident Identity Card (PRC) Number</span></span>
- <span data-ttu-id="cb8a4-172">Kreditkortsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-172">Credit Card Number</span></span>
- <span data-ttu-id="cb8a4-173">Kroatiens identitetskortsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-173">Croatia Identity Card Number</span></span>  
- <span data-ttu-id="cb8a4-174">Kroatiens OIB-nummer (Personal Identification)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-174">Croatia Personal Identification (OIB) Number</span></span>  
- <span data-ttu-id="cb8a4-175">Tjeckiska Personliga identitetsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-175">Czech Personal Identity Number</span></span>  
- <span data-ttu-id="cb8a4-176">Danmarks personliga id-nummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-176">Denmark Personal Identification Number</span></span>
- <span data-ttu-id="cb8a4-177">Tvingande Enforcement Agency (DEA) Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-177">Drug Enforcement Agency (DEA) Number</span></span>
- <span data-ttu-id="cb8a4-178">Betalkortsnummer (EU)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-178">EU Debit Card Number</span></span>
- <span data-ttu-id="cb8a4-179">EU:s körkortsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-179">EU Driver's License Number</span></span>  
- <span data-ttu-id="cb8a4-180">EU National Identification Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-180">EU National Identification Number</span></span>  
- <span data-ttu-id="cb8a4-181">EU Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-181">EU Passport Number</span></span>  
- <span data-ttu-id="cb8a4-182">SOCIAL SECURITY Number (SSN) eller motsvarande ID</span><span class="sxs-lookup"><span data-stu-id="cb8a4-182">EU Social Security Number (SSN) or Equivalent ID</span></span>  
- <span data-ttu-id="cb8a4-183">EU:s skatteidentifieringsnummer (TIN)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-183">EU Tax Identification Number (TIN)</span></span>  
- <span data-ttu-id="cb8a4-184">Finlands national-ID</span><span class="sxs-lookup"><span data-stu-id="cb8a4-184">Finland National ID</span></span>
- <span data-ttu-id="cb8a4-185">Finland Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-185">Finland Passport Number</span></span>
- <span data-ttu-id="cb8a4-186">Frankrikes licensnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-186">France Driver's License Number</span></span>
- <span data-ttu-id="cb8a4-187">France National ID Card (CNI)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-187">France National ID Card (CNI)</span></span>
- <span data-ttu-id="cb8a4-188">France Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-188">France Passport Number</span></span>
- <span data-ttu-id="cb8a4-189">France Social Security Number (INSEE)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-189">France Social Security Number (INSEE)</span></span>
- <span data-ttu-id="cb8a4-190">Tyskt körkortsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-190">German Driver's License Number</span></span>
- <span data-ttu-id="cb8a4-191">Tyska Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-191">German Passport Number</span></span>
- <span data-ttu-id="cb8a4-192">Id Card Number för Tyskland</span><span class="sxs-lookup"><span data-stu-id="cb8a4-192">Germany Identity Card Number</span></span>
- <span data-ttu-id="cb8a4-193">Greklands national-ID-kort</span><span class="sxs-lookup"><span data-stu-id="cb8a4-193">Greece National ID Card</span></span>  
- <span data-ttu-id="cb8a4-194">Hong Kong Identity Card (HKID)-nummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-194">Hong Kong Identity Card (HKID) Number</span></span>
- <span data-ttu-id="cb8a4-195">Indiens permanenta kontonummer (PAN)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-195">India Permanent Account Number (PAN)</span></span>
- <span data-ttu-id="cb8a4-196">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-196">India Unique Identification (Aadhaar) Number</span></span>
- <span data-ttu-id="cb8a4-197">Indonesia Identity Card-nummer (KTP)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-197">Indonesia Identity Card (KTP) Number</span></span>
- <span data-ttu-id="cb8a4-198">International Banking Account Number (IBAN)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-198">International Banking Account Number (IBAN)</span></span>
- <span data-ttu-id="cb8a4-199">Internationell klassificering av avnärende (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-199">International Classification of Diseases (ICD-10-CM)</span></span>  
- <span data-ttu-id="cb8a4-200">Internationell klassificering av tidsklassificering (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-200">International Classification of Diseases (ICD-9-CM)</span></span>  
- <span data-ttu-id="cb8a4-201">IP-adress</span><span class="sxs-lookup"><span data-stu-id="cb8a4-201">IP Address</span></span>
- <span data-ttu-id="cb8a4-202">Ireland Personal Public Service -nummer (PPS)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-202">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="cb8a4-203">Israels bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-203">Israel Bank Account Number</span></span>
- <span data-ttu-id="cb8a4-204">Israels national-ID</span><span class="sxs-lookup"><span data-stu-id="cb8a4-204">Israel National ID</span></span>
- <span data-ttu-id="cb8a4-205">Italiens licensnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-205">Italy Driver's License Number</span></span>
- <span data-ttu-id="cb8a4-206">Japan Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-206">Japan Bank Account Number</span></span>
- <span data-ttu-id="cb8a4-207">Japan Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-207">Japan Driver's License Number</span></span>
- <span data-ttu-id="cb8a4-208">Japan Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-208">Japan Passport Number</span></span>
- <span data-ttu-id="cb8a4-209">Invånarregistreringsnummer för Japan</span><span class="sxs-lookup"><span data-stu-id="cb8a4-209">Japan Resident Registration Number</span></span>
- <span data-ttu-id="cb8a4-210">Japan Social Insurance Number (SIN)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-210">Japan Social Insurance Number (SIN)</span></span>
- <span data-ttu-id="cb8a4-211">Japanska Residence Card Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-211">Japanese Residence Card Number</span></span>
- <span data-ttu-id="cb8a4-212">Malaysia Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-212">Malaysia Identity Card Number</span></span>
- <span data-ttu-id="cb8a4-213">Nederländska medborgares servicenummer (BSN)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-213">Netherlands Citizen's Service (BSN) Number</span></span>  
- <span data-ttu-id="cb8a4-214">New Zealand Ministry of Health Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-214">New Zealand Ministry of Health Number</span></span>
- <span data-ttu-id="cb8a4-215">Norges identitetsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-215">Norway Identity Number</span></span>  
- <span data-ttu-id="cb8a4-216">Philippines Unified Multi-Purpose ID Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-216">Philippines Unified Multi-Purpose ID Number</span></span>
- <span data-ttu-id="cb8a4-217">Polens identitetskort</span><span class="sxs-lookup"><span data-stu-id="cb8a4-217">Poland Identity Card</span></span>
- <span data-ttu-id="cb8a4-218">Polens National ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-218">Poland National ID (PESEL)</span></span>
- <span data-ttu-id="cb8a4-219">Polen-pass</span><span class="sxs-lookup"><span data-stu-id="cb8a4-219">Poland Passport</span></span>
- <span data-ttu-id="cb8a4-220">Portugal, kreditkortsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-220">Portugal Citizen Card Number</span></span>
- <span data-ttu-id="cb8a4-221">Saudiarabiens national-ID</span><span class="sxs-lookup"><span data-stu-id="cb8a4-221">Saudi Arabia National ID</span></span>
- <span data-ttu-id="cb8a4-222">Singapore National Registration Identity Card (NRIC) Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-222">Singapore National Registration Identity Card (NRIC) Number</span></span>
- <span data-ttu-id="cb8a4-223">South Africa Identification Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-223">South Africa Identification Number</span></span>  
- <span data-ttu-id="cb8a4-224">Sydkoreas invånarregistreringsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-224">South Korea Resident Registration Number</span></span>
- <span data-ttu-id="cb8a4-225">Spain Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-225">Spain Social Security Number (SSN)</span></span>
- <span data-ttu-id="cb8a4-226">SQL Server Anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="cb8a4-226">SQL Server Connection String</span></span>  
- <span data-ttu-id="cb8a4-227">National ID för Sverige</span><span class="sxs-lookup"><span data-stu-id="cb8a4-227">Sweden National ID</span></span>
- <span data-ttu-id="cb8a4-228">Sverige Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-228">Sweden Passport Number</span></span>
- <span data-ttu-id="cb8a4-229">SWIFT-kod</span><span class="sxs-lookup"><span data-stu-id="cb8a4-229">SWIFT Code</span></span>
- <span data-ttu-id="cb8a4-230">Taiwan National ID</span><span class="sxs-lookup"><span data-stu-id="cb8a4-230">Taiwan National ID</span></span>
- <span data-ttu-id="cb8a4-231">Taiwan Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-231">Taiwan Passport Number</span></span>
- <span data-ttu-id="cb8a4-232">Taiwan Resident Certificate (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-232">Taiwan Resident Certificate (ARC/TARC)</span></span>
- <span data-ttu-id="cb8a4-233">Identifieringskod för thailändska</span><span class="sxs-lookup"><span data-stu-id="cb8a4-233">Thai Population Identification Code</span></span>
- <span data-ttu-id="cb8a4-234">Turkiska National Identification Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-234">Turkish National Identification number</span></span>
- <span data-ttu-id="cb8a4-235">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="cb8a4-235">U.K.</span></span> <span data-ttu-id="cb8a4-236">Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-236">Driver's License Number</span></span>
- <span data-ttu-id="cb8a4-237">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="cb8a4-237">U.K.</span></span> <span data-ttu-id="cb8a4-238">E-nummer för att samla in</span><span class="sxs-lookup"><span data-stu-id="cb8a4-238">Electoral Roll Number</span></span>
- <span data-ttu-id="cb8a4-239">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="cb8a4-239">U.K.</span></span> <span data-ttu-id="cb8a4-240">National Hälsotjänst Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-240">National Health Service Number</span></span>
- <span data-ttu-id="cb8a4-241">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="cb8a4-241">U.K.</span></span> <span data-ttu-id="cb8a4-242">National Insurance Number (NINO)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-242">National Insurance Number (NINO)</span></span>
- <span data-ttu-id="cb8a4-243">U.S. / Storbritannien</span><span class="sxs-lookup"><span data-stu-id="cb8a4-243">U.S. / U.K.</span></span> <span data-ttu-id="cb8a4-244">Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-244">Passport Number</span></span>
- <span data-ttu-id="cb8a4-245">U.S. Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-245">U.S. Bank Account Number</span></span>
- <span data-ttu-id="cb8a4-246">U.S. Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-246">U.S. Driver's License Number</span></span>
- <span data-ttu-id="cb8a4-247">U.S. Individual Taxpayer Identification Number (ITIN)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-247">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="cb8a4-248">U.S. Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-248">U.S. Social Security Number (SSN)</span></span>

<span data-ttu-id="cb8a4-249">Observera att anpassade typer av känslig information även stöds för DLP-principtips, utöver de för in visna typerna av känslig information.</span><span class="sxs-lookup"><span data-stu-id="cb8a4-249">Please note that custom sensitive information types are also supported for DLP policy tips in addition to the above out-of-the-box sensitive information types.</span></span>

## <a name="data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="cb8a4-250">Dataförlustskydd på slutpunktsenheter har stöd för principtips för endast vissa typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="cb8a4-250">Data Loss Prevention on endpoint devices supports policy tips for only some sensitive information types</span></span>

<span data-ttu-id="cb8a4-251">Listan över inringningstyper för känslig information som identifieras i dokument som lagras på slutpunktsenheter är följande:</span><span class="sxs-lookup"><span data-stu-id="cb8a4-251">The list of out-of-the-box sensitive information types that will be detected in documents residing on endpoint devices are the following :</span></span>

- <span data-ttu-id="cb8a4-252">ABA-routningsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-252">ABA Routing Number</span></span> 
- <span data-ttu-id="cb8a4-253">Argentina National Identity (DNI) Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-253">Argentina National Identity (DNI) Number</span></span> 
- <span data-ttu-id="cb8a4-254">Bank Account Number för Australien</span><span class="sxs-lookup"><span data-stu-id="cb8a4-254">Australia Bank Account Number</span></span> 
- <span data-ttu-id="cb8a4-255">Australiens medicinska kontonummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-255">Australia Medical Account Number</span></span> 
- <span data-ttu-id="cb8a4-256">Australia Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-256">Australia Passport Number</span></span> 
- <span data-ttu-id="cb8a4-257">Australiens skattenummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-257">Australia Tax File Number</span></span> 
- <span data-ttu-id="cb8a4-258">Australiensiska företagsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-258">Australian Business Number</span></span> 
- <span data-ttu-id="cb8a4-259">Australiensiska företags nummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-259">Australian Company Number</span></span> 
- <span data-ttu-id="cb8a4-260">Österrikes registreringsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-260">Austria Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-261">Österrike-identitetskort</span><span class="sxs-lookup"><span data-stu-id="cb8a4-261">Austria Identity Card</span></span> 
- <span data-ttu-id="cb8a4-262">Österrike Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-262">Austria Passport Number</span></span> 
- <span data-ttu-id="cb8a4-263">Österrike, social security number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-263">Austria Social Security Number</span></span> 
- <span data-ttu-id="cb8a4-264">Österrike skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-264">Austria Tax Identification Number</span></span> 
- <span data-ttu-id="cb8a4-265">Österrike , momsregistreringsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-265">Austria Value Added Tax (VAT) Number</span></span> 
- <span data-ttu-id="cb8a4-266">Autentiseringsnyckel för Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="cb8a4-266">Azure DocumentDB Auth Key</span></span> 
- <span data-ttu-id="cb8a4-267">Azure IAAS-databasanslutningssträng och Azure SQL-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="cb8a4-267">Azure IAAS Database Connection String and Azure SQL Connection String</span></span> 
- <span data-ttu-id="cb8a4-268">Azure IoT-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="cb8a4-268">Azure IoT Connection String</span></span> 
- <span data-ttu-id="cb8a4-269">Lösenord för Inställning av Azure-publicering</span><span class="sxs-lookup"><span data-stu-id="cb8a4-269">Azure Publish Setting Password</span></span> 
- <span data-ttu-id="cb8a4-270">Azure Redis Cache-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="cb8a4-270">Azure Redis Cache Connection String</span></span> 
- <span data-ttu-id="cb8a4-271">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="cb8a4-271">Azure SAS</span></span> 
- <span data-ttu-id="cb8a4-272">Azure Service Bus-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="cb8a4-272">Azure Service Bus Connection String</span></span> 
- <span data-ttu-id="cb8a4-273">Azure Storage Kontonyckel</span><span class="sxs-lookup"><span data-stu-id="cb8a4-273">Azure Storage Account Key</span></span> 
- <span data-ttu-id="cb8a4-274">Azure Storage Kontonyckel (allmän)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-274">Azure Storage Account Key (Generic)</span></span> 
- <span data-ttu-id="cb8a4-275">Belgien Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-275">Belgium Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-276">Belgiens nationalnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-276">Belgium National Number</span></span> 
- <span data-ttu-id="cb8a4-277">Belgien Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-277">Belgium Passport Number</span></span> 
- <span data-ttu-id="cb8a4-278">Belgium Value Added Tax Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-278">Belgium Value Added Tax Number</span></span> 
- <span data-ttu-id="cb8a4-279">Brasilien CPF-nummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-279">Brazil CPF Number</span></span> 
- <span data-ttu-id="cb8a4-280">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-280">Brazil Legal Entity Number (CNPJ)</span></span> 
- <span data-ttu-id="cb8a4-281">Brazil National ID Card (RG)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-281">Brazil National ID Card (RG)</span></span> 
- <span data-ttu-id="cb8a4-282">Bulgariens registreringsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-282">Bulgaria Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-283">Bulgarien Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-283">Bulgaria Passport Number</span></span> 
- <span data-ttu-id="cb8a4-284">Bulgariens enhetliga civilnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-284">Bulgaria Uniform Civil Number</span></span> 
- <span data-ttu-id="cb8a4-285">Bank Account Number för Kanada</span><span class="sxs-lookup"><span data-stu-id="cb8a4-285">Canada Bank Account Number</span></span> 
- <span data-ttu-id="cb8a4-286">Kanadas driver's License Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-286">Canada Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-287">Kanada Hälsotjänst Kanada</span><span class="sxs-lookup"><span data-stu-id="cb8a4-287">Canada Health Service Number</span></span> 
- <span data-ttu-id="cb8a4-288">Canada Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-288">Canada Passport Number</span></span> 
- <span data-ttu-id="cb8a4-289">Canada Personal Health Identification Number (PHIN)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-289">Canada Personal Health Identification Number (PHIN)</span></span> 
- <span data-ttu-id="cb8a4-290">Canada Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-290">Canada Social Insurance Number</span></span> 
- <span data-ttu-id="cb8a4-291">Chile Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-291">Chile Identity Card Number</span></span> 
- <span data-ttu-id="cb8a4-292">China Resident Identity Card (Folkrepubliken Kina) Nummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-292">China Resident Identity Card (PRC) Number</span></span> 
- <span data-ttu-id="cb8a4-293">Kreditkortsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-293">Credit Card Number</span></span> 
- <span data-ttu-id="cb8a4-294">Kroatiens licensnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-294">Croatia Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-295">Kroatiens identitetskortsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-295">Croatia Identity Card Number</span></span> 
- <span data-ttu-id="cb8a4-296">Kroatiens National ID-kortnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-296">Croatia National ID Card Number</span></span> 
- <span data-ttu-id="cb8a4-297">Kroatien Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-297">Croatia Passport Number</span></span> 
- <span data-ttu-id="cb8a4-298">Kroatiens OIB-nummer (Personal Identification)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-298">Croatia Personal Identification (OIB) Number</span></span> 
- <span data-ttu-id="cb8a4-299">CSCAN-AZURE0060 Azure Storage signatur för delad åtkomst</span><span class="sxs-lookup"><span data-stu-id="cb8a4-299">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span></span> 
- <span data-ttu-id="cb8a4-300">CSCAN-GENERAL0140 allmän symmetrisk nyckel</span><span class="sxs-lookup"><span data-stu-id="cb8a4-300">CSCAN-GENERAL0140 General Symmetric Key</span></span> 
- <span data-ttu-id="cb8a4-301">Cyperns drivrutinslicensnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-301">Cyprus Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-302">Cypern-identitetskort</span><span class="sxs-lookup"><span data-stu-id="cb8a4-302">Cyprus Identity Card</span></span> 
- <span data-ttu-id="cb8a4-303">Cypern Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-303">Cyprus Passport Number</span></span> 
- <span data-ttu-id="cb8a4-304">Cyperns skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-304">Cyprus Tax Identification Number</span></span> 
- <span data-ttu-id="cb8a4-305">Tjeckiska driver's License Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-305">Czech Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-306">Tjeckiska Personliga identitetsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-306">Czech Personal Identity Number</span></span> 
- <span data-ttu-id="cb8a4-307">Tjeckien Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-307">Czech Republic Passport Number</span></span> 
- <span data-ttu-id="cb8a4-308">Danmarks körkortsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-308">Denmark Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-309">Danmark Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-309">Denmark Passport Number</span></span> 
- <span data-ttu-id="cb8a4-310">Danmarks personliga id-nummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-310">Denmark Personal Identification Number</span></span> 
- <span data-ttu-id="cb8a4-311">Tvingande Enforcement Agency (DEA) Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-311">Drug Enforcement Agency (DEA) Number</span></span> 
- <span data-ttu-id="cb8a4-312">Estlands licensnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-312">Estonia Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-313">Estland Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-313">Estonia Passport Number</span></span> 
- <span data-ttu-id="cb8a4-314">Estland – personidentifieringskod</span><span class="sxs-lookup"><span data-stu-id="cb8a4-314">Estonia Personal Identification Code</span></span> 
- <span data-ttu-id="cb8a4-315">Betalkortsnummer (EU)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-315">EU Debit Card Number</span></span> 
- <span data-ttu-id="cb8a4-316">EU:s körkortsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-316">EU Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-317">EU National Identification Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-317">EU National Identification Number</span></span> 
- <span data-ttu-id="cb8a4-318">EU Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-318">EU Passport Number</span></span> 
- <span data-ttu-id="cb8a4-319">SOCIAL SECURITY Number (SSN) eller motsvarande ID</span><span class="sxs-lookup"><span data-stu-id="cb8a4-319">EU Social Security Number (SSN) or Equivalent ID</span></span> 
- <span data-ttu-id="cb8a4-320">EU:s skatteidentifieringsnummer (TIN)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-320">EU Tax Identification Number (TIN)</span></span> 
- <span data-ttu-id="cb8a4-321">Finland Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-321">Finland Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-322">Finland European Health Insurance Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-322">Finland European Health Insurance Number</span></span> 
- <span data-ttu-id="cb8a4-323">Finlands national-ID</span><span class="sxs-lookup"><span data-stu-id="cb8a4-323">Finland National ID</span></span> 
- <span data-ttu-id="cb8a4-324">Finland Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-324">Finland Passport Number</span></span> 
- <span data-ttu-id="cb8a4-325">Frankrikes licensnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-325">France Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-326">France Health Insurance Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-326">France Health Insurance Number</span></span> 
- <span data-ttu-id="cb8a4-327">France National ID Card (CNI)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-327">France National ID Card (CNI)</span></span> 
- <span data-ttu-id="cb8a4-328">France Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-328">France Passport Number</span></span> 
- <span data-ttu-id="cb8a4-329">France Social Security Number (INSEE)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-329">France Social Security Number (INSEE)</span></span> 
- <span data-ttu-id="cb8a4-330">France Tax Identification Number (numéro SPI.)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-330">France Tax Identification Number (numéro SPI.)</span></span> 
- <span data-ttu-id="cb8a4-331">France Value Added Tax Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-331">France Value Added Tax Number</span></span> 
- <span data-ttu-id="cb8a4-332">Tyskt körkortsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-332">German Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-333">Tyska Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-333">German Passport Number</span></span> 
- <span data-ttu-id="cb8a4-334">Id Card Number för Tyskland</span><span class="sxs-lookup"><span data-stu-id="cb8a4-334">Germany Identity Card Number</span></span> 
- <span data-ttu-id="cb8a4-335">Tysklands skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-335">Germany Tax Identification Number</span></span> 
- <span data-ttu-id="cb8a4-336">Värdeskattenummer för Tyskland</span><span class="sxs-lookup"><span data-stu-id="cb8a4-336">Germany Value Added Tax Number</span></span> 
- <span data-ttu-id="cb8a4-337">Greklands körkortsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-337">Greece Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-338">Greklands national-ID-kort</span><span class="sxs-lookup"><span data-stu-id="cb8a4-338">Greece National ID Card</span></span> 
- <span data-ttu-id="cb8a4-339">Greklands passnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-339">Greece Passport Number</span></span> 
- <span data-ttu-id="cb8a4-340">Greklands social securitynummer (AMKA)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-340">Greece Social Security Number (AMKA)</span></span> 
- <span data-ttu-id="cb8a4-341">Grekiska skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-341">Greek Tax identification Number</span></span> 
- <span data-ttu-id="cb8a4-342">Hong Kong Identity Card (HKID)-nummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-342">Hong Kong Identity Card (HKID) Number</span></span> 
- <span data-ttu-id="cb8a4-343">Ungerska social security number (TAD)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-343">Hungarian Social Security Number (TAJ)</span></span> 
- <span data-ttu-id="cb8a4-344">Ungerska nummer med moms</span><span class="sxs-lookup"><span data-stu-id="cb8a4-344">Hungarian Value Added Tax Number</span></span> 
- <span data-ttu-id="cb8a4-345">Ungerns registreringsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-345">Hungary Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-346">Ungern Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-346">Hungary Passport Number</span></span> 
- <span data-ttu-id="cb8a4-347">Ungerns personliga id-nummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-347">Hungary Personal Identification Number</span></span> 
- <span data-ttu-id="cb8a4-348">Ungerns skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-348">Hungary Tax identification Number</span></span> 
- <span data-ttu-id="cb8a4-349">Indiens permanenta kontonummer (PAN)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-349">India Permanent Account Number (PAN)</span></span> 
- <span data-ttu-id="cb8a4-350">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-350">India Unique Identification (Aadhaar) Number</span></span> 
- <span data-ttu-id="cb8a4-351">Indonesia Identity Card-nummer (KTP)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-351">Indonesia Identity Card (KTP) Number</span></span> 
- <span data-ttu-id="cb8a4-352">International Banking Account Number (IBAN)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-352">International Banking Account Number (IBAN)</span></span> 
- <span data-ttu-id="cb8a4-353">Internationell klassificering av avnärende (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-353">International Classification of Diseases (ICD-10-CM)</span></span> 
- <span data-ttu-id="cb8a4-354">Internationell klassificering av tidsklassificering (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-354">International Classification of Diseases (ICD-9-CM)</span></span> 
- <span data-ttu-id="cb8a4-355">IP-adress</span><span class="sxs-lookup"><span data-stu-id="cb8a4-355">IP Address</span></span> 
- <span data-ttu-id="cb8a4-356">Ireland Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-356">Ireland Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-357">Ireland Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-357">Ireland Passport Number</span></span> 
- <span data-ttu-id="cb8a4-358">Ireland Personal Public Service -nummer (PPS)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-358">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="cb8a4-359">Israels bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-359">Israel Bank Account Number</span></span> 
- <span data-ttu-id="cb8a4-360">Israels national-ID</span><span class="sxs-lookup"><span data-stu-id="cb8a4-360">Israel National ID</span></span> 
- <span data-ttu-id="cb8a4-361">Italiens licensnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-361">Italy Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-362">Italiens räkenskapskod</span><span class="sxs-lookup"><span data-stu-id="cb8a4-362">Italy Fiscal Code</span></span> 
- <span data-ttu-id="cb8a4-363">Italy Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-363">Italy Passport Number</span></span> 
- <span data-ttu-id="cb8a4-364">Italy Value Added Tax Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-364">Italy Value Added Tax Number</span></span> 
- <span data-ttu-id="cb8a4-365">Japan Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-365">Japan Bank Account Number</span></span> 
- <span data-ttu-id="cb8a4-366">Japan Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-366">Japan Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-367">Japan Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-367">Japan Passport Number</span></span> 
- <span data-ttu-id="cb8a4-368">Invånarregistreringsnummer för Japan</span><span class="sxs-lookup"><span data-stu-id="cb8a4-368">Japan Resident Registration Number</span></span> 
- <span data-ttu-id="cb8a4-369">Japan Social Insurance Number (SIN)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-369">Japan Social Insurance Number (SIN)</span></span> 
- <span data-ttu-id="cb8a4-370">Japanska My Number Corporate</span><span class="sxs-lookup"><span data-stu-id="cb8a4-370">Japanese My Number Corporate</span></span> 
- <span data-ttu-id="cb8a4-371">Japanska, Mitt nummer Personligt</span><span class="sxs-lookup"><span data-stu-id="cb8a4-371">Japanese My Number Personal</span></span> 
- <span data-ttu-id="cb8a4-372">Japanska Residence Card Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-372">Japanese Residence Card Number</span></span> 
- <span data-ttu-id="cb8a4-373">Lettlands drivrutinslicensnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-373">Latvia Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-374">Lettlands passport number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-374">Latvia Passport Number</span></span> 
- <span data-ttu-id="cb8a4-375">Personlig kod för Lettland</span><span class="sxs-lookup"><span data-stu-id="cb8a4-375">Latvia Personal Code</span></span> 
- <span data-ttu-id="cb8a4-376">Litauens licensnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-376">Lithuania Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-377">Litauen Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-377">Lithuania Passport Number</span></span> 
- <span data-ttu-id="cb8a4-378">Litauen – personlig kod</span><span class="sxs-lookup"><span data-stu-id="cb8a4-378">Lithuania Personal Code</span></span> 
- <span data-ttu-id="cb8a4-379">Luxemburg-drivrutinens licensnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-379">Luxemburg Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-380">Luxemburg National Identification Number (naturliga personer)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-380">Luxemburg National Identification Number (Natural persons)</span></span> 
- <span data-ttu-id="cb8a4-381">Luxemburg National Identification Number (icke-naturliga personer)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-381">Luxemburg National Identification Number (Non-natural persons)</span></span> 
- <span data-ttu-id="cb8a4-382">Luxemburg Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-382">Luxemburg Passport Number</span></span> 
- <span data-ttu-id="cb8a4-383">Malaysia Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-383">Malaysia Identity Card Number</span></span> 
- <span data-ttu-id="cb8a4-384">Malta Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-384">Malta Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-385">Malta-identitetskortsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-385">Malta Identity Card Number</span></span> 
- <span data-ttu-id="cb8a4-386">Malta Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-386">Malta Passport Number</span></span> 
- <span data-ttu-id="cb8a4-387">Maltas skattenummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-387">Malta Tax ID Number</span></span> 
- <span data-ttu-id="cb8a4-388">Nederländska medborgares servicenummer (BSN)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-388">Netherlands Citizen's Service (BSN) Number</span></span> 
- <span data-ttu-id="cb8a4-389">Nederländska driver's License Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-389">Netherlands Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-390">Nederländerna Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-390">Netherlands Passport Number</span></span> 
- <span data-ttu-id="cb8a4-391">Nederländska skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-391">Netherlands Tax Identification Number</span></span> 
- <span data-ttu-id="cb8a4-392">Nederländska värdeskattenummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-392">Netherlands Value Added Tax Number</span></span> 
- <span data-ttu-id="cb8a4-393">Bankkontonummer för Nya Zeeland</span><span class="sxs-lookup"><span data-stu-id="cb8a4-393">New Zealand bank account number</span></span> 
- <span data-ttu-id="cb8a4-394">New Zealand Driver License Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-394">New Zealand Driver License Number</span></span> 
- <span data-ttu-id="cb8a4-395">New Zealand Inland Revenue number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-395">New Zealand Inland Revenue number</span></span> 
- <span data-ttu-id="cb8a4-396">New Zealand Ministry of Health Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-396">New Zealand Ministry of Health Number</span></span> 
- <span data-ttu-id="cb8a4-397">New Zealand Social Enl. Nummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-397">New Zealand Social Welfare Number</span></span> 
- <span data-ttu-id="cb8a4-398">Norges identitetsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-398">Norway Identity Number</span></span> 
- <span data-ttu-id="cb8a4-399">Philippines Unified Multi-Purpose ID Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-399">Philippines Unified Multi-Purpose ID Number</span></span> 
- <span data-ttu-id="cb8a4-400">Polens licensnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-400">Poland Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-401">Polens identitetskort</span><span class="sxs-lookup"><span data-stu-id="cb8a4-401">Poland Identity Card</span></span> 
- <span data-ttu-id="cb8a4-402">Polens National ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-402">Poland National ID (PESEL)</span></span> 
- <span data-ttu-id="cb8a4-403">Polen-pass</span><span class="sxs-lookup"><span data-stu-id="cb8a4-403">Poland Passport</span></span> 
- <span data-ttu-id="cb8a4-404">Polens skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-404">Poland Tax Identification Number</span></span> 
- <span data-ttu-id="cb8a4-405">Polska REGON-nummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-405">Polish REGON Number</span></span> 
- <span data-ttu-id="cb8a4-406">Portugal, kreditkortsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-406">Portugal Citizen Card Number</span></span> 
- <span data-ttu-id="cb8a4-407">Portugal Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-407">Portugal Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-408">Portugal Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-408">Portugal Passport Number</span></span> 
- <span data-ttu-id="cb8a4-409">Portugals skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-409">Portugal Tax Identification Number</span></span> 
- <span data-ttu-id="cb8a4-410">Rumäniens registreringsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-410">Romania Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-411">Rumänien Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-411">Romania Passport Number</span></span> 
- <span data-ttu-id="cb8a4-412">Rumäniens personliga numeriska kod (CNP)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-412">Romania Personal Numerical Code (CNP)</span></span> 
- <span data-ttu-id="cb8a4-413">Ryska passnummer (inrikes)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-413">Russian Passport Number (Domestic)</span></span> 
- <span data-ttu-id="cb8a4-414">Ryska Passport Number (internationellt)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-414">Russian Passport Number (International)</span></span> 
- <span data-ttu-id="cb8a4-415">Saudiarabiens national-ID</span><span class="sxs-lookup"><span data-stu-id="cb8a4-415">Saudi Arabia National ID</span></span> 
- <span data-ttu-id="cb8a4-416">Singapore National Registration Identity Card (NRIC) Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-416">Singapore National Registration Identity Card (NRIC) Number</span></span> 
- <span data-ttu-id="cb8a4-417">Slovakiens licensnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-417">Slovakia Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-418">Slovakien Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-418">Slovakia Passport Number</span></span> 
- <span data-ttu-id="cb8a4-419">Slovakiens personliga nummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-419">Slovakia Personal Number</span></span> 
- <span data-ttu-id="cb8a4-420">Sloveniens körkortsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-420">Slovenia Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-421">Slovenien Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-421">Slovenia Passport Number</span></span> 
- <span data-ttu-id="cb8a4-422">Sloveniens skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-422">Slovenia Tax Identification Number</span></span> 
- <span data-ttu-id="cb8a4-423">Slovenska unik master number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-423">Slovenia Unique Master Citizen Number</span></span> 
- <span data-ttu-id="cb8a4-424">South Africa Identification Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-424">South Africa Identification Number</span></span> 
- <span data-ttu-id="cb8a4-425">Sydkoreas invånarregistreringsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-425">South Korea Resident Registration Number</span></span> 
- <span data-ttu-id="cb8a4-426">Spanien DNI</span><span class="sxs-lookup"><span data-stu-id="cb8a4-426">Spain DNI</span></span> 
- <span data-ttu-id="cb8a4-427">Spaniens licensnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-427">Spain Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-428">Spain Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-428">Spain Passport Number</span></span> 
- <span data-ttu-id="cb8a4-429">Spain Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-429">Spain Social Security Number (SSN)</span></span> 
- <span data-ttu-id="cb8a4-430">Spaniens skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-430">Spain Tax Identification Number</span></span> 
- <span data-ttu-id="cb8a4-431">SQL Server Anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="cb8a4-431">SQL Server Connection String</span></span> 
- <span data-ttu-id="cb8a4-432">Sverige driver's License Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-432">Sweden Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-433">National ID för Sverige</span><span class="sxs-lookup"><span data-stu-id="cb8a4-433">Sweden National ID</span></span> 
- <span data-ttu-id="cb8a4-434">Sverige Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-434">Sweden Passport Number</span></span> 
- <span data-ttu-id="cb8a4-435">Skatteidentifieringsnummer i Sverige</span><span class="sxs-lookup"><span data-stu-id="cb8a4-435">Sweden Tax Identification Number</span></span> 
- <span data-ttu-id="cb8a4-436">SWIFT-kod</span><span class="sxs-lookup"><span data-stu-id="cb8a4-436">SWIFT Code</span></span> 
- <span data-ttu-id="cb8a4-437">Swiss Social Security Number AHV</span><span class="sxs-lookup"><span data-stu-id="cb8a4-437">Swiss Social Security Number AHV</span></span> 
- <span data-ttu-id="cb8a4-438">Taiwan National ID</span><span class="sxs-lookup"><span data-stu-id="cb8a4-438">Taiwan National ID</span></span> 
- <span data-ttu-id="cb8a4-439">Taiwan Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-439">Taiwan Passport Number</span></span> 
- <span data-ttu-id="cb8a4-440">Taiwan Resident Certificate (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-440">Taiwan Resident Certificate (ARC/TARC)</span></span> 
- <span data-ttu-id="cb8a4-441">Identifieringskod för thailändska</span><span class="sxs-lookup"><span data-stu-id="cb8a4-441">Thai Population Identification Code</span></span> 
- <span data-ttu-id="cb8a4-442">Turkiska National Identification Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-442">Turkish National Identification number</span></span> 
- <span data-ttu-id="cb8a4-443">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="cb8a4-443">U.K.</span></span> <span data-ttu-id="cb8a4-444">Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-444">Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-445">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="cb8a4-445">U.K.</span></span> <span data-ttu-id="cb8a4-446">E-nummer för att samla in</span><span class="sxs-lookup"><span data-stu-id="cb8a4-446">Electoral Roll Number</span></span> 
- <span data-ttu-id="cb8a4-447">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="cb8a4-447">U.K.</span></span> <span data-ttu-id="cb8a4-448">National Hälsotjänst Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-448">National Health Service Number</span></span> 
- <span data-ttu-id="cb8a4-449">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="cb8a4-449">U.K.</span></span> <span data-ttu-id="cb8a4-450">National Insurance Number (NINO)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-450">National Insurance Number (NINO)</span></span> 
- <span data-ttu-id="cb8a4-451">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="cb8a4-451">U.K.</span></span> <span data-ttu-id="cb8a4-452">Unique Taxpayer-referensnummer</span><span class="sxs-lookup"><span data-stu-id="cb8a4-452">Unique Taxpayer Reference Number</span></span> 
- <span data-ttu-id="cb8a4-453">U.S. / Storbritannien</span><span class="sxs-lookup"><span data-stu-id="cb8a4-453">U.S. / U.K.</span></span> <span data-ttu-id="cb8a4-454">Passport Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-454">Passport Number</span></span> 
- <span data-ttu-id="cb8a4-455">U.S. Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-455">U.S. Bank Account Number</span></span> 
- <span data-ttu-id="cb8a4-456">U.S. Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="cb8a4-456">U.S. Driver's License Number</span></span> 
- <span data-ttu-id="cb8a4-457">U.S. Individual Taxpayer Identification Number (ITIN)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-457">U.S. Individual Taxpayer Identification Number (ITIN)</span></span> 
- <span data-ttu-id="cb8a4-458">U.S. Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-458">U.S. Social Security Number (SSN)</span></span> 
- <span data-ttu-id="cb8a4-459">Ukraina Passport Number (inrikes)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-459">Ukraine Passport Number (Domestic)</span></span> 
- <span data-ttu-id="cb8a4-460">Ukraina Passport Number (internationellt)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-460">Ukraine Passport Number (International)</span></span> 
 
<span data-ttu-id="cb8a4-461">Observera att anpassade typer av känslig information också identifieras, utöver de för insmådde typerna av känslig information</span><span class="sxs-lookup"><span data-stu-id="cb8a4-461">Please note that custom sensitive information types will also be detected in addition to the above out-of-the-box sensitive information types</span></span>

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a><span data-ttu-id="cb8a4-462">Tips om stödmatris för DLP-principen i Microsoft-appar</span><span class="sxs-lookup"><span data-stu-id="cb8a4-462">Support Matrix for DLP policy tips across Microsoft apps</span></span>

|<span data-ttu-id="cb8a4-463">**App och plattform**</span><span class="sxs-lookup"><span data-stu-id="cb8a4-463">**App and platform**</span></span>|<span data-ttu-id="cb8a4-464">**Stöd för DLP-principtips**</span><span class="sxs-lookup"><span data-stu-id="cb8a4-464">**DLP policy tip support**</span></span>|<span data-ttu-id="cb8a4-465">**Typer av känslig information som stöds**</span><span class="sxs-lookup"><span data-stu-id="cb8a4-465">**Sensitive information types supported**</span></span>|<span data-ttu-id="cb8a4-466">**Predikat och åtgärder som stöds**</span><span class="sxs-lookup"><span data-stu-id="cb8a4-466">**Predicates and actions supported**</span></span>|<span data-ttu-id="cb8a4-467">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="cb8a4-467">**Comments**</span></span>|
|:--|:--|:--|:--|:--|
|<span data-ttu-id="cb8a4-468">**Outlook Web Access**</span><span class="sxs-lookup"><span data-stu-id="cb8a4-468">**Outlook Web Access**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="cb8a4-469">Alla</span><span class="sxs-lookup"><span data-stu-id="cb8a4-469">All</span></span>|<span data-ttu-id="cb8a4-470">Delmängd</span><span class="sxs-lookup"><span data-stu-id="cb8a4-470">Subset</span></span>|<span data-ttu-id="cb8a4-471">Se [referens för policytips för skydd mot dataförlust](#data-loss-prevention-policy-tips-reference)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-471">See [Data Loss Prevention policy tips reference](#data-loss-prevention-policy-tips-reference)</span></span>|
|<span data-ttu-id="cb8a4-472">**Outlook Win32 (Outlook 2013 och därefter)**</span><span class="sxs-lookup"><span data-stu-id="cb8a4-472">**Outlook Win32 (Outlook 2013 and beyond)**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="cb8a4-473">Delmängd</span><span class="sxs-lookup"><span data-stu-id="cb8a4-473">Subset</span></span>|<span data-ttu-id="cb8a4-474">Delmängd</span><span class="sxs-lookup"><span data-stu-id="cb8a4-474">Subset</span></span>|<span data-ttu-id="cb8a4-475">Se [Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) och senare funktioner med principtips för bara vissa villkor och undantag, [och i Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) och senare samt i Office-program på skrivbordet visas principtips för endast vissa typer av känslig information, information om stöd för typer av känslig information och vilka DLP-villkor och åtgärder som stöds för att visa DLP-principtips på Outlook Win32.</span><span class="sxs-lookup"><span data-stu-id="cb8a4-475">See [Outlook 2013 and later supports showing policy tips for only some conditions and exceptions](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) and [Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) for details on support for sensitive information types and DLP conditions and actions supported for showing DLP policy tips on Outlook Win32.</span></span>|
|<span data-ttu-id="cb8a4-476">**Outlook Mobil (iOS, Android)/Outlook Mac**</span><span class="sxs-lookup"><span data-stu-id="cb8a4-476">**Outlook Mobile (iOS, Android)/Outlook Mac**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="cb8a4-477">Inga</span><span class="sxs-lookup"><span data-stu-id="cb8a4-477">None</span></span>|<span data-ttu-id="cb8a4-478">Inga</span><span class="sxs-lookup"><span data-stu-id="cb8a4-478">None</span></span>|<span data-ttu-id="cb8a4-479">DLP-principtips stöds inte på Outlook mobil</span><span class="sxs-lookup"><span data-stu-id="cb8a4-479">DLP policy tips are not supported on Outlook mobile</span></span>|
|<span data-ttu-id="cb8a4-480">**Sharepoint Online/One Drive för företag-webbklient**</span><span class="sxs-lookup"><span data-stu-id="cb8a4-480">**Sharepoint Online/One Drive for Business Web client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="cb8a4-481">Alla</span><span class="sxs-lookup"><span data-stu-id="cb8a4-481">All</span></span>|<span data-ttu-id="cb8a4-482">Alla SPO/ODB-predikat och åtgärder i DLP</span><span class="sxs-lookup"><span data-stu-id="cb8a4-482">All SPO/ODB predicates and actions in DLP</span></span>||
|<span data-ttu-id="cb8a4-483">**Sharepoint Win32/ One Drive för företag Win32-klient**</span><span class="sxs-lookup"><span data-stu-id="cb8a4-483">**Sharepoint Win32/ One Drive for Business Win32 client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="cb8a4-484">Inga</span><span class="sxs-lookup"><span data-stu-id="cb8a4-484">None</span></span>|<span data-ttu-id="cb8a4-485">Inga</span><span class="sxs-lookup"><span data-stu-id="cb8a4-485">None</span></span>|<span data-ttu-id="cb8a4-486">Tips för DLP-princip stöds inte i Sharepoint- OneDrive-klientprogram på datorn</span><span class="sxs-lookup"><span data-stu-id="cb8a4-486">DLP policy tips are not supported on Sharepoint or OneDrive desktop client apps</span></span>|
|<span data-ttu-id="cb8a4-487">**Word, Excel, PowerPoint webbklient**</span><span class="sxs-lookup"><span data-stu-id="cb8a4-487">**Word, Excel, PowerPoint Web Client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="cb8a4-488">Alla</span><span class="sxs-lookup"><span data-stu-id="cb8a4-488">All</span></span>|<span data-ttu-id="cb8a4-489">Alla SPO/ODB-predikat och åtgärder i DLP</span><span class="sxs-lookup"><span data-stu-id="cb8a4-489">All SPO/ODB predicates and actions in DLP</span></span>|<span data-ttu-id="cb8a4-490">Tips för DLP-princip stöds om dokumentet ligger på SPO- eller ODB-webbappen och DLP-principen redan har stämplats.</span><span class="sxs-lookup"><span data-stu-id="cb8a4-490">DLP policy tip is supported if the document is hosted on SPO or ODB web app and the DLP policy is already stamped.</span></span>|
|<span data-ttu-id="cb8a4-491">**Word Excel PowerPoint Mobile klient**</span><span class="sxs-lookup"><span data-stu-id="cb8a4-491">**Word, Excel, PowerPoint Mobile Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="cb8a4-492">Inga</span><span class="sxs-lookup"><span data-stu-id="cb8a4-492">None</span></span>|<span data-ttu-id="cb8a4-493">Inga</span><span class="sxs-lookup"><span data-stu-id="cb8a4-493">None</span></span>|<span data-ttu-id="cb8a4-494">Tips för DLP-princip stöds inte i mobilappar för Office.</span><span class="sxs-lookup"><span data-stu-id="cb8a4-494">DLP policy tips are not supported in mobile apps for Office.</span></span>|
|<span data-ttu-id="cb8a4-495">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span><span class="sxs-lookup"><span data-stu-id="cb8a4-495">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="cb8a4-496">Alla</span><span class="sxs-lookup"><span data-stu-id="cb8a4-496">All</span></span>|<span data-ttu-id="cb8a4-497">Alla Teams i DLP-principen</span><span class="sxs-lookup"><span data-stu-id="cb8a4-497">All Teams predicates in DLP policy</span></span>|<span data-ttu-id="cb8a4-498">Principtips visas när ett meddelande flaggas som "Det här meddelandet har flaggats.</span><span class="sxs-lookup"><span data-stu-id="cb8a4-498">Policy tips will show when a message is flagged as “This message has been flagged.</span></span> <span data-ttu-id="cb8a4-499">Vad kan jag göra?"</span><span class="sxs-lookup"><span data-stu-id="cb8a4-499">What can I do?”</span></span> <span data-ttu-id="cb8a4-500">När användaren klickar på länken kan han eller hon granska de typer av känslig information som upptäckts och åsidosätta eller rapportera ett problem om administratören tillåtit det. Observera att inga principtips visas för filer.</span><span class="sxs-lookup"><span data-stu-id="cb8a4-500">When clicking the link, the user can review the sensitive info types detected and override or report an issue if allowed by the admin. Note that no policy tips are shown for files.</span></span> <span data-ttu-id="cb8a4-501">När mottagaren försöker komma åt dokumentet kan de få åtkomst nekad om det inte är tillåtet.</span><span class="sxs-lookup"><span data-stu-id="cb8a4-501">When the recipient tries to access the document, they might get access denied if not allowed.</span></span>|
|<span data-ttu-id="cb8a4-502">**Win32-slutpunktsenheter**</span><span class="sxs-lookup"><span data-stu-id="cb8a4-502">**Win32 Endpoint Devices**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="cb8a4-503">Delmängd</span><span class="sxs-lookup"><span data-stu-id="cb8a4-503">Subset</span></span>|<span data-ttu-id="cb8a4-504">Alla endpoint DLP-predikat och åtgärder i DLP-princip</span><span class="sxs-lookup"><span data-stu-id="cb8a4-504">All Endpoint DLP predicates and actions in DLP policy</span></span>|<span data-ttu-id="cb8a4-505">Se [Skydd mot dataförlust i Slutpunkt som stöder principtips för endast vissa typer av känslig information](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-505">See [Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)</span></span>|
|<span data-ttu-id="cb8a4-506">**Mac-enheter**</span><span class="sxs-lookup"><span data-stu-id="cb8a4-506">**Mac devices**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="cb8a4-507">Inga</span><span class="sxs-lookup"><span data-stu-id="cb8a4-507">None</span></span>|<span data-ttu-id="cb8a4-508">Inga</span><span class="sxs-lookup"><span data-stu-id="cb8a4-508">None</span></span>|<span data-ttu-id="cb8a4-509">Principer för skydd mot dataförlust är i dag inte tillgängliga på Mac-enheter</span><span class="sxs-lookup"><span data-stu-id="cb8a4-509">Data loss prevention policies are not enforceable on Mac devices today</span></span>|
|<span data-ttu-id="cb8a4-510">**Molnbaserade appar från tredje part**</span><span class="sxs-lookup"><span data-stu-id="cb8a4-510">**3rd party cloud apps**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="cb8a4-511">Inga</span><span class="sxs-lookup"><span data-stu-id="cb8a4-511">None</span></span>|<span data-ttu-id="cb8a4-512">Inga</span><span class="sxs-lookup"><span data-stu-id="cb8a4-512">None</span></span>|<span data-ttu-id="cb8a4-513">Policytips för skydd mot dataförlust stöds inte i molnappar från tredje part</span><span class="sxs-lookup"><span data-stu-id="cb8a4-513">Data Loss Prevention policy tips are not supported on 3rd party cloud apps</span></span>|
|<span data-ttu-id="cb8a4-514">**On-prem**</span><span class="sxs-lookup"><span data-stu-id="cb8a4-514">**On-prem**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="cb8a4-515">Inga</span><span class="sxs-lookup"><span data-stu-id="cb8a4-515">None</span></span>|<span data-ttu-id="cb8a4-516">Inga</span><span class="sxs-lookup"><span data-stu-id="cb8a4-516">None</span></span>||
|<span data-ttu-id="cb8a4-517">**Word-, Excel-, PowerPoint Win32-klient**</span><span class="sxs-lookup"><span data-stu-id="cb8a4-517">**Word, Excel, PowerPoint Win32 Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="cb8a4-518">Delmängd</span><span class="sxs-lookup"><span data-stu-id="cb8a4-518">Subset</span></span>|<span data-ttu-id="cb8a4-519">Delmängd</span><span class="sxs-lookup"><span data-stu-id="cb8a4-519">Subset</span></span>|<span data-ttu-id="cb8a4-520">Se [Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) och senare samt stöd för Office-program på stationära datorer med policytips för endast vissa typer av känslig information för listan över typer av känslig information som stöds</span><span class="sxs-lookup"><span data-stu-id="cb8a4-520">Please see [Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) for the list of sensitive information types supported</span></span></br></br><span data-ttu-id="cb8a4-521">Principtips för WXP-klientprogram fungerar för dokument som lagras på Sharepoint Online- eller One Drive för företag-webbplatser för alla DLP-principer som har exakt nedanstående eller en delmängd villkor eller åtgärder i DLP-principen:</span><span class="sxs-lookup"><span data-stu-id="cb8a4-521">Policy tips for WXP client apps will work for documents stored on Sharepoint Online or One Drive for Business Sites for all DLP policies which have exactly the below or a subset of conditions or actions in the DLP policy:</span></span></br> <ul><li><span data-ttu-id="cb8a4-522">Innehållet innehåller typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="cb8a4-522">Content contains sensitive information types</span></span></li><li><span data-ttu-id="cb8a4-523">Åtkomstomfattning (innehåll delas internt/externt)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-523">Access Scope (Content is shared internally/externally)</span></span></li><li><span data-ttu-id="cb8a4-524">Meddela användare (principtips/användarmeddelanden)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-524">Notify User (policy tips/user notifications)</span></span></li><li><span data-ttu-id="cb8a4-525">Blockera alla</span><span class="sxs-lookup"><span data-stu-id="cb8a4-525">Block everyone</span></span></li><li><span data-ttu-id="cb8a4-526">Incidentrapporter</span><span class="sxs-lookup"><span data-stu-id="cb8a4-526">Incident reports</span></span></li></ul></br> <span data-ttu-id="cb8a4-527">Om det finns andra villkor eller åtgärder visas inte DLP-principtipset för den principen i skrivbordsapparna i Word, Excel eller PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="cb8a4-527">If any other condition or action is present, the DLP policy tip for that policy will not appear in the desktop apps of Word, Excel or PowerPoint.</span></span></br><span data-ttu-id="cb8a4-528">Mer [information finns i Excel, PowerPoint och Word](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word)</span><span class="sxs-lookup"><span data-stu-id="cb8a4-528">See [Policy tips in Excel, PowerPoint, and Word](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word) for more details</span></span>|
||||||
