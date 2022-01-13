---
title: 在應用程式中的 Walkie Talkie Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 如何從 ITAdmin 的觀點，在 Microsoft Teams中設定 Walkie Talkie 應用程式。
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
ms.openlocfilehash: c19894106dfd06c13ec9936657837aa42fcdade0
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015013"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>在應用程式中的 Walkie Talkie Microsoft Teams

Teams中的對講Teams App 提供您小組的立即隨 (PTT) 通訊，現在可在 Android & iOS 上使用。 Walkie Talkie 允許使用者使用他們成員相同的基礎頻道，與小組聯繫。 只有在頻道中連接到 Walkie Talkie 的使用者才能成為參與者，而且可以使用隨推即說的方式彼此通訊，一次一個。

在 Teams 中使用 Walkie Talkie，前線員工現在可以使用熟悉的 PTT 體驗安全地通訊，而不需要攜帶大量收音機，而 Walkie Talkie 可在任何位置使用 WiFi 或行動電話網際網路連接。

## <a name="getting-started"></a>快速入門

### <a name="deploying-walkie-talkie"></a>部署對講臺 Talkie

Android 裝置支援在 Android 裝置上使用 Google 行動服務 (GMS) iOS 裝置。 

目前，Walkie Talkie 尚未預先安裝。 若要為貴組織的使用者啟用這項功能，您必須將 Walkie Talkie 新增到 [](teams-app-setup-policies.md)從系統管理中心指派給使用者的應用程式設定Teams   [策略](https://admin.teams.microsoft.com/)。 啟用之後，Walkie Talkie 將在 48 小時內在 App 上提供。

### <a name="adding-walkie-talkie-to-your-app-list"></a>新增對講臺到您的應用程式清單

在 Microsoft Teams系統管理中心，Teams **應用程式** 設定政策下，您應該將允許使用者釘點設定  >  為 **On**。  接著，在 [釘上的應用程式> 區段下，按一下 **[+新增應用程式>**。

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="顯示已釘選的 App 區段和要選取的新增應用程式按鈕。":::

在右側 **出現的新增釘上** 應用程式面板上，使用搜尋文字方塊尋找Walkie Talkie。 當您將名稱做為搜尋結果時，請選取名稱右邊的新增按鈕，將其新加到清單中。

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="顯示在搜尋窗格中輸入 Walkie 的已釘選應用程式側邊欄，以及搜尋結果中的 Walkie Talkie 應用程式，旁邊有新增按鈕。":::

Walkie Talkie App 現在應該會出現在 [釘選的 App」 清單中，而且一旦按一下 [儲存） 按鈕，即可 **使用** 。

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="顯示已新增 Walkie Talkie 應用程式的釘選應用程式清單，以及清單下方的儲存按鈕。":::

### <a name="network-documentation"></a>網路檔

Teams對講Teams需要網際網路連接，且網路條件低於網路條件才能獲得最佳體驗。

|度量 | 必要 |
|---|---|
|RTT (延遲)  | < 300 毫秒 |
|抖動 |< 30 毫秒 |
|封包遺失 |< 1% |

如上所述，IP 網路即時媒體的品質會受到網路連接品質的嚴重影響，尤其是受到以下數量的影響：

- **延遲** - 這是從 A 點到網路 B 點取得 IP 封包所花的時間。 網路傳播延遲基本上與兩點之間的實際距離和光速有關，包括介於兩者之間的各種路由器所增加的負荷。 延遲是以 RTT (的往返時間) 。
- **到達間抖動** - 這是連續封包之間延遲的平均變化。
- **封包** 遺失 - 這通常定義為在給定時段內遺失的封包百分比。 封包遺失會直接影響音訊品質，包括小型、個別遺失的封包幾乎沒有影響，以及造成音訊完全中斷的背對背斷流損失。

在傳送或接收音訊時，Walkie Talkie 的預期資料使用量約為 20 Kb/s。 閒置時，Walkie Talkie 的預期資料使用量可忽略不計。

### <a name="walkie-talkie-devices"></a>Walkie Talkie 裝置

即使電話已鎖定，前線員工通常也需要說話並接聽 Walkie Talkie 通話。 透過具有專用 PTT 按鈕的專用裝置，即可獲得此體驗。

- **耳機**
  - iOS (Android &的無線) 
    - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - 只有 Android (有線耳機) 
    - [克洛因電子](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- **崎嶇的 Android 手機**
  - Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)， [Galaxy XCover 5，](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy) [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
    - 手動設定 - 安裝Teams之後，流覽至 設定 > XCover/Active 鍵>進>功能。 開啟 '使用 App 控制 XCover 鍵'，然後選取 'Teams'
    - [MDM 設定](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
  - 斑 [馬版 TC5x，](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html) [TC7x，](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html) [TC2x，](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html) [EC5x，](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html) [EC30，](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html) [MC3300，](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html) [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
    - 手動設定 - Teams安裝之後，專用 PTT 按鈕 (LEFT_TRIGGER_2) 在 Walkie Talkie 中運作
    
> [!NOTE]
> 這些裝置未通過Teams認證。 它們已經過驗證，可Teams Walkie Talkie。

### <a name="license-requirements"></a>授權需求

Walkie Talkie 應用程式會包含在所有付費授權Teams訂閱Office 365[中](/office365/servicedescriptions/teams-service-description)。 若要進一Teams，請參閱如何 [存取Microsoft Teams？](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="further-information"></a>進一步資訊

- ITAdmins 可以透過應用程式策略，維持對講臺對講程式消費者的控制。
- 如果您的前線員工使用行動資料透過 Teams 通訊，Walkie Talkie 會使用相同的方法。
- 對講機在低頻寬情況下，或智慧型手機已連接及使用的情況下，應該可以順利使用。 當完全沒有連接時，對講臺 Talkie 將無法工作。

有關使用者體驗的進一步閱讀，請參閱：

- [開始使用 walkie Talkie Teams Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [使用 Walkie Talkie 與小組溝通](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
