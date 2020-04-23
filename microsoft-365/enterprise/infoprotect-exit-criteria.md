---
title: Avslutsvillkor för informationsskyddets infrastruktur
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
description: Kontrollera villkoren för informationsskyddsbaserade tjänster och infrastruktur för att säkerställa att din konfiguration uppfyller kraven för Microsoft 365 Enterprise.
ms.openlocfilehash: c0b4ff6a0d289b8a8c63255d817ea455df00bf13
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631639"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="453d9-103">Avslutsvillkor för informationsskyddets infrastruktur</span><span class="sxs-lookup"><span data-stu-id="453d9-103">Information protection infrastructure exit criteria</span></span>

![Fas 6: Informationsskydd](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="453d9-105">Kontrollera att infrastrukturen för informationsskydd uppfyller följande krav och att du har bedömt vilka villkor som kan vara valfria.</span><span class="sxs-lookup"><span data-stu-id="453d9-105">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="453d9-106">Obligatoriskt: Säkerhets- och informationsskyddsnivåer för din organisation har definierats</span><span class="sxs-lookup"><span data-stu-id="453d9-106">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="453d9-107">Du har planerat för och avgjort vilka säkerhetsnivåer din organisation behöver.</span><span class="sxs-lookup"><span data-stu-id="453d9-107">You've planned for and determined the security levels that your organization needs.</span></span> <span data-ttu-id="453d9-108">Dessa nivåer definierar en lägsta säkerhetsnivå och ytterligare nivåer för känsligare information och den datasäkerhet den kräver.</span><span class="sxs-lookup"><span data-stu-id="453d9-108">These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="453d9-109">Som minst använder du tre säkerhetsnivåer:</span><span class="sxs-lookup"><span data-stu-id="453d9-109">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="453d9-110">Baslinje</span><span class="sxs-lookup"><span data-stu-id="453d9-110">Baseline</span></span>
- <span data-ttu-id="453d9-111">Känslig</span><span class="sxs-lookup"><span data-stu-id="453d9-111">Sensitive</span></span>
- <span data-ttu-id="453d9-112">Strikt reglerad</span><span class="sxs-lookup"><span data-stu-id="453d9-112">Highly regulated</span></span>

<span data-ttu-id="453d9-113">Vid behov kan [Steg 1](infoprotect-define-sec-infoprotect-levels.md) hjälpa dig med detta krav.</span><span class="sxs-lookup"><span data-stu-id="453d9-113">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="453d9-114">Obligatoriskt: Ökad säkerhet för Microsoft 365 har konfigurerats</span><span class="sxs-lookup"><span data-stu-id="453d9-114">Required: Increased security for Microsoft 365 is configured</span></span>

<span data-ttu-id="453d9-115">Du har konfigurerat följande inställningar för [ökad säkerhet i Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span><span class="sxs-lookup"><span data-stu-id="453d9-115">You've configured the following settings for [Microsoft 365 increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="453d9-116">Principer för hothantering i Microsoft 365 Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="453d9-116">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="453d9-117">Ytterligare inställningar för hela Exchange Online-klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="453d9-117">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="453d9-118">Delningsprinciper för hela klientorganisationen i administrationscentret för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="453d9-118">Tenant-wide sharing policies in SharePoint Online admin center</span></span>
- <span data-ttu-id="453d9-119">Inställningar i Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="453d9-119">Settings in Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="453d9-120">Du har även [aktiverat Office 365 Advanced Threat Protection för SharePoint, OneDrive och Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="453d9-120">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="453d9-121">Vid behov kan [Steg 3](infoprotect-configure-increased-security-office-365.md) hjälpa dig med detta krav.</span><span class="sxs-lookup"><span data-stu-id="453d9-121">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="453d9-122">Valfritt: Klassificering har konfigurerats i hela din miljö</span><span class="sxs-lookup"><span data-stu-id="453d9-122">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="453d9-123">Du har samarbetat med dina juridiska team och efterlevnadsteam för att utveckla ett lämpligt klassificerings- och märkningsschema för organisationens datastyrning och säkerhetsprinciper.</span><span class="sxs-lookup"><span data-stu-id="453d9-123">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization's data governance and security policies.</span></span> 

<span data-ttu-id="453d9-124">Dessa principer motsvarar konfigurationen och distributionen av:</span><span class="sxs-lookup"><span data-stu-id="453d9-124">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="453d9-125">Känsliga datatyper</span><span class="sxs-lookup"><span data-stu-id="453d9-125">Sensitive data types</span></span>
- <span data-ttu-id="453d9-126">Kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="453d9-126">Retention labels</span></span>
- <span data-ttu-id="453d9-127">Känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="453d9-127">Sensitivity labels</span></span>
- <span data-ttu-id="453d9-128">Azure Information Protection-etiketter</span><span class="sxs-lookup"><span data-stu-id="453d9-128">Azure Information Protection labels</span></span>

<span data-ttu-id="453d9-129">Vid behov kan [Steg 2](infoprotect-configure-classification.md) hjälpa dig med detta krav.</span><span class="sxs-lookup"><span data-stu-id="453d9-129">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a><span data-ttu-id="453d9-130">Valfritt: Windows Information Protection distribueras i hela din miljö</span><span class="sxs-lookup"><span data-stu-id="453d9-130">Optional: Windows Information Protection is deployed across your environment</span></span>

<span data-ttu-id="453d9-131">Dina registrerade Windows 10 Enterprise-enheter innehåller en Intune-princip som definierar:</span><span class="sxs-lookup"><span data-stu-id="453d9-131">Your enrolled Windows 10 Enterprise devices have an Intune policy deployed and applied that defines:</span></span>

- <span data-ttu-id="453d9-132">Vilka appar som ska skyddas.</span><span class="sxs-lookup"><span data-stu-id="453d9-132">Which apps to protect.</span></span>
- <span data-ttu-id="453d9-133">Skyddsnivån.</span><span class="sxs-lookup"><span data-stu-id="453d9-133">The level of protection.</span></span>
- <span data-ttu-id="453d9-134">Hur långt skyddet sträcker sig.</span><span class="sxs-lookup"><span data-stu-id="453d9-134">Where the protection extends.</span></span>

<span data-ttu-id="453d9-135">Vid behov kan [Steg 4](infoprotect-deploy-windows-information-protection.md) hjälpa dig med detta krav.</span><span class="sxs-lookup"><span data-stu-id="453d9-135">If needed, [Step 4](infoprotect-deploy-windows-information-protection.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-data-loss-prevention-dlp-is-deployed"></a><span data-ttu-id="453d9-136">Valfritt: Dataförlustskydd (DLP) har distribuerats</span><span class="sxs-lookup"><span data-stu-id="453d9-136">Optional: Data Loss Prevention (DLP) is deployed</span></span>

<span data-ttu-id="453d9-137">Du har analyserat, testat och distribuerat en uppsättning DLP-principer – som innehåller platser och regler med villkor och åtgärder – som din organisation behöver för att skydda kunddata och andra typer av privata data, samt för att kunna följa branschbaserade och regionala regler och föreskrifter.</span><span class="sxs-lookup"><span data-stu-id="453d9-137">You have analyzed, tested, and then rolled out the set of DLP policies—with locations and rules with conditions and actions—that your organization requires to protect customer and other types of private data and to adhere to industry and regional regulations and requirements.</span></span>

<span data-ttu-id="453d9-138">Din personal inom dataefterlevnad och säkerhet använder instrumentpanelen för säkerhet och efterlevnad till att övervaka DLP-incidenter.</span><span class="sxs-lookup"><span data-stu-id="453d9-138">Your data compliance and security staff are using the Security & Compliance dashboard to monitor DLP incidents.</span></span>

<span data-ttu-id="453d9-139">Vid behov kan [Steg 5](infoprotect-data-loss-prevention.md) hjälpa dig med detta krav.</span><span class="sxs-lookup"><span data-stu-id="453d9-139">If needed, [Step 5](infoprotect-data-loss-prevention.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step6"></a>
## <a name="optional-email-encryption-is-configured"></a><span data-ttu-id="453d9-140">Valfritt: E-postkryptering har konfigurerats</span><span class="sxs-lookup"><span data-stu-id="453d9-140">Optional: Email encryption is configured</span></span>

<span data-ttu-id="453d9-141">Du har konfigurerat följande e-postkryptering vid behov för din organisation:</span><span class="sxs-lookup"><span data-stu-id="453d9-141">You've configured the following email encryption as needed for your organization:</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="453d9-142">**Krypteringsmetod**</span><span class="sxs-lookup"><span data-stu-id="453d9-142">**Encryption method**</span></span> | <span data-ttu-id="453d9-143">**För e-post som skickas**</span><span class="sxs-lookup"><span data-stu-id="453d9-143">**For email sent**</span></span> |
| [<span data-ttu-id="453d9-144">Meddelandekryptering i Office 365 (OME)</span><span class="sxs-lookup"><span data-stu-id="453d9-144">Office 365 Message Encryption (OME)</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | <span data-ttu-id="453d9-145">Utanför organisationen med kryptering</span><span class="sxs-lookup"><span data-stu-id="453d9-145">Outside your organization with encryption</span></span> |
| [<span data-ttu-id="453d9-146">IRM (Information Rights Management)</span><span class="sxs-lookup"><span data-stu-id="453d9-146">Information Rights Management (IRM)</span></span>](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | <span data-ttu-id="453d9-147">Med både kryptering och behörigheter</span><span class="sxs-lookup"><span data-stu-id="453d9-147">With both encryption and permissions</span></span> |
| [<span data-ttu-id="453d9-148">S/MIME (Secure/Multipurpose Internet Mail Extensions)</span><span class="sxs-lookup"><span data-stu-id="453d9-148">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | <span data-ttu-id="453d9-149">Med både kryptering och digitala signaturer som använder kryptering med offentliga nycklar</span><span class="sxs-lookup"><span data-stu-id="453d9-149">With both encryption and digital signatures using public key cryptography</span></span> |
|||

<span data-ttu-id="453d9-150">Vid behov kan [Steg 6](infoprotect-email-encryption.md) hjälpa dig med detta krav.</span><span class="sxs-lookup"><span data-stu-id="453d9-150">If needed, [Step 6](infoprotect-email-encryption.md) can help you meet this requirement.</span></span>

<a name="crit-infoprotect-step7"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="453d9-151">Valfritt: Konfigurera Privileged Access Management i Office 365</span><span class="sxs-lookup"><span data-stu-id="453d9-151">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="453d9-152">Du har använt informationen i [Konfigurera Privileged Access Management i Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) för att aktivera privilegierad åtkomst och skapa en eller flera principer för privilegierad åtkomst inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="453d9-152">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="453d9-153">Du har konfigurerat dessa principer och just-in-time-åtkomst är aktiverad för åtkomst till känsliga data eller kritiska konfigurationsinställningar.</span><span class="sxs-lookup"><span data-stu-id="453d9-153">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="453d9-154">Vid behov kan [Steg 7](infoprotect-configure-privileged-access-management.md) hjälpa dig med detta krav.</span><span class="sxs-lookup"><span data-stu-id="453d9-154">If needed, [Step 7](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="453d9-155">Resultat och nästa steg</span><span class="sxs-lookup"><span data-stu-id="453d9-155">Results and next steps</span></span>

<span data-ttu-id="453d9-156">Din infrastruktur för informationsskydd i Microsoft 365 Enterprise använder definierade säkerhetsnivåer, ökad säkerhet för Office 365, klassificering med känsliga datatyper och etiketter, Windows Information Protection, dataförlustskydd, e-postkryptering och Privileged Access Management.</span><span class="sxs-lookup"><span data-stu-id="453d9-156">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, Windows Information Protection, Data Loss Prevention, email encryption, and privileged access management.</span></span>

<span data-ttu-id="453d9-157">Om du har följt distributionen från slutpunkt till slutpunkt för Microsoft 365 Enterprise, är du nu redo att låta [arbetsbelastningar och scenarier](deploy-workloads.md) utnyttja funktioner och konfiguration av den grundläggande infrastrukturen.</span><span class="sxs-lookup"><span data-stu-id="453d9-157">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
