---
title: Samarbeta med gäster i ett team
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- M365solutions
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Lär dig mer om konfigurationsstegen för Microsoft 365 som krävs för att konfigurera ett team för samarbete med gäster i Teams.
ms.openlocfilehash: 2a412502af16ff95bf0f1f912ac57d00eb1d382a
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430393"
---
# <a name="collaborate-with-guests-in-a-team"></a>Samarbeta med gäster i ett team

Om du behöver samarbeta med gäster över dokument, uppgifter och konversationer rekommenderar vi att du använder Microsoft Teams. Teams tillhandahåller alla samarbetsfunktioner som är tillgängliga i Office och SharePoint med beständig chatt och en anpassningsbar och utökningsbar uppsättning samarbetsverktyg i en enhetlig användarupplevelse.

I den här artikeln går vi igenom de konfigurationssteg för Microsoft 365 som krävs för att konfigurera ett team för samarbete med gäster.

## <a name="video-demonstration"></a>Videodemonstration

Den här videon visar konfigurationsstegen som beskrivs i det här dokumentet.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a>Inställningar för Azure-organisationsrelationer

Delning i Microsoft 365 styrs på högsta nivå av organisationsrelationerinställningarna i Azure Active Directory. Om gästdelning är inaktiverat eller begränsat i Azure AD åsidosätter detta alla delningsinställningar som du konfigurerar i Microsoft 365.

Kontrollera inställningarna för organisationsrelationer för att säkerställa att delning med gäster inte blockeras.

![Skärmbild av sidan med inställningar för organisationsrelationer i Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Så här anger du inställningar för organisationsrelationer

1. Logga in på Microsoft Azure på [https://portal.azure.com](https://portal.azure.com) .
2. Klicka på Azure **Active Directory**i den vänstra navigeringen .
3. Klicka på Externa **identiteter**i **fönstret Översikt** .
4. Klicka på Inställningar för **externt samarbete**i fönstret **Organisationsidentiteter** .
5. Se till att **administratörer och användare i gäst inbjudna roll kan bjuda in** och medlemmar kan bjuda **in** är båda inställda på **Ja**.
6. Om du har gjort ändringar klickar du på **Spara**.

Observera inställningarna i avsnittet **Samarbetsbegränsningar.** Kontrollera att domänerna för de gäster som du vill samarbeta med inte är blockerade.

## <a name="teams-guest-access-settings"></a>Inställningar för gäståtkomst till team

Lagen har en master on/off-knapp för gäståtkomst och en mängd olika inställningar som är tillgängliga för att styra vad gästerna kan göra i ett team. Huvudväxeln, **Tillåt gäståtkomst i Teams** måste vara **på** för gäståtkomst till arbete i Teams.

Kontrollera att gäståtkomst är aktiverat i Teams och gör eventuella justeringar av gästinställningarna baserat på dina affärsbehov. Tänk på att dessa inställningar påverkar alla team.

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

## <a name="microsoft-365-groups-guest-settings"></a>Gästinställningar för Microsoft 365 Grupper

Team använder Microsoft 365 Grupper för lagmedlemskap. Gästinställningarna för Microsoft 365 Grupper måste vara aktiverade för att gäståtkomsten i Teams ska fungera.

![Skärmbild av gästinställningarna för Microsoft 365-grupper i administrationscenter för Microsoft 365](../media/office-365-groups-guest-settings.png)

Så här anger du gästinställningar för Microsoft 365 Grupper

1. Expandera **Inställningar**i det vänstra navigeringsfältet i Microsoft 365 i det vänstra navigeringscentret .
2. Klicka på **Organisationsinställningar**.
3. Klicka på **Microsoft 365 Grupper**i listan .
4. Kontrollera att kryssrutorna **Låt gruppmedlemmar utanför organisationen får åtkomst till gruppinnehåll** och **Låt gruppägare lägga till personer utanför organisationen i grupper** är markerade.
5. Om du har gjort ändringar klickar du på **Spara ändringar**.


## <a name="sharepoint-organization-level-sharing-settings"></a>Delningsinställningar för SharePoint-organisationsnivå

Teams-innehåll som filer, mappar och listor lagras alla i SharePoint. För att gästerna ska få tillgång till dessa objekt i Teams måste delningsinställningarna på SharePoint-organisationsnivå tillåta delning med gäster.

Inställningarna på organisationsnivå avgör vilka inställningar som är tillgängliga för enskilda webbplatser, inklusive webbplatser som är associerade med team. Webbplatsinställningarna kan inte vara mer tillåtande än inställningarna på organisationsnivå.

Om du vill tillåta fil- och mappdelning med oautentiserade personer väljer du **Alla**. Om du vill se till att alla gäster måste autentisera, välj **Nya och befintliga gäster.** Välj den mest tillåtande inställningen som behövs av en webbplats i organisationen.

![Skärmbild av delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)


Så här anger du delningsinställningar för SharePoint-organisationsnivå

1. Klicka på **SharePoint**under Administrationscenter i administrationscentret för Microsoft 365 i det vänstra **navigeringscentret.**
2. I navigeringsfönstret till vänster i administrationscentret för SharePoint klickar du på **Delning**.
3. Kontrollera att extern delning för SharePoint är inställt **på Alla** eller Nya och **befintliga gäster**.
4. Om du har gjort ändringar klickar du på **Spara**.


## <a name="sharepoint-organization-level-default-link-settings"></a>Standardlänkinställningar för sharepoint-organisationsnivå

Standardinställningarna för fil- och mapplänk avgör vilket länkalternativ som visas för användaren som standard när de delar en fil eller mapp. Användare kan ändra länktypen till ett av de andra alternativen innan de delar om så önskas.

Tänk på att den här inställningen påverkar alla team och SharePoint-webbplatser i organisationen.

Välj den typ av länk som är markerad som standard när användare delar filer och mappar:

- **Alla med länken** - Välj det här alternativet om du förväntar dig att göra en hel del oautentiserade delning av filer och mappar. Om du vill tillåta *någon* länkar men är oroliga för oavsiktlig oautentiserade delning, överväga ett av de andra alternativen som standard. Den här länktypen är bara tillgänglig om du har aktiverat **Någon delning.**
- **Endast personer i organisationen** – Välj det här alternativet om du förväntar dig att de flesta fil- och mappdelning ska vara med personer i organisationen.
- **Specifika personer** - Överväga det här alternativet om du förväntar dig att göra en hel del fil- och mappdelning med gäster. Denna typ av länk fungerar med gäster och kräver att de autentisera.
 
![Skärmbild av delningsinställningar för filer och mappar för SharePoint på organisationsnivå](../media/sharepoint-organization-files-folders-sharing-settings.png)


Så här anger du standardlänkinställningar för SharePoint-organisationsnivå

1. Gå till sidan Delning i administrationscentret för SharePoint.
2. Under **Fil- och mapplänkar**väljer du den standarddelningslänk som du vill använda.
3. Om du har gjort ändringar klickar du på **Spara**.

## <a name="create-a-team"></a>Skapa ett team

Nästa steg är att skapa det team som du planerar att använda för att samarbeta med gäster.

Så här skapar du ett team
1. På fliken **Teams** i Teams klickar du på **Anslut eller skapa ett lag** längst ned i den vänstra rutan.
2. Klicka på **Skapa ett team**.
3. Klicka på **Bygg ett team från grunden**.
4. Välj **Privat** eller **Offentlig**.
5. Skriv ett namn och en beskrivning för teamet och klicka sedan på **Skapa**.
6. Klicka på **Hoppa över**.

Vi bjuder in användare senare. Därefter är det viktigt att kontrollera delningsinställningarna på webbplatsnivå för SharePoint-webbplatsen som är kopplad till teamet.

## <a name="sharepoint-site-level-sharing-settings"></a>Delningsinställningar för SharePoint-webbplatsnivå

Kontrollera delningsinställningarna på webbplatsnivå för att se till att de tillåter den typ av åtkomst som du vill ha för det här teamet. Om du till exempel anger inställningarna på organisationsnivå till **Alla**, men vill att alla gäster ska autentisera för det här teamet, kontrollerar du att delningsinställningarna på webbplatsnivå är inställda på **Nya och befintliga gäster**.

![Skärmbild av inställningar för extern delning för SharePoint](../media/sharepoint-site-external-sharing-settings.png)


Så här anger du delningsinställningar på webbplatsnivå
1. I navigeringsfönstret till vänster i administrationscentret för SharePoint expanderar du **Webbplatser** och klickar på **Aktiva webbplatser**.
2. Välj webbplatsen för det team som du just har skapat.
3. Klicka på **Delning** i menyfliksområdet.
4. Se till att delning är inställt **på Vem som helst** eller Nya och befintliga **gäster**.
5. Om du har gjort ändringar klickar du på **Spara**.

## <a name="invite-users"></a>Bjud in användare

Gästdelningsinställningarna är nu konfigurerade, så att du kan börja lägga till interna användare och gäster i ditt team. 

Så här bjuder du in interna användare till ett team
1. Klicka på **Fler alternativ** ( ) i gruppen och klicka sedan på Lägg **\*\*\*** till **medlem**.
2. Skriv namnet på den person som du vill bjuda in.
3. Klicka på **Lägg till**och sedan på **Stäng**.

Så här bjuder du in gäster till ett team
1. Klicka på **Fler alternativ** ( ) i gruppen och klicka sedan på Lägg **\*\*\*** till **medlem**.
2. Skriv e-postadressen till den gäst som du vill bjuda in.
3. Klicka på **Redigera gästinformation**.
4. Skriv gästens fullständiga namn och klicka på bocken.
5. Klicka på **Lägg till**och sedan på **Stäng**.

## <a name="see-also"></a>Se även

[Metodtips för att dela filer och mappar med oautentiserade användare](best-practices-anonymous-sharing.md)

[Begränsa oavsiktlig exponering för filer när de delas med gäster](share-limit-accidental-exposure.md)

[Skapa en säker miljö för gästdelning](create-secure-guest-sharing-environment.md)

[Skapa ett B2B-extranät med hanterade gäster](b2b-extranet.md)
