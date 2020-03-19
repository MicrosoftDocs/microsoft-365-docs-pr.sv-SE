---
title: 'Steg 3: Konfigurera ökad säkerhet för Microsoft 365'
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
description: Förstå och konfigurera ökad säkerhet för Microsoft 365.
ms.openlocfilehash: eabf0d60f3cfb61b7fffcc688a080ba99f83293e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808094"
---
# <a name="step-3-configure-increased-security-for-microsoft-365"></a><span data-ttu-id="6df54-103">Steg 3: Konfigurera ökad säkerhet för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6df54-103">Step 3: Configure increased security for Microsoft 365</span></span>

<span data-ttu-id="6df54-104">*Det här steget är obligatoriskt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="6df54-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fas 6: Informationsskydd](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="6df54-106">Om du vill vara säker på att din Microsoft 365-prenumeration och tillhörande data skyddas mot skadliga hot redan från början och framåt konfigurerar du följande:</span><span class="sxs-lookup"><span data-stu-id="6df54-106">To ensure that your Microsoft 365 subscription and its data start off and remain secure from malicious threats, configure the following:</span></span>

- [<span data-ttu-id="6df54-107">Ställ in principer för hantering av hot</span><span class="sxs-lookup"><span data-stu-id="6df54-107">Tune threat management policies</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#tune-threat-management-policies-in-the-microsoft-365-security-center)
- [<span data-ttu-id="6df54-108">Ytterligare inställningar för hela Exchange Online-klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="6df54-108">Additional Exchange Online tenant-wide settings</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-additional-exchange-online-tenant-wide-settings)
- [<span data-ttu-id="6df54-109">Delningsprinciper för hela klientorganisationen i administrationscentret för SharePoint</span><span class="sxs-lookup"><span data-stu-id="6df54-109">Tenant-wide sharing policies in the SharePoint admin center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-tenant-wide-sharing-policies-in-sharepoint-admin-center)
- [<span data-ttu-id="6df54-110">Inställningar i Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="6df54-110">Settings in Azure Active Directory (Azure AD)</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-settings-in-azure-active-directory)

<span data-ttu-id="6df54-111">När det är konfigurerat kan du få information om säkerhetsstatusen från:</span><span class="sxs-lookup"><span data-stu-id="6df54-111">Once configured, you can obtain information about your security status from:</span></span>

- [<span data-ttu-id="6df54-112">Instrumentpaneler och rapporter i Microsoft Security Center</span><span class="sxs-lookup"><span data-stu-id="6df54-112">Dashboards and reports in the Microsoft security Center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#view-dashboards-and-reports-in-the-security-and-compliance-centers)
- [<span data-ttu-id="6df54-113">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="6df54-113">Microsoft Secure Score</span></span>](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)

<span data-ttu-id="6df54-114">En extra säkerhetsfunktion är [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) som hjälper din organisation att samarbeta säkrare genom att:</span><span class="sxs-lookup"><span data-stu-id="6df54-114">An additional security feature is [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="6df54-115">Skydda [länkar](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) och [bifogade filer](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) i e-post.</span><span class="sxs-lookup"><span data-stu-id="6df54-115">Protecting [links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) and [attachments](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) in email.</span></span> 
- <span data-ttu-id="6df54-116">Tillhandahålla information om bedrägerier och anti-phishing för e-post i Exchange Online och [filer i SharePoint Online, OneDrive för företag och Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="6df54-116">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and [files in SharePoint Online, OneDrive for Business, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span></span> 

<span data-ttu-id="6df54-117">Office 365 ATP är endast tillgängligt med Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="6df54-117">Office 365 ATP is only available with Microsoft 365 E5.</span></span>

|||
|:-------|:-----|
|![Testlabbsguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="6df54-119">Testlabbsguide: Konfigurera ökad säkerhet i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6df54-119">Test Lab Guide: Configure increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="6df54-120">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](infoprotect-exit-criteria.md#crit-infoprotect-step3) som motsvarar det här steget.</span><span class="sxs-lookup"><span data-stu-id="6df54-120">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="6df54-121">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="6df54-121">Next step</span></span>


|||
|:-------|:-----|
|![Steg 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="6df54-123">Konfigurera Windows-informationsskydd</span><span class="sxs-lookup"><span data-stu-id="6df54-123">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|


