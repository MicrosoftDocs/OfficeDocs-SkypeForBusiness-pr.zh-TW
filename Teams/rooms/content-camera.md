---
title: 使用 XML 設定檔遠端系統管理 Microsoft 團隊聊天室的主控台設定
ms.author: kenwith
author: kenwith
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 本文將討論 Microsoft 團隊聊天室裝置所使用的預設設定的遠端系統管理，包括套用自訂主題。
ms.openlocfilehash: b470804ac2c5a44a0eb74330ea5158c2e9fe9098
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824531"
---
# <a name="content-cameras"></a>內容相機

您現在可以使用內容相機搭配 Microsoft [小組室系統]。 內容相機會與特殊的影像處理軟體和白板互動，讓簡報者在類比白板上繪圖，並與遠端參與者共用內容。

請參閱下列影片，以取得內容攝影機功能的範例。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E7fy]

## <a name="set-up-a-content-camera"></a>設定內容攝影機

> [!NOTE]
> 請務必遵循您的國家或地區的建築物程式碼，這可能會定義最小到地面的距離，或要求將天花板掛載的裝置安全地提供給 rafter 或其他結構。 針對您所選取的相機提供的硬體，按照安裝指示進行。 OEM 相機安裝套件包括相機、USB 2.0 延伸器以及所需的纜線。

共用所用的白板大小會影響相機的位置。 建議的版面大小：

- 支援3到6英尺（0.9 – 1.8 m）
- 全（1.8 – 2.7 m）寬的6–9英尺（建議使用）
- 支援 9-12 英尺（2.7 – 3.6 m）
- 超過12英尺（3.6 m）寬-相機涵蓋9–12英尺（2.7 到 3.6 m），並裁掉其餘部分。

## <a name="camera-location"></a>相機位置

內容相機的理想位置是在白板上垂直或水準居中。 本機組建程式碼可能會有高度限制，必須比白板頂端更高的相機升高。

您最多可以將相機安裝到6。 （152 mm）高於白板頂端，並以白色面板為中心（如圖所示）。 請確定相機影像包含至少6個。 （152 mm）會在兩邊水準框線。 您可以在 Microsoft 團隊聊天室 app 中使用相機預覽來判斷相機的最終位置。

![內容相機位置圖表](../media/Magic-whiteboard.png)

### <a name="camera-distances"></a>相機距離

使用典型的白板標記，最佳的遠端使用者體驗是在內容相機影像中的每個圖元範圍中共用筆跡筆劃，而最佳結果則會使用 1.5 mm/象素。 所有支援的相機都提供 1920 x 1080 解析度，而部分可能超出該解析度。

相機與 [白板] 的距離會結合相機解析度和 HFoV 來判斷白板的距離。 下表顯示各種白板大小的距離範例。 您可以使用這些值做為開始點來決定內容相機的最終位置。

**從白板的相機距離**

| 相機 HFoV |3英尺（0.91 m）     | 6英尺（1.8 m）    | 9英尺（2.74 m）        |12英尺。 （3.65 m）         | 從白板最大距離  |
|:---         |:---               |:---                |:---                 |:---             | :--- |
| 80°         | 1.79 英尺（0.54 m） | 3.58 英尺（1.09 m）  | 5.36 英尺（1.6 m）    |7.15 英尺（2.17 m） |7.51 英尺（2.28 m） |
| 90°         | 1.5 英尺（0.45 m） | 3.00 英尺（0.91 m）   | 4.5 英尺（1.37 m）    |6.0 英尺（1.82 m）    |6.3 英尺（1.92 m） |
| 100°        | 1.26 英尺（0.38 m）| 2.52 英尺（0.77 m）   | 3.78 英尺（1.15 m）   |5.03 英尺（1.53 m）   |5.29 英尺（1.61 m） |
| 110°        | 1.05 英尺（0.32 m）| 2.10 英尺（0.64 m）   | 3.15 英尺（0.96 m）   |4.2 英尺（1.28 m）    |4.41 英尺（1.31 m） |
| 120°        | 0.87 英尺（0.26 m）| 1.73 英尺（0.52 m）   | 2.60 英尺（0.79 m）   |3.46 英尺（1.05 m）   |3.64 英尺（1.10 m） |
|             |               |                  |                  |        |                    |                  |

[內容相機] 與 [白板] 上所安裝的牆之間的距離，取決於該模型的 HFoV，也就是不同的。 使用較大的 HFoV （例如120度）安裝攝影機，並將相機的 HFoV 距離牆遠較窄。 在您開始安裝選取的相機之前，請先檢查 HFoV。

如果您的白板大於12英尺（3.65 m）或沒有角落（例如全形白板），您可以將相機放在中間的任何位置。 如果找不到 [白板角落]，增強軟體會選取中間的區域。

> [!NOTE]
> 您可以使用彩色的膠帶或其他專案，在全牆白板上建立已定義的內容相機區域。
>
> 您可以選擇是否要將相機安裝在可移動的機架上，而不是永久安裝。 在白板上將 [置中] 放在中央。 這項設定可能是暫時的，或用於在裝置上有挖空的情況。 如果您使用的是暫時裝載，請記住，如果您在初次共用之後移動攝像頭，就會影響內容增強，您必須重新共用才能讓移動正確。
>
> 不支援不是白色的書寫板。

## <a name="supported-cameras"></a>支援的相機

若要判斷您是否可以使用相機做為內容攝影機，請參閱[USB 音訊與視頻週邊設備的已認證固件版本](requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals)。

或者，請參閱 Microsoft 團隊裝置 marketplace 以取得支援的內容攝影機[aka.ms/teamsdevices](https://aka.ms/teamsdevices)。

## <a name="camera-settings"></a>相機設定

在房間中安裝攝影機之後，請在該聊天室的 Microsoft 團隊聊天室主控台上進行設定：

1. 選取 [**設定** ![設定](../media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)] 圖示、[以系統管理員身分登入]，然後選取 [**裝置設定**]。
2. 在 [**相機預設值**] 區段中，選取 [內容相機]，並確認已選取 [**內容增強功能**] 選項。
3. 可選如果相機是從天花板掛載，且已倒置安裝攝像頭，請核取 [**旋轉內容相機 180** ] 選項。
4. 選取 [**儲存並**結束]。

![內容攝影機設定](../media/content-camera.png)

您也可以使用[XML 設定檔](xml-config-file.md)來遠端調整這些設定。

## <a name="see-also"></a>另請參閱

[使用 XML 設定檔遠端系統管理 Microsoft 團隊聊天室的主控台設定](xml-config-file.md)

[Microsoft 團隊會議室需求](requirements.md)

> [!NOTE]
> 某些具有 Microsoft Surface Pro （例如 Logitech Smartdock 和 Crestron SR）的 Microsoft 團隊機房裝置還不支援 [內容相機]。 這些裝置的支援稍後會在 CY2019 中新增。 
>
