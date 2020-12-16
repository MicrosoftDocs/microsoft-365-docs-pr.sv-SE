---
title: Migreringsåtgärder för migrering från Microsoft Cloud Deutschland
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
description: 'Sammanfattning: migrering av AD FS (Active Directory Federation Services) för migrering från Microsoft Cloud Deutschland.'
ms.openlocfilehash: c946ec3c0772cf95ab696266475b50959d682ef2
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688671"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>Migreringsåtgärder för migrering från Microsoft Cloud Deutschland

Så här migrerar du din AD FS-servergrupp (Active Directory Federation Services) från Microsoft Cloud Deutschland:

1. Säkerhetskopiera dina AD FS-inställningar inklusive AA-förtroende uppgifter med [de här stegen](#backup). Ge säkerhets kopierings programmet **Microsoft cloud Deutschland_Only** att det endast har Microsoft Cloud Deutschland-klient organisationen.
2. Testa återställningen med säkerhets kopian för Microsoft Cloud Deutschland_Only kan AD FS-servergruppen fortsätta fungera endast som Microsoft Cloud Deutschland.
3. Skapa ett nytt förlitande part-förtroende från **AD FS > Office 365-tjänster**.
4. I **förlitande part-förtroenden** i AD FS-hanteringskonsolen väljer du **Lägg till förlitande part-förtroende**.
5. Välj **Nästa** på **välkomst** sidan i guiden Lägg till förlitande part.
6. Välj **Importera data om den förlitande parten som publicerades online eller på ett lokalt nätverk** på sidan **Välj data källa** . Värdet för **federationsmetadata (värd namn eller URL)** är inställt på `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Klicka på **Nästa**.
7. Skriv visnings namnet på sidan **Välj data källa** . Microsoft rekommenderar **Microsoft Office 365 Identity Platform världen över**. Klicka på **Nästa**.
8. Klicka på **Nästa** på fliken **Konfigurera multifaktorautentisering nu?**, **Välj regler för utfärdandeauktorisering** och **klar att lägga till förtroende** sidor.
9. Klicka på **Stäng** på sidan **Slutför** .

Genom att stänga guiden är förlitande part-förtroendet för Office 365-tjänsterna eSTS. Inga regler för utfärdandeauktorisering upprättas.

Du kan använda [AD FS-hjälpen](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) för att generera korrekta regler för utfärdandeauktorisering. De genererade anspråks reglerna som skapas med AD FS-hjälpen kan antingen läggas till manuellt via AD FS-hanteringskonsolen eller med PowerShell. Med hjälp av AD FS kan du skapa nödvändiga PowerShell-skript som måste köras.  

1. Kör **Skapa anspråk** på AD FS-hjälp och kopiera omvandlingen av PowerShell-anspråk med alternativet **Kopiera** till höger övre högra hörnet i skriptet.
2. Klistra in den genererade PowerShell-filen på följande sätt:

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  Kör det färdiga skriptet.
4.  Kontrol lera att två förlitande part-förtroenden finns; en för hela världen och en för BF.
5.  Säkerhetskopiera dina förtroenden med [de här stegen](#backup). Spara den med namnet **FFAndWorldwide**.
6.  Slutför din server dels migrering och kontrol lera att AD FS fortfarande fungerar under migreringsprocessen.

## <a name="ad-fs-disaster-recovery-wid-database"></a>Återställning av en katastrof för AD FS (WID-databas)

För att återställa AD FS-servergruppen måste [Rapid Restore Tool-verktyget](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) användas av en katastrof. Verktyget måste laddas ned och innan migreringens början måste en säkerhets kopia skapas och sparas på ett säkert sätt. I det här exemplet (TAT Environment) har följande kommandon utförts för att säkerhetskopiera Server gruppen:

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>Säkerhetskopiera en AD FS-servergrupp

1. Installera AD FS Rapid Restore Tool på den primära AD FS-servern.
2. Importera modulen i en PowerShell-session med det här kommandot.

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. Kör säkerhets kopierings kommandot:

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. Spara säkerhets kopian på ett säkert sätt på önskad plats. 

### <a name="restore-an-ad-fs-farm"></a>Återställa en AD FS-servergrupp

Om din server grupp inte är fullständigt och det inte går att återvända till den gamla gruppen gör du följande: 

1. Flytta den tidigare genererade och lagrade säkerhets kopian till den nya primära AD FS-servern.
2. Kör följande `Restore-ADFS` PowerShell-kommando. Importera då AD FS SSL-certifikatet om det behövs.

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. Peka på de nya DNS-posterna eller belastningsutjämnaren till de nya AD FS-servrarna.

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
