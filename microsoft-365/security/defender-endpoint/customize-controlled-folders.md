---
title: Anpassa kontrollerad mappåtkomst
description: Lägg till andra mappar som ska skyddas med kontrollerad mappåtkomst eller tillåta appar som felaktigt blockerar ändringar av viktiga filer.
keywords: Kontrollerad mappåtkomst, windows 10, windows defender, utpressningstrojaner, skydda, filer, mappar, anpassa, lägga till mapp, lägga till app, tillåta, lägga till körbar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: jcedola, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.date: 05/10/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: e12368b6241a2c79eead66ed77b30b7864af3955
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326539"
---
# <a name="customize-controlled-folder-access"></a>Anpassa kontrollerad mappåtkomst

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Kontrollerad mappåtkomst hjälper dig att skydda värdefulla data från skadliga program och hot, till exempel utpressningstrojaner. Reglerad mappåtkomst stöds i Windows Server 2019 och Windows 10 klienter. Den här artikeln beskriver hur du anpassar funktioner för kontrollerad mappåtkomst och innehåller följande avsnitt:

- [Skydda ytterligare mappar](#protect-additional-folders)
- [Lägga till appar som ska ha åtkomst till skyddade mappar](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [Tillåt signerade körbara filer att komma åt skyddade mappar](#allow-signed-executable-files-to-access-protected-folders)
- [Anpassa meddelandet](#customize-the-notification)

> [!IMPORTANT]
> Kontrollerad mappåtkomst övervakar appar för aktiviteter som identifieras som skadliga. Ibland blockeras legitima appar från att göra ändringar i dina filer. Om kontrollerad mappåtkomst påverkar organisationens produktivitet kan du överväga att köra den här funktionen i [granskningsläge](audit-windows-defender.md) för att helt bedöma påverkan.

## <a name="protect-additional-folders"></a>Skydda ytterligare mappar

Kontrollerad mappåtkomst gäller många systemmappar och standardplatser, inklusive mappar som **Dokument,** **Bilder** och **Filmer.** Du kan lägga till andra mappar som ska skyddas, men du kan inte ta bort standardmapparna i standardlistan.

Att lägga till andra mappar i kontrollerad mappåtkomst kan vara användbart när du inte lagrar filer i standard-Windows-biblioteken eller om du har ändrat standardplatsen för biblioteken.

Du kan också ange nätverksresurser och mappade enheter. Miljövariabler och jokertecken stöds. Information om hur du använder jokertecken finns i Använda jokertecken i listorna filnamn och [mappsökväg eller undantag för filnamnstillägg.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

Du kan använda Windows-säkerhet, Grupprincip, PowerShell-cmdlets eller tjänstleverantörer för konfigurationstjänster för hantering av mobila enheter för att lägga till och ta bort skyddade mappar.

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a>Använda Windows-säkerhet för att skydda ytterligare mappar

1. Öppna Windows-säkerhet genom att välja sköldikonen i aktivitetsfältet eller genom att söka efter *säkerhet* på Start-menyn.

2. Välj **Virus & skydd mot hot** och rulla sedan ned till avsnittet **Utpressningstrojanskydd.**

3. Välj **Hantera utpressningstrojanskydd** för att öppna **skyddsfönstret för utpressningstrojaner.**

4. Under avsnittet **Kontrollerad mappåtkomst** väljer du **Skyddade mappar**.

5. Välj **Ja** i **kommandotolken för** användaråtkomstkontroll. Fönstret **Skyddade** mappar visas.

6. Välj **Lägg till en skyddad mapp** och följ anvisningarna för att lägga till mappar.

### <a name="use-group-policy-to-protect-additional-folders"></a>Använda grupprinciper för att skydda ytterligare mappar

1. Öppna [Konsolen för grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true) på datorn för grupprinciphantering. 

2. Högerklicka på det grupprincipobjekt du vill konfigurera och välj sedan **Redigera**.

3. Gå till **Administrativa mallar för datorkonfigurationsprinciper** i   >    >  **redigeraren för grupprinciphantering.**

4. Expandera trädet för att **Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **Windows Defender sårbarhetsskyddad**  >  **mappåtkomst**. <br/>**Obs!** I äldre versioner av Windows kanske du ser **Windows Defender Antivirus** i stället **för Microsoft Defender Antivirus**.

5. Dubbelklicka på **Konfigurerade skyddade mappar** och ställ sedan in alternativet Aktiverad .  Välj **Visa** och ange varje mapp som du vill skydda.

6. Distribuera grupprincipobjektet som vanligt.

### <a name="use-powershell-to-protect-additional-folders"></a>Använda PowerShell för att skydda ytterligare mappar

1. Skriv **PowerShell** på Start-menyn, högerklicka på **Windows PowerShell** välj Kör **som administratör**

2. Skriv följande PowerShell-cmdlet och `<the folder to be protected>` ersätt med mappens sökväg (till `"c:\apps\"` exempel):

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. Upprepa steg 2 för varje mapp som du vill skydda. Mappar som är skyddade är synliga i Windows-säkerhet appen.

   :::image type="content" source="images/cfa-allow-folder-ps.png" alt-text="PowerShell-fönster med cmdleten visad":::

> [!IMPORTANT]
> Används `Add-MpPreference` för att lägga till appar i listan och inte `Set-MpPreference` . Med `Set-MpPreference` hjälp av cmdleten skriver du över den befintliga listan.

### <a name="use-mdm-csps-to-protect-additional-folders"></a>Använda MDM-csps för att skydda ytterligare mappar

Använd [konfigurationstjänsten ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) (CSP) för att tillåta appar att göra ändringar i skyddade mappar.

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a>Tillåta specifika appar att göra ändringar i kontrollerade mappar

Du kan ange om vissa appar alltid anses vara säkra och ge skrivbehörighet till filer i skyddade mappar. Tillåta appar kan vara användbart om en viss app som du känner till och litar på blockeras av funktionen kontrollerad mappåtkomst.

> [!IMPORTANT]
> Som standard läggs Windows appar som anses vara användarvänliga i listan över tillåtna appar. Sådana appar som läggs till automatiskt registreras inte i listan som visas i Windows-säkerhet-appen eller med hjälp av de associerade PowerShell-cmdletarna. Du borde inte behöva lägga till de flesta appar. Lägg bara till appar om de blockeras och du kan kontrollera tillförlitligheten.

När du lägger till ett program måste du ange programmets plats. Endast appen på den platsen får åtkomst till de skyddade mapparna. Om programmet (med samma namn) finns på en annan plats läggs det inte till i listan över tillåtna program och kan blockeras av kontrollerad mappåtkomst.

Ett tillåtet program eller en tillåten tjänst har skrivbehörighet till en reglerad mapp när den har startats. En uppdateringstjänst fortsätter till exempel att utlösa händelser när den tillåts tills den stoppas och startas om.

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a>Använd appen Windows Defender säkerhet för att tillåta specifika appar

1. Öppna Windows-säkerhet genom att söka efter Säkerhet på **Start-menyn.**

2. Välj panelen **& virusskydd** (eller sköldikonen på den vänstra menyraden) och välj sedan Hantera utpressningstrojanskydd. 

3. Under avsnittet **Kontrollerad mappåtkomst** väljer du **Tillåt en app via reglerad mappåtkomst**

4. Välj **Lägg till en tillåten app** och följ anvisningarna för att lägga till appar.

   :::image type="content" source="images/cfa-allow-app.png" alt-text="Knappen Lägg till en tillåten app":::

### <a name="use-group-policy-to-allow-specific-apps"></a>Använda grupprinciper för att tillåta specifika appar

1. Öppna grupprinciphanteringskonsolen på [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)din enhet för grupprinciphantering, högerklicka på det grupprincipobjekt du vill konfigurera och välj **Redigera.**

2. I **Redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.

3. Expandera trädet för att **Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **Windows Defender sårbarhetsskyddad**  >  **mappåtkomst**.

4. Dubbelklicka på inställningen **Konfigurera tillåtna** program och ställ in alternativet **Aktiverad**. Välj **Visa** och ange varje app.

### <a name="use-powershell-to-allow-specific-apps"></a>Använda PowerShell för att tillåta specifika appar

1. Skriv **PowerShell** på Start-menyn, högerklicka på **Windows PowerShell** välj Kör **som administratör**
2. Ange följande cmdlet:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    Om du till exempel vill lägga till *test.exe* körbara filer som finns i mappen *C:\apps* ser cmdleten ut så här:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   Fortsätt att använda `Add-MpPreference -ControlledFolderAccessAllowedApplications` för att lägga till fler appar i listan. Appar som läggs till med den här cmdleten visas Windows-säkerhet appen.

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="PowerShell-cmdleten tillåter en app":::

> [!IMPORTANT]
> Används `Add-MpPreference` för att lägga till eller lägga till appar i listan. Med `Set-MpPreference` hjälp av cmdleten skriver du över den befintliga listan.

### <a name="use-mdm-csps-to-allow-specific-apps"></a>Använda MDM CSP för att tillåta specifika appar

Använd [konfigurationstjänsten ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) (CSP) för att tillåta appar att göra ändringar i skyddade mappar.

## <a name="allow-signed-executable-files-to-access-protected-folders"></a>Tillåt signerade körbara filer att komma åt skyddade mappar

Med hjälp av Microsoft Defender för slutpunktscertifikat och filindikatorer kan signerade körbara filer få åtkomst till skyddade mappar. Mer information om implementering finns [i Skapa indikatorer baserade på certifikat.](indicator-certificates.md)

> [!Note]
> Det här gäller inte för skriptmotorer, inklusive Powershell

## <a name="customize-the-notification"></a>Anpassa meddelandet

Mer information om hur du anpassar meddelandet när en regel utlöses och blockerar en app eller fil finns i Konfigurera aviseringsmeddelanden [i Microsoft Defender för slutpunkt.](configure-email-notifications.md)

## <a name="see-also"></a>Se även

- [Skydda viktiga mappar med kontrollerad mappåtkomst](controlled-folders.md)
- [Aktivera kontrollerad mappåtkomst](enable-controlled-folders.md)
- [Utvärdera regler för minskning av attackytan](evaluate-attack-surface-reduction.md)
