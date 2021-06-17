---
title: Konfigurera händelsehubben
description: Lär dig hur du konfigurerar händelsehubben
keywords: händelsenav, konfigurera, insikter
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.openlocfilehash: d28ad22721e22dfd0dc5962bd46bab2b45469781
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985666"
---
# <a name="configure-your-event-hub"></a><span data-ttu-id="44fb1-104">Konfigurera händelsehubben</span><span class="sxs-lookup"><span data-stu-id="44fb1-104">Configure your Event Hub</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="44fb1-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="44fb1-105">**Applies to:**</span></span>
- [<span data-ttu-id="44fb1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="44fb1-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="44fb1-107">Lär dig hur du konfigurerar händelsehubben så att det kan mata in händelser från Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="44fb1-107">Learn how to configure your Event Hub so that it can ingest events from Microsoft 365 Defender.</span></span>


## <a name="setup-the-required-resource-provider-in-the-event-hub-subscription"></a><span data-ttu-id="44fb1-108">Konfigurera den nödvändiga resursleverantören i prenumerationen på Händelsehubben</span><span class="sxs-lookup"><span data-stu-id="44fb1-108">Setup the required Resource Provider in the Event Hub subscription</span></span>


1. <span data-ttu-id="44fb1-109">Logga in på [Azure-portalen](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="44fb1-109">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
1. <span data-ttu-id="44fb1-110">Välj **Prenumerationer { Välj den prenumeration som \> ***händelsehubben ska distribueras till***} \> Resursleverantörer**.</span><span class="sxs-lookup"><span data-stu-id="44fb1-110">Select **Subscriptions \> {***Select the subscription the event hub will be deployed to***} \> Resource providers**.</span></span>
1. <span data-ttu-id="44fb1-111">Kontrollera att **Microsoft.Insights** providern är registrerad.</span><span class="sxs-lookup"><span data-stu-id="44fb1-111">Verify that the **Microsoft.Insights** Provider is registered.</span></span> <span data-ttu-id="44fb1-112">Registrera det annars.</span><span class="sxs-lookup"><span data-stu-id="44fb1-112">Otherwise, register it.</span></span>

![Bild av resursleverantörer i Microsoft Azure](../../media/f893db7a7b1f7aa520e8b9257cc72562.png)

## <a name="setup-azure-active-directory-app-registration"></a><span data-ttu-id="44fb1-114">Konfigurera Azure Active Directory för appar</span><span class="sxs-lookup"><span data-stu-id="44fb1-114">Setup Azure Active Directory App Registration</span></span>


><span data-ttu-id="44fb1-115">! [OBS] Du måste ha administratörsroll eller Azure Active Directory (AAD) måste vara inställd på att tillåta icke-administratörer att registrera appar.</span><span class="sxs-lookup"><span data-stu-id="44fb1-115">![NOTE] You must have Administrator role or Azure Active Directory (AAD) must be set to allow non-Administrators to register apps.</span></span> <span data-ttu-id="44fb1-116">Du måste också ha rollen Ägare eller Administratör för användaråtkomst för att tilldela tjänstens huvudroll.</span><span class="sxs-lookup"><span data-stu-id="44fb1-116">You must also have an Owner or User Access Administrator role to assign the service principal a role.</span></span>  
><span data-ttu-id="44fb1-117">Mer information finns i Skapa [en Azure AD-app & tjänstens huvudnamn i portalen – Microsofts identitetsplattform \| Microsoft Docs.](/azure/active-directory/develop/howto-create-service-principal-portal)</span><span class="sxs-lookup"><span data-stu-id="44fb1-117">For more information, see [Create an Azure AD app & service principal in the portal - Microsoft identity platform \| Microsoft Docs](/azure/active-directory/develop/howto-create-service-principal-portal).</span></span>

1. <span data-ttu-id="44fb1-118">Skapa en ny registrering (som på ett sätt skapar ett tjänsthuvudnamn) **Azure Active Directory \> appregistreringar \> Ny registrering.**</span><span class="sxs-lookup"><span data-stu-id="44fb1-118">Create a new registration (which inherently creates a service principal) in **Azure Active Directory \> App registrations \> New registration.**</span></span>

1. <span data-ttu-id="44fb1-119">Fyll i formuläret med bara namnet (ingen Omdirigerings-URI krävs).</span><span class="sxs-lookup"><span data-stu-id="44fb1-119">Fill out the form with just the Name (no Redirect URI is required).</span></span>

    ![Bild på att registrera en ansökan](../../media/336bc84e6be23900c43232b4ef0c253c.png)

    ![Bild av översiktsinformation](../../media/06ac04c4ff713c2065cec2ef2f99a294.png)

1. <span data-ttu-id="44fb1-122">Skapa en hemlig genom att klicka på **Certifikat & hemligheter Ny \> klienthemlighet:**</span><span class="sxs-lookup"><span data-stu-id="44fb1-122">Create a secret by clicking on **Certificates & secrets \> New client secret**:</span></span>

    ![Bild av certifikat och hemligheter](../../media/d2ef88d3d2310d2c60c294b569cdf02e.png)

>[!WARNING]
><span data-ttu-id="44fb1-124">**Du kommer inte att kunna komma åt klienthemligheten igen, så se till att spara den**.</span><span class="sxs-lookup"><span data-stu-id="44fb1-124">**You won't be able to access the client secret again so make sure to save it**.</span></span>

## <a name="setup-event-hub-namespace"></a><span data-ttu-id="44fb1-125">Namnområde för konfigurationshändelsehubben</span><span class="sxs-lookup"><span data-stu-id="44fb1-125">Setup Event Hub namespace</span></span>


1. <span data-ttu-id="44fb1-126">Skapa ett namnområde i händelsehubben:</span><span class="sxs-lookup"><span data-stu-id="44fb1-126">Create an Event Hub Namespace:</span></span>

    <span data-ttu-id="44fb1-127">Gå **till Händelsehubben \> Lägg** till och välj prissättningsnivå, dataflödesenheter och automatisk härdning (kräver standardpris och under funktioner) som är lämpliga för den belastning du förväntar dig.</span><span class="sxs-lookup"><span data-stu-id="44fb1-127">Go **to Event Hubs \> Add** and select the pricing tier, throughput units and Auto-Inflate (requires standard pricing and under features) appropriate for the load you are expecting.</span></span>  
    <span data-ttu-id="44fb1-128">Mer information finns i [Priser – evenemangshubben \| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="44fb1-128">For more information, see [Pricing - Event Hubs \| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)</span></span>

    >[!NOTE]
    > <span data-ttu-id="44fb1-129">Du kan använda ett befintligt händelsenav, men dataflödet och skalningen är inställda på namnområdesnivå, så vi rekommenderar att placera ett händelsenav i dess namnområde.</span><span class="sxs-lookup"><span data-stu-id="44fb1-129">You can use an existing event hub, but the throughput and scaling are set at the namespace level so it is recommended to place an event hub in itsown namespace.</span></span>

   ![Bild av namnutrymmet i händelsehubben](../../media/ebc4ca37c342ad1da75c4aee4018e51a.png)

1. <span data-ttu-id="44fb1-131">Du behöver också resurs-ID för namnområdet i händelsehubben.</span><span class="sxs-lookup"><span data-stu-id="44fb1-131">You will also need the Resource ID of this Event Hub Namespace.</span></span> <span data-ttu-id="44fb1-132">Gå till namnområdessidan i Azure Event \> Hubs.</span><span class="sxs-lookup"><span data-stu-id="44fb1-132">Go to your Azure Event Hubs namespace page \> Properties.</span></span> <span data-ttu-id="44fb1-133">Kopiera texten under Resurs-ID och registrera den för användning i avsnittet M365-konfiguration nedan.</span><span class="sxs-lookup"><span data-stu-id="44fb1-133">Copy the text under Resource ID and record it for use during the M365 Configuration section below.</span></span> 

    ![Bild av egenskaper](../../media/759498162a4e93cbf17c4130d704d164.png)

1. <span data-ttu-id="44fb1-135">När namnområdet för händelsehubben har skapats måste du lägga till Tjänstens huvudnamn för appregistrering som läsare, Azure Event Hubs Data Receiver och användaren som ska logga in på Microsoft 365 Defender som deltagare (detta kan också göras på resursgrupp- eller prenumerationsnivå).</span><span class="sxs-lookup"><span data-stu-id="44fb1-135">Once the Event Hub Namespace is created you will need to add the App Registration Service Principal as Reader, Azure Event Hubs Data Receiver, and the user who will be logging into Microsoft 365 Defender as Contributor (this can also be done at Resource Group or Subscription level).</span></span>

    <span data-ttu-id="44fb1-136">Detta görs i **IAM (Namespace Access Control) i Event \> Hubs Namespace Access Control (IAM) \> Add** and verify under **Role assignments:**</span><span class="sxs-lookup"><span data-stu-id="44fb1-136">This is done in **Event Hubs Namespace \> Access Control (IAM) \> Add** and verify under **Role assignments**:</span></span>

    ![Bild på åtkomstkontroll](../../media/9c9c29137b90d5858920202d87680d16.png)

## <a name="setup-event-hub"></a><span data-ttu-id="44fb1-138">Konfigurera händelsehubben</span><span class="sxs-lookup"><span data-stu-id="44fb1-138">Setup Event Hub</span></span>


<span data-ttu-id="44fb1-139">**Alternativ 1:**</span><span class="sxs-lookup"><span data-stu-id="44fb1-139">**Option 1:**</span></span>

<span data-ttu-id="44fb1-140">Du kan skapa ett händelsenav  i namnområdet och alla händelsetyper (tabeller) du väljer att exportera skrivs till det **här händelsehubben.**</span><span class="sxs-lookup"><span data-stu-id="44fb1-140">You can create an Event Hub within your Namespace and **all** the Event Types (Tables) you select to export will be written into this **one** Event Hub.</span></span>

<span data-ttu-id="44fb1-141">**Alternativ 2:**</span><span class="sxs-lookup"><span data-stu-id="44fb1-141">**Option 2:**</span></span>

<span data-ttu-id="44fb1-142">I stället för att exportera alla händelsetyper (tabeller) till ett händelsenav kan du exportera varje tabell till ett annat händelsenav i namnområdet i händelsehubben (ett händelsenav per händelsetyp).</span><span class="sxs-lookup"><span data-stu-id="44fb1-142">Instead of exporting all the Event Types (Tables) into one Event Hub, you can export each table into a different Event Hub inside your Event Hub Namespace (one Event Hub per Event Type).</span></span>  

<span data-ttu-id="44fb1-143">Med det här alternativet Microsoft 365 Defender händelsehubben åt dig.</span><span class="sxs-lookup"><span data-stu-id="44fb1-143">In this option, Microsoft 365 Defender will create Event Hubs for you.</span></span>  
>[!NOTE]
> <span data-ttu-id="44fb1-144">Om du använder ett namnområde  för händelsehubben som inte ingår i ett händelsenavskluster kan du bara välja upp till 10 händelsetyper (tabeller) att exportera i varje export-Inställningar som du definierar, på grund av en Azure-begränsning på 10 händelsehubben per namnområde i händelsehubben.</span><span class="sxs-lookup"><span data-stu-id="44fb1-144">If you are using an Event Hub Namespace that is **not** part of an Event Hub Cluster, you will only be able to choose up to 10 Event Types (Tables) to export in each Export Settings you define, due to an Azure limitation of 10 Event Hubs per Event Hub Namespace.</span></span>

<span data-ttu-id="44fb1-145">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="44fb1-145">For example:</span></span>

![Bild av exempel på händelsehubben](../../media/005c1f6c10c34420d387f594987f9ffe.png)

<span data-ttu-id="44fb1-147">Om du väljer det här alternativet kan du gå till avsnittet Konfigurera [e-Microsoft 365 Defender ska skicka e-posttabeller.](#configure-microsoft-365-defender-to-send-email-tables)</span><span class="sxs-lookup"><span data-stu-id="44fb1-147">If you choose this option, you can skip to the [Configure Microsoft 365 Defender to send email tables](#configure-microsoft-365-defender-to-send-email-tables) section.</span></span>

<span data-ttu-id="44fb1-148">Skapa ett händelsehubben i namnområdet genom att välja **Händelsehubben \> + Händelsehubben.**</span><span class="sxs-lookup"><span data-stu-id="44fb1-148">Create an Event Hub within your Namespace by selecting **Event Hubs \> + Event Hub**.</span></span>

<span data-ttu-id="44fb1-149">Partition Count tillåter ytterligare dataflöde via parallellitet, så vi rekommenderar att öka detta tal baserat på den belastning du förväntar dig.</span><span class="sxs-lookup"><span data-stu-id="44fb1-149">The Partition Count allows for additional throughput via parallelism, so it is recommended to increase this number based on the load you are expecting.</span></span>  
<span data-ttu-id="44fb1-150">Standardvärdena För lagring av meddelanden och Spara med värdena 1 och Av rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="44fb1-150">Default Message Retention and Capture values of 1 and Off are recommended.</span></span>

![Bild av Skapa händelsehubben](../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png)

<span data-ttu-id="44fb1-152">För det här händelsehubben (inte namnområde) måste du konfigurera en princip för delad åtkomst med Skicka, lyssna på anspråk.</span><span class="sxs-lookup"><span data-stu-id="44fb1-152">For this Event Hub (not namespace) you will need to configure a Shared Access Policy with Send, Listen Claims.</span></span> <span data-ttu-id="44fb1-153">Klicka på principer för delad åtkomst i händelsehubben **\> \> +** Lägg till och ge den sedan ett principnamn (används inte någon annanstans) och markera **Skicka** och **lyssna**.</span><span class="sxs-lookup"><span data-stu-id="44fb1-153">Click on your **Event Hub \> Shared access policies \> + Add** and then give it a Policy name (not used elsewhere) and check **Send** and **Listen**.</span></span>

![Bild av principer för delad åtkomst](../../media/1867d13f46dc6a0f4cdae6cf00df24db.png)

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a><span data-ttu-id="44fb1-155">Konfigurera e Microsoft 365 Defender att skicka e-posttabeller</span><span class="sxs-lookup"><span data-stu-id="44fb1-155">Configure Microsoft 365 Defender to send email tables</span></span>


### <a name="setup-microsoft-365-defender-send-email-tables-to-splunk-via-event-hub"></a><span data-ttu-id="44fb1-156">Setup Microsoft 365 Defender send Email tables to Splunk via Event Hub</span><span class="sxs-lookup"><span data-stu-id="44fb1-156">Setup Microsoft 365 Defender send Email tables to Splunk via Event Hub</span></span>


1. <span data-ttu-id="44fb1-157">Logga in Microsoft 365 Defender logga <https://security.microsoft.com> in på med ett konto som uppfyller alla följande rollkrav:</span><span class="sxs-lookup"><span data-stu-id="44fb1-157">Login to Microsoft 365 Defender at <https://security.microsoft.com> with an account that meets all the following role requirements:</span></span>

    - <span data-ttu-id="44fb1-158">Deltagarroll på *namnområdets resursnivå* i händelsehubben eller högre för händelsehubben som du ska exportera till.</span><span class="sxs-lookup"><span data-stu-id="44fb1-158">Contributor role at the Event Hub *Namespace* Resource level or higher for the Event Hub that you will be exporting to.</span></span> <span data-ttu-id="44fb1-159">Utan detta får du ett exportfel när du försöker spara inställningarna.</span><span class="sxs-lookup"><span data-stu-id="44fb1-159">Without this you will get an export error when you try to save the settings.</span></span>

    - <span data-ttu-id="44fb1-160">Global administratör eller säkerhetsadministratörsroll i klientorganisationens knutna till Microsoft 365 Defender och Azure.</span><span class="sxs-lookup"><span data-stu-id="44fb1-160">Global Admin or Security Admin Role on the tenant tied to Microsoft 365 Defender and Azure.</span></span>

    ![Bild på säkerhetsportalen](../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png)

1. <span data-ttu-id="44fb1-162">Klicka på **Raw Data Export \> +Add.**</span><span class="sxs-lookup"><span data-stu-id="44fb1-162">Click on **Raw Data Export \> +Add**.</span></span>

    <span data-ttu-id="44fb1-163">Nu kommer du att använda de data som du har spelat in ovan.</span><span class="sxs-lookup"><span data-stu-id="44fb1-163">You will now use the data that your recorded above.</span></span>

    <span data-ttu-id="44fb1-164">**Namn:** Det här är lokalt och ska vara det som fungerar i din miljö.</span><span class="sxs-lookup"><span data-stu-id="44fb1-164">**Name**: This is local and should be whatever works in your environment.</span></span>

    <span data-ttu-id="44fb1-165">**Vidarebefordra händelser till händelsehubben**: Markera den här kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="44fb1-165">**Forward events to event hub**: Select this checkbox.</span></span>

    <span data-ttu-id="44fb1-166">**Händelse-Hubbens resurs-ID:** Det här är namnområdets namnområdes-ID för händelsehubben som du registrerade ovan när du konfigurerade händelsehubben.</span><span class="sxs-lookup"><span data-stu-id="44fb1-166">**Event-Hub Resource ID**: This is the Event Hub Namespace Resource ID you  recorded above when you setup the Event Hub.</span></span>

    <span data-ttu-id="44fb1-167">**Event-Hub-namn:** Om du har skapat ett händelsenav i namnområdet för händelsehubben klistrar du in namnet på händelsehubben som du spelade in ovan.</span><span class="sxs-lookup"><span data-stu-id="44fb1-167">**Event-Hub name**:  If you created an Event Hub inside your Event Hub Namespace, paste the Event Hub  name you recorded above.</span></span>

    <span data-ttu-id="44fb1-168">Om du väljer att låta Microsoft 365 Defender skapa händelsehubben per händelsetyper (tabeller) lämnar du det här fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="44fb1-168">If you choose to let Microsoft 365 Defender to create Event Hubs per Event Types  (Tables) for you, leave this field empty.</span></span>

    <span data-ttu-id="44fb1-169">**Händelsetyper:** Välj de tabeller för avancerad sökning som du vill vidarebefordra till Händelsehubben och sedan vidare till den anpassade appen.</span><span class="sxs-lookup"><span data-stu-id="44fb1-169">**Event Types**: Select the Advanced Hunting tables that you want to forward to the Event Hub and then on to your custom app.</span></span> <span data-ttu-id="44fb1-170">Aviseringstabellerna är Microsoft 365 Defender, Enheter-tabeller är från Microsoft Defender för Slutpunkt (Identifiering och åtgärd på slutpunkt) och E-posttabeller är från Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="44fb1-170">Alert tables are from Microsoft 365 Defender, Devices tables are from Microsoft Defender for Endpoint (EDR), and Email tables are from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="44fb1-171">E-posthändelser registrerar alla e-posttransaktioner.</span><span class="sxs-lookup"><span data-stu-id="44fb1-171">Email Events records all Email Transactions.</span></span> <span data-ttu-id="44fb1-172">URL-adressen (SafeLinks), Attachment (Valv Attachments) och POST Delivery Events (ZAP) registreras också och kan kopplas till e-posthändelser i fältet NetworkMessageId.</span><span class="sxs-lookup"><span data-stu-id="44fb1-172">The URL (SafeLinks), Attachment (Safe Attachments) and Post Delivery Events (ZAP) are also recorded and can be joined to the Email Events on the NetworkMessageId field.</span></span>

    ![Bild på inställningar för direktuppspelnings-API](../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png)

1. <span data-ttu-id="44fb1-174">Se till att klicka på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="44fb1-174">Make sure to click **Submit**.</span></span>

### <a name="verify-that-the-events-are-being-exported-to-the-event-hub"></a><span data-ttu-id="44fb1-175">Kontrollera att händelserna exporteras till händelsehubben</span><span class="sxs-lookup"><span data-stu-id="44fb1-175">Verify that the events are being exported to the Event Hub</span></span>


<span data-ttu-id="44fb1-176">Du kan kontrollera att händelser skickas till Händelsehubben genom att köra en grundläggande avancerad fråga för sökning.</span><span class="sxs-lookup"><span data-stu-id="44fb1-176">You can verify that events are being sent to the Event Hub by running a basic Advanced Hunting query.</span></span> <span data-ttu-id="44fb1-177">Välj **Söka avancerad fråga \> \> för** sökning och ange följande fråga:</span><span class="sxs-lookup"><span data-stu-id="44fb1-177">Select **Hunting \> Advanced Hunting \> Query** and enter the following query:</span></span>

```
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

<span data-ttu-id="44fb1-178">Det visar hur många e-postmeddelanden som togs emot den senaste timmen sammanfogade i alla andra tabeller.</span><span class="sxs-lookup"><span data-stu-id="44fb1-178">This will show you how many emails were received in the last hour joined across all the other tables.</span></span> <span data-ttu-id="44fb1-179">Du ser även om du ser händelser som kan exporteras till händelsehubben.</span><span class="sxs-lookup"><span data-stu-id="44fb1-179">It will also show you if you are seeing events that could be exported to the event hub.</span></span> <span data-ttu-id="44fb1-180">Om antalet visar 0 ser du inga data som kommer till händelsehubben.</span><span class="sxs-lookup"><span data-stu-id="44fb1-180">If this count shows 0 then you won't see any data going out to the Event Hub.</span></span>

![Bild på avancerad sökning](../../media/c305e57dc6f72fa9eb035943f244738e.png)

<span data-ttu-id="44fb1-182">När du har kontrollerat att det finns data att exportera kan du visa Händelsehubben för att verifiera att meddelandena är inkommande.</span><span class="sxs-lookup"><span data-stu-id="44fb1-182">Once you have verified there is data to export, you can view the Event Hub to verify that messages are incoming.</span></span> <span data-ttu-id="44fb1-183">Det kan ta upp till en timme.</span><span class="sxs-lookup"><span data-stu-id="44fb1-183">This can take up to one hour.</span></span> 
 
1. <span data-ttu-id="44fb1-184">I Azure går du till **Händelsehubben \> Klicka på \> namnområdeshändelsehubben \> Klicka på händelsehubben.**</span><span class="sxs-lookup"><span data-stu-id="44fb1-184">In Azure, go to **Event Hubs \> Click on the Namespace \> Event Hubs \> Click on the Event Hub**.</span></span>  
1. <span data-ttu-id="44fb1-185">Rulla **nedåt** under Översikt och i diagrammet Meddelanden bör du se Inkommande meddelanden.</span><span class="sxs-lookup"><span data-stu-id="44fb1-185">Under **Overview**, scroll down and in the Messages graph you should see Incoming Messages.</span></span> <span data-ttu-id="44fb1-186">Om du inte ser några resultat visas inga meddelanden för att mata in den anpassade appen.</span><span class="sxs-lookup"><span data-stu-id="44fb1-186">If you don't see any results, then there will be no messages for your custom app to ingest.</span></span>

    ![Bild på fliken Översikt med meddelanden](../../media/e88060e315d76e74269a3fc866df047f.png)
