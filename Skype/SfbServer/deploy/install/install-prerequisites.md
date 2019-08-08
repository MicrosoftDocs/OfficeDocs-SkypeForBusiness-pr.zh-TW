---
title: 安裝商務用 Skype Server 的先決條件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: '摘要: 瞭解您必須先設定的伺服器和伺服器角色, 才能安裝商務用 Skype Server。 從 Microsoft 評估中心下載免費試用版商務用 Skype Server, 網址為: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: 2fbf90a1ee6f517cad2c716e6a50dd814352993e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240907"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a>安裝商務用 Skype Server 的先決條件
 
**摘要:** 瞭解您必須先設定的伺服器和伺服器角色, 才能安裝商務用 Skype Server。 從[Microsoft 評估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)下載商務用 Skype Server 的免費試用版。
  
安裝先決條件包括在拓撲中的每個伺服器上安裝所需的角色和功能, 以設定 Windows Server。 需求是以伺服器將在拓撲中履行的角色為基礎。 您可以依照任何循序執行步驟1到5。 不過, 您必須在順序中執行步驟6、7和 8, 並在步驟1到5之後, 如圖表中所述。 安裝必備元件是8的步驟1。
  
![概覽圖表-安裝必備元件。](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>設定 Windows Server

商務用 Skype 伺服器需要具備 Windows Server 作業系統及幾個必備元件才能安裝。 如需針對必備元件規劃的詳細資料, 請參閱[商務用 Skype server 的伺服器需求](../../../SfBServer2019/plan/system-requirements.md)。 
  
> [!TIP]
> 此程式會使用 Windows Server 2012 R2。 如果您使用的是其他版本的 Windows Server, 程式可能會稍有不同。 
  
> [!IMPORTANT]
> 在開始之前, 請先使用 Windows Update, 確定 Windows Server 是最新的。 
  
![Windows Server 保持最新狀態。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
請觀看**安裝必備元件**的影片步驟:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>安裝前端伺服器所需的角色和功能

您可以使用伺服器管理員安裝必要的角色和功能。 
    
1. 安裝[商務用 Skype server 的伺服器需求](../../../SfBServer2019/plan/system-requirements.md)中所列的必備軟體功能。 所需的軟體必須位於將執行商務用 Skype Server 的伺服器上。
    
    > [!CAUTION]
    > Windows Server 2012 R2 預設不會安裝所需功能的所有來源檔案。 如果伺服器未連線至網際網路, 您將需要插入 Windows Server 2012 R2 媒體, 然後選取 [**指定替代來源路徑**] 來安裝所需的功能。 來源檔案位於 sources\sxs 目錄中。 例如, 如果 Windows Server 2012 R2 媒體位於磁片磁碟機 D, 您會將路徑設定為`d:\sources\sxs`。 您必須具備 Windows 更新中的最新更新, 才能使用這項功能。 如果您未連線至網際網路, 您將需要手動安裝所有相關的更新, 以及任何必要的更新。 
  
1. 當對話方塊指示安裝已完成時, 您必須重新開機伺服器才能完成程式。
    
1. 再次執行**Windows Update** , 以檢查是否有已安裝之角色和服務的任何更新。
    
1. 如果您要在此伺服器上使用商務用 Skype Server 的 [控制台], 您也必須安裝 Silverlight。 若要安裝 Silverlight, 請參閱[Microsoft Silverlight](https://www.microsoft.com/silverlight/)。


> [!IMPORTANT]
> 執行伺服器 (例如 Director、永久聊天或邊緣角色) 等角色的伺服器必備元件有自己的先決條件。 如需每種伺服器類型所需的確切先決條件的詳細資訊, 請參閱[商務用 Skype server 的伺服器需求](../../../SfBServer2019/plan/system-requirements.md)。 
  

