---
title: Justera inställningarna efter registrering
description: Så här utesluter du vissa Microsoft-konton
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e78f0123c909c90ff90be913e8775cc1e5b30313
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777105"
---
# <a name="adjust-settings-after-enrollment"></a>Justera inställningarna efter registrering

När du är klar med registreringen på Microsoft Managed Desktop måste du justera de inställningar för Microsoft Intune och Azure Active Directory (Azure AD) som anges i den här artikeln för att tillåta hantering och underhåll av säkerhet. Ange följande inställningar för att exkludera specifika Azure AD-grupper som innehåller Microsoft Managed Desktop-enheter och-användare. Anvisningar för hur du exkluderar grupper finns i [villkorlig åtkomst: användare och grupper](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users).

> [!NOTE]
> Om du gör några ändringar efter registrering till principer i Microsoft Intune, Azure Active Directory eller Microsoft 365 kan det hända att Microsoft Managed Desktop slutar fungera korrekt. För att undvika problem med Microsoft Managed Station ära datorer kontrollerar du de specifika inställningarna som beskrivs i [åtgärda problem som upptäckts av verktyget för utvärdering av beredskap](../get-ready/readiness-assessment-fix.md) innan du ändrar några principer.


## <a name="microsoft-intune-settings"></a>Microsoft Intune-inställningar

- Distributions profil för automatisk pilot: för autopilot-profiler som skapas av administratörer på ditt företag utesluter du den **moderna arbets ytans enheter-alla** Azure AD-grupper. Anvisningar finns i [registrera Windows-enheter i Intune med hjälp av Windows autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot). Uteslut inte den **moderna arbets ytans enheter-alla** Azure AD-grupper från alla distributions principer som skapats av Microsoft Managed Desktop med "modern arbets plats" i namnet (till exempel den **moderna arbets platsen autopilot-profil**). 
- Principer för villkorsstyrd åtkomst: för principer för villkorlig åtkomst som skapas av administratörer i ditt företag utesluter du den **moderna arbets plats tjänstens konton** Azure AD-grupp. Anvisningar finns i [villkorlig åtkomst: användare och grupper](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups). Uteslut inte den **moderna arbets ytans enheter-alla** Azure AD-grupper från alla principer som har skapats av Microsoft Managed Desktop med "modern arbets plats" i namnet (till exempel **modern arbets plats säker arbets Station**).
- Multifaktorautentisering: kontrol lera att alla villkorsstyrda åtkomst principer som skapas av administratörer i ditt företag som kräver multifaktorautentisering exkluderar den **moderna arbets plats tjänstens konton** Azure AD-grupp. Mer information finns i [principer för villkorsstyrd åtkomst](../get-ready/readiness-assessment-fix.md#conditional-access-policies) och [villkorsstyrd åtkomst: Kräv MFA för alla användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).
- Säkerhets bas linje: för principer för säkerhets rikt linjer som skapas av administratörer i ditt företag, exkluderar du den **moderna arbets ytans enheter-alla**  Azure AD-grupper. Anvisningar finns i [använda säkerhets bas linjer för att konfigurera Windows 10-enheter i Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines). Uteslut inte den **moderna arbets ytans enheter-alla** Azure AD-grupper från alla principer som skapas av Microsoft Managed Desktop med "modern arbets plats" i namnet (till exempel **modern arbets plats säkerhet**).
- Uppdaterings samtal för Windows 10: för Windows 10 Update ring-principer som skapas av administratörer på ditt företag utesluter du den **moderna arbets ytans enheter-alla**  Azure AD-grupper. Anvisningar finns i [hantera program uppdateringar för Windows 10 i Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure). Uteslut inte den **moderna arbets ytans enheter-alla** Azure AD-grupper från alla principer som skapas av Microsoft Managed Desktop med "modern arbets plats" i namnet (till exempel den **moderna arbets plats uppdaterings** policyn).


## <a name="azure-active-directory-settings"></a>Azure Active Directory-inställningar

Själv återställning av lösen ord: Välj den **valda** inställningen och välj sedan **moderna arbets plats enheter-alla** Azure AD-grupper. Mer information finns i [själv studie kursen: Låt användare låsa upp sina konton eller återställa lösen ord med hjälp av återställning av Azure Active Directory Self-Service](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Steg för att komma igång med Microsoft Managed Desktop

1. [Lägga till och verifiera administratörskontakter i administratörsportalen](add-admin-contacts.md)
2. Justera inställningar efter registrering (den här artikeln)
3. [Koppla licenser](assign-licenses.md)
4. [Distribuera Intune-företagsportalen](company-portal.md)
5. [Aktivera Enterprise State Roaming](enterprise-state-roaming.md)
6. [Konfigurera enheter](set-up-devices.md)
7. [Gör användarna redo att använda enheter](get-started-devices.md)
8. [Distribuera appar](deploy-apps.md)
