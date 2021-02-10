---
title: Rapportera skräppost, icke-skräppost och nätfiskemeddelanden till Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig mer om de olika sätten att rapportera bra och dåliga meddelanden och filer till Microsoft för analys.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b75b05f33ab6c6a5827101ad2f5b14c94b932135
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166693"
---
# <a name="report-messages-and-files-to-microsoft"></a>Rapportera meddelanden och filer till Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection (EOP) organisationer utan Exchange Online-postlådor har både användare och administratörer flera olika metoder för att rapportera e-postmeddelanden och filer till Microsoft.

****

|Metod|Beskrivning|
|---|---|
|[Använd administrationsinskickning för att skicka misstänkt skräppost, nätt phish, URL:er och filer till Microsoft](admin-submission.md)|Den rekommenderade rapporteringsmetoden för administratörer i organisationer med Exchange Online-postlådor (inte tillgängligt i fristående EOP).|
|[Aktivera tillägget för att rapportera meddelande](enable-the-report-message-add-in.md)|Fungerar med Outlook och Outlook på webben (hette tidigare Outlook Web App). <p> Beroende på din prenumeration är meddelanden som användare har rapporterat med tillägget tillgängliga i portalen För inskickade [administratörer,](admin-submission.md) [AIR-resultat](view-email-security-reports.md#user-reported-messages-report) [(Automatiserad](air-view-investigation-results.md)undersökning och svar), rapporten över användarrapporterade meddelanden och [HotUtforskaren.](threat-explorer-views.md#email--submissions) <p> Du kan konfigurera rapporterade meddelanden så att de kopieras eller omdirigeras till en postlåda som du anger. Mer information finns i principer [för användarinskick.](user-submission.md)
|[Aktivera tillägget för att rapportera nätfiske](enable-the-report-phish-add-in.md)|Fungerar med Outlook och Outlook på webben (hette tidigare Outlook Web App). <p> Beroende på din prenumeration är meddelanden som användare har rapporterat med tillägget tillgängliga i portalen För inskickade [administratörer,](admin-submission.md) [AIR-resultat](view-email-security-reports.md#user-reported-messages-report) [(Automatiserad](air-view-investigation-results.md)undersökning och svar), rapporten över användarrapporterade meddelanden och [HotUtforskaren.](threat-explorer-views.md#email--submissions) <p> Du kan konfigurera rapporterade meddelanden så att de kopieras eller omdirigeras till en postlåda som du anger. Mer information finns i principer [för användarinskick.](user-submission.md)|
|[Installera och använda tillägget Skräppostrapportering för Microsoft Outlook](junk-email-reporting-add-in-for-microsoft-outlook.md)|Fungerar bara i Outlook.|
|[Rapportera skräppost och nätfiske i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Använd de inbyggda funktionerna i Outlook på webben för organisationer med Exchange Online-postlådor (inte tillgängligt i fristående EOP). <p> Meddelanden som användarna rapporterar är tillgängliga i [portalen För inskickade administratörer.](admin-submission.md) <p> Du kan konfigurera rapporterade meddelanden som ska kopieras eller omdirigeras till en postlåda som du anger. Mer information finns i principer [för användarinskick.](user-submission.md)|
|[Rapportera skräppost och nätfiske i Outlook för iOS och Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)|Använd de inbyggda funktionerna i Outlook för iOS och Android för organisationer med Exchange Online-postlådor (inte tillgängligt i fristående EOP). <p> Meddelanden som användarna rapporterar är tillgängliga i [portalen För inskickade administratörer.](admin-submission.md) <p> Du kan konfigurera rapporterade meddelanden så att de kopieras eller omdirigeras till en postlåda som du anger. Mer information finns i principer [för användarinskick.](user-submission.md)|
|[Skicka meddelanden till Microsoft manuellt för analys](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Skicka bifogade meddelanden manuellt till specifika Microsoft-e-postadresser för skräppost, inte skräppost och nätfiske.|
|[Använd regler för e-postflöde för att se vad dina användare rapporterar till Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|Lär dig hur du skapar en e-postflödesregel (kallas även transportregel) som meddelar dig när användare rapporterar meddelanden till Microsoft för analys.|
|[Skicka skadlig programvara och icke-skadlig programvara till Microsoft för analys](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Använd Microsoft Security Intelligence-webbplatsen för att skicka bifogade filer och andra filer.|

Om skräppost- eller nätfiskemeddelanden har satts i karantän i stället för levererats kan användare rapportera dem till Microsoft från karantänportalen i Säkerhets- & Efterlevnadscenter. Mer information finns i [Hitta och släppa meddelanden i karantän som användare i Microsoft 365.](find-and-release-quarantined-messages-as-a-user.md)

> [!NOTE]
> Data från inskickade data till Microsoft finns i Office 365 efterlevnadsgränsen i nord-amerikanska datacenter. Data granskas av analytiker i teknikteamet för att hjälpa till att göra filtren mer effektiva.
