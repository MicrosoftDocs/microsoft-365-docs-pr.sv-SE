---
title: Hur DLP fungerar med säkerhets- & säkerhets- och efterlevnadscenter & Exchange administrationscenter
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Läs om hur DLP i Säkerhets- & efterlevnadscenter fungerar med DLP- och e-postflödesregler (transportregler) i Exchange administrationscenter.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 34ddee1c1f0997852b6e59295ab9b630acc3ba3c
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177183"
---
# <a name="how-dlp-works-between-the-microsoft-365-compliance-center-and-exchange-admin-center"></a><span data-ttu-id="986d3-103">Hur DLP fungerar mellan efterlevnadscentret Microsoft 365 och Exchange administrationscenter</span><span class="sxs-lookup"><span data-stu-id="986d3-103">How DLP works between the Microsoft 365 Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="986d3-104">I Microsoft 365 kan du skapa en DLP-princip (Data Loss Prevention) i två olika administrationscenter:</span><span class="sxs-lookup"><span data-stu-id="986d3-104">In Microsoft 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="986d3-105">I **Microsoft 365 efterlevnadscenter** kan du skapa en enda DLP-princip för att skydda innehåll i SharePoint, OneDrive, Exchange, Teams och nu Slutpunkt-enheter.</span><span class="sxs-lookup"><span data-stu-id="986d3-105">In the **Microsoft 365 Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, Exchange, Teams, and now Endpoint Devices.</span></span> <span data-ttu-id="986d3-106">Vi rekommenderar att du skapar en DLP-princip här.</span><span class="sxs-lookup"><span data-stu-id="986d3-106">We recommend that you create a DLP policy here.</span></span> <span data-ttu-id="986d3-107">Mer information finns i Referens [för dataförlustskydd.](data-loss-prevention-policies.md)</span><span class="sxs-lookup"><span data-stu-id="986d3-107">For more information, see [Data Loss Prevention reference](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="986d3-108">I Exchange **kan du skapa** en DLP-princip för att endast skydda innehåll i Exchange.</span><span class="sxs-lookup"><span data-stu-id="986d3-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="986d3-109">Den här principen kan Exchange e-postflödesregler (kallas även transportregler), vilket innebär att det finns fler alternativ för hantering av e-post.</span><span class="sxs-lookup"><span data-stu-id="986d3-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="986d3-110">Mer information finns i [DLP i Exchange administrationscenter.](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)</span><span class="sxs-lookup"><span data-stu-id="986d3-110">For more information, see [DLP in the Exchange admin center](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention).</span></span>
    
<span data-ttu-id="986d3-111">DLP-information som skapats i dessa administrationscenter fungerar sida vid sida – i det här avsnittet förklaras hur.</span><span class="sxs-lookup"><span data-stu-id="986d3-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![DLP-sidor i Säkerhets- och efterlevnadscenter Exchange administrationscenter](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="986d3-113">Hur DLP i säkerhets- & säkerhets- och efterlevnadscenter fungerar med DLP- och e-postflödesregler i Exchange administrationscenter</span><span class="sxs-lookup"><span data-stu-id="986d3-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="986d3-114">När du har skapat en DLP-princip i Säkerhets- & säkerhets- och efterlevnadscenter distribueras principen till alla platser som ingår i principen.</span><span class="sxs-lookup"><span data-stu-id="986d3-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="986d3-115">Om principen innehåller Exchange Online synkroniseras principen där och tillämpas på exakt samma sätt som en DLP-princip som skapas Exchange administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="986d3-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="986d3-116">Om du har skapat DLP-principer i administrationscentret för Exchange kommer de principerna att fortsätta att fungera sida vid sida med eventuella principer för e-post som du skapar i Säkerhets- och & efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="986d3-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="986d3-117">Observera dock att regler som skapats Exchange administratörscenter har företräde.</span><span class="sxs-lookup"><span data-stu-id="986d3-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="986d3-118">Alla Exchange e-postflödesregler bearbetas först, och sedan bearbetas DLP-& säkerhets- och efterlevnadscentret.</span><span class="sxs-lookup"><span data-stu-id="986d3-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="986d3-119">Det innebär följande:</span><span class="sxs-lookup"><span data-stu-id="986d3-119">This means that:</span></span>
  
- <span data-ttu-id="986d3-120">Meddelanden som blockeras av Exchange genomsöks inte av DLP-regler som skapats i Säkerhets- och & säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="986d3-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>

- <span data-ttu-id="986d3-121">Meddelanden som har satts i Exchange e-postflödesregler eller andra filter körs innan DLP genomsöks inte av DLP</span><span class="sxs-lookup"><span data-stu-id="986d3-121">Messages that are quarantined by Exchange mail flow rules or any other filters run before DLP will not be scanned by DLP</span></span>
    
- <span data-ttu-id="986d3-122">Om en Exchange-e-postflödesregel ändrar ett meddelande på ett sätt som gör att det matchar en DLP-princip i Säkerhets- och efterlevnadscenter för & – som att lägga till externa användare – identifierar DLP-reglerna den här och tillämpar principen efter behov.</span><span class="sxs-lookup"><span data-stu-id="986d3-122">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="986d3-123">Observera även att Exchange-postflödesregler som använder åtgärden "stoppa bearbetning" inte påverkar bearbetningen av D & LP-regler i säkerhets- och efterlevnadscentret – de bearbetas fortfarande.</span><span class="sxs-lookup"><span data-stu-id="986d3-123">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="986d3-124">Principtips i Säkerhets- & Säkerhets- och efterlevnadscenter Exchange administrationscentret</span><span class="sxs-lookup"><span data-stu-id="986d3-124">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="986d3-125">Principtips kan antingen fungera med DLP-principer och e-postflödesregler som skapats i administrationscentret för Exchange eller med DLP-principer som skapats i säkerhets- och &-efterlevnadscentret, men inte båda.</span><span class="sxs-lookup"><span data-stu-id="986d3-125">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="986d3-126">Det beror på att dessa principer lagras på olika platser, men principtips kan endast ritas från en enda plats.</span><span class="sxs-lookup"><span data-stu-id="986d3-126">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="986d3-127">Om du har konfigurerat principtips i administrationscentret för Exchange visas inga principtips som du konfigurerar i säkerhets- och efterlevnadscentret för & i Outlook på webben och Outlook 2013 eller senare förrän du stänger av tipsen i administrationscentret för Exchange.</span><span class="sxs-lookup"><span data-stu-id="986d3-127">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="986d3-128">Det säkerställer att dina Exchange-postflödesregler fortsätter att fungera tills du väljer att växla över till Säkerhets- & efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="986d3-128">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="986d3-129">Observera att även om principtips bara kan ritas från en enda plats skickas alltid e-postaviseringar, även om du använder DLP-principer i både Säkerhets- och efterlevnadscenter & och administrationscentret för Exchange.</span><span class="sxs-lookup"><span data-stu-id="986d3-129">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
