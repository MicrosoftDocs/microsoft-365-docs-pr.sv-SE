---
title: Ytterligare enhetsinformation för migreringen från Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Sammanfattning: Ytterligare enhetsinformation om tjänster när du flyttar från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365-tjänster i den nya tyska datacenterområdet.'
ms.openlocfilehash: 21188372f03af394fe1c0e227c1adeabbad02a85
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928162"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Ytterligare enhetsinformation för migreringen från Microsoft Cloud Deutschland

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

**Hur vet jag om min organisation påverkas?**

Administratörer bör kontrollera `https://portal.microsoftazure.de` om de har några registrerade enheter. Om din organisation har registrerade enheter påverkas du.

**Hur påverkar det mina användare?**

Användare från en registrerad enhet kommer inte längre att kunna [](ms-cloud-germany-transition.md#how-is-the-migration-organized) logga in när migreringen har fasat in Azure AD-migreringen.  

Se till att alla dina enheter är registrerade med den globala slutpunkten innan din organisation kopplas bort från Microsoft Cloud Deutschland.
  
**När registrerar mina användare sina enheter igen?**

Det är viktigt att du endast avregistrerar och registrerar dina enheter igen under migreringsfasen Separat från [Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

**Hur återställer jag enhetens status efter migreringen?**

För hybrid-Azure AD-anslutna och företagsägda Windows-enheter som är registrerade med Azure AD kan administratörer hantera migreringen av dessa enheter genom fjärrutlösta arbetsflöden som avregistrerar de gamla enhets tillstånden.
  
För alla andra enheter, inklusive personliga Windows-enheter som är registrerade i Azure AD, måste slutanvändaren utföra de här stegen manuellt. För Azure AD-anslutna enheter måste användarna ha ett lokalt administratörskonto för att avregistrera och sedan registrera sina enheter på nytt.

Microsoft publicerar instruktioner för hur man återställer enhetens status. 
 
**Hur vet jag att alla mina enheter är registrerade i det offentliga molnet?**

Om du vill kontrollera om dina enheter är registrerade i det offentliga molnet bör du exportera och ladda ned listan med enheter från Azure AD-portalen till ett Excel-kalkylblad. Filtrera sedan de enheter som är registrerade (med hjälp av kolumnen _registeredTime)_ efter migreringsfasen Separat från [Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

Enhetsregistrering inaktiveras efter migrering av klientorganisationen och kan inte aktiveras eller inaktiveras. Om Intune inte används loggar du in på din prenumeration och kör det här kommandot för att aktivera alternativet igen:

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="hybrid-azure-ad-join"></a>Hybrid Azure AD-anslutning

### <a name="windows-down-level"></a>Windows-nednivå

_Windows-enheter_ på nedåtnivå är Windows-enheter som för närvarande kör tidigare versioner av Windows (till exempel Windows 8.1 eller Windows 7) eller som kör Windows Server-versioner tidigare än 2019 och 2016. Om sådana enheter har registrerats tidigare måste du avregistrera och registrera om enheterna. 

Använd följande kommando på enheten för att avgöra om en Windows-enhet på lägre nivå tidigare var ansluten till Azure AD:

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

Om enheten tidigare var ansluten till Azure AD, och enheten har nätverksanslutning till globala Azure AD-slutpunkter, ser du följande utdata:

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

De enheter som påverkas har "Enhetens status" med värdet "Okänt". Om utdata är "Enheten är inte ansluten" eller om "Enhetens status" är "Ok", ignorera följande vägledning.

Endast för enheter som visar att enheten är ansluten (på grund av enhetensId, thumbprint och så vidare) och vars "Enhetstillstånd"-värde är "Okänt", bör administratörer köra följande kommando i samband med att en domänanvändare loggar in på en sådan enhet på nedåtnivå:

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

Föregående kommando behöver bara köras en gång per domänanvändare som loggar in på Windows-nednivåenheten. Det här kommandot ska köras inom ramen för domänanvändaren som loggar in. 

Tillräcklig försiktighet måste vidtas för att inte köra det här kommandot när användaren sedan loggar in. När föregående kommando körs rensas den sammanskrivna statusen för den lokala Azure AD-sammanskrivna hybriddatorn för den användare som loggade in. Och om datorn fortfarande är konfigurerad att vara hybrid-Azure AD-ansluten i klientorganisationen försöker den ansluta när användaren loggar in igen.

### <a name="windows-current"></a>Windows Current

#### <a name="unjoin"></a>Ta bort anslutning

För att ta reda på om Windows 10-enheten tidigare var ansluten till Azure AD kör du följande kommando på enheten:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Om enheten är Azure AD-ansluten till hybrid ser administratören följande utdata:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

Om utdata är "AzureAdJoined : Nej" ignorerar du följande vägledning.

För enheter som visar att enheten är ansluten till Azure AD kör du följande kommando som administratör för att ta bort enhetens anslutna tillstånd.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

Föregående kommando behöver bara köras en gång i ett administrativt sammanhang på Windows-enheten.

#### <a name="hybrid-ad-joinre-registration"></a>Hybrid AD Join\Re-Registration

Enheten ansluts automatiskt till Azure AD utan åtgärd från användare eller administratör så länge enheten är ansluten till globala Azure AD-slutpunkter. 


## <a name="azure-ad-join"></a>Azure AD-anslutning

**VIKTIGT!** Intune-tjänstens huvudnamn aktiveras efter e-handelsmigrering, vilket innebär aktivering av enhetsregistrering för Azure AD. Om du blockerade enhetsregistrering för Azure AD före migreringen måste du inaktivera Intune-tjänstens huvudnamn med PowerShell om du vill inaktivera enhetsregistrering för Azure AD med Azure AD-portalen igen. Du kan inaktivera Intune-tjänstens huvudnamn med det här kommandot i Azure Active Directory PowerShell för Graph-modulen.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a>Ta bort anslutning

För att avgöra om Windows 10-enheten tidigare var ansluten till Azure AD kan användaren eller administratören köra följande kommando på enheten:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Om enheten är ansluten till Azure AD ser användaren eller administratören följande utdata:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

Om utdata är "AzureAdJoined : NO" ignorerar du följande vägledning.

Användare: Om enheten är Azure AD ansluten kan en användare ta bort enheten från inställningarna. Kontrollera att det finns ett lokalt administratörskonto på enheten innan du tar bort enheten från Azure AD. Det lokala administratörskontot krävs för att logga in på enheten igen.

Administratör: Om organisationens administratör vill ta bort användarnas enheter som är Azure AD-anslutna kan de göra det genom att köra följande kommando på var och en av enheterna med hjälp av en mekanism, till exempel grupprincip. Administratören måste kontrollera att det finns ett lokalt administratörskonto på enheten innan enheten tas bort från Azure AD. Det lokala administratörskontot krävs för att logga in på enheten igen.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

Föregående kommando behöver bara köras en gång i ett administrativt sammanhang på Windows-enheten. 

### <a name="azure-ad-joinre-registration"></a>Azure AD- anslutning/omregistrering

Användaren kan ansluta enheten till Azure AD från Windows-inställningar: Inställningar för **>-> Arbets- eller skolkonto > Connect.**
 

## <a name="azure-ad-registered-company-owned"></a>Azure AD Registered (företagsägd)

Om du vill avgöra om Windows 10-enheten är Azure AD-registrerad kör du följande kommando på enheten:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Om enheten är Azure AD Registrerad ser du följande utdata:

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

Så här tar du bort det befintliga Azure AD-registrerade kontot på enheten:

- Om du vill ta bort det Azure AD-registrerade kontot på enheten använder du CleanupWPJ, ett verktyg som du kan ladda ned härifrån: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).

- Extrahera ZIP-filen och kör **WPJCleanup.cmd**. Det här verktyget startar rätt körbar baserat på versionen av Windows på enheten.

- Genom att använda en mekanism som grupprincip kan administratören köra kommandot på enheten i samband med alla användare som är inloggade på enheten.

Om du vill inaktivera Web Account Manager-uppmaningar om att registrera enheten i Azure AD lägger du till det här registervärdet: 

- Plats: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- Typ: DWORD (32 bitar)
- Namn: BlockAADWorkplaceJoin
- Värdedata: 1

Förekomsten av det här registervärdet bör blockera anslutning till arbetsplatsen och förhindra att användarna ser uppmaningar om att ansluta till enheten.

## <a name="android"></a>Android

För Android måste användarna avregistrera sig och registrera sina enheter igen. Det kan du göra via appen Microsoft Authenticator eller företagsportalen. 

- Från Microsoft Authenticator-appen kan användare gå till **Inställningar > Enhetsregistrering.** Därifrån kan användare avregistrera sig och registrera sin enhet igen.
 
- Från företagsportalen kan användarna gå till **fliken Enheter** och ta bort enheten. Därefter kan du registrera enheten igen via företagsportalen.
 
- Användare kan också avregistrera och registrera igen genom att ta bort kontot från sidan kontoinställningar och sedan lägga till arbetskontot igen.

Så här avregistrerar du och registrerar om enheten på Android med hjälp av appen Microsoft Authenticator:

1.  Öppna Appen Microsoft Authenticator och gå till **Inställningar**.
2.  Välj **Enhetsregistrering**.
3.  Avregistrera enheten genom att välja **Avregistrera**.
4.  För **enhetsregistrering** registrerar du enheten igen genom att skriva din e-postadress och väljer **registrera**.

Så här avregistrerar du och registrerar om en Android-enhet på sidan För Android-inställningar:

1.  Öppna **Enhetsinställningar** och gå till **Konton**.
2.  Välj det arbetskonto du vill registrera igen och välj Ta **bort konto**.
3.  När kontot har tagits bort går du till **sidan Konton** och väljer Lägg till konto **> Arbetskonto**.
4.  I **Workplace Join** skriver du din e-postadress och väljer **Anslut** för att slutföra registreringen av enheten.

Så här avregistrerar du och registrerar om enheten på Android från företagsportalen:

1.  Starta företagsportalen och gå till **fliken** Enheter.
2.  Välj enheten om du vill se enhetsinformationen.
3.  På ellipsmenyn (tre punkter) väljer du Ta **bort** enhet och slutför borttagningen genom att bekräfta i dialogrutan.
4.  Du bör nu vara utloggad från företagsportalappen. Välj **Logga in** för att registrera enheten igen.

Mer information om åtgärder som krävs under migreringsfasen av den här arbetsbelastningen, eller påverkan på administration eller användning, finns i informationen om Azure Active Directory (Azure AD) i Ytterligare Azure AD-information för migreringen från [Microsoft Cloud Deutschland.](ms-cloud-germany-transition-azure-ad.md)

## <a name="ios"></a>iOS

På iOS-enheter måste en användare manuellt ta bort cachelagrade konton från Microsoft Authenticator, avregistrera enheten och logga ut från alla inbyggda appar på enheten.

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>Steg 1: Om det finns tar du bort kontot från Microsoft Authenticator-appen

1. Tryck på kontot i appen Microsoft Authenticator.
2. Tryck på **ikonen** Inställningar i det övre högra hörnet. Om du inte ser ikonen **Förinställningar** använder du kanske inte den senaste versionen av Microsoft Authenticator.
3. Tryck på **knappen Ta bort** konto.
4. Tryck **på Alla appar på den här enheten**.
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>Steg 2: Avregistrera enheten från Microsoft Authenticator-appen

1. Tryck på menyikonen i det övre högra hörnet.
2. Tryck **på Inställningar** och sedan på **Enhetsregistrering.**
4. Om ditt konto visas trycker du på **Avregistrera enhet** **och Fortsätt** i dialogrutan. Därefter bör du inte se något konto.
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>Steg 3: Logga ut från enskilda appar om det behövs

Användare kan gå till enskilda appar som Outlook, Teams och OneDrive och ta bort konton från dessa appar.

## <a name="more-information"></a>Mer information

Komma igång:

- [Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i nya tyska datacenterområden](ms-cloud-germany-transition.md)
- [Migreringshjälp för Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Så här väljer du in för migrering](ms-cloud-germany-migration-opt-in.md)
- [Kundupplevelse under migreringen](ms-cloud-germany-transition-experience.md)

Flytta genom övergången:

- [Åtgärder och påverkan i migreringsfaser](ms-cloud-germany-transition-phases.md)
- [Ytterligare arbete](ms-cloud-germany-transition-add-pre-work.md)
- Ytterligare information för [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [enheter,](ms-cloud-germany-transition-add-devices.md) [upplevelser](ms-cloud-germany-transition-add-experience.md)och [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Molnappar:

- [Information om Dynamics 365-migreringsprogram](/dynamics365/get-started/migrate-data-german-region)
- [Information om Migreringsprogram för Power BI](/power-bi/admin/service-admin-migrate-data-germany)
- [Komma igång med uppgraderingen till Microsoft Teams](/microsoftteams/upgrade-start-here)