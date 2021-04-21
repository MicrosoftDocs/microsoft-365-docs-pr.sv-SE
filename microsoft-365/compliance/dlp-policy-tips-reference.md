---
title: Referensinformation om principtips för dataförlustskydd
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
ms.openlocfilehash: 36e4d4f96146b51e0b31731c9e93222eed767045
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903808"
---
# <a name="data-loss-prevention-policy-tips-reference"></a><span data-ttu-id="c5b22-103">Referensinformation om principtips för dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="c5b22-103">Data Loss Prevention policy tips reference</span></span>

<span data-ttu-id="c5b22-104">DLP-principtips i Outlook Web Access stöds för alla villkor, undantag och åtgärder som är tillämpliga för Exchange-arbetsbelastning i en DLP-princip, förutom följande:</span><span class="sxs-lookup"><span data-stu-id="c5b22-104">DLP policy tips in Outlook Web Access is supported for all the conditions, exceptions and actions that are applicable on Exchange workload in a DLP policy except the following:</span></span>

<span data-ttu-id="c5b22-105">**Villkor:**</span><span class="sxs-lookup"><span data-stu-id="c5b22-105">**Conditions:**</span></span>

- <span data-ttu-id="c5b22-106">Sender Is</span><span class="sxs-lookup"><span data-stu-id="c5b22-106">Sender Is</span></span>
- <span data-ttu-id="c5b22-107">Sender Domain Is</span><span class="sxs-lookup"><span data-stu-id="c5b22-107">Sender Domain Is</span></span>
- <span data-ttu-id="c5b22-108">Mottagaren är medlem i</span><span class="sxs-lookup"><span data-stu-id="c5b22-108">Recipient is a member of</span></span>
- <span data-ttu-id="c5b22-109">Sidhuvudet innehåller ord eller fraser</span><span class="sxs-lookup"><span data-stu-id="c5b22-109">Header contains words or phrases</span></span>
- <span data-ttu-id="c5b22-110">Sidhuvud matchar mönster</span><span class="sxs-lookup"><span data-stu-id="c5b22-110">Header matches patterns</span></span>
- <span data-ttu-id="c5b22-111">Dokumentstorlek är lika med eller större än</span><span class="sxs-lookup"><span data-stu-id="c5b22-111">Document size equals or is greater than</span></span>
- <span data-ttu-id="c5b22-112">Meddelandetypen är</span><span class="sxs-lookup"><span data-stu-id="c5b22-112">Message type is</span></span>
- <span data-ttu-id="c5b22-113">Meddelandets prioritet är</span><span class="sxs-lookup"><span data-stu-id="c5b22-113">Message importance is</span></span>
- <span data-ttu-id="c5b22-114">Innehållsteckenuppsättning innehåller ord</span><span class="sxs-lookup"><span data-stu-id="c5b22-114">Content character set contains words</span></span>
- <span data-ttu-id="c5b22-115">Ämne eller brödtext innehåller ord eller fraser</span><span class="sxs-lookup"><span data-stu-id="c5b22-115">Subject or body contains words or phrases</span></span>
- <span data-ttu-id="c5b22-116">Mönster för ämne eller brödtext</span><span class="sxs-lookup"><span data-stu-id="c5b22-116">Subject or body matches patterns</span></span>
- <span data-ttu-id="c5b22-117">Innehållsteckenuppsättning innehåller ord</span><span class="sxs-lookup"><span data-stu-id="c5b22-117">Content character set contains words</span></span>
- <span data-ttu-id="c5b22-118">Innehåll tas emot från</span><span class="sxs-lookup"><span data-stu-id="c5b22-118">Content is received from</span></span>
- <span data-ttu-id="c5b22-119">Har avsändaren åsidosättt principtipset</span><span class="sxs-lookup"><span data-stu-id="c5b22-119">Has sender overridden the policy tip</span></span>
- <span data-ttu-id="c5b22-120">Meddelandestorlek är lika med eller större än</span><span class="sxs-lookup"><span data-stu-id="c5b22-120">Message size equals or is greater than</span></span>
- <span data-ttu-id="c5b22-121">Sender AD-attributet innehåller ord eller fraser</span><span class="sxs-lookup"><span data-stu-id="c5b22-121">Sender AD attribute contains words or phrases</span></span>
- <span data-ttu-id="c5b22-122">Ad-sender-attributet matchar mönster</span><span class="sxs-lookup"><span data-stu-id="c5b22-122">Sender AD attribute matches patterns</span></span>
- <span data-ttu-id="c5b22-123">Dokumentinnehållet innehåller ord eller fraser</span><span class="sxs-lookup"><span data-stu-id="c5b22-123">Document content contains words or phrases</span></span>
- <span data-ttu-id="c5b22-124">Dokumentinnehåll matchar mönster</span><span class="sxs-lookup"><span data-stu-id="c5b22-124">Document content matches patterns</span></span>

<span data-ttu-id="c5b22-125">**Åtgärder:**</span><span class="sxs-lookup"><span data-stu-id="c5b22-125">**Actions:**</span></span>

- <span data-ttu-id="c5b22-126">Vidarebefordra meddelandet för godkännande till avsändarens chef</span><span class="sxs-lookup"><span data-stu-id="c5b22-126">Forward the message for approval to sender’s manager</span></span>
- <span data-ttu-id="c5b22-127">Vidarebefordra meddelandet för godkännande till vissa godkännare</span><span class="sxs-lookup"><span data-stu-id="c5b22-127">Forward the message for approval to specific approvers</span></span>
- <span data-ttu-id="c5b22-128">Omdirigera meddelandet till specifika användare</span><span class="sxs-lookup"><span data-stu-id="c5b22-128">Redirect the message to specific users</span></span>
- <span data-ttu-id="c5b22-129">Lägga till mottagare i Rutan Till</span><span class="sxs-lookup"><span data-stu-id="c5b22-129">Add recipients to the To Box</span></span>
- <span data-ttu-id="c5b22-130">Lägga till mottagare i rutan Kopia</span><span class="sxs-lookup"><span data-stu-id="c5b22-130">Add recipients to the Cc Box</span></span>
- <span data-ttu-id="c5b22-131">Lägga till mottagare i rutan Hemlig kopia</span><span class="sxs-lookup"><span data-stu-id="c5b22-131">Add recipients to the Bcc Box</span></span>
- <span data-ttu-id="c5b22-132">Lägga till avsändarens chef som mottagare</span><span class="sxs-lookup"><span data-stu-id="c5b22-132">Add the sender’s manager as recipient</span></span>
- <span data-ttu-id="c5b22-133">Lägga till HTML-ansvarsfriskrivning</span><span class="sxs-lookup"><span data-stu-id="c5b22-133">Add HTML disclaimer</span></span>
- <span data-ttu-id="c5b22-134">Förbereda ämnet för e-post</span><span class="sxs-lookup"><span data-stu-id="c5b22-134">Prepend email subject</span></span>
- <span data-ttu-id="c5b22-135">Ta bort meddelandekryptering och rättighetsskydd i O365</span><span class="sxs-lookup"><span data-stu-id="c5b22-135">Remove O365 Message Encryption and rights protection</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a><span data-ttu-id="c5b22-136">Outlook 2013 och senare har stöd för att visa principtips för bara vissa villkor och undantag</span><span class="sxs-lookup"><span data-stu-id="c5b22-136">Outlook 2013 and later supports showing policy tips for only some conditions and exceptions</span></span>

<span data-ttu-id="c5b22-137">För närvarande har Outlook 2013 och senare stöd för att visa principtips för principer som inte innehåller några villkor eller undantag utöver nedan nämnda villkor och motsvarande undantag:</span><span class="sxs-lookup"><span data-stu-id="c5b22-137">Currently, Outlook 2013 and later supports showing policy tips for policies which do not contain any condition or exception apart from the below mentioned conditions and corresponding exceptions :</span></span>

- <span data-ttu-id="c5b22-138">Innehållet innehåller (fungerar endast för typer av känslig information.</span><span class="sxs-lookup"><span data-stu-id="c5b22-138">Content contains (works only for Sensitive information types.</span></span> <span data-ttu-id="c5b22-139">Känslighetsetiketter stöds inte)</span><span class="sxs-lookup"><span data-stu-id="c5b22-139">Sensitivity labels are not supported)</span></span>
- <span data-ttu-id="c5b22-140">Innehåll delas</span><span class="sxs-lookup"><span data-stu-id="c5b22-140">Content is shared</span></span>

<span data-ttu-id="c5b22-141">Observera att alla villkor fungerar för e-postmeddelanden som redigeras i Outlook-klientappen, där de matchar innehåll och tillämpar skyddsåtgärder för innehåll.</span><span class="sxs-lookup"><span data-stu-id="c5b22-141">Note that all the conditions work for emails authored in Outlook client app, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="c5b22-142">Men det går inte att visa principtips för användare för villkor som används utöver de som nämns ovan.</span><span class="sxs-lookup"><span data-stu-id="c5b22-142">However, showing policy tips to users is not supported for any conditions that are used apart from the ones mentioned above.</span></span>

## <a name="outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="c5b22-143">Outlook 2013 och senare samt stöd för Office-program på stationära datorer som visar principtips för endast vissa typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="c5b22-143">Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types</span></span>

<span data-ttu-id="c5b22-144">Följande är en lista med för indelad känslig informationstyper som identifieras för visning av DLP-principtips i Outlook på skrivbordet (2013 och senare) och Office-program (Word, Excel, PowerPoint) på skrivbordet:</span><span class="sxs-lookup"><span data-stu-id="c5b22-144">The list of out-of-the-box sensitive information types that will be detected for showing DLP policy tips in Outlook on Desktop (2013 and later) and Office apps (Word, Excel, PowerPoint) on Desktop are the following :</span></span>

- <span data-ttu-id="c5b22-145">ABA-routningsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-145">ABA Routing Number</span></span>
- <span data-ttu-id="c5b22-146">Argentina National Identity (DNI) Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-146">Argentina National Identity (DNI) Number</span></span>
- <span data-ttu-id="c5b22-147">Bank Account Number för Australien</span><span class="sxs-lookup"><span data-stu-id="c5b22-147">Australia Bank Account Number</span></span>
- <span data-ttu-id="c5b22-148">Australiens medicinska kontonummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-148">Australia Medical Account Number</span></span>
- <span data-ttu-id="c5b22-149">Australia Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-149">Australia Passport Number</span></span>
- <span data-ttu-id="c5b22-150">Australiens skattenummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-150">Australia Tax File Number</span></span>
- <span data-ttu-id="c5b22-151">Autentiseringsnyckel för Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="c5b22-151">Azure DocumentDB Auth Key</span></span>  
- <span data-ttu-id="c5b22-152">Azure IAAS-databasanslutningssträng och Azure SQL-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="c5b22-152">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>  
- <span data-ttu-id="c5b22-153">Azure IoT-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="c5b22-153">Azure IoT Connection String</span></span>  
- <span data-ttu-id="c5b22-154">Lösenord för Inställning av Azure-publicering</span><span class="sxs-lookup"><span data-stu-id="c5b22-154">Azure Publish Setting Password</span></span>  
- <span data-ttu-id="c5b22-155">Azure Redis Cache-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="c5b22-155">Azure Redis Cache Connection String</span></span>  
- <span data-ttu-id="c5b22-156">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="c5b22-156">Azure SAS</span></span>  
- <span data-ttu-id="c5b22-157">Azure Service Bus Connection String</span><span class="sxs-lookup"><span data-stu-id="c5b22-157">Azure Service Bus Connection String</span></span>  
- <span data-ttu-id="c5b22-158">Azure Storage Account Key</span><span class="sxs-lookup"><span data-stu-id="c5b22-158">Azure Storage Account Key</span></span>  
- <span data-ttu-id="c5b22-159">Azure Storage Account Key (generic)</span><span class="sxs-lookup"><span data-stu-id="c5b22-159">Azure Storage Account Key (Generic)</span></span>  
- <span data-ttu-id="c5b22-160">Belgiens nationalnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-160">Belgium National Number</span></span>
- <span data-ttu-id="c5b22-161">Brasilien CPF-nummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-161">Brazil CPF Number</span></span>
- <span data-ttu-id="c5b22-162">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="c5b22-162">Brazil Legal Entity Number (CNPJ)</span></span>
- <span data-ttu-id="c5b22-163">Brazil National ID Card (RG)</span><span class="sxs-lookup"><span data-stu-id="c5b22-163">Brazil National ID Card (RG)</span></span>
- <span data-ttu-id="c5b22-164">Bank Account Number för Kanada</span><span class="sxs-lookup"><span data-stu-id="c5b22-164">Canada Bank Account Number</span></span>
- <span data-ttu-id="c5b22-165">Kanadas driver's License Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-165">Canada Driver's License Number</span></span>
- <span data-ttu-id="c5b22-166">Canada Health Service Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-166">Canada Health Service Number</span></span>
- <span data-ttu-id="c5b22-167">Canada Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-167">Canada Passport Number</span></span>
- <span data-ttu-id="c5b22-168">Canada Personal Health Identification Number (PHIN)</span><span class="sxs-lookup"><span data-stu-id="c5b22-168">Canada Personal Health Identification Number (PHIN)</span></span>
- <span data-ttu-id="c5b22-169">Canada Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-169">Canada Social Insurance Number</span></span>
- <span data-ttu-id="c5b22-170">Chile Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-170">Chile Identity Card Number</span></span>
- <span data-ttu-id="c5b22-171">China Resident Identity Card (Folkrepubliken Kina) Nummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-171">China Resident Identity Card (PRC) Number</span></span>
- <span data-ttu-id="c5b22-172">Kreditkortsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-172">Credit Card Number</span></span>
- <span data-ttu-id="c5b22-173">Kroatiens identitetskortsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-173">Croatia Identity Card Number</span></span>  
- <span data-ttu-id="c5b22-174">Kroatiens OIB-nummer (Personal Identification)</span><span class="sxs-lookup"><span data-stu-id="c5b22-174">Croatia Personal Identification (OIB) Number</span></span>  
- <span data-ttu-id="c5b22-175">Tjeckiska Personliga identitetsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-175">Czech Personal Identity Number</span></span>  
- <span data-ttu-id="c5b22-176">Danmarks personliga id-nummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-176">Denmark Personal Identification Number</span></span>
- <span data-ttu-id="c5b22-177">Tvingande Enforcement Agency (DEA) Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-177">Drug Enforcement Agency (DEA) Number</span></span>
- <span data-ttu-id="c5b22-178">Betalkortsnummer (EU)</span><span class="sxs-lookup"><span data-stu-id="c5b22-178">EU Debit Card Number</span></span>
- <span data-ttu-id="c5b22-179">EU:s körkortsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-179">EU Driver's License Number</span></span>  
- <span data-ttu-id="c5b22-180">EU National Identification Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-180">EU National Identification Number</span></span>  
- <span data-ttu-id="c5b22-181">EU Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-181">EU Passport Number</span></span>  
- <span data-ttu-id="c5b22-182">SOCIAL SECURITY Number (SSN) eller motsvarande ID</span><span class="sxs-lookup"><span data-stu-id="c5b22-182">EU Social Security Number (SSN) or Equivalent ID</span></span>  
- <span data-ttu-id="c5b22-183">EU:s skatteidentifieringsnummer (TIN)</span><span class="sxs-lookup"><span data-stu-id="c5b22-183">EU Tax Identification Number (TIN)</span></span>  
- <span data-ttu-id="c5b22-184">Finlands national-ID</span><span class="sxs-lookup"><span data-stu-id="c5b22-184">Finland National ID</span></span>
- <span data-ttu-id="c5b22-185">Finland Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-185">Finland Passport Number</span></span>
- <span data-ttu-id="c5b22-186">Frankrikes licensnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-186">France Driver's License Number</span></span>
- <span data-ttu-id="c5b22-187">France National ID Card (CNI)</span><span class="sxs-lookup"><span data-stu-id="c5b22-187">France National ID Card (CNI)</span></span>
- <span data-ttu-id="c5b22-188">France Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-188">France Passport Number</span></span>
- <span data-ttu-id="c5b22-189">France Social Security Number (INSEE)</span><span class="sxs-lookup"><span data-stu-id="c5b22-189">France Social Security Number (INSEE)</span></span>
- <span data-ttu-id="c5b22-190">Tyskt körkortsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-190">German Driver's License Number</span></span>
- <span data-ttu-id="c5b22-191">Tyska Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-191">German Passport Number</span></span>
- <span data-ttu-id="c5b22-192">Id Card Number för Tyskland</span><span class="sxs-lookup"><span data-stu-id="c5b22-192">Germany Identity Card Number</span></span>
- <span data-ttu-id="c5b22-193">Greklands national-ID-kort</span><span class="sxs-lookup"><span data-stu-id="c5b22-193">Greece National ID Card</span></span>  
- <span data-ttu-id="c5b22-194">Hong Kong Identity Card (HKID)-nummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-194">Hong Kong Identity Card (HKID) Number</span></span>
- <span data-ttu-id="c5b22-195">Indiens permanenta kontonummer (PAN)</span><span class="sxs-lookup"><span data-stu-id="c5b22-195">India Permanent Account Number (PAN)</span></span>
- <span data-ttu-id="c5b22-196">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-196">India Unique Identification (Aadhaar) Number</span></span>
- <span data-ttu-id="c5b22-197">Indonesia Identity Card-nummer (KTP)</span><span class="sxs-lookup"><span data-stu-id="c5b22-197">Indonesia Identity Card (KTP) Number</span></span>
- <span data-ttu-id="c5b22-198">International Banking Account Number (IBAN)</span><span class="sxs-lookup"><span data-stu-id="c5b22-198">International Banking Account Number (IBAN)</span></span>
- <span data-ttu-id="c5b22-199">Internationell klassificering av avnärende (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="c5b22-199">International Classification of Diseases (ICD-10-CM)</span></span>  
- <span data-ttu-id="c5b22-200">Internationell klassificering av tidsklassificering (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="c5b22-200">International Classification of Diseases (ICD-9-CM)</span></span>  
- <span data-ttu-id="c5b22-201">IP-adress</span><span class="sxs-lookup"><span data-stu-id="c5b22-201">IP Address</span></span>
- <span data-ttu-id="c5b22-202">Ireland Personal Public Service -nummer (PPS)</span><span class="sxs-lookup"><span data-stu-id="c5b22-202">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="c5b22-203">Israels bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-203">Israel Bank Account Number</span></span>
- <span data-ttu-id="c5b22-204">Israels national-ID</span><span class="sxs-lookup"><span data-stu-id="c5b22-204">Israel National ID</span></span>
- <span data-ttu-id="c5b22-205">Italiens licensnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-205">Italy Driver's License Number</span></span>
- <span data-ttu-id="c5b22-206">Japan Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-206">Japan Bank Account Number</span></span>
- <span data-ttu-id="c5b22-207">Japan Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-207">Japan Driver's License Number</span></span>
- <span data-ttu-id="c5b22-208">Japan Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-208">Japan Passport Number</span></span>
- <span data-ttu-id="c5b22-209">Invånarregistreringsnummer för Japan</span><span class="sxs-lookup"><span data-stu-id="c5b22-209">Japan Resident Registration Number</span></span>
- <span data-ttu-id="c5b22-210">Japan Social Insurance Number (SIN)</span><span class="sxs-lookup"><span data-stu-id="c5b22-210">Japan Social Insurance Number (SIN)</span></span>
- <span data-ttu-id="c5b22-211">Japanska Residence Card Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-211">Japanese Residence Card Number</span></span>
- <span data-ttu-id="c5b22-212">Malaysia Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-212">Malaysia Identity Card Number</span></span>
- <span data-ttu-id="c5b22-213">Nederländska medborgares servicenummer (BSN)</span><span class="sxs-lookup"><span data-stu-id="c5b22-213">Netherlands Citizen's Service (BSN) Number</span></span>  
- <span data-ttu-id="c5b22-214">New Zealand Ministry of Health Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-214">New Zealand Ministry of Health Number</span></span>
- <span data-ttu-id="c5b22-215">Norges identitetsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-215">Norway Identity Number</span></span>  
- <span data-ttu-id="c5b22-216">Philippines Unified Multi-Purpose ID Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-216">Philippines Unified Multi-Purpose ID Number</span></span>
- <span data-ttu-id="c5b22-217">Polens identitetskort</span><span class="sxs-lookup"><span data-stu-id="c5b22-217">Poland Identity Card</span></span>
- <span data-ttu-id="c5b22-218">Polens National ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="c5b22-218">Poland National ID (PESEL)</span></span>
- <span data-ttu-id="c5b22-219">Polen-pass</span><span class="sxs-lookup"><span data-stu-id="c5b22-219">Poland Passport</span></span>
- <span data-ttu-id="c5b22-220">Portugal, kreditkortsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-220">Portugal Citizen Card Number</span></span>
- <span data-ttu-id="c5b22-221">Saudiarabiens national-ID</span><span class="sxs-lookup"><span data-stu-id="c5b22-221">Saudi Arabia National ID</span></span>
- <span data-ttu-id="c5b22-222">Singapore National Registration Identity Card (NRIC) Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-222">Singapore National Registration Identity Card (NRIC) Number</span></span>
- <span data-ttu-id="c5b22-223">South Africa Identification Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-223">South Africa Identification Number</span></span>  
- <span data-ttu-id="c5b22-224">Sydkoreas invånarregistreringsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-224">South Korea Resident Registration Number</span></span>
- <span data-ttu-id="c5b22-225">Spain Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="c5b22-225">Spain Social Security Number (SSN)</span></span>
- <span data-ttu-id="c5b22-226">SQL Server-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="c5b22-226">SQL Server Connection String</span></span>  
- <span data-ttu-id="c5b22-227">National ID för Sverige</span><span class="sxs-lookup"><span data-stu-id="c5b22-227">Sweden National ID</span></span>
- <span data-ttu-id="c5b22-228">Sverige Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-228">Sweden Passport Number</span></span>
- <span data-ttu-id="c5b22-229">SWIFT-kod</span><span class="sxs-lookup"><span data-stu-id="c5b22-229">SWIFT Code</span></span>
- <span data-ttu-id="c5b22-230">Taiwan National ID</span><span class="sxs-lookup"><span data-stu-id="c5b22-230">Taiwan National ID</span></span>
- <span data-ttu-id="c5b22-231">Taiwan Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-231">Taiwan Passport Number</span></span>
- <span data-ttu-id="c5b22-232">Taiwan Resident Certificate (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="c5b22-232">Taiwan Resident Certificate (ARC/TARC)</span></span>
- <span data-ttu-id="c5b22-233">Identifieringskod för thailändska</span><span class="sxs-lookup"><span data-stu-id="c5b22-233">Thai Population Identification Code</span></span>
- <span data-ttu-id="c5b22-234">Turkiska National Identification Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-234">Turkish National Identification number</span></span>
- <span data-ttu-id="c5b22-235">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="c5b22-235">U.K.</span></span> <span data-ttu-id="c5b22-236">Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-236">Driver's License Number</span></span>
- <span data-ttu-id="c5b22-237">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="c5b22-237">U.K.</span></span> <span data-ttu-id="c5b22-238">E-nummer för att samla in</span><span class="sxs-lookup"><span data-stu-id="c5b22-238">Electoral Roll Number</span></span>
- <span data-ttu-id="c5b22-239">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="c5b22-239">U.K.</span></span> <span data-ttu-id="c5b22-240">National Health Service Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-240">National Health Service Number</span></span>
- <span data-ttu-id="c5b22-241">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="c5b22-241">U.K.</span></span> <span data-ttu-id="c5b22-242">National Insurance Number (NINO)</span><span class="sxs-lookup"><span data-stu-id="c5b22-242">National Insurance Number (NINO)</span></span>
- <span data-ttu-id="c5b22-243">U.S. / Storbritannien</span><span class="sxs-lookup"><span data-stu-id="c5b22-243">U.S. / U.K.</span></span> <span data-ttu-id="c5b22-244">Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-244">Passport Number</span></span>
- <span data-ttu-id="c5b22-245">U.S. Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-245">U.S. Bank Account Number</span></span>
- <span data-ttu-id="c5b22-246">U.S. Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-246">U.S. Driver's License Number</span></span>
- <span data-ttu-id="c5b22-247">U.S. Individual Taxpayer Identification Number (ITIN)</span><span class="sxs-lookup"><span data-stu-id="c5b22-247">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="c5b22-248">U.S. Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="c5b22-248">U.S. Social Security Number (SSN)</span></span>

<span data-ttu-id="c5b22-249">Observera att anpassade typer av känslig information även stöds för DLP-principtips, utöver de för in visna typerna av känslig information.</span><span class="sxs-lookup"><span data-stu-id="c5b22-249">Please note that custom sensitive information types are also supported for DLP policy tips in addition to the above out-of-the-box sensitive information types.</span></span>

## <a name="data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="c5b22-250">Dataförlustskydd på slutpunktsenheter har stöd för principtips för endast vissa typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="c5b22-250">Data Loss Prevention on endpoint devices supports policy tips for only some sensitive information types</span></span>

<span data-ttu-id="c5b22-251">Listan över inringningstyper för känslig information som identifieras i dokument som lagras på slutpunktsenheter är följande:</span><span class="sxs-lookup"><span data-stu-id="c5b22-251">The list of out-of-the-box sensitive information types that will be detected in documents residing on endpoint devices are the following :</span></span>

- <span data-ttu-id="c5b22-252">ABA-routningsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-252">ABA Routing Number</span></span> 
- <span data-ttu-id="c5b22-253">Argentina National Identity (DNI) Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-253">Argentina National Identity (DNI) Number</span></span> 
- <span data-ttu-id="c5b22-254">Bank Account Number för Australien</span><span class="sxs-lookup"><span data-stu-id="c5b22-254">Australia Bank Account Number</span></span> 
- <span data-ttu-id="c5b22-255">Australiens medicinska kontonummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-255">Australia Medical Account Number</span></span> 
- <span data-ttu-id="c5b22-256">Australia Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-256">Australia Passport Number</span></span> 
- <span data-ttu-id="c5b22-257">Australiens skattenummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-257">Australia Tax File Number</span></span> 
- <span data-ttu-id="c5b22-258">Australiensiska företagsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-258">Australian Business Number</span></span> 
- <span data-ttu-id="c5b22-259">Australiensiska företags nummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-259">Australian Company Number</span></span> 
- <span data-ttu-id="c5b22-260">Österrikes registreringsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-260">Austria Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-261">Österrike-identitetskort</span><span class="sxs-lookup"><span data-stu-id="c5b22-261">Austria Identity Card</span></span> 
- <span data-ttu-id="c5b22-262">Österrike Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-262">Austria Passport Number</span></span> 
- <span data-ttu-id="c5b22-263">Österrike, social security number</span><span class="sxs-lookup"><span data-stu-id="c5b22-263">Austria Social Security Number</span></span> 
- <span data-ttu-id="c5b22-264">Österrike skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-264">Austria Tax Identification Number</span></span> 
- <span data-ttu-id="c5b22-265">Österrike , momsregistreringsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-265">Austria Value Added Tax (VAT) Number</span></span> 
- <span data-ttu-id="c5b22-266">Autentiseringsnyckel för Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="c5b22-266">Azure DocumentDB Auth Key</span></span> 
- <span data-ttu-id="c5b22-267">Azure IAAS-databasanslutningssträng och Azure SQL-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="c5b22-267">Azure IAAS Database Connection String and Azure SQL Connection String</span></span> 
- <span data-ttu-id="c5b22-268">Azure IoT-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="c5b22-268">Azure IoT Connection String</span></span> 
- <span data-ttu-id="c5b22-269">Lösenord för Inställning av Azure-publicering</span><span class="sxs-lookup"><span data-stu-id="c5b22-269">Azure Publish Setting Password</span></span> 
- <span data-ttu-id="c5b22-270">Azure Redis Cache-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="c5b22-270">Azure Redis Cache Connection String</span></span> 
- <span data-ttu-id="c5b22-271">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="c5b22-271">Azure SAS</span></span> 
- <span data-ttu-id="c5b22-272">Azure Service Bus Connection String</span><span class="sxs-lookup"><span data-stu-id="c5b22-272">Azure Service Bus Connection String</span></span> 
- <span data-ttu-id="c5b22-273">Azure Storage Account Key</span><span class="sxs-lookup"><span data-stu-id="c5b22-273">Azure Storage Account Key</span></span> 
- <span data-ttu-id="c5b22-274">Azure Storage Account Key (generic)</span><span class="sxs-lookup"><span data-stu-id="c5b22-274">Azure Storage Account Key (Generic)</span></span> 
- <span data-ttu-id="c5b22-275">Belgien Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-275">Belgium Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-276">Belgiens nationalnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-276">Belgium National Number</span></span> 
- <span data-ttu-id="c5b22-277">Belgien Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-277">Belgium Passport Number</span></span> 
- <span data-ttu-id="c5b22-278">Belgium Value Added Tax Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-278">Belgium Value Added Tax Number</span></span> 
- <span data-ttu-id="c5b22-279">Brasilien CPF-nummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-279">Brazil CPF Number</span></span> 
- <span data-ttu-id="c5b22-280">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="c5b22-280">Brazil Legal Entity Number (CNPJ)</span></span> 
- <span data-ttu-id="c5b22-281">Brazil National ID Card (RG)</span><span class="sxs-lookup"><span data-stu-id="c5b22-281">Brazil National ID Card (RG)</span></span> 
- <span data-ttu-id="c5b22-282">Bulgariens registreringsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-282">Bulgaria Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-283">Bulgarien Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-283">Bulgaria Passport Number</span></span> 
- <span data-ttu-id="c5b22-284">Bulgariens enhetliga civilnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-284">Bulgaria Uniform Civil Number</span></span> 
- <span data-ttu-id="c5b22-285">Bank Account Number för Kanada</span><span class="sxs-lookup"><span data-stu-id="c5b22-285">Canada Bank Account Number</span></span> 
- <span data-ttu-id="c5b22-286">Kanadas driver's License Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-286">Canada Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-287">Canada Health Service Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-287">Canada Health Service Number</span></span> 
- <span data-ttu-id="c5b22-288">Canada Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-288">Canada Passport Number</span></span> 
- <span data-ttu-id="c5b22-289">Canada Personal Health Identification Number (PHIN)</span><span class="sxs-lookup"><span data-stu-id="c5b22-289">Canada Personal Health Identification Number (PHIN)</span></span> 
- <span data-ttu-id="c5b22-290">Canada Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-290">Canada Social Insurance Number</span></span> 
- <span data-ttu-id="c5b22-291">Chile Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-291">Chile Identity Card Number</span></span> 
- <span data-ttu-id="c5b22-292">China Resident Identity Card (Folkrepubliken Kina) Nummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-292">China Resident Identity Card (PRC) Number</span></span> 
- <span data-ttu-id="c5b22-293">Kreditkortsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-293">Credit Card Number</span></span> 
- <span data-ttu-id="c5b22-294">Kroatiens licensnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-294">Croatia Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-295">Kroatiens identitetskortsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-295">Croatia Identity Card Number</span></span> 
- <span data-ttu-id="c5b22-296">Kroatiens National ID-kortnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-296">Croatia National ID Card Number</span></span> 
- <span data-ttu-id="c5b22-297">Kroatien Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-297">Croatia Passport Number</span></span> 
- <span data-ttu-id="c5b22-298">Kroatiens OIB-nummer (Personal Identification)</span><span class="sxs-lookup"><span data-stu-id="c5b22-298">Croatia Personal Identification (OIB) Number</span></span> 
- <span data-ttu-id="c5b22-299">CSCAN-AZURE0060 Signatur för delat åtkomstkonto för Azure-lagring</span><span class="sxs-lookup"><span data-stu-id="c5b22-299">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span></span> 
- <span data-ttu-id="c5b22-300">CSCAN-GENERAL0140 allmän symmetrisk nyckel</span><span class="sxs-lookup"><span data-stu-id="c5b22-300">CSCAN-GENERAL0140 General Symmetric Key</span></span> 
- <span data-ttu-id="c5b22-301">Cyperns drivrutinslicensnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-301">Cyprus Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-302">Cypern-identitetskort</span><span class="sxs-lookup"><span data-stu-id="c5b22-302">Cyprus Identity Card</span></span> 
- <span data-ttu-id="c5b22-303">Cypern Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-303">Cyprus Passport Number</span></span> 
- <span data-ttu-id="c5b22-304">Cyperns skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-304">Cyprus Tax Identification Number</span></span> 
- <span data-ttu-id="c5b22-305">Tjeckiska driver's License Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-305">Czech Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-306">Tjeckiska Personliga identitetsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-306">Czech Personal Identity Number</span></span> 
- <span data-ttu-id="c5b22-307">Tjeckien Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-307">Czech Republic Passport Number</span></span> 
- <span data-ttu-id="c5b22-308">Danmarks körkortsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-308">Denmark Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-309">Danmark Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-309">Denmark Passport Number</span></span> 
- <span data-ttu-id="c5b22-310">Danmarks personliga id-nummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-310">Denmark Personal Identification Number</span></span> 
- <span data-ttu-id="c5b22-311">Tvingande Enforcement Agency (DEA) Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-311">Drug Enforcement Agency (DEA) Number</span></span> 
- <span data-ttu-id="c5b22-312">Estlands licensnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-312">Estonia Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-313">Estland Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-313">Estonia Passport Number</span></span> 
- <span data-ttu-id="c5b22-314">Estland – personidentifieringskod</span><span class="sxs-lookup"><span data-stu-id="c5b22-314">Estonia Personal Identification Code</span></span> 
- <span data-ttu-id="c5b22-315">Betalkortsnummer (EU)</span><span class="sxs-lookup"><span data-stu-id="c5b22-315">EU Debit Card Number</span></span> 
- <span data-ttu-id="c5b22-316">EU:s körkortsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-316">EU Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-317">EU National Identification Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-317">EU National Identification Number</span></span> 
- <span data-ttu-id="c5b22-318">EU Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-318">EU Passport Number</span></span> 
- <span data-ttu-id="c5b22-319">SOCIAL SECURITY Number (SSN) eller motsvarande ID</span><span class="sxs-lookup"><span data-stu-id="c5b22-319">EU Social Security Number (SSN) or Equivalent ID</span></span> 
- <span data-ttu-id="c5b22-320">EU:s skatteidentifieringsnummer (TIN)</span><span class="sxs-lookup"><span data-stu-id="c5b22-320">EU Tax Identification Number (TIN)</span></span> 
- <span data-ttu-id="c5b22-321">Finland Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-321">Finland Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-322">Finland European Health Insurance Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-322">Finland European Health Insurance Number</span></span> 
- <span data-ttu-id="c5b22-323">Finlands national-ID</span><span class="sxs-lookup"><span data-stu-id="c5b22-323">Finland National ID</span></span> 
- <span data-ttu-id="c5b22-324">Finland Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-324">Finland Passport Number</span></span> 
- <span data-ttu-id="c5b22-325">Frankrikes licensnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-325">France Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-326">France Health Insurance Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-326">France Health Insurance Number</span></span> 
- <span data-ttu-id="c5b22-327">France National ID Card (CNI)</span><span class="sxs-lookup"><span data-stu-id="c5b22-327">France National ID Card (CNI)</span></span> 
- <span data-ttu-id="c5b22-328">France Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-328">France Passport Number</span></span> 
- <span data-ttu-id="c5b22-329">France Social Security Number (INSEE)</span><span class="sxs-lookup"><span data-stu-id="c5b22-329">France Social Security Number (INSEE)</span></span> 
- <span data-ttu-id="c5b22-330">France Tax Identification Number (numéro SPI.)</span><span class="sxs-lookup"><span data-stu-id="c5b22-330">France Tax Identification Number (numéro SPI.)</span></span> 
- <span data-ttu-id="c5b22-331">France Value Added Tax Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-331">France Value Added Tax Number</span></span> 
- <span data-ttu-id="c5b22-332">Tyskt körkortsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-332">German Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-333">Tyska Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-333">German Passport Number</span></span> 
- <span data-ttu-id="c5b22-334">Id Card Number för Tyskland</span><span class="sxs-lookup"><span data-stu-id="c5b22-334">Germany Identity Card Number</span></span> 
- <span data-ttu-id="c5b22-335">Tysklands skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-335">Germany Tax Identification Number</span></span> 
- <span data-ttu-id="c5b22-336">Värdeskattenummer för Tyskland</span><span class="sxs-lookup"><span data-stu-id="c5b22-336">Germany Value Added Tax Number</span></span> 
- <span data-ttu-id="c5b22-337">Greklands körkortsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-337">Greece Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-338">Greklands national-ID-kort</span><span class="sxs-lookup"><span data-stu-id="c5b22-338">Greece National ID Card</span></span> 
- <span data-ttu-id="c5b22-339">Greklands passnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-339">Greece Passport Number</span></span> 
- <span data-ttu-id="c5b22-340">Greklands social securitynummer (AMKA)</span><span class="sxs-lookup"><span data-stu-id="c5b22-340">Greece Social Security Number (AMKA)</span></span> 
- <span data-ttu-id="c5b22-341">Grekiska skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-341">Greek Tax identification Number</span></span> 
- <span data-ttu-id="c5b22-342">Hong Kong Identity Card (HKID)-nummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-342">Hong Kong Identity Card (HKID) Number</span></span> 
- <span data-ttu-id="c5b22-343">Ungerska social security number (TAD)</span><span class="sxs-lookup"><span data-stu-id="c5b22-343">Hungarian Social Security Number (TAJ)</span></span> 
- <span data-ttu-id="c5b22-344">Ungerska nummer med moms</span><span class="sxs-lookup"><span data-stu-id="c5b22-344">Hungarian Value Added Tax Number</span></span> 
- <span data-ttu-id="c5b22-345">Ungerns registreringsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-345">Hungary Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-346">Ungern Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-346">Hungary Passport Number</span></span> 
- <span data-ttu-id="c5b22-347">Ungerns personliga id-nummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-347">Hungary Personal Identification Number</span></span> 
- <span data-ttu-id="c5b22-348">Ungerns skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-348">Hungary Tax identification Number</span></span> 
- <span data-ttu-id="c5b22-349">Indiens permanenta kontonummer (PAN)</span><span class="sxs-lookup"><span data-stu-id="c5b22-349">India Permanent Account Number (PAN)</span></span> 
- <span data-ttu-id="c5b22-350">India Unique Identification (Aadhaar) Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-350">India Unique Identification (Aadhaar) Number</span></span> 
- <span data-ttu-id="c5b22-351">Indonesia Identity Card-nummer (KTP)</span><span class="sxs-lookup"><span data-stu-id="c5b22-351">Indonesia Identity Card (KTP) Number</span></span> 
- <span data-ttu-id="c5b22-352">International Banking Account Number (IBAN)</span><span class="sxs-lookup"><span data-stu-id="c5b22-352">International Banking Account Number (IBAN)</span></span> 
- <span data-ttu-id="c5b22-353">Internationell klassificering av avnärende (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="c5b22-353">International Classification of Diseases (ICD-10-CM)</span></span> 
- <span data-ttu-id="c5b22-354">Internationell klassificering av tidsklassificering (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="c5b22-354">International Classification of Diseases (ICD-9-CM)</span></span> 
- <span data-ttu-id="c5b22-355">IP-adress</span><span class="sxs-lookup"><span data-stu-id="c5b22-355">IP Address</span></span> 
- <span data-ttu-id="c5b22-356">Ireland Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-356">Ireland Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-357">Ireland Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-357">Ireland Passport Number</span></span> 
- <span data-ttu-id="c5b22-358">Ireland Personal Public Service -nummer (PPS)</span><span class="sxs-lookup"><span data-stu-id="c5b22-358">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="c5b22-359">Israels bankkontonummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-359">Israel Bank Account Number</span></span> 
- <span data-ttu-id="c5b22-360">Israels national-ID</span><span class="sxs-lookup"><span data-stu-id="c5b22-360">Israel National ID</span></span> 
- <span data-ttu-id="c5b22-361">Italiens licensnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-361">Italy Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-362">Italiens räkenskapskod</span><span class="sxs-lookup"><span data-stu-id="c5b22-362">Italy Fiscal Code</span></span> 
- <span data-ttu-id="c5b22-363">Italy Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-363">Italy Passport Number</span></span> 
- <span data-ttu-id="c5b22-364">Italy Value Added Tax Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-364">Italy Value Added Tax Number</span></span> 
- <span data-ttu-id="c5b22-365">Japan Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-365">Japan Bank Account Number</span></span> 
- <span data-ttu-id="c5b22-366">Japan Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-366">Japan Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-367">Japan Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-367">Japan Passport Number</span></span> 
- <span data-ttu-id="c5b22-368">Invånarregistreringsnummer för Japan</span><span class="sxs-lookup"><span data-stu-id="c5b22-368">Japan Resident Registration Number</span></span> 
- <span data-ttu-id="c5b22-369">Japan Social Insurance Number (SIN)</span><span class="sxs-lookup"><span data-stu-id="c5b22-369">Japan Social Insurance Number (SIN)</span></span> 
- <span data-ttu-id="c5b22-370">Japanska My Number Corporate</span><span class="sxs-lookup"><span data-stu-id="c5b22-370">Japanese My Number Corporate</span></span> 
- <span data-ttu-id="c5b22-371">Japanska, Mitt nummer Personligt</span><span class="sxs-lookup"><span data-stu-id="c5b22-371">Japanese My Number Personal</span></span> 
- <span data-ttu-id="c5b22-372">Japanska Residence Card Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-372">Japanese Residence Card Number</span></span> 
- <span data-ttu-id="c5b22-373">Lettlands drivrutinslicensnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-373">Latvia Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-374">Lettlands passport number</span><span class="sxs-lookup"><span data-stu-id="c5b22-374">Latvia Passport Number</span></span> 
- <span data-ttu-id="c5b22-375">Personlig kod för Lettland</span><span class="sxs-lookup"><span data-stu-id="c5b22-375">Latvia Personal Code</span></span> 
- <span data-ttu-id="c5b22-376">Litauens licensnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-376">Lithuania Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-377">Litauen Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-377">Lithuania Passport Number</span></span> 
- <span data-ttu-id="c5b22-378">Litauen – personlig kod</span><span class="sxs-lookup"><span data-stu-id="c5b22-378">Lithuania Personal Code</span></span> 
- <span data-ttu-id="c5b22-379">Luxemburg-drivrutinens licensnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-379">Luxemburg Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-380">Luxemburg National Identification Number (naturliga personer)</span><span class="sxs-lookup"><span data-stu-id="c5b22-380">Luxemburg National Identification Number (Natural persons)</span></span> 
- <span data-ttu-id="c5b22-381">Luxemburg National Identification Number (icke-naturliga personer)</span><span class="sxs-lookup"><span data-stu-id="c5b22-381">Luxemburg National Identification Number (Non-natural persons)</span></span> 
- <span data-ttu-id="c5b22-382">Luxemburg Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-382">Luxemburg Passport Number</span></span> 
- <span data-ttu-id="c5b22-383">Malaysia Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-383">Malaysia Identity Card Number</span></span> 
- <span data-ttu-id="c5b22-384">Malta Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-384">Malta Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-385">Malta-identitetskortsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-385">Malta Identity Card Number</span></span> 
- <span data-ttu-id="c5b22-386">Malta Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-386">Malta Passport Number</span></span> 
- <span data-ttu-id="c5b22-387">Maltas skattenummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-387">Malta Tax ID Number</span></span> 
- <span data-ttu-id="c5b22-388">Nederländska medborgares servicenummer (BSN)</span><span class="sxs-lookup"><span data-stu-id="c5b22-388">Netherlands Citizen's Service (BSN) Number</span></span> 
- <span data-ttu-id="c5b22-389">Nederländska driver's License Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-389">Netherlands Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-390">Nederländerna Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-390">Netherlands Passport Number</span></span> 
- <span data-ttu-id="c5b22-391">Nederländska skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-391">Netherlands Tax Identification Number</span></span> 
- <span data-ttu-id="c5b22-392">Nederländska värdeskattenummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-392">Netherlands Value Added Tax Number</span></span> 
- <span data-ttu-id="c5b22-393">Bankkontonummer för Nya Zeeland</span><span class="sxs-lookup"><span data-stu-id="c5b22-393">New Zealand bank account number</span></span> 
- <span data-ttu-id="c5b22-394">New Zealand Driver License Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-394">New Zealand Driver License Number</span></span> 
- <span data-ttu-id="c5b22-395">New Zealand Inland Revenue number</span><span class="sxs-lookup"><span data-stu-id="c5b22-395">New Zealand Inland Revenue number</span></span> 
- <span data-ttu-id="c5b22-396">New Zealand Ministry of Health Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-396">New Zealand Ministry of Health Number</span></span> 
- <span data-ttu-id="c5b22-397">New Zealand Social Enl. Nummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-397">New Zealand Social Welfare Number</span></span> 
- <span data-ttu-id="c5b22-398">Norges identitetsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-398">Norway Identity Number</span></span> 
- <span data-ttu-id="c5b22-399">Philippines Unified Multi-Purpose ID Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-399">Philippines Unified Multi-Purpose ID Number</span></span> 
- <span data-ttu-id="c5b22-400">Polens licensnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-400">Poland Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-401">Polens identitetskort</span><span class="sxs-lookup"><span data-stu-id="c5b22-401">Poland Identity Card</span></span> 
- <span data-ttu-id="c5b22-402">Polens National ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="c5b22-402">Poland National ID (PESEL)</span></span> 
- <span data-ttu-id="c5b22-403">Polen-pass</span><span class="sxs-lookup"><span data-stu-id="c5b22-403">Poland Passport</span></span> 
- <span data-ttu-id="c5b22-404">Polens skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-404">Poland Tax Identification Number</span></span> 
- <span data-ttu-id="c5b22-405">Polska REGON-nummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-405">Polish REGON Number</span></span> 
- <span data-ttu-id="c5b22-406">Portugal, kreditkortsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-406">Portugal Citizen Card Number</span></span> 
- <span data-ttu-id="c5b22-407">Portugal Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-407">Portugal Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-408">Portugal Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-408">Portugal Passport Number</span></span> 
- <span data-ttu-id="c5b22-409">Portugals skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-409">Portugal Tax Identification Number</span></span> 
- <span data-ttu-id="c5b22-410">Rumäniens registreringsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-410">Romania Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-411">Rumänien Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-411">Romania Passport Number</span></span> 
- <span data-ttu-id="c5b22-412">Rumäniens personliga numeriska kod (CNP)</span><span class="sxs-lookup"><span data-stu-id="c5b22-412">Romania Personal Numerical Code (CNP)</span></span> 
- <span data-ttu-id="c5b22-413">Ryska passnummer (inrikes)</span><span class="sxs-lookup"><span data-stu-id="c5b22-413">Russian Passport Number (Domestic)</span></span> 
- <span data-ttu-id="c5b22-414">Ryska Passport Number (internationellt)</span><span class="sxs-lookup"><span data-stu-id="c5b22-414">Russian Passport Number (International)</span></span> 
- <span data-ttu-id="c5b22-415">Saudiarabiens national-ID</span><span class="sxs-lookup"><span data-stu-id="c5b22-415">Saudi Arabia National ID</span></span> 
- <span data-ttu-id="c5b22-416">Singapore National Registration Identity Card (NRIC) Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-416">Singapore National Registration Identity Card (NRIC) Number</span></span> 
- <span data-ttu-id="c5b22-417">Slovakiens licensnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-417">Slovakia Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-418">Slovakien Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-418">Slovakia Passport Number</span></span> 
- <span data-ttu-id="c5b22-419">Slovakiens personliga nummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-419">Slovakia Personal Number</span></span> 
- <span data-ttu-id="c5b22-420">Sloveniens körkortsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-420">Slovenia Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-421">Slovenien Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-421">Slovenia Passport Number</span></span> 
- <span data-ttu-id="c5b22-422">Sloveniens skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-422">Slovenia Tax Identification Number</span></span> 
- <span data-ttu-id="c5b22-423">Slovenska unik master number</span><span class="sxs-lookup"><span data-stu-id="c5b22-423">Slovenia Unique Master Citizen Number</span></span> 
- <span data-ttu-id="c5b22-424">South Africa Identification Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-424">South Africa Identification Number</span></span> 
- <span data-ttu-id="c5b22-425">Sydkoreas invånarregistreringsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-425">South Korea Resident Registration Number</span></span> 
- <span data-ttu-id="c5b22-426">Spanien DNI</span><span class="sxs-lookup"><span data-stu-id="c5b22-426">Spain DNI</span></span> 
- <span data-ttu-id="c5b22-427">Spaniens licensnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-427">Spain Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-428">Spain Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-428">Spain Passport Number</span></span> 
- <span data-ttu-id="c5b22-429">Spain Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="c5b22-429">Spain Social Security Number (SSN)</span></span> 
- <span data-ttu-id="c5b22-430">Spaniens skatteidentifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-430">Spain Tax Identification Number</span></span> 
- <span data-ttu-id="c5b22-431">SQL Server-anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="c5b22-431">SQL Server Connection String</span></span> 
- <span data-ttu-id="c5b22-432">Sverige driver's License Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-432">Sweden Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-433">National ID för Sverige</span><span class="sxs-lookup"><span data-stu-id="c5b22-433">Sweden National ID</span></span> 
- <span data-ttu-id="c5b22-434">Sverige Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-434">Sweden Passport Number</span></span> 
- <span data-ttu-id="c5b22-435">Skatteidentifieringsnummer i Sverige</span><span class="sxs-lookup"><span data-stu-id="c5b22-435">Sweden Tax Identification Number</span></span> 
- <span data-ttu-id="c5b22-436">SWIFT-kod</span><span class="sxs-lookup"><span data-stu-id="c5b22-436">SWIFT Code</span></span> 
- <span data-ttu-id="c5b22-437">Swiss Social Security Number AHV</span><span class="sxs-lookup"><span data-stu-id="c5b22-437">Swiss Social Security Number AHV</span></span> 
- <span data-ttu-id="c5b22-438">Taiwan National ID</span><span class="sxs-lookup"><span data-stu-id="c5b22-438">Taiwan National ID</span></span> 
- <span data-ttu-id="c5b22-439">Taiwan Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-439">Taiwan Passport Number</span></span> 
- <span data-ttu-id="c5b22-440">Taiwan Resident Certificate (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="c5b22-440">Taiwan Resident Certificate (ARC/TARC)</span></span> 
- <span data-ttu-id="c5b22-441">Identifieringskod för thailändska</span><span class="sxs-lookup"><span data-stu-id="c5b22-441">Thai Population Identification Code</span></span> 
- <span data-ttu-id="c5b22-442">Turkiska National Identification Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-442">Turkish National Identification number</span></span> 
- <span data-ttu-id="c5b22-443">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="c5b22-443">U.K.</span></span> <span data-ttu-id="c5b22-444">Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-444">Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-445">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="c5b22-445">U.K.</span></span> <span data-ttu-id="c5b22-446">E-nummer för att samla in</span><span class="sxs-lookup"><span data-stu-id="c5b22-446">Electoral Roll Number</span></span> 
- <span data-ttu-id="c5b22-447">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="c5b22-447">U.K.</span></span> <span data-ttu-id="c5b22-448">National Health Service Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-448">National Health Service Number</span></span> 
- <span data-ttu-id="c5b22-449">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="c5b22-449">U.K.</span></span> <span data-ttu-id="c5b22-450">National Insurance Number (NINO)</span><span class="sxs-lookup"><span data-stu-id="c5b22-450">National Insurance Number (NINO)</span></span> 
- <span data-ttu-id="c5b22-451">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="c5b22-451">U.K.</span></span> <span data-ttu-id="c5b22-452">Unique Taxpayer-referensnummer</span><span class="sxs-lookup"><span data-stu-id="c5b22-452">Unique Taxpayer Reference Number</span></span> 
- <span data-ttu-id="c5b22-453">U.S. / Storbritannien</span><span class="sxs-lookup"><span data-stu-id="c5b22-453">U.S. / U.K.</span></span> <span data-ttu-id="c5b22-454">Passport Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-454">Passport Number</span></span> 
- <span data-ttu-id="c5b22-455">U.S. Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-455">U.S. Bank Account Number</span></span> 
- <span data-ttu-id="c5b22-456">U.S. Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="c5b22-456">U.S. Driver's License Number</span></span> 
- <span data-ttu-id="c5b22-457">U.S. Individual Taxpayer Identification Number (ITIN)</span><span class="sxs-lookup"><span data-stu-id="c5b22-457">U.S. Individual Taxpayer Identification Number (ITIN)</span></span> 
- <span data-ttu-id="c5b22-458">U.S. Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="c5b22-458">U.S. Social Security Number (SSN)</span></span> 
- <span data-ttu-id="c5b22-459">Ukraina Passport Number (inrikes)</span><span class="sxs-lookup"><span data-stu-id="c5b22-459">Ukraine Passport Number (Domestic)</span></span> 
- <span data-ttu-id="c5b22-460">Ukraina Passport Number (internationellt)</span><span class="sxs-lookup"><span data-stu-id="c5b22-460">Ukraine Passport Number (International)</span></span> 
 
<span data-ttu-id="c5b22-461">Observera att anpassade typer av känslig information också identifieras, utöver de för insmådde typerna av känslig information</span><span class="sxs-lookup"><span data-stu-id="c5b22-461">Please note that custom sensitive information types will also be detected in addition to the above out-of-the-box sensitive information types</span></span>

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a><span data-ttu-id="c5b22-462">Tips om stödmatris för DLP-principen i Microsoft-appar</span><span class="sxs-lookup"><span data-stu-id="c5b22-462">Support Matrix for DLP policy tips across Microsoft apps</span></span>

|<span data-ttu-id="c5b22-463">**App och plattform**</span><span class="sxs-lookup"><span data-stu-id="c5b22-463">**App and platform**</span></span>|<span data-ttu-id="c5b22-464">**Stöd för DLP-principtips**</span><span class="sxs-lookup"><span data-stu-id="c5b22-464">**DLP policy tip support**</span></span>|<span data-ttu-id="c5b22-465">**Typer av känslig information som stöds**</span><span class="sxs-lookup"><span data-stu-id="c5b22-465">**Sensitive information types supported**</span></span>|<span data-ttu-id="c5b22-466">**Predikat och åtgärder som stöds**</span><span class="sxs-lookup"><span data-stu-id="c5b22-466">**Predicates and actions supported**</span></span>|<span data-ttu-id="c5b22-467">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="c5b22-467">**Comments**</span></span>|
|:--|:--|:--|:--|:--|
|<span data-ttu-id="c5b22-468">**Outlook Web Access**</span><span class="sxs-lookup"><span data-stu-id="c5b22-468">**Outlook Web Access**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="c5b22-469">Alla</span><span class="sxs-lookup"><span data-stu-id="c5b22-469">All</span></span>|<span data-ttu-id="c5b22-470">Delmängd</span><span class="sxs-lookup"><span data-stu-id="c5b22-470">Subset</span></span>|<span data-ttu-id="c5b22-471">Se [referens för policytips för skydd mot dataförlust](#data-loss-prevention-policy-tips-reference)</span><span class="sxs-lookup"><span data-stu-id="c5b22-471">See [Data Loss Prevention policy tips reference](#data-loss-prevention-policy-tips-reference)</span></span>|
|<span data-ttu-id="c5b22-472">**Outlook Win32 (Outlook 2013 och vidare)**</span><span class="sxs-lookup"><span data-stu-id="c5b22-472">**Outlook Win32 (Outlook 2013 and beyond)**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="c5b22-473">Delmängd</span><span class="sxs-lookup"><span data-stu-id="c5b22-473">Subset</span></span>|<span data-ttu-id="c5b22-474">Delmängd</span><span class="sxs-lookup"><span data-stu-id="c5b22-474">Subset</span></span>|<span data-ttu-id="c5b22-475">Se [Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) och senare med stöd för att visa principtips för bara vissa villkor och undantag och stöd för Outlook [2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) och senare samt Stöd för Office-program på skrivbordet med principtips för endast vissa typer av känslig information om information om stöd för typer av känslig information och vilka DLP-villkor och åtgärder som stöds för att visa DLP-principtips i Outlook Win32.</span><span class="sxs-lookup"><span data-stu-id="c5b22-475">See [Outlook 2013 and later supports showing policy tips for only some conditions and exceptions](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) and [Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) for details on support for sensitive information types and DLP conditions and actions supported for showing DLP policy tips on Outlook Win32.</span></span>|
|<span data-ttu-id="c5b22-476">**Outlook Mobile (iOS, Android)/Outlook Mac**</span><span class="sxs-lookup"><span data-stu-id="c5b22-476">**Outlook Mobile (iOS, Android)/Outlook Mac**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="c5b22-477">Inga</span><span class="sxs-lookup"><span data-stu-id="c5b22-477">None</span></span>|<span data-ttu-id="c5b22-478">Inga</span><span class="sxs-lookup"><span data-stu-id="c5b22-478">None</span></span>|<span data-ttu-id="c5b22-479">Tips för DLP-policyer stöds inte i Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="c5b22-479">DLP policy tips are not supported on Outlook mobile</span></span>|
|<span data-ttu-id="c5b22-480">**Sharepoint Online/One Drive för företag-webbklient**</span><span class="sxs-lookup"><span data-stu-id="c5b22-480">**Sharepoint Online/One Drive for Business Web client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="c5b22-481">Alla</span><span class="sxs-lookup"><span data-stu-id="c5b22-481">All</span></span>|<span data-ttu-id="c5b22-482">Alla SPO/ODB-predikat och åtgärder i DLP</span><span class="sxs-lookup"><span data-stu-id="c5b22-482">All SPO/ODB predicates and actions in DLP</span></span>||
|<span data-ttu-id="c5b22-483">**Sharepoint Win32/ One Drive för företag Win32-klient**</span><span class="sxs-lookup"><span data-stu-id="c5b22-483">**Sharepoint Win32/ One Drive for Business Win32 client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="c5b22-484">Inga</span><span class="sxs-lookup"><span data-stu-id="c5b22-484">None</span></span>|<span data-ttu-id="c5b22-485">Inga</span><span class="sxs-lookup"><span data-stu-id="c5b22-485">None</span></span>|<span data-ttu-id="c5b22-486">Tips för DLP-princip stöds inte i Sharepoint- eller OneDrive-klientprogram</span><span class="sxs-lookup"><span data-stu-id="c5b22-486">DLP policy tips are not supported on Sharepoint or OneDrive desktop client apps</span></span>|
|<span data-ttu-id="c5b22-487">**Word, Excel, PowerPoint Web Client**</span><span class="sxs-lookup"><span data-stu-id="c5b22-487">**Word, Excel, PowerPoint Web Client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="c5b22-488">Alla</span><span class="sxs-lookup"><span data-stu-id="c5b22-488">All</span></span>|<span data-ttu-id="c5b22-489">Alla SPO/ODB-predikat och åtgärder i DLP</span><span class="sxs-lookup"><span data-stu-id="c5b22-489">All SPO/ODB predicates and actions in DLP</span></span>|<span data-ttu-id="c5b22-490">Tips för DLP-princip stöds om dokumentet ligger på SPO- eller ODB-webbappen och DLP-principen redan har stämplats.</span><span class="sxs-lookup"><span data-stu-id="c5b22-490">DLP policy tip is supported if the document is hosted on SPO or ODB web app and the DLP policy is already stamped.</span></span>|
|<span data-ttu-id="c5b22-491">**Word, Excel, PowerPoint Mobile-klient**</span><span class="sxs-lookup"><span data-stu-id="c5b22-491">**Word, Excel, PowerPoint Mobile Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="c5b22-492">Inga</span><span class="sxs-lookup"><span data-stu-id="c5b22-492">None</span></span>|<span data-ttu-id="c5b22-493">Inga</span><span class="sxs-lookup"><span data-stu-id="c5b22-493">None</span></span>|<span data-ttu-id="c5b22-494">Tips för DLP-princip stöds inte i mobilappar för Office.</span><span class="sxs-lookup"><span data-stu-id="c5b22-494">DLP policy tips are not supported in mobile apps for Office.</span></span>|
|<span data-ttu-id="c5b22-495">**Teams Webb/ Teams skrivbords- / Teams Mobile/ Teams Mac**</span><span class="sxs-lookup"><span data-stu-id="c5b22-495">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="c5b22-496">Alla</span><span class="sxs-lookup"><span data-stu-id="c5b22-496">All</span></span>|<span data-ttu-id="c5b22-497">Alla Teams-predikat i DLP-princip</span><span class="sxs-lookup"><span data-stu-id="c5b22-497">All Teams predicates in DLP policy</span></span>|<span data-ttu-id="c5b22-498">Principtips visas när ett meddelande flaggas som "Det här meddelandet har flaggats.</span><span class="sxs-lookup"><span data-stu-id="c5b22-498">Policy tips will show when a message is flagged as “This message has been flagged.</span></span> <span data-ttu-id="c5b22-499">Vad kan jag göra?"</span><span class="sxs-lookup"><span data-stu-id="c5b22-499">What can I do?”</span></span> <span data-ttu-id="c5b22-500">När användaren klickar på länken kan han eller hon granska de typer av känslig information som upptäckts och åsidosätta eller rapportera ett problem om administratören tillåtit det. Observera att inga principtips visas för filer.</span><span class="sxs-lookup"><span data-stu-id="c5b22-500">When clicking the link, the user can review the sensitive info types detected and override or report an issue if allowed by the admin. Note that no policy tips are shown for files.</span></span> <span data-ttu-id="c5b22-501">När mottagaren försöker komma åt dokumentet kan de få åtkomst nekad om det inte är tillåtet.</span><span class="sxs-lookup"><span data-stu-id="c5b22-501">When the recipient tries to access the document, they might get access denied if not allowed.</span></span>|
|<span data-ttu-id="c5b22-502">**Win32-slutpunktsenheter**</span><span class="sxs-lookup"><span data-stu-id="c5b22-502">**Win32 Endpoint Devices**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="c5b22-503">Delmängd</span><span class="sxs-lookup"><span data-stu-id="c5b22-503">Subset</span></span>|<span data-ttu-id="c5b22-504">Alla endpoint DLP-predikat och åtgärder i DLP-princip</span><span class="sxs-lookup"><span data-stu-id="c5b22-504">All Endpoint DLP predicates and actions in DLP policy</span></span>|<span data-ttu-id="c5b22-505">Se [Skydd mot dataförlust i Slutpunkt som stöder principtips för endast vissa typer av känslig information](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)</span><span class="sxs-lookup"><span data-stu-id="c5b22-505">See [Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)</span></span>|
|<span data-ttu-id="c5b22-506">**Mac-enheter**</span><span class="sxs-lookup"><span data-stu-id="c5b22-506">**Mac devices**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="c5b22-507">Inga</span><span class="sxs-lookup"><span data-stu-id="c5b22-507">None</span></span>|<span data-ttu-id="c5b22-508">Inga</span><span class="sxs-lookup"><span data-stu-id="c5b22-508">None</span></span>|<span data-ttu-id="c5b22-509">Principer för skydd mot dataförlust är i dag inte tillgängliga på Mac-enheter</span><span class="sxs-lookup"><span data-stu-id="c5b22-509">Data loss prevention policies are not enforceable on Mac devices today</span></span>|
|<span data-ttu-id="c5b22-510">**Molnbaserade appar från tredje part**</span><span class="sxs-lookup"><span data-stu-id="c5b22-510">**3rd party cloud apps**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="c5b22-511">Inga</span><span class="sxs-lookup"><span data-stu-id="c5b22-511">None</span></span>|<span data-ttu-id="c5b22-512">Inga</span><span class="sxs-lookup"><span data-stu-id="c5b22-512">None</span></span>|<span data-ttu-id="c5b22-513">Policytips för skydd mot dataförlust stöds inte i molnappar från tredje part</span><span class="sxs-lookup"><span data-stu-id="c5b22-513">Data Loss Prevention policy tips are not supported on 3rd party cloud apps</span></span>|
|<span data-ttu-id="c5b22-514">**On-prem**</span><span class="sxs-lookup"><span data-stu-id="c5b22-514">**On-prem**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="c5b22-515">Inga</span><span class="sxs-lookup"><span data-stu-id="c5b22-515">None</span></span>|<span data-ttu-id="c5b22-516">Inga</span><span class="sxs-lookup"><span data-stu-id="c5b22-516">None</span></span>||
|<span data-ttu-id="c5b22-517">**Word, Excel, PowerPoint Win32-klient**</span><span class="sxs-lookup"><span data-stu-id="c5b22-517">**Word, Excel, PowerPoint Win32 Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="c5b22-518">Delmängd</span><span class="sxs-lookup"><span data-stu-id="c5b22-518">Subset</span></span>|<span data-ttu-id="c5b22-519">Delmängd</span><span class="sxs-lookup"><span data-stu-id="c5b22-519">Subset</span></span>|<span data-ttu-id="c5b22-520">Se [Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) och senare, och stöd för Office-program på stationära datorer med policytips för endast vissa typer av känslig information för listan över typer av känslig information som stöds</span><span class="sxs-lookup"><span data-stu-id="c5b22-520">Please see [Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) for the list of sensitive information types supported</span></span></br></br><span data-ttu-id="c5b22-521">Principtips för WXP-klientprogram fungerar för dokument som lagras på Sharepoint Online- eller One Drive för företag-webbplatser för alla DLP-principer som har exakt nedanstående eller en delmängd villkor eller åtgärder i DLP-principen:</span><span class="sxs-lookup"><span data-stu-id="c5b22-521">Policy tips for WXP client apps will work for documents stored on Sharepoint Online or One Drive for Business Sites for all DLP policies which have exactly the below or a subset of conditions or actions in the DLP policy:</span></span></br> <ul><li><span data-ttu-id="c5b22-522">Innehållet innehåller typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="c5b22-522">Content contains sensitive information types</span></span></li><li><span data-ttu-id="c5b22-523">Åtkomstomfattning (innehåll delas internt/externt)</span><span class="sxs-lookup"><span data-stu-id="c5b22-523">Access Scope (Content is shared internally/externally)</span></span></li><li><span data-ttu-id="c5b22-524">Meddela användare (principtips/användarmeddelanden)</span><span class="sxs-lookup"><span data-stu-id="c5b22-524">Notify User (policy tips/user notifications)</span></span></li><li><span data-ttu-id="c5b22-525">Blockera alla</span><span class="sxs-lookup"><span data-stu-id="c5b22-525">Block everyone</span></span></li><li><span data-ttu-id="c5b22-526">Incidentrapporter</span><span class="sxs-lookup"><span data-stu-id="c5b22-526">Incident reports</span></span></li></ul></br> <span data-ttu-id="c5b22-527">Om det finns andra villkor eller åtgärder visas inte DLP-principtipset för den principen i skrivbordsapparna för Word, Excel eller PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="c5b22-527">If any other condition or action is present, the DLP policy tip for that policy will not appear in the desktop apps of Word, Excel or PowerPoint.</span></span></br><span data-ttu-id="c5b22-528">Mer [information finns i Principtips i Excel, PowerPoint](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word) och Word</span><span class="sxs-lookup"><span data-stu-id="c5b22-528">See [Policy tips in Excel, PowerPoint, and Word](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word) for more details</span></span>|
||||||
