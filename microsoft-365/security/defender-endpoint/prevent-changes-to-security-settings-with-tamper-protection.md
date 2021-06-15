---
title: Skydda säkerhetsinställningarna med manipuleringsskydd
ms.reviewer: shwjha, hayhov
manager: dansimp
description: Använd skydd mot manipulering för att förhindra att skadliga program ändrar viktiga säkerhetsinställningar.
keywords: skadlig programvara, defender, antivirus, skydd mot manipulering
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.date: 05/17/2021
ms.openlocfilehash: f6217cccf79b951c3103e1024ac74669d68645cd
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925941"
---
# <a name="protect-security-settings-with-tamper-protection"></a>Skydda säkerhetsinställningarna med manipuleringsskydd

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Skydd mot manipulering är tillgängligt för enheter som kör någon av följande versioner Windows:

- Windows 10
- Windows Server 2019
- Windows Server, version 1803 eller senare
- Windows Server 2016

## <a name="overview"></a>Översikt

Under vissa typer av cyberattacker försöker dåliga aktör att inaktivera säkerhetsfunktioner, till exempel antivirusskydd, på dina datorer. Dåliga aktör vill inaktivera dina säkerhetsfunktioner för att få enklare åtkomst till dina data, installera skadlig programvara eller på annat sätt utnyttja dina data, din identitet och dina enheter. Skydd mot manipulering förhindrar att den här typen av saker uppstår.

Med skydd mot manipulering förhindras skadliga program från att vidta åtgärder som:

- Inaktivera skydd mot virus och hot
- Inaktivera realtidsskydd
- Stänga av beteendeövervakning
- Inaktivera antivirus (till exempel IOfficeAntivirus (IOAV))
- Inaktivera moln levererat skydd
- Ta bort säkerhetsintelligensuppdateringar

### <a name="how-it-works"></a>Så här fungerar det

Skydd mot manipulering låser Microsoft Defender Antivirus och förhindrar att säkerhetsinställningarna ändras via appar och metoder som:

- Konfigurera inställningar i Registereditorn på din Windows enhet
- Ändra inställningar med PowerShell-cmdlets
- Redigera eller ta bort säkerhetsinställningar via grupprinciper

Skydd mot manipulering hindrar dig inte från att visa dina säkerhetsinställningar. Skydd mot manipulering påverkar inte heller hur antivirusappar från tredje part registreras i Windows-säkerhet program. Om din organisation använder e Windows 10 Enterprise E5 kan enskilda användare inte ändra inställningen för skydd mot manipulering. I så fall hanteras skydd mot manipulering av säkerhetsteamet.

### <a name="what-do-you-want-to-do"></a>Vad vill du göra?

| När du ska utföra den här uppgiften ... | Se det här avsnittet... |
|:---|:---|
| Hantera skydd mot manipulering i hela klientorganisationen <p>Använd Microsoft Defender Säkerhetscenter för att aktivera eller inaktivera skydd mot manipulering | [Hantera skydd mot manipulering för organisationen med hjälp av Microsoft Defender Säkerhetscenter](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) |
| Finjustera inställningar för manipuleringsskydd i organisationen <p>Använd Intune (Microsoft Endpoint Manager) för att aktivera eller inaktivera skydd mot manipulering. Du kan konfigurera skydd mot manipulering för vissa eller alla användare med den här metoden. | [Hantera skydd mot manipulering för din organisation med Intune](#manage-tamper-protection-for-your-organization-using-intune) |
| Aktivera (eller inaktivera) skydd mot manipulering för organisationen med Konfigurationshanteraren | [Hantera skydd mot manipulering för organisationen med innehavar bifoga med Konfigurationshanteraren, version 2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006) |
| Aktivera (eller inaktivera) skydd mot manipulering för en enskild enhet | [Hantera skydd mot manipulering på en enskild enhet](#manage-tamper-protection-on-an-individual-device) |
| Visa information om manipuleringsförsök på enheter | [Visa information om försök till manipulering](#view-information-about-tampering-attempts) |
| Granska dina säkerhetsrekommendationer | [Granska säkerhetsrekommendationer](#review-your-security-recommendations) |
| Granska listan med vanliga frågor och svar | [Bläddra i vanliga frågor och svar](#view-information-about-tampering-attempts) |

Beroende på vilken metod eller vilket hanteringsverktyg du använder för att aktivera skydd mot manipulering kan det finnas ett beroende av KARTOR (moln levererat skydd). 

Följande tabell innehåller information om metoder, verktyg och beroenden.

| Så här aktiveras skydd mot manipulering  | Beroende på KARTOR (moln levererat skydd)    |
|:----|:----|
| Microsoft Intune  | Nej |
| Microsoft Endpoint Configuration Manager + Klientorganisationens bifoga  |     Nej  |
| Microsoft Defender Säkerhetscenter ( [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) )    |     Ja |
| Microsoft 365 säkerhetscenter ( [https://security.microsoft.com](https://security.microsoft.com) )  |     Ja  |

## <a name="manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center"></a>Hantera skydd mot manipulering för organisationen med hjälp av Microsoft Defender Säkerhetscenter

Skydd mot manipulering kan aktiveras eller inaktiveras för klientorganisationen med hjälp av Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ). Här är några saker att tänka på:

- För närvarande är alternativet för att hantera skydd mot manipulering Microsoft Defender Säkerhetscenter skydd på som standard för nya distributioner. För befintliga distributioner är skydd av manipulering tillgängligt med möjlighet att välja alternativ, med planer på att registrera sig i standardmetoden inom kort. (Om du vill registrera dig väljer Microsoft Defender Säkerhetscenter i **Inställningar**  >  **Avancerade funktioner**  >  **Skydd mot manipulering**.) 

- När du använder Microsoft Defender Säkerhetscenter för att hantera skydd mot manipulering behöver du inte använda Intune eller metoden för att bifoga klientorganisation.

- När du hanterar skydd mot manipulering i Microsoft Defender Säkerhetscenter tillämpas inställningen på hela klientorganisationen och påverkar alla enheter som kör Windows 10, Windows Server 2016 eller Windows Server 2019. Om du vill finjustera skydd mot manipulering (t.ex. om du har skydd mot manipulering på vissa enheter men inaktiverat för andra) använder du [antingen Intune](#manage-tamper-protection-for-your-organization-using-intune) eller [Konfigurationshanteraren med klientorganisationens bifoga](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006).

- Om du har en hybridmiljö har inställningar för skydd mot manipulering i Intune företräde framför inställningar som konfigurerats i Microsoft Defender Säkerhetscenter. 

### <a name="requirements-for-managing-tamper-protection-in-the-microsoft-defender-security-center"></a>Krav för hantering av skydd mot manipulering i Microsoft Defender Säkerhetscenter

- Du måste ha rätt [behörighet,](/microsoft-365/security/defender-endpoint/assign-portal-access)till exempel global administratör, säkerhetsadministratör eller säkerhetsåtgärder.

- Dina Windows-enheter måste köra någon av följande versioner av Windows:
   - Windows 10
   - [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
   - Windows Server, version [1803](/windows/release-health/status-windows-10-1803) eller senare
   - [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
   - Mer information om versioner finns i Windows 10 [versionsinformation.](/windows/release-health/release-information)

- Dina enheter måste vara [onboarded to Microsoft Defender för Endpoint.](/microsoft-365/security/defender-endpoint/onboarding)

- Enheterna måste använda plattform mot skadlig programvara version 4.18.2010.7 (eller senare) och motor med skadlig programvara version 1.1.17600.5 (eller senare). ([Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer](manage-updates-baselines-microsoft-defender-antivirus.md).)

- [Moln levererat skydd](enable-cloud-protection-microsoft-defender-antivirus.md) måste vara aktiverat.

### <a name="turn-tamper-protection-on-or-off-in-the-microsoft-defender-security-center"></a>Aktivera (eller inaktivera skydd mot manipulering) i Microsoft Defender Säkerhetscenter 

![Aktivera skydd mot manipulering i Microsoft Defender Säkerhetscenter](images/mde-turn-tamperprotect-on.png)

1. Gå till Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) och logga in.

2. Välj **Inställningar**.

3. Gå till **Allmänna**  >  **avancerade funktioner** och aktivera sedan skydd mot manipulering.

## <a name="manage-tamper-protection-for-your-organization-using-intune"></a>Hantera skydd mot manipulering för din organisation med Intune

Om du ingår i organisationens säkerhetsteam och prenumerationen omfattar [Intune](/intune/fundamentals/what-is-intune)kan du aktivera (eller inaktivera) skydd mot manipulering för organisationen i administrationscentret för Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ). Använd Intune när du vill finjustera inställningarna för skydd mot manipulering. Om du till exempel vill aktivera skydd mot manipulering på vissa enheter, men inte alla, använder du Intune.

### <a name="requirements-for-managing-tamper-protection-in-intune"></a>Krav för hantering av skydd mot manipulering i Intune

- Du måste ha rätt [behörighet,](/microsoft-365/security/defender-endpoint/assign-portal-access)till exempel global administratör, säkerhetsadministratör eller säkerhetsåtgärder.

- Din organisation använder [Intune för att hantera enheter](/intune/fundamentals/what-is-device-management). ([Intune-licenser](/intune/fundamentals/licenses) krävs; Intune ingår i Microsoft 365 E5.)

- Dina Windows-enheter måste köra Windows 10 OS [1709,](/windows/release-health/status-windows-10-1709) [1803,](/windows/release-health/status-windows-10-1803) [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) eller senare. (Mer information om versioner finns i Windows 10 [versionsinformation](/windows/release-health/release-information).)

- Du måste använda Windows med [säkerhetsinformation](https://www.microsoft.com/wdsi/definitions) som uppdaterats till version 1.287.60.0 (eller senare).

- Enheterna måste använda plattform mot skadlig programvara version 4.18.1906.3 (eller senare) och motor med skadlig programvara version 1.1.15500.X (eller senare). ([Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer](manage-updates-baselines-microsoft-defender-antivirus.md).)

### <a name="turn-tamper-protection-on-or-off-in-intune"></a>Aktivera (eller inaktivera skydd mot manipulering) i Intune

![Aktivera manipuleringsskydd med Intune](images/turnontamperprotect-MEM.png)

1. Gå till [Microsoft Endpoint Manager och logga](https://endpoint.microsoft.com) in med ditt arbets- eller skolkonto.

2. Välj   >  **Konfigurationsprofiler för enheter**.

3. Skapa en profil som innehåller följande inställningar:
    - **Plattform: Windows 10 och senare**
    - **Profiltyp: Slutpunktsskydd**
    - **Kategori: Microsoft Defender Säkerhetscenter**
    - **Skydd mot manipulering: aktiverat**

4. Tilldela profilen till en eller flera grupper.

### <a name="are-you-using-windows-os-1709-1803-or-1809"></a>Använder du WINDOWS OS 1709, 1803 eller 1809?

Om du använder Windows 10 OS [1709,](/windows/release-health/status-windows-10-1709) [1803](/windows/release-health/status-windows-10-1803)eller [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)visas  inte Skydd mot manipulering i Windows-säkerhet program. I stället kan du använda PowerShell för att avgöra om skydd mot manipulering är aktiverat.

#### <a name="use-powershell-to-determine-whether-tamper-protection-is-turned-on"></a>Använda PowerShell för att avgöra om skydd mot manipulering är aktiverat

1. Öppna Windows PowerShell appen.

2. Använd [PowerShell-cmdleten Get-MpComputerStatus.](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps)

3. Leta efter i `IsTamperProtected` resultatlistan. (Värdet sant innebär *att* skydd mot manipulering har aktiverats.)

## <a name="manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006"></a>Hantera skydd mot manipulering för organisationen med Konfigurationshanteraren, version 2006

Om du använder [version 2006](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006)av Konfigurationshanteraren kan du hantera inställningar för skydd mot manipulering i Windows 10, Windows Server 2016 och Windows Server 2019 med en metod som kallas *klientorganisations* bifoga. Med Klientorganisationens fästa kan du synkronisera dina enheter med Konfigurationshanteraren för lokala enheter till administrationscentret i Microsoft Endpoint Manager och sedan leverera principer för slutpunktssäkerhetskonfiguration till lokala samlingar & enheter.

:::image type="content" source="images/win-security- exp-policy-endpt-security.png" alt-text="Windows-säkerhet upplevelsen i Endpoint Manager":::

> [!NOTE]
> Proceduren kan användas för att utöka skydd mot manipulering till enheter med Windows 10 och Windows Server 2019. Kontrollera att du behöver granska förutsättningarna och annan information i resurserna som nämns i den här proceduren.

1. Konfigurera klientorganisations bifoga. Mer information finns i koppla [Microsoft Endpoint Manager klientorganisation: Enhetsynkronisering och enhetsåtgärder](/mem/configmgr/tenant-attach/device-sync-actions).

2. Gå till [Microsoft Endpoint Manager Säkerhetsantivirusprogram](https://go.microsoft.com/fwlink/?linkid=2109431)för **slutpunkt i administrationscentret** och välj sedan + Skapa  >   **princip.**<br/> 
   - I listan **Plattform** väljer du **Windows 10 och Windows Server (ConfigMgr)**.  
   - I **profillistan** väljer du Windows-säkerhet **upplevelse (förhandsversion)**. <br/>

3. Distribuera principen till din enhetssamling.

### <a name="need-help-with-this-method"></a>Behöver du hjälp med den här metoden? 

Se följande resurser:

- [Inställningar för Windows-säkerhet-upplevelsen i Microsoft Intune](/mem/intune/protect/antivirus-security-experience-windows-settings)
- [Tech Community-blogg: Vi presenterar skydd mot manipulering för Configuration Manager-klientorganisationens bifogar klienter](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

## <a name="manage-tamper-protection-on-an-individual-device"></a>Hantera skydd mot manipulering på en enskild enhet

> [!NOTE]
> Skydd mot manipulering blockerar försök Microsoft Defender Antivirus ändra inställningarna via registret.
>
> Om du vill se till att skydd mot manipulering inte stör säkerhetsprodukter från tredje part  eller företagsinstallationsskript som ändrar de här inställningarna går du till **Windows-säkerhet** och uppdaterar Säkerhetsinformation till version 1.287.60.0 eller senare. (Se [Säkerhetsintelligensuppdateringar](https://www.microsoft.com/wdsi/definitions).)
>
> När du har gjort den här uppdateringen fortsätter skydd mot manipulering att skydda dina registerinställningar och loggar försöker ändra dem utan att returnera fel.

Om du är hemanvändare, eller om du inte omfattas av inställningar som hanteras av ett säkerhetsteam, kan du använda Windows-säkerhet-appen för att hantera skydd mot manipulering. Du måste ha rätt administratörsbehörighet på enheten för att ändra säkerhetsinställningarna, till exempel skydd mot manipulering.

Det här är vad som visas i Windows-säkerhet appen:

![Skydd mot manipulering är aktiverat i Windows 10 Home](images/tamperprotectionturnedon.png)

1. Välj **Start** och börja skriva *Säkerhet.* I sökresultatet väljer du **Windows-säkerhet**.

2. Välj **Virus & skydd mot hot**& för skydd mot  >  **hot**.

3. Ställ **in Skydd mot manipulering** på **På** eller **Av.**

## <a name="view-information-about-tampering-attempts"></a>Visa information om försök till manipulering

Manipuleringsförsök indikerar vanligtvis större cyberattacker. Bad actors try to change security settings as a way to persist and stay undetected. Om du är en del av organisationens säkerhetsteam kan du visa information om sådana försök och sedan vidta lämpliga åtgärder för att minimera hot.

När ett manipuleringsförsök upptäcks avhöjs en avisering i [Microsoft Defender Säkerhetscenter](/microsoft-365/security/defender-endpoint/portal-overview) ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

![Microsoft Defender Säkerhetscenter](images/tamperattemptalert.png)

Med [identifiering och åtgärd på slutpunkt](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) och [avancerade](/microsoft-365/security/defender-endpoint/advanced-hunting-overview) sökfunktioner i Microsoft Defender för Endpoint kan ditt säkerhetsteam undersöka och åtgärda sådana försök.

## <a name="review-your-security-recommendations"></a>Granska dina säkerhetsrekommendationer

Skydd mot manipulering [integreras & funktioner för sårbarhetshantering.](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) [Bland säkerhetsrekommendationerna](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) finns att se till att skydd mot manipulering är aktiverat. Du kan till exempel söka efter *manipulering,* så som visas i följande bild:

![Skydd mot manipulering resulterar i säkerhetsrekommendationer](/images/securityrecs-tamperprotect.jpg)

I resultatet kan du välja Aktivera skydd **mot manipulering om** du vill veta mer och aktivera det.

![Aktivera skydd mot manipulering](images/tamperprotectsecurityrecos.png)

Mer information om hur du & säkerhetshantering finns i [& säkerhetshantering i Microsoft Defender Säkerhetscenter.](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center)

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

### <a name="to-which-windows-os-versions-is-configuring-tamper-protection-is-applicable"></a>För vilka Windows OS-versioner gäller skydd mot manipulering?

Windows 10 OS [1709,](/windows/release-health/status-windows-10-1709) [1803,](/windows/release-health/status-windows-10-1803) [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)eller senare tillsammans med [Microsoft Defender för Slutpunkt.](/microsoft-365/security/defender-endpoint)

Om du använder Konfigurationshanteraren, version 2006, med innehavar bifoga kan skydd mot manipulering utökas till Windows Server 2019. Se [Klientorganisationens ansluta: Skapa och distribuera säkerhetsprincip för slutpunkt Antivirus från administrationscentret (förhandsversion)](/mem/configmgr/tenant-attach/deploy-antivirus-policy).

### <a name="will-tamper-protection-have-any-impact-on-third-party-antivirus-registration"></a>Kommer skydd mot manipulering att påverka antivirusregistrering från tredje part?

Nej. Antiviruserbjudanden från tredje part fortsätter att registrera sig i Windows-säkerhet program.

### <a name="what-happens-if-microsoft-defender-antivirus-is-not-active-on-a-device"></a>Vad händer om Microsoft Defender Antivirus inte är aktiv på en enhet?

Enheter som är onboarded to Microsoft Defender för Endpoint kommer att Microsoft Defender Antivirus i passiv form. Skydd mot manipulering fortsätter att skydda tjänsten och dess funktioner. 

### <a name="how-can-i-turn-tamper-protection-onoff"></a>Hur kan jag aktivera/inaktivera skydd mot manipulering?

Om du är hemanvändare kan du gå till [Hantera skydd mot manipulering på en enskild enhet](#manage-tamper-protection-on-an-individual-device).

Om du är en organisation som använder [Microsoft Defender](/microsoft-365/security/defender-endpoint)för Endpoint bör du kunna hantera skydd mot manipulering i Intune på liknande sätt som du hanterar andra funktioner för slutpunktsskydd. Se följande avsnitt i den här artikeln: 

- [Hantera skydd mot manipulering med Intune](#manage-tamper-protection-for-your-organization-using-intune)
- [Hantera skydd mot manipulering med Konfigurationshanteraren, version 2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [Hantera skydd mot manipulering med hjälp av Microsoft Defender Säkerhetscenter](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) 

### <a name="how-does-configuring-tamper-protection-in-intune-affect-how-i-manage-microsoft-defender-antivirus-through-my-group-policy"></a>Hur påverkar konfigureringsskyddet i Intune hur jag hanterar Microsoft Defender Antivirus via min grupprincip?

Din vanliga grupprincip gäller inte skydd mot manipulering, och ändringar i Microsoft Defender Antivirus ignoreras när skydd mot manipulering är på. 

### <a name="for-microsoft-defender-for-endpoint-is-configuring-tamper-protection-in-intune-targeted-to-the-entire-organization-only"></a>Konfigurerar du skydd mot manipulering i Intune enbart för hela organisationen för Microsoft Defender för Endpoint?

Konfigurering av skydd mot manipulering i Intune eller Microsoft Endpoint Manager kan riktas till hela organisationen och till specifika enheter och användargrupper.

### <a name="can-i-configure-tamper-protection-in-microsoft-endpoint-configuration-manager"></a>Kan jag konfigurera skydd mot manipulering i Microsoft Endpoint Configuration Manager?

Om du använder klientorganisationens bifoga kan du använda Microsoft Endpoint Configuration Manager. Se följande resurser:
- [Hantera skydd mot manipulering för organisationen med Konfigurationshanteraren, version 2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [Tech Community-blogg: Vi presenterar skydd mot manipulering för Klientorganisationens Konfigurationshanteraren-klientorganisationens klienter](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

### <a name="i-have-the-windows-e3-enrollment-can-i-use-configuring-tamper-protection-in-intune"></a>Jag har den Windows E3-registrering. Kan jag använda konfigurerar skydd mot manipulering i Intune?

För närvarande är konfigurering av skydd mot manipulering i Intune bara tillgängligt för kunder som har [Microsoft Defender för slutpunkt.](/microsoft-365/security/defender-endpoint)

### <a name="what-happens-if-i-try-to-change-microsoft-defender-for-endpoint-settings-in-intune-microsoft-endpoint-configuration-manager-and-windows-management-instrumentation-when-tamper-protection-is-enabled-on-a-device"></a>Vad händer om jag försöker ändra Microsoft Defender för slutpunktsinställningar i Intune, Microsoft Endpoint Configuration Manager och Windows Management Instrumentation när Manipuleringsskydd har aktiverats på en enhet?

Du kan inte ändra de funktioner som skyddas genom skydd mot manipulering. sådana ändringsförfrågningar ignoreras.

### <a name="im-an-enterprise-customer-can-local-admins-change-tamper-protection-on-their-devices"></a>Jag är företagskund. Kan lokala administratörer ändra skydd mot manipulering på sina enheter?

Nej. Lokala administratörer kan inte ändra inställningarna för skydd mot manipulering eller ändringar.

### <a name="what-happens-if-my-device-is-onboarded-with-microsoft-defender-for-endpoint-and-then-goes-into-an-off-boarded-state"></a>Vad händer om min enhet är inbyggd i Microsoft Defender för Endpoint och sedan hamnar i en status som inte är ombord?

Om en enhet är avstängd från Microsoft Defender för Endpoint aktiveras skydd mot manipulering, vilket är standardinställningen för ohanterade enheter. 

### <a name="will-there-be-an-alert-about-tamper-protection-status-changing-in-the-microsoft-defender-security-center"></a>Kommer det att finnas en varning om att status för manipuleringsskydd ändras i Microsoft Defender Säkerhetscenter?

Ja. Aviseringen visas [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) under **Aviseringar**.

Ditt säkerhetsteam kan också använda sökfrågor, till exempel följande exempel:

`DeviceAlertEvents | where Title == "Tamper Protection bypass"`

[Visa information om manipuleringsförsök](#view-information-about-tampering-attempts).

## <a name="see-also"></a>Se även

[Skydda Windows datorer med Endpoint Protection för Microsoft Intune](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

[Få en översikt över Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint)

[Bättre tillsammans: Microsoft Defender Antivirus och Microsoft Defender för Endpoint](why-use-microsoft-defender-antivirus.md)