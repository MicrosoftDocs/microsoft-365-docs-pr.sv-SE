---
title: Arbeta med Microsoft Consulting Services
description: förberedelser och anvisningar för att följa för att arbeta med MCS för att paketera dina appar
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation, appar, MCS, packning
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f8c4e427c536577ea2fc768d4930b9d4db6ac697
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841429"
---
# <a name="working-with-microsoft-consulting-services"></a>Arbeta med Microsoft Consulting Services

Du kan delta i Microsoft Consulting Services (MCS) för att få dina appar paketerade för användning med Microsoft Managed Desktop. Mer detaljerad information finns i arbeta med konto representanten för att kontakta MCS och räckvidd för ditt specifika program packnings projekt.

## <a name="roles-and-responsibilities"></a>Roller och ansvar

Om du vill arbeta med MCS-programpaketet **måste du tillhandahålla följande element**:

- Installations program för källfiler (till exempel setup.exe eller. msi).
- Installations anvisningar, med information om hur den slutliga installationen ska se ut. Om det till exempel finns en genväg till programmet? Vad bör appens synlighet vara? Ska programmet ansluta till en server och om så är fallet, vilken? Mer information finns i [mallen för begäran om program packning](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).
- Du måste utföra dina egna godkännande test för att verifiera att programmet fungerar när du behöver det i din miljö.

**MCS kommer att vidta dessa åtgärder:**

- Kontrollerar om programmet är förbjudet eller begränsat i Microsoft Managed Desktop Environment.
- Att testa installation, start och avinstallation av appen för att säkerställa kompatibilitet med Windows 10. Om MCS upptäcker ett kompatibilitetsproblem kan de lämna in appen till [Skriv bords](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) programmet för att säkerställa att programmet är åtgärdat.
- Paketera programmet i din specifikation och testa sedan program distributionen med hjälp av Microsoft Intune.

## <a name="app-delivery-schedule"></a>Program leverans schema

Starta packningen genom att överföra program informationen till Microsoft Managed Desktop-portalen. Förpacknings gruppen granskar nya inlämningar varje torsdag. När du har granskat och paketerat levereras de paketerade apparna följande fredag: Det går att paketera upp till fem appar per vecka, men tjänsten kan anpassas efter dina behov.

![kalender som visar hur programmet inflödar på en torsdag (tjugoförsta i det här exemplet), media verifiering nästa dag, paket för följande måndag (25) och program leverans på nästa fredag (29)](../../media/MCS-cal.png)

Du får ett meddelande när appen har levererats. Då har vi 21 dagar på dig för att testa och godkänna arbetet på Microsoft Managed Desktop-portalen. Om du upptäcker problem med appen under godkännande testningen kan du avvisa programmet på Microsoft Managed Desktop-portalen och du kommer att vara ansluten via e-post med en MCS-paketerare för att förstå och lösa problemet.

## <a name="testing-accounts-and-environment"></a>Testa konton och miljö

För att förpacknings gruppen ska kunna slutföra migreringen till Microsoft Intune rekommenderar vi att du ger vissa behörigheter:
 
-   Åtkomst till Microsoft Intune-funktioner för program distribution för att Paketeraren ska kunna lägga till och tilldela programmet 
-   Testa grupper, användar konton och licenser för paketen för att kunna testa apparna

MCS använder dessa behörigheter för att utföra följande åtgärder:
 
-   Kontrol lera att programmet fungerar på en virtuell dator konfigurerad för Microsoft Managed Desktop
-   Ladda upp appen till Microsoft Intune för distribution till dina användare

Utan dessa behörigheter är det möjligt för MCS att gå vidare, men de kommer inte att kunna ladda upp program till din miljö.


