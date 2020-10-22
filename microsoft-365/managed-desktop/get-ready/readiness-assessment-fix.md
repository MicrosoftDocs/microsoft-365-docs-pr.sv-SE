---
title: Åtgärda problem som upptäckts av verktyget för bedömning av beredskap
description: Detaljerade åtgärder att vidta för varje problem som verktyget hittar
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2c9638dc7b8c6d095b87cf81114f3812c8362597
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656157"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Åtgärda problem som upptäckts av verktyget för bedömning av beredskap

För varje kontroll rapporteras ett av tre möjliga resultat:


|Resultat  |Betydelse  |
|---------|---------|
|Förbereder     | Ingen åtgärd krävs innan du slutför registreringen.        |
|Rådgivare    | Följ stegen i verktyget eller den här artikeln för att få bästa möjliga upplevelse av registrering och användare. Du *kan* slutföra registreringen, men du måste åtgärda dessa problem innan du distribuerar den första enheten.        |
|Inte klart | *Registreringen Miss lyckas om du inte åtgärdar dessa problem.* Följ stegen i verktyget eller den här artikeln för att åtgärda dem.        |

## <a name="microsoft-intune-settings"></a>Microsoft Intune-inställningar

### <a name="autopilot-deployment-profile"></a>Distributions profil för autopilot

Du bör inte ha några befintliga autopilot-profiler som riktar sig till tilldelade eller dynamiska grupper som används av Microsoft Managed Desktop. Microsoft Managed Desktop använder autopilot för att etablera nya enheter.

**Inte klart**

Du har en autopilot-profil som kopplats till alla enheter. Anvisningar finns i [registrera Windows-enheter i Intune med hjälp av Windows autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot). Efter Microsoft Managed Desktop-registrering ställer du in autopilot-principen så att den **moderna arbets ytan visas-alla** Azure AD-grupper.

**Rådgivare**

Se till att dina autopilot-profiler är riktade till en tilldelad eller dynamisk Azure AD-grupp som inte innehåller Microsoft Managed Station ära enheter som kommer att skapas vid registrering. Anvisningar finns i [registrera Windows-enheter i Intune med hjälp av Windows autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot). Efter Microsoft Managed Desktop-registrering ställer du in autopilot-principen så att den **moderna arbets ytan visas-alla** Azure AD-grupper.


### <a name="certificate-connectors"></a>Certifikat anslutningar

Om du har några certifikat anslutningar som används av de enheter som du vill registrera på Microsoft Managed Desktop kan de inte ha några fel. Endast en av följande rådgivare kommer att gälla för din situation, så kolla dem noggrant.

**Rådgivare**

Det finns inga certifikat kopplingar. Det är möjligt att du inte behöver några kopplingar, men du bör utvärdera om du kan behöva vissa för nätverks anslutningen till Microsoft Managed Station ära datorer. Mer information finns i [förbereda certifikat och nätverks profiler för Microsoft Managed Desktop](certs-wifi-lan.md).

**Rådgivare**

Minst ett certifikat har ett fel. Om du behöver den här kopplingen för anslutning till Microsoft-hanterade Skriv bords enheter måste du lösa problemet. Mer information finns i [förbereda certifikat och nätverks profiler för Microsoft Managed Desktop](certs-wifi-lan.md).


**Rådgivare**

Du har minst en certifikatanslutningsappen och inga fel rapporteras. Men det kan hända att du måste skapa en profil för att återanvända Connector för Microsoft-hanterade Station ära datorer. Mer information finns i [förbereda certifikat och nätverks profiler för Microsoft Managed Desktop](certs-wifi-lan.md).


### <a name="conditional-access-policies"></a>Principer för villkorsstyrd åtkomst

Principer för villkorsstyrd åtkomst i din Azure AD-organisation får inte vara riktade till Microsoft Manage Desktop-användare.

**Inte klart**

Du har minst en princip för villkorsstyrd åtkomst som är riktad till alla användare. Återställ principen för en viss Azure AD-grupp som inte innehåller Azure AD-gruppen av Microsoft Managed Desktop Service-konton som kommer att skapas vid registrering. Anvisningar finns i [villkorlig åtkomst: användare och grupper](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).

**Rådgivare**

Se till att alla principer för villkorsstyrd åtkomst du har exkluderar den **moderna arbets plats tjänstens konton** Azure AD-grupp. Anvisningar finns i [Justera villkorlig åtkomst](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access). Den **moderna arbets plats tjänsten** är en dynamisk grupp som vi skapar för tjänsten när du registrerar dig. Du måste komma tillbaka för att utesluta den här gruppen efter registreringen. Mer information om dessa tjänst konton finns i [vanliga rutiner](../service-description/operations-and-monitoring.md#standard-operating-procedures).


### <a name="device-compliance-policies"></a>Principer för enhetskompatibilitet

Principer för hantering av efterlevnadsprinciper i din Azure AD-organisation får inte uppfylla alla hanterade Microsoft-användare.

**Inte klart**

Du har minst en efterlevnadsprincip som är riktad till alla användare. Återställ principen för en viss Azure AD-grupp som inte innehåller några hanterade Microsoft-användare. Anvisningar finns i [skapa en policy för efterlevnad i Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).

**Rådgivare**

Se till att eventuella efterlevnadsprinciper som du inte har Microsoft-hanterade Skriv bords användare. Anvisningar finns i [skapa en policy för efterlevnad i Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).



### <a name="device-configuration-policies"></a>Konfigurations principer för enheter

Konfigurations principer för Intune-enheter i din Azure AD-organisation får inte vara riktade till Microsoft Manage Station ära enheter eller användare.

**Inte klart**

Du har minst en konfigurations princip som är riktad till alla användare, alla enheter eller både och. Återställ principen för en viss Azure AD-grupp som inte innehåller några Microsoft-hanterade Skriv bords enheter. Anvisningar finns i [skapa en policy för efterlevnad i Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).

**Rådgivare**

Se till att eventuella efterlevnadsprinciper som du inte har Microsoft-hanterade Skriv bords enheter eller-användare. Anvisningar finns i [skapa en policy för efterlevnad i Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).



### <a name="device-type-restrictions"></a>Begränsningar för enhets typer

Microsoft Managed Station ära datorer måste tillåtas att registrera i Intune.

**Inte klart**

Följ stegen i [Ange registrerings begränsningar](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) för att ändra inställningen till **Tillåt**.


### <a name="enrollment-status-page"></a>Sidan registrerings status

Du har för närvarande sidan registrerings status (ESP) aktive rad. Om du deltar i den offentliga för hands versionen av den här funktionen kan du ignorera det här objektet. Mer information finns i förstagångskörningen [med autopilot och sidan registrerings status](../get-started/esp-first-run.md).

**Inte klart**

Du har aktiverat ESP-standardprofilen för att **Visa konfigurations förlopp för appar och profiler**. Inaktivera den här inställningen genom att följa anvisningarna i [Konfigurera sidan registrerings status](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).

**Rådgivare**

Kontrol lera att alla profiler som har **statusen Visa program-och profil konfiguration** inte är tilldelade någon Azure AD-grupp som innehåller Microsoft Managed Station ära enheter. Mer information finns i [Konfigurera sidan registrerings status](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).

### <a name="intune-enrollment"></a>Intune-registrering

Windows 10-enheter i din Azure AD-organisation måste registreras automatiskt i Intune.

**Inte klart**

Användare i din Azure AD-organisation registreras inte automatiskt i Microsoft Intune. Ändra omfattningen för MDM-användare till **vissa** eller **alla**. Om du väljer. Lite * *, kom tillbaka efter registreringen och välj den **moderna arbets platsen – alla** Azure AD-grupper för **grupper**.


### <a name="microsoft-store-for-business"></a>Microsoft Store för företag

Vi använder Microsoft Store för företag så att du kan ladda ned företags Portal för att distribuera vissa program, till exempel Microsoft Project och Microsoft Visio.

**Inte klart**

Microsoft Store för företag är antingen inte aktiverat eller synkroniseras inte med Intune. Mer information finns i [så här hanterar du volym köps program från Microsoft Store för företag med Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) och [Installera Intune företags Portal på enheter](../get-started/company-portal.md).

### <a name="multi-factor-authentication"></a>Multifaktorautentisering

Multifaktorautentisering får inte på ett oavsiktligt sätt tillämpas på Microsoft Managed Desktop Service-konton.


**Inte klart**

Du har vissa principer för multifaktorautentisering (MFA) inställda som "obligatoriskt" för principer för villkorsstyrd åtkomst som är tilldelade till alla användare. Ändra principen för att använda en tilldelning som är riktad till en viss Azure AD-grupp som inte innehåller Microsoft hanterade Station ära datorer. Mer information finns i [principer för villkorsstyrd åtkomst](#conditional-access-policies) och [villkorsstyrd åtkomst: Kräv MFA för alla användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).

**Rådgivare**

Se till att alla villkorsstyrda åtkomst principer som kräver MFA exkluderar den **moderna arbets platsen – alla** Azure AD-grupper. Mer information finns i [principer för villkorsstyrd åtkomst](#conditional-access-policies) och [villkorsstyrd åtkomst: Kräv MFA för alla användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa). Den **moderna arbets platsen – alla** Azure AD-grupper är en dynamisk grupp som vi skapar när du registrerar dig på Microsoft Managed Desktop, så att du måste komma tillbaka till den här gruppen efter registrering.



### <a name="powershell-scripts"></a>PowerShell-skript

Windows PowerShell-skript kan inte tilldelas på ett sätt som riktar sig till Microsoft Managed Station ära enheter.  

**Rådgivare**

Kontrol lera att Windows PowerShell-skript i din Azure AD-organisation inte har några Microsoft-hanterings enheter eller användare. Mer information finns i [använda PowerShell-skript på Windows 10-enheter i Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).

### <a name="region"></a>Region

Din region måste vara kompatibel med Microsoft Managed Desktop.

**Inte klart**

Din organisations region för Azure AD stöds för närvarande inte av Microsoft Managed Desktop. Mer information finns i [regioner och språk som stöds i Microsoft hanterade skriv bord](../service-description/regions-languages.md).

**Rådgivare**

Ett eller flera av de länder där din Azure AD-organisation finns stöds inte av Microsoft Managed Desktop. Mer information finns i [regioner och språk som stöds i Microsoft hanterade skriv bord](../service-description/regions-languages.md).


### <a name="security-baselines"></a>Säkerhets bas linjer

Principer för säkerhets rikt linjer ska inte vara riktade till enheter som hanteras av Microsoft.

**Inte klart**

Du har en säkerhets bas profil som är riktad till alla användare, alla enheter eller både och. Ändra principen för att använda en tilldelning som är riktad till en viss Azure AD-grupp som inte innehåller Microsoft hanterade Station ära datorer. Anvisningar finns i [använda säkerhets bas linjer för att konfigurera Windows 10-enheter i Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).

**Rådgivare**

Se till att alla principer för säkerhets rikt linjer du har exkluderar Microsoft Managed Station ära enheter. Anvisningar finns i [använda säkerhets bas linjer för att konfigurera Windows 10-enheter i Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines). **Moderna arbets plats enheter-alla** Azure AD-grupper är en dynamisk grupp som vi skapar när du registrerar dig på Microsoft Managed Desktop, så att du måste komma tillbaka till den här gruppen efter registrering.


### <a name="windows-apps"></a>Windows-appar

Granska de program du vill att Microsoft Managed Desktop-användarna ska ha.

**Rådgivare**

Du bör förbereda en inventering av de program som du vill att Microsoft Managed Desktop-användarna ska ha. Kontrol lera att dessa appar kan distribueras av Intune. Mer information finns i [program på Microsoft Managed Desktop](apps.md).

Du kan be din Microsoft-representant om en fråga i Microsoft Endpoint Configuration Manager att identifiera de program som är redo att migreras till Intune eller behöver justeras.


### <a name="windows-hello-for-business"></a>Windows Hello för företag

Microsoft Managed Desktop kräver att Windows Hello för företag aktive ras.

**Inte klart**

Windows Hello för företag är inaktiverat. Aktivera den genom att följa anvisningarna i [skapa en Windows Hello för företag-princip](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**Rådgivare**

Windows Hello för företag är inte konfigurerat. Aktivera den genom att följa anvisningarna i [skapa en Windows Hello för företag-policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).


### <a name="windows-10-update-rings"></a>Windows 10-uppdaterings ringar

Din "Windows 10 Update ring"-princip i Intune får inte uppfylla alla hanterade Microsoft-enheter.

**Inte klart**

Du har en "uppdatera ring"-princip som är riktad till alla enheter, alla användare eller både och. Ändra principen för att använda en tilldelning som är riktad till en viss Azure AD-grupp som inte innehåller Microsoft hanterade Station ära datorer. Anvisningar finns i [hantera program uppdateringar för Windows 10 i Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).

**Rådgivare**

Se till att eventuella uppdaterings rings principer du har exkluderar den **moderna arbets platsen – alla** Azure AD-grupper. Anvisningar finns i [hantera program uppdateringar för Windows 10 i Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure). **Moderna arbets plats enheter-alla** Azure AD-grupper är en dynamisk grupp som vi skapar när du registrerar dig på Microsoft Managed Desktop, så att du måste komma tillbaka till den här gruppen efter registrering.


## <a name="azure-active-directory-settings"></a>Azure Active Directory-inställningar


### <a name="ad-hoc-subscriptions"></a>Ad hoc-abonnemang

Här beskrivs hur du kontrollerar en inställning som (om värdet är "falskt") kan hindra företags tillstånd från att fungera korrekt.

**Rådgivare**

Kontrol lera att **AllowAdHocSubscriptions** är inställt på **True**. I annat fall kanske företags statusen roaming inte fungerar. Mer information finns i [set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

Roaming för företags status bör vara aktiverat.

**Rådgivare**

Kontrol lera att organisationens centrala nätverks tillstånd är aktiverat för **alla** eller för **markerade** grupper. Mer information finns i [Aktivera roaming för företags tillstånd i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).

### <a name="licenses"></a>Licenser

Det krävs flera olika licenser för att använda Microsoft Managed Desktop.

**Inte klart**

Du har inte alla licenser som du behöver för att använda Microsoft Managed Desktop. Mer information finns i [Microsoft hanterad Skriv bords teknik](../intro/technologies.md) och [mer om licenser](prerequisites.md#more-about-licenses).


### <a name="security-account-names"></a>Namn på säkerhets konton

Vissa namn på säkerhets konton kan vara i konflikt med dem som har skapats av Microsoft Managed Desktop.

**Inte klart**

Du har minst ett konto namn som är oförenliga med dem som skapas av Microsoft Managed Desktop. Arbeta med ditt Microsoft-konto för att utesluta dessa konto namn.


### <a name="security-administrator-roles"></a>Säkerhets administratörs roller

Användare med vissa säkerhets roller måste ha kopplade till dem i Microsoft Defender för slut punkter.

**Rådgivare**

Om du har någon av de här rollerna i din Azure AD-organisation kontrollerar du att de också har tilldelats dessa roller i Microsoft Defender för slut punkter. Annars kommer administratörer med dessa roller inte att kunna använda administrations portalen.

- Säkerhets läsare
- Säkerhets ansvarig
- Global läsare

Mer information finns i [skapa och hantera roller för rollbaserad åtkomst kontroll](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).


### <a name="security-default"></a>Säkerhets standard

Säkerhets inställningar i Azure Active Directory kommer inte att hantera dina enheter på Microsoft.

**Inte klart**

Säkerhets inställningarna är aktiverat. Inaktivera säkerhets standarder och konfigurera villkorsstyrda åtkomst principer. Mer information finns i [vanliga principer för villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).

### <a name="self-service-password-reset"></a>Självbetjäning för återställning av lösen ord

Självbetjäning för återställning av lösen ord (SSPR) måste aktive ras.

**Inte klart**

SSPR måste vara aktiverat för alla användare. Om det inte är det kan inte Microsoft Managed Desktop-tjänsten fungera. Mer information finns i [själv studie kursen: Låt användare låsa upp sina konton eller återställa lösen ord med hjälp av återställning av Azure Active Directory Self-Service](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).

**Rådgivare**

Kontrol lera att SSPR **valda** inställningar innehåller Microsoft Managed Station ära datorer.

### <a name="standard-user-role"></a>Standard användar roll

Microsoft Managed Desktop-användare ska vara vanliga användare utan lokala administratörs behörigheter. De tilldelas en standard användar roll när de startar sin Microsoft-hanterade Station.

**Rådgivare**

Microsoft Managed Station ära datorer bör inte ha lokala administratörs behörigheter innan de registreras.

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365-appar för företag

### <a name="onedrive-for-business"></a>OneDrive för företag

Inställningen **Tillåt synkronisering endast på datorer som är anslutna till vissa domäner** visas i konflikt med Microsoft Managed Desktop.

**Rådgivare**

Du använder alternativet **Tillåt synkronisering endast på datorer som är anslutna till vissa domän** inställningar. Den här inställningen fungerar inte med Microsoft Managed Desktop. Inaktivera den här inställningen och konfigurera i stället OneDrive för företag för användning av villkorsstyrd åtkomst policy. Se [Planera en distribution för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) för hjälp.

