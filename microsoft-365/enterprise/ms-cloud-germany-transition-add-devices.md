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
description: 'Sammanfattning: Ytterligare enhetsinformation om tjänster när du flyttar från Microsoft Cloud Germany (Microsoft Cloud Deutschland) till Office 365 tjänster i den nya tyska datacenterområdet.'
ms.openlocfilehash: 27426a26befab85bf62a0a143861e447dd722724
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861312"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Ytterligare enhetsinformation för migreringen från Microsoft Cloud Deutschland

Azure AD-anslutna och registrerade enheter som är anslutna till Microsoft Cloud Deutschland måste migreras efter fas 9 och före fas 10. Migreringen av en enhet beror på typen av enheter, operativsystemet och AAD-relationen. 

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

**Hur vet jag om min organisation påverkas?**

Administratörer bör kontrollera `https://portal.microsoftazure.de` om de har några registrerade eller Azure AD-anslutna enheter. Om din organisation har registrerade enheter påverkas du.

**Hur påverkar det mina användare?**

Användare från en registrerad enhet kan inte längre logga in när migreringsfasen [10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) har slutförts och slutpunkterna för Microsoft Cloud Deutschland har inaktiverats.  

Se till att alla dina enheter är registrerade med den globala slutpunkten innan din organisation kopplas bort från Microsoft Cloud Deutschland.
  
**När registrerar mina användare sina enheter igen?**

Det är viktigt att du bara avregistrerar och registrerar dina enheter igen när [fas 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) är klar. Du måste slutföra omregistreringen innan fas 10 startar, annars kan åtkomsten till din enhet gå förlorade.

**Hur återställer jag enhetens status efter migreringen?**

För företagsägda Windows enheter som är registrerade med Azure AD kan administratörer hantera migreringen av dessa enheter via fjärrutlösta arbetsflöden som avregistrerar de gamla enhets tillstånden.
  
För alla andra enheter, inklusive personliga Windows enheter som är registrerade i Azure AD, måste slutanvändaren utföra dessa steg manuellt. För Azure AD-anslutna enheter måste användarna ha ett lokalt administratörskonto för att avregistrera och sedan registrera sina enheter på nytt.

Se detaljerade anvisningar om hur du återställer enhetens tillstånd nedan. 
 
**Hur vet jag att alla mina enheter är registrerade i det offentliga molnet?**

Om du vill kontrollera om dina enheter är registrerade i det offentliga molnet bör du exportera och ladda ned listan med enheter från Azure AD-portalen till ett Excel kalkylblad. Filtrera sedan de enheter som är registrerade (med hjälp av kolumnen _registeredTime)_ efter migreringsfasen Separat från [Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

## <a name="additional-considerations"></a>Ytterligare överväganden
Enhetsregistrering inaktiveras efter migrering av klientorganisationen och kan inte aktiveras eller inaktiveras. 

Om Intune inte används loggar du in på din prenumeration och kör det här kommandot för att aktivera alternativet igen:

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```
**VIKTIGT!** Intune-tjänstens huvudnamn aktiveras efter e-handelsmigrering, vilket innebär aktivering av enhetsregistrering för Azure AD. Om du blockerade enhetsregistrering för Azure AD före migreringen måste du inaktivera Intune-tjänstens huvudnamn med PowerShell om du vill inaktivera enhetsregistrering för Azure AD med Azure AD-portalen igen. Du kan inaktivera Intune-tjänstens huvudnamn med det här kommandot Azure Active Directory PowerShell för Graph modul.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```


## <a name="azure-ad-join"></a>Azure AD-anslutning
Det här gäller Windows 10 enheter. 

Om en enhet är Azure AD ansluten måste den kopplas bort från Azure AD och anslutas igen. 

[![Azure AD-Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)


Om användaren är administratör på en annan Windows 10 kan användaren avregistrera enheten från Azure AD och åter ansluta till den igen. Om han eller hon inte har administratörsbehörighet behöver användaren autentiseringsuppgifter för ett lokalt administratörskonto på den här datorn. 


En administratör kan skapa ett lokalt administratörskonto på enheten genom att följa den här konfigurationssökvägen:

*Inställningar > konton > andra konton > okänd > Lägg till användare utan Microsoft-konto*

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a>Steg 1: Avgör om enheten är Azure-ID ansluten
1.  Logga in med användarnaS e-post och lösenord.
2.  Gå till Inställningar > Konton > Åtkomst till arbete eller skola. 
3.  Leta efter en användare i listan som är **ansluten till ... s Azure AD.** 
4.  Om en ansluten användare finns fortsätter du med steg 2. Om inte krävs inga ytterligare åtgärder.
### <a name="step-2-disconnect-the-device-from-azure-ad"></a>Steg 2: Koppla bort enheten från Azure AD
1.  Tryck **på Koppla** från på det anslutna arbets- eller skolkontot. 
2.  Bekräfta frånkopplingen två gånger. 
3.  Ange lokalt administratörsnamn och lösenord. Enheten kopplas från.
4.  Starta om enheten.
### <a name="step-3-join-the-device-to-azure-ad"></a>Steg 3: Anslut enheten till Azure AD
1.  användaren loggar in med den lokala administratörens autentiseringsuppgifter
2.  Gå till **Inställningar** sedan **Konton och** komma åt arbete eller **skola**
3.  Tryck **på Anslut**
4.  **VIKTIGT:** Tryck **på Anslut till Azure AD**
5.  Ange användarens e-postadress och lösenord. Enheten är ansluten
6.  Starta om enheten 
7.  med din e-postadress och ditt lösenord

## <a name="azure-ad-registered-company-owned"></a>Azure AD Registered (företagsägd)

För att avgöra om Windows 10 är Azure AD-registrerad kör du följande kommando på enheten:

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

För Android måste användarna avregistrera sig och registrera sina enheter igen. Det kan du göra via Microsoft Authenticator eller det Företagsportal appen. 

- Från Microsoft Authenticator kan användarna gå till **enhetsregistreringen Inställningar >.** Därifrån kan användare avregistrera sig och registrera sin enhet igen.
 
- I Företagsportal enheter kan användarna gå till **fliken Enheter** och ta bort enheten. Därefter kan du registrera enheten igen med hjälp av Företagsportal.
 
- Användare kan också avregistrera och registrera igen genom att ta bort kontot från sidan kontoinställningar och sedan lägga till arbetskontot igen.

Så här avregistrerar du och registrerar om enheten på Android med hjälp av Microsoft Authenticator appen:

1.  Öppna Microsoft Authenticator och gå till **Inställningar**.
2.  Välj **Enhetsregistrering**.
3.  Avregistrera enheten genom att välja **Avregistrera**.
4.  För **enhetsregistrering** registrerar du enheten igen genom att skriva din e-postadress och väljer **registrera**.

Så här avregistrerar du och registrerar en Android-enhet på Inställningar Android-enhet:

1.  Öppna **Enhetshanteraren Inställningar** gå till **Konton**.
2.  Välj det arbetskonto du vill registrera igen och välj Ta **bort konto**.
3.  När kontot har tagits bort går du till **sidan Konton** och väljer Lägg till konto **> Arbetskonto**.
4.  I **Workplace Join** skriver du din e-postadress och väljer **Anslut** för att slutföra registreringen av enheten.

Så här avregistrerar du och registrerar om enheten på Android från Företagsportal:

1.  Starta Företagsportal gå till **fliken** Enheter.
2.  Välj enheten om du vill se enhetsinformationen.
3.  På ellipsmenyn (tre punkter) väljer du Ta **bort** enhet och slutför borttagningen genom att bekräfta i dialogrutan.
4.  Du bör nu vara utloggad från Företagsportal appen. Välj **Logga in** för att registrera enheten igen.

Mer information om åtgärder som krävs under migreringsfasen av den här arbetsbelastningen, eller som påverkar administration eller användning, finns i informationen om Azure Active Directory (Azure AD) i Ytterligare Azure AD-information för migreringen från [Microsoft Cloud Deutschland.](ms-cloud-germany-transition-azure-ad.md)

## <a name="ios"></a>iOS

På iOS-enheter måste en användare manuellt ta bort cachelagrade konton från Microsoft Authenticator, avregistrera enheten och logga ut från alla inbyggda appar på enheten.

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>Steg 1: Om det finns tar du bort kontot från Microsoft Authenticator programmet

1. Tryck på kontot i Microsoft Authenticator appen.
2. Tryck **Inställningar** i det övre högra hörnet. Om du inte ser ikonen **Inställningar** kanske du inte använder den senaste versionen av Microsoft Authenticator.
3. Tryck på **knappen Ta bort** konto.
4. Tryck **på Alla appar på den här enheten**.
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>Steg 2: Avregistrera enheten från Microsoft Authenticator appen

1. Tryck på menyikonen i det övre högra hörnet.
2. Tryck **Inställningar** och sedan **på Enhetsregistrering**.
4. Om ditt konto visas trycker du på **Avregistrera enhet** **och Fortsätt** i dialogrutan. Därefter bör du inte se något konto.
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>Steg 3: Logga ut från enskilda appar om det behövs

Användare kan gå till enskilda appar som Outlook, Teams och OneDrive och ta bort konton från dessa program.

## <a name="more-information"></a>Mer information

Komma igång:

- [Migrering från Microsoft Cloud Deutschland till Office 365 i de nya tyska datacenterområdena](ms-cloud-germany-transition.md)
- [Migreringshjälp för Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Så här väljer du in för migrering](ms-cloud-germany-migration-opt-in.md)
- [Kundupplevelse under migreringen](ms-cloud-germany-transition-experience.md)

Flytta genom övergången:

- [Åtgärder och påverkan i migreringsfaser](ms-cloud-germany-transition-phases.md)
- [Ytterligare arbete](ms-cloud-germany-transition-add-pre-work.md)
- Ytterligare information för [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [enheter,](ms-cloud-germany-transition-add-devices.md) [upplevelser](ms-cloud-germany-transition-add-experience.md)och [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Molnappar:

- [Information om Dynamics 365-migreringsprogram](/dynamics365/get-started/migrate-data-german-region)
- [Power BI i migreringsprogrammet](/power-bi/admin/service-admin-migrate-data-germany)
- [Komma igång med din Microsoft Teams uppgradering](/microsoftteams/upgrade-start-here)