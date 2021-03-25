---
title: 在 Surface Hub 上管理 Microsoft Teams 組
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
description: 使用 Microsoft Intune 和 Windows Configuration Designer 管理 Surface Hub 上的 Microsoft Teams 設定
ms.openlocfilehash: 9c16fa4875febd3c9e0a8457626db5e09bf90545
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117381"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>管理 Surface Hub 上的 Microsoft Teams 設定

您可以使用 Windows Configuration Designer 或 Microsoft 端點管理員中的 Microsoft Intune，在 Surface Hub 上管理 Microsoft Teams 設定。 若要變更 Teams 設定，必須具備 Windows Configuration Designer 或 Microsoft Intune 的知識。 有關這些選項的詳細資訊，請參閱下列文章：

- [建立 Windows 10 的部署套件](/windows/configuration/provisioning-packages/provisioning-create-package)
- [什麼是 Microsoft Intune 裝置管理？](/mem/intune/remote-actions/device-management)

如果您只有一些 Surface Hub 裝置，而且您可以輕鬆地存取這些裝置，Windows 組組設計工具是很好的選項。 如果您有許多 Surface Hub，或者它們位於遠端位置，請使用 Microsoft 端點管理員中的 Microsoft Intune ，如果其部署在貴組織中。 無論您選擇哪種方法，您都需要建立 XML 設定檔，以變更 Surface Hub 上的 Teams 設定。

## <a name="teams-configuration-file-syntax"></a>Teams 組設定檔語法

Surface Hub 上的 Teams 組組是使用 XML 檔案定義。 XML 檔案包含可用來控制 Teams 運作方式的所有設定。 Windows Configuration Designer 和 Microsoft Intune 使用相同的 XML 語法。 以下是 Teams 組組 XML 檔案的範例：

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

下表說明組設定檔中所有可用的設定設定：

| 父母                  | 元素                                   | 屬性 | 說明                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 無                    | `<SurfaceHubSettings>`                    |           | 包含 Surface Hub 上 Teams 組的所有組組元素。                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | 決定 Surface Hub 是否宣告它可用於藍牙連接。<br>接受的值 `true` ：， `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | 決定 Teams 是否會自動接受鄰近式會議。<br>接受的值 `true` ：， `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | 包含所有協調會議的配置元素。                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | 決定是否將 Teams 配置為與其他裝置一起參與協調會議。<br>接受的值 `true` ：， `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | 這是每個 Teams 會議室裝置或 Surface Hub 的 UPNs 逗號分隔清單，裝置應接受會議加入邀請，或應該將會議加入邀請寄到哪個位置。<br>接受的值：字串                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | 包含協調會議的配置音訊和視音訊組組元素                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | 控制 Surface Hub 上的 Teams 音訊組。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 決定會議開始時，麥克風會位於哪個裝置上。 只有一 (一般是 Teams 會議室裝置) 可以設定此欄位，而其他裝置必須設定此欄位以避免音訊回音和 `true` `false` 意見回應。<br>接受的值 `true` ：， `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | 決定會議參與者是否可以開啟或關閉麥克風。 設定為 **音訊** 預設值的裝置應設定此設定，讓參與者不會不小心開啟麥克風，並造成 `false` 音訊回 `false` 音或意見回應。<p>如果 **音訊預設值** 設為 `true` ，此設定會被忽略，參與者可以將麥克風設為靜音或取消靜音。<br>接受的值 `true` ：， `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | 在 Surface Hub 上控制 Teams 的視像組組。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 決定會議開始時攝影機會使用哪個裝置。 為了獲得最佳體驗，我們建議您只將 Teams 會議室裝置設定為 ，而所有其他裝置則設為 `true` `false` 。<br>接受的值 `true` ：， `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | 決定會議參與者是否可以開啟或關閉相機。 您可以在活動參與者想要共用不同視 (，例如參與者使用 Surface Hub 白板或 `true`) 。 如果您不希望參與者在裝置上開啟或關閉相機，請將其設定為 `false` 。<p> 如果 **視音訊預設值** 設定為 `true` ，此設定會被忽略，參與者可以開啟或關閉相機。<br>接受的值 `true` ：， `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>將 Teams 設定適用于 Surface Hub

在 Surface Hub 上，使用 Windows 設定設計工具或 Microsoft 端點管理員中的 Microsoft Intune 來申請或更新 Teams 設定設定。

### <a name="use-windows-configuration-designer"></a>使用 Windows 組組設計工具

您可以使用 Windows Configuration Designer 來建立一個設定套件，您可以使用該套件將 Teams 設定套用至 Surface Hub。 您將上述所建立之 XML 檔案貼到 Windows Configuration Designer 中，以建立部署套件。

> [!IMPORTANT]
> 如果您已經使用部署套件將 Teams 組配置套用至 Surface Hub，並想要變更，您需先移除現有的部署套件。 詳細資訊，請參閱移除由 Windows Configuration [Designer 所建立的配置套件](#remove-a-provisioning-package-created-by-windows-configuration-designer)。

請執行下列操作，在 Windows Configuration Designer 中建立部署套件：

1. 從您本地電腦的 Windows 市場安裝 Windows 組組設計工具並開啟
2. 選取 **置備 Surface Hub 裝置** ， **然後切換到進位編輯器**
3. 在下一個畫面上，展開 **WindowsTeamSettings**  >  **Teams，** 然後選取設定
4. 在中間窗格的組 **塊旁的** 欄位中，貼上您上方所建立的單行 XML
5. 選取 **匯出**  >  **置備套件**
6. 在名稱中提供資源配置套件 **的名稱，然後** 選取下 **一**  >  **步**
7. 指定儲存置備套件的位置，然後選取下 **一步**
8. 選取 **建立** 以建立部署 **套件，然後** 選取完成

最後，建立部署套件之後，請執行下列操作，將部署套件套用至 Surface Hub：

1. 將您上述所建立之部署套件儲存至 USB 磁碟機
2. 將 USB 磁碟機插入 Surface Hub
3. 在 Surface Hub 上，開啟開始功能表，選取所有 **應用程式**，然後 **選取設定**
4. 提供您的系統管理員使用者名稱和密碼， **然後選取**
5. 前往 **Surface Hub**、 **裝置管理**、 **新增或移除部署套件**，然後 **新增套件**
6. 在 **選取套件下****，選取您的** 部署套件旁的新增，然後重新開機 Surface Hub

### <a name="use-microsoft-intune"></a>使用 Microsoft Intune

如果您的 Surface Hub 是使用 Microsoft Intune 在 Microsoft 端點管理中管理，您可以使用它來將 Teams 設定適用于您的 Surface Hub。 您將建立一個新的組組設定檔，然後將您上述所建立之 XML 檔案貼到檔案中。

> [!IMPORTANT]
> 您的 Surface Hub 必須位在裝置群組中，Microsoft Intune 才能識別要將組式設定檔適用于哪些裝置。 若要瞭解如何建立裝置群組，請參閱新增 [群組以組織使用者和裝置](/mem/intune/fundamentals/groups-add)。

請執行下列操作來建立設定設定檔，將 Teams 設定適用于您的 Surface Hub：

1. 請流覽以登錄 Microsoft 端點管理員 https://endpoint.microsoft.com/
2. 流覽至 **裝置**  >  **組組設定檔，** 然後選取 **建立設定檔**
3. 在 **平臺下**，選取 **Windows 10 及更新版本**
4. 在 **[設定檔中**， **選取自訂**，然後按一下 **建立**
5. On the **Basics** tab, in **Name**, provide a descriptive name for your configuration profile and select **Next**
6. 在設定 **設定選項卡** 上 **，選取**
7. 在新增 **列窗格中** ，執行下列操作：
    1. 提供您新增之 Teams 設定的描述性名稱，以及選擇性的描述
    2. 在 **OMA-URI** 中，輸入 `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. 在 **資料類型中**，選取 **XML 檔案 (字串)**
    4. 開啟檔案瀏覽器，選取您上述所建立之 XML 檔案，然後 **開啟**
8. 選取 **新增** ，然後選取下 **一步**
9. 在 " **作業"** 選項卡上，確定 **已** 設定為已選取 **的群組**
10. 在 **選取的群組** 下，選取 **要** 包含的群組，然後選擇包含 Surface Hub 的群組，然後 **選取選取**
11. 選取 **下一** 個 ， **下一個**
12. 在評論 **+ 建立上****，選取建立**

## <a name="remove-teams-settings-from-a-surface-hub"></a>從 Surface Hub 移除 Teams 設定

在 Microsoft 端點管理員中，使用 Windows 設定設計工具或 Microsoft Intune 移除 Surface Hub 上的 Teams 設定設定。

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>移除 Windows Configuration Designer 所建立的配置套件

如果您使用 Windows Configuration Designer 所建立的配置套件將 Teams 設定套用至 Surface Hub，請使用下列步驟移除套件及其設定：

1. 在 Surface Hub 上，開啟開始功能表，選取所有 **應用程式**，然後 **選取設定**
2. 提供您的系統管理員使用者名稱和密碼， **然後選取**
3. 前往 **Surface Hub**、 **裝置管理** ，然後 **新增或移除部署套件**
4. 在您想要移除的部署套件旁邊， **選取移除**
5. 前往 **Surface Hub，** 然後 **使用應用程式&功能**
6. 尋找 **Surface Hub 的 Microsoft Teams，** 然後選取進 **位選項**
7. 選取 **重設**，然後 **再次重設**
8. 重新開機 Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>移除 Microsoft Intune 所申請的設定

如果您在 Microsoft 端點管理中使用 Microsoft Intune 將 Teams 設定應用程式至 Surface Hub，請使用下列步驟移除組式設定檔及其設定：

1. 請流覽以登錄 Microsoft 端點管理員 https://endpoint.microsoft.com/
2. 流覽至 **裝置**  >  **組組設定檔**
3. 選取包含您想要移除之協調會議設定的配置設定檔
4. 在設定檔詳細資料頁面上，選取 **刪除** ，然後選取 **確定**

移除包含 Surface Hub 協調會議設定的配置設定檔之後，請使用下列步驟來重設 Surface Hub 上的 Teams 應用程式：

1. 在 Surface Hub 上，開啟開始功能表，選取所有 **應用程式**，然後 **選取設定**
2. 提供您的系統管理員使用者名稱和密碼， **然後選取**
3. 前往 **Surface Hub，** 然後 **使用應用程式&功能**
4. 尋找 **Surface Hub 的 Microsoft Teams，** 然後選取進 **位選項**
5. 選取 **重設**，然後 **再次重設**
6. 重新開機 Surface Hub