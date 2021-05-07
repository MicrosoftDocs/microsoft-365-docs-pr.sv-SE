---
title: Registrera Windows 10-enheter via grupprincip
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Använd grupprincip för att distribuera konfigurationspaketet på Windows 10-enheter så att de förs in i tjänsten.
ms.openlocfilehash: 284de5169324b6da4038cfe0b50b2f2ffa40e3fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "52162761"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>Introducera Windows 10 enheter med grupprincip 

**Gäller för:**

- [Microsoft 365 Dataförlustskydd i slutpunkt (DLP)](./endpoint-dlp-learn-about.md)
- Grupprincip

> [!NOTE]
> Om du vill använda grupprincipuppdateringar (GP) för att distribuera paketet måste du använda Windows Server 2008 R2 eller senare.

> För Windows Server 2019 kan du behöva ersätta NT AUTHORITY\Well-Known-System-Account med NT AUTHORITY\SYSTEM för den XML-fil som grupprincipinställning skapar.

## <a name="onboard-devices-using-group-policy"></a>Registrera enheter med grupprinciper

1. Öppna filen för GP.zip konfigurationspaket *(DeviceComplianceOnboardingPackage.zip)* som du laddade ned från guiden för registrering av tjänster. Du kan också hämta paketet från [Microsofts efterlevnadscenter](https://compliance.microsoft.com/compliancesettings/deviceonboarding)

2. Välj Registrering av enhet **Inställningar**  >  **navigeringsfönstret.**

3. Välj **Grupprincip i** fältet **Distributionsmetod.**

4. Klicka **på Ladda ned** paket och spara .zip filen.

5. Extrahera innehållet i filen .zip till en delad, skrivskyddad plats som kan nås av enheten. Du bör ha en mapp med namnet *OptionalParamsPolicy* och filen *DeviceComplianceLocalOnboardingScript.cmd.*

6. Öppna GPMC [(Group Policy Management Console),](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) högerklicka på det grupprincipobjekt (GPO) du vill konfigurera och klicka på **Redigera.**

7. I **redigeraren för grupprinciphantering** går du **till Datorkonfiguration** **och** sedan Inställningar och **inställningar för Kontrollpanelen.**

8. Högerklicka på **Schemalagda aktiviteter**, peka på **Nytt** och klicka sedan på **Direktaktivitet (minst Windows 7).**

9. I **uppgiftsfönstret** som öppnas går du till **fliken** Allmänt. Under **Säkerhetsalternativ klickar** du **på Ändra användare eller grupp,** skriver SYSTEM och klickar sedan **på Kontrollera namn** och sedan på **OK.** NT AUTHORITY\SYSTEM visas som det användarkonto som aktiviteten körs som.

10. Välj **Kör om användaren är inloggad eller inte** och markera kryssrutan Kör med **högst** behörighet.

11. Gå till fliken **Åtgärder** och klicka på **Ny...** Kontrollera att **Starta ett program** är markerat i **fältet** Åtgärd. Ange filnamnet och platsen för den delade *filen WindowsDefenderATPOnboardingScript.cmd.*

12. Klicka **på OK** och stäng alla öppna GPMC-fönster.


## <a name="offboard-devices-using-group-policy"></a>Offboard-enheter med grupprincip
Av säkerhetsskäl upphör paketet som används till Offboard-enheter 30 dagar efter det datum då det laddades ned. Utgångna offboarding-paket som skickats till en enhet kommer att avvisas. När du laddar ned ett offboarding-paket meddelas du om paketens utgångsdatum och det inkluderas också i paketnamnet.

> [!NOTE]
> Principer för onboarding och offboarding får inte distribueras på samma enhet samtidigt, annars kan det orsaka oförutsägbara tavlor.

1. Hämta offboarding-paketet från [Microsofts efterlevnadscenter.](https://compliance.microsoft.com/compliancesettings/deviceonboarding)

2. I navigeringsfönstret väljer du **Inställningar**  >  **//Device onboarding**  >  **Offboarding**.

3. Välj **Grupprincip i** fältet **Distributionsmetod.**

4. Klicka **på Ladda ned** paket och spara .zip filen.

5. Extrahera innehållet i filen .zip till en delad, skrivskyddad plats som kan nås av enheten. Du bör ha en fil med *namnet DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

6. Öppna GPMC [(Group Policy Management Console),](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) högerklicka på det grupprincipobjekt (GPO) du vill konfigurera och klicka på **Redigera.**

7. I **redigeraren för grupprinciphantering** går du **till Datorkonfiguration,** **inställningar** och sedan Inställningar på **Kontrollpanelen.**

8. Högerklicka på **Schemalagda aktiviteter**, peka på **Nytt** och klicka sedan på **Direktaktivitet.**

9. I **uppgiftsfönstret** som öppnas går du till **fliken** Allmänt. Välj det lokala systemanvändarkontot (INBYGGD\SYSTEM) under **Säkerhetsalternativ**.

10. Markera **Kör om användaren är inloggad eller inte** och markera **kryssrutan** Kör med högst behörighet.

11. Gå till fliken **Åtgärder** och klicka på **Nytt...**. Kontrollera att **Starta ett program** är markerat i **fältet** Åtgärd. Ange filnamn och plats för den delade filen *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd.*

12. Klicka **på OK** och stäng alla öppna GPMC-fönster.

> [!IMPORTANT]
> Offboarding gör att enheten slutar skicka sensordata till portalen men data från enheten.


## <a name="monitor-device-configuration"></a>Övervaka enhetskonfiguration
Med Grupprincip finns det inte något alternativ för att övervaka distribution av principer på enheter. Övervakning kan utföras direkt i portalen eller med hjälp av de olika distributionsverktygen.

## <a name="monitor-devices-using-the-portal"></a>Övervaka enheter med hjälp av portalen
1. Gå till [Microsofts efterlevnadscenter.](https://compliance.microsoft.com/)
2. Klicka **på Listan** Enheter.
3. Kontrollera att enheter visas.

> [!NOTE]
> Det kan ta flera dagar innan enheter börjar visas i **listan Enheter.** Det inkluderar den tid det tar för principerna att distribueras till enheten, den tid det tar innan användaren loggar in och den tid det tar för slutpunkten att starta rapporteringen.


## <a name="related-topics"></a>Relaterade ämnen
- [Introducera Windows 10 enheter med Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter](dlp-configure-endpoints-mdm.md)
- [Registrera Windows 10-enheter med ett lokalt skript](dlp-configure-endpoints-script.md)
- [Registrera enheter för icke beständiga VDI-enheter (Virtual Desktop Infrastructure)](dlp-configure-endpoints-vdi.md)
- [Köra ett identifieringstest på en nyligen onboarded Microsoft Defender för Slutpunkt-enheter](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Felsöka Microsoft Defender Avancerat skydd onboarding-problem](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)