---
title: Läs mer om standardprincipen för dataförlustskydd i Microsoft Teams (förhandsversion)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Läs mer om standardprincipen för skydd mot dataförlust i Microsoft Teams
ms.openlocfilehash: c6b7413fdd4017fe1211e804c00a2e9c0684468d
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149124"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a>Läs mer om standardprincipen för dataförlustskydd i Microsoft Teams (förhandsversion)

[Funktioner för skydd mot](dlp-learn-about-dlp.md) dataförlust har utökats så att de omfattar Microsoft Teams och kanalmeddelanden, inklusive meddelanden i privata kanaler. Som en del av den här versionen skapade vi en standard-DLP-princip för Microsoft Teams för första gången kunder till efterlevnadscenter.

## <a name="applies-to"></a>Gäller för

Alla klientorganisationar som är licensierade med en eller flera av licenserna nedan och har aktiva Teams användare
 
- ME5 
- MA5, 
- Efterlevnad i E5/A5 
- IP+G 
- OE5 
- O365 Advanced Compliance 
- EMS E5


## <a name="what-does-the-default-policy-do"></a>Vad innebär standardprincipen?

Standardprincipen för DLP för Teams spårar alla kreditkortsnummer som delas internt och externt i organisationen. Den här principen är som standardinställning för alla användare av klientorganisationen. Inga principtips skapas för slutanvändarna, men en aviseringshändelse skapas och ett meddelande med låg allvarlighetsgrad utlöses för administratören (som läggs till i principen). Administratören kan visa aktiviteterna och redigera policyinformationen genom att logga in på efterlevnadscentret.

Administratörer kan visa den här principen i [efterlevnadscentret >](https://compliance.microsoft.com/compliancesettings) sidan Principer för skydd mot dataförlust.


> [!div class="mx-imgBorder"]
> ![DLP Teams standardprincip](../media/default-teams-dlp-policy.png)

## <a name="edit-or-delete-the-default-policy"></a>Redigera eller ta bort standardprincipen

Om [du vill redigera standardprincipen för bättre prestanda eller ta bort den](create-test-tune-dlp-policy.md#tune-a-dlp-policy)använder du bara ett konto med behörigheter för **DLP-efterlevnadshantering.** Mer information finns i [Behörigheter](create-test-tune-dlp-policy.md#permissions).

