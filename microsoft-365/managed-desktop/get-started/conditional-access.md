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
ms.openlocfilehash: 88a832f6c4e17756bfb25ef5cb7c4c5ecedaf2c0
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794394"
---
# <a name="adjust-settings-after-enrollment"></a>Justera inställningarna efter registrering

När du har registrerat dig på Microsoft Managed Desktop kan vissa hanterings inställningar behöva justeras. Följ de här stegen om du vill kontrol lera och justera om det behövs:

1. Granska de inställningar för Microsoft Intune och Azure Active Directory som beskrivs i nästa avsnitt.
2. Om något av objekten gäller för din miljö gör du ändringarna beskrivna.
3. Om du vill kontrol lera att alla inställningar är korrekta kan du köra verktyget för utvärdering av [beredskap](https://aka.ms/mmdart) för att se till att det inte finns några konflikter med Microsoft Managed Desktop.

> [!NOTE]
> När dina åtgärder fortsätter under de följande månaderna är det möjligt att Microsoft Managed Desktop slutar fungera korrekt om du gör ändringar efter registrering till principer i Microsoft Intune, Azure Active Directory eller Microsoft 365 som påverkar Microsoft Managed Desktop. För att undvika problem med tjänsten kontrollerar du de specifika inställningar som beskrivs i [åtgärda problem som upptäckts av verktyget för utvärdering av beredskap](../get-ready/readiness-assessment-fix.md) innan du ändrar principerna som visas där. Du kan också köra verktyget för utvärdering av beredskap när som helst.


## <a name="microsoft-intune-settings"></a>Microsoft Intune-inställningar

- Distributions profil för automatisk pilot: om du använder några principer för automatisk pilot uppdaterar du var och en för att exkludera den **moderna arbets ytan-alla** Azure AD-grupper. Om du vill uppdatera dem väljer du den **moderna arbets ytan** i avsnittet **undantagna grupper** under **TILLDELNINGar**-alla Azure AD-grupper som har skapats under Microsoft Managed Desktop-registrering. Microsoft Managed Desktop har också skapat en autopilot-profil, som kommer att ha "modern arbets plats" i namnet (den **moderna arbets ytans pilot profil**). När du uppdaterar dina egna autopilot-profiler bör du kontrol lera att du *inte* utesluter de **moderna arbets Stations enheterna-alla** Azure AD-grupper från den **moderna arbets platsen automatisk pilot-profil** som har skapats av Microsoft Managed Desktop.

- Principer för villkorsstyrd åtkomst: om du har skapat villkorsstyrda åtkomst principer utesluter du den **moderna arbets plats tjänstens konton** Azure AD-grupp. Anvisningar finns i [villkorlig åtkomst: användare och grupper](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups). Microsoft Managed Desktop har också skapat vissa principer för villkorsstyrd åtkomst, vilka alla har "modern arbets plats" i namnet (till exempel **modern arbets plats säker arbets Station**). När du uppdaterar dina egna principer för villkorsstyrd åtkomst bör du kontrol lera att du *inte* utesluter den **moderna arbets ytans enheter-alla** Azure AD-grupper från alla principer som skapas av Microsoft Managed Desktop.

- Multifaktorautentisering: kontrol lera att alla principer för villkorsstyrd åtkomst som kräver multifaktorautentisering exkluderar den **moderna arbets plats tjänstens konton** Azure AD-grupp. Mer information finns i [principer för villkorsstyrd åtkomst](../get-ready/readiness-assessment-fix.md#conditional-access-policies) och [villkorsstyrd åtkomst: Kräv MFA för alla användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).

- Windows 10 – uppdatera signal: för en Windows 10-uppdaterings ring som du har skapat exkluderar du de **moderna arbets platserna-alla** Azure AD-grupper från varje princip. Anvisningar finns i [skapa och tilldela uppdaterings ringar](https://docs.microsoft.com/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings). Microsoft Managed Desktop har också skapat vissa uppdaterings samtals principer, vilka alla har "modern arbets plats" i namnet (till exempel **moderna arbets plats uppdaterings princip [breda]**, **moderna arbets plats uppdaterings princip [snabbt]**, **modern arbets plats uppdaterings princip [First]** och **moderna arbets plats uppdaterings princip [test]**). När du uppdaterar dina egna principer bör du kontrol lera att du *inte* utesluter de **moderna arbets Stations enheterna-alla** Azure AD-grupper från dem som hanteras av Microsoft.


## <a name="azure-active-directory-settings"></a>Azure Active Directory-inställningar

Självbetjäning för återställning av lösen ord: om du använder självbetjäning för återställning av lösen ord för alla användare, justera tilldelningen för att utesluta Microsoft Managed Desktop Service-konton. Om du vill justera den här tilldelningen skapar du en dynamisk Azure AD-grupp för alla användare *förutom* Microsoft Managed Desktop Service-konton och använder sedan gruppen för tilldelning i stället för "alla användare".

För att hjälpa dig att hitta och exkludera tjänst konton är det här ett exempel på en dynamisk fråga som du kan använda:

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

I den här frågan ersätter du @TENANT med namnet på klient organisationens domän.



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Steg för att komma igång med Microsoft Managed Desktop

1. [Lägga till och verifiera administratörskontakter i administratörsportalen](add-admin-contacts.md)
2. Justera inställningar efter registrering (den här artikeln)
3. [Koppla licenser](assign-licenses.md)
4. [Distribuera Intune-företagsportalen](company-portal.md)
5. [Aktivera Enterprise State Roaming](enterprise-state-roaming.md)
6. [Konfigurera enheter](set-up-devices.md)
7. [Gör användarna redo att använda enheter](get-started-devices.md)
8. [Distribuera appar](deploy-apps.md)
