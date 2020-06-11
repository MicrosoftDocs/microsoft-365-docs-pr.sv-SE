---
title: Distribuera informationsskydd för dataskydd med Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: Konfigurera säkerhets- och tjänstinfrastrukturen för att skydda din information och följa datasekretessreglerna.
ms.openlocfilehash: 35ccfb21accd969c2a2cbdddde9a4ec1c7eeed64
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695116"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a><span data-ttu-id="34acd-103">Distribuera informationsskydd för dataskydd med Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="34acd-103">Deploy information protection for data privacy regulations with Microsoft 365</span></span>

<span data-ttu-id="34acd-104">Den här lösningen ger vägledning om hur du planerar för och skyddar personuppgifter som lagras i Microsoft 365-tjänster och eventuellt omfattas av dataskyddsbestämmelser som EU:s allmänna dataskyddsförordning (GDPR).</span><span class="sxs-lookup"><span data-stu-id="34acd-104">This solution provides guidance on how to plan for and protect personal data that is stored in Microsoft 365 services and potentially subject to data privacy regulations such as the European Union's General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="34acd-105">Den här lösningen fokuserar på tillämpliga funktioner för microsofts informationsskydd och efterlevnad, Microsofts efterlevnadsresultat och bedömningsverktyg som hjälper dig att känna till dina data.</span><span class="sxs-lookup"><span data-stu-id="34acd-105">This solution focuses on applicable Microsoft information protection and compliance features, Microsoft Compliance Score, and assessment tools to help you know your data.</span></span> 
 
<span data-ttu-id="34acd-106">Ytterligare information finns också om användningen av Microsofts identitets-, enhets- och hotskyddskontroller för dina datasekretessbehov samt verktyg för identifiering av dataincidenter och svar.</span><span class="sxs-lookup"><span data-stu-id="34acd-106">Additional information is also provided on the use of Microsoft identity, device, and threat protection controls for your data privacy needs, as well as data incident discovery and response tools.</span></span> 

## <a name="organization-of-this-guidance-material"></a><span data-ttu-id="34acd-107">Organisation av detta vägledningsmaterial</span><span class="sxs-lookup"><span data-stu-id="34acd-107">Organization of this guidance material</span></span>

<span data-ttu-id="34acd-108">För att hjälpa dig att förstå de Microsoft 365-verktyg som finns tillgängliga för att identifiera, hantera, kontrollera och övervaka personliga data som omfattas av en eller flera sekretessrelaterade bestämmelser, är den här vägledningen uppdelad i avsnitt.</span><span class="sxs-lookup"><span data-stu-id="34acd-108">To help you understand the Microsoft 365 tools available to identify, manage, control, and monitor personal data subject to one or more privacy-related regulations, this guidance is organized into sections.</span></span>
 
![Distribuera informationsskydd för datasekretessregler](../media/information-protection-deploy/information-protection-deploy-grid.png)

<span data-ttu-id="34acd-110">Var och en av dessa avsnitt motsvarar en separat artikel i den här lösningen.</span><span class="sxs-lookup"><span data-stu-id="34acd-110">Each of these sections correspond to a separate article in this solution.</span></span>

>[!Note]
><span data-ttu-id="34acd-111">Om du redan är bekant med dina datasekretessskyldigheter och utför mot en befintlig plan kanske du vill fokusera på vägledningen Förhindra, Skydda, Behåll och Undersök.</span><span class="sxs-lookup"><span data-stu-id="34acd-111">If you are already familiar with your data privacy obligations and are executing against an existing plan, you may want to focus on the Prevent, Protect, Retain, and Investigate guidance.</span></span>

>[!Important]
><span data-ttu-id="34acd-112">Att följa den här vägledningen kommer inte nödvändigtvis att göra dig kompatibel med någon datasekretessreglering, särskilt med tanke på antalet steg som krävs som ligger utanför ramen för funktionerna.</span><span class="sxs-lookup"><span data-stu-id="34acd-112">Following this guidance will not necessarily make you compliant with any data privacy regulation, especially considering the number of steps required that are outside the context of the features.</span></span> <span data-ttu-id="34acd-113">Du är ansvarig för att säkerställa din efterlevnad och att konsultera dina juridiska och efterlevnadsteam eller för att söka vägledning och råd från tredje part som är specialiserade på efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="34acd-113">You are responsible for ensuring your compliance and to consult your legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a><span data-ttu-id="34acd-114">Planera: Bedöma datasekretessrisker och identifiera känsliga objekt</span><span class="sxs-lookup"><span data-stu-id="34acd-114">Plan: Assess data privacy risks and identify sensitive items</span></span> 

<span data-ttu-id="34acd-115">Att bedöma datasekretessregler och risker som din organisation omfattas av är ett viktigt första steg att ta innan du börjar implementera förbättringar, inklusive de som kan uppnås via Microsoft 365-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="34acd-115">Assessing data privacy regulations and risks that your organization is subject to is a key first step to take before starting to implement improvements, including those achievable through Microsoft 365 configuration.</span></span> <span data-ttu-id="34acd-116">Detta kan omfatta en övergripande beredskapsbedömning eller identifiering av särskilda känsliga informationstyper som omfattas av regelkontroller som din organisation måste följa, samt förekomsten av dem i din Microsoft 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="34acd-116">This may include an overall readiness assessment or identification of particular sensitive information types that are subject to regulatory controls your organization needs to comply with, as well as the occurrence of them in your Microsoft 365 environment.</span></span>

<span data-ttu-id="34acd-117">Mer information finns i [Bedöma datasekretessrisker och identifiera känsliga objekt](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="34acd-117">For more information, see [Assess data privacy risks and identify sensitive items](information-protection-deploy-assess.md).</span></span>

## <a name="track-use-compliance-score-and-compliance-manager"></a><span data-ttu-id="34acd-118">Spår: Använd efterlevnadspoäng och efterlevnadshanterare</span><span class="sxs-lookup"><span data-stu-id="34acd-118">Track: Use Compliance Score and Compliance Manager</span></span> 

<span data-ttu-id="34acd-119">Compliance Score and Compliance Manager innehåller en integrerad uppsättning verktyg som är tillgängliga i Microsoft 365 Compliance admin center och Services Trust Portal.</span><span class="sxs-lookup"><span data-stu-id="34acd-119">Compliance Score and Compliance Manager provide an integrated set of tools available in the Microsoft 365 Compliance admin center and Services Trust Portal.</span></span> <span data-ttu-id="34acd-120">Tillsammans ger dessa verktyg dig en inbyggd förmåga att spåra och hantera förbättringsåtgärder totalt sett samt de som rör flera datasekretessbestämmelser som du utsätts för.</span><span class="sxs-lookup"><span data-stu-id="34acd-120">Together, these tools provide you with a built-in ability to track and manage improvement actions overall as well as those related to multiple data privacy regulations to which you are subjected.</span></span>

<span data-ttu-id="34acd-121">Med verktygen kan du också utnyttja inbyggda bedömningsmallar som är specifika för varje förordning, där du kan spåra åtgärdsobjekt för varje vald bedömningsmall, samt visa specifika regelkontroller och relatera dem till specifika åtgärder.</span><span class="sxs-lookup"><span data-stu-id="34acd-121">The tools also allow you to leverage built in assessment templates specific to each regulation, where you can track action items for each assessment template selected, as well as view specific regulatory controls, and relate them to specific actions.</span></span>

<span data-ttu-id="34acd-122">Mer information finns i [Använd efterlevnadspoäng och efterlevnadshanteraren för att hantera förbättringsåtgärder](information-protection-deploy-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="34acd-122">For more information, see [Use Compliance Score and Compliance Manager to manage improvement actions](information-protection-deploy-compliance.md).</span></span>

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="34acd-123">Förhindra: Använd identitet, enhet och hotskydd för datasekretessreglering</span><span class="sxs-lookup"><span data-stu-id="34acd-123">Prevent: Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="34acd-124">Microsoft 365 tillhandahåller ett antal funktioner för identitets-, enhets- och hotskydd som du kan använda för att följa efterlevnaden av datasekretessregleringen.</span><span class="sxs-lookup"><span data-stu-id="34acd-124">Microsoft 365 provides a number of identity, device, and threat protection capabilities that you can use to help comply with data privacy regulatory compliance.</span></span> 

<span data-ttu-id="34acd-125">Mer information finns i [Använda identitet, enhet och hotskydd för dataskyddsreglering](information-protection-deploy-identity-device-threat.md).</span><span class="sxs-lookup"><span data-stu-id="34acd-125">For more information, see [Use identity, device, and threat protection for data privacy regulation](information-protection-deploy-identity-device-threat.md).</span></span>

<span data-ttu-id="34acd-126">I den här artikeln beskrivs kortfattat vad de dataskyddsbestämmelser som vanligtvis kräver inom dessa områden och innehåller en lista över relaterade Microsoft 365-lösningar, med länkar till mer information som hjälper dig att hantera eventuella implementeringskrav.</span><span class="sxs-lookup"><span data-stu-id="34acd-126">This article briefly describes what the data privacy regulations generally call for in these areas and provides a listing of related Microsoft 365 solutions, with links to more information to help you address any implementation requirements.</span></span> 

## <a name="protect-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="34acd-127">Skydda information som omfattas av dataskyddsförordningen</span><span class="sxs-lookup"><span data-stu-id="34acd-127">Protect information subject to data privacy regulation</span></span>

<span data-ttu-id="34acd-128">Dataskyddsregler dikterar ett antal kontroller för skydd av personuppgifter som kan användas i din miljö, inklusive mer än fyrtio Protect Information-kontroller över bara de fyra dataskyddsbestämmelserna i vår urvalsuppsättning AV GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States health care privacy act) och Brazil Data Protection Act (LGPD).</span><span class="sxs-lookup"><span data-stu-id="34acd-128">Data privacy regulations dictate a number of personal information protection controls that can be employed in your environment, including more than forty Protect Information controls across just the four data privacy regulations in our sample set of GDPR, California Consumer Protection Act (CCPA), HIPAA-HITECH (United States health care privacy act), and the Brazil Data Protection Act (LGPD).</span></span>

<span data-ttu-id="34acd-129">Mer information finns i [Skydda information som omfattas av datasekretessreglering i din organisation](information-protection-deploy-protect-information.md).</span><span class="sxs-lookup"><span data-stu-id="34acd-129">For more information, see [Protect information subject to data privacy regulation in your organization](information-protection-deploy-protect-information.md).</span></span>

<span data-ttu-id="34acd-130">I den här artikeln beskrivs de viktigaste kontrollscheman som kan användas för att tillgodose informationsskyddsbehov för datasekretess i din organisation.</span><span class="sxs-lookup"><span data-stu-id="34acd-130">This article lays out the main control schemes that can be used for addressing information protection needs for data privacy in your organization.</span></span>

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="34acd-131">Behåll: Reglera information som omfattas av dataskyddsförordningen</span><span class="sxs-lookup"><span data-stu-id="34acd-131">Retain: Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="34acd-132">Datasekretessbestämmelser kräver kontroller för styrning av personlig information som kan användas i din miljö, inklusive mer än tjugofyra kontroller i de fyra datasekretessreglerna i vår urvalsuppsättning GDPR, CCPA, HIPAA-HITECH och LGPD.</span><span class="sxs-lookup"><span data-stu-id="34acd-132">Data privacy regulations call for personal information governance controls that can be employed in your environment, including more than twenty-four controls across the four data privacy regulations in our sample set of GDPR, CCPA, HIPAA-HITECH, and LGPD.</span></span>

<span data-ttu-id="34acd-133">Mer information finns i [Styra information som omfattas av dataskyddsreglering i din organisation](information-protection-deploy-govern.md).</span><span class="sxs-lookup"><span data-stu-id="34acd-133">For more information, see [Govern information subject to data privacy regulation in your organization](information-protection-deploy-govern.md).</span></span>

<span data-ttu-id="34acd-134">Även om reglerna för datasekretess kan vara vaga när det gäller informationsstyrning, &mdash; till exempel målmedveten lagring, borttagning och arkivering &mdash; av den här artikeln innehåller de primära kontrollscheman som du kan använda behov av adressinformationsstyrning för datasekretess i din organisation.</span><span class="sxs-lookup"><span data-stu-id="34acd-134">While the data privacy regulations can be vague regarding information governance&mdash;such as purposeful retention, deletion and archiving&mdash;this article lays out the primary control schemes that you can use address information governance needs for data privacy in your organization.</span></span>

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a><span data-ttu-id="34acd-135">Undersöka: Övervaka och svara på datasekretessreglering</span><span class="sxs-lookup"><span data-stu-id="34acd-135">Investigate: Monitor and respond subject to data privacy regulation</span></span>

<span data-ttu-id="34acd-136">Det finns Microsoft 365-funktioner som hjälper dig att övervaka, undersöka och svara på datasekretessincidenter i organisationen när du operationaliserar relaterade funktioner.</span><span class="sxs-lookup"><span data-stu-id="34acd-136">There are Microsoft 365 features available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> 

<span data-ttu-id="34acd-137">Att ha processer, förfaranden och annan dokumentation för var och en av dessa kan vara viktigt för att visa efterlevnad för tillsynsorgan.</span><span class="sxs-lookup"><span data-stu-id="34acd-137">Having processes, procedures, and other documentation for each of these can be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="34acd-138">Mer information finns i [Övervaka och svara på datasekretessincidenter i organisationen](information-protection-deploy-monitor-respond.md).</span><span class="sxs-lookup"><span data-stu-id="34acd-138">For more information, see [Monitor and respond to data privacy incidents in your organization](information-protection-deploy-monitor-respond.md).</span></span>
