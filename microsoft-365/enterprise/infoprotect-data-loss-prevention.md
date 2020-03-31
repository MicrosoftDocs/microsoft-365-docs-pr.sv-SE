---
title: 'Steg 5: Konfigurera dataförlustskydd i Office 365'
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
description: Förstå och distribuera dataförlustskydd för Office 365 i Microsoft 365.
ms.openlocfilehash: 896670e9ae83324a1220d64f49a8ea48aee85169
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812937"
---
# <a name="step-5-configure-office-365-data-loss-prevention"></a><span data-ttu-id="35b6e-103">Steg 5: Konfigurera dataförlustskydd i Office 365</span><span class="sxs-lookup"><span data-stu-id="35b6e-103">Step 5: Configure Office 365 Data Loss Prevention</span></span>

<span data-ttu-id="35b6e-104">*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="35b6e-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fas 6: Informationsskydd](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="35b6e-106">Med principer för dataförlustskydd (DLP) i Säkerhets- och efterlevnadscenter för Office 365 kan du identifiera, övervaka och automatiskt skydda känslig information i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="35b6e-106">With data loss prevention (DLP) policies in the Office 365 Security & Compliance center, you can identify, monitor, and automatically protect sensitive information across Microsoft 365.</span></span> <span data-ttu-id="35b6e-107">Med DLP-principer kan du göra följande:</span><span class="sxs-lookup"><span data-stu-id="35b6e-107">With DLP policies, you can:</span></span>

- <span data-ttu-id="35b6e-108">Identifiera känslig information på många platser, till exempel Exchange Online, SharePoint Online, OneDrive för företag och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="35b6e-108">Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>
- <span data-ttu-id="35b6e-109">Förhindra oavsiktlig delning av känslig information genom att blockera åtkomst till ett dokument eller blockera e-postmeddelandet som innehåller det.</span><span class="sxs-lookup"><span data-stu-id="35b6e-109">Prevent the accidental sharing of sensitive information by blocking access to a document or blocking the email that contains it.</span></span>
- <span data-ttu-id="35b6e-110">Övervaka och skydda känslig information i skrivbordsversionerna av Excel, PowerPoint och Word.</span><span class="sxs-lookup"><span data-stu-id="35b6e-110">Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.</span></span>
- <span data-ttu-id="35b6e-111">Hjälpa användare att upprätthålla efterlevnaden utan att avbryta arbetsflödet med e-postmeddelanden och policytips.</span><span class="sxs-lookup"><span data-stu-id="35b6e-111">Help users learn how to stay compliant without interrupting their workflow with email notifications and policy tips.</span></span> 
- <span data-ttu-id="35b6e-112">Visa DLP-rapporter som visar innehåll som överensstämmer med din organisations DLP-principer.</span><span class="sxs-lookup"><span data-stu-id="35b6e-112">View DLP reports showing content that matches your organization's DLP policies.</span></span>

<span data-ttu-id="35b6e-113">En DLP-princip anger:</span><span class="sxs-lookup"><span data-stu-id="35b6e-113">A DLP policy specifies:</span></span>

- <span data-ttu-id="35b6e-114">**Var:** Platser som Exchange Online, SharePoint Online, OneDrive för företag-webbplatser och Microsoft Teams-chattar och kanaler.</span><span class="sxs-lookup"><span data-stu-id="35b6e-114">**Where:** Locations such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chats and channels.</span></span>
- <span data-ttu-id="35b6e-115">**När:** Villkor som innehållet måste matcha i en specifik policyregel.</span><span class="sxs-lookup"><span data-stu-id="35b6e-115">**When:** Conditions the content must match within a specific policy rule.</span></span>
- <span data-ttu-id="35b6e-116">**Hur:** Åtgärder i matchningspolicyregeln som automatiskt ska utföras för matchningsvillkoren.</span><span class="sxs-lookup"><span data-stu-id="35b6e-116">**How:** Actions within that matching policy rule to take automatically for the matching conditions.</span></span>

<span data-ttu-id="35b6e-117">Med andra ord:</span><span class="sxs-lookup"><span data-stu-id="35b6e-117">In other words:</span></span>

- <span data-ttu-id="35b6e-118">För ett dokument på den här platsen (var), om innehållet överensstämmer med villkoren för en regel (när), ska åtgärderna som anges i regeln automatiskt utföras (hur).</span><span class="sxs-lookup"><span data-stu-id="35b6e-118">For a document in this location (where), if the content matches the conditions of a rule (when), then automatically take the actions specified in the rule (how).</span></span>

<span data-ttu-id="35b6e-119">Om du vill fastställa vilken uppsättning DLP-principer du behöver måste du analysera dina dokument och de datatyper i dem som måste skyddas från dataförlust.</span><span class="sxs-lookup"><span data-stu-id="35b6e-119">To determine the set of DLP policies you need, you must analyze your documents and the types of data within them that need protection from data loss.</span></span> <span data-ttu-id="35b6e-120">Om du till exempel arbetar i en finansorganisation i USA kan du skapa en DLP-princip som hindrar att dokument med socialförsäkringsnummer delas utanför organisationen eller skickas via e-post till platser utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="35b6e-120">For example, if you are a financial organization in the United States of America, you would create a DLP policy that prevents documents with social security numbers from being shared outside the organization or sent in email to locations outside the organization.</span></span>

<span data-ttu-id="35b6e-121">Därefter konfigurerar och testar du principerna med testplatser för att säkerställa korrekt DLP-beteende och minimera falska positiva identifieringar.</span><span class="sxs-lookup"><span data-stu-id="35b6e-121">Next, you configure and test the policies with test locations to ensure the correct DLP behavior and to minimize false positives.</span></span>

<span data-ttu-id="35b6e-122">Slutligen kan du distribuera det i din organisation genom att informera medarbetarna om de nya principerna och deras önskade beteende och bredda omfånget för platserna.</span><span class="sxs-lookup"><span data-stu-id="35b6e-122">Finally, you roll it out to your organization by informing the employees of the new policies and their desired behavior and widening the scope of the locations.</span></span>

<span data-ttu-id="35b6e-123">Mer information finns i [Kom igång med DLP-principrekommendationer](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).</span><span class="sxs-lookup"><span data-stu-id="35b6e-123">For more information, see [Get started with DLP policy recommendations](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).</span></span>

<span data-ttu-id="35b6e-124">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](infoprotect-exit-criteria.md#crit-infoprotect-step5) som motsvarar det här steget.</span><span class="sxs-lookup"><span data-stu-id="35b6e-124">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step5) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="35b6e-125">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="35b6e-125">Next step</span></span>

|||
|:-------|:-----|
|![Steg 6](../media/stepnumbers/Step6.png)|[<span data-ttu-id="35b6e-127">Konfigurera e-postkryptering</span><span class="sxs-lookup"><span data-stu-id="35b6e-127">Configure email encryption</span></span>](infoprotect-email-encryption.md)|


