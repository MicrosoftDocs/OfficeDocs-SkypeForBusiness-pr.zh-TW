---
title: 在 商務用 Skype Server 中建立檔案共用
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
description: 摘要：瞭解如何在安裝 商務用 Skype Server 時建立Windows伺服器檔案共用。
ms.openlocfilehash: 12ea75a11470d5730c891b1c738a3337ccb28ac8
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860724"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>在 商務用 Skype Server 中建立檔案共用
 
**總結：** 瞭解如何在安裝 商務用 Skype Server 時建立 Windows Server 檔案共用。
  
商務用 Skype Server需要檔案共用，讓整個拓撲的電腦可以交換檔案。 在商務用 Skype Server的安裝程式中，建立檔案共用是步驟 8 的步驟 2。 您可以依任何循序執行步驟 1 到 5。 不過，您必須依序執行步驟 6、7 和 8，以及依照圖表中所述的步驟 1 到 5 之後執行。 如需檔案共用的規劃詳細資料，請參閱[商務用 Skype Server 的環境](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)需求或[2019 商務用 Skype Server伺服器需求](../../../SfBServer2019/plan/system-requirements.md)。
  
![概觀圖表。](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>建立基本檔案共用

本節將逐步引導您建立基本Windows伺服器檔案共用。 商務用 Skype Server支援基本Windows伺服器檔案共用。 不過，它不會明確地提供高可用性。 針對高可用性環境，建議使用分散式檔案系統 (DFS) 檔案共用。 如需高可用性檔案共用和 DFS 的詳細資訊，請參閱[在 商務用 Skype Server 中規劃高可用性和災害復原](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
> [!NOTE]
> Windows Server 2012 R2 在使用 Windows Server 平臺提供儲存體區域網路 (SAN) 類檔案共用解決方案方面，已大有不同。 相較于傳統的 SAN 型設備，Windows Server 2012 R2 儲存體解決方案可將成本減半，對效能的影響非常小。 如需 Windows Server 2012 R2 中檔案共用選項的詳細資訊，請參閱可下載的白皮書[Windows Server 2012 R2 儲存體](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)。 
  
觀看 **建立檔案共用的** 影片步驟：
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>建立基本檔案共用

1. 登入將裝載檔案共用的電腦。
    
2. 以滑鼠右鍵按一下您打算共用的資料夾，然後選取 [ **屬性]**。
    
3. 選取 [ **共用] 索引** 標籤，然後按一下 [ **進階共用]**。
    
4. 按一下 **[共用此資料夾]**。
    
5. 按一下 [權限]。
    
6. 新增裝載檔案共用之伺服器的本機 **Administrators** 群組，授與 **[允許：完全控制]、[變更] 和 [讀取]** 許可權，然後按一下 [ **確定]**。
    
7. 再次按一下 **[確定** ]，並記下網路路徑。
    
8. 按一下 **[完成** ] 關閉精靈。
    
     ![共用資料夾的 [共用] 索引標籤。](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>如果檔案存放區裝載于 DFS 共用上，則會收到下列警告：

`Warning: Unable to access share permissions for "\\<domain>\<share>".`

>如果您不是檔案伺服器上的系統管理員，或這是分散式檔案系統 (DFS) 共用，則這是預期的。 如果共用許可權已設定，則可以忽略此警告。 如果是新的共用，請參閱檔以取得手動設定共用許可權的詳細資料。

>由於無法存取 DFS 共用的共用許可權，商務用 Skype Server將無法在檔案共用上明確設定群組。 若要確保商務用 Skype Server元件可以使用適當的許可權來存取檔案共用，請確定除了具有完全控制共用許可權的本機系統管理員之外，還會使用讀取和變更層級共用許可權新增下列 RTC 群組。
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
