---
title: Åtgärda problem som hittats av verktyget för bedömning av beredskap
description: Detaljerade åtgärder som ska vidtas för varje problem som verktyget hittar
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 866d1a2de820fca4c66537583dc5f55098149931
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327017"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Åtgärda problem som hittats av verktyget för bedömning av beredskap

För varje kontroll rapporterar verktyget ett av fyra möjliga resultat:


|Resultat  |Betydelse  |
|---------|---------|
|Klar     | Ingen åtgärd krävs innan registrering slutförs.        |
|Rådgivning    | Följ stegen i verktyget eller den här artikeln för den bästa upplevelsen med registrering och för användare. Du *kan* slutföra registreringen, men du måste åtgärda de här problemen innan du distribuerar din första enhet.        |
|Inte klar | *Registrering kommer att misslyckas om du inte åtgärdar dessa problem.* Följ stegen i verktyget eller den här artikeln för att lösa dem.        |
|Fel | Rollen Azure Active Directory (AD) som du använder har inte tillräcklig behörighet för att köra den här kontrollen. |

> [!NOTE]
> Det resultat som rapporterats av det här verktyget återspeglar bara statusen för dina inställningar vid en viss tidpunkt som du körde det. Om du senare gör ändringar i principer i Microsoft Intune, Azure Active Directory och Microsoft 365 kan objekt som var "Klara" bli "Inte klara". För att undvika problem Microsoft Hanterat skrivbord åtgärder kontrollerar du de specifika inställningarna som beskrivs i den här artikeln innan du ändrar några principer.

## <a name="microsoft-intune-settings"></a>Microsoft Intune inställningar

Du kan komma åt Intune-inställningarna Microsoft Endpoint Manager [administrationscentret](https://endpoint.microsoft.com).

### <a name="autopilot-deployment-profile"></a>Distributionsprofil för Autopilot

Du bör inte ha befintliga Autopilot-profiler som riktar in sig på tilldelade eller dynamiska grupper Microsoft Hanterat skrivbord enheter. Microsoft Hanterat skrivbord använder Autopilot för att tillhandahålla nya enheter.

**Inte klar**

Du har en Autopilot-profil som är tilldelad till alla enheter. Anvisningar finns i [Registrera Windows i Intune med hjälp av Windows Autopilot.](/mem/autopilot/enrollment-autopilot) När Microsoft Hanterat skrivbord registrering ställer du in Autopilot-principen så att den utesluter **modern workplace-enheter –alla** Azure AD-grupper.

**Rådgivning**

Se till att dina Autopilot-profiler riktar sig mot en tilldelad eller dynamisk Azure AD-grupp som inte inkluderar Microsoft Hanterat skrivbord enheter. Anvisningar finns i [Registrera Windows i Intune med hjälp av Windows Autopilot.](/mem/autopilot/enrollment-autopilot) När Microsoft Hanterat skrivbord registrering ställer du in dina Autopilot-profiler så att moderna **workplace-enheter utesluts –alla** Azure AD-grupper.


### <a name="certificate-connectors"></a>Certifikatkopplingar

Om du har några certifikatkopplingar som kommer att användas av de enheter som du vill registrera Microsoft Hanterat skrivbord bör kopplingarna inte ha några fel. Det är bara en av följande rådgivningar som gäller för din situation, så kontrollera dem noggrant.

**Rådgivning**

Inga certifikatkopplingar finns. Det är möjligt att du inte behöver några kopplingar, men du bör utvärdera om du kan behöva några för nätverksanslutningen på Microsoft Hanterat skrivbord enheter. Mer information finns i Förbereda [certifikat och nätverksprofiler för Microsoft Hanterat skrivbord](certs-wifi-lan.md).

**Rådgivning**

Minst en certifikatkoppling har ett fel. Om du behöver den här anslutningen för att tillhandahålla certifikat Microsoft Hanterat skrivbord-enheter måste du lösa felet. Mer information finns i Förbereda [certifikat och nätverksprofiler för Microsoft Hanterat skrivbord](certs-wifi-lan.md).


**Rådgivning**

Du har minst en certifikatkoppling och inga fel rapporteras. Men inför distributionen kan du behöva skapa en profil för att kunna återanvända kopplingen för Microsoft Hanterat skrivbord enheter. Mer information finns i Förbereda [certifikat och nätverksprofiler för Microsoft Hanterat skrivbord](certs-wifi-lan.md).

### <a name="company-portal"></a>Företagsportal

Microsoft Hanterat skrivbord att IT-administratörer installerar Intune-företagsportal för sina användare med Microsoft Hanterat skrivbord enheter. 

**Inte klar**

Du har inte Företagsportal för användarna. Köp Företagsportal och tvinga fram en synkronisering mellan Intune och Microsoft Store för företag. Mer information finns i [Installera Intune-företagsportal på enheter.](../get-started/company-portal.md)


### <a name="conditional-access-policies"></a>Villkorsstyrda åtkomstprinciper

Villkorsstyrda åtkomstprinciper får inte Microsoft Hanterat skrivbord förhindra hantering av Azure AD-organisationen (klientorganisationen) i Intune och Azure AD.

**Inte klar**

Du har minst en princip för villkorsstyrd åtkomst som riktar sig till alla användare. Under registreringen exkluderar vi Microsoft Hanterat skrivbord relevanta villkorsstyrda åtkomstprinciper och tillämpar nya villkorsstyrda åtkomstprinciper för att begränsa åtkomsten till dessa konton. Efter registrering kan du granska principen Microsoft Hanterat skrivbord villkorsstyrd åtkomst i Microsoft Endpoint Manager. Mer information om dessa tjänstkonton finns i [Standard-operativsystem.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Rådgivning**

Du har principer för villkorsstyrd åtkomst som Microsoft Hanterat skrivbord förhindra att Microsoft Hanterat skrivbord tjänsten. Under registreringen exkluderar vi Microsoft Hanterat skrivbord relevanta villkorsstyrda åtkomstprinciper och tillämpar nya villkorsstyrda åtkomstprinciper för att begränsa åtkomsten till dessa konton. Mer information om dessa tjänstkonton finns i [Standard-operativsystem.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Fel**

Intune-administratörsrollen har inte tillräcklig behörighet för den här kontrollen. Du behöver också någon av dessa Azure AD-roller för att kunna köra den här kontrollen:

- Säkerhetsläsare
- Säkerhetsadministratör
- Administratör för villkorsstyrd åtkomst
- Global läsare
- Administratör för enheter


### <a name="device-compliance-policies"></a>Policyer för enhetsefterlevnad

Intune-policyer för enhetsefterlevnad i din Azure AD-organisation kan Microsoft Hanterat skrivbord enheter.

**Inte klar**

Du har minst en efterlevnadsprincip som riktar sig till alla användare. Microsoft Hanterat skrivbord innehåller efterlevnadsprinciper som riktar sig mot dina Microsoft Hanterat skrivbord enheter.  Ändra principen så att den riktar sig mot en viss Azure AD-grupp som inte inkluderar några Microsoft Hanterat skrivbord användare eller enheter. Instruktioner finns i Skapa [en efterlevnadsprincip i Microsoft Intune](/mem/intune/protect/create-compliance-policy).

**Rådgivning**

Kontrollera att eventuella efterlevnadsprinciper du har inte riktar sig mot några Microsoft Hanterat skrivbord användare. Instruktioner finns i Skapa [en efterlevnadsprincip i Microsoft Intune](/mem/intune/protect/create-compliance-policy).



### <a name="device-configuration-profiles"></a>Profiler för enhetskonfiguration

Intune-enhetskonfigurationsprofiler i Din Azure AD-organisation får inte ha som mål att Microsoft Hantera skrivbordsenheter eller -användare.

**Inte klar**

Du har minst en konfigurationsprofil som riktar sig till alla användare, alla enheter eller båda. Återställ profilen så den är mål för en viss Azure AD-grupp som inte inkluderar några Microsoft Hanterat skrivbord enheter. Instruktioner finns i [Skapa en profil med anpassade inställningar i Microsoft Intune](/mem/intune/configuration/custom-settings-configure).

**Rådgivning**

Kontrollera att eventuella konfigurationsprinciper som du har inte innehåller några konfigurationsprinciper Microsoft Hanterat skrivbord och användare. Instruktioner finns i [Skapa en profil med anpassade inställningar i Microsoft Intune](/mem/intune/configuration/custom-settings-configure).



### <a name="device-type-restrictions"></a>Begränsningar för enhetstyp

Microsoft Hanterat skrivbord-enheter måste tillåtas att registrera i Intune.

**Inte klar**

Du har för närvarande minst en princip med begränsningar för registrering konfigurerad för att förhindra Windows enheter från registrering i Intune. Följ stegen i Ange [begränsningar för registrering för](/mem/intune/enrollment/enrollment-restrictions-set) varje princip för registreringbegränsningar som riktar Microsoft Hanterat skrivbord användare och ändra inställningen för Windows **(MDM)** till **Tillåt.** Du kan däremot ange att alla **personligt ägda** **Windows-enheter (MDM)** ska **blockeras.** 


### <a name="enrollment-status-page"></a>Statussida för registrering

Du har nu aktiverat ESP (Enrollment Status Page). Om du tänker delta i den Microsoft Hanterat skrivbord förhandsgranskningen av den här funktionen kan du ignorera det här objektet. Mer information finns i [Första körningen med Autopilot och registreringsstatussidan.](../get-started/esp-first-run.md)

**Inte klar**

Du har standardprofilen ESP inställd på **Visa konfigurationsstatus för appar och profiler.** Inaktivera den här inställningen eller kontrollera att tilldelningar till en Azure AD-grupp inte omfattar Microsoft Hanterat skrivbord-enheter genom att följa stegen i Konfigurera [statussidan för registrering.](/mem/intune/enrollment/windows-enrollment-status)

**Rådgivning**

Kontrollera att alla profiler som har inställningen Visa **app-** och profilkonfigurationsstatus inte tilldelas till någon Azure AD-grupp som innehåller Microsoft Hanterat skrivbord enheter. Mer information finns i [Konfigurera statussidan för registrering.](/mem/intune/enrollment/windows-enrollment-status)

### <a name="microsoft-store-for-business"></a>Microsoft Store för företag

Vi använder Microsoft Store för företag och distribuerar Företagsportal-appen på Microsoft Hanterat skrivbord för att tillåta användare att installera vissa appar, till exempel Microsoft Project och Microsoft Visio (där det är tillåtet).

**Inte klar**

Microsoft Store för företag antingen inte är aktiverat eller inte synkroniseras med Intune. Mer information finns i [Hantera volymköpta appar från](/mem/intune/apps/windows-store-for-business) Microsoft Store för företag med Microsoft Intune och installera Intune-företagsportal på [enheter.](../get-started/company-portal.md)

### <a name="multifactor-authentication"></a>Multifaktorautentisering

Multifaktorautentisering får inte Microsoft Hanterat skrivbord att hantera Azure AD-organisationen (klientorganisationen) i Intune och Azure AD.


**Inte klar**

Du har angett vissa multifaktorautentiseringsprinciper **som krävs** för villkorsstyrda åtkomstprinciper som har tilldelats till alla användare. Under registreringen exkluderar vi Microsoft Hanterat skrivbord relevanta villkorsstyrda åtkomstprinciper och tillämpar nya villkorsstyrda åtkomstprinciper för att begränsa åtkomsten till dessa konton. Mer information om dessa tjänstkonton finns i [Standard-operativsystem.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Rådgivning**

Du har multifaktorautentisering som krävs för villkorsstyrda åtkomstprinciper som Microsoft Hanterat skrivbord förhindra att Microsoft Hanterat skrivbord tjänsten. Under registreringen exkluderar vi Microsoft Hanterat skrivbord relevanta villkorsstyrda åtkomstprinciper och tillämpar nya villkorsstyrda åtkomstprinciper för att begränsa åtkomsten till dessa konton. Mer information om dessa tjänstkonton finns i [Standard-operativsystem.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Fel**

Intune-administratörsrollen har inte tillräcklig behörighet för den här kontrollen. Du behöver också någon av dessa Azure AD-roller för att kunna köra den här kontrollen:

- Säkerhetsläsare
- Säkerhetsadministratör
- Administratör för villkorsstyrd åtkomst
- Global läsare
- Administratör för enheter


### <a name="powershell-scripts"></a>PowerShell-skript

Windows PowerShell skript kan inte tilldelas på ett sätt som riktar sig Microsoft Hanterat skrivbord enheter.  

**Rådgivning**

Kontrollera att Windows PowerShell-skript i Azure AD-organisationen inte är målet för Microsoft Hantera skrivbordsenheter eller -användare. Tilldela inte ett PowerShell-skript för att rikta alla användare, alla enheter eller båda. Ändra principen så att en tilldelning används som mål för en viss Azure AD-grupp som inte inkluderar några Microsoft Hanterat skrivbord enheter eller användare. Mer information finns i [Använda PowerShell-skript på Windows 10 enheter i Intune.](/mem/intune/apps/intune-management-extension)

### <a name="region"></a>Region

Din region måste stödjas av Microsoft Hanterat skrivbord.

**Inte klar**

Din Azure AD-organisationsregion stöds för närvarande inte av Microsoft Hanterat skrivbord. Mer information finns i Microsoft Hanterat skrivbord [och språk som stöds.](../service-description/regions-languages.md)

**Rådgivning**

Ett eller flera av de länder där Azure AD-organisationen finns stöds inte av Microsoft Hanterat skrivbord. Mer information finns i Microsoft Hanterat skrivbord [och språk som stöds.](../service-description/regions-languages.md)


### <a name="security-baselines"></a>Säkerhetsbaslinjer

Säkerhetsprinciper bör inte ha några Microsoft Hanterat skrivbord enheter.

**Inte klar**

Du har en säkerhetsbaslinjeprofil som riktar sig till alla användare, alla enheter eller båda. Ändra principen så att en tilldelning används som mål för en viss Azure AD-grupp som inte inkluderar några Microsoft Hanterat skrivbord enheter. Instruktioner finns i Använda [säkerhetsbaslinjer för att konfigurera Windows 10 enheter i Intune.](/mem/intune/protect/security-baselines) Under registreringen används en ny säkerhetsbaslinje för alla Microsoft Hanterat skrivbord enheter. Efter registreringen kan du granska Microsoft Hanterat skrivbord säkerhetsbaslinjeprincipen i området **Konfigurationsprincip** i Microsoft Endpoint Manager.

**Rådgivning**

Kontrollera att eventuella principer för säkerhetsbaslinje som du har exkluderat Microsoft Hanterat skrivbord enheter. Instruktioner finns i Använda [säkerhetsbaslinjer för att konfigurera Windows 10 enheter i Intune.](/mem/intune/protect/security-baselines) Under registreringen används en ny säkerhetsbaslinje för alla Microsoft Hanterat skrivbord enheter. Gruppen **Moderna workplace-enheter – Alla** Azure AD är en dynamisk grupp som vi skapar när du registrerar dig i Microsoft Hanterat skrivbord, så du måste gå tillbaka och utesluta den här gruppen efter registreringen. 

### <a name="unlicensed-admins"></a>Olicensierade administratörer

Den här inställningen måste vara aktiverad för att undvika felet "brist på behörigheter" när vi interagerar med Azure AD-organisationen. 

**Inte klar**

**Tillåt åtkomst till olicensierade administratörer** ska vara aktiverat. Anvisningar finns i Förutsättningar [för gästkonton.](/microsoft-365/managed-desktop/get-ready/guest-accounts)

### <a name="windows-apps"></a>Windows appar

Granska appar som du vill Microsoft Hanterat skrivbord användarna ska ha.

**Rådgivning**

Du bör förbereda en inventering av de program som du vill att Microsoft Hanterat skrivbord användarna ska ha. Eftersom dessa appar måste distribueras av Intune bör du utvärdera återanvändning av befintliga Intune-appar. Överväg att Företagsportal (se [Installera Intune-företagsportal på](../get-started/company-portal.md) enheter och ESP (Enrollment Status Page) för att distribuera appar till användarna. Mer information finns i [Program i Microsoft Hanterat skrivbord](apps.md) och [First-run med Autopilot och registreringsstatussidan.](../get-started/esp-first-run.md)

Du kan be din Microsoft-kontorepresentant för en fråga i Microsoft Endpoint Configuration Manager att identifiera de appar som är redo att migreras till Intune eller behöver justeras.


### <a name="windows-hello-for-business"></a>Windows Hello för företag

Microsoft Hanterat skrivbord kräver Windows Hello för företag är aktiverat.

**Inte klar**

Windows Hello för företag är inaktiverat. Aktivera den genom att följa stegen i [Skapa en Windows Hello för företag-princip](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**Rådgivning**

Windows Hello för företag har inte ställts in. Aktivera den genom att följa stegen i [Skapa en Windows Hello för företag-princip.](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)


### <a name="windows-10-update-rings"></a>Windows 10 uppdateringsringar

Principen för Windows 10 uppdateringsringen i Intune får inte ha som mål några Microsoft Hanterat skrivbord enheter.

**Inte klar**

Du har en princip för "uppdateringsringen" som riktar in alla enheter, alla användare eller båda. Ändra principen till att använda en tilldelning som riktar in en viss Azure AD-grupp som inte inkluderar några Microsoft Hanterat skrivbord enheter. Anvisningar finns i Hantera [Windows 10 programuppdateringar i Intune.](/mem/intune/protect/windows-update-for-business-configure)

**Rådgivning**

Kontrollera att alla principer för uppdateringsringen du har exkluderat **Modern Workplace-enheter –Alla** Azure AD-grupper. Om du har tilldelat Azure AD-användargrupper till de här principerna ska du se till att alla principer för uppdateringsringen även har uteslutit den **moderna arbetsplatsen -Alla** Azure AD-grupp du lägger till dina Microsoft Hanterat skrivbord-användare i (eller en motsvarande grupp). Anvisningar finns i Hantera [Windows 10 programuppdateringar i Intune.](/mem/intune/protect/windows-update-for-business-configure) Både **moderna workplace-enheter –alla** och moderna arbetsplatsen **–Alla** Azure AD-grupper är grupper som vi skapar när du registrerar dig i Microsoft Hanterat skrivbord, så du måste komma tillbaka och utesluta den här gruppen efter registreringen.


## <a name="azure-active-directory-settings"></a>Azure Active Directory inställningar

Du kan komma Azure Active Directory inställningar i [Azure Portal.](https://portal.azure.com)

### <a name="intune-enrollment"></a>Intune-registrering

Windows 10 enheter i din Azure AD-organisation måste kunna registreras automatiskt i Intune.

**Rådgivning**

Kontrollera att **MDM-användarens omfattning** är inställd **på Vissa** eller **Alla**, inte **Inget.** Om du väljer **Vissa** kommer du tillbaka efter registreringen och  väljer den moderna arbetsplatsen – alla Azure **AD-grupper** för grupper eller en motsvarande grupp som är riktad mot alla Microsoft Hanterat skrivbord användare.  Se [Konfigurera registrering för Windows enheter med hjälp av Microsoft Intune](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment).

### <a name="ad-hoc-subscriptions"></a>Ad hoc-prenumerationer

Ger information om hur du kontrollerar en inställning som (om denna är inställd på "falskt") kan förhindra att Roaming i företagstillståndet fungerar korrekt.

**Rådgivning**

Kontrollera att **AllowAdHocSubscriptions** är inställt på **Sant.** Annars kanske Inte Enterprise State Roaming fungerar. Mer information finns i [Set-MsolCompanySettings.](/powershell/module/msonline/set-msolcompanysettings)


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

Roaming i företagstillstånd ska vara aktiverat.

**Rådgivning**

Kontrollera att Roaming i företagstillstånd är aktiverat för **Alla** eller **för valda** grupper. Mer information finns i [Aktivera roaming i företagstillstånd i Azure Active Directory.](/azure/active-directory/devices/enterprise-state-roaming-enable)

### <a name="licenses"></a>Licenser

Ett antal licenser krävs för att använda Microsoft Hanterat skrivbord.

**Inte klar**

Du har inte alla licenser du behöver för att använda Microsoft Hanterat skrivbord. Mer information finns i Microsoft Hanterat skrivbord [och](../intro/technologies.md) [Mer om licenser.](prerequisites.md#more-about-licenses)


### <a name="microsoft-managed-desktop-service-accounts"></a>Microsoft Hanterat skrivbord-tjänstkonton

Vissa kontonamn kan vara i konflikt med kontonamn som skapats Microsoft Hanterat skrivbord för att hantera Microsoft Hanterat skrivbord tjänst.

**Inte klar**

Du har minst ett kontonamn som kan vara i konflikt med kontonamn som skapats av Microsoft Hanterat skrivbord. Arbeta med din Microsoft-kontorepresentant för att utesluta dessa kontonamn. Vi listar inte kontonamnen offentligt för att minimera säkerhetsriskerna. 


### <a name="security-administrator-roles"></a>Säkerhetsadministratörsroller

Användare med vissa säkerhetsroller måste ha de rollerna tilldelade i Microsoft Defender för Endpoint.

**Rådgivning**

Om du har användare tilldelade till någon av de här rollerna i din Azure AD-organisation bör du kontrollera att de även har tilldelats de här rollerna i Microsoft Defender för Slutpunkt. I annat fall kommer administratörer med de här rollerna inte att kunna komma åt administrationsportalen.

- Säkerhetsoperatör
- Global läsare

Mer information finns i [Skapa och hantera roller för rollbaserad åtkomstkontroll.](/windows/security/threat-protection/microsoft-defender-atp/user-roles)


### <a name="security-default"></a>Standardsäkerhet

Säkerhetsstandarder i Azure Active Directory hindrar Microsoft Hanterat skrivbord att hantera dina enheter.

**Inte klar**

Du har aktiverat standardinställningarna för säkerhet. Inaktivera säkerhetsstandarder och konfigurera principer för villkorsstyrd åtkomst. Mer information finns i Vanliga principer [för villkorsstyrd åtkomst.](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)

### <a name="self-service-password-reset"></a>Självbetjäning för återställning av lösenord

Självbetjäning för återställning av lösenord (SSPR) kan aktiveras för Microsoft Hanterat skrivbord användare utom Microsoft Hanterat skrivbord-tjänstkonton. Mer information finns i självstudiekursen: Tillåta användare att låsa upp sitt konto eller återställa lösenord [Azure Active Directory självbetjäning för återställning av lösenord.](/azure/active-directory/authentication/tutorial-enable-sspr)

**Rådgivning**

Kontrollera att inställningen SSPR **Selected omfattar** alla Microsoft Hanterat skrivbord men exkluderar Microsoft Hanterat skrivbord tjänstkonton. Microsoft Hanterat skrivbord-tjänstkonton fungerar inte som förväntat när SSPR är aktiverat.  


### <a name="standard-user-role"></a>Standardanvändarroll

Förutom de användare som har tilldelats Azure AD-roller som global administratör och enhetsadministratör är Microsoft Hanterat skrivbord-användare standardanvändare utan lokal administratörsbehörighet. Alla andra användare tilldelas en standardanvändarroll när de startar sin egen Microsoft Hanterat skrivbord enhet.

**Rådgivning**

Microsoft Hanterat skrivbord användare inte har lokal administratörsbehörighet på sina Microsoft Hanterat skrivbord-enheter när de har registrerat sig.

## <a name="microsoft-365-apps-for-enterprise"></a> Microsoft 365 Apps för företag

### <a name="onedrive"></a>OneDrive

Inställningen **Tillåt synkronisering endast på datorer som är ansluten till vissa domäner är** i konflikt Microsoft Hanterat skrivbord. Du kan OneDrive i administrationscentret OneDrive [.](https://admin.onedrive.com)

**Rådgivning**

Du använder inställningen Tillåt **synkronisering endast på datorer som är ansluten till vissa** domäner. Den här inställningen fungerar inte med Microsoft Hanterat skrivbord. Inaktivera den här inställningen och konfigurera den OneDrive använda en princip för villkorsstyrd åtkomst. Mer [hjälp finns i Planera en villkorsstyrd åtkomstdistribution.](/azure/active-directory/conditional-access/plan-conditional-access)
