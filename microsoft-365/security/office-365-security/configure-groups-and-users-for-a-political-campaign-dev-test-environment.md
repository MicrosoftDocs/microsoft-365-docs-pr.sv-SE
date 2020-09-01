---
title: Konfigurera grupper och användare i en utvecklings-/testmiljö för en politisk kampanj
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 0e22bcf3-bad3-42a4-b44f-276e0cf4790f
description: 'Sammanfattning: skapa utvärderingsversioner av Office 365 och Enterprise Mobility + Security (EMS) med användare och grupper i en utvecklings-/test miljö för en politisk kampanj.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7282659399d2541b50c43dffc9fc8690baecd803
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308445"
---
# <a name="configure-groups-and-users-for-a-political-campaign-devtest-environment"></a><span data-ttu-id="8768d-103">Konfigurera grupper och användare i en utvecklings-/testmiljö för en politisk kampanj</span><span class="sxs-lookup"><span data-stu-id="8768d-103">Configure groups and users for a political campaign dev/test environment</span></span>

 <span data-ttu-id="8768d-104">**Sammanfattning:** skapa utvärderingsversioner av Office 365 och Enterprise Mobility + Security (EMS) med användare och grupper i en utvecklings-/test miljö för en politisk kampanj.</span><span class="sxs-lookup"><span data-stu-id="8768d-104">**Summary:** Create Office 365 and Enterprise Mobility + Security (EMS) trial subscriptions with users and groups for a political campaign dev/test environment.</span></span>

<span data-ttu-id="8768d-105">Följ anvisningarna i den här artikeln om du vill skapa en utvecklings-/testmiljö som innehåller förenklade användarkonton och grupper i en lösning för [Microsofts säkerhetsvägledning för politiska kampanjer, ideella föreningar och andra Agila organisationer](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md).</span><span class="sxs-lookup"><span data-stu-id="8768d-105">Use the instructions in this article to create a dev/test environment that includes simplified user accounts and groups for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution.</span></span>

## <a name="phase-1-create-your-office-365-devtest-environment"></a><span data-ttu-id="8768d-106">Steg 1: skapa en utvecklings-/test miljö för Office 365</span><span class="sxs-lookup"><span data-stu-id="8768d-106">Phase 1: Create your Office 365 dev/test environment</span></span>

<span data-ttu-id="8768d-107">I den här fasen får du provprenumerationer för Office 365 E5 och Enterprise Mobility + Security (EMS) E5 för en fiktiv organisation som representerar en politisk kampanj.</span><span class="sxs-lookup"><span data-stu-id="8768d-107">In this phase, you obtain trial subscriptions for Office 365 E5 and Enterprise Mobility + Security (EMS) E5 for a fictional organization that represents a political campaign.</span></span>

<span data-ttu-id="8768d-108">Följ anvisningarna i **fas 2** i [Enkel baskonfiguration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="8768d-108">First, follow the instructions in **Phase 2** of [The lightweight base configuration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span></span>

<span data-ttu-id="8768d-109">Registrera dig sedan för en utvärderingsprenumeration på EMS E5 och lägg till den i samma organisation som utvärderingsprenumerationen.</span><span class="sxs-lookup"><span data-stu-id="8768d-109">Next, sign up for the EMS E5 trial subscription and add it to the same organization as your trial subscription.</span></span>

1. <span data-ttu-id="8768d-110">Om det behövs loggar du in på administrationscentret med autentiseringsuppgifterna för utvärderingsprenumerationens globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="8768d-110">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="8768d-111">Mer information finns i [Så här loggar du in](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="8768d-111">For help, see [Where to sign in](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="8768d-112">Klicka på panelen **Administratör**.</span><span class="sxs-lookup"><span data-stu-id="8768d-112">Click the **Admin** tile.</span></span>

3. <span data-ttu-id="8768d-113">På fliken **Microsoft 365 administrationscenter** i webbläsaren klickar du **Fakturering > Köpa tjänster**i det vänstra navigeringsfältet.</span><span class="sxs-lookup"><span data-stu-id="8768d-113">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Billing > Purchase services**.</span></span>

4. <span data-ttu-id="8768d-114">På sidan **Köpa tjänster** hittar du **Enterprise Mobility + Security E5**-objekt.</span><span class="sxs-lookup"><span data-stu-id="8768d-114">On the **Purchase services** page, find the **Enterprise Mobility + Security E5** item.</span></span> <span data-ttu-id="8768d-115">Håll muspekaren över den och klicka på **Starta kostnadsfri utvärderingsversion**.</span><span class="sxs-lookup"><span data-stu-id="8768d-115">Hover your mouse pointer over it and click **Start free trial**.</span></span>

5. <span data-ttu-id="8768d-116">På sidan **Bekräfta din beställning** väljer du **Prova nu**.</span><span class="sxs-lookup"><span data-stu-id="8768d-116">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="8768d-117">På sidan **Beställningskvitto** klickar du **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="8768d-117">On the **Order receipt** page, click **Continue**.</span></span>

<span data-ttu-id="8768d-118">Aktivera sedan EMS E5-licensen för ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="8768d-118">Next, enable the EMS E5 license for your global administrator account.</span></span>

1. <span data-ttu-id="8768d-119">Klicka på **Användare > Aktiva användare** i det vänstra navigeringsfältet på fliken **Microsoft 365 administrationscenter** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="8768d-119">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Users > Active users**.</span></span>

2. <span data-ttu-id="8768d-120">Klicka på det globala administratörskontot och klicka sedan på **Redigera** för **Produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="8768d-120">Click your global administrator account, and then click **Edit** for **Product licenses**.</span></span>

3. <span data-ttu-id="8768d-121">I fönstret **Produktlicenser** ställer du in produktlicensen för **Enterprise Mobility + Security E5** till **På**, klickar **Spara** och klickar sedan två gånger på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="8768d-121">On the **Product licenses** pane, turn the product license for **Enterprise Mobility + Security E5** to **On**, click **Save,** and then click **Close** twice.</span></span>

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups"></a><span data-ttu-id="8768d-122">Steg 2: skapa och konfigurera Azure Active Directory-grupper (AD)</span><span class="sxs-lookup"><span data-stu-id="8768d-122">Phase 2: Create and configure your Azure Active Directory (AD) groups</span></span>

<span data-ttu-id="8768d-123">I den här fasen skapar och konfigurerar du Azure AD-grupper för din kampanj.</span><span class="sxs-lookup"><span data-stu-id="8768d-123">In this phase, you create and configure the Azure AD groups for your campaign.</span></span>

<span data-ttu-id="8768d-124">Börja med att skapa en uppsättning grupper för en typisk politisk kampanj med Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="8768d-124">First, create a set of groups for a typical political campaign with the Azure portal.</span></span>

1. <span data-ttu-id="8768d-125">Gå till Azure-portalen vid [https://portal.azure.com](https://portal.azure.com) på en separat flik i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="8768d-125">On a separate tab in your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span> <span data-ttu-id="8768d-126">Om det behövs loggar du in med inloggningsuppgifterna för det globala administratörskontot för din utvärderingsprenumeration av Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="8768d-126">If needed, sign in with the credentials of the global administrator account for your Office 365 E5 trial subscription.</span></span>

2. <span data-ttu-id="8768d-127">Klicka på **Azure Active Directory > Användare och grupper > Alla grupper** i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="8768d-127">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>

3. <span data-ttu-id="8768d-128">Utför följande steg för varje gruppnamn i den här listan:</span><span class="sxs-lookup"><span data-stu-id="8768d-128">Do the following steps for each group name in this list:</span></span>

   - <span data-ttu-id="8768d-129">Seniora och strategisk personal</span><span class="sxs-lookup"><span data-stu-id="8768d-129">Senior and strategic staff</span></span>

   - <span data-ttu-id="8768d-130">IT-personal</span><span class="sxs-lookup"><span data-stu-id="8768d-130">IT staff</span></span>

   - <span data-ttu-id="8768d-131">Analyspersonal</span><span class="sxs-lookup"><span data-stu-id="8768d-131">Analytics staff</span></span>

   - <span data-ttu-id="8768d-132">Normal baspersonal</span><span class="sxs-lookup"><span data-stu-id="8768d-132">Regular core staff</span></span>

   - <span data-ttu-id="8768d-133">Driftspersonal</span><span class="sxs-lookup"><span data-stu-id="8768d-133">Operations staff</span></span>

   - <span data-ttu-id="8768d-134">Fältpersonal</span><span class="sxs-lookup"><span data-stu-id="8768d-134">Field staff</span></span>

1. <span data-ttu-id="8768d-135">Gå till bladet **Alla grupper** och klicka på **+ Ny grupp**.</span><span class="sxs-lookup"><span data-stu-id="8768d-135">On the **All groups** blade, click **+ New group**.</span></span>

2. <span data-ttu-id="8768d-136">Skriv gruppens namn från listan i **namn**.</span><span class="sxs-lookup"><span data-stu-id="8768d-136">Type the group name from the list in **Name**.</span></span>

3. <span data-ttu-id="8768d-137">Välj **Dynamiska användare** i **Medlemskap**.</span><span class="sxs-lookup"><span data-stu-id="8768d-137">Select **Dynamic user** in **Membership**.</span></span>

4. <span data-ttu-id="8768d-138">Klicka på **Ja** för att **Aktivera Office-funktioner**.</span><span class="sxs-lookup"><span data-stu-id="8768d-138">Click **Yes** for **Enable Office features**.</span></span>

5. <span data-ttu-id="8768d-139">Klicka på **Lägg till dynamisk fråga**.</span><span class="sxs-lookup"><span data-stu-id="8768d-139">Click **Add dynamic query**.</span></span>

6. <span data-ttu-id="8768d-140">I **Lägg till användare där** väljer du **Avdelning**.</span><span class="sxs-lookup"><span data-stu-id="8768d-140">In **Add users where**, select **department**.</span></span>

7. <span data-ttu-id="8768d-141">I nästa fält väljer du **Är lika med**.</span><span class="sxs-lookup"><span data-stu-id="8768d-141">In the next field, select **Equals**.</span></span>

8. <span data-ttu-id="8768d-142">I nästa fält skriver du gruppnamnet från listan.</span><span class="sxs-lookup"><span data-stu-id="8768d-142">In the next field, type the group name from the list.</span></span>

9. <span data-ttu-id="8768d-143">Klicka på **Lägg till fråga**och klicka sedan på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="8768d-143">Click **Add query**, and then click **Create**.</span></span>

10. <span data-ttu-id="8768d-144">Klicka på **Användare och grupper – Alla grupper**.</span><span class="sxs-lookup"><span data-stu-id="8768d-144">Click **Users and groups - All groups**.</span></span>

<span data-ttu-id="8768d-145">Därefter konfigurerar du grupperna så att medlemmarna automatiskt tilldelas Office 365 E5- och EMS E5-licenser.</span><span class="sxs-lookup"><span data-stu-id="8768d-145">Next, you configure the groups so that members are automatically assigned Office 365 E5 and EMS E5 licenses.</span></span>

1. <span data-ttu-id="8768d-146">Klicka på **Azure Active Directory > Licenser > Alla produkter** i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="8768d-146">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>

2. <span data-ttu-id="8768d-147">Välj **Enterprise Mobility + Security E5** och **Office 365 Enterprise E5** och klicka sedan på **+ Tilldela**.</span><span class="sxs-lookup"><span data-stu-id="8768d-147">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **+ Assign**.</span></span>

3. <span data-ttu-id="8768d-148">I bladet **Tilldela licens** klickar du på **Användare och grupper**.</span><span class="sxs-lookup"><span data-stu-id="8768d-148">In the **Assign license** blade, click **Users and groups**.</span></span>

4. <span data-ttu-id="8768d-149">I listan med grupper väljer du följande:</span><span class="sxs-lookup"><span data-stu-id="8768d-149">In the list of groups, select the following:</span></span>

   - <span data-ttu-id="8768d-150">Analyspersonal</span><span class="sxs-lookup"><span data-stu-id="8768d-150">Analytics staff</span></span>

   - <span data-ttu-id="8768d-151">Fältpersonal</span><span class="sxs-lookup"><span data-stu-id="8768d-151">Field staff</span></span>

   - <span data-ttu-id="8768d-152">IT-personal</span><span class="sxs-lookup"><span data-stu-id="8768d-152">IT staff</span></span>

   - <span data-ttu-id="8768d-153">Driftspersonal</span><span class="sxs-lookup"><span data-stu-id="8768d-153">Operations staff</span></span>

   - <span data-ttu-id="8768d-154">Normal baspersonal</span><span class="sxs-lookup"><span data-stu-id="8768d-154">Regular core staff</span></span>

   - <span data-ttu-id="8768d-155">Seniora och strategisk personal</span><span class="sxs-lookup"><span data-stu-id="8768d-155">Senior and strategic staff</span></span>

5. <span data-ttu-id="8768d-156">Klicka **Välj** och klicka sedan **Tilldela**.</span><span class="sxs-lookup"><span data-stu-id="8768d-156">Click **Select**, and then click **Assign**.</span></span>

6. <span data-ttu-id="8768d-157">Stäng fliken Azure Portal i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="8768d-157">Close the Azure portal tab in your browser.</span></span>

## <a name="phase-3-add-your-user-accounts"></a><span data-ttu-id="8768d-158">Steg 3: lägga till användarkonton</span><span class="sxs-lookup"><span data-stu-id="8768d-158">Phase 3: Add your user accounts</span></span>

<span data-ttu-id="8768d-159">I den här fasen lägger du till exempelanvändarkonton för din politiska kampanj.</span><span class="sxs-lookup"><span data-stu-id="8768d-159">In this phase, you add the example user accounts for your political campaign.</span></span>

<span data-ttu-id="8768d-160">Först [Anslut med Azure Active Directory PowerShell för diagrammodulen](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="8768d-160">First, you [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell).</span></span>

<span data-ttu-id="8768d-161">Därefter fyller du i ditt organisationsnamn, din plats och ett vanligt lösenord och kör dessa kommandon från PowerShells kommandotolk eller integrerat skriptmiljö (ISE):</span><span class="sxs-lookup"><span data-stu-id="8768d-161">Next, you fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE):</span></span>

```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$deptName="Senior and strategic staff"
$userNames=@("Candidate","ChiefOfStaff","Strategic1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Analytics staff"
$userNames=@("DataScientist1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Regular core staff"
$userNames=@("Regular1","Regular2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Operations staff"
$userNames=@("Operations1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Field staff"
$userNames=@("FieldConsultant1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
```

> [!IMPORTANT]
> <span data-ttu-id="8768d-162">Användningen av ett vanligt lösenord här är för Automatisering och enklare konfiguration för en utvecklings-/testmiljö.</span><span class="sxs-lookup"><span data-stu-id="8768d-162">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="8768d-163">Detta rekommenderas inte för produktionsprenumerationer.</span><span class="sxs-lookup"><span data-stu-id="8768d-163">This is not recommended for production subscriptions.</span></span> <span data-ttu-id="8768d-164">När du loggar in med vart och ett av dessa nya användarkonton kommer du att uppmanas att ändra lösenordet.</span><span class="sxs-lookup"><span data-stu-id="8768d-164">As you sign in with each of these new user accounts, you will be prompted to change the password.</span></span>

<span data-ttu-id="8768d-165">Använd de här anvisningarna för att kontrollera att dynamiska gruppmedlemskap och gruppbaserad licensiering fungerar som de ska.</span><span class="sxs-lookup"><span data-stu-id="8768d-165">Use these steps to verify that dynamic group membership and group-based licensing are working correctly.</span></span>

1. <span data-ttu-id="8768d-166">På fliken **Microsoft Office Home** i webbläsaren klickar du på fliken **Administratör**.</span><span class="sxs-lookup"><span data-stu-id="8768d-166">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>

2. <span data-ttu-id="8768d-167">Klicka **Användare**under den nya fliken **administrationscentret för Microsoft 365** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="8768d-167">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>

3. <span data-ttu-id="8768d-168">I listan över användare klickar du på **Kandidat**.</span><span class="sxs-lookup"><span data-stu-id="8768d-168">In the list of users, click **Candidate**.</span></span>

4. <span data-ttu-id="8768d-169">Kontrollera att du har en lista över egenskaperna för **Kandidat** användarkonto:</span><span class="sxs-lookup"><span data-stu-id="8768d-169">In the pane that lists the properties of the **Candidate** user account, verify that:</span></span>

   - <span data-ttu-id="8768d-170">Det är en medlem i gruppen **Seniora och strategisk personal** (i **Gruppmedlemskap**).</span><span class="sxs-lookup"><span data-stu-id="8768d-170">It is a member of the **Senior and strategic staff** group (in **Group memberships**).</span></span>

   - <span data-ttu-id="8768d-171">Den har tilldelats **Enterprise Mobility + Security E5**- och **Office 365 Enterprise E5**-licenser (i **Produktlicenser**).</span><span class="sxs-lookup"><span data-stu-id="8768d-171">It has been assigned the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses (in **Product licenses**).</span></span>

5. <span data-ttu-id="8768d-172">Stäng användarkontofönstret för **Kandidat**.</span><span class="sxs-lookup"><span data-stu-id="8768d-172">Close the **Candidate** user account pane.</span></span>

## <a name="record-values-for-future-reference"></a><span data-ttu-id="8768d-173">Skriv upp värden för framtida referens</span><span class="sxs-lookup"><span data-stu-id="8768d-173">Record values for future reference</span></span>

<span data-ttu-id="8768d-174">Skriv upp dessa värden för att arbeta med utvärderingsprenumerationer för Office 365 och EMS för denna utvecklings-/testmiljö:</span><span class="sxs-lookup"><span data-stu-id="8768d-174">Record these values for working with the Office 365 and EMS trial subscriptions for this dev/test environment:</span></span>

- <span data-ttu-id="8768d-175">Organisationens namn för utvärderingsversionen:</span><span class="sxs-lookup"><span data-stu-id="8768d-175">Your trial subscription organization name:</span></span> ![Understrykning](../../media/Common-Images/TableLine.png)

  <span data-ttu-id="8768d-177">Till exempel är ”contoso” organisationsnamnet för utvärderingsprenumerationen i domännamnet contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="8768d-177">For example, for the trial subscription domain name of contoso.onmicrosoft.com, the organization name is "contoso".</span></span>

- <span data-ttu-id="8768d-178">Det globala administratörsnamnet:</span><span class="sxs-lookup"><span data-stu-id="8768d-178">The global administrator name:</span></span> ![Understrykning](../../media/Common-Images/TableLine.png)<span data-ttu-id="8768d-180">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="8768d-180">.onmicrosoft.com</span></span>

  <span data-ttu-id="8768d-181">Anteckna lösenordet för kontot och det vanliga första lösenordet för de andra användarkontona på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="8768d-181">Record the password for this account and the common initial password for the other user accounts in a secure location.</span></span>

## <a name="next-step"></a><span data-ttu-id="8768d-182">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="8768d-182">Next step</span></span>

<span data-ttu-id="8768d-183">Skapa fyra olika typer av SharePoint Online-gruppwebbplatser i den här utvecklings-/testmiljön med [Skapa gruppwebbplatser i en utvecklings-/testmiljö för en politisk kampanj](create-team-sites-in-a-political-campaign-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="8768d-183">Build the four different types of SharePoint Online team sites in this dev/test environment with [Create team sites in a political campaign dev/test environment](create-team-sites-in-a-political-campaign-dev-test-environment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8768d-184">Se även</span><span class="sxs-lookup"><span data-stu-id="8768d-184">See also</span></span>

[<span data-ttu-id="8768d-185">Microsofts säkerhetsvägledning för politiska kampanjer, ideella föreningar och andra Agila organisationer</span><span class="sxs-lookup"><span data-stu-id="8768d-185">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="8768d-186">Skapa gruppwebbplatser i en utvecklings-/testmiljö för en politisk kampanj</span><span class="sxs-lookup"><span data-stu-id="8768d-186">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="8768d-187">TLG (Test Lab Guides) för integrering med molntjänster</span><span class="sxs-lookup"><span data-stu-id="8768d-187">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[<span data-ttu-id="8768d-188">Integrering av moln- och hybridlösningar</span><span class="sxs-lookup"><span data-stu-id="8768d-188">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
