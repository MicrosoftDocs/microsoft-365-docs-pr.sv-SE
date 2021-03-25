---
title: Anpassa reglerad mappåtkomst
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
ms.date: 03/24/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 0962913df63e6837664cdb8ff79710d66e66977c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199927"
---
# <a name="customize-controlled-folder-access"></a>Anpassa reglerad mappåtkomst

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)


Kontrollerad mappåtkomst hjälper dig att skydda värdefulla data från skadliga program och hot, till exempel utpressningstrojaner. Reglerad mappåtkomst stöds i Windows Server 2019- och Windows 10-klienter.

Den här artikeln beskriver hur du anpassar funktioner för kontrollerad mappåtkomst och innehåller följande avsnitt:

- [Skydda ytterligare mappar](#protect-additional-folders)
- [Lägga till appar som ska ha åtkomst till skyddade mappar](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [Tillåt signerade körbara filer att komma åt skyddade mappar](#allow-signed-executable-files-to-access-protected-folders)
- [Anpassa meddelandet](#customize-the-notification)

> [!IMPORTANT]
> Kontrollerad mappåtkomst övervakar appar för aktiviteter som identifieras som skadliga. Ibland blockeras legitima appar från att göra ändringar i dina filer. Om kontrollerad mappåtkomst påverkar organisationens produktivitet kan du överväga att köra den här funktionen i [granskningsläge](audit-windows-defender.md) för att helt bedöma påverkan.

## <a name="protect-additional-folders"></a>Skydda ytterligare mappar

Kontrollerad mappåtkomst gäller många systemmappar och standardplatser, inklusive mappar som **Dokument,** **Bilder** och **Filmer.** Du kan lägga till fler mappar som ska skyddas, men du kan inte ta bort standardmapparna i standardlistan.

Att lägga till andra mappar i kontrollerad mappåtkomst kan vara praktiskt när du inte lagrar filer i standardbiblioteken i Windows eller om du har ändrat standardplatsen för biblioteken.

Du kan också ange nätverksresurser och mappade enheter. Miljövariabler och jokertecken stöds. Information om hur du använder jokertecken finns i Använda jokertecken i listorna filnamn och [mappsökväg eller undantag för filnamnstillägg.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)

Du kan använda Windows-säkerhetsappen, grupprincipen, PowerShell-cmdlets eller tjänstleverantörer för konfiguration av mobil enhetshantering till att lägga till och ta bort ytterligare skyddade mappar.

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a>Använda Windows-säkerhetsappen för att skydda ytterligare mappar

1. Öppna appen Windows-säkerhet genom att välja sköldikonen i aktivitetsfältet eller söka efter Säkerhet på **Start-menyn.**

2. Välj **Virus & skydd mot hot** och rulla sedan ned till avsnittet **Utpressningstrojanskydd.**

3. Välj **Hantera utpressningstrojanskydd** för att öppna **skyddsfönstret för utpressningstrojaner.**

4. Under avsnittet **Kontrollerad mappåtkomst** väljer du **Skyddade mappar**.

5. Välj **Ja** i **kommandotolken för** användaråtkomstkontroll. Fönstret **Skyddade** mappar visas.

4. Välj **Lägg till en skyddad mapp** och följ anvisningarna för att lägga till mappar.

### <a name="use-group-policy-to-protect-additional-folders"></a>Använda grupprinciper för att skydda ytterligare mappar

1. Öppna grupprinciphanteringskonsolen på [](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)datorn för grupprinciphantering, högerklicka på det grupprincipobjekt som du vill konfigurera och välj sedan **Redigera.**

2. I **redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.

3. Expandera trädet till **Windows-komponenter**  >  **Microsoft Defender Antivirus** Windows Defender  >  **Sårbarhetsskyddad**  >  **mappåtkomst**.

4. Dubbelklicka på **Konfigurerade skyddade mappar och** ställ in alternativet Aktiverad .  Välj **Visa** och ange varje mapp.

### <a name="use-powershell-to-protect-additional-folders"></a>Använda PowerShell för att skydda ytterligare mappar

1. Skriv **PowerShell** på Start-menyn, högerklicka på **Windows PowerShell och** välj Kör som **administratör**

2. Ange följande cmdlet:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. Upprepa steg 2 tills du har lagt till alla mappar som du vill skydda. Mappar som läggs till visas i appen Windows-säkerhet.

   ![Skärmbild av ett PowerShell-fönster med cmdleten ovan angivet](/microsoft-365/security/defender-endpoint/images/cfa-allow-folder-ps)

> [!IMPORTANT]
> Används `Add-MpPreference` för att lägga till eller lägga till appar i listan. Med `Set-MpPreference` hjälp av cmdleten skriver du över den befintliga listan.

### <a name="use-mdm-csps-to-protect-additional-folders"></a>Använda MDM-csps för att skydda ytterligare mappar

Använd [konfigurationstjänsten ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) (CSP) för att tillåta appar att göra ändringar i skyddade mappar.

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a>Tillåta specifika appar att göra ändringar i kontrollerade mappar

Du kan ange om vissa appar alltid anses vara säkra och ge skrivbehörighet till filer i skyddade mappar. Tillåta appar kan vara användbart om en viss app som du känner till och litar på blockeras av funktionen kontrollerad mappåtkomst.

> [!IMPORTANT]
> Som standard lägger Windows till appar som anses vara användarvänliga i listan över tillåtna appar. Sådana appar som läggs till automatiskt registreras inte i listan som visas i Windows-säkerhetsappen eller med hjälp av de associerade PowerShell-cmdletarna. Du borde inte behöva lägga till de flesta appar. Lägg bara till appar om de blockeras och du kan kontrollera tillförlitligheten.

När du lägger till ett program måste du ange programmets plats. Endast appen på den platsen får åtkomst till de skyddade mapparna. Om programmet (med samma namn) finns på en annan plats läggs det inte till i listan över tillåtna och kan blockeras av kontrollerad mappåtkomst.

Ett tillåtet program eller en tillåten tjänst har skrivbehörighet till en reglerad mapp när den har startats. En uppdateringstjänst fortsätter till exempel att utlösa händelser när den tillåts tills den stoppas och startas om.

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a>Använda appen Windows Defender Säkerhet för att tillåta specifika appar

1. Öppna appen Windows-säkerhet genom att söka efter Säkerhet på **Start-menyn.**

2. Välj panelen **& virusskydd** (eller sköldikonen på den vänstra menyraden) och välj sedan Hantera utpressningstrojanskydd. 

3. Under avsnittet **Kontrollerad mappåtkomst** väljer du **Tillåt en app via reglerad mappåtkomst**

4. Välj **Lägg till en tillåten app** och följ anvisningarna för att lägga till appar.

   :::image type="content" source="images/cfa-allow-app.png" alt-text="Knappen Lägg till en tillåten app":::

### <a name="use-group-policy-to-allow-specific-apps"></a>Använda grupprinciper för att tillåta specifika appar

1. Öppna grupprinciphanteringskonsolen på [](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)din enhet för grupprinciphantering, högerklicka på det grupprincipobjekt du vill konfigurera och välj **Redigera.**

2. I **redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.

3. Expandera trädet till **Windows-komponenter**  >  **Microsoft Defender Antivirus** Windows Defender  >  **Sårbarhetsskyddad**  >  **mappåtkomst**.

4. Dubbelklicka på inställningen **Konfigurera tillåtna** program och ställ in alternativet **Aktiverad**. Välj **Visa** och ange varje app.

### <a name="use-powershell-to-allow-specific-apps"></a>Använda PowerShell för att tillåta specifika appar

1. Skriv **PowerShell** på Start-menyn, högerklicka på **Windows PowerShell och** välj Kör som **administratör**
2. Ange följande cmdlet:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    Om du till exempel vill lägga till *test.exe* körbara filer som finns i mappen *C:\apps* ser cmdleten ut så här:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   Fortsätt att använda `Add-MpPreference -ControlledFolderAccessAllowedApplications` för att lägga till fler appar i listan. Appar som läggs till med den här cmdleten visas i Windows-säkerhetsappen.

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="PowerShell-cmdleten tillåter en app":::

> [!IMPORTANT]
> Används `Add-MpPreference` för att lägga till eller lägga till appar i listan. Med `Set-MpPreference` hjälp av cmdleten skriver du över den befintliga listan.

### <a name="use-mdm-csps-to-allow-specific-apps"></a>Använda MDM CSP för att tillåta specifika appar

Använd [konfigurationstjänsten ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) (CSP) för att tillåta appar att göra ändringar i skyddade mappar.

## <a name="allow-signed-executable-files-to-access-protected-folders"></a>Tillåt signerade körbara filer att komma åt skyddade mappar

Med hjälp av Microsoft Defender för slutpunktscertifikat och filindikatorer kan signerade körbara filer få åtkomst till skyddade mappar. Mer information om implementering finns [i Skapa indikatorer baserade på certifikat.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates)

> [!Note]
> Det här gäller inte för skriptmotorer, inklusive Powershell

## <a name="customize-the-notification"></a>Anpassa meddelandet

Mer information om hur du anpassar meddelandet när en regel utlöses och blockerar en app eller fil finns i Konfigurera aviseringsmeddelanden [i Microsoft Defender för slutpunkt.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications)

## <a name="see-also"></a>Se även

- [Skydda viktiga mappar med kontrollerad mappåtkomst](controlled-folders.md)
- [Aktivera reglerad mappåtkomst](enable-controlled-folders.md)
- [Utvärdera minskningsregler för attackytor](evaluate-attack-surface-reduction.md)
