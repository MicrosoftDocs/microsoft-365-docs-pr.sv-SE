---
title: Arbeta med Microsoft Consulting Services
description: förberedelser och steg att följa för att arbeta med MCS för att paketera dina appar
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation, appar, MCS, förpackning
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d2a6c09e1bcb84885e607d133c14e26e08e3c621
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530169"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="5cc4a-104">Arbeta med Microsoft Consulting Services</span><span class="sxs-lookup"><span data-stu-id="5cc4a-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="5cc4a-105">Du kan samarbeta med Microsoft Consulting Services (MCS) för att få dina appar paketerade för användning med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="5cc4a-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="5cc4a-106">Om du vill ha exakt information kan du arbeta med din kontorepresentant för att kontakta MCS och begränsa ditt specifika apppaketeringsprojekt.</span><span class="sxs-lookup"><span data-stu-id="5cc4a-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="5cc4a-107">Roller och ansvar</span><span class="sxs-lookup"><span data-stu-id="5cc4a-107">Roles and responsibilities</span></span>

<span data-ttu-id="5cc4a-108">Om du vill arbeta med MCS-appförpackningar **måste du ange följande element:**</span><span class="sxs-lookup"><span data-stu-id="5cc4a-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="5cc4a-109">Källinstallationsfilerna (t.ex. setup.exe eller MSI).</span><span class="sxs-lookup"><span data-stu-id="5cc4a-109">The source installer files (e.g., setup.exe or .msi).</span></span>
- <span data-ttu-id="5cc4a-110">Installationsinstruktionerna som anger information om hur den slutliga installationen ska se ut.</span><span class="sxs-lookup"><span data-stu-id="5cc4a-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="5cc4a-111">Till exempel, bör det finnas en genväg till skrivbordet till appen?</span><span class="sxs-lookup"><span data-stu-id="5cc4a-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="5cc4a-112">Vad ska appens synlighet vara?</span><span class="sxs-lookup"><span data-stu-id="5cc4a-112">What should the app's visibility be?</span></span> <span data-ttu-id="5cc4a-113">Ska appen ansluta till en server och i så fall vilken?</span><span class="sxs-lookup"><span data-stu-id="5cc4a-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="5cc4a-114">Mer information finns i [mallen för begäran om programpaketering](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span><span class="sxs-lookup"><span data-stu-id="5cc4a-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="5cc4a-115">Du måste utföra dina egna acceptanstester för att verifiera att appen fungerar som du behöver den i din miljö.</span><span class="sxs-lookup"><span data-stu-id="5cc4a-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="5cc4a-116">**MCS kommer att ta hand om dessa åtgärder:**</span><span class="sxs-lookup"><span data-stu-id="5cc4a-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="5cc4a-117">Kontrollera om appen är förbjuden eller begränsad i Microsoft Managed Desktop-miljön.</span><span class="sxs-lookup"><span data-stu-id="5cc4a-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="5cc4a-118">Testning av installation, start och avinstallation av appen för att säkerställa kompatibilitet med Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5cc4a-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="5cc4a-119">Om MCS upptäcker ett kompatibilitetsproblem lämnar de ut appen till [Desktop App Assure-programmet](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) för reparation.</span><span class="sxs-lookup"><span data-stu-id="5cc4a-119">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="5cc4a-120">Paketera appen efter din specifikation och testa sedan appdistribution med hjälp av Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="5cc4a-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="5cc4a-121">Schema för appleverans</span><span class="sxs-lookup"><span data-stu-id="5cc4a-121">App delivery schedule</span></span>

<span data-ttu-id="5cc4a-122">Starta förpackningsprocessen genom att ladda upp appinformationen till Microsoft Managed Desktop-portalen.</span><span class="sxs-lookup"><span data-stu-id="5cc4a-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="5cc4a-123">Förpackningsteamet granskar nya inlämningar varje torsdag.</span><span class="sxs-lookup"><span data-stu-id="5cc4a-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="5cc4a-124">Efter granskning och förpackning levereras de paketerade apparna följande fredag.</span><span class="sxs-lookup"><span data-stu-id="5cc4a-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="5cc4a-125">Upp till fem appar per vecka kan paketeras för att starta men tjänsten kan skalas efter dina behov.</span><span class="sxs-lookup"><span data-stu-id="5cc4a-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![kalender som visar appinflöde på en torsdag (den 21: a i det här exemplet), media validering nästa dag, förpackning på följande måndag (den 25: e) och app leverans på den efterföljande fredagen (den 29: e)](../../media/MCS-cal.png)

<span data-ttu-id="5cc4a-127">Du får ett meddelande när appen har levererats.</span><span class="sxs-lookup"><span data-stu-id="5cc4a-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="5cc4a-128">Då har du 21 dagar på dig att utföra acceptanstester och logga ut på arbetet i Microsoft Managed Desktop-portalen.</span><span class="sxs-lookup"><span data-stu-id="5cc4a-128">At that point, you have 21 days to perform acceptance testing and sign off on the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="5cc4a-129">Om du upptäcker några problem med appen under acceptanstestningen avvisar du appen i Microsoft Managed Desktop-portalen så ansluts du via e-post med en MCS-paketerare för att förstå och lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="5cc4a-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="5cc4a-130">Testa konton och miljö</span><span class="sxs-lookup"><span data-stu-id="5cc4a-130">Testing accounts and environment</span></span>

<span data-ttu-id="5cc4a-131">För att paketeringsteamet ska kunna slutföra migreringen till Microsoft Intune rekommenderar vi att du anger vissa behörigheter:</span><span class="sxs-lookup"><span data-stu-id="5cc4a-131">For the packaging team to complete the migration to Microsoft Intune we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="5cc4a-132">Tillgång till Microsoft Intunes funktioner för appdistribution för paketeraren att lägga till och tilldela appen</span><span class="sxs-lookup"><span data-stu-id="5cc4a-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="5cc4a-133">Testgrupper, användarkonton och licenser för paketerare för att kunna testa apparna</span><span class="sxs-lookup"><span data-stu-id="5cc4a-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="5cc4a-134">MCS använder dessa behörigheter för att utföra följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="5cc4a-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="5cc4a-135">Se till att appen fungerar på virtuell dator som konfigurerats för Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="5cc4a-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="5cc4a-136">Ladda upp appen till Microsoft Intune för distribution till användarna</span><span class="sxs-lookup"><span data-stu-id="5cc4a-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="5cc4a-137">Utan dessa behörigheter är det möjligt för MCS att gå vidare, men de kommer inte att kunna ladda upp programmen till din miljö.</span><span class="sxs-lookup"><span data-stu-id="5cc4a-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


