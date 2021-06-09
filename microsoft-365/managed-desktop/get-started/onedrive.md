---
title: Microsoft OneDrive
description: Hur Microsoft Hanterat skrivbord uppsättningar OneDrive för registrerade enheter
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation, appar, verksamhetsbaserade appar, verksamhetsbaserade appar
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a26500c1671afffc7b70d509a4242914631b937c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904846"
---
# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Microsoft Hanterat skrivbord använder [OneDrive för företag](/onedrive/plan-onedrive-enterprise) som en molnlagringstjänst för alla Microsoft Hanterat skrivbord-enheter för att säkerställa att enheterna är så stateless som möjligt. Användaren kan hitta sina filer oavsett vilken enhet de loggar in på. Om du till exempel ersätter en Microsoft Hanterat skrivbord enhet med en ny synkroniseras filer automatiskt till den nya enheten.

Vi konfigurerar automatiskt de här inställningarna som standard på Microsoft Hanterade enheter:

- OneDrive är tyst konfigurerad med användarkontot och loggas automatiskt in (utan interaktion med användaren) på det användarkonto som användes för att logga in på Windows. Mer information finns i [Använda tyst konfiguration av användarkonton – OneDrive](/onedrive/use-silent-account-configuration)

- Funktionen Filer på begäran är aktiverad så att användarna kan komma åt filer från sin molnlagring i OneDrive utan att behöva använda diskutrymmet i onödan. Mer information finns i [Spara diskutrymme med OneDrive i Filer](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)på begäran för Windows 10 .

- Funktionen Flytta känd mapp aktiveras utan att du har aktiverat den för att backa upp användarnas data i molnet, vilket ger dem åtkomst till deras filer från valfri enhet. Mer information finns i [Backa upp dina dokument, bilder och skrivbordsmappar med OneDrive.](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)

- Användare kan inte inaktivera funktionen För känd mappflyttning eller ändra platsen för kända mappar för att säkerställa en enhetlig upplevelse på Microsoft Hanterat skrivbord enheter.

## <a name="user-experience"></a>Användarupplevelse

När Microsoft Hanterat skrivbord får en ny enhet går de igenom första körningen genom att ange sina Azure-autentiseringsuppgifter när de inställningar för enheten. När den här processen är slutförd kan de komma åt sitt skrivbord och ha den OneDrive upplevelsen.

1. Systemet meddelar användarna att OneDrive har konfigurerats och att de har loggats in automatiskt i OneDrive.

:::image type="content" source="media/onedrive-sync.png" alt-text="Avisering om att du nu synkroniserar OneDrive och du kan redigera filer i OneDrive. klicka här för att visa dina filer":::

2. Systemet meddelar användarna att OneDrive flytta känd mapp har konfigurerats för dem.

:::image type="content" source="media/onedrive-folders.png" alt-text="Meddelande som läser IT-avdelningen har säkerhetskopierat viktiga mappar. Mapparna säkerhetskopieras nu till enheten OneDrive är tillgängliga från andra enheter":::

3. För att undvika att dubbla ikoner på skrivbordet när enheter återställs eller uppdateras tar systemet automatiskt bort Microsoft Edge- och Microsoft Teams-ikoner från OneDrive-synkroniseringen, som visas i den här vyn i Utforskaren.

:::image type="content" source="media/onedrive-teams.png" alt-text="Utforskaren som visar Teams Och Edge-listor med avmarkerade kryssrutor och uppläsning av hovringstext som är undantagen från synkronisering.":::


## <a name="onedrive-sync-restrictions"></a>OneDrive för synkronisering

Om du behöver begränsa OneDrive synkronisering rekommenderar vi att du kontrollerar åtkomsten med en Azure Active Directory princip för villkorsstyrd åtkomst. Mer information finns i Aktivera [stöd för villkorsstyrd åtkomst i OneDrive synkroniseringsapp.](/onedrive/enable-conditional-access)

Om du inte kan använda en villkorsbaserad åtkomstprincip för Azure AD i organisationen ska DIN IT-administratör följa de här stegen:

1. Om du inte redan känner till det letar du upp ditt klientorganisations-ID enligt beskrivningen i [Hitta ditt Microsoft 365 klientorganisations-ID](/onedrive/find-your-office-365-tenant-id).
2. Logga in på OneDrive och välj sedan **Synkronisera i** det vänstra fönstret. Markera kryssrutan **Tillåt synkronisering endast på datorer som är ansluten** till vissa domäner och lägg sedan till klientorganisations-ID:t i listan över domäner. Mer information finns i Tillåt [synkronisering endast på datorer som är ansluten till vissa domäner.](/onedrive/allow-syncing-only-on-specific-domains)

> [!NOTE]
> Den här vägledningen gäller endast för klientorganisationen i Microsoft Hanterat skrivbord. Det finns andra inställningar som inte tas upp i den här artikeln.