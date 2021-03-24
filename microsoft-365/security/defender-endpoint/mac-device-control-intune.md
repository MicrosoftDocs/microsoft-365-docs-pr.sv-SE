---
title: Exempel på principer för enhetskontroll för Intune
description: Lär dig hur du använder principer för enhetskontroll med exempel som kan användas med Intune.
keywords: microsoft, defender, atp, mac, enhet, kontroll, usb, flyttbart, media, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f007364fb1bc5ccb2ef671a344bbb04b7912174b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072161"
---
# <a name="examples-of-device-control-policies-for-intune"></a><span data-ttu-id="0b176-104">Exempel på principer för enhetskontroll för Intune</span><span class="sxs-lookup"><span data-stu-id="0b176-104">Examples of device control policies for Intune</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0b176-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="0b176-105">**Applies to:**</span></span>
- [<span data-ttu-id="0b176-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="0b176-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="0b176-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b176-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0b176-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="0b176-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0b176-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="0b176-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="0b176-110">Det här dokumentet innehåller exempel på principer för enhetskontroll som du kan anpassa för din egen organisation.</span><span class="sxs-lookup"><span data-stu-id="0b176-110">This document contains examples of device control policies that you can customize for your own organization.</span></span> <span data-ttu-id="0b176-111">De här exemplen gäller om du använder Intune för att hantera enheter i ditt företag.</span><span class="sxs-lookup"><span data-stu-id="0b176-111">These examples are applicable if you are using Intune to manage devices in your enterprise.</span></span>

## <a name="restrict-access-to-all-removable-media"></a><span data-ttu-id="0b176-112">Begränsa åtkomsten till alla flyttbara medium</span><span class="sxs-lookup"><span data-stu-id="0b176-112">Restrict access to all removable media</span></span>

<span data-ttu-id="0b176-113">I följande exempel begränsas åtkomsten till alla flyttbara medium.</span><span class="sxs-lookup"><span data-stu-id="0b176-113">The following example restricts access to all removable media.</span></span> <span data-ttu-id="0b176-114">Observera den behörighet som tillämpas på den högsta nivån i `none` principen, vilket innebär att alla filåtgärder inte kommer att gälla.</span><span class="sxs-lookup"><span data-stu-id="0b176-114">Note the `none` permission that is applied at the top level of the policy, meaning that all file operations will be disallowed.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1"> 
    <dict> 
        <key>PayloadUUID</key> 
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string> 
        <key>PayloadType</key> 
        <string>Configuration</string> 
        <key>PayloadOrganization</key> 
        <string>Microsoft</string> 
        <key>PayloadIdentifier</key> 
        <string>com.microsoft.wdav</string> 
        <key>PayloadDisplayName</key> 
        <string>Microsoft Defender ATP settings</string> 
        <key>PayloadDescription</key> 
        <string>Microsoft Defender ATP configuration settings</string> 
        <key>PayloadVersion</key> 
        <integer>1</integer> 
        <key>PayloadEnabled</key> 
        <true/> 
        <key>PayloadRemovalDisallowed</key> 
        <true/> 
        <key>PayloadScope</key> 
        <string>System</string> 
        <key>PayloadContent</key> 
        <array> 
            <dict> 
                <key>PayloadUUID</key> 
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string> 
                <key>PayloadType</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadOrganization</key> 
                <string>Microsoft</string> 
                <key>PayloadIdentifier</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadDisplayName</key> 
                <string>Microsoft Defender ATP configuration settings</string> 
                <key>PayloadDescription</key> 
                <string/> 
                <key>PayloadVersion</key> 
                <integer>1</integer> 
                <key>PayloadEnabled</key> 
                <true/> 
                <key>deviceControl</key> 
                <dict> 
                    <key>removableMediaPolicy</key> 
                    <dict> 
                        <key>enforcementLevel</key> 
                        <string>block</string> 
                        <key>permission</key> 
                        <array> 
                            <string>none</string> 
                        </array> 
                    </dict> 
                </dict>
            </dict> 
        </array> 
    </dict> 
</plist>
```

## <a name="set-all-removable-media-to-be-read-only"></a><span data-ttu-id="0b176-115">Ange att alla flyttbara medium ska vara skrivskyddade</span><span class="sxs-lookup"><span data-stu-id="0b176-115">Set all removable media to be read-only</span></span>

<span data-ttu-id="0b176-116">I följande exempel konfigureras alla flyttbara medium som skrivskyddade.</span><span class="sxs-lookup"><span data-stu-id="0b176-116">The following example configures all removable media to be read-only.</span></span> <span data-ttu-id="0b176-117">Observera att behörigheten som används på den högsta nivån i principen, vilket innebär att alla skriv- och köråtgärder inte `read` kommer att gälla.</span><span class="sxs-lookup"><span data-stu-id="0b176-117">Note the `read` permission that is applied at the top level of the policy, meaning that all write and execute operations will be disallowed.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1"> 
    <dict> 
        <key>PayloadUUID</key> 
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string> 
        <key>PayloadType</key> 
        <string>Configuration</string> 
        <key>PayloadOrganization</key> 
        <string>Microsoft</string> 
        <key>PayloadIdentifier</key> 
        <string>com.microsoft.wdav</string> 
        <key>PayloadDisplayName</key> 
        <string>Microsoft Defender ATP settings</string> 
        <key>PayloadDescription</key> 
        <string>Microsoft Defender ATP configuration settings</string> 
        <key>PayloadVersion</key> 
        <integer>1</integer> 
        <key>PayloadEnabled</key> 
        <true/> 
        <key>PayloadRemovalDisallowed</key> 
        <true/> 
        <key>PayloadScope</key> 
        <string>System</string> 
        <key>PayloadContent</key> 
        <array> 
            <dict> 
                <key>PayloadUUID</key> 
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string> 
                <key>PayloadType</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadOrganization</key> 
                <string>Microsoft</string> 
                <key>PayloadIdentifier</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadDisplayName</key> 
                <string>Microsoft Defender ATP configuration settings</string> 
                <key>PayloadDescription</key> 
                <string/> 
                <key>PayloadVersion</key> 
                <integer>1</integer> 
                <key>PayloadEnabled</key> 
                <true/> 
                <key>deviceControl</key> 
                <dict> 
                    <key>removableMediaPolicy</key> 
                    <dict> 
                        <key>enforcementLevel</key> 
                        <string>block</string> 
                        <key>permission</key> 
                        <array> 
                            <string>read</string> 
                        </array> 
                    </dict> 
                </dict>
            </dict> 
        </array> 
    </dict> 
</plist>
```

## <a name="disallow-program-execution-from-removable-media"></a><span data-ttu-id="0b176-118">Tillåta programkörning från flyttbara medium</span><span class="sxs-lookup"><span data-stu-id="0b176-118">Disallow program execution from removable media</span></span>

<span data-ttu-id="0b176-119">I följande exempel visas hur programkörning från flyttbara media inte kan förhindras.</span><span class="sxs-lookup"><span data-stu-id="0b176-119">The following example shows how program execution from removable media can be disallowed.</span></span> <span data-ttu-id="0b176-120">Observera de `read` behörigheter som tillämpas på den högsta nivån i `write` principen.</span><span class="sxs-lookup"><span data-stu-id="0b176-120">Note the `read` and `write` permissions that are applied at the top level of the policy.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1"> 
    <dict> 
        <key>PayloadUUID</key> 
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string> 
        <key>PayloadType</key> 
        <string>Configuration</string> 
        <key>PayloadOrganization</key> 
        <string>Microsoft</string> 
        <key>PayloadIdentifier</key> 
        <string>com.microsoft.wdav</string> 
        <key>PayloadDisplayName</key> 
        <string>Microsoft Defender ATP settings</string> 
        <key>PayloadDescription</key> 
        <string>Microsoft Defender ATP configuration settings</string> 
        <key>PayloadVersion</key> 
        <integer>1</integer> 
        <key>PayloadEnabled</key> 
        <true/> 
        <key>PayloadRemovalDisallowed</key> 
        <true/> 
        <key>PayloadScope</key> 
        <string>System</string> 
        <key>PayloadContent</key> 
        <array> 
            <dict> 
                <key>PayloadUUID</key> 
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string> 
                <key>PayloadType</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadOrganization</key> 
                <string>Microsoft</string> 
                <key>PayloadIdentifier</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadDisplayName</key> 
                <string>Microsoft Defender ATP configuration settings</string> 
                <key>PayloadDescription</key> 
                <string/> 
                <key>PayloadVersion</key> 
                <integer>1</integer> 
                <key>PayloadEnabled</key> 
                <true/> 
                <key>deviceControl</key> 
                <dict> 
                    <key>removableMediaPolicy</key> 
                    <dict> 
                        <key>enforcementLevel</key> 
                        <string>block</string> 
                        <key>permission</key> 
                        <array> 
                            <string>read</string>
                            <string>write</string> 
                        </array> 
                    </dict> 
                </dict>
            </dict> 
        </array> 
    </dict> 
</plist> 
```

## <a name="restrict-all-devices-from-specific-vendors"></a><span data-ttu-id="0b176-121">Begränsa alla enheter från specifika leverantörer</span><span class="sxs-lookup"><span data-stu-id="0b176-121">Restrict all devices from specific vendors</span></span>

<span data-ttu-id="0b176-122">I följande exempel begränsas alla enheter från specifika leverantörer (i det här fallet identifierade av `fff0` och `4525` ).</span><span class="sxs-lookup"><span data-stu-id="0b176-122">The following example restricts all devices from specific vendors (in this case identified by `fff0` and `4525`).</span></span> <span data-ttu-id="0b176-123">Alla andra enheter är obegränsade eftersom behörigheten som definieras på den högsta nivån i principen listar alla möjliga behörigheter (läsa, skriva och köra).</span><span class="sxs-lookup"><span data-stu-id="0b176-123">All other devices will be unrestricted, since the permission defined at the top level of the policy lists all possible permissions (read, write, and execute).</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1"> 
    <dict> 
        <key>PayloadUUID</key> 
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string> 
        <key>PayloadType</key> 
        <string>Configuration</string> 
        <key>PayloadOrganization</key> 
        <string>Microsoft</string> 
        <key>PayloadIdentifier</key> 
        <string>com.microsoft.wdav</string> 
        <key>PayloadDisplayName</key> 
        <string>Microsoft Defender ATP settings</string> 
        <key>PayloadDescription</key> 
        <string>Microsoft Defender ATP configuration settings</string> 
        <key>PayloadVersion</key> 
        <integer>1</integer> 
        <key>PayloadEnabled</key> 
        <true/> 
        <key>PayloadRemovalDisallowed</key> 
        <true/> 
        <key>PayloadScope</key> 
        <string>System</string> 
        <key>PayloadContent</key> 
        <array> 
            <dict> 
                <key>PayloadUUID</key> 
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string> 
                <key>PayloadType</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadOrganization</key> 
                <string>Microsoft</string> 
                <key>PayloadIdentifier</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadDisplayName</key> 
                <string>Microsoft Defender ATP configuration settings</string> 
                <key>PayloadDescription</key> 
                <string/> 
                <key>PayloadVersion</key> 
                <integer>1</integer> 
                <key>PayloadEnabled</key> 
                <true/> 
                <key>deviceControl</key> 
                <dict> 
                    <key>removableMediaPolicy</key> 
                    <dict> 
                        <key>enforcementLevel</key> 
                        <string>block</string> 
                        <key>permission</key> 
                        <array> 
                            <string>read</string>
                            <string>write</string>
                            <string>execute</string> 
                        </array> 
                        <key>vendors</key> 
                        <dict> 
                            <key>fff0</key> 
                            <dict> 
                                <key>permission</key> 
                                <array> 
                                    <string>none</string> 
                                </array> 
                            </dict> 
                            <key>4525</key> 
                            <dict> 
                                <key>permission</key> 
                                <array>                         
                                    <string>none</string> 
                                </array> 
                            </dict> 
                        </dict> 
                    </dict> 
                </dict>
            </dict> 
        </array> 
    </dict> 
</plist>
```

## <a name="restrict-specific-devices-identified-by-vendor-id-product-id-and-serial-number"></a><span data-ttu-id="0b176-124">Begränsa specifika enheter som identifieras med leverantörs-ID, produkt-ID och serienummer</span><span class="sxs-lookup"><span data-stu-id="0b176-124">Restrict specific devices identified by vendor ID, product ID, and serial number</span></span>

<span data-ttu-id="0b176-125">I följande exempel begränsas två specifika enheter som identifieras med leverantörs-ID, `fff0` produkt-ID `1000` och serienummer och `04ZSSMHI2O7WBVOA` `04ZSSMHI2O7WBVOB` .</span><span class="sxs-lookup"><span data-stu-id="0b176-125">The following example restricts two specific devices, identified by vendor ID `fff0`, product ID `1000`, and serial numbers `04ZSSMHI2O7WBVOA` and `04ZSSMHI2O7WBVOB`.</span></span> <span data-ttu-id="0b176-126">På alla andra nivåer i principen omfattar behörigheterna alla möjliga värden (läsa, skriva och köra), vilket innebär att alla andra enheter kommer att vara obegränsade.</span><span class="sxs-lookup"><span data-stu-id="0b176-126">At all other levels of the policy the permissions include all possible values (read, write, and execute), meaning that all other devices will be unrestricted.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1"> 
    <dict> 
        <key>PayloadUUID</key> 
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string> 
        <key>PayloadType</key> 
        <string>Configuration</string> 
        <key>PayloadOrganization</key> 
        <string>Microsoft</string> 
        <key>PayloadIdentifier</key> 
        <string>com.microsoft.wdav</string> 
        <key>PayloadDisplayName</key> 
        <string>Microsoft Defender ATP settings</string> 
        <key>PayloadDescription</key> 
        <string>Microsoft Defender ATP configuration settings</string> 
        <key>PayloadVersion</key> 
        <integer>1</integer> 
        <key>PayloadEnabled</key> 
        <true/> 
        <key>PayloadRemovalDisallowed</key> 
        <true/> 
        <key>PayloadScope</key> 
        <string>System</string> 
        <key>PayloadContent</key> 
        <array> 
            <dict> 
                <key>PayloadUUID</key> 
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string> 
                <key>PayloadType</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadOrganization</key> 
                <string>Microsoft</string> 
                <key>PayloadIdentifier</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadDisplayName</key> 
                <string>Microsoft Defender ATP configuration settings</string> 
                <key>PayloadDescription</key> 
                <string/> 
                <key>PayloadVersion</key> 
                <integer>1</integer> 
                <key>PayloadEnabled</key> 
                <true/> 
                <key>deviceControl</key> 
                <dict> 
                    <key>removableMediaPolicy</key> 
                    <dict> 
                        <key>enforcementLevel</key> 
                        <string>block</string> 
                        <key>permission</key> 
                        <array> 
                            <string>read</string>
                            <string>write</string>
                            <string>execute</string>
                        </array> 
                        <key>vendors</key> 
                        <dict> 
                            <key>fff0</key> 
                            <dict> 
                                <key>permission</key> 
                                <array> 
                                    <string>read</string> 
                                    <string>write</string>
                                    <string>execute</string> 
                                </array> 
                                <key>products</key> 
                                <dict> 
                                    <key>1000</key> 
                                    <dict> 
                                        <key>permission</key> 
                                        <array> 
                                            <string>read</string> 
                                            <string>write</string>
                                            <string>execute</string>
                                        </array> 
                                        <key>serialNumbers</key> 
                                        <dict> 
                                            <key>04ZSSMHI2O7WBVOA</key> 
                                            <array> 
                                            <string>none</string> 
                                            </array> 
                                            <key>04ZSSMHI2O7WBVOB</key>
                                            <array> 
                                            <string>none</string> 
                                            </array> 
                                        </dict> 
                                    </dict> 
                                </dict> 
                            </dict>
                        </dict> 
                    </dict> 
                </dict>
            </dict> 
        </array> 
    </dict> 
</plist>
```

## <a name="related-topics"></a><span data-ttu-id="0b176-127">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="0b176-127">Related topics</span></span>

- [<span data-ttu-id="0b176-128">Översikt över enhetskontroll för macOS</span><span class="sxs-lookup"><span data-stu-id="0b176-128">Overview of device control for macOS</span></span>](mac-device-control-overview.md)
