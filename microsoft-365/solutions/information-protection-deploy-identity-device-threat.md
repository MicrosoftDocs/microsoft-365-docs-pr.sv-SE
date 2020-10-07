---
title: Använd identitets-, enhets-och hot skydd för data integritets förordning
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
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Förhindra person uppgifter om identitets-, enhets-och hot skydd i Microsoft 365.
ms.openlocfilehash: 681ff807b734430ae864334b409fe11397f3089e
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377063"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="bcd0a-103">Använd identitets-, enhets-och hot skydd för data integritets förordning</span><span class="sxs-lookup"><span data-stu-id="bcd0a-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="bcd0a-104">Microsoft 365 tillhandahåller ett antal funktioner för identitets-, enhets-och hot skydd som organisationer kan använda för att uppfylla data integritets regler.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="bcd0a-105">I den här artikeln beskrivs vad data integritets reglerna kräver i dessa områden och en lista över relaterade funktioner och tjänster i Microsoft 365 med länkar till mer information som hjälper dig att hantera implementerings kraven.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="bcd0a-106">Så här skyddar identitet, enhet och hot mot data integritets reglering</span><span class="sxs-lookup"><span data-stu-id="bcd0a-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="bcd0a-107">Även om data integritets reglerna varierar beroende på deras betydelse, är syftet med vad de kan prata med i GDPR i paragraf 5.1 (f), som visar att:</span><span class="sxs-lookup"><span data-stu-id="bcd0a-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span> 

- <span data-ttu-id="bcd0a-108">Person uppgifter ska behandlas på ett sätt som säkerställer lämplig säkerhet för person uppgifter, inklusive skydd mot obehörig eller olaglig behandling samt mot oavsiktlig förlust, destruktion eller skada, med lämpliga tekniska eller organisatoriska åtgärder ("integritet och konfidentialitet").</span><span class="sxs-lookup"><span data-stu-id="bcd0a-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="bcd0a-109">Eftersom person data brott ofta orsakas av administratörs-eller slutanvändarens problem med intrång i systemet.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="bcd0a-110">Ett administratörs konto Hacker kan till exempel ge exfiltration kreditkorts nummer eller annan personlig information.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="bcd0a-111">Allt allmänt tillrådligt krypterings-, enhets-och hot-skydd som är tillgängligt med Microsoft 365 kan komma att implementeras, som kommer att återspeglas i din uppkopplings poäng, i Compliance Manager.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="bcd0a-112">Använda resultaten av din bedömnings arbete och kompatibilitetskontrollen</span><span class="sxs-lookup"><span data-stu-id="bcd0a-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="bcd0a-113">Efterföljandekrav inkluderar identitets-, enhets-och hot skydd med dessa kategorier:</span><span class="sxs-lookup"><span data-stu-id="bcd0a-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="bcd0a-114">Identiteten motsvarar kategorin för **kontroll åtkomst**</span><span class="sxs-lookup"><span data-stu-id="bcd0a-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="bcd0a-115">Enheten motsvarar kategorin **Hantera enheter**</span><span class="sxs-lookup"><span data-stu-id="bcd0a-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="bcd0a-116">Hotet skyddas **mot kategorin skydda mot hot**</span><span class="sxs-lookup"><span data-stu-id="bcd0a-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="bcd0a-117">Om dessa är markerade i vårt exempel med fyra viktiga data integritets regler anger överensstämmelse hanteraren 90 förbättrings åtgärder, de flesta av dessa betyg är "27".</span><span class="sxs-lookup"><span data-stu-id="bcd0a-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="bcd0a-118">Eftersom ett sådant stort nummer besvaras av Compliance Manager för dessa kategorier, är några av de vanligaste fälten listade som referens.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="bcd0a-119">Använd [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) för identitet och **kontroll åtkomst** kategori, med vilken du kan:</span><span class="sxs-lookup"><span data-stu-id="bcd0a-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="bcd0a-120">Implementera Replay-motstånd (för att förhindra "man i mitten")</span><span class="sxs-lookup"><span data-stu-id="bcd0a-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="bcd0a-121">Blockera bakåtkompatibel-verifikation.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-121">Block legacy authentication.</span></span>
- <span data-ttu-id="bcd0a-122">Konfigurera principer för användar risker och användar inloggnings risker.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="bcd0a-123">Aktivera villkorsstyrd åtkomst och multifaktorautentisering för administratörer och icke-administratörer.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="bcd0a-124">Konfigurera och tillämpa lösen ords principer.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="bcd0a-125">Begränsa åtkomsten till behöriga konton med Azure AD restrict Identity Management.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="bcd0a-126">Inaktivera åtkomst vid uppsägning.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-126">Disable access upon termination.</span></span>
- <span data-ttu-id="bcd0a-127">Granska användar konton och status ändringar.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="bcd0a-128">Granska roll grupper och administrativa ändringar.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="bcd0a-129">Använd [Microsoft slut punkts hanteraren](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) för enheter och kategorin **Hantera enheter** , med vilken du kan:</span><span class="sxs-lookup"><span data-stu-id="bcd0a-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="bcd0a-130">Blockera Jail trasiga och rotade mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="bcd0a-131">Konfigurera Intune för hantering av mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="bcd0a-132">Skapa efterlevnadsprinciper för Android, iOS, macOS och Windows-enheter.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="bcd0a-133">Skapa en konfigurations profil för Android, iOS, macOS och Windows.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="bcd0a-134">Skapa program skydds principer för iOS och Windows.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="bcd0a-135">Dölja information med lås skärmen.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="bcd0a-136">Implementera principer för lösen ord för mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="bcd0a-137">Kräv att mobila enheter låses vid inaktivitet.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="bcd0a-138">Kräv att mobila enheter rensas på flera inloggnings problem.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="bcd0a-139">Använd [Exchange Online Protection och Office 365 Avancerat skydd (ATP)](../security/office-365-security/office-365-atp.md) för kategorin **skydda mot hot** :</span><span class="sxs-lookup"><span data-stu-id="bcd0a-139">Use [Exchange Online Protection and Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="bcd0a-140">Aktivera avsändare (SPF, DMARC och DKIM).</span><span class="sxs-lookup"><span data-stu-id="bcd0a-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="bcd0a-141">Konfigurera Office 365 skydd mot nätfiske (avancerat skydd).</span><span class="sxs-lookup"><span data-stu-id="bcd0a-141">Set up Office 365 Advanced Threat Protection (ATP) anti-phishing policies.</span></span>
- <span data-ttu-id="bcd0a-142">Implementera säkra filer för ATP.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-142">Implement ATP Safe Attachments.</span></span>
- <span data-ttu-id="bcd0a-143">Implementera säkra ATP-länkar.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-143">Implement ATP Safe Links.</span></span>
- <span data-ttu-id="bcd0a-144">Implementera identifierings-och svars principer för skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="bcd0a-145">Implementera principer för utgående och inkommande skräp post.</span><span class="sxs-lookup"><span data-stu-id="bcd0a-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="bcd0a-146">Innehåller</span><span class="sxs-lookup"><span data-stu-id="bcd0a-146">References:</span></span>

- [<span data-ttu-id="bcd0a-147">Vanliga principer för identitets- och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="bcd0a-147">Common identity and device access policies</span></span>](../enterprise/identity-access-policies.md)
- [<span data-ttu-id="bcd0a-148">Skydda mot hot i Office 365</span><span class="sxs-lookup"><span data-stu-id="bcd0a-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="bcd0a-149">Säkra filer för ATP</span><span class="sxs-lookup"><span data-stu-id="bcd0a-149">ATP Safe Attachments</span></span>](../security/office-365-security/atp-safe-attachments.md)
- [<span data-ttu-id="bcd0a-150">Säkra ATP-länkar</span><span class="sxs-lookup"><span data-stu-id="bcd0a-150">ATP Safe Links</span></span>](../security/office-365-security/atp-safe-links.md)
- [<span data-ttu-id="bcd0a-151">ATP Säkra dokument</span><span class="sxs-lookup"><span data-stu-id="bcd0a-151">ATP Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
