---
title: 商務用 Skype 用戶端影片解析度
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: 摘要：在規劃商務用 Skype Server 時，複查用戶端的影片需求。
ms.openlocfilehash: 717813e9ed667bbd0d3d9d63e45ae3b9c45b4dcf
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856550"
---
# <a name="skype-for-business-client-video-resolutions"></a>商務用 Skype 用戶端影片解析度
 
**摘要：** 在規劃商務用 Skype Server 時，請複查用戶端影片的需求。
  
本文說明商務用 Skype 影片通話的影片硬體支援，並說明如何判斷各種電腦、平板電腦及行動裝置設定的預期影片品質。 
  
IT 專業人員會發現此資訊有助於評估已在組織中使用的膝上型電腦適用性，或考慮使用。 他們也可以在[Microsoft Teams 裝置](https://www.microsoft.com/microsoft-teams/across-devices/device)上搜尋特定裝置的詳細資訊。
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Windows 桌面、Mac 和平板電腦影片的需求和功能

商務用 Skype 會使用硬體加速進行影片編碼，並根據 h-p/MPEG-4 第10部分的第10個高級視頻編碼標準來進行影片編碼和解碼。 這可讓具有較低 CPU 時脈速度的電腦編碼和解碼較高解析度的影片。 影片硬體需求會因電腦設定和影片解析度的需要而異。
  
另請參閱[Windows 和 Mac 硬體需求](https://products.office.com/office-system-requirements)。
  
### <a name="video-hardware-requirements"></a>影片硬體需求

|**功能**|**需求**|
|:-----|:-----|
|使用 DirectX 影片加速 (DXVA) 硬體加速的 .H 解碼  <br/> |•圖形卡必須支援 DirectX 9.0，且必須公開 DXVA2_ModeH264_VLD_NoFGT 解碼模式和 DirectX 9 API。  <br/> •必須安裝最新的圖形卡驅動程式。  <br/> |
|硬體加速的 H-p 編碼：晶片組需求  <br/> |下列為支援的 Intel 硬體加速視頻編碼方案：  <br/> •第二個和第三代的 Intel HD Graphics 2000、2500、3000及4000晶片組 (或更新版本) 整合的硬體視頻編碼器。 需要安裝 Intel HD Graphics 驅動程式15.28.9.2884 或最新的驅動程式，其中包含下列各項：  <br/> •顯示驅動程式9.17.10.2884 或最新的驅動程式  <br/> •硬體媒體基礎轉換 (HMFT) 版本3.12.10.31 或最新 HMFT  <br/> 支援下列 AMD 硬體加速影片編碼方案：  <br/> • AMD Video 編解碼器引擎，可在許多獨立的圖形卡中，以及 AMD A Series 加速處理器的整合式加速處理單位。 9.12.0.0 或更新版本必須安裝 AMD Video 編解碼器引擎驅動程式。  <br/> |
|硬體加速的 H-p 編碼：攝像頭需求  <br/> |帶有整合的 H-p 硬體編碼器的 USB 影片相機，其符合 USB Video 類別 (UVC) 規格版本1.5。  <br/> **附注：** 商務用 Skype 支援具有 Windows 8 或 Windows 8.1 的 UVC 1.5 攝像頭，其中包含 UVC 1.5 的支援。 因為 Windows 7 不包含支援 UVC 1.5，所以商務用 Skype 會將 UVC 1.5 相機視為不含硬體編碼支援的一般攝像頭。 <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>決定 H-p 影片的編碼和解碼功能

一般來說，有四個主要因素會決定特定電腦設定的最大編碼和解碼功能：
  
- 使用 DXVA 支援硬體加速解碼
    
- 硬體加速編碼支援
    
- 實體核心數目
    
- WindowsWEI 的經驗索引 () 
    
Windows 系統評定工具 (WinSAT) 決定 WEI。 當您執行 WinSAT 工具時，它會在%windir%\Performance\WinSAT\DataStore 目錄的電腦上產生正規的評估 XML 檔。 此 XML 檔包含下列兩個分數，尤其是決定編碼和解碼功能的特別重要性：
  
- VideoEncodeScore 指出電腦的軟體型影片功能。
    
- GraphicsScore 值表示電腦的硬體加速編碼功能。
    
下列三個表格針對不同的電腦類型，根據其所支援的硬體加速度，說明其編碼和解碼功能的上限。 針對640x360 及更高版本，支援的框架速率上限為每秒30個畫面 (fps) 。 對於低於640x360 的解析度，支援的最大畫面播放速率為 15 fps。
  
**沒有 DXVA 且不含硬體加速編碼器的電腦**

|**支援的編碼器解析**|**支援的解碼器解析度**|**需求**|
|:-----|:-----|:-----|
|424x240  <br/> |424x240 (640x360 at 15fps 僅限接收案例)   <br/> |1核心和 VideoEncodeScore ≧4。0  <br/> |
|640x360  <br/> |640x360  <br/> |2核心和 VideoEncodeScore ≧4。5  <br/> |
|640x360  <br/> |1280x720  <br/> |2核心和 VideoEncodeScore ≧4。5  <br/> |
|640x360  <br/> |1920x1080  <br/> |4核心和 VideoEncodeScore ≧4。5  <br/> |
|1280x720  <br/> |1280x720  <br/> |4核心和 VideoEncodeScore ≧7。3  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4核心和 VideoEncodeScore ≧7。3  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |不適用  <br/> |
   
**具有 DXVA 但不含硬體加速編碼器的電腦**

|**支援的編碼器解析**|**支援的解碼器解析度**|**需求**|
|:-----|:-----|:-----|
|424x240  <br/> |1920x1080  <br/> |1核心和 VideoEncodeScore ≧3。0  <br/> |
|640x360  <br/> |1920x1080  <br/> |2核心和 VideoEncodeScore ≧4。5  <br/> |
|960x540  <br/> |1920x1080  <br/> |2核心和 VideoEncodeScore ≧6。0  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4核心和 VideoEncodeScore ≧6。7  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |4核心和 VideoEncodeScore ≧8。2  <br/> |
   
> [!NOTE]
> Windows 7 上的 WinSAT 分數限制為7.9 的最大值。 因此，在沒有硬體加速編碼器的電腦上，只能在 Windows 8 或 Windows 8.1 上達到最大的 WinSAT 分數為9.9 的編碼功能。 
  
**具有 DXVA 且具有英特爾 HD 圖形硬體加速編碼器的電腦**

|**支援的編碼器解析**|**支援的解碼器解析度**|**需求**|
|:-----|:-----|:-----|
|1280x720  <br/> |1920x1080  <br/> |所有第二個和第三代的 Intel HD 顯卡  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |第二和第三代 Intel HD Graphics 和 GraphicsScore ≧5。0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>行動裝置影片功能

下表說明支援的行動裝置上可用的最大影片解析度。 如需行動裝置支援的詳細資訊，請商務用 Skype 的行動[用戶端功能比較](mobile-feature-comparison.md)。
  
|**功能**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|最高解析度的264編碼  <br/> |VGA  <br/> |QVGA： iPhone 4S  <br/> VGA： iPhone 5  <br/> 720p： iPhone 5S 和更新版本  <br/> |VGA： iPad 2 和更新版本/iPad 小型1和更新版本  <br/> 720p： iPad 空氣/iPad 迷你 2/iPad Pro 及更新版本  <br/> |取決於裝置模型，最多 VGA  <br/> |
|-264 解碼最大解析度  <br/> |VGA  <br/> |QVGA： iPhone 4S  <br/> VGA： iPhone 5  <br/> 720p： iPhone 5S 和更新版本  <br/> |VGA： iPad 2 和更新版本/iPad 小型1和更新版本  <br/> 720p： iPad 空氣/iPad 迷你 2/iPad Pro 及更新版本  <br/> |取決於裝置模型，最多 VGA  <br/> |
   

