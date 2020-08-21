---
title: Vanliga frågor och svar om delegerad administration
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: Det här avsnittet innehåller vanliga frågor och svar om Microsoft-partners och åter försäljare som vill utföra delegerade Microsoft 365-administrations uppgifter.
ms.openlocfilehash: 01781437bbc7e8fe5c035ea23e4392e734e0231f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827093"
---
# <a name="delegated-administration-faq"></a><span data-ttu-id="26f54-103">Vanliga frågor och svar om delegerad administration</span><span class="sxs-lookup"><span data-stu-id="26f54-103">Delegated administration FAQ</span></span>

<span data-ttu-id="26f54-104">Det här avsnittet innehåller vanliga frågor och svar om Microsoft-partners och åter försäljare som vill utföra delegerade administrativa uppgifter, inklusive möjligheten att hantera Exchange Online Protection (EOP) för andra klient organisationer.</span><span class="sxs-lookup"><span data-stu-id="26f54-104">This topic provides frequently asked questions and answers for Microsoft partners and resellers who want to perform delegated administration tasks, including the ability to manage Exchange Online Protection (EOP) for other tenants (companies).</span></span>

## <a name="im-a-reseller-and-i-need-to-manage-my-customers-tenants-how-does-this-work"></a><span data-ttu-id="26f54-105">Jag är åter försäljare och måste hantera min kunds innehavare; Hur fungerar detta?</span><span class="sxs-lookup"><span data-stu-id="26f54-105">I'm a reseller and I need to manage my customer's tenants; how does this work?</span></span>

<span data-ttu-id="26f54-106">Om du är Microsoft-partner eller åter försäljare och har registrerat dig för att vara Microsoft Advisor kan du begära tillstånd att administrera klient organisationen i administrations centret.</span><span class="sxs-lookup"><span data-stu-id="26f54-106">If you are a Microsoft partner or reseller, and you've signed up to be a Microsoft advisor, you can request permission to administer their tenant within the admin center.</span></span> <span data-ttu-id="26f54-107">Detta kallas delegerad administration och gör att du kan hantera sin Microsoft 365-klient organisation (inklusive EOP-inställningar) som om du vore administratör inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="26f54-107">This is known as delegated administration, and it allows you to manage their Microsoft 365 tenant (including EOP settings) as if you were an administrator within their organization.</span></span> <span data-ttu-id="26f54-108">Så här gör du för att utföra delegerad administration:</span><span class="sxs-lookup"><span data-stu-id="26f54-108">The steps for performing delegated administration are as follows:</span></span>

1. <span data-ttu-id="26f54-109">Registrera dig som [Microsoft Office 365-rådgivare](https://aka.ms/cloudbenefits).</span><span class="sxs-lookup"><span data-stu-id="26f54-109">Sign up to be a [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits).</span></span>

2. <span data-ttu-id="26f54-110">Registrera dig för delegerad administration.</span><span class="sxs-lookup"><span data-stu-id="26f54-110">Sign up for delegated administration.</span></span> <span data-ttu-id="26f54-111">Innan du kan börja administrera en kunds konto måste de ge dig administratörs behörighet.</span><span class="sxs-lookup"><span data-stu-id="26f54-111">Before you can start administering a customer's account, they must authorize you as a delegated administrator.</span></span> <span data-ttu-id="26f54-112">För att få sitt godkännande, [Skicka först dem ett anbud för delegerad administration](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e).</span><span class="sxs-lookup"><span data-stu-id="26f54-112">To obtain their approval, you first [send them an offer for delegated administration](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e).</span></span> <span data-ttu-id="26f54-113">(Du kan även ge din kund delegerad administration vid ett senare tillfälle.)</span><span class="sxs-lookup"><span data-stu-id="26f54-113">(You can also offer delegated administration to your customer at a later time.)</span></span>

3. <span data-ttu-id="26f54-114">Skapa det delegerade administratörs kontot enligt anvisningarna i [lägga till, ändra eller ta bort en abonnemangs rådgivare](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).</span><span class="sxs-lookup"><span data-stu-id="26f54-114">Create the delegated admin account using the steps in [Add, change, or delete a subscription advisor partner](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).</span></span>

<span data-ttu-id="26f54-115">Besök [partners: skapa en prenumeration på ditt företag och administrera partner](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) för mer information om hur du konfigurerar delegerad administration.</span><span class="sxs-lookup"><span data-stu-id="26f54-115">Visit [Partners: Build your business and administer partner subscription](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) for more information about how to set up delegated administration.</span></span>

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-sub-tenants"></a><span data-ttu-id="26f54-116">Jag är kund och inte en åter försäljare, hur kan konfigurera den delegerade administratören för mina under klienter?</span><span class="sxs-lookup"><span data-stu-id="26f54-116">I'm a customer, not a reseller, how can set up delegated administrator for my sub-tenants?</span></span>

<span data-ttu-id="26f54-117">Delegerad administration är bara tillgänglig för åter försäljare och partner för närvarande.</span><span class="sxs-lookup"><span data-stu-id="26f54-117">Delegated administration is only available for resellers and partners at this time.</span></span> <span data-ttu-id="26f54-118">Vi har ett exempel på ett Windows PowerShell-skript som hjälper dig att tillämpa principer på dina under klienter (företag).</span><span class="sxs-lookup"><span data-stu-id="26f54-118">However, we've provided a sample Windows PowerShell script that will help you apply policies to your sub-tenants (companies).</span></span> <span data-ttu-id="26f54-119">Mer information finns i [exempel skript för att tillämpa EOP-inställningar på flera klient organisationer](sample-script-for-applying-eop-settings-to-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="26f54-119">For more information, see [Sample script for applying EOP settings to multiple tenants](sample-script-for-applying-eop-settings-to-multiple-tenants.md).</span></span>

## <a name="can-i-prevent-my-sub-tenant-admin-from-modifying-my-policy"></a><span data-ttu-id="26f54-120">Kan jag förhindra att min princip ändras med administratör för under administratören?</span><span class="sxs-lookup"><span data-stu-id="26f54-120">Can I prevent my sub-tenant admin from modifying my policy?</span></span>

<span data-ttu-id="26f54-121">Microsoft 365 har för närvarande inte den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="26f54-121">Microsoft 365 does not currently have this capability.</span></span>

## <a name="can-i-get-consolidated-reporting-across-all-of-my-sub-tenants"></a><span data-ttu-id="26f54-122">Kan jag få konsol IDE rad rapportering i alla mina under klienter?</span><span class="sxs-lookup"><span data-stu-id="26f54-122">Can I get consolidated reporting across all of my sub-tenants?</span></span>

<span data-ttu-id="26f54-123">Konsol IDE rad rapportering över de företag som du hanterar är inte tillgängligt för Microsoft 365 Admin Center-rapporter just nu.</span><span class="sxs-lookup"><span data-stu-id="26f54-123">Consolidated reporting across the companies you manage is not available for the Microsoft 365 admin center reports at this time.</span></span> <span data-ttu-id="26f54-124">Det kan du göra genom att använda [Microsoft Graph](https://docs.microsoft.com/graph/overview).</span><span class="sxs-lookup"><span data-stu-id="26f54-124">However, you can do this by using [Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>
