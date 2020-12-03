---
title: Lägga till DNS-poster för att ansluta till din domän
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
description: Lär dig verifiera din domän och skapa DNS-poster på vilken DNS-värd som helst för Microsoft 365.
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: bc22dbd3a050516f518c9ddc9ccf5a3af9c76f12
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519299"
---
# <a name="add-dns-records-to-connect-your-domain"></a><span data-ttu-id="2c6f7-103">Lägga till DNS-poster för att ansluta till din domän</span><span class="sxs-lookup"><span data-stu-id="2c6f7-103">Add DNS records to connect your domain</span></span>

<span data-ttu-id="2c6f7-104">Om du har köpt en domän från en tredjeparts värd kan du ansluta den till Microsoft 365 genom att uppdatera DNS-posterna i ditt registratorskonto.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-104">If you purchased a domain from a third-party hosting provider, you can connect it to Microsoft 365 by updating the DNS records in your registrar’s account.</span></span>

<span data-ttu-id="2c6f7-105">När du har slutfört de här anvisningarna förblir din domän registrerad hos den värd som du köpte domänen från, men Microsoft 365 kan använda den för e-postadresser (till exempel user@yourdomain.com) och andra tjänster.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-105">At the end of these steps, your domain will stay registered with the host that you purchased the domain from, but Microsoft 365 can use it for your email addresses (like user@yourdomain.com) and other services.</span></span>

<span data-ttu-id="2c6f7-106">Om du inte lägger till en domän kommer personer i din organisation att använda domänen onmicrosoft.com för sina e-postadresser tills du gör det.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-106">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="2c6f7-107">Det är viktigt att lägga till domänen innan du lägger till användare, så att du inte behöver konfigurera dem två gånger.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-107">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="2c6f7-108">[Läs frågor och svar om domäner](../setup/domains-faq.md) om du inte hittar det du letar efter nedan.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-108">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for below.</span></span>

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a><span data-ttu-id="2c6f7-109">Steg 1: Lägga till en TXT eller MX-post för att verifiera att det är din domän</span><span class="sxs-lookup"><span data-stu-id="2c6f7-109">Step 1: Add a TXT or MX record to verify you own the domain</span></span>

### <a name="recommended-verify-with-a-txt-record"></a><span data-ttu-id="2c6f7-110">Rekommenderas: Verifiera med en TXT-post</span><span class="sxs-lookup"><span data-stu-id="2c6f7-110">Recommended: Verify with a TXT record</span></span>

<span data-ttu-id="2c6f7-111">Först måste du bevisa att du äger den domän som du vill lägga till i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-111">First, you need to prove you own the domain you want to add to Microsoft 365.</span></span>

1. <span data-ttu-id="2c6f7-112">Logga in på [Administrationscenter för Microsoft 365](https://admin.microsoft.com/) och välj **Visa alla** > **Inställningar** > **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-112">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="2c6f7-113">Logga in på din DNS-värdtjänst i en ny flik i webbläsaren eller i en ny webbläsare och leta sedan reda på hur du hanterar dina DNS-inställningar (t. ex. inställningar för zonfiler, hantera domäner, domänhanteraren, DNS-hanteraren).</span><span class="sxs-lookup"><span data-stu-id="2c6f7-113">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="2c6f7-114">Gå till din leverantörs DNS-hanterare och lägga till den TXT-post som anges i administrationscentret för din domän.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-114">Go to your provider's DNS Manager page, and add the TXT record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="2c6f7-115">Om du lägger till den här posten påverkas inte din befintliga e-post och andra tjänster, och du kan ta bort den när domänen är ansluten till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-115">Adding this record won't affect your existing email or other services and you can safely remove it once your domain is connected to Microsoft 365.</span></span>

<span data-ttu-id="2c6f7-116">Exempel:</span><span class="sxs-lookup"><span data-stu-id="2c6f7-116">Example:</span></span>
- <span data-ttu-id="2c6f7-117">TXT-namn: `@`</span><span class="sxs-lookup"><span data-stu-id="2c6f7-117">TXT Name: `@`</span></span>
- <span data-ttu-id="2c6f7-118">TXT-värde: MS = MS # # # # # # # # (unikt ID från administrationscentret)</span><span class="sxs-lookup"><span data-stu-id="2c6f7-118">TXT Value: MS=ms######## (unique ID from the admin center)</span></span>
- <span data-ttu-id="2c6f7-119">TTL: `3600‎` (eller din leverantörs standard)</span><span class="sxs-lookup"><span data-stu-id="2c6f7-119">TTL: `3600‎` (or your provider default)</span></span>

4. <span data-ttu-id="2c6f7-120">Spara posten, gå tillbaka till administrationscentret och välj **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-120">Save the record, go back to the admin center, and then select **Verify**.</span></span> <span data-ttu-id="2c6f7-121">Det tar normalt cirka 15 minuter innan ändringarna registreras, men ibland kan det ta längre tid.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-121">It typically takes around 15 minutes for record changes to register, but sometimes it can take longer.</span></span> <span data-ttu-id="2c6f7-122">Ge det lite tid och några försök att fånga förändringen.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-122">Give it some time and a few tries to pick up the change.</span></span>

<span data-ttu-id="2c6f7-123">När Microsoft hittar rätt TXT-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-123">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

### <a name="verify-with-an-mx-record"></a><span data-ttu-id="2c6f7-124">Verifiera med en MX-post</span><span class="sxs-lookup"><span data-stu-id="2c6f7-124">Verify with an MX record</span></span>

<span data-ttu-id="2c6f7-125">Om din domänregistrator inte har stöd för att lägga till TXT-poster kan du verifiera genom att lägga till en MX-post.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-125">If your registrar doesn't support adding TXT records, you can verify by adding an MX record.</span></span>

1. <span data-ttu-id="2c6f7-126">Logga in på [Administrationscenter för Microsoft 365](https://admin.microsoft.com/) och välj **Visa alla** > **Inställningar** > **Domäner**.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-126">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="2c6f7-127">Logga in på din DNS-värdtjänst i en ny flik i webbläsaren eller i en ny webbläsare och leta sedan reda på hur du hanterar dina DNS-inställningar (t. ex. inställningar för zonfiler, hantera domäner, domänhanteraren, DNS-hanteraren).</span><span class="sxs-lookup"><span data-stu-id="2c6f7-127">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="2c6f7-128">Gå till din leverantörs DNS-hanterare och lägga till den MX-post som anges i administrationscentret för din domän.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-128">Go to your provider's DNS Manager page, and add the MX record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="2c6f7-129">MX-postens **Prioritet** måste vara den högsta av alla befintliga MX-poster för domänen.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-129">This MX record's **Priority** must be the highest of all existing MX records for the domain.</span></span> <span data-ttu-id="2c6f7-130">Annars kan det störa sändning och mottagning av e-post.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-130">Otherwise, it can interfere with sending and receiving email.</span></span> <span data-ttu-id="2c6f7-131">Du bör ta bort de här posterna när domänverifieringen är slutförd.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-131">You should delete this records as soon as domain verification is complete.</span></span>

<span data-ttu-id="2c6f7-132">Kontrollera att fälten är inställda på följande värden:</span><span class="sxs-lookup"><span data-stu-id="2c6f7-132">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="2c6f7-133">Posttyp: `MX`</span><span class="sxs-lookup"><span data-stu-id="2c6f7-133">Record Type: `MX`</span></span>
- <span data-ttu-id="2c6f7-134">Prioritet: Ange det högsta värdet, vanligtvis `0`.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-134">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="2c6f7-135">Värdnamn: `@`</span><span class="sxs-lookup"><span data-stu-id="2c6f7-135">Host Name: `@`</span></span>
- <span data-ttu-id="2c6f7-136">Pekar på adress: Kopiera värdet från administrationscentret och klistra in det här.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-136">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="2c6f7-137">TTL: `3600‎` (eller din leverantörs standard)</span><span class="sxs-lookup"><span data-stu-id="2c6f7-137">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="2c6f7-138">När Microsoft hittar rätt MX-post är din domän verifierad.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-138">When Microsoft finds the correct MX record, your domain is verified.</span></span>

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a><span data-ttu-id="2c6f7-139">Steg 2: Lägga till DNS-poster för att ansluta till Microsoft-tjänster</span><span class="sxs-lookup"><span data-stu-id="2c6f7-139">Step 2: Add DNS records to connect Microsoft services</span></span>

<span data-ttu-id="2c6f7-140">Logga in på din DNS-värdtjänst i en ny flik i webbläsaren eller i en ny webbläsare och leta reda på hur du hanterar dina DNS-inställningar (t. ex. inställningar för zonfiler, hantera domäner, domänhanteraren, DNS-hanteraren).</span><span class="sxs-lookup"><span data-stu-id="2c6f7-140">In a new browser tab or window, sign in to your DNS hosting provider, and find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>

<span data-ttu-id="2c6f7-141">Du kan lägga till flera olika typer av DNS-poster beroende på vilka tjänster du vill aktivera.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-141">You'll be adding several different types of DNS records depending on the services you want to enable.</span></span> 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a><span data-ttu-id="2c6f7-142">Lägga till en MX-post för e-post (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="2c6f7-142">Add an MX record for email (Outlook, Exchange Online)</span></span>
<span data-ttu-id="2c6f7-143">**Innan du börjar**: om användarna redan har ett e-postmeddelande med din domän (t. ex. user@yourdomain.com), skapar du kontona i administrationscentret innan du konfigurerar dina MX-poster.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-143">**Before you begin:** If users already have email with your domain (such as user@yourdomain.com), create their accounts in the admin center before you set up your MX records.</span></span> <span data-ttu-id="2c6f7-144">På så sätt fortsätter de att få e-post.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-144">That way, they’ll continue to receive email.</span></span> <span data-ttu-id="2c6f7-145">När du uppdaterar domänens MX-post kommer nu alla nya e-postmeddelanden till alla som använder din domän till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-145">When you update your domain's MX record, all new email for anyone who uses your domain will now come to Microsoft 365.</span></span> <span data-ttu-id="2c6f7-146">E-postmeddelanden som du redan har finns kvar hos din nuvarande e-postvärd, om du inte bestämmer dig för att [migrera e-postmeddelanden och kontakter till Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)</span><span class="sxs-lookup"><span data-stu-id="2c6f7-146">Any email you already have will stay at your current email host, unless you decide to [migrate email and contacts to Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)</span></span>

<span data-ttu-id="2c6f7-147">Du får information om MX-posten från administrationscentrets konfigurationsguide.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-147">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="2c6f7-148">Lägg till en ny MX-post på värdens webbplats.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-148">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="2c6f7-149">Kontrollera att fälten är inställda på följande värden:</span><span class="sxs-lookup"><span data-stu-id="2c6f7-149">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="2c6f7-150">Posttyp: `MX`</span><span class="sxs-lookup"><span data-stu-id="2c6f7-150">Record Type: `MX`</span></span>
- <span data-ttu-id="2c6f7-151">Prioritet: Ange det högsta värdet, vanligtvis `0`.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-151">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="2c6f7-152">Värdnamn: `@`</span><span class="sxs-lookup"><span data-stu-id="2c6f7-152">Host Name: `@`</span></span>
- <span data-ttu-id="2c6f7-153">Pekar på adress: Kopiera värdet från administrationscentret och klistra in det här.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-153">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="2c6f7-154">TTL: `3600‎` (eller din leverantörs standard)</span><span class="sxs-lookup"><span data-stu-id="2c6f7-154">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="2c6f7-155">Spara posten och ta bort eventuella andra MX-poster.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-155">Save the record, and then remove any other MX records.</span></span>

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a><span data-ttu-id="2c6f7-156">Lägga till CNAME-poster för att ansluta till andra tjänster (Teams, Exchange Online, AAD, MDM)</span><span class="sxs-lookup"><span data-stu-id="2c6f7-156">Add CNAME records to connect other services (Teams, Exchange Online, AAD, MDM)</span></span>
<span data-ttu-id="2c6f7-157">Du får information om CNAME-posterna från administrationscentrets konfigurationsguide.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-157">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="2c6f7-158">Lägg till CNAME-poster för varje tjänst du vill ansluta på värdens webbplats.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-158">On your hosting provider's website, add CNAME records for each service that you want to connect.</span></span>
<span data-ttu-id="2c6f7-159">Kontrollera att fälten är inställda på följande värden för varje:</span><span class="sxs-lookup"><span data-stu-id="2c6f7-159">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="2c6f7-160">Posttyp: `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="2c6f7-160">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="2c6f7-161">Värd: Klistra in värdena som du kopierar från administrationscentret här.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-161">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="2c6f7-162">Pekar på adress: Kopiera värdet från administrationscentret och klistra in det här.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-162">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="2c6f7-163">TTL: `3600‎` (eller din leverantörs standard)</span><span class="sxs-lookup"><span data-stu-id="2c6f7-163">TTL: `3600‎` (or your provider default)</span></span>


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a><span data-ttu-id="2c6f7-164">Lägga till eller redigera en SPF TXT-post för att förhindra skräppost i e-post (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="2c6f7-164">Add or edit an SPF TXT record to help prevent email spam (Outlook, Exchange Online)</span></span>
<span data-ttu-id="2c6f7-165">**Innan du börjar:** Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-165">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="2c6f7-166">Lägg istället till de obligatoriska Microsoft 365-värdena i den aktuella posten på din värds webbplats så att du har en *enda* SPF-post som innehåller båda uppsättningarna med värden.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-166">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="2c6f7-167">Redigera den befintliga SPF-posten eller skapa en SPF-post på värdens webbplats.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-167">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="2c6f7-168">Kontrollera att fälten är inställda på följande värden:</span><span class="sxs-lookup"><span data-stu-id="2c6f7-168">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="2c6f7-169">Posttyp: `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="2c6f7-169">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="2c6f7-170">Värd: `@`</span><span class="sxs-lookup"><span data-stu-id="2c6f7-170">Host: `@`</span></span>
- <span data-ttu-id="2c6f7-171">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="2c6f7-171">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="2c6f7-172">TTL: `3600‎` (eller din leverantörs standard)</span><span class="sxs-lookup"><span data-stu-id="2c6f7-172">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="2c6f7-173">Spara posten.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-173">Save the record.</span></span>

<span data-ttu-id="2c6f7-174">Använd något av följande [SPF-verifieringsverktyg](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) för att verifiera SPF-posten</span><span class="sxs-lookup"><span data-stu-id="2c6f7-174">Validate your SPF record by using one of these [SPF validation tools](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="2c6f7-175">SPF har utformats för att hjälpa till att förhindra förfalskning men det finns förfalskningsmetoder som SPF inte skyddar mot.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-175">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="2c6f7-176">För att skydda mot dessa ska du, efter att ha konfigurerat SPF, även konfigurera DKIM och DMARC för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-176">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span> 

<span data-ttu-id="2c6f7-177">Information om hur du kommer igång finns i [Använda DKIM för att validera utgående e-post som skickas från din domän i Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) och [Använda DMARC för att validera e-post i Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="2c6f7-177">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) and [Use DMARC to validate email in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a><span data-ttu-id="2c6f7-178">Lägga till SRV-poster för kommunikationstjänster (Teams, Skype för företag)</span><span class="sxs-lookup"><span data-stu-id="2c6f7-178">Add SRV records for communications services (Teams, Skype for Business)</span></span>

<span data-ttu-id="2c6f7-179">Lägg till SRV-poster för varje tjänst du vill ansluta på värdens webbplats.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-179">On your hosting provider's website, add SRV records for each service you want to connect.</span></span>
<span data-ttu-id="2c6f7-180">Kontrollera att fälten är inställda på följande värden för varje:</span><span class="sxs-lookup"><span data-stu-id="2c6f7-180">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="2c6f7-181">Posttyp: `SRV (Service)`</span><span class="sxs-lookup"><span data-stu-id="2c6f7-181">Record Type: `SRV (Service)`</span></span>
- <span data-ttu-id="2c6f7-182">Namn: `@`</span><span class="sxs-lookup"><span data-stu-id="2c6f7-182">Name: `@`</span></span>
- <span data-ttu-id="2c6f7-183">Mål: Kopiera värdet från administrationscentret och klistra in det här.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-183">Target: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="2c6f7-184">Protokoll: Kopiera värdet från administrationscentret och klistra in det här.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-184">Protocol: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="2c6f7-185">Tjänst: Kopiera värdet från administrationscentret och klistra in det här.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-185">Service: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="2c6f7-186">Prioritet: `100`</span><span class="sxs-lookup"><span data-stu-id="2c6f7-186">Priority: `100`</span></span>
- <span data-ttu-id="2c6f7-187">Vikt: `1`</span><span class="sxs-lookup"><span data-stu-id="2c6f7-187">Weight: `1`</span></span>
- <span data-ttu-id="2c6f7-188">Port: Kopiera värdet från administrationscentret och klistra in det här.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-188">Port: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="2c6f7-189">TTL: `3600‎` (eller din leverantörs standard)</span><span class="sxs-lookup"><span data-stu-id="2c6f7-189">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="2c6f7-190">Spara posten.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-190">Save the record.</span></span>

#### <a name="srv-record-field-restrictions-and-workarounds"></a><span data-ttu-id="2c6f7-191">Restriktioner och lösningar för SRV-postfält</span><span class="sxs-lookup"><span data-stu-id="2c6f7-191">SRV record field restrictions and workarounds</span></span>
<span data-ttu-id="2c6f7-192">Vissa värdar har restriktioner för fältvärden i SRV-poster.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-192">Some hosting providers impose restrictions on field values within SRV records.</span></span> <span data-ttu-id="2c6f7-193">Här är några vanliga lösningar på de här begränsningarna.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-193">Here are some common workarounds for these restrictions.</span></span>

##### <a name="name"></a><span data-ttu-id="2c6f7-194">Namn</span><span class="sxs-lookup"><span data-stu-id="2c6f7-194">Name</span></span>
<span data-ttu-id="2c6f7-195">Om din värd inte tillåter att fältet anges till **@**, lämnar du det tomt.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-195">If your hosting provider doesn't allow setting this field to **@**, leave it blank.</span></span> <span data-ttu-id="2c6f7-196">Använd den här metoden *bara* när din värd har separata fält för värdena Tjänst och Protokoll.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-196">Use this approach *only* when your hosting provider has separate fields for the Service and Protocol values.</span></span> <span data-ttu-id="2c6f7-197">Se annars anteckningarna om Tjänst och Protokoll nedan.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-197">Otherwise, see the Service and Protocol notes below.</span></span>

##### <a name="service-and-protocol"></a><span data-ttu-id="2c6f7-198">Tjänst och protokoll</span><span class="sxs-lookup"><span data-stu-id="2c6f7-198">Service and Protocol</span></span>
<span data-ttu-id="2c6f7-199">Om värden inte tillhandahåller dessa fält för SRV-poster måste du ange värdena för **Tjänst-** och **Protokollvärden** i postens **Namn**.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-199">If your hosting provider doesn't provide these fields for SRV records, you must specify the **Service** and **Protocol** values in the record's **Name** field.</span></span> <span data-ttu-id="2c6f7-200">(Obs! Beroende på värden kan fältet **Namn** heta något annat, t.ex. **Värd**, **Värdnamn** eller **Underdomän**.) För att lägga till värdet skapar du en enskild sträng och separerar värdena med en punkt.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-200">(Note: Depending on your hosting provider, the **Name** field might be called something else, like: **Host**, **Hostname**, or **Subdomain**.) To add these values, you create a single string, separating the values with a dot.</span></span> 

<span data-ttu-id="2c6f7-201">Exempel: `_sip._tls`</span><span class="sxs-lookup"><span data-stu-id="2c6f7-201">Example: `_sip._tls`</span></span>

##### <a name="priority-weight-and-port-br"></a><span data-ttu-id="2c6f7-202">Prioritet, vikt och port</span><span class="sxs-lookup"><span data-stu-id="2c6f7-202">Priority, Weight, and Port</span></span> <br>
<span data-ttu-id="2c6f7-203">Om värden inte tillhandahåller dessa fält för SRV-poster måste du ange värdena för postens **Målfält**.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-203">If your hosting provider doesn't provide these fields for SRV records, you must specify them in the record's **Target** field.</span></span> <span data-ttu-id="2c6f7-204">(Obs! beroende på din värd kan **Målfältet** kallas för något annat, t. ex.: **Innehåll**, **IP-adress** eller **Målvärd**.)</span><span class="sxs-lookup"><span data-stu-id="2c6f7-204">(Note: Depending on your hosting provider, the **Target** field might be called something else, like: **Content**, **IP Address**, or **Target Host**.)</span></span> 

<span data-ttu-id="2c6f7-205">Om du vill lägga till de här värdena skapar du en sträng som avgränsar värdena med blanksteg och *ibland slutar med en punkt* (kontrollera med din leverantör om du är osäker).</span><span class="sxs-lookup"><span data-stu-id="2c6f7-205">To add these values, create a single string, separating the values with spaces and *sometimes ending with a dot* (check with your provider if you are unsure).</span></span> <span data-ttu-id="2c6f7-206">Värdena måste tas med i följande ordning: Prioritet, Vikt, Port, Mål.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-206">The values must be included in this order: Priority, Weight, Port, Target.</span></span> 

- <span data-ttu-id="2c6f7-207">Exempel 1: `100 1 443 sipdir.online.lync.com.`</span><span class="sxs-lookup"><span data-stu-id="2c6f7-207">Example 1: `100 1 443 sipdir.online.lync.com.`</span></span>
- <span data-ttu-id="2c6f7-208">Exempe 2l: `100 1 443 sipdir.online.lync.com`</span><span class="sxs-lookup"><span data-stu-id="2c6f7-208">Example 2: `100 1 443 sipdir.online.lync.com`</span></span>
