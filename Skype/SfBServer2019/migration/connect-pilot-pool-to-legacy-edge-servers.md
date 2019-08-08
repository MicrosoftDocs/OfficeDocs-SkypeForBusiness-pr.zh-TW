---
title: 將試用版池連線到舊版 Edge 伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 部署商務用 Skype Server 2019 之後, 您必須為您的網站設定同盟路由。 若要使用舊版安裝所使用的同盟路由, 商務用 Skype Server 2019 必須設定為使用這個路線。
ms.openlocfilehash: 7a5a65e1488d5a119e3d11affbbaa9995a06626e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239551"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>將試用版池連線到舊版 Edge 伺服器

部署商務用 Skype Server 2019 之後, 您必須為您的網站設定同盟路由。 若要使用舊版安裝所使用的同盟路由, 商務用 Skype Server 2019 必須設定為使用這個路線。 
  
若要讓商務用 Skype Server 2019 網站使用舊版部署的控制器與邊緣伺服器, 請使用拓撲建立器建立舊版邊緣池的關聯。
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>使用拓撲建立器關聯舊版 Edge 池

1. 開啟拓撲建立器。 
    
2. 選取您的網站, 這會直接位於**商務用 Skype Server**節點的正下方。 
    
3. 在 [**動作**] 功能表上, 按一下 [**編輯屬性**]。
    
4. 在左窗格中, 選取 [**同盟路由**]。
    
5. 在 [**網站同盟路由指派**] 底下, 選取 [**啟用 SIP 同盟**], 然後選取舊版控制器或舊版 Edge 伺服器 (如果沒有列出任何導演)。
  
6. 按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。 
    
7. 在拓撲建立器中, 在商務用 Skype Server 2019 節點底下, 流覽至**標準版 server**或**Enterprise edition 前端池**, 以滑鼠右鍵按一下該池, 然後按一下 [**編輯屬性**]。
    
8. 在 [**關聯**性] 底下, 選取 [關聯邊緣池] 旁的核取方塊 **(適用于媒體元件)**。 
    
9. 從清單中選取舊版邊緣伺服器。 
  
10. 按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。 
    
11. 在 [**拓撲**建立器] 中, 選取最上方的節點, 即**商務用 Skype 伺服器**。
    
12. 在 [**動作**] 功能表中, 按一下 [**發佈拓撲**], 然後按一下 **[下一步]**。
    
13. **發佈嚮導**完成後, 請按一下 **[完成]**。
    

