---
title: Använda Microsoft Teams-kurser i ditt system för utbildningshantering
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrera Microsoft Teams-kurser i ditt system för utbildningshantering
ms.openlocfilehash: 18d33225dd57932af20421c6b3b5dc4fe3b397b8
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327821"
---
# <a name="use-microsoft-teams-classes-in-your-learning-management-system"></a><span data-ttu-id="d1fe3-103">Använda Microsoft Teams-kurser i ditt system för utbildningshantering</span><span class="sxs-lookup"><span data-stu-id="d1fe3-103">Use Microsoft Teams classes in your Learning Management System</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1fe3-104">En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d1fe3-105">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="d1fe3-106">Microsoft Teams-klassteam är en LTI-app (Learning Tools Interoperability) som hjälper lärare och elever att enkelt navigera mellan sina LMS (Learning Management System) och Teams.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-106">Microsoft Teams class teams is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="d1fe3-107">Användare kan komma åt sina klassteam som är kopplade till kursen direkt från LMS.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="approve-the-app-in-the-microsoft-azure-tenant"></a><span data-ttu-id="d1fe3-108">Godkänna appen i Microsoft Azure-klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="d1fe3-108">Approve the app in the Microsoft Azure tenant</span></span>

<span data-ttu-id="d1fe3-109">Följande uppgifter slutförs av Microsoft Office 365-administratören och Blackboard Learn Ultra-administratören.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-109">The following tasks are completed by the Microsoft Office 365 admin and the Blackboard Learn Ultra admin.</span></span>

<span data-ttu-id="d1fe3-110">Innan du hanterar integreringen i Blackboard Learn Ultra måste Microsoft Office 365-administratören godkänna Blackboard **MSFT Teams** för Appen Lär dig Ultra Azure som institutions Microsoft Azure-klient.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-110">Before managing the integration within Blackboard Learn Ultra, the Microsoft Office 365 admin must approve the Blackboard **MSFT Teams for Learn Ultra Azure** app for the institution’s Microsoft Azure tenant.</span></span>

1. <span data-ttu-id="d1fe3-111">Hitta ditt klientorganisations-ID för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-111">Find your Microsoft Tenant ID.</span></span> <span data-ttu-id="d1fe3-112">Ta [reda på hur du hittar klientorganisationen.](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant)</span><span class="sxs-lookup"><span data-stu-id="d1fe3-112">See [how to find the tenant](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).</span></span>

2. <span data-ttu-id="d1fe3-113">Omdirigera slutpunkten för administratörsmedgivande för Microsoft-identitetsplattformen enligt följande exempel:</span><span class="sxs-lookup"><span data-stu-id="d1fe3-113">Redirect the Microsoft Identity Platform Admin Consent Endpoint according to the following example:</span></span>

   `https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

   > [!NOTE]
   > <span data-ttu-id="d1fe3-114">Ersätt {tenant} med din organisations Microsoft-klientorganisations-ID.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-114">Replace {tenant} with your organization’s Microsoft tenant ID.</span></span>

## <a name="register-the-integration-apps"></a><span data-ttu-id="d1fe3-115">Registrera integrationsapparna</span><span class="sxs-lookup"><span data-stu-id="d1fe3-115">Register the integration apps</span></span>

<span data-ttu-id="d1fe3-116">Som Blackboard Learn Ultra-administratör måste du registrera 2 LTI 1.3-integreringsappar i testmiljön:</span><span class="sxs-lookup"><span data-stu-id="d1fe3-116">As a Blackboard Learn Ultra admin, you'll need to register 2 LTI 1.3 integration apps within your Test environment:</span></span>

- <span data-ttu-id="d1fe3-117">Integreringen av Blackboard Learn Class Teams med stöd för synkronisering av deltagarlistan</span><span class="sxs-lookup"><span data-stu-id="d1fe3-117">The Blackboard Learn Class Teams integration to support the roster sync</span></span>

- <span data-ttu-id="d1fe3-118">LTI-appen för Microsoft Teams-klassteamet</span><span class="sxs-lookup"><span data-stu-id="d1fe3-118">The Microsoft Teams class team LTI app</span></span>

1. <span data-ttu-id="d1fe3-119">Notera följande LTI-klient-ID för båda apparna:</span><span class="sxs-lookup"><span data-stu-id="d1fe3-119">Make a note of the following LTI Client IDs for both Apps:</span></span>

    - <span data-ttu-id="d1fe3-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span><span class="sxs-lookup"><span data-stu-id="d1fe3-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span></span>

    - <span data-ttu-id="d1fe3-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span><span class="sxs-lookup"><span data-stu-id="d1fe3-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span></span>

2. <span data-ttu-id="d1fe3-122">Öppna administrationspanelen och leta upp **LTI-verktygsleverantörerna** under Integrations.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-122">Access the Admin Panel, and under **Integrations**, locate the LTI Tool Providers.</span></span>

   ![det här är dialogrutan för LTI-verktygsleverantör som visar en lista över leverantörer](../media/lti-media/lti-tool-providers.png)

3. <span data-ttu-id="d1fe3-124">Välj **Registrera LTI1.3/Advantage-verktyget**.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-124">Select **Register LTI1.3/Advantage Tool**.</span></span>

4. <span data-ttu-id="d1fe3-125">Ange det första klient-IDt som tillhandahålls (antingen Blackboard eller Microsoft) och välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-125">Enter the first of the Client IDs provided (either Blackboard or Microsoft), and select **Submit**.</span></span>

   ![LTI-registerverktyget med ett fält för att ange klient-ID](../media/lti-media/register-tool.png)

5. <span data-ttu-id="d1fe3-127">Granska de ifyllda inställningarna och kontrollera att verktygsstatusen har markerats som godkänd.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-127">Review the pre-populated settings and ensure that the tool status is marked as approved.</span></span>

6. <span data-ttu-id="d1fe3-128">Bläddra längst ned och välj sedan **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-128">Scroll to the bottom, and then select **Submit**.</span></span>

7. <span data-ttu-id="d1fe3-129">Upprepa föregående steg för att registrera den andra av LTI-apparna i din miljö.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-129">Repeat the previous steps to register the second of the LTI apps within your environment.</span></span>

## <a name="set-up-the-rest-application-and-cross-origin-resource-sharing"></a><span data-ttu-id="d1fe3-130">Konfigurera resursdelning för REST-program och resursdelning mellan ursprung</span><span class="sxs-lookup"><span data-stu-id="d1fe3-130">Set up the REST Application and Cross Origin Resource Sharing</span></span>

<span data-ttu-id="d1fe3-131">Blackboard Learn Ultra-administratören måste också konfigurera konfigurationen REST-program och Resursdelning mellan ursprung.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-131">The Blackboard Learn Ultra admin will also need to configure the REST Application and the Cross Origin Resource Sharing configuration.</span></span>

<span data-ttu-id="d1fe3-132">Fyll i följande för att konfigurera REST-programmet</span><span class="sxs-lookup"><span data-stu-id="d1fe3-132">Complete the following to set up the REST Application</span></span>

1. <span data-ttu-id="d1fe3-133">Öppna Lär dig administrationsverktyg och välj sedan **REST API-integrationer** i **avsnittet Integrationer.**</span><span class="sxs-lookup"><span data-stu-id="d1fe3-133">Access the Learn Administration Tools, and then select **REST API Integrations** from the **Integrations** section.</span></span>

2. <span data-ttu-id="d1fe3-134">Välj **Skapa integrationer och** ange samma program-/klient-ID som du angav för Blackboard Learn Class Teams Integration LTI-verktyget.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-134">Select **Create integrations** and enter the same Application/Client ID that you entered for the Blackboard Learn Class Teams Integration LTI tool.</span></span>

3. <span data-ttu-id="d1fe3-135">Ange Läs in användare (det här kan vara ditt eget användarnamn för lär dig), eller välj **Bläddra och** leta reda på det.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-135">Enter the Learn User (this could be your own learn admin username), or select **Browse** to locate.</span></span>

4. <span data-ttu-id="d1fe3-136">Välj **Ja** för **slutanvändaråtkomst.**</span><span class="sxs-lookup"><span data-stu-id="d1fe3-136">Select **Yes** for **End User Access**.</span></span>

5. <span data-ttu-id="d1fe3-137">Välj **Ja** för **Behörig att agera som användare**</span><span class="sxs-lookup"><span data-stu-id="d1fe3-137">Select **Yes** for **Authorized to Act as User**</span></span>

6. <span data-ttu-id="d1fe3-138">Välj **Skicka när** du är klar.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-138">Select **Submit** once complete.</span></span>

## <a name="set-up-cross-origin-resource-sharing"></a><span data-ttu-id="d1fe3-139">Konfigurera resursdelning mellan ursprung</span><span class="sxs-lookup"><span data-stu-id="d1fe3-139">Set up Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="d1fe3-140">Öppna Lär dig administrationsverktyg och välj **Resursdelning mellan ursprung** i **avsnittet Integreringar.**</span><span class="sxs-lookup"><span data-stu-id="d1fe3-140">Access the Learn Administration Tools, and select **Cross-Origin Resource Sharing** from the **Integrations** section.</span></span>

2. <span data-ttu-id="d1fe3-141">Välj **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-141">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="d1fe3-142">Ange `https://bb-ms-teams-ultra-ext.api.blackboard.com` ursprunget.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-142">Enter `https://bb-ms-teams-ultra-ext.api.blackboard.com` in the origin.</span></span>

4. <span data-ttu-id="d1fe3-143">Lägg till ordet **Auktorisering** **i Tillåtna rubriker.**</span><span class="sxs-lookup"><span data-stu-id="d1fe3-143">Add the word **Authorization** in the **Allowed Headers**.</span></span>

5. <span data-ttu-id="d1fe3-144">Ange **Tillgänglig** till **Ja.**</span><span class="sxs-lookup"><span data-stu-id="d1fe3-144">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="d1fe3-145">Välj **Skicka när** du är klar.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-145">Select **Submit** once complete.</span></span>

## <a name="enable-class-teams-in-blackboard-learn"></a><span data-ttu-id="d1fe3-146">Aktivera Klassteam i Blackboard Learn</span><span class="sxs-lookup"><span data-stu-id="d1fe3-146">Enable Class Teams in Blackboard Learn</span></span>

<span data-ttu-id="d1fe3-147">När du har aktiverat LTI-verktygen är nästa steg att konfigurera Microsoft Class Teams-integreringen från din egen Microsoft Office 365-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-147">Once you've enabled the LTI tools, your next step will be to set up the Microsoft Class Teams integration from your own Microsoft Office 365 tenant.</span></span> <span data-ttu-id="d1fe3-148">Du kan göra det genom att följa de här stegen som Blackboard Learn Ultra-administratör.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-148">You can do this by following these steps as the Blackboard Learn Ultra admin.</span></span>

1. <span data-ttu-id="d1fe3-149">Välj **Microsoft**  >  **Teams-integreringsadministratör** i **Lär dig mer om administrationsverktyg och verktyg.**</span><span class="sxs-lookup"><span data-stu-id="d1fe3-149">In **Learn Admin** > **Tools and Utilities**, select **Microsoft Teams Integration Admin**.</span></span>

   ![dialogrutan Verktyg och verktyg med en lista över tillgängliga verktyg](../media/lti-media/tools-utilities.png)

2. <span data-ttu-id="d1fe3-151">Markera kryssrutan för Aktivera **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-151">Select the checkbox for **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="d1fe3-152">Ange ditt klientorganisations-ID som det refereras till i avsnittet under Microsoft O365 Admin</span><span class="sxs-lookup"><span data-stu-id="d1fe3-152">Enter your tenant ID as referenced in the section under Microsoft O365 Admin</span></span>

 > [!NOTE]
 > <span data-ttu-id="d1fe3-153">Du kan inte spara inställningarna förrän appen har godkänts av O365-administratören. Se [Godkänna appen i Microsoft Azure-klientorganisationen.](#approve-the-app-in-the-microsoft-azure-tenant)</span><span class="sxs-lookup"><span data-stu-id="d1fe3-153">You won't be able to save the settings until the app has been approved by the O365 admin. See [Approve the app in Microsoft Azure tenant](#approve-the-app-in-the-microsoft-azure-tenant).</span></span>

4. <span data-ttu-id="d1fe3-154">När den globala O365-administratören har godkänt Blackboard Teams-programmet i din Microsoft-klientorganisation väljer du **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="d1fe3-154">When the global O365 admin has approved the Blackboard Teams application in your Microsoft Tenant, select **Submit**.</span></span>
