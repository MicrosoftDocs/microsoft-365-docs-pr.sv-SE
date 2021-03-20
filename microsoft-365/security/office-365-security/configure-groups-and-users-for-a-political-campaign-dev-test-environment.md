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
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 0e22bcf3-bad3-42a4-b44f-276e0cf4790f
description: 'Sammanfattning: skapa utvärderingsversioner av Office 365 och Enterprise Mobility + Security (EMS) med användare och grupper i en utvecklings-/test miljö för en politisk kampanj.'
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 54d2543313c1a031974876d7fd09b453cc2ec24d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906546"
---
# <a name="configure-groups-and-users-for-a-political-campaign-devtest-environment"></a><span data-ttu-id="dc14a-103">Konfigurera grupper och användare i en utvecklings-/testmiljö för en politisk kampanj</span><span class="sxs-lookup"><span data-stu-id="dc14a-103">Configure groups and users for a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="dc14a-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="dc14a-104">**Applies to**</span></span>
- [<span data-ttu-id="dc14a-105">Microsoft Defender för Office 365 abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="dc14a-105">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)

 <span data-ttu-id="dc14a-106">**Sammanfattning:** skapa utvärderingsversioner av Office 365 och Enterprise Mobility + Security (EMS) med användare och grupper i en utvecklings-/test miljö för en politisk kampanj.</span><span class="sxs-lookup"><span data-stu-id="dc14a-106">**Summary:** Create Office 365 and Enterprise Mobility + Security (EMS) trial subscriptions with users and groups for a political campaign dev/test environment.</span></span>

<span data-ttu-id="dc14a-107">Följ anvisningarna i den här artikeln om du vill skapa en utvecklings-/testmiljö som innehåller förenklade användarkonton och grupper i en lösning för [Microsofts säkerhetsvägledning för politiska kampanjer, ideella föreningar och andra Agila organisationer](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md).</span><span class="sxs-lookup"><span data-stu-id="dc14a-107">Use the instructions in this article to create a dev/test environment that includes simplified user accounts and groups for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution.</span></span>

## <a name="phase-1-create-your-office-365-devtest-environment"></a><span data-ttu-id="dc14a-108">Steg 1: skapa en utvecklings-/test miljö för Office 365</span><span class="sxs-lookup"><span data-stu-id="dc14a-108">Phase 1: Create your Office 365 dev/test environment</span></span>

<span data-ttu-id="dc14a-109">I den här fasen får du provprenumerationer för Office 365 E5 och Enterprise Mobility + Security (EMS) E5 för en fiktiv organisation som representerar en politisk kampanj.</span><span class="sxs-lookup"><span data-stu-id="dc14a-109">In this phase, you obtain trial subscriptions for Office 365 E5 and Enterprise Mobility + Security (EMS) E5 for a fictional organization that represents a political campaign.</span></span>

<span data-ttu-id="dc14a-110">Följ anvisningarna i **fas 2** i [Enkel baskonfiguration](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="dc14a-110">First, follow the instructions in **Phase 2** of [The lightweight base configuration](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>

<span data-ttu-id="dc14a-111">Registrera dig sedan för en utvärderingsprenumeration på EMS E5 och lägg till den i samma organisation som utvärderingsprenumerationen.</span><span class="sxs-lookup"><span data-stu-id="dc14a-111">Next, sign up for the EMS E5 trial subscription and add it to the same organization as your trial subscription.</span></span>

1. <span data-ttu-id="dc14a-112">Om det behövs loggar du in på administrationscentret med autentiseringsuppgifterna för utvärderingsprenumerationens globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="dc14a-112">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="dc14a-113">Mer information finns i [Så här loggar du in](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="dc14a-113">For help, see [Where to sign in](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="dc14a-114">Klicka på panelen **Administratör**.</span><span class="sxs-lookup"><span data-stu-id="dc14a-114">Click the **Admin** tile.</span></span>

3. <span data-ttu-id="dc14a-115">På fliken **Microsoft 365 administrationscenter** i webbläsaren klickar du **Fakturering > Köpa tjänster** i det vänstra navigeringsfältet.</span><span class="sxs-lookup"><span data-stu-id="dc14a-115">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Billing > Purchase services**.</span></span>

4. <span data-ttu-id="dc14a-116">På sidan **Köpa tjänster** hittar du **Enterprise Mobility + Security E5**-objekt.</span><span class="sxs-lookup"><span data-stu-id="dc14a-116">On the **Purchase services** page, find the **Enterprise Mobility + Security E5** item.</span></span> <span data-ttu-id="dc14a-117">Håll muspekaren över den och klicka på **Starta kostnadsfri utvärderingsversion**.</span><span class="sxs-lookup"><span data-stu-id="dc14a-117">Hover your mouse pointer over it and click **Start free trial**.</span></span>

5. <span data-ttu-id="dc14a-118">På sidan **Bekräfta din beställning** väljer du **Prova nu**.</span><span class="sxs-lookup"><span data-stu-id="dc14a-118">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="dc14a-119">På sidan **Beställningskvitto** klickar du **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="dc14a-119">On the **Order receipt** page, click **Continue**.</span></span>

<span data-ttu-id="dc14a-120">Aktivera sedan EMS E5-licensen för ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="dc14a-120">Next, enable the EMS E5 license for your global administrator account.</span></span>

1. <span data-ttu-id="dc14a-121">Klicka på **Användare > Aktiva användare** i det vänstra navigeringsfältet på fliken **Microsoft 365 administrationscenter** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="dc14a-121">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Users > Active users**.</span></span>

2. <span data-ttu-id="dc14a-122">Klicka på det globala administratörskontot och klicka sedan på **Redigera** för **Produktlicenser**.</span><span class="sxs-lookup"><span data-stu-id="dc14a-122">Click your global administrator account, and then click **Edit** for **Product licenses**.</span></span>

3. <span data-ttu-id="dc14a-123">I fönstret **Produktlicenser** ställer du in produktlicensen för **Enterprise Mobility + Security E5** till **På**, klickar **Spara** och klickar sedan två gånger på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="dc14a-123">On the **Product licenses** pane, turn the product license for **Enterprise Mobility + Security E5** to **On**, click **Save,** and then click **Close** twice.</span></span>

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups"></a><span data-ttu-id="dc14a-124">Steg 2: skapa och konfigurera Azure Active Directory-grupper (AD)</span><span class="sxs-lookup"><span data-stu-id="dc14a-124">Phase 2: Create and configure your Azure Active Directory (AD) groups</span></span>

<span data-ttu-id="dc14a-125">I den här fasen skapar och konfigurerar du Azure AD-grupper för din kampanj.</span><span class="sxs-lookup"><span data-stu-id="dc14a-125">In this phase, you create and configure the Azure AD groups for your campaign.</span></span>

<span data-ttu-id="dc14a-126">Börja med att skapa en uppsättning grupper för en typisk politisk kampanj med Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="dc14a-126">First, create a set of groups for a typical political campaign with the Azure portal.</span></span>

1. <span data-ttu-id="dc14a-127">Gå till Azure-portalen vid <https://portal.azure.com> på en separat flik i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="dc14a-127">On a separate tab in your browser, go to the Azure portal at <https://portal.azure.com>.</span></span> <span data-ttu-id="dc14a-128">Om det behövs loggar du in med inloggningsuppgifterna för det globala administratörskontot för din utvärderingsprenumeration av Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="dc14a-128">If needed, sign in with the credentials of the global administrator account for your Office 365 E5 trial subscription.</span></span>

2. <span data-ttu-id="dc14a-129">Klicka på **Azure Active Directory > Användare och grupper > Alla grupper** i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="dc14a-129">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>

3. <span data-ttu-id="dc14a-130">Utför följande steg för varje gruppnamn i den här listan:</span><span class="sxs-lookup"><span data-stu-id="dc14a-130">Do the following steps for each group name in this list:</span></span>

   - <span data-ttu-id="dc14a-131">Seniora och strategisk personal</span><span class="sxs-lookup"><span data-stu-id="dc14a-131">Senior and strategic staff</span></span>

   - <span data-ttu-id="dc14a-132">IT-personal</span><span class="sxs-lookup"><span data-stu-id="dc14a-132">IT staff</span></span>

   - <span data-ttu-id="dc14a-133">Analyspersonal</span><span class="sxs-lookup"><span data-stu-id="dc14a-133">Analytics staff</span></span>

   - <span data-ttu-id="dc14a-134">Normal baspersonal</span><span class="sxs-lookup"><span data-stu-id="dc14a-134">Regular core staff</span></span>

   - <span data-ttu-id="dc14a-135">Driftspersonal</span><span class="sxs-lookup"><span data-stu-id="dc14a-135">Operations staff</span></span>

   - <span data-ttu-id="dc14a-136">Fältpersonal</span><span class="sxs-lookup"><span data-stu-id="dc14a-136">Field staff</span></span>

1. <span data-ttu-id="dc14a-137">Gå till bladet **Alla grupper** och klicka på **+ Ny grupp**.</span><span class="sxs-lookup"><span data-stu-id="dc14a-137">On the **All groups** blade, click **+ New group**.</span></span>

2. <span data-ttu-id="dc14a-138">Skriv gruppens namn från listan i **namn**.</span><span class="sxs-lookup"><span data-stu-id="dc14a-138">Type the group name from the list in **Name**.</span></span>

3. <span data-ttu-id="dc14a-139">Välj **Dynamiska användare** i **Medlemskap**.</span><span class="sxs-lookup"><span data-stu-id="dc14a-139">Select **Dynamic user** in **Membership**.</span></span>

4. <span data-ttu-id="dc14a-140">Klicka på **Ja** för att **Aktivera Office-funktioner**.</span><span class="sxs-lookup"><span data-stu-id="dc14a-140">Click **Yes** for **Enable Office features**.</span></span>

5. <span data-ttu-id="dc14a-141">Klicka på **Lägg till dynamisk fråga**.</span><span class="sxs-lookup"><span data-stu-id="dc14a-141">Click **Add dynamic query**.</span></span>

6. <span data-ttu-id="dc14a-142">I **Lägg till användare där** väljer du **Avdelning**.</span><span class="sxs-lookup"><span data-stu-id="dc14a-142">In **Add users where**, select **department**.</span></span>

7. <span data-ttu-id="dc14a-143">I nästa fält väljer du **Är lika med**.</span><span class="sxs-lookup"><span data-stu-id="dc14a-143">In the next field, select **Equals**.</span></span>

8. <span data-ttu-id="dc14a-144">I nästa fält skriver du gruppnamnet från listan.</span><span class="sxs-lookup"><span data-stu-id="dc14a-144">In the next field, type the group name from the list.</span></span>

9. <span data-ttu-id="dc14a-145">Klicka på **Lägg till fråga** och klicka sedan på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="dc14a-145">Click **Add query**, and then click **Create**.</span></span>

10. <span data-ttu-id="dc14a-146">Klicka på **Användare och grupper – Alla grupper**.</span><span class="sxs-lookup"><span data-stu-id="dc14a-146">Click **Users and groups - All groups**.</span></span>

<span data-ttu-id="dc14a-147">Därefter konfigurerar du grupperna så att medlemmarna automatiskt tilldelas Office 365 E5- och EMS E5-licenser.</span><span class="sxs-lookup"><span data-stu-id="dc14a-147">Next, you configure the groups so that members are automatically assigned Office 365 E5 and EMS E5 licenses.</span></span>

1. <span data-ttu-id="dc14a-148">Klicka på **Azure Active Directory > Licenser > Alla produkter** i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="dc14a-148">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>

2. <span data-ttu-id="dc14a-149">Välj **Enterprise Mobility + Security E5** och **Office 365 Enterprise E5** och klicka sedan på **+ Tilldela**.</span><span class="sxs-lookup"><span data-stu-id="dc14a-149">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **+ Assign**.</span></span>

3. <span data-ttu-id="dc14a-150">I bladet **Tilldela licens** klickar du på **Användare och grupper**.</span><span class="sxs-lookup"><span data-stu-id="dc14a-150">In the **Assign license** blade, click **Users and groups**.</span></span>

4. <span data-ttu-id="dc14a-151">I listan med grupper väljer du följande:</span><span class="sxs-lookup"><span data-stu-id="dc14a-151">In the list of groups, select the following:</span></span>

   - <span data-ttu-id="dc14a-152">Analyspersonal</span><span class="sxs-lookup"><span data-stu-id="dc14a-152">Analytics staff</span></span>

   - <span data-ttu-id="dc14a-153">Fältpersonal</span><span class="sxs-lookup"><span data-stu-id="dc14a-153">Field staff</span></span>

   - <span data-ttu-id="dc14a-154">IT-personal</span><span class="sxs-lookup"><span data-stu-id="dc14a-154">IT staff</span></span>

   - <span data-ttu-id="dc14a-155">Driftspersonal</span><span class="sxs-lookup"><span data-stu-id="dc14a-155">Operations staff</span></span>

   - <span data-ttu-id="dc14a-156">Normal baspersonal</span><span class="sxs-lookup"><span data-stu-id="dc14a-156">Regular core staff</span></span>

   - <span data-ttu-id="dc14a-157">Seniora och strategisk personal</span><span class="sxs-lookup"><span data-stu-id="dc14a-157">Senior and strategic staff</span></span>

5. <span data-ttu-id="dc14a-158">Klicka **Välj** och klicka sedan **Tilldela**.</span><span class="sxs-lookup"><span data-stu-id="dc14a-158">Click **Select**, and then click **Assign**.</span></span>

6. <span data-ttu-id="dc14a-159">Stäng fliken Azure Portal i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="dc14a-159">Close the Azure portal tab in your browser.</span></span>

## <a name="phase-3-add-your-user-accounts"></a><span data-ttu-id="dc14a-160">Steg 3: lägga till användarkonton</span><span class="sxs-lookup"><span data-stu-id="dc14a-160">Phase 3: Add your user accounts</span></span>

<span data-ttu-id="dc14a-161">I den här fasen lägger du till exempelanvändarkonton för din politiska kampanj.</span><span class="sxs-lookup"><span data-stu-id="dc14a-161">In this phase, you add the example user accounts for your political campaign.</span></span>

<span data-ttu-id="dc14a-162">Först [Anslut med Azure Active Directory PowerShell för diagrammodulen](../../enterprise/connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="dc14a-162">First, you [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="dc14a-163">Därefter fyller du i ditt organisationsnamn, din plats och ett vanligt lösenord och kör dessa kommandon från PowerShells kommandotolk eller integrerat skriptmiljö (ISE):</span><span class="sxs-lookup"><span data-stu-id="dc14a-163">Next, you fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE):</span></span>

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
> <span data-ttu-id="dc14a-164">Användningen av ett vanligt lösenord här är för Automatisering och enklare konfiguration för en utvecklings-/testmiljö.</span><span class="sxs-lookup"><span data-stu-id="dc14a-164">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="dc14a-165">Detta rekommenderas inte för produktionsprenumerationer.</span><span class="sxs-lookup"><span data-stu-id="dc14a-165">This is not recommended for production subscriptions.</span></span> <span data-ttu-id="dc14a-166">När du loggar in med vart och ett av dessa nya användarkonton kommer du att uppmanas att ändra lösenordet.</span><span class="sxs-lookup"><span data-stu-id="dc14a-166">As you sign in with each of these new user accounts, you will be prompted to change the password.</span></span>

<span data-ttu-id="dc14a-167">Använd de här anvisningarna för att kontrollera att dynamiska gruppmedlemskap och gruppbaserad licensiering fungerar som de ska.</span><span class="sxs-lookup"><span data-stu-id="dc14a-167">Use these steps to verify that dynamic group membership and group-based licensing are working correctly.</span></span>

1. <span data-ttu-id="dc14a-168">På fliken **Microsoft Office Home** i webbläsaren klickar du på fliken **Administratör**.</span><span class="sxs-lookup"><span data-stu-id="dc14a-168">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>

2. <span data-ttu-id="dc14a-169">Klicka **Användare** under den nya fliken **administrationscentret för Microsoft 365** i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="dc14a-169">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>

3. <span data-ttu-id="dc14a-170">I listan över användare klickar du på **Kandidat**.</span><span class="sxs-lookup"><span data-stu-id="dc14a-170">In the list of users, click **Candidate**.</span></span>

4. <span data-ttu-id="dc14a-171">Kontrollera att du har en lista över egenskaperna för **Kandidat** användarkonto:</span><span class="sxs-lookup"><span data-stu-id="dc14a-171">In the pane that lists the properties of the **Candidate** user account, verify that:</span></span>

   - <span data-ttu-id="dc14a-172">Det är en medlem i gruppen **Seniora och strategisk personal** (i **Gruppmedlemskap**).</span><span class="sxs-lookup"><span data-stu-id="dc14a-172">It is a member of the **Senior and strategic staff** group (in **Group memberships**).</span></span>

   - <span data-ttu-id="dc14a-173">Den har tilldelats **Enterprise Mobility + Security E5**- och **Office 365 Enterprise E5**-licenser (i **Produktlicenser**).</span><span class="sxs-lookup"><span data-stu-id="dc14a-173">It has been assigned the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses (in **Product licenses**).</span></span>

5. <span data-ttu-id="dc14a-174">Stäng användarkontofönstret för **Kandidat**.</span><span class="sxs-lookup"><span data-stu-id="dc14a-174">Close the **Candidate** user account pane.</span></span>

## <a name="record-values-for-future-reference"></a><span data-ttu-id="dc14a-175">Skriv upp värden för framtida referens</span><span class="sxs-lookup"><span data-stu-id="dc14a-175">Record values for future reference</span></span>

<span data-ttu-id="dc14a-176">Skriv upp dessa värden för att arbeta med utvärderingsprenumerationer för Office 365 och EMS för denna utvecklings-/testmiljö:</span><span class="sxs-lookup"><span data-stu-id="dc14a-176">Record these values for working with the Office 365 and EMS trial subscriptions for this dev/test environment:</span></span>

- <span data-ttu-id="dc14a-177">Organisationens namn för utvärderingsversionen:</span><span class="sxs-lookup"><span data-stu-id="dc14a-177">Your trial subscription organization name:</span></span> ![Understrykning](../../media/Common-Images/TableLine.png)

  <span data-ttu-id="dc14a-179">Till exempel är ”contoso” organisationsnamnet för utvärderingsprenumerationen i domännamnet contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="dc14a-179">For example, for the trial subscription domain name of contoso.onmicrosoft.com, the organization name is "contoso".</span></span>

- <span data-ttu-id="dc14a-180">Det globala administratörsnamnet:</span><span class="sxs-lookup"><span data-stu-id="dc14a-180">The global administrator name:</span></span> ![Understrykning](../../media/Common-Images/TableLine.png)<span data-ttu-id="dc14a-182">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="dc14a-182">.onmicrosoft.com</span></span>

  <span data-ttu-id="dc14a-183">Anteckna lösenordet för kontot och det vanliga första lösenordet för de andra användarkontona på en säker plats.</span><span class="sxs-lookup"><span data-stu-id="dc14a-183">Record the password for this account and the common initial password for the other user accounts in a secure location.</span></span>

## <a name="next-step"></a><span data-ttu-id="dc14a-184">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="dc14a-184">Next step</span></span>

<span data-ttu-id="dc14a-185">Skapa fyra olika typer av SharePoint Online-gruppwebbplatser i den här utvecklings-/testmiljön med [Skapa gruppwebbplatser i en utvecklings-/testmiljö för en politisk kampanj](create-team-sites-in-a-political-campaign-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="dc14a-185">Build the four different types of SharePoint Online team sites in this dev/test environment with [Create team sites in a political campaign dev/test environment](create-team-sites-in-a-political-campaign-dev-test-environment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dc14a-186">Se även</span><span class="sxs-lookup"><span data-stu-id="dc14a-186">See also</span></span>

[<span data-ttu-id="dc14a-187">Microsofts säkerhetsvägledning för politiska kampanjer, ideella föreningar och andra Agila organisationer</span><span class="sxs-lookup"><span data-stu-id="dc14a-187">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="dc14a-188">Skapa gruppwebbplatser i en utvecklings-/testmiljö för en politisk kampanj</span><span class="sxs-lookup"><span data-stu-id="dc14a-188">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="dc14a-189">TLG (Test Lab Guides) för integrering med molntjänster</span><span class="sxs-lookup"><span data-stu-id="dc14a-189">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="dc14a-190">Integrering av moln- och hybridlösningar</span><span class="sxs-lookup"><span data-stu-id="dc14a-190">Cloud adoption and hybrid solutions</span></span>](/office365/enterprise/cloud-adoption-and-hybrid-solutions)