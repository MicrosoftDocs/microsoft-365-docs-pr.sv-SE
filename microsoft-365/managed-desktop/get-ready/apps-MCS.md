---
title: Arbeta med Microsoft Consulting Services
description: förberedelser och anvisningar för att följa för att arbeta med MCS för att paketera dina appar
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation, appar, MCS, packning
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f8c4e427c536577ea2fc768d4930b9d4db6ac697
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841429"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="14180-104">Arbeta med Microsoft Consulting Services</span><span class="sxs-lookup"><span data-stu-id="14180-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="14180-105">Du kan delta i Microsoft Consulting Services (MCS) för att få dina appar paketerade för användning med Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="14180-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="14180-106">Mer detaljerad information finns i arbeta med konto representanten för att kontakta MCS och räckvidd för ditt specifika program packnings projekt.</span><span class="sxs-lookup"><span data-stu-id="14180-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="14180-107">Roller och ansvar</span><span class="sxs-lookup"><span data-stu-id="14180-107">Roles and responsibilities</span></span>

<span data-ttu-id="14180-108">Om du vill arbeta med MCS-programpaketet **måste du tillhandahålla följande element**:</span><span class="sxs-lookup"><span data-stu-id="14180-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="14180-109">Installations program för källfiler (till exempel setup.exe eller. msi).</span><span class="sxs-lookup"><span data-stu-id="14180-109">The source installer files (for example, setup.exe or .msi).</span></span>
- <span data-ttu-id="14180-110">Installations anvisningar, med information om hur den slutliga installationen ska se ut.</span><span class="sxs-lookup"><span data-stu-id="14180-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="14180-111">Om det till exempel finns en genväg till programmet?</span><span class="sxs-lookup"><span data-stu-id="14180-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="14180-112">Vad bör appens synlighet vara?</span><span class="sxs-lookup"><span data-stu-id="14180-112">What should the app's visibility be?</span></span> <span data-ttu-id="14180-113">Ska programmet ansluta till en server och om så är fallet, vilken?</span><span class="sxs-lookup"><span data-stu-id="14180-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="14180-114">Mer information finns i [mallen för begäran om program packning](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span><span class="sxs-lookup"><span data-stu-id="14180-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="14180-115">Du måste utföra dina egna godkännande test för att verifiera att programmet fungerar när du behöver det i din miljö.</span><span class="sxs-lookup"><span data-stu-id="14180-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="14180-116">**MCS kommer att vidta dessa åtgärder:**</span><span class="sxs-lookup"><span data-stu-id="14180-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="14180-117">Kontrollerar om programmet är förbjudet eller begränsat i Microsoft Managed Desktop Environment.</span><span class="sxs-lookup"><span data-stu-id="14180-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="14180-118">Att testa installation, start och avinstallation av appen för att säkerställa kompatibilitet med Windows 10.</span><span class="sxs-lookup"><span data-stu-id="14180-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="14180-119">Om MCS upptäcker ett kompatibilitetsproblem kan de lämna in appen till [Skriv bords](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) programmet för att säkerställa att programmet är åtgärdat.</span><span class="sxs-lookup"><span data-stu-id="14180-119">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="14180-120">Paketera programmet i din specifikation och testa sedan program distributionen med hjälp av Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="14180-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="14180-121">Program leverans schema</span><span class="sxs-lookup"><span data-stu-id="14180-121">App delivery schedule</span></span>

<span data-ttu-id="14180-122">Starta packningen genom att överföra program informationen till Microsoft Managed Desktop-portalen.</span><span class="sxs-lookup"><span data-stu-id="14180-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="14180-123">Förpacknings gruppen granskar nya inlämningar varje torsdag.</span><span class="sxs-lookup"><span data-stu-id="14180-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="14180-124">När du har granskat och paketerat levereras de paketerade apparna följande fredag:</span><span class="sxs-lookup"><span data-stu-id="14180-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="14180-125">Det går att paketera upp till fem appar per vecka, men tjänsten kan anpassas efter dina behov.</span><span class="sxs-lookup"><span data-stu-id="14180-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![kalender som visar hur programmet inflödar på en torsdag (tjugoförsta i det här exemplet), media verifiering nästa dag, paket för följande måndag (25) och program leverans på nästa fredag (29)](../../media/MCS-cal.png)

<span data-ttu-id="14180-127">Du får ett meddelande när appen har levererats.</span><span class="sxs-lookup"><span data-stu-id="14180-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="14180-128">Då har vi 21 dagar på dig för att testa och godkänna arbetet på Microsoft Managed Desktop-portalen.</span><span class="sxs-lookup"><span data-stu-id="14180-128">At that point, you have 21 days to perform acceptance testing and approve the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="14180-129">Om du upptäcker problem med appen under godkännande testningen kan du avvisa programmet på Microsoft Managed Desktop-portalen och du kommer att vara ansluten via e-post med en MCS-paketerare för att förstå och lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="14180-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="14180-130">Testa konton och miljö</span><span class="sxs-lookup"><span data-stu-id="14180-130">Testing accounts and environment</span></span>

<span data-ttu-id="14180-131">För att förpacknings gruppen ska kunna slutföra migreringen till Microsoft Intune rekommenderar vi att du ger vissa behörigheter:</span><span class="sxs-lookup"><span data-stu-id="14180-131">For the packaging team to complete the migration to Microsoft Intune, we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="14180-132">Åtkomst till Microsoft Intune-funktioner för program distribution för att Paketeraren ska kunna lägga till och tilldela programmet</span><span class="sxs-lookup"><span data-stu-id="14180-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="14180-133">Testa grupper, användar konton och licenser för paketen för att kunna testa apparna</span><span class="sxs-lookup"><span data-stu-id="14180-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="14180-134">MCS använder dessa behörigheter för att utföra följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="14180-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="14180-135">Kontrol lera att programmet fungerar på en virtuell dator konfigurerad för Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="14180-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="14180-136">Ladda upp appen till Microsoft Intune för distribution till dina användare</span><span class="sxs-lookup"><span data-stu-id="14180-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="14180-137">Utan dessa behörigheter är det möjligt för MCS att gå vidare, men de kommer inte att kunna ladda upp program till din miljö.</span><span class="sxs-lookup"><span data-stu-id="14180-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


