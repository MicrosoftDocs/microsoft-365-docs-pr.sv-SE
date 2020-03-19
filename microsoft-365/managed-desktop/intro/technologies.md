---
title: Microsoftmanaged Desktop-tekniker
description: I det här avsnittet visas de tekniker och appar som används i Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: beab5df5b978cc3e2fd6dd345609a22209501298
ms.sourcegitcommit: 237589a0c8a24510e5c8f3b8b4747d944ad0afbf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "42811453"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoftmanaged Desktop-tekniker

I det här avsnittet visas de tekniker och appar som används i Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise-licensiering krävs för alla Användare av Microsoft Managed Desktop. Mer information om licenskrav för tjänsten finns i [Förutsättningar för Microsoft Managed Desktop](../get-ready/prerequisites.md).

I det här avsnittet sammanfattas de komponenter som ingår i de enterprise-licenser som krävs, med en beskrivning av hur tjänsten använder varje komponent med Microsoft Managed Desktop-enheter. Specifika roller och ansvarsområden för varje område beskrivs i dokumentationen för Microsoft Managed Desktop. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 eller E5
 |
 --- | ---
Office 365 ProPlus (64-bitars) | Dessa Office-program levereras med enheten: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype för företag, OneNote.<br><br>De 64-bitars fullständiga versionerna av Microsoft Project och Microsoft Visio ingår inte. Eftersom installationen av dessa program beror på Office 365 ProPlus-installationen har Microsoft Managed Desktop skapat standarddistributioner och säkerhetsgrupper som du sedan kan använda för att distribuera dessa program till licensierade slutanvändare. Mer information finns i [Installera Microsoft Project eller Microsoft Visio på Microsoft Managed Desktop-enheter](../get-started/project-visio.md).
OneDrive för företag |Azure Active Directory Single Sign On är aktiverat för slutanvändare vid första inloggning till OneDrive för företag.<br><br>Kända mappomdirigering för mapparna "Desktop", "Document" och "Pictures" ingår. aktiveras och konfigureras av Microsoft Managed Desktop. 
Lagra appar |    Microsoft Sway och Power BI levereras inte med enheten. Dessa appar är tillgängliga för nedladdning från Microsoft Store.
Win32-program |    Team levereras inte med enheten, utan paketeras och tillhandahålls av Microsoft för Microsoft Managed Desktop-enheter. Azure Information Protection Client levereras inte med enheten, men du kan låta den här paketeras för distribution. 
Webbprogram |  Yammer, Office i en webbläsare, Delve, Flow, StaffHub, PowerApps och Planner levereras inte med enheten. Användare kan komma åt webbversionen av dessa program med en webbläsare.


## <a name="windows-10-enterprise-e3-or-e5"></a>Windows 10 Enterprise E3 eller E5

 |
 --- | ---
Programvirtualisering (App-V) |    Kunder kan distribuera App-V-paket med intune Win32-apphanteringsklienten.
Microsoft Defender avancerat hotskydd |  Microsoft Managed Desktop använder detta för att övervaka enhetssäkerhet. 

## <a name="enterprise-mobility--security-e5"></a>Företagsmobilitet + Säkerhet E5

 |
 --- | ---
Företagsmobilitet + Säkerhet E3<br>Azure Active Directory Premium P2 |    Du kan använda alla funktioner i Enterprise Mobility + Security E3 och Azure Active Directory Premium P2 för att hantera MDM-enheter.
Säkerhet för Microsoft Cloud-appar |  Du kan använda den här valfria funktionen med Microsoft Managed Desktop.
Azure-informationsskydd P2  | Du kan använda den här valfria funktionen med Microsoft Managed Desktop.
