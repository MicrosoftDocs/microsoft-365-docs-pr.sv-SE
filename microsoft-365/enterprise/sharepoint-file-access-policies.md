---
title: Rekommenderade principer för säker dokument – Microsoft 365 Enterprise | Microsoft-dok
description: Beskriver policyerna för Microsoft-rekommendationer om hur du skyddar åtkomst till SharePoint-filer.
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.date: 06/07/2018
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 784a4d617d74916ae7b0ec4b431cc298ce45531e
ms.sourcegitcommit: d6b641d0ef92f4176da9f4a98d3d5aa3d4f2e184
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/11/2020
ms.locfileid: "46617192"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Policy rekommendationer för att skydda SharePoint-webbplatser och-filer

I den här artikeln beskrivs hur du implementerar Rekommenderad identitet och enhets åtkomst principer för att skydda SharePoint Online och OneDrive för företag. Den här vägledningen bygger på [vanliga principer för identitets-och enhets åtkomst](identity-access-policies.md).

De här rekommendationerna bygger på tre olika nivåer av säkerhet och skydd för SharePoint-filer som kan användas baserat på hur olika behov fungerar: **original plan**, **känslig**och **högreglerad**. Du kan läsa mer om de här säkerhets nivåerna och de rekommenderade klient operativ systemen som hänvisas till av de här rekommendationerna i [översikten](microsoft-365-policies-configurations.md).

Förutom att implementera den här vägledningen måste du konfigurera SharePoint-webbplatser med rätt skydds nivå, inklusive att ange lämpliga behörigheter för känslig och hög reglerad information.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Uppdatera gemensamma principer för att inkludera SharePoint och OneDrive för företag

I följande diagram visas den uppsättning rekommenderade principer för att skydda filer i SharePoint Online och OneDrive för företag. Det visar vilka principer som ska uppdateras eller nyskapas för att skydda SharePoint Online och OneDrive för företag.

[![Översikt över principer för SharePoint Online och OneDrive ](../media/identity-access-ruleset-sharepoint.png)](../media/identity-access-ruleset-sharepoint.png#lightbox)

Om du har inkluderat SharePoint Online när du skapade de gemensamma principerna behöver du bara skapa de nya principerna. När du konfigurerar regler för villkorlig åtkomst inkluderar SharePoint Online OneDrive för företag.

De nya principerna implementerar enhets skydd för känsligt och starkt reglerat innehåll genom att använda specifika åtkomst krav på SharePoint-webbplatser som du anger.

I följande tabell visas de principer som du måste granska och uppdatera eller skapa en ny för SharePoint Online. Gemensamma principer-länken till de associerade konfigurations anvisningarna i artikeln om [principer för åtkomst policys för identitet och enheter](identity-access-policies.md) .

|Skydds nivå|Principerna|Mer information|
|:---------------|:-------|:----------------|
|**Grundläggande**|[Kräv MFA när en inloggnings risk är *mellan* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inkludera SharePoint Online i tilldelning av moln program|
|        |[Blockera klienter som inte har stöd för modern autentisering](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Inkludera SharePoint Online i tilldelning av moln program|
|        |[Tillämpa program data skydds policy](identity-access-policies.md#apply-app-data-protection-policies)|Se till att alla rekommenderade appar ingår i listan med program. Se till att uppdatera policyn för varje plattform (iOS, Android, Windows)|
|        |[Kräv kompatibla PC-datorer](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Inkludera SharePoint Online i listan över moln program|
|        |[Använda program begränsningar i SharePoint Online](#use-app-enforced-restrictions-in-sharepoint-online)|Lägg till den här nya principen. Detta meddelar Azure AD att använda inställningarna i SharePoint Online. Den här regeln gäller för alla användare, men påverkar bara åtkomst till webbplatser som ingår i SharePoint Online-åtkomst principer|
|**Känslig**|[Kräv MFA när en inloggnings risk är *låg*, *medium* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inkludera SharePoint Online i tilldelningarna av moln program|
|         |[Kräv kompatibla datorer *och* mobila enheter](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Ta med SharePoint Online i listan med moln program|
||[Åtkomst kontroll princip för SharePoint Online](#sharepoint-online-access-control-policies): Tillåt åtkomst via webbläsare för vissa SharePoint-webbplatser från ohanterade enheter|Detta förhindrar redigering och nedladdning av filer. Använda PowerShell för att ange webbplatser|
|**Strikt reglerad**|[Kräv *alltid* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inkludera SharePoint Online i tilldelning av moln program|
||[Åtkomst kontroll princip för SharePoint Online](#use-app-enforced-restrictions-in-sharepoint-online): blockera åtkomst till specifika SharePoint-webbplatser från ohanterade enheter|Använda PowerShell för att ange webbplatser|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a>Använd program begränsningar i SharePoint Online

Om du implementerar åtkomst kontroller i SharePoint Online måste du skapa den här principen för villkorsstyrd åtkomst i Azure AD för att Azure AD ska kunna använda de principer du konfigurerar i SharePoint Online. Den här regeln gäller för alla användare, men påverkar bara åtkomst till de webbplatser som du anger med PowerShell när du skapar Access-kontroller i SharePoint Online.

Om du vill konfigurera den här principen kan du läsa "blockera eller begränsa åtkomst till specifika SharePoint-webbplatssamling eller OneDrive-konton" i den här artikeln: [kontrol lera åtkomst från ohanterade enheter](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).

## <a name="sharepoint-online-access-control-policies"></a>Åtkomst kontroll principer för SharePoint Online

Microsoft rekommenderar att du skyddar innehåll på SharePoint-webbplatser med känsligt och starkt reglerat innehåll med enhets åtkomst kontroller. Det gör du genom att skapa en princip som anger nivån på skyddet och webbplatserna som skyddar mot.

- Känsliga webbplatser: Tillåt åtkomst via webbläsare. Detta förhindrar att användare redigerar och laddar ned filer.
- Högreglerade webbplatser: blockera åtkomst från ohanterade enheter.

Se "blockera eller begränsa åtkomst till specifika SharePoint-webbplats samlingar eller OneDrive-konton" i den här artikeln: [kontrol lera åtkomst från ohanterade enheter](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).

## <a name="how-these-policies-work-together"></a>Hur dessa principer fungerar tillsammans

Det är viktigt att förstå att SharePoint-webbplatsens behörigheter normalt baseras på affärs behov för åtkomst till webbplatser. Dessa behörigheter hanteras av webbplats ägare och kan vara mycket dynamiska. Genom att använda åtkomst principer för SharePoint-enheter skyddas de här webbplatserna, oavsett om användare är tilldelade till en Azure AD-grupp som är kopplad till original-, känsligt-eller starkt reglerat skydd.

Följande bild visar ett exempel på hur åtkomst principer för SharePoint-enheter skyddar åtkomst till webbplatser.

[![Så här skyddas webbplatser ](../media/SharePoint-rules-scenario.png) med åtkomst principer för SharePoint-enheter](../media/SharePoint-rules-scenario.png#lightbox)

På bilden:

- Jonas är tilldelad till principer för villkorlig åtkomst som är kopplade till original planens skydd, men han kan få åtkomst till SharePoint-webbplatser som är kopplade till känsligt eller starkt reglerat skydd.
- Om Johan har åtkomst till en känslig eller högreglerad webbplats han är medlem i sin dator, ges hans åtkomst så länge datorn är kompatibel.
- Om Jonas öppnar en känslig webbplats han är medlem i att använda sin ohanterade telefon, som är tillåten för bas linje användare, får han eller hon skrivskyddad åtkomst till den känsliga webbplatsen på grund av enhets åtkomst principen som har kon figurer ATS för den här webbplatsen.
- Om Johan har åtkomst till en högreglerad webbplats som han är medlem i med sin ohanterade telefon kommer han att blockeras på grund av åtkomst principen som har kon figurer ATS för den här webbplatsen. Han kan bara komma åt den här webbplatsen via sin hanterade och kompatibla dator.


