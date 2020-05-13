---
title: Vanliga frågor och svar om delegerad administration
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: Det här avsnittet innehåller vanliga frågor och svar för Microsoft-partner och återförsäljare som vill utföra delegerade Microsoft 365-administrationsuppgifter.
ms.openlocfilehash: d1522973292b290fd9f66f534ca23aeaa55ee756
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209529"
---
# <a name="delegated-administration-faq"></a><span data-ttu-id="88202-103">Vanliga frågor och svar om delegerad administration</span><span class="sxs-lookup"><span data-stu-id="88202-103">Delegated administration FAQ</span></span>

<span data-ttu-id="88202-104">Det här avsnittet innehåller vanliga frågor och svar för Microsoft-partner och återförsäljare som vill utföra delegerade administrationsuppgifter, inklusive möjligheten att hantera Exchange Online Protection (EOP) för andra klienter (företag).</span><span class="sxs-lookup"><span data-stu-id="88202-104">This topic provides frequently asked questions and answers for Microsoft partners and resellers who want to perform delegated administration tasks, including the ability to manage Exchange Online Protection (EOP) for other tenants (companies).</span></span>

## <a name="im-a-reseller-and-i-need-to-manage-my-customers-tenants-how-does-this-work"></a><span data-ttu-id="88202-105">Jag är återförsäljare och jag måste hantera mina kunders hyresgäster; Hur fungerar detta?</span><span class="sxs-lookup"><span data-stu-id="88202-105">I'm a reseller and I need to manage my customer's tenants; how does this work?</span></span>

<span data-ttu-id="88202-106">Om du är en Microsoft-partner eller återförsäljare och har registrerat dig för att vara Microsoft-rådgivare kan du begära tillstånd att administrera deras klientorganisation i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="88202-106">If you are a Microsoft partner or reseller, and you've signed up to be a Microsoft advisor, you can request permission to administer their tenant within the admin center.</span></span> <span data-ttu-id="88202-107">Detta kallas delegerad administration och gör att du kan hantera deras Microsoft 365-klientorganisation (inklusive EOP-inställningar) som om du var administratör inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="88202-107">This is known as delegated administration, and it allows you to manage their Microsoft 365 tenant (including EOP settings) as if you were an administrator within their organization.</span></span> <span data-ttu-id="88202-108">Stegen för att utföra delegerad administration är följande:</span><span class="sxs-lookup"><span data-stu-id="88202-108">The steps for performing delegated administration are as follows:</span></span>

1. <span data-ttu-id="88202-109">Registrera dig för att bli microsoft [office 365 Advisor](https://aka.ms/cloudbenefits).</span><span class="sxs-lookup"><span data-stu-id="88202-109">Sign up to be a [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits).</span></span>

2. <span data-ttu-id="88202-110">Registrera dig för delegerad administration.</span><span class="sxs-lookup"><span data-stu-id="88202-110">Sign up for delegated administration.</span></span> <span data-ttu-id="88202-111">Innan du kan börja administrera en kunds konto måste de auktorisera dig som delegerad administratör.</span><span class="sxs-lookup"><span data-stu-id="88202-111">Before you can start administering a customer's account, they must authorize you as a delegated administrator.</span></span> <span data-ttu-id="88202-112">För att få deras godkännande skickar du dem först [ett erbjudande om delegerad administration](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e).</span><span class="sxs-lookup"><span data-stu-id="88202-112">To obtain their approval, you first [send them an offer for delegated administration](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e).</span></span> <span data-ttu-id="88202-113">(Du kan också erbjuda delegerad administration till kunden vid ett senare tillfälle.)</span><span class="sxs-lookup"><span data-stu-id="88202-113">(You can also offer delegated administration to your customer at a later time.)</span></span>

3. <span data-ttu-id="88202-114">Skapa det delegerade administratörskontot med hjälp av stegen i [Lägg till, ändra eller ta bort en partner för prenumerationsrådgivare](https://docs.microsoft.com/office365/admin/misc/add-partner).</span><span class="sxs-lookup"><span data-stu-id="88202-114">Create the delegated admin account using the steps in [Add, change, or delete a subscription advisor partner](https://docs.microsoft.com/office365/admin/misc/add-partner).</span></span>

<span data-ttu-id="88202-115">Besök [Partners: Skapa din företagsprenumeration och administrera partnerprenumerationen](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319) för mer information om hur du konfigurerar delegerad administration.</span><span class="sxs-lookup"><span data-stu-id="88202-115">Visit [Partners: Build your business and administer partner subscription](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319) for more information about how to set up delegated administration.</span></span>

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-sub-tenants"></a><span data-ttu-id="88202-116">Jag är kund, inte återförsäljare, hur kan konfigurera delegerad administratör för mina underhyresgäster?</span><span class="sxs-lookup"><span data-stu-id="88202-116">I'm a customer, not a reseller, how can set up delegated administrator for my sub-tenants?</span></span>

<span data-ttu-id="88202-117">Delegerad administration är för närvarande endast tillgänglig för återförsäljare och partner.</span><span class="sxs-lookup"><span data-stu-id="88202-117">Delegated administration is only available for resellers and partners at this time.</span></span> <span data-ttu-id="88202-118">Vi har dock tillhandahållit ett exempel på Windows PowerShell-skript som hjälper dig att tillämpa principer på dina underhyresgäster (företag).</span><span class="sxs-lookup"><span data-stu-id="88202-118">However, we've provided a sample Windows PowerShell script that will help you apply policies to your sub-tenants (companies).</span></span> <span data-ttu-id="88202-119">Mer information finns i [Exempelskript för att tillämpa EOP-inställningar på flera klienter](sample-script-for-applying-eop-settings-to-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="88202-119">For more information, see [Sample script for applying EOP settings to multiple tenants](sample-script-for-applying-eop-settings-to-multiple-tenants.md).</span></span>

## <a name="can-i-prevent-my-sub-tenant-admin-from-modifying-my-policy"></a><span data-ttu-id="88202-120">Kan jag hindra min administratör för underinnehavare från att ändra min princip?</span><span class="sxs-lookup"><span data-stu-id="88202-120">Can I prevent my sub-tenant admin from modifying my policy?</span></span>

<span data-ttu-id="88202-121">Microsoft 365 har för närvarande inte den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="88202-121">Microsoft 365 does not currently have this capability.</span></span>

## <a name="can-i-get-consolidated-reporting-across-all-of-my-sub-tenants"></a><span data-ttu-id="88202-122">Kan jag få konsoliderad rapportering över alla mina underhyresgäster?</span><span class="sxs-lookup"><span data-stu-id="88202-122">Can I get consolidated reporting across all of my sub-tenants?</span></span>

<span data-ttu-id="88202-123">Konsoliderad rapportering för de företag du hanterar är inte tillgänglig för Microsoft 365 admincenterrapporter för tillfället.</span><span class="sxs-lookup"><span data-stu-id="88202-123">Consolidated reporting across the companies you manage is not available for the Microsoft 365 admin center reports at this time.</span></span> <span data-ttu-id="88202-124">Du kan dock göra detta med hjälp av [Microsoft Graph](https://docs.microsoft.com/graph/overview).</span><span class="sxs-lookup"><span data-stu-id="88202-124">However, you can do this by using [Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>
