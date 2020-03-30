---
title: 'Steg 13: Övervaka klientorganisationen och inloggningsaktivitet'
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
description: Förstå och konfigurera rapportering av Azure AD-åtkomst och användning.
ms.openlocfilehash: 997d52bc11036e1dbb7dcc6e1f9f48a59b2ddbf5
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "42806440"
---
# <a name="step-13-monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="9aaf6-103">Steg 13: Övervaka klientorganisationen och inloggningsaktivitet</span><span class="sxs-lookup"><span data-stu-id="9aaf6-103">Step 13: Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="9aaf6-104">*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="9aaf6-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="9aaf6-105">I det här steget ska du granska granskningsloggar och inloggningsaktivitet med hjälp av Azure AD-rapportering.</span><span class="sxs-lookup"><span data-stu-id="9aaf6-105">In this step, you'll review audit logs and sign-in activity using Azure AD reporting.</span></span> <span data-ttu-id="9aaf6-106">Det finns två typer av rapporter.</span><span class="sxs-lookup"><span data-stu-id="9aaf6-106">Two types of reports are available.</span></span>

<span data-ttu-id="9aaf6-107">I **aktivitetsrapporten för granskningsloggar** registreras historiken för varje aktivitet som utförs i Azure AD-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="9aaf6-107">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant.</span></span> <span data-ttu-id="9aaf6-108">Den här rapporten besvarar frågor som:</span><span class="sxs-lookup"><span data-stu-id="9aaf6-108">This report answers questions like:</span></span>

- <span data-ttu-id="9aaf6-109">Vem har lagt till någon i en administratörsgrupp?</span><span class="sxs-lookup"><span data-stu-id="9aaf6-109">Who added someone to an admin group?</span></span>
- <span data-ttu-id="9aaf6-110">Vilka användare är inloggade på en specifik app?</span><span class="sxs-lookup"><span data-stu-id="9aaf6-110">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="9aaf6-111">Hur många återställningar av lösenord görs?</span><span class="sxs-lookup"><span data-stu-id="9aaf6-111">How many password resets are happening?</span></span>

<span data-ttu-id="9aaf6-112">I **rapporten för inloggningsaktivitet** registreras vem som utförde de aktiviteter som rapporterades i granskningsloggrapporten.</span><span class="sxs-lookup"><span data-stu-id="9aaf6-112">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report.</span></span> <span data-ttu-id="9aaf6-113">Den här rapporten besvarar frågor som:</span><span class="sxs-lookup"><span data-stu-id="9aaf6-113">This report answers questions like:</span></span>

- <span data-ttu-id="9aaf6-114">Vilket inloggningsmönster har en specifik användare som undersöks?</span><span class="sxs-lookup"><span data-stu-id="9aaf6-114">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="9aaf6-115">Hur många inloggningar har jag under en dag, vecka eller månad?</span><span class="sxs-lookup"><span data-stu-id="9aaf6-115">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="9aaf6-116">Hur många av de här inloggningarna misslyckades och för vilka konton?</span><span class="sxs-lookup"><span data-stu-id="9aaf6-116">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="9aaf6-117">Mer information om rapporterna och hur du kommer åt dem finns i [Azure Active Directory-rapportering](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="9aaf6-117">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="9aaf6-118">I det här steget får veta mer om rapporterna och du förstår hur du kan använda dem för att få insikter om Azure AD-händelser och aktiviteter för planering och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="9aaf6-118">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>

## <a name="next-step"></a><span data-ttu-id="9aaf6-119">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="9aaf6-119">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step14.png)| [<span data-ttu-id="9aaf6-120">Tillåta att användare skapar och hanterar egna grupper</span><span class="sxs-lookup"><span data-stu-id="9aaf6-120">Allow users to create and manage their own groups</span></span>](identity-self-service-group-management.md) |
