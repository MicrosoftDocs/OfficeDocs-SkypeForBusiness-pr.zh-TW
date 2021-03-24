---
title: 部署 Surface Hub 的 Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: 瞭解如何安裝和設定 Surface Hub 的 Teams 應用程式，讓 Teams 成為預設的通話和會議應用程式。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Devices
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 38202fcbb4c2147baae3f745bc2455da6fdff3e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093933"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>部署 Surface Hub 的 Microsoft Teams
======================================

安裝 Surface Hub 的 Teams 之前，請務必執行下列操作：

 □確認硬體、作業系統和其他需求都符合。 詳細資訊，請參閱 Microsoft [Surface Hub 系統管理指南](/surface-hub/)。<br>
 □確認已安裝 Teams 所需的最低作業系統更新 - [KB4343889](https://support.microsoft.com/help/4343889)。<br>
 □指派 Teams 授權至中樞裝置帳戶。<br>
 □如果您是從商務用 Skype Online 轉場，請確認已指派 Teams 授權給使用者。

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>從 Microsoft Store 安裝 Surface Hub 的 Teams 

這些指示適用于從 Microsoft Store 安裝 Surface Hub 的 Teams。 
 
1. 啟動 Microsoft Store：<br>
   a. 點 **一下啟動**  >  **所有應用程式**  >  **設定**。<br> b. 點 **一下 Surface Hub 裝置帳戶、管理**。<br>
   C。 在左側，點& **功能欄** 。<br> D。 在右側，點選 **開啟市面商店** 按鈕。 
2. 從 Microsoft Store 搜尋 *Microsoft Teams*。 **系統會顯示 Surface Hub 的 Microsoft Teams。** 點選 **要安裝的取得應用程式** 按鈕。  
3. 安裝完成後，請重新開機 Surface Hub。 

> [!NOTE]
> 請勿從市 **/市** 清單頁面點一下啟動。

## <a name="make-teams-the-default-calling-and-meetings-application"></a>將 Teams 做為預設的通話和會議應用程式
 
有兩個選項可針對預設通話和會議應用程式策略進行配置： 

- **選項 1：** 透過 USB 鍵設定。 
- **選項 2：** 透過 MDM 設定 ，例如 Intune。
 
### <a name="option-1-configure-via-usb-key"></a>選項 1：透過 USB 鍵設定 
 
您可以在此下載頁面上找到 [套件](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g)。 針對您打算安裝並複製到 USB 金鑰的套件，挑選適當的套件。 要使用正確的 .ppkg 檔案，取決於您要採用的預設應用程式原則，如下所示： 

|數量  |說明  |
|---------|---------|
|0     | 啟動畫面上的 Skype 偏好應用程式，提供 Teams 會議        |
|1     | Teams 偏好應用程式在啟動畫面上，提供 Skype 會議        |
|2     | Skype 應用程式無法 (開始畫面上的 Teams 專屬應用程式)         |
 
1. 將 USB 鍵附加到 Surface Hub 裝置。 
2. 在 Surface **Hub** 裝置上開啟設定應用程式。 
3. 開啟 **Surface Hub 裝置帳戶管理**。
4. 開啟 **裝置管理**。 
5. 按一下 **[新增或移除置備套件**。 
6. 按一下 **[新增套件**> 。
7. 從 **下拉式功能表選取** 移除媒體選項。 
8. 新增先前複製到 USB 金鑰的適當 <strong>TeamsRTMode*.ppkg</strong> 套件。 
9. 重新開機 Surface Hub 裝置。 
10. 裝置重新開機後，您應該能夠從開始畫面啟動 Teams 應用程式，然後從日曆加入會議。 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>選項 2：透過 MDM 設定 ，例如 Intune 

使用下列專案透過 Intune 設定預設的通話和會議應用程式策略。 另請參閱使用 Intune 部署 [Microsoft Teams for Surface Hub App 的部落格](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/)。

|設定   |值    |說明    |
|----------|---------|---------|
|路徑      | ./廠商/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|資料類型 | 整數 (0-2)    |0 - 啟動畫面上的 Skype 偏好應用程式，Teams 會議可用<br>1 - 啟動畫面上的 Teams 偏好應用程式，提供 Skype 會議<br>2 - 啟動畫面上的 Teams 專屬應用程式 (Skype 應用程式無法)  |
|營運| 取得、設定        |

|設定   |值    |
|----------|---------|
|路徑      | ./廠商/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|資料類型 | string - 將字串設定為 Teams 應用程式套件識別碼做 **為Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe！Teams** |
|營運| 取得、設定        |

重新開機 Surface Hub 裝置。 裝置重新開機後，您應該能夠從開始畫面啟動 Teams 應用程式，然後從日曆加入會議。