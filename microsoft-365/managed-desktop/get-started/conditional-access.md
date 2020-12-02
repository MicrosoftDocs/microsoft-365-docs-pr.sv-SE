---
title: Justera inställningar efter registrering
description: Så här utesluter du vissa Microsoft-konton
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 76a73372cc7517c3241390e58c28b0b02bffd664
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527703"
---
# <a name="adjust-settings-after-enrollment"></a>Justera inställningar efter registrering

När du är klar med registreringen på Microsoft Managed Desktop måste du justera vissa inställningar för Microsoft Intune och Azure Active Directory (Azure AD) för att tillåta hantering och underhåll av säkerhet. Ange följande inställningar för att utesluta Azure AD-grupperna som innehåller Microsoft Managed Desktop-enheter och-användare. Anvisningar för hur du exkluderar grupper finns i [villkorlig åtkomst: användare och grupper](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users).

## <a name="microsoft-intune-settings"></a>Microsoft Intune-inställningar

- Distributions profil för automatisk pilot: exkludera den **moderna arbets ytan enheter-alla**  Azure AD-grupper. Anvisningar finns i [registrera Windows-enheter i Intune med hjälp av Windows autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).
- Principer för villkorsstyrd åtkomst: exkludera den **moderna arbets plats tjänstens konton** Azure AD-grupp. Anvisningar finns i [villkorlig åtkomst: användare och grupper](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).
- Multifaktorautentisering: kontrol lera att alla principer för villkorsstyrd åtkomst som kräver multifaktorautentisering exkluderar den **moderna arbets plats tjänstens konton** Azure AD-grupp. Mer information finns i [principer för villkorsstyrd åtkomst](../get-ready/readiness-assessment-fix.md#conditional-access-policies) och [villkorsstyrd åtkomst: Kräv MFA för alla användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).
- Säkerhets bas linje: exkludera den **moderna arbets ytans enheter-alla**  Azure AD-grupper. Anvisningar finns i [använda säkerhets bas linjer för att konfigurera Windows 10-enheter i Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).
- Windows 10, uppdaterings ring: Uteslut **moderna arbets plats enheter-alla**  Azure AD-grupper. Anvisningar finns i [hantera program uppdateringar för Windows 10 i Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).


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
