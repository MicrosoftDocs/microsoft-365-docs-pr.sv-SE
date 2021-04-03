---
title: Åtgärda problem som hittats av verktyget för bedömning av beredskap
description: Detaljerade åtgärder som ska vidtas för varje problem som verktyget hittar
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 5a22996ce9e39dc16191ddddc6aa9393de557bbc
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579416"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Åtgärda problem som hittats av verktyget för bedömning av beredskap

För varje kontroll rapporterar verktyget ett av fyra möjliga resultat:


|Resultat  |Betydelse  |
|---------|---------|
|Klar     | Ingen åtgärd krävs innan registrering slutförs.        |
|Rådgivning    | Följ stegen i verktyget eller den här artikeln för den bästa upplevelsen med registrering och för användare. Du *kan* slutföra registreringen, men du måste åtgärda de här problemen innan du distribuerar din första enhet.        |
|Inte klar | *Registrering kommer att misslyckas om du inte åtgärdar dessa problem.* Följ stegen i verktyget eller den här artikeln för att lösa dem.        |
|Fel | Azure Active Directory-rollen (AD) som du använder har inte tillräcklig behörighet för att köra den här kontrollen. |

> [!NOTE]
> Det resultat som rapporterats av det här verktyget återspeglar bara statusen för dina inställningar vid en viss tidpunkt som du körde det. Om du senare gör ändringar i principer i Microsoft Intune, Azure Active Directory eller Microsoft 365 kan objekt som var "Ready" bli "Inte klara". För att undvika problem med åtgärder som hanteras av Microsoft Managed Desktop kontrollerar du de specifika inställningarna som beskrivs i den här artikeln innan du ändrar några principer.

## <a name="microsoft-intune-settings"></a>Microsoft Intune-inställningar

Du kan komma åt Intune-inställningarna i administrationscentret för Microsoft Endpoint [Manager.](https://endpoint.microsoft.com)

### <a name="autopilot-deployment-profile"></a>Distributionsprofil för Autopilot

Du bör inte ha befintliga Autopilot-profiler som har tilldelats eller dynamiska grupper med Microsoft Managed Desktop-enheter. Microsoft Hanterat skrivbord använder Autopilot för att tillhandahålla nya enheter.

**Inte klar**

Du har en Autopilot-profil som är tilldelad till alla enheter. Instruktioner finns i [Registrera Windows-enheter i Intune med Windows Autopilot.](/mem/autopilot/enrollment-autopilot) Efter registrering av Microsoft Hanterad dator ställer du in Autopilot-principen så att den utesluter **moderna workplace-enheter –alla** Azure AD-grupper.

**Rådgivning**

Se till att dina Autopilot-profiler riktar sig mot en tilldelad eller dynamisk Azure AD-grupp som inte inkluderar Microsoft Managed Desktop-enheter. Instruktioner finns i [Registrera Windows-enheter i Intune med Windows Autopilot.](/mem/autopilot/enrollment-autopilot) När du har hanterat skrivbordsregistreringen i Microsoft ställer du in Autopilot-profiler så att **moderna workplace-enheter utesluts –alla** Azure AD-grupper.


### <a name="certificate-connectors"></a>Certifikatkopplingar

Om du har några certifikatkopplingar som kommer att användas av de enheter som du vill registrera i Microsoft Managed Desktop bör kopplingarna inte ha några fel. Det är bara en av följande rådgivningar som gäller för din situation, så kontrollera dem noggrant.

**Rådgivning**

Inga certifikatkopplingar finns. Det är möjligt att du inte behöver några kopplingar, men du bör utvärdera om du kan behöva några för nätverksanslutningen på dina Microsoft Managed Desktop-enheter. Mer information finns i Förbereda [certifikat och nätverksprofiler för Microsoft Managed Desktop.](certs-wifi-lan.md)

**Rådgivning**

Minst en certifikatkoppling har ett fel. Om du behöver den här anslutningen för att tillhandahålla certifikat till Microsoft Managed Desktop-enheter måste du lösa felet. Mer information finns i Förbereda [certifikat och nätverksprofiler för Microsoft Managed Desktop.](certs-wifi-lan.md)


**Rådgivning**

Du har minst en certifikatkoppling och inga fel rapporteras. När du gör en förberedelse inför distributionen kanske du måste skapa en profil för att kunna återanvända kopplingen för Microsoft Managed Desktop-enheter. Mer information finns i Förbereda [certifikat och nätverksprofiler för Microsoft Managed Desktop.](certs-wifi-lan.md)


### <a name="conditional-access-policies"></a>Villkorsstyrda åtkomstprinciper

Villkorsstyrda åtkomstprinciper får inte hindra Microsoft Managed Desktop från att hantera din Azure AD-organisation (klientorganisation) i Intune och Azure AD.

**Inte klar**

Du har minst en princip för villkorsstyrd åtkomst som riktar sig till alla användare. Under registreringen exkluderar vi Microsoft Managed Desktop-tjänstkonton från relevanta principer för villkorsstyrd åtkomst och tillämpar nya villkorsstyrda åtkomstprinciper för att begränsa åtkomsten till dessa konton. Efter registreringen kan du granska principen för villkorsstyrd åtkomst i Microsoft Managed Desktop i Microsoft Endpoint Manager. Mer information om dessa tjänstkonton finns i [Standard-operativsystem.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Rådgivning**

Du har principer för villkorsstyrd åtkomst som kan hindra Microsoft Managed Desktop från att hantera Microsoft Managed Desktop-tjänsten. Under registreringen exkluderar vi Microsoft Managed Desktop-tjänstkonton från relevanta principer för villkorsstyrd åtkomst och tillämpar nya villkorsstyrda åtkomstprinciper för att begränsa åtkomsten till dessa konton. Mer information om dessa tjänstkonton finns i [Standard-operativsystem.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Fel**

Intune-administratörsrollen har inte tillräcklig behörighet för den här kontrollen. Du behöver också någon av dessa Azure AD-roller för att kunna köra den här kontrollen:

- Säkerhetsläsare
- Säkerhetsadministratör
- Administratör för villkorsstyrd åtkomst
- Global läsare
- Administratör för enheter


### <a name="device-compliance-policies"></a>Policyer för enhetsefterlevnad

Intune-policyer för enhetsefterlevnad i din Azure AD-organisation kan påverka Microsoft Hanterade skrivbordsenheter.

**Inte klar**

Du har minst en efterlevnadsprincip som riktar sig till alla användare. Microsoft Managed Desktop innehåller efterlevnadsprinciper som riktar sig mot dina Microsoft Managed Desktop-enheter.  Ändra principen så att den riktar sig till en viss Azure AD-grupp som inte innehåller några användare eller enheter som hanteras av Microsoft Managed Desktop. Instruktioner finns i [Skapa en efterlevnadsprincip i Microsoft Intune.](/mem/intune/protect/create-compliance-policy)

**Rådgivning**

Kontrollera att eventuella efterlevnadsprinciper som du har inte riktar sig mot användare av Microsoft Managed Desktop. Instruktioner finns i [Skapa en efterlevnadsprincip i Microsoft Intune.](/mem/intune/protect/create-compliance-policy)



### <a name="device-configuration-profiles"></a>Profiler för enhetskonfiguration

Intune-enhetskonfigurationsprofiler i Din Azure AD-organisation får inte ha som mål att Microsoft Hantera skrivbordsenheter eller -användare.

**Inte klar**

Du har minst en konfigurationsprofil som riktar sig till alla användare, alla enheter eller båda. Återställ profilen så att den är mål för en viss Azure AD-grupp som inte inkluderar några Microsoft Managed Desktop-enheter. Instruktioner finns i [Skapa en profil med anpassade inställningar i Microsoft Intune](/mem/intune/configuration/custom-settings-configure).

**Rådgivning**

Se till att eventuella konfigurationsprinciper som du har inte innehåller några microsoft-hanterade enheter eller användare. Instruktioner finns i [Skapa en profil med anpassade inställningar i Microsoft Intune](/mem/intune/configuration/custom-settings-configure).



### <a name="device-type-restrictions"></a>Begränsningar för enhetstyp

Microsoft Hanterade skrivbordsenheter måste tillåtas att registrera i Intune.

**Inte klar**

Du har för närvarande minst en princip med begränsningar för registrering konfigurerad för att förhindra att Windows-enheter registrering i Intune. Följ stegen i Ange [registreringsbegränsningar för](/mem/intune/enrollment/enrollment-restrictions-set) varje princip för registreringbegränsningar som riktar in Microsoft Managed Desktop-användare och ändra **Windows-inställningen (MDM)** till **Tillåt.** Du kan däremot ställa in så att alla **personligt ägda** **Windows-enheter (MDM)** **blockeras.** 


### <a name="enrollment-status-page"></a>Statussida för registrering

Du har nu aktiverat ESP (Enrollment Status Page). Om du har för avsikt att delta i den offentliga förhandsversionen av den här funktionen i Microsoft Managed Desktop kan du ignorera det här objektet. Mer information finns i [Första körningen med Autopilot och registreringsstatussidan.](../get-started/esp-first-run.md)

**Inte klar**

Du har standardprofilen ESP inställd på **Visa konfigurationsstatus för appar och profiler.** Inaktivera den här inställningen eller kontrollera att tilldelningar till en Azure AD-grupp inte omfattar Microsoft Managed Desktop-enheter genom att följa stegen i Konfigurera statussidan för [registrering.](/mem/intune/enrollment/windows-enrollment-status)

**Rådgivning**

Kontrollera att alla profiler som har inställningen Visa **app-** och profilkonfigurationsstatus inte tilldelas till någon Azure AD-grupp som inkluderar Microsoft Managed Desktop-enheter. Mer information finns i [Konfigurera statussidan för registrering.](/mem/intune/enrollment/windows-enrollment-status)

### <a name="microsoft-store-for-business"></a>Microsoft Store för företag

Vi använder Microsoft Store för företag och distribuerar företagsportalappen på Microsoft Hanterat skrivbord för att tillåta användare att installera vissa appar, till exempel Microsoft Project och Microsoft Visio (om det är tillåtet).

**Inte klar**

Microsoft Store för företag är antingen inte aktiverat eller inte synkroniserat med Intune. Mer information finns i Hantera volymköpta appar från Microsoft Store för företag med [Microsoft Intune](/mem/intune/apps/windows-store-for-business) och [Installera Intune-företagsportal på enheter.](../get-started/company-portal.md)

### <a name="multifactor-authentication"></a>Multifaktorautentisering

Multifaktorautentisering får inte hindra Microsoft Managed Desktop från att hantera din Azure AD-organisation (klientorganisation) i Intune och Azure AD.


**Inte klar**

Du har angett vissa multifaktorautentiseringsprinciper **som krävs** för villkorsstyrda åtkomstprinciper som har tilldelats till alla användare. Under registreringen exkluderar vi Microsoft Managed Desktop-tjänstkonton från relevanta principer för villkorsstyrd åtkomst och tillämpar nya villkorsstyrda åtkomstprinciper för att begränsa åtkomsten till dessa konton. Mer information om dessa tjänstkonton finns i [Standard-operativsystem.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Rådgivning**

Du har multifaktorautentisering som krävs för villkorsstyrda åtkomstprinciper som kan hindra Microsoft Managed Desktop från att hantera Microsoft Managed Desktop-tjänsten. Under registreringen exkluderar vi Microsoft Managed Desktop-tjänstkonton från relevanta principer för villkorsstyrd åtkomst och tillämpar nya villkorsstyrda åtkomstprinciper för att begränsa åtkomsten till dessa konton. Mer information om dessa tjänstkonton finns i [Standard-operativsystem.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Fel**

Intune-administratörsrollen har inte tillräcklig behörighet för den här kontrollen. Du behöver också någon av dessa Azure AD-roller för att kunna köra den här kontrollen:

- Säkerhetsläsare
- Säkerhetsadministratör
- Administratör för villkorsstyrd åtkomst
- Global läsare
- Administratör för enheter


### <a name="powershell-scripts"></a>PowerShell-skript

Windows PowerShell-skript kan inte tilldelas på ett sätt som riktar sig mot Microsoft Managed Desktop-enheter.  

**Rådgivning**

Kontrollera att Windows PowerShell-skript i din Azure AD-organisation inte är målet för Microsoft Manage Desktop-enheter eller -användare. Tilldela inte ett PowerShell-skript för att rikta alla användare, alla enheter eller båda. Ändra principen till att använda en tilldelning som riktar in en viss Azure AD-grupp som inte inkluderar några enheter eller användare av Microsoft Managed Desktop. Mer information finns i Använda [PowerShell-skript på Windows 10-enheter i Intune.](/mem/intune/apps/intune-management-extension)

### <a name="region"></a>Region

Din region måste stödjas av Microsoft Managed Desktop.

**Inte klar**

Din Azure AD-organisationsregion stöds för närvarande inte av Microsoft Managed Desktop. Mer information finns i Regioner [och språk som stöds av Microsoft Managed Desktop.](../service-description/regions-languages.md)

**Rådgivning**

Ett eller flera av de länder där din Azure AD-organisation finns stöds inte av Microsoft Managed Desktop. Mer information finns i Regioner [och språk som stöds av Microsoft Managed Desktop.](../service-description/regions-languages.md)


### <a name="security-baselines"></a>Säkerhetsbaslinjer

Säkerhetsprinciper bör inte ha några Microsoft Managed Desktop-enheter som mål.

**Inte klar**

Du har en säkerhetsbaslinjeprofil som riktar sig till alla användare, alla enheter eller båda. Ändra principen så att en tilldelning används som mål för en viss Azure AD-grupp som inte inkluderar några Microsoft Managed Desktop-enheter. Instruktioner finns i Använda [säkerhetsbaslinjer för att konfigurera Windows 10-enheter i Intune.](/mem/intune/protect/security-baselines) Under registreringen tillämpar vi en ny säkerhetsbaslinje för alla Microsoft Managed Desktop-enheter. Efter registreringen kan du granska säkerhetsbaslinjepolicyn för Microsoft Managed Desktop i området **Konfigurationsprincip** i Microsoft Endpoint Manager.

**Rådgivning**

Kontrollera att eventuella principer för säkerhetsbaslinje du har utesluta Microsoft Managed Desktop-enheter. Instruktioner finns i Använda [säkerhetsbaslinjer för att konfigurera Windows 10-enheter i Intune.](/mem/intune/protect/security-baselines) Under registreringen tillämpar vi en ny säkerhetsbaslinje för alla Microsoft Managed Desktop-enheter. Gruppen **Moderna workplace-enheter – Alla** Azure AD-grupper är en dynamisk grupp som vi skapar när du registrerar dig för Microsoft Managed Desktop, så du måste gå tillbaka och utesluta den här gruppen efter registreringen. 


### <a name="windows-apps"></a>Windows-appar

Granska appar som du vill att dina Microsoft Managed Desktop-användare ska ha.

**Rådgivning**

Du bör förbereda en inventering av de appar som du vill att Microsoft Hanterade skrivbordsanvändare ska ha. Eftersom dessa appar måste distribueras av Intune bör du utvärdera återanvändning av befintliga Intune-appar. Överväg att använda företagsportalen (se [Installera Intune-företagsportalen](../get-started/company-portal.md) på enheter och ESP (Enrollment Status Page) för att distribuera appar till användarna. Mer information finns i [Program i Microsoft Hanterad skrivbords-](apps.md) [och first-run-upplevelse med Autopilot och registreringsstatussidan.](../get-started/esp-first-run.md)

Du kan be din Microsoft-kontorepresentant för en fråga i Microsoft Endpoint Configuration Manager att identifiera de appar som är redo att migreras till Intune eller behöver justeras.


### <a name="windows-hello-for-business"></a>Windows Hello för företag

Microsoft Managed Desktop kräver att Windows Hello för företag aktiveras.

**Inte klar**

Windows Hello för företag är inaktiverat. Aktivera det genom att följa stegen i [Skapa en Windows Hello för företag-princip](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**Rådgivning**

Windows Hello för företag har inte installerats. Aktivera det genom att följa stegen i [Skapa en Windows Hello för företag-princip.](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)


### <a name="windows-10-update-rings"></a>Uppdateringsringar för Windows 10

Principen för windows 10-uppdateringsringen i Intune får inte ha som mål några Microsoft Managed Desktop-enheter.

**Inte klar**

Du har en princip för "uppdateringsringen" som riktar in alla enheter, alla användare eller båda. Ändra principen till att använda en uppgift som riktar sig mot en viss Azure AD-grupp som inte inkluderar några Microsoft Managed Desktop-enheter. Anvisningar finns i Hantera [programvaruuppdateringar för Windows 10 i Intune.](/mem/intune/protect/windows-update-for-business-configure)

**Rådgivning**

Kontrollera att alla principer för uppdateringsringen du har exkluderat **Modern Workplace-enheter –Alla** Azure AD-grupper. Om du har tilldelat Azure AD-användargrupper till de här principerna ska du se till att alla principer för uppdateringsringen även har uteslutit den **moderna arbetsplatsen -alla** Azure AD-gruppen som du lägger till microsoft hanterade skrivbordsanvändare i (eller en motsvarande grupp). Anvisningar finns i Hantera [programvaruuppdateringar för Windows 10 i Intune.](/mem/intune/protect/windows-update-for-business-configure) Både **moderna workplace-enheter –alla** och moderna arbetsplatsen **–** Alla Azure AD-grupper är grupper som vi skapar när du registrerar dig för Microsoft Managed Desktop, så du måste komma tillbaka för att utesluta den här gruppen efter registreringen.


## <a name="azure-active-directory-settings"></a>Azure Active Directory-inställningar

Du kan komma åt Azure Active Directory-inställningarna på [Azure Portal.](https://portal.azure.com)

### <a name="intune-enrollment"></a>Intune-registrering

Windows 10-enheter i din Azure AD-organisation måste kunna registreras automatiskt i Intune.

**Rådgivning**

Kontrollera att **MDM-användarens omfattning** är inställd **på Vissa** eller **Alla**, inte **Inget.** Om du väljer **Vissa** kommer du tillbaka efter registreringen och  väljer den moderna arbetsplatsen – alla Azure **AD-grupper** för grupper eller en motsvarande grupp som är riktad mot alla användare av Microsoft Managed Desktop.  Se [Konfigurera registrering för Windows-enheter med hjälp av Microsoft Intune.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)


### <a name="ad-hoc-subscriptions"></a>Ad hoc-prenumerationer

Ger information om hur du kontrollerar en inställning som (om denna är inställd på "falskt") kan förhindra att Roaming i företagstillståndet fungerar korrekt.

**Rådgivning**

Kontrollera att **AllowAdHocSubscriptions** är inställt på **Sant.** Annars kanske Inte Enterprise State Roaming fungerar. Mer information finns i [Set-MsolCompanySettings.](/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

Roaming i företagstillstånd ska vara aktiverat.

**Rådgivning**

Kontrollera att Roaming i företagstillstånd är aktiverat för **Alla** eller **för valda** grupper. Mer information finns i [Aktivera företagsroaming i Azure Active Directory.](/azure/active-directory/devices/enterprise-state-roaming-enable)

### <a name="licenses"></a>Licenser

Ett antal licenser krävs för att använda Microsoft Managed Desktop.

**Inte klar**

Du har inte alla licenser som du behöver för att använda Microsoft Managed Desktop. Mer information finns i [Microsofts teknik för hanterade skrivbord](../intro/technologies.md) och [Mer om licenser.](prerequisites.md#more-about-licenses)


### <a name="microsoft-managed-desktop-service-accounts"></a>Microsoft Hanterade skrivbordstjänstkonton

Vissa kontonamn kan vara i konflikt med kontonamn som skapats av Microsoft Managed Desktop för att hantera tjänsten Microsoft Managed Desktop.

**Inte klar**

Du har minst ett kontonamn som står i konflikt med kontonamn som skapats av Microsoft Managed Desktop. Arbeta med din Microsoft-kontorepresentant för att utesluta dessa kontonamn. Vi listar inte kontonamnen offentligt för att minimera säkerhetsriskerna. 


### <a name="security-administrator-roles"></a>Säkerhetsadministratörsroller

Användare med vissa säkerhetsroller måste ha de rollerna tilldelade i Microsoft Defender för Endpoint.

**Rådgivning**

Om du har användare tilldelade till någon av de här rollerna i din Azure AD-organisation bör du kontrollera att de även har tilldelats de här rollerna i Microsoft Defender för Slutpunkt. I annat fall kommer administratörer med de här rollerna inte att kunna komma åt administrationsportalen.

- Säkerhetsoperatör
- Global läsare

Mer information finns i [Skapa och hantera roller för rollbaserad åtkomstkontroll.](/windows/security/threat-protection/microsoft-defender-atp/user-roles)


### <a name="security-default"></a>Standardsäkerhet

Säkerhetsstandarder i Azure Active Directory hindrar Microsoft Managed Desktop från att hantera dina enheter.

**Inte klar**

Du har aktiverat standardinställningarna för säkerhet. Inaktivera säkerhetsstandarder och konfigurera principer för villkorsstyrd åtkomst. Mer information finns i Vanliga principer [för villkorsstyrd åtkomst.](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)

### <a name="self-service-password-reset"></a>Självbetjäning för återställning av lösenord

Självbetjäning för återställning av lösenord (SSPR) kan aktiveras för alla användare av Microsoft Managed Desktop exklusive Microsoft Managed Desktop-tjänstkonton. Mer information finns i Självbetjäning för lösenordsåterställning för Azure Active Directory: Aktivera så att användare låser upp sitt konto eller återställer lösenord med [självbetjäning för Azure Active Directory.](/azure/active-directory/authentication/tutorial-enable-sspr)

**Rådgivning**

Kontrollera att SSPR **Selected-inställningen inkluderar** Microsoft Managed Desktop-användare men exkluderar Microsoft Managed Desktop-tjänstkonton. Microsofts konton för den hanterade skrivbordstjänsten fungerar inte som förväntat när SSPR har aktiverats.  


### <a name="standard-user-role"></a>Standardanvändarroll

Förutom de användare som har tilldelats Azure AD-roller som global administratör och enhetsadministratör blir Microsoft Managed Desktop-användare standardanvändare utan lokal administratörsbehörighet. Alla andra användare tilldelas en standardanvändarroll när de startar sin Microsoft Managed Desktop-enhet.

**Rådgivning**

Microsoft Managed Desktop-användare har inte lokal administratörsbehörighet på sina Microsoft Managed Desktop-enheter när de har registrerat sig.

## <a name="microsoft-365-apps-for-enterprise"></a> Microsoft 365 Apps för företag

### <a name="onedrive"></a>OneDrive

Inställningen **Tillåt synkronisering endast på datorer som är ansluten till vissa domäner är** i konflikt med Microsoft Managed Desktop. Du kommer åt OneDrive-inställningarna i administrationscentret [för OneDrive.](https://admin.onedrive.com)

**Rådgivning**

Du använder inställningen Tillåt **synkronisering endast på datorer som är ansluten till vissa** domäner. Den här inställningen fungerar inte med Microsoft Managed Desktop. Inaktivera den här inställningen och konfigurera i stället OneDrive för att använda en princip för villkorsstyrd åtkomst. Mer [hjälp finns i Planera en villkorsstyrd åtkomstdistribution.](/azure/active-directory/conditional-access/plan-conditional-access)