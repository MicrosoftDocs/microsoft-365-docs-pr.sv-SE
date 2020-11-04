---
title: Abonnemang för Microsoft 365 multi-geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Lär dig mer om Microsoft 365 multi-geo, hur multi-geo fungerar och vilka geo-platser som är tillgängliga för data lagring.
ms.openlocfilehash: a8eba731fac16e56ef66ac0a905de521dfa7a6c8
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877238"
---
# <a name="plan-for-microsoft-365-multi-geo"></a>Abonnemang för Microsoft 365 multi-geo

Den här vägledningen är avsedd för administratörer av multinationella företag (MNCs) som förbereder sin Microsoft 365-klient för att utökas till ytterligare i enlighet med företagets närvaro för att uppfylla data de kraven.

I en multi-geo-konfiguration består din Microsoft 365-klient av en central plats och en eller flera satellit platser. Det här är en enda klient organisation som sträcker sig över flera geo platser. Din klient information, inklusive geo platser, hanteras i Azure Active Directory (Azure AD).

Här är några viktiga multi-geo-termer som hjälper dig att förstå de grundläggande begreppen i konfigurationen:

-   **Innehavare** – en organisations representation i Microsoft 365 som normalt har en eller flera domäner kopplade till sig (till exempel https://contoso.sharepoint.com) . 

-   **Geo platser** – de geografiska platser som är tillgängliga för att hantera data i en Microsoft 365-klient organisation.

-   **Satellit platser** – de ytterligare geo-platser som du har konfigurerat för att hantera data i din Microsoft 365-klient organisation. Multi-geo-klient organisationer är mer än en Geo-plats, till exempel Nord Amerika och Europa.

-   **Önskad data plats (PDL)** – den Geo-plats där en enskild användares Exchange-och OneDrive-data lagras. Det här kan anges av administratören till en av de geo-platser som har kon figurer ATS för innehavaren. Om du ändrar PDL för en användare som redan har en OneDrive-webbplats flyttas inte deras OneDrive-data till den nya geo-platsen automatiskt. Se [Flytta ett OneDrive-bibliotek till en annan Geo-plats](move-onedrive-between-geo-locations.md) för mer information. Om de har en Exchange-postlåda flyttas post lådan till den nya önskade data platsen automatiskt.

Att aktivera multi-geo kräver fyra viktiga steg:

1.  Arbeta med ditt konto team för att lägga till _flera geo funktioner i Microsoft 365_ service plan.

2.  Välj önskade satellit platser och Lägg till dem till din klient organisation.

3.  Ange användarnas förvalda plats på den önskade satellit platsen. När en ny OneDrive-webbplats eller Exchange-postlåda etableras för en användare har den tilldelats sin PDL.

4.  Migrera användarnas befintliga OneDrive-webbplatser från den centrala platsen till deras önskade data plats efter behov. (Exchange-postlådor migreras automatiskt när du anger en användares PDL.)

Mer information finns i [Konfigurera Microsoft 365 multi-geo](multi-geo-tenant-configuration.md) .

> [!IMPORTANT]
> Observera att Microsoft 365 multi-geo inte är utformat för prestanda optimering, att det är utformat för att uppfylla data de kraven. Information om prestanda optimering för Microsoft 365 finns i [nätverks planering och prestanda justering för microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) eller kontakta support gruppen.

Du kan konfigurera följande platser så att de är satellit platser där du kan vara värd för OneDrive-och SharePoint-webbplatser och Exchange-postlådor. När du planerar för multi-geo gör du en lista över de platser som du vill lägga till i Microsoft 365-klient organisationen. Vi rekommenderar att du startar med en eller två satellit platser och sedan gradvis expandera till fler geo platser om det behövs.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

När du konfigurerar multi-geo kan det vara bra att ta en att konsolidera din lokala infrastruktur när du migrerar till Microsoft 365. Om du till exempel har lokala Server grupper i Singapore och Malaysia kan du konsolidera dem till APC satellit plats, förutsatt att data de krav tillåter dig att göra det.

## <a name="best-practices"></a>Metodtips

Vi rekommenderar att du skapar en test användare i Microsoft 365 för att göra lite inledande testning. Vi går igenom några test-och verifierings steg med den här användaren innan du går vidare till inbyggda produktions användare i Microsoft 365 multi-geo.

När du har testat med test användaren väljer du en pilot grupp – eventuellt från din IT-avdelning – så att den är första att använda OneDrive och Exchange på en ny Geo-plats. För den första gruppen väljer du användare som inte har OneDrive. Vi rekommenderar att du inte har fler än fem personer i den här gruppen och expanderar successivt efter en grupp införande.

Varje användare bör ha en inställd *data plats* (PDL) så att Microsoft 365 kan bestämma vilken Geo-plats som ska användas för att etablera sin OneDrive. Användarens förvalda plats måste matcha en av dina valda satellit platser eller din centrala plats. När fältet PDL inte är obligatoriskt rekommenderar vi att en PDL är inställd för alla användare. Arbets belastningar för en användare utan en PDL etableras på Central platsen.

Skapa en lista över användarna och ange deras huvud namn (UPN) och plats koden för lämplig data plats. Ta med din test användare och den första pilot gruppen att börja med. Du behöver den här listan för konfigurations procedurerna.

Om dina användare synkroniseras från ett lokalt Active Directory-system till Azure Active Directory måste du ange önskad data plats som ett Active Directory-attribut och synkronisera den med Azure Active Directory Connect. Du kan inte konfigurera den valda platsen för synkroniserade användare direkt med Azure AD PowerShell. Anvisningarna för hur du konfigurerar PDL i Active Directory och synkroniserar dem finns i [Azure Active Directory Connect-synkronisering: konfigurera önskad data plats för Microsoft 365-resurser](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).

Administrationen av en multi-geo-klient organisation kan skilja sig från en icke-geo-klient organisation, så många av SharePoint-och OneDrive-inställningarna och-tjänsterna är multi-geo-medvetna. Vi rekommenderar att du granskar [administrationen av en multi-geo-miljö](administering-a-multi-geo-environment.md) innan du fortsätter med konfigurationen.

Läs [användar upplevelse i en multi-geo-miljö](multi-geo-user-experience.md) för att få information om slutanvändarnas erfarenheter i en miljö med flera geo.

Mer information om Teams Experience i ett Microsoft 365 multi-geo-innehavning finns i [Teams Experience i ett microsoft 365 OneDrive och SharePoint Online multi-geo-aktiveradt innehav](https://docs.microsoft.com/microsoftteams/teams-experience-o365odb-spo-multi-geo).

Om du vill komma igång med att konfigurera Microsoft 365 multi-geo läser du [Konfigurera microsoft 365 multi-geo](multi-geo-tenant-configuration.md).

När du har slutfört konfigurationen måste du komma ihåg att [migrera användarnas OneDrive-bibliotek](move-onedrive-between-geo-locations.md) om det behövs för att användarna ska kunna arbeta från sina data platser.
