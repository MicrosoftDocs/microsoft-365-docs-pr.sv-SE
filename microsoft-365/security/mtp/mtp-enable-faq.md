---
title: Vanliga frågor och svar när du aktiverar Microsoft 365 Defender
description: Få svar på de vanligaste frågorna om licensiering, behörigheter, inledande inställningar och andra produkter och tjänster relaterade till att aktivera Microsoft 365 Defender
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
ms.openlocfilehash: bfb58cb043f2bc641245814c41e389ddcdbfdefa
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842422"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="e0192-104">Vanliga frågor och svar när du aktiverar Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0192-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e0192-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="e0192-105">**Applies to:**</span></span>
- <span data-ttu-id="e0192-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0192-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e0192-107">Läs svar på de vanligaste frågorna om att aktivera [Microsoft 365 Defender](microsoft-threat-protection.md), inklusive nödvändiga licenser och behörigheter, distribuera Support tjänster och Start Inställningar.</span><span class="sxs-lookup"><span data-stu-id="e0192-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="e0192-108">Instruktioner om hur du aktiverar tjänsten finns [i Aktivera Microsoft 365 Defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="e0192-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="e0192-109">Jag har ingen Microsoft 365 E5-licens.</span><span class="sxs-lookup"><span data-stu-id="e0192-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="e0192-110">Kan jag fortfarande använda Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="e0192-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="e0192-111">Kunder med följande icke-E5 licenser kan använda Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="e0192-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="e0192-112">Microsoft Defender för slut punkt</span><span class="sxs-lookup"><span data-stu-id="e0192-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="e0192-113">Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="e0192-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="e0192-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e0192-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="e0192-115">Defender för Office 365 (abonnemang 2)</span><span class="sxs-lookup"><span data-stu-id="e0192-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="e0192-116">En fullständig lista över licenser som stöds finns i [licensierings kraven](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="e0192-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="e0192-117">Behöver jag installera eller distribuera något för att komma igång med Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="e0192-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="e0192-118">Nej, Microsoft 365 Defender konsoliderar data från Microsoft 365-säkerhetstjänster som du redan har distribuerat.</span><span class="sxs-lookup"><span data-stu-id="e0192-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="e0192-119">När du har aktiverat det kommer incident-, automatiserings-och jakt upplevelser att fungera inom omfattningen för de distribuerade produkterna.</span><span class="sxs-lookup"><span data-stu-id="e0192-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="e0192-120">Om ingen av de här produkterna distribueras korrekt visas inga data i Microsoft 365 Defender och det går inte att vidta någon åtgärd.</span><span class="sxs-lookup"><span data-stu-id="e0192-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="e0192-121">För att optimera din Microsoft 365 Defender-upplevelse rekommenderar vi att du distribuerar *alla* [Microsoft 365-säkerhetsprodukter och-tjänster](deploy-supported-services.md)som stöds.</span><span class="sxs-lookup"><span data-stu-id="e0192-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="e0192-122">Var är Microsoft 365 Defender och lagrar mina data?</span><span class="sxs-lookup"><span data-stu-id="e0192-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="e0192-123">Microsoft 365 Defender väljer automatiskt en optimal plats för data centret där konsoliderade data behandlas och lagras.</span><span class="sxs-lookup"><span data-stu-id="e0192-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="e0192-124">Om du har Microsoft Defender för slut punkt väljer den platsen som används av Defender för slut punkten.</span><span class="sxs-lookup"><span data-stu-id="e0192-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="e0192-125">Microsoft Defender för slut punkt är automatiskt bestämmelser i EU-datacenter när de är aktiverade genom Azure Defender \*.</span><span class="sxs-lookup"><span data-stu-id="e0192-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender\*.</span></span> <span data-ttu-id="e0192-126">Microsoft 365 Defender tillhandahåller automatiskt samma EU-datacentertjänster för kunder som har etablerat Microsoft Defender för slut punkter på det här sättet.</span><span class="sxs-lookup"><span data-stu-id="e0192-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="e0192-127">Data Center platsen visas innan och efter det att tjänsten har etablerats på inställnings sidan för Microsoft 365 Defender ( **inställningar > Microsoft 365 Defender** ).</span><span class="sxs-lookup"><span data-stu-id="e0192-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender ( **Settings > Microsoft 365 Defender** ).</span></span> <span data-ttu-id="e0192-128">Om du föredrar att använda en annan data Center plats väljer du **behöver hjälp?** i Microsoft 365 säkerhets Center för att kontakta Microsofts support.</span><span class="sxs-lookup"><span data-stu-id="e0192-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="e0192-129">Var kan jag komma åt Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="e0192-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="e0192-130">Microsoft 365 Defender finns i Microsoft 365 säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="e0192-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="e0192-131">Gå till säkerhets Center genom att bläddra till webb adressen [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="e0192-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="e0192-132">Vilka behörigheter behöver jag för att få åtkomst till Microsoft 365 Defender i Microsoft 365 säkerhets Center?</span><span class="sxs-lookup"><span data-stu-id="e0192-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="e0192-133">Konton tilldelade följande Azure Active Directory (AD)-roller kan komma åt Microsoft 365 Defender-funktioner och-data:</span><span class="sxs-lookup"><span data-stu-id="e0192-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="e0192-134">Global administratör</span><span class="sxs-lookup"><span data-stu-id="e0192-134">Global administrator</span></span>
- <span data-ttu-id="e0192-135">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="e0192-135">Security administrator</span></span>
- <span data-ttu-id="e0192-136">Säkerhets ansvarig</span><span class="sxs-lookup"><span data-stu-id="e0192-136">Security Operator</span></span>
- <span data-ttu-id="e0192-137">Global läsare</span><span class="sxs-lookup"><span data-stu-id="e0192-137">Global Reader</span></span>
- <span data-ttu-id="e0192-138">Säkerhets läsare</span><span class="sxs-lookup"><span data-stu-id="e0192-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="e0192-139">Rollbaserad åtkomst kontroll inställningar i Microsoft Defender för slut punkten påverkar åtkomsten till data.</span><span class="sxs-lookup"><span data-stu-id="e0192-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="e0192-140">Mer information finns i [Hantera åtkomst till Microsoft 365 Defender](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e0192-140">For more information, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="e0192-141">Vilken tidszon är Microsoft 365 Defender standard?</span><span class="sxs-lookup"><span data-stu-id="e0192-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="e0192-142">Som standard visar Microsoft 365 Defender tidsinformation i UTC-tidszonen.</span><span class="sxs-lookup"><span data-stu-id="e0192-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="e0192-143">Du kan ändra den här inställningen för att använda din lokala tidszon.</span><span class="sxs-lookup"><span data-stu-id="e0192-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="e0192-144">Lär dig hur du ställer in tids zonen</span><span class="sxs-lookup"><span data-stu-id="e0192-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="e0192-145">Hur kan jag lära dig mer om nya funktioner och UI-uppdateringar för Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="e0192-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="e0192-146">Microsoft ger regelbundet information via de olika kanalerna, bland annat:</span><span class="sxs-lookup"><span data-stu-id="e0192-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="e0192-147">[Meddelande Center](../../admin/manage/message-center.md) i administrations Center för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0192-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="e0192-148">Blogposts i [microsofts 365 säkerhets &-kompatibilitet teknisk community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="e0192-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="e0192-149">Få de senaste allmänt tillgängliga upplevelserna genom att aktivera [förhands gransknings funktionerna](preview.md).</span><span class="sxs-lookup"><span data-stu-id="e0192-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="e0192-150">Är Microsoft 365 Defender tillgängligt för AMERIKANSKt community-moln (GCC) eller GCC High?</span><span class="sxs-lookup"><span data-stu-id="e0192-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="e0192-151">För tillfället är den inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="e0192-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e0192-152">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e0192-152">Related topics</span></span>

- [<span data-ttu-id="e0192-153">Översikt över Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0192-153">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="e0192-154">[Aktivera Microsoft 365 Defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="e0192-154">[Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>
- [<span data-ttu-id="e0192-155">Licens krav och andra förutsättningar</span><span class="sxs-lookup"><span data-stu-id="e0192-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="e0192-156">Distribuera tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="e0192-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="e0192-157">Aktivera förhandsgranskningsfunktioner</span><span class="sxs-lookup"><span data-stu-id="e0192-157">Turn on preview features</span></span>](preview.md)
