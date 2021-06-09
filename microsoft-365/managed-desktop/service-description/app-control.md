---
title: Appkontroll
description: Så här använder du appkontroll och förtroende för program
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
# <a name="app-control"></a><span data-ttu-id="17a80-104">Appkontroll</span><span class="sxs-lookup"><span data-stu-id="17a80-104">App control</span></span>

<span data-ttu-id="17a80-105">Appkontroll är en valfri säkerhetsmetod i Microsoft Hanterat skrivbord som begränsar körningen av kod på klientenheter.</span><span class="sxs-lookup"><span data-stu-id="17a80-105">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="17a80-106">Den här kontrollen minimerar risken för skadlig programvara eller skadliga skript genom att kräva att endast kod som signerats av en kundgodkänd lista med utgivare kan köras.</span><span class="sxs-lookup"><span data-stu-id="17a80-106">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="17a80-107">Det finns många säkerhetsfördelar med den här kontrollen, men den strävar främst efter att skydda data och identitet från klientbaserade sårbarheter.</span><span class="sxs-lookup"><span data-stu-id="17a80-107">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="17a80-108">Microsoft Hanterat skrivbord förenklar hanteringen av principer för appkontroll genom att skapa en basprincip som möjliggör grundläggande produktivitetsscenarier.</span><span class="sxs-lookup"><span data-stu-id="17a80-108">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="17a80-109">Du kan utöka förtroende till andra signerare som är specifika för de program och skript i din miljö.</span><span class="sxs-lookup"><span data-stu-id="17a80-109">You can extend trust to other signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="17a80-110">Alla säkerhetsteknik kräver en balans mellan användarupplevelse, säkerhet och kostnad.</span><span class="sxs-lookup"><span data-stu-id="17a80-110">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="17a80-111">Appkontroll minskar risken för skadlig programvara i din miljö, men det finns konsekvenser för användaren och ytterligare åtgärder för IT-administratören.</span><span class="sxs-lookup"><span data-stu-id="17a80-111">App control reduces the threat of malicious software in your environment, but there are consequences to the user and further actions for your IT administrator.</span></span>

<span data-ttu-id="17a80-112">**Ytterligare säkerhet:**</span><span class="sxs-lookup"><span data-stu-id="17a80-112">**Additional security:**</span></span>

<span data-ttu-id="17a80-113">Appar eller skript som inte är betrodda av programkontrollprincipen blockeras från att köras på enheter.</span><span class="sxs-lookup"><span data-stu-id="17a80-113">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="17a80-114">**Dina ytterligare ansvarsområden:**</span><span class="sxs-lookup"><span data-stu-id="17a80-114">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="17a80-115">Du ansvarar för att testa dina appar för att ta reda på om de blockeras av programkontrollprincipen.</span><span class="sxs-lookup"><span data-stu-id="17a80-115">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="17a80-116">Om en app blockeras (eller skulle blockeras) ansvarar du för att identifiera den nödvändiga undertecknarinformationen och begära en ändring via administratörsportalen.</span><span class="sxs-lookup"><span data-stu-id="17a80-116">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="17a80-117">**Microsoft Hanterat skrivbord ansvarsområden:**</span><span class="sxs-lookup"><span data-stu-id="17a80-117">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="17a80-118">Microsoft Hanterat skrivbord principen som ger möjlighet till grundläggande Microsoft-produkter som M365-appar, Windows, Teams, OneDrive och så vidare.</span><span class="sxs-lookup"><span data-stu-id="17a80-118">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="17a80-119">Microsoft Hanterat skrivbord infogar betrodda undertecknare och distribuerar den uppdaterade principen på dina enheter.</span><span class="sxs-lookup"><span data-stu-id="17a80-119">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="17a80-120">Hantera förtroende i program</span><span class="sxs-lookup"><span data-stu-id="17a80-120">Managing trust in applications</span></span>

<span data-ttu-id="17a80-121">Microsoft Hanterat skrivbord en basprincip som litar på huvudkomponenterna av Microsoft-tekniker.</span><span class="sxs-lookup"><span data-stu-id="17a80-121">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="17a80-122">Sedan kan *du lägga* till förtroende för dina egna program och skript genom att Microsoft Hanterat skrivbord vilka av dem du redan litar på.</span><span class="sxs-lookup"><span data-stu-id="17a80-122">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="17a80-123">Basprincip</span><span class="sxs-lookup"><span data-stu-id="17a80-123">Base policy</span></span>

<span data-ttu-id="17a80-124">Microsoft Hanterat skrivbord, i samarbete med Microsofts experter på cybersäkerhet, skapar och upprätthåller en standardprincip som gör att de flesta appar distribueras via Microsoft Intune samtidigt som de blockerar skadliga aktiviteter som kodkompilering eller körning av filer som inte är betrodda.</span><span class="sxs-lookup"><span data-stu-id="17a80-124">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates, and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="17a80-125">Basprincipen använder följande metod för att begränsa körning av programvara:</span><span class="sxs-lookup"><span data-stu-id="17a80-125">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="17a80-126">Filer som körs av administratörer tillåts att köras.</span><span class="sxs-lookup"><span data-stu-id="17a80-126">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="17a80-127">Filer på platser som *inte finns* i användarskrivbara kataloger kan köras.</span><span class="sxs-lookup"><span data-stu-id="17a80-127">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="17a80-128">Filer har signerats av [en betrodd undertecknare](#signer-requests).</span><span class="sxs-lookup"><span data-stu-id="17a80-128">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="17a80-129">De flesta filer signerade av Microsoft körs, men vissa blockeras för att förhindra högriskåtgärder som kodkompilering.</span><span class="sxs-lookup"><span data-stu-id="17a80-129">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="17a80-130">Om en annan användare än en administratör kan ha lagt till ett program eller skript på en enhet (d.v.s. den finns i en användarskrivbar katalog) tillåter vi inte att den körs såvida den inte redan har tillåtits av en administratör.</span><span class="sxs-lookup"><span data-stu-id="17a80-130">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="17a80-131">Om en användare luras att installera skadlig programvara, om ett problem finns i ett program som användaren kör försöker installera skadlig programvara, eller om en användare avsiktligt försöker köra ett obehörigt program eller skript, stoppar vår princip körningen.</span><span class="sxs-lookup"><span data-stu-id="17a80-131">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="17a80-132">Undertecknarbegäranden</span><span class="sxs-lookup"><span data-stu-id="17a80-132">Signer requests</span></span>

<span data-ttu-id="17a80-133">Du informerar oss om vilka appar som tillhandahålls av programvaruutgivare som du litar på genom att spara en *undertecknares begäran.*</span><span class="sxs-lookup"><span data-stu-id="17a80-133">You inform us of which apps are provided by software publishers you trust by filing a *signer request*.</span></span> <span data-ttu-id="17a80-134">När vi gör det lägger vi till den förtroendeinformationen i kontrollprincipen för originalprogram och tillåter att all programvara som är signerad med den utgivarens certifikat körs på dina enheter.</span><span class="sxs-lookup"><span data-stu-id="17a80-134">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="17a80-135">Granska och tillämpa principer</span><span class="sxs-lookup"><span data-stu-id="17a80-135">Audit and Enforced policies</span></span>

<span data-ttu-id="17a80-136">Microsoft Hanterat skrivbord två principer Microsoft Intune för att ge appkontroll:</span><span class="sxs-lookup"><span data-stu-id="17a80-136">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="17a80-137">Granskningspolicy</span><span class="sxs-lookup"><span data-stu-id="17a80-137">Audit policy</span></span>
<span data-ttu-id="17a80-138">Den här principen skapar loggar för att spela in om ett program eller skript ska blockeras av enforced-principen.</span><span class="sxs-lookup"><span data-stu-id="17a80-138">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="17a80-139">Granskningsprinciper upprätthåller inte appkontrollregler och är avsedda för teständamål för att identifiera om ett program kommer att kräva ett undantag från utgivaren.</span><span class="sxs-lookup"><span data-stu-id="17a80-139">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="17a80-140">Den loggar varningar (8003- eller 8006-händelser) i Loggboken i stället för att blockera körning eller installation av angivna appar eller skript.</span><span class="sxs-lookup"><span data-stu-id="17a80-140">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="17a80-141">Tillämpad princip</span><span class="sxs-lookup"><span data-stu-id="17a80-141">Enforced policy</span></span>
<span data-ttu-id="17a80-142">Den här principen blockerar icke betrodda appar och skript från att köras och skapar loggar när ett program eller skript blockeras.</span><span class="sxs-lookup"><span data-stu-id="17a80-142">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="17a80-143">Användarprinciper hindrar standardanvändare från att köra appar eller skript som lagras i användar skrivbara kataloger.</span><span class="sxs-lookup"><span data-stu-id="17a80-143">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="17a80-144">Enheter i gruppen Test har en granskningsprincip tillämpad så att du kan använda dem för att verifiera om några program orsakar problem.</span><span class="sxs-lookup"><span data-stu-id="17a80-144">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="17a80-145">Alla andra grupper (Första, Snabb och Bred) använder en tillämpad princip, så att användare i de grupperna inte kan köra icke betrodda appar eller skript.</span><span class="sxs-lookup"><span data-stu-id="17a80-145">All other groups (First, Fast, and Broad) use an Enforced policy, so users in those groups won't be able to run untrusted apps or scripts.</span></span>







