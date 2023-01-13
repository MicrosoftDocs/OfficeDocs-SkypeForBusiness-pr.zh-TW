---
title: 針對敏感的 Teams 會議要求浮水印
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: 瞭解如何在敏感的 Teams 會議中啟用或要求出席者視訊和共用內容上的浮水印。
ms.openlocfilehash: 199ba2d84ca4187a7d8e3c4f9a4d471bb9251598
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800254"
---
# <a name="require-a-watermark-for-sensitive-teams-meetings"></a>針對敏感的 Teams 會議要求浮水印

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

您可以在 Teams 會議中針對在螢幕上共用的內容和出席者視訊，啟用浮水印。 浮水印會顯示會議參與者的電子郵件地址。 會議參與者無法關閉浮水印。 

Teams 電腦版、Teams 行動裝置版、Windows 上的 Microsoft Teams 會議室 和 Surface Hub 上的 Microsoft Teams 會議室 都支援浮水印。  (Android 上的 Microsoft Teams 會議室 不支援浮水印。) 人員從不支援的平臺加入會議，包括[雲端視訊 Interop (CVI) ](cloud-video-interop.md)等，將能看到沒有浮水印的內容。

使用浮水印時，下列參與者會有音訊專用體驗：

- 使用 Teams Web 用戶端的參與者
- VDI) 參與者 (虛擬桌面基礎結構
- 匿名參與者
- 溢位參與者

> [!Note]
> 敏感度標籤、自訂會議範本及浮水印中的會議設定需要Teams 進階版。

Teams 系統管理中心會啟用會議浮水印。 會議召集人就可以新增這些專案，也可以使用範本或敏感度標籤強制執行。

下表顯示設定浮水印的位置：

|設定|管理員原則|敏感度標籤|範本|會議召集人|
|:------|:----------:|:---------------:|:------:|:---------------:|
|將浮水印套用至共用內容|是|是|是|是|
|將浮水印套用至每個人的視訊摘要|是|是|是|是|

在會議中使用浮水印時，會關閉下列功能：

- 會議錄製，包括自動錄製

- 大型圖庫

- 共聚模式

- PowerPoint Live

- 白板

- 來自相機的內容

## <a name="watermarks-for-sensitive-and-highly-sensitive-meetings"></a>敏感性與高度敏感性會議的浮水印

浮水印可協助保護會議中共用的機密資訊。 與一般無法存取訊號的人員共用資訊時，此功能最為有用。 例如，財務組織的成員可能會在與不同部門的主管共用每季估算時使用浮水印。

由於浮水印的設計目的是要降低機密資訊被外流的可能性，因此在所有參與者都可直接存取共用內容的會議中使用浮水印，因此可能不會增加安全性。

如需有關搭配其他會議功能使用浮水印來協助保護會議中的機密資訊的相關資訊，請參閱設定 [Teams 會議以保護高度機密資料](/microsoftteams/configure-meetings-highly-sensitive-protection)。

## <a name="enable-watermarks"></a>啟用浮水印

若要在範本和敏感度標籤中使用浮水印，而且會議召集人必須在 Teams 系統管理中心啟用浮水印。

為會議啟用浮水印

1. 在 Teams 系統管理中心中，展開 **[會議]** ，然後選取 **[會議原則]**。

1. 選取您要更新的原則。

1. 若要在出席者視訊上啟用浮水印，請將 **[浮水印] 影片** 設為 **[開啟]**。

1. 若要在會議中共用的內容上啟用浮水印，請將 **[浮水印] 共用內容** 設為 [ **開啟]**。

    ![Teams 浮水印系統管理原則的螢幕擷取畫面](media/watermark-admin-policy.png)

1. 若要查看浮水印在桌上型電腦和行動裝置上的外觀，請選取 **[預覽]**。

1. 選取 [儲存 **]**。

您也可以使用 PowerShell 啟用或停用浮水印。 搭配及參數使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet `-AllowWatermarkForCameraVideo` `-AllowWatermarkForScreenSharing` 。

例如：

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowWatermarkForCameraVideo $True 

Set-CsTeamsMeetingPolicy -Identity Global -AllowWatermarkForScreenSharing $True 
```

## <a name="related-topics"></a>相關主題

[設定具有三層保護層級的 Teams 會議](configure-meetings-three-tiers-protection.md)

[搭配使用 Teams 會議範本、敏感度標籤和系統管理原則來進行敏感性會議](meeting-templates-sensitivity-labels-policies.md)
