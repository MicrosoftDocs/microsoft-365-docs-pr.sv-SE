---
title: AD FS-migreringssteg för migreringen från Microsoft Cloud Deutschland
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
description: 'Sammanfattning: Ad FS-migreringssteg (Active Directory Federation Services) för migreringen från Microsoft Cloud Deutschland.'
ms.openlocfilehash: 030515227f3abdae82736807a01d1691d2d45552
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727473"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>AD FS-migreringssteg för migreringen från Microsoft Cloud Deutschland

Den här konfigurationsändringen kan tillämpas när som helst innan fas 4 startar.
När fas 2 är slutförd kommer konfigurationsändringen att fungera och du kan logga in på globala slutpunkter för Office 365, till exempel `https://portal.office.com` . Om du implementerar konfigurationsändringen före fas 2 fungerar ännu  inte de globala Office 365-slutpunkterna, men det nya förtroende som förlitar sig på parten fortfarande är en del av AD FS-konfigurationen (Active Directory Federation Services).

Så här migrerar du AD FS-servergruppen från Microsoft Cloud Deutschland:

1. Backa upp dina AD FS-inställningar, inklusive information om FF-förtroende med [hjälp av de här stegen.](#backup) Namnge säkerhetskopian **Microsoft Cloud Deutschland_Only** den bara har information om Microsoft Cloud Deutschland-klientorganisationen.
2. Testa återställningen med hjälp av säkerhetskopian Microsoft Cloud Deutschland_Only. AD FS-servergruppen bör fortsätta fungera som Endast Microsoft Cloud Deutschland.

När du har slutfört och testat AD FS-säkerhetskopieringen utför du följande steg för att lägga till ett nytt förtroende för den beroende parten i din ADFS-konfiguration:

1. Öppna AD FS-hanteringskonsolen
2. I den vänstra rutan i ADFS-hanteringskonsolen expanderar du **ADFS** och sedan Förtroenderelationer **och** använder **gruppförtroenden**
3. I den högra rutan väljer du **Lägg till förtroende för förlitande part...**
4. Välj **Nästa** på **välkomstsidan** i guiden Lägg till förtroende för förlitande part.
5. Välj Importera **data om den** beroende part som är publicerad online eller i ett lokalt nätverk på sidan Välj **datakälla.** Värdet **för federationsmetadataadress (värdnamn** eller URL) måste anges till `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Klicka sedan på **Nästa**.
6. På sidan **Välj datakälla** skriver du visningsnamnet, till exempel **Microsoft Office 365 Identity Platform WorldWide.** Klicka sedan på **Nästa**.
7. På sidan Konfigurera **multifaktorautentisering nu?** väljer du ett lämpligt val enligt dina autentiseringskrav. Om du väljer Jag vill inte konfigurera flerfaktorautentisering för detta förtroende för förlitar sig på part för **stunden.** Du kan ändra den här inställningen senare om du vill.
8. Behåll Tillåt alla användare  att komma åt **den** här beroende parten som är vald på Klicka på **Nästa** i välj utfärdningsauktoriseringsregler
9. Klicka **på** Nästa på **sidan Är redo att lägga till** förtroende för att slutföra guiden.
10. Klicka **på** Stäng på **sidan** Slutför.

Genom att stänga guiden upprättas förtroende för den beroende parten med globala Office 365-tjänster. Det finns dock ännu inga regler för utfärdningstransformning.

Du kan använda [AD FS-hjälpen för](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) att generera rätt regler för utfärdningstransformning. De anspråksregler som skapats med AD FS-hjälpen kan antingen läggas till manuellt via AD FS-hanteringskonsolen eller med PowerShell. AD FS-hjälpen genererar de PowerShell-skript som krävs.  

<!--
    Question from ckinder
    is step #3 true?
    how to verify step 5? Need more information!
-->
1. Kör Generera anspråk på AD FS-hjälp och kopiera PowerShell anspråk på transformeringsskript med alternativet Kopiera i det övre högra hörnet i skriptet.  
2. Öppna den textredigerare du föredrar och klistra in PowerShell-skriptet i ett nytt textfönster.
3. Lägg till följande PowerShell-rader i slutet av det klistrade skriptet från steg 2
    ```powershell
    $authzRules = "=>issue(Type = `"http://schemas.microsoft.com/authorization/claims/permit`", Value = `"true`"); "
    $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
    Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString -IssuanceAuthorizationRules $authzRules
    ```
4. Säkra och kör PowerShell-skriptet.
5. Kontrollera att det finns två förtroenden för förlitande part. en för Microsoft Cloud Deutschland och en för den globala Office 365-tjänsten.
6. Säkerhetskopiera dina förtroenden genom att [följa de här stegen](#backup). Spara den med namnet **FFAndWorldwide**.
7. Slutför backend-migreringen och kontrollera att AD FS fortfarande fungerar under migreringen.

## <a name="ad-fs-disaster-recovery-wid-database"></a>AD FS-katastrofåterställning (WID-databas)

Om du vill återställa AD FS-servergruppen i en katastrof måste snabb återställningsverktyget för [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) utnyttjas. Därför måste verktyget laddas ned och innan migreringen startar måste en säkerhetskopia skapas och lagras på ett säkert sätt. I det här exemplet (TAT-miljöer) har följande kommandon körts för att backa servergruppen:

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>Backa upp en AD FS-servergrupp

1. Installera AD FS Rapid Restore Tool på den primära AD FS-servern.
2. Importera modulen i en PowerShell-session med det här kommandot.
    ```powershell
    Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
    ```
3. Kör kommandot för säkerhetskopiering:
    ```powershell
    Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
    ```
4. Spara säkerhetskopian på ett säkert sätt på önskad destination.

### <a name="restore-an-ad-fs-farm"></a>Återställa en AD FS-servergrupp

Om servergruppen misslyckades helt och det inte går att återgå till den gamla servergruppen gör du följande. 

1. Flytta den tidigare skapade och lagrade säkerhetskopian till den nya primära AD FS-servern.
2. Kör följande `Restore-ADFS` PowerShell-kommando. Om det behövs importerar du AD FS SSL-certifikatet i förväg.

    ```powershell
    Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
    ```

3. Peka dina nya DNS-poster eller belastningsutjämnaren på de nya AD FS-servrarna.

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

- [Information om Dynamics 365-migreringsprogram](https://aka.ms/d365ceoptin)
- [Information om Migreringsprogram för Power BI](https://aka.ms/pbioptin)
- [Komma igång med uppgraderingen till Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
