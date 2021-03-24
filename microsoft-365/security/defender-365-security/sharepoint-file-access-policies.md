---
title: Rekommenderade principer för säkra dokument – Microsoft 365 för företag | Microsoft Docs
description: Här beskrivs principer för Microsofts rekommendationer om hur du skyddar SharePoint-filåtkomst.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 1771f71e444233ffce60a4a56273d3062fe8b70d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072506"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Principrekommendationer för att skydda SharePoint-webbplatser och -filer

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- SharePoint Online 


I den här artikeln beskrivs hur du implementerar rekommenderade principer för identitet och enhetsåtkomst för att skydda SharePoint och OneDrive för företag. Den här vägledningen bygger på de [gemensamma principerna för identitet och enhetsåtkomst.](identity-access-policies.md)

Dessa rekommendationer baseras på tre olika nivåer av säkerhet och skydd för SharePoint-filer som kan tillämpas utifrån dina behovs granularitet: **baslinje** **,** känslig och **mycket reglerad**. Du kan läsa mer om dessa säkerhetsnivåer och de rekommenderade klientoperativsystemet, som refereras av dessa rekommendationer i [översikten.](microsoft-365-policies-configurations.md)

Förutom att implementera denna vägledning ska du se till att konfigurera SharePoint-webbplatser med rätt skyddsnivå, inklusive att ange lämpliga behörigheter för känsligt och starkt reglerat innehåll.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Uppdatera vanliga principer så att de omfattar SharePoint och OneDrive för företag

I följande diagram visas vilka principer som ska uppdateras från de gemensamma principerna för identitets- och enhetsåtkomst för att skydda filer i SharePoint och OneDrive.

[![Sammanfattning av principuppdateringar för att skydda åtkomsten till Teams och dess beroende tjänster](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

Om du inkluderade SharePoint när du skapade de gemensamma principerna behöver du bara skapa de nya principerna. För villkorsstyrda åtkomstprinciper inkluderar SharePoint OneDrive.

Med de nya principerna implementeras enhetsskydd för känsligt och starkt reglerat innehåll genom att specifika åtkomstkrav tillämpas på SharePoint-webbplatser som du anger.

I följande tabell finns de principer som du antingen behöver granska och uppdatera eller skapa nya för SharePoint. De vanliga principerna länkar till de associerade konfigurationsanvisningarna i [artikeln Principer för enhetsåtkomst och identiteter.](identity-access-policies.md)

|Skyddsnivå|Principer|Mer information|
|---|---|---|
|**Grundläggande**|[Kräv MFA när inloggningsrisken är *medium* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inkludera SharePoint i tilldelningen av molnappar.|
||[Blockera klienter som inte har stöd för modern autentisering](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Inkludera SharePoint i tilldelningen av molnappar.|
||[Använda principer för APP-dataskydd](identity-access-policies.md#apply-app-data-protection-policies)|Se till att alla rekommenderade appar finns med i listan med appar. Se till att uppdatera principen för varje plattform (iOS, Android, Windows).|
||[Kräv kompatibla PC-datorer](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Ta med SharePoint i listan över molnappar.|
||[Använda appanvändningsbegränsningar i SharePoint](#use-app-enforced-restrictions-in-sharepoint)|Lägg till den här nya principen. Det innebär att Azure Active Directory (Azure AD) använder inställningarna som anges i SharePoint. Den här principen gäller för alla användare, men påverkar bara åtkomsten till webbplatser som ingår i SharePoint-åtkomstprinciper.|
|**Känslig**|[Kräv MFA när inloggningsrisken är *låg,* *medelstor* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Ta med SharePoint i uppgifterna för molnappar.|
||[Kräv kompatibla datorer *och* mobila enheter](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Ta med SharePoint i listan med molnappar.|
||[Princip för åtkomstkontroll i SharePoint:](#sharepoint-access-control-policies)Tillåt åtkomst endast till vissa SharePoint-webbplatser från ohanterade enheter.|Det förhindrar redigering och nedladdning av filer. Använd PowerShell för att ange webbplatser.|
|**Strikt reglerad**|[*Kräv* alltid MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inkludera SharePoint i tilldelningen av molnappar.|
||[Princip för åtkomstkontroll i SharePoint:](#use-app-enforced-restrictions-in-sharepoint)Blockera åtkomst till vissa SharePoint-webbplatser från ohanterade enheter.|Använd PowerShell för att ange webbplatser.|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>Använda apptvingade begränsningar i SharePoint

Om du implementerar åtkomstkontroller i SharePoint måste du skapa den här villkorsstyrda åtkomstprincipen i Azure AD för att ange att Azure AD ska tillämpa principerna du konfigurerar i SharePoint. Den här principen gäller för alla användare, men påverkar bara åtkomsten till de webbplatser som du anger med PowerShell när du skapar åtkomstkontroller i SharePoint.

Information om hur du konfigurerar den här principen finns i "Blockera eller begränsa åtkomsten till specifika SharePoint-webbplatssamlingar eller OneDrive-konton" i Styra åtkomst från [ohanterade enheter.](/sharepoint/control-access-from-unmanaged-devices)

## <a name="sharepoint-access-control-policies"></a>Principer för åtkomstkontroll i SharePoint

Microsoft rekommenderar att du skyddar innehåll på SharePoint-webbplatser med känsligt och starkt reglerat innehåll med enhetsåtkomstkontroller. Det gör du genom att skapa en princip som anger skyddsnivån och webbplatserna som skyddet ska gälla för.

- Känsliga webbplatser: Tillåt åtkomst endast till webbläsare. Det förhindrar att användare redigerar och laddar ned filer.
- Starkt reglerade webbplatser: Blockera åtkomst från ohanterade enheter.

Läs "Blockera eller begränsa åtkomsten till specifika SharePoint-webbplatssamlingar eller OneDrive-konton" i Styra [åtkomst från ohanterade enheter.](/sharepoint/control-access-from-unmanaged-devices)

## <a name="how-these-policies-work-together"></a>Så här fungerar de här principerna tillsammans

Det är viktigt att förstå att SharePoint-webbplatsbehörigheter vanligtvis baseras på affärs behov av åtkomst till webbplatser. De här behörigheterna hanteras av webbplatsägare och kan vara mycket dynamiska. Genom att använda sharePoint-principer för enhetsåtkomst skyddas webbplatserna, oavsett om användare tilldelas till en Azure AD-grupp som är kopplad till grundläggande, känslig eller starkt reglerad skydd.

Följande bild visar ett exempel på hur åtkomstprinciper för SharePoint-enheter skyddar åtkomsten till webbplatser för en användare.

[![Exempel på hur åtkomstprinciper för SharePoint-enheter skyddar webbplatser](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

[Visa en större version av den här bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

James har grundläggande principer för villkorsstyrd åtkomst som tilldelats, men han kan ges åtkomst till SharePoint-webbplatser med känsligt eller starkt reglerat skydd.

- Om James använder en känslig eller starkt reglerad webbplats är han medlem i sin dator, men hans åtkomst beviljas så länge hans dator är kompatibel.
- Om James öppnar en känslig webbplats är han medlem i att använda sin ohanterade telefon, vilket är tillåtet för grundläggande användare, han kommer att få webbläsaråtkomst till den känsliga webbplatsen på grund av principen för enhetsåtkomst som konfigurerats för den här webbplatsen.
- Om James använder en hårt reglerad webbplats är han medlem i sin ohanterade telefon, så blockeras han på grund av åtkomstprincipen som konfigurerats för den här webbplatsen. Han kan bara komma åt den här webbplatsen på en hanterad och kompatibel dator.

## <a name="next-step"></a>Nästa steg

![Steg 4: Principer för Microsoft 365-molnappar](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Konfigurera principer för villkorsstyrd åtkomst för:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)