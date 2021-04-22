---
title: Vanliga frågor och svar när du slår på Microsoft 365 Defender
description: Få svar på de vanligaste frågorna om licensiering, behörigheter, initiala inställningar och andra produkter och tjänster relaterade till att aktivera Microsoft 365 Defender
keywords: Vanliga frågor och svar, vanliga frågor och svar, GCC, kom igång, aktivera Microsoft 365 Defender, Microsoft 365 Defender, M365, säkerhet, dataplats, nödvändiga behörigheter, licensberättigande, inställningssidan
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
ms.openlocfilehash: 55c1a3807fe8e28ca12f4f638c1ab2ca717523ed
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933439"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="88e8b-104">Vanliga frågor och svar när du slår på Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="88e8b-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="88e8b-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="88e8b-105">**Applies to:**</span></span>
- <span data-ttu-id="88e8b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="88e8b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="88e8b-107">Läs svaren på de vanligaste frågorna om att aktivera [Microsoft 365 Defender](microsoft-365-defender.md), inklusive obligatoriska licenser och behörigheter, distribuera supporttjänster och initiala inställningar.</span><span class="sxs-lookup"><span data-stu-id="88e8b-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-365-defender.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="88e8b-108">Anvisningar om hur du aktiverar tjänsten finns i [Aktivera Microsoft 365 Defender.](m365d-enable.md)</span><span class="sxs-lookup"><span data-stu-id="88e8b-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="88e8b-109">Jag har ingen Microsoft 365 E5-licens.</span><span class="sxs-lookup"><span data-stu-id="88e8b-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="88e8b-110">Kan jag ändå använda Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="88e8b-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="88e8b-111">Kunder med följande icke-E5-licenser kan använda Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="88e8b-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="88e8b-112">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="88e8b-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="88e8b-113">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="88e8b-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="88e8b-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="88e8b-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="88e8b-115">Defender för Office 365 (abonnemang 2)</span><span class="sxs-lookup"><span data-stu-id="88e8b-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="88e8b-116">En fullständig lista över licenser som stöds [finns i licenskraven.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="88e8b-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="88e8b-117">Behöver jag installera eller distribuera något för att börja använda Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="88e8b-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="88e8b-118">Nej, Microsoft 365 Defender konsoliderar data från Microsoft 365-säkerhetstjänster som du redan har distribuerat.</span><span class="sxs-lookup"><span data-stu-id="88e8b-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="88e8b-119">När du aktiverar den börjar incident-, automatiserings- och licenshanteringen fungera inom omfattningen för de distribuerade produkterna.</span><span class="sxs-lookup"><span data-stu-id="88e8b-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="88e8b-120">Om ingen av dessa produkter har distribuerats korrekt visas inga data i Microsoft 365 Defender och det går inte att vidta någon åtgärd.</span><span class="sxs-lookup"><span data-stu-id="88e8b-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="88e8b-121">Om du vill optimera dina Microsoft 365 Defender-upplevelser rekommenderar vi att du distribuerar alla säkerhetsprodukter och tjänster som [stöds av Microsoft 365.](deploy-supported-services.md) </span><span class="sxs-lookup"><span data-stu-id="88e8b-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="88e8b-122">Var bearbetas och lagras mina data i Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="88e8b-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="88e8b-123">Microsoft 365 Defender väljer automatiskt en optimal plats för det datacenter där konsoliderade data bearbetas och lagras.</span><span class="sxs-lookup"><span data-stu-id="88e8b-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="88e8b-124">Om du har Microsoft Defender för slutpunkt markeras samma plats som används av Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="88e8b-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="88e8b-125">Microsoft Defender för Slutpunkt tillhandahåller automatiskt datacenter i Europeiska unionen (EU) när det aktiveras via Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="88e8b-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="88e8b-126">Microsoft 365 Defender etablerar automatiskt i samma datacenter i EU för kunder som har etablerat Microsoft Defender för Endpoint på det här sättet.</span><span class="sxs-lookup"><span data-stu-id="88e8b-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="88e8b-127">Platsen för datacenter visas före och efter att tjänsten har etablerats på inställningssidan för Microsoft 365 Defender (inställningar **> Microsoft 365 Defender).**</span><span class="sxs-lookup"><span data-stu-id="88e8b-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender (**Settings > Microsoft 365 Defender**).</span></span> <span data-ttu-id="88e8b-128">Om du föredrar att använda en annan datacenterplats väljer du Behöver du **hjälp?** i säkerhetscentret i Microsoft 365 för att kontakta Microsofts support.</span><span class="sxs-lookup"><span data-stu-id="88e8b-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="88e8b-129">Var kan jag komma åt Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="88e8b-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="88e8b-130">Microsoft 365 Defender är tillgängligt i Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="88e8b-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="88e8b-131">Gå till säkerhetscentret genom att bläddra till URL:en [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="88e8b-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="88e8b-132">Vilka behörigheter behöver jag för att få tillgång till Microsoft 365 Defender i Microsoft 365 Säkerhetscenter?</span><span class="sxs-lookup"><span data-stu-id="88e8b-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="88e8b-133">Konton som tilldelats följande Azure Active Directory-roller (AD) kan komma åt funktioner och data i Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="88e8b-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="88e8b-134">Global administratör</span><span class="sxs-lookup"><span data-stu-id="88e8b-134">Global administrator</span></span>
- <span data-ttu-id="88e8b-135">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="88e8b-135">Security administrator</span></span>
- <span data-ttu-id="88e8b-136">Säkerhetsoperatör</span><span class="sxs-lookup"><span data-stu-id="88e8b-136">Security Operator</span></span>
- <span data-ttu-id="88e8b-137">Global läsare</span><span class="sxs-lookup"><span data-stu-id="88e8b-137">Global Reader</span></span>
- <span data-ttu-id="88e8b-138">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="88e8b-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="88e8b-139">Rollbaserade inställningar för åtkomstkontroll i Microsoft Defender för Slutpunkt påverkar åtkomsten till data.</span><span class="sxs-lookup"><span data-stu-id="88e8b-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="88e8b-140">Mer information finns i hantera [åtkomst till Microsoft 365 Defender.](m365d-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="88e8b-140">For more information, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="88e8b-141">Vilken tidszon används som standard i Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="88e8b-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="88e8b-142">Som standard visas tidsinformation i UTC-tidszonen i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="88e8b-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="88e8b-143">Du kan ändra den här inställningen om du vill använda din lokala tidszon.</span><span class="sxs-lookup"><span data-stu-id="88e8b-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="88e8b-144">Läs mer om hur du ställer in tidszon</span><span class="sxs-lookup"><span data-stu-id="88e8b-144">Learn about setting the time zone</span></span>](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="88e8b-145">Hur får jag veta mer om nya funktioner och uppdateringar av användargränssnittet i Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="88e8b-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="88e8b-146">Microsoft tillhandahåller regelbundet information genom de olika kanalerna, inklusive:</span><span class="sxs-lookup"><span data-stu-id="88e8b-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="88e8b-147">Meddelandecenter [i](../../admin/manage/message-center.md) administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="88e8b-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="88e8b-148">Blogginlägg i den tekniska [communityn för Säkerhet & Microsoft 365](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="88e8b-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="88e8b-149">Få de senaste offentligt tillgängliga funktionerna genom att aktivera [förhandsgranskningsfunktioner.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="88e8b-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="88e8b-150">Är Microsoft 365 Defender tillgänglig för amerikanska Government Community Cloud (GCC) eller GCC High?</span><span class="sxs-lookup"><span data-stu-id="88e8b-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="88e8b-151">För tillfället är den inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="88e8b-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="88e8b-152">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="88e8b-152">Related topics</span></span>

- [<span data-ttu-id="88e8b-153">Översikt över Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="88e8b-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- <span data-ttu-id="88e8b-154">[Aktivera Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="88e8b-154">[Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>
- [<span data-ttu-id="88e8b-155">Licenskrav och andra krav</span><span class="sxs-lookup"><span data-stu-id="88e8b-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="88e8b-156">Distribuera tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="88e8b-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="88e8b-157">Aktivera förhandsgranskningsfunktioner</span><span class="sxs-lookup"><span data-stu-id="88e8b-157">Turn on preview features</span></span>](preview.md)
