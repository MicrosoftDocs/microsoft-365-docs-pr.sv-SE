---
title: Konfigurera S/MIME-inställningar – Exchange Online för Outlook på webben
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: En kort beskrivning av vad Exchange Online-administratörer behöver göra för att visa och konfigurera S/MIME-inställningarna i Outlook på webben i Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b9f4e6c33369640ad66956568959dd02b01c4fb9
ms.sourcegitcommit: df59c83174d845b8ddec48b9be2659fbfb58bb7f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/29/2020
ms.locfileid: "46517491"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Konfigurera S/MIME-inställningar i Exchange Online för Outlook på webben

Som administratör för Exchange Online kan du konfigurera Outlook på webben (tidigare kallat Outlook Web App) så att s/mime-skyddade meddelanden kan skickas och ta emot. Använd cmdletsna **Get-SmimeConfig** och **Set-SmimeConfig** för att visa och hantera den här funktionen i Exchange Online PowerShell. Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

Detaljerad syntax- och parameterinformation finns i [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) och [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Överväganden för nya Microsoft Edge (Krom-baserade)

Om du vill använda S/MIME i Outlook på webben i den nya [microsoft edge-webbläsaren](https://www.microsoft.com/windows/microsoft-edge) måste du (eller en annan administratör) ange och konfigurera microsoft edge-webbläsarprincipen **ExtensionInstallForcelist** för att installera Microsoft S/MIME-tillägget i den nya Microsoft Edge. Principvärdet är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Och observera att tillämpa den här principen kräver domänanslutna eller Azure AD-anslutna enheter, så att använda S/MIME i den nya Microsoft Edge-webbläsaren kräver effektivt domänanslutna eller Azure AD-anslutna enheter.

Mer information om principen **ExtensionInstallForcelist** finns i [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).

Det här steget är en förutsättning för att använda nya Microsoft Edge. Den ersätter inte S/MIME-kontrollen som installeras av användare. Användare uppmanas att hämta och installera S/MIME-kontrollen i Outlook på webben under sin första användning av S/MIME. Eller, användare kan proaktivt gå till **S / MIME** i sin Outlook på webben inställningar för att få nedladdningslänken för kontrollen.

## <a name="considerations-for-chrome"></a>Överväganden för Chrome

Om du vill använda S/MIME i Outlook på webben i webbläsaren Google Chrome måste du (eller en annan administratör) ställa in och konfigurera Chromium-principen **ExtensionInstallForcelist** för att installera Microsoft S/MIME-tillägget i Chrome. Principvärdet är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Och observera att tillämpa denna princip kräver domän-anslutna datorer, så att använda S / MIME i Chrome effektivt kräver domän-anslutna datorer.

Mer information om principen **ExtensionInstallForcelist** finns i [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).

Det här steget är en förutsättning för att använda Chrome. Den ersätter inte S/MIME-kontrollen som installeras av användare. Användare uppmanas att hämta och installera S/MIME-kontrollen i Outlook på webben under sin första användning av S/MIME. Eller, användare kan proaktivt gå till **S / MIME** i sin Outlook på webben inställningar för att få nedladdningslänken för kontrollen.

## <a name="for-more-information"></a>Mer information

[S/MIME för signering och kryptering av meddelanden](s-mime-for-message-signing-and-encryption.md)
