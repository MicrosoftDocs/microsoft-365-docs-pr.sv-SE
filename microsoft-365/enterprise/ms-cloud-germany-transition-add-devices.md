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
ms.openlocfilehash: cdb3278e1d96b2ebdced122ab53db716c3195d8c
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903889"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Ytterligare enhetsinformation för migreringen från Microsoft Cloud Deutschland

Azure AD-anslutna och registrerade enheter som är anslutna till Microsoft Cloud Deutschland måste migreras efter fas 9 och före fas 10. Migreringen av en enhet beror på enhetstyper, operativsystem och Azure AD-relation. 

## <a name="azure-ad-joined-windows-10-devices"></a>Azure AD-anslutna Windows 10 enheter
Om en Windows 10 är Azure AD-ansluten måste den vara frånkopplad från Azure AD och måste vara ansluten igen. 

[![Azure AD-Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)


Om användaren är administratör på en Windows 10 kan användaren avregistrera enheten från Azure AD och åter ansluta till den i tre steg. 

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a>Steg 1: Avgör om enheten är Azure-ID ansluten
1.  Logga in med ditt jobbkonto.
2.  Gå till **Inställningar**  >  **Konton åtkomst** till arbete eller  >  **skola.** 
3.  Leta efter ett konto i listan som är **anslutet till [...]' s Azure AD.** 
4.  Om det finns ett anslutet konto fortsätter du med steg 2. 
### <a name="step-2-disconnect-the-device-from-azure-ad"></a>Steg 2: Koppla bort enheten från Azure AD
1.  Klicka **på Koppla** från på det anslutna arbets- eller skolkontot. 
2.  Bekräfta frånkopplingen två gånger. 
3.  Ange ett lokalt administratörsnamn och lösenord. Enheten kopplas från.
4.  Starta om enheten.
### <a name="step-3-join-the-device-to-azure-ad"></a>Steg 3: Anslut enheten till Azure AD
1.  Logga in med den lokala administratörens autentiseringsuppgifter.
2.  Gå till **Inställningar**  >  **Konton åtkomst** till arbete eller  >  **skola.**
3.  Klicka **på Anslut**.
4.  **VIKTIGT:** Klicka **på Anslut till Azure AD.**
5.  Ange e-postadressen och lösenordet för ditt arbetskonto. Enheten är ansluten.
6.  Starta om enheten.
7.  Logga in med e-postadressen och lösenordet för ditt arbetskonto.

Om användaren inte är administratör för enheten kan en global Azure AD-administratör skapa det lokala administratörskontot på enheten genom att följa den här konfigurationssökvägen och sedan ansluta till enheten igen:

*Inställningar > konton > andra konton > okänd > Lägg till användare utan Microsoft-konto*

För att åter gå med i organisationen kan autentiseringsuppgifterna för alla arbetskonto från din organisation användas i det här steget. 

Tänk på att det arbetskonto som användes för att ansluta till enheten automatiskt framhävs som administratör för enheten.
Alla andra arbetskonto från organisationen kan logga in på enheten men har inga administratörsbehörigheter.

## <a name="azure-ad-registered-workplace-joined-windows-10-devices"></a>Azure AD-registrerade (arbetsplats-anslutna) Windows 10 enheter
Om en Windows 10 är Azure AD-registrerad måste den kopplas bort från Azure AD och anslutas igen.

[![Azure AD-Re-Registration Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)

### <a name="step-1-determine-if-the-device-is-azure-id-registered"></a>Steg 1: Avgör om enheten är registrerad Azure-ID
1.  Logga in med din användare.
2.  Gå till **Inställningar**  >  **Konton åtkomst** till arbete eller  >  **skola.** 
3.  Upptäck ditt arbetskonto i listan och kontrollera om det är **anslutet till [...]' s Azure AD.**

    Om ditt arbetskonto finns i listan men INTE är anslutet till ett Azure AD fortsätter du med steg 2.

    I annat fall är enheten en Azure AD-ansluten enhet och du måste hänvisa till [Azure AD-Windows 10 enheter.](#azure-ad-joined-windows-10-devices)

### <a name="step-2-disconnect-the-device-from-azure-ad"></a>Steg 2: Koppla bort enheten från Azure AD
1.  Klicka på ditt arbetskonto. Knapparna *Info och* *Koppla från* visas.
2.  Klicka **på Koppla från.** 
3.  Bekräfta kontoborttagningen från enheten genom att klicka på **Ja**.
### <a name="step-3-connect-the-device-to-azure-ad"></a>Steg 3: Anslut till Azure AD
1.  Klicka **på Anslut**.
2.  Ange e-postadressen till ditt arbetskonto och klicka på **Nästa.**
3.  Ange lösenordet för ditt arbetskonto och klicka på **Logga in**.
4.  Bekräfta genom att klicka **på Klar**. Ditt arbetskonto visas igen.

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

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

**Hur vet jag om min organisation påverkas?**

Administratörer bör kontrollera `https://portal.microsoftazure.de` om de har några Azure AD-registrerade eller Azure AD-anslutna enheter. Om din organisation har Azure AD registrerat eller Azure AD-anslutna enheter måste organisationen följa instruktionerna på den här sidan.

**När registrerar mina användare sina enheter igen?**

Det är viktigt att du bara avregistrerar och registrerar dina enheter igen när [fas 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) är klar. Du måste slutföra omregistreringen innan fas 10 startar, annars kan åtkomsten till din enhet gå förlorade.

**Hur vet jag att alla mina enheter är registrerade i det offentliga molnet?**

Om du vill kontrollera om dina enheter är registrerade i det offentliga molnet bör du exportera och ladda ned listan med enheter från Azure AD-portalen till ett Excel kalkylblad. Filtrera sedan de enheter som är registrerade (med hjälp av kolumnen _registeredTime)_ efter det datum då organisationen har passerat [fas 9 i migreringsprocessen.](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization)

## <a name="additional-considerations"></a>Ytterligare överväganden

> [!IMPORTANT]
> Intune-tjänstens huvudnamn aktiveras efter fas [3](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer)i migreringsprocessen, vilket antyder aktiveringen av Azure AD-enhetsregistrering. Om du blockerade enhetsregistrering för Azure AD före migreringen måste du inaktivera Intune-tjänstens huvudnamn med PowerShell om du vill inaktivera enhetsregistrering för Azure AD med Azure AD-portalen igen. Du kan inaktivera Intune-tjänstens huvudnamn med det här kommandot Azure Active Directory PowerShell för Graph modul.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

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