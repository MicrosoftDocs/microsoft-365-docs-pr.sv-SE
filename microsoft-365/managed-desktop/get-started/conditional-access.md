---
title: Justera inställningarna efter registrering
description: Så här utesluter du vissa Microsoft-konton
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 760fcb94ec6d84a55fe4b8c3cb3540ae29994ae3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918448"
---
# <a name="adjust-settings-after-enrollment"></a>Justera inställningarna efter registrering

När du har slutfört registreringen i Microsoft Managed Desktop kan vissa hanteringsinställningar behöva justeras. Kontrollera och justera om det behövs genom att följa de här stegen:

1. Granska inställningarna för Microsoft Intune och Azure Active Directory som beskrivs i nästa avsnitt.
2. Om något av objekten gäller för din miljö gör du de justeringar som beskrivs.
3. Om du vill kontrollera att alla inställningar är korrekta [](https://aka.ms/mmdart) kan du köra beredskapsutvärderingsverktyget igen för att säkerställa att ingenting står i konflikt med Microsoft Managed Desktop.

> [!NOTE]
> När åtgärderna fortsätter under de kommande månaderna, och du gör ändringar efter registrering av principer i Microsoft Intune, Azure Active Directory eller Microsoft 365 som påverkar Microsoft Managed Desktop, är det möjligt att Microsoft Managed Desktop inte fungerar som det ska. För att undvika problem med tjänsten kontrollerar [](../get-ready/readiness-assessment-fix.md) du de specifika inställningar som beskrivs i Åtgärda problem som påträffats av beredskapsutvärderingsverktyget innan du ändrar principerna som anges där. Du kan också köra beredskapsutvärderingsverktyget igen när som helst.


## <a name="microsoft-intune-settings"></a>Microsoft Intune-inställningar

- Distributionsprofilen för Autopilot: Om du använder autopilotprinciper ska du uppdatera var och en för att utesluta **den moderna arbetsplatsen-enheten –alla** Azure AD-grupper. Du uppdaterar dem genom att **i** avsnittet Undantagna grupper under **Uppgifter** välja den **moderna arbetsplatsen-enheter –alla Azure AD-grupper** som skapades under Microsoft Hanterad skrivbordsregistrering. Microsoft Hanterat skrivbord har också skapat en Autopilot-profil som har "Modern workplace" i namnet **(profilen Modern Workplace Autopilot).** När du uppdaterar dina egna Autopilot-profiler ska du se till att du inte utesluter gruppen **Moderna workplace-enheter –Alla** Azure AD-grupper från **den moderna workplace autopilot-profilen** som skapades av Microsoft Managed Desktop. 

- Villkorsstyrda åtkomstprinciper: Om du skapar nya villkorsstyrda åtkomstprinciper relaterade till Azure AD, Microsoft Intune eller Microsoft Defender för Endpoint efter Microsoft Hanterad skrivbordsregistrering ska du utesluta **Azure** AD-gruppen för tjänstekonton för modern workplace från dem. Anvisningar finns i [Villkorsstyrd åtkomst: Användare och grupper.](/azure/active-directory/conditional-access/concept-conditional-access-users-groups) Microsoft Managed Desktop har separata principer för villkorsstyrd åtkomst för att begränsa åtkomsten till dessa konton. Gå till Microsoft Endpoint Manager och gå till Villkorsstyrd åtkomst **i** **Slutpunktssäkerhet** för att granska principen för villkorsstyrd åtkomst för Microsoft Managed Desktop (Modern workplace – Secure **Arbetsstation).** Ändra inte villkorsstyrda åtkomstprinciper för Azure AD som skapats av Microsoft Managed Desktop och som har "Modern Workplace" i namnet.

- Multifaktorautentisering: Om du skapar nya multifaktorautentiseringskrav i villkorsstyrda åtkomstprinciper som är relaterade till Azure AD, Intune eller Microsoft Defender för Slutpunkt efter Microsoft Hanterad skrivbordsregistrering ska du utesluta Azure AD-gruppen för **tjänstekonton** för modern arbetsplats från dem. Anvisningar finns i [Villkorsstyrd åtkomst: Användare och grupper.](/azure/active-directory/conditional-access/concept-conditional-access-users-groups) Microsoft Managed Desktop har separata principer för villkorsstyrd åtkomst för att begränsa åtkomsten till medlemmar i den här gruppen. Om du vill granska principen för villkorsstyrd åtkomst i Microsoft Managed Desktop **(Modern Workplace –**) går du till Microsoft Endpoint Manager och navigerar till **Villkorsstyrd åtkomst** i **Slutpunktssäkerhet.** 

- Uppdateringsringen i Windows 10: För alla principer för Windows 10-uppdateringsringen som du har skapat exkluderar du **moderna workplace-enheter –alla Azure AD-grupper** från varje princip. Instruktioner finns i Skapa [och tilldela uppdateringsringar.](/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings) Microsoft Hanterat skrivbord kommer också att ha skapat vissa principer för uppdateringsringen, som alla har "Modern workplace" i namnet (till exempel Uppdateringsprincip för **modern arbetsplats [Bred]**, Uppdateringsprincip för **modern arbetsplats [Snabb]**, Uppdateringsprincip för modern arbetsplats **[första]** och Uppdateringsprincip **för modern arbetsplats [Test]**). När du uppdaterar dina egna principer  ska du se till att du inte utesluter **gruppen Moderna workplace-enheter –Alla** Azure AD-grupper från de som Microsoft Hanterat skrivbord har skapat.


## <a name="azure-active-directory-settings"></a>Azure Active Directory-inställningar

Självbetjäning för återställning av lösenord: Om du använder självbetjäning för återställning av lösenord för alla användare justerar du tilldelningen så att den exkluderar Microsoft Managed Desktop-tjänstkonton. Om du vill justera den här uppgiften skapar du en dynamisk Azure AD-grupp för alla användare utom *Microsoft* Managed Desktop-tjänstkonton och använder sedan gruppen för tilldelning i stället för "alla användare".

Här är ett exempel på en dynamisk fråga som du kan använda för att hjälpa dig att hitta och utesluta tjänstkonton:

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

I den här frågan ersätter @TENANT domännamnet med klientorganisationens domännamn.



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Steg för att komma igång med Microsoft Managed Desktop

1. [Lägga till och verifiera administratörskontakter i administratörsportalen](add-admin-contacts.md)
2. Justera inställningar efter registrering (den här artikeln)
3. [Koppla licenser](assign-licenses.md)
4. [Distribuera Intune-företagsportalen](company-portal.md)
5. [Aktivera Enterprise State Roaming](enterprise-state-roaming.md)
6. [Konfigurera enheter](set-up-devices.md)
7. [Gör användarna redo att använda enheter](get-started-devices.md)
8. [Distribuera appar](deploy-apps.md)