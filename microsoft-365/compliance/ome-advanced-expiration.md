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
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Konfigurera ett utgångsdatum för e-post som krypterats med Office 365 Advanced Message Encryption

Office 365 Advanced Message Encryption ingår i [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (priser för ideella föreningar), Office 365 Enterprise E5 (priser för ideella föreningar) och Office 365 Education A5. Om organisationen har en prenumeration som inte inkluderar Office 365 Advanced Message Encryption kan du köpa den med SKU-tillägget för Microsoft 365 E5 Compliance för Microsoft 365 E3, Microsoft 365 E3 (priser för ideella föreningar) eller SKU-tillägget Office 365 Advanced Compliance för Microsoft 365 E3, Microsoft 365 E3 (priser för ideella föreningar) eller Office 365-SKU:er.

Du kan använda förfallotid för meddelanden som användarna skickar till externa mottagare som använder OME-portalen för att komma åt krypterade e-postmeddelanden. Du tvingar mottagarna att använda OME-portalen för att visa och svara på krypterade e-postmeddelanden som skickas av din organisation med hjälp av en anpassad anpassad mall som anger ett utgångsdatum i Windows PowerShell.

Som global Office 365 kan du, när du tillämpar företagets varumärke för att anpassa utseendet på din organisations e-postmeddelanden, också ange ett utgångsdatum för dessa e-postmeddelanden. Med Office 365 Advanced Message Encryption kan du skapa flera mallar för krypterade e-postmeddelanden som kommer från din organisation. Med hjälp av en mall kan du styra hur länge mottagare har åtkomst till e-post som skickas av dina användare.

När en slutanvändare får e-post som har ett utgångsdatum inställt ser användaren utgångsdatumet i e-postmeddelandet för radbrytningen. Om en användare försöker öppna ett e-postmeddelande som redan har löpt ut visas ett fel i OME-portalen.

Du kan bara ange utgångsdatum för e-postmeddelanden till externa mottagare.

När Office 365 Advanced Message Encryption använder anpassade profiler används figursättning i Office 365 för e-post som passar e-postflödesregeln som du använder mallen för. Du kan dessutom bara använda förfallotid om du använder anpassade profilering.

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>Skapa en anpassad varumärkesmall för att tvinga fram förfallotid för e-post med hjälp av PowerShell

1. [Anslut att Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) med ett konto som har globala administratörsbehörigheter i organisationen.

2. Kör New-OMEConfiguration cmdlet.

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

Var:

- `Identity` är namnet på den anpassade mallen.

- `ExternalMailExpiryInDays` anger antal dagar som mottagare kan behålla sin e-post innan den löper ut. Du kan använda val valfri värde mellan 1–730 dagar.

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Mer information om Office 365 Advanced Message Encryption

- [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md)

- [Återkalla e-post som krypterats med Office 365 Advanced Message Encryption](revoke-ome-encrypted-mail.md)

- [Beskrivning av meddelandeprincip och efterlevnadstjänst](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)