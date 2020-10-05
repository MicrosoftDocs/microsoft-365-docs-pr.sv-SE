---
title: Samar beta med gäster i ett dokument
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: I den här artikeln får du lära dig hur du samarbetar med gäster i ett dokument i SharePoint och OneDrive.
ms.openlocfilehash: 1a7591915efa82f1995ce2789e181dc350cd3784
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357788"
---
# <a name="collaborate-with-guests-on-a-document"></a>Samar beta med gäster i ett dokument

Om du behöver samar beta med personer utanför organisationen för dokument i SharePoint eller OneDrive kan du skicka en delnings länk till dokumentet. I den här artikeln går vi igenom de Microsoft 365-inställningar som krävs för att konfigurera delnings Länkar för SharePoint och OneDrive för organisationen.

## <a name="video-demonstration"></a>Videodemonstration

I den här videon visas de konfigurations steg som beskrivs i det här dokumentet.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a>Inställningar för Azure organisations relationer

Delning i Microsoft 365 regleras på högsta nivå av [organisations Relations inställningarna i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations). Om gäst delning är inaktiverat eller begränsat i Azure AD åsidosätter detta eventuella delnings inställningar som du konfigurerar i Microsoft 365.

Kontrol lera inställningarna för organisations relationer för att säkerställa att delning med gäster inte blockeras.

![Skärmbild av sidan med inställningar för organisationsrelationer i Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Så här anger du inställningar för organisations relationer

1. Logga in på Microsoft Azure på [https://portal.azure.com](https://portal.azure.com) .
2. I det vänstra navigerings fältet klickar du på **Azure Active Directory**.
3. I fönstret **Översikt** klickar du på **organisations relationer**.
4. Klicka på **Inställningar**i fönstret **organisations relationer** .
5. Kontrol lera att **Administratörer och användare i rollen för att bjuda in gäst kan bjuda** in och **medlemmar kan bjuda** in till **Ja**.
6. Om du har gjort ändringar klickar du på **Spara**.

Observera inställningarna i avsnittet **samarbets begränsningar** . Kontrol lera att domänerna för de gäster som du vill samar beta med inte är blockerade.

Om du arbetar med gäster från flera organisationer kan det vara bra att begränsa deras möjligheter att komma åt katalog data. Detta hindrar dem från att se vem som är gäst i katalogen. För att göra det, under **gäst användares restriktioner**, väljer du **gäst användare har begränsad åtkomst till egenskaper och medlemskap i inställningar för katalog objekt** eller **gäst användares åtkomst är begränsad till egenskaper och medlemskap i deras egna katalog objekt**.

## <a name="sharepoint-organization-level-sharing-settings"></a>Delnings inställningar för SharePoint-organisationnivå

För att personer utanför din organisation ska ha till gång till ett dokument i SharePoint eller OneDrive måste delnings inställningarna för SharePoint och OneDrive tillåta delning med personer utanför organisationen.

Inställningarna på organisations nivå för SharePoint avgör vilka inställningar som är tillgängliga för enskilda SharePoint-webbplatser. Webbplats inställningarna kan inte vara mer tillåtna än inställningarna på organisations nivå. Inställningen på organisations nivå för OneDrive bestämmer vilken delnings nivå som är tillgänglig i användarnas OneDrive-bibliotek.

Om du vill tillåta icke verifierade fil-och mappdelning för SharePoint och OneDrive väljer du **vem som helst**. Om du vill vara säker på att personer utanför din organisation måste autentisera, väljer du **nytt och befintligt gäster**. *Alla* länkar är det enklaste sättet att dela: personer utanför din organisation kan öppna länken utan att det är möjligt att överföra den till andra.

För SharePoint väljer du den mest krävda inställning som behövs av någon webbplats i organisationen.

![Skärmbild av delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)


Så här anger du delnings inställningar för SharePoint-organisationnivå

1. Klicka på **SharePoint**i det vänstra navigerings fältet **i administrations**centret för Microsoft 365.
2. I navigeringsfönstret till vänster i administrationscentret för SharePoint klickar du på **Delning**.
3. Kontrol lera att extern delning för SharePoint eller OneDrive är inställt på **vem som helst** eller **nya och befintliga gäster**. (Observera att OneDrive-inställningen inte kan bli mer tillåtna än SharePoint-inställningen.)
4. Om du har gjort ändringar klickar du på **Spara**.

## <a name="sharepoint-organization-level-default-link-settings"></a>Standardinställningar för inställningar för SharePoint-organisations nivå

Standardinställningen för fil-och mappikonen bestämmer vilken länk som visas som standard för användaren när de delar en fil eller mapp. Användare kan ändra länktyp till något av de andra alternativen innan de delas om så önskas.

Tänk på att den här inställningen påverkar SharePoint-webbplatser i din organisation samt OneDrive.

Välj den typ av länk som är markerad som standard när användarna delar filer och mappar:

- **Vem som helst med länken** – Välj det här alternativet om du förväntar dig att göra mängder av overifierade fil-och mappdelning. Om du vill tillåta *alla* länkar, men är bekymrad över oavsiktlig autentisering, bör du överväga något av de andra alternativen som standard. Den här länk typen är bara tillgänglig om du har aktiverat **någon** delning.
- **Endast personer i organisationen** – Välj det här alternativet om du tror att de flesta fil-och mappdelning är med i din organisation.
- **Vissa personer** -Överväg det här alternativet om du förväntar dig att göra många fil-och mappdelning med gästerna. Den här typen av länk fungerar med gäster och kräver att de autentiseras.
 
![Skärmbild av delningsinställningar för filer och mappar för SharePoint på organisationsnivå](../media/sharepoint-organization-files-folders-sharing-settings.png)


Så här anger du inställningar för SharePoint-och OneDrive-organisations nivå

1. Gå till sidan delning i administrations centret för SharePoint.
2. Under **fil-och mappaktiviteter**väljer du den standard delnings länk som du vill använda.
3. Om du har gjort ändringar klickar du på **Spara**.

## <a name="sharepoint-site-level-sharing-settings"></a>Delnings inställningar för SharePoint-webbplats nivå

Om du delar filer och mappar på en SharePoint-webbplats måste du också kontrol lera delnings inställningarna för webbplatsen på webbplats nivå.

![Skärmbild av inställningar för extern delning för SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Ange delnings inställningar på webbplats nivå
1. I navigeringsfönstret till vänster i administrationscentret för SharePoint expanderar du **Webbplatser** och klickar på **Aktiva webbplatser**.
2. Välj den webbplats du just har skapat.
3. Klicka på **Delning** i menyfliksområdet.
4. Kontrol lera att delning är inställt på **vem som helst** eller **nya och befintliga gäster**.
5. Om du har gjort ändringar klickar du på **Spara**.

## <a name="invite-users"></a>Bjuda in användare

Inställningar för gäst delning är nu konfigurerade så att användarna kan nu dela filer och mappar med personer utanför organisationen. Mer information finns i [dela OneDrive-filer och-mappar](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) och [dela SharePoint-filer eller-mappar](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) .

## <a name="see-also"></a>Se även

[Metodtips för att dela filer och mappar med oautentiserade användare](best-practices-anonymous-sharing.md)

[Begränsa oavsiktlig exponering för filer när de delas med gäster](share-limit-accidental-exposure.md)

[SharePoint och OneDrive-integrering med Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)