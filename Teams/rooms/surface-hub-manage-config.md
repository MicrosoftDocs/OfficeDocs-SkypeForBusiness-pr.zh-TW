---
title: 在 Surface Hub 上管理 Microsoft Teams 設定
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 使用 Microsoft Intune 和 Windows 設定設計工具在 Surface Hub 上管理 Microsoft Teams 設定
ms.openlocfilehash: 6e99922ebb7bb30db1b5e94fd1a4d30b8ec653b8
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272208"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>在 Surface Hub 上管理 Microsoft Teams 設定

您可以使用 Windows 設定設計工具或 Microsoft 端點管理員 中的Microsoft Intune，在 Surface Hub 上管理 Microsoft Teams 設定。 您必須瞭解 Windows 設定設計工具或Microsoft Intune，才能對 Teams 設定進行變更。 如需這些選項的詳細資訊，請參閱下列文章：

- [建立Windows 10的布建套件](/windows/configuration/provisioning-packages/provisioning-create-package)
- [什麼是Microsoft Intune裝置管理？](/mem/intune/remote-actions/device-management)

如果您只有少數幾個 Surface Hub 裝置且可以輕鬆存取，Windows 設定設計工具是不錯的選擇。 如果您有許多 Surface Hub，或者它們位於遠端位置，請在 Microsoft 端點管理員 中使用Microsoft Intune，如果它部署在您的組織中。 無論您選擇哪種方法，您都需要建立 XML 組態檔來變更 Surface Hub 上的 Teams 設定。

## <a name="teams-configuration-file-syntax"></a>Teams 組態檔語法

Surface Hub 上的 Teams 設定是使用 XML 檔案定義。 XML 檔案包含所有可用來控制 Teams 運作方式的設定。 Windows 設定設計工具和Microsoft Intune使用相同的 XML 語法。 以下是 Teams 設定 XML 檔案的範例：

```xml
<SurfaceHubSettings>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <AutoAcceptProximateMeetingInvitations>true</AutoAcceptProximateMeetingInvitations>
    <CoordinatedMeetings enabled="true"> 
        <TrustedAccounts>room@contoso.com</TrustedAccounts>
        <Settings> 
            <Audio default="false" enabled="false" />
            <Video default="false" enabled="true" /> 
        </Settings> 
    </CoordinatedMeetings>
</SurfaceHubSettings>
```

下表說明組態檔中所有可用的組態設定：

| 父母                  | 元素                                   | 屬性 | 描述                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 無                    | `<SurfaceHubSettings>`                    |           | 包含 Surface Hub 上 Teams 設定的所有組態元素。                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | 判斷 Surface Hub 是否公告其適用于藍牙連線。<br>公認的值： `true``false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | 決定 Teams 是否會自動接受近接式會議。<br>公認的值： `true``false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | 包含協調會議的所有組態元素。                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | 判斷 Teams 是否設定為與其他裝置參與協調會議。<br>公認的值： `true``false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | 這是每個 Teams 會議室裝置或 Surface Hub 的逗號分隔 UPN 清單，裝置應接受會議加入邀請，或應傳送會議加入要求。<br>公認的值：字串                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | 包含協調會議的設定音訊和視訊組態元素                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | 控制 Surface Hub 上 Teams 的音訊設定。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 決定當會議開始時，麥克風會在哪個裝置上作用中。 通常只有一個裝置 (Teams 會議室裝置) 可以將此欄位設定為 `true` ，而其他裝置必須設定此欄位，以避免 `false` 音訊回音和意見反應。<br>公認的值： `true``false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | 判斷會議中的參與者是否可以開啟或關閉麥克風。 設為 `false` **Audio 預設** 值的裝置應將此設定設為 `false` ，讓參與者無法意外開啟麥克風並造成音訊回音或意見反應。<p>如果 **音訊預設** 值設為 `true` ，此設定會被忽略，參與者可以將麥克風設為靜音或取消靜音。<br>公認的值： `true``false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | 控制 Surface Hub 上 Teams 的視訊設定。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 決定會議開始時相機會在哪個裝置上使用。 為獲得最佳體驗，建議您在所有其他裝置都設 `false` 為 `true` 時，只設定Teams 會議室裝置。<br>公認的值： `true``false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | 判斷會議中的參與者是否可以開啟或關閉相機。 您可以將此設定在 `true` 活動參與者想要分享不同視訊觀點的任何其他裝置上， (例如參與者正在使用 Surface Hub 白板) 。 如果您不希望參與者在裝置上開啟或關閉相機，請將此設定設為 `false` 。<p> 如果 **[視訊] 預設** 值設為 `true` ，則會忽略此設定，且參與者可以開啟或關閉相機。<br>公認的值： `true``false` |

## <a name="apply-teams-settings-to-surface-hub"></a>將 Teams 設定套用至 Surface Hub

在 Microsoft 端點管理員 中使用 Windows 設定設計工具或Microsoft Intune，在 Surface Hub 上套用或更新 Teams 設定。

### <a name="use-windows-configuration-designer"></a>使用 Windows 設定設計工具

您可以使用 Windows 設定設計工具來建立布建套件，以便用來將 Teams 設定套用到 Surface Hub。 您將將上述建立的 XML 檔案貼到 Windows 設定設計工具中，以建立布建套件。

> [!IMPORTANT]
> 如果您已經使用布建套件將 Teams 設定套用到 Surface Hub，而且想要變更，您必須先移除現有的布建套件。 如需詳細資訊，請參閱 [移除由 Windows 設定設計工具建立的布建套件](#remove-a-provisioning-package-created-by-windows-configuration-designer)。

請執行下列動作以在 Windows 設定設計工具中建立布建套件：

1. 在本機電腦上從 Windows 市集安裝 Windows 設定設計工具並開啟它
2. 選 **取 [布建 Surface Hub 裝置** ]，然後 **切換到進階編輯器**
3. 在下一個畫面上，展開 **[WindowsTeamSettings Teams]**  >  ，然後選取 [**設定]** ****
4. 在中間窗格中 [設定] 旁邊 **的** 欄位中，貼上您在上方建立的 XML 單一線條
5. 選 **取 [匯出**  >  **布建套件]**
6. 在 [**名稱**] 中提供布建套件的名稱，然後選取 **[下一步**  >  **]**
7. 指定儲存布建套件的位置，然後選取 [ **下一步]**
8. 選 **取 [組建** ] 以建立布建套件，然後選取 [ **完成]**

最後，在您建立布建套件之後，請執行下列動作，將布建套件套件套用到 Surface Hub：

1. 將您于上述建立的布建套件儲存到 USB 磁片磁碟機
2. 將 USB 磁片磁碟機插入 Surface Hub
3. 在 Surface Hub 上，開啟 [開始] 功能表，選取 **[所有應用程式**]，然後選取 [ **設定]**
4. 提供您的系統管理員使用者名稱和密碼，然後選取 [ **是]**
5. 移至 **[Surface Hub**]、[ **裝置管理]**、 **[新增或移除布建套** 件]，然後 **[新增套件]**
6. 在 **[選取包裹**] 底下，選取布建套件旁的 [ **新增** ]，然後重新開機 Surface Hub

### <a name="use-microsoft-intune"></a>使用 Microsoft Intune

如果您的 Surface Hub 是使用 Microsoft 端點管理中的Microsoft Intune來管理，您可以使用它來將 Teams 設定套用到 Surface Hub。 您將建立新的組態設定檔，然後將您在上面建立的 XML 檔案貼到其中。

> [!IMPORTANT]
> 您的 Surface Hub 必須位於裝置群組中，Microsoft Intune才能識別要套用組態設定檔的裝置。 如需如何建立裝置群組的相關資訊，請參閱 [新增群組來組織使用者和裝置](/mem/intune/fundamentals/groups-add)。

執行下列動作以建立設定設定檔，以將 Teams 設定套用至 Surface Hub：

1. 流覽以登入 Microsoft 端點管理員https://endpoint.microsoft.com/
2. 流覽至 **[裝置**  >  **設定] 設定檔，** 然後選取 **[建立設定檔]**
3. 在 [**平臺]** 底下，選 **取 [Windows 10及更新版本]**
4. 在 **[設定檔**] 底下，選取 [ **自訂**]，然後按一下 [ **建立]**
5. 在 [ **基本功能] 索引** 標籤的 [ **名稱**] 中，為您的組態設定檔提供描述性名稱，然後選取 [ **下一步]**
6. 在 [ **設定設定] 索引標籤上** ，選取 [ **新增]**
7. 在 [ **新增列** ] 窗格中，執行下列動作：
    1. 提供描述性名稱，並選擇性地提供您要新增的 Teams 設定描述
    2. 在 **OMA-URI 中**，輸入 `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. 在 **[資料類型]** 中，選 **取 [字串 (XML 檔案)**
    4. 開啟檔案瀏覽器，選取您在上面建立的 XML 檔案，然後 **開** 啟
8. 選取 **[新增** ]，然後選取 **[下一步]**
9. 在 [ **作業] 索引標籤上** ，確定 [ **指派至** ] 已設定為 [ **選取的群組]**
10. 在 **[選取的群組**] 底下，**選取 [選取要包含的群組**]，然後選擇包含 Surface Hub 的群組，然後選取 **[選取**]
11. 選取 **[下一步****]、[下一步]**
12. 在 [ **校閱 + 建立]** 上，選取 [ **建立]**

## <a name="remove-teams-settings-from-a-surface-hub"></a>從 Surface Hub 移除 Teams 設定

在 Microsoft 端點管理員 中使用 Windows 設定設計工具或Microsoft Intune，移除 Surface Hub 上的 Teams 設定設定。

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>移除由 Windows 設定設計工具建立的布建套件

如果您使用 Windows 設定設計工具所建立的布建套件，將 Teams 設定套用到 Surface Hub，請使用下列步驟來移除套件及其設定：

1. 在 Surface Hub 上，開啟 [開始] 功能表，選取 **[所有應用程式**]，然後選取 [ **設定]**
2. 提供您的系統管理員使用者名稱和密碼，然後選取 [ **是]**
3. 移至 **Surface Hub**、 **裝置管理** ，然後 **新增或移除布建套件**
4. 在您要移除的布建套件旁邊，選 **取 [移除]**
5. 移至 **Surface Hub** ，然後 **移至應用程式&功能**
6. 尋找 **Surface Hub 版 Microsoft Teams** ，然後選取 [ **進階選項]**
7. 選取 **[重設**]，然後再次 **選取 [重設** ]
8. 重新開機 Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>移除Microsoft Intune套用的設定

如果您在 Microsoft 端點管理中使用 Microsoft Intune 將 Teams 設定套用至 Surface Hub，請使用下列步驟移除組態設定檔及其設定：

1. 流覽以登入 Microsoft 端點管理員https://endpoint.microsoft.com/
2. 流覽至 **裝置**  >  **設定設定檔**
3. 選取包含您要移除之 [協調會議] 設定的組態設定檔
4. 在 [設定設定檔詳細資料] 頁面上，選 **取 [刪除** ]，然後選取 [ **確定]**

移除 Surface Hub 中包含 [協調會議] 設定的組態設定檔之後，請使用下列步驟在 Surface Hub 上重設 Teams 應用程式：

1. 在 Surface Hub 上，開啟 [開始] 功能表，選取 **[所有應用程式**]，然後選取 [ **設定]**
2. 提供您的系統管理員使用者名稱和密碼，然後選取 [ **是]**
3. 移至 **Surface Hub** ，然後 **移至應用程式&功能**
4. 尋找 **Surface Hub 版 Microsoft Teams** ，然後選取 [ **進階選項]**
5. 選取 **[重設**]，然後再次 **選取 [重設** ]
6. 重新開機 Surface Hub
