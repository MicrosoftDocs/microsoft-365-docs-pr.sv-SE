---
title: Vanliga frågor och svar när du slår Microsoft 365 Defender
description: Få svar på de vanligaste frågorna om licensiering, behörigheter, initiala inställningar och andra produkter och tjänster som är relaterade till att aktivera Microsoft 365 Defender
keywords: Vanliga frågor, vanliga frågor, GCC, komma igång, aktivera Microsoft 365 Defender, Microsoft 365 Defender, M365, säkerhet, dataplats, obligatorisk behörighet, licensbehörighet, inställningssida
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 008e3cc6ee65597a032aa932b74a64ac591927f2
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572771"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="4cbb0-104">Vanliga frågor och svar när du slår Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4cbb0-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4cbb0-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="4cbb0-105">**Applies to:**</span></span>
- <span data-ttu-id="4cbb0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4cbb0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4cbb0-107">Läs svar på de vanligaste frågorna om hur du [slår på Microsoft 365 Defender](microsoft-365-defender.md), inklusive nödvändiga licenser och behörigheter, distribution av supporttjänster och inledande inställningar.</span><span class="sxs-lookup"><span data-stu-id="4cbb0-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-365-defender.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="4cbb0-108">Instruktioner om hur du aktiverar tjänsten finns i [Aktivera Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="4cbb0-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="4cbb0-109">Jag har inget Microsoft 365 E5 körkort.</span><span class="sxs-lookup"><span data-stu-id="4cbb0-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="4cbb0-110">Kan jag fortfarande använda Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="4cbb0-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="4cbb0-111">Kunder med följande icke-E5-licenser kan använda Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="4cbb0-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="4cbb0-112">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="4cbb0-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="4cbb0-113">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="4cbb0-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="4cbb0-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4cbb0-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="4cbb0-115">Försvarare för Office 365 (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="4cbb0-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="4cbb0-116">En fullständig lista över licenser som stöds [finns i licenskraven](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="4cbb0-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="4cbb0-117">Behöver jag installera eller distribuera något för att börja använda Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="4cbb0-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="4cbb0-118">Nej, Microsoft 365 Defender konsoliderar data från Microsoft 365 som du redan har distribuerat.</span><span class="sxs-lookup"><span data-stu-id="4cbb0-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="4cbb0-119">När du har aktiverat den kommer incident-, automatiserings- och jaktupplevelser att börja fungera inom ramen för de distribuerade produkterna.</span><span class="sxs-lookup"><span data-stu-id="4cbb0-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="4cbb0-120">Om ingen av dessa produkter distribueras korrekt Microsoft 365 Defender inga data och kan inte vidta några åtgärder.</span><span class="sxs-lookup"><span data-stu-id="4cbb0-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="4cbb0-121">För att optimera Microsoft 365 Defender-upplevelser rekommenderar vi att du *distribuerar alla* [Microsoft 365 som stöds av säkerhetsprodukter och säkerhetstjänster](deploy-supported-services.md).</span><span class="sxs-lookup"><span data-stu-id="4cbb0-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="4cbb0-122">Var bearbetar Microsoft 365 Defender och lagrar mina data?</span><span class="sxs-lookup"><span data-stu-id="4cbb0-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="4cbb0-123">Microsoft 365 Defender väljer automatiskt en optimal plats för det datacenter där konsoliderade data bearbetas och lagras.</span><span class="sxs-lookup"><span data-stu-id="4cbb0-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="4cbb0-124">Om du har Microsoft Defender för slutpunkt väljer den samma plats som Används av Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="4cbb0-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="4cbb0-125">Microsoft Defender for Endpoint-bestämmelser i EU-datacenter (EU) när de aktiveras via Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="4cbb0-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="4cbb0-126">Microsoft 365 Defender etablerar automatiskt i samma EU-datacenter för kunder som har etablerat Microsoft Defender för Slutpunkt på detta sätt.</span><span class="sxs-lookup"><span data-stu-id="4cbb0-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="4cbb0-127">Datacenterplatsen visas före och efter att tjänsten har etablerats på inställningssidan för Microsoft 365 Defender (**Inställningar > Microsoft 365 Defender**).</span><span class="sxs-lookup"><span data-stu-id="4cbb0-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender (**Settings > Microsoft 365 Defender**).</span></span> <span data-ttu-id="4cbb0-128">Om du föredrar att använda en annan datacenterplats väljer du Behöver **du hjälp i** Microsoft 365 säkerhetscenter för att kontakta Microsoft-supporten.</span><span class="sxs-lookup"><span data-stu-id="4cbb0-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="4cbb0-129">Var kommer jag åt Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="4cbb0-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="4cbb0-130">Microsoft 365 Defender finns i Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="4cbb0-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="4cbb0-131">Om du vill gå till säkerhetscentret bläddrar du till URL:en [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="4cbb0-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="4cbb0-132">Vilka behörigheter behöver jag för att komma Microsoft 365 Defender Microsoft 365 säkerhetscenter?</span><span class="sxs-lookup"><span data-stu-id="4cbb0-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="4cbb0-133">Konton som tilldelats följande Azure Active Directory (Azure AD) kan komma åt Microsoft 365 Defender-funktioner och -data:</span><span class="sxs-lookup"><span data-stu-id="4cbb0-133">Accounts assigned the following Azure Active Directory (Azure AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="4cbb0-134">Global administratör</span><span class="sxs-lookup"><span data-stu-id="4cbb0-134">Global administrator</span></span>
- <span data-ttu-id="4cbb0-135">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="4cbb0-135">Security administrator</span></span>
- <span data-ttu-id="4cbb0-136">Säkerhetsoperatör</span><span class="sxs-lookup"><span data-stu-id="4cbb0-136">Security Operator</span></span>
- <span data-ttu-id="4cbb0-137">Global läsare</span><span class="sxs-lookup"><span data-stu-id="4cbb0-137">Global Reader</span></span>
- <span data-ttu-id="4cbb0-138">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="4cbb0-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="4cbb0-139">Rollbaserade åtkomstkontrollinställningar i Microsoft Defender för slutpunkt påverkar åtkomsten till data.</span><span class="sxs-lookup"><span data-stu-id="4cbb0-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="4cbb0-140">Mer information finns i om hur [du hanterar åtkomst Microsoft 365 Defender](m365d-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="4cbb0-140">For more information, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="4cbb0-141">Vilken tidszon Microsoft 365 Defender som standard?</span><span class="sxs-lookup"><span data-stu-id="4cbb0-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="4cbb0-142">Som standard visar Microsoft 365 Defender tidsinformation i UTC-tidszonen.</span><span class="sxs-lookup"><span data-stu-id="4cbb0-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="4cbb0-143">Du kan ändra den här inställningen så att den använder din lokala tidszon.</span><span class="sxs-lookup"><span data-stu-id="4cbb0-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="4cbb0-144">Lär dig mer om hur du ställer in tidszonen</span><span class="sxs-lookup"><span data-stu-id="4cbb0-144">Learn about setting the time zone</span></span>](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="4cbb0-145">Hur kan jag lära mig mer om Microsoft 365 Defender-funktionen och uppdateringar av användargränssnittet?</span><span class="sxs-lookup"><span data-stu-id="4cbb0-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="4cbb0-146">Microsoft tillhandahåller regelbundet information via de olika kanalerna, inklusive:</span><span class="sxs-lookup"><span data-stu-id="4cbb0-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="4cbb0-147">Meddelandecentret [i](../../admin/manage/message-center.md) Microsoft 365 administrationscenter</span><span class="sxs-lookup"><span data-stu-id="4cbb0-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="4cbb0-148">Blogginlägg i Microsoft 365 [säkerhets& teknikgemenskap för regelefterlevnad](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="4cbb0-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="4cbb0-149">Få de senaste offentligt tillgängliga upplevelserna genom att aktivera [förhandsgranskningsfunktioner](preview.md).</span><span class="sxs-lookup"><span data-stu-id="4cbb0-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="4cbb0-150">Är Microsoft 365 Defender tillgängligt för US Government Community Cloud (GCC) eller GCC High?</span><span class="sxs-lookup"><span data-stu-id="4cbb0-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="4cbb0-151">För närvarande är det inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="4cbb0-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4cbb0-152">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="4cbb0-152">Related topics</span></span>

- [<span data-ttu-id="4cbb0-153">Microsoft 365 Översikt över Defender</span><span class="sxs-lookup"><span data-stu-id="4cbb0-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- <span data-ttu-id="4cbb0-154">[Aktivera Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="4cbb0-154">[Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>
- [<span data-ttu-id="4cbb0-155">Licenskrav och andra förutsättningar</span><span class="sxs-lookup"><span data-stu-id="4cbb0-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="4cbb0-156">Distribuera tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="4cbb0-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="4cbb0-157">Aktivera förhandsgranskningsfunktioner</span><span class="sxs-lookup"><span data-stu-id="4cbb0-157">Turn on preview features</span></span>](preview.md)
