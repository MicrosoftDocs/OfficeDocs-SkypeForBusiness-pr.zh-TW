---
title: 安裝 Business Server skype 的系統管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
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
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 摘要： 了解如何安裝系統管理工具安裝所需的的 Skype for Business Server。 下載 Microsoft 評估管理中心，從 Business Server Skype 免費試用版： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。
ms.openlocfilehash: 27cda52612eef1259017250ebcc4669e45165229
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018264"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>安裝 Business Server skype 的系統管理工具
 
**摘要：** 了解如何安裝系統管理工具安裝所需的的 Skype for Business Server。 下載 Microsoft 評估管理中心，從 Business Server Skype 免費試用版： [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
系統管理工具包括拓撲產生器] 及 [控制台]。 系統管理工具必須安裝在至少一部伺服器拓撲或執行支援 skype for Business Server 的 Windows 作業系統版本的 64 位元管理工作站上。 您可以執行步驟 1 到 5，以任何順序。 不過，您必須先執行步驟 6、 7 和 8 順序，並在步驟 1 到 5 之後，在圖表中所述。 安裝系統管理工具是 8 的步驟 3。
  
![概觀圖表](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>安裝 Skype for Business Server 系統管理工具

Skype for Business Server 安裝媒體，可提供彈性的體驗。 當您第一次執行 Setup.exe 時，只有已安裝的工具是 Skype for Business Server 部署精靈與 Skype for Business Server 管理命令介面。 使用這兩種工具，稱為核心元件]，您可以繼續安裝程序，但它們不提供主要功能商務伺服器環境的整體 skype。 安裝核心元件之後，會自動啟動 [部署精靈。 ] 區段中的標題為 [**安裝系統管理工具]** [部署精靈安裝 Skype 商務 Server 拓撲產生器與 Skype for Business Server Control Panel。
  
> [!IMPORTANT]
> 每個 Skype for Business Server 環境中必須至少一部伺服器已安裝系統管理工具。 
  
觀賞影片步驟的**安裝系統管理工具**：
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>安裝 Skype for Business Server 系統管理工具，從 [部署精靈

1. 插入 Skype for Business Server 安裝媒體。 如果安裝程式不會自動開始，按兩下 [**設定**]。
    
2. 安裝媒體需要 Microsoft 若要執行的 Visual c + +。 就會出現對話方塊詢問您是否要安裝它。 按一下 [是]****。
    
3. 使用智慧型安裝程式，Skype for Business Server 中的新功能，您可以連線到網際網路，才能在安裝過程中檢查有更新。 此提供更好的經驗，以確定您在安裝有產品最新的更新。 按一下 **[安裝]** 開始安裝。
    
4. 請仔細檢閱授權合約，以及如果您同意，請選取 [**我接受授權合約中的條款**]，並按一下 [**確定]**。
    
5. Skype for Business 伺服器核心元件將會安裝在伺服器上。 
    
    核心元件包括下列項目，如圖所示。
    
    ![在應用程式] 畫面中的核心元件。](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **Skype for Business Server 部署精靈**提供啟動平台安裝各種元件的 Skype for Business Server 部署計畫。
    
   - **Skype for Business Server 管理命令介面**一種預先設定的 PowerShell 程式可用於管理的 Skype for Business Server。
    
     核心元件安裝完成後，Skype for Business Server 部署精靈將會自動啟動，如圖所示。 
    
     ![Skype for Business Server 部署精靈](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. 除了核心元件] 中，您也需要安裝用 Skype 商務 Server 拓撲產生器與 Skype for Business Server Control Panel 環境中的至少一部伺服器上。 按一下 [部署精靈中的 [**安裝系統管理工具**]。
    
7. 按 [下一步]**** 開始安裝。
    
8. 當安裝完成時，按一下 [**完成**]。 系統管理工具現在會被新增至伺服器時，如圖所示。
    
    ![Skype for Business Server 系統管理工具](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **Skype for Business Server 拓撲產生器**程式，用來建立、 部署及管理拓撲。
    
   - **Skype for Business Server Control Panel**用來管理安裝程式。
    

