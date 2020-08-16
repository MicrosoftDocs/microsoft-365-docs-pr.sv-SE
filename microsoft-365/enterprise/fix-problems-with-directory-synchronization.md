---
title: Åtgärda problem med katalogsynkronisering for Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MBS150
ms.assetid: 79c43023-5a47-45ae-8068-d8a26eee6bc2
description: Här beskrivs vanliga orsaker till problem med katalogsynkronisering i Office 365 samt några metoder för att felsöka och åtgärda dem.
ms.openlocfilehash: 80b4a88e91230a8736f209ecd65c58b2882c25d6
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694855"
---
# <a name="fixing-problems-with-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="742b6-103">Åtgärda problem med katalogsynkronisering for Office 365</span><span class="sxs-lookup"><span data-stu-id="742b6-103">Fixing problems with directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="742b6-104">Med Katalogsynkronisering kan du fortsätta att hantera användare och grupper lokalt och synkronisera tillägg, borttagningar och ändringar i molnet.</span><span class="sxs-lookup"><span data-stu-id="742b6-104">With directory synchronization, you can continue to manage users and groups on-premises and synchronize additions, deletions, and changes to the cloud.</span></span> <span data-ttu-id="742b6-105">Men konfigurationen är lite komplicerad och det kan ibland vara svårt att identifiera problemkällan.</span><span class="sxs-lookup"><span data-stu-id="742b6-105">But setup is a little complicated and it can sometimes be difficult to identify the source of problems.</span></span> <span data-ttu-id="742b6-106">Vi har resurser som kan hjälpa dig att identifiera potentiella problem och åtgärda dem.</span><span class="sxs-lookup"><span data-stu-id="742b6-106">We have resources to help you identify potential issues and fix them.</span></span>
  
## <a name="how-do-i-know-if-something-is-wrong"></a><span data-ttu-id="742b6-107">Hur vet jag om något är fel?</span><span class="sxs-lookup"><span data-stu-id="742b6-107">How do I know if something is wrong?</span></span>

<span data-ttu-id="742b6-108">Det första tecknet på att något är fel är när DirSync-statuspanelen i Microsoft 365 administrationscenter indikerar ett problem.</span><span class="sxs-lookup"><span data-stu-id="742b6-108">The first indication that something is wrong is when the DirSync Status tile in the Microsoft 365 admin center indicates there is a problem.</span></span>
  
<span data-ttu-id="742b6-109">Du får även ett e-postmeddelande (till din alternativa e-postadress och din e-postadress som administratör) från Microsoft 365 som anger att det har uppstått katalogsynkroniseringsfel på klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="742b6-109">You will also receive a mail (to the alternate email and to your admin email) from Microsoft 365 that indicates your tenant has encountered directory synchronization errors.</span></span> <span data-ttu-id="742b6-110">Mer information finns i [Identifiera katalogsynkroniseringsfel i Microsoft 365](identify-directory-synchronization-errors.md).</span><span class="sxs-lookup"><span data-stu-id="742b6-110">For details see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
## <a name="how-do-i-get-azure-active-directory-connect-tool"></a><span data-ttu-id="742b6-111">Hur får jag verktyget Azure Active Directory Connect?</span><span class="sxs-lookup"><span data-stu-id="742b6-111">How do I get Azure Active Directory Connect tool?</span></span>

<span data-ttu-id="742b6-112">I [Microsoft 365 administrationscenter](https://admin.microsoft.com), gå till **Användare** \> **Aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="742b6-112">In the [Microsoft 365 admin center](https://admin.microsoft.com), navigate to **Users** \> **Active users**.</span></span> <span data-ttu-id="742b6-113">Klicka på menyn **Mer (tre punkter)** och välj **Katalogsynkronisering**..</span><span class="sxs-lookup"><span data-stu-id="742b6-113">Click the **More** menu (three dots) and select **Directory synchronization**.</span></span> 
  
<span data-ttu-id="742b6-114">Följ [anvisningarna i guiden](set-up-directory-synchronization.md) för att ladda ned Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="742b6-114">Follow the [instructions in the wizard](set-up-directory-synchronization.md) to download Azure AD Connect.</span></span> 
  
<span data-ttu-id="742b6-115">Om du fortfarande använder Azure Active Directory (Azure AD)-synkroniseringsverktyget (DirSync) läser du [Så här felsöker du felmeddelanden för installationen av och konfigurationsguiden för Azure Active Directory-synkroniseringsverktyget i Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=396717). Där finns information om systemkraven för att installera dirsync, vilken behörighet du behöver och hur du felsöker vanliga fel.</span><span class="sxs-lookup"><span data-stu-id="742b6-115">If you are still using Azure Active Directory (Azure AD) Sync (DirSync), take a look at [How to troubleshoot Azure Active Directory Sync Tool installation and Configuration Wizard error messages in Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=396717) for information about the system requirements to install dirsync, the permissions you need, and how to troubleshoot common errors.</span></span> 
  
<span data-ttu-id="742b6-116">För Information om hur du uppdaterar från Azure AD-Synkronisering till Azure AD Connect se [Uppgraderingsinstruktioner](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span><span class="sxs-lookup"><span data-stu-id="742b6-116">To update from Azure AD Sync to Azure AD Connect, see [the upgrade instructions](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span></span>
  
## <a name="resolving-common-causes-of-problems-with-directory-synchronization-in-microsoft-365"></a><span data-ttu-id="742b6-117">Vanliga orsaker till problem med katalogsynkronisering i Office 365</span><span class="sxs-lookup"><span data-stu-id="742b6-117">Resolving common causes of problems with directory synchronization in Microsoft 365</span></span>

### <a name="synchronized-objects-arent-appearing-or-updating-online-or-im-getting-synchronization-error-reports-from-the-service"></a><span data-ttu-id="742b6-118">Synkroniserade objekt visas eller uppdateras inte online, eller jag får rapporter om synkroniseringsfel från tjänsten.</span><span class="sxs-lookup"><span data-stu-id="742b6-118">Synchronized objects aren't appearing or updating online, or I'm getting synchronization error reports from the Service.</span></span>

- [<span data-ttu-id="742b6-119">Identitetssynkronisering och flexibilitet för dubblettattribut</span><span class="sxs-lookup"><span data-stu-id="742b6-119">Identity synchronization and duplicate attribute resiliency</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)

### <a name="i-have-an-alert-in-the-admin-center-or-am-receiving-automated-emails-that-there-hasnt-been-a-recent-synchronization-event"></a><span data-ttu-id="742b6-120">Jag har en avisering i administrationscenter, eller får automatiska e-postmeddelanden om att det inte har skett en synkronisering på sistone</span><span class="sxs-lookup"><span data-stu-id="742b6-120">I have an alert in the admin center, or am receiving automated emails that there hasn't been a recent synchronization event</span></span>
- [<span data-ttu-id="742b6-121">Felsöka anslutningsproblem med Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="742b6-121">Troubleshoot connectivity issues with Azure AD Connect</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/tshoot-connect-connectivity)
- [<span data-ttu-id="742b6-122">Azure AD Connect-konton och -behörigheter</span><span class="sxs-lookup"><span data-stu-id="742b6-122">Azure AD Connect Accounts and permissions</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=820598)
- [<span data-ttu-id="742b6-123">Azure AD Connect-synkronisering: Hantera Azure AD-tjänstkontot</span><span class="sxs-lookup"><span data-stu-id="742b6-123">Azure AD Connect sync: How to manage the Azure AD service account</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-azureadaccount)
- [<span data-ttu-id="742b6-124">Katalogsynkronisering med Azure Active Directory avslutas eller så får du en varning om att synkronisering inte registrerats på mer än en dag</span><span class="sxs-lookup"><span data-stu-id="742b6-124">Directory synchronization to Azure Active Directory stops or you're warned that sync hasn't registered in more than a day</span></span>](https://support.microsoft.com/help/2882421/directory-synchronization-to-azure-active-directory-stops-or-you-re-warned-that-sync-hasn-t-registered-in-more-than-a-day)

### <a name="password-hashes-arent-synchronizing-or-im-seeing-an-alert-in-the-admin-center-that-there-hasnt-been-a-recent-password-hash-synchronization"></a><span data-ttu-id="742b6-125">Lösenordshashar synkroniseras inte, eller jag ser en varning i administrationscenter om att det inte har skett någon synkronisering av lösenordshash på sistone </span><span class="sxs-lookup"><span data-stu-id="742b6-125">Password hashes aren't synchronizing, or I'm seeing an alert in the admin center that there hasn't been a recent password hash synchronization</span></span>
- [<span data-ttu-id="742b6-126">Implementera synkronisering av lösenordshash med Azure AD Connect-synkronisering</span><span class="sxs-lookup"><span data-stu-id="742b6-126">Implementing password hash synchronization with Azure AD Connect sync</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)

### <a name="im-seeing-an-alert-that-object-quota-exceeded"></a><span data-ttu-id="742b6-127">Ett meddelande om att objektkvoten har överskridits visas</span><span class="sxs-lookup"><span data-stu-id="742b6-127">I'm seeing an alert that Object quota exceeded</span></span>
- <span data-ttu-id="742b6-128">Vi har en inbyggd objektkvot för att skydda tjänsten.</span><span class="sxs-lookup"><span data-stu-id="742b6-128">We have a built-in object quota to help protect the service.</span></span> <span data-ttu-id="742b6-129">Om du har för många objekt i katalogen som måste synkroniseras till Microsoft 365 måste du [Kontakta supporten för företags produkter ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)för att öka din kvot.</span><span class="sxs-lookup"><span data-stu-id="742b6-129">If you have too many objects in your directory that need to sync to Microsoft 365, you'll have to [Contact support for business products](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) to increase your quota.</span></span>

### <a name="i-need-to-know-which-attributes-are-synchronized"></a><span data-ttu-id="742b6-130">Jag behöver veta vilka attribut som synkroniseras</span><span class="sxs-lookup"><span data-stu-id="742b6-130">I need to know which attributes are synchronized</span></span>
- <span data-ttu-id="742b6-131">En lista över alla attribut som synkroniseras till molnet finns [här](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span><span class="sxs-lookup"><span data-stu-id="742b6-131">You can find a list of all the attributes that are synced between on-premises and the cloud [right here](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span></span>

### <a name="i-cant-manage-or-remove-objects-that-were-synchronized-to-the-cloud"></a><span data-ttu-id="742b6-132">Jag kan inte hantera eller ta bort objekt som har synkroniserats till molnet</span><span class="sxs-lookup"><span data-stu-id="742b6-132">I can't manage or remove objects that were synchronized to the cloud</span></span>
- <span data-ttu-id="742b6-133">Är du redo att hantera objekt endast i molnet?</span><span class="sxs-lookup"><span data-stu-id="742b6-133">Are you ready to manage objects in the cloud only?</span></span> <span data-ttu-id="742b6-134">Eller finns det ett objekt som har tagits bort lokalt, men fastnat i molnet?</span><span class="sxs-lookup"><span data-stu-id="742b6-134">Or is there an object that was deleted on-premises, but is stuck in the cloud?</span></span> <span data-ttu-id="742b6-135">Ta en titt på den här [Felsökningsfel under synkronisering ](https://go.microsoft.com/fwlink/p/?linkid=842044) och [Supportartikel](https://go.microsoft.com/fwlink/p/?LinkId=396720) för vägledning om hur du löser problemen.</span><span class="sxs-lookup"><span data-stu-id="742b6-135">Take a look at this [Troubleshooting Errors during synchronization](https://go.microsoft.com/fwlink/p/?linkid=842044) and [support article](https://go.microsoft.com/fwlink/p/?LinkId=396720) for guidance on how to resolve these issues.</span></span>

### <a name="i-got-an-error-message-that-my-company-has-exceeded-the-number-of-objects-that-can-be-synchronized"></a><span data-ttu-id="742b6-136">Jag fick ett felmeddelande om att företaget har överskridit det antal objekt som går att synkronisera</span><span class="sxs-lookup"><span data-stu-id="742b6-136">I got an error message that my company has exceeded the number of objects that can be synchronized</span></span>
- <span data-ttu-id="742b6-137">Du kan läsa mer om problemet [här](https://go.microsoft.com/fwlink/p/?LinkId=396721).</span><span class="sxs-lookup"><span data-stu-id="742b6-137">You can read more about this issue [here](https://go.microsoft.com/fwlink/p/?LinkId=396721).</span></span>
   
## <a name="other-resources"></a><span data-ttu-id="742b6-138">Andra resurser</span><span class="sxs-lookup"><span data-stu-id="742b6-138">Other resources</span></span>

- [<span data-ttu-id="742b6-139">Skript för att åtgärda dubbletter av UPN-namn</span><span class="sxs-lookup"><span data-stu-id="742b6-139">Script to fix duplicate user principal names</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396725)
    
- [<span data-ttu-id="742b6-140">Så här förbereder du en icke-dirigerbar domän som .lokal domän för katalogsynkronisering</span><span class="sxs-lookup"><span data-stu-id="742b6-140">How to prepare a non-routable domain (such as .local domain) for directory synchronization</span></span>](prepare-a-non-routable-domain-for-directory-synchronization.md)
    
- [<span data-ttu-id="742b6-141">Skript för att räkna totalt antal synkroniserade objekt</span><span class="sxs-lookup"><span data-stu-id="742b6-141">Script to count total synchronized objects</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396726)
    
- [<span data-ttu-id="742b6-142">Felsöka AD FS 2.0</span><span class="sxs-lookup"><span data-stu-id="742b6-142">Troubleshoot AD FS 2.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396727)
    
- [<span data-ttu-id="742b6-143">Använda PowerShell för att åtgärda tomma DisplayName-attribut för e-postgrupper</span><span class="sxs-lookup"><span data-stu-id="742b6-143">Use PowerShell to fix empty DisplayName attributes for mail-enabled groups</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396728)
    
- [<span data-ttu-id="742b6-144">Använda PowerShell för att åtgärda UPN-dubbletter</span><span class="sxs-lookup"><span data-stu-id="742b6-144">Use PowerShell to fix duplicate UPN</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396730)
    
- [<span data-ttu-id="742b6-145">Använda PowerShell för att åtgärda dubbletter av e-postadresser</span><span class="sxs-lookup"><span data-stu-id="742b6-145">Use PowerShell to fix duplicate email addresses</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=396731)
    
