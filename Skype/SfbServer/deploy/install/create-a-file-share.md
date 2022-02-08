---
title: 在商務用 Skype Server 中建立檔案共用
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 摘要：瞭解如何在安裝商務用 Skype Server 時建立 Windows 伺服器檔案共用。 從 Microsoft 評估中心下載免費試用版商務用 Skype Server，網址如下： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。
ms.openlocfilehash: c5d072c643061f65f68226eeed43f769a06bd2e4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385221"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>在商務用 Skype Server 中建立檔案共用
 
**總結：** 瞭解如何在安裝商務用 Skype Server 中建立 Windows 伺服器檔案共用。 從 Microsoft 評估中心下載免費試用版商務用 Skype Server，網址如下： [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 。
  
商務用 Skype Server 需要檔案共用，使整個拓撲中的電腦可以交換檔案。 建立檔案共用是商務用 Skype Server 安裝程式中的步驟2之8。 您可以依任何循序執行步驟1到5。 不過，您必須依序執行步驟6、7和8，並在圖表中所述的步驟1到5之後進行。 如需檔案共用的規劃詳細資料，請參閱[商務用 Skype Server 2019 商務用 Skype Server 或伺服器需求](../../../SfBServer2019/plan/system-requirements.md)[的環境需求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。
  
![一覽表圖表。](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>建立基本檔案共用

本節會逐步引導您建立基本的 Windows 伺服器檔案共用。 商務用 Skype Server 支援基本 Windows 伺服器檔案共用。 不過，它並未明確提供高可用性。 在高可用性環境中，建議使用分散式檔案系統 (DFS) 檔案共用。 如需高可用性檔案共用及 DFS 的詳細資訊，請參閱[商務用 Skype Server 中的計畫高可用性和嚴重損壞修復](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
> [!NOTE]
> Windows Server 2012 R2 在提供儲存體區域網路 (SAN) （如使用 Windows 伺服器平臺的檔案共用解決方案）上有重大的大幅突破。 與傳統的 SAN 裝置相較時，Windows Server 2012 R2 儲存解決方案可以以極小的效能影響降低成本。 如需 Windows Server 2012 R2 中檔案共用選項的詳細資訊，請參閱可下載的白皮書[Windows Server 2012 R2 儲存體](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)。 
  
觀賞 **建立檔案共用** 的影片步驟：
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>建立基本檔案共用

1. 登入將主檔案共用的電腦。
    
2. 以滑鼠右鍵按一下您要共用的資料夾，然後選取 [ **屬性**]。
    
3. 選取 [ **共用** ] 索引標籤，然後按一下 [ **高級共用**]。
    
4. 按一下 [ **共用此資料夾**]。
    
5. 按一下 [權限]。
    
6. 新增主控檔案共用之伺服器的本機系統 **管理員** 群組、授與 **允許：完全控制、變更和讀取** 許可權，然後按一下 **[確定]**。
    
7. 再按一下 **[確定]** ，記下網路路徑。
    
8. 按一下 [ **完成** ]，關閉嚮導。
    
     ![共用資料夾的 [共用] 索引標籤。](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>如果檔案存放區裝載于 DFS 共用上，則會收到下列警告：

`Warning: Unable to access share permissions for "\\<domain>\<share>".`

>如果您不是檔案伺服器上的系統管理員，或者這是分散式檔案系統 (DFS) 共用，就會發生這種情況。 如果已設定共用許可權，則可以忽略此警告。 如果是新的共用，請參閱檔，以瞭解手動設定共用許可權的詳細資料。

>由於無法存取 DFS 共用的共用許可權，因此商務用 Skype Server 將無法明確設定檔案共用上的群組。 為了確保商務用 Skype Server 元件可以存取具有適當許可權的檔案共用，請確定下列 RTC 群組新增了「讀取」和「變更層級共用」許可權，除了具備完全控制共用許可權的本機管理員之外。
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
