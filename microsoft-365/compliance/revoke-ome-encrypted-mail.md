---
title: Återkalla e-post som krypteras med avancerad meddelandekryptering
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 06/11/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Som administratör och som meddelandeavsändare kan du återkalla vissa e-postmeddelanden som har krypterats med Office 365 Advanced Message Encryption.
ms.openlocfilehash: 340a9e73dba50e28223ee561db749a089c649df6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "52162335"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="4f960-103">Återkalla e-post som krypteras med avancerad meddelandekryptering</span><span class="sxs-lookup"><span data-stu-id="4f960-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="4f960-104">E-poståterkallning erbjuds som en del av Office 365 Advanced Message Encryption.</span><span class="sxs-lookup"><span data-stu-id="4f960-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="4f960-105">Office 365 Advanced Message Encryption ingår i [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (priser för ideella föreningar), Office 365 Enterprise E5 (priser för ideella föreningar) och Office 365 Education A5.</span><span class="sxs-lookup"><span data-stu-id="4f960-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="4f960-106">Om organisationen har en prenumeration som inte inkluderar Office 365 Advanced Message Encryption kan du köpa den med SKU-tillägget för Microsoft 365 E5 Compliance för Microsoft 365 E3, Microsoft 365 E3 (priser för ideella föreningar) eller SKU-tillägget Office 365 Advanced Compliance för Microsoft 365 E3, Microsoft 365 E3 (priser för ideella föreningar) eller Office 365-SKU:er.</span><span class="sxs-lookup"><span data-stu-id="4f960-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="4f960-107">Den här artikeln är en del av en större serie artiklar om [Meddelandekryptering i Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="4f960-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="4f960-108">Om ett meddelande krypterades med Office 365 Advanced Message Encryption och du är en Microsoft 365-administratör eller du är meddelandets avsändare kan du återkalla meddelandet under vissa förhållanden.</span><span class="sxs-lookup"><span data-stu-id="4f960-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="4f960-109">Administratörer återkallar meddelanden med hjälp av PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f960-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="4f960-110">Som avsändare återkallar du ett meddelande som du skickat direkt Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="4f960-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="4f960-111">I den här artikeln beskrivs under vilka omständigheter en återkallelse är möjlig och hur du gör det.</span><span class="sxs-lookup"><span data-stu-id="4f960-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="4f960-112">Krypterade e-postmeddelanden som du kan återkalla</span><span class="sxs-lookup"><span data-stu-id="4f960-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="4f960-113">Administratörer och avsändare kan återkalla krypterade e-postmeddelanden om mottagaren har fått ett länkbaserat, företagskrypterat e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="4f960-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="4f960-114">Om mottagaren har fått en inbyggd inbyggd upplevelse i en Outlook klient kan du inte återkalla meddelandet.</span><span class="sxs-lookup"><span data-stu-id="4f960-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="4f960-115">Om en mottagare får en länkbaserad upplevelse eller en direkt infogade upplevelse beror på mottagarens identitetstyp: mottagare av Office 365- och Microsoft-konton (till exempel outlook.com-användare) får en direkt upplevelse i de Outlook-klienter som stöds.</span><span class="sxs-lookup"><span data-stu-id="4f960-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="4f960-116">Alla andra mottagartyper, till exempel Gmail- och Yahoo-mottagare, får en länkbaserad upplevelse.</span><span class="sxs-lookup"><span data-stu-id="4f960-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="4f960-117">Administratörer och avsändare kan återkalla meddelanden som krypteras med kryptering som används direkt Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="4f960-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="4f960-118">Till exempel meddelanden som krypteras med alternativet Kryptera endast.</span><span class="sxs-lookup"><span data-stu-id="4f960-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Skärmbild som visar alternativet Endast kryptera Outlook på webben.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="4f960-120">Mottagarens upplevelse av återkallade krypterade e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="4f960-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="4f960-121">När ett e-postmeddelande har återkallats får mottagaren ett felmeddelande när de öppnar det krypterade e-postmeddelandet via Meddelandekryptering i Office 365-portalen: "Meddelandet har återkallats av avsändaren".</span><span class="sxs-lookup"><span data-stu-id="4f960-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![Skärmbild som visar ett återkallat krypterat e-postmeddelande.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="4f960-123">Återkalla ett krypterat meddelande som du skickat</span><span class="sxs-lookup"><span data-stu-id="4f960-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="4f960-124">Du kan återkalla ett e-postmeddelande som du har skickat till en enskild mottagare som använder ett socialt konto, till exempel gmail.com eller yahoo.com.</span><span class="sxs-lookup"><span data-stu-id="4f960-124">You can revoke a mail that you sent to a single recipient that uses a social account such as gmail.com or yahoo.com.</span></span> <span data-ttu-id="4f960-125">Med andra ord kan du återkalla ett e-postmeddelande som skickas till en enskild mottagare som fått den länkbaserade upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="4f960-125">In other words, you can revoke an email sent to a single recipient that received the link-based experience.</span></span>

<span data-ttu-id="4f960-126">Du kan inte återkalla ett e-postmeddelande som du har skickat till en mottagare som använder ett arbets- eller skolkonto från Office 365 eller Microsoft 365 eller en användare som använder ett Microsoft-konto, till exempel ett outlook.com konto.</span><span class="sxs-lookup"><span data-stu-id="4f960-126">You cannot revoke a mail that you sent to a recipient that uses a work or school account from Office 365 or Microsoft 365 or a user that uses a Microsoft account, for example, an outlook.com account.</span></span> 

<span data-ttu-id="4f960-127">Gör så här om du vill återkalla ett krypterat meddelande som du har skickat</span><span class="sxs-lookup"><span data-stu-id="4f960-127">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="4f960-128">I Outlook på webben går du till **mappen** Skickat och bläddrar till meddelandet som du vill återkalla.</span><span class="sxs-lookup"><span data-stu-id="4f960-128">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="4f960-129">Om e-postmeddelandet kan återkallas visas länken "Ta bort extern åtkomst" högst upp i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="4f960-129">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Skärmbild som visar krypterad e-post som du vill återkalla Outlook på webben.":::

2. <span data-ttu-id="4f960-131">Klicka **på Ta bort extern** åtkomst om du vill återkalla meddelandet.</span><span class="sxs-lookup"><span data-stu-id="4f960-131">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="4f960-132">Meddelandet visar att dess status har återkallats.</span><span class="sxs-lookup"><span data-stu-id="4f960-132">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Skärmbild som visar återkallat krypterat meddelande Outlook på webben.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="4f960-134">Återkalla ett krypterat meddelande som administratör</span><span class="sxs-lookup"><span data-stu-id="4f960-134">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="4f960-135">Microsoft 365 här allmänna anvisningarna för att återkalla ett berättigat krypterat e-postmeddelande:</span><span class="sxs-lookup"><span data-stu-id="4f960-135">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="4f960-136">Hämta e-postmeddelandets meddelande-ID.</span><span class="sxs-lookup"><span data-stu-id="4f960-136">Get the Message ID of the email.</span></span>
- <span data-ttu-id="4f960-137">Kontrollera att du kan återkalla meddelandet.</span><span class="sxs-lookup"><span data-stu-id="4f960-137">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="4f960-138">Återkalla e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="4f960-138">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="4f960-139">Steg 1.</span><span class="sxs-lookup"><span data-stu-id="4f960-139">Step 1.</span></span> <span data-ttu-id="4f960-140">Hämta e-postmeddelandets meddelande-ID</span><span class="sxs-lookup"><span data-stu-id="4f960-140">Obtain the Message ID of the email</span></span>

<span data-ttu-id="4f960-141">Innan du kan återkalla ett krypterat e-postmeddelande måste du samla in e-postmeddelandets meddelande-ID.</span><span class="sxs-lookup"><span data-stu-id="4f960-141">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="4f960-142">Meddelande-ID:t är vanligtvis av följande format:</span><span class="sxs-lookup"><span data-stu-id="4f960-142">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="4f960-143">Det finns flera sätt att hitta meddelande-ID för e-postmeddelandet som du vill återkalla.</span><span class="sxs-lookup"><span data-stu-id="4f960-143">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="4f960-144">I det här avsnittet beskrivs några olika alternativ, men du kan använda valfri metod som tillhandahåller ID:t.</span><span class="sxs-lookup"><span data-stu-id="4f960-144">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="4f960-145">Identifiera meddelande-ID för det e-postmeddelande som du vill återkalla med hjälp av Meddelandespårning i &amp; Säkerhetsefterlevnad</span><span class="sxs-lookup"><span data-stu-id="4f960-145">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="4f960-146">Sök efter e-postmeddelandet efter avsändare eller mottagare med [hjälp av Ny meddelandespårning i & Säkerhets- och efterlevnadscenter.](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)</span><span class="sxs-lookup"><span data-stu-id="4f960-146">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="4f960-147">När du har hittat e-postmeddelandet väljer du det så att fönstret **Meddelandespårning visas.**</span><span class="sxs-lookup"><span data-stu-id="4f960-147">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="4f960-148">Expandera **Mer information för** att hitta meddelande-ID.</span><span class="sxs-lookup"><span data-stu-id="4f960-148">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="4f960-149">Identifiera meddelande-ID för det e-postmeddelande som du vill återkalla med hjälp Office meddelandekrypteringsrapporter i &amp; Säkerhetsefterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="4f960-149">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="4f960-150">Gå till &amp; rapporten Meddelandekryptering i **Säkerhetsefterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="4f960-150">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="4f960-151">Mer information om den här rapporten finns i [Visa säkerhetsrapporter för e-post i &amp; Säkerhetsefterlevnadscenter.](../security/defender-365-security/view-email-security-reports.md)</span><span class="sxs-lookup"><span data-stu-id="4f960-151">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/defender-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="4f960-152">Välj tabellen **Visa information** och identifiera meddelandet som du vill återkalla.</span><span class="sxs-lookup"><span data-stu-id="4f960-152">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="4f960-153">Dubbelklicka på meddelandet för att visa information som innehåller meddelande-ID.</span><span class="sxs-lookup"><span data-stu-id="4f960-153">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="4f960-154">Steg 2.</span><span class="sxs-lookup"><span data-stu-id="4f960-154">Step 2.</span></span> <span data-ttu-id="4f960-155">Kontrollera att e-postmeddelandet kan återkallas</span><span class="sxs-lookup"><span data-stu-id="4f960-155">Verify that the mail is revocable</span></span>

<span data-ttu-id="4f960-156">Kontrollera om du kan återkalla ett meddelande genom att kontrollera om fältet Återkallelsestatus visas i rapporten Kryptering i tabellen **Information** i &amp; Säkerhetsefterlevnad.</span><span class="sxs-lookup"><span data-stu-id="4f960-156">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="4f960-157">Utför de här stegen för att verifiera om du kan återkalla ett visst e Windows PowerShell postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="4f960-157">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="4f960-158">Om du använder ett arbets- eller skolkonto med global administratörsbehörighet i din organisation startar du Windows PowerShell en session och ansluter till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4f960-158">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="4f960-159">Instruktioner finns i [Anslut för Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="4f960-159">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="4f960-160">Kör Get-OMEMessageStatus cmdleten så här:</span><span class="sxs-lookup"><span data-stu-id="4f960-160">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="4f960-161">Det här kommandot returnerar ämnet för meddelandet och om meddelandet kan återkallas.</span><span class="sxs-lookup"><span data-stu-id="4f960-161">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="4f960-162">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="4f960-162">For example,</span></span>

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="4f960-163">Steg 3.</span><span class="sxs-lookup"><span data-stu-id="4f960-163">Step 3.</span></span> <span data-ttu-id="4f960-164">Återkalla e-postmeddelandet</span><span class="sxs-lookup"><span data-stu-id="4f960-164">Revoke the mail</span></span>

<span data-ttu-id="4f960-165">När du vet meddelande-ID för e-postmeddelandet som du vill återkalla och du har verifierat att meddelandet kan återkallas kan du återkalla e-postmeddelandet med hjälp av Säkerhetsefterlevnad &amp; eller Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f960-165">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="4f960-166">Så här återkallar du meddelandet med hjälp av &amp; Säkerhetsefterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="4f960-166">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="4f960-167">Använd ett arbets- eller skolkonto med global administratörsbehörighet i din organisation och anslut till Säkerhets- & efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="4f960-167">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="4f960-168">Välj **Återkalla meddelande** i **tabellen Information för** meddelandet i rapporten **Kryptering.**</span><span class="sxs-lookup"><span data-stu-id="4f960-168">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="4f960-169">Om du vill återkalla ett e-Windows PowerShell med hjälp av Set-OMEMessageRevocation-cmdleten.</span><span class="sxs-lookup"><span data-stu-id="4f960-169">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="4f960-170">Med ett arbets- eller skolkonto med global administratörsbehörighet i din organisation kan [du Anslut till Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="4f960-170">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="4f960-171">Kör Set-OMEMessageRevocation cmdleten så här:</span><span class="sxs-lookup"><span data-stu-id="4f960-171">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="4f960-172">Om du vill kontrollera om e-postmeddelandet har återkallats kör du cmdleten Get-OMEMessageStatus följande:</span><span class="sxs-lookup"><span data-stu-id="4f960-172">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="4f960-173">Om återkallelsen lyckades returnerar cmdleten följande resultat:</span><span class="sxs-lookup"><span data-stu-id="4f960-173">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="4f960-174">Mer information om Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="4f960-174">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="4f960-175">Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="4f960-175">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="4f960-176">Office 365 Advanced Message Encryption – förfallotid för e-post</span><span class="sxs-lookup"><span data-stu-id="4f960-176">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="4f960-177">Beskrivning av meddelandeprincip och efterlevnadstjänst</span><span class="sxs-lookup"><span data-stu-id="4f960-177">Message policy and compliance service description</span></span>](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)