---
title: Inaktivera skräppostrapportering i Outlook på webben
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
ms.collection:
- M365-security-compliance
description: Som Office 365-administratör kan du inaktivera möjligheten för personer att rapportera e-post som skräppost.
ms.openlocfilehash: 0bca03786d0335c24e48340e588510f09d6f6a7e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42811137"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a>Inaktivera skräppostrapportering i Outlook på webben

Du kan skicka skräppost, skräppost och inte skräpmeddelanden till Microsoft för analys med hjälp av Outlook på webben (tidigare känt som Outlook Web App) skräprapporteringsalternativ, enligt beskrivningen i [Rapportera skräppost och nätfiskebedrägerier i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). Om du inte vill använda dessa alternativ kan administratörer stänga av dem via cmdleten [Set-OwaMailboxPolicy.](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?
<a name="sectionSection0"> </a>

- Beräknad tid att slutföra: 5 minuter

- Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Mer information om vilka behörigheter du behöver finns i posten "Outlook på webbpostlådeprinciperna" i [Exchange Online-behörigheter](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).

- Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a>Inaktivera skräppost, nätfiske och inte skräppostrapportering till Microsoft
<a name="sectionSection1"> </a>

Kör först följande kommando för att hämta namnen på dina tillgängliga Outlook-principer för webbpostlådan:

```
Get-OwaMailboxPolicy | Format-Table Name
```

Använd sedan följande syntax för att aktivera eller inaktivera skräppost och inte skräppostrapportering till Microsoft i Outlook på webben:

```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

I det här exemplet inaktiveras rapportering i standardprincipen för Outlook-webbappar:

```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

Detaljerad syntax- och parameterinformation finns i [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) och [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?
<a name="sectionSection2"> </a>

Kör **Get-OWAMailboxPolicy** för att kontrollera parametervärdena och öppna sedan Outlook på webben för en berörd användare (som har principen Outlook på webbpostlådan som tillämpas på dem) och kontrollera att alternativen för att rapportera skräppost, nätfiske och inte skräppost inte är tillgängliga. Du kan fortfarande markera meddelanden som skräppost, nätfiske och inte skräp, men du kan inte rapportera dem.
