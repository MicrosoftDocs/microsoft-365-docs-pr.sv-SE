---
title: Samarbeta med gäster på ett dokument
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords: NOCSH
description: Läs om hur du samarbetar med gäster i ett dokument i SharePoint och OneDrive.
ms.openlocfilehash: 139533b2d7bf65ddd9584007a5ac03800c731d0b
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/11/2020
ms.locfileid: "42813079"
---
# <a name="collaborate-with-guests-on-a-document"></a>Samarbeta med gäster på ett dokument

Om du behöver samarbeta med personer utanför organisationen i dokument i SharePoint eller OneDrive kan du skicka dem en delningslänk till dokumentet. I den här artikeln går vi igenom de konfigurationssteg för Microsoft 365 som krävs för att konfigurera delningslänkar för SharePoint och OneDrive för organisationens behov.

## <a name="video-demonstration"></a>Videodemonstration

Det här videoklippet visar de konfigurationssteg som beskrivs i det här dokumentet.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a>Inställningar för Azure-organisationsrelationer

Delning i Microsoft 365 styrs på den högsta nivån av organisationsrelationsinställningarna i Azure Active Directory. Om gästdelning är inaktiverat eller begränsat i Azure AD åsidosätter detta alla delningsinställningar som du konfigurerar i Microsoft 365.

Kontrollera inställningarna för organisationsrelationer för att säkerställa att delning med gäster inte är blockerad.

![Skärmbild av sidan Azure Active Directory-relationer](../media/azure-ad-organizational-relationships-settings.png)

Så här anger du inställningar för organisationsrelation

1. Logga in på [https://portal.azure.com](https://portal.azure.com)Microsoft Azure på .
2. Klicka på Azure Active Directory i den vänstra **navigeringen**.
3. Klicka på **Organisationsrelationer**i fönstret **Översikt** .
4. Klicka på **Inställningar**i fönstret **Organisationsrelationer** .
5. Se till att **administratörer och användare i rollen som gästinbjudare kan bjuda in** och att medlemmar kan bjuda **in** är båda inställda på **Ja**.
6. Om du har gjort ändringar klickar du på **Spara**.

Observera inställningarna i avsnittet **Samarbetsbegränsningar.** Kontrollera att domänerna för de gäster som du vill samarbeta med inte är blockerade.

## <a name="sharepoint-organization-level-sharing-settings"></a>Delningsinställningar för SharePoint-organisationsnivå

För att personer utanför organisationen ska ha åtkomst till ett dokument i SharePoint eller OneDrive måste delningsinställningarna för SharePoint- och OneDrive-organisationnivå tillåta delning med personer utanför organisationen.

Inställningarna på organisationsnivå för SharePoint avgör vilka inställningar som är tillgängliga för enskilda SharePoint-webbplatser. Webbplatsinställningar kan inte vara mer tillåtande än inställningarna på organisationsnivå. Inställningen på organisationsnivå för OneDrive avgör vilken delningsnivå som är tillgänglig i användarnas OneDrive-bibliotek.

Om du vill tillåta oautentiserad fil- och mappdelning väljer du **Vem som helst**om du vill tillåta oautentiserad fil- och mappdelning. Om du vill vara säker på att personer utanför organisationen måste autentisera väljer du **Nya och befintliga gäster**. *Alla* länkar är det enklaste sättet att dela: personer utanför organisationen kan öppna länken utan autentisering och är fria att vidarebefordra den till andra.

För SharePoint väljer du den mest tillåtande inställningen som behövs av en webbplats i organisationen.

![Skärmbild av delningsinställningar på organisationsnivå i SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Så här anger du delningsinställningar för SharePoint-organisationsnivå

1. Klicka på **SharePoint**i administrationscentret för Microsoft 365 under **Administrationscenter.**
2. Klicka på **Dela**i det vänstra navigeringscentret i administrationscentret för SharePoint.
3. Kontrollera att extern delning för SharePoint eller OneDrive är inställd **på Alla** eller Nya och **befintliga gäster**. (Observera att OneDrive-inställningen inte kan vara mer tillåtande än SharePoint-inställningen.)
4. Om du har gjort ändringar klickar du på **Spara**.

## <a name="sharepoint-organization-level-default-link-settings"></a>Standardlänkinställningar för SharePoint-organisationsnivå

Standardinställningarna för fil- och mapplänk avgör vilket länkalternativ som ska visas för användaren som standard när de delar en fil eller mapp. Användare kan ändra länktypen till något av de andra alternativen innan de delar om så önskas.

Tänk på att den här inställningen påverkar SharePoint-webbplatser i organisationen samt OneDrive.

Välj den typ av länk som är markerad som standard när användare delar filer och mappar:

- **Alla med länken** - Välj det här alternativet om du förväntar dig att göra en hel del oautentiserad fil- och mappdelning. Om du vill tillåta *alla* länkar men är oroade över oavsiktlig oautentiserad delning, överväga ett av de andra alternativen som standard. Den här länktypen är bara tillgänglig om du har aktiverat **Alla som** delar.
- **Endast personer i organisationen** – Välj det här alternativet om du förväntar dig att de flesta fil- och mappdelning ska vara med personer i organisationen.
- **Specifika personer** - Tänk på det här alternativet om du förväntar dig att göra en hel del fil- och mappdelning med gäster. Den här typen av länk fungerar med gäster och kräver att de autentiseras.
 
![Skärmbild av filer och inställningar för delning på Organisationsnivå i SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


Så här anger du standardlänkinställningarna för organisationsnivå på organisationsnivå och OneDrive

1. Navigera till sidan Dela i administrationscentret för SharePoint.
2. Under **Fil- och mapplänkar**väljer du den standarddelningslänk som du vill använda.
3. Om du har gjort ändringar klickar du på **Spara**.

## <a name="sharepoint-site-level-sharing-settings"></a>Dela inställningar för delning på SharePoint-webbplatsnivå

Om du delar filer och fodler som finns på en SharePoint-webbplats måste du också kontrollera delningsinställningarna för webbplatsnivå för den webbplatsen.

![Skärmbild av externa delningsinställningar för SharePoint-webbplats](../media/sharepoint-site-external-sharing-settings.png)

Så här anger du delningsinställningar på platsnivå
1. Expandera **Webbplatser** i det vänstra navigeringscentret i administrationscentret för SharePoint och klicka på **Aktiva webbplatser**.
2. Välj den webbplats som du just skapade.
3. Klicka på **Dela**i menyfliksområdet.
4. Se till att delning är inställt **på Alla** eller Nya och **befintliga gäster**.
5. Om du har gjort ändringar klickar du på **Spara**.

## <a name="invite-users"></a>Bjud in användare

Inställningar för gästdelning är nu konfigurerade, så att användarna nu kan dela filer och mappar med personer utanför organisationen. Mer information finns i [Dela OneDrive-filer och mappar](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) och Dela [SharePoint-filer eller mappar.](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c)

## <a name="see-also"></a>Se även

[Metodtips för delning av filer och mappar med oautentiserade användare](best-practices-anonymous-sharing.md)

[Begränsa oavsiktlig exponering för filer när du delar med gäster](share-limit-accidental-exposure.md)