---
title: 在商務用 Skype Server 中安裝轉送伺服器的檔案
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
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
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 摘要：瞭解如何在商務用 Skype Server 中安裝轉送伺服器的檔案。
ms.openlocfilehash: 5662e4e79534fd469c64005bba98d1c507defff8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620499"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a>在商務用 Skype Server 中安裝轉送伺服器的檔案
 
**摘要：** 瞭解如何在商務用 Skype Server 中安裝轉送伺服器的檔案。
  
若要順利完成此程式，您應該至少以本機系統管理員身分登入伺服器，以及至少擁有 RTCUniversalReadOnlyAdmins 群組成員資格的網域使用者。
  
使用本主題中的步驟執行商務用 Skype Server 部署嚮導，以在您已使用拓撲產生器來定義及發行集區之後，于已新增至轉送伺服器集區的電腦上，安裝轉送伺服器的檔案。 在安裝檔轉送伺服器時，您也會安裝並指派轉送伺服器集區中每一部電腦所需的憑證。 
  
> [!NOTE]
> 本主題假設您已在拓撲中定義及發行獨立的轉送伺服器集區（如在商務用 Skype Server 的拓撲產生器中[部署轉送伺服器](deploy-a-mediation-server.md)所述）。 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>若要為獨立的轉送伺服器集區安裝檔案

1. 在安裝媒體中，以滑鼠右鍵按一下 [  _\<installation media\>_ **\Setup\amd64\Setup.exe**]，然後按一下 [以 **系統管理員身分執行**]。
    
2. 在 [ **安裝位置** ] 頁面上，按一下 **[確定]**。
    
3. 在 [ **使用者授權合約** ] 頁面上，按一下 [ **我接受**]，然後按一下 **[確定]**。 需要 (才能繼續。 ) 
    
4. 在 [**商務用 Skype Server 部署嚮導]** 頁面上，按一下 [**安裝或更新商務用 Skype Server 系統**]。
    
5. 在 [ **步驟1：安裝本機設定存放區**] 旁邊，按一下 [ **執行**]，然後依照畫面上的指示進行。
    
6. 在 [ **設定中央管理存放區的本機複本** ] 頁面上，接受 **直接從中央管理存放區進行** 的預設檢索，然後按 **[下一步]**。
    
7. 在 [ **執行命令** ] 頁面上，當工作狀態顯示為 [ **已完成**] 時，按一下 **[完成]**。
    
8. 在 [**步驟2：安裝或移除商務用 Skype Server 元件**] 旁，按一下 [**執行**]，然後按 **[下一步]**。
    
9. 在 [ **執行命令** ] 頁面上，當工作狀態顯示為 [ **已完成**] 時，按一下 **[完成]**。
    
10. 在 [ **步驟3：要求、安裝或指派憑證**] 旁邊，按一下 [ **執行**]。 依照畫面上的指示，接受預設設定。 轉送伺服器需要一個憑證，因此您將執行 **步驟 3** 兩次：一次發出必要的憑證，再進行指派。
    
11. 當憑證已正確發行並指派正確時，在 [ **步驟4：啟動服務**] 旁邊，按一下 [ **執行**]，然後依照畫面上的指示進行。
    
12. 當 **步驟 4** 成功完成後，請重新開機伺服器，並以 DomainAdmins 群組成員的身分登入伺服器。
    
13. 在您執行商務用 Skype Server 控制台的電腦上，確認轉送伺服器的服務狀態顯示為綠色核取記號，請在商務用 Skype Server 控制台的 [**拓撲**] 頁面上進行確認。 若改為顯示紅色 X，請選取轉送伺服器。 在 [ **動作** ] 功能表上，按一下 [ **啟動所有服務**]。 
    
如果您已將一部以上的電腦新增至轉送伺服器集區，請在轉送伺服器集區中的所有其他電腦上，執行此程式中的步驟。 如果您不需要為其他任何電腦安裝轉送伺服器的檔案，請遵循[configure 主幹 in 商務用 Skype Server 中](configure-trunks.md)的程式，來設定此轉送伺服器集區 (或所有轉送伺服器（位於網站) 及其對等電腦之間）的設定。

