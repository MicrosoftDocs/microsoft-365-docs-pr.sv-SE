---
title: Hantera ett komprometterat e-postkonto
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection:
- o365_security_incident_response
- M365-security-compliance
- m365solution-smb
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Lär dig hur du känner igen och hanterar ett komprometterat e-postkonto ned tillgängliga verktyg i Microsoft 365.
ms.openlocfilehash: cfd20b0d5e6e13343346761b9b909a333b9a6ff5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827523"
---
# <a name="responding-to-a-compromised-email-account"></a><span data-ttu-id="fce93-103">Hantera ett komprometterat e-postkonto</span><span class="sxs-lookup"><span data-stu-id="fce93-103">Responding to a Compromised Email Account</span></span>

<span data-ttu-id="fce93-104">**Sammanfattning** Lär dig hur du känner igen och hanterar ett komprometterat e-postkonto i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fce93-104">**Summary** Learn how to recognize and respond to a compromised email account in Microsoft 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a><span data-ttu-id="fce93-105">Vad är ett komprometterat e-postkonto i Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="fce93-105">What is a Compromised Email Account in Microsoft 365?</span></span>

<span data-ttu-id="fce93-106">Åtkomst till Microsoft 365-postlådor, data och andra tjänster styrs genom användningen av autentiseringsuppgifter, t.ex. ett användarnamn och lösenord eller en PIN-kod.</span><span class="sxs-lookup"><span data-stu-id="fce93-106">Access to Microsoft 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN.</span></span> <span data-ttu-id="fce93-107">När någon annan än den avsedda användaren stjäl de här autentiseringsuppgifterna anses de stulna uppgifterna ha komprometterats.</span><span class="sxs-lookup"><span data-stu-id="fce93-107">When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised.</span></span> <span data-ttu-id="fce93-108">Angriparen kan använda dem för att logga in som den ursprungliga användaren och utföra illegala åtgärder.</span><span class="sxs-lookup"><span data-stu-id="fce93-108">With them the attacker can sign in as the original user and perform illicit actions.</span></span>
<span data-ttu-id="fce93-109">Med hjälp av de stulna autentiseringsuppgifterna kan angriparen komma åt användarens Microsoft 365-postlåda, SharePoint-mappar eller filer i användarens OneDrive.</span><span class="sxs-lookup"><span data-stu-id="fce93-109">Using the stolen credentials, the attacker can access the user's Microsoft 365 mailbox, SharePoint folders, or files in the user's OneDrive.</span></span> <span data-ttu-id="fce93-110">En vanligt förekommande åtgärd är att angriparen skickar e-postmeddelanden i den ursprungliga användarens namn till mottagare både inom och utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="fce93-110">One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization.</span></span> <span data-ttu-id="fce93-111">När angriparen skickar data via e-post till externa mottagare kallas det för dataexfiltrering.</span><span class="sxs-lookup"><span data-stu-id="fce93-111">When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a><span data-ttu-id="fce93-112">Symptom hos ett komprometterat Microsoft-e-postkonto</span><span class="sxs-lookup"><span data-stu-id="fce93-112">Symptoms of a Compromised Microsoft Email Account</span></span>

<span data-ttu-id="fce93-113">Användarna kan lägga märka till och rapportera ovanliga aktiviteter i sina Microsoft 365-postlådor.</span><span class="sxs-lookup"><span data-stu-id="fce93-113">Users might notice and report unusual activity in their Microsoft 365 mailboxes.</span></span> <span data-ttu-id="fce93-114">Här är några vanliga tecken:</span><span class="sxs-lookup"><span data-stu-id="fce93-114">Here are some common symptoms:</span></span>

- <span data-ttu-id="fce93-115">Misstänkt aktivitet, t.ex. saknade eller borttagna e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="fce93-115">Suspicious activity, such as missing or deleted emails.</span></span>

- <span data-ttu-id="fce93-116">Andra användare kan få e-postmeddelanden från det skadade kontot utan att motsvarande e-postmeddelanden finns i mappen **Skickat** hos avsändaren.</span><span class="sxs-lookup"><span data-stu-id="fce93-116">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>

- <span data-ttu-id="fce93-117">Förekomsten av inkorgsregler som inte har skapats av den avsedda användaren eller administratören.</span><span class="sxs-lookup"><span data-stu-id="fce93-117">The presence of inbox rules that weren't created by the intended user or the administrator.</span></span> <span data-ttu-id="fce93-118">Reglerna kan automatiskt vidarebefordra e-postmeddelanden till okända adresser eller flytta dem till någon av mapparna **Anteckningar**, **Skräppost** eller **RSS-prenumerationer**.</span><span class="sxs-lookup"><span data-stu-id="fce93-118">These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>

- <span data-ttu-id="fce93-119">Användarens visningsnamn kan ändras i den globala adresslistan.</span><span class="sxs-lookup"><span data-stu-id="fce93-119">The user's display name might be changed in the Global Address List.</span></span>

- <span data-ttu-id="fce93-120">Användarens postlåda hindras från att skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="fce93-120">The user's mailbox is blocked from sending email.</span></span>

- <span data-ttu-id="fce93-121">Mapparna Skickat och Borttaget i Microsoft Outlook eller Outlook på webben (tidigare Outlook Web App) innehåller vanliga meddelanden för hackade konton, t. ex. ”Jag är fast i London, skicka pengar”.</span><span class="sxs-lookup"><span data-stu-id="fce93-121">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>

- <span data-ttu-id="fce93-122">Ovanliga profiländringar av t.ex. namn eller telefonnummer, eller uppdatering av postnumret.</span><span class="sxs-lookup"><span data-stu-id="fce93-122">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>

- <span data-ttu-id="fce93-123">Ovanliga ändringar av autentiseringsuppgifter, till exempel flera ändringar av lösenordet krävs.</span><span class="sxs-lookup"><span data-stu-id="fce93-123">Unusual credential changes, such as multiple password changes are required.</span></span>

- <span data-ttu-id="fce93-124">Vidarebefordring av e-post har lagts till nyligen.</span><span class="sxs-lookup"><span data-stu-id="fce93-124">Mail forwarding was recently added.</span></span>

- <span data-ttu-id="fce93-125">En ovanlig signatur har nyligen lagts till, t.ex. en förfalskad banksignatur eller en signatur för ett receptbelagt läkemedel.</span><span class="sxs-lookup"><span data-stu-id="fce93-125">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="fce93-126">Om en användare rapporterar något av ovanstående symptom bör du utföra ytterligare utredningar.</span><span class="sxs-lookup"><span data-stu-id="fce93-126">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="fce93-127">Säkerhets- och efterlevnadscenter för Microsoft 365 och Azure-portalen tillhandahåller verktyg som hjälper dig att undersöka aktiviteter hos ett användarkonto som du misstänker kan ha komprometterats.</span><span class="sxs-lookup"><span data-stu-id="fce93-127">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="fce93-128">**Enhetliga granskningsloggar i Säkerhets- och efterlevnadscenter**: Granska alla aktiviteter för det misstänkta kontot genom att filtrera resultaten för datumintervallet från före den misstänkta aktiviteten till dagens datum.</span><span class="sxs-lookup"><span data-stu-id="fce93-128">**Unified Audit Logs in the Security & Compliance Center**: Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date.</span></span> <span data-ttu-id="fce93-129">Filtrera inte på aktiviteterna under sökningen.</span><span class="sxs-lookup"><span data-stu-id="fce93-129">Do not filter on the activities during the search.</span></span>

- <span data-ttu-id="fce93-130">**Granskningsloggar för administratörer i EAC**: I Exchange Online kan du använda administrationscentret för Exchange (EAC) för att söka efter och visa poster i granskningsloggen för administratörer.</span><span class="sxs-lookup"><span data-stu-id="fce93-130">**Admin Audit logs in the EAC**: In Exchange Online, you can use the Exchange admin center (EAC) to search for and view entries in the administrator audit log.</span></span> <span data-ttu-id="fce93-131">I granskningsloggen för administratörer registreras vissa åtgärder baserat på Exchange Online PowerShell-cmdletar, utförda av administratörer och användare som har tilldelats administratörsbehörigheter.</span><span class="sxs-lookup"><span data-stu-id="fce93-131">The administrator audit log records specific actions, based on Exchange Online PowerShell cmdlets, performed by administrators and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="fce93-132">Poster i granskningsloggen för administratörer innehåller information om vilken cmdlet som kördes, vilka parametrar som användes, vem som körde cmdleten och vilka objekt som påverkades.</span><span class="sxs-lookup"><span data-stu-id="fce93-132">Entries in the administrator audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

- <span data-ttu-id="fce93-133">**Inloggningsloggar för Azure AD och andra riskrapporter på Azure AD-portalen**: Granska värdena i följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="fce93-133">**Azure AD Sign-in logs and other risk reports in the Azure AD portal**: Examine the values in these columns:</span></span>

  - <span data-ttu-id="fce93-134">Granska IP-adress</span><span class="sxs-lookup"><span data-stu-id="fce93-134">Review IP address</span></span>
  - <span data-ttu-id="fce93-135">inloggningsplatser</span><span class="sxs-lookup"><span data-stu-id="fce93-135">sign-in locations</span></span>
  - <span data-ttu-id="fce93-136">inloggningstider</span><span class="sxs-lookup"><span data-stu-id="fce93-136">sign-in times</span></span>
  - <span data-ttu-id="fce93-137">lyckad eller misslyckad inloggning</span><span class="sxs-lookup"><span data-stu-id="fce93-137">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a><span data-ttu-id="fce93-138">Så kan du skydda och återställa e-postfunktionen till ett konto eller en postlåda i Microsoft 365 som misstänks ha komprometterats</span><span class="sxs-lookup"><span data-stu-id="fce93-138">How to secure and restore email function to a suspected compromised Microsoft 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="fce93-139">Även efter att du har återskapat åtkomsten till ditt konto kan angriparen ha lagt till bakdörrsposter som gör det möjligt för angripare att återta kontrollen av kontot.</span><span class="sxs-lookup"><span data-stu-id="fce93-139">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="fce93-140">Du måste utföra alla följande steg för att återta åtkomsten till ditt konto så snabbt som möjligt, för att se till att kaparen inte återtar kontrollen av ditt konto.</span><span class="sxs-lookup"><span data-stu-id="fce93-140">You must perform all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account.</span></span> <span data-ttu-id="fce93-141">De här åtgärderna hjälper dig att ta bort alla eventuella bakdörrsposter som kaparen kan ha lagt till på ditt konto.</span><span class="sxs-lookup"><span data-stu-id="fce93-141">These steps help you remove any back-door entries that the hijacker may have added to your account.</span></span> <span data-ttu-id="fce93-142">När du har utfört de här stegen rekommenderar vi att du kör en viruskontroll för att se till att datorn inte är komprometterad.</span><span class="sxs-lookup"><span data-stu-id="fce93-142">After you perform these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="fce93-143">Steg 1 Återställ användarens lösenord</span><span class="sxs-lookup"><span data-stu-id="fce93-143">Step 1 Reset the user's password</span></span>

<span data-ttu-id="fce93-144">Följ anvisningarna i [återställa ett företags lösen ord för någon](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords#reset-my-admin-password).</span><span class="sxs-lookup"><span data-stu-id="fce93-144">Follow the procedures in [Reset a business password for someone](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords#reset-my-admin-password).</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="fce93-145">Skicka inte det nya lösen ordet till den avsedda användaren via e-post, eftersom angriparen fortfarande har tillgång till postlådan.</span><span class="sxs-lookup"><span data-stu-id="fce93-145">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>
>
> - <span data-ttu-id="fce93-146">Kontrollera att lösenordet är starkt och att det innehåller gemener, versaler, minst en siffra och minst ett specialtecken.</span><span class="sxs-lookup"><span data-stu-id="fce93-146">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span>
>
> - <span data-ttu-id="fce93-147">Återanvänd aldrig något av ditt senaste fem lösenord.</span><span class="sxs-lookup"><span data-stu-id="fce93-147">Don't reuse any of your last five passwords.</span></span> <span data-ttu-id="fce93-148">Även om kravet för lösenordshistorik gör att du kan återanvända ett lösenord du använt nyligen bör du välja något som angriparen inte kan gissa.</span><span class="sxs-lookup"><span data-stu-id="fce93-148">Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>
>
> - <span data-ttu-id="fce93-149">Om din lokala identitet är federerad med Microsoft 365 måste du ändra ditt lösenord lokalt och därefter informera administratören om skadan.</span><span class="sxs-lookup"><span data-stu-id="fce93-149">If your on-premises identity is federated with Microsoft 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>
>
> - <span data-ttu-id="fce93-150">Se till att uppdatera applösenord.</span><span class="sxs-lookup"><span data-stu-id="fce93-150">Be sure to update app passwords.</span></span> <span data-ttu-id="fce93-151">Applösenord återkallas inte automatiskt när ett lösenord för ett användarkonto återställs.</span><span class="sxs-lookup"><span data-stu-id="fce93-151">App passwords aren't automatically revoked when a user account password reset.</span></span> <span data-ttu-id="fce93-152">Användaren ska ta bort befintliga applösenord och skapa nya.</span><span class="sxs-lookup"><span data-stu-id="fce93-152">The user should delete existing app passwords and create new ones.</span></span> <span data-ttu-id="fce93-153">För instruktioner, se [Skapa och ta bort applösenord från sidan Ytterligare säkerhetsverifiering](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).</span><span class="sxs-lookup"><span data-stu-id="fce93-153">For instructions, see [Create and delete app passwords from the Additional security verification page](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).</span></span>
>
> - <span data-ttu-id="fce93-154">Vi rekommenderar att du aktiverar multifaktorautentisering (MFA) för att förhindra kompromettering, i synnerhet för konton med administratörsbehörigheter.</span><span class="sxs-lookup"><span data-stu-id="fce93-154">We highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.</span></span> <span data-ttu-id="fce93-155">Mer information om MFA finns i [Konfigurera multifaktorautentisering](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="fce93-155">To learn more about MFA, go to [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="fce93-156">Steg 2 Ta bort misstänkta adresser för vidarebefordran av e-post</span><span class="sxs-lookup"><span data-stu-id="fce93-156">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="fce93-157">Öppna Administrationscenter för Microsoft 365 på <https://admin.microsoft.com></span><span class="sxs-lookup"><span data-stu-id="fce93-157">Open the Microsoft 365 admin center at <https://admin.microsoft.com></span></span>

2. <span data-ttu-id="fce93-158">Gå till **användare** \> **aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="fce93-158">Go to **Users** \> **Active users**.</span></span> <span data-ttu-id="fce93-159">Hitta användarkontot i fråga och välj användare (rad) utan att markera kryssrutan.</span><span class="sxs-lookup"><span data-stu-id="fce93-159">Find the user account in question, and select the user (row) without selecting the checkbox.</span></span>

3. <span data-ttu-id="fce93-160">I den information som visas, väljer du fliken **e-post**.</span><span class="sxs-lookup"><span data-stu-id="fce93-160">In the details flyout that appears, select the **Mail** tab.</span></span>

4. <span data-ttu-id="fce93-161">Om värdet i avsnittet **vidarebefordra e-post** **tillämpas**klickar du på **hantera e-postvidarebefordran**.</span><span class="sxs-lookup"><span data-stu-id="fce93-161">If the value in the **Email forwarding** section is **Applied**, click **Manage email forwarding**.</span></span> <span data-ttu-id="fce93-162">I **Hantera e vidarebefordran** flyout som visas klart **vidarebefordra all e-post som skickas till denna brevlåda**, och klicka sedan på **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="fce93-162">In the **Manage email forwarding** flyout that appears, clear **Forward all email sent to this mailbox**, and then click **Save changes**.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="fce93-163">Steg 3 Inaktivera alla misstänkta inkorgsregler</span><span class="sxs-lookup"><span data-stu-id="fce93-163">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="fce93-164">Logga in i användarens postlåda med hjälp av Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="fce93-164">Sign in to the user's mailbox using Outlook on the web.</span></span>

2. <span data-ttu-id="fce93-165">Klicka på kugghjulsikonen och klicka på **E-post**.</span><span class="sxs-lookup"><span data-stu-id="fce93-165">Click on the gear icon and click **Mail**.</span></span>

3. <span data-ttu-id="fce93-166">Klicka på **Regler för inkorgen och rensning** och granska reglerna.</span><span class="sxs-lookup"><span data-stu-id="fce93-166">Click **Inbox and sweep rules** and review the rules.</span></span>

4. <span data-ttu-id="fce93-167">Inaktivera eller ta bort misstänkta regler.</span><span class="sxs-lookup"><span data-stu-id="fce93-167">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="fce93-168">Steg 4 Tillåt att användaren skickar e-post</span><span class="sxs-lookup"><span data-stu-id="fce93-168">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="fce93-169">Om den misstänkt komprometterade postlådan har använts på ett otillåtet sätt för att skicka skräppost, är det sannolikt att postlådan har hindrats från att skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="fce93-169">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>

<span data-ttu-id="fce93-170">Om du vill tillåta att en postlåda skickar e-post igen följer du procedurerna i [Ta bort en användare från portalen med åtkomstbegränsade användare efter att användaren har skickat skräppost](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="fce93-170">To unblock a mailbox from sending mail, follow the procedures in [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="fce93-171">Steg 5 valfritt: Blockera inloggning på användarkontot</span><span class="sxs-lookup"><span data-stu-id="fce93-171">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fce93-172">Du kan blockera inloggning på det misstänkt komprometterade kontot tills du anser att det är säkert att aktivera åtkomst igen.</span><span class="sxs-lookup"><span data-stu-id="fce93-172">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="fce93-173">Öppna Administrationscenter för Microsoft 365 och gå till **användare** \> **aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="fce93-173">Open the Microsoft 365 admin center and go to **Users** \> **Active users**.</span></span>

2. <span data-ttu-id="fce93-174">Hitta och välj användarkontot, klicka på ![More-ikonen](../../media/ITPro-EAC-MoreOptionsIcon.png) och välj sedan **Redigera inloggningsstatus**.</span><span class="sxs-lookup"><span data-stu-id="fce93-174">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Edit sign-in status**.</span></span>

3. <span data-ttu-id="fce93-175">I fönstret **Blockera inloggning** väljer du **Blockera användaren från att logga in**, och klickar sedan på **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="fce93-175">On the **Block sign-in** pane that appears, select **Block this user from signing in**, and then click **Save changes**.</span></span>

4. <span data-ttu-id="fce93-176">Öppna Exchange administrations centret (EAC) på <admin.protection.outlook.com/ecp/> och gå till **Mottagare> Mailboxes**.</span><span class="sxs-lookup"><span data-stu-id="fce93-176">Open the Exchange admin center (EAC) at <admin.protection.outlook.com/ecp/>, and go to **Recipients > Mailboxes**.</span></span>

5. <span data-ttu-id="fce93-177">Hitta och välj markera användaren.</span><span class="sxs-lookup"><span data-stu-id="fce93-177">Find and select the select the user.</span></span> <span data-ttu-id="fce93-178">Gör följande steg i detaljrutan:</span><span class="sxs-lookup"><span data-stu-id="fce93-178">In the details pane, do the following steps:</span></span>

   - <span data-ttu-id="fce93-179">Gör följande steg i avsnittet **Telefon- och röstfunktioner**:</span><span class="sxs-lookup"><span data-stu-id="fce93-179">In the **Phone and voice features** section, do the following steps:</span></span>

     - <span data-ttu-id="fce93-180">Välj **inaktivera Exchange ActiveSync** och klicka sedan på **Ja** i varningen som visas.</span><span class="sxs-lookup"><span data-stu-id="fce93-180">Select **Disable Exchange ActiveSync** and then click **Yes** in the warning that appears.</span></span>
     - <span data-ttu-id="fce93-181">Välj **inaktivera OWA för enheter** och klicka sedan på **Ja** i varningen som visas.</span><span class="sxs-lookup"><span data-stu-id="fce93-181">Select **Disable OWA for Devices** and then click **Yes** in the warning that appears.</span></span>

   - <span data-ttu-id="fce93-182">Gå till avsnittet **e-postanslutning** för Outlook på webben. Klicka på **inaktivera** och klicka sedan på **Ja** i varningen som visas.</span><span class="sxs-lookup"><span data-stu-id="fce93-182">In the **Email Connectivity** section for Outlook on the web, click **Disable** and then click **Yes** in the warning that appears.</span></span>

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="fce93-183">Steg 6 valfritt: Ta bort det misstänkt komprometterade kontot från alla administrativa rollgrupper</span><span class="sxs-lookup"><span data-stu-id="fce93-183">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="fce93-184">Medlemskap i administratörsgruppen kan återställas när kontot har skyddats.</span><span class="sxs-lookup"><span data-stu-id="fce93-184">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="fce93-185">Logga in med ett globalt administratörskonto:</span><span class="sxs-lookup"><span data-stu-id="fce93-185">Sign in with a global administrator account:</span></span>

2. <span data-ttu-id="fce93-186">Gör följande steg i Administrationscenter för Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="fce93-186">In the Microsoft 365 admin center, do the following steps:</span></span>

   1. <span data-ttu-id="fce93-187">Gå till **användare** \> **aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="fce93-187">Go to **Users** \> **Active users**.</span></span>
   2. <span data-ttu-id="fce93-188">Hitta och välj användarkontot, klicka på ![More-ikonen](../../media/ITPro-EAC-MoreOptionsIcon.png) och välj sedan **Hantera roller**.</span><span class="sxs-lookup"><span data-stu-id="fce93-188">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Manage roles**.</span></span>
   3. <span data-ttu-id="fce93-189">Ta bort alla administrativa roller som tilldelas kontot.</span><span class="sxs-lookup"><span data-stu-id="fce93-189">Remove any administrative roles that are assigned to the account.</span></span> <span data-ttu-id="fce93-190">När du är klar klickar du på **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="fce93-190">When you're finished, click **Save changes**.</span></span>

3. <span data-ttu-id="fce93-191">I säkerhets & Compliance Center på <https://protection.office.com>gör du så här:</span><span class="sxs-lookup"><span data-stu-id="fce93-191">In the Security & Compliance Center at <https://protection.office.com>, do the following steps:</span></span>

   <span data-ttu-id="fce93-192">Välj **behörigheter**. Välj varje roll grupp i listan och leta efter användar kontot i **Medlemmar** delen av den information som visas.</span><span class="sxs-lookup"><span data-stu-id="fce93-192">Select **Permissions**, select each role group in the list and look for the user account in the **Members** section of the details flyout that appears.</span></span> <span data-ttu-id="fce93-193">Om rollgruppen innehåller användarkontot gör du följande steg:</span><span class="sxs-lookup"><span data-stu-id="fce93-193">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="fce93-194">a.</span><span class="sxs-lookup"><span data-stu-id="fce93-194">a.</span></span> <span data-ttu-id="fce93-195">Klicka på **redigera** bredvid **medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="fce93-195">Click **Edit** next to **Members**.</span></span>
   <span data-ttu-id="fce93-196">b.</span><span class="sxs-lookup"><span data-stu-id="fce93-196">b.</span></span> <span data-ttu-id="fce93-197">I **redigerar väljer du medlemmar** utfällbar som visas klickar du på **redigera**.</span><span class="sxs-lookup"><span data-stu-id="fce93-197">On the **Editing Choose members** flyout that appears, click **Edit**.</span></span>
   <span data-ttu-id="fce93-198">c.</span><span class="sxs-lookup"><span data-stu-id="fce93-198">c.</span></span> <span data-ttu-id="fce93-199">I **Välj medlemmar** utfällbar som visas väljer du användar konto och klickar sedan på **ta bort**.</span><span class="sxs-lookup"><span data-stu-id="fce93-199">In the **Choose members** flyout that appears, select the user account, and then click **Remove**.</span></span> <span data-ttu-id="fce93-200">När du är klar klickar du på **klar** **Spara**och **sedan**stänga.</span><span class="sxs-lookup"><span data-stu-id="fce93-200">When you're finished, click **Done**, **Save**, and then **Close**.</span></span>

4. <span data-ttu-id="fce93-201">Gör följande steg i EAC på <admin.protection.outlook.com/ecp/>:</span><span class="sxs-lookup"><span data-stu-id="fce93-201">In the EAC at <admin.protection.outlook.com/ecp/>, do the following steps:</span></span>

   <span data-ttu-id="fce93-202">Välj **behörigheter**, markera varje roll grupp manuellt och kontrol lera sedan användar kontona i avsnittet **medlemmar** i informations fönstret.</span><span class="sxs-lookup"><span data-stu-id="fce93-202">Select **Permissions**, manually select each role group, and in the details pane, verify the user accounts in the **Members** section.</span></span>  <span data-ttu-id="fce93-203">Om rollgruppen innehåller användarkontot gör du följande steg:</span><span class="sxs-lookup"><span data-stu-id="fce93-203">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="fce93-204">a.</span><span class="sxs-lookup"><span data-stu-id="fce93-204">a.</span></span> <span data-ttu-id="fce93-205">Välj roll gruppen och klicka på **redigera** ![redigera ikonen](../../media/ITPro-EAC-EditIcon.png).</span><span class="sxs-lookup"><span data-stu-id="fce93-205">Select the role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>
   <span data-ttu-id="fce93-206">b.</span><span class="sxs-lookup"><span data-stu-id="fce93-206">b.</span></span> <span data-ttu-id="fce93-207">Gå till avsnittet **medlem**, Välj användar kontot och klicka sedan på **ta bort** ![ta bort ikonen](../../media/ITPro-EAC-RemoveIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="fce93-207">In the **Member** section, select the user account, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span> <span data-ttu-id="fce93-208">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="fce93-208">When you're finished, click **Save**.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="fce93-209">Steg 7 Valfritt: Ytterligare försiktighetsåtgärder</span><span class="sxs-lookup"><span data-stu-id="fce93-209">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="fce93-210">Var noga med att verifiera dina skickade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="fce93-210">Make sure that you verify your sent items.</span></span> <span data-ttu-id="fce93-211">Du kanske måste meddela personer i din kontaktlista att ditt konto har komprometterats.</span><span class="sxs-lookup"><span data-stu-id="fce93-211">You may have to inform people on your contacts list that your account was compromised.</span></span> <span data-ttu-id="fce93-212">Angriparen kan ha bett om att få pengar genom så kallad förfalskning, t.ex. att du var fast i ett annat land och behövde pengar, eller så kan angriparen ha skickat ett virus för att kapa deras datorer.</span><span class="sxs-lookup"><span data-stu-id="fce93-212">The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>

2. <span data-ttu-id="fce93-213">Andra tjänster som har använt Exchange-kontot som ett alternativt e-postkonto kan ha komprometterats.</span><span class="sxs-lookup"><span data-stu-id="fce93-213">Any other service that used this Exchange account as its alternative email account may have been compromised.</span></span> <span data-ttu-id="fce93-214">Utför först de här stegen för din Microsoft 365-prenumeration och därefter för dina övriga konton.</span><span class="sxs-lookup"><span data-stu-id="fce93-214">First, perform these steps for your Microsoft 365 subscription, and then perform these steps for your other accounts.</span></span>

3. <span data-ttu-id="fce93-215">Kontrollera att din kontaktinformation, t. ex. telefonnummer och adresser, är korrekt.</span><span class="sxs-lookup"><span data-stu-id="fce93-215">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="fce93-216">Skydda Microsoft 365 som en expert på cybersäkerhet</span><span class="sxs-lookup"><span data-stu-id="fce93-216">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="fce93-217">Din Microsoft 365-prenumeration innehåller kraftfulla säkerhetsfunktioner som du kan använda för att skydda dina data och dina användare.</span><span class="sxs-lookup"><span data-stu-id="fce93-217">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="fce93-218">Använd [Säkerhetsöversikt för Microsoft 365 – de vanligaste prioriteringarna för de första 30 dagarna, 90 dagarna och bortom](security-roadmap.md) för att implementera Microsofts metodtips för att skydda din Microsoft 365-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="fce93-218">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="fce93-219">Uppgifter som ska utföras under de första 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="fce93-219">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="fce93-220">De har omedelbar effekt och påverkar inte användarna i någon större utsträckning.</span><span class="sxs-lookup"><span data-stu-id="fce93-220">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="fce93-221">Uppgifter som ska utföras inom 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="fce93-221">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="fce93-222">De tar lite längre tid att planera och implementera men förbättrar din säkerhet avsevärt.</span><span class="sxs-lookup"><span data-stu-id="fce93-222">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="fce93-223">Efter 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="fce93-223">Beyond 90 days.</span></span> <span data-ttu-id="fce93-224">De här förbättringarna uppnås under de första 90 dagarna.</span><span class="sxs-lookup"><span data-stu-id="fce93-224">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="fce93-225">Se även</span><span class="sxs-lookup"><span data-stu-id="fce93-225">See also</span></span>

- [<span data-ttu-id="fce93-226">Identifiera och reparera Outlook-regler och inmatningsattacker i anpassade formulär i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fce93-226">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Microsoft 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

- [<span data-ttu-id="fce93-227">Klagomålscenter för brottslighet på Internet</span><span class="sxs-lookup"><span data-stu-id="fce93-227">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/preventiontips.aspx)

- [<span data-ttu-id="fce93-228">Tillsynsmyndigheten för värdepapper – Bedrägerier genom nätfiske</span><span class="sxs-lookup"><span data-stu-id="fce93-228">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)

- <span data-ttu-id="fce93-229">Om du vill rapportera skräppost direkt till Microsoft och din administratör [använder du tillägget Rapportera meddelande](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="fce93-229">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>
