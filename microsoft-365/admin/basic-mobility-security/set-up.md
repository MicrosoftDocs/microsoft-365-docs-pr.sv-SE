---
title: Konfigurera grundläggande mobilitet och säkerhet
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Konfigurera grundläggande mobilitet och säkerhet för att skydda och hantera användares mobila enheter.
ms.openlocfilehash: cb010668d95e51edfbc913caa308ddd830d674e2
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430322"
---
# <a name="set-up-basic-mobility-and-security"></a><span data-ttu-id="34007-103">Konfigurera grundläggande mobilitet och säkerhet</span><span class="sxs-lookup"><span data-stu-id="34007-103">Set up Basic Mobility and Security</span></span>

<span data-ttu-id="34007-104">Den inbyggda grundläggande mobilitet och säkerhet för Microsoft 365 hjälper dig att skydda och hantera användares mobila enheter som iPhone, iPad, Android och Windows-telefoner.</span><span class="sxs-lookup"><span data-stu-id="34007-104">The built-in Basic Mobility and Security for Microsoft 365 helps you secure and manage users' mobile devices such as iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="34007-105">Du kan skapa och hantera säkerhets principer för enheter, rensa en enhet och se detaljerade enhets rapporter.</span><span class="sxs-lookup"><span data-stu-id="34007-105">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

<span data-ttu-id="34007-106">Har du några frågor?</span><span class="sxs-lookup"><span data-stu-id="34007-106">Have questions?</span></span> <span data-ttu-id="34007-107">Vanliga frågor och svar om vanliga frågor [och](frequently-asked-questions.md)svar om frågor finns här.</span><span class="sxs-lookup"><span data-stu-id="34007-107">For a FAQ to help address common questions, see [Basic Mobility and Security Frequently-asked questions (FAQ)](frequently-asked-questions.md).</span></span> <span data-ttu-id="34007-108">Observera att du inte kan använda ett delegerat administratörs konto för att hantera grundläggande mobilitet och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="34007-108">Be aware that you cannot use a delegated administrator account to manage Basic Mobility and Security.</span></span> <span data-ttu-id="34007-109">Mer information finns i [partners: tillhandahålla delegerad administration](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e).</span><span class="sxs-lookup"><span data-stu-id="34007-109">For more info, see [Partners: Offer delegated administration](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e).</span></span> 

<span data-ttu-id="34007-110">Enhets hantering är en del av säkerhets & Compliance Center så du måste gå dit för att starta MDM-installationen.</span><span class="sxs-lookup"><span data-stu-id="34007-110">Device management is part of the Security & Compliance Center so you'll need to go there to kick off MDM setup.</span></span>

## <a name="activate-the-basic-mobility-and-security-service"></a><span data-ttu-id="34007-111">Aktivera den grundläggande mobilitets-och säkerhets tjänsten</span><span class="sxs-lookup"><span data-stu-id="34007-111">Activate the Basic Mobility and Security service</span></span>

1. <span data-ttu-id="34007-112">Logga in på Microsoft 365 med ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="34007-112">Sign in to Microsoft 365 with your global admin account.</span></span>
    

2. <span data-ttu-id="34007-113">Gå till [aktivera grundläggande mobilitet och säkerhet](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span><span class="sxs-lookup"><span data-stu-id="34007-113">Go to [Activate Basic Mobility and Security](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span>
    
    <span data-ttu-id="34007-114">Det kan ta lite tid att aktivera grundläggande mobilitet och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="34007-114">It can take some time to activate Basic Mobility and Security.</span></span> <span data-ttu-id="34007-115">När det är klart får du ett e-postmeddelande som förklarar nästa steg.</span><span class="sxs-lookup"><span data-stu-id="34007-115">When it finishes, you'll receive an email that explains the next steps to take.</span></span>

## <a name="set-up-mobile-device-management"></a><span data-ttu-id="34007-116">Konfigurera hantering av mobila enheter</span><span class="sxs-lookup"><span data-stu-id="34007-116">Set up Mobile Device Management</span></span>

<span data-ttu-id="34007-117">När tjänsten är klar följer du anvisningarna nedan för att slutföra konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="34007-117">When the service is ready, complete the following steps to finish setup.</span></span>

### <a name="step-1-required-configure-domains-for-mdm"></a><span data-ttu-id="34007-118">Steg 1: (obligatoriskt) konfigurera domäner för MDM</span><span class="sxs-lookup"><span data-stu-id="34007-118">Step 1: (Required) Configure domains for MDM</span></span>

<span data-ttu-id="34007-119">Om du inte har en egen domän kopplad till Microsoft 365 eller om du inte hanterar Windows-enheter kan du hoppa över det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="34007-119">If you don't have a custom domain associated with Microsoft 365 or if you're not managing Windows devices, you can skip this section.</span></span> <span data-ttu-id="34007-120">Annars måste du lägga till DNS-poster för domänen hos DNS-värden.</span><span class="sxs-lookup"><span data-stu-id="34007-120">Otherwise, you'll need to add DNS records for the domain at your DNS host.</span></span> <span data-ttu-id="34007-121">Om du har lagt till posterna som du redan har gjort, är du redo att konfigurera din domän med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34007-121">If you've added the records already, as part of setting up your domain with Microsoft 365, you're all set.</span></span> <span data-ttu-id="34007-122">När du har lagt till posterna omdirigeras de Microsoft 365-användare i organisationen som loggar in på sin Windows-enhet med en e-postadress som använder din egen domän för att registrera dig för grundläggande mobilitet och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="34007-122">After you add the records, Microsoft 365 users in your organization who sign in on their Windows device with an email address that uses your custom domain are redirected to enroll in Basic Mobility and Security.</span></span>

<span data-ttu-id="34007-123">Behöver du hjälp med att konfigurera posterna?</span><span class="sxs-lookup"><span data-stu-id="34007-123">Need help setting up the records?</span></span> <span data-ttu-id="34007-124">Hitta din domän registrator och välj registratorns namn för att gå till steg-för-steg-hjälp för att skapa DNS-poster i listan i [Lägg till DNS-poster för att ansluta din domän](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span><span class="sxs-lookup"><span data-stu-id="34007-124">Find your domain registrar and select the registrar name to go to step-by-step help for creating DNS record in the list provided in [Add DNS records to connect your domain](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span> <span data-ttu-id="34007-125">Använd dessa instruktioner för att skapa CNAME-poster som beskrivs i [förenkla Windows-registrering utan Azure AD Premium](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium).</span><span class="sxs-lookup"><span data-stu-id="34007-125">Use those instructions to create CNAME records described in [Simplify Windows enrollment without Azure AD Premium](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium).</span></span>

<span data-ttu-id="34007-126">När du har lagt till de två CNAME-posterna kan du gå tillbaka till sidan säkerhets & efterlevnad och gå till hantering av **data förlust**  >  **Device management**   för att slutföra nästa steg.</span><span class="sxs-lookup"><span data-stu-id="34007-126">After you add the two CNAME records, go back to the Security & Compliance Center and go to **Data loss prevention** > **Device management** to complete the next step.</span></span>

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="34007-127">Steg 2: (obligatoriskt) Konfigurera ett APN-certifikat för iOS-enheter</span><span class="sxs-lookup"><span data-stu-id="34007-127">Step 2: (Required) Configure an APNs Certificate for iOS devices</span></span>

<span data-ttu-id="34007-128">För att hantera iOS-enheter som iPad och iPhone måste du skapa ett APN-certifikat.</span><span class="sxs-lookup"><span data-stu-id="34007-128">To manage iOS devices like iPad and iPhones, you need to create an APNs certificate.</span></span>

1. <span data-ttu-id="34007-129">Logga in på Microsoft 365 med ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="34007-129">Sign in to  Microsoft 365 with your global admin account.</span></span>   

2. <span data-ttu-id="34007-130">I webbläsaren:  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="34007-130">In your browser type: [https://protection.office.com](https://protection.office.com/).</span></span>  

3. <span data-ttu-id="34007-131">Välj **Hantera data förlust**   >  **Device management**och välj **APNs-certifikat för iOS-enheter**.</span><span class="sxs-lookup"><span data-stu-id="34007-131">Select **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>   

4. <span data-ttu-id="34007-132">På sidan Inställningar för Apple Push Notification-certifikat väljer du **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="34007-132">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>  

5. <span data-ttu-id="34007-133">Välj **Ladda ned din CSR-fil**   och spara begäran om certifikat signering någonstans på din dator som du kommer ihåg.</span><span class="sxs-lookup"><span data-stu-id="34007-133">Select **Download your CSR file** and save the Certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="34007-134">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="34007-134">Select **Next**.</span></span>
    
6. <span data-ttu-id="34007-135">På sidan Skapa ett APN-certifikat:</span><span class="sxs-lookup"><span data-stu-id="34007-135">On the Create an APNs certificate page:</span></span>
    
    - <span data-ttu-id="34007-136">Välj Apple-APN-portalen för att öppna Apple Push certificates-portalen.</span><span class="sxs-lookup"><span data-stu-id="34007-136">Select Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>
    - <span data-ttu-id="34007-137">Logga in med ett Apple-ID.</span><span class="sxs-lookup"><span data-stu-id="34007-137">Sign in with an Apple ID.</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="34007-138">Använd ett Apple-ID för företag som är kopplat till ett e-postkonto som kommer att fortsätta med din organisation även om den användare som hanterar kontot lämnar.</span><span class="sxs-lookup"><span data-stu-id="34007-138">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves.</span></span> <span data-ttu-id="34007-139">Spara detta ID eftersom du måste använda samma ID när det är dags att förnya certifikatet.</span><span class="sxs-lookup"><span data-stu-id="34007-139">Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    - <span data-ttu-id="34007-140">Välj Skapa ett certifikat och godkänn användnings villkoren.</span><span class="sxs-lookup"><span data-stu-id="34007-140">Select Create a Certificate and accept the Terms of Use.</span></span>
    
    - <span data-ttu-id="34007-141">Browseto som du laddat ner till din dator från Microsoft 365 och selectUpload.</span><span class="sxs-lookup"><span data-stu-id="34007-141">Browseto the Certificate signing request you downloaded to your computer from Microsoft 365 and selectUpload.</span></span>
    
    - <span data-ttu-id="34007-142">Downloadthe APN-certifikat skapat av Apple Push Certificate-portalen till din dator.</span><span class="sxs-lookup"><span data-stu-id="34007-142">Downloadthe APN certificate created by the Apple Push Certificate Portal to your computer.</span></span>

    >[!TIP]
    ><span data-ttu-id="34007-143">Om du har problem med att ladda ner certifikatet kan du uppdatera webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="34007-143">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="34007-144">Gå tillbaka till Microsoft 365 och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="34007-144">Go back to Microsoft 365 and select **Next**.</span></span>   

8. <span data-ttu-id="34007-145">Bläddra till det APN-certifikat som du laddade ned från Apple Push certificates-portalen.</span><span class="sxs-lookup"><span data-stu-id="34007-145">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>   

9. <span data-ttu-id="34007-146">Välj  **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="34007-146">Select  **Finish**.</span></span>  

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a><span data-ttu-id="34007-147">Steg 3: (rekommenderas) Konfigurera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="34007-147">Step 3: (Recommended) Set up multi-factor authentication</span></span>

<span data-ttu-id="34007-148">MFA hjälper dig att skydda inloggningen till Microsoft 365 för mobil telefon registrering genom att kräva en andra form av auktorisering.</span><span class="sxs-lookup"><span data-stu-id="34007-148">MFA helps secure the sign in to Microsoft 365 for mobile device enrollment by requiring a second form of authentication.</span></span> <span data-ttu-id="34007-149">Användare måste bekräfta ett telefonsamtal, SMS eller ett program meddelande på sina mobila enheter när de har angett sitt arbets konto lösen ord korrekt.</span><span class="sxs-lookup"><span data-stu-id="34007-149">Users are required to acknowledge a phone call, text message, or app notification on their mobile device after correctly entering their work account password.</span></span> <span data-ttu-id="34007-150">De kan registrera sin enhet först efter det att den här andra formen av verifikationen är klar.</span><span class="sxs-lookup"><span data-stu-id="34007-150">They can enroll their device only after this second form of authentication is completed.</span></span> <span data-ttu-id="34007-151">När användar enheter har registrerats i grundläggande mobilitet och säkerhet kan användarna komma åt Microsoft 365-resurser med bara deras arbets konto.</span><span class="sxs-lookup"><span data-stu-id="34007-151">After user devices are enrolled in Basic Mobility and Security, users can access Microsoft 365 resources with only their work account.</span></span>

<span data-ttu-id="34007-152">Information om hur du aktiverar MFA i Azure AD-portalen finns i [Konfigurera multifaktorautentisering](https://go.microsoft.com/fwlink/p/?LinkId=519255).</span><span class="sxs-lookup"><span data-stu-id="34007-152">To learn how to turn on MFA in the Azure AD portal, see [Set up multi-factor authentication](https://go.microsoft.com/fwlink/p/?LinkId=519255).</span></span>

<span data-ttu-id="34007-153">När du har konfigurerat MFA kan du gå tillbaka till säkerhets & Compliance Center och navigera till **Data loss prevention**   >  **Device management**   >  **enhets principer**för hantering av data förlust   för att slutföra nästa steg.</span><span class="sxs-lookup"><span data-stu-id="34007-153">After you set up MFA, go back to the Security & Compliance Center and navigate to **Data loss prevention** > **Device management** > **Device policies** to complete the next step.</span></span>

### <a name="step-4-recommended-manage-device-security-policies"></a><span data-ttu-id="34007-154">Steg 4: (rekommenderas) hantera säkerhets principer för enheter</span><span class="sxs-lookup"><span data-stu-id="34007-154">Step 4: (Recommended) Manage device security policies</span></span>

<span data-ttu-id="34007-155">Nästa steg är att skapa och distribuera säkerhets principer för enheter för att skydda dina Microsoft 365-organisations data.</span><span class="sxs-lookup"><span data-stu-id="34007-155">The next step is to create and deploy device security policies to help protect your Microsoft 365 organization data.</span></span> <span data-ttu-id="34007-156">Du kan till exempel förhindra data förlust om en användare förlorar sin enhet genom att skapa en princip för att låsa enheter efter fem minuters inaktivitet och rensa enheter efter tre inloggnings problem.</span><span class="sxs-lookup"><span data-stu-id="34007-156">For example, you can help prevent data loss if a user loses their device by creating a policy to lock devices after five minutes of inactivity and wipe devices after three sign-in failures.</span></span>

1. <span data-ttu-id="34007-157">Logga in på Microsoft 365 med ditt globala administratörs konto.</span><span class="sxs-lookup"><span data-stu-id="34007-157">Sign in to Microsoft 365 with your global admin account.</span></span> 

2. <span data-ttu-id="34007-158">Välj [aktivera hantering av mobila enheter](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span><span class="sxs-lookup"><span data-stu-id="34007-158">Select [Activate Mobile Device Management](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="34007-159">Om tjänsten är aktive rad kommer du att se en länk för att [Hantera enheter](https://admin.microsoft.com/adminportal/home#/MifoDevices)i stället   .</span><span class="sxs-lookup"><span data-stu-id="34007-159">If the service is activated, instead the activation steps you'll see a link to [Manage Devices](https://admin.microsoft.com/adminportal/home#/MifoDevices) .</span></span>
    
3. <span data-ttu-id="34007-160">Gå till **enhets principer**.</span><span class="sxs-lookup"><span data-stu-id="34007-160">Go to **Device policies**.</span></span>

     :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Grundläggande principer för säkerhet och mobilitet":::

4. <span data-ttu-id="34007-162">Skapa och distribuera säkerhets principer för enheter som passar din organisation enligt anvisningarna i [skapa säkerhets principer för enheter i grundläggande mobilitet och säkerhet](create-device-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="34007-162">Create and deploy device security policies appropriate for your organization following the steps in [Create device security policies in Basic Mobility and Security](create-device-security-policies.md).</span></span>

>[!TIP]
    - <span data-ttu-id="34007-163">När du skapar en ny princip kanske du vill ange principen för att tillåta åtkomst-och rapport policy brott där en användare het inte är kompatibel med principen.</span><span class="sxs-lookup"><span data-stu-id="34007-163">When you create a new policy, you might want to set the policy to allow access and report policy violation where a user device isn't compliant with the policy.</span></span> <span data-ttu-id="34007-164">Då kan du se hur många mobila enheter som påverkas av principen utan att blockera åtkomst till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34007-164">This allows you see how many mobile devices are impacted by the policy without blocking access to Microsoft 365 .</span></span><br/><span data-ttu-id="34007-165">-Innan du distribuerar en ny princip till alla i organisationen rekommenderar vi att du testar den på de enheter som används av ett litet antal användare.</span><span class="sxs-lookup"><span data-stu-id="34007-165">- Before you deploy a new policy to everyone in your organization, we recommend you test it on the devices used by a small number of users.</span></span><br/><span data-ttu-id="34007-166">-Innan du distribuerar principer kan din organisation ta reda på de potentiella konsekvenserna av att registrera en enhet i grundläggande mobilitet och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="34007-166">- Also, before you deploy policies, let your organization know the potential impacts of enrolling a device in Basic Mobility and Security.</span></span> <span data-ttu-id="34007-167">Beroende på hur du konfigurerar principer kan enheter som inte uppfyller principer (icke-kompatibla enheter) blockeras från att få åtkomst till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34007-167">Depending on how you set up the policies, devices that don't comply with policies (non-compliant devices) could be blocked from accessing Microsoft 365.</span></span> <span data-ttu-id="34007-168">Icke-kompatibla enheter kan också ha installerade appar, foton och annan personlig information som på en registrerad enhet kan tas bort om enheten rensas.</span><span class="sxs-lookup"><span data-stu-id="34007-168">Non-compliant devices might also have apps installed, photos, and other personal information which, on an enrolled device, could be deleted if the device is wiped.</span></span> <span data-ttu-id="34007-169">Mer information finns i [Rensa en mobil enhet i grundläggande mobilitet och säkerhet](wipe-mobile-device.md).</span><span class="sxs-lookup"><span data-stu-id="34007-169">For more info, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>
    
## <a name="make-sure-users-enroll-their-devices"></a><span data-ttu-id="34007-170">Se till att användarna registrerar sina enheter</span><span class="sxs-lookup"><span data-stu-id="34007-170">Make sure users enroll their devices</span></span>

<span data-ttu-id="34007-171">När du har skapat och distribuerat en hanterings princip för mobila enheter kan varje licensierad Microsoft 365-användare i organisationen som enhets principen gäller för få ett registrerings meddelande nästa gång de loggar in på Microsoft 365 från sin mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="34007-171">After you've created and deployed a mobile device management policy, each licensed Microsoft 365 user in your organization that the device policy applies receives an enrollment message the next time they sign into Microsoft 365 from their mobile device.</span></span> <span data-ttu-id="34007-172">De måste slutföra registrerings-och aktiverings stegen innan de kan komma åt Microsoft 365-e-post och dokument.</span><span class="sxs-lookup"><span data-stu-id="34007-172">They must complete the enrollment and activation steps before they can access Microsoft 365 email and documents.</span></span> <span data-ttu-id="34007-173">Mer information finns i [Registrera din mobila enhet med grundläggande mobilitet och säkerhet](enroll-your-mobile-device.md).</span><span class="sxs-lookup"><span data-stu-id="34007-173">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="34007-174">Om en användares prioriterade språk inte stöds av registrerings processen kan användarna få ett meddelande om registrering och anvisningar på sina mobila enheter på ett annat språk.</span><span class="sxs-lookup"><span data-stu-id="34007-174">If a user's preferred language isn't supported by the enrollment process, users might receive enrollment notification and steps on their mobile devices in another language.</span></span> <span data-ttu-id="34007-175">Det går för närvarande inte att använda alla språk i Microsoft 365 för att registrera dig på mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="34007-175">Not all languages supported in Microsoft 365 are currently supported for the enrollment process on mobile devices.</span></span>

<span data-ttu-id="34007-176">Användare med Android-eller iOS-enheter måste installera företagsportalsappen som en del av registrerings processen.</span><span class="sxs-lookup"><span data-stu-id="34007-176">Users with Android or iOS devices are required to install the Company Portal app as part of the enrollment process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="34007-177">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="34007-177">Related Topics</span></span>

[<span data-ttu-id="34007-178">Möjligheter till grundläggande mobilitet och säkerhet</span><span class="sxs-lookup"><span data-stu-id="34007-178">Capabilities of Basic Mobility and Security</span></span>](capabilities.md)<br/>
[<span data-ttu-id="34007-179">Skapa säkerhets principer för enheter i grundläggande mobilitet och säkerhet</span><span class="sxs-lookup"><span data-stu-id="34007-179">Create device security policies in Basic Mobility and Security</span></span>](create-device-security-policies.md)