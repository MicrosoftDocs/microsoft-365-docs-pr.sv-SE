---
title: Konfigurera ett utgångsdatum för e-post som krypterats med Office 365 Advanced Message Encryption
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/8/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Använd Office 365 Advanced Message Encryption för att utöka din e-postsäkerhet genom att ange ett utgångsdatum för e-postmeddelanden med hjälp av en anpassad anpassad mall.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f936ffa62f31e47f51fc1bcb2765195b0ea809af
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162244"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="51dbf-103">Konfigurera ett utgångsdatum för e-post som krypterats med Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="51dbf-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="51dbf-104">Office 365 Advanced Message Encryption ingår i [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (priser för ideella föreningar), Office 365 Enterprise E5 (priser för ideella föreningar) och Office 365 Education A5.</span><span class="sxs-lookup"><span data-stu-id="51dbf-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="51dbf-105">Om organisationen har en prenumeration som inte inkluderar Office 365 Advanced Message Encryption kan du köpa den med SKU-tillägget för Microsoft 365 E5 Compliance för Microsoft 365 E3, Microsoft 365 E3 (priser för ideella föreningar) eller SKU-tillägget Office 365 Advanced Compliance för Microsoft 365 E3, Microsoft 365 E3 (priser för ideella föreningar) eller Office 365-SKU:er.</span><span class="sxs-lookup"><span data-stu-id="51dbf-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="51dbf-106">Du kan använda förfallotid för meddelanden som användarna skickar till externa mottagare som använder OME-portalen för att komma åt krypterade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="51dbf-106">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="51dbf-107">Du tvingar mottagarna att använda OME-portalen för att visa och svara på krypterade e-postmeddelanden som skickas av din organisation med hjälp av en anpassad anpassad mall som anger ett utgångsdatum i Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51dbf-107">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows PowerShell.</span></span>

<span data-ttu-id="51dbf-108">Som global Office 365 kan du, när du tillämpar företagets varumärke för att anpassa utseendet på din organisations e-postmeddelanden, också ange ett utgångsdatum för dessa e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="51dbf-108">As an Office 365 global administrator, when you apply your company brand to customize the look of your organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="51dbf-109">Med Office 365 Advanced Message Encryption kan du skapa flera mallar för krypterade e-postmeddelanden som kommer från din organisation.</span><span class="sxs-lookup"><span data-stu-id="51dbf-109">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="51dbf-110">Med hjälp av en mall kan du styra hur länge mottagare har åtkomst till e-post som skickas av dina användare.</span><span class="sxs-lookup"><span data-stu-id="51dbf-110">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="51dbf-111">När en slutanvändare får e-post som har ett utgångsdatum inställt ser användaren utgångsdatumet i e-postmeddelandet för radbrytningen.</span><span class="sxs-lookup"><span data-stu-id="51dbf-111">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="51dbf-112">Om en användare försöker öppna ett e-postmeddelande som redan har löpt ut visas ett fel i OME-portalen.</span><span class="sxs-lookup"><span data-stu-id="51dbf-112">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="51dbf-113">Du kan bara ange utgångsdatum för e-postmeddelanden till externa mottagare.</span><span class="sxs-lookup"><span data-stu-id="51dbf-113">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="51dbf-114">När Office 365 Advanced Message Encryption använder anpassade profiler används figursättning i Office 365 för e-post som passar e-postflödesregeln som du använder mallen för.</span><span class="sxs-lookup"><span data-stu-id="51dbf-114">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="51dbf-115">Du kan dessutom bara använda förfallotid om du använder anpassade profilering.</span><span class="sxs-lookup"><span data-stu-id="51dbf-115">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="51dbf-116">Skapa en anpassad varumärkesmall för att tvinga fram förfallotid för e-post med hjälp av PowerShell</span><span class="sxs-lookup"><span data-stu-id="51dbf-116">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="51dbf-117">[Anslut att Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) med ett konto som har globala administratörsbehörigheter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="51dbf-117">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your organization.</span></span>

2. <span data-ttu-id="51dbf-118">Kör New-OMEConfiguration cmdlet.</span><span class="sxs-lookup"><span data-stu-id="51dbf-118">Run the New-OMEConfiguration cmdlet.</span></span>

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

<span data-ttu-id="51dbf-119">Var:</span><span class="sxs-lookup"><span data-stu-id="51dbf-119">Where:</span></span>

- <span data-ttu-id="51dbf-120">`Identity` är namnet på den anpassade mallen.</span><span class="sxs-lookup"><span data-stu-id="51dbf-120">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="51dbf-121">`ExternalMailExpiryInDays` anger antal dagar som mottagare kan behålla sin e-post innan den löper ut.</span><span class="sxs-lookup"><span data-stu-id="51dbf-121">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="51dbf-122">Du kan använda val valfri värde mellan 1–730 dagar.</span><span class="sxs-lookup"><span data-stu-id="51dbf-122">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="51dbf-123">Mer information om Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="51dbf-123">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="51dbf-124">Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="51dbf-124">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="51dbf-125">Återkalla e-post som krypterats med Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="51dbf-125">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="51dbf-126">Beskrivning av meddelandeprincip och efterlevnadstjänst</span><span class="sxs-lookup"><span data-stu-id="51dbf-126">Message policy and compliance service description</span></span>](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)