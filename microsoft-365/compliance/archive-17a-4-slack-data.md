---
title: Konfigurera en koppling för att arkivera slackdata i Microsoft 365
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
description: Lär dig att konfigurera och använda en dataparserkoppling med 17a-4 slack för att importera och arkivera slackdata i Microsoft 365.
ms.openlocfilehash: 0eb9564ac5a6e8a3fa76cf1a336f266a456b272a
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53097171"
---
# <a name="set-up-a-connector-to-archive-slack-data-preview"></a><span data-ttu-id="7ad08-103">Konfigurera en koppling för att arkivera slackdata (förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="7ad08-103">Set up a connector to archive Slack data (preview)</span></span>

<span data-ttu-id="7ad08-104">Använd [DataParser från 17a-4 LLC](https://www.17a-4.com/slack-dataparser/) till att importera och arkivera data från slackplattformen till användarpostlådor i Microsoft 365 organisation.</span><span class="sxs-lookup"><span data-stu-id="7ad08-104">Use [DataParser from 17a-4 LLC](https://www.17a-4.com/slack-dataparser/) to import and archive data from the Slack platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="7ad08-105">DataParser innehåller en slackkoppling som är konfigurerad för att hämta objekt från en datakälla från tredje part och importera objekten till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7ad08-105">DataParser includes a Slack connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="7ad08-106">Kopplingen Slackdataparser konverterar slackdata till ett e-postmeddelandeformat och importerar sedan dessa objekt till användarpostlådor i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7ad08-106">The Slack DataParser connector converts Slack data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="7ad08-107">När slackdata har lagrats i användarpostlådor kan du använda efterlevnadsfunktioner Microsoft 365 till exempel Bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter samt kommunikationsefterlevnad.</span><span class="sxs-lookup"><span data-stu-id="7ad08-107">After Slack data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="7ad08-108">Genom att använda en slackkoppling för att importera och arkivera data i Microsoft 365 kan det hjälpa din organisation att följa myndighets- och regleringsprinciper.</span><span class="sxs-lookup"><span data-stu-id="7ad08-108">Using a Slack connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-slack-data"></a><span data-ttu-id="7ad08-109">Översikt över arkivering av slackdata</span><span class="sxs-lookup"><span data-stu-id="7ad08-109">Overview of archiving Slack data</span></span>

<span data-ttu-id="7ad08-110">I följande översikt beskrivs hur du använder en datakoppling för att arkivera slackdata i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7ad08-110">The following overview explains the process of using a data connector to archive Slack data in Microsoft 365.</span></span>

![Arkivering av arbetsflöde för slackdata från 17a-4](../media/SlackDataParserConnectorWorkflow.png)

1. <span data-ttu-id="7ad08-112">Din organisation arbetar med 17a-4 för att konfigurera och konfigurera Slack-dataparser.</span><span class="sxs-lookup"><span data-stu-id="7ad08-112">Your organization works with 17a-4 to set up and configure the Slack DataParser.</span></span>

2. <span data-ttu-id="7ad08-113">Slackobjekt samlas in regelbundet av DataParser.</span><span class="sxs-lookup"><span data-stu-id="7ad08-113">On a regular basis, Slack items are collected by the DataParser.</span></span> <span data-ttu-id="7ad08-114">DataParser konverterar även innehållet i ett meddelande till ett e-postmeddelandeformat.</span><span class="sxs-lookup"><span data-stu-id="7ad08-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="7ad08-115">Kopplingen slackdataparser som du skapar i Microsoft 365 Efterlevnadscenter ansluter till DataParser och överför meddelanden till en säker Azure Storage i Microsoft-molnet.</span><span class="sxs-lookup"><span data-stu-id="7ad08-115">The Slack DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="7ad08-116">En undermapp i mappen Inkorgen med namnet **Slack dataparser** skapas i användarnas postlådor och slackobjekten importeras till den mappen.</span><span class="sxs-lookup"><span data-stu-id="7ad08-116">A subfolder in the Inbox folder named **Slack DataParser** is created in the user mailboxes, and the Slack items are imported to that folder.</span></span> <span data-ttu-id="7ad08-117">Kopplingen avgör vilken postlåda som objekt ska importeras till med hjälp av värdet för egenskapen *E-post.*</span><span class="sxs-lookup"><span data-stu-id="7ad08-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="7ad08-118">Varje slackobjekt innehåller den här egenskapen, som fylls i med e-postadresserna för alla deltagare.</span><span class="sxs-lookup"><span data-stu-id="7ad08-118">Every Slack item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="7ad08-119">Innan du skapa en koppling</span><span class="sxs-lookup"><span data-stu-id="7ad08-119">Before you set up a connector</span></span>

- <span data-ttu-id="7ad08-120">Skapa ett DataParser-konto för Microsoft-kopplingar.</span><span class="sxs-lookup"><span data-stu-id="7ad08-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="7ad08-121">Det gör du genom att [kontakta 17a-4 LLC.](https://www.17a-4.com/contact/)</span><span class="sxs-lookup"><span data-stu-id="7ad08-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="7ad08-122">Du måste logga in på det här kontot när du skapar kopplingen i steg 1.</span><span class="sxs-lookup"><span data-stu-id="7ad08-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="7ad08-123">Den användare som skapar slackdataparserkopplingen i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7ad08-123">The user who creates the Slack DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="7ad08-124">Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="7ad08-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="7ad08-125">Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7ad08-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="7ad08-126">Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7ad08-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="7ad08-127">Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="7ad08-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="7ad08-128">Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="7ad08-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-slack-dataparser-connector"></a><span data-ttu-id="7ad08-129">Steg 1: Konfigurera en slackdataparserkoppling</span><span class="sxs-lookup"><span data-stu-id="7ad08-129">Step 1: Set up a Slack DataParser connector</span></span>

<span data-ttu-id="7ad08-130">Det första steget är att komma åt sidan Datakopplingar i Microsoft 365 Efterlevnadscenter och skapa en 17a-4-koppling för slackdata.</span><span class="sxs-lookup"><span data-stu-id="7ad08-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for Slack data.</span></span>

1. <span data-ttu-id="7ad08-131">Gå till <https://compliance.microsoft.com> och klicka sedan på **Datakopplingar**  >  **Slack Dataparser**.</span><span class="sxs-lookup"><span data-stu-id="7ad08-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **Slack DataParser**.</span></span>

2. <span data-ttu-id="7ad08-132">På sidan **Slack DataParser produktbeskrivning** klickar du på Lägg **till koppling**.</span><span class="sxs-lookup"><span data-stu-id="7ad08-132">On the **Slack DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="7ad08-133">Klicka på **Acceptera på** sidan **Användningsvillkor.**</span><span class="sxs-lookup"><span data-stu-id="7ad08-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="7ad08-134">Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="7ad08-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="7ad08-135">Logga in på ditt 17a-4-konto och utför stegen i guiden Slack DataParser-anslutning.</span><span class="sxs-lookup"><span data-stu-id="7ad08-135">Sign in to your 17a-4 account and complete the steps in the Slack DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-slack-dataparser-connector"></a><span data-ttu-id="7ad08-136">Steg 2: Konfigurera dataparserkopplingen för slack</span><span class="sxs-lookup"><span data-stu-id="7ad08-136">Step 2: Configure the Slack DataParser connector</span></span>

<span data-ttu-id="7ad08-137">Konfigurera dataparserkopplingen slack med stöd för 17a-4.</span><span class="sxs-lookup"><span data-stu-id="7ad08-137">Work with 17a-4 Support to configure the Slack DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="7ad08-138">Steg 3: Mappa användare</span><span class="sxs-lookup"><span data-stu-id="7ad08-138">Step 3: Map users</span></span>

<span data-ttu-id="7ad08-139">Kopplingen Slackdataparser mappar automatiskt användare till sina e Microsoft 365 adresser innan data importeras till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7ad08-139">The Slack DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-slack-dataparser-connector"></a><span data-ttu-id="7ad08-140">Steg 4: Övervaka dataparserkopplingen med slack</span><span class="sxs-lookup"><span data-stu-id="7ad08-140">Step 4: Monitor the Slack DataParser connector</span></span>

<span data-ttu-id="7ad08-141">När du har skapat en dataparserkoppling med slack kan du visa kopplingsstatusen i Microsoft 365 Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="7ad08-141">After you create a Slack DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="7ad08-142">Gå till <https://compliance.microsoft.com> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.</span><span class="sxs-lookup"><span data-stu-id="7ad08-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="7ad08-143">Klicka på **fliken Kopplingar** och välj sedan slackdataparserkopplingen som du har skapat för att visa den utfällbar sida som innehåller egenskaper och information om kopplingen.</span><span class="sxs-lookup"><span data-stu-id="7ad08-143">Click the **Connectors** tab and then select the Slack DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="7ad08-144">Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen.</span><span class="sxs-lookup"><span data-stu-id="7ad08-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="7ad08-145">Den här loggen innehåller data som har importerats till Microsoft-molnet.</span><span class="sxs-lookup"><span data-stu-id="7ad08-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="7ad08-146">Kända problem</span><span class="sxs-lookup"><span data-stu-id="7ad08-146">Known issues</span></span>

<span data-ttu-id="7ad08-147">För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB.</span><span class="sxs-lookup"><span data-stu-id="7ad08-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="7ad08-148">Stöd för större objekt blir tillgängligt vid ett senare tillfälle.</span><span class="sxs-lookup"><span data-stu-id="7ad08-148">Support for larger items will be available at a later date.</span></span>
