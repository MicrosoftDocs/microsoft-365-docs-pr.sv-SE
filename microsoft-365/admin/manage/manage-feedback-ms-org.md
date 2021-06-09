---
title: Hantera Microsoft-feedback för din organisation
f1.keywords:
- NOCSH
ms.author: Kwekua
author: Kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Hantera feedback som dina användare kan skicka till Microsoft om Microsoft-produkter.
ms.openlocfilehash: 70ea1d5c176dd603f6a5addb09356909f13f9ace
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840676"
---
# <a name="manage-microsoft-feedback-for-your-organization"></a>Hantera Microsoft-feedback för din organisation

Som administratör för en organisation Microsoft 365 finns det nu flera principer som hjälper dig att hantera feedbackinsamlingen och kundgagemang för användarna när du använder Microsoft 365 program. Du kan skapa och använda befintliga Azure Active Directory-grupper i organisationen för var och en av dessa principer. Med de här enheterna kan du styra hur olika avdelningar i organisationen kan skicka feedback till Microsoft. Microsoft granskar all feedback som skickats in av kunder och använder denna feedback för att förbättra produkten. Om du låter **feedbackupplevelsen vara** påslagen kan du se vad användarna säger om de Microsoft-produkter de använder. Den feedback vi samlar in från dina användare kommer snart att bli tillgänglig Microsoft 365 administrationscentret.

Mer information om typer av feedback och hur Microsoft använder feedback från användare finns i [Läs mer om Microsoft-feedback för din organisation.](../misc/feedback-user-control.md)

I tabellen nedan ser du vilka appar och tjänster som för närvarande är anslutna till feedbackprinciperna som visas i tabellen för feedbackprinciper nedan. Se tabellen nedanför för skärmbildsexempel.

|**Appar & Tjänster**|**Feedback i produkten** <br> |**Undersökningar i produkten** <br> |**Metadatasamling** <br> |**Kundgagemang** <br> |
|:-----|:-----|:-----|:-----|:-----|
|**Åtkomst**|Ja|Ja|Ja|Ja|
|**Excel**|Ja|Ja|Ja|Ja|
|**Office.com**|Kommer snart|Kommer snart|Kommer snart|Kommer snart|
|**OneNote**|Ja|Ja|Ja|Ja|
|**OneDrive**|[Vissa inställningar hanteras för närvarande av andra kontroller.](/onedrive/disable-contact-support-send-feedback)||||
|**Outlook**|Kommer snart|Kommer snart|Kommer snart|Kommer snart|
|**PowerPoint**|Ja|Ja|Ja|Ja|
|**Project**|Kommer snart|Kommer snart|Kommer snart|Kommer snart|
|**Publisher**|Ja|Ja|Ja|Ja|
|**SharePoint**|[Vissa inställningar hanteras för närvarande av andra kontroller.](/powershell/module/sharepoint-online/set-spotenant)||||
|**Teams**|[Vissa inställningar hanteras för närvarande av andra kontroller.](/microsoftteams/manage-feedback-policies-in-teams)||||
|**Word**|Ja|Ja|Ja|Ja|
|**Visio**|Ja|Ja|Ja|Ja|
|**Yammer**|Ja|Ja|Ja|Ja|

[Här finns några exempel på undersökningar och feedback i produkter.](/microsoft-365/admin/misc/feedback-user-control#in-product-surveys)

**Metadatasamling**

:::image type="content" source="../../media/feedback-metadata2.png" alt-text="Skärmbild: Feedbacksida som visar metadataexempel":::

**Kundgagemang**

:::image type="content" source="../../media/feedback-in-product-customer-engagement.png" alt-text="Skärmbild: Exempel på produktspecifik kundundersökning":::

## <a name="before-you-begin"></a>Innan du börjar

Enheterna måste ha ett lägsta build-nummer för att kunna använda dessa principer. Se tabellen nedan för mer information.

|**Version #**|**Win32**|**iOS**|**Android**|**Mac**|**Webb**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Feedback i produkten|Minst 16.0.13328|Minst 2,42|Minst 16.0.13328|Minst 16,42|Offentligt tillgänglig|
|Undersökningar i produkten|Minst 16.0.13328|Minst 2,42|Minst 16.0.13426|Minst 16,42|Väntande utrullning|
|Metadatasamling|Minst 16.0.13328|Minst 2,42|Minst 16.0.13328|Minst 16,42|Offentligt tillgänglig|
|Kundgagemang|Minst 16.0.13328|Minst 2,42|Minst 16.0.13426|Minst 16,42|Väntande utrullning|

## <a name="specific-policies-you-can-configure"></a>Specifika principer som du kan konfigurera

### <a name="feedback-policies"></a>Feedbackpolicyer

|**Principnamn**|**Standardtillstånd**|**Kontrollsammanfattning**|
|:-----|:-----|:-----|
|Tillåt användare att skicka feedback till Microsoft|På|Styr feedbackinmatningspunkter mellan program|
|Tillåt att användare tar emot och svarar på undersökningar i produkter från Microsoft|På|Kontroller i undersökningsuppnstruktionerna i produkten|
|Tillåt användare att inkludera skärmbilder och bifogade filer när de skickar feedback till Microsoft|Av|Avgör vilka metadata som användaren kan skicka med feedback/undersökning|
|Tillåt Microsoft att följa upp feedback som skickats in av användare|Av|Avgör om användaren kan dela kontaktinformation med feedback/undersökning|
|Tillåt användare att inkludera loggfiler och innehållsexempel när feedback skickas till Microsoft|Av|Fastställer metadata som användaren kan skicka med feedback/undersökning|

## <a name="configure-policies"></a>Konfigurera principer

1. Gå till [https://config.office.com](https://config.office.com) och logga in som användare med behörighet som global administratör.
1. Välj **Anpassning** och **sedan Principhantering.**
1. Välj **Skapa**.
1. Ange **namn** och **beskrivning.**
1. Välj de Azure Active Directory-grupper som du vill konfigurera.
1. Sök efter **feedback** och **undersökning**.
1. För varje princip som visas ställer du in det värde du vill ha.

Mer information finns i [Översikt över Office molnprinciptjänsten.](/deployoffice/overview-office-cloud-policy-service)

De här principinställningarna är också tillgängliga om du använder Grupprincip. Om du vill använda de här principinställningarna laddar du ned minst version 5146.1000 av administrationsmallfilerna [(ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030)som släpptes den 22 mars 2021.

Du hittar de här principinställningarna under Användarkonfiguration -> Principer -> Administrativa mallar -> Microsoft Office 2016 -> Sekretess -> Säkerhetscenter.

> [!NOTE]
> Det tar några timmar innan klientprogrammen har uppdaterats.
