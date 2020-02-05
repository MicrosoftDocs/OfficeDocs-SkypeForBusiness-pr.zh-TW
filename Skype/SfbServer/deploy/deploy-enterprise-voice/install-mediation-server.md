---
title: 在商務用 Skype Server 中安裝用於轉送服務伺服器的檔案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
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
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 摘要：瞭解如何在商務用 Skype Server 中安裝用於轉送作業伺服器的檔案。
ms.openlocfilehash: 4dc4c9971b74bf27d0f516ed70484646b666a845
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767116"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>在商務用 Skype Server 中安裝用於轉送服務伺服器的檔案
 
**摘要：** 瞭解如何在商務用 Skype Server 中安裝用於轉送轉送伺服器的檔案。
  
若要成功完成這個程式，您應該至少以本機系統管理員和至少擁有 RTCUniversalReadOnlyAdmins 群組成員資格的網域使用者的身分登入伺服器。
  
使用本主題中的步驟，執行商務用 Skype Server 部署嚮導，在您已使用拓撲建立器定義及發佈池之後，在您新增到轉送伺服器池中的電腦上安裝轉送服務伺服器的檔案。 在安裝檔轉送伺服器時，您也會安裝並指派中繼伺服器池中每個電腦所需的憑證。 
  
> [!NOTE]
> 本主題假設您已在您的拓撲中定義併發布獨立的轉送伺服器池，如在商務用 Skype Server 的 [拓撲建立器] 中[部署轉送伺服器](deploy-a-mediation-server.md)中所述。 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>若要為獨立的中繼伺服器池安裝檔案

1. 在安裝媒體中，以滑鼠右鍵按一下_ \<[\>安裝媒體_ **\Setup\amd64\Setup.exe**]，然後按一下 [**以系統管理員身分執行**]。
    
2. 在 [**安裝位置**] 頁面上，按一下 **[確定]**。
    
3. 在 [**使用者授權合約**] 頁面上，按一下 [**我接受**]，然後按一下 **[確定]**。 （需要才能繼續）。
    
4. 在 [**商務用 Skype Server 部署嚮導]** 頁面上，按一下 [**安裝或更新商務用 Skype server 系統**]。
    
5. 在 [**步驟1：安裝本機設定儲存區**] 旁，按一下 [**執行**]，然後依照畫面上的指示進行。
    
6. 在 [**設定中央管理儲存的本機複本**] 頁面上，接受 **[直接從中央管理存儲**的預設檢索]，然後按 **[下一步]**。
    
7. 在 [**執行命令**] 頁面上，當任務狀態顯示為 [**完成**] 時，按一下 **[完成]**。
    
8. 在 [**步驟2：設定] 或 [移除商務用 Skype 伺服器元件**] 旁，按一下 [**執行**]，然後按一下 **[下一步]**。
    
9. 在 [**執行命令**] 頁面上，當任務狀態顯示為 [**完成**] 時，按一下 **[完成]**。
    
10. 在**步驟3：要求、安裝或指派憑證**，按一下 [**執行**]。 依照畫面上的指示進行，接受預設設定。 中繼伺服器需要一個憑證，因此您執行的**步驟 3**兩次：一次是頒發所需的憑證，然後再將它指派給您。
    
11. 在證書已頒發並指派正確之後，在**步驟4：啟動服務**，按一下 [**執行**]，然後依照畫面上的指示進行。
    
12. 當**步驟 4**成功完成時，請重新開機伺服器，並以 DomainAdmins 群組成員的身分登入伺服器。
    
13. 在您執行商務用 Skype Server 控制台的電腦上，確認已將中繼伺服器的服務狀態顯示為綠色核取記號，並在商務用 Skype Server [控制台] 的 [**拓撲**] 頁面上進行驗證。 如果改為顯示紅色 X，請選取中繼伺服器。 在 [**動作**] 功能表上，按一下 [**啟動所有服務**]。 
    
如果您在中繼伺服器池中新增多個電腦，請在轉送伺服器池中的所有其他電腦上執行此程式中的步驟。 如果您不需要為任何其他電腦安裝轉送伺服器的檔案，請依照在[商務用 Skype server 中設定 trunks 中](configure-trunks.md)的程式來設定此中繼伺服器池（或網站上的所有中繼伺服器）與對等機之間的主幹連接設定。

