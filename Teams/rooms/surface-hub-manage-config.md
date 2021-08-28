---
title: 在 Microsoft Teams 管理Surface Hub
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
ms.localizationpriority: medium
description: 使用Microsoft Teams設定Surface Hub管理Microsoft Intune Windows設定
ms.openlocfilehash: 39d62296a87fa50722bce98a4fcd5e0372b362cc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602158"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>管理Microsoft Teams上的Surface Hub設定Surface Hub

您可以使用設定設計Microsoft Teams管理Surface Hub上的Windows設定Microsoft Intune或Microsoft 端點管理員。 若要變更Windows設定，Microsoft Intune需要具備設定設計工具或Teams知識。 有關這些選項的詳細資訊，請參閱下列文章：

- [建立適用于您Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package)
- [什麼是Microsoft Intune管理？](/mem/intune/remote-actions/device-management)

Windows如果您只有一些裝置，而且您Surface Hub，則組Surface Hub設計工具是很好的選項。 如果您有許多 Surface Hub，或者它們位於遠端位置，請使用 Microsoft Intune Microsoft 端點管理員部署在貴組織中。 無論您選擇哪種方法，您都需要建立 XML 設定檔，以變更 Teams 上的Surface Hub。

## <a name="teams-configuration-file-syntax"></a>Teams組設定檔語法

Teams上的Surface Hub是使用 XML 檔案定義。 XML 檔案包含可用來控制其運作方式Teams設定。 組Windows設計工具Microsoft Intune使用相同的 XML 語法。 以下是組Teams XML 檔案的範例：

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

下表說明設定檔中所有可用的設定設定：

| 父母                  | 元素                                   | 屬性 | 描述                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 無                    | `<SurfaceHubSettings>`                    |           | 包含所有組Teams組Surface Hub。                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | 判斷Surface Hub是否可藍牙連結。<br>接受的值 `true` ：， `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | 決定Teams是否會自動接受鄰近型會議。<br>接受的值 `true` ：， `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | 包含所有協調會議的配置元素。                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | 決定是否Teams其他裝置參與協調會議。<br>接受的值 `true` ：， `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | 這是每個 Teams 會議室裝置或 Surface Hub 裝置應接受會議加入邀請，或應該將會議加入邀請寄到哪個會議加入邀請的 UPN 逗號分隔清單。<br>接受的值：字串                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | 包含協調會議的配置音訊和視音訊組組元素                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | 控制Teams上Surface Hub的音訊Surface Hub。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 決定會議開始時，麥克風會位於哪個裝置上。 只有一 (裝置Teams 會議室裝置) 可以設定此欄位，而其他裝置必須設定此欄位以避免音訊回音和 `true` `false` 意見回應。<br>接受的值 `true` ：， `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | 決定會議參與者是否可以開啟或關閉麥克風。 設定為 **音訊** 預設值的裝置應設定此設定，讓參與者不會不小心開啟麥克風，並造成 `false` 音訊回 `false` 音或意見回應。<p>如果 **音訊預設值** 設為 `true` ，此設定會被忽略，參與者可以將麥克風設為靜音或取消靜音。<br>接受的值 `true` ：， `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | 控制視Teams視Surface Hub。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 決定會議開始時攝影機會使用哪個裝置。 為了獲得最佳體驗，我們建議您只將Teams 會議室設定為 ，而所有其他裝置都設為 `true` `false` 。<br>接受的值 `true` ：， `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | 決定會議參與者是否可以開啟或關閉相機。 您可以在活動參與者想要共用不同視 (，例如參與者使用 Surface Hub 白板 `true`) 。 如果您不希望參與者在裝置上開啟或關閉相機，請將其設定為 `false` 。<p> 如果 **視音訊預設值** 設定為 `true` ，此設定會被忽略，參與者可以開啟或關閉相機。<br>接受的值 `true` ：， `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>將Teams設定Surface Hub

在系統Teams或更新Surface Hub設定設定Windows或Microsoft Intune設定Microsoft 端點管理員。

### <a name="use-windows-configuration-designer"></a>使用 Windows設計工具

您可以使用設定Windows來建立一個設定套件，您可以使用該套件將Teams套用至 Surface Hub。 您將上述所建立之 XML 檔案貼到Windows設計工具中，以建立資源配置套件。

> [!IMPORTANT]
> 如果您已經使用Teams套件將Surface Hub套用至您的部署套件，並想要變更，您需先移除現有的部署套件。 詳細資訊，請參閱移除由組Windows[所建立的配置套件](#remove-a-provisioning-package-created-by-windows-configuration-designer)。

請執行下列操作，在組Windows建立套件：

1. 從Windows市Windows安裝組Windows設計工具並開啟
2. 選取 **Surface Hub裝置，****然後切換到進位編輯器**
3. 在下一個畫面上，展開 **WindowsTeamSettings**  >  **Teams** 並選取設定
4. 在中間窗格的組 **塊旁的** 欄位中，貼上您上方所建立的單行 XML
5. 選取 **匯出**  >  **置備套件**
6. 在名稱中提供資源配置套件 **的名稱，然後** 選取下 **一**  >  **步**
7. 指定儲存置備套件的位置，然後選取下 **一步**
8. 選取 **建立** 以建立部署 **套件，然後** 選取完成

最後，在您建立部署套件之後，請執行下列操作，將部署套件套用至您的Surface Hub：

1. 將您上述所建立之部署套件儲存到 USB 磁碟機
2. 將 USB 磁碟機插入您的Surface Hub
3. 在 Surface Hub上，開啟 [開始] 功能表，選取所有 **應用程式**，**然後選取** 設定
4. 提供您的系統管理員使用者名稱和密碼， **然後選取**
5. 請前往 **Surface Hub**、**裝置管理**、**新增或移除部署套件**，然後 **新增套件**
6. 在 **選取套件下****，選取您的** 部署套件旁的新增，然後重新開機Surface Hub

### <a name="use-microsoft-intune"></a>使用Microsoft Intune

如果您的 Surface Hub 是使用 Microsoft 端點管理中的 Microsoft Intune管理，您可以使用它來將 Teams設定適用于您的 Surface Hub。 您將建立一個新的組組設定檔，然後將您上述所建立之 XML 檔案貼到檔案中。

> [!IMPORTANT]
> 您的 Surface Hub 必須位在裝置群組中，Microsoft Intune識別要將組式設定檔用於哪些裝置。 若要瞭解如何建立裝置群組，請參閱新增 [群組以組織使用者和裝置](/mem/intune/fundamentals/groups-add)。

執行下列操作以建立設定設定檔，Teams Surface Hub：

1. 請流覽以Microsoft 端點管理員帳戶https://endpoint.microsoft.com/
2. 流覽至 **裝置**  >  **組組設定檔，** 然後選取 **建立設定檔**
3. 在 **平臺** 下，Windows 10 **及稍後**
4. 在 **[設定檔中**， **選取自訂**，然後按一下 **建立**
5. On the **Basics** tab, in **Name**, provide a descriptive name for your configuration profile and select **Next**
6. 在設定 **設定選項卡** 上 **，選取**
7. 在新增 **列窗格中** ，執行下列操作：
    1. 提供描述性名稱，並選擇性地提供Teams新增之設定的描述
    2. 在 **OMA-URI** 中，輸入 `./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. 在 **資料類型中**，選取 **XML 檔案 (字串)**
    4. 開啟檔案瀏覽器，選取您上述所建立之 XML 檔案，然後 **開啟**
8. 選取 **新增** ，然後選取下 **一步**
9. 在 " **作業"** 選項卡上，確定 **已** 設定為已選取 **的群組**
10. 在 **選取的群組** 下，選取 **要** 包含的群組，然後選擇包含 Surface Hub 的群組，然後 **選取選取**
11. 選取 **下一** 個 ， **下一個**
12. 在評論 **+ 建立上****，選取建立**

## <a name="remove-teams-settings-from-a-surface-hub"></a>從Teams移除Surface Hub

在 Teams上移除Surface Hub設定設定Windows設定設計工具Microsoft Intune或Microsoft 端點管理員。

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>移除由組Windows建立的配置套件

如果您使用 Teams設定Surface Hub組組設計工具所建立Windows套件，請使用下列步驟移除套件及其設定：

1. 在 Surface Hub上，開啟 [開始] 功能表，選取所有 **應用程式**，**然後選取** 設定
2. 提供您的系統管理員使用者名稱和密碼， **然後選取**
3. 請前往 **Surface Hub** 裝置 **管理**，然後 **新增或移除資源調配套件**
4. 在您想要移除的置備套件旁邊， **選取移除**
5. 前往應用程式 **Surface Hub****應用程式&功能**
6. 尋找 **Microsoft Teams選項Surface Hub，** 然後選取進 **一Surface Hub選項**
7. 選取 **重** 設，然後 **再次重設**
8. 重新開機Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>移除應用程式所Microsoft Intune

如果您在 Microsoft 端點管理Teams將Surface Hub設定Microsoft Intune至系統，請使用下列步驟移除設定設定檔及其設定：

1. 請流覽以Microsoft 端點管理員帳戶https://endpoint.microsoft.com/
2. 流覽至 **裝置**  >  **組組設定檔**
3. 選取包含您想要移除之協調會議設定的配置設定檔
4. 在組設定檔詳細資料頁面上，選取 **刪除** ，然後選取 **確定**

移除包含您 Surface Hub 協調會議設定的配置設定檔之後，請使用下列步驟重設 Teams 應用程式Surface Hub：

1. 在 Surface Hub上，開啟[開始] 功能表，選取所有 **應用程式**，**然後選取** 設定
2. 提供您的系統管理員使用者名稱和密碼， **然後選取**
3. 前往應用程式 **Surface Hub****應用程式&功能**
4. 尋找 **Microsoft Teams選項Surface Hub，** 然後選取進 **一Surface Hub選項**
5. 選取 **重** 設，然後 **再次重設**
6. 重新開機Surface Hub