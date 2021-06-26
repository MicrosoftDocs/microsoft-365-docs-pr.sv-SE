---
title: Använda principer för skydd mot dataförlust för molnappar som inte kommer från Microsoft (förhandsversion)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du använder dlp-principer för program som inte är Microsoft-molnappar.
ms.openlocfilehash: ca522b5accbd2c08e80b0ce63871179ff64bbcc8
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149160"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="cf147-103">Använda principer för skydd mot dataförlust för molnappar som inte kommer från Microsoft (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="cf147-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="cf147-104">Principer för skydd mot dataförlust (DLP) för icke-Microsoft-molnappar är en del Microsoft 365 DLP-paketet med funktioner. med dessa funktioner kan du identifiera och skydda känsliga objekt i Microsoft 365 tjänster.</span><span class="sxs-lookup"><span data-stu-id="cf147-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="cf147-105">Mer information om alla Microsoft DLP-erbjudanden finns i [Läs mer om skydd mot dataförlust.](dlp-learn-about-dlp.md)</span><span class="sxs-lookup"><span data-stu-id="cf147-105">For more information about all Microsoft DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="cf147-106">Du kan använda DLP-principer till andra molnappar än Microsoft för att övervaka och identifiera när känsliga objekt används och delas via andra molnappar än Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf147-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="cf147-107">Med de här principerna får du den synlighet och kontroll som du behöver för att säkerställa att de används och skyddas korrekt, och det hjälper till att förhindra riskabelt beteende som kan avslöja dem.</span><span class="sxs-lookup"><span data-stu-id="cf147-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="cf147-108">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="cf147-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="cf147-109">Licensiering av SKU/prenumerationer</span><span class="sxs-lookup"><span data-stu-id="cf147-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="cf147-110">Innan du börjar använda DLP-principer för andra program än Microsoft-molnappar måste [Microsoft 365 din](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) prenumeration och eventuella tillägg.</span><span class="sxs-lookup"><span data-stu-id="cf147-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="cf147-111">För att komma åt och använda den här funktionen måste du ha någon av dessa prenumerationer eller tillägg:</span><span class="sxs-lookup"><span data-stu-id="cf147-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="cf147-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="cf147-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="cf147-113">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="cf147-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="cf147-114">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="cf147-114">Microsoft 365 E5 Security</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="cf147-115">Förbereda din Cloud App Security miljö</span><span class="sxs-lookup"><span data-stu-id="cf147-115">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="cf147-116">DLP-principer för icke-Microsoft-molnappar Cloud App Security DLP-funktioner.</span><span class="sxs-lookup"><span data-stu-id="cf147-116">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="cf147-117">Om du vill använda den bör du förbereda Cloud App Security miljön.</span><span class="sxs-lookup"><span data-stu-id="cf147-117">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="cf147-118">Anvisningar finns i Ange [åtgärder för snabb synlighet, skydd och styrning för dina appar.](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)</span><span class="sxs-lookup"><span data-stu-id="cf147-118">For instructions, see [Set instant visibility, protection, and governance actions for your apps](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="cf147-119">Anslut ett molnapp som inte är ett Microsoft-program</span><span class="sxs-lookup"><span data-stu-id="cf147-119">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="cf147-120">Om du vill använda DLP-principen för en viss app som inte är en Microsoft-molnapp måste programmet vara anslutet till Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="cf147-120">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="cf147-121">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="cf147-121">For information, see:</span></span>

- [<span data-ttu-id="cf147-122">Anslut Box</span><span class="sxs-lookup"><span data-stu-id="cf147-122">Connect Box</span></span>](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="cf147-123">Anslut Dropbox</span><span class="sxs-lookup"><span data-stu-id="cf147-123">Connect Dropbox</span></span>](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="cf147-124">Anslut G-Suite</span><span class="sxs-lookup"><span data-stu-id="cf147-124">Connect G-Suite</span></span>](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="cf147-125">Anslut Salesforce</span><span class="sxs-lookup"><span data-stu-id="cf147-125">Connect Salesforce</span></span>](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="cf147-126">Anslut Cisco Webex</span><span class="sxs-lookup"><span data-stu-id="cf147-126">Connect Cisco Webex</span></span>](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="cf147-127">När du har anslutt dina molnprogram till Cloud App Security kan du skapa Microsoft 365 DLP-principer för dem.</span><span class="sxs-lookup"><span data-stu-id="cf147-127">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

>[!NOTE]
><span data-ttu-id="cf147-128">Det går också bra att använda Microsoft Cloud App Security för att skapa DLP-principer för Microsoft-molnappar.</span><span class="sxs-lookup"><span data-stu-id="cf147-128">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="cf147-129">Vi rekommenderar dock att du använder Microsoft 365 att skapa och hantera DLP-principer för Microsoft-molnappar.</span><span class="sxs-lookup"><span data-stu-id="cf147-129">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="cf147-130">Skapa en DLP-princip i en molnbaserad app som inte är en Microsoft-app</span><span class="sxs-lookup"><span data-stu-id="cf147-130">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="cf147-131">När du väljer en plats för DLP-principen aktiverar du **Microsoft Cloud App Security** plats.</span><span class="sxs-lookup"><span data-stu-id="cf147-131">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="cf147-132">Om du vill välja en viss app eller instans väljer du **Välj instans**.</span><span class="sxs-lookup"><span data-stu-id="cf147-132">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="cf147-133">Om du inte väljer en instans används alla anslutna appar i din klientorganisation Microsoft Cloud App Security princip.</span><span class="sxs-lookup"><span data-stu-id="cf147-133">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![Platser där principen ska tillämpas](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US och Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="cf147-136">Du kan välja olika åtgärder för alla program som inte stöds i Microsoft-molnprogrammet.</span><span class="sxs-lookup"><span data-stu-id="cf147-136">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="cf147-137">Det finns olika möjliga åtgärder för varje program (beror på molnapp-API:t).</span><span class="sxs-lookup"><span data-stu-id="cf147-137">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![Skapa regel](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="cf147-139">När du skapar en regel i DLP-principen kan du välja en åtgärd för icke-Microsoft-molnappar.</span><span class="sxs-lookup"><span data-stu-id="cf147-139">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="cf147-140">Om du vill begränsa appar från tredje part **väljer du Begränsa appar från tredje part.**</span><span class="sxs-lookup"><span data-stu-id="cf147-140">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![Begränsa appar från tredje part](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

><span data-ttu-id="cf147-142">[OBS] De DLP-principer som tillämpas på icke-Microsoft-appar Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="cf147-142">[NOTE] DLP policies applied to non-Microsoft apps use Microsoft Cloud App Security.</span></span> <span data-ttu-id="cf147-143">När DLP-principen för en app som inte är en Microsoft-app skapas samma princip automatiskt Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="cf147-143">When the DLP policy for a non-Microsoft app is created, the same policy will be automatically created in Microsoft Cloud App Security.</span></span>

<span data-ttu-id="cf147-144">Information om hur du skapar och konfigurerar DLP-principer finns [i Skapa testa och finjustera en DLP-princip.](./create-test-tune-dlp-policy.md?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="cf147-144">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md?view=o365-worldwide).</span></span>

## <a name="see-also"></a><span data-ttu-id="cf147-145">Se även</span><span class="sxs-lookup"><span data-stu-id="cf147-145">See Also</span></span>

- [<span data-ttu-id="cf147-146">Skapa testa och finjustera en DLP-princip</span><span class="sxs-lookup"><span data-stu-id="cf147-146">Create test and tune a DLP policy</span></span>](./create-test-tune-dlp-policy.md?view=o365-worldwide)
- [<span data-ttu-id="cf147-147">Kom igång med DLP-standardprincipen</span><span class="sxs-lookup"><span data-stu-id="cf147-147">Get started with the default DLP policy</span></span>](./get-started-with-the-default-dlp-policy.md?view=o365-worldwide)
- [<span data-ttu-id="cf147-148">Skapa en DLP-princip från en mall</span><span class="sxs-lookup"><span data-stu-id="cf147-148">Create a DLP policy from a template</span></span>](./create-a-dlp-policy-from-a-template.md?view=o365-worldwide)
