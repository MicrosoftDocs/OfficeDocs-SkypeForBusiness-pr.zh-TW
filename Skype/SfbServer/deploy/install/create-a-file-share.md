---
title: 在商務用 Skype Server 中建立檔案共用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 摘要：瞭解如何在安裝商務用 Skype Server 的過程中建立 Windows Server 檔案共用。 從 Microsoft 評估中心下載免費試用版商務用 Skype Server，網址為： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。
ms.openlocfilehash: 57d1bc348d1fed7a0dc8297723d41d3d90888710
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790181"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>在商務用 Skype Server 中建立檔案共用
 
**摘要：** 瞭解如何在安裝商務用 Skype Server 的過程中建立 Windows Server 檔案共用。 從 Microsoft 評估中心下載免費試用版商務用 Skype Server，網址為：[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
商務用 Skype Server 需要檔案共用，才能讓整個拓撲中的電腦都可以交換檔案。 建立檔案共用是商務用 Skype Server 安裝程式中的步驟2（共8個）。 您可以依照任何循序執行步驟1到5。 不過，您必須在順序中執行步驟6、7和8，並在圖表中所述的步驟1到5之後進行。 如需檔案共用的規劃詳細資料，請參閱商務用 skype Server 2019 的[商務用 Skype server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[伺服器需求](../../../SfBServer2019/plan/system-requirements.md)的環境需求。
  
![概覽圖表](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>建立基本檔案共用

本節將引導您逐步完成建立基本的 Windows Server 檔案共用。 商務用 Skype 伺服器支援基本的 Windows Server 檔案共用。 不過，它不會明確提供高可用性。 針對高可用性環境，建議使用分散式檔案系統（DFS）檔案共用。 如需高可用性檔案共用和 DFS 的詳細資訊，請參閱[在商務用 Skype Server 中規劃高可用性和災害復原](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
> [!NOTE]
> Windows Server 2012 R2 在提供儲存區域網路（SAN）等方面的巨大突破，就像是使用 Windows Server 平臺的檔案共用解決方案一樣。 與傳統的基於 SAN 的裝置相比，Windows Server 2012 R2 儲存方案會以極小的效能影響，降低成本的一半。 如需有關 Windows Server 2012 R2 中檔案共用選項的詳細資訊，請參閱可下載的白皮書[Windows Server 2012 R2 儲存空間](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)。 
  
觀看**建立檔案共用**的影片步驟：
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>建立基本檔案共用

1. 登入將主持檔案共用的電腦。
    
2. 以滑鼠右鍵按一下您要共用的資料夾，然後選取 [**屬性**]。
    
3. 選取 [**共用**] 索引標籤，然後按一下 [**高級共用**]。
    
4. 按一下 [**共用此資料夾**]。
    
5. 按一下 [**許可權**]。
    
6. 新增主持檔案共用的伺服器 [本機**管理員**] 群組、[准許**允許]： [完全控制**]、[變更] 和 [讀取] 許可權，然後按一下 **[確定]**。
    
7. 再次按一下 **[確定]** ，記下網路路徑。
    
8. 按一下 [**完成**] 以關閉嚮導。
    
     ![共用資料夾的 [共用] 索引標籤。](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>如果檔案存放區託管在 DFS 共用上，則會收到下列警告：

警告：無法存取 [\\<domain>\<共用>] 的共用許可權。

>如果您不是檔案伺服器的系統管理員，或者這是分散式檔案系統（DFS）共用，則預期是這種情況。 如果已設定共用許可權，就可以忽略此警告。 如果是新的共用，請參閱相關檔，以取得手動設定共用許可權的詳細資料。

>由於無法存取 DFS 共用的共用許可權，商務用 Skype 伺服器將無法明確設定檔案共用上的群組。 若要確保商務用 Skype 伺服器元件可以使用適當的許可權存取檔案共用，請務必先使用 [讀取] 和 [變更層級共用] 許可權來新增下列 RTC 群組，除了擁有 [完全控制] 共用的本機管理員之外許可權.
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
