---
title: 在商務用 Skype Server 中安裝系統管理工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：瞭解如何安裝商務用 Skype Server 安裝所需的系統管理工具。 從 Microsoft 評估中心下載免費試用版的商務用 Skype Server，網址如下： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。
ms.openlocfilehash: ab3e64ae5d330c5b24eff7c23172b1141ff75527
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812103"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a>在商務用 Skype Server 中安裝系統管理工具
 
**摘要：** 瞭解如何安裝商務用 Skype Server 安裝所需的系統管理工具。 從 Microsoft 評估中心下載免費試用版的商務用 Skype Server，網址如下： [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 。
  
系統管理工具組括拓撲產生器和 [控制台]。 系統管理工具必須安裝在拓撲中至少一部伺服器上，或執行支援商務用 Skype Server 之 Windows 作業系統版本的64位管理工作站。 您可以依任何循序執行步驟1到5。 不過，您必須依序執行步驟6、7和8，並在步驟1到5之後進行，如圖表中所述。 安裝系統管理工具的步驟3之8。
  
![一覽表圖表](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a>安裝商務用 Skype Server 系統管理工具

商務用 Skype Server 的安裝媒體可提供彈性的體驗。 當您第一次執行 Setup.exe 時，只有安裝的工具是商務用 Skype Server 部署嚮導和商務用 Skype Server 管理命令介面。 使用這兩個工具（稱為核心元件），您可以繼續安裝程式，但不會提供整個商務用 Skype Server 環境的主要功能。 安裝核心元件後，就會自動啟動部署嚮導。 「 **安裝系統管理工具** 」部署嚮導的區段會安裝商務用 Skype server 拓撲產生器和商務用 Skype server 控制台。
  
> [!IMPORTANT]
> 每個商務用 Skype 伺服器環境都必須至少有一個伺服器安裝了系統管理工具。 
  
觀賞 **安裝系統管理工具** 的影片步驟：
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a>從部署嚮導安裝商務用 Skype Server 系統管理工具

1. 插入商務用 Skype Server 安裝媒體。 如果安裝程式未自動開始，請按兩下 [ **設定**]。
    
2. 安裝媒體需要 Microsoft Visual c + + 才能執行。 隨即會彈出一個對話方塊，詢問您是否要安裝。 按一下 [是]。
    
3. 您可以使用 Smart Setup （商務用 Skype Server 中的新功能），連線至網際網路，以在安裝程式期間檢查更新。 這可讓您在安裝時，確保產品有最新的更新，以獲得較佳的體驗。 按一下 **[安裝]** 開始安裝。
    
4. 請仔細閱讀授權合約，如果同意，請選取 [ **我接受授權合約中的條款**]，然後按一下 **[確定]**。
    
5. 商務用 Skype Server 核心元件將會安裝在伺服器上。 
    
    核心元件包含下列，如圖所示。
    
    ![[應用程式] 畫面中的核心元件。](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - **商務用 Skype Server 部署嚮導** 為安裝商務用 Skype Server 的各種元件提供啟動墊的部署程式。
    
   - **商務用 Skype Server 管理命令** 介面可供您管理商務用 Skype Server 的預先設定的 PowerShell 程式。
    
     核心元件的安裝完成後，商務用 Skype Server 部署嚮導將會自動啟動，如圖所示。 
    
     ![商務用 Skype Server 部署嚮導](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. 除了核心元件之外，您還需要在環境中至少一部伺服器上安裝商務用 Skype Server 拓撲產生器和商務用 Skype Server 控制台。 按一下 [部署嚮導] 上的 [ **安裝系統管理工具** ]。
    
7. 按 [下一步] 開始安裝。
    
8. 完成安裝後，請按一下 **[完成]**。 系統管理工具現在已新增至伺服器，如圖所示。
    
    ![商務用 Skype Server 系統管理工具](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - **商務用 Skype Server 拓撲** 產生器用來建立、部署及管理拓撲的程式。
    
   - **商務用 Skype Server 控制台** 用來管理安裝的程式。
    

