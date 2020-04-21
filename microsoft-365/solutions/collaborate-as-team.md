---
title: Samarbeta med gäster i ett team
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords: NOCSH
description: Läs om hur du samarbetar med gäster i Teams.
ms.openlocfilehash: 4b395f0086198c6226d720c38fc4ea13b1a9d887
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630755"
---
# <a name="collaborate-with-guests-in-a-team"></a>Samarbeta med gäster i ett team

Om du behöver samarbeta med gäster över dokument, uppgifter och konversationer rekommenderar vi att du använder Microsoft Teams. Teams tillhandahåller alla samarbetsfunktioner som är tillgängliga i Office och SharePoint med beständig chatt och en anpassningsbar och utökningsbar uppsättning samarbetsverktyg i en enhetlig användarupplevelse.

I den här artikeln går vi igenom de konfigurationssteg för Microsoft 365 som krävs för att konfigurera ett team för samarbete med gäster.

## <a name="video-demonstration"></a>Videodemonstration

I det här videoklippet visas de konfigurationssteg som beskrivs i det här dokumentet.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a>Inställningar för Azure-organisationsrelationer

Delning i Microsoft 365 styrs på högsta nivå av organisationsrelationerinställningarna i Azure Active Directory. Om gästdelning är inaktiverat eller begränsat i Azure AD åsidosätter detta alla delningsinställningar som du konfigurerar i Microsoft 365.

Kontrollera inställningarna för organisationsrelationer för att säkerställa att delning med gäster inte blockeras.

![Skärmbild av sidan med inställningar för organisationsrelationer i Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Så här anger du inställningar för organisationsrelationer

1. Logga in på [https://portal.azure.com](https://portal.azure.com)Microsoft Azure på .
2. Klicka på Azure **Active Directory**i den vänstra navigeringen .
3. Klicka på **Organisationsrelationer**i **fönstret Översikt.**
4. Klicka på **Inställningar**i fönstret **Organisationsrelationer** .
5. Se till att **administratörer och användare i gäst inbjudna roll kan bjuda in** och medlemmar kan bjuda **in** är båda inställda på **Ja**.
6. Om du har gjort ändringar klickar du på **Spara**.

Observera inställningarna i avsnittet **Samarbetsbegränsningar.** Kontrollera att domänerna för de gäster som du vill samarbeta med inte är blockerade.

## <a name="teams-guest-access-settings"></a>Inställningar för gäståtkomst till team

Lagen har en master on/off-knapp för gäståtkomst och en mängd olika inställningar som är tillgängliga för att styra vad gästerna kan göra i ett team. Huvudväxeln, **Tillåt gäståtkomst i Teams** måste vara **på** för gäståtkomst till arbete i Teams.

Kontrollera att gäståtkomst är aktiverat i Teams och gör eventuella justeringar av gästinställningarna baserat på dina affärsbehov. Tänk på att dessa inställningar påverkar alla team.

![Skärmbild av inställningen för gäståtkomst i Teams](../media/teams-guest-access-toggle-on.png)

Så här anger du inställningar för Teams gäståtkomst

1. Logga in på Microsoft 365 [https://admin.microsoft.com](https://admin.microsoft.com)admin center på .
2. I den vänstra navigeringen klickar du på **Visa alla**.
3. Klicka på **Teams** **under Administrationscenter**.
4. Expandera inställningar för hela Organisationen för hela Organisationen i administrationscentret för Team i den vänstra **navigeringen** och klicka på **Gäståtkomst**.
5. Kontrollera att **Tillåt gäståtkomst i Teams** är inställt på **På**.
6. Gör önskade ändringar i de ytterligare gästinställningarna och klicka sedan på **Spara**.

> [!NOTE]
> Det kan ta upp till 24 timmar innan Teams gästinställning blir aktiv när du har aktiverat den.

## <a name="microsoft-365-groups-guest-settings"></a>Gästinställningar för Microsoft 365 Grupper

Team använder Microsoft 365 Grupper för lagmedlemskap. Gästinställningarna för Microsoft 365 Grupper måste vara aktiverade för att gäståtkomsten i Teams ska fungera.

![Skärmbild av gästinställningar för Microsoft 365 Grupper i Microsoft 365-administrationscentret](../media/office-365-groups-guest-settings.png)

Så här anger du gästinställningar för Microsoft 365 Grupper

1. Expandera **Inställningar**i det vänstra navigeringsfältet i Microsoft 365 i det vänstra navigeringscentret .
2. Klicka på **Tjänster & tillägg**.
3. Klicka på **Microsoft 365 Grupper**i listan .
4. Kontrollera att kryssrutorna **Låt gruppmedlemmar utanför organisationen får åtkomst till gruppinnehåll** och **Låt gruppägare lägga till personer utanför organisationen i grupper** är markerade.
5. Om du har gjort ändringar klickar du på **Spara ändringar**.


## <a name="sharepoint-organization-level-sharing-settings"></a>Delningsinställningar för SharePoint-organisationsnivå

Teams-innehåll som filer, mappar och listor lagras alla i SharePoint. För att gästerna ska få tillgång till dessa objekt i Teams måste delningsinställningarna på SharePoint-organisationsnivå tillåta delning med gäster.

Inställningarna på organisationsnivå avgör vilka inställningar som är tillgängliga för enskilda webbplatser, inklusive webbplatser som är associerade med team. Webbplatsinställningarna kan inte vara mer tillåtande än inställningarna på organisationsnivå.

Om du vill tillåta fil- och mappdelning med oautentiserade personer väljer du **Alla**. Om du vill se till att alla gäster måste autentisera, välj **Nya och befintliga gäster.** Välj den mest tillåtande inställningen som behövs av en webbplats i organisationen.

![Skärmbild av delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)


Så här anger du delningsinställningar för SharePoint-organisationsnivå

1. Klicka på **SharePoint**under **Administrationscenter i administrationscentret**för Microsoft 365, i den vänstra navigeringen.
2. I navigeringsfönstret till vänster i administrationscentret för SharePoint klickar du på **Delning**.
3. Kontrollera att extern delning för SharePoint är inställt **på Alla** eller Nya och **befintliga gäster**.
4. Om du har gjort ändringar klickar du på **Spara**.


## <a name="sharepoint-organization-level-default-link-settings"></a>Standardlänkinställningar för sharepoint-organisationsnivå

Standardinställningarna för fil- och mapplänk avgör vilket länkalternativ som visas för användaren som standard när de delar en fil eller mapp. Användare kan ändra länktypen till ett av de andra alternativen innan de delar om så önskas.

Tänk på att den här inställningen påverkar alla team och SharePoint-webbplatser i organisationen.

Välj den typ av länk som är markerad som standard när användare delar filer och mappar:

- **Alla med länken** - Välj det här alternativet om du förväntar dig att göra en hel del oautentiserade delning av filer och mappar. Om du vill tillåta *någon* länkar men är oroliga för oavsiktlig oautentiserade delning, överväga ett av de andra alternativen som standard. Den här länktypen är bara tillgänglig om du har aktiverat **Alla delar.**
- **Endast personer i organisationen** – Välj det här alternativet om du förväntar dig att de flesta fil- och mappdelning ska vara med personer i organisationen.
- **Specifika personer** - Tänk på det här alternativet om du förväntar dig att göra en hel del fil- och mappdelning med gäster. Denna typ av länk fungerar med gäster och kräver att de autentisera.
 
![Skärmbild av delningsinställningar för filer och mappar för SharePoint på organisationsnivå](../media/sharepoint-organization-files-folders-sharing-settings.png)


Så här anger du standardlänkinställningar för SharePoint-organisationsnivå

1. Navigera till sidan Delning i administrationscentret för SharePoint.
2. Under **Fil- och mapplänkar**väljer du den standarddelningslänk som du vill använda.
3. Om du har gjort ändringar klickar du på **Spara**.

## <a name="create-a-team"></a>Skapa ett team

Nästa steg är att skapa det team som du planerar att använda för att samarbeta med gäster.

Så här skapar du ett team
1. På fliken **Teams** i Teams klickar du på **Gå med i eller skapa ett lag** längst ned i den vänstra rutan.
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
1. Klicka på **Fler alternativ** **\*\***( ) i gruppen och klicka sedan på **Lägg till medlem**.
2. Skriv namnet på den person som du vill bjuda in.
3. Klicka på **Lägg till**och sedan på **Stäng**.

Så här bjuder du in gäster till ett team
1. Klicka på **Fler alternativ** **\*\***( ) i gruppen och klicka sedan på **Lägg till medlem**.
2. Skriv e-postadressen till den gäst som du vill bjuda in.
3. Klicka på **Redigera gästinformation**.
4. Skriv gästens fullständiga namn och klicka på bocken.
5. Klicka på **Lägg till**och sedan på **Stäng**.

## <a name="see-also"></a>Se även

[Metodtips för att dela filer och mappar med oautentiserade användare](best-practices-anonymous-sharing.md)

[Begränsa oavsiktlig exponering för filer när de delas med gäster](share-limit-accidental-exposure.md)

[Skapa en säker miljö för gästdelning](create-secure-guest-sharing-environment.md)

[Skapa ett B2B-extranät med hanterade gäster](b2b-extranet.md)
