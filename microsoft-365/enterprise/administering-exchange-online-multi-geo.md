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
ms.openlocfilehash: ea7090cd65634138f9677960beab7770825a6e86
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950682"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="61737-103">Administrera Exchange Online-postlådor i en multi-geo-miljö</span><span class="sxs-lookup"><span data-stu-id="61737-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="61737-104">Exchange Online PowerShell krävs för att visa och konfigurera multi geo-egenskaper i din Microsoft 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="61737-104">Exchange Online PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="61737-105">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="61737-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="61737-106">Du behöver [Microsoft Azure Active Directory PowerShell modul](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v 1.1.166.0 eller senare i v1. x för att se egenskapen **PreferredDataLocation** för användar objekt.</span><span class="sxs-lookup"><span data-stu-id="61737-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="61737-107">De användar objekt som synkroniseras via AAD Connect into AAD kan inte ha sitt **PreferredDataLocation** -värde direkt ändrat via AAD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61737-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="61737-108">Endast molnbaserade användar objekt kan ändras via AAD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61737-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="61737-109">Information om hur du ansluter till Azure AD PowerShell finns i [ansluta till PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="61737-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="61737-110">Ansluta direkt till en Geo-plats med Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="61737-110">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="61737-111">Normalt ansluter Exchange Online PowerShell till Central geo-platsen.</span><span class="sxs-lookup"><span data-stu-id="61737-111">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="61737-112">Men du kan också ansluta direkt till satellit platser på andra ställen.</span><span class="sxs-lookup"><span data-stu-id="61737-112">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="61737-113">På grund av förbättringar av prestanda rekommenderar vi att du ansluter direkt till satellitens Geo plats när du bara hanterar användare på den platsen.</span><span class="sxs-lookup"><span data-stu-id="61737-113">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="61737-114">Kraven för att installera och använda EXO v2 finns beskrivna i [Installera och underhålla EXO v2-modulen](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span><span class="sxs-lookup"><span data-stu-id="61737-114">The requirements for installing and using the EXO V2 module are described in [Install and maintain the EXO V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

<span data-ttu-id="61737-115">Om du vill ansluta Exchange Online PowerShell till en specifik Geo-plats är *ConnectionUri* -parametern annorlunda än de vanliga anslutnings anvisningarna.</span><span class="sxs-lookup"><span data-stu-id="61737-115">To connect Exchange Online PowerShell to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="61737-116">Resten av kommandona och värdena är desamma.</span><span class="sxs-lookup"><span data-stu-id="61737-116">The rest of the commands and values are the same.</span></span>

<span data-ttu-id="61737-117">Specifikt måste du lägga till `?email=<emailaddress>` värdet i slutet av _ConnectionUri_ -värdet.</span><span class="sxs-lookup"><span data-stu-id="61737-117">Specifically, you need to add the `?email=<emailaddress>` value to end of the _ConnectionUri_ value.</span></span> <span data-ttu-id="61737-118">`<emailaddress>` är e-postadressen till **alla** post lådor på Geo-platsen för mål.</span><span class="sxs-lookup"><span data-stu-id="61737-118">`<emailaddress>` is the email address of **any** mailbox in the target geo location.</span></span> <span data-ttu-id="61737-119">Din behörighet till post lådan eller relationen till dina autentiseringsuppgifter är inte en faktor; e-postadressen säger bara till Exchange Online PowerShell för anslutning.</span><span class="sxs-lookup"><span data-stu-id="61737-119">Your permissions to that mailbox or the relationship to your credentials are not a factor; the email address simply tells Exchange Online PowerShell where to connect.</span></span>

<span data-ttu-id="61737-120">Microsoft 365 eller Microsoft 365 GCC-kunder behöver vanligt vis inte använda parametern _ConnectionUri_ för att ansluta till Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61737-120">Microsoft 365 or Microsoft 365 GCC customers typically don't need to use the _ConnectionUri_ parameter to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="61737-121">Men om du vill ansluta till en specifik Geo-plats måste du använda _ConnectionUri_ parameter så att du kan använda `?email=<emailaddress>` i värdet.</span><span class="sxs-lookup"><span data-stu-id="61737-121">But, to connect to a specific geo location, you do need to use _ConnectionUri_ parameter so you can use `?email=<emailaddress>` in the value.</span></span>

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-using-multi-factor-authentication-mfa"></a><span data-ttu-id="61737-122">Ansluta till en Geo-plats i Exchange Online PowerShell med multifaktorautentisering (MFA)</span><span class="sxs-lookup"><span data-stu-id="61737-122">Connect to a geo location in Exchange Online PowerShell using multi-factor authentication (MFA)</span></span>

1. <span data-ttu-id="61737-123">Öppna modulen EXO v2 i ett Windows PowerShell-fönster genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="61737-123">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="61737-124">I det här exemplet är admin@contoso.onmicrosoft.com administratörs konto och mål-geo-platsen där post lådans olga@contoso.onmicrosoft.com finns.</span><span class="sxs-lookup"><span data-stu-id="61737-124">In the following example, admin@contoso.onmicrosoft.com is the admin account, and the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

  ```powershell
  Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
  ```

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-without-using-mfa"></a><span data-ttu-id="61737-125">Ansluta till en Geo-plats i Exchange Online PowerShell utan MFA</span><span class="sxs-lookup"><span data-stu-id="61737-125">Connect to a geo location in Exchange Online PowerShell without using MFA</span></span>

1. <span data-ttu-id="61737-126">Öppna modulen EXO v2 i ett Windows PowerShell-fönster genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="61737-126">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="61737-127">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="61737-127">Run the following command:</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

   <span data-ttu-id="61737-128">I dialog rutan **begäran om autentiseringsuppgifter för Windows PowerShell** anger du ditt arbets-eller skol konto och lösen ord och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="61737-128">In the **Windows PowerShell Credential Request** dialog box that appears, type your work or school account and password, and then click **OK**.</span></span>

3. <span data-ttu-id="61737-129">I det här exemplet är mål-geo platsen där olga@contoso.onmicrosoft.com finns.</span><span class="sxs-lookup"><span data-stu-id="61737-129">In the following example, the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

   ```powershell
   Connect-ExchangeOnline -Credential $UserCredential -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="61737-130">Visa tillgängliga geo-platser som är konfigurerade i din Exchange Online-organisation</span><span class="sxs-lookup"><span data-stu-id="61737-130">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="61737-131">Om du vill visa en lista över konfigurerade geo-platser i Microsoft 365 multi-geo kör du följande kommando i Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="61737-131">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="61737-132">Visa Central geo-platsen för din Exchange Online-organisation</span><span class="sxs-lookup"><span data-stu-id="61737-132">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="61737-133">Om du vill visa klient organisationens centrala Geo-plats kör du följande kommando i Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="61737-133">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="61737-134">Hitta geo-platsen för en post låda</span><span class="sxs-lookup"><span data-stu-id="61737-134">Find the geo location of a mailbox</span></span>

<span data-ttu-id="61737-135">Cmdleten **Get-Mailbox** in Exchange Online PowerShell visar följande multi-geo-relaterade egenskaper i post lådorna:</span><span class="sxs-lookup"><span data-stu-id="61737-135">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="61737-136">**Databas**: de första 3 bokstäverna i databas namnet motsvarar geo-koden, vilket anger var post lådan finns.</span><span class="sxs-lookup"><span data-stu-id="61737-136">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="61737-137">För online-arkiv-post lådor ska egenskapen **ArchiveDatabase** användas.</span><span class="sxs-lookup"><span data-stu-id="61737-137">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="61737-138">**MailboxRegion**: anger den Geo-plats kod som angavs av administratören (synkroniserad från **PREFERREDDATALOCATION** i Azure AD).</span><span class="sxs-lookup"><span data-stu-id="61737-138">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="61737-139">**MailboxRegionLastUpdateTime**: anger när MailboxRegion senast uppdaterades (antingen automatiskt eller manuellt).</span><span class="sxs-lookup"><span data-stu-id="61737-139">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="61737-140">Använd följande syntax för att visa de här egenskaperna för en post låda:</span><span class="sxs-lookup"><span data-stu-id="61737-140">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="61737-141">Om du till exempel vill visa geo-platsens information om chris@contoso.onmicrosoft.com kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="61737-141">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="61737-142">Kommandot ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="61737-142">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="61737-143">Om den Geo-plats koden i databas namnet inte stämmer överens med **MailboxRegion** -värdet kommer post lådan automatiskt att placeras i en kö för lagring och flyttas till den Geo-plats som anges i **MailboxRegion** -värdet (Exchange Online letar efter en avvikelse mellan dessa egenskaps värden).</span><span class="sxs-lookup"><span data-stu-id="61737-143">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="61737-144">Flytta en befintlig brev låde post låda till en specifik Geo-plats</span><span class="sxs-lookup"><span data-stu-id="61737-144">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="61737-145">En användare som endast är en molnad användare är inte synkroniserad med klient organisationen via AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="61737-145">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="61737-146">Denna användare skapades direkt i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="61737-146">This user was created directly in Azure AD.</span></span> <span data-ttu-id="61737-147">Använd cmdletarna **Get-MsolUser** och **set-MSOLUSER** i Azure AD-modulen för Windows PowerShell för att visa eller ange den Geo-plats där en användares post låda i molnet lagras.</span><span class="sxs-lookup"><span data-stu-id="61737-147">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="61737-148">Om du vill visa **PreferredDataLocation** -värdet för en användare använder du denna syntax i Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="61737-148">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="61737-149">Om du till exempel vill visa **PreferredDataLocation** -värdet för användar Michelle@contoso.onmicrosoft.com kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="61737-149">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="61737-150">Om du vill ändra **PreferredDataLocation** -värdet för ett objekt i molnet kan du använda följande syntax i Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="61737-150">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="61737-151">Om du till exempel vill ange **PreferredDataLocation** -värdet till EU (EUR) geo för User Michelle@contoso.onmicrosoft.com kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="61737-151">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - <span data-ttu-id="61737-152">Som tidigare nämnts kan du inte använda den här proceduren för synkroniserade användar objekt från lokala Active Directory.</span><span class="sxs-lookup"><span data-stu-id="61737-152">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="61737-153">Du måste ändra värdet för **PreferredDataLocation** i Active Directory och synkronisera det med hjälp av AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="61737-153">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="61737-154">Mer information finns i [Azure Active Directory Connect Sync: konfigurera önskad data plats för Microsoft 365-resurser](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span><span class="sxs-lookup"><span data-stu-id="61737-154">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
>
> - <span data-ttu-id="61737-155">Hur lång tid det tar att hitta en post låda på en ny Geo-plats beror på flera faktorer:</span><span class="sxs-lookup"><span data-stu-id="61737-155">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
>
>   - <span data-ttu-id="61737-156">Storlek och typ av post låda.</span><span class="sxs-lookup"><span data-stu-id="61737-156">The size and type of mailbox.</span></span>
>   - <span data-ttu-id="61737-157">Antalet post lådor som flyttas.</span><span class="sxs-lookup"><span data-stu-id="61737-157">The number of mailboxes being moved.</span></span>
>   - <span data-ttu-id="61737-158">Tillgängligheten för att flytta resurser.</span><span class="sxs-lookup"><span data-stu-id="61737-158">The availability of move resources.</span></span>

### <a name="move-disabled-mailboxes-that-are-on-litigation-hold"></a><span data-ttu-id="61737-159">Flytta inaktiverade post lådor som har en tvist kvar</span><span class="sxs-lookup"><span data-stu-id="61737-159">Move disabled mailboxes that are on Litigation Hold</span></span>

<span data-ttu-id="61737-160">Inaktiverade post lådor i tvist spärr som bevaras för eDiscovery kan inte flyttas genom att ändra deras **PreferredDataLocation** -värde i inaktiverat läge.</span><span class="sxs-lookup"><span data-stu-id="61737-160">Disabled mailboxes on Litigation Hold that are preserved for eDiscovery purposes cannot be moved by changing their **PreferredDataLocation** value in their disabled state.</span></span> <span data-ttu-id="61737-161">Så här flyttar du en inaktive rad post låda i en tvist:</span><span class="sxs-lookup"><span data-stu-id="61737-161">To move a disabled mailbox on litigation hold:</span></span>

1. <span data-ttu-id="61737-162">Koppla tillfälligt en licens till post lådan.</span><span class="sxs-lookup"><span data-stu-id="61737-162">Temporarily assign a license to the mailbox.</span></span>

2. <span data-ttu-id="61737-163">Ändra **PreferredDataLocation**.</span><span class="sxs-lookup"><span data-stu-id="61737-163">Change the **PreferredDataLocation**.</span></span>

3. <span data-ttu-id="61737-164">Ta bort licensen från post lådan efter att den har flyttats till den valda geo-platsen för att den ska vara inaktive rad.</span><span class="sxs-lookup"><span data-stu-id="61737-164">Remove the license from the mailbox after it has been moved to the selected geo location to put it back into the disabled state.</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="61737-165">Skapa nya moln post lådor på en viss Geo-plats</span><span class="sxs-lookup"><span data-stu-id="61737-165">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="61737-166">Om du vill skapa en ny post låda på en specifik Geo-plats måste du göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="61737-166">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="61737-167">Konfigurera **PreferredDataLocation** -värdet enligt beskrivningen i föregående avsnitt *innan* post lådan skapas i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="61737-167">Configure the **PreferredDataLocation** value as described in the previous section *before* the mailbox is created in Exchange Online.</span></span> <span data-ttu-id="61737-168">Konfigurera till exempel värdet **PreferredDataLocation** för en användare innan du tilldelar en licens.</span><span class="sxs-lookup"><span data-stu-id="61737-168">For example, configure the **PreferredDataLocation** value on a user before assigning a license.</span></span>

- <span data-ttu-id="61737-169">Tilldela en licens samtidigt ställer du in **PreferredDataLocation** -värdet.</span><span class="sxs-lookup"><span data-stu-id="61737-169">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="61737-170">Om du vill skapa en ny moln-licensierad användare (inte AAD Connect Synchronized) på en specifik Geo-plats använder du följande syntax i Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="61737-170">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="61737-171">I det här exemplet skapas ett nytt användar konto för Elizabeth Brunner med följande värden:</span><span class="sxs-lookup"><span data-stu-id="61737-171">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="61737-172">Användarens huvud namn: ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="61737-172">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>
- <span data-ttu-id="61737-173">Förnamn: Elizabeth</span><span class="sxs-lookup"><span data-stu-id="61737-173">First name: Elizabeth</span></span>
- <span data-ttu-id="61737-174">Efter namn: Brunner</span><span class="sxs-lookup"><span data-stu-id="61737-174">Last name: Brunner</span></span>
- <span data-ttu-id="61737-175">Visnings namn: Elizabeth Brunner</span><span class="sxs-lookup"><span data-stu-id="61737-175">Display name: Elizabeth Brunner</span></span>
- <span data-ttu-id="61737-176">Lösen ord: skapas och visas slumpmässigt i resultatet av kommandot (eftersom det inte använder *lösen ords* parametern)</span><span class="sxs-lookup"><span data-stu-id="61737-176">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>
- <span data-ttu-id="61737-177">Licens: `contoso:ENTERPRISEPREMIUM` (E5)</span><span class="sxs-lookup"><span data-stu-id="61737-177">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>
- <span data-ttu-id="61737-178">Plats: Australien (Australien)</span><span class="sxs-lookup"><span data-stu-id="61737-178">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="61737-179">Mer information om hur du skapar nya användar konton och hittar LicenseAssignment värden i Azure AD PowerShell finns i [skapa användar konton med PowerShell](create-user-accounts-with-microsoft-365-powershell.md) och [Visa licenser och tjänster med PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="61737-179">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="61737-180">Om du använder Exchange Online PowerShell för att aktivera en post låda och behöver post lådan på en Geo-plats som anges i **PreferredDataLocation**, måste du använda en Exchange Online-cmdlet, till exempel **Aktivera-post låda** eller **ny-post låda** direkt mot moln tjänsten.</span><span class="sxs-lookup"><span data-stu-id="61737-180">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="61737-181">Om du använder cmdleten **Enable-RemoteMailbox** i lokal Exchange PowerShell skapas post lådan på den centrala geo-platsen.</span><span class="sxs-lookup"><span data-stu-id="61737-181">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="61737-182">Befintliga lokala post lådor på en viss Geo-plats</span><span class="sxs-lookup"><span data-stu-id="61737-182">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="61737-183">Du kan använda standardinställningarna för inbyggda verktyg och processer för att migrera en post låda från en lokal Exchange-organisation till Exchange Online, inklusive [instrument panelen för migrering i UK](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)och cmdleten [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61737-183">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="61737-184">Det första steget är att verifiera att ett User-objekt finns för varje post låda som ska registreras och att rätt **PreferredDataLocation** -värde är konfigurerat i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="61737-184">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="61737-185">De inbyggda verktygen påverkar **PreferredDataLocation** -värdet och migrerar post lådorna direkt till angiven Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="61737-185">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="61737-186">Eller så kan du använda följande steg för att hantera post lådor direkt i en viss Geo-plats med den nya cmdleten [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61737-186">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="61737-187">Verifiera att användarobjektet finns för varje post låda som ska registreras och att **PreferredDataLocation** är inställt på önskat värde i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="61737-187">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="61737-188">Värdet för **PreferredDataLocation** synkroniseras till attributet **MailboxRegion** för motsvarande e-postanvändarnamn i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="61737-188">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="61737-189">Anslut direkt till den specifika satellit platsen med anslutnings anvisningarna från tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="61737-189">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="61737-190">I Exchange Online PowerShell kan du lagra de lokala administratörs uppgifterna som används för att utföra en migrering av post lådor i en variabel genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="61737-190">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="61737-191">I Exchange Online PowerShell kan du skapa ett nytt **nytt-MoveRequest** som liknar det här exemplet:</span><span class="sxs-lookup"><span data-stu-id="61737-191">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="61737-192">Upprepa steg #4 för varje post låda som du måste migrera från lokalt Exchange till den satellitbaserade geo platsen du är ansluten till.</span><span class="sxs-lookup"><span data-stu-id="61737-192">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="61737-193">Om du behöver migrera ytterligare post lådor till olika satellit platser upprepar du steg 2 till 4 för varje specifik plats.</span><span class="sxs-lookup"><span data-stu-id="61737-193">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="61737-194">Multi-geo-rapportering</span><span class="sxs-lookup"><span data-stu-id="61737-194">Multi-geo reporting</span></span>

<span data-ttu-id="61737-195">**Flera geo rapporter för användning** i administrations centret för Microsoft 365 visar antalet användare per Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="61737-195">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="61737-196">I rapporten visas användar distribution för den aktuella månaden och historik för de senaste sex månaderna.</span><span class="sxs-lookup"><span data-stu-id="61737-196">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="61737-197">Se även</span><span class="sxs-lookup"><span data-stu-id="61737-197">See also</span></span>

[<span data-ttu-id="61737-198">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="61737-198">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
