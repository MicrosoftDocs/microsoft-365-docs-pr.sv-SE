---
title: 'Steg 10: förenkla inloggning för användare'
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
description: Mer information om hur du förstår och konfigurerar enkel inloggning med Azure AD.
ms.openlocfilehash: 9d18cb559d3a4a9ee401e0f94fb53bc6360d88c8
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "42810030"
---
# <a name="step-10-simplify-user-sign-in"></a><span data-ttu-id="bce85-103">Steg 10: förenkla inloggning för användare</span><span class="sxs-lookup"><span data-stu-id="bce85-103">Step 10: Simplify user sign-in</span></span>

<span data-ttu-id="bce85-104">*Det här steget är valfritt för hybridversioner och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="bce85-104">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="bce85-105">I det här steget konfigurerar du enkel inloggning med Azure Active Directory (Azure AD Seamless SSO) så att användare kan logga in på tjänster som använder Azure AD-användarkonton utan att behöva ange lösenord, och i många fall användarnamn.</span><span class="sxs-lookup"><span data-stu-id="bce85-105">In this step, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="bce85-106">Det gör att användarna lättare kommer åt molnbaserade program, till exempel Office 365, utan att behöva några ytterligare lokala komponenter som identitetsservrar.</span><span class="sxs-lookup"><span data-stu-id="bce85-106">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="bce85-107">Du konfigurerar Azure AD Seamless SSO med Azure AD Connect-verktyget.</span><span class="sxs-lookup"><span data-stu-id="bce85-107">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="bce85-108">Se [anvisningarna för att konfigurera Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="bce85-108">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Testlabbsguider för Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="bce85-110">Testlabbsguide: enkel inloggning med Azure AD Seamless</span><span class="sxs-lookup"><span data-stu-id="bce85-110">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="bce85-111">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](identity-exit-criteria.md#crit-identity-sso) för detta steg.</span><span class="sxs-lookup"><span data-stu-id="bce85-111">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="bce85-112">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="bce85-112">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step11.png)| [<span data-ttu-id="bce85-113">Anpassa inloggningssidan för Office 365</span><span class="sxs-lookup"><span data-stu-id="bce85-113">Customize the Office 365 sign-in page</span></span>](identity-customize-office-365-sign-in.md) |

