---
title: Microsoft Informationsstyrning i Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
recommendations: false
description: Implementera Microsofts Informationsstyrningsfunktioner för att styra dina data för efterlevnad eller regleringskrav.
ms.openlocfilehash: 304b4e57702c55242e49fae7fdf4a36e9b2f7cdb
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244570"
---
# <a name="microsoft-information-governance-in-microsoft-365"></a><span data-ttu-id="56008-103">Microsoft Informationsstyrning i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="56008-103">Microsoft Information Governance in Microsoft 365</span></span>

><span data-ttu-id="56008-104">*[Licensieringsvägledning för Microsoft 365 för säkerhet och efterlevnad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="56008-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="56008-105">Använd Microsoft Informationsstyrning (ibland förkortad till MIG) för att styra dina data för efterlevnad eller regleringskrav.</span><span class="sxs-lookup"><span data-stu-id="56008-105">Use Microsoft Information Governance (sometimes abbreviated to MIG) capabilities to govern your data for compliance or regulatory requirements.</span></span>

![Styra dina data – informationsstyrning och hantering av arkivhandlingar](../media/information-governance-records-management.png)

<span data-ttu-id="56008-107">Vill du skydda dina data?</span><span class="sxs-lookup"><span data-stu-id="56008-107">Looking to protect your data?</span></span> <span data-ttu-id="56008-108">Se [Microsoft Informationsskydd i Microsoft 365](information-protection.md).</span><span class="sxs-lookup"><span data-stu-id="56008-108">See [Microsoft Information Protection in Microsoft 365](information-protection.md).</span></span>

<span data-ttu-id="56008-109">För att hjälpa dig att följa föreskrifterna för datasekretess har vi utformat ett arbetsflöde som vägleder dig genom hela processen för att planera och implementera funktioner i Microsoft 365, inklusive säker åtkomst, skydd mot hot, informationsskydd och datastyrning.</span><span class="sxs-lookup"><span data-stu-id="56008-109">To help you comply with data privacy regulations, we’ve designed a workflow to guide you through an end-to-end process to plan and implement capabilities across Microsoft 365, including secure access, threat protection, information protection, and data governance.</span></span> <span data-ttu-id="56008-110">Mer information finns i [Distribuera informationsskydd för föreskrifter för datasekretess med Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).</span><span class="sxs-lookup"><span data-stu-id="56008-110">For more information, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).</span></span> 

## <a name="information-governance"></a><span data-ttu-id="56008-111">Informationsstyrning</span><span class="sxs-lookup"><span data-stu-id="56008-111">Information governance</span></span>

<span data-ttu-id="56008-112">Om du vill behålla det du behöver och ta bort det du inte behöver:</span><span class="sxs-lookup"><span data-stu-id="56008-112">To keep what you need and delete what you don't:</span></span>
 
|<span data-ttu-id="56008-113">Funktion</span><span class="sxs-lookup"><span data-stu-id="56008-113">Capability</span></span>|<span data-ttu-id="56008-114">Vilka problem löser den?</span><span class="sxs-lookup"><span data-stu-id="56008-114">What problems does it solve?</span></span>|<span data-ttu-id="56008-115">Komma igång</span><span class="sxs-lookup"><span data-stu-id="56008-115">Get started</span></span>|
|:------|:------------|:--------------------|:-----------------------------|
|[<span data-ttu-id="56008-116">Kvarhållningsprinciper och -etiketter</span><span class="sxs-lookup"><span data-stu-id="56008-116">Retention policies and retention labels</span></span>](retention.md)| <span data-ttu-id="56008-117">Behålla eller ta bort innehåll med principhantering och ett borttagningsarbetsflöde för e-post, dokument, snabbmeddelanden med mera</span><span class="sxs-lookup"><span data-stu-id="56008-117">Retain or delete content with policy management and a deletion workflow for email, documents, instant messages, and more</span></span> <br /><br /><span data-ttu-id="56008-118">Exempelscenario: [Tillämpa en kvarhållningsetikett till innehåll automatiskt](apply-retention-labels-automatically.md)</span><span class="sxs-lookup"><span data-stu-id="56008-118">Example scenario: [Apply a retention label to content automatically](apply-retention-labels-automatically.md)</span></span> | [<span data-ttu-id="56008-119">Komma igång med kvarhållningsprinciper och -etiketter</span><span class="sxs-lookup"><span data-stu-id="56008-119">Get started with retention policies and retention labels</span></span>](get-started-with-retention.md)|
|[<span data-ttu-id="56008-120">Importtjänst</span><span class="sxs-lookup"><span data-stu-id="56008-120">Import service</span></span>](importing-pst-files-to-office-365.md)| <span data-ttu-id="56008-121">Massimporterar PST-filer till Exchange Online-postlådor för att behålla och söka i e-postmeddelanden efter efterlevnad eller regleringskrav</span><span class="sxs-lookup"><span data-stu-id="56008-121">Bulk-import PST files to Exchange Online mailboxes to retain and search email messages for compliance or regulatory requirements</span></span> | [<span data-ttu-id="56008-122">Använd nätverksuppladdning för att importera odin organisations PST-filer till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="56008-122">Use network upload to import your organization's PST files to Microsoft 365</span></span>](use-network-upload-to-import-pst-files.md)|
|[<span data-ttu-id="56008-123">Arkivera tredjepartsdata</span><span class="sxs-lookup"><span data-stu-id="56008-123">Archive third-party data</span></span>](archiving-third-party-data.md)| <span data-ttu-id="56008-124">Importera, arkivera och tillämpa efterlevnadslösningar för tredjepartsdata från plattformar för sociala medier, snabbmeddelanden och dokumentsamarbete</span><span class="sxs-lookup"><span data-stu-id="56008-124">Import, archive, and apply compliance solutions to third-party data from social media platforms, instant messaging platforms, and document collaboration platforms</span></span>| [<span data-ttu-id="56008-125">Tredjepartskopplingar</span><span class="sxs-lookup"><span data-stu-id="56008-125">Third-party connectors</span></span>](archiving-third-party-data.md#third-party-data-connectors)|
|[<span data-ttu-id="56008-126">Inaktiva postlådor</span><span class="sxs-lookup"><span data-stu-id="56008-126">Inactive mailboxes</span></span>](inactive-mailboxes-in-office-365.md)| <span data-ttu-id="56008-127">Behåll postlådeinnehåll efter att anställda har lämnar organisationen</span><span class="sxs-lookup"><span data-stu-id="56008-127">Retain mailbox content after employees leave the organization</span></span> | [<span data-ttu-id="56008-128">Skapa och hantera inaktiva postlådor</span><span class="sxs-lookup"><span data-stu-id="56008-128">Create and manage inactive mailboxes</span></span>](create-and-manage-inactive-mailboxes.md)|

## <a name="records-management"></a><span data-ttu-id="56008-129">Hantering av arkivhandlingar</span><span class="sxs-lookup"><span data-stu-id="56008-129">Records management</span></span>

<span data-ttu-id="56008-130">För att hantera högvärdigt innehåll för juridiska-, affärs- eller regleringsåtaganden:</span><span class="sxs-lookup"><span data-stu-id="56008-130">To manage high-value content for legal, business, or regulatory obligations:</span></span>

|<span data-ttu-id="56008-131">Funktion</span><span class="sxs-lookup"><span data-stu-id="56008-131">Capability</span></span>|<span data-ttu-id="56008-132">Vilka problem löser den?</span><span class="sxs-lookup"><span data-stu-id="56008-132">What problems does it solve?</span></span>|<span data-ttu-id="56008-133">Komma igång</span><span class="sxs-lookup"><span data-stu-id="56008-133">Get started</span></span>|
|:------|:------------|---------------------|:----------------------------|
|[<span data-ttu-id="56008-134">Hantering av arkivhandlingar</span><span class="sxs-lookup"><span data-stu-id="56008-134">Records management</span></span>](records-management.md)| <span data-ttu-id="56008-135">En enda lösning för e-post och dokument som integrerar kvarhållningsscheman och krav i en filplan som stöder hela livscykeln för ditt innehåll med arkivhandlingar av deklaration, kvarhållning och disposition</span><span class="sxs-lookup"><span data-stu-id="56008-135">A single solution for email and documents that incorporates retention schedules and requirements into a file plan that supports the full lifecycle of your content with records declaration, retention, and disposition</span></span> <br /><br /><span data-ttu-id="56008-136">Exempel scenario: [Disposition av arkivhandlingar](disposition.md#disposition-of-records)</span><span class="sxs-lookup"><span data-stu-id="56008-136">Example scenario: [Disposition of records](disposition.md#disposition-of-records)</span></span>|[<span data-ttu-id="56008-137">Kom igång med hantering av arkivhandlingar</span><span class="sxs-lookup"><span data-stu-id="56008-137">Get started with records management</span></span>](get-started-with-records-management.md) |