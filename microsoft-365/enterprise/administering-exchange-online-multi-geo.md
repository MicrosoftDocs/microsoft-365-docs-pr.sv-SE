---
title: Administrera Exchange Online-postlådor i en multi-geo-miljö
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
localization_priority: normal
description: Lär dig hur du hanterar Exchange Online multi-geo-inställningar i din Microsoft 365-miljö med PowerShell.
ms.openlocfilehash: 645d48066ca02dbf3480e20ae30dc187f84293cf
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694315"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="b3933-103">Administrera Exchange Online-postlådor i en multi-geo-miljö</span><span class="sxs-lookup"><span data-stu-id="b3933-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="b3933-104">Remote PowerShell krävs för att visa och konfigurera multi geo-egenskaper i din Microsoft 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="b3933-104">Remote PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="b3933-105">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b3933-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="b3933-106">Du behöver [Microsoft Azure Active Directory PowerShell modul](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v 1.1.166.0 eller senare i v1. x för att se egenskapen **PreferredDataLocation** för användar objekt.</span><span class="sxs-lookup"><span data-stu-id="b3933-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="b3933-107">De användar objekt som synkroniseras via AAD Connect into AAD kan inte ha sitt **PreferredDataLocation** -värde direkt ändrat via AAD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3933-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="b3933-108">Endast molnbaserade användar objekt kan ändras via AAD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3933-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="b3933-109">Information om hur du ansluter till Azure AD PowerShell finns i [ansluta till PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="b3933-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="b3933-110">Ansluta direkt till en Geo-plats med Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3933-110">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="b3933-111">Normalt ansluter Exchange Online PowerShell till Central geo-platsen.</span><span class="sxs-lookup"><span data-stu-id="b3933-111">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="b3933-112">Men du kan också ansluta direkt till satellit platser på andra ställen.</span><span class="sxs-lookup"><span data-stu-id="b3933-112">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="b3933-113">På grund av förbättringar av prestanda rekommenderar vi att du ansluter direkt till satellitens Geo plats när du bara hanterar användare på den platsen.</span><span class="sxs-lookup"><span data-stu-id="b3933-113">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="b3933-114">Om du vill ansluta till en viss Geo-plats är *ConnectionUri* -parametern annorlunda än de vanliga anslutnings anvisningarna.</span><span class="sxs-lookup"><span data-stu-id="b3933-114">To connect to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="b3933-115">Resten av kommandona och värdena är desamma.</span><span class="sxs-lookup"><span data-stu-id="b3933-115">The rest of the commands and values are the same.</span></span> <span data-ttu-id="b3933-116">Stegen är:</span><span class="sxs-lookup"><span data-stu-id="b3933-116">The steps are:</span></span>

1. <span data-ttu-id="b3933-117">Öppna Windows PowerShell på din lokala dator och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="b3933-117">On your local computer, open Windows PowerShell and run the following command:</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

   <span data-ttu-id="b3933-118">I dialog rutan **begäran om autentiseringsuppgifter för Windows PowerShell** anger du ditt arbets-eller skol konto och lösen ord och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3933-118">In the **Windows PowerShell Credential Request** dialog box, type your work or school account and password, and then click **OK**.</span></span>

2. <span data-ttu-id="b3933-119">Ersätt `<emailaddress>` med e-postadressen för **en** post låda på mål-geo platsen och kör följande kommando.</span><span class="sxs-lookup"><span data-stu-id="b3933-119">Replace `<emailaddress>` with the email address of **any** mailbox in the target geo location and run the following command.</span></span> <span data-ttu-id="b3933-120">Din behörighet på post lådan och relationen till dina inloggnings uppgifter i steg 1 är inte en faktor; e-postadressen säger bara till Exchange Online var du kan ansluta.</span><span class="sxs-lookup"><span data-stu-id="b3933-120">Your permissions on the mailbox and the relationship to your credentials in Step 1 are not a factor; the email address simply tells Exchange Online where to connect.</span></span>
  
   ```powershell
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell?email=<emailaddress> -Credential $UserCredential -Authentication  Basic -AllowRedirection
   ```

   <span data-ttu-id="b3933-121">Om till exempel olga@contoso.onmicrosoft.com är e-postadressen till en giltig post låda på den Geo-plats där du vill ansluta kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="b3933-121">For example, if olga@contoso.onmicrosoft.com is the email address of a valid mailbox in the geo location where you want to connect, run the following command:</span></span>

   ```powershell
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com -Credential $UserCredential -Authentication  Basic -AllowRedirection
   ```

3. <span data-ttu-id="b3933-122">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="b3933-122">Run the following command:</span></span>

    ```powershell
    Import-PSSession $Session
    ```

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="b3933-123">Visa tillgängliga geo-platser som är konfigurerade i din Exchange Online-organisation</span><span class="sxs-lookup"><span data-stu-id="b3933-123">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="b3933-124">Om du vill visa en lista över konfigurerade geo-platser i Microsoft 365 multi-geo kör du följande kommando i Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b3933-124">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="b3933-125">Visa Central geo-platsen för din Exchange Online-organisation</span><span class="sxs-lookup"><span data-stu-id="b3933-125">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="b3933-126">Om du vill visa klient organisationens centrala Geo-plats kör du följande kommando i Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b3933-126">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="b3933-127">Hitta geo-platsen för en post låda</span><span class="sxs-lookup"><span data-stu-id="b3933-127">Find the geo location of a mailbox</span></span>

<span data-ttu-id="b3933-128">Cmdleten **Get-Mailbox** in Exchange Online PowerShell visar följande multi-geo-relaterade egenskaper i post lådorna:</span><span class="sxs-lookup"><span data-stu-id="b3933-128">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="b3933-129">**Databas**: de första 3 bokstäverna i databas namnet motsvarar geo-koden, vilket anger var post lådan finns.</span><span class="sxs-lookup"><span data-stu-id="b3933-129">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="b3933-130">För online-arkiv-post lådor ska egenskapen **ArchiveDatabase** användas.</span><span class="sxs-lookup"><span data-stu-id="b3933-130">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="b3933-131">**MailboxRegion**: anger den Geo-plats kod som angavs av administratören (synkroniserad från **PREFERREDDATALOCATION** i Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b3933-131">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="b3933-132">**MailboxRegionLastUpdateTime**: anger när MailboxRegion senast uppdaterades (antingen automatiskt eller manuellt).</span><span class="sxs-lookup"><span data-stu-id="b3933-132">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="b3933-133">Använd följande syntax för att visa de här egenskaperna för en post låda:</span><span class="sxs-lookup"><span data-stu-id="b3933-133">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="b3933-134">Om du till exempel vill visa geo-platsens information om chris@contoso.onmicrosoft.com kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="b3933-134">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="b3933-135">Kommandot ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="b3933-135">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="b3933-136">Om den Geo-plats koden i databas namnet inte stämmer överens med **MailboxRegion** -värdet kommer post lådan automatiskt att placeras i en kö för lagring och flyttas till den Geo-plats som anges i **MailboxRegion** -värdet (Exchange Online letar efter en avvikelse mellan dessa egenskaps värden).</span><span class="sxs-lookup"><span data-stu-id="b3933-136">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="b3933-137">Flytta en befintlig brev låde post låda till en specifik Geo-plats</span><span class="sxs-lookup"><span data-stu-id="b3933-137">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="b3933-138">En användare som endast är en molnad användare är inte synkroniserad med klient organisationen via AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="b3933-138">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="b3933-139">Denna användare skapades direkt i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b3933-139">This user was created directly in Azure AD.</span></span> <span data-ttu-id="b3933-140">Använd cmdletarna **Get-MsolUser** och **set-MSOLUSER** i Azure AD-modulen för Windows PowerShell för att visa eller ange den Geo-plats där en användares post låda i molnet lagras.</span><span class="sxs-lookup"><span data-stu-id="b3933-140">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="b3933-141">Om du vill visa **PreferredDataLocation** -värdet för en användare använder du denna syntax i Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b3933-141">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="b3933-142">Om du till exempel vill visa **PreferredDataLocation** -värdet för användar Michelle@contoso.onmicrosoft.com kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="b3933-142">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="b3933-143">Om du vill ändra **PreferredDataLocation** -värdet för ett objekt i molnet kan du använda följande syntax i Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b3933-143">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="b3933-144">Om du till exempel vill ange **PreferredDataLocation** -värdet till EU (EUR) geo för User Michelle@contoso.onmicrosoft.com kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="b3933-144">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
> - <span data-ttu-id="b3933-145">Som tidigare nämnts kan du inte använda den här proceduren för synkroniserade användar objekt från lokala Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b3933-145">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="b3933-146">Du måste ändra värdet för **PreferredDataLocation** i Active Directory och synkronisera det med hjälp av AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="b3933-146">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="b3933-147">Mer information finns i [Azure Active Directory Connect Sync: konfigurera önskad data plats för Microsoft 365-resurser](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span><span class="sxs-lookup"><span data-stu-id="b3933-147">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
> 
> - <span data-ttu-id="b3933-148">Hur lång tid det tar att hitta en post låda på en ny Geo-plats beror på flera faktorer:</span><span class="sxs-lookup"><span data-stu-id="b3933-148">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
> 
>   - <span data-ttu-id="b3933-149">Storlek och typ av post låda.</span><span class="sxs-lookup"><span data-stu-id="b3933-149">The size and type of mailbox.</span></span>
> 
>   - <span data-ttu-id="b3933-150">Antalet post lådor som flyttas.</span><span class="sxs-lookup"><span data-stu-id="b3933-150">The number of mailboxes being moved.</span></span>
> 
>   - <span data-ttu-id="b3933-151">Tillgängligheten för att flytta resurser.</span><span class="sxs-lookup"><span data-stu-id="b3933-151">The availability of move resources.</span></span>

### <a name="move-disabled-mailboxes-that-are-on-litigation-hold"></a><span data-ttu-id="b3933-152">Flytta inaktiverade post lådor som har en tvist kvar</span><span class="sxs-lookup"><span data-stu-id="b3933-152">Move disabled mailboxes that are on Litigation Hold</span></span>

<span data-ttu-id="b3933-153">Inaktiverade post lådor i tvist spärr som bevaras för eDiscovery kan inte flyttas genom att ändra deras **PreferredDataLocation** -värde i inaktiverat läge.</span><span class="sxs-lookup"><span data-stu-id="b3933-153">Disabled mailboxes on Litigation Hold that are preserved for eDiscovery purposes cannot be moved by changing their **PreferredDataLocation** value in their disabled state.</span></span> <span data-ttu-id="b3933-154">Så här flyttar du en inaktive rad post låda i en tvist:</span><span class="sxs-lookup"><span data-stu-id="b3933-154">To move a disabled mailbox on litigation hold:</span></span>

1. <span data-ttu-id="b3933-155">Koppla tillfälligt en licens till post lådan.</span><span class="sxs-lookup"><span data-stu-id="b3933-155">Temporarily assign a license to the mailbox.</span></span>

2. <span data-ttu-id="b3933-156">Ändra **PreferredDataLocation**.</span><span class="sxs-lookup"><span data-stu-id="b3933-156">Change the **PreferredDataLocation**.</span></span>

3. <span data-ttu-id="b3933-157">Ta bort licensen från post lådan efter att den har flyttats till den valda geo-platsen för att den ska vara inaktive rad.</span><span class="sxs-lookup"><span data-stu-id="b3933-157">Remove the license from the mailbox after it has been moved to the selected geo location to put it back into the disabled state.</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="b3933-158">Skapa nya moln post lådor på en viss Geo-plats</span><span class="sxs-lookup"><span data-stu-id="b3933-158">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="b3933-159">Om du vill skapa en ny post låda på en specifik Geo-plats måste du göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="b3933-159">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="b3933-160">Konfigurera **PreferredDataLocation** -värdet enligt beskrivningen i föregående avsnitt *innan* post lådan skapas i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b3933-160">Configure the **PreferredDataLocation** value as described in the previous section *before* the mailbox is created in Exchange Online.</span></span> <span data-ttu-id="b3933-161">Konfigurera till exempel värdet **PreferredDataLocation** för en användare innan du tilldelar en licens.</span><span class="sxs-lookup"><span data-stu-id="b3933-161">For example, configure the **PreferredDataLocation** value on a user before assigning a license.</span></span>

- <span data-ttu-id="b3933-162">Tilldela en licens samtidigt ställer du in **PreferredDataLocation** -värdet.</span><span class="sxs-lookup"><span data-stu-id="b3933-162">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="b3933-163">Om du vill skapa en ny moln-licensierad användare (inte AAD Connect Synchronized) på en specifik Geo-plats använder du följande syntax i Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b3933-163">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="b3933-164">I det här exemplet skapas ett nytt användar konto för Elizabeth Brunner med följande värden:</span><span class="sxs-lookup"><span data-stu-id="b3933-164">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="b3933-165">Användarens huvud namn: ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="b3933-165">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>

- <span data-ttu-id="b3933-166">Förnamn: Elizabeth</span><span class="sxs-lookup"><span data-stu-id="b3933-166">First name: Elizabeth</span></span>

- <span data-ttu-id="b3933-167">Efter namn: Brunner</span><span class="sxs-lookup"><span data-stu-id="b3933-167">Last name: Brunner</span></span>

- <span data-ttu-id="b3933-168">Visnings namn: Elizabeth Brunner</span><span class="sxs-lookup"><span data-stu-id="b3933-168">Display name: Elizabeth Brunner</span></span>

- <span data-ttu-id="b3933-169">Lösen ord: skapas och visas slumpmässigt i resultatet av kommandot (eftersom det inte använder *lösen ords* parametern)</span><span class="sxs-lookup"><span data-stu-id="b3933-169">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>

- <span data-ttu-id="b3933-170">Licens: `contoso:ENTERPRISEPREMIUM` (E5)</span><span class="sxs-lookup"><span data-stu-id="b3933-170">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>

- <span data-ttu-id="b3933-171">Plats: Australien (Australien)</span><span class="sxs-lookup"><span data-stu-id="b3933-171">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="b3933-172">Mer information om hur du skapar nya användar konton och hittar LicenseAssignment värden i Azure AD PowerShell finns i [skapa användar konton med PowerShell](create-user-accounts-with-microsoft-365-powershell.md) och [Visa licenser och tjänster med PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="b3933-172">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b3933-173">Om du använder Exchange Online PowerShell för att aktivera en post låda och behöver post lådan på en Geo-plats som anges i **PreferredDataLocation**, måste du använda en Exchange Online-cmdlet, till exempel **Aktivera-post låda** eller **ny-post låda** direkt mot moln tjänsten.</span><span class="sxs-lookup"><span data-stu-id="b3933-173">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="b3933-174">Om du använder cmdleten **Enable-RemoteMailbox** i lokal Exchange PowerShell skapas post lådan på den centrala geo-platsen.</span><span class="sxs-lookup"><span data-stu-id="b3933-174">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="b3933-175">Befintliga lokala post lådor på en viss Geo-plats</span><span class="sxs-lookup"><span data-stu-id="b3933-175">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="b3933-176">Du kan använda standardinställningarna för inbyggda verktyg och processer för att migrera en post låda från en lokal Exchange-organisation till Exchange Online, inklusive [instrument panelen för migrering i UK](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)och cmdleten [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3933-176">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="b3933-177">Det första steget är att verifiera att ett User-objekt finns för varje post låda som ska registreras och att rätt **PreferredDataLocation** -värde är konfigurerat i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b3933-177">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="b3933-178">De inbyggda verktygen påverkar **PreferredDataLocation** -värdet och migrerar post lådorna direkt till angiven Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="b3933-178">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="b3933-179">Eller så kan du använda följande steg för att hantera post lådor direkt i en viss Geo-plats med den nya cmdleten [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3933-179">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="b3933-180">Verifiera att användarobjektet finns för varje post låda som ska registreras och att **PreferredDataLocation** är inställt på önskat värde i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b3933-180">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="b3933-181">Värdet för **PreferredDataLocation** synkroniseras till attributet **MailboxRegion** för motsvarande e-postanvändarnamn i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b3933-181">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="b3933-182">Anslut direkt till den specifika satellit platsen med anslutnings anvisningarna från tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="b3933-182">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="b3933-183">I Exchange Online PowerShell kan du lagra de lokala administratörs uppgifterna som används för att utföra en migrering av post lådor i en variabel genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="b3933-183">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="b3933-184">I Exchange Online PowerShell kan du skapa ett nytt **nytt-MoveRequest** som liknar det här exemplet:</span><span class="sxs-lookup"><span data-stu-id="b3933-184">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="b3933-185">Upprepa steg #4 för varje post låda som du måste migrera från lokalt Exchange till den satellitbaserade geo platsen du är ansluten till.</span><span class="sxs-lookup"><span data-stu-id="b3933-185">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="b3933-186">Om du behöver migrera ytterligare post lådor till olika satellit platser upprepar du steg 2 till 4 för varje specifik plats.</span><span class="sxs-lookup"><span data-stu-id="b3933-186">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="b3933-187">Multi-geo-rapportering</span><span class="sxs-lookup"><span data-stu-id="b3933-187">Multi-geo reporting</span></span>

<span data-ttu-id="b3933-188">**Flera geo rapporter för användning** i administrations centret för Microsoft 365 visar antalet användare per Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="b3933-188">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="b3933-189">I rapporten visas användar distribution för den aktuella månaden och historik för de senaste sex månaderna.</span><span class="sxs-lookup"><span data-stu-id="b3933-189">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3933-190">Se även</span><span class="sxs-lookup"><span data-stu-id="b3933-190">See also</span></span>

[<span data-ttu-id="b3933-191">Hantera Microsoft 365 och Exchange Online med Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3933-191">Managing Microsoft 365 and Exchange Online with Windows PowerShell</span></span>](https://support.office.com//article/06a743bb-ceb6-49a9-a61d-db4ffdf54fa6)
