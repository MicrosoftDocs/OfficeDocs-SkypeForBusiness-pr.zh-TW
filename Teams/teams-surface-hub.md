---
title: 部署適用于 Surface Hub 的 Microsoft 團隊
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: 針對 Surface Hub 設定 Microsoft 團隊的管理員設定。
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 70398d6718268742205181db3fd21bfc01886c0e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235036"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>部署適用于 Surface Hub 的 Microsoft 團隊
======================================

安裝 Surface Hub 的團隊之前, 請務必執行下列動作:

 □請確定符合硬體、作業系統及其他需求。 如需詳細資訊, 請參閱[Microsoft Surface Hub 系統管理中心指南](https://docs.microsoft.com/surface-hub/)。<br>
 □請確定已安裝團隊所需的最低作業系統更新- [KB4343889](https://support.microsoft.com/help/4343889)。<br>
 □ [將團隊授權指派給中心裝置帳戶]。<br>
 □如果您是從商務用 Skype Online 轉換, 請確認已將團隊授權指派給使用者。

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>從 Microsoft 網上商店安裝 Surface Hub 的團隊 

下列指示適用于從 Microsoft 網上商店安裝 Surface Hub 的小組。 
 
1. 啟動 Microsoft Store:<br>
   是. 按一下 [**開始** > **所有應用程式** > **設定**]。<br> 乙. 攻絲**Surface Hub 裝置帳戶、管理**。<br>
   c-clip. 在左邊, 輕觸 [ **app & 功能**] 索引標籤。<br> 希望. 在右側, 請敲擊 [**開啟商店**] 按鈕。 
2. 從 Microsoft 網上商店搜尋*Microsoft 團隊*。 隨即會顯示 [ **Surface Hub** ] 的 Microsoft [小組]。 輕觸 [**取得 app** ] 按鈕即可進行安裝。  
3. 安裝完成後, 請重新開機 Surface Hub。 

> [!NOTE]
> 請勿在 [商店清單] 頁面上敲擊 [**啟動**]。

## <a name="make-teams-the-default-calling-and-meetings-application"></a>將團隊設為預設通話與會議應用程式
 
設定預設通話與會議應用程式原則的選項有兩種: 

- **選項 1**: 透過 USB 金鑰進行設定。 
- **選項 2**: 透過 MDM (例如 Intune) 進行設定。
 
### <a name="option-1-configure-via-usb-key"></a>選項 1: 透過 USB 金鑰進行設定 
 
套件可以在此[下載頁面](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g)上找到。 針對您要安裝的套件挑選合適的專案, 並將其複製到 USB 機碼。 要使用的正確. ppkg 檔案, 取決於您想要套用的預設應用程式原則, 如下所示: 

|電話  |說明  |
|---------|---------|
|0     | [開始] 畫面上的 Skype 偏好 app, [團隊會議] 可供使用        |
|sr-1     | [開始] 畫面上的 [小組偏好] app, 提供 Skype 會議        |
|pplx-2     | [開始] 畫面上的 [團隊專用] 應用程式 (Skype app 無法使用)        |
 
1. 將 USB 金鑰附加至 Surface Hub 裝置。 
2. 在 Surface Hub 裝置上開啟 [**設定**] 應用程式。 
3. 開啟**Surface Hub 裝置帳戶管理**。
4. 開啟 [**裝置管理**]。 
5. 按一下 [**新增或移除預配套件**]。 
6. 按一下 [**新增套件**]。
7. 從下拉式功能表中選取 [**卸除式媒體**] 選項。 
8. 新增先前複製到 USB 金鑰的適當<strong>TeamsRTMMode *. ppkg</strong>封裝。 
9. 重新開機 Surface Hub 裝置。 
10. 裝置重新開機之後, 您應該能夠從 [開始] 畫面啟動 [團隊] app, 然後從行事曆加入會議。 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>選項 2: 透過 MDM (例如 Intune) 進行設定 

使用下列選項, 透過 Intune 設定預設通話與會議應用程式原則。 另請參閱[使用 Intune 部署 Microsoft 團隊的 Surface Hub 應用程式](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/)。

|正在   |值    |說明    |
|----------|---------|---------|
|路徑      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|資料類型 | integer (0-2)   |0-[開始] 畫面上的 Skype 慣用 app, [團隊會議] 可供使用<br>1-[開始] 畫面上的 [團隊喜好] app, 提供 Skype 會議<br>2-[開始] 畫面上的 [團隊專用] 應用程式 (Skype app 無法使用) |
|作業| 取得、設定        |

|正在   |值    |
|----------|---------|
|路徑      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|資料類型 | 字串-將 [團隊應用程式套件識別碼] 設定為**MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!團隊** |
|作業| 取得、設定        |

重新開機 Surface Hub 裝置。 裝置重新開機之後, 您應該能夠從 [開始] 畫面啟動 [團隊] app, 然後從行事曆加入會議。

