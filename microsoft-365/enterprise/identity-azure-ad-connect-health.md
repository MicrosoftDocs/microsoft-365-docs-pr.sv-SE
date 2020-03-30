---
title: 'Steg 8: Övervaka synkroniseringshälsa'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå och konfigurera Azure AD Connect Health.
ms.openlocfilehash: 21cfd88617bccab3f0a2bdb51c0d320cd4568a56
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "42811823"
---
# <a name="step-8-monitor-synchronization-health"></a><span data-ttu-id="d4326-103">Steg 8: Övervaka synkroniseringshälsa</span><span class="sxs-lookup"><span data-stu-id="d4326-103">Step 8: Monitor synchronization health</span></span>

<span data-ttu-id="d4326-104">*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="d4326-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="d4326-105">I det här steget installerar du en Azure AD Connect Health-agent på var och en av dina lokala identitetsservrar för att övervaka din identitetsinfrastruktur och de synkroniseringstjänster som tillhandahålls av Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="d4326-105">In this step, you'll install an Azure AD Connect Health agent on each of your on-premises identity servers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="d4326-106">Övervakningsinformationen visas i en Azure AD Connect Health-portal, där du kan se varningar, prestandaövervakning, användningsanalys och annan information.</span><span class="sxs-lookup"><span data-stu-id="d4326-106">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Komponenter i Azure AD Connect Health](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

<span data-ttu-id="d4326-108">Det viktiga beslutet för hur du ska använda Azure AD Connect Health, baseras på hur du använder Azure AD Connect:</span><span class="sxs-lookup"><span data-stu-id="d4326-108">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="d4326-109">Om du använder **hanterad autentisering** börjar du med [Använda Azure AD Connect Health med synkronisering](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) för att förstå och konfigurera Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="d4326-109">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="d4326-110">Om du bara synkroniserar namnen på de konton och grupper som använder **federerad autentisering** med Active Directory Federation Services (AD FS), börjar du med [Använda Azure AD Connect Health med AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) för att förstå och konfigurera Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="d4326-110">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="d4326-111">När du har slutfört det här steget har du:</span><span class="sxs-lookup"><span data-stu-id="d4326-111">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="d4326-112">Azure AD Connect Health-agenten installerad på dina lokala identitetsproviderservrar.</span><span class="sxs-lookup"><span data-stu-id="d4326-112">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="d4326-113">Azure AD Connect Health-portalen visar aktuell status för lokal infrastruktur och synkronisering med Azure AD-klientorganisationen för dina Office 365- och EMS-prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="d4326-113">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Office 365 and EMS subscriptions.</span></span>

<span data-ttu-id="d4326-114">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-identity-sync-health) för detta steg.</span><span class="sxs-lookup"><span data-stu-id="d4326-114">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync-health) for this step.</span></span>


## <a name="next-step"></a><span data-ttu-id="d4326-115">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="d4326-115">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step9.png)| [<span data-ttu-id="d4326-116">Enklare uppdatering av lösenord</span><span class="sxs-lookup"><span data-stu-id="d4326-116">Simplify password updates</span></span>](identity-password-writeback.md) |

