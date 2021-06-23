---
title: Rapportera skräppost, icke-skräppost och nätfiskemeddelanden till Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
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
ms.openlocfilehash: a89ea8a41a31c9544284566fade0e603d48af759
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082822"
---
# <a name="report-messages-and-files-to-microsoft"></a>Rapportera meddelanden och filer till Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365 organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor har både användare och administratörer flera olika metoder för att rapportera e-postmeddelanden och filer till Microsoft.

<br>

****

|Metod|Beskrivning|
|---|---|
|[Använd administrationsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft](admin-submission.md)|Den rekommenderade rapporteringsmetoden för administratörer i organisationer med Exchange Online (inte tillgängligt i fristående EOP).|
|[Aktivera rapportmeddelandet eller tilläggen för nätfiske](enable-the-report-message-add-in.md)|Fungerar med Outlook och Outlook på webben (tidigare kallat Outlook Web App). <p> Beroende på din prenumeration finns meddelanden som användare rapporterat med tilläggen tillgängliga i portalen för administrationsinskick, AIR-resultat [(Automated investigation and response),](air-view-investigation-results.md)rapporten över användarrapporter och [Utforskaren.](threat-explorer-views.md#email--submissions) [](admin-submission.md) [](view-email-security-reports.md#user-reported-messages-report) <p> Du kan konfigurera rapporterade meddelanden så att de kopieras eller omdirigeras till en postlåda som du anger. Mer information finns i Principer [för användarinskick.](user-submission.md)
|[Rapportera falska positiva och falska negativa i Outlook](report-false-positives-and-false-negatives.md)|Skicka falska positiva resultat (bra e-postmeddelande som har blockerats eller skickats till skräppostmappen) och falska negativa meddelanden (oönskad e-post eller nätfingr som skickats till Inkorgen) till Exchange Online Protection (EOP) med hjälp av funktionen Rapportmeddelande.|
|[Skicka meddelanden till Microsoft manuellt för analys](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Skicka bifogade meddelanden manuellt till specifika Microsoft-e-postadresser för skräppost, inte skräppost och nätfiske.|
|[Använd e-postflödesregler för att se vad användare rapporterar till Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|Lär dig hur du skapar en e-postflödesregel (kallas även transportregel) som meddelar dig när användare rapporterar meddelanden till Microsoft för analys.|
|[Skicka skadlig programvara och icke-skadlig programvara till Microsoft för analys](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Använd webbplatsen Microsoft Säkerhetsinsikter skicka bifogade filer och andra filer.|
|

Om skräppost- eller nätfiskemeddelanden har satts i karantän i stället för att levereras kan användare rapportera meddelandena till Microsoft från karantän i Microsoft 365 Defender portalen. Mer information finns i [Hitta och släppa meddelanden i karantän som användare i Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).

> [!NOTE]
> Data från inskickade data till Microsoft lagras Office 365 gränsen för efterlevnad i nordamerikas datacenter. Data granskas av analytikerna i teknikteamet för att hjälpa till att göra filtren mer effektiva.
