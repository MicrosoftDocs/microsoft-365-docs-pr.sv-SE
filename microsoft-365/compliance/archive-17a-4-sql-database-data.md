---
title: Konfigurera en koppling för att arkivera SQL data i Microsoft 365
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
description: Lär dig att konfigurera och använda en 17a-4-SQL DataParser-koppling för att importera och arkivera SQL data i Microsoft 365.
ms.openlocfilehash: 51fd433ad072ba5afe0b314d7b61041728337240
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137673"
---
# <a name="set-up-a-connector-to-archive-sql-data-preview"></a><span data-ttu-id="3b56f-103">Konfigurera en koppling för att arkivera SQL data (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="3b56f-103">Set up a connector to archive SQL data (preview)</span></span>

<span data-ttu-id="3b56f-104">Använd [SQL-dataparser](https://www.17a-4.com/sql-dataparser/) från 17a-4 LLC för att importera och arkivera data från en SQL-databas till användarnas postlådor i Microsoft 365 organisation.</span><span class="sxs-lookup"><span data-stu-id="3b56f-104">Use the [SQL DataParser](https://www.17a-4.com/sql-dataparser/) from 17a-4 LLC to import and archive data from a SQL database to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="3b56f-105">DataParser innehåller en SQL-koppling som är konfigurerad för att hämta objekt från en datakälla från tredje part och importera objekten till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b56f-105">The DataParser includes a SQL connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="3b56f-106">Med SQL DataParser-koppling konverteras data SQL till ett e-postmeddelandeformat och sedan importeras objekten till användarpostlådor i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b56f-106">The SQL DataParser connector converts SQL data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="3b56f-107">När SQL data har lagrats i användarnas postlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter samt kommunikationsefterlevnad.</span><span class="sxs-lookup"><span data-stu-id="3b56f-107">After SQL data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="3b56f-108">Genom att SQL en anslutare för att importera och arkivera data i Microsoft 365 kan detta hjälpa din organisation att följa myndighets- och regelpolicyn.</span><span class="sxs-lookup"><span data-stu-id="3b56f-108">Using a SQL connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-sql-data"></a><span data-ttu-id="3b56f-109">Översikt över arkivering SQL data</span><span class="sxs-lookup"><span data-stu-id="3b56f-109">Overview of archiving SQL data</span></span>

<span data-ttu-id="3b56f-110">I följande översikt beskrivs hur du använder en datakoppling för att arkivera SQL data i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b56f-110">The following overview explains the process of using a data connector to archive SQL data in Microsoft 365.</span></span>

![Arkivering av arbetsflöde för SQL data från 17a-4](../media/SQLDatabaseDataParserConnectorWorkflow.png)

1. <span data-ttu-id="3b56f-112">Din organisation använder 17a-4 för att konfigurera och konfigurera SQL DataParser.</span><span class="sxs-lookup"><span data-stu-id="3b56f-112">Your organization works with 17a-4 to set up and configure the SQL DataParser.</span></span>

2. <span data-ttu-id="3b56f-113">Regelbundet samlas SQL objekt in av DataParser.</span><span class="sxs-lookup"><span data-stu-id="3b56f-113">On a regular basis, SQL items are collected by the DataParser.</span></span> <span data-ttu-id="3b56f-114">DataParser konverterar även innehållet i ett meddelande till ett e-postmeddelandeformat.</span><span class="sxs-lookup"><span data-stu-id="3b56f-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="3b56f-115">Den SQL DataParser-koppling som du skapar i Microsoft 365 Efterlevnadscenter ansluter till DataParser och överför meddelandena till en säker Azure Storage i Microsoft-molnet.</span><span class="sxs-lookup"><span data-stu-id="3b56f-115">The SQL DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="3b56f-116">En undermapp i mappen Inkorgen **med namnet SQL DataParser** skapas i användarnas postlådor och SQL importeras till den mappen.</span><span class="sxs-lookup"><span data-stu-id="3b56f-116">A subfolder in the Inbox folder named **SQL DataParser** is created in the user mailboxes, and the SQL items are imported to that folder.</span></span> <span data-ttu-id="3b56f-117">Kopplingen avgör vilken postlåda som objekt ska importeras till med hjälp av värdet för egenskapen *E-post.*</span><span class="sxs-lookup"><span data-stu-id="3b56f-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="3b56f-118">Alla SQL innehåller den här egenskapen, som fylls i med e-postadresserna för alla deltagare.</span><span class="sxs-lookup"><span data-stu-id="3b56f-118">Every SQL item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="3b56f-119">Innan du skapa en koppling</span><span class="sxs-lookup"><span data-stu-id="3b56f-119">Before you set up a connector</span></span>

- <span data-ttu-id="3b56f-120">Skapa ett DataParser-konto för Microsoft-kopplingar.</span><span class="sxs-lookup"><span data-stu-id="3b56f-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="3b56f-121">Det gör du genom att [kontakta 17a-4 LLC.](https://www.17a-4.com/contact/)</span><span class="sxs-lookup"><span data-stu-id="3b56f-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="3b56f-122">Du måste logga in på det här kontot när du skapar kopplingen i steg 1.</span><span class="sxs-lookup"><span data-stu-id="3b56f-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="3b56f-123">Den användare som skapar SQL DataParser-koppling i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3b56f-123">The user who creates the SQL DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="3b56f-124">Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="3b56f-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="3b56f-125">Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3b56f-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="3b56f-126">Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3b56f-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="3b56f-127">Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="3b56f-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="3b56f-128">Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="3b56f-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-sql-dataparser-connector"></a><span data-ttu-id="3b56f-129">Steg 1: Konfigurera en SQL DataParser-koppling</span><span class="sxs-lookup"><span data-stu-id="3b56f-129">Step 1: Set up a SQL DataParser connector</span></span>

<span data-ttu-id="3b56f-130">Det första steget är att få åtkomst till sidan Datakopplingar i Microsoft 365 Efterlevnadscenter och skapa en 17a-4-koppling för SQL data.</span><span class="sxs-lookup"><span data-stu-id="3b56f-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for SQL data.</span></span>

1. <span data-ttu-id="3b56f-131">Gå till <https://compliance.microsoft.com> och klicka på **Datakopplingar**  >  **SQL DataParser**.</span><span class="sxs-lookup"><span data-stu-id="3b56f-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **SQL DataParser**.</span></span>

2. <span data-ttu-id="3b56f-132">På sidan **SQL DataParser produktbeskrivning** klickar du på Lägg **till koppling**.</span><span class="sxs-lookup"><span data-stu-id="3b56f-132">On the **SQL DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="3b56f-133">Klicka på **Acceptera på** sidan **Användningsvillkor.**</span><span class="sxs-lookup"><span data-stu-id="3b56f-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="3b56f-134">Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="3b56f-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="3b56f-135">Logga in på ditt 17a-4-konto och slutför stegen SQL i guiden DataParser-anslutning.</span><span class="sxs-lookup"><span data-stu-id="3b56f-135">Sign in to your 17a-4 account and complete the steps in the SQL DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-sql-dataparser-connector"></a><span data-ttu-id="3b56f-136">Steg 2: Konfigurera SQL DataParser-koppling</span><span class="sxs-lookup"><span data-stu-id="3b56f-136">Step 2: Configure the SQL DataParser connector</span></span>

<span data-ttu-id="3b56f-137">Arbeta med 17a-4 Support för att konfigurera SQL DataParser-koppling.</span><span class="sxs-lookup"><span data-stu-id="3b56f-137">Work with 17a-4 Support to configure the SQL DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="3b56f-138">Steg 3: Mappa användare</span><span class="sxs-lookup"><span data-stu-id="3b56f-138">Step 3: Map users</span></span>

<span data-ttu-id="3b56f-139">Med SQL DataParser-koppling mappas användare automatiskt till sina e Microsoft 365 adresser innan data importeras till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b56f-139">The SQL DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-sql-dataparser-connector"></a><span data-ttu-id="3b56f-140">Steg 4: Övervaka SQL med DataParser-kopplingen</span><span class="sxs-lookup"><span data-stu-id="3b56f-140">Step 4: Monitor the SQL DataParser connector</span></span>

<span data-ttu-id="3b56f-141">När du har SQL en DataParser-koppling kan du visa kopplingsstatusen i Microsoft 365 Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="3b56f-141">After you create a SQL DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="3b56f-142">Gå till <https://compliance.microsoft.com> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.</span><span class="sxs-lookup"><span data-stu-id="3b56f-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="3b56f-143">Klicka på **fliken Kopplingar** och välj sedan den SQL DataParser-koppling som du har skapat för att visa den utfällbar sida som innehåller egenskaper och information om kopplingen.</span><span class="sxs-lookup"><span data-stu-id="3b56f-143">Click the **Connectors** tab and then select the SQL DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="3b56f-144">Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen.</span><span class="sxs-lookup"><span data-stu-id="3b56f-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="3b56f-145">Den här loggen innehåller data som har importerats till Microsoft-molnet.</span><span class="sxs-lookup"><span data-stu-id="3b56f-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="3b56f-146">Kända problem</span><span class="sxs-lookup"><span data-stu-id="3b56f-146">Known issues</span></span>

<span data-ttu-id="3b56f-147">För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB.</span><span class="sxs-lookup"><span data-stu-id="3b56f-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="3b56f-148">Stöd för större objekt blir tillgängligt vid ett senare tillfälle.</span><span class="sxs-lookup"><span data-stu-id="3b56f-148">Support for larger items will be available at a later date.</span></span>
