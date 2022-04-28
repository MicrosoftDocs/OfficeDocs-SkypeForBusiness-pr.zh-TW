---
title: 管理 Microsoft Teams 會議室
ms.author: czawideh
author: cazawideh
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
description: 瞭解如何開發和執行持續維護和作業，以確保您的Microsoft Teams 會議室系統可供使用者使用。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 47f1c170fd0c41331dfaffa2d81386ac3c2fb722
ms.sourcegitcommit: 0967f725aad0a7b9c430b2e30a37ea333007558a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2022
ms.locfileid: "65106268"
---
# <a name="manage-microsoft-teams-rooms"></a>管理 Microsoft Teams 會議室

如果您的組織中有Microsoft Teams 會議室，您有彈性的管理選項。  您可以在管理所有Teams解決方案的同一個中央位置自行管理裝置，Microsoft Teams系統管理中心。 或者，您可以使用Microsoft Teams 會議室[管理服務](https://portal.rooms.microsoft.com)，將管理責任轉移給專屬專家。  您也可以針對其中一個選項，將管理存取權委派給您選擇的合作夥伴。

透過Microsoft Teams系統管理中心，您可以：

- 執行裝置管理，例如重新開機裝置和下載裝置記錄
- 套用Teams特定設定
- 檢查Microsoft Teams 會議室及其周邊設備的健康情況狀態，包括相機、顯示器、麥克風等
- 檢閱目前和過去的會議活動 (例如通話品質、網路健康情況和連線能力的詳細資料，以及) 
- 查看周邊設備 (，例如) 連接到Microsoft Teams 會議室的相機和投影機

若要管理Teams 會議室裝置，請開 [啟Microsoft Teams系統管理中心](https://admin.teams.microsoft.com)，然後移至Windows 上的 **[Teams裝置**  >  **Teams 會議室**]。

:::image type="content" source="../media/teams-rooms-summary2.png" alt-text="Teams系統管理中心的Teams 會議室摘要頁面。":::


> [!IMPORTANT]
> 若要使用 Teams 系統管理中心管理裝置，您必須指派全域系統管理員、Teams系統管理員或Teams裝置系統管理員角色。

## <a name="make-changes-to-teams-rooms-devices"></a>變更Teams 會議室裝置

如果您有多個Teams 會議室，您可以在多個裝置上同時執行大部分的動作。 例如，您可以同時在所有Teams 會議室上設定Teams應用程式設定。

### <a name="device-settings"></a>裝置設定

您可以變更組織中一或多個Teams 會議室的設定。 若要變更設定，請選取您要管理的裝置，然後選取 **[編輯設定]**。 隨即會開啟一個新窗格，其中包含您可以變更的所有設定。 下表列出您可以使用系統管理中心Teams變更的設定。 有些設定只有在您選取單一Teams 會議室時才能使用。

如果您選取多個選項，支援大量編輯的設定會顯示下列兩個選項。

- **保留現有值** 如果您選擇此選項，就不會對所選Teams 會議室上的設定進行任何變更。
- **以現有值取代現有值** 如果您選擇此選項，您可以使用您所提供的值來更新所選Teams 會議室上的設定。
    > [!CAUTION]
    > 您選擇更新之設定上的現有值將會取代為您提供的值。 如果您想要新增到現有值清單，您必須將現有值與您要新增的值一併包含在一起。 例如，如果設定有現有的網域清單 ， `contoso.com, fabrikam.com` 而您想要新增 `northwindtraders.com` ，則您需要提供的值會是 `contoso.com, fabrikam.com, northwindtraders.com` 。
    >
    > 如果您選取多個Teams 會議室，您所選取之所有裝置上的設定將會變更為您提供的值。 如果Teams 會議室設定的值不同，它們都會更新為相同的值。

| 設定                                                      | 公認的值                                        | 支援大量編輯 |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *帳戶*                                                    |                                                        |                    |
| **電子郵件**                                                    | 電子郵件地址                                          | 否                 |
| **支援的會議模式**                                   | 僅限Microsoft Teams<br>商務用 Skype (預設) 和Microsoft Teams<br>商務用 Skype和Microsoft Teams (預設) <br>僅商務用 Skype|是|
| **新式驗證**                                    | 開啟<br>關閉                                              | 是                |
| **Exchange位址**                                         | 電子郵件地址                                          | 否                 |
| **網域\使用者名稱 (選擇性)**                               | 帳戶網域和使用者名稱                           | 否                 |
| **設定網域**                                         | 逗號分隔清單                                   | 是                |
| *會議*                                                   |                                                        |                    |
| **自動螢幕畫面分享**                                 | 開啟<br>關閉                                              | 是                |
| **HDMI 內充音訊共用**                                 | 開啟<br>關閉                                              | 是                |
| **顯示會議名稱**                                       | 開啟<br>關閉                                              | 是                |
| **如果其他人都已離開會議，請自動離開**                 | 開啟<br>關閉                                              | 是                |
| **加入協力廠商會議**                 | Cisco Webex<br>縮放                                              | 是                |
| **使用會議室資訊加入**                 | 選擇<br>未選取                                              | 是                |
| **使用自訂資訊加入**                 | 選擇<br>未選取                                              | 是                |
| **需要名稱 ()**                 | 聊天室或空間的名稱                                              | 是                |
| **需要電子郵件 ()**                 | 電子郵件地址                                              | 是                |
| *裝置*                                                     |                                                        |                    |
| **雙螢幕模式**                                        | 開啟<br>關閉                                              | 是                |
| **允許複製內容** | 選擇<br>未選取                                 | 是                |
| **藍牙指標**                                      | 開啟<br>關閉                                              | 是                |
| **自動接受近接式會議邀請** | 選擇<br>未選取                                 | 是                |
| **傳送含有意見反應的記錄**                                  | 開啟<br>關閉                                              | 是                |
| **記錄檔和意見反應的電子郵件地址**                      | 電子郵件地址                                          | 是                |
| *協調會議*                                                     |                                                        |                    |
| **協調會議** | 開啟<br>關閉                                 | 否                |
| **開啟此裝置的麥克風** | 開啟<br>關閉                                 | 否                |
| **讓人員在加入會議時啟用** | 選擇<br>未選取                                 | 否                |
| **開啟此裝置的相機** | 開啟<br>關閉                                 | 否                |
| **讓人員在加入會議時啟用** | 選擇<br>未選取                                 | 否                |
| **開啟此裝置的白板功能** | 開啟<br>關閉                                 | 否                |
| **信任的裝置帳戶 (以逗號) 分隔** | 裝置清單                              | 否                |
| *外設*                                                |                                                        |                    |
| **會議麥克風**                                  | 可用麥克風清單                          | 否                 |
| **會議演講者**                                     | 可用喇叭清單                             | 否                 |
| **預設磁片區**                                           | 0-100                                                  | 否                 |
| **預設喇叭**                                          | 可用喇叭清單                             | 否                 |
| **預設磁片區**                                           | 0-100                                                  | 否                 |
| **內容相機**                                           | 可用相機清單                              | 否                 |
| **內容相機增強功能**                              | 開啟<br>關閉                                              | 否                 |
| **將內容相機旋轉 180 度**                        | 開啟<br>關閉                                              | 否                 |
| *主題*                                                    |                                                        |                    |
|                                                              | 預設<br>無主題<br>自 定義<br>內建主題清單   | 是                |

### <a name="cortana-settings"></a>Cortana設定

您可以針對組織中的所有裝置，或針對每個裝置分別使用 PowerShell，啟用 _語音啟動_ 或 _推播_ 功能的Cortana。

See [Microsoft Teams Rooms on Windows](../cortana-in-teams.md) in the "Cortana voice assistance in Teams" article.

### <a name="front-row-layout-settings"></a>前列版面配置設定

前列是Windows上Teams 會議室的會議檢視版面配置選項。

| Teams裝置 | 應用程式版本 | 會議室前方顯示器 |
|--------------|-------------|-----------------------|
|在 Windows 上Microsoft Teams 會議室 | 4.11.12.0 或更新版本 (建議)  | 支援單一和雙顯示器;最小大小：46 英吋;外觀比例 16：9，解析度 1920x1080 或 2560x1080 解析度為 21：9;在Windows設定中，所有顯示器都應該設定為 100% 的縮放比例 |

請[參閱Microsoft Teams 會議室維護與作業](rooms-operations.md#scale-and-resolution)，以調整顯示設定以符合前方列的需求。

若要瞭解如何將前列設定為聊天室的預設版面配置，或如何將它關閉，請參閱使用[XML 組態檔遠端系統管理Microsoft Teams 會議室主機設定](xml-config-file.md#set-front-row-as-the-default-layout)。

如需管理前方列的詳細資訊，請參閱 [已知問題](known-issues.md#Limits) 。

## <a name="device-restart-options"></a>裝置重新開機選項

只有在重新開機Teams 會議室之後，裝置設定的變更才會生效。 當您進行需要重新開機的變更時，您可以選擇是否要立即重新開機或排程重新開機。 以下是可用的重新開機選項：

- **立即重新開機** 如果您選擇此選項，您要變更的所有裝置都會在您選取此選項時立即重新開機。
- **排定的重新開機** 如果您選擇此選項，您可以重新開機您要對組織進行變更的裝置，
  - **選取日期和時間** - 選擇要重新開機裝置的特定日期和時間。 您選擇的日期和時間是重新開機之裝置的本機日期和時間。 
  - **讓更新保持為夜間重新開機** 裝置會在夜間重新開機以執行維護。 您對裝置所做的變更將會在重新開機期間套用。

> [!CAUTION]
> 重新開機時使用的Teams 會議室在重新開機程式期間將無法使用。 它們將會與進行中的會議中斷連線，且無法加入新會議。

## <a name="remove-device"></a>移除裝置

當您移除裝置時，裝置會從貴組織移除，且不會再出現在您Teams系統管理中心的Windows上Teams 會議室清單中。

如果您移除裝置，但仍使用有效的使用者名稱和密碼進行設定，如果該裝置再次連線至Microsoft 365，它會自動重新新增至您的Teams 會議室清單。

若要移除一或多個裝置，請執行下列動作：

1. 移至 **Windows上的 [Teams裝置**  >  **Teams 會議室**，然後選取您要移除的裝置。
2. 選 **取 [移除]**。

## <a name="download-device-logs"></a>下載裝置記錄檔

如果 Microsoft 支援服務要求，您可以下載裝置診斷記錄檔的複本。 記錄檔會壓縮成 zip 檔案，可從Teams系統管理中心下載。

若要從Teams 會議室裝置下載記錄檔到您的電腦，請執行下列動作：

1. 移至 **Teams裝置**  >  **Teams 會議室在Windows上**，然後選取您要從中下載記錄檔的裝置名稱。
1. 選取 **[下載裝置記錄檔]**。 裝置記錄可能需要幾分鐘的時間才能使用。
1. 選取 [ **歷程記錄]** 索引標籤，然後選取 **[診斷檔**] 底下的 [記錄檔] 連結。 包含您裝置診斷記錄檔的 zip 檔案將會下載到瀏覽器的預設 [下載] 資料夾。

## <a name="view-device-information"></a>檢視裝置資訊

您可以從Teams系統管理中心檢視組織中所有裝置的整體狀態，並個別檢視每個裝置的詳細資料。

### <a name="teams-rooms-system-dashboard"></a>Teams 會議室系統儀表板

Teams 會議室系統儀表板一目了然地顯示您所有裝置的狀態和健康情況。

### <a name="device-details-view"></a>裝置詳細資料檢視

若要檢視裝置的詳細資訊，請從裝置清單中選取其名稱。 在詳細資料檢視中，您可以看到下列裝置相關資訊：

- **健康情況狀態** 顯示 Teams Room 裝置的整體健康情況。 健康狀態可以是 **健康** 狀態或 **不健康**。
- **離線，因為** 顯示Microsoft 365最後一次與裝置通訊的時間。
- **裝置狀態** 顯示裝置的目前狀態：**閒置**、**Teams會議**、**Skype會議** 或 **Ingest**。
- **外設** 顯示連接到 Teams Room 裝置的周邊設備及其健康情況狀態。 健康情況狀態可以是 **已連線** 或 **中斷連線**。
- **健康** 顯示連接到Teams會議室裝置、網路連線、必要服務的登入狀態，以及軟體版本資訊的周邊裝置詳細資訊。
- **細節** 顯示製造商資訊、網路 IP 位址，以及Teams會議室裝置序號/MAC 位址。
- **活動** 顯示過去的會議詳細資料，包括會議的日期和時間、參與者人數、持續時間和音訊品質。 For more information about meeting details, see the [Meeting activity details](#meeting-activity-details) section later in this article.
- **歷史** 顯示 Teams Room 裝置上的管理活動歷程記錄，包括設定更新、裝置重新開機，以及裝置記錄下載連結。

#### <a name="meeting-activity-details"></a>會議活動詳細資料

[Teams會議室裝置詳細資料] 中的 [**活動**] 索引標籤會顯示裝置在一段時間內參與的所有會議的高層級和詳細資訊。 在 [ **活動] 索** 引標籤中，您可以查看會議的召開時間、參與會議的參與者數目，以及會議期間的音訊品質。

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Teams會議室裝置活動摘要清單]":::

若要查看特定會議的詳細資訊，請選取您要深入瞭解的會議日期和時間。 如果會議只有兩個參與者，您會看到參與者詳細資料頁面，否則您會看到參與者摘要頁面。

##### <a name="participant-summary"></a>參與者摘要

參與者摘要頁面會顯示所有出席會議的參與者。 您可以查看每位參與者何時加入會議、其名稱、音訊品質，以及會話期間使用的功能。 若要檢視參與者的會話詳細資料，請選取該參與者的會話開始時間。

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Teams會議室裝置會議詳細資料。":::

##### <a name="participant-details"></a>參與者詳細資料

參與者詳細資料頁面會顯示該參與者會話的端對端診斷資訊。 如下圖所示，**系統**、**系統** 和 **連線** 資訊是提供給參與者和Teams 會議室裝置的。 **也** 提供參與者與Teams 會議室裝置之間的網路診斷資訊。 選取您要取得詳細資訊之內容的圖示。 如需其他診斷資訊，請選取 [ **進階** ] 索引標籤。

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Teams會議室裝置通話詳細資料。":::
