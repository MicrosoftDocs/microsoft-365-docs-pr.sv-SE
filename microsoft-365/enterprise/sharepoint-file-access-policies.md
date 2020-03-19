---
title: Rekommenderade principer för säkra dokument – Microsoft 365 Enterprise | Microsoft-dokument
description: I artikeln beskrivs principerna för Microsofts rekommendationer om hur du skyddar SharePoint-filåtkomst.
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
ms.openlocfilehash: d11b2682b9699e61a4c9ecfa47eb73de87de5e4f
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811103"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Principrekommendationer för att skydda SharePoint-webbplatser och -filer

I den här artikeln beskrivs hur du implementerar de rekommenderade principerna för identitet och enhetsåtkomst för att skydda SharePoint Online och OneDrive för företag. Den här vägledningen bygger på principerna [för gemensam identitet och enhetsåtkomst](identity-access-policies.md).

Dessa rekommendationer baseras på tre olika säkerhets- och skyddsnivåer för SharePoint-filer som kan tillämpas baserat på dina behovs kornighet: **baslinje,** **känslig**och **starkt reglerad**. Du kan läsa mer om dessa säkerhetsnivåer och de rekommenderade klientoperativsystemen, som refereras av dessa rekommendationer i [översikten](microsoft-365-policies-configurations.md).

Förutom att implementera den här vägledningen måste du konfigurera SharePoint-webbplatser med rätt mängd skydd, inklusive att ange lämpliga behörigheter för känsligt och starkt reglerat innehåll. Mer information om hur du skapar webbplatser för baslinje, känsligt och starkt reglerat skydd finns i Webbplatser och filer för [Säker SharePoint Online](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files).

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Uppdatera vanliga principer så att de inkluderar SharePoint och OneDrive för företag

I följande diagram visas en uppsättning rekommenderade principer för att skydda filer i SharePoint Online och OneDrive för företag. Den anger vilka principer som ska uppdateras eller nyligen skapas för att lägga till skydd för SharePoint Online och OneDrive för företag.

![Sammanfattning av principer för SharePoint Online och OneDrive](../media/identity-access-ruleset-sharepoint.png)

Om du inkluderade SharePoint Online när du skapade de gemensamma principerna behöver du bara skapa de nya principerna. När du konfigurerar regler för villkorlig åtkomst innehåller SharePoint Online OneDrive för företag.

De nya principerna implementerar enhetsskydd för känsligt och starkt reglerat innehåll genom att tillämpa specifika åtkomstkrav på SharePoint-webbplatser som du anger.

I följande tabell visas de principer som du antingen behöver granska och uppdatera eller skapa nya för SharePoint Online. De vanliga principerna länkar till tillhörande konfigurationsinstruktioner i artikeln [Gemensamma identitets- och enhetsåtkomstprinciper.](identity-access-policies.md)

|Skyddsnivå|Politik|Mer information|
|:---------------|:-------|:----------------|
|**Originalplan**|[Kräv MFA när inloggningsrisken är *medelhög* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inkludera SharePoint Online i tilldelningen av molnappar|
|        |[Blockera klienter som inte stöder modern autentisering](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Inkludera SharePoint Online i tilldelningen av molnappar|
|        |[Definiera principer för appskydd](identity-access-policies.md#define-app-protection-policies)|Se till att alla rekommenderade appar ingår i listan över appar. Var noga med att uppdatera principen för varje plattform (iOS, Android, Windows)|
|        |[Kräv kompatibla datorer](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Inkludera SharePoint Online i listan över molnappar|
|        |[Använda begränsningar för apppåstvingade i SharePoint Online](#use-app-enforced-restrictions-in-sharepoint-online)|Lägg till den här nya principen. Detta talar om för Azure AD att använda de inställningar som anges i SharePoint Online. Den här regeln gäller för alla användare, men påverkar bara åtkomsten till webbplatser som ingår i SharePoint Online-åtkomstprinciper|
|**Känsliga**|[Kräv MFA när inloggningsrisken är *låg,* *medelhög* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inkludera SharePoint Online i tilldelningar av molnappar|
|         |[Kräv kompatibla datorer *och* mobila enheter](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Inkludera SharePoint Online i listan över molnappar|
||[Åtkomstkontrollprincip för SharePoint Online:](#sharepoint-online-access-control-policies)Tillåt åtkomst endast för webbläsare till specifika SharePoint-webbplatser från ohanterade enheter|Detta förhindrar redigering och hämtning av filer. Använda PowerShell för att ange platser|
|**Starkt reglerad**|[*Kräver alltid* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inkludera SharePoint Online i tilldelningen av molnappar|
||[Åtkomstkontrollprincip för SharePoint Online:](#use-app-enforced-restrictions-in-sharepoint-online)Blockera åtkomst till specifika SharePoint-webbplatser från ohanterade enheter|Använda PowerShell för att ange platser|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a>Använda begränsningar för appadvingande i SharePoint Online

Om du implementerar åtkomstkontroller i SharePoint Online måste du skapa den här princip för villkorlig åtkomst i Azure AD för att be Azure AD att tillämpa principerna som du konfigurerar i SharePoint Online. Den här regeln gäller för alla användare, men påverkar bara åtkomsten till de webbplatser som du anger med PowerShell när du skapar åtkomstkontrollerna i SharePoint Online.

Information om hur du konfigurerar den här principen finns i "Blockera eller begränsa åtkomsten till specifika SharePoint-webbplatssamlingar eller OneDrive-konton" i den här artikeln: [Kontrollera åtkomsten från ohanterade enheter](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).

## <a name="sharepoint-online-access-control-policies"></a>Principer för åtkomstkontroll för SharePoint Online

Microsoft rekommenderar att du skyddar innehåll på SharePoint-webbplatser med känsligt och starkt reglerat innehåll med kontroller för enhetsåtkomst. Du gör detta genom att skapa en princip som anger skyddsnivån och de platser som ska användas på.

- Känsliga webbplatser: Tillåt åtkomst endast för webbläsare. Detta hindrar användare från att redigera och hämta filer.
- Starkt reglerade platser: Blockera åtkomst från ohanterade enheter.

Se Blockera eller begränsa åtkomsten till specifika SharePoint-webbplatssamlingar eller OneDrive-konton i den här artikeln: [Kontrollera åtkomsten från ohanterade enheter](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).

## <a name="how-these-policies-work-together"></a>Hur dessa policyer fungerar tillsammans

Det är viktigt att förstå att SharePoint-webbplatsbehörigheter vanligtvis baseras på affärsbehov för åtkomst till webbplatser. Dessa behörigheter hanteras av webbplatsägare och kan vara mycket dynamiska. Genom att använda SharePoint-principer för enhetsåtkomst säkerställer skyddet för dessa platser, oavsett om användare har tilldelats en Azure AD-grupp som är associerad med baslinje, känslig eller starkt reglerad skydd.

Följande bild är ett exempel på hur åtkomstprinciper för SharePoint-enheter skyddar åtkomsten till webbplatser.

![Så här skyddar SharePoint-principer för enhetsåtkomstwebbplatser webbplatser](../media/SharePoint-rules-scenario.png)

I bilden:

- James tilldelas principer för villkorlig åtkomst som är associerade med baslinjeskydd, men han kan få åtkomst till SharePoint-webbplatser som är associerade med känsligt eller starkt reglerat skydd.
- Om James kommer åt en känslig eller starkt reglerad webbplats han är medlem i att använda sin dator, är hans tillgång beviljas så länge hans dator är kompatibel.
- Om James kommer åt en känslig webbplats som han är medlem i att använda sin ohanterade telefon, vilket är tillåtet för baslinjeanvändare, får han endast åtkomst till den känsliga webbplatsen på grund av enhetsåtkomstprincipen som konfigurerats för den här webbplatsen.
- Om James kommer åt en starkt reglerad webbplats han är medlem i att använda sin ohanterade telefon, kommer han att blockeras på grund av åtkomstprincipen konfigureras för denna webbplats. Han kan bara komma åt denna webbplats med hjälp av sin hanterade och kompatibla dator.

## <a name="next-steps"></a>Nästa steg

[Säkra SharePoint Online-webbplatser och -filer](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)
