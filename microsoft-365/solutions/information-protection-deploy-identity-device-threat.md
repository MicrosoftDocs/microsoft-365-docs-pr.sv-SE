---
title: Använda identitets-, enhets- och hotskydd för dataskydd
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
ms.custom: ''
description: Förhindra personuppgiftsbrott med microsoft 365-tjänster för personuppgiftsskydd och hotskydd.
ms.openlocfilehash: a309b5d0ba5f939cf89a31d7ac91ca3aac25ce0d
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/29/2020
ms.locfileid: "46520987"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="9865c-103">Använda identitets-, enhets- och hotskydd för dataskydd</span><span class="sxs-lookup"><span data-stu-id="9865c-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="9865c-104">Microsoft 365 tillhandahåller ett antal funktioner för identitets-, enhets- och hotskydd som organisationer kan använda för att följa reglerna för datasekretessrelaterad efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="9865c-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="9865c-105">I den här artikeln beskrivs vad de datasekretessregler som krävs i dessa områden och en lista över relaterade funktioner och tjänster från Microsoft 365 med länkar till mer information som hjälper dig att hantera implementeringskrav.</span><span class="sxs-lookup"><span data-stu-id="9865c-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="9865c-106">Hur identitet, enhet och hotskydd relaterar till dataskyddsreglering</span><span class="sxs-lookup"><span data-stu-id="9865c-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="9865c-107">Även om bestämmelserna om datasekretess varierar i fråga om deras specificitet, ingår kärnan i vad de kräver i GDPR:s artikel 5.1 f, där det anges att</span><span class="sxs-lookup"><span data-stu-id="9865c-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span> 

- <span data-ttu-id="9865c-108">Personuppgifter ska behandlas på ett sätt som säkerställer lämplig säkerhet för personuppgifterna, inklusive skydd mot obehörig eller olaglig behandling och mot oavsiktlig förlust, förstörelse eller skada, med hjälp av lämpliga tekniska eller organisatoriska åtgärder ("integritet och sekretess").</span><span class="sxs-lookup"><span data-stu-id="9865c-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="9865c-109">Eftersom personuppgiftsbrott ofta orsakas av kompromettering av administrativa konton eller slutanvändarkonto och åtkomst till skadliga system.</span><span class="sxs-lookup"><span data-stu-id="9865c-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="9865c-110">Till exempel, en admin konto hacka kan resultera i exfiltration av kundens kreditkortsnummer eller annan personlig information.</span><span class="sxs-lookup"><span data-stu-id="9865c-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="9865c-111">Alla allmänt tillrådliga identitets-, enhets- och hotskydd som är tillgängliga med Microsoft 365 bör implementeras, vilket återspeglas i din efterlevnadspoäng.</span><span class="sxs-lookup"><span data-stu-id="9865c-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your Compliance Score.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-score"></a><span data-ttu-id="9865c-112">Använda resultaten av ditt bedömningsarbete och efterlevnadspoäng</span><span class="sxs-lookup"><span data-stu-id="9865c-112">Using the results of your assessment work and Compliance Score</span></span>

<span data-ttu-id="9865c-113">Efterlevnadspoängen omfattar identitets-, enhets- och hotskydd med hjälp av följande kategorier:</span><span class="sxs-lookup"><span data-stu-id="9865c-113">Compliance Score includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="9865c-114">Identiteten motsvarar kategorin **Kontrollåtkomst**</span><span class="sxs-lookup"><span data-stu-id="9865c-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="9865c-115">Enheten motsvarar kategorin **Hantera enheter**</span><span class="sxs-lookup"><span data-stu-id="9865c-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="9865c-116">Skydd mot hot motsvarar kategorin **Skydda mot hot**</span><span class="sxs-lookup"><span data-stu-id="9865c-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="9865c-117">Om dessa väljs ut i vår urvalsuppsättning med fyra huvudregler för datasekretess anger efterlevnadspoäng 90 förbättringsåtgärder, varav de flesta har fått ett "27".</span><span class="sxs-lookup"><span data-stu-id="9865c-117">If these are selected across our sample set of four major data privacy regulations, Compliance Score specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="9865c-118">Eftersom ett så stort antal kallas ut av efterlevnadspoäng för dessa kategorier, listas några av de vanligaste här, som referens.</span><span class="sxs-lookup"><span data-stu-id="9865c-118">Since such a large number are called out by Compliance Score for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="9865c-119">Använd [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) för identitet och kategorin Control **Access,** med vilken du kan:</span><span class="sxs-lookup"><span data-stu-id="9865c-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="9865c-120">Implementera rearesistent autentisering (för att förhindra "Man in the middle"-attacker)</span><span class="sxs-lookup"><span data-stu-id="9865c-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="9865c-121">Blockera äldre autentisering.</span><span class="sxs-lookup"><span data-stu-id="9865c-121">Block legacy authentication.</span></span>
- <span data-ttu-id="9865c-122">Konfigurera användarrisk- och användaråtkomstriskprinciper.</span><span class="sxs-lookup"><span data-stu-id="9865c-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="9865c-123">Aktivera villkorad åtkomst och MFA (Multi factor Authentication) för administratörer och icke-administratörer.</span><span class="sxs-lookup"><span data-stu-id="9865c-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="9865c-124">Konfigurera och tillämpa lösenordsprinciper.</span><span class="sxs-lookup"><span data-stu-id="9865c-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="9865c-125">Begränsa åtkomsten till privilegierade konton med Azure AD Privileged Identity Management.</span><span class="sxs-lookup"><span data-stu-id="9865c-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="9865c-126">Inaktivera åtkomst vid uppsägning.</span><span class="sxs-lookup"><span data-stu-id="9865c-126">Disable access upon termination.</span></span>
- <span data-ttu-id="9865c-127">Granska användarkonton och statusändringar.</span><span class="sxs-lookup"><span data-stu-id="9865c-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="9865c-128">Granska rollgrupp och administrativa ändringar.</span><span class="sxs-lookup"><span data-stu-id="9865c-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="9865c-129">Använd [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) för enheter och kategorin Hantera **enheter,** med vilken du kan:</span><span class="sxs-lookup"><span data-stu-id="9865c-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="9865c-130">Blockera fängelse trasiga och rotade mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="9865c-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="9865c-131">Konfigurera Intune för hantering av mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="9865c-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="9865c-132">Skapa efterlevnadsprinciper för Android-, iOS-, macOS- och Windows-enheter.</span><span class="sxs-lookup"><span data-stu-id="9865c-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="9865c-133">Skapa en enhetskonfigurationsprofil för Android-, iOS-, macOS- och Windows-enheter.</span><span class="sxs-lookup"><span data-stu-id="9865c-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="9865c-134">Skapa principer för appskydd för iOS och Windows.</span><span class="sxs-lookup"><span data-stu-id="9865c-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="9865c-135">Dölj information med låsskärmen.</span><span class="sxs-lookup"><span data-stu-id="9865c-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="9865c-136">Implementera lösenordsprinciper för mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="9865c-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="9865c-137">Kräv att mobila enheter låser in vid inaktivitet.</span><span class="sxs-lookup"><span data-stu-id="9865c-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="9865c-138">Kräv att mobila enheter rensar vid flera inloggningsfel.</span><span class="sxs-lookup"><span data-stu-id="9865c-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="9865c-139">Använd [Exchange Online Protection och Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md) för kategorin Skydda mot **hot,** med vilken du kan:</span><span class="sxs-lookup"><span data-stu-id="9865c-139">Use [Exchange Online Protection and Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="9865c-140">Aktivera avsändareautentisering (SPF, DMARC och DKIM).</span><span class="sxs-lookup"><span data-stu-id="9865c-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="9865c-141">Konfigurera ATP-principer (Advanced Threat Protection) (Office 365 Advanced Threat Protection).</span><span class="sxs-lookup"><span data-stu-id="9865c-141">Set up Office 365 Advanced Threat Protection (ATP) anti-phishing policies.</span></span>
- <span data-ttu-id="9865c-142">Implementera ATP-säkra bilagor.</span><span class="sxs-lookup"><span data-stu-id="9865c-142">Implement ATP Safe Attachments.</span></span>
- <span data-ttu-id="9865c-143">Implementera ATP Safe Links.</span><span class="sxs-lookup"><span data-stu-id="9865c-143">Implement ATP Safe Links.</span></span>
- <span data-ttu-id="9865c-144">Implementera principer för identifiering och svar av skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="9865c-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="9865c-145">Implementera principer för skräppost för utgående och inkommande.</span><span class="sxs-lookup"><span data-stu-id="9865c-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="9865c-146">Referenser:</span><span class="sxs-lookup"><span data-stu-id="9865c-146">References:</span></span>

- [<span data-ttu-id="9865c-147">Vanliga principer för identitets- och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="9865c-147">Common identity and device access policies</span></span>](../enterprise/identity-access-policies.md)
- [<span data-ttu-id="9865c-148">Skydda mot hot i Office 365</span><span class="sxs-lookup"><span data-stu-id="9865c-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="9865c-149">ATP säkra bilagor</span><span class="sxs-lookup"><span data-stu-id="9865c-149">ATP Safe Attachments</span></span>](../security/office-365-security/atp-safe-attachments.md)
- [<span data-ttu-id="9865c-150">Säkra ATP-länkar</span><span class="sxs-lookup"><span data-stu-id="9865c-150">ATP Safe Links</span></span>](../security/office-365-security/atp-safe-links.md)
- [<span data-ttu-id="9865c-151">ATP Säkra dokument</span><span class="sxs-lookup"><span data-stu-id="9865c-151">ATP Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
