---
title: Vanliga frågor och svar om att aktivera Microsoft 365 Defender
description: Få svar på de vanligaste frågorna om licensiering, behörigheter, inledande inställningar och andra produkter och tjänster relaterade till att aktivera Microsoft 365 Defender
keywords: vanliga frågor och svar, vanliga frågor och svar, GCC, komma igång, aktivera MTP, Microsoft Threat Protection, M365, säkerhet, dataplats, nödvändiga behörigheter, licensberättigande, inställningssidan
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2cb9aed070959644e3660188835386118d5f4d9b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930192"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="f3370-104">Vanliga frågor och svar när du slår på Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3370-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f3370-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f3370-105">**Applies to:**</span></span>
- <span data-ttu-id="f3370-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3370-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f3370-107">Läs svaren på de vanligaste frågorna om att aktivera [Microsoft 365 Defender,](microsoft-threat-protection.md)inklusive obligatoriska licenser och behörigheter, distribution av supporttjänster och initiala inställningar.</span><span class="sxs-lookup"><span data-stu-id="f3370-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="f3370-108">Anvisningar om hur du aktiverar tjänsten finns i [Aktivera Microsoft 365 Defender.](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="f3370-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="f3370-109">Jag har ingen Microsoft 365 E5-licens.</span><span class="sxs-lookup"><span data-stu-id="f3370-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="f3370-110">Kan jag ändå använda Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="f3370-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="f3370-111">Kunder med följande icke-E5-licenser kan använda Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="f3370-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="f3370-112">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f3370-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="f3370-113">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="f3370-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="f3370-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f3370-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="f3370-115">Defender för Office 365 (abonnemang 2)</span><span class="sxs-lookup"><span data-stu-id="f3370-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="f3370-116">En fullständig lista över licenser som stöds [finns i licenskraven.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="f3370-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="f3370-117">Behöver jag installera eller distribuera något för att börja använda Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="f3370-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="f3370-118">Nej, Microsoft 365 Defender konsoliderar data från Microsoft 365-säkerhetstjänster som du redan har distribuerat.</span><span class="sxs-lookup"><span data-stu-id="f3370-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="f3370-119">När du aktiverar den börjar incident- och automatiserings- och fiskeupplevelserna fungera inom de distribuerade produkterna.</span><span class="sxs-lookup"><span data-stu-id="f3370-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="f3370-120">Om ingen av dessa produkter distribueras korrekt visas inga data i Microsoft 365 Defender och det går inte att vidta någon åtgärd.</span><span class="sxs-lookup"><span data-stu-id="f3370-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="f3370-121">Om du vill optimera dina Microsoft 365 Defender-upplevelser rekommenderar vi att du distribuerar alla säkerhetsprodukter och tjänster som stöds [av Microsoft 365.](deploy-supported-services.md) </span><span class="sxs-lookup"><span data-stu-id="f3370-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="f3370-122">Var bearbetar och lagrar Microsoft 365 Defender mina data?</span><span class="sxs-lookup"><span data-stu-id="f3370-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="f3370-123">Microsoft 365 Defender väljer automatiskt en optimal plats för det datacenter där konsoliderade data bearbetas och lagras.</span><span class="sxs-lookup"><span data-stu-id="f3370-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="f3370-124">Om du har Microsoft Defender för slutpunkten markeras samma plats som används av Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="f3370-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="f3370-125">Microsoft Defender för Slutpunkt tillhandahåller automatiskt datacenter i Europeiska unionen (EU) när det aktiveras via Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="f3370-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="f3370-126">Microsoft 365 Defender etablerar automatiskt i samma DATACENTER i EU för kunder som har etablerat Microsoft Defender för Slutpunkt på det här sättet.</span><span class="sxs-lookup"><span data-stu-id="f3370-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="f3370-127">Datacenterplatsen visas före och efter att tjänsten har etablerats på inställningssidan för Microsoft 365 Defender (inställningar **> Microsoft 365 Defender).**</span><span class="sxs-lookup"><span data-stu-id="f3370-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender (**Settings > Microsoft 365 Defender**).</span></span> <span data-ttu-id="f3370-128">Om du föredrar att använda en annan datacenterplats väljer du Behöver du **hjälp?** I säkerhetscentret i Microsoft 365 kontaktar du Microsoft Support.</span><span class="sxs-lookup"><span data-stu-id="f3370-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="f3370-129">Var får jag tillgång till Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="f3370-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="f3370-130">Microsoft 365 Defender är tillgängligt i Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="f3370-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="f3370-131">Gå till säkerhetscentret genom att bläddra till [https://security.microsoft.com](https://security.microsoft.com) URL:en.</span><span class="sxs-lookup"><span data-stu-id="f3370-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="f3370-132">Vilka behörigheter behöver jag för att få åtkomst till Microsoft 365 Defender i Microsoft 365 Säkerhetscenter?</span><span class="sxs-lookup"><span data-stu-id="f3370-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="f3370-133">Konton som tilldelats följande Azure Active Directory-roller (AD) har åtkomst till funktioner och data i Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="f3370-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="f3370-134">Global administratör</span><span class="sxs-lookup"><span data-stu-id="f3370-134">Global administrator</span></span>
- <span data-ttu-id="f3370-135">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="f3370-135">Security administrator</span></span>
- <span data-ttu-id="f3370-136">Säkerhetsoperatör</span><span class="sxs-lookup"><span data-stu-id="f3370-136">Security Operator</span></span>
- <span data-ttu-id="f3370-137">Global läsare</span><span class="sxs-lookup"><span data-stu-id="f3370-137">Global Reader</span></span>
- <span data-ttu-id="f3370-138">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="f3370-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="f3370-139">Rollbaserade inställningar för åtkomstkontroll i Microsoft Defender för Slutpunkt påverkar åtkomsten till data.</span><span class="sxs-lookup"><span data-stu-id="f3370-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="f3370-140">Mer information finns i artikeln om hur [du hanterar åtkomst till Microsoft 365 Defender.](mtp-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="f3370-140">For more information, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="f3370-141">Vilken tidszon används som standard i Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="f3370-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="f3370-142">Som standard visar Microsoft 365 Defender tidsinformation i tidszonen UTC.</span><span class="sxs-lookup"><span data-stu-id="f3370-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="f3370-143">Du kan ändra den här inställningen om du vill använda din lokala tidszon.</span><span class="sxs-lookup"><span data-stu-id="f3370-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="f3370-144">Läs mer om hur du ställer in tidszon</span><span class="sxs-lookup"><span data-stu-id="f3370-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="f3370-145">Hur får jag veta mer om de nya funktions- och gränssnittsuppdateringarna för Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="f3370-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="f3370-146">Microsoft tillhandahåller regelbundet information genom de olika kanalerna, inklusive:</span><span class="sxs-lookup"><span data-stu-id="f3370-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="f3370-147">Meddelandecenter [i](../../admin/manage/message-center.md) administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f3370-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="f3370-148">Blogginlägg i Microsoft [365 Security & tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="f3370-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="f3370-149">Få de senaste offentligt tillgängliga funktionerna genom att aktivera [förhandsgranskningsfunktioner.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="f3370-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="f3370-150">Är Microsoft 365 Defender tillgängligt för GCC (Government Community Cloud) eller GCC High?</span><span class="sxs-lookup"><span data-stu-id="f3370-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="f3370-151">För tillfället är den inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="f3370-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f3370-152">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="f3370-152">Related topics</span></span>

- [<span data-ttu-id="f3370-153">Översikt över Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3370-153">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="f3370-154">[Aktivera Microsoft 365 Defender.](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="f3370-154">[Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>
- [<span data-ttu-id="f3370-155">Licenskrav och andra förutsättningar</span><span class="sxs-lookup"><span data-stu-id="f3370-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="f3370-156">Distribuera tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="f3370-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="f3370-157">Aktivera förhandsgranskningsfunktioner</span><span class="sxs-lookup"><span data-stu-id="f3370-157">Turn on preview features</span></span>](preview.md)
