---
title: 管理 Surface Hub 上的 Microsoft 團隊設定
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 使用 Microsoft Intune 和 Windows 配置設計工具管理 Surface Hub 上的 Microsoft 團隊設定
ms.openlocfilehash: 3e254d7f7afbd918e8279d2dc7b100ebbfdc3daf
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761432"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>管理 Surface Hub 上的 Microsoft 團隊設定

您可以在 Microsoft [端點管理員] 中使用 Windows 配置設計工具或 Microsoft Intune 來管理 Surface Hub 上的 Microsoft 團隊設定。 您必須瞭解 Windows 配置設計工具或 Microsoft Intune，才能變更團隊設定。 如需這些選項的詳細資訊，請參閱下列文章：

- [建立適用于 Windows 10 的預配套件](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-create-package)
- [什麼是 Microsoft Intune 裝置管理？](https://docs.microsoft.com/mem/intune/remote-actions/device-management)

如果您只有幾個 Surface 中樞裝置，且您可以輕鬆存取，Windows 配置設計工具就是一個不錯的選擇。 如果您有多個 Surface Hub，或它們位於遠端位置，請在 Microsoft Intune Manager 中使用 Microsoft Intune （如果它是在您的組織中部署的）。 不論您選擇的方法為何，您都必須建立 XML 設定檔，以變更 Surface Hub 上的團隊設定。

## <a name="teams-configuration-file-syntax"></a>小組設定檔語法

Surface Hub 上的團隊設定是使用 XML 檔案定義。 XML 檔案包含可用於控制團隊運作方式的所有設定。 Windows 配置設計工具和 Microsoft Intune 都使用相同的 XML 語法。 以下是團隊配置 XML 檔案的範例：

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

下表說明設定檔中所有可用的配置設定：

| 父                  | 元件                                   | Attribute | 說明                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 無                    | `<SurfaceHubSettings>`                    |           | 包含 Surface Hub 上團隊設定的所有配置元素。                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | 判斷 Surface Hub 是否公佈它提供給藍牙連線。<br>接受的值： `true` ， `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | 決定團隊是否會自動接受鄰近性的會議。<br>接受的值： `true` ， `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | 包含適用于協調會議的所有配置元素。                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | 決定團隊是否已設定為參與與其他裝置的協同會議。<br>接受的值： `true` ， `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | 這是一個以逗號分隔的 Upn 清單，其中包含裝置應接受會議加入要求的每個小組房間裝置或 Surface Hub，或應傳送給哪個會議連接要求。<br>已接受的值： string                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | 包含適用于協調會議的設定音訊與視頻配置元素                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | 控制 Surface Hub 上的團隊音訊設定。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 決定會議開始時麥克風起作用的裝置。 只有一個裝置 (通常是團隊會議室裝置) 可以將此欄位設定為， `true` 而其他裝置必須將此欄位設定為， `false` 以避免音訊回顯和意見反應。<br>接受的值： `true` ， `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | 決定會議中的參與者是否可以開啟或關閉麥克風。 在其上設定 **音訊預設值** 的裝置， `false` 應該將此設定設定為， `false` 讓參與者不會不小心開啟麥克風並導致音訊回音或意見反應。<p>如果 [ **音訊預設值** ] 設定為 `true` ，則會忽略此設定，且參與者可以將麥克風設為靜音或取消靜音。<br>接受的值： `true` ， `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | 控制 Surface Hub 上團隊的影片設定。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 決定會議開始時，相機在哪一個裝置上起作用。 為了獲得最佳體驗，我們建議您只有在 `true` 所有其他裝置都設定為時，才會將小組聊天室裝置設定為 `false` 。<br>接受的值： `true` ， `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | 決定會議中的參與者是否可以開啟或關閉相機。 您可以 `true` 在活動參與者中的任何其他裝置上將此設定為 [共用]， (例如參與者使用 Surface Hub 白板) 。 如果您不希望參與者在裝置上開啟或關閉相機，請將此選項設定為 `false` 。<p> 如果 [ **影片預設值** ] 設定為 `true` ，則會忽略此設定，且參與者可以開啟或關閉相機。<br>接受的值： `true` ， `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>將團隊設定套用至 Surface Hub

使用 Microsoft Endpoint Manager 中的 Windows 配置設計工具或 Microsoft Intune，在 Surface Hub 上套用或更新團隊設定設定。

### <a name="use-windows-configuration-designer"></a>使用 Windows 配置設計工具

您可以使用 Windows 配置設計工具來建立可讓您用來將團隊設定套用至 Surface Hub 的置備套件。 您會將您在上面建立的 XML 檔案貼到 Windows 配置設計工具中，以建立預配套件。

> [!IMPORTANT]
> 如果您已使用預配套件將團隊配置套用至 Surface Hub，且想要變更它，您必須先移除現有的預配套件。 如需詳細資訊，請參閱 [移除 Windows 配置設計工具建立的置備套件](#remove-a-provisioning-package-created-by-windows-configuration-designer)。

請執行下列動作，在 Windows [組態工具設計工具] 中建立預配套件：

1. 從本機電腦上的 Windows 市集中安裝 Windows 配置設計工具，然後開啟該應用程式
2. 選取 [**置備 Surface Hub 裝置**]，然後**切換到 [高級編輯器**]
3. 在下一個畫面中，展開 [ **WindowsTeamSettings**  >  **團隊**]，然後選取**Configurations** [設定]
4. **在中間**窗格的 [設定] 旁的欄位中，貼上您所建立的單行 XML
5. 選取 [**匯出**  >  **預配套件**]
6. 在**名稱**中提供預配套件的名稱，然後選取 **[下**一  >  **步]**
7. 指定儲存預配套件的位置，然後選取 **[下一步]**
8. 選取 [ **建立** ] 以建立預配套件，然後按一下 **[完成]**

最後，在您建立預配套件之後，請執行下列動作，將預配套件套用至 Surface Hub：

1. 將您建立的預配套件儲存至 USB 磁片磁碟機
2. 將 USB 磁片磁碟機插入 Surface Hub
3. 在 Surface Hub 上，開啟 [開始] 功能表，選取 [**所有應用程式**]，然後選取 [**設定**]。
4. 提供您的系統管理員使用者名稱和密碼，然後選取 **[是]**
5. 移至 **Surface Hub**、 **裝置管理**、 **新增或移除預配套件**，然後 **新增套件**
6. 在 [ **選取套件**] 底下，選取您的 [配套件] 旁的 [ **新增** ]，然後重新開機 Surface Hub

### <a name="use-microsoft-intune"></a>使用 Microsoft Intune

如果您的 Surface Hub 是使用 microsoft Intune 管理中的 Microsoft Intune 進行管理，您可以使用它將團隊設定套用到 Surface Hub。 您將會建立新的設定檔，然後貼上您在其中建立的 XML 檔案。

> [!IMPORTANT]
> 您的 Surface Hub 必須位於裝置群組中，才能讓 Microsoft Intune 識別要將設定檔套用到哪些裝置。 如需如何建立裝置群組的相關資訊，請參閱 [新增群組以組織使用者和裝置](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)。

請執行下列動作來建立將團隊設定套用至 Surface Hub 的設定檔：

1. 透過造訪登入 Microsoft 端點管理員 https://endpoint.microsoft.com/
2. 流覽至 [**裝置**設定] 配置  >  **檔**，然後選取 [**建立設定檔**]
3. 在 [**平臺**] 底下，選取 [ **Windows 10 及更新版本**]
4. 選取 [**設定檔**] 底下的 [**自訂**]，然後按一下 [**建立**]
5. 在 [ **基本** 功能] 索引標籤上的 [ **名稱**] 中，為您的配置設定檔提供描述名稱，然後選取 **[**
6. 在 [**設定設定**] 索引標籤上，選取 [**新增**]
7. 在 [ **Add row] （新增列** ）窗格中，執行下列動作：
    1. 提供描述性的名稱，以及選擇您要新增之團隊設定的描述
    2. 在 **OMA URI**中，輸入 `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. 在 [**資料類型**] 中，選取 [**字串 (XML**檔案]) 
    4. 開啟 [檔案瀏覽器]，選取您在上述建立的 XML 檔案，然後 **開啟**
8. 選取 [ **新增** ]，然後選取 **下一步**
9. 在 [**作業**] 索引標籤上，確認 [**指派至**] 已設定為 [**選取的群組**]
10. 在 [**選取的群組**] 底下，選取 [**選取要包含的群組**]，然後選擇內含 Surface hub 的群組，然後選取 [**選取**]
11. 選取 **[下一**步 **]，接著**
12. 在 [**評論 + 建立**] 上，選取 [**建立**]

## <a name="remove-teams-settings-from-a-surface-hub"></a>從 Surface Hub 移除團隊設定

使用 Microsoft Endpoint Manager 中的 Windows 配置設計工具或 Microsoft Intune，在 Surface Hub 上移除團隊設定設定。

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>移除 Windows 配置設計工具所建立的置備套件

如果您使用 Windows 配置設計工具建立的置備套件將團隊設定套用至 Surface Hub，請使用下列步驟移除套件及其設定：

1. 在 Surface Hub 上，開啟 [開始] 功能表，選取 [**所有應用程式**]，然後選取 [**設定**]。
2. 提供您的系統管理員使用者名稱和密碼，然後選取 **[是]**
3. 移至 **Surface Hub**、 **裝置管理** ，然後 **新增或移除預配套件**
4. 在您要移除的預配套件旁邊，選取 [**移除**]
5. 移至 **Surface Hub** ，然後 **應用程式 & 功能**
6. 尋找 [ **Surface Hub 的 Microsoft 團隊**]，然後選取 [**高級選項**]
7. 選取 [**重設**]，然後再次**重設**
8. 重新開機 Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>移除 Microsoft Intune 套用的設定

如果您在 Microsoft 端點管理中使用 Microsoft Intune 將團隊設定套用至 Surface Hub，請使用下列步驟移除設定檔及其設定：

1. 透過造訪登入 Microsoft 端點管理員 https://endpoint.microsoft.com/
2. 流覽至**裝置**  >  **設定檔**
3. 選取包含您要移除之協調會議設定的設定檔
4. 在 [設定檔詳細資料] 頁面上，選取 [ **刪除** ]，然後選取 **[確定]**

移除包含 Surface Hub 之共同會議設定的設定檔後，請使用下列步驟重設 Surface Hub 上的團隊應用程式：

1. 在 Surface Hub 上，開啟 [開始] 功能表，選取 [**所有應用程式**]，然後選取 [**設定**]。
2. 提供您的系統管理員使用者名稱和密碼，然後選取 **[是]**
3. 移至 **Surface Hub** ，然後 **應用程式 & 功能**
4. 尋找 [ **Surface Hub 的 Microsoft 團隊**]，然後選取 [**高級選項**]
5. 選取 [**重設**]，然後再次**重設**
6. 重新開機 Surface Hub