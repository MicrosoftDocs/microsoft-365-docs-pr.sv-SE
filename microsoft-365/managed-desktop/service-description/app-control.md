---
title: Appkontroll
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: e9d33df0ae11d01c8c214fbe0f001a16e8f4908d
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170743"
---
# <a name="app-control"></a><span data-ttu-id="523c0-103">Appkontroll</span><span class="sxs-lookup"><span data-stu-id="523c0-103">App control</span></span>

<span data-ttu-id="523c0-104">Appkontroll är en valfri säkerhetspraxis i Microsoft Managed Desktop som begränsar körningen av kod på klientenheter.</span><span class="sxs-lookup"><span data-stu-id="523c0-104">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="523c0-105">Den här kontrollen minskar risken för skadlig kod eller skadliga skript genom att kräva att endast kod som signeras av en kundgodkänd lista över utgivare kan köras.</span><span class="sxs-lookup"><span data-stu-id="523c0-105">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="523c0-106">Det finns många säkerhetsfördelar med denna kontroll, men det syftar främst till att skydda data och identitet från kundbaserade bedrifter.</span><span class="sxs-lookup"><span data-stu-id="523c0-106">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="523c0-107">Microsoft Managed Desktop förenklar hanteringen av appkontrollprinciper genom att skapa en basprincip som möjliggör grundläggande produktivitetsscenarier.</span><span class="sxs-lookup"><span data-stu-id="523c0-107">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="523c0-108">Du kan utöka förtroendet till ytterligare undertecknare som är specifika för appar och skript i din miljö.</span><span class="sxs-lookup"><span data-stu-id="523c0-108">You can extend trust to additional signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="523c0-109">All säkerhetsteknik kräver en balans mellan användarupplevelse, säkerhet och kostnad.</span><span class="sxs-lookup"><span data-stu-id="523c0-109">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="523c0-110">Appkontrollen minskar risken för skadlig programvara i din miljö, men det får konsekvenser för slutanvändaren och ytterligare åtgärder för IT-administratören.</span><span class="sxs-lookup"><span data-stu-id="523c0-110">App control reduces the threat of malicious software in your environment, but there are consequences to the end user and additional actions for your IT administrator.</span></span>

<span data-ttu-id="523c0-111">**Ytterligare säkerhet:**</span><span class="sxs-lookup"><span data-stu-id="523c0-111">**Additional security:**</span></span>

<span data-ttu-id="523c0-112">Appar eller skript som inte är betrodda av appkontrollprincipen blockeras från att köras på enheter.</span><span class="sxs-lookup"><span data-stu-id="523c0-112">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="523c0-113">**Dina extra ansvarsområden:**</span><span class="sxs-lookup"><span data-stu-id="523c0-113">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="523c0-114">Du är ansvarig för att testa dina appar för att identifiera om de skulle blockeras av programkontrollprincipen.</span><span class="sxs-lookup"><span data-stu-id="523c0-114">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="523c0-115">Om en app blockeras (eller skulle blockeras) är du ansvarig för att identifiera de uppgifter som behövs undertecknare och begära en ändring via adminportalen.</span><span class="sxs-lookup"><span data-stu-id="523c0-115">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="523c0-116">**Microsoft Hanterade skrivbordsansvar:**</span><span class="sxs-lookup"><span data-stu-id="523c0-116">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="523c0-117">Microsoft Managed Desktop underhåller basprincipen som aktiverar centrala Microsoft-produkter som M365 Apps, Windows, Teams, OneDrive och så vidare.</span><span class="sxs-lookup"><span data-stu-id="523c0-117">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="523c0-118">Microsoft Managed Desktop infogar dina betrodda undertecknare och distribuerar den uppdaterade principen till dina enheter.</span><span class="sxs-lookup"><span data-stu-id="523c0-118">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="523c0-119">Hantera förtroende för program</span><span class="sxs-lookup"><span data-stu-id="523c0-119">Managing trust in applications</span></span>

<span data-ttu-id="523c0-120">Microsoft Managed Desktop ger en basprincip som litar på kärnkomponenterna i Microsoft-teknik.</span><span class="sxs-lookup"><span data-stu-id="523c0-120">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="523c0-121">Du *lägger* sedan till förtroende för dina egna program och skript genom att informera Microsoft Managed Desktop vilken av dem du redan litar på.</span><span class="sxs-lookup"><span data-stu-id="523c0-121">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="523c0-122">Baspolicy</span><span class="sxs-lookup"><span data-stu-id="523c0-122">Base policy</span></span>

<span data-ttu-id="523c0-123">Microsoft Managed Desktop skapar och underhåller i samarbete med Microsofts cybersäkerhetsexperter en standardprincip som gör att de flesta appar som distribueras via Microsoft Intune kan blockeras samtidigt som farliga aktiviteter som kodkompilering eller körning av ej betrodda filer blockeras.</span><span class="sxs-lookup"><span data-stu-id="523c0-123">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="523c0-124">Grundprincipen har följande metod för att begränsa programkörning:</span><span class="sxs-lookup"><span data-stu-id="523c0-124">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="523c0-125">Filer som körs av administratörer tillåts att köras.</span><span class="sxs-lookup"><span data-stu-id="523c0-125">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="523c0-126">Filer på platser som *inte* finns i användardokumentade kataloger tillåts att köras.</span><span class="sxs-lookup"><span data-stu-id="523c0-126">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="523c0-127">Filer signeras av en [betrodd undertecknare](#signer-requests).</span><span class="sxs-lookup"><span data-stu-id="523c0-127">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="523c0-128">De flesta filer som signeras av Microsoft kommer att köras, men vissa är blockerade för att förhindra högriskåtgärder som kodkompilering.</span><span class="sxs-lookup"><span data-stu-id="523c0-128">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="523c0-129">Om en annan användare än en administratör kunde ha lagt till en app eller ett skript på en enhet (det vill säga den finns i en katalog som kan skrivas av användaren) tillåter vi inte att den körs om den inte redan har tillåtits specifikt av en administratör.</span><span class="sxs-lookup"><span data-stu-id="523c0-129">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="523c0-130">Om en användare luras att försöka installera skadlig kod, om ett säkerhetsproblem i en app användaren kör försöker installera skadlig kod, eller om en användare avsiktligt försöker köra en obehörig app eller skript, kommer vår policy att stoppa körningen.</span><span class="sxs-lookup"><span data-stu-id="523c0-130">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="523c0-131">Begäran om undertecknare</span><span class="sxs-lookup"><span data-stu-id="523c0-131">Signer requests</span></span>

<span data-ttu-id="523c0-132">Du informerar oss om vilka appar som tillhandahålls av programvaruleverantörer som du litar på genom att lämna in en *undertecknarbegäran.*</span><span class="sxs-lookup"><span data-stu-id="523c0-132">You inform us of which apps are provided by software vendors you trust by filing a *signer request*.</span></span> <span data-ttu-id="523c0-133">På så sätt lägger vi till att lita på information i principen för grundläggande programkontroll och tillåter all programvara som signerats med utgivarens certifikat att köras på dina enheter.</span><span class="sxs-lookup"><span data-stu-id="523c0-133">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="523c0-134">Gransknings- och verkställda principer</span><span class="sxs-lookup"><span data-stu-id="523c0-134">Audit and Enforced policies</span></span>

<span data-ttu-id="523c0-135">Microsoft Managed Desktop använder två Microsoft Intune-principer för att tillhandahålla appkontroll:</span><span class="sxs-lookup"><span data-stu-id="523c0-135">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="523c0-136">Revisionspolicy</span><span class="sxs-lookup"><span data-stu-id="523c0-136">Audit policy</span></span>
<span data-ttu-id="523c0-137">Den här principen skapar loggar för att registrera om en app eller ett skript skulle blockeras av principen Tvingande.</span><span class="sxs-lookup"><span data-stu-id="523c0-137">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="523c0-138">Granskningsprinciper tillämpar inte appkontrollregler och är avsedda för testning för att identifiera om ett program kräver ett undantag från utgivaren.</span><span class="sxs-lookup"><span data-stu-id="523c0-138">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="523c0-139">Den loggar varningar (8003 eller 8006 händelser) i Loggboken i stället för att blockera körningen eller installationen av angivna appar eller skript.</span><span class="sxs-lookup"><span data-stu-id="523c0-139">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="523c0-140">Tvingande policy</span><span class="sxs-lookup"><span data-stu-id="523c0-140">Enforced policy</span></span>
<span data-ttu-id="523c0-141">Den här principen blockerar ej betrodda appar och skript från att köras och skapar loggar när en app eller ett skript blockeras.</span><span class="sxs-lookup"><span data-stu-id="523c0-141">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="523c0-142">Tvingande principer hindrar standardanvändare från att köra appar eller skript som lagras i användarskrivna kataloger.</span><span class="sxs-lookup"><span data-stu-id="523c0-142">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="523c0-143">Enheter i gruppen Test har en granskningsprincip tillämpad så att du kan använda dem för att verifiera om några program orsakar problem.</span><span class="sxs-lookup"><span data-stu-id="523c0-143">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="523c0-144">Alla andra grupper (Första, Fasta och Breda) använder en tvingande princip, så att slutanvändare i dessa grupper inte kan köra ej betrodda appar eller skript.</span><span class="sxs-lookup"><span data-stu-id="523c0-144">All other groups (First, Fast, and Broad) use an Enforced policy, so end users in those groups won't be able to run untrusted apps or scripts.</span></span>







