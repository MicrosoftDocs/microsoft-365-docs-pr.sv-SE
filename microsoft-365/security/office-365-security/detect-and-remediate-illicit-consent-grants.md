---
title: Identifiera och åtgärda beviljat medgivande för någon av de här medgivandena
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Lär dig hur du känner igen och åtgärdar att medgivande från medgivande förser dig med angrepp i Microsoft Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a50ce58d91d2ff7b2e31e57830289c870364d9b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288293"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a><span data-ttu-id="95eaa-103">Identifiera och åtgärda beviljat medgivande för någon av de här medgivandena</span><span class="sxs-lookup"><span data-stu-id="95eaa-103">Detect and Remediate Illicit Consent Grants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="95eaa-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="95eaa-104">**Applies to**</span></span>
- [<span data-ttu-id="95eaa-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="95eaa-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="95eaa-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95eaa-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="95eaa-107">**Sammanfattning**  Lär dig hur du känner igen och åtgärdar att medgivande från medgivande förser dig med angrepp i Office 365.</span><span class="sxs-lookup"><span data-stu-id="95eaa-107">**Summary**  Learn how to recognize and remediate the illicit consent grants attack in Office 365.</span></span>

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a><span data-ttu-id="95eaa-108">Vad är det för medgivande som godkänner angrepp i Office 365?</span><span class="sxs-lookup"><span data-stu-id="95eaa-108">What is the illicit consent grant attack in Office 365?</span></span>

<span data-ttu-id="95eaa-109">I ett medgivande från medgivande på begäran av en förälder skapar attackeraren ett Azure-registrerat program som begär åtkomst till data, till exempel kontaktinformation, e-post eller dokument.</span><span class="sxs-lookup"><span data-stu-id="95eaa-109">In an illicit consent grant attack, the attacker creates an Azure-registered application that requests access to data such as contact information, email, or documents.</span></span> <span data-ttu-id="95eaa-110">Attackeraren tricksar sedan en slutanvändare till att ge det programmet medgivande för att få åtkomst till sina data antingen genom en nätfiskeattack eller genom att mata in en säkerhetskod på en betrodd webbplats.</span><span class="sxs-lookup"><span data-stu-id="95eaa-110">The attacker then tricks an end user into granting that application consent to access their data either through a phishing attack, or by injecting illicit code into a trusted website.</span></span> <span data-ttu-id="95eaa-111">Efter att programmet med programmet för programmet har beviljats medgivande har det åtkomst på kontonivå till data utan att ett organisationskonto behövs.</span><span class="sxs-lookup"><span data-stu-id="95eaa-111">After the illicit application has been granted consent, it has account-level access to data without the need for an organizational account.</span></span> <span data-ttu-id="95eaa-112">Vanliga åtgärder som att återställa lösenord för konton som har brutits eller som kräver Multi-Factor Authentication (MFA) på konton, är inte effektiva mot den här typen av angrepp eftersom dessa är tredjepartsprogram och är externa för organisationen.</span><span class="sxs-lookup"><span data-stu-id="95eaa-112">Normal remediation steps, like resetting passwords for breached accounts or requiring Multi-Factor Authentication (MFA) on accounts, are not effective against this type of attack, since these are third-party applications and are external to the organization.</span></span>

<span data-ttu-id="95eaa-113">Dessa attacker utnyttjar en interaktionsmodell som antas vara entitet som anropar informationen är automation och inte en person.</span><span class="sxs-lookup"><span data-stu-id="95eaa-113">These attacks leverage an interaction model which presumes the entity that is calling the information is automation and not a human.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95eaa-114">Misstänker du att du har problem med att få medgivande från en app, just nu?</span><span class="sxs-lookup"><span data-stu-id="95eaa-114">Do you suspect you're experiencing problems with illicit consent-grants from an app, right now?</span></span> <span data-ttu-id="95eaa-115">Microsoft Cloud App Security (MCAS) har verktyg för att identifiera, undersöka och åtgärda OAuth-apparna.</span><span class="sxs-lookup"><span data-stu-id="95eaa-115">Microsoft Cloud App Security (MCAS) has tools to detect, investigate, and remediate your OAuth apps.</span></span> <span data-ttu-id="95eaa-116">Den här MCAS-artikeln innehåller en självstudiekurs som beskriver hur du [undersöker riskfyllda OAuth-appar.](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth)</span><span class="sxs-lookup"><span data-stu-id="95eaa-116">This MCAS article has a tutorial that outlines how to go about [investigating risky OAuth apps](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth).</span></span> <span data-ttu-id="95eaa-117">Du kan också ange [OAuth-appprinciper](https://docs.microsoft.com/cloud-app-security/app-permission-policy) för att undersöka vilka behörigheter som efterfrågas, vilka användare som godkänner dessa appar, och godkänna eller förbjuda behörighetsförfrågningar.</span><span class="sxs-lookup"><span data-stu-id="95eaa-117">You can also set [OAuth app policies](https://docs.microsoft.com/cloud-app-security/app-permission-policy) to investigate app-requested permissions, which users are authorizing these apps, and widely approve or ban these permissions requests.</span></span>

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a><span data-ttu-id="95eaa-118">Hur ser en förälders medgivande ut för att bevilja attack i Office 365?</span><span class="sxs-lookup"><span data-stu-id="95eaa-118">What does an illicit consent grant attack look like in Office 365?</span></span>

<span data-ttu-id="95eaa-119">Du måste söka i **granskningsloggen för** att hitta tecken, även kallade indikatorer på kompromett (IOC) för den här attacken.</span><span class="sxs-lookup"><span data-stu-id="95eaa-119">You need to search the **audit log** to find signs, also called Indicators of Compromise (IOC) of this attack.</span></span> <span data-ttu-id="95eaa-120">För organisationer med många Azure-registrerade program och en stor användarbas är det bäst att granska organisationens medgivande beviljat varje vecka.</span><span class="sxs-lookup"><span data-stu-id="95eaa-120">For organizations with many Azure-registered applications and a large user base, the best practice is to review your organizations consent grants on a weekly basis.</span></span>

### <a name="steps-for-finding-signs-of-this-attack"></a><span data-ttu-id="95eaa-121">Steg för att hitta tecken på den här attacken</span><span class="sxs-lookup"><span data-stu-id="95eaa-121">Steps for finding signs of this attack</span></span>

1. <span data-ttu-id="95eaa-122">Öppna **Säkerhets- & Efterlevnadscenter** <https://protection.office.com> på.</span><span class="sxs-lookup"><span data-stu-id="95eaa-122">Open the **Security & Compliance Center** at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="95eaa-123">Gå till **Sök** och välj **Granskningsloggsökning.**</span><span class="sxs-lookup"><span data-stu-id="95eaa-123">Navigate to **Search** and select **Audit log search**.</span></span>

3. <span data-ttu-id="95eaa-124">Sök (alla aktiviteter och alla användare) och ange startdatum och slutdatum om det behövs och klicka sedan på **Sök.**</span><span class="sxs-lookup"><span data-stu-id="95eaa-124">Search (all activities and all users) and enter the start date and end date if required and then click **Search**.</span></span>

4. <span data-ttu-id="95eaa-125">Klicka **på Filtrera** resultat och ange godkännande till programmet i **fältet** Aktivitet.</span><span class="sxs-lookup"><span data-stu-id="95eaa-125">Click **Filter results** and enter Consent to application in the **Activity** field.</span></span>

5. <span data-ttu-id="95eaa-126">Klicka på resultatet om du vill se information om aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="95eaa-126">Click on the result to see the details of the activity.</span></span> <span data-ttu-id="95eaa-127">Klicka **på Mer information** för att få information om aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="95eaa-127">Click **More Information** to get details of the activity.</span></span> <span data-ttu-id="95eaa-128">Kontrollera om IsAdminContent är inställt på Sant.</span><span class="sxs-lookup"><span data-stu-id="95eaa-128">Check to see if IsAdminContent is set to True.</span></span>

> [!NOTE]
>
> <span data-ttu-id="95eaa-129">Det kan ta från 30 minuter till 24 timmar innan motsvarande granskningsloggpost visas i sökresultatet efter att en händelse inträffat.</span><span class="sxs-lookup"><span data-stu-id="95eaa-129">It can take from 30 minutes up to 24 hours for the corresponding audit log entry to be displayed in the search results after an event occurs.</span></span>
>
> <span data-ttu-id="95eaa-130">Hur lång tid som en granskningspost behålls och är sökbar i granskningsloggen beror på din Microsoft 365-prenumeration, och särskilt på vilken typ av licens som tilldelas till en viss användare.</span><span class="sxs-lookup"><span data-stu-id="95eaa-130">The length of time that an audit record is retained and searchable in the audit log depends on your Microsoft 365 subscription, and specifically the type of the license that is assigned to a specific user.</span></span> <span data-ttu-id="95eaa-131">Mer information finns i [granskningsloggen.](../../compliance/search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="95eaa-131">For more information, see [Audit log](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>
>
> <span data-ttu-id="95eaa-132">Om det här värdet är sant anger det att någon med global administratörsåtkomst kan ha beviljat bred åtkomst till data.</span><span class="sxs-lookup"><span data-stu-id="95eaa-132">If this value is true, it indicates that someone with Global Administrator access may have granted broad access to data.</span></span> <span data-ttu-id="95eaa-133">Om det här är oväntat kan du vidta åtgärder [för att bekräfta en attack.](#how-to-confirm-an-attack)</span><span class="sxs-lookup"><span data-stu-id="95eaa-133">If this is unexpected, take steps to [confirm an attack](#how-to-confirm-an-attack).</span></span>

## <a name="how-to-confirm-an-attack"></a><span data-ttu-id="95eaa-134">Så här bekräftar du en attack</span><span class="sxs-lookup"><span data-stu-id="95eaa-134">How to confirm an attack</span></span>

<span data-ttu-id="95eaa-135">Om du har en eller flera instanser av IOCs som anges ovan måste du undersöka ytterligare för att bekräfta att attacken inträffade.</span><span class="sxs-lookup"><span data-stu-id="95eaa-135">If you have one or more instances of the IOCs listed above, you need to do further investigation to positively confirm that the attack occurred.</span></span> <span data-ttu-id="95eaa-136">Du kan använda någon av följande tre metoder för att bekräfta attacken:</span><span class="sxs-lookup"><span data-stu-id="95eaa-136">You can use any of these three methods to confirm the attack:</span></span>

- <span data-ttu-id="95eaa-137">Inventeringsprogram och deras behörigheter med hjälp av Azure Active Directory-portalen.</span><span class="sxs-lookup"><span data-stu-id="95eaa-137">Inventory applications and their permissions using the Azure Active Directory portal.</span></span> <span data-ttu-id="95eaa-138">Den här metoden är genomgående, men du kan bara kontrollera en användare i taget vilket kan ta mycket tid om du har många användare att kontrollera.</span><span class="sxs-lookup"><span data-stu-id="95eaa-138">This method is thorough, but you can only check one user at a time which can be very time consuming if you have many users to check.</span></span>

- <span data-ttu-id="95eaa-139">Inventeringsprogram och deras behörigheter med hjälp av PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95eaa-139">Inventory applications and their permissions using PowerShell.</span></span> <span data-ttu-id="95eaa-140">Det här är den snabbaste och mest genomgående metoden med minsta möjliga overhead.</span><span class="sxs-lookup"><span data-stu-id="95eaa-140">This is the fastest and most thorough method, with the least amount of overhead.</span></span>

- <span data-ttu-id="95eaa-141">Be användarna individuellt kontrollera sina appar och behörigheter och rapportera resultaten till administratörerna för åtgärd.</span><span class="sxs-lookup"><span data-stu-id="95eaa-141">Have your users individually check their apps and permissions and report the results back to the administrators for remediation.</span></span>

## <a name="inventory-apps-with-access-in-your-organization"></a><span data-ttu-id="95eaa-142">Inventeringsprogram med åtkomst i din organisation</span><span class="sxs-lookup"><span data-stu-id="95eaa-142">Inventory apps with access in your organization</span></span>

<span data-ttu-id="95eaa-143">Du kan göra detta för dina användare med antingen Azure Active Directory-portalen eller PowerShell eller låt användarna räkna upp deras programåtkomst individuellt.</span><span class="sxs-lookup"><span data-stu-id="95eaa-143">You can do this for your users with either the Azure Active Directory Portal, or PowerShell or have your users individually enumerate their application access.</span></span>

### <a name="steps-for-using-the-azure-active-directory-portal"></a><span data-ttu-id="95eaa-144">Anvisningar för hur du använder Azure Active Directory-portalen</span><span class="sxs-lookup"><span data-stu-id="95eaa-144">Steps for using the Azure Active Directory Portal</span></span>

<span data-ttu-id="95eaa-145">Du kan slå upp de program som en enskild användare har beviljat behörighet till med hjälp av [Azure Active Directory-portalen.](https://portal.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="95eaa-145">You can look up the applications to which any individual user has granted permissions by using the [Azure Active Directory Portal](https://portal.azure.com/).</span></span>

1. <span data-ttu-id="95eaa-146">Logga in på Azure Portal med administrativa rättigheter.</span><span class="sxs-lookup"><span data-stu-id="95eaa-146">Sign in to the Azure Portal with administrative rights.</span></span>

2. <span data-ttu-id="95eaa-147">Välj Azure Active Directory-bladet.</span><span class="sxs-lookup"><span data-stu-id="95eaa-147">Select the Azure Active Directory blade.</span></span>

3. <span data-ttu-id="95eaa-148">Välj **Användare**.</span><span class="sxs-lookup"><span data-stu-id="95eaa-148">Select **Users**.</span></span>

4. <span data-ttu-id="95eaa-149">Välj den användare som du vill granska.</span><span class="sxs-lookup"><span data-stu-id="95eaa-149">Select the user that you want to review.</span></span>

5. <span data-ttu-id="95eaa-150">Välj **program.**</span><span class="sxs-lookup"><span data-stu-id="95eaa-150">Select **Applications**.</span></span>

<span data-ttu-id="95eaa-151">Då visas de appar som tilldelats användaren och vilka behörigheter programmen har.</span><span class="sxs-lookup"><span data-stu-id="95eaa-151">This will show you the apps that are assigned to the user and what permissions the applications have.</span></span>

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a><span data-ttu-id="95eaa-152">Steg för att användarna ska räkna upp sin programåtkomst</span><span class="sxs-lookup"><span data-stu-id="95eaa-152">Steps for having your users enumerate their application access</span></span>

<span data-ttu-id="95eaa-153">Be användarna gå till https://myapps.microsoft.com och granska sina egna programåtkomst där.</span><span class="sxs-lookup"><span data-stu-id="95eaa-153">Have your users go to https://myapps.microsoft.com and review their own application access there.</span></span> <span data-ttu-id="95eaa-154">De bör kunna se alla appar som har åtkomst, visa information om dem (inklusive omfattningen av åtkomst) och kunna återkalla behörigheter till misstänkta appar eller använda appar som används igen.</span><span class="sxs-lookup"><span data-stu-id="95eaa-154">They should be able to see all the apps with access, view details about them (including the scope of access), and be able to revoke privileges to suspicious or illicit apps.</span></span>

### <a name="steps-for-doing-this-with-powershell"></a><span data-ttu-id="95eaa-155">Steg för att göra detta med PowerShell</span><span class="sxs-lookup"><span data-stu-id="95eaa-155">Steps for doing this with PowerShell</span></span>

<span data-ttu-id="95eaa-156">Det enklaste sättet att verifiera medgivande grant-attacken för medgivande är att köra [Get-AzureADPSPermissions.ps1, ](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)så att alla OAuth-medgivandetillägg och OAuth-appar för alla användare i ditt innehavare sätts i en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="95eaa-156">The simplest way to verify the Illicit Consent Grant attack is to run [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), which will dump all the OAuth consent grants and OAuth apps for all users in your tenancy into one .csv file.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="95eaa-157">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="95eaa-157">Pre-requisites</span></span>

- <span data-ttu-id="95eaa-158">Azure AD PowerShell-biblioteket installerat.</span><span class="sxs-lookup"><span data-stu-id="95eaa-158">The Azure AD PowerShell library installed.</span></span>

- <span data-ttu-id="95eaa-159">Globala administratörsrättigheter för klientorganisationen som skriptet ska köras mot.</span><span class="sxs-lookup"><span data-stu-id="95eaa-159">Global administrator rights on the tenant that the script will be run against.</span></span>

- <span data-ttu-id="95eaa-160">Lokal administratör på datorn som kör skripten från.</span><span class="sxs-lookup"><span data-stu-id="95eaa-160">Local Administrator on the computer from which will run the scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95eaa-161">Vi ***rekommenderar att*** du kräver multifaktorautentisering för ditt administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="95eaa-161">We ***highly recommend*** that you require multi-factor authentication on your administrative account.</span></span> <span data-ttu-id="95eaa-162">Det här skriptet har stöd för MFA-autentisering.</span><span class="sxs-lookup"><span data-stu-id="95eaa-162">This script supports MFA authentication.</span></span>

1. <span data-ttu-id="95eaa-163">Logga in på den dator som du kör skriptet från med lokala administratörsrättigheter.</span><span class="sxs-lookup"><span data-stu-id="95eaa-163">Sign in to the computer that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="95eaa-164">Ladda ned eller [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) skriptet från GitHub till en mapp som du ska köra skriptet från.</span><span class="sxs-lookup"><span data-stu-id="95eaa-164">Download or copy the [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script from GitHub to a folder from which you will run the script.</span></span> <span data-ttu-id="95eaa-165">Det blir samma mapp som utdatafilen "permissions.csv" ska skrivas till.</span><span class="sxs-lookup"><span data-stu-id="95eaa-165">This will be the same folder to which the output "permissions.csv" file will be written.</span></span>

3. <span data-ttu-id="95eaa-166">Öppna en PowerShell-instans som administratör och öppna den mapp där du sparade skriptet.</span><span class="sxs-lookup"><span data-stu-id="95eaa-166">Open a PowerShell instance as an administrator and open to the folder you saved the script to.</span></span>

4. <span data-ttu-id="95eaa-167">Anslut till katalogen med cmdleten [Connect-AzureAD.](https://docs.microsoft.com/powershell/module/azuread/connect-azuread)</span><span class="sxs-lookup"><span data-stu-id="95eaa-167">Connect to your directory using the [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread) cmdlet.</span></span>

5. <span data-ttu-id="95eaa-168">Kör det här PowerShell-kommandot:</span><span class="sxs-lookup"><span data-stu-id="95eaa-168">Run this PowerShell command:</span></span>

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

<span data-ttu-id="95eaa-169">Skriptet ger en fil med namnet Permissions.csv.</span><span class="sxs-lookup"><span data-stu-id="95eaa-169">The script produces one file named Permissions.csv.</span></span> <span data-ttu-id="95eaa-170">Följ dessa steg om du vill söka efter beviljad behörighet för programmet:</span><span class="sxs-lookup"><span data-stu-id="95eaa-170">Follow these steps to look for illicit application permission grants:</span></span>

1. <span data-ttu-id="95eaa-171">I kolumnen ConsentType (kolumn G) söker du efter värdet "AllPrinciples".</span><span class="sxs-lookup"><span data-stu-id="95eaa-171">In the ConsentType column (column G) search for the value "AllPrinciples".</span></span> <span data-ttu-id="95eaa-172">Med behörigheten AllPrincipals har klientprogrammet åtkomst till innehållet som gäller för alla under klienttiden.</span><span class="sxs-lookup"><span data-stu-id="95eaa-172">The AllPrincipals permission allows the client application to access everyone's content in the tenancy.</span></span> <span data-ttu-id="95eaa-173">Ursprungliga Microsoft 365-program behöver den här behörigheten för att fungera korrekt.</span><span class="sxs-lookup"><span data-stu-id="95eaa-173">Native Microsoft 365 applications need this permission to work correctly.</span></span> <span data-ttu-id="95eaa-174">Alla program som inte är Microsoft-program med den här behörigheten bör granskas noggrant.</span><span class="sxs-lookup"><span data-stu-id="95eaa-174">Every non-Microsoft application with this permission should be reviewed carefully.</span></span>

2. <span data-ttu-id="95eaa-175">I kolumnen Behörighet (kolumn F) granskar du behörigheterna som varje delegerat program har till innehållet.</span><span class="sxs-lookup"><span data-stu-id="95eaa-175">In the Permission column (column F) review the permissions that each delegated application has to content.</span></span> <span data-ttu-id="95eaa-176">Leta efter behörigheten "Läsa" och "Skriva" eller "\*. Alla" och granska dem noggrant eftersom de kanske inte är lämpliga.</span><span class="sxs-lookup"><span data-stu-id="95eaa-176">Look for "Read" and "Write" permission or "\*.All" permission, and review these carefully because they may not be appropriate.</span></span>

3. <span data-ttu-id="95eaa-177">Granska specifika användare som har beviljats medgivande.</span><span class="sxs-lookup"><span data-stu-id="95eaa-177">Review the specific users that have consents granted.</span></span> <span data-ttu-id="95eaa-178">Om användare med hög profil eller hög effekt beviljas olämpliga medgivanden bör du undersöka ytterligare.</span><span class="sxs-lookup"><span data-stu-id="95eaa-178">If high profile or high impact users have inappropriate consents granted, you should investigate further.</span></span>

4. <span data-ttu-id="95eaa-179">Leta efter appar som verkar misstänkta i kolumnen ClientDisplayName (kolumn C).</span><span class="sxs-lookup"><span data-stu-id="95eaa-179">In the ClientDisplayName column (column C) look for apps that seem suspicious.</span></span> <span data-ttu-id="95eaa-180">Appar med felstavade namn, supersliga namn och hackarljud bör granskas noggrant.</span><span class="sxs-lookup"><span data-stu-id="95eaa-180">Apps with misspelled names, super bland names, or hacker-sounding names should be reviewed carefully.</span></span>

## <a name="determine-the-scope-of-the-attack"></a><span data-ttu-id="95eaa-181">Fastställa attackens omfattning</span><span class="sxs-lookup"><span data-stu-id="95eaa-181">Determine the scope of the attack</span></span>

<span data-ttu-id="95eaa-182">När du har slutfört inventeringen av programåtkomst granskar du **granskningsloggen** för att fastställa den fullständiga omfattningen av intrånget.</span><span class="sxs-lookup"><span data-stu-id="95eaa-182">After you have finished inventorying application access, review the **audit log** to determine the full scope of the breach.</span></span> <span data-ttu-id="95eaa-183">Sök efter de aktuella användarna, tidsramarna som det berörda programmet hade åtkomst till din organisation och vilka behörigheter appen hade.</span><span class="sxs-lookup"><span data-stu-id="95eaa-183">Search on the affected users, the time frames that the illicit application had access to your organization, and the permissions the app had.</span></span> <span data-ttu-id="95eaa-184">Du kan söka i **granskningsloggen** i Säkerhets- och [efterlevnadscenter för Microsoft 365.](../../compliance/search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="95eaa-184">You can search the **audit log** in the [Microsoft 365 Security and Compliance Center](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95eaa-185">[Postlådegranskning](../../compliance/enable-mailbox-auditing.md) [och aktivitetsgranskning för administratörer](../../compliance/turn-audit-log-search-on-or-off.md) och användare måste ha aktiverats före attacken för att du ska få den här informationen.</span><span class="sxs-lookup"><span data-stu-id="95eaa-185">[Mailbox auditing](../../compliance/enable-mailbox-auditing.md) and [Activity auditing for admins and users](../../compliance/turn-audit-log-search-on-or-off.md) must have been enabled prior to the attack for you to get this information.</span></span>

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a><span data-ttu-id="95eaa-186">Hur man stoppar och åtgärdar ett medgivande från en förälder för att bevilja attack</span><span class="sxs-lookup"><span data-stu-id="95eaa-186">How to stop and remediate an illicit consent grant attack</span></span>

<span data-ttu-id="95eaa-187">När du har identifierat ett program med behörigheten så kan du ta bort den åtkomsten på flera olika sätt.</span><span class="sxs-lookup"><span data-stu-id="95eaa-187">After you have identified an application with illicit permissions, you have several ways to remove that access.</span></span>

- <span data-ttu-id="95eaa-188">Du kan återkalla programmets behörighet i Azure Active Directory-portalen genom att:</span><span class="sxs-lookup"><span data-stu-id="95eaa-188">You can revoke the application's permission in the Azure Active Directory Portal by:</span></span>

  - <span data-ttu-id="95eaa-189">Navigera till den aktuella användaren i **Azure Active Directory-användarbladet.**</span><span class="sxs-lookup"><span data-stu-id="95eaa-189">Navigate to the affected user in the **Azure Active Directory User** blade.</span></span>

  - <span data-ttu-id="95eaa-190">Välj **program.**</span><span class="sxs-lookup"><span data-stu-id="95eaa-190">Select **Applications**.</span></span>

  - <span data-ttu-id="95eaa-191">Välj programmet med programmet som används.</span><span class="sxs-lookup"><span data-stu-id="95eaa-191">Select the illicit application.</span></span>

  - <span data-ttu-id="95eaa-192">Klicka **på Ta** bort i detaljgranskningen.</span><span class="sxs-lookup"><span data-stu-id="95eaa-192">Click **Remove** in the drill down.</span></span>

- <span data-ttu-id="95eaa-193">Du kan återkalla OAuth-medgivandet med PowerShell genom att följa stegen i [Remove-AzureADOAuth2PermissionGrant.](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)</span><span class="sxs-lookup"><span data-stu-id="95eaa-193">You can revoke the OAuth consent grant with PowerShell by following the steps in [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).</span></span>

- <span data-ttu-id="95eaa-194">Du kan återkalla tjänstappens rolltilldelning med PowerShell genom att följa stegen i [Remove-AzureADServiceAppRoleAssignment.](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)</span><span class="sxs-lookup"><span data-stu-id="95eaa-194">You can revoke the Service App Role Assignment with PowerShell by following the steps in [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).</span></span>

- <span data-ttu-id="95eaa-195">Du kan också inaktivera inloggning för det påverkade kontot helt och hållet, vilket i sin tur inaktiverar appåtkomst till data i det kontot.</span><span class="sxs-lookup"><span data-stu-id="95eaa-195">You can also disable sign-in for the affected account altogether, which will in turn disable app access to data in that account.</span></span> <span data-ttu-id="95eaa-196">Det här är naturligtvis inte perfekt för slutanvändarens produktivitet, men om du arbetar för att begränsa påverkan snabbt kan det vara en möjlig åtgärd på kort sikt.</span><span class="sxs-lookup"><span data-stu-id="95eaa-196">This isn't ideal for the end user's productivity, of course, but if you are working to limit impact quickly, it can be a viable short-term remediation.</span></span>

- <span data-ttu-id="95eaa-197">Du kan inaktivera integrerade program för ditt tiotal.</span><span class="sxs-lookup"><span data-stu-id="95eaa-197">You can turn integrated applications off for your tenancy.</span></span> <span data-ttu-id="95eaa-198">Det här är ett avsevärt steg som inaktiverar möjligheten för slutanvändare att bevilja medgivande för hela klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="95eaa-198">This is a drastic step that disables the ability for end users to grant consent on a tenant-wide basis.</span></span> <span data-ttu-id="95eaa-199">Det förhindrar att användarna oavsiktligt beviljar åtkomst till ett skadligt program.</span><span class="sxs-lookup"><span data-stu-id="95eaa-199">This prevents your users from inadvertently granting access to a malicious application.</span></span> <span data-ttu-id="95eaa-200">Det rekommenderas inte särskilt mycket eftersom det allvarligt försämrar dina användares möjligheter att vara produktiva med program från tredje part.</span><span class="sxs-lookup"><span data-stu-id="95eaa-200">This isn't strongly recommended as it severely impairs your users' ability to be productive with third party applications.</span></span> <span data-ttu-id="95eaa-201">Det gör du genom att följa anvisningarna för [att aktivera eller inaktivera integrerade appar.](../../admin/misc/user-consent.md)</span><span class="sxs-lookup"><span data-stu-id="95eaa-201">You can do this by following the steps in [Turning Integrated Apps on or off](../../admin/misc/user-consent.md).</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="95eaa-202">Skydda Microsoft 365 som en expert på cybersäkerhet</span><span class="sxs-lookup"><span data-stu-id="95eaa-202">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="95eaa-203">Din Microsoft 365-prenumeration innehåller kraftfulla säkerhetsfunktioner som du kan använda för att skydda dina data och dina användare.</span><span class="sxs-lookup"><span data-stu-id="95eaa-203">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="95eaa-204">Använd [Säkerhetsöversikt för Microsoft 365 – de vanligaste prioriteringarna för de första 30 dagarna, 90 dagarna och bortom](security-roadmap.md) för att implementera Microsofts metodtips för att skydda din Microsoft 365-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="95eaa-204">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="95eaa-205">Uppgifter som ska utföras under de första 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="95eaa-205">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="95eaa-206">De har omedelbar effekt och påverkar inte användarna i någon större utsträckning.</span><span class="sxs-lookup"><span data-stu-id="95eaa-206">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="95eaa-207">Uppgifter som ska utföras inom 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="95eaa-207">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="95eaa-208">De tar lite längre tid att planera och implementera men förbättrar din säkerhet avsevärt.</span><span class="sxs-lookup"><span data-stu-id="95eaa-208">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="95eaa-209">Efter 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="95eaa-209">Beyond 90 days.</span></span> <span data-ttu-id="95eaa-210">De här förbättringarna uppnås under de första 90 dagarna.</span><span class="sxs-lookup"><span data-stu-id="95eaa-210">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="95eaa-211">Se även:</span><span class="sxs-lookup"><span data-stu-id="95eaa-211">See also:</span></span>

- <span data-ttu-id="95eaa-212">[Med oväntade program i programlistan](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) går administratörer igenom olika åtgärder som de kan vilja vidta när de har inse att det finns oväntade program som har åtkomst till data.</span><span class="sxs-lookup"><span data-stu-id="95eaa-212">[Unexpected application in my applications list](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) walks administrators through various actions they may want to take after realizing there are unexpected applications with access to data.</span></span>

- <span data-ttu-id="95eaa-213">[Integrering av program med Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) är en översikt över medgivande och behörigheter på hög nivå.</span><span class="sxs-lookup"><span data-stu-id="95eaa-213">[Integrating applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) is a high-level overview of consent and permissions.</span></span>

- <span data-ttu-id="95eaa-214">[Problem med att utveckla programmet](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) innehåller länkar till olika medgivanderelaterade artiklar.</span><span class="sxs-lookup"><span data-stu-id="95eaa-214">[Problems developing my application](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) provides links to various consent related articles.</span></span>

- <span data-ttu-id="95eaa-215">[Application and service principal objects in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) provides an overview of the Application and Service principal objects that are core to the application model.</span><span class="sxs-lookup"><span data-stu-id="95eaa-215">[Application and service principal objects in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) provides an overview of the Application and Service principal objects that are core to the application model.</span></span>

- <span data-ttu-id="95eaa-216">[Hantera åtkomst till appar](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) är en översikt över de funktioner som administratörer har för att hantera användaråtkomst till appar.</span><span class="sxs-lookup"><span data-stu-id="95eaa-216">[Manage access to apps](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) is an overview of the capabilities that administrators have to manage user access to apps.</span></span>
