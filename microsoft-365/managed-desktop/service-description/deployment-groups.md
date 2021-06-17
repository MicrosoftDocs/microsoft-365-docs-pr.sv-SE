---
title: Grupper för enhetsdistribution
description: Distributionsgrupper som används för att hantera uppdateringar och andra ändringar
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2d1f2325937488b95c40600f277835cca1329d1e
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985654"
---
# <a name="device-deployment-groups"></a>Grupper för enhetsdistribution

Microsoft Hanterat skrivbord använder distributionsgrupper för att hantera utgivningen av uppdateringar och konfigurationsändringar på enheter. Enheter läggs till i distributionsgrupper ("ringar" eller "uppdateringsgrupper") automatiskt när de registreras i Microsoft Hanterat skrivbord. Distributionsgrupper tillåter att enheter tar emot ändringar på en fasad tidslinje.

Du kanske vill tilldela vissa enheter endast i testsyfte eller utse specifika tidiga användare som ska få ändringarna först. Om du har kritiska enheter som de som används av chefer eller som använder verksamhetskritiska funktioner, kan du behålla dem i den grupp som får uppdateringar efter den långsammaste takten. Microsoft Hanterat skrivbord du ange att en enhet ska vara kvar i någon av följande grupper.

- **Test:** Bäst för enheter som används för testning eller användare som kan använda upprepade ändringar och exponering för nya funktioner och även ge tidig feedback. Den här gruppen får ofta ändringar och upplevelser i den här gruppen har en stark effekt. Testgruppen är undantagen från alla fastställda servicenivåavtal och användarsupport. Det är bäst att flytta bara några enheter i början och sedan kontrollera användarupplevelsen. Microsoft Hanterat skrivbord tilldelar inte automatiskt enheter till den här gruppen. det kommer bara att innehålla enheter som du anger.
- **Första**: perfekt för tidiga användare, frivilliga eller utsedda validerare, IT-proffs eller representanter för affärsfunktioner, det vill säga personer som kan validera ändringar och ge dig feedback på upplevelsen.
- **Bred** tar emot ändringar sist. Oftast finns de flesta i organisationen i den här gruppen. Du kan också ange enheter som måste finnas i den här gruppen och bara ska få ändringar sist eftersom de utför verksamhetskritiska funktioner eller tillhör användare i kritiska roller. 
- **Automatiskt:** Välj det här alternativet om du vill Microsoft Hanterat skrivbord att automatiskt tilldela enheter till någon av de andra grupperna. (Vi tilldelar inte automatiskt enheter till test.) Om du vill släppa en enhet som du tidigare har angett så att den kan tilldelas automatiskt igen väljer du det här alternativet. 

Microsoft Hanterat skrivbord använder några ytterligare grupper för att styra distributioner, men du kan inte tilldela enheter till dem. Du kan däremot flytta enheter från dessa grupper till någon av grupperna i den här artikeln. Mer information om hur Windows hanteras i grupper finns i [Hur uppdateringar hanteras i Microsoft Hanterat skrivbord.](updates.md)

Om en enhet finns i en grupp som du har angett står **det Grupp tilldelat av** som **administratör.** Om Microsoft Hanterat skrivbord har tilldelat gruppen visas **automatiskt**. När en enhet flyttas till en grupp står det **Väntande**. I **fältet** Grupp visas alltid den grupp enheten befinner sig i och bara uppdateras när flyttningen är slutförd.

> [!IMPORTANT]
> Försök inte direkt ändra medlemskapet i de här grupperna. Följ alltid anvisningarna som beskrivs [i Tilldela enheter till en distributionsgrupp.](../working-with-managed-desktop/assign-deployment-group.md)
