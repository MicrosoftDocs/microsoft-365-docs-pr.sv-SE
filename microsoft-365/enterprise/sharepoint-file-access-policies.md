---
title: Rekommenderade principer för säkra dokument – Microsoft 365 för företag | Microsoft-dok
description: Beskriver policyerna för Microsoft-rekommendationer om hur du skyddar åtkomst till SharePoint-filer.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 1c6cdc626b31a486b8858efcff76480d31769740
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547836"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Policy rekommendationer för att skydda SharePoint-webbplatser och-filer

I den här artikeln beskrivs hur du implementerar Rekommenderad identitet och enhets åtkomst principer för att skydda SharePoint och OneDrive för företag. Den här vägledningen bygger på [vanliga principer för identitets-och enhets åtkomst](identity-access-policies.md).

De här rekommendationerna bygger på tre olika nivåer av säkerhet och skydd för SharePoint-filer som kan användas baserat på hur olika behov fungerar: **original plan**, **känslig**och **högreglerad**. Du kan läsa mer om de här säkerhets nivåerna och de rekommenderade klient operativ systemen som hänvisas till av de här rekommendationerna i [översikten](microsoft-365-policies-configurations.md).

Förutom att implementera den här vägledningen måste du konfigurera SharePoint-webbplatser med rätt skydds nivå, inklusive att ange lämpliga behörigheter för känslig och hög reglerad information.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Uppdatera gemensamma principer för att inkludera SharePoint och OneDrive för företag

För att skydda filer i SharePoint och OneDrive illustrerar följande diagram vilka principer som ska uppdateras från principer för åtkomst för identitet och enheter.

[![Sammanfattning av princip uppdateringar för att skydda åtkomst till team och dess beroende tjänster](../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

[Visa en större version av bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

Om du har inkluderat SharePoint när du skapade de gemensamma policyerna behöver du bara skapa de nya principerna. För principer för villkorsstyrd åtkomst inkluderar SharePoint OneDrive.

De nya principerna implementerar enhets skydd för känsligt och starkt reglerat innehåll genom att använda specifika åtkomst krav på SharePoint-webbplatser som du anger.

I följande tabell visas de principer som du måste granska och uppdatera eller skapa en ny för SharePoint. Gemensamma principer-länken till de associerade konfigurations anvisningarna i artikeln om [principer för åtkomst policys för identitet och enheter](identity-access-policies.md) .

|Skydds nivå|Principerna|Mer information|
|:---------------|:-------|:----------------|
|**Grundläggande**|[Kräv MFA när en inloggnings risk är *mellan* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inkludera SharePoint i tilldelningen av Cloud-appar.|
|        |[Blockera klienter som inte har stöd för modern autentisering](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Inkludera SharePoint i tilldelningen av Cloud-appar.|
|        |[Tillämpa program data skydds policy](identity-access-policies.md#apply-app-data-protection-policies)|Se till att alla rekommenderade appar ingår i listan med program. Se till att uppdatera policyn för varje plattform (iOS, Android, Windows).|
|        |[Kräv kompatibla PC-datorer](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Ta med SharePoint i listan med moln program.|
|        |[Använda tvingande program begränsningar i SharePoint](#use-app-enforced-restrictions-in-sharepoint)|Lägg till den här nya principen. Detta meddelar Azure Active Directory (Azure AD) att använda inställningarna i SharePoint. Den här principen gäller för alla användare, men påverkar bara åtkomst till webbplatser som ingår i SharePoint Access-principer.|
|**Känslig**|[Kräv MFA när en inloggnings risk är *låg*, *medium* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inkludera SharePoint i tilldelningarna för molnappar.|
|         |[Kräv kompatibla datorer *och* mobila enheter](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Ta med SharePoint i listan med moln program.|
||[Kontroll policy för SharePoint-åtkomst](#sharepoint-access-control-policies): Tillåt åtkomst via webbläsare till specifika SharePoint-webbplatser från ohanterade enheter.|Detta förhindrar redigering och nedladdning av filer. Använd PowerShell för att ange webbplatser.|
|**Strikt reglerad**|[Kräv *alltid* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inkludera SharePoint i tilldelningen av Cloud-appar.|
||[Åtkomst kontroll princip för SharePoint](#use-app-enforced-restrictions-in-sharepoint): blockera åtkomst till specifika SharePoint-webbplatser från ohanterade enheter.|Använd PowerShell för att ange webbplatser.|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>Använd program begränsningar i SharePoint

Om du implementerar Access-kontroller i SharePoint måste du skapa den här principen för villkorsstyrd åtkomst i Azure AD för att Azure AD ska kunna använda de principer du konfigurerar i SharePoint. Den här principen gäller för alla användare, men påverkar bara åtkomst till de webbplatser som du anger med PowerShell när du skapar Access-kontroller i SharePoint.

Om du vill konfigurera den här principen kan du läsa "blockera eller begränsa åtkomst till specifika SharePoint-webbplats samlingar eller OneDrive-konton" i [kontrol lera åtkomst från ohanterade enheter](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).

## <a name="sharepoint-access-control-policies"></a>Åtkomst kontroll principer för SharePoint

Microsoft rekommenderar att du skyddar innehåll på SharePoint-webbplatser med känsligt och starkt reglerat innehåll med enhets åtkomst kontroller. Det gör du genom att skapa en princip som anger nivån på skyddet och webbplatserna som skyddar mot.

- Känsliga webbplatser: Tillåt åtkomst via webbläsare. Detta förhindrar att användare redigerar och laddar ned filer.
- Högreglerade webbplatser: blockera åtkomst från ohanterade enheter.

Se "blockera eller begränsa åtkomst till specifika SharePoint-webbplats samlingar eller OneDrive-konton" i [kontrol lera åtkomst från ohanterade enheter](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).

## <a name="how-these-policies-work-together"></a>Hur dessa principer fungerar tillsammans

Det är viktigt att förstå att SharePoint-webbplatsens behörigheter normalt baseras på affärs behov för åtkomst till webbplatser. Dessa behörigheter hanteras av webbplats ägare och kan vara mycket dynamiska. Genom att använda åtkomst principer för SharePoint-enheter skyddas de här webbplatserna, oavsett om användare är tilldelade till en Azure AD-grupp som är kopplad till original-, känsligt-eller starkt reglerat skydd.

Följande bild visar ett exempel på hur åtkomst principer för SharePoint-enheter skyddar åtkomst till webbplatser för en användare.

[![Exempel på hur åtkomst principer för SharePoint-enheter skyddar webbplatser](../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

[Visa en större version av bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

Jonas har grundläggande principer för villkorsstyrd åtkomst, men han kan få åtkomst till SharePoint-webbplatser med känsligt och starkt reglerat skydd.

- Om Johan har åtkomst till en känslig eller högreglerad webbplats han är medlem i sin dator, ges hans åtkomst så länge datorn är kompatibel.
- Om Jonas öppnar en känslig webbplats han är medlem i att använda sin ohanterade telefon, som är tillåten för bas linje användare, får han eller hon skrivskyddad åtkomst till den känsliga webbplatsen på grund av enhets åtkomst principen som har kon figurer ATS för den här webbplatsen.
- Om Johan har åtkomst till en högreglerad webbplats som han är medlem i med sin ohanterade telefon kommer han att blockeras på grund av åtkomst principen som har kon figurer ATS för den här webbplatsen. Han kan bara komma åt den här webbplatsen via sin hanterade och kompatibla dator.

## <a name="next-step"></a>Nästa steg

![Steg 4: principer för Microsoft 365-molnappar](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Konfigurera principer för villkorsstyrd åtkomst för:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)

