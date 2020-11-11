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
ms.openlocfilehash: c9219d29a1fdae68075d296404a6c2aeab30f1aa
ms.sourcegitcommit: f941495e9257a0013b4a6a099b66c649e24ce8a1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993382"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="68f18-103">Administrera Exchange Online-postlådor i en multi-geo-miljö</span><span class="sxs-lookup"><span data-stu-id="68f18-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="68f18-104">Exchange Online PowerShell krävs för att visa och konfigurera multi geo-egenskaper i din Microsoft 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="68f18-104">Exchange Online PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="68f18-105">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="68f18-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="68f18-106">Du behöver [Microsoft Azure Active Directory PowerShell modul](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v 1.1.166.0 eller senare i v1. x för att se egenskapen **PreferredDataLocation** för användar objekt.</span><span class="sxs-lookup"><span data-stu-id="68f18-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="68f18-107">De användar objekt som synkroniseras via AAD Connect into AAD kan inte ha sitt **PreferredDataLocation** -värde direkt ändrat via AAD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68f18-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="68f18-108">Endast molnbaserade användar objekt kan ändras via AAD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68f18-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="68f18-109">Information om hur du ansluter till Azure AD PowerShell finns i [ansluta till PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="68f18-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="68f18-110">Ansluta direkt till en Geo-plats med Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="68f18-110">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="68f18-111">Normalt ansluter Exchange Online PowerShell till Central geo-platsen.</span><span class="sxs-lookup"><span data-stu-id="68f18-111">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="68f18-112">Men du kan också ansluta direkt till satellit platser på andra ställen.</span><span class="sxs-lookup"><span data-stu-id="68f18-112">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="68f18-113">På grund av förbättringar av prestanda rekommenderar vi att du ansluter direkt till satellitens Geo plats när du bara hanterar användare på den platsen.</span><span class="sxs-lookup"><span data-stu-id="68f18-113">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="68f18-114">Kraven för att installera och använda EXO v2 finns beskrivna i [Installera och underhålla EXO v2-modulen](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span><span class="sxs-lookup"><span data-stu-id="68f18-114">The requirements for installing and using the EXO V2 module are described in [Install and maintain the EXO V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

<span data-ttu-id="68f18-115">Om du vill ansluta Exchange Online PowerShell till en specifik Geo-plats är *ConnectionUri* -parametern annorlunda än de vanliga anslutnings anvisningarna.</span><span class="sxs-lookup"><span data-stu-id="68f18-115">To connect Exchange Online PowerShell to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="68f18-116">Resten av kommandona och värdena är desamma.</span><span class="sxs-lookup"><span data-stu-id="68f18-116">The rest of the commands and values are the same.</span></span>

<span data-ttu-id="68f18-117">Specifikt måste du lägga till `?email=<emailaddress>` värdet i slutet av _ConnectionUri_ -värdet.</span><span class="sxs-lookup"><span data-stu-id="68f18-117">Specifically, you need to add the `?email=<emailaddress>` value to end of the _ConnectionUri_ value.</span></span> <span data-ttu-id="68f18-118">`<emailaddress>` är e-postadressen till **alla** post lådor på Geo-platsen för mål.</span><span class="sxs-lookup"><span data-stu-id="68f18-118">`<emailaddress>` is the email address of **any** mailbox in the target geo location.</span></span> <span data-ttu-id="68f18-119">Din behörighet till post lådan eller relationen till dina autentiseringsuppgifter är inte en faktor; e-postadressen säger bara till Exchange Online PowerShell för anslutning.</span><span class="sxs-lookup"><span data-stu-id="68f18-119">Your permissions to that mailbox or the relationship to your credentials are not a factor; the email address simply tells Exchange Online PowerShell where to connect.</span></span>

<span data-ttu-id="68f18-120">Microsoft 365 eller Microsoft 365 GCC-kunder behöver vanligt vis inte använda parametern _ConnectionUri_ för att ansluta till Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68f18-120">Microsoft 365 or Microsoft 365 GCC customers typically don't need to use the _ConnectionUri_ parameter to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="68f18-121">Men om du vill ansluta till en specifik Geo-plats måste du använda _ConnectionUri_ parameter så att du kan använda `?email=<emailaddress>` i värdet.</span><span class="sxs-lookup"><span data-stu-id="68f18-121">But, to connect to a specific geo location, you do need to use _ConnectionUri_ parameter so you can use `?email=<emailaddress>` in the value.</span></span>

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-using-multi-factor-authentication-mfa"></a><span data-ttu-id="68f18-122">Ansluta till en Geo-plats i Exchange Online PowerShell med multifaktorautentisering (MFA)</span><span class="sxs-lookup"><span data-stu-id="68f18-122">Connect to a geo location in Exchange Online PowerShell using multi-factor authentication (MFA)</span></span>

1. <span data-ttu-id="68f18-123">Öppna modulen EXO v2 i ett Windows PowerShell-fönster genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="68f18-123">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="68f18-124">I det här exemplet är admin@contoso.onmicrosoft.com administratörs konto och mål-geo-platsen där post lådans olga@contoso.onmicrosoft.com finns.</span><span class="sxs-lookup"><span data-stu-id="68f18-124">In the following example, admin@contoso.onmicrosoft.com is the admin account, and the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

  ```powershell
  Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
  ```

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-without-using-mfa"></a><span data-ttu-id="68f18-125">Ansluta till en Geo-plats i Exchange Online PowerShell utan MFA</span><span class="sxs-lookup"><span data-stu-id="68f18-125">Connect to a geo location in Exchange Online PowerShell without using MFA</span></span>

1. <span data-ttu-id="68f18-126">Öppna modulen EXO v2 i ett Windows PowerShell-fönster genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="68f18-126">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="68f18-127">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="68f18-127">Run the following command:</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

   <span data-ttu-id="68f18-128">I dialog rutan **begäran om autentiseringsuppgifter för Windows PowerShell** anger du ditt arbets-eller skol konto och lösen ord och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="68f18-128">In the **Windows PowerShell Credential Request** dialog box that appears, type your work or school account and password, and then click **OK**.</span></span>

3. <span data-ttu-id="68f18-129">I det här exemplet är mål-geo platsen där olga@contoso.onmicrosoft.com finns.</span><span class="sxs-lookup"><span data-stu-id="68f18-129">In the following example, the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

   ```powershell
   Connect-ExchangeOnline -Credential $UserCredential -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="68f18-130">Visa tillgängliga geo-platser som är konfigurerade i din Exchange Online-organisation</span><span class="sxs-lookup"><span data-stu-id="68f18-130">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="68f18-131">Om du vill visa en lista över konfigurerade geo-platser i Microsoft 365 multi-geo kör du följande kommando i Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68f18-131">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="68f18-132">Visa Central geo-platsen för din Exchange Online-organisation</span><span class="sxs-lookup"><span data-stu-id="68f18-132">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="68f18-133">Om du vill visa klient organisationens centrala Geo-plats kör du följande kommando i Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68f18-133">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="68f18-134">Hitta geo-platsen för en post låda</span><span class="sxs-lookup"><span data-stu-id="68f18-134">Find the geo location of a mailbox</span></span>

<span data-ttu-id="68f18-135">Cmdleten **Get-Mailbox** in Exchange Online PowerShell visar följande multi-geo-relaterade egenskaper i post lådorna:</span><span class="sxs-lookup"><span data-stu-id="68f18-135">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="68f18-136">**Databas** : de första 3 bokstäverna i databas namnet motsvarar geo-koden, vilket anger var post lådan finns.</span><span class="sxs-lookup"><span data-stu-id="68f18-136">**Database** : The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="68f18-137">För online-arkiv-post lådor ska egenskapen **ArchiveDatabase** användas.</span><span class="sxs-lookup"><span data-stu-id="68f18-137">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="68f18-138">**MailboxRegion** : anger den Geo-plats kod som angavs av administratören (synkroniserad från **PREFERREDDATALOCATION** i Azure AD).</span><span class="sxs-lookup"><span data-stu-id="68f18-138">**MailboxRegion** : Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="68f18-139">**MailboxRegionLastUpdateTime** : anger när MailboxRegion senast uppdaterades (antingen automatiskt eller manuellt).</span><span class="sxs-lookup"><span data-stu-id="68f18-139">**MailboxRegionLastUpdateTime** : Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="68f18-140">Använd följande syntax för att visa de här egenskaperna för en post låda:</span><span class="sxs-lookup"><span data-stu-id="68f18-140">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="68f18-141">Om du till exempel vill visa geo-platsens information om chris@contoso.onmicrosoft.com kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="68f18-141">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="68f18-142">Kommandot ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="68f18-142">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="68f18-143">Om den Geo-plats koden i databas namnet inte stämmer överens med **MailboxRegion** -värdet kommer post lådan automatiskt att placeras i en kö för lagring och flyttas till den Geo-plats som anges i **MailboxRegion** -värdet (Exchange Online letar efter en avvikelse mellan dessa egenskaps värden).</span><span class="sxs-lookup"><span data-stu-id="68f18-143">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="68f18-144">Flytta en befintlig brev låde post låda till en specifik Geo-plats</span><span class="sxs-lookup"><span data-stu-id="68f18-144">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="68f18-145">En användare som endast är en molnad användare är inte synkroniserad med klient organisationen via AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="68f18-145">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="68f18-146">Denna användare skapades direkt i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="68f18-146">This user was created directly in Azure AD.</span></span> <span data-ttu-id="68f18-147">Använd cmdletarna **Get-MsolUser** och **set-MSOLUSER** i Azure AD-modulen för Windows PowerShell för att visa eller ange den Geo-plats där en användares post låda i molnet lagras.</span><span class="sxs-lookup"><span data-stu-id="68f18-147">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="68f18-148">Om du vill visa **PreferredDataLocation** -värdet för en användare använder du denna syntax i Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68f18-148">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="68f18-149">Om du till exempel vill visa **PreferredDataLocation** -värdet för användar Michelle@contoso.onmicrosoft.com kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="68f18-149">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="68f18-150">Om du vill ändra **PreferredDataLocation** -värdet för ett objekt i molnet kan du använda följande syntax i Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68f18-150">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="68f18-151">Om du till exempel vill ange **PreferredDataLocation** -värdet till EU (EUR) geo för User Michelle@contoso.onmicrosoft.com kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="68f18-151">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - <span data-ttu-id="68f18-152">Som tidigare nämnts kan du inte använda den här proceduren för synkroniserade användar objekt från lokala Active Directory.</span><span class="sxs-lookup"><span data-stu-id="68f18-152">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="68f18-153">Du måste ändra värdet för **PreferredDataLocation** i Active Directory och synkronisera det med hjälp av AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="68f18-153">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="68f18-154">Mer information finns i [Azure Active Directory Connect Sync: konfigurera önskad data plats för Microsoft 365-resurser](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span><span class="sxs-lookup"><span data-stu-id="68f18-154">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
>
> - <span data-ttu-id="68f18-155">Hur lång tid det tar att hitta en post låda på en ny Geo-plats beror på flera faktorer:</span><span class="sxs-lookup"><span data-stu-id="68f18-155">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
>
>   - <span data-ttu-id="68f18-156">Storlek och typ av post låda.</span><span class="sxs-lookup"><span data-stu-id="68f18-156">The size and type of mailbox.</span></span>
>   - <span data-ttu-id="68f18-157">Antalet post lådor som flyttas.</span><span class="sxs-lookup"><span data-stu-id="68f18-157">The number of mailboxes being moved.</span></span>
>   - <span data-ttu-id="68f18-158">Tillgängligheten för att flytta resurser.</span><span class="sxs-lookup"><span data-stu-id="68f18-158">The availability of move resources.</span></span>

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a><span data-ttu-id="68f18-159">Flytta en inaktiv post låda till en viss geo</span><span class="sxs-lookup"><span data-stu-id="68f18-159">Move an inactive mailbox to a specific geo</span></span>

<span data-ttu-id="68f18-160">Du kan inte flytta inaktiva post lådor som bevaras i enlighet (till exempel post lådor på rättsliga håll) genom att ändra deras **PreferredDataLocation** -värde.</span><span class="sxs-lookup"><span data-stu-id="68f18-160">You can't move inactive mailboxes that are preserved for compliance purposes (for example, mailboxes on Litigation Hold) by changing their **PreferredDataLocation** value.</span></span> <span data-ttu-id="68f18-161">Gör så här om du vill flytta en inaktiv post låda till en annan geo:</span><span class="sxs-lookup"><span data-stu-id="68f18-161">To move an inactive mailbox to a different geo, do the following steps:</span></span>

1. <span data-ttu-id="68f18-162">Återställ den inaktiva post lådan.</span><span class="sxs-lookup"><span data-stu-id="68f18-162">Recover the inactive mailbox.</span></span> <span data-ttu-id="68f18-163">Anvisningar finns i [återställa en inaktiv post låda](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="68f18-163">For instructions, see [Recover an inactive mailbox](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox).</span></span>

2. <span data-ttu-id="68f18-164">Förhindra att hanteraren för hanterade mappar bearbetar den återställda post lådan genom att ersätta den \<MailboxIdentity\> med namn, alias, konto eller e-postadress för post lådan och köra följande kommando i [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span><span class="sxs-lookup"><span data-stu-id="68f18-164">Prevent the Managed Folder Assistant from processing the recovered mailbox by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. <span data-ttu-id="68f18-165">Tilldela en **Exchange Online abonnemang 2** -licens till den återställda post lådan.</span><span class="sxs-lookup"><span data-stu-id="68f18-165">Assign an **Exchange Online Plan 2** license to the recovered mailbox.</span></span> <span data-ttu-id="68f18-166">Det här steget krävs för att återställa post lådan på den juridiska processen.</span><span class="sxs-lookup"><span data-stu-id="68f18-166">This step is required to place the mailbox back on Litigation Hold.</span></span> <span data-ttu-id="68f18-167">Anvisningar finns i [tilldela licenser till användare](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="68f18-167">For instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

4. <span data-ttu-id="68f18-168">Konfigurera **PreferredDataLocation** -värdet i post lådan enligt beskrivningen i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="68f18-168">Configure the **PreferredDataLocation** value on the mailbox as described in the previous section.</span></span>

5. <span data-ttu-id="68f18-169">När du har bekräftat att post lådan har flyttats till den nya geo-platsen placerar du den återställda post lådan igen i arbets gruppen.</span><span class="sxs-lookup"><span data-stu-id="68f18-169">After you've confirmed that the mailbox has moved to the new geo location, place the recovered mailbox back on Litigation Hold.</span></span> <span data-ttu-id="68f18-170">Anvisningar finns i [lägga till en post låda med undantag](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold).</span><span class="sxs-lookup"><span data-stu-id="68f18-170">For instructions, see [Place a mailbox on Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold).</span></span>

6. <span data-ttu-id="68f18-171">När du har verifierat att den kvarhållna processen är på plats kan du låta den hanterade mappstrukturen bearbeta post lådan igen genom att ersätta den \<MailboxIdentity\> med namn, alias, konto eller e-postadress för post lådan och köra följande kommando i [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span><span class="sxs-lookup"><span data-stu-id="68f18-171">After verifying that the Litigation Hold is in place, allow the Managed Folder Assistant to process the mailbox again by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. <span data-ttu-id="68f18-172">Gör post lådan inaktiv igen genom att ta bort det användar konto som är kopplat till post lådan.</span><span class="sxs-lookup"><span data-stu-id="68f18-172">Make the mailbox inactive again by removing the user account that's associated with the mailbox.</span></span> <span data-ttu-id="68f18-173">Anvisningar finns i [ta bort en användare från din organisation](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user).</span><span class="sxs-lookup"><span data-stu-id="68f18-173">For instructions, see [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user).</span></span> <span data-ttu-id="68f18-174">I det här steget ges även Exchange Online abonnemang 2-licensen för andra användnings områden.</span><span class="sxs-lookup"><span data-stu-id="68f18-174">This step also releases the Exchange Online Plan 2 license for other uses.</span></span>

<span data-ttu-id="68f18-175">**Obs!** när du flyttar en inaktiv post låda till en annan Geo-plats kan du påverka innehållet Sök resultat eller möjligheten att söka i post lådan från den tidigare geo-platsen.</span><span class="sxs-lookup"><span data-stu-id="68f18-175">**Note** : When you move an inactive mailbox to a different geo location, you might affect content search results or the ability to search the mailbox from the former geo location.</span></span> <span data-ttu-id="68f18-176">Mer information finns i [söka efter och exportera innehåll i multi-geo-miljöer](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments).</span><span class="sxs-lookup"><span data-stu-id="68f18-176">For more information, see [Searching and exporting content in Multi-Geo environments](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments).</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="68f18-177">Skapa nya moln post lådor på en viss Geo-plats</span><span class="sxs-lookup"><span data-stu-id="68f18-177">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="68f18-178">Om du vill skapa en ny post låda på en specifik Geo-plats måste du göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="68f18-178">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="68f18-179">Konfigurera **PreferredDataLocation** -värdet enligt beskrivningen ovan [flytta en befintlig moln-Only-postlåda till ett specifikt Geo-plats-](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) avsnitt *innan* du skapar post lådan i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="68f18-179">Configure the **PreferredDataLocation** value as described in the previous [Move an existing cloud-only mailbox to a specific geo location](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) section *before* you create the mailbox in Exchange Online.</span></span> <span data-ttu-id="68f18-180">Konfigurera till exempel värdet **PreferredDataLocation** för en användare innan du tilldelar en licens.</span><span class="sxs-lookup"><span data-stu-id="68f18-180">For example, configure the **PreferredDataLocation** value on a user before you assign a license.</span></span>

- <span data-ttu-id="68f18-181">Tilldela en licens samtidigt ställer du in **PreferredDataLocation** -värdet.</span><span class="sxs-lookup"><span data-stu-id="68f18-181">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="68f18-182">Om du vill skapa en ny moln-licensierad användare (inte AAD Connect Synchronized) på en specifik Geo-plats använder du följande syntax i Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="68f18-182">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="68f18-183">I det här exemplet skapas ett nytt användar konto för Elizabeth Brunner med följande värden:</span><span class="sxs-lookup"><span data-stu-id="68f18-183">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="68f18-184">Användarens huvud namn: ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="68f18-184">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>
- <span data-ttu-id="68f18-185">Förnamn: Elizabeth</span><span class="sxs-lookup"><span data-stu-id="68f18-185">First name: Elizabeth</span></span>
- <span data-ttu-id="68f18-186">Efter namn: Brunner</span><span class="sxs-lookup"><span data-stu-id="68f18-186">Last name: Brunner</span></span>
- <span data-ttu-id="68f18-187">Visnings namn: Elizabeth Brunner</span><span class="sxs-lookup"><span data-stu-id="68f18-187">Display name: Elizabeth Brunner</span></span>
- <span data-ttu-id="68f18-188">Lösen ord: skapas och visas slumpmässigt i resultatet av kommandot (eftersom det inte använder *lösen ords* parametern)</span><span class="sxs-lookup"><span data-stu-id="68f18-188">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>
- <span data-ttu-id="68f18-189">Licens: `contoso:ENTERPRISEPREMIUM` (E5)</span><span class="sxs-lookup"><span data-stu-id="68f18-189">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>
- <span data-ttu-id="68f18-190">Plats: Australien (Australien)</span><span class="sxs-lookup"><span data-stu-id="68f18-190">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="68f18-191">Mer information om hur du skapar nya användar konton och hittar LicenseAssignment värden i Azure AD PowerShell finns i [skapa användar konton med PowerShell](create-user-accounts-with-microsoft-365-powershell.md) och [Visa licenser och tjänster med PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="68f18-191">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="68f18-192">Om du använder Exchange Online PowerShell för att aktivera en post låda och behöver post lådan på en Geo-plats som anges i **PreferredDataLocation** , måste du använda en Exchange Online-cmdlet, till exempel **Aktivera-post låda** eller **ny-post låda** direkt mot moln tjänsten.</span><span class="sxs-lookup"><span data-stu-id="68f18-192">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation** , you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="68f18-193">Om du använder cmdleten **Enable-RemoteMailbox** i lokal Exchange PowerShell skapas post lådan på den centrala geo-platsen.</span><span class="sxs-lookup"><span data-stu-id="68f18-193">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="68f18-194">Befintliga lokala post lådor på en viss Geo-plats</span><span class="sxs-lookup"><span data-stu-id="68f18-194">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="68f18-195">Du kan använda standardinställningarna för inbyggda verktyg och processer för att migrera en post låda från en lokal Exchange-organisation till Exchange Online, inklusive [instrument panelen för migrering i UK](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)och cmdleten [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68f18-195">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="68f18-196">Det första steget är att verifiera att ett User-objekt finns för varje post låda som ska registreras och att rätt **PreferredDataLocation** -värde är konfigurerat i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="68f18-196">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="68f18-197">De inbyggda verktygen påverkar **PreferredDataLocation** -värdet och migrerar post lådorna direkt till angiven Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="68f18-197">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="68f18-198">Eller så kan du använda följande steg för att hantera post lådor direkt i en viss Geo-plats med den nya cmdleten [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68f18-198">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="68f18-199">Verifiera att användarobjektet finns för varje post låda som ska registreras och att **PreferredDataLocation** är inställt på önskat värde i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="68f18-199">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="68f18-200">Värdet för **PreferredDataLocation** synkroniseras till attributet **MailboxRegion** för motsvarande e-postanvändarnamn i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="68f18-200">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="68f18-201">Anslut direkt till den specifika satellit platsen med anslutnings anvisningarna från tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="68f18-201">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="68f18-202">I Exchange Online PowerShell kan du lagra de lokala administratörs uppgifterna som används för att utföra en migrering av post lådor i en variabel genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="68f18-202">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="68f18-203">I Exchange Online PowerShell kan du skapa ett nytt **nytt-MoveRequest** som liknar det här exemplet:</span><span class="sxs-lookup"><span data-stu-id="68f18-203">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="68f18-204">Upprepa steg #4 för varje post låda som du måste migrera från lokalt Exchange till den satellitbaserade geo platsen du är ansluten till.</span><span class="sxs-lookup"><span data-stu-id="68f18-204">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="68f18-205">Om du behöver migrera ytterligare post lådor till olika satellit platser upprepar du steg 2 till 4 för varje specifik plats.</span><span class="sxs-lookup"><span data-stu-id="68f18-205">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="68f18-206">Multi-geo-rapportering</span><span class="sxs-lookup"><span data-stu-id="68f18-206">Multi-geo reporting</span></span>

<span data-ttu-id="68f18-207">**Flera geo rapporter för användning** i administrations centret för Microsoft 365 visar antalet användare per Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="68f18-207">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="68f18-208">I rapporten visas användar distribution för den aktuella månaden och historik för de senaste sex månaderna.</span><span class="sxs-lookup"><span data-stu-id="68f18-208">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="68f18-209">Se även</span><span class="sxs-lookup"><span data-stu-id="68f18-209">See also</span></span>

[<span data-ttu-id="68f18-210">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="68f18-210">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
