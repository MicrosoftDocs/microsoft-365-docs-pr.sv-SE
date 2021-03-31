---
title: Arbeta med Microsoft Consulting Services
description: Förberedelse och steg att följa för att arbeta med MCS för att paketera dina appar
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 1441ca3305a5f3e5a83ddd5e1547812f08d7d96b
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445702"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="1d66d-104">Arbeta med Microsoft Consulting Services</span><span class="sxs-lookup"><span data-stu-id="1d66d-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="1d66d-105">Du kan kommunicera med Microsoft Consulting Services (MCS) för att få program paketerade för användning med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="1d66d-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="1d66d-106">Kontakta DIN kontorepresentant för att kontakta MCS och ta kontakt med din specifika appförpackningsprojekt för mer information.</span><span class="sxs-lookup"><span data-stu-id="1d66d-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="1d66d-107">Roller och ansvar</span><span class="sxs-lookup"><span data-stu-id="1d66d-107">Roles and responsibilities</span></span>

<span data-ttu-id="1d66d-108">Om du vill arbeta med **MCS-appförpackningen måste du ange följande element:**</span><span class="sxs-lookup"><span data-stu-id="1d66d-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="1d66d-109">Installationsfilerna för källan (till exempel setup.exe eller .msi).</span><span class="sxs-lookup"><span data-stu-id="1d66d-109">The source installer files (for example, setup.exe or .msi).</span></span>
- <span data-ttu-id="1d66d-110">Installationsanvisningarna som anger hur den slutliga installationen ska se ut.</span><span class="sxs-lookup"><span data-stu-id="1d66d-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="1d66d-111">Ska det till exempel finnas en genväg till programmet på skrivbordet?</span><span class="sxs-lookup"><span data-stu-id="1d66d-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="1d66d-112">Vad ska appens synlighet vara?</span><span class="sxs-lookup"><span data-stu-id="1d66d-112">What should the app's visibility be?</span></span> <span data-ttu-id="1d66d-113">Ska programmet ansluta till en server och i så fall vilken?</span><span class="sxs-lookup"><span data-stu-id="1d66d-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="1d66d-114">Mer information finns i mallen [för paketeringsförfrågan för programmet.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)</span><span class="sxs-lookup"><span data-stu-id="1d66d-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="1d66d-115">Du måste utföra egna godkännandetester för att verifiera att appen fungerar som den ska i din miljö.</span><span class="sxs-lookup"><span data-stu-id="1d66d-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="1d66d-116">**MCS sköter de här åtgärderna:**</span><span class="sxs-lookup"><span data-stu-id="1d66d-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="1d66d-117">Kontrollera om appen är förbjudna eller begränsad i Microsoft Managed Desktop-miljön.</span><span class="sxs-lookup"><span data-stu-id="1d66d-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="1d66d-118">Testning av installation, start och avinstallation av appen för att säkerställa kompatibilitet med Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1d66d-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="1d66d-119">Om MCS upptäcker ett kompatibilitetsproblem lämnar de över appen till [Assure-programmet](https://docs.microsoft.com/fasttrack/products-and-capabilities#app-assure) för appen för åtgärd.</span><span class="sxs-lookup"><span data-stu-id="1d66d-119">If MCS discovers a compatibility issue, they will hand off the app to the [App Assure](https://docs.microsoft.com/fasttrack/products-and-capabilities#app-assure) program for remediation.</span></span>
- <span data-ttu-id="1d66d-120">Paketera appen till din specifikation och testa sedan appdistribution med hjälp av Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="1d66d-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="1d66d-121">Schema för appleverans</span><span class="sxs-lookup"><span data-stu-id="1d66d-121">App delivery schedule</span></span>

<span data-ttu-id="1d66d-122">Starta paketeringsprocessen genom att ladda upp appinformationen till Microsoft Managed Desktop-portalen.</span><span class="sxs-lookup"><span data-stu-id="1d66d-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="1d66d-123">Paketeringsteamet granskar nya inskickade inskickade inskickade produkter varje torsdag.</span><span class="sxs-lookup"><span data-stu-id="1d66d-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="1d66d-124">Efter granskning och paketering levereras de paketerade apparna följande fredag.</span><span class="sxs-lookup"><span data-stu-id="1d66d-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="1d66d-125">Upp till fem appar per vecka kan paketeras för att starta men tjänsten kan skalas efter dina behov.</span><span class="sxs-lookup"><span data-stu-id="1d66d-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![kalender som visar appinflöde på torsdag (den 21:a i det här exemplet), medier som validerar nästa dag, paketering på efterföljande måndag (den 25)) och appleverans den efterföljande fredagen (den 29:e)](../../media/MCS-cal.png)

<span data-ttu-id="1d66d-127">Du meddelas när appen har levererats.</span><span class="sxs-lookup"><span data-stu-id="1d66d-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="1d66d-128">Då har du 21 dagar på dig att utföra godkännandetester och godkänna arbetet i Microsoft Managed Desktop-portalen.</span><span class="sxs-lookup"><span data-stu-id="1d66d-128">At that point, you have 21 days to perform acceptance testing and approve the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="1d66d-129">Om du upptäcker problem med appen under testningen av accepterande avvisar du appen i Microsoft Managed Desktop-portalen så ansluts du via e-post med en MCS-paketerare för att förstå och lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="1d66d-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="1d66d-130">Testa konton och miljö</span><span class="sxs-lookup"><span data-stu-id="1d66d-130">Testing accounts and environment</span></span>

<span data-ttu-id="1d66d-131">För att paketeringsteamet ska kunna slutföra migreringen till Microsoft Intune rekommenderar vi att du anger vissa behörigheter:</span><span class="sxs-lookup"><span data-stu-id="1d66d-131">For the packaging team to complete the migration to Microsoft Intune, we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="1d66d-132">Åtkomst till appdistributionsfunktionerna för Microsoft Intune för paketeraren som lägger till och tilldelar appen</span><span class="sxs-lookup"><span data-stu-id="1d66d-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="1d66d-133">Testa grupper, användarkonton och licenser för paketeraren för att kunna testa apparna</span><span class="sxs-lookup"><span data-stu-id="1d66d-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="1d66d-134">MCS använder behörigheterna för att utföra följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="1d66d-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="1d66d-135">Se till att appen fungerar på en virtuell dator som konfigurerats för Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="1d66d-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="1d66d-136">Ladda upp programmet till Microsoft Intune för distribution till användarna</span><span class="sxs-lookup"><span data-stu-id="1d66d-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="1d66d-137">Utan dessa behörigheter är det möjligt för MCS att gå framåt, men de kommer inte att kunna ladda upp programmen till din miljö.</span><span class="sxs-lookup"><span data-stu-id="1d66d-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>
