---
title: Använd regler för e-postflöde för att se vad användarna rapporterar till Microsoft
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Du kan skapa en Exchange-flödesregel för att förhindra att användarna skickar e-postmeddelanden till Microsoft för analys och använder dem i dina egna säkerhetsprocesser
ms.openlocfilehash: ae8655416840dc326344e2c2aea7c67486389492
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806033"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Använd regler för e-postflöde för att se vad användarna rapporterar till Microsoft

Det finns flera sätt att skicka falska positiva och falska negativa meddelanden till Microsoft för analys. Som administratör kan du använda regler för e-postflöde för att se vad användarna rapporterar till Microsoft som skräppost, icke-skräppost och nätfiskebedrägerier. Mer information finns i [Skicka meddelanden om skräppost, icke-skräppost och nätfisketill Microsoft för analys](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). Omvänt kan du skapa en Exchange-flödesregel (kallas även en transportregel) för att förhindra att användarna skickar e-postmeddelanden till Microsoft för analys och använder dem i dina egna säkerhetsprocesser.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

Beräknad tid att slutföra: 5 minuter

Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Mer information om vilka behörigheter du behöver finns i postposterna "E-postflöde" och "Outlook på webbpostlådeprinciperna" i [Exchange Online-behörigheter](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).

Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns i [Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a>Använd EAC för att skapa en e-postflödesregel för att visa användarnas manuella skräppost, nätfiske och inte skräppostrapporter

1. Navigera till regler för **e-postflöde** \> **i**EAC.

2. Klicka ![på](../../media/ITPro-EAC-AddIcon.gif) Lägg till ikon och välj sedan **Skapa en ny regel**.

3. Ge regeln ett namn och klicka sedan på **Fler alternativ**.

4. Under **Använd den här regeln om**väljer du **Mottagaren** och väljer sedan adress innehåller något av **dessa ord**.

5. Gör följande steg i rutan **Ange ord eller fraser:**

   - Skriv `abuse@messaging.microsoft.com`, klicka](../../media/ITPro-EAC-AddIcon.gif)på `junk@office365.microsoft.com` **Lägg till** ![lägg](../../media/ITPro-EAC-AddIcon.gif)till ikon, skriv och klicka sedan på Lägg **till** ![ikon . Dessa e-postadresser används för att skicka falska negativa meddelanden till Microsoft.

   - Skriv `phish@office365.microsoft.com` och klicka sedan](../../media/ITPro-EAC-AddIcon.gif)på Lägg **till** ![lägg till ikon . Den här e-postadressen används för att skicka missade nätfiskemeddelanden till Microsoft.

   - Skriv `false_positive@messaging.microsoft.com`, klicka](../../media/ITPro-EAC-AddIcon.gif)på `not_junk@office365.microsoft.com` **Lägg till** ![ikonen,](../../media/ITPro-EAC-AddIcon.gif)skriv och klicka sedan på Lägg **till** ![ikonen . Dessa e-postadresser används för att skicka falska positiva meddelanden till Microsoft.

   - Klicka på **OK**.

6. Under **Gör följande**väljer du Hemlig kopia av meddelandet **till...** och väljer sedan de postlådor där du vill ta emot meddelandena.

7. Om du vill kan du göra val för att granska regeln, testa regeln, aktivera regeln under en viss tidsperiod och andra val. Vi rekommenderar att du testar regeln under en period innan du tillämpar den. Se [Regler för e-postflöde](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).

8. Klicka på **spara-knappen** för att spara regeln. Den visas i listan över regler.

När du har skapat och tillämpat regeln kopieras alla meddelanden som skickas från din organisation till angivna e-postadresser till den angivna postlådan.
