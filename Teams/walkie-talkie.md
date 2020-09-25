---
title: Microsoft 團隊中的 Walkie Talkie 應用程式
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 如何在 Microsoft 團隊中從 ITAdmin 的觀點來設定 Walkie Talkie 應用程式。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 605ba58582210c71561cd60442aa66f97be0be0d
ms.sourcegitcommit: 8924cd77923ca321de72edc3fed04425a4b13044
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262500"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Microsoft 團隊中的 Walkie Talkie 應用程式

小組中的 Walkie Talkie 應用程式可為您的小組提供立即推播 (PTT) 溝通，且現已在 Android 上提供。 Walkie Talkie 可讓使用者使用其成員的相同基礎頻道與其團隊進行連線。 只有在頻道中連接至 Walkie Talkie 的使用者才會成為參與者，而且可以使用推入式交談與對方進行通訊。

在團隊中使用 Walkie Talkie，第一線員工工作者現在可以與熟悉的 PTT 體驗安全地溝通，而不需要攜帶容量龐大的無線電，而且 Walkie Talkie 可在任何地方使用 WiFi 或行動電話網際網路連線。

## <a name="getting-started"></a>快速入門

### <a name="deploying-walkie-talkie"></a>部署 Walkie Talkie

目前尚未預先安裝 Walkie Talkie。 若要針對貴組織中的使用者啟用此功能，您必須將 Walkie Talkie 新增 [App Setup Policy](teams-app-setup-policies.md)至   指派給團隊系統[管理中心](https://admin.teams.microsoft.com/)使用者的 App 設定原則。

一旦啟用，在48小時內，Android 應用程式就可以使用 Walkie Talkie。

### <a name="adding-walkie-talkie-to-your-app-list"></a>將 Walkie Talkie 新增至您的應用程式清單

在 Microsoft 團隊系統管理中心的 [**團隊 app**  >  **設定原則**] 底下，您應該將 [**允許使用者釘**選] 設為 [**開啟**]。 接著，在 [固定的 App] 區段底下，按一下 [ **+ 新增 app**]。

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="顯示 [固定的 app] 區段以及要選取的 [新增應用程式] 按鈕。":::

在右側顯示的 [ **新增釘選 app** ] 面板上，使用 [ **搜尋** ] 文字方塊尋找 Walkie Talkie。 當您將它作為搜尋結果時，請按一下名稱右邊的 [ **新增** ] 按鈕，將其新增至您的清單。

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="顯示 [新增釘選的 app] 提要欄位，並在搜尋結果中輸入 Walkie 並 Walkie Talkie 應用程式，其旁邊的 [新增] 按鈕。":::

Walkie Talkie 應用程式現在應該會出現在釘選的 app 清單中，而且在您按一下 [ **儲存** ] 按鈕之後就能使用。

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="顯示已新增 [Walkie Talkie] 應用程式的固定 app 清單，以及清單下方的 [儲存] 按鈕。":::

### <a name="network-documentation"></a>網路檔

小組中的 Walkie Talkie 需要網際網路連線，而且網路條件必須低於最佳體驗。

|衡量 | 必要 |
|---|---|
|RTT (延隔時間)  | < 300ms |
|抖動 |< 30ms |
|資料包遺失 |< 1% |

如上所述，透過網路連線的品質，即時媒體質量會受到很大的影響，但特別是下列數量：

- **延遲** -這是取得 IP 資料包從點 A 到網路上的點 B 所需的時間。 此網路傳播延遲實質上會與兩個點之間的實際距離和光線速度之間的距離產生關聯，包括不同的路由器所佔用的額外負荷。 延遲是以往返時間 (RTT) 來測量。
- **資料包遺失** -通常會定義為在指定的時間視窗中遺失的資料包百分比。 資料包遺失會直接影響音訊品質-從較小、個別遺失且幾乎沒有影響的資料包，到可導致完整音訊切出的後置突發損失。
- **抖動** -這是連續資料包之間延遲的平均變更。

傳送或接收音訊時，Walkie Talkie 的預期資料使用量是在 20KB/s 的周圍。 閒置時，從 Walkie Talkie 預期的資料使用量不計。

### <a name="walkie-talkie-devices"></a>Walkie Talkie 裝置

第一線員工工人通常需要朗讀並接收 Walkie Talkie 通話，即使他們的手機已鎖定也一樣。 透過專用的 PTT 按鈕，就可以使用這種體驗。

- 耳機
  - 有線耳機 ([Klein 電子](https://www.kleinelectronics.com/poc-accessories/mtwt/)) 
  - 無線耳機 ([Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)) 
- 耐用手機
  - Samsung Galaxy XCover Pro
    - [其他資訊](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)。
    - [安裝指南](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)。

> [!NOTE]
> 這些裝置不是經過小組認證。 他們已經過驗證，可與團隊 Walkie Talkie 搭配使用。

### <a name="license-requirements"></a>授權需求

Walkie Talkie 應用程式包含在 [Office 365 訂閱](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)中所有已付費的小組授權中。 如需取得團隊的詳細資訊，請參閱 [如何取得 Microsoft 團隊的存取權](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)？

> [!NOTE]
> 某些高級功能可能需要額外的授權。 例如，與 Samsung Galaxy XCover Pro 的整合需要 Knox 授權。

## <a name="further-information"></a>進一步資訊

- ITAdmins 可以透過應用程式原則維持對誰使用 Walkie Talkie 的控制權。
- 如果您的第一線員工工作者使用行動資料來透過團隊進行通訊，Walkie Talkie 會使用相同的方法。
- 在低頻寬情況下，Walkie Talkie 應該能正常運作，或讓您的智慧型手機連線並正常運作的情況。 如果根本沒有連線，Walkie Talkie 將無法運作。

如需有關最終使用者體驗的進一步閱讀，請參閱：

- [開始使用團隊 Walkie Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [使用 Walkie Talkie 與您的小組進行溝通](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
