---
title: Hantera Meddelandekryptering i Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: När du är klar med att konfigurera Meddelandekryptering i Office 365 (OME) kan du lära dig hur du anpassar distributionen på flera olika sätt.
ms.openlocfilehash: a2b3dde44ea541deb41eeb9d55d5ed745fa6c719
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52650990"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="e911b-103">Hantera Meddelandekryptering i Office 365</span><span class="sxs-lookup"><span data-stu-id="e911b-103">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="e911b-104">När du är klar med konfigureringen Meddelandekryptering i Office 365 (OME) kan du anpassa konfigurationen av distributionen på flera olika sätt.</span><span class="sxs-lookup"><span data-stu-id="e911b-104">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="e911b-105">Du kan till exempel konfigurera om du vill aktivera  lösenord för endast en gång, visa knappen Kryptera i Outlook på webben och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="e911b-105">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="e911b-106">Uppgifterna i den här artikeln beskriver hur.</span><span class="sxs-lookup"><span data-stu-id="e911b-106">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="e911b-107">Hantera om mottagarna av Google-, Yahoo- och Microsoft-konton kan använda dessa konton för att logga in på Meddelandekryptering i Office 365 portalen</span><span class="sxs-lookup"><span data-stu-id="e911b-107">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="e911b-108">När du konfigurerat Meddelandekryptering i Office 365 funktioner kan användare i organisationen skicka meddelanden till mottagare som finns utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="e911b-108">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your organization.</span></span> <span data-ttu-id="e911b-109">Om mottagaren använder ett *socialt ID,* till exempel ett Google-konto, Yahoo-konto eller Microsoft-konto, kan mottagaren logga in på OME-portalen med ett socialt ID.</span><span class="sxs-lookup"><span data-stu-id="e911b-109">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="e911b-110">Om du vill kan du välja att inte tillåta att mottagare använder sociala IDs för att logga in på OME-portalen.</span><span class="sxs-lookup"><span data-stu-id="e911b-110">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="e911b-111">Så här hanterar du om mottagare kan använda sociala IDs för att logga in på OME-portalen</span><span class="sxs-lookup"><span data-stu-id="e911b-111">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="e911b-112">[Anslut att Exchange Online använda Remote PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="e911b-112">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e911b-113">Kör cmdleten Set-OMEConfiguration Med parametern SocialIdSignIn enligt följande:</span><span class="sxs-lookup"><span data-stu-id="e911b-113">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="e911b-114">Om du till exempel vill inaktivera sociala ID:</span><span class="sxs-lookup"><span data-stu-id="e911b-114">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="e911b-115">Så här aktiverar du sociala ID:</span><span class="sxs-lookup"><span data-stu-id="e911b-115">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="e911b-116">Hantera användningen av lösenordskoder för Meddelandekryptering i Office 365 portalen</span><span class="sxs-lookup"><span data-stu-id="e911b-116">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="e911b-117">Om mottagaren av ett meddelande som krypteras med OME inte använder Outlook, oavsett vilket konto som används av mottagaren, får mottagaren en tidsbegränsad webbvylänk som gör att mottagaren kan läsa meddelandet.</span><span class="sxs-lookup"><span data-stu-id="e911b-117">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="e911b-118">Den här länken innehåller en kod för ett lösenord.</span><span class="sxs-lookup"><span data-stu-id="e911b-118">This link includes a one-time pass code.</span></span> <span data-ttu-id="e911b-119">Som administratör kan du bestämma om mottagarna ska kunna logga in på OME-portalen med hjälp av koder som du använder som lösenord.</span><span class="sxs-lookup"><span data-stu-id="e911b-119">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="e911b-120">Så här hanterar du om OME genererar koder för en gång</span><span class="sxs-lookup"><span data-stu-id="e911b-120">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="e911b-121">Använd ett arbets- eller skolkonto som har globala administratörsbehörigheter i din organisation och starta en Windows PowerShell session och anslut till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e911b-121">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e911b-122">För instruktioner se: [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e911b-122">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e911b-123">Kör Set-OMEConfiguration-cmdleten med parametern OTPEnabled:</span><span class="sxs-lookup"><span data-stu-id="e911b-123">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="e911b-124">Så här inaktiverar du till exempel lösenord för en gång:</span><span class="sxs-lookup"><span data-stu-id="e911b-124">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="e911b-125">Så här aktiverar du lösenord för en gång:</span><span class="sxs-lookup"><span data-stu-id="e911b-125">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="e911b-126">Hantera visningen av knappen Kryptera i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="e911b-126">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="e911b-127">Som administratör kan du hantera om den här knappen ska visas för slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="e911b-127">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="e911b-128">Så här hanterar du om knappen Kryptera visas Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="e911b-128">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="e911b-129">Använd ett arbets- eller skolkonto som har globala administratörsbehörigheter i din organisation och starta en Windows PowerShell session och anslut till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e911b-129">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e911b-130">För instruktioner se: [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e911b-130">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e911b-131">Kör cmdleten Set-IRMConfiguration -SimplifiedClientAccessEnabled:</span><span class="sxs-lookup"><span data-stu-id="e911b-131">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="e911b-132">Om du till exempel vill inaktivera **knappen** Kryptera:</span><span class="sxs-lookup"><span data-stu-id="e911b-132">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="e911b-133">Så här aktiverar du **knappen** Kryptera:</span><span class="sxs-lookup"><span data-stu-id="e911b-133">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="e911b-134">Aktivera dekryptering av e-postmeddelanden på tjänstsidan för e-postanvändare i iOS-e-postprogrammet</span><span class="sxs-lookup"><span data-stu-id="e911b-134">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="e911b-135">E-postprogrammet i iOS kan inte dekryptera meddelanden som skyddas med Meddelandekryptering i Office 365.</span><span class="sxs-lookup"><span data-stu-id="e911b-135">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="e911b-136">Som administratör Microsoft 365 kan du använda dekryptering på tjänstsidan för meddelanden som levereras till e-postprogrammet i iOS.</span><span class="sxs-lookup"><span data-stu-id="e911b-136">As a Microsoft 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="e911b-137">När du väljer att dekryptera på tjänstsidan skickar tjänsten en dekrypterad kopia av meddelandet till iOS-enheten.</span><span class="sxs-lookup"><span data-stu-id="e911b-137">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="e911b-138">En dekrypterad kopia av meddelandet lagras på klientenheten.</span><span class="sxs-lookup"><span data-stu-id="e911b-138">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="e911b-139">Meddelandet behåller även information om användningsrättigheter även om e-postappen i iOS inte tillämpar användningsrättigheter på klientsidan för användaren.</span><span class="sxs-lookup"><span data-stu-id="e911b-139">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="e911b-140">Användaren kan kopiera eller skriva ut meddelandet även om de inte ursprungligen har behörighet att göra det.</span><span class="sxs-lookup"><span data-stu-id="e911b-140">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="e911b-141">Men om användaren försöker slutföra en åtgärd som kräver att Microsoft 365-e-postservern, till exempel vidarebefordrar meddelandet, tillåter servern inte åtgärden om användaren inte ursprungligen har rätt att göra det.</span><span class="sxs-lookup"><span data-stu-id="e911b-141">However, if the user attempts to complete an action that requires the Microsoft 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="e911b-142">Men slutanvändarna kan komma runt användningsbegränsningen Vidarebefordra inte genom att vidarebefordra meddelandet från ett annat konto i e-postprogrammet i iOS.</span><span class="sxs-lookup"><span data-stu-id="e911b-142">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="e911b-143">Oavsett om du anger dekryptering av e-post på tjänstsidan kan inte bifogade filer i krypterad och rättighetsskyddad e-post visas i e-postprogrammet i iOS.</span><span class="sxs-lookup"><span data-stu-id="e911b-143">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="e911b-144">Om du väljer att inte tillåta att dekrypterade meddelanden skickas till användare i iOS-e-postprogrammet får användarna ett meddelande om att de inte har behörighet att visa meddelandet.</span><span class="sxs-lookup"><span data-stu-id="e911b-144">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="e911b-145">Som standard är dekryptering av e-postmeddelanden inte aktiverat på tjänstsidan.</span><span class="sxs-lookup"><span data-stu-id="e911b-145">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="e911b-146">Mer information och en vy över klientupplevelsen finns i Visa [krypterade](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)meddelanden på din iPhone eller iPad .</span><span class="sxs-lookup"><span data-stu-id="e911b-146">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="e911b-147">Hantera om användare av iOS-e-postprogram kan visa meddelanden som skyddas av Meddelandekryptering i Office 365</span><span class="sxs-lookup"><span data-stu-id="e911b-147">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="e911b-148">Använd ett arbets- eller skolkonto som har globala administratörsbehörigheter i din organisation och starta en Windows PowerShell session och anslut till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e911b-148">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e911b-149">För instruktioner se: [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e911b-149">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e911b-150">Kör Set-ActiveSyncOrganizations med parametern AllowRMSSupportForUnenlightenedApps:</span><span class="sxs-lookup"><span data-stu-id="e911b-150">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="e911b-151">Om du till exempel vill konfigurera tjänsten för att dekryptera meddelanden innan de skickas till oaktiverade appar som e-postprogrammet i iOS:</span><span class="sxs-lookup"><span data-stu-id="e911b-151">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="e911b-152">Om du vill konfigurera tjänsten så att dekrypterade meddelanden inte skickas till oaktiverade appar:</span><span class="sxs-lookup"><span data-stu-id="e911b-152">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> <span data-ttu-id="e911b-153">Enskilda postlådeprinciper (OWA/ActiveSync) åsidosätter de här inställningarna (dvs. om -IRMEnabled är inställt på Falskt inom respektive OWA-postlådeprincip eller ActiveSync-postlådeprincip, gäller inte de här konfigurationerna).</span><span class="sxs-lookup"><span data-stu-id="e911b-153">Individual mailbox policies (OWA/ActiveSync) override these settings (i.e. if -IRMEnabled is set to False within the respective OWA Mailbox policy, or ActiveSync Mailbox policy, then these configurations would not apply).</span></span>

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="e911b-154">Aktivera dekryptering av e-postbilagor på tjänstsidan för e-postklienter i webbläsaren</span><span class="sxs-lookup"><span data-stu-id="e911b-154">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="e911b-155">När du använder Office 365 krypteras bifogade filer automatiskt.</span><span class="sxs-lookup"><span data-stu-id="e911b-155">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="e911b-156">Som administratör kan du använda dekryptering på tjänstsidan för e-postbilagor som användare laddar ned från en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="e911b-156">As an administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="e911b-157">När du använder dekryptering på tjänstsidan skickar tjänsten en dekrypterad kopia av filen till enheten.</span><span class="sxs-lookup"><span data-stu-id="e911b-157">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="e911b-158">Meddelandet krypteras fortfarande.</span><span class="sxs-lookup"><span data-stu-id="e911b-158">The message is still encrypted.</span></span> <span data-ttu-id="e911b-159">Den bifogade filen för e-post behåller även information om användningsrättigheter även om webbläsaren inte gäller användarens användningsrättigheter på klientsidan.</span><span class="sxs-lookup"><span data-stu-id="e911b-159">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="e911b-160">Användaren kan kopiera eller skriva ut den bifogade filen i ett e-postmeddelande även om de inte ursprungligen har behörighet att göra det.</span><span class="sxs-lookup"><span data-stu-id="e911b-160">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="e911b-161">Men om användaren försöker slutföra en åtgärd som kräver att Microsoft 365-e-postservern, till exempel vidarebefordrar den bifogade filen, tillåter servern inte åtgärden om användaren inte ursprungligen har rätt att göra det.</span><span class="sxs-lookup"><span data-stu-id="e911b-161">However, if the user tries to complete an action that requires the Microsoft 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="e911b-162">Oavsett om du krypterar bifogade filer på tjänstsidan kan användarna inte visa bifogade filer i krypterad och rättighetsskyddad e-post i iOS-e-postprogrammet.</span><span class="sxs-lookup"><span data-stu-id="e911b-162">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="e911b-163">Om du väljer att inte tillåta dekrypterade e-postbilagor, vilket är standard, får användarna ett meddelande om att de inte har behörighet att visa den bifogade filen.</span><span class="sxs-lookup"><span data-stu-id="e911b-163">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="e911b-164">Mer information om hur Microsoft 365 implementerar kryptering för e-postmeddelanden och e-postbilagor med alternativet Encrypt-Only finns [i Alternativet Endast kryptering för e-postmeddelanden.](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="e911b-164">For more information about how Microsoft 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="e911b-165">Hantera om e-postbilagor dekrypteras vid nedladdning från en webbläsare</span><span class="sxs-lookup"><span data-stu-id="e911b-165">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="e911b-166">Använd ett arbets- eller skolkonto som har globala administratörsbehörigheter i din organisation och starta en Windows PowerShell session och anslut till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e911b-166">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e911b-167">För instruktioner se: [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e911b-167">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e911b-168">Kör cmdleten Set-IRMConfiguration med parametern DecryptAttachmentForEncryptOnly:</span><span class="sxs-lookup"><span data-stu-id="e911b-168">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentForEncryptOnly parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   <span data-ttu-id="e911b-169">Om du till exempel vill konfigurera tjänsten för att dekryptera e-postbilagor när en användare hämtar dem från en webbläsare:</span><span class="sxs-lookup"><span data-stu-id="e911b-169">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   <span data-ttu-id="e911b-170">Så här konfigurerar du tjänsten för att lämna krypterade e-postbilagor som de är vid nedladdning:</span><span class="sxs-lookup"><span data-stu-id="e911b-170">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a><span data-ttu-id="e911b-171">Kontrollera att alla externa mottagare använder OME-portalen för att läsa krypterad e-post</span><span class="sxs-lookup"><span data-stu-id="e911b-171">Ensure all external recipients use the OME Portal to read encrypted mail</span></span>

<span data-ttu-id="e911b-172">Du kan använda anpassade varumärkesmallar för att tvinga mottagare att ta emot ett omslagsmeddelande som dirigerar dem till att läsa krypterad e-post i OME-portalen i stället för att använda Outlook eller Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="e911b-172">You can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="e911b-173">Det kan vara bra att göra det om du vill ha större kontroll över hur mottagarna använder sin e-post.</span><span class="sxs-lookup"><span data-stu-id="e911b-173">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="e911b-174">Om externa mottagare till exempel visar e-post i webbportalen kan du ange ett utgångsdatum för e-postmeddelandet och återkalla e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="e911b-174">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="e911b-175">De här funktionerna stöds endast via OME-portalen.</span><span class="sxs-lookup"><span data-stu-id="e911b-175">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="e911b-176">Du kan använda alternativen Kryptera och Vidarebefordra inte när du skapar e-postflödesregler.</span><span class="sxs-lookup"><span data-stu-id="e911b-176">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a><span data-ttu-id="e911b-177">Använda en anpassad mall för att tvinga alla externa mottagare att använda OME-portalen och för krypterad e-post</span><span class="sxs-lookup"><span data-stu-id="e911b-177">Use a custom template to force all external recipients to use the OME Portal and for encrypted email</span></span>

1. <span data-ttu-id="e911b-178">Använd ett arbets- eller skolkonto som har globala administratörsbehörigheter i din organisation och starta en Windows PowerShell session och anslut till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e911b-178">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e911b-179">För instruktioner se: [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e911b-179">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e911b-180">Kör cmdleten New-TransportRule-cmdleten:</span><span class="sxs-lookup"><span data-stu-id="e911b-180">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="e911b-181">där:</span><span class="sxs-lookup"><span data-stu-id="e911b-181">where:</span></span>

   - <span data-ttu-id="e911b-182">`mail flow rule name` är det namn du vill använda för den nya e-postflödesregeln.</span><span class="sxs-lookup"><span data-stu-id="e911b-182">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="e911b-183">`option name` är antingen `Encrypt` eller `Do Not Forward` .</span><span class="sxs-lookup"><span data-stu-id="e911b-183">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="e911b-184">`template name` är namnet du gav mallen för anpassade profilering, till exempel `OME Configuration` .</span><span class="sxs-lookup"><span data-stu-id="e911b-184">`template name` is the name you gave the custom branding template, for example `OME Configuration`.</span></span>

   <span data-ttu-id="e911b-185">Om du vill kryptera all extern e-post med mallen "OME-konfiguration" och använda Encrypt-Only alternativet:</span><span class="sxs-lookup"><span data-stu-id="e911b-185">To encrypt all external email with the "OME Configuration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   <span data-ttu-id="e911b-186">Om du vill kryptera all extern e-post med mallen "OME-konfiguration" och använda alternativet Vidarebefordra inte:</span><span class="sxs-lookup"><span data-stu-id="e911b-186">To encrypt all external email with the "OME Configuration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="e911b-187">Anpassa utseendet på e-postmeddelanden och OME-portalen</span><span class="sxs-lookup"><span data-stu-id="e911b-187">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="e911b-188">Detaljerad information om hur du kan anpassa OME för organisationen finns i [Lägga till företagets varumärke i krypterade meddelanden.](add-your-organization-brand-to-encrypted-messages.md)</span><span class="sxs-lookup"><span data-stu-id="e911b-188">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="e911b-189">Inaktivera de nya funktionerna för OME</span><span class="sxs-lookup"><span data-stu-id="e911b-189">Disable the new capabilities for OME</span></span>

<span data-ttu-id="e911b-190">Vi hoppas att det inte blir så, men om du behöver det är det mycket enkelt att inaktivera de nya funktionerna för OME.</span><span class="sxs-lookup"><span data-stu-id="e911b-190">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="e911b-191">Först måste du ta bort alla e-postflödesregler som du har skapat och som använder de nya OME-funktionerna.</span><span class="sxs-lookup"><span data-stu-id="e911b-191">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="e911b-192">Information om hur du tar bort e-postflödesregler finns [i Hantera e-postflödesregler.](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="e911b-192">For information about removing mail flow rules, see [Manage mail flow rules](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span></span> <span data-ttu-id="e911b-193">Utför sedan dessa steg i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e911b-193">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="e911b-194">Inaktivera de nya funktionerna för OME</span><span class="sxs-lookup"><span data-stu-id="e911b-194">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="e911b-195">Om du använder ett arbets- eller skolkonto med global administratörsbehörighet i din organisation startar du Windows PowerShell en session och ansluter till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e911b-195">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e911b-196">För instruktioner se: [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e911b-196">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e911b-197">Om du  har aktiverat knappen Kryptera i Outlook på webben inaktiverar du den genom att köra cmdleten Set-IRMConfiguration med parametern SimplifiedClientAccessEnabled.</span><span class="sxs-lookup"><span data-stu-id="e911b-197">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="e911b-198">Annars hoppar du över det här steget.</span><span class="sxs-lookup"><span data-stu-id="e911b-198">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="e911b-199">Inaktivera de nya funktionerna för OME genom att köra cmdleten Set-IRMConfiguration med parametern AzureRMSLicensingEnabled inställd på falskt:</span><span class="sxs-lookup"><span data-stu-id="e911b-199">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
