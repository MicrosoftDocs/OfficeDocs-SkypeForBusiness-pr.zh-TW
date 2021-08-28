---
title: 瞭解如何設定內容攝影機 - Microsoft Teams
ms.author: serdars
author: serdarsoysal
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-mar2020
description: 在會議室使用內容Microsoft Teams，與影像處理軟體互動，讓簡報者在類比白板上繪圖。
ms.openlocfilehash: e24a90e65a5d844a5431951283153a5de2406498
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613002"
---
# <a name="content-cameras"></a>內容相機

現在，您可以將內容相機與會議室系統Microsoft Teams使用。 內容攝影機會與特殊的影像處理軟體和白板互動，讓簡報者在類比白板上繪圖，並與遠端參與者共用內容。

請參閱下列影片，瞭解內容相機功能範例。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E7fy]

## <a name="set-up-a-content-camera"></a>設定內容攝影機

> [!NOTE]
> 請一直遵循您國家/地區或地區的建置規範，此規範可能會定義與樓面的最小距離，或要求將天花板安裝的設備固定至木條或其他結構。 請遵循所選相機所提供之硬體的安裝指示。 OEM 相機安裝套件包括相機、USB 2.0 延伸線和必要的纜線連接。

用來共用之白板的大小會影響相機的位置。 董事會大小建議為：

- 3 到 6 (寬 0.9 到 1.8) - 支援
- 6 至 9 (寬 1.8 到 2.7) - 建議
- 9 到 12 (寬 2.7 到 3.6) - 支援
- 超過 12 呎 (3.6) 寬 — 相機會覆蓋 9-12 呎 (2.7 到 3.6 m) 並切下其餘部分。

## <a name="camera-location"></a>相機位置

內容相機的理想位置會以垂直和水準方式置中于白板上。 當地建築物代碼可能有高度限制，要求相機高於白板頂端。

您最多可以安裝 6 in 的相機。  (152 mm) 高於白板頂端，且位於白板中央 ，如下所示。 請確定相機影像至少包含 6 in。  (水準) 兩側的 152 mm 外邊界。 您可以在相機應用程式中使用相機預覽Microsoft Teams 會議室決定相機的最終位置。

![內容相機位置圖表](../media/Magic-whiteboard.png)

### <a name="camera-distances"></a>相機距離

使用一般的白板標記，最佳遠端使用者體驗是共用內容相機影像中每圖元 1 到 2 mm 範圍的筆劃，而最佳結果會使用每圖元 1.5 mm。 所有支援的相機都提供 1920 x 1080 解析度，有些相機可能會超過該解析度。

相機與白板的距離會結合相機解析度和 HFoV 來判斷與白板的距離。 下表顯示各種白板大小之距離的範例。 您可以使用這些值做為起點，決定內容攝影機的最終位置。

**從白板的相機距離**

| 相機 HFoV |3 呎 (0.91)      | 6 呎 (1.8)     | 9 呎 (2.74)         |12 呎 (3.65 m)          | 與 Whiteboard 的最大距離  |
|:---         |:---               |:---                |:---                 |:---             | :--- |
| 80°         | 1.79 (0.54)  | 3.58 呎 (1.09)   | 5.36 (1.6 m)     |7.15 呎 (2.17)  |7.51 呎 (2.28)  |
| 90°         | 1.5 呎 (0.45)  | 3.00 ft. (0.91 m)    | 4.5 呎 (1.37)     |6.0 (1.82 m)     |6.3 (1.92 m)  |
| 100°        | 1.26 (0.38 m) | 2.52 呎 (0.77)    | 3.78 呎 (1.15)    |5.03 呎 (1.53)    |5.29 ft. (1.61 m)  |
| 110°        | 1.05 (0.32 m) | 2.10 (0.64)    | 3.15 呎 (0.96)    |4.2 呎 (1.28)     |4.41 ft. (1.31 m)  |
| 120°        | 0.87 ft. (0.26 m) | 1.73 ft. (0.52 m)    | 2.60 (0.79 m)    |3.46 呎 (1.05)    |3.64 呎 (1.10)  |
|             |               |                  |                  |        |                    |                  |

內容相機與白板所安裝之牆之間的距離取決於該相機型號的 HFoV，這兩者會有所不同。 安裝較大型 HFoV (120 度 ，例如) 靠近牆面的相機，以及距離牆較遠的較窄 HFoV 相機。 在開始安裝所選相機之前，請檢查 HFoV。

如果您的白板大於 12 呎 (3.65) 或沒有角落 (例如全牆白板) ，您可以將相機放在中間的任何位置。 如果找不到白板角落，增強軟體會選取中間的區域。

> [!NOTE]
> 您可以使用深色的帶子或其他專案，在全牆白板上建立已定義的內容攝影機區域。
>
> 您可以選擇將相機安裝在可移動的三腳架上，而不是永久安裝。 將三腳架放在白板中央。 此設定可能是暫時性的，或是在幾乎無法翻倒設備的地方使用。 如果您使用暫時安裝，請記住，如果您在初始共用之後移動相機，且您必須重新共用，以修正移動，內容增強功能將會受到影響。
>
> 不支援非白色書寫板。

## <a name="supported-cameras"></a>支援的相機

若要判斷您是否可以使用相機做為內容相機，請參閱 USB 音訊和視音訊周邊的認證固件 [版本](requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals)。

或者，請參閱 Microsoft Teams 裝置市場，以在[aka.ms/teamsdevices。](https://aka.ms/teamsdevices)

## <a name="camera-settings"></a>相機設定

在會議室中安裝相機之後，請設定該會議室的主機Microsoft Teams 會議室：

1. 選取 **設定設定** ![ 圖示，以系統管理員登入，然後選取 ](../media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) **設定。**
2. 在相機 **預設值區** 段，選取內容相機，然後確認已 **選取內容增強功能** 選項。
3.  (選) 如果相機是因為從天花板安裝而上下顛倒安裝，請檢查旋轉內容相機 **180 度** 選項。
4. 選取 **儲存並離開**。

![內容相機設定](../media/content-camera.png)

您也可以使用 XML 設定檔遠端調整 [這些設定](xml-config-file.md)。

## <a name="see-also"></a>另請參閱

[使用 XML Microsoft Teams 會議室遠端系統管理主機設定](xml-config-file.md)

[Microsoft Teams 會議室需求](requirements.md)


