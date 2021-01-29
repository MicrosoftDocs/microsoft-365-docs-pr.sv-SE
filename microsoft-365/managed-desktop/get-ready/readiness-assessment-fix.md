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
ms.openlocfilehash: 360cd50556b77f141d1585f42ac08ee5990b4851
ms.sourcegitcommit: f3059a0065496623e36e5a084cd2291e6b844597
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/28/2021
ms.locfileid: "50040526"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Åtgärda problem som hittats av verktyget för bedömning av beredskap

För varje kontroll rapporterar verktyget ett av fyra möjliga resultat:


|Resultat  |Betydelse  |
|---------|---------|
|Klar     | Ingen åtgärd krävs innan registrering kan slutföras.        |
|Rådgivning    | Följ stegen i verktyget eller den här artikeln för att få den bästa upplevelsen med registrering och för användare. Du *kan* slutföra registreringen, men du måste åtgärda problemen innan du distribuerar din första enhet.        |
|Inte klar | *Registrering misslyckas om du inte åtgärdar dessa problem.* Följ anvisningarna i verktyget eller den här artikeln för att lösa problemen.        |
|Fel | Azure Active Directory-rollen (AD) som du använder har inte tillräcklig behörighet för att köra den här kontrollen. |

> [!NOTE]
> Resultaten som rapporterats av det här verktyget återspeglar bara statusen för dina inställningar vid den specifika tidpunkt då du körde det. Om du senare gör ändringar i principer i Microsoft Intune, Azure Active Directory eller Microsoft 365 kan objekt som var "Redo" bli "Inte redo". Om du vill undvika problem med åtgärder som hanteras av Microsoft Managed Desktop kontrollerar du de specifika inställningarna som beskrivs i den här artikeln innan du ändrar några principer.

## <a name="microsoft-intune-settings"></a>Microsoft Intune-inställningar

Du kan komma åt Intune-inställningarna i administrationscentret för Microsoft Endpoint [Manager.](https://endpoint.microsoft.com)

### <a name="autopilot-deployment-profile"></a>Distributionsprofil för Autopilot

Du bör inte ha befintliga Autopilot-profiler som riktar sig till tilldelade eller dynamiska grupper med Microsoft Managed Desktop-enheter. Microsoft Hanterade skrivbord använder Autopilot för att tillhandahålla nya enheter.

**Inte klar**

Du har en Autopilot-profil som är tilldelad till alla enheter. Anvisningar finns i Registrera [Windows-enheter i Intune med Windows Autopilot.](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot) Efter Microsoft Hanterad skrivbordsregistrering ställer du in Autopilot-principen så att **den utesluter moderna workplace-enheter –alla** Azure AD-grupper.

**Rådgivning**

Se till att Dina Autopilot-profiler riktar sig mot en tilldelad eller dynamisk Azure AD-grupp som inte inkluderar Microsoft Managed Desktop-enheter. Anvisningar finns i Registrera [Windows-enheter i Intune med Windows Autopilot.](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot) Efter Registrering i Microsoft Hanterad skrivbordsversionen ställer du in dina Autopilot-profiler så att **de exkluderar moderna workplace-enheter – alla** Azure AD-grupper.


### <a name="certificate-connectors"></a>Certifikatkopplingar

Om du har några certifikatkopplingar som kommer att användas av de enheter som du vill registrera i Microsoft Managed Desktop bör kopplingarna inte ha några fel. Endast en av följande rekommendationer gäller för din situation, så kontrollera dem noggrant.

**Rådgivning**

Det finns inga certifikatkopplingar. Det är möjligt att du inte behöver några kopplingar, men du bör utvärdera om du kanske behöver några för nätverksanslutningen på dina Microsoft Managed Desktop-enheter. Mer information finns i Förbereda [certifikat och nätverksprofiler för Microsoft Managed Desktop.](certs-wifi-lan.md)

**Rådgivning**

Minst en certifikatkoppling har ett fel. Om du behöver den här anslutningen för att tillhandahålla certifikat till Microsoft Managed Desktop-enheter måste du lösa felet. Mer information finns i Förbereda [certifikat och nätverksprofiler för Microsoft Managed Desktop.](certs-wifi-lan.md)


**Rådgivning**

Du har minst en certifikatkoppling och inga fel rapporteras. Men inför distributionen kan du behöva skapa en profil för att kunna återanvända anslutningen för Microsoft Managed Desktop-enheter. Mer information finns i Förbereda [certifikat och nätverksprofiler för Microsoft Managed Desktop.](certs-wifi-lan.md)


### <a name="conditional-access-policies"></a>Villkorsstyrda åtkomstprinciper

Villkorsstyrda åtkomstprinciper får inte hindra Microsoft Managed Desktop från att hantera din Azure AD-organisation (klientorganisation) i Intune och Azure AD.

**Inte klar**

Du har minst en princip för villkorsstyrd åtkomst som riktar alla användare mot varandra. Under registreringen exkluderar vi Microsofts hanterade skrivbordskonton från relevanta villkorsstyrda åtkomstprinciper och tillämpar nya villkorsstyrda åtkomstprinciper för att begränsa åtkomsten till dessa konton. Efter registrering kan du granska villkorsstyrd åtkomstpolicyn för Microsoft Managed Desktop i Microsoft Endpoint Manager. Mer information om de här tjänstkontona finns [i Standard-operativsystem.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Rådgivning**

Du har villkorsstyrda åtkomstprinciper som kan hindra Microsoft Managed Desktop från att hantera Microsofts tjänst för hanterade skrivbord. Under registreringen exkluderar vi Microsofts hanterade skrivbordskonton från relevanta villkorsstyrda åtkomstprinciper och tillämpar nya villkorsstyrda åtkomstprinciper för att begränsa åtkomsten till dessa konton. Mer information om de här tjänstkontona finns [i Standard-operativsystem.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Fel**

Intune-administratörsrollen har inte tillräcklig behörighet för den här kontrollen. Du behöver också någon av dessa Azure AD-roller för att kunna köra den här kontrollen:

- Säkerhetsläsare
- Säkerhetsadministratör
- Villkorsstyrd åtkomstadministratör
- Global läsare
- Administratör för enheter


### <a name="device-compliance-policies"></a>Policyer för enhetsefterlevnad

Principer för Enhetsefterlevnad för Intune i din Azure AD-organisation kan påverka Microsoft-enheter som hanteras av datorn.

**Inte klar**

Du har minst en efterlevnadsprincip som riktar sig mot alla användare. Microsoft Hanterat skrivbord innehåller efterlevnadsprinciper som riktar sig till Microsoft-enheter som hanteras av Microsoft.  Ändra principen så att den riktar sig mot en specifik Azure AD-grupp som inte inkluderar några användare eller enheter som hanteras av Microsoft Managed Desktop. Instruktioner finns i Skapa [en efterlevnadsprincip i Microsoft Intune.](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)

**Rådgivning**

Se till att eventuella efterlevnadsprinciper du har inte riktar sig mot användare av Microsoft Managed Desktop. Instruktioner finns i Skapa [en efterlevnadsprincip i Microsoft Intune.](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)



### <a name="device-configuration-profiles"></a>Enhetskonfigurationsprofiler

Intune Device Configuration profiles in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.

**Inte klar**

Du har minst en konfigurationsprofil som riktar sig till alla användare, alla enheter eller båda. Återställ profilen så att den är mål för en viss Azure AD-grupp som inte inkluderar några Microsoft Managed Desktop-enheter. Instruktioner finns i Skapa [en profil med anpassade inställningar i Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)

**Rådgivning**

Se till att de konfigurationsprinciper du har inte omfattar Microsoft-enheter eller användare som hanteras av Microsoft. Instruktioner finns i Skapa [en profil med anpassade inställningar i Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)



### <a name="device-type-restrictions"></a>Begränsningar av enhetstyp

Microsoft-enheter med hanterade datorer måste ha tillåtelse att registrera sig i Intune.

**Inte klar**

Du har för närvarande minst en princip för registreringbegränsning konfigurerad för att förhindra registrering på Windows-enheter i Intune. Följ stegen i Ange [registreringbegränsningar för](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) varje princip för registreringsbegränsningar som riktar sig mot Microsoft Managed Desktop-användare och ändra **Windows-inställningen (MDM)** till **Tillåt.** Du kan däremot ange att alla **personligt ägda** **Windows-enheter (MDM)** ska **blockeras.** 


### <a name="enrollment-status-page"></a>Statussida för registrering

Du har för närvarande aktiverat ESP (Enrollment Status Page). Om du tänker delta i den offentliga förhandsversionen av Microsoft Managed Desktop av den här funktionen kan du ignorera det här objektet. Mer information finns i [Första körningsupplevelsen med Autopilot och statussidan för registrering.](../get-started/esp-first-run.md)

**Inte klar**

Standardprofilen ESP är inställd på Visa **program- och profilkonfigurationsstatus.** Inaktivera den här inställningen eller se till att tilldelningar till en Azure AD-grupp inte omfattar Microsoft Managed Desktop-enheter genom att följa stegen i Konfigurera statussidan [För registrering.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)

**Rådgivning**

Kontrollera att profiler som har inställningen Visa **app-** och profilkonfigurationsstatus inte har tilldelats till någon Azure AD-grupp som inkluderar Microsoft Managed Desktop-enheter. Mer information finns på [Konfigurera statussidan för registrering.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)

### <a name="microsoft-store-for-business"></a>Microsoft Store för företag

Vi använder Microsoft Store för företag och distribuerar företagsportalappen på Microsoft Hanterat skrivbord för att tillåta användare att installera vissa appar, till exempel Microsoft Project och Microsoft Visio (där det är tillåtet).

**Inte klar**

Microsoft Store för företag är inte aktiverat eller synkroniseras inte med Intune. Mer information finns i Hantera volymköpta appar från Microsoft Store för [företag med Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) och [Installera Intune-företagsportal på enheter.](../get-started/company-portal.md)

### <a name="multifactor-authentication"></a>Multifaktorautentisering

Multifaktorautentisering får inte hindra Microsoft Managed Desktop från att hantera din Azure AD-organisation (klientorganisation) i Intune och Azure AD.


**Inte klar**

Du har vissa principer för multifaktorautentisering som angetts **som** obligatoriska för villkorsstyrda åtkomstprinciper som har tilldelats till alla användare. Under registreringen exkluderar vi Microsofts hanterade skrivbordskonton från relevanta villkorsstyrda åtkomstprinciper och tillämpar nya villkorsstyrda åtkomstprinciper för att begränsa åtkomsten till dessa konton. Mer information om de här tjänstkontona finns [i Standard-operativsystem.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Rådgivning**

Du har multifaktorautentisering som krävs för villkorsstyrda åtkomstprinciper som kan hindra Microsoft Hanterat skrivbord från att hantera Microsofts hanterade skrivbordstjänst. Under registreringen exkluderar vi Microsofts hanterade skrivbordskonton från relevanta villkorsstyrda åtkomstprinciper och tillämpar nya villkorsstyrda åtkomstprinciper för att begränsa åtkomsten till dessa konton. Mer information om de här tjänstkontona finns [i Standard-operativsystem.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Fel**

Intune-administratörsrollen har inte tillräcklig behörighet för den här kontrollen. Du behöver också någon av dessa Azure AD-roller för att kunna köra den här kontrollen:

- Säkerhetsläsare
- Säkerhetsadministratör
- Villkorsstyrd åtkomstadministratör
- Global läsare
- Administratör för enheter


### <a name="powershell-scripts"></a>PowerShell-skript

Windows PowerShell-skript kan inte tilldelas på ett sätt som riktar sig till Microsoft Managed Desktop-enheter.  

**Rådgivning**

Kontrollera att Windows PowerShell-skript i Azure AD-organisationen inte är mål för Microsoft Hantera skrivbordsenheter eller användare. Tilldela inte ett PowerShell-skript till alla användare, alla enheter eller båda. Ändra principen så att en tilldelning används som mål för en viss Azure AD-grupp som inte inkluderar några Microsoft Managed Desktop-enheter eller användare. Mer information finns i Använda [PowerShell-skript på Windows 10-enheter i Intune.](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)

### <a name="region"></a>Region

Din region måste stödjas av Microsoft Managed Desktop.

**Inte klar**

Din Azure AD-organisationsregion stöds för närvarande inte av Microsoft Managed Desktop. Mer information finns i områden och språk [som stöds av Microsoft Managed Desktop.](../service-description/regions-languages.md)

**Rådgivning**

Ett eller flera av de länder där Azure AD-organisationen finns stöds inte av Microsoft Managed Desktop. Mer information finns i områden och språk [som stöds av Microsoft Managed Desktop.](../service-description/regions-languages.md)


### <a name="security-baselines"></a>Säkerhetsbaslinjer

Säkerhetsprinciper bör inte ha några Microsoft Managed Desktop-enheter som mål.

**Inte klar**

Du har en säkerhetsbaslinje som riktar sig till alla användare, alla enheter eller båda. Ändra principen så att en tilldelning används som mål för en viss Azure AD-grupp som inte inkluderar några Microsoft Managed Desktop-enheter. Instruktioner finns i Använda [säkerhetsbaslinjer för att konfigurera Windows 10-enheter i Intune.](https://docs.microsoft.com/mem/intune/protect/security-baselines)

**Rådgivning**

Kontrollera att eventuella principer för säkerhetsbaslinjer som du har utesluter Microsoft Managed Desktop-enheter. Instruktioner finns i Använda [säkerhetsbaslinjer för att konfigurera Windows 10-enheter i Intune.](https://docs.microsoft.com/mem/intune/protect/security-baselines) **The Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when youroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.


### <a name="windows-apps"></a>Windows-appar

Granska appar som du vill att Microsoft Hanterade skrivbord-användare ska ha.

**Rådgivning**

Du bör förbereda en inventering av de program som du vill att dina Microsoft Managed Desktop-användare ska ha. Eftersom dessa appar måste distribueras av Intune bör du utvärdera återanvändning av befintliga Intune-appar. Överväg att använda företagsportalen [(se Installera Intune-företagsportal](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) på enheter och ESP (Enrollment Status Page) för att distribuera appar till användarna. Mer information finns i [Program i Microsoft Managed Desktop](apps.md) och [First-run med Autopilot och statussidan för registrering.](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)

Du kan be din Microsoft-kontorepresentant för en fråga i Microsoft Endpoint Konfigurationshanteraren att identifiera de appar som är redo att migreras till Intune eller behöver justeras.


### <a name="windows-hello-for-business"></a>Windows Hello för företag

Microsoft Hanterat skrivbord kräver att Windows Hello för företag är aktiverat.

**Inte klar**

Windows Hello för företag är inaktiverat. Aktivera den genom att följa stegen i [Skapa en Princip för Windows Hello för företag](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**Rådgivning**

Windows Hello för företag är inte konfigurerat. Aktivera det genom att följa stegen i [Skapa en Windows Hello för företag-princip.](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)


### <a name="windows-10-update-rings"></a>Uppdateringsringar för Windows 10

Principen för Windows 10-uppdateringsringen i Intune får inte ha några Microsoft Managed Desktop-enheter som mål.

**Inte klar**

Du har en princip för uppdateringsring som riktar alla enheter, alla användare eller båda. Ändra principen så att en tilldelning används som mål för en viss Azure AD-grupp som inte inkluderar några Microsoft Managed Desktop-enheter. Instruktioner finns i Hantera [windows 10-programvaruuppdateringar i Intune.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)

**Rådgivning**

Se till att alla principer för uppdateringsringen som du har **exkluderat moderna workplace-enheter –alla** Azure AD-grupper. Om du har tilldelat Azure AD-användargrupper till de här principerna ska du se till att alla principer för uppdateringsringen även har uteslutit den moderna arbetsplatsen – alla Azure AD-grupper som du lägger till dina Microsoft Managed **Desktop-användare** i (eller en motsvarande grupp). Instruktioner finns i Hantera [windows 10-programvaruuppdateringar i Intune.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure) Både moderna workplace-enheter **–alla** och den moderna arbetsplatsen **–** Alla Azure AD-grupper är grupper som vi skapar när du registrerar dig för Microsoft Managed Desktop, så du måste gå tillbaka för att utesluta den här gruppen efter registreringen.


## <a name="azure-active-directory-settings"></a>Azure Active Directory-inställningar

Du kan komma åt Azure Active Directory-inställningarna på [Azure Portal.](https://portal.azure.com)

### <a name="intune-enrollment"></a>Intune-registrering

Windows 10-enheter i din Azure AD-organisation måste kunna registrera sig automatiskt i Intune.

**Rådgivning**

Kontrollera att **MDM-användaromfattningen** är inställd **på Vissa** eller **Alla,** inte **Inget.** Om du väljer **Vissa går** du tillbaka efter registreringen och  väljer Den moderna arbetsplatsen – Alla Azure **AD-gruppen** för grupper eller en motsvarande grupp som riktar sig till alla användare av Microsoft Managed Desktop.  Se [Konfigurera registrering för Windows-enheter med Microsoft Intune.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)


### <a name="ad-hoc-subscriptions"></a>Ad hoc-prenumerationer

Ger information om hur du kontrollerar en inställning som (om inställningen är "falskt") kan hindra Enterprise State Roaming från att fungera korrekt.

**Rådgivning**

Kontrollera att **AllowAdHocSubscriptions** är inställt på **Sant.** I annat fall kanske Roaming i företagstillstånd inte fungerar. Mer information finns i [Set-MsolCompanySettings.](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

Roaming i företagstillstånd ska vara aktiverat.

**Rådgivning**

Kontrollera att Roaming i företagstillstånd är aktiverat för **Alla** eller **för markerade** grupper. Mer information finns i Aktivera [företagsroaming i Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)

### <a name="licenses"></a>Licenser

Ett antal licenser krävs för att använda Microsoft Managed Desktop.

**Inte klar**

Du har inte alla licenser du behöver för att använda Microsoft Managed Desktop. Mer information finns i [teknikerna för Microsoft Managed Desktop](../intro/technologies.md) och Mer om [licenser.](prerequisites.md#more-about-licenses)


### <a name="security-account-names"></a>Namn på säkerhetskonto

Vissa namn på säkerhetskontot kan vara i konflikt med namn som skapats av Microsoft Managed Desktop.

**Inte klar**

Du har minst ett kontonamn som står i konflikt med de som skapats av Microsoft Managed Desktop. Arbeta med din Microsoft-kontorepresentant för att utesluta dessa kontonamn.


### <a name="security-administrator-roles"></a>Säkerhetsadministratörsroller

Användare med vissa säkerhetsroller måste ha de rollerna tilldelade i Microsoft Defender för Endpoint.

**Rådgivning**

Om du har användare tilldelade till någon av de här rollerna i din Azure AD-organisation bör du kontrollera att de också har tilldelats de här rollerna i Microsoft Defender för Slutpunkt. Annars kan administratörer med de här rollerna inte komma åt administrationsportalen.

- Säkerhetsoperatör
- Global läsare

Mer information finns i [Skapa och hantera roller för rollbaserad åtkomstkontroll.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)


### <a name="security-default"></a>Standardsäkerhet

Säkerhetsstandarder i Azure Active Directory förhindrar att Microsoft Hanterat skrivbord hanterar dina enheter.

**Inte klar**

Du har aktiverat säkerhet som standard. Inaktivera säkerhetsstandarder och konfigurera principer för villkorsstyrd åtkomst. Mer information finns i Vanliga principer [för villkorsstyrd åtkomst.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)

### <a name="self-service-password-reset"></a>Självbetjäning för återställning av lösenord

Självbetjäning för återställning av lösenord (SSPR) kan aktiveras för alla Microsoft Managed Desktop-användare utom Microsoft Managed Desktop-tjänstkonton. Mer information finns i [självstudiekursen: Gör](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)det möjligt för användare att låsa upp sitt konto eller återställa lösenord med självbetjäning för återställning av lösenord i Azure Active Directory.

**Rådgivning**

Kontrollera att inställningen SSPR **Selected omfattar** Microsoft-användare av hanterade skrivbord men exkluderar Microsoft Managed Desktop-tjänstkonton. Microsofts tjänstkonton för hanterad dator fungerar inte som förväntat när SSPR är aktiverat.  


### <a name="standard-user-role"></a>Standardanvändarroll

Förutom de användare som har tilldelats Azure AD-roller som global administratör och enhetsadministratör är Microsoft Managed Desktop-användare standardanvändare utan lokal administratörsbehörighet. Alla andra användare tilldelas en standardanvändarroll när de startar sin Microsoft Managed Desktop-enhet.

**Rådgivning**

Microsoft Managed Desktop-användare har inte lokal administratörsbehörighet på sina Microsoft Managed Desktop-enheter när de har registrerat sig.

## <a name="microsoft-365-apps-for-enterprise"></a> Microsoft 365 Apps för företag

### <a name="onedrive"></a>OneDrive

Inställningen **Tillåt synkronisering endast på datorer som är ansluten till vissa domäner kommer att** vara i konflikt med Microsoft Managed Desktop. Du kan komma åt OneDrive-inställningarna i administrationscentret [för OneDrive.](https://admin.onedrive.com)

**Rådgivning**

Du använder inställningen Tillåt **synkronisering endast på datorer som är ansluten till vissa domäner.** Den här inställningen fungerar inte med Microsoft Managed Desktop. Inaktivera den här inställningen och konfigurera istället OneDrive för användning av en princip för villkorsstyrd åtkomst. Se [Planera en distribution av villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) om du behöver hjälp.
