---
title: Serviceförändringar och kommunikation
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 00d1cb409364c017585c6afcd10a236ecbcdc3a0
ms.sourcegitcommit: 53148fc3663bdcfa9605684317785cb19f37e141
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2019
ms.locfileid: "42810616"
---
# <a name="service-changes-and-communication"></a>Serviceförändringar och kommunikation

Ibland kan Microsoft behöva ändra information om hur Microsoft Managed Desktop fungerar. På samma sätt kan du behöva göra ändringar som också påverkar tjänsten. Vi hanterar sådana förändringar på olika sätt beroende på hur betydande de är. Det här avsnittet definierar de ändringar vi anser vara stora och förklarar hur vi hanterar dem jämfört med andra ändringar.



## <a name="changes-made-by-microsoft"></a>Ändringar som gjorts av Microsoft

Vi kommer att meddela dig minst 30 dagar i förväg för alla större förändringar som kräver åtgärder. Vi meddelar dig med hjälp av portalmeddelandesystemet för Microsoft Managed Desktop Admin.

**Stora förändringar** är de som kan påverka något av dessa områden:
- Förändringar som påverkar den dagliga produktiviteten
- Ändringar i anpassade funktioner och program
- Öka eller minska synlig kapacitet
- Ändringar i produktvarumärkesmärkning som kan orsaka förvirring eller förändring av helpdesk-processer och referensmaterial eller webbadresser
- Ändringar som kräver behörigheter utöver dem som krävs av tjänsten för dagliga åtgärder, med undantag för åtgärder som förhindrar eller åtgärdar problem
- Ändringar i var dina data lagras
- Lägga till en ny komponenttjänst eller ett nytt program i tjänstens omfattning
- Borttagning av en komponenttjänst eller ett program från tjänstens omfattning
- Lägga till ny funktion i tjänsten

> [!NOTE]
> Vi kanske måste göra ändringar för att minska incidenter eller säkerhetsproblem som skulle uteslutas från 30-dagars meddelandeprincipen.

Vi gör rutinmässigt andra ändringar i tjänsten för att förbättra användarupplevelsen, säkerheten, tillförlitligheten och rapporteringen. Några exempel på dessa ändringar är:

- Installation av Windows- och Office-uppdateringar
- Uppdateringar av säkerhetsbaslinjen som tillämpas på enheter
- [Enheter som stöds](device-list.md)

Vi kommunicerar dessa ändringar med hjälp av etablerade kanaler. Om du har några frågor om eventuella ändringar kontaktar du Microsoft Managed Desktop [Operations-teamet](../working-with-managed-desktop/admin-support.md). Ändringar i tjänsten dokumenteras också efter behov i [ändringshistoriken](../change-history-managed-desktop.md).

Ändringar och kommunikation för Microsoft Managed Desktop styrs av två Microsoft-principer:
- [Modern livscykelpolicy](https://support.microsoft.com/help/30881/modern-lifecycle-policy)
- [Microsoft 365 Ändra kommunikationspolicy](https://docs.microsoft.com/office365/admin/manage/message-center?redirectSourcePath=%252fen-us%252farticle%252fMessage-center-in-Office-365-38FB3333-BFCC-4340-A37B-DEDA509C2093&view=o365-worldwide)

## <a name="changes-you-make"></a>Ändringar du gör

Vissa ändringar som du kan göra i din miljö kan påverka Microsoft Managed Desktop. För dessa större ändringar ber vi dig att meddela oss minst 30 dagar genom att skicka en servicebegäran i Microsoft Managed Desktop Admin-portalen. Mer information [finns i Administratörssupport för Microsoft Managed Desktop.](../working-with-managed-desktop/admin-support.md) Detta ger oss tillräckligt med tid att planera och förbereda oss för förändringen för att undvika störningar.

Stora förändringar är de som kan påverka något av dessa områden:

- Identitetssystem och grupper
- Nätverks- och nätverkskontroller som brandväggar, proxy- eller cachelagring och VPN-system
- Kontroller för åtkomst till molntjänstkonfigurationer
- Användar- eller enhetscertifikat som används för identitet eller säkring av nätverkstjänster
- Hanteringssystem som interagerar med tjänsten
- Säkerhetssystem eller agenter som interagerar med tjänsten
- Konfiguration av någon av Microsoft 365-molntjänsterna som är associerade med eller används av tjänsten

Dessa förändringar är inte sannolikt att störande, så du behöver inte låta oss veta om dem i förväg:

- Rensning av överblivna objekt
- Lägga till eller ta bort användare från tjänsten
- Konfiguration av system som inte har någon väsentlig inverkan på leveransen av Microsoft Managed Desktop
- Programversionsuppdateringar, med undantag för VPN- eller proxyprogram


