---
title: Konfigurera teams med grundläggande skydd
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365solutions
ms.custom:
- Ent_Solutions
description: Lär dig hur du distribuerar team med en grundläggande nivå av skydd.
ms.openlocfilehash: 4be93ce98f0066dcc65d7f532bd1d9d50acae406
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159973"
---
# <a name="configure-teams-with-baseline-protection"></a>Konfigurera teams med grundläggande skydd

I den här artikeln tittar vi på hur du distribuerar team med en grundläggande nivå av skydd. Den här nivån ger användare ett stort utbud av alternativ för samarbete medan det förbättrar av behörighetshantering och ger grundläggande skydd mot överdelning. Rekommenderade skydd för denna nivå inkluderar principer för identitets- och enhetsåtkomst och skydd mot skadlig programvara. Du kan också använda principer för villkorlig åtkomst och skydd mot dataförlust efter behov.

## <a name="initial-protections"></a>Initiala skydd

Som ett första steg rekommenderar vi att du konfigurerar principer för grundläggande principer för identitets- och enhetsåtkomst. Mer information finns i [Principrekommendationer för att skydda Teams-chattar, grupper och filer](https://docs.microsoft.com/microsoft-365/enterprise/teams-access-policies).

Vi rekommenderar även att du aktiverar grundläggande ATP-funktioner för att skydda mot skadlig programvara i dokument, bilagor och länkar. Vi rekommenderar att du aktiverar vart och ett av alternativen i tabellen nedan.

|Alternativ|Information |
|:------|:-----------|
|ATP säkra bilagor för SPO, OneDrive och Teams|[Office 365 ATP säkra bilagor](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br>[Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)|
|ATP Säkra dokument|[Säkra dokument i Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)|
|ATP Säkra länkar för Teams|[Office 365 säkra länkar i Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams)<br>[Office 365 ATP säkra länkar](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)|

## <a name="teams-guest-sharing"></a>Gästdelning i Teams

I respektive lager har vi alternativet att dela med personer utanför organisationen. I känsliga och mycket känsliga lager kan vi välja att inaktivera gästdelning på gruppnivå genom att använda känslighetsetiketter. Men inställning av gästdelning på organisationsnivå måste aktiveras för att gästdelning ska fungera över huvud taget i Teams.

![Skärmbild av växling för gäståtkomst i Teams](../media/teams-guest-access-toggle-on.png)

Att ange inställningar för gäståtkomst i Teams

1. Logga in på Administrationscenter för Microsoft 365 på [https://admin.microsoft.com](https://admin.microsoft.com).
2. Klicka på **Visa alla** i det vänstra navigeringsfönstret.
3. Under **Administrationscenter**klickar du på **Teams**.
4. Expandera **Inställningar för hela organisationen** och klicka på **Gäståtkomst** i Teams Administrationscenter i vänstra navigeringsfönstret.
5. Kontrollera att **Tillåt gäståtkomst i Teams** är inställt på **På**.
6. Gör önskade ändringar i de ytterligare gästinställningarna och klicka sedan på **Spara**.

> [!NOTE]
> Det kan ta upp till 24 timmar för gästinställningar i Teams att bli aktiva när du har aktiverat det.

Gästdelning är aktiverad som standard för Office 365-grupper och SharePoint, men om du tidigare har ändrat gästdelningsinställningarna för din organisation rekommenderar vi att du går igenom [Samarbeta med gäster i ett team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team) för att säkerställa att gästdelning blir tillgängligt i Teams.

## <a name="site-and-file-sharing"></a>Delning av webbplatser och filer

Om du vill minska risken för att oavsiktligt dela filer eller mappar med personer utanför organisationen rekommenderar vi att du ändrar den förvalda delningslänken för SharePoint till *Endast personer i organisationen*. (Om användare måste dela externt, och du har aktiverat gästdelning, kan de fortfarande ändra länktypen när de delar.)

Ändra standardlänken för delning
1. Öppna [SharePoint Online Administrationscenter](https://admin.microsoft.com/sharepoint).
2. Under **Principer**klickar du på **Delning**.
3. Under **Fil- och mapplänkar** väljer du **Endast personer i organisationen**.
4. Klicka på **Spara**.

Vi rekommenderar även att du aktiverar [SharePoint- och OneDrive-integrering med Azure Active Directory B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) om du vill ha bästa möjliga gästdelning.

## <a name="create-a-team"></a>Skapa ett team

Ytterligare konfiguration av grundläggande nivå av skydd görs på den SharePoint-webbplats som är kopplad till ett team. [Skapa ett offentligt eller privat team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) innan du går vidare till nästa avsnitt.

## <a name="site-sharing-settings"></a>Inställningar för webbplatsdelning

Som standard kan medlemmar i en SharePoint-webbplats bjuda in andra till webbplatsen. När en webbplats är en del av ett team inkluderas gruppmedlemmarna som webbplatsmedlemmar. Personer som lagts till direkt i webbplatsen har dock inte tillgång till resten av gruppen. Därför rekommenderar vi att du hanterar behörigheter exklusivt via gruppen.

Om du vill ha hjälp med hantering av behörigheter rekommenderar vi att du konfigurerar den kopplade webbplatsen så att ägaren bara kan dela webbplatsen. Det förenklar hantering av behörigheter och hindrar åtkomst av personer utan att gruppägarens kunskap. Gör detta för varje team som kräver grundläggande skydd.

Uppdatera inställningarna för webbplatsdelning
1. I verktygsfältet för teamet klickar du på **Filer**.
2. Klicka sedan **Öppna i SharePoint**.
3. Klicka på inställningsikonen i verktygsfältet på SharePoint-gruppwebbplatsen och klicka sedan på **Webbplatsbehörigheter**.
4. I fönstret **Webbplatsbehörigheter** under **Delningsinställningar** klickar du på **Ändra delningsinställningar**.
5. Under **Delningsbehörigheter** väljer du **Webbplatsägare och medlemmar, och personer med redigeringsbehörighet kan dela filer och mappar, men endast webbplatsägare kan dela webbplatsen** och klicka sedan på **Spara**.

## <a name="additional-protections"></a>Ytterligare skydd

Microsoft 365 tillhandahåller fler metoder för att skydda innehållet. Överväg att använda följande alternativ för att förbättra säkerheten för din organisation.

- Låt dina gästanvändare godkänna [användningsvillkor](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use).
- Konfigurera en [princip om tidsgräns för sessioner](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) för gäster.
- Skapa [känslig informationstyper](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types) och Använd [skydd mot dataförlust](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) för att ange principer för åtkomst av känslig information.

## <a name="see-also"></a>Se även

Få mer information om hur du [hanterar mötesprinciper i Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams).

[Komma igång med hantering av Insider-riskhantering](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure)
