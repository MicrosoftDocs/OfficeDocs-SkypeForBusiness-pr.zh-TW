---
title: 管理 Microsoft Teams 會議室
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: 瞭解如何開發和執行持續維護與作業，以確保您的Microsoft Teams 會議室系統可供使用者使用。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dbe3a22b86fa9f4b0773e1a7397bb206deb093e1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58636637"
---
# <a name="manage-microsoft-teams-rooms"></a>管理 Microsoft Teams 會議室

如果您擁有Microsoft Teams 會議室認證的裝置，您擁有彈性的管理選項。  您可以在管理您所有解決方案的中央位置管理裝置，Teams系統管理中心Microsoft Teams，您也可以使用受管理服務將管理責任Microsoft Teams 會議室[專家。](https://portal.rooms.microsoft.com)  您也可以將管理存取權委派給您所選擇的合作夥伴，以取得其中一個選項。

使用 Microsoft Teams系統管理中心，您可以：

- 執行裝置管理，例如重新開機裝置和下載裝置記錄
- 將Teams特定設定
- 檢查會議室裝置Microsoft Teams裝置及其周邊裝置的健康情況，包括相機、顯示器、麥克風等
- 檢閱目前和過去的 (活動，例如通話品質、網路健康情況與連接，以及參與者) 
- 查看已 (裝置上的) 裝置等Microsoft Teams裝置

若要管理Teams 會議室，請開啟 Microsoft Teams [系統管理中心](https://admin.teams.microsoft.com)，然後前往 **裝置**  >  **Teams 會議室。**

:::image type="content" source="../media/teams-rooms-summary.png" alt-text="Teams 會議室系統管理中心Teams摘要頁面":::

> [!IMPORTANT]
> 若要使用系統管理Teams管理中心管理裝置，您必須指派全域系統管理員、Teams系統管理員或Teams系統管理員角色。

## <a name="make-changes-to-teams-rooms-devices"></a>變更Teams 會議室裝置

如果您有多個裝置Teams 會議室，您可以同時在多個裝置上執行大部分的動作。 例如，您可以同時Teams所有裝置上的應用程式設定。

### <a name="device-settings"></a>裝置設定

您可以在貴組織的一或多個裝置上變更設定。 若要變更設定，請選取您想要管理的裝置，然後選取編輯 **設定。** 新的窗格將會開啟，並包含您可以在裝置上變更的所有設定。 下表列出您可以使用系統管理中心Teams設定。 某些設定只有在您選取單一裝置時才能使用。

如果您選取多個裝置，支援大量編輯的設定會顯示下列兩個選項。

- **保留現有值** 如果您選擇這個選項，您所選的裝置上的設定不會變更。
- **以取代現有值** 如果您選擇這個選項，就可以使用您提供的值更新您所選裝置上的設定。
    > [!CAUTION]
    > 您選擇更新之設定上的現有值將會以您提供的值取代。 如果您想要新增到現有值清單中，您必須包含現有值與您想要新增的值。 例如，如果設定有 現有的網域清單 ，而您想要新增，您需要提供 `contoso.com, fabrikam.com` `northwindtraders.com` 的值就是 `contoso.com, fabrikam.com, northwindtraders.com` 。
    >
    > 如果您選取多個裝置，您選取的所有裝置上的設定都會變更為您提供的值。 如果裝置設定的值不同，則所有設定的值都將會更新為相同的值。

| 設定                                                      | 接受的值                                        | 支援大量編輯 |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *帳戶*                                                    |                                                        |                    |
| **電子郵件**                                                    | 電子郵件地址                                          | 否                 |
| **支援的會議模式**                                   | 商務用 Skype (預設) Microsoft Teams<br>商務用 Skype Microsoft Teams (預設) <br>商務用 Skype只|是|
| **新式驗證**                                    | 開啟<br>關閉                                              | 是                |
| **Exchange位址**                                         | 電子郵件地址                                          | 否                 |
| **網域\使用者 (選)**                               | 帳戶網域和使用者名稱                           | 否                 |
| **設定網域**                                         | 逗號分隔清單                                   | 是                |
| *會議*                                                   |                                                        |                    |
| **自動螢幕畫面共用**                                 | 開啟<br>關閉                                              | 是                |
| **顯示會議名稱**                                       | 開啟<br>關閉                                              | 是                |
| **如果其他人都離開會議，自動離開**                 | 開啟<br>關閉                                              | 是                |
| *裝置*                                                     |                                                        |                    |
| **雙監視器模式**                                        | 開啟<br>關閉                                              | 是                |
| **藍牙標**                                      | 開啟<br>關閉                                              | 是                |
| **自動接受鄰近會議邀請** | 選擇<br>未選                                 | 是                |
| **傳送有意見回饋的記錄**                                  | 開啟<br>關閉                                              | 是                |
| **記錄與意見回饋的電子郵件地址**                      | 電子郵件地址                                          | 是                |
| *外設*                                                |                                                        |                    |
| **會議麥克風**                                  | 可用的麥克風清單                          | 否                 |
| **會議演講者**                                     | 可用的演講者清單                             | 否                 |
| **預設音量**                                           | 0-100                                                  | 否                 |
| **預設喇叭**                                          | 可用的演講者清單                             | 否                 |
| **預設音量**                                           | 0-100                                                  | 否                 |
| **內容相機**                                           | 可用的相機清單                              | 否                 |
| **內容相機增強功能**                              | 開啟<br>關閉                                              | 否                 |
| **旋轉內容相機 180 度**                        | 開啟<br>關閉                                              | 否                 |
| *主題*                                                    |                                                        |                    |
|                                                              | 預設<br>無主題<br>自 定義<br>內建主題清單   | 是                |

### <a name="device-restart-options"></a>裝置重新開機選項

只有在裝置重新開機之後，裝置設定變更才能生效。 當您進行需要重新開機的變更時，您可以選擇是否要立即重新開機裝置或排程重新開機。 以下是可用的重新開機選項：

- **立即重新開機** 如果您選擇這個選項，您進行變更的所有裝置都會在選取此選項後立即重新開機。
- **排定的重新開機** 如果您選擇這個選項，您可以重新開機要變更的裝置，同時對貴組織影響較小。
  - **選取日期和時間** - 選擇重新開機裝置的特定日期和時間。 您選取的日期和時間是重新開機之裝置的本地日期和時間。 
  - **將更新保留為夜間重新開機** 裝置會夜間重新開機以執行維護。 您對裝置進行變更，將會在此重新開機期間進行。

> [!CAUTION]
> 重新開機時使用中的裝置在重新開機程式期間將無法使用。 他們將與進行中的會議中斷連接，而且無法加入新的會議。

### <a name="remove-device"></a>移除裝置

當您移除裝置時，裝置會從貴組織移除，且不會再出現在系統管理中心Teams 會議室裝置Teams清單中。

如果您移除裝置，但裝置仍以有效的使用者名稱和密碼進行配置，如果裝置再次連接到 Teams 會議室，系統會自動將其重新Microsoft 365清單中。

若要移除一或多個裝置，請執行下列操作：

1. 前往 **裝置**  >  **Teams 會議室，** 然後選取您想要移除的裝置。
1. 選取 **移除**。

## <a name="download-device-logs"></a>下載裝置記錄

您可以下載裝置診斷記錄檔案的一份副本 ，如果 Microsoft 支援人員要求這麼做。 記錄檔案會壓縮成 zip 檔案，可從系統管理中心Teams下載。

若要將記錄從Teams 會議室下載到您的電腦，請執行下列操作：

1. 前往 **裝置Teams 會議室，** 然後選取您想要下載記錄  >  之裝置的名稱。
1. 選取 **下載裝置記錄**。 裝置記錄可能需要數分鐘的時間才能使用。
1. 選取記錄 **選項卡** ，然後選取診斷檔案下的 **記錄檔案連結**。 包含您裝置診斷記錄檔案的 zip 檔案會下載到瀏覽器的預設下載資料夾。

## <a name="view-device-information"></a>查看裝置資訊

從 Teams系統管理中心，您可以查看貴組織所有裝置的整體狀態，並個別查看每個裝置的詳細資訊。

### <a name="teams-rooms-system-dashboard"></a>Teams 會議室儀表板

系統Teams 會議室儀表板一目了然地顯示所有裝置的狀態和健康情況。

### <a name="device-details-view"></a>裝置詳細資料檢視

若要查看裝置的詳細資訊，請從裝置清單中選取其名稱。 在詳細資料檢視時，您可以查看下列裝置相關資訊：

- **健康情況** 顯示會議室裝置Teams健康情況。 健康狀態可以是健康 **狀態或****不健康狀態**。
- **離線，因為** 顯示上次Microsoft 365裝置通訊的時間。
- **裝置狀態** 顯示裝置目前的狀態：空閒、Teams、Skype **會議** 或 **Ingest。** 
- **周邊設備** 顯示連接到您會議室Teams的周邊設備及其健康狀態。 健康狀態可以是已 **連接或****已中斷連接**。
- **健康狀態** 顯示連接到您會議室裝置Teams、網路連接、登錄所需服務的狀態，以及軟體版本資訊的詳細資訊。
- **詳細資料** 顯示製造商資訊、網路 IP 位址，Teams會議室裝置序列/MAC 位址。
- **活動** 顯示過去的會議詳細資料，包括會議日期和時間、參與者人數、持續時間和音訊品質。 有關會議詳細資料的詳細資訊，請參閱本文稍後[](#meeting-activity-details)的會議活動詳細資料一節。
- **歷程記錄** 顯示會議室Teams管理活動的歷程記錄，包括組Teams更新、裝置重新開機，以及裝置記錄下載連結。

#### <a name="meeting-activity-details"></a>會議活動詳細資料

會議室 **裝置** Teams中的活動選項卡會顯示裝置一段時間參與之所有會議的高層級和詳細資訊。 在 **活動** 選項卡中，您可以查看會議召開時間、出席會議的參與者人數，以及會議期間的音訊品質。

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Teams會議室裝置活動摘要清單":::

若要查看特定會議的詳細資訊，請選取您想要進一步說明的會議日期和時間。 如果會議只有兩個參與者，則會看到參與者詳細資料頁面，否則會看到參與者摘要頁面。

##### <a name="participant-summary"></a>參與者摘要

參與者摘要頁面會顯示所有參加會議的參與者。 您可以查看每個參與者何時加入會議、他們的名稱、音訊品質，以及會話期間使用的功能。 若要查看參與者的會話詳細資料，請選取該參與者的會話開始時間。

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Teams會議室裝置會議詳細資料":::

##### <a name="participant-details"></a>參與者詳細資料

參與者詳細資料頁面會顯示該參與者會話的端對端診斷資訊。 如下列圖形所示，系統會為參與者和裝置提供裝置Teams 會議室資訊。  **參與者** 與裝置之間的網路診斷Teams 會議室也會提供。 選取您想要詳細資訊之上下文的圖示。 有關其他診斷資訊，請選取進 **一步資料表** 。

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Teams會議室裝置通話詳細資料":::
