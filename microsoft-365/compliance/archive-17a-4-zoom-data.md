---
title: Konfigurera en koppling för att arkivera zoomdata i Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Lär dig att konfigurera och använda en 17a-4-zoomdataparserkoppling för att importera och arkivera zoomdata i Microsoft 365.
ms.openlocfilehash: dffececb0719999abf19ea58eab1a52afdb3daea
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53097221"
---
# <a name="set-up-a-connector-to-archive-zoom-data-preview"></a><span data-ttu-id="ba998-103">Konfigurera en koppling för att arkivera zoomdata (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="ba998-103">Set up a connector to archive Zoom data (preview)</span></span>

<span data-ttu-id="ba998-104">Använd [Zoomdataparser](https://www.17a-4.com/dataparser/) från 17a-4 LLC för att importera och arkivera data från zoomplattformen till användarpostlådor i Microsoft 365 organisation.</span><span class="sxs-lookup"><span data-stu-id="ba998-104">Use the [Zoom DataParser](https://www.17a-4.com/dataparser/) from 17a-4 LLC to import and archive data from the Zoom platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="ba998-105">DataParser har en zoomkoppling som är konfigurerad för att hämta objekt från en datakälla från tredje part och importera objekten till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ba998-105">The DataParser includes a Zoom connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="ba998-106">Kopplingen Zooma dataparser konverterar zoomdata till ett e-postmeddelandeformat och importerar sedan dessa objekt till användarnas postlådor i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ba998-106">The Zoom DataParser connector converts Zoom data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="ba998-107">När zoomdata har lagrats i användarnas postlådor kan du tillämpa efterlevnadsfunktioner i Microsoft 365, till exempel Bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter samt kommunikationsefterlevnad.</span><span class="sxs-lookup"><span data-stu-id="ba998-107">After Zoom data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="ba998-108">Om du använder en Zoom-koppling för att importera och arkivera data i Microsoft 365 kan det hjälpa din organisation att följa myndighets- och regelpolicyer.</span><span class="sxs-lookup"><span data-stu-id="ba998-108">Using a Zoom connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-zoom-data"></a><span data-ttu-id="ba998-109">Översikt över arkivering av zoomdata</span><span class="sxs-lookup"><span data-stu-id="ba998-109">Overview of archiving Zoom data</span></span>

<span data-ttu-id="ba998-110">I följande översikt beskrivs hur du använder en datakoppling för att arkivera zoomdata i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ba998-110">The following overview explains the process of using a data connector to archive Zoom data in Microsoft 365.</span></span>

![Arkivering av arbetsflöde för att zooma data från 17a-4](../media/ZoomDataParserConnectorWorkflow.png)

1. <span data-ttu-id="ba998-112">Din organisation arbetar med 17a-4 för att konfigurera och konfigurera Zoomdataparser.</span><span class="sxs-lookup"><span data-stu-id="ba998-112">Your organization works with 17a-4 to set up and configure the Zoom DataParser.</span></span>

2. <span data-ttu-id="ba998-113">Regelbundet samlas zoomobjekt in av DataParser.</span><span class="sxs-lookup"><span data-stu-id="ba998-113">On a regular basis, Zoom items are collected by the DataParser.</span></span> <span data-ttu-id="ba998-114">DataParser konverterar även innehållet i ett meddelande till ett e-postmeddelandeformat.</span><span class="sxs-lookup"><span data-stu-id="ba998-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="ba998-115">Zoomdataparser-kopplingen som du skapar i Microsoft 365 Efterlevnadscenter ansluter till DataParser och överför meddelanden till en säker Azure Storage plats i Microsoft-molnet.</span><span class="sxs-lookup"><span data-stu-id="ba998-115">The Zoom DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="ba998-116">En undermapp i mappen Inkorgen med namnet **Zooma dataparser** skapas i användarnas postlådor och zoomobjekten importeras till den mappen.</span><span class="sxs-lookup"><span data-stu-id="ba998-116">A subfolder in the Inbox folder named **Zoom DataParser** is created in the user mailboxes, and the Zoom items are imported to that folder.</span></span> <span data-ttu-id="ba998-117">Kopplingen avgör vilken postlåda som objekt ska importeras till med hjälp av värdet för egenskapen *E-post.*</span><span class="sxs-lookup"><span data-stu-id="ba998-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="ba998-118">Varje zoomobjekt innehåller den här egenskapen, som fylls i med e-postadresserna för alla deltagare.</span><span class="sxs-lookup"><span data-stu-id="ba998-118">Every Zoom item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="ba998-119">Innan du skapa en koppling</span><span class="sxs-lookup"><span data-stu-id="ba998-119">Before you set up a connector</span></span>

- <span data-ttu-id="ba998-120">Skapa ett DataParser-konto för Microsoft-kopplingar.</span><span class="sxs-lookup"><span data-stu-id="ba998-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="ba998-121">Det gör du genom att [kontakta 17a-4 LLC.](https://www.17a-4.com/contact/)</span><span class="sxs-lookup"><span data-stu-id="ba998-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="ba998-122">Du måste logga in på det här kontot när du skapar kopplingen i steg 1.</span><span class="sxs-lookup"><span data-stu-id="ba998-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="ba998-123">Den användare som skapar zoomdataparserkopplingen i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ba998-123">The user who creates the Zoom DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="ba998-124">Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="ba998-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ba998-125">Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ba998-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="ba998-126">Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ba998-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="ba998-127">Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="ba998-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="ba998-128">Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="ba998-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-zoom-dataparser-connector"></a><span data-ttu-id="ba998-129">Steg 1: Konfigurera en zoomdataparserkoppling</span><span class="sxs-lookup"><span data-stu-id="ba998-129">Step 1: Set up a Zoom DataParser connector</span></span>

<span data-ttu-id="ba998-130">Det första steget är att komma åt sidan Datakopplingar i Microsoft 365 Efterlevnadscenter och skapa en 17a-4-koppling för zoomdata.</span><span class="sxs-lookup"><span data-stu-id="ba998-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for Zoom data.</span></span>

1. <span data-ttu-id="ba998-131">Gå till <https://compliance.microsoft.com> och klicka sedan på **Datakopplingar**  >  **Zooma dataparser**.</span><span class="sxs-lookup"><span data-stu-id="ba998-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **Zoom DataParser**.</span></span>

2. <span data-ttu-id="ba998-132">På sidan **Zooma dataparser produktbeskrivning** klickar du på Lägg **till koppling**.</span><span class="sxs-lookup"><span data-stu-id="ba998-132">On the **Zoom DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="ba998-133">Klicka på **Acceptera på** sidan **Användningsvillkor.**</span><span class="sxs-lookup"><span data-stu-id="ba998-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="ba998-134">Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="ba998-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="ba998-135">Logga in på ditt 17a-4-konto och utför stegen i guiden Zooma dataparser-anslutning.</span><span class="sxs-lookup"><span data-stu-id="ba998-135">Sign in to your 17a-4 account and complete the steps in the Zoom DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-zoom-dataparser-connector"></a><span data-ttu-id="ba998-136">Steg 2: Konfigurera zoomdataparserkopplingen</span><span class="sxs-lookup"><span data-stu-id="ba998-136">Step 2: Configure the Zoom DataParser connector</span></span>

<span data-ttu-id="ba998-137">Konfigurera zoomdataparser-kopplingen med stöd för 17a-4.</span><span class="sxs-lookup"><span data-stu-id="ba998-137">Work with 17a-4 Support to configure the Zoom DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="ba998-138">Steg 3: Mappa användare</span><span class="sxs-lookup"><span data-stu-id="ba998-138">Step 3: Map users</span></span>

<span data-ttu-id="ba998-139">Zoomdataparser-kopplingen mappar automatiskt användare till sina e Microsoft 365-postadresser innan de importerar data till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ba998-139">The Zoom DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-zoom-dataparser-connector"></a><span data-ttu-id="ba998-140">Steg 4: Övervaka zoomdataparserkopplingen</span><span class="sxs-lookup"><span data-stu-id="ba998-140">Step 4: Monitor the Zoom DataParser connector</span></span>

<span data-ttu-id="ba998-141">När du har skapat en zoomdataparserkoppling kan du visa kopplingsstatusen i Microsoft 365 Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="ba998-141">After you create a Zoom DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="ba998-142">Gå till <https://compliance.microsoft.com> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.</span><span class="sxs-lookup"><span data-stu-id="ba998-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="ba998-143">Klicka på **fliken Kopplingar** och välj sedan zoomdataparserkopplingen som du har skapat för att visa den utfällbar sidan, som innehåller egenskaper och information om kopplingen.</span><span class="sxs-lookup"><span data-stu-id="ba998-143">Click the **Connectors** tab and then select the Zoom DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="ba998-144">Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen.</span><span class="sxs-lookup"><span data-stu-id="ba998-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="ba998-145">Den här loggen innehåller data som har importerats till Microsoft-molnet.</span><span class="sxs-lookup"><span data-stu-id="ba998-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="ba998-146">Kända problem</span><span class="sxs-lookup"><span data-stu-id="ba998-146">Known issues</span></span>

<span data-ttu-id="ba998-147">För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB.</span><span class="sxs-lookup"><span data-stu-id="ba998-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="ba998-148">Stöd för större objekt blir tillgängligt vid ett senare tillfälle.</span><span class="sxs-lookup"><span data-stu-id="ba998-148">Support for larger items will be available at a later date.</span></span>
