---
title: Microsoft-teknik för hanterade skrivbord
description: I det här avsnittet visas de tekniker och appar som används i Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8a86220e7fcfe4c2e788b28842c77d238d98fda4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636202"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft-teknik för hanterade skrivbord

I det här avsnittet visas de tekniker och appar som används i Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise-licensiering krävs för alla Microsoft Managed Desktop-användare. Mer information om licenskrav för tjänsten finns i [Förutsättningar för Microsoft Managed Desktop](../get-ready/prerequisites.md).

I det här avsnittet sammanfattas de komponenter som ingår i de nödvändiga Företagslicenserna, med en beskrivning av hur tjänsten använder varje komponent med Microsoft Managed Desktop-enheter. Specifika roller och ansvarsområden för varje område beskrivs i microsofts hanterade skrivbordsdokumentation. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 eller E5
 |
 --- | ---
Microsoft 365-appar för företag (64-bitars) | Dessa Office-program levereras med enheten: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype för företag, OneNote.<br><br>De 64-bitars fullständiga versionerna av Microsoft Project och Microsoft Visio ingår inte. Eftersom installationen av dessa program beror på Microsoft 365 Apps för företagsinstallation har Microsoft Managed Desktop skapat standarddistributioner och säkerhetsgrupper för Microsoft Intune som du sedan kan använda för att distribuera dessa program till licensierade slutanvändare. Mer information finns i [Installera Microsoft Project eller Microsoft Visio på Microsoft Managed Desktop-enheter](../get-started/project-visio.md).
OneDrive för företag |Enkel inloggning i Azure Active Directory är aktiverat för slutanvändare när de loggar in på OneDrive för företag.<br><br>Kända mappomdirigering för mapparna "Skrivbord", "Dokument" och "Bilder" ingår. aktiveras och konfigureras av Microsoft Managed Desktop. 
Lagra appar |    Microsoft Sway och Power BI levereras inte med enheten. Dessa appar är tillgängliga för nedladdning från Microsoft Store.
Win32-program |    Team levereras inte med enheten, men är paketerade och tillhandahålls av Microsoft för Microsoft Managed Desktop-enheter. Azure Information Protection Client levereras inte med enheten, men du kan få det här paketerat för distribution. 
Webbprogram |  Yammer, Office i en webbläsare, Delve, Flow, StaffHub, PowerApps och Planner levereras inte med enheten. Användare kan komma åt webbversionen av dessa program med en webbläsare.


## <a name="windows-10-enterprise-e3-or-e5"></a>Windows 10 Enterprise E3 eller E5

 |
 --- | ---
Programvirtualisering (App-V) |    Kunder kan distribuera App-V-paket med hjälp av Intune Win32-apphanteringsklienten.
Microsoft Defender Avancerat skydd |  Microsoft Managed Desktop använder detta för att övervaka enhetssäkerheten. 

## <a name="enterprise-mobility--security-e5"></a>Företagsmobilitet + Säkerhet E5

 |
 --- | ---
Företagsmobilitet + Säkerhet E3<br>Azure Active Directory Premium P2 |    Du kan använda alla funktioner i Enterprise Mobility + Security E3 och Azure Active Directory Premium P2 för att hantera MDM-enheter.
Microsoft Cloud App Security |  Du kan använda den här valfria funktionen med Microsoft Managed Desktop.
Azure informationsskydd P2  | Du kan använda den här valfria funktionen med Microsoft Managed Desktop.
