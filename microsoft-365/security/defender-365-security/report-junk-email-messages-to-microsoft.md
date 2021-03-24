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
ms.openlocfilehash: 64b5708194d7597b8a2b1a84b51f2196415e56ea
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073185"
---
# <a name="report-messages-and-files-to-microsoft"></a>Rapportera meddelanden och filer till Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor har både användare och administratörer flera olika metoder för att rapportera e-postmeddelanden och filer till Microsoft.

****

|Metod|Beskrivning|
|---|---|
|[Använd administrationsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft](admin-submission.md)|Den rekommenderade rapporteringsmetoden för administratörer i organisationer med Exchange Online-postlådor (inte tillgängligt i fristående EOP).|
|[Aktivera tillägget för att rapportera meddelande](enable-the-report-message-add-in.md)|Fungerar med Outlook och Outlook på webben (kallades tidigare Outlook Web App). <p> Beroende på din prenumeration finns meddelanden som användare rapporterat med tillägget tillgängliga i portalen för administrationsinskick, AIR-resultat [(Automatiserad](air-view-investigation-results.md)undersökning och svar), Rapporten över användarrapporterade meddelanden och [](admin-submission.md) [Hotutforskaren.](threat-explorer-views.md#email--submissions) [](view-email-security-reports.md#user-reported-messages-report) <p> Du kan konfigurera rapporterade meddelanden så att de kopieras eller omdirigeras till en postlåda som du anger. Mer information finns i Principer [för användarinskick.](user-submission.md)
|[Aktivera tillägget för att rapportera nätfiske](enable-the-report-phish-add-in.md)|Fungerar med Outlook och Outlook på webben (kallades tidigare Outlook Web App). <p> Beroende på din prenumeration finns meddelanden som användare rapporterat med tillägget tillgängliga i portalen för administrationsinskick, AIR-resultat [(Automatiserad](air-view-investigation-results.md)undersökning och svar), Rapporten över användarrapporterade meddelanden och [](admin-submission.md) [Hotutforskaren.](threat-explorer-views.md#email--submissions) [](view-email-security-reports.md#user-reported-messages-report) <p> Du kan konfigurera rapporterade meddelanden så att de kopieras eller omdirigeras till en postlåda som du anger. Mer information finns i Principer [för användarinskick.](user-submission.md)|
|[Installera och använda tillägget Skräppostrapportering för Microsoft Outlook](junk-email-reporting-add-in-for-microsoft-outlook.md)|Fungerar bara i Outlook.|
|[Rapportera skräppost och nätfiske i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Använd de inbyggda funktionerna i Outlook på webben för organisationer med Exchange Online-postlådor (inte tillgängligt i fristående EOP). <p> Meddelanden som användare rapporterar är tillgängliga i [portalen för administrationsinskick.](admin-submission.md) <p> Du kan konfigurera rapporterade meddelanden så att de kopieras eller omdirigeras till en postlåda som du anger. Mer information finns i Principer [för användarinskick.](user-submission.md)|
|[Rapportera skräppost och nätfiske i Outlook för iOS och Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)|Använd de inbyggda funktionerna i Outlook för iOS och Android för organisationer med Exchange Online-postlådor (inte tillgängligt i fristående EOP). <p> Meddelanden som användare rapporterar är tillgängliga i [portalen för administrationsinskick.](admin-submission.md) <p> Du kan konfigurera rapporterade meddelanden så att de kopieras eller omdirigeras till en postlåda som du anger. Mer information finns i Principer [för användarinskick.](user-submission.md)|
|[Skicka meddelanden till Microsoft manuellt för analys](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Skicka bifogade meddelanden manuellt till specifika Microsoft-e-postadresser för skräppost, inte skräppost och nätfiske.|
|[Använd regler för e-postflöde för att se vad dina användare rapporterar till Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|Lär dig hur du skapar en e-postflödesregel (kallas även transportregel) som meddelar dig när användare rapporterar meddelanden till Microsoft för analys.|
|[Skicka skadlig programvara och icke-skadlig programvara till Microsoft för analys](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Använd Microsofts säkerhetsinformationswebbplats för att skicka bifogade filer och andra filer.|

Om skräppost- eller nätfiskemeddelanden har satts i karantän i stället för att levereras kan användare rapportera meddelandena till Microsoft från karantänportalen i säkerhets- & efterlevnadscenter. Mer information finns i [Hitta och släppa meddelanden i karantän som användare i Microsoft 365.](find-and-release-quarantined-messages-as-a-user.md)

> [!NOTE]
> Data från inskickade data till Microsoft lagras i Office 365-efterlevnadsgränsen i nordamerikas datacenter. Data granskas av analytikerna i teknikteamet för att hjälpa till att göra filtren mer effektiva.
