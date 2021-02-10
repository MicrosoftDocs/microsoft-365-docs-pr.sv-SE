---
title: Vanliga frågor och svar om meddelanden i karantän
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratörer kan visa vanliga frågor och svar om meddelanden i karantän i Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 019f1c103ef1aaf7641072cd1259d22e83f0de4c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166933"
---
# <a name="quarantined-messages-faq"></a>Vanliga frågor och svar om meddelanden i karantän

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Det här avsnittet innehåller vanliga frågor och svar om e-postmeddelanden i karantän för Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor.

Frågor och svar om skydd mot skräppost finns i Vanliga frågor och svar om skydd mot [skräppost.](anti-spam-protection-faq.md)

Frågor och svar om skydd mot skadlig programvara finns i Vanliga frågor och svar om skydd mot [skadlig programvara.](anti-malware-protection-faq-eop.md)

Frågor och svar om skydd mot förfalskning finns i Vanliga frågor och svar om skydd mot [förfalskning.](anti-spoofing-protection-faq.md)

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>Hur hanterar jag meddelanden som har satts i karantän för skadlig programvara?

Endast administratörer kan hantera meddelanden som har satts i karantän för skadlig programvara. Mer information finns i [Hantera meddelanden i karantän och filer som administratör.](manage-quarantined-messages-and-files.md)

## <a name="how-do-i-quarantine-spam"></a>Hur sätt jag i karantän för skräppost?

Som standard levereras meddelanden som klassificeras som skräppost eller massutskick av skräppostfiltrering till användarens postlåda och flyttas till mappen Skräppost. Men du kan skapa och konfigurera principer för skräppostskydd för att sätta skräppost i karantän eller massutskick av e-postmeddelanden i stället. Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>Hur ger jag användare tillgång till karantän?

En användare måste ha ett giltigt konto för att komma åt sina egna meddelanden i karantän. Fristående EOP kräver att användare representeras som e-postanvändare i EOP (skapas eller skapas manuellt via katalogsynkronisering). Mer information om hur du hanterar användare i fristående EOP-miljöer finns i [Hantera e-postanvändare i EOP.](manage-mail-users-in-eop.md)

## <a name="what-messages-can-end-users-access-in-quarantine"></a>Vilka meddelanden kan slutanvändarna få åtkomst till i karantän?

Användare kan komma åt skräppost, massutskick och nätfiskemeddelanden i april 2020 där de är mottagare. Slutanvändarna kan inte komma åt skadlig programvara i karantän, nätfiske med hög konfidens eller meddelanden som satts i karantän på grund av åtgärden Leverera meddelandet till den värdinde karantänen i e-postflödesregler (kallas även transportregler).  Mer information om användare som får åtkomst till meddelanden i karantän finns i [Hitta och släppa meddelanden i karantän som användare.](find-and-release-quarantined-messages-as-a-user.md)

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>Hur länge sparas meddelanden i karantän?

Du konfigurerar hur länge skräppost, nätfiske och massutskick av e-postmeddelanden sparas i karantän genom att använda principer för skydd mot skräppost. Standardvärdet är 30 dagar, vilket också är det högsta. Mer information finns i Konfigurera [principer för skydd mot skräppost i EOP](configure-your-spam-filter-policies.md)

För meddelanden som satts i karantän av åtgärden e-postflödesregel leverera meddelandet till den värdinde karantänen, lagras meddelandena i karantän i 30 dagar. Du kan inte konfigurera den här varaktigheten.

När tidsperioden gått ut tas meddelandena bort och kan inte återställas.

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>Kan jag släppa eller rapportera fler än ett meddelande i karantän åt gången?

I Säkerhets- & efterlevnadscenter kan du välja och släppa upp till 100 meddelanden i taget.

Administratörer kan använda cmdlet:arna [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) och [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) i Exchange Online PowerShell eller fristående EOP PowerShell för att hitta och släppa meddelanden i karantän samtidigt som de rapporterar falska positiva meddelanden i grupp.

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>Stöds jokertecken vid sökning efter meddelanden i karantän? Kan jag söka efter meddelanden i karantän för en viss domän?

Jokertecken stöds inte i Säkerhets- & Säkerhets- och efterlevnadscenter. När du söker efter en avsändare måste du till exempel ange den fullständiga e-postadressen. Men du kan använda jokertecken i Exchange Online PowerShell eller fristående EOP PowerShell.

Kopiera till exempel följande PowerShell-kod i Anteckningar och spara filen som .ps1 på en plats som är lätt att hitta (till exempel C:\Data\QuarantineRelease.ps1).

När du sedan ansluter till [Exchange Online PowerShell eller](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) Exchange Online Protection [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)kör du följande kommando för att köra skriptet:

```powershell
& C:\Data\QuarantineRelease.ps1
```

Skriptet gör följande:

- Hitta outgivna meddelanden som satts i karantän som skräppost från alla avsändare på fabrikam-domänen. Det maximala antalet resultat är 50 000 (50 sidor med 1 000 resultat).
- Spara resultatet i en CSV-fil.
- Släpp matchande meddelanden i karantän till alla ursprungliga mottagare.

```powershell
$Page = 1
$List = $null

Do
{
Write-Host "Getting Page " $Page

$List = (Get-QuarantineMessage -Type Spam -PageSize 1000 -Page $Page | where {$_.Released -like "False" -and $_.SenderAddress -like "*fabrikam.com"})
Write-Host "                     " $List.count " rows in this page match"
Write-Host "                                                             Exporting list to appended CSV for logging"
$List | Export-Csv -Path "C:\Data\Quarantined Message Matches.csv" -Append -NoTypeInformation

Write-Host "Releasing page " $Page
$List | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}

$Page = $Page + 1

} Until ($Page -eq 50)
```

När du släppt ett meddelande kan du inte släppa det igen.
