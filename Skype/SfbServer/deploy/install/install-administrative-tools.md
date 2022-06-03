---
title: 在 商務用 Skype Server 中安裝系統管理工具
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2018
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
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 摘要：瞭解如何安裝安裝商務用 Skype Server所需的系統管理工具。
ms.openlocfilehash: e18ad5953eb063cdb91ea2927ad03ed1057c840a
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860524"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>在 商務用 Skype Server 中安裝系統管理工具
 
**總結：** 瞭解如何安裝安裝商務用 Skype Server所需的系統管理工具。
  
系統管理工具組括拓撲產生器和主控台。 系統管理工具必須安裝在拓撲中的至少一部伺服器上，或執行商務用 Skype Server支援之 Windows OS 版本的 64 位管理工作站上。 您可以依任何循序執行步驟 1 到 5。 不過，您必須依序執行步驟 6、7 和 8，以及步驟 1 到 5 之後，如圖表中所述。 安裝系統管理工具是步驟 8 的步驟 3。
  
![概觀圖表。](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>安裝商務用 Skype Server管理工具

適用于 商務用 Skype Server 的安裝媒體提供彈性體驗。 當您第一次執行Setup.exe時，唯一安裝的工具是商務用 Skype Server部署精靈和商務用 Skype Server管理命令介面。 藉由使用這兩個稱為「核心元件」的工具，您可以繼續安裝程式，但不會為整體商務用 Skype Server環境提供主要功能。 部署精靈會在您安裝核心元件之後自動啟動。 [部署精靈] 標題為 **[安裝系統管理工具**] 的區段會安裝 商務用 Skype Server 拓撲產生器和商務用 Skype Server 主控台。
  
> [!IMPORTANT]
> 每個商務用 Skype Server環境都必須至少有一部已安裝系統管理工具的伺服器。 
  
觀看 **安裝系統管理工具** 的影片步驟：
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>從部署精靈安裝商務用 Skype Server管理工具

1. 插入商務用 Skype Server安裝媒體。 如果安裝程式未自動開始，請按兩下 [ **安裝程式]**。
    
2. 安裝媒體需要Microsoft Visual C++才能執行。 隨即會出現一個對話方塊，詢問您是否要安裝它。 按一下 [是]。
    
3. 藉由使用智慧型安裝程式，這是商務用 Skype Server的新功能，您可以連線到網際網路，以在安裝程式期間檢查更新。 這可確保您在安裝時有最新的產品更新，以提供更好的體驗。 按一下 **[安裝]** 開始安裝。
    
4. 仔細檢閱授權合約，如果您同意，請選取 **[我接受授權合約中的條款**]，然後按一下 [ **確定]**。
    
5. 商務用 Skype Server核心元件將會安裝在伺服器上。 
    
    核心元件包含下列專案，如圖所示。
    
    ![[應用程式] 畫面中的核心元件。](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **商務用 Skype Server部署精靈**：提供啟動板以安裝商務用 Skype Server各種元件的部署程式。
    
   - **商務用 Skype Server管理命令介面**：預先設定的 PowerShell 程式，可讓您管理商務用 Skype Server。
    
     一旦核心元件安裝完成，商務用 Skype Server部署精靈就會自動啟動，如圖所示。 
    
     ![商務用 Skype Server部署精靈]。](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. 除了核心元件之外，您也需要在環境中至少一部伺服器上安裝商務用 Skype Server拓撲產生器和商務用 Skype Server 主控台。 按一下 **[部署精** 靈] 上的 [安裝系統管理工具]。
    
7. 按 [下一步] 開始安裝。
    
8. 安裝完成後，按一下 [ **完成]**。 系統管理工具現在會新增至伺服器，如圖所示。
    
    ![商務用 Skype Server系統管理工具] 。](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **商務用 Skype Server拓撲產生器**：用來建置、部署及管理拓撲的程式。
    
   - **商務用 Skype Server 主控台** 用來管理安裝的程式。
    

