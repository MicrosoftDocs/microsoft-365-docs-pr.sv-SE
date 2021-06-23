---
title: Konfigurera en koppling för att arkivera Cisco Webex-data i Microsoft 365
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
description: Lär dig att konfigurera och använda en 17a-4 Cisco Webex DataParser-koppling för att importera och arkivera Cisco Webex-data i Microsoft 365.
ms.openlocfilehash: 055152f2d566f7cfc32dac132a70bbaf63ceb503
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53097172"
---
# <a name="set-up-a-connector-to-archive-cisco-webex-data-preview"></a><span data-ttu-id="b5ba7-103">Konfigurera en koppling för att arkivera Cisco Webex-data (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="b5ba7-103">Set up a connector to archive Cisco Webex data (preview)</span></span>

<span data-ttu-id="b5ba7-104">Använd [Cisco Webex DataParser](https://www.17a-4.com/webex-dataparser/) från 17a-4 LLC för att importera och arkivera data från Cisco Cisco Webex-plattformen till användarpostlådor i Microsoft 365 organisation.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-104">Use the [Cisco Webex DataParser](https://www.17a-4.com/webex-dataparser/) from 17a-4 LLC to import and archive data from the Cisco Cisco Webex platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="b5ba7-105">DataParser innehåller en Cisco Webex-koppling som är konfigurerad för att hämta objekt från en datakälla från tredje part och importera objekten till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-105">The DataParser includes a Cisco Webex connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="b5ba7-106">Med Cisco Webex DataParser-kopplingen konverteras Cisco Webex-data till ett e-postmeddelandeformat och sedan importeras objekten till användarpostlådor i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-106">The Cisco Webex DataParser connector converts Cisco Webex data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="b5ba7-107">När Cisco Webex-data lagras i användarpostlådor kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel Bevarande av juridiska skäl, eDiscovery, bevarandeprinciper och bevarandeetiketter samt kommunikationsefterlevnad.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-107">After Cisco Webex data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="b5ba7-108">Med en Cisco Webex-anslutning för att importera och arkivera data i Microsoft 365 kan hjälpa din organisation att följa myndighets- och regelpolicyer.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-108">Using a Cisco Webex connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-cisco-webex-data"></a><span data-ttu-id="b5ba7-109">Översikt över arkivering av Cisco Webex-data</span><span class="sxs-lookup"><span data-stu-id="b5ba7-109">Overview of archiving Cisco Webex data</span></span>

<span data-ttu-id="b5ba7-110">Följande översikt förklarar processen med att använda en datakoppling för att arkivera Cisco Webex-data i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-110">The following overview explains the process of using a data connector to archive Cisco Webex data in Microsoft 365.</span></span>

![Arkivera arbetsflöde för Cisco Webex-data från 17a-4](../media/WebexTeamsDataParserConnectorWorkflow.png)

1. <span data-ttu-id="b5ba7-112">Din organisation arbetar med 17a-4 för att konfigurera och konfigurera Cisco Webex DataParser.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-112">Your organization works with 17a-4 to set up and configure the Cisco Webex DataParser.</span></span>

2. <span data-ttu-id="b5ba7-113">Cisco Webex-objekt samlas in regelbundet av DataParser.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-113">On a regular basis, Cisco Webex items are collected by the DataParser.</span></span> <span data-ttu-id="b5ba7-114">DataParser konverterar även innehållet i ett meddelande till ett e-postmeddelandeformat.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="b5ba7-115">Den Cisco Webex DataParser-koppling som du skapar i Microsoft 365 Efterlevnadscenter ansluter till DataParser och överför meddelandena till en säker Azure Storage plats i Microsoft-molnet.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-115">The Cisco Webex DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="b5ba7-116">En undermapp i mappen Inkorgen med namnet **Cisco Webex DataParser** skapas i användarpostlådorna och Cisco Webex-objekten importeras till den mappen.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-116">A subfolder in the Inbox folder named **Cisco Webex DataParser** is created in the user mailboxes, and the Cisco Webex items are imported to that folder.</span></span> <span data-ttu-id="b5ba7-117">Kopplingen avgör vilken postlåda som objekt ska importeras till med hjälp av värdet för egenskapen *E-post.*</span><span class="sxs-lookup"><span data-stu-id="b5ba7-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="b5ba7-118">Varje Cisco Webex-objekt innehåller den här egenskapen, som fylls i med e-postadresserna för alla deltagare.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-118">Every Cisco Webex item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="b5ba7-119">Innan du skapa en koppling</span><span class="sxs-lookup"><span data-stu-id="b5ba7-119">Before you set up a connector</span></span>

- <span data-ttu-id="b5ba7-120">Skapa ett DataParser-konto för Microsoft-kopplingar.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="b5ba7-121">Det gör du genom att [kontakta 17a-4 LLC.](https://www.17a-4.com/contact/)</span><span class="sxs-lookup"><span data-stu-id="b5ba7-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="b5ba7-122">Du måste logga in på det här kontot när du skapar kopplingen i steg 1.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="b5ba7-123">Användaren som skapar Cisco Webex DataParser-kopplingen i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-123">The user who creates the Cisco Webex DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="b5ba7-124">Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="b5ba7-125">Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="b5ba7-126">Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="b5ba7-127">Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="b5ba7-128">Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="b5ba7-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-cisco-webex-dataparser-connector"></a><span data-ttu-id="b5ba7-129">Steg 1: Konfigurera en Cisco Webex DataParser-koppling</span><span class="sxs-lookup"><span data-stu-id="b5ba7-129">Step 1: Set up a Cisco Webex DataParser connector</span></span>

<span data-ttu-id="b5ba7-130">Det första steget är att få åtkomst till sidan Datakopplingar i Microsoft 365 Efterlevnadscenter och skapa en 17a-4-koppling för Cisco Webex-data.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for Cisco Webex data.</span></span>

1. <span data-ttu-id="b5ba7-131">Gå till <https://compliance.microsoft.com> och klicka sedan på **Datakopplingar**  >  **Cisco Webex DataParser**.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **Cisco Webex DataParser**.</span></span>

2. <span data-ttu-id="b5ba7-132">På sidan **Cisco Webex DataParser produktbeskrivning** klickar du på Lägg **till koppling**.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-132">On the **Cisco Webex DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="b5ba7-133">Klicka på **Acceptera på** sidan **Användningsvillkor.**</span><span class="sxs-lookup"><span data-stu-id="b5ba7-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="b5ba7-134">Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="b5ba7-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="b5ba7-135">Logga in på ditt 17a-4-konto och slutför stegen i anslutningsguiden för Cisco Webex DataParser.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-135">Sign in to your 17a-4 account and complete the steps in the Cisco Webex DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-cisco-webex-dataparser-connector"></a><span data-ttu-id="b5ba7-136">Steg 2: Konfigurera Cisco Webex DataParser-kopplingen</span><span class="sxs-lookup"><span data-stu-id="b5ba7-136">Step 2: Configure the Cisco Webex DataParser connector</span></span>

<span data-ttu-id="b5ba7-137">Arbeta med 17a-4-stöd för att konfigurera Cisco Webex DataParser-kopplingen.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-137">Work with 17a-4 Support to configure the Cisco Webex DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="b5ba7-138">Steg 3: Mappa användare</span><span class="sxs-lookup"><span data-stu-id="b5ba7-138">Step 3: Map users</span></span>

<span data-ttu-id="b5ba7-139">Cisco Webex DataParser-kopplingen mappar automatiskt användare till sina Microsoft 365-postadresser innan de importerar data till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-139">The Cisco Webex DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-cisco-webex-dataparser-connector"></a><span data-ttu-id="b5ba7-140">Steg 4: Övervaka Cisco Webex DataParser-kopplingen</span><span class="sxs-lookup"><span data-stu-id="b5ba7-140">Step 4: Monitor the Cisco Webex DataParser connector</span></span>

<span data-ttu-id="b5ba7-141">När du har skapat en Cisco Webex DataParser-koppling kan du visa anslutningsstatusen i Microsoft 365 Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-141">After you create a Cisco Webex DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="b5ba7-142">Gå till <https://compliance.microsoft.com> och klicka på **Datakopplingar** i det vänstra navigeringsfältet.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="b5ba7-143">Klicka på **fliken Kopplingar** och välj sedan den Cisco Webex DataParser-koppling som du har skapat för att visa den utfällbar sida som innehåller egenskaper och information om kopplingen.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-143">Click the **Connectors** tab and then select the Cisco Webex DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="b5ba7-144">Under **Anslutningsstatus med källa** klickar du på länken Ladda ned **logg** för att öppna (eller spara) statusloggen för kopplingen.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="b5ba7-145">Den här loggen innehåller data som har importerats till Microsoft-molnet.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="b5ba7-146">Kända problem</span><span class="sxs-lookup"><span data-stu-id="b5ba7-146">Known issues</span></span>

<span data-ttu-id="b5ba7-147">För stunden går det inte att importera bifogade filer eller objekt som är större än 10 MB.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="b5ba7-148">Stöd för större objekt blir tillgängligt vid ett senare tillfälle.</span><span class="sxs-lookup"><span data-stu-id="b5ba7-148">Support for larger items will be available at a later date.</span></span>
