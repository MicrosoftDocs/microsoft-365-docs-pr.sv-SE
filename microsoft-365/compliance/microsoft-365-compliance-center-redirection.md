---
title: Omdirigera användare från säkerhets- Office 365 säkerhets- och efterlevnadscentret till Microsoft 365 säkerhets- och efterlevnadscenter
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: Läs mer om hur du automatiskt Office 365 användare i Säkerhets- och efterlevnadscenter Microsoft 365 säkerhets- och efterlevnadscenter.
ms.collection: M365-security-compliance
ms.openlocfilehash: fb667e8f19b26cbe229b3aceffe194a86133c261
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772542"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="fb168-103">Omdirigera användare från säkerhets- Office 365 säkerhets- och efterlevnadscentret till Microsoft 365 säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="fb168-103">Redirect users from the Office 365 Security and Compliance center to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="fb168-104">Den här artikeln förklarar hur automatisk omdirigering fungerar för användare som använder efterlevnadslösningar från säkerhets- och efterlevnadscentret för Office 365 (protection.office.com) till efterlevnadscentret för Microsoft 365 (compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="fb168-104">This article explains how automatic redirection works for users accessing compliance solutions from the Office 365 Security and Compliance Center (protection.office.com) to the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="fb168-105">Vad du kan förvänta dig</span><span class="sxs-lookup"><span data-stu-id="fb168-105">What to expect</span></span>

<span data-ttu-id="fb168-106">Automatisk omdirigering är som standard aktiverad för alla användare som har åtkomst till följande efterlevnadsrelaterade lösningar Office 365 säkerhet och efterlevnad (protection.office.com):</span><span class="sxs-lookup"><span data-stu-id="fb168-106">Automatic redirection is enabled by default for all users accessing the following compliance-related solutions in Office 365 Security and Compliance (protection.office.com):</span></span>

- <span data-ttu-id="fb168-107">Skydd mot dataförlust (DLP)</span><span class="sxs-lookup"><span data-stu-id="fb168-107">Data loss prevention (DLP)</span></span>
- <span data-ttu-id="fb168-108">Klassificering</span><span class="sxs-lookup"><span data-stu-id="fb168-108">Classification</span></span>
- <span data-ttu-id="fb168-109">Informationsstyrning</span><span class="sxs-lookup"><span data-stu-id="fb168-109">Information governance</span></span>
- <span data-ttu-id="fb168-110">Hantering av arkivhandlingar</span><span class="sxs-lookup"><span data-stu-id="fb168-110">Records management</span></span>
- <span data-ttu-id="fb168-111">Kommunikationsefterlevnad (tidigare "överlevnad")</span><span class="sxs-lookup"><span data-stu-id="fb168-111">Communication compliance (formerly 'Supervision')</span></span>

<span data-ttu-id="fb168-112">Användare dirigeras automatiskt till samma efterlevnadslösningar i kompatibilitetscentret för Microsoft 365 (compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="fb168-112">Users are automatically routed to the same compliance solutions in the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

>[!NOTE]
><span data-ttu-id="fb168-113">För andra efterlevnadslösningar som ingår i Säkerhets- och efterlevnadscenter för Office 365 fortsätter användarna att hantera lösningarna i antingen Microsoft 365-efterlevnadscentret eller Säkerhets- och efterlevnadscenter för Office 365- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="fb168-113">For other compliance solutions included in the Office 365 Security and Compliance Center, users will continue to manage these solutions in either the Microsoft 365 compliance center or the Office 365 Security and Compliance Center.</span></span> <span data-ttu-id="fb168-114">Den automatiska omdirigeringen för dessa efterlevnadslösningar kommer snart att bli tillgänglig.\*</span><span class="sxs-lookup"><span data-stu-id="fb168-114">The automatic redirection for these compliance solutions will be available soon.\*</span></span>

<span data-ttu-id="fb168-115">Den här funktionen och tillhörande kontroller aktiverar inte automatisk omdirigering av säkerhetsfunktioner för Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="fb168-115">This feature and associated controls does not enable the automatic redirection of Security features for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="fb168-116">Mer information om hur du aktiverar omdirigeringen av säkerhetsfunktionerna finns i Omdirigera konton från Microsoft Defender för [Office 365 till Microsoft 365 säkerhetscenter.](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection)</span><span class="sxs-lookup"><span data-stu-id="fb168-116">To enable the redirection for security features, see [Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) for details.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="fb168-117">Kan jag använda den tidigare portalen igen?</span><span class="sxs-lookup"><span data-stu-id="fb168-117">Can I go back to using the former portal?</span></span>

<span data-ttu-id="fb168-118">Om något inte fungerar för dig eller om det finns något som du inte kan slutföra via portalen för efterlevnadscenter för Microsoft 365 kan du tillfälligt inaktivera den automatiska omdirigeringen för alla användare.</span><span class="sxs-lookup"><span data-stu-id="fb168-118">If something isn't working for you or if there's anything you're unable to complete through the Microsoft 365 compliance center portal, you can temporarily disable the automatic redirection for all users.</span></span>

>[!IMPORTANT]
><span data-ttu-id="fb168-119">Efterlevnadscenter Microsoft 365 är en ersättningshanteringsportal för efterlevnadslösningar som för närvarande hanteras i Office 365 Säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="fb168-119">The Microsoft 365 compliance center is the replacement management portal for compliance solutions currently managed in the Office 365 Security and Compliance center.</span></span> <span data-ttu-id="fb168-120">Alla Microsoft 365-efterlevnadslösningar hanteras enbart i Microsoft 365 efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="fb168-120">All Microsoft 365 compliance solutions will be managed solely in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fb168-121">Att inaktivera omdirigering till Microsoft 365 efterlevnadscenter bör vara en kort lösning.\*</span><span class="sxs-lookup"><span data-stu-id="fb168-121">Disabling redirection to the Microsoft 365 compliance center should be a short-term solution.\*</span></span>

<span data-ttu-id="fb168-122">Om du vill gå Office 365 säkerhets- och efterlevnadscenter (protection.microsoft.com) för alla användare gör du följande:</span><span class="sxs-lookup"><span data-stu-id="fb168-122">To switch back to the Office 365 Security and Compliance center (protection.microsoft.com) for all users, complete the following steps:</span></span>

1. <span data-ttu-id="fb168-123">Logga in på [Microsoft 365 som global](https://compliance.microsoft.com) administratör eller använd ett konto med efterlevnadsadministratörsbehörigheter i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fb168-123">Sign in to the [Microsoft 365 compliance center](https://compliance.microsoft.com) as a global administrator or using any account with compliance administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="fb168-124">Gå till **Inställningar**  >  **omdirigering av efterlevnadscentret.**</span><span class="sxs-lookup"><span data-stu-id="fb168-124">Navigate to **Settings** > **Compliance center redirection**.</span></span>
3. <span data-ttu-id="fb168-125">Ändra inställningen för automatisk omdirigering till **Av**.</span><span class="sxs-lookup"><span data-stu-id="fb168-125">Toggle the Automatic redirection setting to **Off**.</span></span>
4. <span data-ttu-id="fb168-126">Välj **Inaktivera** och dela feedback när du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="fb168-126">Select **Disable** and share feedback when prompted.</span></span>

<span data-ttu-id="fb168-127">När den är inaktiverad dirigeras användarna inte längre till compliance.microsoft.com och de dirigeras Office 365 Säkerhets- och efterlevnadscenter (protection.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="fb168-127">Once disabled, users will no longer be routed to compliance.microsoft.com and they will be directed to the Office 365 Security and Compliance center (protection.microsoft.com).</span></span> <span data-ttu-id="fb168-128">Den här inställningen kan aktiveras igen när som helst av globala administratörer eller efterlevnadsadministratörer.</span><span class="sxs-lookup"><span data-stu-id="fb168-128">This setting can be enabled again at any time by Global or Compliance admins.</span></span>

## <a name="related-information"></a><span data-ttu-id="fb168-129">Relaterad information</span><span class="sxs-lookup"><span data-stu-id="fb168-129">Related information</span></span>

- [<span data-ttu-id="fb168-130">Microsoft 365 översikt över efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="fb168-130">Microsoft 365 compliance center overview</span></span>](/microsoft-365/compliance/microsoft-365-compliance-center)
