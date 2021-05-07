---
title: Läs mer om informationsbarriärer i Microsoft 365
description: Använd informationsbarriärer för att säkerställa att kommunikationsefterlevnaden Microsoft Teams inom organisationen.
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4ef3fce82a10792c8289a4a3c4e3cb5639a4d178
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "52162392"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a>Läs mer om informationsbarriärer i Microsoft 365

Microsofts molntjänster innehåller kraftfulla funktioner för kommunikation och samarbete. Anta dock att du vill begränsa kommunikation och samarbete mellan två grupper för att undvika en intressekonflikt i organisationen. Eller kanske du vill begränsa kommunikation och samarbete mellan vissa personer i organisationen för att skydda intern information. Microsoft 365 här funktionen möjliggör kommunikation och samarbete mellan grupper och organisationer, så finns det något sätt att begränsa kommunikation och samarbete mellan specifika grupper av användare när det behövs? Om det finns informationsbarriärer kan du det!

Microsoft Teams, SharePoint online och OneDrive för företag inte kan hjälpa dig. Anta att [din prenumeration](#required-licenses-and-permissions) omfattar informationsbarriärer, en efterlevnadsadministratör eller en informationsbarriäradministratör kan definiera principer för att tillåta eller förhindra kommunikation mellan grupper av användare i Microsoft Teams. Informationsbarriärprinciper kan användas i situationer som dessa:

- Användare i daggruppen ska inte kommunicera eller dela filer med marknadsföringsteamet
- Ekonomipersonal som arbetar med konfidentiell företagsinformation ska inte kommunicera eller dela filer med vissa grupper inom organisationen
- Ett internt team med affärshemlighetsmaterial ska inte ringa eller chatta online med personer i vissa grupper inom organisationen
- En forskningsgrupp ska endast ringa eller chatta online med ett utvecklingsteam
- En webbplats för dag-grupp ska inte delas eller användas av någon utanför daggruppen

> [!IMPORTANT]
> Informationsbarriärer ***stöder endast** tvåvägsbegränsningar. Ett sätt begränsningar, t.ex. marknadsföring kan kommunicera och samarbeta med dag handlar, men dag handlar inte kan kommunicera och samarbeta med marknadsföring _*_stöds inte_**.

För alla dessa exempelscenarier (och mer) kan informationsbarriärprinciper definieras för att förhindra eller tillåta kommunikation och samarbete i Microsoft Teams, SharePoint Online och OneDrive. Sådana principer kan förhindra att personer ringer eller chattar med de som de inte borde ha eller gör det möjligt för personer att bara kommunicera med vissa grupper i Microsoft Teams. Med principer för informationsbarriärer i praktiken, och när användare som omfattas av dessa principer försöker kommunicera och samarbeta med andra i Microsoft Teams utförs kontroller av SharePoint Online eller OneDrive för att förhindra (eller tillåta) kommunikation och samarbete (enligt informationsbarriärprinciper).

Mer information om användarupplevelsen med informationsbarriärer finns i:

- [Informationsbarriärer i Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Informationsbarriärer i SharePoint Online](/sharepoint/information-barriers)
- [Informationsbarriärer i OneDrive](/onedrive/information-barriers)

> [!IMPORTANT]
> För närvarande gäller inte informationsbarriärer för e-postkommunikation. Dessutom är informationsbarriärer oberoende [av efterlevnadsgränser.](set-up-compliance-boundaries.md)<p> Innan du definierar och tillämpar principer för informationsbarriärer bör du kontrollera att din [organisation inte Exchange adressboksprinciper](/exchange/address-books/address-book-policies/address-book-policies) i praktiken. (Informationsbarriärer baseras på adressboksprinciper.)

## <a name="what-happens-with-information-barriers"></a>Vad som händer med informationsbarriärer

När informationsbarriärprinciper finns kan personer som inte ska kommunicera eller dela filer med andra specifika användare inte hitta, välja, chatta eller ringa dessa användare. Om det finns informationsbarriärer utförs kontroller för att förhindra obehörig kommunikation och samarbete. 

Informationsbarriärer gäller för Microsoft Teams (chattar och kanaler), SharePoint Online och OneDrive. I Microsoft Teams kan informationsbarriärprinciper fastställa och förhindra följande typer av obehörig kommunikation:

- Söka efter en användare
- Lägga till en medlem i ett team
- Starta en chattsession med någon
- Starta en gruppchatt
- Bjuda in någon att ansluta till ett möte
- Dela en skärm
- Ringa ett samtal
- Dela en fil med en annan användare
- Åtkomst till fil via delningslänk

Om de berörda personerna ingår i en informationsbarriärpolicy för att förhindra aktiviteten kan de inte fortsätta. Dessutom kan alla som omfattas av informationsbarriärpolicyn blockeras från att kommunicera med andra i Microsoft Teams. När personer som påverkas av informationsbarriärer ingår i samma team eller gruppchatt kan de tas bort från chattsessionerna och det är inte tillåtet att kommunicera vidare med gruppen.

Mer information om användarupplevelsen med informationsbarriärer finns i [informationsbarriärer i Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams).

I SharePoint online OneDrive företag avgör och förhindrar informationsbarriärsprinciper följande typer av obehöriga samarbeten:

- Lägga till en medlem på en webbplats
- Åtkomst till webbplats eller innehåll för en användare
- Dela webbplats eller innehåll med en annan användare
- Söka på en webbplats

Mer information om användarupplevelsen med informationsbarriärer finns i [informationsbarriärer i SharePoint Online](/sharepoint/information-barriers)

## <a name="required-licenses-and-permissions"></a>Licenser och behörigheter som krävs

Informationsbarriärer lanseras nu och ingår i prenumerationer som:

- Microsoft 365 E5/A5
- Office 365 E5/A5
- Office 365 Advanced Compliance
- Microsoft 365 Efterlevnad E5/A5
- Microsoft 365 Insider-riskhantering

Mer information finns i [vägledningen Microsoft 365 om licensiering för säkerhet och & regelefterlevnad.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)

Du [måste tilldelas en av](information-barriers-policies.md)följande roller för att definiera eller redigera principer för informationsbarriärer:

- Microsoft 365 global administratör
- Office 365 global administratör
- Efterlevnadsadministratör
- IB-efterlevnadshantering

(Mer information om roller och behörigheter finns i [Behörigheter i Office 365 för & kompatibilitetscenter](../security/defender-365-security/permissions-in-the-security-and-compliance-center.md).)

Du måste vara bekant med PowerShell-cmdlets för att kunna definiera, verifiera eller redigera principer för informationsbarriärer. Vi tillhandahåller flera exempel på [PowerShell-cmdlets](information-barriers-policies.md)i vår artikel , men du behöver känna till annan information, till exempel parametrar, för organisationen.

## <a name="next-steps"></a>Nästa steg

- [Läs mer om informationsbarriärer i Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Läs mer om informationsbarriärer i SharePoint Online](/sharepoint/information-barriers)
- [Läs mer om informationsbarriärer i OneDrive](/onedrive/information-barriers)
- [Se vilka attribut som kan användas för informationsbarriärer](information-barriers-attributes.md)
- [Definiera principer för informationsbarriärer](information-barriers-policies.md)
- [Redigera (eller ta bort) informationsbarriärpolicyer](information-barriers-edit-segments-policies.md)