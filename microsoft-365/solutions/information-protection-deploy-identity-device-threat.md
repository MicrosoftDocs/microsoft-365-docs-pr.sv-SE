---
title: Använda identitets-, enhets- och hotskydd för dataskyddsförordningen
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
description: Förhindra personliga databrott med tjänster för identitet, enhet och hotskydd i Microsoft 365.
ms.openlocfilehash: 5e08ef574e199769e572b3836b3323dc88fc4bbd
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199471"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="0a10a-103">Använda identitets-, enhets- och hotskydd för dataskyddsförordningen</span><span class="sxs-lookup"><span data-stu-id="0a10a-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="0a10a-104">Microsoft 365 tillhandahåller ett antal funktioner för identitet, enheter och hotskydd som organisationer kan använda för att hjälpa till att uppfylla sekretessrelaterade bestämmelser om datasekretess.</span><span class="sxs-lookup"><span data-stu-id="0a10a-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="0a10a-105">I den här artikeln beskrivs vad datasekretessbestämmelser kräver på dessa områden och en lista med relaterade Microsoft 365-funktioner och -tjänster med länkar till mer information som hjälper dig att uppfylla implementeringskraven.</span><span class="sxs-lookup"><span data-stu-id="0a10a-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="0a10a-106">Hur identitets-, enhets- och hotskydd relaterar till dataskyddsförordningen</span><span class="sxs-lookup"><span data-stu-id="0a10a-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="0a10a-107">Även om datasekretessreglerna varierar beroende på deras specifika natur är det viktigaste för det de kallar i GDPR:s artikel 5(1)(f), där det står att:</span><span class="sxs-lookup"><span data-stu-id="0a10a-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span>

- <span data-ttu-id="0a10a-108">Personuppgifter ska bearbetas på ett sätt som säkerställer tillräcklig säkerhet för personuppgifter, inklusive skydd mot obehörig eller olaglig bearbetning och mot oavsiktlig förlust, intrång eller skada genom att använda lämpliga tekniska åtgärder eller organisationsåtgärder (integritet och konfidentialitet).</span><span class="sxs-lookup"><span data-stu-id="0a10a-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="0a10a-109">Eftersom personliga databrott ofta orsakas av administrativa intrång eller slutanvändarkontointrång och skadlig systemåtkomst.</span><span class="sxs-lookup"><span data-stu-id="0a10a-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="0a10a-110">Till exempel kan en hack för ett administratörskonto resultera i att kundkortsnummer eller annan personlig information förs över.</span><span class="sxs-lookup"><span data-stu-id="0a10a-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="0a10a-111">Alla vi rekommenderar att du använder identitets-, enhets- och hotskydd tillsammans med Microsoft 365 bör potentiellt implementeras, vilket återspeglas i efterlevnadsresultatet i Efterlevnadshanteraren.</span><span class="sxs-lookup"><span data-stu-id="0a10a-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="0a10a-112">Använda resultaten från ditt utvärderingsarbete och Efterlevnadshanteraren</span><span class="sxs-lookup"><span data-stu-id="0a10a-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="0a10a-113">Efterlevnadshanteraren innehåller identitets-, enhets- och hotskydd med följande kategorier:</span><span class="sxs-lookup"><span data-stu-id="0a10a-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="0a10a-114">Identiteten motsvarar **kategorin Kontrollåtkomst**</span><span class="sxs-lookup"><span data-stu-id="0a10a-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="0a10a-115">Enheten motsvarar kategorin **Hantera** enheter</span><span class="sxs-lookup"><span data-stu-id="0a10a-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="0a10a-116">Hotskydd motsvarar **kategorin Skydda mot** hot</span><span class="sxs-lookup"><span data-stu-id="0a10a-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="0a10a-117">Om dessa väljs i vår exempeluppsättning med fyra huvudregler för datasekretess anger Efterlevnadshanteraren 90 förbättringsåtgärder, varav de flesta har poänget "27".</span><span class="sxs-lookup"><span data-stu-id="0a10a-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="0a10a-118">Eftersom Ett så stort antal anges av Efterlevnadshanteraren för dessa kategorier anges några av de vanligaste här, som referens.</span><span class="sxs-lookup"><span data-stu-id="0a10a-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="0a10a-119">Använd [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) för identitet och kategorin **Kontrollåtkomst,** som du kan med:</span><span class="sxs-lookup"><span data-stu-id="0a10a-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="0a10a-120">Implementera replay-authentication (för att förhindra "man i mitten"-attacker)</span><span class="sxs-lookup"><span data-stu-id="0a10a-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="0a10a-121">Blockera äldre autentisering.</span><span class="sxs-lookup"><span data-stu-id="0a10a-121">Block legacy authentication.</span></span>
- <span data-ttu-id="0a10a-122">Konfigurera principer för användarrisk och användar inloggningsrisk.</span><span class="sxs-lookup"><span data-stu-id="0a10a-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="0a10a-123">Aktivera villkorlig åtkomst och multifaktorautentisering (MFA) för administratörer och icke-administratörer.</span><span class="sxs-lookup"><span data-stu-id="0a10a-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="0a10a-124">Konfigurera och tillämpa lösenordsprinciper.</span><span class="sxs-lookup"><span data-stu-id="0a10a-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="0a10a-125">Begränsa åtkomst till konton med behörighet med identitetshantering med Azure AD-behörighet.</span><span class="sxs-lookup"><span data-stu-id="0a10a-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="0a10a-126">Inaktivera åtkomst vid uppsägning.</span><span class="sxs-lookup"><span data-stu-id="0a10a-126">Disable access upon termination.</span></span>
- <span data-ttu-id="0a10a-127">Granska användarkonton och statusändringar.</span><span class="sxs-lookup"><span data-stu-id="0a10a-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="0a10a-128">Granska rollgrupper och administrativa ändringar.</span><span class="sxs-lookup"><span data-stu-id="0a10a-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="0a10a-129">Använd [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) för enheter och kategorin **Hantera** enheter med vilka du kan:</span><span class="sxs-lookup"><span data-stu-id="0a10a-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="0a10a-130">Blockera jail broken and rooted mobile devices.</span><span class="sxs-lookup"><span data-stu-id="0a10a-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="0a10a-131">Konfigurera Intune för hantering av mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="0a10a-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="0a10a-132">Skapa efterlevnadsprinciper för Android-, iOS-, macOS- och Windows-enheter.</span><span class="sxs-lookup"><span data-stu-id="0a10a-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="0a10a-133">Skapa en profil för enhetskonfiguration för Android-, iOS-, macOS- och Windows-enheter.</span><span class="sxs-lookup"><span data-stu-id="0a10a-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="0a10a-134">Skapa principer för appskydd för iOS och Windows.</span><span class="sxs-lookup"><span data-stu-id="0a10a-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="0a10a-135">Dölj information med låsskärmen.</span><span class="sxs-lookup"><span data-stu-id="0a10a-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="0a10a-136">Implementera lösenordsprinciper för mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="0a10a-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="0a10a-137">Kräv att mobila enheter låser sig vid inaktivitet.</span><span class="sxs-lookup"><span data-stu-id="0a10a-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="0a10a-138">Kräva att mobila enheter rensar vid flera inloggningsfel.</span><span class="sxs-lookup"><span data-stu-id="0a10a-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="0a10a-139">Använd [Exchange Online Protection och Microsoft Defender för Office 365](../security/office-365-security/defender-for-office-365.md) **för** kategorin Skydda mot hot med vilka du kan:</span><span class="sxs-lookup"><span data-stu-id="0a10a-139">Use [Exchange Online Protection and Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="0a10a-140">Aktivera avsändarautentisering (SPF, DMARC och DKIM).</span><span class="sxs-lookup"><span data-stu-id="0a10a-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="0a10a-141">Konfigurera Microsoft Defender för Office 365 mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="0a10a-141">Set up Microsoft Defender for Office 365 anti-phishing policies.</span></span>
- <span data-ttu-id="0a10a-142">Implementera säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="0a10a-142">Implement Safe Attachments.</span></span>
- <span data-ttu-id="0a10a-143">Implementera säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="0a10a-143">Implement Safe Links.</span></span>
- <span data-ttu-id="0a10a-144">Implementera principer för identifiering av skadlig programvara och svar.</span><span class="sxs-lookup"><span data-stu-id="0a10a-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="0a10a-145">Implementera principer för utgående och inkommande skräppost.</span><span class="sxs-lookup"><span data-stu-id="0a10a-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="0a10a-146">Referenser:</span><span class="sxs-lookup"><span data-stu-id="0a10a-146">References:</span></span>

- [<span data-ttu-id="0a10a-147">Vanliga principer för identitets- och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="0a10a-147">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)
- [<span data-ttu-id="0a10a-148">Skydda mot hot i Office 365</span><span class="sxs-lookup"><span data-stu-id="0a10a-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="0a10a-149">Säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="0a10a-149">Safe Attachments</span></span>](../security/office-365-security/safe-attachments.md)
- [<span data-ttu-id="0a10a-150">Säkra länkar</span><span class="sxs-lookup"><span data-stu-id="0a10a-150">Safe Links</span></span>](../security/office-365-security/safe-links.md)
- [<span data-ttu-id="0a10a-151">Säkra dokument</span><span class="sxs-lookup"><span data-stu-id="0a10a-151">Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
