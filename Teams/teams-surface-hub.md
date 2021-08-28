---
title: 部署 Microsoft Teams Surface Hub
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: 瞭解如何安裝及設定 Teams 應用程式Surface Hub，Teams通話和會議應用程式。
ms.localizationpriority: medium
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
ms.openlocfilehash: 7b3856dd7cd88626236e370b633663c1e3182bba
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586475"
---
# <a name="deploy-microsoft-teams-for-surface-hub"></a>部署 Microsoft Teams Surface Hub

在安裝 Teams Surface Hub，請務必執行下列操作：

 □確認硬體、作業系統和其他需求都符合。 詳細資訊，請參閱管理Microsoft Surface Hub[指南](/surface-hub/)。<br>
 □請確定已安裝適用于 Teams 的最低作業系統更新 - [KB4343889](https://support.microsoft.com/help/4343889)。<br>
 □指派授權Teams中心裝置帳戶。<br>
 □如果您是從 商務用 Skype Online 轉換，請確認Teams指派授權給使用者。

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>從 Teams Surface Hub安裝Microsoft Store 

這些指示適用于從 Teams Surface Hub安裝Microsoft Store。 
 
1. 啟動Microsoft Store：<br>
   a. 點 **一下啟動**  >  **所有應用程式**  >  **設定。**<br> b. 點 **Surface Hub裝置帳戶、管理**。<br>
   C。 在左側，點& **功能欄** 。<br> D。 在右側，點選 **開啟市面商店** 按鈕。 
2. 從 Microsoft Store，*搜尋* Microsoft Teams。 系統 **Microsoft Teams顯示Surface Hub** 的圖示。 點選 **要安裝的取得應用程式** 按鈕。  
3. 安裝完成後，請重新開機Surface Hub。 

> [!NOTE]
> 請勿從市 **/市** 清單頁面點一下啟動。

## <a name="make-teams-the-default-calling-and-meetings-application"></a>使用Teams通話和會議應用程式
 
有兩個選項可配置預設的通話和會議應用程式策略： 

- **選項 1：** 透過 USB 鍵設定。 
- **選項 2：** 透過 MDM 設定 ，例如 Intune。
 
### <a name="option-1-configure-via-usb-key"></a>選項 1：透過 USB 鍵設定 
 
您可以在此下載頁面上找到 [套件](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g)。 針對您打算安裝並複製到 USB 金鑰的套件，挑選適當的套件。 要使用正確的 .ppkg 檔案，取決於您要採用的預設應用程式原則，如下所示： 

|數量  |描述  |
|---------|---------|
|0     | Skype畫面上的偏好應用程式，Teams會議        |
|1     | Teams畫面上的偏好應用程式，Skype會議        |
|2     | Teams畫面上的專屬應用程式 (Skype應用程式無法)         |
 
1. 將 USB 鍵連接到Surface Hub裝置。 
2. 在 **設定** 開啟 Surface Hub 應用程式。 
3. 開啟 **Surface Hub帳戶管理**。
4. 開啟 **裝置管理**。 
5. 按一下 **[新增或移除置備套件**。 
6. 按一下 **[新增套件**> 。
7. 從 **下拉式功能表選取** 移除媒體選項。 
8. 新增先前複製到 USB 金鑰的適當 <strong>TeamsRTMode*.ppkg</strong> 套件。 
9. 重新開機Surface Hub裝置。 
10. 裝置重新開機後，您應該可以啟動 Teams畫面中的應用程式，然後從日曆加入會議。 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>選項 2：透過 MDM 設定 ，例如 Intune 

使用下列專案透過 Intune 設定預設的通話和會議應用程式策略。 另請參閱使用[Intune Microsoft Teams應用程式Surface Hub的部落格](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/)。

|設定   |值    |描述    |
|----------|---------|---------|
|路徑      | ./廠商/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|資料類型 | 整數 (0-2)    |0 - Skype畫面上的偏好應用程式，Teams會議<br>1 - Teams畫面上的偏好應用程式，Skype會議<br>2 - Teams畫面上的專屬應用程式 (Skype應用程式無法)  |
|營運| 取得、設定        |

|設定   |值    |
|----------|---------|
|路徑      | ./廠商/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|資料類型 | string - 將字串設為Teams套件識別碼做 **為Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe！Teams** |
|營運| 取得、設定        |

重新開機Surface Hub裝置。 裝置重新開機後，您應該可以啟動 Teams畫面中的應用程式，然後從日曆加入會議。