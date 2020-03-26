---
title: 'Steg 6: skydda mot obehörig inloggning'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå och konfigurera Azure AD Identity Protection.
ms.openlocfilehash: b1dea9d2917c45bf87bd972f56c9eac2b074c252
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "42812933"
---
# <a name="step-6-protect-against-credential-compromise"></a><span data-ttu-id="2b57c-103">Steg 6: skydda mot obehörig inloggning</span><span class="sxs-lookup"><span data-stu-id="2b57c-103">Step 6: Protect against credential compromise</span></span>

<span data-ttu-id="2b57c-104">*Det här steget är valfritt och gäller endast E5-versionen av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="2b57c-104">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="2b57c-105">I det här steget får du lära dig hur du konfigurerar principer som skyddar mot obehörig inloggning, där en angripare bestämmer en användares kontonamn och lösenord för att få åtkomst till organisationens molntjänster och -data.</span><span class="sxs-lookup"><span data-stu-id="2b57c-105">In this step, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="2b57c-106">Med Azure AD Identity Protection får du ett antal olika sätt att förhindra att en angripare kan röra sig lateralt genom dina konton och grupper, och sedan till dina mest värdefulla data.</span><span class="sxs-lookup"><span data-stu-id="2b57c-106">Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="2b57c-107">Med Azure AD Identity Protection kan du:</span><span class="sxs-lookup"><span data-stu-id="2b57c-107">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="2b57c-108">Fastställa och åtgärda potentiella säkerhetsproblem i organisationens identiteter</span><span class="sxs-lookup"><span data-stu-id="2b57c-108">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="2b57c-109">I Azure AD används maskininlärning för att identifiera avvikelser och misstänkt aktivitet, till exempel inloggningar och aktiviteter efter inloggning.</span><span class="sxs-lookup"><span data-stu-id="2b57c-109">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities.</span></span> <span data-ttu-id="2b57c-110">Med dessa data genererar Identity Protection rapporter och aviseringar som hjälper dig att utvärdera problem och vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="2b57c-110">Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="2b57c-111">Identifiera misstänkta åtgärder som är relaterade till organisationens identitet och svara på dem automatiskt</span><span class="sxs-lookup"><span data-stu-id="2b57c-111">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="2b57c-112">Du kan konfigurera riskfyllda principer som automatiskt reagerar på problem som upptäcks när en viss risknivå har uppnåtts.</span><span class="sxs-lookup"><span data-stu-id="2b57c-112">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="2b57c-113">Dessa principer, förutom andra kontroller för villkorlig åtkomst i Azure Active Directory och Enterprise Mobility + Security (EMS), kan antingen automatiskt blockera åtkomst eller utföra korrigeringsåtgärder, t. ex. återställning av lösenord och krav på multifaktorautentisering för efterföljande inloggningar.</span><span class="sxs-lookup"><span data-stu-id="2b57c-113">These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="2b57c-114">Undersök misstänkta händelser och åtgärda dem med administrativa åtgärder</span><span class="sxs-lookup"><span data-stu-id="2b57c-114">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="2b57c-115">Du kan undersöka riskhändelser med hjälp av information om säkerhetshändelsen.</span><span class="sxs-lookup"><span data-stu-id="2b57c-115">You can investigate risk events using information about the security incident.</span></span> <span data-ttu-id="2b57c-116">Enkla arbetsflöden är tillgängliga för att spåra undersökningar och initiera åtgärder för reparationer, som återställning av lösenord.</span><span class="sxs-lookup"><span data-stu-id="2b57c-116">Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="2b57c-117">Se [More information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection) (Mer information om Azure AD Identity Protection).</span><span class="sxs-lookup"><span data-stu-id="2b57c-117">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="2b57c-118">Se [stegen för att aktivera Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span><span class="sxs-lookup"><span data-stu-id="2b57c-118">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="2b57c-119">Resultatet av det här steget är att du har aktiverat Azure AD Identity Protection och att du använder det för att:</span><span class="sxs-lookup"><span data-stu-id="2b57c-119">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="2b57c-120">Åtgärda potentiella identitetssårbarheter.</span><span class="sxs-lookup"><span data-stu-id="2b57c-120">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="2b57c-121">Upptäck möjliga försök till intrång i autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="2b57c-121">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="2b57c-122">Undersök och åtgärda fortlöpande misstänkta identitetstillbud.</span><span class="sxs-lookup"><span data-stu-id="2b57c-122">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="2b57c-124">Testlabbguide: Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="2b57c-124">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="2b57c-125">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-identity-ident-prot) för detta steg.</span><span class="sxs-lookup"><span data-stu-id="2b57c-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="2b57c-126">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="2b57c-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="2b57c-127">Synkronisera kataloger</span><span class="sxs-lookup"><span data-stu-id="2b57c-127">Synchronize directories</span></span>](identity-azure-ad-connect.md) |


