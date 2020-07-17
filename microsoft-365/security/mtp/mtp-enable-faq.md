---
title: Vanliga frågor och svar när du aktiverar Microsoft Threat Protection
description: Få svar på de vanligaste frågorna om licensiering, behörigheter, inledande inställningar och andra produkter och tjänster relaterade till att aktivera Microsoft Threat Protection
keywords: vanliga frågor, vanliga frågor, GCC, komma igång, aktivera MTP, Microsoft Threat Protection, M365, säkerhet, dataplats, nödvändiga behörigheter, licensberättigande, inställningssida
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 9dcfeb5616afc8953e862d6d1a542d694582b157
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "44845088"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a><span data-ttu-id="fdbb1-104">Vanliga frågor och svar när du aktiverar Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fdbb1-104">Frequently asked questions when turning on Microsoft Threat Protection</span></span>

<span data-ttu-id="fdbb1-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="fdbb1-105">**Applies to:**</span></span>
- <span data-ttu-id="fdbb1-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="fdbb1-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="fdbb1-107">Läs svar på de vanligaste frågorna om hur du aktiverar [Microsoft Threat Protection](microsoft-threat-protection.md), inklusive nödvändiga licenser och behörigheter, distribution av supporttjänster och inledande inställningar.</span><span class="sxs-lookup"><span data-stu-id="fdbb1-107">Read responses to the most commonly asked questions about turning on [Microsoft Threat Protection](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="fdbb1-108">Instruktioner om hur du aktiverar tjänsten [finns i Aktivera Microsoft Threat Protection](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="fdbb1-108">For instructions on how to turn on the service, [read Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a><span data-ttu-id="fdbb1-109">Jag har ingen Microsoft 365 E5-licens.</span><span class="sxs-lookup"><span data-stu-id="fdbb1-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="fdbb1-110">Kan jag fortfarande använda Microsoft Threat Protection?</span><span class="sxs-lookup"><span data-stu-id="fdbb1-110">Can I still use Microsoft Threat Protection?</span></span>

<span data-ttu-id="fdbb1-111">Kunder med följande licenser som inte är E5 kan använda Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="fdbb1-111">Customers with the following non-E5 licenses can use Microsoft Threat Protection:</span></span>

- <span data-ttu-id="fdbb1-112">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="fdbb1-112">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="fdbb1-113">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fdbb1-113">Azure Advanced Threat Protection</span></span>
- <span data-ttu-id="fdbb1-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="fdbb1-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="fdbb1-115">Avancerat skydd mot Office 365 (plan 2)</span><span class="sxs-lookup"><span data-stu-id="fdbb1-115">Office 365 Advanced Threat Protection (Plan 2)</span></span>
 
<span data-ttu-id="fdbb1-116">En fullständig lista över licenser som stöds [finns i licenskraven](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="fdbb1-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a><span data-ttu-id="fdbb1-117">Måste jag installera eller distribuera något för att börja använda Microsoft Threat Protection?</span><span class="sxs-lookup"><span data-stu-id="fdbb1-117">Do I need to install or deploy anything to start using Microsoft Threat Protection?</span></span>

<span data-ttu-id="fdbb1-118">Nej, Microsoft Threat Protection konsoliderar data från Microsoft 365-säkerhetstjänster som du redan har distribuerat.</span><span class="sxs-lookup"><span data-stu-id="fdbb1-118">No, Microsoft Threat Protection consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="fdbb1-119">När du slår på den kommer incident-, automatiserings- och jaktupplevelser att börja arbeta inom ramen för de distribuerade produkterna.</span><span class="sxs-lookup"><span data-stu-id="fdbb1-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="fdbb1-120">Om ingen av dessa produkter har distribuerats korrekt visas inga data i Microsofts hotskydd och kan inte vidta några åtgärder.</span><span class="sxs-lookup"><span data-stu-id="fdbb1-120">If none of these products are properly deployed, Microsoft Threat Protection will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="fdbb1-121">För att optimera dina Microsoft Threat Protection-upplevelser rekommenderar vi att du distribuerar *alla* [microsoft 365-säkerhetsprodukter och -tjänster som](deploy-supported-services.md)stöds .</span><span class="sxs-lookup"><span data-stu-id="fdbb1-121">To optimize your Microsoft Threat Protection experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a><span data-ttu-id="fdbb1-122">Var bearbetar och lagrar Microsoft Threat Protection mina data?</span><span class="sxs-lookup"><span data-stu-id="fdbb1-122">Where does Microsoft Threat Protection process and store my data?</span></span>
<span data-ttu-id="fdbb1-123">Microsoft Threat Protection väljer automatiskt en optimal plats för det datacenter där konsoliderade data bearbetas och lagras.</span><span class="sxs-lookup"><span data-stu-id="fdbb1-123">Microsoft Threat Protection automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="fdbb1-124">Om du har Microsoft Defender ATP väljer den samma plats som används av Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="fdbb1-124">If you have Microsoft Defender ATP, it selects the same location used by Microsoft Defender ATP.</span></span>

>[!NOTE]
><span data-ttu-id="fdbb1-125">Microsoft Defender ATP etablerar automatiskt bestämmelser i EU-datacenter när de aktiveras via Azure Security Center.</span><span class="sxs-lookup"><span data-stu-id="fdbb1-125">Microsoft Defender ATP automatically provisions in European Union (EU) data centers when turned on through Azure Security Center.</span></span> <span data-ttu-id="fdbb1-126">Microsoft Threat Protection etableras automatiskt i samma EU-datacenter för kunder som har etablerat Microsoft Defender ATP på det här sättet.</span><span class="sxs-lookup"><span data-stu-id="fdbb1-126">Microsoft Threat Protection will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender ATP in this manner.</span></span> 

<span data-ttu-id="fdbb1-127">Datacenterplatsen visas före och efter att tjänsten har etablerats på inställningssidan för Microsoft Threat Protection (**Inställningar > Microsoft Threat Protection**).</span><span class="sxs-lookup"><span data-stu-id="fdbb1-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft Threat Protection (**Settings > Microsoft Threat Protection**).</span></span> <span data-ttu-id="fdbb1-128">Om du föredrar att använda en annan datacenterplats väljer du **Behöver du hjälp?**</span><span class="sxs-lookup"><span data-stu-id="fdbb1-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-threat-protection"></a><span data-ttu-id="fdbb1-129">Var kan jag komma åt Microsoft Threat Protection?</span><span class="sxs-lookup"><span data-stu-id="fdbb1-129">Where can I access Microsoft Threat Protection?</span></span>

<span data-ttu-id="fdbb1-130">Microsoft Threat Protection finns i Microsoft 365 security center.</span><span class="sxs-lookup"><span data-stu-id="fdbb1-130">Microsoft Threat Protection is available in Microsoft 365 security center.</span></span> <span data-ttu-id="fdbb1-131">Om du vill gå till säkerhetscentret bläddrar du till webbadressen [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="fdbb1-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a><span data-ttu-id="fdbb1-132">Vilka behörigheter behöver jag för att komma åt Microsoft Threat Protection i Microsoft 365-säkerhetscenter?</span><span class="sxs-lookup"><span data-stu-id="fdbb1-132">What permissions do I need to access Microsoft Threat Protection in Microsoft 365 security center?</span></span>

<span data-ttu-id="fdbb1-133">Konton som tilldelats följande Azure Active Directory-roller (AD) kan komma åt Microsoft Threat Protection-funktioner och data:</span><span class="sxs-lookup"><span data-stu-id="fdbb1-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>

- <span data-ttu-id="fdbb1-134">Global administratör</span><span class="sxs-lookup"><span data-stu-id="fdbb1-134">Global administrator</span></span>
- <span data-ttu-id="fdbb1-135">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="fdbb1-135">Security administrator</span></span>
- <span data-ttu-id="fdbb1-136">Säkerhetsoperatör</span><span class="sxs-lookup"><span data-stu-id="fdbb1-136">Security Operator</span></span>
- <span data-ttu-id="fdbb1-137">Global läsare</span><span class="sxs-lookup"><span data-stu-id="fdbb1-137">Global Reader</span></span>
- <span data-ttu-id="fdbb1-138">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="fdbb1-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="fdbb1-139">Rollbaserade åtkomstkontrollinställningar i Microsoft Defender ATP påverkar åtkomsten till data.</span><span class="sxs-lookup"><span data-stu-id="fdbb1-139">Role-based access control settings in Microsoft Defender ATP influence access to data.</span></span> <span data-ttu-id="fdbb1-140">Mer information finns i om [hur du hanterar åtkomst till Microsoft Threat Protection](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="fdbb1-140">For more information, read about [managing access to Microsoft Threat Protection](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a><span data-ttu-id="fdbb1-141">Vilken tidszon standard för Microsoft Threat Protection?</span><span class="sxs-lookup"><span data-stu-id="fdbb1-141">What time zone does Microsoft Threat Protection default to?</span></span>
<span data-ttu-id="fdbb1-142">Som standard visar Microsoft Threat Protection tidsinformation i UTC-tidszonen.</span><span class="sxs-lookup"><span data-stu-id="fdbb1-142">By default, Microsoft Threat Protection displays time information in the UTC time zone.</span></span> <span data-ttu-id="fdbb1-143">Du kan ändra den här inställningen om du vill använda den lokala tidszonen.</span><span class="sxs-lookup"><span data-stu-id="fdbb1-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="fdbb1-144">Läs mer om hur du ställer in tidszonen</span><span class="sxs-lookup"><span data-stu-id="fdbb1-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a><span data-ttu-id="fdbb1-145">Hur lär jag mig mer om nya Microsoft Threat Protection-funktioner och uppdateringar av användargränssnittet?</span><span class="sxs-lookup"><span data-stu-id="fdbb1-145">How can I learn about new Microsoft Threat Protection feature and UI updates?</span></span>

<span data-ttu-id="fdbb1-146">Microsoft tillhandahåller regelbundet information via de olika kanalerna, inklusive:</span><span class="sxs-lookup"><span data-stu-id="fdbb1-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="fdbb1-147">[Administrationscentret](../../admin/manage/message-center.md) för Meddelanden i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fdbb1-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="fdbb1-148">Blogginlägg i [Microsoft 365-säkerhets- & teknikcommunity för efterlevnad](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="fdbb1-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="fdbb1-149">Få de senaste allmänt tillgängliga upplevelserna genom att aktivera [förhandsgranskningsfunktioner](preview.md).</span><span class="sxs-lookup"><span data-stu-id="fdbb1-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="fdbb1-150">Är Microsoft Threat Protection tillgängligt för GCC (US Government Community Cloud) eller GCC High?</span><span class="sxs-lookup"><span data-stu-id="fdbb1-150">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="fdbb1-151">För närvarande är den inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="fdbb1-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fdbb1-152">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="fdbb1-152">Related topics</span></span>

- [<span data-ttu-id="fdbb1-153">Översikt över Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fdbb1-153">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="fdbb1-154">[Aktivera Microsoft Threat Protection](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="fdbb1-154">[Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>
- [<span data-ttu-id="fdbb1-155">Licenskrav och andra förutsättningar</span><span class="sxs-lookup"><span data-stu-id="fdbb1-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="fdbb1-156">Distribuera tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="fdbb1-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="fdbb1-157">Aktivera förhandsgranskningsfunktioner</span><span class="sxs-lookup"><span data-stu-id="fdbb1-157">Turn on preview features</span></span>](preview.md)