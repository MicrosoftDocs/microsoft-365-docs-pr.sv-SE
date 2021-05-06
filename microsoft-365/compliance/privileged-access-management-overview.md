---
title: Lär dig mer om privilegierad åtkomsthantering
description: Den här artikeln innehåller en översikt över hantering av privilegierad åtkomst i Microsoft 365, bland annat svar på vanliga frågor och svar.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
f1.keywords:
- NOCSH
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.openlocfilehash: 059e1653d7db9140dbc80fd69fe36e95a744b079
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "52161796"
---
# <a name="learn-about-privileged-access-management"></a>Lär dig mer om privilegierad åtkomsthantering

Med hantering av behörighetsbehörighet kan du få detaljerad åtkomstkontroll över administrativa uppgifter med Office 365. Det kan skydda organisationen från överträdelser som använder befintliga administratörskonton för privilegierad behörighet med stående åtkomst till känsliga data eller åtkomst till viktiga konfigurationsinställningar. Hantering av behörighet kräver att användare begär snabb åtkomst för att slutföra uppgifter med förhöjd och privilegierad behörighet via ett arbetsflöde med mycket begränsad och tidsbunden behörighet. Den här konfigurationen ger användarna precis tillräckligt många åtkomst för att utföra den tillgängliga uppgiften, utan att riskera exponering av känsliga data eller viktiga konfigurationsinställningar. Genom att aktivera hantering av Microsoft 365 åtkomst i Microsoft 365 kan organisationen arbeta utan några stående behörigheter och skydda sig mot säkerhetsproblem av administrativ åtkomst.

En snabb översikt över det integrerade Customer Lockbox-arbetsflödet och arbetsflödet för behörighetshantering finns i den här video om Customer Lockbox och [behörighetshantering för åtkomst.](https://go.microsoft.com/fwlink/?linkid=2066800)

## <a name="layers-of-protection"></a>Skyddslager

Hantering av privilegierad åtkomst kompletterar andra data- och åtkomstfunktionsskydd i den Microsoft 365 säkerhetsarkitekturen. Att ta med hantering av privilegierad åtkomst som en del av en integrerad och lagerberoende metod för säkerhet ger en säkerhetsmodell som maximerar skyddet av känslig information Microsoft 365 konfigurationsinställningar. Som visas i diagrammet bygger hantering av privilegierad åtkomst på skyddet som tillhandahålls med inbyggd kryptering av Microsoft 365-data och den rollbaserade säkerhetsmodellen för åtkomstkontroll Microsoft 365 tjänster. När de används [med Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure)ger de här två funktionerna åtkomstkontroll med direktåtkomst i olika omfattningar.

![Lagerskydd i Microsoft 365](../media/pam-layered-protection.png)

Hantering av privilegierad åtkomst definieras och omfattas på aktivitetsnivå, medan Azure AD Privileged Identity Management tillämpar skydd på **rollnivå** med möjlighet att köra flera aktiviteter.  Med Azure AD Privileged Identity Management det främst åtkomst för AD-roller och rollgrupper, medan hantering av privilegierad åtkomst i Microsoft 365 endast gäller på aktivitetsnivå.

- **Aktivera hantering av behörighet när du redan använder Azure AD-Privileged Identity Management:** Genom att lägga till hantering av privilegierad åtkomst får du en annan detaljerad skyddsnivå och granskningsfunktioner för behörighet att Microsoft 365 data.

- **Aktivera Azure AD-Privileged Identity Management medan du redan använder hantering av privilegierad åtkomst i Office 365:**  Om du lägger till Azure AD Privileged Identity Management till hantering av privilegierad åtkomst kan du utöka behörigheten till data utanför Microsoft 365 som främst definieras av användarroller eller identitet.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Arkitektur och processflöde för behörighetshantering

Vart och ett av följande processflöden sammanfattar arkitekturen för privilegierad åtkomst och hur den interagerar med Microsoft 365, granskning och Exchange Management-körningen.

### <a name="step-1-configure-a-privileged-access-policy"></a>Steg 1: Konfigurera en princip för privilegierad åtkomst

När du konfigurerar en princip för behörighetsbehörighet i [administrationscentret för Microsoft 365](https://admin.microsoft.com) eller Exchange Management PowerShell definierar du principen och funktionsprocesserna för behörighetsåtkomst och principattributen i Microsoft 365-administratören. Aktiviteterna loggas i &amp; Säkerhetsefterlevnadscenter. Principen är nu aktiverad och redo att hantera inkommande förfrågningar om godkännanden.

![Steg 1: Skapa princip](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Steg 2: Åtkomstbegäran

I Microsoft 365 [eller med PowerShell](https://admin.microsoft.com) för Exchange-hantering kan användarna begära åtkomst till uppgifter med förhöjd behörighet eller behörighet. Funktionen behörig åtkomst skickar begäran till användaren Microsoft 365 för bearbetning mot principen för konfigurerad behörighetsåtkomst och registrerar aktiviteten i loggarna för &amp; säkerhetsefterlevnadscenter.

![Steg 2: Åtkomstbegäran](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Steg 3: Åtkomstgodkännande

En begäran om godkännande skapas och meddelandet om väntande begäran skickas till godkännare via e-post. Om den godkänns bearbetas begäran om behörighet och uppgiften är klar att slutföras. Om du nekas blockeras uppgiften och ingen åtkomst ges till beställaren. Beställaren meddelas om begärans godkännande eller av nekande via e-postmeddelande.

![Steg 3: Åtkomstgodkännande](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Steg 4: Access-bearbetning

För en godkänd begäran bearbetas aktiviteten av Exchange Management Runspace. Godkännandet kontrolleras mot principen för behörighetsåtkomst och bearbetas av Microsoft 365 den. All aktivitet för uppgiften loggas i &amp; Säkerhetsefterlevnadscenter.

![Steg 4: Access-bearbetning](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>Vilka SKU:er kan använda behörighet i Office 365?

Hantering av privilegierad åtkomst är tillgänglig för kunder med ett brett Microsoft 365 och Office 365 och tillägg. Mer [information finns i Komma igång med hantering av privilegierad](privileged-access-management-configuration.md) åtkomst.

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>När har behörighet stöd för Office 365 arbetsbelastning utöver Exchange?

Hantering av privilegierad åtkomst blir tillgänglig i Office 365 arbetsbelastningar snart. Gå till [Microsoft 365 översikt](https://www.microsoft.com/microsoft-365/roadmap) för mer information.

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>Min organisation behöver mer än 30 principer för behörighetsåtkomst, kommer den här gränsen att ökas?

Ja, det finns en översikt över funktioner att höja den aktuella gränsen på 30 behöriga åtkomstprinciper per organisation.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>Måste jag vara global administratör för att hantera behörighet i Office 365?

Nej, du behöver rollen Exchange rollhantering tilldelad till konton som hanterar privilegierad åtkomst i Office 365. Om du inte vill konfigurera rollhanteringsrollen som en fristående kontobehörighet, innehåller rollen Global administratör den här rollen som standard och kan hantera behörighet. Användare som ingår i en godkännaregrupp behöver inte vara globala administratörer eller ha rollhanteringsrollen tilldelad till att granska och godkänna förfrågningar med PowerShell.

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a>Hur är hantering av privilegierad åtkomst relaterad till Customer Lockbox?

[Customer Lockbox](/office365/admin/manage/customer-lockbox-requests) ger en nivå av åtkomstkontroll för organisationer när Microsoft har åtkomst till data. Med hantering av behörighetsbehörigheter får du en detaljerad åtkomstkontroll inom en organisation för Microsoft 365 aktiviteter med behörighet.

## <a name="ready-to-get-started"></a>Är du redo att börja?

Börja [konfigurera organisationen för hantering av privilegierad åtkomst.](privileged-access-management-configuration.md)

## <a name="learn-more"></a>Mer information

[Interaktiv guide: Övervaka och kontrollera administratörsuppgifter med behörighetshantering](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
