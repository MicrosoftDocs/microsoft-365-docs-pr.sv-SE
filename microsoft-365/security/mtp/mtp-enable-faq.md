---
title: Vanliga frågor och svar när du aktiverar skydd mot Microsoft Threat
description: Få svar på de vanligaste frågorna om licensiering, behörigheter, inledande inställningar och andra produkter och tjänster relaterade till att aktivera Microsoft Threat Protection
keywords: Vanliga frågor, FAQ, GCC, kom igång, aktivera MTP, Microsoft Threat Protection, M365, säkerhet, data plats, nödvändiga behörigheter, licens kvalificering, sidan Inställningar
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
ms.openlocfilehash: 6b0d8d9be0cc84e61a3228f79fc14f1bfc9f8a83
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198845"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a><span data-ttu-id="65533-104">Vanliga frågor och svar när du aktiverar skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="65533-104">Frequently asked questions when turning on Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="65533-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="65533-105">**Applies to:**</span></span>
- <span data-ttu-id="65533-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="65533-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="65533-107">Läs svar på de vanligaste frågorna om att aktivera skydd mot [Microsoft Threat](microsoft-threat-protection.md), inklusive nödvändiga licenser och behörigheter, distribuera Support tjänster och Start Inställningar.</span><span class="sxs-lookup"><span data-stu-id="65533-107">Read responses to the most commonly asked questions about turning on [Microsoft Threat Protection](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="65533-108">Instruktioner om hur du aktiverar tjänsten finns i [Aktivera skydd mot Microsoft hot](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="65533-108">For instructions on how to turn on the service, [read Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a><span data-ttu-id="65533-109">Jag har ingen Microsoft 365 E5-licens.</span><span class="sxs-lookup"><span data-stu-id="65533-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="65533-110">Kan jag fortfarande använda skydd mot Microsoft Threat?</span><span class="sxs-lookup"><span data-stu-id="65533-110">Can I still use Microsoft Threat Protection?</span></span>

<span data-ttu-id="65533-111">Kunder med följande icke-E5 licenser kan använda Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="65533-111">Customers with the following non-E5 licenses can use Microsoft Threat Protection:</span></span>

- <span data-ttu-id="65533-112">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="65533-112">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="65533-113">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="65533-113">Azure Advanced Threat Protection</span></span>
- <span data-ttu-id="65533-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="65533-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="65533-115">Office 365 Avancerat skydd (abonnemang 2)</span><span class="sxs-lookup"><span data-stu-id="65533-115">Office 365 Advanced Threat Protection (Plan 2)</span></span>
 
<span data-ttu-id="65533-116">En fullständig lista över licenser som stöds finns i [licensierings kraven](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="65533-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a><span data-ttu-id="65533-117">Behöver jag installera eller distribuera något för att komma igång med Microsoft Threat Protection?</span><span class="sxs-lookup"><span data-stu-id="65533-117">Do I need to install or deploy anything to start using Microsoft Threat Protection?</span></span>

<span data-ttu-id="65533-118">Nej, Microsoft Threat Protection konsoliderar data från säkerhets tjänsterna för Microsoft 365 som du redan har distribuerat.</span><span class="sxs-lookup"><span data-stu-id="65533-118">No, Microsoft Threat Protection consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="65533-119">När du har aktiverat det kommer incident-, automatiserings-och jakt upplevelser att fungera inom omfattningen för de distribuerade produkterna.</span><span class="sxs-lookup"><span data-stu-id="65533-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="65533-120">Om ingen av de här produkterna distribueras korrekt visas inga data och det går inte att vidta någon åtgärd.</span><span class="sxs-lookup"><span data-stu-id="65533-120">If none of these products are properly deployed, Microsoft Threat Protection will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="65533-121">För att optimera skyddet mot Microsoft Threat Protection rekommenderar vi att du distribuerar *alla* [Microsoft 365-säkerhetsprodukter och-tjänster](deploy-supported-services.md)som stöds.</span><span class="sxs-lookup"><span data-stu-id="65533-121">To optimize your Microsoft Threat Protection experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a><span data-ttu-id="65533-122">Var finns Microsoft Threat Protection och lagrar mina data?</span><span class="sxs-lookup"><span data-stu-id="65533-122">Where does Microsoft Threat Protection process and store my data?</span></span>
<span data-ttu-id="65533-123">Microsoft Threat Protection väljer automatiskt en optimal plats för data centret där konsoliderade data behandlas och lagras.</span><span class="sxs-lookup"><span data-stu-id="65533-123">Microsoft Threat Protection automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="65533-124">Om du har Microsoft Defender ATP väljer den den plats som används av Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="65533-124">If you have Microsoft Defender ATP, it selects the same location used by Microsoft Defender ATP.</span></span>

>[!NOTE]
><span data-ttu-id="65533-125">Microsoft Defender ATP tillhandahåller automatiskt bestämmelser i EU-datacenter när de aktive ras via Azure Security Center.</span><span class="sxs-lookup"><span data-stu-id="65533-125">Microsoft Defender ATP automatically provisions in European Union (EU) data centers when turned on through Azure Security Center.</span></span> <span data-ttu-id="65533-126">Microsoft Threat Protection tillhandahåller automatiskt samma EU-datacenter för kunder som har etablerat Microsoft Defender ATP på det här sättet.</span><span class="sxs-lookup"><span data-stu-id="65533-126">Microsoft Threat Protection will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender ATP in this manner.</span></span> 

<span data-ttu-id="65533-127">Data Center platsen visas innan och efter det att tjänsten har etablerats på inställnings sidan för Microsoft Threat Protection (**inställningar > skydd mot Microsoft hotet**).</span><span class="sxs-lookup"><span data-stu-id="65533-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft Threat Protection (**Settings > Microsoft Threat Protection**).</span></span> <span data-ttu-id="65533-128">Om du föredrar att använda en annan data Center plats väljer du **behöver hjälp?** i Microsoft 365 säkerhets Center för att kontakta Microsofts support.</span><span class="sxs-lookup"><span data-stu-id="65533-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-threat-protection"></a><span data-ttu-id="65533-129">Var kan jag få åtkomst till Microsoft Threat Protection?</span><span class="sxs-lookup"><span data-stu-id="65533-129">Where can I access Microsoft Threat Protection?</span></span>

<span data-ttu-id="65533-130">Microsoft Threat Protection är tillgängligt i säkerhets Center för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="65533-130">Microsoft Threat Protection is available in Microsoft 365 security center.</span></span> <span data-ttu-id="65533-131">Gå till säkerhets Center genom att bläddra till webb adressen [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="65533-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a><span data-ttu-id="65533-132">Vilka behörigheter behöver jag för att få åtkomst till Microsoft Threat Protection i Microsoft 365 säkerhets Center?</span><span class="sxs-lookup"><span data-stu-id="65533-132">What permissions do I need to access Microsoft Threat Protection in Microsoft 365 security center?</span></span>

<span data-ttu-id="65533-133">Konton tilldelade följande Azure Active Directory (AD)-roller kan komma åt funktioner och data för Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="65533-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>

- <span data-ttu-id="65533-134">Global administratör</span><span class="sxs-lookup"><span data-stu-id="65533-134">Global administrator</span></span>
- <span data-ttu-id="65533-135">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="65533-135">Security administrator</span></span>
- <span data-ttu-id="65533-136">Säkerhets ansvarig</span><span class="sxs-lookup"><span data-stu-id="65533-136">Security Operator</span></span>
- <span data-ttu-id="65533-137">Global läsare</span><span class="sxs-lookup"><span data-stu-id="65533-137">Global Reader</span></span>
- <span data-ttu-id="65533-138">Säkerhets läsare</span><span class="sxs-lookup"><span data-stu-id="65533-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="65533-139">Rollbaserad åtkomst kontroll inställningar i Microsoft Defender ATP påverkar till gång till data.</span><span class="sxs-lookup"><span data-stu-id="65533-139">Role-based access control settings in Microsoft Defender ATP influence access to data.</span></span> <span data-ttu-id="65533-140">Mer information finns i om [att hantera åtkomst till Microsoft Threat Protection](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="65533-140">For more information, read about [managing access to Microsoft Threat Protection](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a><span data-ttu-id="65533-141">Vilken tidszon används som standard i tids zonen?</span><span class="sxs-lookup"><span data-stu-id="65533-141">What time zone does Microsoft Threat Protection default to?</span></span>
<span data-ttu-id="65533-142">Som standard visas tidsinformation i tids zonen för UTC.</span><span class="sxs-lookup"><span data-stu-id="65533-142">By default, Microsoft Threat Protection displays time information in the UTC time zone.</span></span> <span data-ttu-id="65533-143">Du kan ändra den här inställningen för att använda din lokala tidszon.</span><span class="sxs-lookup"><span data-stu-id="65533-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="65533-144">Lär dig hur du ställer in tids zonen</span><span class="sxs-lookup"><span data-stu-id="65533-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a><span data-ttu-id="65533-145">Hur kan jag lära dig mer om nya funktioner I Microsoft Threat Protection och UI-uppdateringar?</span><span class="sxs-lookup"><span data-stu-id="65533-145">How can I learn about new Microsoft Threat Protection feature and UI updates?</span></span>

<span data-ttu-id="65533-146">Microsoft ger regelbundet information via de olika kanalerna, bland annat:</span><span class="sxs-lookup"><span data-stu-id="65533-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="65533-147">[Meddelande Center](../../admin/manage/message-center.md) i administrations Center för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="65533-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="65533-148">Blogposts i [microsofts 365 säkerhets &-kompatibilitet teknisk community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="65533-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="65533-149">Få de senaste allmänt tillgängliga upplevelserna genom att aktivera [förhands gransknings funktionerna](preview.md).</span><span class="sxs-lookup"><span data-stu-id="65533-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="65533-150">Finns Microsoft Threat Protection för AMERIKANSKt community-moln (GCC) eller GCC High?</span><span class="sxs-lookup"><span data-stu-id="65533-150">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="65533-151">För tillfället är den inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="65533-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="65533-152">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="65533-152">Related topics</span></span>

- [<span data-ttu-id="65533-153">Microsoft Threat Protection-översikt</span><span class="sxs-lookup"><span data-stu-id="65533-153">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="65533-154">[Aktivera skydd mot Microsoft Threat](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="65533-154">[Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>
- [<span data-ttu-id="65533-155">Licens krav och andra förutsättningar</span><span class="sxs-lookup"><span data-stu-id="65533-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="65533-156">Distribuera tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="65533-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="65533-157">Aktivera förhands gransknings funktioner</span><span class="sxs-lookup"><span data-stu-id="65533-157">Turn on preview features</span></span>](preview.md)
