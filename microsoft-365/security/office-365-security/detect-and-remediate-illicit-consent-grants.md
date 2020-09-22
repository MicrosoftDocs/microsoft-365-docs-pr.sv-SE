---
title: Upptäcka och reparera bidrag för olaglig medgivande
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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Lär dig hur du känner igen och reparerar otillåtet medgivande i Microsoft Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b534d53166c09cf77993948cf1c448e21c8cd330
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203101"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a><span data-ttu-id="419ec-103">Upptäcka och reparera bidrag för olaglig medgivande</span><span class="sxs-lookup"><span data-stu-id="419ec-103">Detect and Remediate Illicit Consent Grants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="419ec-104">**Sammanfattning**  Lär dig hur du känner igen och reparerar otillåtet medgivande i Office 365.</span><span class="sxs-lookup"><span data-stu-id="419ec-104">**Summary**  Learn how to recognize and remediate the illicit consent grants attack in Office 365.</span></span>

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a><span data-ttu-id="419ec-105">Vad är godkännandet för medgivande i Office 365?</span><span class="sxs-lookup"><span data-stu-id="419ec-105">What is the illicit consent grant attack in Office 365?</span></span>

<span data-ttu-id="419ec-106">Vid intrång i ett otillåtet medgivande ger angriparen ett Azure-registrerat program som begär åtkomst till data, till exempel kontakt information, e-post eller dokument.</span><span class="sxs-lookup"><span data-stu-id="419ec-106">In an illicit consent grant attack, the attacker creates an Azure-registered application that requests access to data such as contact information, email, or documents.</span></span> <span data-ttu-id="419ec-107">Angriparen får ett råd för slutanvändaren att få åtkomst till sina data via nätfiske eller genom att injicera illegal kod på en betrodd webbplats.</span><span class="sxs-lookup"><span data-stu-id="419ec-107">The attacker then tricks an end user into granting that application consent to access their data either through a phishing attack, or by injecting illicit code into a trusted website.</span></span> <span data-ttu-id="419ec-108">När olaglig ansökan har beviljats har den åtkomst nivå till data utan att ett organisations konto behövs.</span><span class="sxs-lookup"><span data-stu-id="419ec-108">After the illicit application has been granted consent, it has account-level access to data without the need for an organizational account.</span></span> <span data-ttu-id="419ec-109">De vanliga reparations stegen, som att återställa lösen ord för överstigta konton eller kräva multifaktorautentisering (MFA) på konton, är inte effektiva mot denna typ av attacker, eftersom dessa är tredjepartsprogram och är utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="419ec-109">Normal remediation steps, like resetting passwords for breached accounts or requiring Multi-Factor Authentication (MFA) on accounts, are not effective against this type of attack, since these are third-party applications and are external to the organization.</span></span>

<span data-ttu-id="419ec-110">Dessa attacker utnyttjar en interaktions modell som förutsätter att den enhet som anropar informationen är automatisering och inte är en mänsklig.</span><span class="sxs-lookup"><span data-stu-id="419ec-110">These attacks leverage an interaction model which presumes the entity that is calling the information is automation and not a human.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="419ec-111">Misstänker du att du har problem med olaglig medgivande-bidrag från en app, just nu?</span><span class="sxs-lookup"><span data-stu-id="419ec-111">Do you suspect you're experiencing problems with illicit consent-grants from an app, right now?</span></span> <span data-ttu-id="419ec-112">Microsoft Cloud App Security (MCAS) har verktyg för att upptäcka, undersöka och åtgärda dina OAuth-appar.</span><span class="sxs-lookup"><span data-stu-id="419ec-112">Microsoft Cloud App Security (MCAS) has tools to detect, investigate, and remediate your OAuth apps.</span></span> <span data-ttu-id="419ec-113">Den här MCAS artikeln har en själv studie kurs som innehåller information om hur du kommer igång med [riskfyllda OAuth-appar](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth).</span><span class="sxs-lookup"><span data-stu-id="419ec-113">This MCAS article has a tutorial that outlines how to go about [investigating risky OAuth apps](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth).</span></span> <span data-ttu-id="419ec-114">Du kan också ange [principer för OAuth-appar](https://docs.microsoft.com/cloud-app-security/app-permission-policy) för att undersöka programbegärda behörigheter, vilka användare som auktoriserar dessa program och hur de kan godkänna eller förbjuda dessa behörighets begär Anden.</span><span class="sxs-lookup"><span data-stu-id="419ec-114">You can also set [OAuth app policies](https://docs.microsoft.com/cloud-app-security/app-permission-policy) to investigate app-requested permissions, which users are authorizing these apps, and widely approve or ban these permissions requests.</span></span>

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a><span data-ttu-id="419ec-115">Vad ser ett otillåtet medgivande i Office 365?</span><span class="sxs-lookup"><span data-stu-id="419ec-115">What does an illicit consent grant attack look like in Office 365?</span></span>

<span data-ttu-id="419ec-116">Du måste söka i **gransknings loggen** för att hitta tecken, även kallade anslags indikationer (IOC).</span><span class="sxs-lookup"><span data-stu-id="419ec-116">You need to search the **audit log** to find signs, also called Indicators of Compromise (IOC) of this attack.</span></span> <span data-ttu-id="419ec-117">För organisationer med många Azure-registrerade program och en stor användar bas är det bästa sättet att granska dina organisationers godkännanden varje vecka.</span><span class="sxs-lookup"><span data-stu-id="419ec-117">For organizations with many Azure-registered applications and a large user base, the best practice is to review your organizations consent grants on a weekly basis.</span></span>

### <a name="steps-for-finding-signs-of-this-attack"></a><span data-ttu-id="419ec-118">Anvisningar för att hitta tecken på det här angreppet</span><span class="sxs-lookup"><span data-stu-id="419ec-118">Steps for finding signs of this attack</span></span>

1. <span data-ttu-id="419ec-119">Öppna **säkerhets & Compliance Center** på <https://protection.office.com> .</span><span class="sxs-lookup"><span data-stu-id="419ec-119">Open the **Security & Compliance Center** at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="419ec-120">Navigera till **Sök** och välj **gransknings loggs ökning**.</span><span class="sxs-lookup"><span data-stu-id="419ec-120">Navigate to **Search** and select **Audit log search**.</span></span>

3. <span data-ttu-id="419ec-121">Sök (alla aktiviteter och alla användare) och ange start datum och slutdatum om det behövs och klicka sedan på **Sök**.</span><span class="sxs-lookup"><span data-stu-id="419ec-121">Search (all activities and all users) and enter the start date and end date if required and then click **Search**.</span></span>

4. <span data-ttu-id="419ec-122">Klicka på **filtrera resultat** och ange medgivande till programmet i **aktivitets** fältet.</span><span class="sxs-lookup"><span data-stu-id="419ec-122">Click **Filter results** and enter Consent to application in the **Activity** field.</span></span>

5. <span data-ttu-id="419ec-123">Klicka på resultatet för att visa aktivitetens uppgifter.</span><span class="sxs-lookup"><span data-stu-id="419ec-123">Click on the result to see the details of the activity.</span></span> <span data-ttu-id="419ec-124">Klicka på **Mer information** om du vill ha mer information om aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="419ec-124">Click **More Information** to get details of the activity.</span></span> <span data-ttu-id="419ec-125">Kontrol lera om IsAdminContent är true.</span><span class="sxs-lookup"><span data-stu-id="419ec-125">Check to see if IsAdminContent is set to True.</span></span>

> [!NOTE]
>
> <span data-ttu-id="419ec-126">Det kan ta från 30 minuter upp till 24 timmar innan motsvarande Gransknings logg post visas i Sök resultatet när en händelse inträffar.</span><span class="sxs-lookup"><span data-stu-id="419ec-126">It can take from 30 minutes up to 24 hours for the corresponding audit log entry to be displayed in the search results after an event occurs.</span></span>
>
> <span data-ttu-id="419ec-127">Den tid som en gransknings post bevaras och sökbar i gransknings loggen beror på din Microsoft 365-prenumeration och speciellt typen för den licens som är tilldelad till en viss användare.</span><span class="sxs-lookup"><span data-stu-id="419ec-127">The length of time that an audit record is retained and searchable in the audit log depends on your Microsoft 365 subscription, and specifically the type of the license that is assigned to a specific user.</span></span> <span data-ttu-id="419ec-128">Mer information finns i [Gransknings logg](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="419ec-128">For more information, see [Audit log](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>
>
> <span data-ttu-id="419ec-129">Om det här värdet är sant betyder det att någon med global administratörs åtkomst kan ha beviljat omfattande åtkomst till data.</span><span class="sxs-lookup"><span data-stu-id="419ec-129">If this value is true, it indicates that someone with Global Administrator access may have granted broad access to data.</span></span> <span data-ttu-id="419ec-130">Om det här är oväntat, vidta åtgärder för att [Bekräfta ett angrepp](#how-to-confirm-an-attack).</span><span class="sxs-lookup"><span data-stu-id="419ec-130">If this is unexpected, take steps to [confirm an attack](#how-to-confirm-an-attack).</span></span>

## <a name="how-to-confirm-an-attack"></a><span data-ttu-id="419ec-131">Så bekräftar du ett angrepp</span><span class="sxs-lookup"><span data-stu-id="419ec-131">How to confirm an attack</span></span>

<span data-ttu-id="419ec-132">Om du har en eller flera instanser av IOCs ovan måste du göra ytterligare undersökningar för att bekräfta att attacket har genomförts.</span><span class="sxs-lookup"><span data-stu-id="419ec-132">If you have one or more instances of the IOCs listed above, you need to do further investigation to positively confirm that the attack occurred.</span></span> <span data-ttu-id="419ec-133">Du kan använda någon av följande tre metoder för att bekräfta angreppet:</span><span class="sxs-lookup"><span data-stu-id="419ec-133">You can use any of these three methods to confirm the attack:</span></span>

- <span data-ttu-id="419ec-134">Inventerings program och deras behörigheter med Azure Active Directory-portalen.</span><span class="sxs-lookup"><span data-stu-id="419ec-134">Inventory applications and their permissions using the Azure Active Directory portal.</span></span> <span data-ttu-id="419ec-135">Den här metoden är fullständig, men du kan bara kontrol lera en användare i taget, om du har många användare att kontrol lera.</span><span class="sxs-lookup"><span data-stu-id="419ec-135">This method is thorough, but you can only check one user at a time which can be very time consuming if you have many users to check.</span></span>

- <span data-ttu-id="419ec-136">Inventerings program och deras behörigheter med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="419ec-136">Inventory applications and their permissions using PowerShell.</span></span> <span data-ttu-id="419ec-137">Det här är den snabbaste och mest omfattande metoden, med minsta möjliga omkostnader.</span><span class="sxs-lookup"><span data-stu-id="419ec-137">This is the fastest and most thorough method, with the least amount of overhead.</span></span>

- <span data-ttu-id="419ec-138">Be dina användare individuellt kontrol lera deras appar och behörigheter och rapportera resultatet tillbaka till administratörerna för reparation.</span><span class="sxs-lookup"><span data-stu-id="419ec-138">Have your users individually check their apps and permissions and report the results back to the administrators for remediation.</span></span>

## <a name="inventory-apps-with-access-in-your-organization"></a><span data-ttu-id="419ec-139">Inventera appar med åtkomst i organisationen</span><span class="sxs-lookup"><span data-stu-id="419ec-139">Inventory apps with access in your organization</span></span>

<span data-ttu-id="419ec-140">Du kan göra detta för dina användare med antingen Azure Active Directory-portalen eller PowerShell eller låta dina användare individuellt räkna upp sin program åtkomst.</span><span class="sxs-lookup"><span data-stu-id="419ec-140">You can do this for your users with either the Azure Active Directory Portal, or PowerShell or have your users individually enumerate their application access.</span></span>

### <a name="steps-for-using-the-azure-active-directory-portal"></a><span data-ttu-id="419ec-141">Steg för att använda Azure Active Directory-portalen</span><span class="sxs-lookup"><span data-stu-id="419ec-141">Steps for using the Azure Active Directory Portal</span></span>

<span data-ttu-id="419ec-142">Du kan leta upp program som en enskild användare har beviljat behörigheter med via [Azure Active Directory-portalen](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="419ec-142">You can look up the applications to which any individual user has granted permissions by using the [Azure Active Directory Portal](https://portal.azure.com/).</span></span>

1. <span data-ttu-id="419ec-143">Logga in på Azure-portalen med administratörs behörighet.</span><span class="sxs-lookup"><span data-stu-id="419ec-143">Sign in to the Azure Portal with administrative rights.</span></span>

2. <span data-ttu-id="419ec-144">Välj Azure Active Directory-bladet.</span><span class="sxs-lookup"><span data-stu-id="419ec-144">Select the Azure Active Directory blade.</span></span>

3. <span data-ttu-id="419ec-145">Välj **Användare**.</span><span class="sxs-lookup"><span data-stu-id="419ec-145">Select **Users**.</span></span>

4. <span data-ttu-id="419ec-146">Välj den användare du vill granska.</span><span class="sxs-lookup"><span data-stu-id="419ec-146">Select the user that you want to review.</span></span>

5. <span data-ttu-id="419ec-147">Välj **program**.</span><span class="sxs-lookup"><span data-stu-id="419ec-147">Select **Applications**.</span></span>

<span data-ttu-id="419ec-148">Då visas de program som har tilldelats till användaren och vilken behörighet de har.</span><span class="sxs-lookup"><span data-stu-id="419ec-148">This will show you the apps that are assigned to the user and what permissions the applications have.</span></span>

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a><span data-ttu-id="419ec-149">Anvisningar för att låta användarna räkna upp sin program åtkomst</span><span class="sxs-lookup"><span data-stu-id="419ec-149">Steps for having your users enumerate their application access</span></span>

<span data-ttu-id="419ec-150">Låt användarna gå med https://myapps.microsoft.com och granska sin egen program åtkomst där.</span><span class="sxs-lookup"><span data-stu-id="419ec-150">Have your users go to https://myapps.microsoft.com and review their own application access there.</span></span> <span data-ttu-id="419ec-151">De bör kunna se alla program med Access, Visa information om dem (inklusive åtkomstscope) och kunna återkalla behörigheter till misstänkta och olagliga appar.</span><span class="sxs-lookup"><span data-stu-id="419ec-151">They should be able to see all the apps with access, view details about them (including the scope of access), and be able to revoke privileges to suspicious or illicit apps.</span></span>

### <a name="steps-for-doing-this-with-powershell"></a><span data-ttu-id="419ec-152">Anvisningar för hur du gör detta med PowerShell</span><span class="sxs-lookup"><span data-stu-id="419ec-152">Steps for doing this with PowerShell</span></span>

<span data-ttu-id="419ec-153">Det enklaste sättet att kontrol lera godkännandet för ett otillåtet medgivande är att köra [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)som kommer att dumpa alla behörigheter för OAuth-godkännanden och OAuth-appar för alla användare i ditt innehav i en. csv-fil.</span><span class="sxs-lookup"><span data-stu-id="419ec-153">The simplest way to verify the Illicit Consent Grant attack is to run [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), which will dump all the OAuth consent grants and OAuth apps for all users in your tenancy into one .csv file.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="419ec-154">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="419ec-154">Pre-requisites</span></span>

- <span data-ttu-id="419ec-155">Azure AD PowerShell-biblioteket installerat.</span><span class="sxs-lookup"><span data-stu-id="419ec-155">The Azure AD PowerShell library installed.</span></span>

- <span data-ttu-id="419ec-156">Global administratörs behörighet på innehavaren som skriptet ska köra på.</span><span class="sxs-lookup"><span data-stu-id="419ec-156">Global administrator rights on the tenant that the script will be run against.</span></span>

- <span data-ttu-id="419ec-157">Lokal administratör på den dator som kör skripten.</span><span class="sxs-lookup"><span data-stu-id="419ec-157">Local Administrator on the computer from which will run the scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="419ec-158">Vi ***rekommenderar starkt*** att du kräver multifaktorautentisering på ditt administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="419ec-158">We ***highly recommend*** that you require multi-factor authentication on your administrative account.</span></span> <span data-ttu-id="419ec-159">Det här manuset stöder MFA-verifikation.</span><span class="sxs-lookup"><span data-stu-id="419ec-159">This script supports MFA authentication.</span></span>

1. <span data-ttu-id="419ec-160">Logga in på datorn som du kör skriptet från med lokal administratörs behörighet.</span><span class="sxs-lookup"><span data-stu-id="419ec-160">Sign in to the computer that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="419ec-161">Ladda ned eller kopiera [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) -skriptet från GitHub till en mapp som du vill köra skriptet från.</span><span class="sxs-lookup"><span data-stu-id="419ec-161">Download or copy the [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script from GitHub to a folder from which you will run the script.</span></span> <span data-ttu-id="419ec-162">Det här kommer att vara samma mapp som utgångs filen "permissions.csv" skrivs till.</span><span class="sxs-lookup"><span data-stu-id="419ec-162">This will be the same folder to which the output "permissions.csv" file will be written.</span></span>

3. <span data-ttu-id="419ec-163">Öppna en PowerShell-instans som administratör och öppna mappen där du sparade skriptet.</span><span class="sxs-lookup"><span data-stu-id="419ec-163">Open a PowerShell instance as an administrator and open to the folder you saved the script to.</span></span>

4. <span data-ttu-id="419ec-164">Anslut till din katalog med cmdleten [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread) .</span><span class="sxs-lookup"><span data-stu-id="419ec-164">Connect to your directory using the [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread) cmdlet.</span></span>

5. <span data-ttu-id="419ec-165">Kör det här PowerShell-kommandot:</span><span class="sxs-lookup"><span data-stu-id="419ec-165">Run this PowerShell command:</span></span>

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

<span data-ttu-id="419ec-166">Skriptet skapar en fil med namnet Permissions.csv.</span><span class="sxs-lookup"><span data-stu-id="419ec-166">The script produces one file named Permissions.csv.</span></span> <span data-ttu-id="419ec-167">Följ de här anvisningarna för att söka efter illegala program behörigheter:</span><span class="sxs-lookup"><span data-stu-id="419ec-167">Follow these steps to look for illicit application permission grants:</span></span>

1. <span data-ttu-id="419ec-168">I kolumnen ConsentType (kolumn G) söker du efter värdet "AllPrinciples".</span><span class="sxs-lookup"><span data-stu-id="419ec-168">In the ConsentType column (column G) search for the value "AllPrinciples".</span></span> <span data-ttu-id="419ec-169">Med AllPrincipals-behörigheten kan klient programmet komma åt allt innehåll i innehavet.</span><span class="sxs-lookup"><span data-stu-id="419ec-169">The AllPrincipals permission allows the client application to access everyone's content in the tenancy.</span></span> <span data-ttu-id="419ec-170">Microsoft 365-program behöver den här behörigheten för att fungera korrekt.</span><span class="sxs-lookup"><span data-stu-id="419ec-170">Native Microsoft 365 applications need this permission to work correctly.</span></span> <span data-ttu-id="419ec-171">Alla program som inte kommer från Microsoft med den här behörigheten bör ses över noggrant.</span><span class="sxs-lookup"><span data-stu-id="419ec-171">Every non-Microsoft application with this permission should be reviewed carefully.</span></span>

2. <span data-ttu-id="419ec-172">I kolumnen permission (kolumn F) granska de behörigheter som varje ombuds program har till innehåll.</span><span class="sxs-lookup"><span data-stu-id="419ec-172">In the Permission column (column F) review the permissions that each delegated application has to content.</span></span> <span data-ttu-id="419ec-173">Leta efter "Läs-och" Skriv "-behörighet eller" \*. Alla "tillstånd" och Läs dessa noggrant eftersom de kanske inte är lämpliga.</span><span class="sxs-lookup"><span data-stu-id="419ec-173">Look for "Read" and "Write" permission or "\*.All" permission, and review these carefully because they may not be appropriate.</span></span>

3. <span data-ttu-id="419ec-174">Granska de specifika användare som har meddelade medgivanden.</span><span class="sxs-lookup"><span data-stu-id="419ec-174">Review the specific users that have consents granted.</span></span> <span data-ttu-id="419ec-175">Om högkvalitativa och högkvalitativa användare har olämpligt skickade beviljade, bör du undersöka ytterligare.</span><span class="sxs-lookup"><span data-stu-id="419ec-175">If high profile or high impact users have inappropriate consents granted, you should investigate further.</span></span>

4. <span data-ttu-id="419ec-176">Leta efter program som verkar vara misstänkta i kolumnen ClientDisplayName (kolumn C).</span><span class="sxs-lookup"><span data-stu-id="419ec-176">In the ClientDisplayName column (column C) look for apps that seem suspicious.</span></span> <span data-ttu-id="419ec-177">Appar med felstavade namn, Super bland-namn eller hackare kan ses över noggrant.</span><span class="sxs-lookup"><span data-stu-id="419ec-177">Apps with misspelled names, super bland names, or hacker-sounding names should be reviewed carefully.</span></span>

## <a name="determine-the-scope-of-the-attack"></a><span data-ttu-id="419ec-178">Fastställ omfattningen för angreppet</span><span class="sxs-lookup"><span data-stu-id="419ec-178">Determine the scope of the attack</span></span>

<span data-ttu-id="419ec-179">När du har slutfört inventeringen kan du granska **gransknings loggen** för att ta reda på vad som är fallet.</span><span class="sxs-lookup"><span data-stu-id="419ec-179">After you have finished inventorying application access, review the **audit log** to determine the full scope of the breach.</span></span> <span data-ttu-id="419ec-180">Sök efter berörda användare, de tids ramar som olaglig ansökan hade till gång till i organisationen och de behörigheter appen hade.</span><span class="sxs-lookup"><span data-stu-id="419ec-180">Search on the affected users, the time frames that the illicit application had access to your organization, and the permissions the app had.</span></span> <span data-ttu-id="419ec-181">Du kan söka i **gransknings loggen** i [säkerhets-och kompatibilitetstillstånd för Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span><span class="sxs-lookup"><span data-stu-id="419ec-181">You can search the **audit log** in the [Microsoft 365 Security and Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="419ec-182">Gransknings-och gransknings kontroll för [post lådor](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) [för administratörer och användare](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) måste ha Aktiver ATS innan det angrips för att få den här informationen.</span><span class="sxs-lookup"><span data-stu-id="419ec-182">[Mailbox auditing](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) and [Activity auditing for admins and users](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) must have been enabled prior to the attack for you to get this information.</span></span>

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a><span data-ttu-id="419ec-183">Så här stoppar och reparerar du en olaglig attack för godkännande</span><span class="sxs-lookup"><span data-stu-id="419ec-183">How to stop and remediate an illicit consent grant attack</span></span>

<span data-ttu-id="419ec-184">När du har identifierat ett program med olaglig behörighet kan du ta bort det på flera sätt.</span><span class="sxs-lookup"><span data-stu-id="419ec-184">After you have identified an application with illicit permissions, you have several ways to remove that access.</span></span>

- <span data-ttu-id="419ec-185">Du kan återkalla Programets behörighet i Azure Active Directory-portalen genom att:</span><span class="sxs-lookup"><span data-stu-id="419ec-185">You can revoke the application's permission in the Azure Active Directory Portal by:</span></span>

  - <span data-ttu-id="419ec-186">Navigera till den berörda användaren i användar bladet i **Azure Active Directory** .</span><span class="sxs-lookup"><span data-stu-id="419ec-186">Navigate to the affected user in the **Azure Active Directory User** blade.</span></span>

  - <span data-ttu-id="419ec-187">Välj **program**.</span><span class="sxs-lookup"><span data-stu-id="419ec-187">Select **Applications**.</span></span>

  - <span data-ttu-id="419ec-188">Välj illegal ansökan.</span><span class="sxs-lookup"><span data-stu-id="419ec-188">Select the illicit application.</span></span>

  - <span data-ttu-id="419ec-189">Klicka på **ta bort** i detalj nivån.</span><span class="sxs-lookup"><span data-stu-id="419ec-189">Click **Remove** in the drill down.</span></span>

- <span data-ttu-id="419ec-190">Du kan återkalla OAuth medgivande-beviljande med PowerShell genom att följa stegen i [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).</span><span class="sxs-lookup"><span data-stu-id="419ec-190">You can revoke the OAuth consent grant with PowerShell by following the steps in [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).</span></span>

- <span data-ttu-id="419ec-191">Du kan återkalla roll tilldelningen för tjänst program med PowerShell genom att följa stegen i [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).</span><span class="sxs-lookup"><span data-stu-id="419ec-191">You can revoke the Service App Role Assignment with PowerShell by following the steps in [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).</span></span>

- <span data-ttu-id="419ec-192">Du kan också inaktivera inloggning för det berörda kontot helt och hållet, som i sin tur inaktiverar program åtkomst till data på det kontot.</span><span class="sxs-lookup"><span data-stu-id="419ec-192">You can also disable sign-in for the affected account altogether, which will in turn disable app access to data in that account.</span></span> <span data-ttu-id="419ec-193">Det här är inte idealiskt för slutanvändarens produktivitet, men om du arbetar med att begränsa effekten snabbt kan det vara en livskraftig kortsiktig åtgärd.</span><span class="sxs-lookup"><span data-stu-id="419ec-193">This isn't ideal for the end user's productivity, of course, but if you are working to limit impact quickly, it can be a viable short-term remediation.</span></span>

- <span data-ttu-id="419ec-194">Du kan stänga av integrerade program för ditt innehav.</span><span class="sxs-lookup"><span data-stu-id="419ec-194">You can turn integrated applications off for your tenancy.</span></span> <span data-ttu-id="419ec-195">Det här är ett drastiskt steg som inaktiverar möjligheten för slutanvändarna att ge tillstånd från en klient organisation.</span><span class="sxs-lookup"><span data-stu-id="419ec-195">This is a drastic step that disables the ability for end users to grant consent on a tenant-wide basis.</span></span> <span data-ttu-id="419ec-196">Detta förhindrar att användarna oavsiktligt tillåter åtkomst till ett skadligt program.</span><span class="sxs-lookup"><span data-stu-id="419ec-196">This prevents your users from inadvertently granting access to a malicious application.</span></span> <span data-ttu-id="419ec-197">Detta rekommenderas inte eftersom det kraftigt försämrar användarnas förmåga att vara produktiv med tredjepartsprogram.</span><span class="sxs-lookup"><span data-stu-id="419ec-197">This isn't strongly recommended as it severely impairs your users' ability to be productive with third party applications.</span></span> <span data-ttu-id="419ec-198">Du kan göra det genom att följa stegen i [Aktivera eller inaktivera integrerade appar](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps).</span><span class="sxs-lookup"><span data-stu-id="419ec-198">You can do this by following the steps in [Turning Integrated Apps on or off](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps).</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="419ec-199">Skydda Microsoft 365 som en expert på cybersäkerhet</span><span class="sxs-lookup"><span data-stu-id="419ec-199">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="419ec-200">Din Microsoft 365-prenumeration innehåller kraftfulla säkerhetsfunktioner som du kan använda för att skydda dina data och dina användare.</span><span class="sxs-lookup"><span data-stu-id="419ec-200">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="419ec-201">Använd [Säkerhetsöversikt för Microsoft 365 – de vanligaste prioriteringarna för de första 30 dagarna, 90 dagarna och bortom](security-roadmap.md) för att implementera Microsofts metodtips för att skydda din Microsoft 365-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="419ec-201">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="419ec-202">Uppgifter som ska utföras under de första 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="419ec-202">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="419ec-203">De har omedelbar effekt och påverkar inte användarna i någon större utsträckning.</span><span class="sxs-lookup"><span data-stu-id="419ec-203">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="419ec-204">Uppgifter som ska utföras inom 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="419ec-204">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="419ec-205">De tar lite längre tid att planera och implementera men förbättrar din säkerhet avsevärt.</span><span class="sxs-lookup"><span data-stu-id="419ec-205">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="419ec-206">Efter 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="419ec-206">Beyond 90 days.</span></span> <span data-ttu-id="419ec-207">De här förbättringarna uppnås under de första 90 dagarna.</span><span class="sxs-lookup"><span data-stu-id="419ec-207">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="419ec-208">Se även:</span><span class="sxs-lookup"><span data-stu-id="419ec-208">See also:</span></span>

- <span data-ttu-id="419ec-209">[Oväntat program i listan Mina program](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) gör att administratörer genom olika åtgärder kan ta sig vidare efter att det finns oväntade program med åtkomst till data.</span><span class="sxs-lookup"><span data-stu-id="419ec-209">[Unexpected application in my applications list](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) walks administrators through various actions they may want to take after realizing there are unexpected applications with access to data.</span></span>

- <span data-ttu-id="419ec-210">Att [integrera program med Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) är en högkvalitativ översikt över medgivande och behörigheter.</span><span class="sxs-lookup"><span data-stu-id="419ec-210">[Integrating applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) is a high-level overview of consent and permissions.</span></span>

- <span data-ttu-id="419ec-211">[Problem med att utveckla mitt program](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) ger länkar till olika godkännande relaterade artiklar.</span><span class="sxs-lookup"><span data-stu-id="419ec-211">[Problems developing my application](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) provides links to various consent related articles.</span></span>

- <span data-ttu-id="419ec-212">[Program-och tjänst huvud objekt i Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) ger en översikt över de program-och tjänst huvud objekt som är kärnan i program modellen.</span><span class="sxs-lookup"><span data-stu-id="419ec-212">[Application and service principal objects in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) provides an overview of the Application and Service principal objects that are core to the application model.</span></span>

- <span data-ttu-id="419ec-213">[Hantera åtkomst till program](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) är en översikt över de funktioner som administratörer har för att hantera användar åtkomst till appar.</span><span class="sxs-lookup"><span data-stu-id="419ec-213">[Manage access to apps](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) is an overview of the capabilities that administrators have to manage user access to apps.</span></span>
