---
title: Microsoft OneDrive
description: Hur Microsoft Managed Desktop uppsättningar av OneDrive för registrerade enheter
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation, appar, verksamhetsbaserade appar, LOB-appar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 6cd2c993e0ca9d4c456a2914b866b65b59799afa
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233953"
---
# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Microsoft Hanterat skrivbord använder [OneDrive för företag](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise) som en molnlagringstjänst för alla Microsoft-enheter som hanteras av Microsoft för att säkerställa att enheterna är så tillståndslösa som möjligt. Användaren kan hitta sina filer oavsett vilken enhet de loggar in på. Om du till exempel ersätter en Microsoft Managed Desktop-enhet med en ny synkroniseras filer automatiskt till den nya enheten.

Vi konfigurerar automatiskt de här inställningarna som standard på Microsoft-hanterade enheter:

- OneDrive är tyst konfigurerad med användarkontot och loggas automatiskt in (utan interaktion med användaren) på det användarkonto som användes för att logga in i Windows. Mer information finns i [Tyst konfiguration av användarkonton – OneDrive](https://docs.microsoft.com/onedrive/use-silent-account-configuration)

- Funktionen Filer på begäran är aktiverad så att användarna kan komma åt filer från sin molnlagring i OneDrive utan att behöva använda diskutrymmet i onödan. Mer information finns i Spara diskutrymme med Filer på begäran [i OneDrive för Windows 10.](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)

- Funktionen Flytta känd mapp aktiveras tyst för att backa upp användarnas data i molnet, vilket ger dem åtkomst till deras filer från valfri enhet. Mer information finns i [Back up your Documents, Pictures, and Desktop folders with OneDrive.](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)

- Användare kan inte inaktivera funktionen Flytta känd mapp eller ändra platsen för kända mappar för att säkerställa en enhetlig upplevelse på Microsoft Managed Desktop-enheter.

## <a name="user-experience"></a>Användarupplevelse

När Microsoft Managed Desktop-användare får en ny enhet får de en första körningsupplevelse genom att ange sina Azure-autentiseringsuppgifter när de konfigurerar enheten. När den här processen är slutförd kan de komma åt skrivbordet och använda OneDrive.

1. Systemet meddelar användarna att OneDrive har konfigurerats och att de automatiskt har loggats in på OneDrive.

:::image type="content" source="media/onedrive-sync.png" alt-text="Avisering om att du synkroniserar OneDrive och du kan redigera filer i OneDrive. klicka här för att visa dina filer":::

2. Systemet meddelar användarna att Den kända mappflyttningen i OneDrive har konfigurerats för dem.

:::image type="content" source="media/onedrive-folders.png" alt-text="Meddelande om att IT-avdelningen har säkerhetskopierat viktiga mappar. Mapparna säkerhetskopieras nu till OneDrive och är tillgängliga från andra enheter":::

3. För att förhindra att dubbla ikoner på skrivbordet när enheter återställs eller återskapas, tar systemet automatiskt bort Microsoft Edge- och Microsoft Teams-ikoner från OneDrive-synkroniseringen, som visas i den här vyn i Utforskaren.

:::image type="content" source="media/onedrive-teams.png" alt-text="Utforskaren med Teams- och Edge-listor med avmarkerade kryssrutor och hovringstext som läser Undantagen från synkronisering.":::


## <a name="onedrive-sync-restrictions"></a>Synkroniseringsbegränsningar för OneDrive

Om du behöver begränsa OneDrive-synkronisering rekommenderar vi att du styr åtkomsten med en villkorsbaserad åtkomstprincip i Azure Active Directory. Mer information finns i Aktivera [stöd för villkorsstyrd åtkomst i OneDrive-synkroniseringsprogrammet.](https://docs.microsoft.com/onedrive/enable-conditional-access)

Om du inte kan använda en villkorsbaserad åtkomstprincip för Azure AD i organisationen ska IT-administratören följa de här stegen:

1. Om du inte redan vet det, slå upp ditt klientorganisations-ID enligt beskrivningen i Hitta [ditt klientorganisations-ID för Microsoft 365.](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id)
2. Logga in på administrationscentret för OneDrive och välj **sedan Synkronisera** i den vänstra rutan. Markera kryssrutan **Tillåt synkronisering endast på datorer med särskilda** domäner och lägg sedan till klientorganisations-ID:t i listan med domäner. Mer information finns i Tillåta [synkronisering endast på datorer som är ansluten till vissa domäner.](https://docs.microsoft.com/onedrive/allow-syncing-only-on-specific-domains)

> [!NOTE]
> Den här vägledningen gäller endast för klienter i Microsoft Managed Desktop. Det finns andra inställningar som inte diskuteras i den här artikeln.
