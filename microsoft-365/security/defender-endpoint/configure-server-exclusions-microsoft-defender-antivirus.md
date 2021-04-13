---
title: Konfigurera undantag för Microsoft Defender Antivirus på Windows Server
ms.reviewer: ''
manager: dansimp
description: Windows Server innehåller automatiska undantag, baserat på serverroll. Du kan också lägga till anpassade undantag.
keywords: undantag, server, automatisk exkludering, automatisk, anpassad, genomsökning, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.date: 02/10/2021
ms.openlocfilehash: 555daac32b202b0b9f46c4f19fa6e4b04bcadda3
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690856"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a>Konfigurera undantag för Microsoft Defender Antivirus på Windows Server

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus på Windows Server 2016 och Windows Server 2019 registrerar dig automatiskt i vissa undantag, enligt din angivna serverroll. Dessa undantag visas inte i standard undantagslistor som visas i [Windows-säkerhetsappen.](microsoft-defender-security-center-antivirus.md)

> [!NOTE]
> Automatiska undantag gäller endast för RTP-skanning (Real-time protection). Automatiska undantag respekteras inte vid en genomsökning av fullständiga/snabba eller på begäran.

Förutom serverrolldefinierade automatiska undantag kan du lägga till eller ta bort anpassade undantag. Information om hur du gör det finns i följande artiklar:
- [Konfigurera och validera undantag baserat på filnamn, filnamnstillägg och mappplats](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Konfigurera och validera undantag för filer som öppnas i processer](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a>Några saker att tänka på

Tänk på följande:

- Anpassade undantag har företräde framför automatiska undantag.
- Automatiska undantag gäller endast för RTP-skanning (Real-time protection). Automatiska undantag respekteras inte vid en genomsökning av fullständiga/snabba eller på begäran.
- Undantag för anpassade och dubbletter står inte i konflikt med automatiska undantag.
- Microsoft Defender Antivirus använder DISM-verktygen (Deployment Image Servicing and Management) för att avgöra vilka roller som är installerade på datorn.

## <a name="opt-out-of-automatic-exclusions"></a>Välja bort automatiska undantag

I Windows Server 2016 och Windows Server 2019 exkluderar de fördefinierade undantagen som levereras av säkerhetsintelligensuppdateringar endast standardsökvägarna för en roll eller funktion. Om du har installerat en roll eller funktion i en anpassad sökväg, eller om du manuellt vill styra uppsättningen undantag, måste du välja bort automatiska undantag som levereras i säkerhetsintelligensuppdateringar. Men kom ihåg att undantagen som levereras automatiskt är optimerade för Windows Server 2016- och 2019-roller. Se [Rekommendationer för att definiera undantag](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) innan du definierar dina undantagslistor.

> [!WARNING]
> Om du väljer bort automatiska undantag kan det påverka prestandan negativt eller resultera i skadade data. Undantag som levereras automatiskt optimeras för Windows Server 2016- och Windows Server 2019-roller.

Eftersom fördefinierade undantag bara exkluderar standardsökvägar måste du lägga till undantag manuellt med hjälp av informationen här om du flyttar NTDS och SYSVOL till en annan enhet eller sökväg som skiljer sig från den ursprungliga [sökvägen.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension)

Du kan inaktivera automatiska undantagslistor med Grupprincip, PowerShell-cmdlets och WMI.

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a>Använda grupprinciper för att inaktivera listan med automatiska undantag i Windows Server 2016 och Windows Server 2019

1. Öppna konsolen Grupprinciphantering på datorn [för grupprinciphantering.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)) Högerklicka på det grupprincipobjekt du vill konfigurera och klicka sedan på **Redigera.**
2. I **redigeraren för grupprinciphantering** går du **till Datorkonfiguration** och klickar sedan på **Administrativa mallar**.
3. Expandera trädet till **Windows-komponenter**  >  **Microsoft Defender Antivirus**  >  **Exclusions**.
4. Dubbelklicka på **Inaktivera automatiska undantag och** ställ in alternativet på **Aktiverad.** Klicka sedan på **OK**. 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a>Använda PowerShell-cmdlets för att inaktivera listan över automatiska undantag i Windows Server 2016 och 2019

Använd följande cmdlets:

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

Mer information finns i följande resurser:

- [Använd PowerShell-cmdlets för att konfigurera och köra Microsoft Defender Antivirus.](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Använd PowerShell med Microsoft Defender Antivirus.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a>Använd Instruktionerna för Windows Management (WMI) för att inaktivera listan över automatiska undantag i Windows Server 2016 och Windows Server 2019

Använd **metoden** Set för [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) för följande egenskaper:

```WMI
DisableAutoExclusions
```

Mer information och tillåtna parametrar finns i följande avsnitt:
- [API:er för Windows Defender WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a>Lista över automatiska undantag

Följande avsnitt innehåller undantag som levereras med automatiska undantag för filsökvägar och filtyper.

### <a name="default-exclusions-for-all-roles"></a>Standard undantag för alla roller

Det här avsnittet innehåller standard undantag för alla Windows Server 2016- och 2019-roller.

> [!NOTE]
> Standardplatserna kan vara annorlunda än de som anges i den här artikeln.

#### <a name="windows-tempedb-files"></a>Windows-filer "temp.edb"

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a>Windows Update-filer eller automatiska uppdateringsfiler

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a>Windows-säkerhetsfiler

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

#### <a name="group-policy-files"></a>Grupprincipfiler

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

#### <a name="wins-files"></a>WINS-filer

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

#### <a name="file-replication-service-frs-exclusions"></a>Undantag för File Replication Service (FRS)

- Filer i FRS-arbetsmappen (File Replication Service). Arbetsmappen FRS anges i registernyckeln `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- FRS-databasloggfiler. Loggfilmappen för FRS-databasen anges i registernyckeln `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`

  - `%windir%\Ntfrs\*\Edb\*.log`

- Mellanlagringsmappen FRS. Mellanlagringsmappen anges i registernyckeln `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- Förinstallera mappen FRS. Den här mappen anges av mappen `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- The Distributed File System Replication (HURR) databas och arbetsmappar. Dessa mappar anges av registernyckeln `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`

  > [!NOTE]
  > Information om anpassade platser finns [i Välja bort automatiska undantag.](#opt-out-of-automatic-exclusions)

  - `%systemdrive%\System Volume Information\DFSR\$db_normal$`
  - `%systemdrive%\System Volume Information\DFSR\FileIDTable_*`
  - `%systemdrive%\System Volume Information\DFSR\SimilarityTable_*`
  - `%systemdrive%\System Volume Information\DFSR\*.XML`
  - `%systemdrive%\System Volume Information\DFSR\$db_dirty$`
  - `%systemdrive%\System Volume Information\DFSR\$db_clean$`
  - `%systemdrive%\System Volume Information\DFSR\$db_lostl$`
  - `%systemdrive%\System Volume Information\DFSR\Dfsr.db`
  - `%systemdrive%\System Volume Information\DFSR\*.frx`
  - `%systemdrive%\System Volume Information\DFSR\*.log`
  - `%systemdrive%\System Volume Information\DFSR\Fsr*.jrs`
  - `%systemdrive%\System Volume Information\DFSR\Tmp.edb`

#### <a name="process-exclusions"></a>Undantag från processer

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

#### <a name="hyper-v-exclusions"></a>Hyper-V-undantag

I följande tabell visas undantag för filtyper, undantag för mappar och processkludering som levereras automatiskt när du installerar rollen Hyper-V.

|Undantag för filtyp |Undantag för mappar  | Undantag från processer |
|:--|:--|:--|
| `*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs` | `%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks` | `%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe` |

#### <a name="sysvol-files"></a>SYSVOL-filer

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


### <a name="active-directory-exclusions"></a>Undantag för Active Directory

Det här avsnittet innehåller en lista över undantag som levereras automatiskt när du installerar Active Directory Domain Services.

#### <a name="ntds-database-files"></a>NTDS-databasfiler

Databasfilerna anges i registernyckeln `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

#### <a name="the-ad-ds-transaction-log-files"></a>AD DS-transaktionsloggfilerna

Transaktionsloggfilerna anges i registernyckeln `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

#### <a name="the-ntds-working-folder"></a>Ntds-arbetsmappen

Den här mappen anges i registernyckeln `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

#### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a>Process undantas för AD DS- och AD DS-relaterade supportfiler

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

### <a name="dhcp-server-exclusions"></a>UNDANTAG för VAR OCH EN-server

Det här avsnittet innehåller en lista över undantag som levereras automatiskt när du installerar rollen TIDESERVER. TIDSFILSFILplatserna anges av parametrarna *DatabasePath,LogiFilePath* och *BackupDatabasePath* i registernyckeln `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a>Undantag för DNS Server

I det här avsnittet visas undantag för filer och mappar och undantag från processer som levereras automatiskt när du installerar DNS-serverrollen.

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a>Undantag för filer och mappar för DNS-serverrollen

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a>Process undantas för DNS Server-rollen

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a>Undantag för fil- och lagringstjänster

I det här avsnittet visas en lista över undantag för filer och mappar som levereras automatiskt när du installerar rollen Fil- och lagringstjänster. Undantag som visas nedan inkluderar inte undantag för rollen Gruppering.

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a>Undantag för Print Server

I det här avsnittet visas en lista över undantag för filtyper, undantag för mappar och processkludering som levereras automatiskt när du installerar rollen Skriv ut server.

#### <a name="file-type-exclusions"></a>Undantag för filtyp

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a>Undantag för mappar

Den här mappen anges i registernyckeln `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a>Undantag från processer

- `spoolsv.exe`

### <a name="web-server-exclusions"></a>Undantag för webbserver

Det här avsnittet innehåller en lista över undantag för mappar och processkludering som levereras automatiskt när du installerar webbserverrollen.

#### <a name="folder-exclusions"></a>Undantag för mappar

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

#### <a name="process-exclusions"></a>Undantag från processer

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a>Stänga av genomsökning av filer i mappen Sysvol\Sysvol eller mappen SYSVOL_DFSR\Sysvol

Den aktuella platsen för eller mappen och alla undermappar är filsystemets mappmål för `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` replikuppsättningens rot. I `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` mapparna och används som standard följande platser:

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

Sökvägen till den aktiva resursen refereras till av NETLOGON-resursen och kan fastställas av `SYSVOL` SysVol-värdenamnet i följande undernyckel: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`

Undanta följande filer från den här mappen och alla dess undermappar:

- `*.adm`
- `*.admx`
- `*.adml`
- `Registry.pol`
- `Registry.tmp`
- `*.aas`
- `*.inf`
- `Scripts.ini`
- `*.ins`
- `Oscfilter.ini`

### <a name="windows-server-update-services-exclusions"></a>Undantag för Windows Server Update Services

Det här avsnittet innehåller en lista över undantag för mappar som levereras automatiskt när du installerar rollen Windows Server Update Services (WSUS). WSUS-mappen anges i registernyckeln `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a>Se även

- [Konfigurera och validera undantag för genomsökningar för Microsoft Defender Antivirus](configure-exclusions-microsoft-defender-antivirus.md)
- [Konfigurera och validera undantag baserat på filnamn, filnamnstillägg och mappplats](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Konfigurera och validera undantag för filer som öppnas i processer](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Vanliga misstag att undvika när du definierar undantag](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [Anpassa, initiera och granska resultatet av genomsökningar och åtgärder i Microsoft Defender Antivirus](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)