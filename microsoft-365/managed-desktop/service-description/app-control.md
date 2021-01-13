---
title: Appkontroll
description: Använda program kontroll och förtroende med program
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6f5cc923b5a18b1f45dd186e88228db8c3a891cc
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841309"
---
# <a name="app-control"></a><span data-ttu-id="432e6-104">Appkontroll</span><span class="sxs-lookup"><span data-stu-id="432e6-104">App control</span></span>

<span data-ttu-id="432e6-105">App Control är en valfri säkerhets metod på Microsoft Managed Desktop som begränsar körning av kod på klient enheter.</span><span class="sxs-lookup"><span data-stu-id="432e6-105">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="432e6-106">Den här kontrollen minskar risken för skadliga program eller skadliga skript genom att kräva att endast kod som är signerad av en kund godkänd lista över utgivare kan köras.</span><span class="sxs-lookup"><span data-stu-id="432e6-106">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="432e6-107">Det finns många säkerhets fördelarna med den här kontrollen, men det är främst att skydda data och identitet från klientbaserade sårbarheter.</span><span class="sxs-lookup"><span data-stu-id="432e6-107">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="432e6-108">Med Microsoft Managed Station ära datorer blir det enklare att hantera program kontroll principer genom att skapa en bas policy som möjliggör grundläggande produktivitets scenarier.</span><span class="sxs-lookup"><span data-stu-id="432e6-108">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="432e6-109">Du kan utöka förtroendet till andra undertecknare som är specifika för appar och skript i miljön.</span><span class="sxs-lookup"><span data-stu-id="432e6-109">You can extend trust to other signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="432e6-110">Alla säkerhets tekniker kräver en avvägning mellan användar upplevelse, säkerhet och kostnad.</span><span class="sxs-lookup"><span data-stu-id="432e6-110">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="432e6-111">Program kontroll minskar risken för skadliga program i miljön, men det finns konsekvenser för användaren och andra åtgärder för IT-administratören.</span><span class="sxs-lookup"><span data-stu-id="432e6-111">App control reduces the threat of malicious software in your environment, but there are consequences to the user and further actions for your IT administrator.</span></span>

<span data-ttu-id="432e6-112">**Ytterligare säkerhet:**</span><span class="sxs-lookup"><span data-stu-id="432e6-112">**Additional security:**</span></span>

<span data-ttu-id="432e6-113">Appar eller skript som inte är betrodda av program kontroll principen blockeras från att köras på enheter.</span><span class="sxs-lookup"><span data-stu-id="432e6-113">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="432e6-114">**Dina ytterligare ansvars områden:**</span><span class="sxs-lookup"><span data-stu-id="432e6-114">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="432e6-115">Du är ansvarig för att testa dina program för att identifiera om de blockeras av program kontroll principen.</span><span class="sxs-lookup"><span data-stu-id="432e6-115">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="432e6-116">Om ett program är (eller skulle bli) blockerat är du ansvarig för att identifiera de uppgifter som behövs och begära en ändring via administrations portalen.</span><span class="sxs-lookup"><span data-stu-id="432e6-116">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="432e6-117">**Microsoft Managed Desktop ansvars område:**</span><span class="sxs-lookup"><span data-stu-id="432e6-117">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="432e6-118">Microsoft Managed Desktop har grundläggande policy som gör att du kan använda de grundläggande Microsoft-produkterna som M365-appar, Windows, teams, OneDrive och så vidare.</span><span class="sxs-lookup"><span data-stu-id="432e6-118">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="432e6-119">Microsoft Managed Desktop infogar betrodda undertecknare och distribuerar den uppdaterade principen på dina enheter.</span><span class="sxs-lookup"><span data-stu-id="432e6-119">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="432e6-120">Hantera förtroende i program</span><span class="sxs-lookup"><span data-stu-id="432e6-120">Managing trust in applications</span></span>

<span data-ttu-id="432e6-121">Microsoft Managed Desktop-granskare en bas policy som är betrodd för huvud komponenterna i Microsoft Technologies.</span><span class="sxs-lookup"><span data-stu-id="432e6-121">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="432e6-122">Sedan kan du *lägga till* förtroende för dina egna program och skript genom att informerar Microsoft Managed Desktop, vilket du redan har förtroende för.</span><span class="sxs-lookup"><span data-stu-id="432e6-122">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="432e6-123">Bas policy</span><span class="sxs-lookup"><span data-stu-id="432e6-123">Base policy</span></span>

<span data-ttu-id="432e6-124">Microsoft Managed Desktop, i samarbete med Microsoft Cybersecurity experter, skapar och underhåller en standard princip som gör att de flesta program som distribueras via Microsoft Intune samtidigt blockerar farliga aktiviteter som kodning eller körning av obetrodda filer.</span><span class="sxs-lookup"><span data-stu-id="432e6-124">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates, and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="432e6-125">Bas policyn har följande metod för att begränsa program körning:</span><span class="sxs-lookup"><span data-stu-id="432e6-125">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="432e6-126">Filer som körs av administratörer kan köras.</span><span class="sxs-lookup"><span data-stu-id="432e6-126">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="432e6-127">Filer på platser som *inte* finns i användarnas skrivbara kataloger kommer att tillåtas att köras.</span><span class="sxs-lookup"><span data-stu-id="432e6-127">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="432e6-128">Filer är signerade av en [betrodd undertecknare](#signer-requests).</span><span class="sxs-lookup"><span data-stu-id="432e6-128">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="432e6-129">De flesta filer som är signerade med Microsoft körs, men vissa blockeras för att förhindra högrisk åtgärder, till exempel kod kompilering.</span><span class="sxs-lookup"><span data-stu-id="432e6-129">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="432e6-130">Om en annan användare än en administratör har lagt till en app eller ett skript till en enhet (det vill säga att det är i en användardefinierad katalog) tillåter vi inte att den körs såvida den inte redan har tillåtits av en administratör.</span><span class="sxs-lookup"><span data-stu-id="432e6-130">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="432e6-131">Om en användare luras att försöka installera skadlig program vara, om ett säkerhets problem i en app som användaren kör försöker installera skadlig program vara, eller om en användare medvetet försöker köra en otillåten app eller skript, kommer vår policy att sluta utföra.</span><span class="sxs-lookup"><span data-stu-id="432e6-131">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="432e6-132">Signerings förfrågningar</span><span class="sxs-lookup"><span data-stu-id="432e6-132">Signer requests</span></span>

<span data-ttu-id="432e6-133">Du informerar dig om vilka appar som tillhandahålls av program varu utgivaren som du litar på genom att arkivera en *registreringsbegäran*.</span><span class="sxs-lookup"><span data-stu-id="432e6-133">You inform us of which apps are provided by software publishers you trust by filing a *signer request*.</span></span> <span data-ttu-id="432e6-134">Genom att göra så lägger vi till den förtroende information i princip policyn för program kontroll och gör att program vara som är signerad med den utgivarens certifikat körs på dina enheter.</span><span class="sxs-lookup"><span data-stu-id="432e6-134">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="432e6-135">Gransknings-och genomdrivta principer</span><span class="sxs-lookup"><span data-stu-id="432e6-135">Audit and Enforced policies</span></span>

<span data-ttu-id="432e6-136">Microsoft Managed Desktop använder två Microsoft Intune-principer för att tillhandahålla program kontroll:</span><span class="sxs-lookup"><span data-stu-id="432e6-136">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="432e6-137">Gransknings princip</span><span class="sxs-lookup"><span data-stu-id="432e6-137">Audit policy</span></span>
<span data-ttu-id="432e6-138">Med den här principen kan du ange om en app eller ett skript ska blockeras av den tvingande principen.</span><span class="sxs-lookup"><span data-stu-id="432e6-138">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="432e6-139">Gransknings principer tvingar inte program kontroll regler och är avsedda för testning för att avgöra om ett program kräver ett undantag från utgivaren.</span><span class="sxs-lookup"><span data-stu-id="432e6-139">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="432e6-140">Den loggar varningar (8003 eller 8006) i logg boken i stället för att blockera körning eller installation av angivna appar eller skript.</span><span class="sxs-lookup"><span data-stu-id="432e6-140">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="432e6-141">Tvingande princip</span><span class="sxs-lookup"><span data-stu-id="432e6-141">Enforced policy</span></span>
<span data-ttu-id="432e6-142">Denna princip blockerar icke betrodda appar och skript att köra och skapar loggar när en app eller ett skript blockeras.</span><span class="sxs-lookup"><span data-stu-id="432e6-142">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="432e6-143">Tillämpade principer hindrar vanliga användare från att köra appar eller skript som lagras i användarnas skrivbara kataloger.</span><span class="sxs-lookup"><span data-stu-id="432e6-143">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="432e6-144">Enheter i test gruppen har en gransknings princip som tillämpas så att du kan använda dem för att kontrol lera om några program orsakar problem.</span><span class="sxs-lookup"><span data-stu-id="432e6-144">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="432e6-145">Alla andra grupper (första, snabba och breda) använder en tvingande princip, så att användare i dessa grupper inte kan köra icke betrodda appar eller skript.</span><span class="sxs-lookup"><span data-stu-id="432e6-145">All other groups (First, Fast, and Broad) use an Enforced policy, so users in those groups won't be able to run untrusted apps or scripts.</span></span>







