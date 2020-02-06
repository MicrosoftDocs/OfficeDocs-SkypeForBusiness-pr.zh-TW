---
title: 商務用 Skype 用戶端影片解析度
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: 摘要：在規劃商務用 Skype Server 時，請查看用戶端的視頻需求。
ms.openlocfilehash: f51e9369cfba636ae37205a6e56e27c7622f12e6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803493"
---
# <a name="skype-for-business-client-video-resolutions"></a>商務用 Skype 用戶端影片解析度
 
**摘要：** 在規劃商務用 Skype Server 時，請複習用戶端的視頻需求。
  
本文將說明商務用 Skype 影片通話的視頻硬體支援，並說明如何判斷各種電腦、平板電腦和行動裝置設定的預期視頻品質。 
  
IT 專業人員會在評估組織中已使用的膝上型電腦的適用性，或在考慮使用時，找到這項資訊。 他們也可以在 [[解決方案] 目錄](https://partnersolutions.skypeforbusiness.com/solutionscatalog)中搜尋特定裝置的相關資訊。
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Windows 桌面、Mac 和平板電腦影片需求與功能

商務用 Skype 會使用硬體加速來進行影片編碼與解碼，並根據 H-264/MPEG-4 個第10部分高級視頻編碼標準進行。 這可讓使用較低 CPU 時脈速度的電腦來編碼及解碼較高的解析度影片。 根據電腦設定與視頻解析度的不同，視頻硬體需求會有所不同。
  
另請參閱[Windows 和 Mac 硬體需求](https://products.office.com/en-us/office-system-requirements)。
  
### <a name="video-hardware-requirements"></a>影片硬體需求

|**功能**|**需求**|
|:-----|:-----|
|使用 DirectX Video 加速進行硬體加速的264解碼（DXVA）  <br/> |•圖形卡必須支援 DirectX 9.0，且必須公開 DXVA2_ModeH264_VLD_NoFGT 解碼模式和 DirectX 9 API。  <br/> •必須安裝最新的圖形配接器驅動程式。  <br/> |
|硬體加速的264編碼：晶片需求  <br/> |支援下列 Intel 硬體加速視頻編碼解決方案：  <br/> •第二和第三代英特爾高質圖形2000、2500、3000和4000晶片組（或更新版本），集成硬體視頻編碼器。 必須安裝英特爾高質圖形驅動程式15.28.9.2884 或包含下列的最新驅動程式：  <br/> •顯示驅動程式9.17.10.2884 或最新的驅動程式  <br/> •硬體媒體基礎轉換（HMFT）版本3.12.10.31 或最新 HMFT  <br/> 支援下列 AMD 硬體加速視頻編碼解決方案：  <br/> •可在幾個獨立圖形卡中使用的 AMD Video 編解碼器引擎，以及採用 AMD A 系列加速處理器的整合加速處理單元。 必須安裝 AMD Video 編解碼器引擎驅動程式9.12.0.0 或更新版本。  <br/> |
|硬體加速的264編碼：相機需求  <br/> |含集成式 H-p 硬體編碼器的 USB 攝影機，符合 USB Video Class （UVC）規格版本1.5。  <br/> **注意：** 商務用 Skype 支援 Windows 8 或 Windows 8.1 的 UVC 1.5 攝影機，包括 UVC 1.5 的支援。 因為 Windows 7 不包括 UVC 1.5 的支援，商務用 Skype 會將 UVC 1.5 相機視為不含硬體編碼支援的一般攝影機。 <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>決定 H-p 的視頻編碼與解碼功能

一般來說，以下四個主要因素決定了特定電腦設定的最大編碼與解碼功能：
  
- 支援使用 DXVA 進行硬體加速解碼
    
- 硬體加速編碼支援
    
- 物理內核數
    
- Windows 體驗索引（WEI）
    
Windows 系統評定工具（WinSAT）會判斷 WEI。 當您執行 WinSAT 工具時，它會在電腦上的%windir%\Performance\WinSAT\DataStore 目錄中產生一個正式的評估 XML 檔。 這個 XML 檔案包含下列兩個分數，對於判斷編碼與解碼功能而言是特別重要的：
  
- VideoEncodeScore 表示電腦的軟體影片編碼功能。
    
- GraphicsScore 值代表電腦的硬體加速編碼功能。
    
下列三個表格會根據其支援的硬體加速，說明不同電腦類型的最大編碼與解碼功能。 針對640x360 及更高版本的解析度，支援的畫面播放速率上限為30個畫面/秒（fps）。 針對低於640x360 的解析度，支援的畫面播放速率上限為 15 fps。
  
**不含 DXVA 且沒有硬體加速編碼器的電腦**

|**支援的編碼器解析度**|**支援的解碼器解析度**|**需求**|
|:-----|:-----|:-----|
|424x240  <br/> |424x240 （640x360 at 僅限接收案例的15fps）  <br/> |1核與 VideoEncodeScore ≥4。0  <br/> |
|640x360  <br/> |640x360  <br/> |2核與 VideoEncodeScore ≥4。5  <br/> |
|640x360  <br/> |1280x720  <br/> |2核與 VideoEncodeScore ≥4。5  <br/> |
|640x360  <br/> |1920x1080  <br/> |4核與 VideoEncodeScore ≥4。5  <br/> |
|1280x720  <br/> |1280x720  <br/> |4核與 VideoEncodeScore ≥7。3  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4核與 VideoEncodeScore ≥7。3  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |不適用  <br/> |
   
**有 DXVA 但沒有硬體加速編碼器的電腦**

|**支援的編碼器解析度**|**支援的解碼器解析度**|**需求**|
|:-----|:-----|:-----|
|424x240  <br/> |1920x1080  <br/> |1核與 VideoEncodeScore ≥3。0  <br/> |
|640x360  <br/> |1920x1080  <br/> |2核與 VideoEncodeScore ≥4。5  <br/> |
|960x540  <br/> |1920x1080  <br/> |2核與 VideoEncodeScore ≥6。0  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4核與 VideoEncodeScore ≥6。7  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |4核與 VideoEncodeScore ≥8。2  <br/> |
   
> [!NOTE]
> Windows 7 上的 WinSAT 得分限制為最大值7.9。 因此，只有在 Windows 8 或 Windows 8.1 上才能取得沒有硬體加速編碼器之電腦的編碼功能，其中最大的 WinSAT 分數為9.9。 
  
**含 DXVA 及含英特爾高質圖形硬體加速編碼器的電腦**

|**支援的編碼器解析度**|**支援的解碼器解析度**|**需求**|
|:-----|:-----|:-----|
|1280x720  <br/> |1920x1080  <br/> |所有第二和第三代英特爾高質圖形  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |第二和第三代英特爾高質圖形及 GraphicsScore ≥5。0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>行動裝置影片功能

下表說明支援的行動裝置上可用的最大視頻解析度。 如需行動裝置支援的詳細資訊，請參閱商務用 Skype 的行動[用戶端功能比較](mobile-feature-comparison.md)。
  
|**功能**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|H-p 編碼最大解析度  <br/> |採用  <br/> |QVGA： iPhone 4S  <br/> VGA： iPhone 5  <br/> 720p： iPhone 5S 及更新版本  <br/> |VGA： iPad 2 及更新版本/iPad 迷你1及更新版本  <br/> 720p： iPad Air/iPad 迷你 2/iPad Pro 及更新版本  <br/> |最多 VGA （視裝置模型而定）  <br/> |
|H-p 解碼最大解析度  <br/> |採用  <br/> |QVGA： iPhone 4S  <br/> VGA： iPhone 5  <br/> 720p： iPhone 5S 及更新版本  <br/> |VGA： iPad 2 及更新版本/iPad 迷你1及更新版本  <br/> 720p： iPad Air/iPad 迷你 2/iPad Pro 及更新版本  <br/> |最多 VGA （視裝置模型而定）  <br/> |
   

