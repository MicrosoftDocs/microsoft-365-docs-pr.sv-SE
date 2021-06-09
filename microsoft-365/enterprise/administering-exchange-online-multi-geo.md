---
title: Administrera Exchange Online postlådor i en miljö med flera geografiska miljöer
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
description: Lär dig hur du Exchange Online fler geoinställningar i din Microsoft 365-miljö med PowerShell.
ms.openlocfilehash: c8f06318313c4192fc2b3a289727933c5a54f3ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905590"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="23f3a-103">Administrera Exchange Online postlådor i en miljö med flera geografiska miljöer</span><span class="sxs-lookup"><span data-stu-id="23f3a-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="23f3a-104">Exchange Online PowerShell krävs för att visa och konfigurera flera geoegenskaper i Microsoft 365 miljö.</span><span class="sxs-lookup"><span data-stu-id="23f3a-104">Exchange Online PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="23f3a-105">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="23f3a-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="23f3a-106">Du behöver [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 eller senare i v1.x för att kunna se egenskapen **PreferredDataLocation** för användarobjekt.</span><span class="sxs-lookup"><span data-stu-id="23f3a-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="23f3a-107">Användarobjekt som synkroniseras via AAD Anslut till AAD kan inte få sitt **PreferredDataLocation-värde** direkt ändrat via AAD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23f3a-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="23f3a-108">Användarobjekt som bara är molnbaserade kan ändras via AAD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23f3a-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="23f3a-109">Information om hur du ansluter till Azure AD PowerShell finns [Anslut till PowerShell.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="23f3a-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="23f3a-110">I Exchange Online geomiljöer behöver du inte göra några manuella steg för att lägga till geos i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="23f3a-110">In Exchange Online multi-geo environments, you don't need to do any manual steps to add geos to your tenant.</span></span> <span data-ttu-id="23f3a-111">När du får ett meddelandecenterinlägg som säger att multi-geo är redo Exchange Online, kommer alla tillgängliga geos att vara klara och konfigurerade att användas.</span><span class="sxs-lookup"><span data-stu-id="23f3a-111">After you receive the Message Center post that says multi-geo is ready for Exchange Online, all available geos will be ready and configured for you to use.</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="23f3a-112">Anslut direkt till en geoplats med hjälp Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="23f3a-112">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="23f3a-113">PowerShell Exchange Online vanligtvis till den centrala geoplatsen.</span><span class="sxs-lookup"><span data-stu-id="23f3a-113">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="23f3a-114">Men du kan också ansluta direkt till satellitgeoplatser.</span><span class="sxs-lookup"><span data-stu-id="23f3a-114">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="23f3a-115">På grund av prestandaförbättringar rekommenderar vi att ansluta direkt till satellit geoplatsen när du bara hanterar användare på den platsen.</span><span class="sxs-lookup"><span data-stu-id="23f3a-115">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="23f3a-116">Kraven för installation och användning av EXO V2-modulen beskrivs i [Installera och underhålla EXO V2-modulen.](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)</span><span class="sxs-lookup"><span data-stu-id="23f3a-116">The requirements for installing and using the EXO V2 module are described in [Install and maintain the EXO V2 module](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

<span data-ttu-id="23f3a-117">När du Exchange Online powershell till en viss geoplats skiljer sig *ConnectionUri-parametern* från de vanliga anslutningsinstruktionerna.</span><span class="sxs-lookup"><span data-stu-id="23f3a-117">To connect Exchange Online PowerShell to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="23f3a-118">Resten av kommandona och värdena är desamma.</span><span class="sxs-lookup"><span data-stu-id="23f3a-118">The rest of the commands and values are the same.</span></span>

<span data-ttu-id="23f3a-119">Mer specifikt måste du lägga till `?email=<emailaddress>` värdet i slutet av värdet för _ConnectionUri._</span><span class="sxs-lookup"><span data-stu-id="23f3a-119">Specifically, you need to add the `?email=<emailaddress>` value to end of the _ConnectionUri_ value.</span></span> <span data-ttu-id="23f3a-120">`<emailaddress>` är e-postadressen **till alla** postlådor på den geografiska målplatsen.</span><span class="sxs-lookup"><span data-stu-id="23f3a-120">`<emailaddress>` is the email address of **any** mailbox in the target geo location.</span></span> <span data-ttu-id="23f3a-121">Dina behörigheter till den postlådan eller relationen till dina autentiseringsuppgifter är inte en faktor. e-postadressen talar bara om Exchange Online PowerShell var du ska ansluta.</span><span class="sxs-lookup"><span data-stu-id="23f3a-121">Your permissions to that mailbox or the relationship to your credentials are not a factor; the email address simply tells Exchange Online PowerShell where to connect.</span></span>

<span data-ttu-id="23f3a-122">Microsoft 365 eller Microsoft 365 GCC behöver kunder vanligtvis inte använda _parametern ConnectionUri_ för att ansluta till Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23f3a-122">Microsoft 365 or Microsoft 365 GCC customers typically don't need to use the _ConnectionUri_ parameter to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="23f3a-123">Men om du vill ansluta till en viss geoplats måste du använda _ConnectionUri-parameter_ så att du kan `?email=<emailaddress>` använda det i värdet.</span><span class="sxs-lookup"><span data-stu-id="23f3a-123">But, to connect to a specific geo location, you do need to use _ConnectionUri_ parameter so you can use `?email=<emailaddress>` in the value.</span></span>

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a><span data-ttu-id="23f3a-124">Anslut till en geoplats i Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="23f3a-124">Connect to a geo location in Exchange Online PowerShell</span></span>

<span data-ttu-id="23f3a-125">Följande anslutningsinstruktioner fungerar för konton som är eller inte har konfigurerats för multifaktorautentisering (MFA).</span><span class="sxs-lookup"><span data-stu-id="23f3a-125">The following connection instructions work for accounts that are or aren't configured for multi-factor authentication (MFA).</span></span>

1. <span data-ttu-id="23f3a-126">I ett Windows PowerShell läser du in EXO V2-modulen genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="23f3a-126">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="23f3a-127">I följande exempel admin@contoso.onmicrosoft.com administratörskontot, och den geografiska målplatsen är den plats postlådan olga@contoso.onmicrosoft.com finns.</span><span class="sxs-lookup"><span data-stu-id="23f3a-127">In the following example, admin@contoso.onmicrosoft.com is the admin account, and the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. <span data-ttu-id="23f3a-128">Ange lösenordet för den admin@contoso.onmicrosoft.com i uppmaningen som visas.</span><span class="sxs-lookup"><span data-stu-id="23f3a-128">Enter the password for the admin@contoso.onmicrosoft.com in the prompt that appears.</span></span> <span data-ttu-id="23f3a-129">Om kontot har konfigurerats för MFA måste du också ange säkerhetskoden.</span><span class="sxs-lookup"><span data-stu-id="23f3a-129">If the account is configured for MFA, you also need to enter the security code.</span></span>

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="23f3a-130">Visa tillgängliga geoplatser som är konfigurerade i din Exchange Online organisation</span><span class="sxs-lookup"><span data-stu-id="23f3a-130">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="23f3a-131">Om du vill se en lista över konfigurerade geoplatser i Microsoft 365 Multi-Geo kör du följande kommando i Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="23f3a-131">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="23f3a-132">Visa den centrala geoplatsen för din Exchange Online organisation</span><span class="sxs-lookup"><span data-stu-id="23f3a-132">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="23f3a-133">Om du vill visa klientorganisationens centrala geoplats kör du följande kommando i Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="23f3a-133">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="23f3a-134">Hitta en postlådas geoplats</span><span class="sxs-lookup"><span data-stu-id="23f3a-134">Find the geo location of a mailbox</span></span>

<span data-ttu-id="23f3a-135">**Cmdlet:en Get-Mailbox** i Exchange Online PowerShell visar följande multigeorelaterade egenskaper för postlådor:</span><span class="sxs-lookup"><span data-stu-id="23f3a-135">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="23f3a-136">**Databas:** De tre första bokstäverna i databasnamnet motsvarar geokoden som anger var postlådan finns för närvarande.</span><span class="sxs-lookup"><span data-stu-id="23f3a-136">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="23f3a-137">För onlinearkivpostlådor **ska egenskapen ArchiveDatabase** användas.</span><span class="sxs-lookup"><span data-stu-id="23f3a-137">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="23f3a-138">**MailboxRegion:** Anger den geoplatskod som angetts av administratören (synkroniserad från **PreferredDataLocation** i Azure AD).</span><span class="sxs-lookup"><span data-stu-id="23f3a-138">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="23f3a-139">**MailboxRegionLastUpdateTime**: Anger när MailboxRegion uppdaterades senast (antingen automatiskt eller manuellt).</span><span class="sxs-lookup"><span data-stu-id="23f3a-139">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="23f3a-140">Om du vill visa de här egenskaperna för en postlåda använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="23f3a-140">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="23f3a-141">Om du till exempel vill se information om platsen för postlådan chris@contoso.onmicrosoft.com du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="23f3a-141">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="23f3a-142">Kommandots utdata ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="23f3a-142">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="23f3a-143">Om geoplatskoden i databasnamnet inte stämmer överens med värdet **MailboxRegion** sätts postlådan automatiskt till en kö för en relation och flyttas till den geoplats som anges av **värdet MailboxRegion** (Exchange Online letar efter en felaktig matchning mellan dessa egenskapsvärden).</span><span class="sxs-lookup"><span data-stu-id="23f3a-143">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="23f3a-144">Flytta en befintlig molnbaserad postlåda till en viss geoplats</span><span class="sxs-lookup"><span data-stu-id="23f3a-144">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="23f3a-145">En användare med endast molnet är en användare som inte synkroniseras till klientorganisationen via AAD Anslut.</span><span class="sxs-lookup"><span data-stu-id="23f3a-145">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="23f3a-146">Den här användaren skapades direkt i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="23f3a-146">This user was created directly in Azure AD.</span></span> <span data-ttu-id="23f3a-147">Använd **cmdletarna Get-MsolUser** och **Set-MsolUser** i Azure AD-modulen för Windows PowerShell för att visa eller ange den geoplats där en molnbaserad användares postlåda ska lagras.</span><span class="sxs-lookup"><span data-stu-id="23f3a-147">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="23f3a-148">Om du vill **visa värdet PreferredDataLocation** för en användare använder du följande syntax i Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="23f3a-148">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="23f3a-149">Om du till exempel vill **visa värdet PreferredDataLocation** för michelle@contoso.onmicrosoft.com kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="23f3a-149">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="23f3a-150">Om du vill **ändra värdet PreferredDataLocation** för ett användarobjekt med enbart molnet använder du följande syntax i Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="23f3a-150">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="23f3a-151">Om du till exempel vill ställa in **värdet PreferredDataLocation** till den europeiska unionen (EUR) för användaren michelle@contoso.onmicrosoft.com, kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="23f3a-151">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - <span data-ttu-id="23f3a-152">Som nämndes tidigare kan du inte använda den här proceduren för synkroniserade användarobjekt från en lokal Active Directory.</span><span class="sxs-lookup"><span data-stu-id="23f3a-152">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="23f3a-153">Du måste ändra värdet **för PreferredDataLocation i** Active Directory och synkronisera det med hjälp av AAD Anslut.</span><span class="sxs-lookup"><span data-stu-id="23f3a-153">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="23f3a-154">Mer information finns i Azure Active Directory Anslut [synkronisering: Konfigurera önskad dataplats för Microsoft 365 resurser.](/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation)</span><span class="sxs-lookup"><span data-stu-id="23f3a-154">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
>
> - <span data-ttu-id="23f3a-155">Hur lång tid det tar att flytta en postlåda till en ny geoplats beror på flera faktorer:</span><span class="sxs-lookup"><span data-stu-id="23f3a-155">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
>
>   - <span data-ttu-id="23f3a-156">Storlek och typ av postlåda.</span><span class="sxs-lookup"><span data-stu-id="23f3a-156">The size and type of mailbox.</span></span>
>   - <span data-ttu-id="23f3a-157">Antalet postlådor som flyttas.</span><span class="sxs-lookup"><span data-stu-id="23f3a-157">The number of mailboxes being moved.</span></span>
>   - <span data-ttu-id="23f3a-158">Tillgängligheten för flyttningsresurser.</span><span class="sxs-lookup"><span data-stu-id="23f3a-158">The availability of move resources.</span></span>

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a><span data-ttu-id="23f3a-159">Flytta en inaktiv postlåda till en viss geo</span><span class="sxs-lookup"><span data-stu-id="23f3a-159">Move an inactive mailbox to a specific geo</span></span>

<span data-ttu-id="23f3a-160">Du kan inte flytta inaktiva postlådor som bevaras i efterlevnadssyfte (till exempel postlådor för bevarande av juridiska skäl) genom att ändra deras **PreferredDataLocation-värde.**</span><span class="sxs-lookup"><span data-stu-id="23f3a-160">You can't move inactive mailboxes that are preserved for compliance purposes (for example, mailboxes on Litigation Hold) by changing their **PreferredDataLocation** value.</span></span> <span data-ttu-id="23f3a-161">Så här flyttar du en inaktiv postlåda till en annan geopostlåda:</span><span class="sxs-lookup"><span data-stu-id="23f3a-161">To move an inactive mailbox to a different geo, do the following steps:</span></span>

1. <span data-ttu-id="23f3a-162">Återställa den inaktiva postlådan.</span><span class="sxs-lookup"><span data-stu-id="23f3a-162">Recover the inactive mailbox.</span></span> <span data-ttu-id="23f3a-163">Instruktioner finns i Återställa [en inaktiv postlåda.](../compliance/recover-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="23f3a-163">For instructions, see [Recover an inactive mailbox](../compliance/recover-an-inactive-mailbox.md).</span></span>

2. <span data-ttu-id="23f3a-164">Förhindra assistenten för hanterade mappar från att bearbeta den återställda postlådan genom att ersätta med namn, alias, konto eller e-postadress för postlådan och köra följande kommando \<MailboxIdentity\> [i Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="23f3a-164">Prevent the Managed Folder Assistant from processing the recovered mailbox by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. <span data-ttu-id="23f3a-165">Tilldela en **licens Exchange Online abonnemang 2 till** den återskapade postlådan.</span><span class="sxs-lookup"><span data-stu-id="23f3a-165">Assign an **Exchange Online Plan 2** license to the recovered mailbox.</span></span> <span data-ttu-id="23f3a-166">Det här steget krävs för att placera postlådan i Bevarande av juridiska skäl igen.</span><span class="sxs-lookup"><span data-stu-id="23f3a-166">This step is required to place the mailbox back on Litigation Hold.</span></span> <span data-ttu-id="23f3a-167">Anvisningar finns i [Tilldela licenser till användare.](../admin/manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="23f3a-167">For instructions, see [Assign licenses to users](../admin/manage/assign-licenses-to-users.md).</span></span>

4. <span data-ttu-id="23f3a-168">Konfigurera värdet **PreferredDataLocation** för postlådan enligt beskrivningen i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="23f3a-168">Configure the **PreferredDataLocation** value on the mailbox as described in the previous section.</span></span>

5. <span data-ttu-id="23f3a-169">När du har bekräftat att postlådan har flyttats till den nya geoplatsen placerar du den återskapade postlådan i Bevarande av juridiska skäl.</span><span class="sxs-lookup"><span data-stu-id="23f3a-169">After you've confirmed that the mailbox has moved to the new geo location, place the recovered mailbox back on Litigation Hold.</span></span> <span data-ttu-id="23f3a-170">Anvisningar finns i Placera [en postlåda i bevarande av juridiska skäl.](../compliance/create-a-litigation-hold.md#place-a-mailbox-on-litigation-hold)</span><span class="sxs-lookup"><span data-stu-id="23f3a-170">For instructions, see [Place a mailbox on Litigation Hold](../compliance/create-a-litigation-hold.md#place-a-mailbox-on-litigation-hold).</span></span>

6. <span data-ttu-id="23f3a-171">När du har verifierat att bevarande av juridiska skäl är på plats kan du låta assistenten för hanterade mappar bearbeta postlådan igen genom att ersätta med namn, alias, konto eller e-postadress för postlådan och köra följande kommando i \<MailboxIdentity\> [Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="23f3a-171">After verifying that the Litigation Hold is in place, allow the Managed Folder Assistant to process the mailbox again by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. <span data-ttu-id="23f3a-172">Gör postlådan inaktiv igen genom att ta bort användarkontot som är kopplat till postlådan.</span><span class="sxs-lookup"><span data-stu-id="23f3a-172">Make the mailbox inactive again by removing the user account that's associated with the mailbox.</span></span> <span data-ttu-id="23f3a-173">Instruktioner finns i Ta [bort en användare från organisationen.](../admin/add-users/delete-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="23f3a-173">For instructions, see [Delete a user from your organization](../admin/add-users/delete-a-user.md).</span></span> <span data-ttu-id="23f3a-174">Det här steget släpper även Exchange Online abonnemang 2 för annan användning.</span><span class="sxs-lookup"><span data-stu-id="23f3a-174">This step also releases the Exchange Online Plan 2 license for other uses.</span></span>

<span data-ttu-id="23f3a-175">**Obs!** När du flyttar en inaktiv postlåda till en annan geoplats kan du påverka sökresultaten för innehåll eller möjligheten att söka i postlådan från den tidigare geoplatsen.</span><span class="sxs-lookup"><span data-stu-id="23f3a-175">**Note**: When you move an inactive mailbox to a different geo location, you might affect content search results or the ability to search the mailbox from the former geo location.</span></span> <span data-ttu-id="23f3a-176">Mer information finns i [Söka efter och exportera innehåll i multigeobaserade miljöer.](../compliance/set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments)</span><span class="sxs-lookup"><span data-stu-id="23f3a-176">For more information, see [Searching and exporting content in Multi-Geo environments](../compliance/set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments).</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="23f3a-177">Skapa nya molnbaserade postlådor på en viss geoplats</span><span class="sxs-lookup"><span data-stu-id="23f3a-177">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="23f3a-178">Om du vill skapa en ny postlåda på en viss geoplats måste du göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="23f3a-178">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="23f3a-179">Konfigurera **värdet preferredDataLocation** enligt beskrivningen i föregående Flytta en befintlig postlåda  med enbart molnet till ett visst område för [geoplats](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) innan du skapar postlådan i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="23f3a-179">Configure the **PreferredDataLocation** value as described in the previous [Move an existing cloud-only mailbox to a specific geo location](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) section *before* you create the mailbox in Exchange Online.</span></span> <span data-ttu-id="23f3a-180">Konfigurera till exempel värdet **PreferredDataLocation för** en användare innan du tilldelar en licens.</span><span class="sxs-lookup"><span data-stu-id="23f3a-180">For example, configure the **PreferredDataLocation** value on a user before you assign a license.</span></span>

- <span data-ttu-id="23f3a-181">Tilldela en licens samtidigt som du anger **värdet PreferredDataLocation.**</span><span class="sxs-lookup"><span data-stu-id="23f3a-181">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="23f3a-182">Om du vill skapa en ny molnlicensierad användare (inte AAD Anslut synkroniserad) på en viss geoplats använder du följande syntax i Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="23f3a-182">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="23f3a-183">I det här exemplet skapas ett nytt användarkonto för Elizabeth Förgrundsman med följande värden:</span><span class="sxs-lookup"><span data-stu-id="23f3a-183">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="23f3a-184">Användarens huvudnamn: ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="23f3a-184">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>
- <span data-ttu-id="23f3a-185">Förnamn: Elizabeth</span><span class="sxs-lookup"><span data-stu-id="23f3a-185">First name: Elizabeth</span></span>
- <span data-ttu-id="23f3a-186">Efternamn: Så här gör du</span><span class="sxs-lookup"><span data-stu-id="23f3a-186">Last name: Brunner</span></span>
- <span data-ttu-id="23f3a-187">Visningsnamn: Elizabeth Förnamn</span><span class="sxs-lookup"><span data-stu-id="23f3a-187">Display name: Elizabeth Brunner</span></span>
- <span data-ttu-id="23f3a-188">Lösenord: slumpmässigt genererad och visas i resultatet av kommandot (eftersom vi inte använder parametern *Lösenord)*</span><span class="sxs-lookup"><span data-stu-id="23f3a-188">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>
- <span data-ttu-id="23f3a-189">Licens: `contoso:ENTERPRISEPREMIUM` (E5)</span><span class="sxs-lookup"><span data-stu-id="23f3a-189">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>
- <span data-ttu-id="23f3a-190">Plats: Australien (AUS)</span><span class="sxs-lookup"><span data-stu-id="23f3a-190">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="23f3a-191">Mer information om hur du skapar nya användarkonton och hittar värden för LicenseAssignment i Azure AD PowerShell finns i Skapa användarkonton med [PowerShell](create-user-accounts-with-microsoft-365-powershell.md) och Visa licenser och tjänster [med PowerShell.](view-licenses-and-services-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="23f3a-191">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="23f3a-192">Om du använder Exchange Online PowerShell för att aktivera en postlåda och behöver att postlådan skapas direkt på den geoplats som anges i **PreferredDataLocation** måste du använda en Exchange Online-cmdlet, till exempel **Enable-Mailbox** eller **New-Mailbox** direkt mot molntjänsten.</span><span class="sxs-lookup"><span data-stu-id="23f3a-192">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="23f3a-193">Om du använder cmdleten **Enable-RemoteMailbox** i en lokal Exchange PowerShell skapas postlådan på den centrala geoplatsen.</span><span class="sxs-lookup"><span data-stu-id="23f3a-193">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="23f3a-194">Introducera befintliga lokala postlådor på en viss geoplats</span><span class="sxs-lookup"><span data-stu-id="23f3a-194">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="23f3a-195">Du kan använda vanliga onboarding-verktyg och -processer för att migrera en postlåda från en lokal Exchange-organisation till Exchange Online, inklusive instrumentpanelen för migrering i [EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)och [cmdleten New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23f3a-195">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="23f3a-196">Det första steget är att verifiera att ett användarobjekt finns för varje postlåda som ska introduceras, och kontrollera att rätt **PreferredDataLocation-värde** har konfigurerats i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="23f3a-196">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="23f3a-197">Onboarding-verktygen respekterar **värdet för PreferredDataLocation** och migrerar postlådorna direkt till den angivna geoplatsen.</span><span class="sxs-lookup"><span data-stu-id="23f3a-197">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="23f3a-198">Du kan också använda följande steg för att registrera postlådor direkt på en viss geoplats med hjälp av cmdleten [New-MoveRequest](/powershell/module/exchange/new-moverequest) i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23f3a-198">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="23f3a-199">Kontrollera att användarobjektet finns för varje postlåda som ska introduceras och att **PreferredDataLocation** är inställt på önskat värde i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="23f3a-199">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="23f3a-200">Värdet för **PreferredDataLocation synkroniseras** med attributet **MailboxRegion** för motsvarande e-postanvändarobjekt i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="23f3a-200">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="23f3a-201">Anslut direkt till den specifika satellit geoplatsen med hjälp av anslutningsanvisningarna från tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="23f3a-201">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="23f3a-202">I Exchange Online PowerShell lagrar du de lokala administratörsautentiseringsuppgifter som används för att utföra en postlådemigrering i en variabel genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="23f3a-202">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="23f3a-203">I Exchange Online PowerShell skapar du en **ny New-MoveRequest** som liknar följande exempel:</span><span class="sxs-lookup"><span data-stu-id="23f3a-203">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="23f3a-204">Upprepa steg #4 för varje postlåda du behöver migrera från lokala platser Exchange till den satellitgeoplats du är ansluten till.</span><span class="sxs-lookup"><span data-stu-id="23f3a-204">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="23f3a-205">Om du behöver migrera ytterligare postlådor till olika satellitplatser upprepar du steg 2 till 4 för varje specifik plats.</span><span class="sxs-lookup"><span data-stu-id="23f3a-205">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="23f3a-206">Multigeorapportering</span><span class="sxs-lookup"><span data-stu-id="23f3a-206">Multi-geo reporting</span></span>

<span data-ttu-id="23f3a-207">**Rapporten Multi-Geo Usage Reports** Microsoft 365 administrationscentret visar antalet användare per geoplats.</span><span class="sxs-lookup"><span data-stu-id="23f3a-207">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="23f3a-208">Rapporten visar användardistribution för den aktuella månaden och innehåller historiska data för de senaste 6 månaderna.</span><span class="sxs-lookup"><span data-stu-id="23f3a-208">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="23f3a-209">Se även</span><span class="sxs-lookup"><span data-stu-id="23f3a-209">See also</span></span>

[<span data-ttu-id="23f3a-210">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="23f3a-210">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)