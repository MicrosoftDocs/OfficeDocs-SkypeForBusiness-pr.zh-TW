---
title: 在商務用 Skype Server 中設定與 Office Web Apps Server 的整合
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
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 摘要：請閱讀本主題，以瞭解如何設定 Office Web Apps 伺服器與商務用 Skype 伺服器之間的整合，以啟用適用于 Web 會議的 PowerPoint 簡報。
ms.openlocfilehash: b20646f31a7925ca66180c1580751574152047e5
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768346"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>在商務用 Skype Server 中設定與 Office Web Apps Server 的整合
 
**摘要：** 請閱讀本主題，瞭解如何設定 Office Web Apps 伺服器與商務用 Skype 伺服器之間的整合，以啟用適用于 Web 會議的 PowerPoint 簡報。
  
商務用 Skype 伺服器使用 Office Web Apps 伺服器來處理適用于 Web 會議的 PowerPoint 簡報。 如需此方法的優點資訊，請參閱[在商務用 Skype 伺服器中規劃會議](../../plan-your-deployment/conferencing/conferencing.md)。
  
在您可以將商務用 Skype Server 設定為使用 Office Web Apps Server 之前，您必須先確認已部署並設定 Office Web Apps 伺服器。 如需 Office Web Apps 伺服器的詳細資訊，請參閱[部署基礎結構： Office Online 伺服器](https://go.microsoft.com/fwlink/p/?linkid=257525)一文。 
  
成功安裝 Office Web Apps 伺服器並正確設定您的網站伺服器之後，您必須先將 Office Web Apps Server 探索 URL 新增至您的商務用 Skype 中，以設定商務用 Skype 伺服器與新伺服器通訊伺服器拓撲。 
  
> [!NOTE]
> Office Web Apps Server 的最新小版本命名為「Office Online Server」，而商務用 Skype Server 支援此伺服器。 如需詳細資訊，請參閱[Office Online Server 檔](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)。 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>設定商務用 Skype 伺服器與 Office Web Apps 伺服器進行通訊

若要將 Office Web Apps 伺服器新增到拓撲中，請完成下列步驟：
  
1. 開啟商務用 Skype Server 拓撲建立器。
    
2. 在 [**拓撲**建立器] 對話方塊中，選取 [**從現有的部署下載拓撲結構**]，然後按一下 **[確定]**。
    
3. 在 [**將拓朴儲存為**] 對話方塊中，于 **[檔案名]** 方塊中輸入拓撲檔的名稱（例如， **PreWebAppsServerTopology**），然後按一下 [**儲存**]。 如果您在新的拓撲中遇到問題，可在稍後檢索並重新發佈此拓撲。
    
4. 在 [拓撲建立器] 中，展開 [**商務用 Skype 伺服器**]，展開您網站的名稱，展開 [**企業版前端池**]，以滑鼠右鍵按一下其中一個池的名稱，然後按一下 [**編輯屬性**]。
    
5. 在 [**編輯屬性**] 對話方塊的 [**一般**] 索引標籤上，找到 [**關聯 Office Web Apps 伺服器**] 的 [標題]，然後按一下下拉式清單中的 [**新增**] （或選取現有的 Office Web Apps 伺服器）。
    
6. 在 [**定義新的 Office Web Apps 伺服器**] 對話方塊的 [ **Office WEB apps server FQDN** ] 方塊中，輸入您 office web apps server 電腦的完整功能變數名稱（FQDN）;當您這樣做時，您的 Office Web Apps 伺服器探索 URL 應該會自動輸入至 [ **Office Web Apps server 探索 url** ] 方塊中。
    
   - 如果 Office Web Apps 伺服器已安裝于內部部署，且位於與商務用 Skype Server 相同的網路區域中，則不應選取 [ **Office Web apps] 伺服器（也就是 [週邊/網際網路]）** 。
    
   - 如果 Office Web Apps 伺服器是在您的內部防火牆外部署，請選取 [ **Office Web Apps 伺服器] 部署在外部網路（也就是 [週邊/網際網路]）**。
    
7. 在 [**定義新的 Office Web Apps Server** ] 對話方塊中，按一下 **[確定]**，然後按一下 [**編輯屬性**] 對話方塊中的 **[確定**]。 然後，發現 URL 就會列為其中一個池的關聯。
    
您必須針對需要與您的 Office Web Apps 伺服器相關聯的每個池重複此程式。
  
將探索 URL 新增到拓撲之後，您必須接著發佈更新後的拓撲。 若要在拓撲建立器中執行此動作：
  
1. 按一下 [**動作**]，然後按一下 [**發佈拓撲**]。
    
2. 在 [發佈拓撲嚮導] 的 [**發佈拓撲**] 頁面上，按一下 **[下一步]**。
    
3. 在 [**發佈嚮導完成]** 頁面上，按一下 **[完成]**。
    
4. 關閉拓撲建立器。
    
## <a name="configure-access-for-external-users"></a>設定外部使用者的存取權

如果您想要將外部使用者（也就是從組織外的防火牆以外的使用者登入），若要存取 Office Web Apps Server PowerPoint 簡報，就必須使用 Office Web Apps Server 和反向 proxy 伺服器。 您也需要建立並設定網站發佈規則，這將有助於確保使用者能夠連線到伺服器。 
  
## <a name="validate-the-configuration"></a>驗證配置

在已將 Office Web Apps 伺服器新增到拓撲之後，且在該拓撲發佈之後，您應該會在商務用 Skype Server 事件記錄檔中看到兩個新的事件記錄事件。 首先，應該新增 LS 資料 MCU 事件（事件 ID 41034）;這個事件會報告已發現 Office Web Apps 伺服器：
  
 **已發現 Web 會議 Server Office Web Apps Server，已啟用 PowerPoint 內容。**
  
此外，您還會看到另一個 [LS 資料 MCU] 事件（事件 ID 41032），該事件會傳回 Office Web Apps Server Url。 例如，您應該會看到類似以下的內容：
  
 **網路會議服務器 Office Web Apps 伺服器探索已成功完成。**
  
 **Office Web Apps Server 內部簡報者頁面https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp：; embed =**
  
 **Office Web Apps 伺服器內部出席者頁面： https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp; embed = true&amp;=**
  
如果您已設定外部使用者的存取權，您也會看到類似以下的內容：
  
 **Office Web Apps Server 外部簡報者頁面https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp：; 內嵌**
  
 **Office Web Apps 伺服器內部出席者頁面： <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>;**
  
如果您看到 LS 資料 MCU 事件，且事件 ID 為41033，表示 Office Web Apps Server 發現失敗。 在這種情況下，商務用 Skype 伺服器會根據需要嘗試許多次數，以探索新設定的 Office Web Apps 伺服器。 如果探索程式重複失敗，您應該從拓撲檔中移除 Office Web Apps 伺服器、發佈更新的拓撲，然後在連線問題解決之後，嘗試將 Office Web Apps 伺服器新增到拓撲結構。
  
如果 Office Web Apps 伺服器出現正確設定，且已被探索程式辨識，您可以在一對商務用 Skype 用戶端之間共用 PowerPoint 簡報，以驗證 Office Web Apps 伺服器是否如期運作。 如果使用者 A 可以載入並顯示 PowerPoint 簡報，而使用者 B 可以接著加入會議，然後查看該簡報，則 Office Web Apps Server 就能正常運作。
  
即使 Office Web Apps 伺服器的設定正確，您也可能會在嘗試共用 PowerPoint 簡報時，收到「由於伺服器連線問題，有些共用功能無法使用」錯誤訊息。 如果您收到該錯誤訊息，您應該重新開機與新的 Office Web Apps 伺服器相關聯的前端伺服器（或伺服器）。
  

