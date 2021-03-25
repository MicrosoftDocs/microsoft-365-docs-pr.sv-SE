---
title: Integrera Microsoft Defender för Endpoint med andra Microsoft-lösningar
description: Läs om hur Microsoft Defender för Endpoint integreras med andra Microsoft-lösningar, bland annat Microsoft Defender för identitet och Azure Säkerhetscenter.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 defender, villkorsstyrd åtkomst, office, avancerat skydd mot hot, microsoft defender för identitet, microsoft defender för office, azure säkerhetscenter, microsoft cloud app security, azure sentinel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 287ad9adeccd527b756bdd5304d3c89fc1b2d789
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076490"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a><span data-ttu-id="50c79-104">Microsoft Defender för Endpoint och andra Microsoft-lösningar</span><span class="sxs-lookup"><span data-stu-id="50c79-104">Microsoft Defender for Endpoint and other Microsoft solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="50c79-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="50c79-105">**Applies to:**</span></span>
- [<span data-ttu-id="50c79-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="50c79-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="50c79-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="50c79-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="50c79-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="50c79-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="50c79-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="50c79-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a><span data-ttu-id="50c79-110">Integrera med andra Microsoft-lösningar</span><span class="sxs-lookup"><span data-stu-id="50c79-110">Integrate with other Microsoft solutions</span></span>

<span data-ttu-id="50c79-111">Microsoft Defender för Endpoint är direkt integrerat med olika Microsoft-lösningar.</span><span class="sxs-lookup"><span data-stu-id="50c79-111">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions.</span></span>

### <a name="azure-security-center"></a><span data-ttu-id="50c79-112">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="50c79-112">Azure Security Center</span></span>
<span data-ttu-id="50c79-113">Microsoft Defender för Endpoint tillhandahåller en omfattande lösning för serverskydd, inklusive funktioner för identifiering av slutpunkt och svar (EDR) på Windows-servrar.</span><span class="sxs-lookup"><span data-stu-id="50c79-113">Microsoft Defender for Endpoint provides a comprehensive server protection solution, including endpoint detection and response (EDR) capabilities on Windows Servers.</span></span>

### <a name="azure-sentinel"></a><span data-ttu-id="50c79-114">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="50c79-114">Azure Sentinel</span></span>
<span data-ttu-id="50c79-115">Med Microsoft Defender för slutpunktskopplingen kan du strömma aviseringar från Microsoft Defender för Slutpunkt till Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="50c79-115">The Microsoft Defender for Endpoint connector lets you stream alerts from Microsoft Defender for Endpoint into Azure Sentinel.</span></span> <span data-ttu-id="50c79-116">På så sätt kan du mer omfattande analysera säkerhetshändelser i organisationen och skapa spelböcker för effektiva och omedelbart svar.</span><span class="sxs-lookup"><span data-stu-id="50c79-116">This will enable you to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span>

### <a name="azure-information-protection"></a><span data-ttu-id="50c79-117">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="50c79-117">Azure Information Protection</span></span>
<span data-ttu-id="50c79-118">Skydda känsliga data samtidigt som du aktiverar produktiviteten på arbetsplatsen genom dataidentifiering och dataskydd.</span><span class="sxs-lookup"><span data-stu-id="50c79-118">Keep sensitive data secure while enabling productivity in the workplace through data discovery and data protection.</span></span>

### <a name="conditional-access"></a><span data-ttu-id="50c79-119">Med villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="50c79-119">Conditional Access</span></span>
<span data-ttu-id="50c79-120">Microsoft Defender för Endpoints riskpoäng för dynamiska enheter integreras i utvärderingen av villkorsstyrd åtkomst och säkerställer att endast säkra enheter har åtkomst till resurser.</span><span class="sxs-lookup"><span data-stu-id="50c79-120">Microsoft Defender for Endpoint's dynamic device risk score is integrated into the Conditional Access evaluation, ensuring that only secure devices have access to resources.</span></span> 

### <a name="microsoft-cloud-app-security"></a><span data-ttu-id="50c79-121">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="50c79-121">Microsoft Cloud App Security</span></span>
<span data-ttu-id="50c79-122">Microsoft Cloud App Security utnyttjar Microsoft Defender för Slutpunktsslutpunktssignaler för att tillåta direkt insyn i användning av molnprogram, inklusive användning av molntjänster som inte stöds (skugg-IT) från alla Microsoft Defender för övervakade slutpunktsenheter.</span><span class="sxs-lookup"><span data-stu-id="50c79-122">Microsoft Cloud App Security leverages Microsoft Defender for Endpoint endpoint signals to allow direct visibility into cloud application usage including the use of unsupported cloud services (shadow IT) from all Microsoft Defender for Endpoint monitored devices.</span></span>

### <a name="microsoft-defender-for-identity"></a><span data-ttu-id="50c79-123">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="50c79-123">Microsoft Defender for Identity</span></span>
<span data-ttu-id="50c79-124">Misstänkta aktiviteter körs under ett användarsammanhang.</span><span class="sxs-lookup"><span data-stu-id="50c79-124">Suspicious activities are processes running under a user context.</span></span> <span data-ttu-id="50c79-125">Integreringen mellan Microsoft Defender för Endpoint och Azure ATP ger flexibiliteten att genomföra undersökning av cybersäkerhet för aktiviteter och identiteter.</span><span class="sxs-lookup"><span data-stu-id="50c79-125">The integration between Microsoft Defender for Endpoint and Azure ATP provides the flexibility of conducting cyber security investigation across activities and identities.</span></span>

### <a name="microsoft-defender-for-office"></a><span data-ttu-id="50c79-126">Microsoft Defender för Office</span><span class="sxs-lookup"><span data-stu-id="50c79-126">Microsoft Defender for Office</span></span>
<span data-ttu-id="50c79-127">[Defender för Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) skyddar organisationen mot skadlig programvara i e-postmeddelanden och filer via ATP – säkra länkar, ATP – säkra bifogade filer, avancerade skydd mot nätfiske och förfalskningsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="50c79-127">[Defender for Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) helps protect your organization from malware in email messages or files through ATP Safe Links, ATP Safe Attachments, advanced Anti-Phishing, and spoof intelligence capabilities.</span></span> <span data-ttu-id="50c79-128">Integreringen mellan Office 365 ATP och Microsoft Defender för Endpoint gör att säkerhetsanalytiker är bättre på att undersöka startpunkten för en attack.</span><span class="sxs-lookup"><span data-stu-id="50c79-128">The integration between Office 365 ATP and Microsoft Defender for Endpoint enables security analysts to go upstream to investigate the entry point of an attack.</span></span> <span data-ttu-id="50c79-129">Genom delning av hotinformation kan attacker finnas och blockeras.</span><span class="sxs-lookup"><span data-stu-id="50c79-129">Through threat intelligence sharing, attacks can be contained and blocked.</span></span> 

>[!NOTE]
> <span data-ttu-id="50c79-130">Defender för Office 365-data visas för händelser under de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="50c79-130">Defender for Office 365 data is displayed for events within the last 30 days.</span></span> <span data-ttu-id="50c79-131">För aviseringar visas Defender för Office 365-data baserat på första aktivitetstiden.</span><span class="sxs-lookup"><span data-stu-id="50c79-131">For alerts, Defender for Office 365 data is displayed based on first activity time.</span></span> <span data-ttu-id="50c79-132">Därefter är data inte längre tillgängliga i Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="50c79-132">After that, the data is no longer available in Defender for Office 365.</span></span>

### <a name="skype-for-business"></a><span data-ttu-id="50c79-133">Skype för företag</span><span class="sxs-lookup"><span data-stu-id="50c79-133">Skype for Business</span></span>
<span data-ttu-id="50c79-134">Integreringen av Skype för företag är ett sätt för analytiker att kommunicera med en potentiellt komprometterad användare eller enhetsägare via en enkel knapp från portalen.</span><span class="sxs-lookup"><span data-stu-id="50c79-134">The Skype for Business integration provides a way for analysts to communicate with a potentially compromised user or device owner through a simple button from the portal.</span></span>

## <a name="microsoft-365-defender"></a><span data-ttu-id="50c79-135">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="50c79-135">Microsoft 365 Defender</span></span>
<span data-ttu-id="50c79-136">Med Microsoft 365 Defender utgör Microsoft Defender för Endpoint och olika Microsoft-säkerhetslösningar en enhetlig företagssäkerhetssvit före och efter intrång som integrerar inbyggt i slutpunkt, identitet, e-post och program för att identifiera, förhindra, undersöka och automatiskt svara på avancerade attacker.</span><span class="sxs-lookup"><span data-stu-id="50c79-136">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate and automatically respond to sophisticated attacks.</span></span> 
 
[<span data-ttu-id="50c79-137">Läs mer om Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="50c79-137">Learn more about Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)


## <a name="related-topics"></a><span data-ttu-id="50c79-138">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="50c79-138">Related topics</span></span>
- [<span data-ttu-id="50c79-139">Konfigurera integrering och andra avancerade funktioner</span><span class="sxs-lookup"><span data-stu-id="50c79-139">Configure integration and other advanced features</span></span>](advanced-features.md)
- [<span data-ttu-id="50c79-140">Översikt över Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="50c79-140">Microsoft 365 Defender overview</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)
- [<span data-ttu-id="50c79-141">Aktivera Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="50c79-141">Turn on Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)
- [<span data-ttu-id="50c79-142">Skydda användare, data och enheter med villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="50c79-142">Protect users, data, and devices with Conditional Access</span></span>](conditional-access.md)
