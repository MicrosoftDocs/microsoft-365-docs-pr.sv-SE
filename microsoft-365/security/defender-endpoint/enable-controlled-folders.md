---
title: Aktivera kontrollerad mappåtkomst
keywords: Reglerad mappåtkomst, windows 10, windows defender, utpressningstrojaner, skydda, filer, mappar, aktivera, aktivera, använda
description: Lär dig hur du skyddar viktiga filer genom att aktivera reglerad mappåtkomst
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 1d09eaf04999478a0cd0b4907667a522a23fb39f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841984"
---
# <a name="enable-controlled-folder-access"></a>Aktivera kontrollerad mappåtkomst

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[Kontrollerad mappåtkomst](controlled-folders.md) hjälper dig att skydda värdefulla data från skadliga program och hot, till exempel utpressningstrojaner. Reglerad mappåtkomst ingår i Windows 10 och Windows Server 2019.

Du kan aktivera reglerad mappåtkomst på något av följande sätt:

* [Windows-säkerhet appen](#windows-security-app)
* [Microsoft Intune](#intune)
* [Hantering av mobila enheter (MDM)](#mobile-device-management-mdm)
* [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
* [Grupprincip](#group-policy)
* [PowerShell](#powershell)

[I granskningsläget](evaluate-controlled-folder-access.md) kan du testa hur funktionen fungerar (och granska händelser) utan att påverka den normala användningen av enheten.

Grupprincipinställningar som inaktiverar sammanslagning av lokala administratörslistor åsidosätter styrda inställningar för mappåtkomst. De åsidosätter även skyddade mappar och tillåtna appar som angetts av den lokala administratören via kontrollerad mappåtkomst. Dessa principer omfattar:

* Microsoft Defender Antivirus Konfigurera **lokala administratörskopplingsbeteenden för listor**
* System Center Endpoint Protection tillåt **användare att lägga till undantag och åsidosättningar**

Mer information om hur du inaktiverar lokal list sammanslagning finns i Förhindra eller tillåta användare att lokalt ändra inställningarna för [Microsoft Defender AV-principen.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged)

## <a name="windows-security-app"></a>Windows-säkerhet appen

1. Öppna Windows-säkerhet genom att välja sköldikonen i aktivitetsfältet. Du kan också söka efter Defender på **startmenyn.**

2. Välj panelen **& skydd mot** hot (eller sköldikonen på den vänstra menyraden) och välj sedan **Utpressningstrojanskydd**.

3. Ställ in växlingsknappen **för kontrollerad mappåtkomst** på **På**.

> [!NOTE]
> Om reglerad mappåtkomst är konfigurerad med grupprincip-, PowerShell- eller MDM-CSP:er ändras statusen i Windows-säkerhet-appen efter en omstart av enheten.
> Om funktionen är inställd på **granskningsläge** med något av dessa verktyg Windows-säkerhet appen statusen **Av.**
> Om du skyddar användarprofildata rekommenderar vi att användarprofilen ska finnas på standardplatsen Windows installationsenhet.

## <a name="intune"></a>Intune

1. Logga in på [Azure Portal och](https://portal.azure.com) öppna Intune.

2. Gå till **Profiler för**  >  **enhetskonfiguration Skapa**  >  **profil**.

3. Namnge profilen, välj Windows 10 **senare och Slutpunktsskydd** .  <br/> ![Skapa profil för slutpunktsskydd](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile) <br/>

4. Gå till **Konfigurera Windows Defender**  >  **för kontrollerad Exploit**  >  **Guard-mappåtkomst**  >  **Enable**.

5. Skriv sökvägen till varje program som har åtkomst till skyddade mappar och sökvägen till ytterligare mappar som behöver skyddas. Välj **Lägg till**.<br/> ![Aktivera kontrollerad mappåtkomst i Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)<br/>

   > [!NOTE]
   > Wilcard stöds för program, men inte för mappar. Undermappar är inte skyddade. Tillåtna appar fortsätter att utlösa händelser tills de startas om.

6. Välj **OK för** att spara alla öppna blad och **Skapa**.

7. Välj profilen Uppgifter **,** tilldela alla **användare till & enheter** och **Spara**.

## <a name="mobile-device-management-mdm"></a>Hantering av mobila enheter (MDM)

Använd [konfigurationstjänsten ./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) (CSP) för att tillåta appar att göra ändringar i skyddade mappar.

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. I Microsoft Endpoint Configuration Manager går du till **Tillgångar och Endpoint Protection** Windows Defender Exploit  >    >  **Guard.**

2. Välj **Home**  >  **Create Exploit Guard-policy**.

3. Ange ett namn och en beskrivning, välj **Kontrollerad mappåtkomst** och välj **Nästa**.

4. Välj om du vill blockera eller granska ändringar, tillåta andra appar eller lägga till andra mappar och välj **Nästa.**
   > [!NOTE]
   > Wilcard stöds för program, men inte för mappar. Undermappar är inte skyddade. Tillåtna appar fortsätter att utlösa händelser tills de startas om.

5. Granska inställningarna och välj **Nästa för** att skapa principen.

6. När principen har skapats stänger **du**.

## <a name="group-policy"></a>Grupprincip

1. Öppna grupprinciphanteringskonsolen på [](https://technet.microsoft.com/library/cc731212.aspx)din enhet för grupprinciphantering, högerklicka på det grupprincipobjekt du vill konfigurera och välj **Redigera.**

2. I **Redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.

3. Expandera trädet för att **Windows komponenter > Microsoft Defender Antivirus > Windows Defender Exploit Guard > kontrollerad mappåtkomst.**

4. Dubbelklicka på inställningen Konfigurera **reglerad mappåtkomst** och ställ in alternativet **Aktiverad**. I avsnittet alternativ måste du ange något av följande alternativ:
    * **Aktivera** – Skadliga och misstänkta appar tillåts inte att göra ändringar i filer i skyddade mappar. Ett meddelande visas i Windows händelseloggen.
    * **Inaktivera (standard)** – Funktionen kontrollerad mappåtkomst fungerar inte. Alla appar kan göra ändringar i filer i skyddade mappar.
    * **Granskningsläge** – Ändringar tillåts om en skadlig eller misstänkt app försöker göra en ändring i en fil i en skyddad mapp. Den registreras dock i den nya Windows där du kan bedöma hur det påverkar organisationen.
    * **Blockera endast diskändring** – Försök av icke betrodda appar att skriva till diskrekvent kommer att loggas Windows händelseloggen. De här loggarna finns i **Program- och tjänstloggar** > Microsoft > Windows > Windows Defender > Operational > ID 1123.
    * **Granska endast diskändring** – Endast försök att skriva till skyddade diskförsök registreras i händelseloggen för Windows **(under** Program- och tjänstloggar  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >    >  **Drift-ID 1124**). Försök att ändra eller ta bort filer i skyddade mappar registreras inte.

      ![Skärmbild av grupprincipalternativet Aktiverad och Granskningsläge markerat i listrutan](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> Om du vill aktivera reglerad mappåtkomst fullt  ut måste du ställa **in** grupprincipalternativet på Aktiverad och välja Blockera i den nedrullningrullningsalternativsmeny som visas.

## <a name="powershell"></a>PowerShell

1. Skriv **powershell** på Start-menyn, högerklicka på **Windows PowerShell** välj Kör **som administratör**.

2. Ange följande cmdlet:

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

Du kan aktivera funktionen i granskningsläge genom att ange i `AuditMode` stället för `Enabled` .

Används `Disabled` för att stänga av funktionen.

## <a name="see-also"></a>Se även

* [Skydda viktiga mappar med kontrollerad mappåtkomst](controlled-folders.md)
* [Anpassa kontrollerad mappåtkomst](customize-controlled-folders.md)
* [Utvärdera Microsoft Defender för Endpoint](evaluate-mde.md)
