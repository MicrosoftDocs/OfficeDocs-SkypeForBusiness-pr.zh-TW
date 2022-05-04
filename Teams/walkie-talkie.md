---
title: Microsoft Teams 中的無線對講機應用程式
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 如何從 ITAdmin 的觀點，在 Microsoft Teams 中設定無線對講機應用程式。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 776f0f31d54788fbffd86bbcbedd44e30ada28a3
ms.sourcegitcommit: ad8447b683381bc07f993bf843a93a4bdb77d840
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2022
ms.locfileid: "65186969"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Microsoft Teams 中的無線對講機應用程式

Teams中的 [無線對講機] 應用程式為您的小組提供即時推播到說話 (PTT) 通訊，現在可在 Android & iOS 上使用。 無線對講機可讓使用者使用屬於其成員的相同基礎頻道與其團隊連線。 只有連線到頻道中無線對講機的使用者會成為參與者，而且可以一次一個按鍵對講功能彼此通訊。

透過 Teams 中的無線對講機，第一線工作人員現在可以安全地與熟悉的 PTT 體驗通訊，而不需要攜帶大量無線電，而且無線對講機可在 WiFi 或行動網路網際網路連線的任何地方使用。

## <a name="getting-started"></a>快速入門

### <a name="deploying-walkie-talkie"></a>部署無線對講機

在配備 Google 行動服務 (MCS) 和 iOS 裝置的 Android 裝置上支援無線對講機。

### <a name="pin-walkie-talkie-to-teams"></a>將無線對講機釘選到Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>使用量身打造的第一線應用程式體驗，將無線對講機和其他應用程式釘選到Teams

在 Teams 中量身打造的第一線應用程式體驗會將最相關的應用程式釘選到 Teams 中，以供[擁有 F 授權](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)的使用者使用。 釘選的應用程式包括無線對講機、班次、工作和核准。 根據預設，此功能為您的第一線工作人員提供專為其需求量身打造的全新體驗。

這些應用程式會釘選到應用程式行，也就是Teams桌面用戶端側邊，以及Teams行動用戶端底部的列，使用者可以在此快速且輕鬆地存取它們。

若要深入瞭解，包括體驗如何與您所設定的應用程式原則搭配運作，請參閱[為前線員工量身打造Teams應用程式](pin-teams-apps-based-on-license.md)。

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>使用應用程式設定原則將無線對講機釘選到Teams

應用程式設定原則可讓您自訂Teams以釘選對使用者中使用者最重要的應用程式。

若要為使用者釘選無線對講機應用程式，您可以編輯全域 (組織的預設) 原則，或建立及指派自訂應用程式設定原則。 若要深入了解，請參閱[管理 Teams 中的應用程式設定原則](teams-app-setup-policies.md)。

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="螢幕擷取畫面顯示在 [新增釘選的應用程式] 窗格中，將 [無線對講機] 新增至釘選的應用程式清單。" lightbox="media/deploy-walkie-talkie-2.png":::

### <a name="network-documentation"></a>網路檔

Teams中的無線對講機需要網際網路連線，而在網路條件之下則需要優化體驗。

|度量 | 必要 |
|---|---|
|RTT)  (延遲 | < 300ms |
|抖動 |< 30ms |
|封包遺失 |< 1% |

如上所述，透過 IP 網路即時媒體的品質受到網路連線品質的極大影響，尤其是受以下情況影響：

- **延遲** - 這是從 A 點取得 IP 封包到網路上指向 B 所需的時間。 此網路傳播延遲基本上是與兩點之間的實體距離和光速系結，包括兩者之間各種路由器所佔用的額外負荷。 延遲是以 RTT)  (來回時間來測量。
- **送達間抖動** - 這是連續封包之間延遲的平均變更。
- **封包遺失** - 這通常定義為在指定時間範圍中遺失的封包百分比。 封包遺失會直接影響音訊品質，從幾乎沒有影響的小型、個別遺失封包，到造成完整音訊完全中斷的連續中斷。

傳送或接收音訊時，無線對講機的預期資料使用量大約為 20 Kb/s。 閒置時，可忽略無線對講機的預期資料使用量。

### <a name="walkie-talkie-devices"></a>無線對講機裝置

即使在手機遭到鎖定時，第一線工作人員仍需要使用無線對講機通話並接聽電話。 此體驗可透過具有專用 PTT 按鈕的專用裝置來體驗。

- **耳機**
  - iOS & Android)  (無線耳機
    - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - Android (有線耳機僅) 
    - [器克電子](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- **崎嶇不平的 Android 手機**
  - Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)、[Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy)、[Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
    - 手動設定 - 安裝Teams後，流覽至 XCover/Active 鍵>設定 >進階功能。 開啟 [搭配應用程式控制 XCover 金鑰]，然後選取 [Teams]
    - [MDM 設定](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
  - Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html)、 [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html)、 [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html)、 [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html)、 [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html)、 [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html)、 [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
    - 手動設定 - 安裝Teams後，依預設專用的 PTT 按鈕 (LEFT_TRIGGER_2) 可與無線對講機搭配使用
    
> [!NOTE]
> 這些裝置未Teams認證。 他們已通過驗證，可搭配Teams無線對講機使用。

### <a name="license-requirements"></a>授權需求

Office 365訂閱中的所有付費Teams授權中都包含無線對講機[應用程式](/office365/servicedescriptions/teams-service-description)。 如需取得Teams的詳細資訊，請參閱 [如何?存取Microsoft Teams嗎](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)？

## <a name="further-information"></a>進一步資訊

- ITAdmins 可以透過應用程式原則來控制誰正在使用無線對講機。
- 如果您的前線員工使用行動資料透過Teams通訊，無線對講機將會使用相同的方法。
- 無線對講機在頻寬不足或智慧型手機連線正常運作的情況下，應該可以正常運作。 完全沒有連線時，無線對講機就無法運作。

如需進一步閱讀使用者體驗，請參閱：

- [開始Teams無線對講機](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [使用無線對講機與您的小組通訊](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
