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
ms.openlocfilehash: 12465acf5b4afe7e252586ddd076250628b57dd3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165663"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>AD FS-migreringssteg för migreringen från Microsoft Cloud Deutschland

Den här konfigurationsändringen måste tillämpas när som helst innan fas 2 startar.
När fas 2 är slutförd kommer konfigurationsändringen att fungera och du kan logga in via Office 365 globala slutpunkter som `https://portal.office.com` . Om du implementerar konfigurationsändringen före fas 2 fungerar  inte de globala Office 365-slutpunkterna ännu men det nya förtroende för den beroende parten är fortfarande en del av AD FS-konfigurationen (Active Directory Federation Services).

Kunder som använder federerad autentisering med AD FS (Active Directory Federation Services) bör inte göra ändringar i utfärdare AV URI:er som används för alla autentiseringar med AD DS (Lokal Active Directory Domain Services) under migreringen. Att ändra utfärdare-URI:er leder till autentiseringsfel för användare i domänen. Uri:er för utfärdare kan ändras direkt i  AD FS eller när en domän konverteras från hanterad _till federerad_ och tvärtom. Vi rekommenderar att du inte lägger till, tar bort eller konverterar en federerad domän i Azure AD-klientorganisationen som har migrerats. Uri:er för utfärdare kan ändras när migreringen är fullständig.

Så här förbereder du AD FS-servergruppen för migreringen från Microsoft Cloud Deutschland:

1. Back up your AD FS settings, including the existing Microsoft Cloud Deutschland Relying Party trust, with [these steps](#backup). Namnge säkerhetskopian **MicrosoftCloudDeutschlandOnly** för att ange att den bara har information om Microsoft Cloud Deutschland-klientorganisationen.

   > [!NOTE]
   > Säkerhetskopian innehåller inte bara det befintliga Office 365 Relying Party Trust för Microsoft Cloud Deutschland, utan även alla andra Relying Party-förtroenden som finns i respektive AD FS-servergrupp.

2. Testa återställningen med hjälp av säkerhetskopian MicrosoftCloudDeutschlandOnly. AD FS-servergruppen bör fortsätta fungera som Endast Microsoft Cloud Deutschland.

När du har slutfört och testat AD FS-säkerhetskopieringen utför du följande steg för att lägga till ett nytt förtroende för den beroende parten i din ADFS-konfiguration:

1. Öppna AD FS-hanteringskonsolen.

2. I den vänstra rutan på ADFS-hanteringskonsolen navigerar du till menyn Förtroenden för **förlitande** part.

3. I den högra rutan väljer du **Lägg till förtroende för förlitande part...**

4. Välj **Börja** på **välkomstsidan** i guiden Lägg till förtroende för förlitande part.

5. Välj Importera **data om den** beroende part som är publicerad online eller i ett lokalt nätverk på sidan Välj **datakälla.** Värdet **för federationsmetadataadress (värdnamn** eller URL) måste anges till `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` . Klicka på **Nästa**.

6. På sidan **Ange visningsnamn** skriver du visningsnamnet, t.ex. **identitetsplattformen Microsoft Office 365 Hela världen.** Klicka på **Nästa**.

7. Om du använder ADFS i Windows Server 2012 väljer du på sidan Konfigurera multifaktorautentisering **nu?** på rätt val enligt dina autentiseringskrav. Om du väljer Jag vill inte konfigurera flerfaktorautentisering för detta förtroende för förlitar sig på part för **stunden.** Du kan ändra den här inställningen senare om du vill.

8. För AD FS 2012: Behåll Tillåt  alla användare att använda den här beroende parten markerad under Välj auktoriseringsregler i välj utfärdningsauktoriseringsregler och klicka på **Nästa.** 

9. För AD FS 2016 och AD FS 2019: På sidan Välj åtkomstkontrollprincip väljer du lämplig åtkomstkontrollprincip och klickar på **Nästa.**  Om inget är valt fungerar inte lita på den beroende **partens** förtroende.

10. Klicka **på** Nästa på **sidan Är redo att lägga till** förtroende för att slutföra guiden.

11. Klicka **på** Stäng på **sidan** Slutför.

Genom att stänga guiden upprättas lita på parten som förlitar sig Office 365 med den globala tjänsten. Det finns dock ännu inga regler för utfärdningstransformning.

Du kan använda [AD FS-hjälpen för](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) att generera rätt regler för utfärdningstransformning. De anspråksregler som skapats med AD FS-hjälpen kan antingen läggas till manuellt via AD FS-hanteringskonsolen eller med PowerShell. AD FS-hjälpen genererar de PowerShell-skript som krävs.  

> [!NOTE]
> [AD FS-hjälpen](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) genererar standardutformningsregler som levereras med produkten. Men om anpassade regler för utfärdningstransformering finns i Microsoft Cloud Deutschland Relying Party Trust (till exempel anpassade utfärdare av URI:er, oföränderliga ICKE-standard-ID eller andra anpassningar), måste reglerna som genereras av AD FS-hjälpen ändras på ett sätt som passar den anpassade logik som för närvarande gäller för Microsoft Cloud Deutschland som förlitar sig på part. Om de här anpassningarna inte är integrerade i reglerna som genereras via [AD FS-hjälpen](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)fungerar troligtvis inte autentisering för **Microsoft Office 365 Identity Platform WorldWide** för dina federerade identiteter. 

1. Kör **Generera anspråk i** AD [FS-hjälpen](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) och  kopiera PowerShell-skriptet med alternativet Kopiera i det övre högra hörnet i skriptet.

2. Följ anvisningarna i AD [FS-hjälpen](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) om hur du kör PowerShell-skriptet i AD FS-servergruppen för att generera det globala litande partförtroendet. Innan du kör skriptet ersätter du följande kodrader i det genererade skriptet enligt beskrivningen nedan:

   ```powershell
   # AD FS Help generated value
   $claims = Get-AdfsRelyingPartyTrust -Identifier $(Get-RpIdentifier) | Select-Object IssuanceTransformRules;
   # replace with
   $claims = Get-AdfsRelyingPartyTrust -Identifier urn:federation:MicrosoftOnline | Select-Object IssuanceTransformRules;

   # AD FS Help generated value
   Set-AdfsRelyingPartyTrust -TargetIdentifier $(Get-RpIdentifier) -IssuanceTransformRules $RuleSet.ClaimRulesString;
   # replace with
   Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:MicrosoftOnline -IssuanceTransformRules $RuleSet.ClaimRulesString;
   ```

3. Kontrollera att två Relying PartyTtrusts finns. en för Microsoft Cloud Deutschland och en för Office 365 globala tjänsten. Följande kommando kan användas för kontrollen. Den bör returnera två rader och respektive namn och identifierare.

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. Säkerhetskopiera din fullständiga migreringskonfiguration, inklusive båda förtroenden från förlitande part, med [hjälp av de här stegen.](#backup) Spara den med namnet **MicrosoftCloudDeutschlandAndWorldwide**.

5. Under migreringen kontrollerar du regelbundet att AD FS-autentisering fungerar med Microsoft Cloud Deutschland och Microsoft Global-molnet i de olika migreringssteg som stöds.

## <a name="ad-fs-disaster-recovery-wid-database"></a>AD FS-katastrofåterställning (WID-databas)

Om du vill återställa AD FS-servergruppen i en katastrof måste snabb återställningsverktyget för [AD FS](/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) utnyttjas. Därför måste verktyget laddas ned och innan migreringen startar måste en säkerhetskopia skapas och lagras på ett säkert sätt. I det här exemplet har följande kommandon körts för att backa upp en servergrupp som körs på en WID-databas:

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
