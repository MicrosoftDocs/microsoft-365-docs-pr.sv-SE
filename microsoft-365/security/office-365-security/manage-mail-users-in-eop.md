---
title: Hantera e-postanvändare i EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Att definiera e-postanvändare är en viktig del av hanteringen av Tjänsten Exchange Online Protection (EOP).
ms.openlocfilehash: bdbc3cd54901d53b4a7d01bcf513a9b9a0df1c01
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42811863"
---
# <a name="manage-mail-users-in-eop"></a><span data-ttu-id="e940f-103">Hantera e-postanvändare i EOP</span><span class="sxs-lookup"><span data-stu-id="e940f-103">Manage mail users in EOP</span></span>

<span data-ttu-id="e940f-104">Att definiera e-postanvändare är en viktig del av hanteringen av Tjänsten Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="e940f-104">Defining mail users is an important part of managing the Exchange Online Protection (EOP) service.</span></span> <span data-ttu-id="e940f-105">Det finns flera sätt att hantera användare i EOP:</span><span class="sxs-lookup"><span data-stu-id="e940f-105">There are several ways that you can manage users in EOP:</span></span>

- <span data-ttu-id="e940f-106">**Använd katalogsynkronisering för att hantera e-postanvändare:** Om företaget har befintliga användarkonton i en lokal Active Directory-miljö kan du synkronisera dessa konton till Azure Active Directory (AD), där en kopia av kontona lagras i molnet.</span><span class="sxs-lookup"><span data-stu-id="e940f-106">**Use directory synchronization to manage mail users**: If your company has existing user accounts in an on-premises Active Directory environment, you can synchronize those accounts to Azure Active Directory (AD), where a copy of the accounts is stored in the cloud.</span></span> <span data-ttu-id="e940f-107">När du synkroniserar dina befintliga användarkonton till Azure Active Directory kan du visa dessa användare i fönstret Mottagare i **Administrationscentret** för Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="e940f-107">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC).</span></span> <span data-ttu-id="e940f-108">Användning av katalogsynkronisering rekommenderas.</span><span class="sxs-lookup"><span data-stu-id="e940f-108">Using directory synchronization is recommended.</span></span>

- <span data-ttu-id="e940f-109">**Använd EAC för att hantera e-postanvändare:** Lägg till och hantera e-postanvändare direkt i EAC.</span><span class="sxs-lookup"><span data-stu-id="e940f-109">**Use the EAC to manage mail users**: Add and manage mail users directly in the EAC.</span></span> <span data-ttu-id="e940f-110">Detta är det enklaste sättet att lägga till e-postanvändare och är användbart för att lägga till en användare i taget.</span><span class="sxs-lookup"><span data-stu-id="e940f-110">This is the easiest way to add mail users and is useful for adding one user at a time.</span></span>

- <span data-ttu-id="e940f-111">**Använd PowerShell för att hantera e-postanvändare:** Lägg till och hantera e-postanvändare i Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e940f-111">**Use PowerShell to manage mail users**: Add and manage mail users by in Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="e940f-112">Den här metoden är användbar när du vill lägga till flera poster och skapa skript.</span><span class="sxs-lookup"><span data-stu-id="e940f-112">This method is useful for adding multiple records and creating scripts.</span></span>

> [!NOTE]
> <span data-ttu-id="e940f-113">Du kan lägga till användare i Microsoft 365-administrationscentret, men dessa användare kan inte användas som e-postmottagare.</span><span class="sxs-lookup"><span data-stu-id="e940f-113">You can add users in the Microsoft 365 admin center, however these users can't be used as mail recipients.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e940f-114">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="e940f-114">Before you begin</span></span>

- <span data-ttu-id="e940f-115">Information om hur du öppnar administrationscentret för Exchange finns [i Administrationscenter för Exchange i Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="e940f-115">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="e940f-116">Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="e940f-116">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="e940f-117">Information om vilka behörigheter du behöver finns i posten "Användare, Kontakter och Rollgrupper" i [Funktionsbehörigheter i EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="e940f-117">To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>

- <span data-ttu-id="e940f-118">Tänk på att när du skapar e-postanvändare med hjälp av Exchange Online Protection PowerShell-cmdlets kan du stöta på begränsning.</span><span class="sxs-lookup"><span data-stu-id="e940f-118">Be aware that when creating mail users by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="e940f-119">PowerShell-kommandona i det här avsnittet använder en batchbearbetningsmetod som resulterar i en spridningsfördröjning på några minuter innan resultaten av kommandona visas.</span><span class="sxs-lookup"><span data-stu-id="e940f-119">The PowerShell commands in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="e940f-120">Mer information om hur du använder Windows PowerShell för att ansluta till Exchange Online Protection finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="e940f-120">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e940f-121">Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns [i Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="e940f-121">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="e940f-122">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="e940f-122">Having problems?</span></span> <span data-ttu-id="e940f-123">Be om hjälp i Forumet för [Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="e940f-123">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="e940f-124">Använda katalogsynkronisering för att hantera e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="e940f-124">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="e940f-125">Det här avsnittet innehåller information om hur du hanterar e-postanvändare med hjälp av katalogsynkronisering.</span><span class="sxs-lookup"><span data-stu-id="e940f-125">This section provides information about managing email users by using directory synchronization.</span></span>

<span data-ttu-id="e940f-126">**Anmärkningar:**</span><span class="sxs-lookup"><span data-stu-id="e940f-126">**Notes**:</span></span>

- <span data-ttu-id="e940f-127">Om du använder katalogsynkronisering för att hantera mottagarna kan du fortfarande lägga till och hantera användare i Microsoft 365-administrationscentret, men de synkroniseras inte med den lokala Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e940f-127">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="e940f-128">Detta beror på att katalogsynkronisering bara synkroniserar mottagare **från** den lokala Active Directory **till** molnet.</span><span class="sxs-lookup"><span data-stu-id="e940f-128">This is because directory synchronization only syncs recipients **from** your on-premises Active Directory **to** the cloud.</span></span>

- <span data-ttu-id="e940f-129">Katalogsynkronisering rekommenderas för användning med följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="e940f-129">Directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="e940f-130">**Outlook-listor med betrodda avsändare och blockerade avsändare**: När de synkroniseras med tjänsten har dessa listor företräde framför skräppostfiltrering i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="e940f-130">**Outlook safe sender and blocked sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="e940f-131">På så sätt kan användare hantera sina egna säkra avsändare och blockerade avsändarelistor per användare eller per domän.</span><span class="sxs-lookup"><span data-stu-id="e940f-131">This lets users manage their own safe sender and blocked sender lists on a per-user or per-domain basis.</span></span>

  - <span data-ttu-id="e940f-132">**Katalogbaserad kantblockering (DBEB)**: Mer information om DBEB finns i [Använda katalogbaserad kantblockering för att avvisa meddelanden som skickas till ogiltiga mottagare](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span><span class="sxs-lookup"><span data-stu-id="e940f-132">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="e940f-133">**Slutanvändarens skräppostkarant karantän**: För att få åtkomst till slutanvändarens skräppostkarantskap måste slutanvändarna ha ett giltigt användar-ID och lösenord för Office 365.</span><span class="sxs-lookup"><span data-stu-id="e940f-133">**End user spam quarantine**: In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="e940f-134">EOP-kunder som skyddar lokala postlådor måste vara giltiga e-postanvändare.</span><span class="sxs-lookup"><span data-stu-id="e940f-134">EOP customers protecting on-premises mailboxes must be valid email users.</span></span>

  - <span data-ttu-id="e940f-135">**Regler för e-postflöde**: När du använder katalogsynkronisering överförs dina befintliga Active Directory-användare och -grupper automatiskt till molnet, och du kan sedan skapa regler för e-postflöde (kallas även transportregler) som riktar sig till specifika användare och/eller grupper utan att behöva lägga till dem manuellt via EAC eller Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e940f-135">**Mail flow rules**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules (also known as transport rules) that target specific users and/or groups without having to manually add them via the the EAC or Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="e940f-136">Observera att [dynamiska distributionsgrupper](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) inte kan synkroniseras via katalogsynkronisering.</span><span class="sxs-lookup"><span data-stu-id="e940f-136">Note that [dynamic distribution groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="e940f-137">Hämta nödvändiga behörigheter och förbereda för katalogsynkronisering enligt beskrivningen i [Vad är hybrididentitet med Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span><span class="sxs-lookup"><span data-stu-id="e940f-137">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="to-synchronize-user-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="e940f-138">Så här synkroniserar du användarkataloger med Azure Active Directory Connect (AAD Connect)</span><span class="sxs-lookup"><span data-stu-id="e940f-138">To synchronize user directories with Azure Active Directory Connect (AAD Connect)</span></span>

<span data-ttu-id="e940f-139">Om du vill synkronisera användare till Azure Active Directory (AAD) måste du först **aktivera katalogsynkronisering**enligt beskrivningen i [Azure AD Connect-synkronisering: Förstå och anpassa synkronisering](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span><span class="sxs-lookup"><span data-stu-id="e940f-139">To synchronize users to Azure Active Directory (AAD) you first have to **activate directory synchronization**, as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="e940f-140">Nästa är installation och konfiguration av en lokal dator för att köra AAD Connect (om du inte redan har en - något värt att kontrollera i förväg).</span><span class="sxs-lookup"><span data-stu-id="e940f-140">Next is the installation and configuration of an on-premises computer to run AAD Connect (if you don't already have one -- something worth checking ahead of time).</span></span> <span data-ttu-id="e940f-141">[När du konfigurerar AAD Connect, uttryckssättet,](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) berättar du hur du konfigurerar och synkroniserar dina konton från lokala till Azure AD med AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="e940f-141">The [Setting up AAD Connect, the express way](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express) topic tells you how to setup and synchronize your accounts from on-premises to Azure AD with AAD Connect.</span></span>

<span data-ttu-id="e940f-142">Men innan du gör det arbetet, se till att [du uppfyller förutsättningarna](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)och [välj din installationstyp](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation).</span><span class="sxs-lookup"><span data-stu-id="e940f-142">But before you do that work, make certain [you meet prerequisites](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites), and [choose your installation type](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation).</span></span> <span data-ttu-id="e940f-143">Den tidigare länken är till en kort artikel för expressinstallationer.</span><span class="sxs-lookup"><span data-stu-id="e940f-143">The earlier link is to a short article for express installs.</span></span> <span data-ttu-id="e940f-144">Du kan också hitta artiklar om [anpassade installationer](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)eller [direktautentisering](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) om de behövs.</span><span class="sxs-lookup"><span data-stu-id="e940f-144">You can also find articles on [custom installations](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom), or [pass-through authentication](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start) if they're needed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e940f-145">När du är klar med konfigurationsguiden för Azure Active Directory Sync Tool skapas **MSOL_AD_SYNC-kontot** i Active Directory-skogen.</span><span class="sxs-lookup"><span data-stu-id="e940f-145">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest.</span></span> <span data-ttu-id="e940f-146">Det här kontot används för att läsa och synkronisera din lokala Active Directory-information.</span><span class="sxs-lookup"><span data-stu-id="e940f-146">This account is used to read and synchronize your on-premises Active Directory information.</span></span> <span data-ttu-id="e940f-147">För att katalogsynkroniseringen ska fungera korrekt kontrollerar du att TCP 443 på den lokala katalogsynkroniseringsservern är öppen.</span><span class="sxs-lookup"><span data-stu-id="e940f-147">In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="e940f-148">När du har konfigurerat synkroniseringen måste du kontrollera att EOP synkroniseras korrekt.</span><span class="sxs-lookup"><span data-stu-id="e940f-148">After configuring your sync, be sure to verify that EOP is synchronizing correctly.</span></span> <span data-ttu-id="e940f-149">I EAC går du till **Mottagare** \> **Kontakter** och visa att listan över användare har synkroniserats korrekt från din lokala miljö.</span><span class="sxs-lookup"><span data-stu-id="e940f-149">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>

## <a name="use-the-eac-to-manage-mail-users"></a><span data-ttu-id="e940f-150">Använda EAC för att hantera e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="e940f-150">Use the EAC to manage mail users</span></span>

<span data-ttu-id="e940f-151">Det här avsnittet innehåller information om hur du lägger till och hanterar e-postanvändare direkt i EAC.</span><span class="sxs-lookup"><span data-stu-id="e940f-151">This section provides information about adding and managing email users directly in the EAC.</span></span>

### <a name="use-the-eac-to-add-a-mail-user"></a><span data-ttu-id="e940f-152">Använda EAC för att lägga till en e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="e940f-152">Use the EAC to add a mail user</span></span>

1. <span data-ttu-id="e940f-153">Skapa en e-postanvändare genom att gå till **Mottagare** \> **Kontakter** i EAC och klicka sedan på **Nytt +**.</span><span class="sxs-lookup"><span data-stu-id="e940f-153">Create an email user by going to go to **Recipients** \> **Contacts** in the EAC, and then clicking **New +**.</span></span>

2. <span data-ttu-id="e940f-154">På sidan **Ny e-postanvändare** anger du användarens information, inklusive följande:</span><span class="sxs-lookup"><span data-stu-id="e940f-154">On the **New mail user** page, enter the user's information, including the following:</span></span>

   ****

   |<span data-ttu-id="e940f-155">**Egenskapen E-postanvändare**</span><span class="sxs-lookup"><span data-stu-id="e940f-155">**Mail user property**</span></span>|<span data-ttu-id="e940f-156">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="e940f-156">**Description**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e940f-157">**Förnamn**, **Initialer**och **Efternamn**</span><span class="sxs-lookup"><span data-stu-id="e940f-157">**First name**, **Initials**, and **Last name**</span></span>|<span data-ttu-id="e940f-158">Skriv användarens fullständiga namn i lämpliga rutor.</span><span class="sxs-lookup"><span data-stu-id="e940f-158">Type the user's full name in the appropriate boxes.</span></span>|
   |<span data-ttu-id="e940f-159">**Visningsnamn**</span><span class="sxs-lookup"><span data-stu-id="e940f-159">**Display name**</span></span>|<span data-ttu-id="e940f-160">Skriv ett namn med upp till 64 tecken.</span><span class="sxs-lookup"><span data-stu-id="e940f-160">Type a name, using up to 64 characters.</span></span> <span data-ttu-id="e940f-161">Som standard visar den här rutan namnen i rutorna **Förnamn,** **Initialer**och **Efternamn** om sådana finns.</span><span class="sxs-lookup"><span data-stu-id="e940f-161">By default, this box shows the names in the **First name**, **Initials**, and **Last name** boxes if any.</span></span> <span data-ttu-id="e940f-162">Visningsnamnet krävs.</span><span class="sxs-lookup"><span data-stu-id="e940f-162">The display name is required.</span></span>|
   |<span data-ttu-id="e940f-163">**Alias**</span><span class="sxs-lookup"><span data-stu-id="e940f-163">**Alias**</span></span>|<span data-ttu-id="e940f-164">Skriv ett unikt alias med upp till 64 tecken för användaren.</span><span class="sxs-lookup"><span data-stu-id="e940f-164">Type a unique alias, using up to 64 characters, for the user.</span></span> <span data-ttu-id="e940f-165">Alias krävs.</span><span class="sxs-lookup"><span data-stu-id="e940f-165">The alias is required.</span></span>|
   |<span data-ttu-id="e940f-166">**Extern e-postadress**</span><span class="sxs-lookup"><span data-stu-id="e940f-166">**External email address**</span></span>|<span data-ttu-id="e940f-167">Skriv användarens externa e-postadress.</span><span class="sxs-lookup"><span data-stu-id="e940f-167">Type the external email address of the user.</span></span>|
   |<span data-ttu-id="e940f-168">**Användar-ID**</span><span class="sxs-lookup"><span data-stu-id="e940f-168">**User id**</span></span>|<span data-ttu-id="e940f-169">Ange det namn som e-postanvändaren ska använda för att logga in på tjänsten.</span><span class="sxs-lookup"><span data-stu-id="e940f-169">Type the name that the mail user will use to sign in to the service.</span></span> <span data-ttu-id="e940f-170">Användarens inloggningsnamn består av ett användarnamn till vänster om at-symbolen (@) och ett suffix till höger.</span><span class="sxs-lookup"><span data-stu-id="e940f-170">The user sign-in name consists of a user name on the left side of the at (@) symbol and a suffix on the right side.</span></span> <span data-ttu-id="e940f-171">Vanligtvis är suffixet det domännamn som användarkontot finns i.</span><span class="sxs-lookup"><span data-stu-id="e940f-171">Typically, the suffix is the domain name in which the user account resides.</span></span>|
   |<span data-ttu-id="e940f-172">**Nytt lösenord**</span><span class="sxs-lookup"><span data-stu-id="e940f-172">**New password**</span></span>|<span data-ttu-id="e940f-173">Skriv lösenordet som e-postanvändaren ska använda för att logga in på tjänsten.</span><span class="sxs-lookup"><span data-stu-id="e940f-173">Type the password that the mail user will use to sign in to the service.</span></span> <span data-ttu-id="e940f-174">Kontrollera att lösenordet du anger uppfyller kraven för lösenordslängd, komplexitet och historik för den domän där du skapar användarkontot.</span><span class="sxs-lookup"><span data-stu-id="e940f-174">Make sure that the password you supply complies with the password length, complexity, and history requirements of the domain in which you're creating the user account.</span></span>|
   |<span data-ttu-id="e940f-175">**Bekräfta lösenord   **</span><span class="sxs-lookup"><span data-stu-id="e940f-175">**Confirm password**</span></span>|<span data-ttu-id="e940f-176">Skriv in lösenordet igen för att bekräfta det.</span><span class="sxs-lookup"><span data-stu-id="e940f-176">Retype the password to confirm it.</span></span>|

3. <span data-ttu-id="e940f-177">Klicka på **Spara** om du vill skapa den nya e-postanvändaren.</span><span class="sxs-lookup"><span data-stu-id="e940f-177">Click **Save** to create the new email user.</span></span> <span data-ttu-id="e940f-178">Den nya användaren ska visas i listan över användare.</span><span class="sxs-lookup"><span data-stu-id="e940f-178">The new user should appear in the list of users.</span></span>

### <a name="use-the-eac-to-edit-or-remove-a-mail-user"></a><span data-ttu-id="e940f-179">Använda EAC för att redigera eller ta bort en e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="e940f-179">Use the EAC to edit or remove a mail user</span></span>

- <span data-ttu-id="e940f-180">Gå till **Mottagare** \> **kontakter**i EAC.</span><span class="sxs-lookup"><span data-stu-id="e940f-180">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="e940f-181">Klicka på den användare som du vill visa eller ändra **Edit** ![i listan](../../media/ITPro-EAC-EditIcon.gif) över användare och välj sedan ikonen Redigera redigera redigera för att uppdatera användarinställningarna efter behov.</span><span class="sxs-lookup"><span data-stu-id="e940f-181">In the list of users, click the user that you want to view or change, and then select **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.gif) to update the user settings as needed.</span></span> <span data-ttu-id="e940f-182">Du kan ändra användarens namn, alias eller kontaktinformation och du kan registrera detaljerad information om användarens roll i organisationen.</span><span class="sxs-lookup"><span data-stu-id="e940f-182">You can change the user's name, alias, or contact information, and you can record detailed information about the user's role in the organization.</span></span> <span data-ttu-id="e940f-183">Du kan också välja en användare](../../media/ITPro-EAC-RemoveIcon.gif) och sedan välja Ikonen Ta bort ta **bort** ![för att ta bort den.</span><span class="sxs-lookup"><span data-stu-id="e940f-183">You can also select a user and then choose **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to delete it.</span></span>

## <a name="use-exchange-online-protection-powershell-to-manage-mail-users"></a><span data-ttu-id="e940f-184">Använda Exchange Online Protection PowerShell för att hantera e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="e940f-184">Use Exchange Online Protection PowerShell to manage mail users</span></span>

<span data-ttu-id="e940f-185">Det här avsnittet innehåller information om hur du lägger till och hanterar e-postanvändare med hjälp av fjärr-Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e940f-185">This section provides information about adding and managing mail users by using remote Windows PowerShell.</span></span>

### <a name="use-eop-powershell-to-add-a-mail-user"></a><span data-ttu-id="e940f-186">Använda EOP PowerShell för att lägga till en e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="e940f-186">Use EOP PowerShell to add a mail user</span></span>

<span data-ttu-id="e940f-187">I det här exemplet används cmdleten [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) för att skapa ett e-postaktiverat användarkonto för Jeffrey Zeng i EOP med följande information:</span><span class="sxs-lookup"><span data-stu-id="e940f-187">This example uses the [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) cmdlet to create a mail-enabled user account for Jeffrey Zeng in EOP with the following details:</span></span>

- <span data-ttu-id="e940f-188">Förnamnet är Jeffrey och efternamnet är Zeng.</span><span class="sxs-lookup"><span data-stu-id="e940f-188">The first name is Jeffrey and the last name is Zeng.</span></span>

- <span data-ttu-id="e940f-189">Namnet är Jeffrey och visningsnamnet är Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="e940f-189">The name is Jeffrey and the display name is Jeffrey Zeng.</span></span>

- <span data-ttu-id="e940f-190">Alias är Jeffreyz.</span><span class="sxs-lookup"><span data-stu-id="e940f-190">The alias is jeffreyz.</span></span>

- <span data-ttu-id="e940f-191">Den externa e-postadressen är jzeng@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="e940f-191">The external email address is jzeng@tailspintoys.com.</span></span>

- <span data-ttu-id="e940f-192">Inloggningsnamnet för Office 365 är jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="e940f-192">The Office 365 sign in name is jeffreyz@contoso.onmicrosoft.com.</span></span>

- <span data-ttu-id="e940f-193">Lösenordet är Pa $ $word1.</span><span class="sxs-lookup"><span data-stu-id="e940f-193">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

<span data-ttu-id="e940f-194">Om du vill kontrollera att detta fungerade kör du följande kommando för att visa information om den nya e-postanvändaren Jeffrey Zeng:</span><span class="sxs-lookup"><span data-stu-id="e940f-194">To verify that this worked, run the following command to display information about new mail user Jeffrey Zeng:</span></span>

```PowerShell
Get-User -Identity "Jeffrey Zeng"
```

<span data-ttu-id="e940f-195">Detaljerad syntax- och parameterinformation finns i [Hämta användare](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).</span><span class="sxs-lookup"><span data-stu-id="e940f-195">For detailed syntax and parameter information, see [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).</span></span>

### <a name="use-eop-powershell-to-edit-the-properties-of-a-mail-user"></a><span data-ttu-id="e940f-196">Använda EOP PowerShell för att redigera egenskaperna för en e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="e940f-196">Use EOP PowerShell to edit the properties of a mail user</span></span>

<span data-ttu-id="e940f-197">Använd cmdlets hämta mottagare och [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) för att visa eller ändra egenskaper för [e-postanvändare.](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient)</span><span class="sxs-lookup"><span data-stu-id="e940f-197">Use the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) and [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) cmdlets to view or change properties for mail users.</span></span>

<span data-ttu-id="e940f-198">I det här exemplet anges den externa e-postadressen för Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="e940f-198">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="e940f-199">I det här exemplet anges egenskapen Företag för alla e-postanvändare till Contoso.</span><span class="sxs-lookup"><span data-stu-id="e940f-199">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="e940f-200">Om du vill kontrollera att detta fungerade använder du cmdleten [Hämta mottagare](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) för att verifiera ändringarna.</span><span class="sxs-lookup"><span data-stu-id="e940f-200">To verify that this worked, use the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) cmdlet to verify the changes.</span></span> <span data-ttu-id="e940f-201">(Observera att du kan visa flera egenskaper för flera e-postkontakter.)</span><span class="sxs-lookup"><span data-stu-id="e940f-201">(Note that you can view multiple properties for multiple mail contacts.)</span></span>

```PowerShell
Get-Recipient -Identity "Pilar Pinilla" | Format-List
```

<span data-ttu-id="e940f-202">I föregående exempel där egenskapen Företag angavs till Contoso för alla e-postanvändare kör du följande kommando för att verifiera ändringarna:</span><span class="sxs-lookup"><span data-stu-id="e940f-202">In the previous example where the Company property was set to Contoso for all mail users, run the following command to verify the changes:</span></span>

```PowerShell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> <span data-ttu-id="e940f-203">Denna cmdlet använder en batchbearbetningsmetod som resulterar i en spridningsfördröjning på några minuter innan cmdletens resultat är synliga.</span><span class="sxs-lookup"><span data-stu-id="e940f-203">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>

### <a name="use-eop-powershell-to-remove-a-mail-user"></a><span data-ttu-id="e940f-204">Använda EOP PowerShell för att ta bort en e-postanvändare</span><span class="sxs-lookup"><span data-stu-id="e940f-204">Use EOP PowerShell to remove a mail user</span></span>

<span data-ttu-id="e940f-205">I det här exemplet används cmdleten [Ta bort EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopmailuser) för att ta bort användaren Jeffrey Zeng:</span><span class="sxs-lookup"><span data-stu-id="e940f-205">This example uses the [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopmailuser) cmdlet to delete user Jeffrey Zeng:</span></span>

```PowerShell
Remove-EOPMailUser -Identity Jeffrey
```
<span data-ttu-id="e940f-206">Om du vill kontrollera att detta fungerade kör du cmdleten Hämta mottagare för att kontrollera att [e-postanvändaren](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) inte längre finns.</span><span class="sxs-lookup"><span data-stu-id="e940f-206">To verify that this worked, run the [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) cmdlet to verify that the mail user no longer exists.</span></span>

```PowerShell
Get-Recipient Jeffrey | Format-List
```
