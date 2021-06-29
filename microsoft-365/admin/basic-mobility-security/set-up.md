---
title: Konfigurera grundläggande Mobility and Security
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
description: Konfigurera Basic Mobility and Security för att skydda och hantera användarnas mobila enheter genom att utföra åtgärder som att fjärradera en enhet.
ms.openlocfilehash: f1cfa6cdc8d799ba62c687408cb12a4ba453f313
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177279"
---
# <a name="set-up-basic-mobility-and-security"></a><span data-ttu-id="cb715-103">Konfigurera grundläggande Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="cb715-103">Set up Basic Mobility and Security</span></span>

<span data-ttu-id="cb715-104">Den inbyggda funktionen Basic Mobility and Security för Microsoft 365 hjälper dig att skydda och hantera användarnas mobila enheter, till exempel iPhone, iPad, Android och Windows telefoner.</span><span class="sxs-lookup"><span data-stu-id="cb715-104">The built-in Basic Mobility and Security for Microsoft 365 helps you secure and manage users' mobile devices such as iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="cb715-105">Du kan skapa och hantera säkerhetsprinciper för enheter, fjärradea enheter och visa detaljerade enhetsrapporter.</span><span class="sxs-lookup"><span data-stu-id="cb715-105">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

<span data-ttu-id="cb715-106">Har du frågor?</span><span class="sxs-lookup"><span data-stu-id="cb715-106">Have questions?</span></span> <span data-ttu-id="cb715-107">Vanliga frågor och svar om grundläggande rörlighet och säkerhet finns i Vanliga frågor och svar om [grundläggande rörlighet och säkerhet.](frequently-asked-questions.yml)</span><span class="sxs-lookup"><span data-stu-id="cb715-107">For a FAQ to help address common questions, see [Basic Mobility and Security Frequently-asked questions (FAQ)](frequently-asked-questions.yml).</span></span> <span data-ttu-id="cb715-108">Observera att du inte kan använda ett delegerat administratörskonto för att hantera grundläggande rörlighet och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="cb715-108">Be aware that you cannot use a delegated administrator account to manage Basic Mobility and Security.</span></span> <span data-ttu-id="cb715-109">Mer information finns i [Partner: Erbjuda delegerad administration.](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e)</span><span class="sxs-lookup"><span data-stu-id="cb715-109">For more info, see [Partners: Offer delegated administration](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e).</span></span> 

<span data-ttu-id="cb715-110">Enhetshantering är en del av säkerhets- & säkerhets- och efterlevnadscentret, så du måste gå dit för att starta installationen av Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="cb715-110">Device management is part of the Security & Compliance Center so you'll need to go there to kick off Basic Mobility and Security setup.</span></span>

## <a name="activate-the-basic-mobility-and-security-service"></a><span data-ttu-id="cb715-111">Aktivera tjänsten Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="cb715-111">Activate the Basic Mobility and Security service</span></span>

1. <span data-ttu-id="cb715-112">Logga in på Microsoft 365 ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="cb715-112">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="cb715-113">Gå till [Aktivera grundläggande rörlighet och säkerhet.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)</span><span class="sxs-lookup"><span data-stu-id="cb715-113">Go to [Activate Basic Mobility and Security](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span>

   <span data-ttu-id="cb715-114">Det kan ta lite tid att aktivera Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="cb715-114">It can take some time to activate Basic Mobility and Security.</span></span> <span data-ttu-id="cb715-115">När den är klar får du ett e-postmeddelande som förklarar nästa steg att vidta.</span><span class="sxs-lookup"><span data-stu-id="cb715-115">When it finishes, you'll receive an email that explains the next steps to take.</span></span>

## <a name="set-up-mobile-device-management"></a><span data-ttu-id="cb715-116">Konfigurera Hantering av mobila enheter</span><span class="sxs-lookup"><span data-stu-id="cb715-116">Set up Mobile Device Management</span></span>

<span data-ttu-id="cb715-117">När tjänsten är klar slutför du konfigurationen genom att följa anvisningarna nedan.</span><span class="sxs-lookup"><span data-stu-id="cb715-117">When the service is ready, complete the following steps to finish setup.</span></span>

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a><span data-ttu-id="cb715-118">Steg 1: (Obligatoriskt) Konfigurera domäner för grundläggande rörlighet och säkerhet</span><span class="sxs-lookup"><span data-stu-id="cb715-118">Step 1: (Required) Configure domains for Basic Mobility and Security</span></span>

<span data-ttu-id="cb715-119">Om du inte har en egen domän som är kopplad Microsoft 365 eller om du inte hanterar Windows kan du hoppa över det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="cb715-119">If you don't have a custom domain associated with Microsoft 365 or if you're not managing Windows devices, you can skip this section.</span></span> <span data-ttu-id="cb715-120">Annars måste du lägga till DNS-poster för domänen hos din DNS-värd.</span><span class="sxs-lookup"><span data-stu-id="cb715-120">Otherwise, you'll need to add DNS records for the domain at your DNS host.</span></span> <span data-ttu-id="cb715-121">Om du redan har lagt till posterna, som ett led i att konfigurera Microsoft 365 domän, är allt klart.</span><span class="sxs-lookup"><span data-stu-id="cb715-121">If you've added the records already, as part of setting up your domain with Microsoft 365, you're all set.</span></span> <span data-ttu-id="cb715-122">När du har lagt till posterna Microsoft 365 användare i organisationen som loggar in på sina Windows-enheter med en e-postadress som använder din egen domän omdirigeras för att registrera sig i Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="cb715-122">After you add the records, Microsoft 365 users in your organization who sign in on their Windows device with an email address that uses your custom domain are redirected to enroll in Basic Mobility and Security.</span></span>

<span data-ttu-id="cb715-123">Behöver du hjälp med att konfigurera posterna?</span><span class="sxs-lookup"><span data-stu-id="cb715-123">Need help setting up the records?</span></span> <span data-ttu-id="cb715-124">Hitta din domänregistrator och välj registratornamnet för att gå till steg-för-steg-hjälp för att skapa DNS-posten i listan i Lägg till DNS-poster för [att ansluta din domän.](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)</span><span class="sxs-lookup"><span data-stu-id="cb715-124">Find your domain registrar and select the registrar name to go to step-by-step help for creating DNS record in the list provided in [Add DNS records to connect your domain](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span> <span data-ttu-id="cb715-125">Använd de här anvisningarna för att skapa CNAME-poster som [beskrivs i Förenkla Windows registrering utan Azure AD Premium.](/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)</span><span class="sxs-lookup"><span data-stu-id="cb715-125">Use those instructions to create CNAME records described in [Simplify Windows enrollment without Azure AD Premium](/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium).</span></span>

<span data-ttu-id="cb715-126">När du har lagt till de två CNAME-posterna går du tillbaka till Säkerhets- och & efterlevnadscenter och går till **Dataförlustskydd**  >  **Enhetshantering för**   att slutföra nästa steg.</span><span class="sxs-lookup"><span data-stu-id="cb715-126">After you add the two CNAME records, go back to the Security & Compliance Center and go to **Data loss prevention** > **Device management** to complete the next step.</span></span>

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="cb715-127">Steg 2: (Obligatoriskt) Konfigurera ett APNs-certifikat för iOS-enheter</span><span class="sxs-lookup"><span data-stu-id="cb715-127">Step 2: (Required) Configure an APNs Certificate for iOS devices</span></span>

<span data-ttu-id="cb715-128">För att hantera iOS-enheter som iPad och iPhone måste du skapa ett APNs-certifikat.</span><span class="sxs-lookup"><span data-stu-id="cb715-128">To manage iOS devices like iPad and iPhones, you need to create an APNs certificate.</span></span>

1. <span data-ttu-id="cb715-129">Logga in på Microsoft 365 ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="cb715-129">Sign in to  Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="cb715-130">Skriv följande i webbläsaren:  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="cb715-130">In your browser type: [https://protection.office.com](https://protection.office.com/).</span></span>

3. <span data-ttu-id="cb715-131">Välj  **Dataförlustskydd**   >  **Enhetshantering och** välj **APNs-certifikat för iOS-enheter.**</span><span class="sxs-lookup"><span data-stu-id="cb715-131">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>

4. <span data-ttu-id="cb715-132">På sidan Apple Push Notification Certificate Inställningar väljer du **Next**.</span><span class="sxs-lookup"><span data-stu-id="cb715-132">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>

5. <span data-ttu-id="cb715-133">Välj **Ladda ned din CSR-fil** och spara begäran om   certifikatsignering någonstans på datorn som är så bra att du kommer ihåg den.</span><span class="sxs-lookup"><span data-stu-id="cb715-133">Select **Download your CSR file** and save the Certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="cb715-134">Välj **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="cb715-134">Select **Next**.</span></span>

6. <span data-ttu-id="cb715-135">På sidan Skapa ett APNs-certifikat:</span><span class="sxs-lookup"><span data-stu-id="cb715-135">On the Create an APNs certificate page:</span></span>

   - <span data-ttu-id="cb715-136">Välj Apple APNS-portalen för att öppna Apple Push Certificates-portalen.</span><span class="sxs-lookup"><span data-stu-id="cb715-136">Select Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>
   - <span data-ttu-id="cb715-137">Logga in med ett Apple-ID.</span><span class="sxs-lookup"><span data-stu-id="cb715-137">Sign in with an Apple ID.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="cb715-138">Använd ett företags-Apple-ID som är kopplat till ett e-postkonto som kommer att finnas kvar i din organisation även om användaren som hanterar kontot slutar.</span><span class="sxs-lookup"><span data-stu-id="cb715-138">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves.</span></span> <span data-ttu-id="cb715-139">Spara detta ID eftersom du måste använda samma ID när det är dags att förnya certifikatet.</span><span class="sxs-lookup"><span data-stu-id="cb715-139">Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

   - <span data-ttu-id="cb715-140">Välj Skapa ett certifikat och godkänn användningsvillkoren.</span><span class="sxs-lookup"><span data-stu-id="cb715-140">Select Create a Certificate and accept the Terms of Use.</span></span>
   - <span data-ttu-id="cb715-141">Bläddra till den begäran om certifikatsignering som du laddade ned till datorn Microsoft 365 och selectUpload.</span><span class="sxs-lookup"><span data-stu-id="cb715-141">Browse to the Certificate signing request you downloaded to your computer from Microsoft 365 and selectUpload.</span></span>
   - <span data-ttu-id="cb715-142">Ladda ned det APN-certifikat som skapades av Apple Push Certificate-portalen till din dator.</span><span class="sxs-lookup"><span data-stu-id="cb715-142">Download the APN certificate created by the Apple Push Certificate Portal to your computer.</span></span>

     > [!TIP]
     > <span data-ttu-id="cb715-143">Om du har problem med att ladda ned certifikatet kan du uppdatera webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="cb715-143">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="cb715-144">Gå tillbaka till Microsoft 365 och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="cb715-144">Go back to Microsoft 365 and select **Next**.</span></span>

8. <span data-ttu-id="cb715-145">Bläddra till det APN-certifikat som du laddade ned från Apple Push Certificates-portalen.</span><span class="sxs-lookup"><span data-stu-id="cb715-145">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>

9. <span data-ttu-id="cb715-146">Välj  **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="cb715-146">Select  **Finish**.</span></span>

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a><span data-ttu-id="cb715-147">Steg 3: (Rekommenderas) Konfigurera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="cb715-147">Step 3: (Recommended) Set up multi-factor authentication</span></span>

<span data-ttu-id="cb715-148">MFA hjälper till att skydda inloggningen på Microsoft 365 registrering av mobila enheter genom att kräva en andra form av autentisering.</span><span class="sxs-lookup"><span data-stu-id="cb715-148">MFA helps secure the sign in to Microsoft 365 for mobile device enrollment by requiring a second form of authentication.</span></span> <span data-ttu-id="cb715-149">Användare måste bekräfta ett telefonsamtal, sms eller appmeddelande på sin mobila enhet efter att de har angett lösenordet för sitt arbetskonto.</span><span class="sxs-lookup"><span data-stu-id="cb715-149">Users are required to acknowledge a phone call, text message, or app notification on their mobile device after correctly entering their work account password.</span></span> <span data-ttu-id="cb715-150">De kan registrera sin enhet efter att den andra formen av autentisering är slutförd.</span><span class="sxs-lookup"><span data-stu-id="cb715-150">They can enroll their device only after this second form of authentication is completed.</span></span> <span data-ttu-id="cb715-151">När användarenheter har registrerats i Basic Mobility and Security kan användarna komma åt Microsoft 365 med sina arbetsresurser.</span><span class="sxs-lookup"><span data-stu-id="cb715-151">After user devices are enrolled in Basic Mobility and Security, users can access Microsoft 365 resources with only their work account.</span></span>

<span data-ttu-id="cb715-152">Mer information om hur du aktiverar MFA i Azure AD-portalen finns i [Konfigurera multifaktorautentisering.](../security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="cb715-152">To learn how to turn on MFA in the Azure AD portal, see [Set up multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="cb715-153">När du har konfigurerat MFA går du tillbaka till \*\*\*\* säkerhets- och efterlevnadscentret för & och navigerar till Principer för dataförlustskydd Enhetshantering för   >     >  \*\*\*\*   att slutföra nästa steg.</span><span class="sxs-lookup"><span data-stu-id="cb715-153">After you set up MFA, go back to the Security & Compliance Center and navigate to  **Data loss prevention** > **Device management** > **Device policies** to complete the next step.</span></span>

### <a name="step-4-recommended-manage-device-security-policies"></a><span data-ttu-id="cb715-154">Steg 4: (Rekommenderas) Hantera säkerhetsprinciper för enheter</span><span class="sxs-lookup"><span data-stu-id="cb715-154">Step 4: (Recommended) Manage device security policies</span></span>

<span data-ttu-id="cb715-155">Nästa steg är att skapa och distribuera säkerhetsprinciper för enheter för att skydda dina Microsoft 365 organisationsdata.</span><span class="sxs-lookup"><span data-stu-id="cb715-155">The next step is to create and deploy device security policies to help protect your Microsoft 365 organization data.</span></span> <span data-ttu-id="cb715-156">Du kan till exempel förhindra dataförlust om en användare förlorar sin enhet genom att skapa en princip för att låsa enheter efter fem minuters inaktivitet och rensa enheter efter tre inloggningsfel.</span><span class="sxs-lookup"><span data-stu-id="cb715-156">For example, you can help prevent data loss if a user loses their device by creating a policy to lock devices after five minutes of inactivity and wipe devices after three sign-in failures.</span></span>

1. <span data-ttu-id="cb715-157">Logga in på Microsoft 365 ditt globala administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="cb715-157">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="cb715-158">Välj [Aktivera Hantering av mobila enheter](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span><span class="sxs-lookup"><span data-stu-id="cb715-158">Select [Activate Mobile Device Management](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="cb715-159">Om tjänsten är aktiverad visas i stället en länk till Hantera enheter under [aktiveringsstegen.](https://admin.microsoft.com/adminportal/home#/MifoDevices)  </span><span class="sxs-lookup"><span data-stu-id="cb715-159">If the service is activated, instead the activation steps you'll see a link to [Manage Devices](https://admin.microsoft.com/adminportal/home#/MifoDevices) .</span></span>

3. <span data-ttu-id="cb715-160">Gå till **Enhetsprinciper.**</span><span class="sxs-lookup"><span data-stu-id="cb715-160">Go to **Device policies**.</span></span>

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Principinställningar för grundläggande säkerhet och rörlighet":::

4. <span data-ttu-id="cb715-162">Skapa och distribuera säkerhetsprinciper för enheter som är lämpliga för din organisation genom att följa stegen i Skapa säkerhetsprinciper för [enheter i Grundläggande rörlighet och säkerhet.](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="cb715-162">Create and deploy device security policies appropriate for your organization following the steps in [Create device security policies in Basic Mobility and Security](create-device-security-policies.md).</span></span>

> [!TIP]
>
> - <span data-ttu-id="cb715-163">När du skapar en ny princip kan du ange att principen ska tillåta åtkomst och rapportera principbrott när en användarenhet inte följer principen.</span><span class="sxs-lookup"><span data-stu-id="cb715-163">When you create a new policy, you might want to set the policy to allow access and report policy violation where a user device isn't compliant with the policy.</span></span> <span data-ttu-id="cb715-164">På så sätt kan du se hur många mobila enheter som påverkas av principen utan att blockera åtkomst till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cb715-164">This allows you see how many mobile devices are impacted by the policy without blocking access to Microsoft 365.</span></span>
>
> - <span data-ttu-id="cb715-165">Innan du distribuerar en ny princip för alla i organisationen rekommenderar vi att du testar den på enheter som används av ett litet antal användare.</span><span class="sxs-lookup"><span data-stu-id="cb715-165">Before you deploy a new policy to everyone in your organization, we recommend you test it on the devices used by a small number of users.</span></span>
>
> - <span data-ttu-id="cb715-166">Innan du distribuerar principer bör du även meddela organisationen hur de kan påverkas av att registrera en enhet i Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="cb715-166">Also, before you deploy policies, let your organization know the potential impacts of enrolling a device in Basic Mobility and Security.</span></span> <span data-ttu-id="cb715-167">Beroende på hur du konfigurerade principerna kan enheter som inte följer principer (icke-kompatibla enheter) blockeras från att komma åt Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cb715-167">Depending on how you set up the policies, devices that don't comply with policies (non-compliant devices) could be blocked from accessing Microsoft 365.</span></span> <span data-ttu-id="cb715-168">Enheter som inte är kompatibla kan också ha installerade appar, foton och annan personlig information som på en registrerad enhet kan tas bort om enheten rensas.</span><span class="sxs-lookup"><span data-stu-id="cb715-168">Non-compliant devices might also have apps installed, photos, and other personal information which, on an enrolled device, could be deleted if the device is wiped.</span></span> <span data-ttu-id="cb715-169">Mer information finns i Rensa [en mobil enhet i Grundläggande rörlighet och säkerhet.](wipe-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="cb715-169">For more info, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="make-sure-users-enroll-their-devices"></a><span data-ttu-id="cb715-170">Se till att användarna registrerar sina enheter</span><span class="sxs-lookup"><span data-stu-id="cb715-170">Make sure users enroll their devices</span></span>

<span data-ttu-id="cb715-171">När du har skapat och distribuerat en princip för hantering av mobila enheter får alla licensierade Microsoft 365-användare i organisationen som principen gäller ett registreringsmeddelande nästa gång de loggar in på Microsoft 365 från sin mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="cb715-171">After you've created and deployed a mobile device management policy, each licensed Microsoft 365 user in your organization that the device policy applies receives an enrollment message the next time they sign into Microsoft 365 from their mobile device.</span></span> <span data-ttu-id="cb715-172">Registreringen och aktiveringen måste slutföras innan de kan komma åt alla e Microsoft 365 och dokument.</span><span class="sxs-lookup"><span data-stu-id="cb715-172">They must complete the enrollment and activation steps before they can access Microsoft 365 email and documents.</span></span> <span data-ttu-id="cb715-173">Mer information finns i [Registrera din mobila enhet med grundläggande rörlighet och säkerhet.](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="cb715-173">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb715-174">Om en användares valda språk inte stöds i registreringsprocessen kan användare få registreringsmeddelande och -steg på sina mobila enheter på ett annat språk.</span><span class="sxs-lookup"><span data-stu-id="cb715-174">If a user's preferred language isn't supported by the enrollment process, users might receive enrollment notification and steps on their mobile devices in another language.</span></span> <span data-ttu-id="cb715-175">Inte alla språk som stöds Microsoft 365 i registreringsprocessen på mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="cb715-175">Not all languages supported in Microsoft 365 are currently supported for the enrollment process on mobile devices.</span></span>

<span data-ttu-id="cb715-176">Användare med Android- eller iOS-enheter måste installera Företagsportal-appen som en del av registreringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="cb715-176">Users with Android or iOS devices are required to install the Company Portal app as part of the enrollment process.</span></span>

## <a name="related-content"></a><span data-ttu-id="cb715-177">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="cb715-177">Related content</span></span>

<span data-ttu-id="cb715-178">[Funktioner för basic mobility and security](capabilities.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="cb715-178">[Capabilities of Basic Mobility and Security](capabilities.md) (article)</span></span>\
<span data-ttu-id="cb715-179">[Skapa säkerhetsprinciper för enheter i Basic Mobility and Security](create-device-security-policies.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="cb715-179">[Create device security policies in Basic Mobility and Security](create-device-security-policies.md) (article)</span></span>