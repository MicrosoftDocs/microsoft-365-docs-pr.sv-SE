---
title: Ytterligare enhets information för migreringen från Microsoft Cloud Deutschland
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
description: 'Sammanfattning: ytterligare enhets information på tjänster när du flyttar från Microsoft Cloud Tyskland (Microsoft Cloud Deutschland) till Office 365-tjänster i det nya tyska data centret.'
ms.openlocfilehash: 1bbb4bf39db61a93844c21cd6062a70699b5d6d7
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688661"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Ytterligare enhets information för migreringen från Microsoft Cloud Deutschland

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

**Hur vet jag om min organisation påverkas?**

Administratörer bör kontrol lera `https://portal.microsoftazure.de` om de har registrerade enheter. Om din organisation har registrerade enheter påverkas det.

**Vad händer med mina användare?**

Användare från en registrerad enhet kommer inte längre att kunna logga in efter migreringen och [Slutför Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration-fasen.  

Kontrol lera att alla dina enheter är registrerade med den globala slut punkten innan organisationen kopplas bort från Microsoft Cloud Deutschland.
  
**När registrerar mina användare en ny omregistrera deras enheter?**

Det är viktigt för din framgång att du bara avregistrerar och registrerar om dina enheter under den separata migrations fasen [för Microsoft Cloud-Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) .

**Hur återställer jag enhetens tillstånd efter migrering?**

För Hybrid Azure AD-anslutna och företagsägda Windows-enheter som är registrerade med Azure AD kan administratörer hantera migreringen av dessa enheter via fjärrutlös ande arbets flöden som avregistrerar de gamla enhets tillstånden.
  
För alla andra enheter, inklusive personliga Windows-enheter som är registrerade i Azure AD, måste slutanvändaren utföra dessa steg manuellt. För Azure AD-anslutna enheter måste användare ha ett lokalt administratörs konto för att avregistrera och sedan registrera om sina enheter.

Microsoft publicerar instruktioner för hur du återställer enhetens status. 
 
**Hur vet jag att alla mina enheter är registrerade i det offentliga molnet?**

Om du vill kontrol lera att dina enheter är registrerade i det offentliga molnet bör du exportera och ladda ned listan över enheter från Azure AD-portalen till ett Excel-kalkylblad. Filtrera sedan de enheter som är registrerade (med hjälp av kolumnen _registeredTime_ ) efter den [avgränsade flytt fasen från Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) .

Enhets registrering är inaktiverat efter migrering av klient organisationen och kan inte aktive ras eller inaktive ras. Om Intune inte används loggar du in på ditt abonnemang och kör det här kommandot för att återaktivera alternativet:

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a>Windows hybrid Azure AD-anslutning

### <a name="windows-down-level"></a>Windows i nivå

_Windows-_ enheter som använder tidigare versioner av Windows (till exempel Windows 8,1 eller Windows 7), eller som kör Windows Server-versioner tidigare än 2019 och 2016, är Windows-produkter. Om sådana enheter registrerades förut måste du avregistrera och registrera om dessa enheter. 

Använd följande kommando på enheten för att avgöra om en Windows-enhet med en låg nivå tidigare varit ansluten till Azure AD:

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

Om enheten tidigare varit ansluten till Azure AD och om enheten har nätverks anslutning till globala Azure AD-slutpunkter ser du följande utdata:

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

Berörda enheter har "enhets status" och värdet "okänt". Om resultatet är "enheten är inte ansluten" eller om "enhetens status"-värde är "OK", ignorerar du följande vägledning.

Endast för enheter som visar att enheten är kopplad (via deviceId, tumavtryck och så vidare) och vars "enhets status"-värde är "okänt", ska administratörer köra följande kommando i kontexten för en domän användare som loggar in på en sådan enhet.

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

Det föregående kommandot behöver bara köras en gång per domän användare som loggar in på den Windows-baserade enheten. Det här kommandot bör köras i kontexten för domän användar inloggningen. 

Tillräckligt med försiktighet måste vidtas för att inte köra det här kommandot när användaren loggar in. När föregående kommando körs raderas det kopplade läget för den lokala hybrid Azure AD-anslutna datorn för den användare som loggat in. Och om datorn fortfarande är konfigurerad för att bli hybrid Azure AD-ansluten till klient organisationen försöker den ansluta när användaren loggar in igen.

### <a name="windows-current"></a>Windows-aktuell

#### <a name="unjoin"></a>Koppla från

Om du vill ta reda på om Windows 10-enheten tidigare varit ansluten till Azure AD kör du följande kommando på enheten:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Om enheten är hybrid Azure AD-ansluten ser administratören följande utdata:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

Om utdata är "AzureAdJoined: No", ignorerar du följande vägledning.

För enheter som visar att enheten är ansluten till Azure AD kör du följande kommando som administratör för att ta bort enhetens anslutna status.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

Föregående kommando måste bara köras en gång i en administrativ kontext på Windows-enheten.

#### <a name="hybrid-ad-joinre-registration"></a>Hybrid annons Join\Re-Registration

Enheten ansluts automatiskt till Azure AD utan användar-eller administratörs åtgärd så länge enheten har nätverks anslutning till globala Azure AD-slutpunkter. 


## <a name="windows-azure-ad-join"></a>Windows Azure AD-anslutning

**Viktigt:** Intune-tjänstens huvud konto aktive ras efter handelsmigrering, vilket innebär aktivering av Azure AD-registrering. Om du blockerade registrering av Azure AD-enheter före migrering måste du inaktivera Intune-tjänstens huvud konto med PowerShell för att inaktivera registrering av Azure AD-enheter med Azure AD-portalen igen. Du kan inaktivera Intune-huvudobjektet med det här kommandot i Azure Active Directory PowerShell för Graph.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a>Koppla från

För att avgöra om en Windows 10-enhet tidigare varit ansluten till Azure AD kan användaren eller administratören köra följande kommando på enheten:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Om enheten är ansluten till Azure AD ser användaren eller administratören följande resultat:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

Om utdata är "AzureAdJoined: NO", ignorerar du följande vägledning.

Användare: om enheten är en Azure AD ansluten kan en användare koppla från enheten från inställningarna. Kontrol lera att det finns ett lokalt administratörs konto på enheten innan du kopplar från enheten från Azure AD. Det lokala administratörs kontot krävs för att logga in på enheten igen.

Administratör: om organisationens administratör vill koppla från användarnas enheter som är Azure AD-anslutna kan de göra det genom att köra följande kommando på varje enhet med hjälp av en mekanism som grup princip. Administratören måste kontrol lera att det finns ett lokalt administratörs konto på enheten innan du kopplar från enheten från Azure AD. Det lokala administratörs kontot behövs för att logga in på enheten igen.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

Föregående kommando måste bara köras en gång i en administrativ kontext på Windows-enheten. 

### <a name="azure-ad-joinre-registration"></a>Azure AD Join/re-registrering

Användaren kan ansluta till enheten till Azure AD från Windows-inställningar: **inställningar > konton > åtkomst till arbets-eller skol > Anslut**.
 

## <a name="windows-azure-ad-registered-company-owned"></a>Windows Azure AD registrerad (företag)

Om du vill ta reda på om Windows 10-enheten är Azure AD-registrerad kör du följande kommando på enheten:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Om enheten är Azure AD registrerad visas följande:

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

Så här tar du bort det befintliga Azure AD-registrerade kontot på enheten:

- Om du vill ta bort Azure AD-det registrerade kontot på enheten använder du CleanupWPJ, ett verktyg som du kan ladda ned härifrån: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).

- Extrahera ZIP-filen och kör **WPJCleanup. cmd**. Det här verktyget startar den rätta körbara filen baserat på Windows-versionen på enheten.

- Genom att använda en funktion som grup princip kan administratören köra kommandot på enheten i kontexten för en användare som är inloggad på enheten.

Om du vill inaktivera Web Account Manager-prompten för att registrera enheten i Azure AD, lägger du till det här registervärdet: 

- Plats: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- Typ: DWORD (32 bitar)
- Namn: BlockAADWorkplaceJoin
- Värde data: 1

Närvaron av det här registervärdet bör blockera arbets plats anslutning och förhindra användare från att se uppmaningar att gå med i enheten.

## <a name="android"></a>Android

För Android måste användarna avregistrera och registrera om sina enheter. Det här kan du göra via programmet Microsoft Authenticator eller företagsportalsappen. 

- Från Microsoft Authenticator-appen kan användarna gå till **inställningar > enhets registrering**. Därifrån kan användarna avregistrera och registrera om sina enheter.
 
- Från företags portalen kan användare gå till fliken **enheter** och ta bort enheten. Därefter omregistrerar du enheten på nytt med hjälp av företags portalen.
 
- Användare kan också avregistrera och registrera om genom att ta bort kontot från sidan konto inställningar och sedan lägga till arbets kontot igen.

För att avregistrera och registrera enheten på Android med hjälp av Microsoft Authenticator-appen:

1.  Öppna Microsoft Authenticator-appen och gå till **Inställningar**.
2.  Välj **enhets registrering**.
3.  Avregistrera enheten genom att välja **avregistrering**.
4.  Registrera **enheten igen** genom att skriva in din e-postadress och välj sedan **Registrera**.

Så här avregistrerar och registrerar du en Android-enhet på nytt på Android-sidan:

1.  Öppna **enhets inställningar** och gå till **konton**.
2.  Välj det arbets konto som du vill registrera om och välj **ta bort konto**.
3.  När kontot har tagits bort väljer du **Lägg till konto > arbets konto** på sidan **konton** .
4.  För **arbets plats anslutning** skriver du din e-postadress och väljer **Anslut** för att slutföra registreringen av enheten.

För att avregistrera och registrera enheten på Android från företags portalen:

1.  Starta företags Portal och gå till fliken **enheter** .
2.  Välj enhet för att Visa enhets informationen.
3.  På menyn punkter (tre punkter) väljer du **ta bort enhet** och slutför borttagningen genom att bekräfta i dialog rutan.
4.  Du ska nu vara utloggad från företagsportalsappen. Välj **Logga in** för att registrera enheten på nytt.

Om du vill ha mer information om åtgärder som krävs under migrations fasen av denna arbets belastning, eller om det påverkar administrationen eller användningen, läser du informationen om Azure Active Directory (Azure AD) i [ytterligare Azure AD-information för migreringen från Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).

## <a name="ios"></a>iOS

På iOS-enheter måste en användare manuellt ta bort alla cachelagrade konton från Microsoft Authenticator, avregistrera enheten och logga ut från alla egna appar på enheten.

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>Steg 1: ta bort kontot från programmet Microsoft Authenticator

1. Tryck på kontot i Microsoft Authenticator-appen.
2. Tryck på ikonen **Inställningar** i det övre högra hörnet. Om du inte ser ikonen **Inställningar** kanske du inte använder den senaste versionen av Microsoft Authenticator.
3. Tryck på knappen **ta bort konto** .
4. Tryck **på alla appar på den här enheten**.
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>Steg 2: avregistrera enheten från Microsoft Authenticator-appen

1. Tryck på Meny ikonen i det övre högra hörnet.
2. Tryck på **Inställningar** och sedan på **enhets registrering**.
4. Om ditt konto visas trycker du på **avregistrera enheten** och **fortsätter** i dialog rutan. Inget konto visas.
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>Steg 3: Logga ut från enskilda appar om det behövs

Användare kan gå till enskilda appar som Outlook, team och OneDrive och ta bort konton från dessa program.

## <a name="more-information"></a>Mer information

Komma igång:

- [Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i de nya tyska Data Center-regionerna](ms-cloud-germany-transition.md)
- [Hjälp för Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Så här väljer du för migrering](ms-cloud-germany-migration-opt-in.md)
- [Kund upplevelse under migreringen](ms-cloud-germany-transition-experience.md)

Flytta genom över gången:

- [Åtgärder och påverkan i migreringsfaser](ms-cloud-germany-transition-phases.md)
- [Övrig för hands arbete](ms-cloud-germany-transition-add-pre-work.md)
- Ytterligare information för [Azure AD](ms-cloud-germany-transition-azure-ad.md), [enheter](ms-cloud-germany-transition-add-devices.md), [upplevelser](ms-cloud-germany-transition-add-experience.md)och [AD FS](ms-cloud-germany-transition-add-adfs.md).

Molnappar:

- [Information om programmet för Dynamics 365 migration](https://aka.ms/d365ceoptin)
- [Information om datamigreringshanteraren för Power BI](https://aka.ms/pbioptin)
- [Komma igång med din uppgradering av Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
