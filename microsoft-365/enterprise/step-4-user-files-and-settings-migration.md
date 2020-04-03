---
title: Steg 4 – Migrering av användares filer och inställningar
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 06/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Läs hur du migrerar användarnas filer och inställningar.
ms.openlocfilehash: f17b11efe889359f97087ac5d96ffa968ca8cd88
ms.sourcegitcommit: 9ca28ae8f7804eb488cf76ca4b09fe88787e0a49
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "43113547"
---
# <a name="step-4-user-files-and-settings-migration"></a>Steg 4: Migrering av användares filer och inställningar

Att flytta användarnas filer och inställningar till de nya eller uppdaterade datorerna är en kritisk process, och att misslyckas är inte ett alternativ. Du kan migrera varje dator manuellt eller välja något av flera olika sätt att automatisera processen. Oavsett vilken metod du väljer för migreringen finns det tre huvudsakliga överväganden som ska hanteras – överföringen av användarnas filer, deras inställningar och hantering av layouterna för Start och aktivitetsfältet i Windows 10.

![](../media/step-4-user-files-and-settings-migration-media/step-4-user-files-and-settings-migration-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-7.png" alt="Step 4" height="135" width="135" /></td>
<td><p><strong>Steg 4: Användares filer och inställningar</strong></p>
<p>När du uppdaterar eller ersätter datorer kan du spara tid genom att automatisera säkerhetskopiering och återställning av användartillstånd. Med nya alternativ för filsynkronisering i molnet kan du framtvinga användarbaserad synkronisering av mapparna Skrivbord, Dokument och Bilder till OneDrive för smidig filåtkomst från nya Windows-installationer.</p></td>
<td><a href="https://aka.ms/ddev4" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-17.png" alt="Step 4" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Även om du kan fortsätta att använda migreringsprocesser som du har använt tidigare, rekommenderar vi att du med bytet till Office 365 ProPlus använder Flytt av känd mapp i OneDrive (se nedan). Om du vill se en fullständig skrivbordsdistribution kan du besöka [Center för skrivbordsdistribution](https://aka.ms/HowToShift).
>

Ett av de krångligaste och ofta mest manuella uppgifterna i en storskalig distribution är överföringen av användarnas filer och inställningar. I den här artikeln går vi igenom de alternativ som är tillgängliga för att migrera användarna till nya, uppdaterade och speglade datorer.

## <a name="manual-migration"></a>Manuell migrering

När det gäller att bestämma vad som ska behållas vid en flytt till en ny dator eller en ny version av Windows vill vissa användare kanske behålla allt medan andra ser en möjlighet att rensa sina enheter. Därför väljer vissa IT-avdelningar att hantera migreringen av användarfiler manuellt. Ibland genom att supportteam besöker användarna, ibland genom att sätta upp supportcentra där användarna tar med sig sin dator till supportteamet. Vilket sätt du än väljer kan användarna involveras i vad som ska överföras och vad som ska tas bort.

Om det här är ett alternativ för din organisation beror på vilken skala på migreringen du planerar. Det begränsas förstås av den tid och insats som behövs för att arbeta direkt med användarna, att förstå deras behov och kopiera filer till en ny eller uppdaterad dator.

Om du väljer en manuell migrering kan du överväga att använda ett av alternativen nedan eller be om hjälp.

## <a name="automated-migration-using-usmt"></a>Automatiserad migrering med USMT 

För storskaliga distributioner kan du automatisera en stor del av processen med uppgiftsverktyg för sekvensbaserad distributionsautomation, t.ex. Microsoft Endpoint Configuration Manager eller Microsoft Deployment Toolkit (MDT). Båda dessa lösningar använder User State Migration Tool (USMT) som en del av processen för distribution från slutpunkt till slutpunkt. USMT är en del av [Windows Assessment and Deployment Kit (Windows ADK)](https://docs.microsoft.com/windows-hardware/get-started/adk-install)

USMT fångar användarkonton, användarfiler, operativsysteminställningar samt programinställningar och migrerar dem till en ny Windows-installation. Det ger också dig som IT-administratör kontroll på exakt vad som migreras och du kan eventuellt utesluta oönskade filtyper, till exempel ljud- och videofiler, eller körbara filer.

Under migreringsprocessen måste du ha tillräcklig serverlagringskapacitet tillgänglig för att fungera som ett tillfälligt migreringsarkiv. För detta har USMT två viktiga funktioner. För det första kan den beräkna, per dator, hur mycket lagringsutrymme du behöver. För det andra kan migreringsarkiv krypteras, vilket minskar risken för att data blir komprometterade när de lagras på filservrar.

När du utför en datoruppdatering och inte omformaterar den primära Windows-partitionen kan du även välja att använda ett migreringsarkiv med hård länk med USMT. Med den här processen bevaras användartillståndet på datorn medan det gamla operativsystemet och apparna tas bort och uppdateras. När återställningsprocessen kommer från samma lokala partition ger det här alternativet betydande förbättringar av prestanda och minskar nätverkstrafiken.

[Översikt över User State Migration Tool (USMT)](https://docs.microsoft.com/windows/deployment/usmt/usmt-overview)

## <a name="onedrive-known-folder-move"></a>Flytt av känd mapp i OneDrive

Om användarna finns på OneDrive eller om du lägger till OneDrive som en del av den här distributionen finns det ett nytt alternativ. När du använder molnet för att synkronisera användarfiler ger funktionen ”Flytt av känd mapp” i OneDrive dig flexibilitet som inte är möjlig med lokala nätverksbaserade alternativ för filmigrering. Om den aktiveras före migreringen ger den säker åtkomst till nya eller uppdaterade datorer och eliminerar behovet av att skapa tillfälliga migreringsarkiv på dina egna servrar. Det kan också vara helt transparent för användaren.

[Dirigera om och flytta kända Windows-mappar till OneDrive](https://docs.microsoft.com/onedrive/redirect-known-folders)

Om du redan använder OneDrive vet du att användarna kan välja vilka mappar och platser de vill synkronisera från OneDrive eller SharePoint till sin enhet, men det gör att slutanvändaren måste göra jobbet med att konfigurera detta. Med Flytt av känd mapp kan du ange mapparna Dokument, Skrivbord och Bilder i en användarprofil och skydda allt på OneDrive. En användare kan göra detta själv eller, vilket är viktigt i det här scenariot, du kan [tvinga fram detta med inställningar för en grupprincip](https://docs.microsoft.com/onedrive/use-group-policy?redirectSourcePath=%252fen-us%252farticle%252fUse-Group-Policy-to-control-OneDrive-sync-client-settings-0ecb2cf5-8882-42b3-a6e9-be6bda30899c).

Med Flytt av känd mapp ändras inte användarnas arbetsflöde – allt ser likadant ut innan, under och efter att synkroniseringen med OneDrive har slutförts. Via en grupprincip kan du även välja om du vill meddela användarna att deras dokument, bilder och skrivbord skyddas i OneDrive. Om du väljer att inte göra det sker allt tyst i bakgrunden. Användarna märker det bara när de tar emot en ny dator eller att deras dator uppdateras. Så snart de har loggat in på OneDrive-kontot är filerna tillgängliga igen och återställs till deras nya dator. Dessutom innebär OneDrive att de också kommer åt sina filer säkert när som helst från sina telefoner och andra enheter.

Autentisering för OneDrive drivs av Azure Active Directory, så för extra säkerhet kan du enkelt aktivera multifaktorautentisering, och du kan ställa in principer för att styra bandbredden för uppladdning och nedladdning som OneDrive använder för att begränsa nätverksaktiviteten.

Du behöver inte migrera all användning samtidigt. Du kanske vill dela upp lanseringen av grupprincipinställningarna, eller [begränsa filsynkronisering till domänanslutna datorer](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenantSyncClientRestriction?view=sharepoint-ps).

## <a name="start-menu-and-task-bar-customization"></a>Anpassning av Start-menyn och aktivitetsfältet

OneDrive är utformat för att synkronisera och skydda filer och mappar, den synkroniserar inte program- eller Windows-inställningar. Om du gjort detta tidigare kanske du har använt metoden med att kopiera profilen för att konfigurera standardlayouter för användarnas Start-menyer och inställningar i aktivitetsfältet. I Windows 10 Pro, Enterprise och Education kan du använda grupprincip, MDM, PowerShell eller konfigurationspaket för att distribuera [anpassade Start- och aktivitetsfältlayouter](https://docs.microsoft.com/windows/configuration/windows-10-start-layout-options-and-policies). Ingen spegling krävs och layouten kan uppdateras genom att skriva över den XML-fil som innehåller layouten.

Om du vill skapa en ny layout konfigurerar du bara ett exempelsystem och använder PowerShell [Export-StartLayout](https://docs.microsoft.com/powershell/module/startlayout/export-startlayout?view=win10-ps)-cmdleten för att generera en XML-fil, placerar denna fil på en nätverksresurs eller lagrar den lokalt som en del av din distributionssekvens. Den behöver bara gå att nå som skrivskyddad fil när användaren loggar in. Du kan sedan använda en princip eller [Import-StartLayout](https://docs.microsoft.com/powershell/module/startlayout/import-startlayout?view=win10-ps)-cmdleten för att referera till den här filen.

## <a name="removing-unwanted-in-box-apps"></a>Ta bort oönskade medföljande appar

Windows 10 innehåller många användbara inbyggda appar som en del av standardinstallationen, men du kanske vill ta bort några av dem från de hanterade datorerna och konfigurera installationen för att förhindra att apparna kommer tillbaka, t.ex. XBOX eller Zune Music. Du kan hämta en lista över de här apparna med hjälp av kommandona [PowerShell Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx) och ta bort dem som du inte vill använda med kommandot [Remove-AppxPackage](https://technet.microsoft.com/library/hh856038.aspx). Alternativt kan du montera filen Windows Image (.img) offline före distributionen och extrahera paket som du inte vill ha med kommandoradsverktyget [Deployment Image Servicing and Management (DISM)](https://docs.microsoft.com/windows-hardware/manufacture/desktop/what-is-dism) och kommandot [Remove-AppxProvisionedPackage](https://docs.microsoft.com/powershell/module/dism/remove-appxprovisionedpackage?view=win10-ps).

## <a name="next-step"></a>Nästa steg

## <a name="step-5-security-and-compliance-considerations"></a>[Steg 5: Överväganden för säkerhet och efterlevnad](https://aka.ms/mdd5)

## <a name="previous-step"></a>Föregående steg

## <a name="step-3-office-and-lob-app-delivery"></a>[Steg 3: Leverans av Office och verksamhetsspecifika appar](https://aka.ms/mdd3)
