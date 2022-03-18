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
description: 瞭解如何開發和執行持續維護與作業，以確保您的Microsoft Teams 會議室系統可供使用者使用。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 12738e544e8bf0f2e46979df0a1d64ea762bfa1f
ms.sourcegitcommit: 640f55fe6144ff867b41b57e52f45b8a64cf779e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2022
ms.locfileid: "63556639"
---
# <a name="manage-microsoft-teams-rooms"></a>管理 Microsoft Teams 會議室

如果您在組織中Microsoft Teams 會議室，則有彈性的管理選項。  您可以在管理所有解決方案的中央位置管理裝置，Teams管理中心Microsoft Teams裝置。 或者，您可以使用受管理服務將管理責任Microsoft Teams 會議室[專家](https://portal.rooms.microsoft.com)。  您也可以將管理存取權委派給您所選擇的合作夥伴，以取得其中一個選項。

有了 Microsoft Teams系統管理中心，您可以：

- 執行裝置管理，例如重新開機裝置和下載裝置記錄
- 將Teams特定設定
- 檢查手機及其Microsoft Teams 會議室的健康情況，包括相機、顯示器、麥克風等
- 檢閱目前和過去的 (活動，例如通話品質、網路健康情況與連接，以及參與者) 
- 查看連接到 (的) 或投影機等Microsoft Teams 會議室

若要管理Teams 會議室，請開啟 Microsoft Teams 系統管理 [中心](https://admin.teams.microsoft.com)  >  ，然後前往 Teams 裝置 **Teams 會議室 Windows**。

:::image type="content" source="../media/teams-rooms-summary2.png" alt-text="Teams 會議室系統管理中心Teams摘要頁面。":::


> [!IMPORTANT]
> 若要使用系統管理中心管理Teams，您必須指派全域系統管理員、Teams系統管理員或Teams系統管理員角色。

## <a name="make-changes-to-teams-rooms-devices"></a>變更Teams 會議室裝置

如果您有多個Teams 會議室，您可以同時在多個裝置上執行大部分的動作。 例如，您可以同時Teams所有應用程式Teams 會議室應用程式設定。

### <a name="device-settings"></a>裝置設定

您可以變更組織中一或多個Teams 會議室上的設定。 若要變更設定，請選取您想要管理的裝置，然後選取編輯 **設定**。 新的窗格將會開啟，其中會包含所有您可以變更的設定。 下表列出您可以使用系統管理中心Teams設定。 某些設定只有在您選取單一Teams 會議室。

如果您選取多個選項，支援大量編輯的設定會顯示下列兩個選項。

- **保留現有值** 如果您選擇這個選項，您所選選項上的設定Teams 會議室變更。
- **以取代現有值** 如果您選擇這個選項，您可以更新所選Teams 會議室您提供的值上的設定。
    > [!CAUTION]
    > 您選擇更新之設定上的現有值將會以您提供的值取代。 如果您想要新增到現有值清單中，您必須包含現有值與您想要新增的值。 例如，如果設定有 現有的 `contoso.com, fabrikam.com` 網域清單 ， `northwindtraders.com` 而您想要新增，您需要提供的值就是 `contoso.com, fabrikam.com, northwindtraders.com` 。
    >
    > 如果您選取多個Teams 會議室，您選取的所有裝置上的設定都會變更為您提供的值。 如果Teams 會議室設定的值不同，則這些值會全部更新為相同的值。

| 設定                                                      | 接受的值                                        | 支援大量編輯 |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|
| *帳戶*                                                    |                                                        |                    |
| **電子郵件**                                                    | 電子郵件地址                                          | 否                 |
| **支援的會議模式**                                   | Microsoft Teams只<br>商務用 Skype (預設) Microsoft Teams<br>商務用 Skype預設Microsoft Teams (和) <br>商務用 Skype僅|是|
| **新式驗證**                                    | 開啟<br>關閉                                              | 是                |
| **Exchange位址**                                         | 電子郵件地址                                          | 否                 |
| **網域\使用者 (選)**                               | 帳戶網域和使用者名稱                           | 否                 |
| **設定網域**                                         | 逗號分隔清單                                   | 是                |
| *會議*                                                   |                                                        |                    |
| **自動螢幕畫面共用**                                 | 開啟<br>關閉                                              | 是                |
| **HDMI 輸入音訊共用**                                 | 開啟<br>關閉                                              | 是                |
| **顯示會議名稱**                                       | 開啟<br>關閉                                              | 是                |
| **如果其他人都離開會議，請自動離開**                 | 開啟<br>關閉                                              | 是                |
| **加入協力廠商會議**                 | Cisco Webex<br>縮放                                              | 是                |
| **使用會議室資訊加入**                 | 選擇<br>未選                                              | 是                |
| **使用自訂資訊加入**                 | 選擇<br>未選                                              | 是                |
| **需要 (名稱)**                 | 會議室或空間的名稱                                              | 是                |
| **需要 (電子郵件)**                 | 電子郵件地址                                              | 是                |
| *裝置*                                                     |                                                        |                    |
| **雙監視器模式**                                        | 開啟<br>關閉                                              | 是                |
| **允許內容重複** | 選擇<br>未選                                 | 是                |
| **藍牙標**                                      | 開啟<br>關閉                                              | 是                |
| **自動接受鄰近會議邀請** | 選擇<br>未選                                 | 是                |
| **傳送有意見回饋的記錄**                                  | 開啟<br>關閉                                              | 是                |
| **記錄與意見回饋的電子郵件地址**                      | 電子郵件地址                                          | 是                |
| *協調會議*                                                     |                                                        |                    |
| **協調會議** | 開啟<br>關閉                                 | 否                |
| **開啟此裝置上的麥克風** | 開啟<br>關閉                                 | 否                |
| **讓人員加入會議時啟用** | 選擇<br>未選                                 | 否                |
| **開啟此裝置相機** | 開啟<br>關閉                                 | 否                |
| **讓人員加入會議時啟用** | 選擇<br>未選                                 | 否                |
| **開啟此裝置上的白板** | 開啟<br>關閉                                 | 否                |
| **信任的裝置帳戶 (逗號或)** | 裝置清單                              | 否                |
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

### <a name="cortana-settings"></a>Cortana設定

您可以使用 PowerShell Cortana或個別針對每個裝置啟用語音啟用或推入通話。

請參閱[Microsoft Teams 會議室Windows](../cortana-in-teams.md)中Cortana語音協助Teams說明。

### <a name="front-row-layout-settings"></a>前排版面配置設定

前列是會議視圖版面配置選項，Teams 會議室上Windows。

| Teams裝置 | 應用程式版本 | 會議室顯示器的前方 |
|--------------|-------------|-----------------------|
|Microsoft Teams 會議室上Windows | 4.11.12.0 (建議使用最新版本)  | 支援單一和雙顯示器;最小大小：46 吋;16：9 與 1920x1080 解析度或 21：9 與 2560x1080 解析度;所有顯示應設定為 100% 縮放比例，Windows設定 |

請參閱[Microsoft Teams 會議室](rooms-operations.md#change-scale-and-resolution)及作業，以調整您的顯示設定，以滿足前列的需求。

若要瞭解如何將前排設定為會議室的預設版面配置，[或如何](xml-config-file.md#set-front-row-as-the-default-layout)關閉，請參閱使用 XML 設定檔Microsoft Teams 會議室管理主機設定。

請參閱 [已知問題](known-issues.md#Limits) ，以瞭解有關管理前列詳細資訊。

## <a name="device-restart-options"></a>裝置重新開機選項

只有在重新開機裝置設定之後，Teams 會議室裝置設定才能生效。 當您進行需要重新開機的變更時，您可以選擇是否要立即重新開機或排程重新開機。 以下是可用的重新開機選項：

- **立即重新開機** 如果您選擇這個選項，您進行變更的所有裝置都會在選取此選項後立即重新開機。
- **排定的重新開機** 如果您選擇這個選項，您可以重新開機要變更的裝置，同時對貴組織影響較小。
  - **選取日期和時間** - 選擇重新開機裝置的特定日期和時間。 您選取的日期和時間是重新開機之裝置的本地日期和時間。 
  - **將更新保留為夜間重新開機** 裝置會夜間重新開機以執行維護。 您對裝置進行變更時，將會在此重新開機期間進行。

> [!CAUTION]
> Teams 會議室重新開機時使用中的應用程式，在重新開機程式期間將無法使用。 他們將與進行中的會議中斷連接，而且無法加入新的會議。

## <a name="remove-device"></a>移除裝置

當您移除裝置時，裝置會從貴組織移除，而且不會再顯示在系統管理中心Teams 會議室Windows清單中Teams清單中。

如果您移除裝置，但裝置仍以有效的使用者名稱和密碼進行配置，如果裝置再次連接到 Teams 會議室，系統會自動將其重新Microsoft 365清單中。

若要移除一或多個裝置，請執行下列操作：

1. 前往 **Teams裝置**  >  **Teams 會議室Windows**，然後選取您想要移除的裝置。
2. 選取 **移除**。

## <a name="download-device-logs"></a>下載裝置記錄

您可以下載裝置診斷記錄檔案的一份副本 ，如果 Microsoft 支援人員要求這麼做。 記錄檔案會壓縮成 zip 檔案，可從系統管理中心Teams下載。

若要將記錄從Teams 會議室下載到您的電腦，請執行下列操作：

1. 請Teams **上**  >  Teams 會議室裝置Windows，然後選取您想要下載記錄之裝置的名稱。****
1. 選取 **下載裝置記錄**。 裝置記錄可能需要數分鐘的時間才能使用。
1. 選取記錄 **選項卡** ，然後選取診斷檔案下的 **記錄檔案連結**。 包含您裝置診斷記錄檔案的 zip 檔案會下載到瀏覽器的預設下載資料夾。

## <a name="view-device-information"></a>查看裝置資訊

您可以Teams系統管理中心，查看貴組織所有裝置的整體狀態，並個別查看每個裝置的詳細資訊。

### <a name="teams-rooms-system-dashboard"></a>Teams 會議室儀表板

系統Teams 會議室儀表板一目了然地顯示所有裝置的狀態和健康情況。

### <a name="device-details-view"></a>裝置詳細資料檢視

若要查看裝置的詳細資訊，請從裝置清單中選取其名稱。 在詳細資料檢視時，您可以查看下列裝置相關資訊：

- **健康情況** 顯示會議室裝置Teams健康情況。 健康狀態可以是健康 **狀態或****不健康狀態**。
- **離線，因為** 顯示上次Microsoft 365裝置通訊的時間。
- **裝置狀態** 顯示裝置目前 **的狀態：空閒**、Teams **、** Skype **會議** 或 **Ingest**。
- **外設** 顯示連接到您會議室Teams的周邊設備及其健康狀態。 健康狀態可以是已 **連接或****已中斷連接**。
- **健康** 顯示連接到您會議室裝置Teams、網路連接、以狀態登錄所需服務，以及軟體版本資訊的詳細資訊。
- **細節** 顯示製造商資訊、網路 IP 位址，Teams會議室裝置序列/MAC 位址。
- **活動** 顯示過去的會議詳細資料，包括會議日期和時間、參與者人數、持續時間和音訊品質。 有關會議詳細資料的詳細資訊，請參閱本文稍後[](#meeting-activity-details)的會議活動詳細資料一節。
- **歷史** 顯示會議室Teams管理活動的歷程記錄，包括組Teams、裝置重新開機，以及裝置記錄下載連結。

#### <a name="meeting-activity-details"></a>會議活動詳細資料

會議室 **裝置** 詳細Teams中的活動選項卡會顯示裝置一段時間參與的所有會議之高層級和詳細資訊。 在 **活動** 選項卡中，您可以查看會議召開時間、出席會議的參與者人數，以及會議期間的音訊品質。

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Teams會議室裝置活動摘要清單。":::

若要查看特定會議的詳細資訊，請選取您想要進一步說明的會議日期和時間。 如果會議只有兩個參與者，則會看到參與者詳細資料頁面，否則會看到參與者摘要頁面。

##### <a name="participant-summary"></a>參與者摘要

參與者摘要頁面會顯示所有參加會議的參與者。 您可以查看每個參與者何時加入會議、他們的名稱、音訊品質，以及會話期間使用的功能。 若要查看參與者的會話詳細資料，請選取該參與者的會話開始時間。

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="Teams會議室裝置會議詳細資料。":::

##### <a name="participant-details"></a>參與者詳細資料

參與者詳細資料頁面會顯示該參與者會話的端對端診斷資訊。 如下列圖形所示，系統會為參與者和裝置提供裝置Teams 會議室資訊。  **參與者** 與裝置之間的網路診斷Teams 會議室也會提供。 選取您想要詳細資訊之上下文的圖示。 有關其他診斷資訊，請選取進 **一步資料表** 。

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="Teams會議室裝置通話詳細資料。":::
